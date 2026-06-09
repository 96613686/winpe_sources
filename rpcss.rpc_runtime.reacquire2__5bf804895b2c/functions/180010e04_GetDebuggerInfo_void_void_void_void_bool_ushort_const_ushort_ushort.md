# GetDebuggerInfo(void *,void *,void *,void *,bool,ushort const *,ushort * *,ushort * *)

- ea: `0x180010e04`
- end: `0x180011116`
- name: `?GetDebuggerInfo@@YAJPEAX000_NPEBGPEAPEAG3@Z`
- size: `786`
- prototype: `__int64 __usercall@<rax>(HANDLE hToken@<rcx>, void *@<rdx>, void *@<r8>, void *@<r9>, bool, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004c4b0`
- `0x18004e578`

## callees

- `0x18000ce5c`
- `0x180010e04`
- `0x18001111c`
- `0x180011258`
- `0x1800210f8`
- `0x180093f20`
- `0x180095c0c`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `ntdll!RtlQueryPackageIdentity` at `0x180010e8f`
- `ntdll!RtlQueryPackageIdentity` at `0x180010e8f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180010f59`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180010fdf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011024`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001103e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011085`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180010f59`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180010fdf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011024`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001103e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180011085`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800110d4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800110e5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800110d4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800110e5`

## string_xrefs

- `0x180010ee5`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180010fb2`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18001105d`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800110aa`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800110fd`: `onecore\com\combase\rpcss\olescm\launch.cxx`

## pseudocode

```c
int __fastcall GetDebuggerInfo(
        HANDLE hToken,
        void *a2,
        void *a3,
        void *a4,
        bool a5,
        unsigned __int16 *a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  char v8; // di
  int v11; // eax
  unsigned int v12; // r8d
  unsigned __int64 v13; // rcx
  int ExeComponent; // ebx
  __int64 v15; // rdx
  int DebuggerInfoForUser; // eax
  const char *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  const char *v21; // r9
  int *v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  int v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h]
  PSID v27; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v28[72]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v29[128]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v30[264]; // [rsp+1F0h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  v8 = 0;
  v27 = a4;
  Sid = a2;
  if ( !a6 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(hToken);
    v15 = 203;
    ExeComponent = -2147024809;
    goto LABEL_7;
  }
  v22 = v24;
  v25 = 256;
  *(_QWORD *)v24 = 132;
  v11 = RtlQueryPackageIdentity(hToken, v29, &v25, v28);
  if ( v11 < 0 )
  {
    if ( v11 == -1073741275 )
      return 0;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x105,
             (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
             (const char *)(unsigned int)v11,
             (int)v24);
  }
  else
  {
    memset_0(v30, 0, 0x208u);
    v13 = -1;
    do
      ++v13;
    while ( a6[v13] );
    ExeComponent = FindExeComponent(v13, a6, v12, v30);
    if ( ExeComponent < 0 )
    {
      v15 = 212;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)ExeComponent,
        (int)v22);
      return ExeComponent;
    }
    if ( a5 )
      goto LABEL_10;
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v8 = 1;
LABEL_10:
      DebuggerInfoForUser = GetDebuggerInfoForUser(Sid, v29, v28, v30, a7, a8);
      if ( DebuggerInfoForUser == -2147024894 && a3 )
      {
        if ( !ImpersonateLoggedOnUser(a3) )
        {
          ExeComponent = wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0xF9,
                           (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                           v18);
          if ( !v8 )
            return ExeComponent;
          if ( a5 )
          {
            if ( ImpersonateLoggedOnUser(hToken) )
              return ExeComponent;
            goto LABEL_20;
          }
LABEL_35:
          RevertToSelf();
          return ExeComponent;
        }
        v8 = 1;
        DebuggerInfoForUser = GetDebuggerInfoForUser(v27, v29, v28, v30, a7, a8);
      }
      ExeComponent = 0;
      if ( DebuggerInfoForUser != -2147024894 )
        ExeComponent = DebuggerInfoForUser;
      if ( ExeComponent < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)ExeComponent,
          v23);
        if ( !v8 )
          return ExeComponent;
        if ( a5 )
        {
          if ( ImpersonateLoggedOnUser(hToken) )
            return ExeComponent;
LABEL_20:
          MicrosoftTelemetryAssertTriggeredNoArgs(v19);
          return ExeComponent;
        }
        goto LABEL_35;
      }
      if ( v8 )
      {
        if ( a5 )
        {
          if ( !ImpersonateLoggedOnUser(hToken) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v20);
        }
        else
        {
          RevertToSelf();
        }
      }
      return 0;
    }
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xED,
             (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
             v21);
  }
}

```

## disassembly

