# SxsBeginAssemblyInstall

- ea: `0x18005ed70`
- end: `0x18005efd1`
- name: `SxsBeginAssemblyInstall`
- size: `609`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000df40`
- `0x18001c270`
- `0x18002e98c`
- `0x18005c978`
- `0x18005d2b0`
- `0x18005ed70`
- `0x180063114`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ef77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005edfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005eebf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005eefb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ef56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ef64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ef9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005edfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005eebf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005eefb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ef56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ef64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ef9b`

## pseudocode

```c
__int64 __fastcall SxsBeginAssemblyInstall(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        struct ISxsStore **a6)
{
  const char *v10; // rcx
  struct ISxsStore *v11; // rdi
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  int v16; // edx
  unsigned int v17; // r15d
  int RemoteStore; // eax
  int v19; // ebx
  int v20; // eax
  int v21; // ebx
  DWORD LastError; // ebx
  unsigned int v23; // ebx
  struct ISxsStore *v25; // [rsp+20h] [rbp-50h] BYREF
  int v26; // [rsp+28h] [rbp-48h] BYREF
  int v27; // [rsp+30h] [rbp-40h] BYREF
  __int64 v28; // [rsp+38h] [rbp-38h]
  __int64 *v29; // [rsp+40h] [rbp-30h]
  __int64 v30; // [rsp+48h] [rbp-28h]
  int v31; // [rsp+50h] [rbp-20h]
  int *v32; // [rsp+58h] [rbp-18h]

  v29 = &qword_180074870;
  v26 = 0;
  v32 = &v26;
  v27 = 1;
  v28 = 0;
  v30 = 544438355;
  v31 = 44;
  CFrame::BaseEnter((CFrame *)&v27);
  v11 = 0;
  v25 = 0;
  if ( a2 )
  {
    v31 = 49;
LABEL_3:
    FusionpTraceParameterCheck(v10);
    SetLastError(0x57u);
    *v32 = 0;
    goto LABEL_31;
  }
  if ( a3 )
  {
    v31 = 50;
    goto LABEL_3;
  }
  if ( a4 )
  {
    v31 = 51;
    goto LABEL_3;
  }
  if ( a5 )
  {
    v31 = 52;
    goto LABEL_3;
  }
  if ( !a6 )
  {
    v31 = 54;
    goto LABEL_3;
  }
  if ( (a1 & 0xFFFFFF80) != 0 )
  {
    v31 = 63;
    goto LABEL_3;
  }
  *a6 = 0;
  v12 = ((a1 & 1) << 6) | 0x800;
  if ( (a1 & 2) == 0 )
    v12 = (a1 & 1) << 6;
  v13 = v12 | 0x10;
  if ( (a1 & 4) == 0 )
    v13 = v12;
  v14 = v13 | 0x20;
  if ( (a1 & 8) == 0 )
    v14 = v13;
  v15 = v14 | 1;
  if ( (a1 & 0x10) == 0 )
    v15 = v14;
  v16 = v15 | 2;
  if ( (a1 & 0x20) == 0 )
    v16 = v15;
  v17 = v16 | 4;
  if ( (a1 & 0x40) == 0 )
    v17 = v16;
  SetLastError(0);
  RemoteStore = SxspGetRemoteStore(&v25);
  v19 = RemoteStore;
  if ( RemoteStore >= 0 )
  {
    SetLastError(0);
    v11 = v25;
    v20 = (*(__int64 (__fastcall **)(struct ISxsStore *, _QWORD))(*(_QWORD *)v25 + 24LL))(v25, v17);
    v21 = v20;
    if ( v20 >= 0 )
    {
      *a6 = v11;
      (*(void (__fastcall **)(struct ISxsStore *))(*(_QWORD *)v11 + 8LL))(v11);
      v26 = 1;
      SetLastError(0);
      SetLastError(0);
      *v32 = 1;
    }
    else
    {
      FusionpTraceCOMFailure(v20, byte_18008517D);
      CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v27, v21);
    }
  }
  else
  {
    FusionpTraceCOMFailure(RemoteStore, byte_18008517D);
    CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v27, v19);
    v11 = v25;
  }
LABEL_31:
  LastError = GetLastError();
  if ( v11 )
    (*(void (__fastcall **)(struct ISxsStore *))(*(_QWORD *)v11 + 16LL))(v11);
  SetLastError(LastError);
  v23 = v26;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v27);
  return v23;
}

```

