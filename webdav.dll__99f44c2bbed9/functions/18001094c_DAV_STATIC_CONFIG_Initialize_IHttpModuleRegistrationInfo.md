# DAV_STATIC_CONFIG::Initialize(IHttpModuleRegistrationInfo *)

- ea: `0x18001094c`
- end: `0x180010ab8`
- name: `?Initialize@DAV_STATIC_CONFIG@@AEAAJPEAVIHttpModuleRegistrationInfo@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(DAV_STATIC_CONFIG *__hidden this, struct IHttpModuleRegistrationInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180010ac0`

## callees

- `0x18001094c`
- `0x18001c460`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800109a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800109a5`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800109b2`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800109b2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800109d5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800109d5`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800109f4`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800109f4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180010a91`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180010a91`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180010979`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180010979`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010993`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010a60`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010993`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010a60`

## pseudocode

```c
__int64 __fastcall DAV_STATIC_CONFIG::Initialize(DAV_STATIC_CONFIG *this, struct IHttpModuleRegistrationInfo *a2)
{
  WINBOOL *v2; // rdi
  const unsigned __int16 *v4; // rax
  int v5; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  const unsigned __int16 *CommandLineW; // rbx
  const unsigned __int16 *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rdx
  int i; // ecx
  unsigned __int16 v14; // ax
  _BYTE v16[56]; // [rsp+20h] [rbp-48h] BYREF

  v2 = (WINBOOL *)DAV_STATIC_CONFIG::sm_StaticConfig;
  MULTISZ::MULTISZ((MULTISZ *)v16);
  v4 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IHttpModuleRegistrationInfo *))a2)(a2);
  v5 = STRU::Copy((STRU *)v2, v4);
  if ( v5 >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !IsWow64Process(CurrentProcess, v2 + 29) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_5:
      v5 = LastError;
      goto LABEL_23;
    }
    CommandLineW = GetCommandLineW();
    LastError = ParseCommandLine(CommandLineW, (struct MULTISZ *)v16);
    if ( LastError < 0 )
      goto LABEL_5;
    v9 = MULTISZ::First((MULTISZ *)v16);
    if ( v9 )
    {
      v10 = -1;
      while ( *v9 != 45 || ((v9[1] - 72) & 0xFFDF) != 0 || v9[2] )
      {
        v11 = -1;
        do
          ++v11;
        while ( v9[v11] );
        v9 += v11 + 1;
        if ( !*v9 )
          goto LABEL_19;
      }
      do
        ++v10;
      while ( v9[v10] );
      v12 = (const unsigned __int16 *)((unsigned __int64)&v9[v10 + 1] & -(__int64)(v9[v10 + 1] != 0));
      if ( v12 )
      {
        LastError = STRU::Copy((STRU *)(v2 + 14), v12);
        if ( LastError < 0 )
          goto LABEL_5;
      }
    }
LABEL_19:
    for ( i = v2[28]; ; i = v14 + 101 * i )
    {
      v14 = *CommandLineW;
      if ( !*CommandLineW )
        break;
      ++CommandLineW;
    }
    v2[28] = i;
    v5 = 0;
  }
LABEL_23:
  MULTISZ::~MULTISZ((MULTISZ *)v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001094c  mov     [rsp+arg_0], rbx
0x180010951  mov     [rsp+arg_10], rsi
0x180010956  push    rdi
0x180010957  sub     rsp, 60h
0x18001095b  mov     rax, cs:__security_cookie
0x180010962  xor     rax, rsp
0x180010965  mov     [rsp+68h+var_10], rax
0x18001096a  mov     rdi, cs:?sm_StaticConfig@DAV_STATIC_CONFIG@@0PEAV1@EA; DAV_STATIC_CONFIG * DAV_STATIC_CONFIG::sm_StaticConfig
0x180010971  lea     rcx, [rsp+68h+var_48]
0x180010976  mov     rbx, rdx
0x180010979  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18001097f  mov     rax, [rbx]
0x180010982  mov     rcx, rbx
0x180010985  mov     rax, [rax]
0x180010988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001098d  mov     rdx, rax
0x180010990  mov     rcx, rdi
0x180010993  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010999  xor     esi, esi
0x18001099b  mov     ebx, eax
0x18001099d  test    eax, eax
0x18001099f  js      loc_180010A8C
0x1800109a5  call    cs:__imp_GetCurrentProcess
0x1800109ab  mov     rcx, rax; hProcess
0x1800109ae  lea     rdx, [rdi+74h]; Wow64Process
0x1800109b2  call    cs:__imp_IsWow64Process
0x1800109b8  test    eax, eax
0x1800109ba  jnz     short loc_1800109D5
0x1800109bc  call    cs:__imp_GetLastError
0x1800109c2  test    eax, eax
0x1800109c4  jle     short loc_1800109CE
0x1800109c6  movzx   eax, ax
0x1800109c9  or      eax, 80070000h
0x1800109ce  mov     ebx, eax
0x1800109d0  jmp     loc_180010A8C
0x1800109d5  call    cs:__imp_GetCommandLineW
0x1800109db  mov     rcx, rax; unsigned __int16 *
0x1800109de  lea     rdx, [rsp+68h+var_48]; struct MULTISZ *
0x1800109e3  mov     rbx, rax
0x1800109e6  call    ?ParseCommandLine@@YAJPEBGPEAVMULTISZ@@@Z; ParseCommandLine(ushort const *,MULTISZ *)
0x1800109eb  test    eax, eax
0x1800109ed  js      short loc_1800109CE
0x1800109ef  lea     rcx, [rsp+68h+var_48]
0x1800109f4  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x1800109fa  test    rax, rax
0x1800109fd  jz      short loc_180010A6E
0x1800109ff  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180010a03  cmp     word ptr [rax], 2Dh ; '-'
0x180010a07  jnz     short loc_180010A23
0x180010a09  movzx   ecx, word ptr [rax+2]
0x180010a0d  mov     r8d, 0FFDFh
0x180010a13  sub     cx, 48h ; 'H'
0x180010a17  test    r8w, cx
0x180010a1b  jnz     short loc_180010A23
0x180010a1d  cmp     [rax+4], si
0x180010a21  jz      short loc_180010A3E
0x180010a23  mov     rcx, rdx
0x180010a26  inc     rcx
0x180010a29  cmp     [rax+rcx*2], si
0x180010a2d  jnz     short loc_180010A26
0x180010a2f  lea     rax, [rax+rcx*2]
0x180010a33  add     rax, 2
0x180010a37  cmp     [rax], si
0x180010a3a  jnz     short loc_180010A03
0x180010a3c  jmp     short loc_180010A6E
0x180010a3e  inc     rdx
0x180010a41  cmp     [rax+rdx*2], si
0x180010a45  jnz     short loc_180010A3E
0x180010a47  inc     rdx
0x180010a4a  lea     rcx, [rax+rdx*2]
0x180010a4e  movzx   eax, word ptr [rcx]
0x180010a51  neg     ax
0x180010a54  sbb     rdx, rdx
0x180010a57  and     rdx, rcx
0x180010a5a  jz      short loc_180010A6E
0x180010a5c  lea     rcx, [rdi+38h]
0x180010a60  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010a66  test    eax, eax
0x180010a68  js      loc_1800109CE
0x180010a6e  mov     ecx, [rdi+70h]
0x180010a71  jmp     short loc_180010A7F
0x180010a73  imul    ecx, 65h ; 'e'
0x180010a76  lea     rbx, [rbx+2]
0x180010a7a  movzx   eax, ax
0x180010a7d  add     ecx, eax
0x180010a7f  movzx   eax, word ptr [rbx]
0x180010a82  test    ax, ax
0x180010a85  jnz     short loc_180010A73
0x180010a87  mov     [rdi+70h], ecx
0x180010a8a  mov     ebx, esi
0x180010a8c  lea     rcx, [rsp+68h+var_48]
0x180010a91  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180010a97  mov     eax, ebx
0x180010a99  mov     rcx, [rsp+68h+var_10]
0x180010a9e  xor     rcx, rsp; StackCookie
0x180010aa1  call    __security_check_cookie
0x180010aa6  lea     r11, [rsp+68h+var_8]
0x180010aab  mov     rbx, [r11+10h]
0x180010aaf  mov     rsi, [r11+20h]
0x180010ab3  mov     rsp, r11
0x180010ab6  pop     rdi
0x180010ab7  retn
```
