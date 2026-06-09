# CTSSessionSecurityDescriptor::CreateAppContainerSD(void)

- ea: `0x1800bfa4c`
- end: `0x1800bfbb0`
- name: `?CreateAppContainerSD@CTSSessionSecurityDescriptor@@IEAAJXZ`
- size: `356`
- prototype: `__int64 __fastcall(CTSSessionSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180055a3c`

## callees

- `0x180009940`
- `0x1800168c0`
- `0x180033f44`
- `0x1800a0b34`
- `0x1800a0c18`
- `0x1800a0dc0`
- `0x1800bf878`
- `0x1800bfa4c`
- `0x1800bfcd8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bfb71`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bfb86`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bfb71`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bfb86`

## string_xrefs

- `0x1800bfad0`: `CUtils::CreateUserSignInCapabilitySID() failed: 0x%x in %s`
- `0x1800bfb54`: `CTSSessionSecurityDescriptor::CreateAppContainerSD`
- `0x1800bfab5`: `CUtils::CreateLPACCapabilitySid() failed: 0x%x in %s`
- `0x1800bfa9a`: `CUtils::CreateAppContainerSid() failed: 0x%x in %s`

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
0x1800bfa4c  mov     [rsp-18h+arg_18], rbx
0x1800bfa51  push    rbp
0x1800bfa52  push    rsi
0x1800bfa53  push    rdi
0x1800bfa54  mov     rbp, rsp
0x1800bfa57  sub     rsp, 20h
0x1800bfa5b  lea     rdi, [rcx+8]
0x1800bfa5f  mov     [rbp+pSid], 0
0x1800bfa67  mov     rsi, rcx
0x1800bfa6a  mov     [rbp+Sid], 0
0x1800bfa72  mov     rcx, [rdi+8]; hMem
0x1800bfa76  mov     [rbp+Block], 0
0x1800bfa7e  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800bfa83  lea     rcx, [rbp+pSid]; pSid
0x1800bfa87  mov     qword ptr [rdi+8], 0
0x1800bfa8f  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x1800bfa94  mov     ebx, eax
0x1800bfa96  test    eax, eax
0x1800bfa98  jns     short loc_1800BFAA6
0x1800bfa9a  lea     rdx, aCutilsCreateap_0; "CUtils::CreateAppContainerSid() failed:"...
0x1800bfaa1  jmp     loc_1800BFB54
0x1800bfaa6  lea     rcx, [rbp+Sid]; Sid
0x1800bfaaa  call    ?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateLPACCapabilitySid(void * *)
0x1800bfaaf  mov     ebx, eax
0x1800bfab1  test    eax, eax
0x1800bfab3  jns     short loc_1800BFAC1
0x1800bfab5  lea     rdx, aCutilsCreatelp_1; "CUtils::CreateLPACCapabilitySid() faile"...
0x1800bfabc  jmp     loc_1800BFB54
0x1800bfac1  lea     rcx, [rbp+Block]; void **
0x1800bfac5  call    ?CreateUserSignInCapabilitySID@CUtils@@SAJPEAPEAX@Z; CUtils::CreateUserSignInCapabilitySID(void * *)
0x1800bfaca  mov     ebx, eax
0x1800bfacc  test    eax, eax
0x1800bface  jns     short loc_1800BFAD9
0x1800bfad0  lea     rdx, aCutilsCreateus_0; "CUtils::CreateUserSignInCapabilitySID()"...
0x1800bfad7  jmp     short loc_1800BFB54
0x1800bfad9  mov     rdx, [rsi+28h]; void *
0x1800bfadd  mov     rcx, rdi; this
0x1800bfae0  call    ?InitializeFromBlob@CTSSecurityDescriptor@@QEAAJPEAX@Z; CTSSecurityDescriptor::InitializeFromBlob(void *)
0x1800bfae5  mov     ebx, eax
0x1800bfae7  test    eax, eax
0x1800bfae9  jns     short loc_1800BFAF4
0x1800bfaeb  lea     rdx, aMAppcontainers_2; "m_AppContainerSD.Initialize() failed: 0"...
0x1800bfaf2  jmp     short loc_1800BFB54
0x1800bfaf4  mov     rdx, [rbp+pSid]; void *
0x1800bfaf8  mov     esi, 1
0x1800bfafd  mov     r8d, esi; unsigned int
0x1800bfb00  mov     rcx, rdi; this
0x1800bfb03  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x1800bfb08  mov     ebx, eax
0x1800bfb0a  test    eax, eax
0x1800bfb0c  jns     short loc_1800BFB17
0x1800bfb0e  lea     rdx, aMAppcontainers_1; "m_AppContainerSD.AddUserAce() - AnyPack"...
0x1800bfb15  jmp     short loc_1800BFB54
0x1800bfb17  mov     rdx, [rbp+Sid]; void *
0x1800bfb1b  mov     r8d, esi; unsigned int
0x1800bfb1e  mov     rcx, rdi; this
0x1800bfb21  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x1800bfb26  mov     ebx, eax
0x1800bfb28  test    eax, eax
0x1800bfb2a  jns     short loc_1800BFB35
0x1800bfb2c  lea     rdx, aMAppcontainers_0; "m_AppContainerSD.AddUserAce() - LPAC fa"...
0x1800bfb33  jmp     short loc_1800BFB54
0x1800bfb35  mov     rdx, [rbp+Block]; void *
0x1800bfb39  mov     r8d, 9; unsigned int
0x1800bfb3f  mov     rcx, rdi; this
0x1800bfb42  call    ?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z; CTSSecurityDescriptor::AddUserAce(void *,ulong)
0x1800bfb47  mov     ebx, eax
0x1800bfb49  test    eax, eax
0x1800bfb4b  jns     short loc_1800BFB68
0x1800bfb4d  lea     rdx, aMAppcontainers; "m_AppContainerSD.AddUserAce() - UserSig"...
0x1800bfb54  lea     r9, aCtssessionsecu; "CTSSessionSecurityDescriptor::CreateApp"...
0x1800bfb5b  mov     r8d, eax
0x1800bfb5e  mov     ecx, 8; int
0x1800bfb63  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800bfb68  mov     rcx, [rbp+pSid]; pSid
0x1800bfb6c  test    rcx, rcx
0x1800bfb6f  jz      short loc_1800BFB7D
0x1800bfb71  call    cs:__imp_FreeSid
0x1800bfb78  nop     dword ptr [rax+rax+00h]
0x1800bfb7d  mov     rcx, [rbp+Sid]; pSid
0x1800bfb81  test    rcx, rcx
0x1800bfb84  jz      short loc_1800BFB92
0x1800bfb86  call    cs:__imp_FreeSid
0x1800bfb8d  nop     dword ptr [rax+rax+00h]
0x1800bfb92  mov     rcx, [rbp+Block]; Block
0x1800bfb96  test    rcx, rcx
0x1800bfb99  jz      short loc_1800BFBA0
0x1800bfb9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800bfba0  mov     eax, ebx
0x1800bfba2  mov     rbx, [rsp+20h+arg_18]
0x1800bfba7  add     rsp, 20h
0x1800bfbab  pop     rdi
0x1800bfbac  pop     rsi
0x1800bfbad  pop     rbp
0x1800bfbae  retn
```