```asm
0x180010e04  push    rbp
0x180010e06  push    rbx
0x180010e07  push    rdi
0x180010e08  push    r12
0x180010e0a  push    r13
0x180010e0c  push    r14
0x180010e0e  push    r15
0x180010e10  lea     rbp, [rsp-310h]
0x180010e18  sub     rsp, 410h
0x180010e1f  mov     rax, cs:__security_cookie
0x180010e26  xor     rax, rsp
0x180010e29  mov     [rbp+340h+var_40], rax
0x180010e30  mov     rbx, [rbp+340h+arg_28]
0x180010e37  xor     edi, edi
0x180010e39  mov     r12, [rbp+340h+arg_30]
0x180010e40  mov     r15, r8
0x180010e43  mov     r13, [rbp+340h+arg_38]
0x180010e4a  mov     r14, rcx
0x180010e4d  mov     [rsp+440h+var_3F0], r9
0x180010e52  mov     [rsp+440h+Sid], rdx
0x180010e57  test    rbx, rbx
0x180010e5a  jz      loc_1800110C0
0x180010e60  lea     rax, [rsp+440h+var_408]
0x180010e65  mov     [rsp+440h+var_418], rdi
0x180010e6a  lea     r9, [rsp+440h+var_3E0]
0x180010e6f  mov     [rsp+440h+var_420], rax; int
0x180010e74  lea     r8, [rsp+440h+var_400]
0x180010e79  mov     [rsp+440h+var_400], 100h
0x180010e82  lea     rdx, [rbp+340h+var_350]
0x180010e86  mov     qword ptr [rsp+440h+var_408], 84h
0x180010e8f  call    cs:__imp_RtlQueryPackageIdentity
0x180010e96  nop     dword ptr [rax+rax+00h]
0x180010e9b  test    eax, eax
0x180010e9d  js      loc_180010FFD
0x180010ea3  xor     edx, edx; Val
0x180010ea5  lea     rcx, [rbp+340h+var_250]; void *
0x180010eac  mov     r8d, 208h; Size
0x180010eb2  call    memset_0
0x180010eb7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180010ebb  inc     rcx; unsigned __int64
0x180010ebe  cmp     [rbx+rcx*2], di
0x180010ec2  jnz     short loc_180010EBB
0x180010ec4  lea     r9, [rbp+340h+var_250]; unsigned __int16 *
0x180010ecb  mov     rdx, rbx; unsigned __int16 *
0x180010ece  call    ?FindExeComponent@@YAJ_KPEBGKPEAG@Z; FindExeComponent(unsigned __int64,ushort const *,ulong,ushort *)
0x180010ed3  mov     ebx, eax
0x180010ed5  test    eax, eax
0x180010ed7  jns     short loc_180010F19
0x180010ed9  mov     edx, 0D4h; void *
0x180010ede  mov     rcx, [rbp+348h]; this
0x180010ee5  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180010eec  mov     r9d, ebx; char *
0x180010eef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ef4  mov     eax, ebx
0x180010ef6  mov     rcx, [rbp+340h+var_40]
0x180010efd  xor     rcx, rsp; StackCookie
0x180010f00  call    __security_check_cookie
0x180010f05  add     rsp, 410h
0x180010f0c  pop     r15
0x180010f0e  pop     r14
0x180010f10  pop     r13
0x180010f12  pop     r12
0x180010f14  pop     rdi
0x180010f15  pop     rbx
0x180010f16  pop     rbp
0x180010f17  retn
0x180010f19  cmp     [rbp+340h+arg_20], dil
0x180010f20  jz      loc_18001103B
0x180010f26  mov     rcx, [rsp+440h+Sid]; Sid
0x180010f2b  lea     r9, [rbp+340h+var_250]; unsigned __int16 *
0x180010f32  mov     [rsp+440h+var_418], r13; unsigned __int16 **
0x180010f37  lea     r8, [rsp+440h+var_3E0]; unsigned __int16 *
0x180010f3c  lea     rdx, [rbp+340h+var_350]; unsigned __int16 *
0x180010f40  mov     [rsp+440h+var_420], r12; int
0x180010f45  call    ?GetDebuggerInfoForUser@@YAJPEAXPEBG11PEAPEAG2@Z; GetDebuggerInfoForUser(void *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x180010f4a  cmp     eax, 80070002h
0x180010f4f  jnz     short loc_180010F99
0x180010f51  test    r15, r15
0x180010f54  jz      short loc_180010F99
0x180010f56  mov     rcx, r15; hToken
0x180010f59  call    cs:__imp_ImpersonateLoggedOnUser
0x180010f60  nop     dword ptr [rax+rax+00h]
0x180010f65  xor     r15d, r15d
0x180010f68  test    eax, eax
0x180010f6a  jz      loc_180011056
0x180010f70  mov     rcx, [rsp+440h+var_3F0]; Sid
0x180010f75  lea     r9, [rbp+340h+var_250]; unsigned __int16 *
0x180010f7c  mov     [rsp+440h+var_418], r13; unsigned __int16 **
0x180010f81  lea     r8, [rsp+440h+var_3E0]; unsigned __int16 *
0x180010f86  lea     rdx, [rbp+340h+var_350]; unsigned __int16 *
0x180010f8a  mov     [rsp+440h+var_420], r12; unsigned __int16 **
0x180010f8f  mov     dil, 1
0x180010f92  call    ?GetDebuggerInfoForUser@@YAJPEAXPEBG11PEAPEAG2@Z; GetDebuggerInfoForUser(void *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x180010f97  jmp     short loc_180010F9C
0x180010f99  xor     r15d, r15d
0x180010f9c  cmp     eax, 80070002h
0x180010fa1  mov     ebx, r15d
0x180010fa4  cmovnz  ebx, eax
0x180010fa7  test    ebx, ebx
0x180010fa9  jns     short loc_18001100F
0x180010fab  mov     rcx, [rbp+348h]; this
0x180010fb2  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180010fb9  mov     r9d, ebx; char *
0x180010fbc  mov     edx, 101h; void *
0x180010fc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fc6  test    dil, dil
0x180010fc9  jz      loc_180010EF4
0x180010fcf  cmp     [rbp+340h+arg_20], r15b
0x180010fd6  jz      loc_1800110D4
0x180010fdc  mov     rcx, r14; hToken
0x180010fdf  call    cs:__imp_ImpersonateLoggedOnUser
0x180010fe6  nop     dword ptr [rax+rax+00h]
0x180010feb  test    eax, eax
0x180010fed  jnz     loc_180010EF4
0x180010ff3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010ff8  jmp     loc_180010EF4
0x180010ffd  cmp     eax, 0C0000225h
0x180011002  jnz     loc_1800110F6
0x180011008  xor     eax, eax
0x18001100a  jmp     loc_180010EF6
0x18001100f  test    dil, dil
0x180011012  jz      short loc_180011008
0x180011014  cmp     [rbp+340h+arg_20], r15b
0x18001101b  jz      loc_1800110E5
0x180011021  mov     rcx, r14; hToken
0x180011024  call    cs:__imp_ImpersonateLoggedOnUser
0x18001102b  nop     dword ptr [rax+rax+00h]
0x180011030  test    eax, eax
0x180011032  jnz     short loc_180011008
0x180011034  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011039  jmp     short loc_180011008
0x18001103b  mov     rcx, r14; hToken
0x18001103e  call    cs:__imp_ImpersonateLoggedOnUser
0x180011045  nop     dword ptr [rax+rax+00h]
0x18001104a  test    eax, eax
0x18001104c  jz      short loc_1800110A3
0x18001104e  mov     dil, 1
0x180011051  jmp     loc_180010F26
0x180011056  mov     rcx, [rbp+348h]; this
0x18001105d  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180011064  mov     edx, 0F9h; void *
0x180011069  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001106e  mov     ebx, eax
0x180011070  test    dil, dil
0x180011073  jz      loc_180010EF4
0x180011079  cmp     [rbp+340h+arg_20], r15b
0x180011080  jz      short loc_1800110D4
0x180011082  mov     rcx, r14; hToken
0x180011085  call    cs:__imp_ImpersonateLoggedOnUser
0x18001108c  nop     dword ptr [rax+rax+00h]
0x180011091  test    eax, eax
0x180011093  jnz     loc_180010EF4
0x180011099  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001109e  jmp     loc_180010EF4
0x1800110a3  mov     rcx, [rbp+348h]; this
0x1800110aa  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800110b1  mov     edx, 0EDh; void *
0x1800110b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800110bb  jmp     loc_180010EF6
0x1800110c0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800110c5  mov     edx, 0CBh
0x1800110ca  mov     ebx, 80070057h
0x1800110cf  jmp     loc_180010EDE
0x1800110d4  call    cs:__imp_RevertToSelf
0x1800110db  nop     dword ptr [rax+rax+00h]
0x1800110e0  jmp     loc_180010EF4
0x1800110e5  call    cs:__imp_RevertToSelf
0x1800110ec  nop     dword ptr [rax+rax+00h]
0x1800110f1  jmp     loc_180011008
0x1800110f6  mov     rcx, [rbp+348h]; this
0x1800110fd  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x180011104  mov     r9d, eax; char *
0x180011107  mov     edx, 105h; void *
0x18001110c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180011111  jmp     loc_180010EF6
```
