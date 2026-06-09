# SxspGetAssemblyRootDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> &)

- ea: `0x18002d3dc`
- end: `0x18002d62a`
- name: `?SxspGetAssemblyRootDirectory@@YAHAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `590`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18002b7e0`
- `0x18002df40`
- `0x18004b524`
- `0x18005d888`
- `0x180060390`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x18001c270`
- `0x18002d3dc`
- `0x18002d630`
- `0x18002de34`
- `0x18002def0`
- `0x180030480`
- `0x180056680`
- `0x18005d7ac`
- `0x18006a0dd`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x18002d4bd`
- `ntdll!RtlGetNtSystemRoot` at `0x18002d4bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d528`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d456`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d4a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d548`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d57e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d5dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d456`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d4a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d548`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d57e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d5dd`

## pseudocode

```c
__int64 __fastcall SxspGetAssemblyRootDirectory(__int64 a1)
{
  __int64 v2; // rbx
  char **v3; // rcx
  __int64 v4; // rcx
  _WORD *NtSystemRoot; // rax
  __int64 v6; // rbx
  unsigned __int16 *v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rsi
  int v10; // ebx
  size_t v11; // rbx
  unsigned int v12; // ebx
  unsigned __int16 *v14[2]; // [rsp+20h] [rbp-39h] BYREF
  unsigned __int64 v15; // [rsp+30h] [rbp-29h]
  int v16; // [rsp+38h] [rbp-21h] BYREF
  int v17; // [rsp+40h] [rbp-19h] BYREF
  __int64 v18; // [rsp+48h] [rbp-11h]
  __int64 *v19; // [rsp+50h] [rbp-9h]
  __int64 v20; // [rsp+58h] [rbp-1h]
  int v21; // [rsp+60h] [rbp+7h]
  unsigned int *v22; // [rsp+68h] [rbp+Fh]

  v17 = 1;
  v19 = &qword_18006E0A8;
  v20 = 544438355;
  v22 = (unsigned int *)&v16;
  v16 = 0;
  v18 = 0;
  v21 = 2444;
  CFrame::BaseEnter((CFrame *)&v17);
  *(_OWORD *)v14 = 0;
  v15 = 0;
  if ( !g_AlternateAssemblyStoreRoot )
  {
    CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(v14, a1);
    NtSystemRoot = (_WORD *)RtlGetNtSystemRoot(v4);
    v6 = -1;
    do
      ++v6;
    while ( NtSystemRoot[v6] );
    v7 = v14[1];
    if ( v15 && !v14[1] )
    {
      v8 = 0;
      SxspSetLastNTError(-1073741811);
LABEL_19:
      if ( GetLastError() != 122 )
        goto LABEL_27;
      CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(v14);
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(a1, v8 + 1) )
      {
        v3 = off_180075670;
        goto LABEL_6;
      }
      CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(v14, a1);
      SetLastError(0);
      if ( !SxspGetAssemblyRootDirectoryHelper(v15, v14[1], 0) )
      {
        v3 = off_180075650;
        goto LABEL_6;
      }
      goto LABEL_25;
    }
    v9 = v6 + 9;
    if ( v6 + 9 <= v15 )
    {
      v11 = v6;
      memcpy_0(v14[1], NtSystemRoot, v11 * 2);
      *(_OWORD *)&v7[v11] = *(_OWORD *)L"\\WinSxS\\";
      v7[v11 + 8] = aWinsxs[8];
    }
    else
    {
      if ( v14[1] )
      {
        v10 = 0;
        SxspSetLastNTError(-1073741789);
      }
      else
      {
        v10 = 1;
      }
      if ( !v10 )
      {
        v8 = v9 - 1;
        goto LABEL_19;
      }
    }
LABEL_25:
    CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(v14);
    goto LABEL_26;
  }
  SetLastError(0);
  v2 = -1;
  do
    ++v2;
  while ( *((_WORD *)g_AlternateAssemblyStoreRoot + v2) );
  if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(a1, g_AlternateAssemblyStoreRoot, v2) )
  {
    SetLastError(0);
LABEL_26:
    SetLastError(0);
    *v22 = 1;
    goto LABEL_27;
  }
  v3 = off_180075690;
LABEL_6:
  *v22 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v3);
LABEL_27:
  v12 = *v22;
  CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(v14);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v17);
  return v12;
}

