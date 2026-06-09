# RpcServer::UserGroupCheck(ulong,User const &,User const &)

- ea: `0x180050f58`
- end: `0x180051053`
- name: `?UserGroupCheck@RpcServer@@CA_NKAEBVUser@@0@Z`
- size: `251`
- prototype: `bool __fastcall(DWORD SessionId, const struct User *, const struct User *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c6d0`

## callees

- `0x18000b4e0`
- `0x180039d00`
- `0x180042fa4`
- `0x180050f58`
- `0x1800517ec`
- `0x180051b3c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180051001`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180051001`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180050fe4`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180050fe4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180050fc5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180050fc5`

## pseudocode

```c
bool __fastcall RpcServer::UserGroupCheck(DWORD SessionId, const struct User *a2, const struct User *a3)
{
  bool v6; // bl
  void *DuplicateTokenHandle; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  void *phToken; // [rsp+30h] [rbp-18h] BYREF
  PSID SidToCheck; // [rsp+38h] [rbp-10h] BYREF
  WINBOOL IsMember; // [rsp+88h] [rbp+40h] BYREF

  v9 = 0;
  if ( (int)User::FromUserSession((struct User *)&v9, SessionId, a3) >= 0 )
  {
    if ( (unsigned __int8)User::operator==(&v9, a2) )
    {
      SidToCheck = 0;
      if ( (int)User::LookupSid(a3, &SidToCheck) >= 0 )
      {
        phToken = 0;
        if ( WTSQueryUserToken(SessionId, &phToken) )
        {
          DuplicateTokenHandle = 0;
          if ( DuplicateToken(phToken, SecurityIdentification, &DuplicateTokenHandle) )
          {
            IsMember = 0;
            if ( CheckTokenMembership(DuplicateTokenHandle, SidToCheck, &IsMember) )
            {
              v6 = IsMember != 0;
              wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&DuplicateTokenHandle);
LABEL_10:
              wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&phToken);
              wmi::AutoRef<User::UserEntry>::Release(&v9);
              return v6;
            }
          }
          wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&DuplicateTokenHandle);
        }
        v6 = 0;
        goto LABEL_10;
      }
    }
  }
  wmi::AutoRef<User::UserEntry>::Release(&v9);
  return 0;
}

```

## disassembly

```asm
0x180050f58  push    rbp
0x180050f5a  push    rbx
0x180050f5b  push    rsi
0x180050f5c  push    rdi
0x180050f5d  mov     rbp, rsp
0x180050f60  sub     rsp, 48h
0x180050f64  mov     rdi, r8
0x180050f67  mov     rsi, rdx
0x180050f6a  mov     ebx, ecx
0x180050f6c  mov     [rbp+var_20], 0
0x180050f74  mov     edx, ecx; SessionId
0x180050f76  lea     rcx, [rbp+var_20]; this
0x180050f7a  call    ?FromUserSession@User@@SAJAEAV1@KPEAX@Z; User::FromUserSession(User &,ulong,void *)
0x180050f7f  test    eax, eax
0x180050f81  js      loc_18005103F
0x180050f87  mov     rdx, rsi
0x180050f8a  lea     rcx, [rbp+var_20]
0x180050f8e  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x180050f93  test    al, al
0x180050f95  jz      loc_18005103F
0x180050f9b  mov     [rbp+SidToCheck], 0
0x180050fa3  lea     rdx, [rbp+SidToCheck]; void **
0x180050fa7  mov     rcx, rdi; this
0x180050faa  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x180050faf  test    eax, eax
0x180050fb1  js      loc_18005103F
0x180050fb7  mov     [rbp+phToken], 0
0x180050fbf  lea     rdx, [rbp+phToken]; phToken
0x180050fc3  mov     ecx, ebx; SessionId
0x180050fc5  call    cs:__imp_WTSQueryUserToken
0x180050fcb  test    eax, eax
0x180050fcd  jz      short loc_180051026
0x180050fcf  mov     [rbp+DuplicateTokenHandle], 0
0x180050fd7  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x180050fdb  mov     edx, 1; ImpersonationLevel
0x180050fe0  mov     rcx, [rbp+phToken]; ExistingTokenHandle
0x180050fe4  call    cs:__imp_DuplicateToken
0x180050fea  test    eax, eax
0x180050fec  jz      short loc_18005101D
0x180050fee  mov     [rbp+IsMember], 0
0x180050ff5  lea     r8, [rbp+IsMember]; IsMember
0x180050ff9  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180050ffd  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x180051001  call    cs:__imp_CheckTokenMembership
0x180051007  test    eax, eax
0x180051009  jz      short loc_18005101D
0x18005100b  cmp     [rbp+IsMember], 0
0x18005100f  setnz   bl
0x180051012  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x180051016  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18005101b  jmp     short loc_180051028
0x18005101d  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x180051021  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180051026  xor     bl, bl
0x180051028  lea     rcx, [rbp+phToken]; this
0x18005102c  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180051031  nop
0x180051032  lea     rcx, [rbp+var_20]
0x180051036  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18005103b  mov     al, bl
0x18005103d  jmp     short loc_18005104A
0x18005103f  lea     rcx, [rbp+var_20]
0x180051043  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180051048  xor     al, al
0x18005104a  add     rsp, 48h
0x18005104e  pop     rdi
0x18005104f  pop     rsi
0x180051050  pop     rbx
0x180051051  pop     rbp
0x180051052  retn
```
