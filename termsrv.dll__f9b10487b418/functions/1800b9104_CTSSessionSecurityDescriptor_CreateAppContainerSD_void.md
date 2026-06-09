# CTSSessionSecurityDescriptor::CreateAppContainerSD(void)

- ea: `0x1800b9104`
- end: `0x1800b925b`
- name: `?CreateAppContainerSD@CTSSessionSecurityDescriptor@@IEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(CTSSessionSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800532dc`

## callees

- `0x18000a210`
- `0x180015dcc`
- `0x1800321d4`
- `0x18009c868`
- `0x18009c940`
- `0x18009caac`
- `0x1800b8f58`
- `0x1800b9104`
- `0x1800b9370`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b9229`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b9238`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b9229`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b9238`

## string_xrefs

- `0x1800b9188`: `CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s`
- `0x1800b920c`: `CTSSessionSecurityDescriptor::CreateAppContainerSD`
- `0x1800b916d`: `CUtils::CreateLPACCapabilitySid() failed: 0x%x in %s`
- `0x1800b9152`: `CUtils::CreateAppContainerSid() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSessionSecurityDescriptor::CreateAppContainerSD(CTSSessionSecurityDescriptor *this)
{
  CTSSecurityDescriptor *v1; // rdi
  void *v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  PSID pSid; // [rsp+40h] [rbp+20h] BYREF
  PSID Sid; // [rsp+48h] [rbp+28h] BYREF
  void *Block; // [rsp+50h] [rbp+30h] BYREF

  v1 = (CTSSessionSecurityDescriptor *)((char *)this + 8);
  pSid = 0;
  Sid = 0;
  v3 = (void *)*((_QWORD *)this + 2);
  Block = 0;
  CUtils::CleanupSD(v3);
  *((_QWORD *)v1 + 1) = 0;
  v4 = CUtils::CreateAppContainerSid(&pSid);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = CUtils::CreateLPACCapabilitySid(&Sid);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = CUtils::CreateUserSignInCapabilitySID(&Block);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v8 = CTSSecurityDescriptor::InitializeFromBlob(v1, *((void **)this + 5));
        v5 = v8;
        if ( v8 >= 0 )
        {
          v9 = CTSSecurityDescriptor::AddUserAce(v1, pSid, 1u);
          v5 = v9;
          if ( v9 >= 0 )
          {
            v10 = CTSSecurityDescriptor::AddUserAce(v1, Sid, 1u);
            v5 = v10;
            if ( v10 >= 0 )
            {
              v11 = CTSSecurityDescriptor::AddUserAce(v1, Block, 9u);
              v5 = v11;
              if ( v11 < 0 )
                _DbgPrintMessage(
                  8,
                  "m_AppContainerSD.AddUserAce() - UserSignIn failed: 0x%x in %s",
                  (unsigned int)v11,
                  "CTSSessionSecurityDescriptor::CreateAppContainerSD");
            }
            else
            {
              _DbgPrintMessage(
                8,
                "m_AppContainerSD.AddUserAce() - LPAC failed: 0x%x in %s",
                (unsigned int)v10,
                "CTSSessionSecurityDescriptor::CreateAppContainerSD");
            }
          }
          else
          {
            _DbgPrintMessage(
              8,
              "m_AppContainerSD.AddUserAce() - AnyPackage failed: 0x%x in %s",
              (unsigned int)v9,
              "CTSSessionSecurityDescriptor::CreateAppContainerSD");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "m_AppContainerSD.Initialize() failed: 0x%x in %s",
            (unsigned int)v8,
            "CTSSessionSecurityDescriptor::CreateAppContainerSD");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s",
          (unsigned int)v7,
          "CTSSessionSecurityDescriptor::CreateAppContainerSD");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CUtils::CreateLPACCapabilitySid() failed: 0x%x in %s",
        (unsigned int)v6,
        "CTSSessionSecurityDescriptor::CreateAppContainerSD");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateAppContainerSid() failed: 0x%x in %s",
      (unsigned int)v4,
      "CTSSessionSecurityDescriptor::CreateAppContainerSD");
  }
  if ( pSid )
    FreeSid(pSid);
  if ( Sid )
    FreeSid(Sid);
  if ( Block )
    operator delete(Block);
  return v5;
}

```

## disassembly

