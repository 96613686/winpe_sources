# RpcServer::UserGroupCheck(ulong,User const &,User const &)

- ea: `0x1800534c8`
- end: `0x1800535d6`
- name: `?UserGroupCheck@RpcServer@@CA_NKAEBVUser@@0@Z`
- size: `270`
- prototype: `bool __fastcall(DWORD SessionId, const struct User *, const struct User *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e9d0`

## callees

- `0x18000fe50`
- `0x180024730`
- `0x180045120`
- `0x1800534c8`
- `0x180053d9c`
- `0x180054130`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005357d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005357d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18005355a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18005355a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180053535`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180053535`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall RpcServer::UserGroupCheck(DWORD SessionId, const struct User *a2, const struct User *this)
{
  bool v6; // bl
  void *DuplicateTokenHandle; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  void *phToken; // [rsp+30h] [rbp-18h] BYREF
  PSID SidToCheck; // [rsp+38h] [rbp-10h] BYREF
  WINBOOL IsMember; // [rsp+88h] [rbp+40h] BYREF

  v9 = 0;
  if ( (int)User::FromUserSession((struct User *)&v9, SessionId, this) >= 0 )
  {
    if ( (unsigned __int8)User::operator==((User *)&v9, a2) )
    {
      SidToCheck = 0;
      if ( (int)User::LookupSid(this, &SidToCheck) >= 0 )
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
0x1800534c8  push    rbp
0x1800534ca  push    rbx
0x1800534cb  push    rsi
0x1800534cc  push    rdi
0x1800534cd  mov     rbp, rsp
0x1800534d0  sub     rsp, 48h
0x1800534d4  mov     rdi, r8
0x1800534d7  mov     rsi, rdx
0x1800534da  mov     ebx, ecx
0x1800534dc  mov     [rbp+var_20], 0
0x1800534e4  mov     edx, ecx; SessionId
0x1800534e6  lea     rcx, [rbp+var_20]; this
0x1800534ea  call    ?FromUserSession@User@@SAJAEAV1@KPEAX@Z; User::FromUserSession(User &,ulong,void *)
0x1800534ef  test    eax, eax
0x1800534f1  js      loc_1800535C1
0x1800534f7  mov     rdx, rsi; User *
0x1800534fa  lea     rcx, [rbp+var_20]; this
0x1800534fe  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x180053503  test    al, al
0x180053505  jz      loc_1800535C1
0x18005350b  mov     [rbp+SidToCheck], 0
0x180053513  lea     rdx, [rbp+SidToCheck]; void **
0x180053517  mov     rcx, rdi; this
0x18005351a  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x18005351f  test    eax, eax
0x180053521  js      loc_1800535C1
0x180053527  mov     [rbp+phToken], 0
0x18005352f  lea     rdx, [rbp+phToken]; phToken
0x180053533  mov     ecx, ebx; SessionId
0x180053535  call    cs:__imp_WTSQueryUserToken
0x18005353c  nop     dword ptr [rax+rax+00h]
0x180053541  test    eax, eax
0x180053543  jz      short loc_1800535A8
0x180053545  mov     [rbp+DuplicateTokenHandle], 0
0x18005354d  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x180053551  mov     edx, 1; ImpersonationLevel
0x180053556  mov     rcx, [rbp+phToken]; ExistingTokenHandle
0x18005355a  call    cs:__imp_DuplicateToken
0x180053561  nop     dword ptr [rax+rax+00h]
0x180053566  test    eax, eax
0x180053568  jz      short loc_18005359F
0x18005356a  mov     [rbp+IsMember], 0
0x180053571  lea     r8, [rbp+IsMember]; IsMember
0x180053575  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180053579  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18005357d  call    cs:__imp_CheckTokenMembership
0x180053584  nop     dword ptr [rax+rax+00h]
0x180053589  test    eax, eax
0x18005358b  jz      short loc_18005359F
0x18005358d  cmp     [rbp+IsMember], 0
0x180053591  setnz   bl
0x180053594  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x180053598  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18005359d  jmp     short loc_1800535AA
0x18005359f  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x1800535a3  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x1800535a8  xor     bl, bl
0x1800535aa  lea     rcx, [rbp+phToken]; this
0x1800535ae  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x1800535b3  nop
0x1800535b4  lea     rcx, [rbp+var_20]
0x1800535b8  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800535bd  mov     al, bl
0x1800535bf  jmp     short loc_1800535CC
0x1800535c1  lea     rcx, [rbp+var_20]
0x1800535c5  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800535ca  xor     al, al
0x1800535cc  add     rsp, 48h
0x1800535d0  pop     rdi
0x1800535d1  pop     rsi
0x1800535d2  pop     rbx
0x1800535d3  pop     rbp
0x1800535d4  retn
```
