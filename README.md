using System.DirectoryServices.AccountManagement;

private static bool IsInGroup(string ingroup)
        {
            string username = Environment.UserName;

            PrincipalContext domainctx = new PrincipalContext(ContextType.Domain,
                                                        "example",
                                                        "DC=example,DC=com");

            UserPrincipal userPrincipal =
                              UserPrincipal.FindByIdentity(domainctx, IdentityType.SamAccountName, username);

            bool isMember = userPrincipal.IsMemberOf(domainctx, IdentityType.Name, ingroup);

            return isMember;
        }