```

## disassembly

```asm
0x18002d3dc  push    rbp
0x18002d3de  push    rbx
0x18002d3df  push    rsi
0x18002d3e0  push    rdi
0x18002d3e1  push    r12
0x18002d3e3  push    r15
0x18002d3e5  lea     rbp, [rsp-2Fh]
0x18002d3ea  sub     rsp, 88h
0x18002d3f1  mov     rax, cs:__security_cookie
0x18002d3f8  xor     rax, rsp
0x18002d3fb  mov     [rbp+57h+var_40], rax
0x18002d3ff  lea     rax, qword_18006E0A8
0x18002d406  mov     [rbp+57h+var_70], 1
0x18002d40d  mov     [rbp+57h+var_60], rax
0x18002d411  mov     r15, rcx
0x18002d414  lea     rax, [rbp+57h+var_78]
0x18002d418  mov     [rbp+57h+var_58], 20737853h
0x18002d420  xor     r12d, r12d
0x18002d423  mov     [rbp+57h+var_48], rax
0x18002d427  lea     rcx, [rbp+57h+var_70]; this
0x18002d42b  mov     [rbp+57h+var_78], r12d
0x18002d42f  mov     [rbp+57h+var_68], r12
0x18002d433  mov     [rbp+57h+var_50], 98Ch
0x18002d43a  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002d43f  cmp     cs:?g_AlternateAssemblyStoreRoot@@3PEBGEB, r12; ushort const * const g_AlternateAssemblyStoreRoot
0x18002d446  xorps   xmm0, xmm0
0x18002d449  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x18002d44e  mov     [rbp+57h+var_80], r12
0x18002d452  jz      short loc_18002D4B1
0x18002d454  xor     ecx, ecx; dwErrCode
0x18002d456  call    cs:__imp_SetLastError
0x18002d45d  nop     dword ptr [rax+rax+00h]
0x18002d462  mov     rdx, cs:?g_AlternateAssemblyStoreRoot@@3PEBGEB; ushort const * const g_AlternateAssemblyStoreRoot
0x18002d469  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d46d  inc     rbx
0x18002d470  cmp     [rdx+rbx*2], r12w
0x18002d475  jnz     short loc_18002D46D
0x18002d477  mov     r8, rbx
0x18002d47a  mov     rcx, r15
0x18002d47d  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18002d482  test    eax, eax
0x18002d484  jnz     short loc_18002D49E
0x18002d486  lea     rcx, off_180075690; struct _CALL_SITE_INFO *
0x18002d48d  mov     rax, [rbp+57h+var_48]
0x18002d491  mov     [rax], r12d
0x18002d494  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002d499  jmp     loc_18002D5F3
0x18002d49e  xor     ecx, ecx; dwErrCode
0x18002d4a0  call    cs:__imp_SetLastError
0x18002d4a7  nop     dword ptr [rax+rax+00h]
0x18002d4ac  jmp     loc_18002D5DB
0x18002d4b1  mov     rdx, r15
0x18002d4b4  lea     rcx, [rbp+57h+var_90]
0x18002d4b8  call    ?Attach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXPEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x18002d4bd  call    cs:__imp_RtlGetNtSystemRoot
0x18002d4c4  nop     dword ptr [rax+rax+00h]
0x18002d4c9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d4cd  inc     rbx
0x18002d4d0  cmp     [rax+rbx*2], r12w
0x18002d4d5  jnz     short loc_18002D4CD
0x18002d4d7  mov     rdi, [rbp+57h+var_90+8]
0x18002d4db  cmp     [rbp+57h+var_80], r12
0x18002d4df  jz      short loc_18002D4F5
0x18002d4e1  test    rdi, rdi
0x18002d4e4  jnz     short loc_18002D4F5
0x18002d4e6  mov     ecx, 0C000000Dh; int
0x18002d4eb  mov     rbx, r12
0x18002d4ee  call    ?SxspSetLastNTError@@YAKJ@Z; SxspSetLastNTError(long)
0x18002d4f3  jmp     short loc_18002D528
0x18002d4f5  lea     rsi, [rbx+9]
0x18002d4f9  cmp     rsi, [rbp+57h+var_80]
0x18002d4fd  jbe     loc_18002D5AA
0x18002d503  test    rdi, rdi
0x18002d506  jz      short loc_18002D517
0x18002d508  mov     ecx, 0C0000023h; int
0x18002d50d  mov     ebx, r12d
0x18002d510  call    ?SxspSetLastNTError@@YAKJ@Z; SxspSetLastNTError(long)
0x18002d515  jmp     short loc_18002D51C
0x18002d517  mov     ebx, 1
0x18002d51c  test    ebx, ebx
0x18002d51e  jnz     loc_18002D5D2
0x18002d524  lea     rbx, [rsi-1]
0x18002d528  call    cs:__imp_GetLastError
0x18002d52f  nop     dword ptr [rax+rax+00h]
0x18002d534  cmp     eax, 7Ah ; 'z'
0x18002d537  jnz     loc_18002D5F3
0x18002d53d  lea     rcx, [rbp+57h+var_90]
0x18002d541  call    ?Detach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXXZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(void)
0x18002d546  xor     ecx, ecx; dwErrCode
0x18002d548  call    cs:__imp_SetLastError
0x18002d54f  nop     dword ptr [rax+rax+00h]
0x18002d554  lea     rdx, [rbx+1]
0x18002d558  mov     rcx, r15
0x18002d55b  call    ?Win32ResizeBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_KW4EPreserveContents@@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(unsigned __int64,EPreserveContents)
0x18002d560  test    eax, eax
0x18002d562  jnz     short loc_18002D570
0x18002d564  lea     rcx, off_180075670; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002d56b  jmp     loc_18002D48D
0x18002d570  mov     rdx, r15
0x18002d573  lea     rcx, [rbp+57h+var_90]
0x18002d577  call    ?Attach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXPEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CGenericStringBufferAccessor<CUnicodeCharTraits>::Attach(CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x18002d57c  xor     ecx, ecx; dwErrCode
0x18002d57e  call    cs:__imp_SetLastError
0x18002d585  nop     dword ptr [rax+rax+00h]
0x18002d58a  mov     rdx, [rbp+57h+var_90+8]; unsigned __int16 *
0x18002d58e  xor     r8d, r8d; unsigned __int64 *
0x18002d591  mov     rcx, [rbp+57h+var_80]; unsigned __int64
0x18002d595  call    ?SxspGetAssemblyRootDirectoryHelper@@YAH_KQEAGPEA_K@Z; SxspGetAssemblyRootDirectoryHelper(unsigned __int64,ushort * const,unsigned __int64 *)
0x18002d59a  test    eax, eax
0x18002d59c  jnz     short loc_18002D5D2
0x18002d59e  lea     rcx, off_180075650; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002d5a5  jmp     loc_18002D48D
0x18002d5aa  add     rbx, rbx
0x18002d5ad  mov     rdx, rax; Src
0x18002d5b0  mov     r8, rbx; Size
0x18002d5b3  mov     rcx, rdi; void *
0x18002d5b6  call    memcpy_0
0x18002d5bb  movups  xmm0, xmmword ptr cs:aWinsxs; "\\WinSxS\\"
0x18002d5c2  movups  xmmword ptr [rbx+rdi], xmm0
0x18002d5c6  movzx   eax, word ptr cs:aWinsxs+10h; ""
0x18002d5cd  mov     [rbx+rdi+10h], ax
0x18002d5d2  lea     rcx, [rbp+57h+var_90]
0x18002d5d6  call    ?Detach@?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAAXXZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::Detach(void)
0x18002d5db  xor     ecx, ecx; dwErrCode
0x18002d5dd  call    cs:__imp_SetLastError
0x18002d5e4  nop     dword ptr [rax+rax+00h]
0x18002d5e9  mov     rax, [rbp+57h+var_48]
0x18002d5ed  mov     dword ptr [rax], 1
0x18002d5f3  mov     rax, [rbp+57h+var_48]
0x18002d5f7  lea     rcx, [rbp+57h+var_90]
0x18002d5fb  mov     ebx, [rax]
0x18002d5fd  call    ??1?$CGenericStringBufferAccessor@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBufferAccessor<CUnicodeCharTraits>::~CGenericStringBufferAccessor<CUnicodeCharTraits>(void)
0x18002d602  lea     rcx, [rbp+57h+var_70]; this
0x18002d606  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18002d60b  mov     eax, ebx
0x18002d60d  mov     rcx, [rbp+57h+var_40]
0x18002d611  xor     rcx, rsp; StackCookie
0x18002d614  call    __security_check_cookie
0x18002d619  add     rsp, 88h
0x18002d620  pop     r15
0x18002d622  pop     r12
0x18002d624  pop     rdi
0x18002d625  pop     rsi
0x18002d626  pop     rbx
0x18002d627  pop     rbp
0x18002d628  retn
```