```asm
0x1800b9104  mov     [rsp-18h+arg_18], rbx
0x1800b9109  push    rbp
0x1800b910a  push    rsi
0x1800b910b  push    rdi
0x1800b910c  mov     rbp, rsp
0x1800b910f  sub     rsp, 20h
0x1800b9113  lea     rdi, [rcx+8]
0x1800b9117  mov     [rbp+pSid], 0
0x1800b911f  mov     rsi, rcx
0x1800b9122  mov     [rbp+Sid], 0
0x1800b912a  mov     rcx, [rdi+8]; hMem
0x1800b912e  mov     [rbp+Block], 0
0x1800b9136  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800b913b  lea     rcx, [rbp+pSid]; pSid
0x1800b913f  mov     qword ptr [rdi+8], 0
0x1800b9147  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x1800b914c  mov     ebx, eax
0x1800b914e  test    eax, eax
0x1800b9150  jns     short loc_1800B915E
0x1800b9152  lea     rdx, aCutilsCreateap_0; "CUtils::CreateAppContainerSid() failed:"...
0x1800b9159  jmp     loc_1800B920C
0x1800b915e  lea     rcx, [rbp+Sid]; Sid
0x1800b9162  call    ?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateLPACCapabilitySid(void * *)
0x1800b9167  mov     ebx, eax
0x1800b9169  test    eax, eax
0x1800b916b  jns     short loc_1800B9179
0x1800b916d  lea     rdx, aCutilsCreatelp_1; "CUtils::CreateLPACCapabilitySid() faile"...
0x1800b9174  jmp     loc_1800B920C
0x1800b9179  lea     rcx, [rbp+Block]; void **
0x1800b917d  call    ?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z; CUtils::CreateUserSignInCapabilitySID(void * *)
0x1800b9182  mov     ebx, eax
0x1800b9184  test    eax, eax
0x1800b9186  jns     short loc_1800B9191
0x1800b9188  lea     rdx, aCutilsCreateus_0; "CUtils::CreateUserSignInCapabilitySID()"...
0x1800b918f  jmp     short loc_1800B920C
0x1800b9191  mov     rdx, [rsi+28h]; void *
0x1800b9195  mov     rcx, rdi; this
0x1800b9198  call    ?InitializeFromBlob@CTSSecurityDescriptor@@QEAAJPEAX@Z; CTSSecurityDescriptor::InitializeFromBlob(void *)
0x1800b919d  mov     ebx, eax
0x1800b919f  test    eax, eax
0x1800b91a1  jns     short loc_1800B91AC
0x1800b91a3  lea     rdx, aMAppcontainers_2; "m_AppContainerSD.Initialize() failed: 0"...
0x1800b91aa  jmp     short loc_1800B920C
0x1800b91ac  mov     rdx, [rbp+pSid]; void *
0x1800b91b0  mov     esi, 1
0x1800b91b5  mov     r8d, esi; unsigned int
0x1800b91b8  mov     rcx, rdi; this
0x1800b91bb  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x1800b91c0  mov     ebx, eax
0x1800b91c2  test    eax, eax
0x1800b91c4  jns     short loc_1800B91CF
0x1800b91c6  lea     rdx, aMAppcontainers_1; "m_AppContainerSD.AddUserAce() - AnyPack"...
0x1800b91cd  jmp     short loc_1800B920C
0x1800b91cf  mov     rdx, [rbp+Sid]; void *
0x1800b91d3  mov     r8d, esi; unsigned int
0x1800b91d6  mov     rcx, rdi; this
0x1800b91d9  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x1800b91de  mov     ebx, eax
0x1800b91e0  test    eax, eax
0x1800b91e2  jns     short loc_1800B91ED
0x1800b91e4  lea     rdx, aMAppcontainers_0; "m_AppContainerSD.AddUserAce() - LPAC fa"...
0x1800b91eb  jmp     short loc_1800B920C
0x1800b91ed  mov     rdx, [rbp+Block]; void *
0x1800b91f1  mov     r8d, 9; unsigned int
0x1800b91f7  mov     rcx, rdi; this
0x1800b91fa  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x1800b91ff  mov     ebx, eax
0x1800b9201  test    eax, eax
0x1800b9203  jns     short loc_1800B9220
0x1800b9205  lea     rdx, aMAppcontainers; "m_AppContainerSD.AddUserAce() - UserSig"...
0x1800b920c  lea     r9, aCtssessionsecu; "CTSSessionSecurityDescriptor::CreateApp"...
0x1800b9213  mov     r8d, eax
0x1800b9216  mov     ecx, 8; int
0x1800b921b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800b9220  mov     rcx, [rbp+pSid]; pSid
0x1800b9224  test    rcx, rcx
0x1800b9227  jz      short loc_1800B922F
0x1800b9229  call    cs:__imp_FreeSid
0x1800b922f  mov     rcx, [rbp+Sid]; pSid
0x1800b9233  test    rcx, rcx
0x1800b9236  jz      short loc_1800B923E
0x1800b9238  call    cs:__imp_FreeSid
0x1800b923e  mov     rcx, [rbp+Block]; Block
0x1800b9242  test    rcx, rcx
0x1800b9245  jz      short loc_1800B924C
0x1800b9247  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b924c  mov     eax, ebx
0x1800b924e  mov     rbx, [rsp+20h+arg_18]
0x1800b9253  add     rsp, 20h
0x1800b9257  pop     rdi
0x1800b9258  pop     rsi
0x1800b9259  pop     rbp
0x1800b925a  retn
```