## disassembly

```asm
0x18005ed70  push    rbp
0x18005ed72  push    rbx
0x18005ed73  push    rsi
0x18005ed74  push    rdi
0x18005ed75  push    r12
0x18005ed77  push    r14
0x18005ed79  push    r15
0x18005ed7b  mov     rbp, rsp
0x18005ed7e  sub     rsp, 70h
0x18005ed82  mov     rax, cs:__security_cookie
0x18005ed89  xor     rax, rsp
0x18005ed8c  mov     [rbp+var_10], rax
0x18005ed90  mov     rsi, [rbp+arg_28]
0x18005ed94  lea     rax, qword_180074870
0x18005ed9b  mov     [rbp+var_30], rax
0x18005ed9f  mov     r14d, ecx
0x18005eda2  lea     rax, [rbp+var_48]
0x18005eda6  mov     [rbp+var_48], 0
0x18005edad  lea     rcx, [rbp+var_40]; this
0x18005edb1  mov     [rbp+var_18], rax
0x18005edb5  mov     r15, r9
0x18005edb8  mov     [rbp+var_40], 1
0x18005edbf  mov     r12, r8
0x18005edc2  mov     [rbp+var_38], 0
0x18005edca  mov     rbx, rdx
0x18005edcd  mov     [rbp+var_28], 20737853h
0x18005edd5  mov     [rbp+var_20], 2Ch ; ','
0x18005eddc  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005ede1  xor     edi, edi
0x18005ede3  mov     [rbp+var_50], rdi
0x18005ede7  test    rbx, rbx
0x18005edea  jz      short loc_18005EE14
0x18005edec  mov     [rbp+var_20], 31h ; '1'
0x18005edf3  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18005edf8  mov     ecx, 57h ; 'W'; dwErrCode
0x18005edfd  call    cs:__imp_SetLastError
0x18005ee04  nop     dword ptr [rax+rax+00h]
0x18005ee09  mov     rax, [rbp+var_18]
0x18005ee0d  mov     [rax], edi
0x18005ee0f  jmp     loc_18005EF77
0x18005ee14  test    r12, r12
0x18005ee17  jz      short loc_18005EE22
0x18005ee19  mov     [rbp+var_20], 32h ; '2'
0x18005ee20  jmp     short loc_18005EDF3
0x18005ee22  test    r15, r15
0x18005ee25  jz      short loc_18005EE30
0x18005ee27  mov     [rbp+var_20], 33h ; '3'
0x18005ee2e  jmp     short loc_18005EDF3
0x18005ee30  cmp     [rbp+arg_20], rdi
0x18005ee34  jz      short loc_18005EE3F
0x18005ee36  mov     [rbp+var_20], 34h ; '4'
0x18005ee3d  jmp     short loc_18005EDF3
0x18005ee3f  test    rsi, rsi
0x18005ee42  jnz     short loc_18005EE4D
0x18005ee44  mov     [rbp+var_20], 36h ; '6'
0x18005ee4b  jmp     short loc_18005EDF3
0x18005ee4d  test    r14d, 0FFFFFF80h
0x18005ee54  jz      short loc_18005EE5F
0x18005ee56  mov     [rbp+var_20], 3Fh ; '?'
0x18005ee5d  jmp     short loc_18005EDF3
0x18005ee5f  mov     ecx, r14d
0x18005ee62  mov     [rsi], rdi
0x18005ee65  mov     r12d, 1
0x18005ee6b  and     ecx, r12d
0x18005ee6e  shl     ecx, 6
0x18005ee71  mov     edx, ecx
0x18005ee73  bts     edx, 0Bh
0x18005ee77  test    r14b, 2
0x18005ee7b  cmovz   edx, ecx
0x18005ee7e  mov     ecx, edx
0x18005ee80  or      ecx, 10h
0x18005ee83  test    r14b, 4
0x18005ee87  cmovz   ecx, edx
0x18005ee8a  mov     edx, ecx
0x18005ee8c  or      edx, 20h
0x18005ee8f  test    r14b, 8
0x18005ee93  cmovz   edx, ecx
0x18005ee96  mov     ecx, edx
0x18005ee98  or      ecx, r12d
0x18005ee9b  test    r14b, 10h
0x18005ee9f  cmovz   ecx, edx
0x18005eea2  mov     edx, ecx
0x18005eea4  or      edx, 2
0x18005eea7  test    r14b, 20h
0x18005eeab  cmovz   edx, ecx
0x18005eeae  mov     r15d, edx
0x18005eeb1  or      r15d, 4
0x18005eeb5  test    r14b, 40h
0x18005eeb9  cmovz   r15d, edx
0x18005eebd  xor     ecx, ecx; dwErrCode
0x18005eebf  call    cs:__imp_SetLastError
0x18005eec6  nop     dword ptr [rax+rax+00h]
0x18005eecb  lea     rcx, [rbp+var_50]; struct ISxsStore **
0x18005eecf  call    ?SxspGetRemoteStore@@YAJPEAPEAUISxsStore@@@Z; SxspGetRemoteStore(ISxsStore * *)
0x18005eed4  mov     ebx, eax
0x18005eed6  test    eax, eax
0x18005eed8  jns     short loc_18005EEF9
0x18005eeda  lea     rdx, byte_18008517D; char *
0x18005eee1  mov     ecx, eax; int
0x18005eee3  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18005eee8  mov     edx, ebx; int
0x18005eeea  lea     rcx, [rbp+var_40]; this
0x18005eeee  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005eef3  mov     rdi, [rbp+var_50]
0x18005eef7  jmp     short loc_18005EF77
0x18005eef9  xor     ecx, ecx; dwErrCode
0x18005eefb  call    cs:__imp_SetLastError
0x18005ef02  nop     dword ptr [rax+rax+00h]
0x18005ef07  mov     rdi, [rbp+var_50]
0x18005ef0b  mov     edx, r15d
0x18005ef0e  mov     rcx, rdi
0x18005ef11  mov     rax, [rdi]
0x18005ef14  mov     rax, [rax+18h]
0x18005ef18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef1d  mov     ebx, eax
0x18005ef1f  test    eax, eax
0x18005ef21  jns     short loc_18005EF3E
0x18005ef23  lea     rdx, byte_18008517D; char *
0x18005ef2a  mov     ecx, eax; int
0x18005ef2c  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18005ef31  mov     edx, ebx; int
0x18005ef33  lea     rcx, [rbp+var_40]; this
0x18005ef37  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005ef3c  jmp     short loc_18005EF77
0x18005ef3e  mov     [rsi], rdi
0x18005ef41  mov     rcx, rdi
0x18005ef44  mov     rax, [rdi]
0x18005ef47  mov     rax, [rax+8]
0x18005ef4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef50  xor     ecx, ecx; dwErrCode
0x18005ef52  mov     [rbp+var_48], r12d
0x18005ef56  call    cs:__imp_SetLastError
0x18005ef5d  nop     dword ptr [rax+rax+00h]
0x18005ef62  xor     ecx, ecx; dwErrCode
0x18005ef64  call    cs:__imp_SetLastError
0x18005ef6b  nop     dword ptr [rax+rax+00h]
0x18005ef70  mov     rax, [rbp+var_18]
0x18005ef74  mov     [rax], r12d
0x18005ef77  call    cs:__imp_GetLastError
0x18005ef7e  nop     dword ptr [rax+rax+00h]
0x18005ef83  mov     ebx, eax
0x18005ef85  test    rdi, rdi
0x18005ef88  jz      short loc_18005EF99
0x18005ef8a  mov     rdx, [rdi]
0x18005ef8d  mov     rcx, rdi
0x18005ef90  mov     rax, [rdx+10h]
0x18005ef94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef99  mov     ecx, ebx; dwErrCode
0x18005ef9b  call    cs:__imp_SetLastError
0x18005efa2  nop     dword ptr [rax+rax+00h]
0x18005efa7  mov     ebx, [rbp+var_48]
0x18005efaa  lea     rcx, [rbp+var_40]; this
0x18005efae  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005efb3  mov     eax, ebx
0x18005efb5  mov     rcx, [rbp+var_10]
0x18005efb9  xor     rcx, rsp; StackCookie
0x18005efbc  call    __security_check_cookie
0x18005efc1  add     rsp, 70h
0x18005efc5  pop     r15
0x18005efc7  pop     r14
0x18005efc9  pop     r12
0x18005efcb  pop     rdi
0x18005efcc  pop     rsi
0x18005efcd  pop     rbx
0x18005efce  pop     rbp
0x18005efcf  retn
```
