# SampQueryCallingProcessInfo(void)

- ea: `0x1800b3e24`
- end: `0x1800b3fce`
- name: `?SampQueryCallingProcessInfo@@YAPEAGXZ`
- size: `426`
- prototype: `unsigned __int16 *(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b2c04`
- `0x1800b2e34`
- `0x1800b34b8`
- `0x1800b37b4`

## callees

- `0x18002cd80`
- `0x18002d720`
- `0x18005308c`
- `0x1800b3e24`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800b3e9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800b3e9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b3f48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b3f48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b3fa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b3fa5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800b3ecf`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800b3ecf`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b3ebd`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b3ebd`

## string_xrefs

- `0x1800b3e46`: `<command line arguments omitted>`

## pseudocode

```c
unsigned __int16 *SampQueryCallingProcessInfo(void)
{
  unsigned __int16 *v0; // rbx
  unsigned __int16 *v1; // rbp
  int v2; // r14d
  LPWSTR CommandLineW; // rax
  __int64 v4; // rcx
  LPWSTR v5; // rsi
  __int64 v6; // rdx
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // edi
  unsigned __int16 *v11; // rax
  _OWORD *v12; // rcx
  const unsigned __int16 *v13; // r8
  _OWORD v15[4]; // [rsp+30h] [rbp-2A8h] BYREF
  wchar_t v16; // [rsp+70h] [rbp-268h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-258h] BYREF

  v15[0] = *(_OWORD *)L"<command line arguments omitted>";
  v0 = 0;
  v15[1] = *(_OWORD *)L" line arguments omitted>";
  v1 = 0;
  v15[2] = *(_OWORD *)L"guments omitted>";
  v15[3] = *(_OWORD *)L"omitted>";
  v16 = aCommandLineArg[32];
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    InitOnceExecuteOnce(&InitOnce, SampInitIncludeArguments, 0, 0);
    v2 = dword_1800F0C04;
    if ( dword_1800F0C04 )
    {
      CommandLineW = GetCommandLineW();
      v4 = -1;
      v5 = CommandLineW;
      v6 = -1;
      do
        ++v6;
      while ( Filename[v6] );
      do
        ++v4;
      while ( CommandLineW[v4] );
      v7 = 2 * (v6 + v4) + 8;
    }
    else
    {
      v8 = -1;
      v9 = -1;
      v5 = 0;
      do
        ++v9;
      while ( *((_WORD *)v15 + v9) );
      do
        ++v8;
      while ( Filename[v8] );
      v7 = 2 * (v8 + v9) + 4;
    }
    v10 = v7;
    v11 = (unsigned __int16 *)LocalAlloc(0x40u, v7);
    v0 = v11;
    if ( v11 )
    {
      memset_0(v11, 0, v10);
      v12 = v15;
      if ( v2 )
        v12 = v5;
      v13 = L"%s (%s)";
      if ( !v2 )
        v13 = L"%s %s";
      if ( (int)RtlStringCbPrintfW(v0, v10, v13, Filename, v12) >= 0 )
      {
        v1 = v0;
        v0 = 0;
      }
    }
  }
  LocalFree(v0);
  return v1;
}

```

## disassembly

```asm
0x1800b3e24  push    rbx
0x1800b3e26  push    rbp
0x1800b3e27  push    rsi
0x1800b3e28  push    rdi
0x1800b3e29  push    r14
0x1800b3e2b  push    r15
0x1800b3e2d  sub     rsp, 2A8h
0x1800b3e34  mov     rax, cs:__security_cookie
0x1800b3e3b  xor     rax, rsp
0x1800b3e3e  mov     [rsp+2D8h+var_48], rax
0x1800b3e46  movaps  xmm0, xmmword ptr cs:aCommandLineArg; "<command line arguments omitted>"
0x1800b3e4d  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x1800b3e55  movaps  xmm1, xmmword ptr cs:aCommandLineArg+10h; " line arguments omitted>"
0x1800b3e5c  xor     r15d, r15d
0x1800b3e5f  movzx   eax, word ptr cs:aCommandLineArg+40h; ""
0x1800b3e66  mov     r8d, 104h; nSize
0x1800b3e6c  movaps  [rsp+2D8h+var_2A8], xmm0
0x1800b3e71  xor     ecx, ecx; hModule
0x1800b3e73  movaps  xmm0, xmmword ptr cs:aCommandLineArg+20h; "guments omitted>"
0x1800b3e7a  mov     ebx, r15d
0x1800b3e7d  movaps  [rsp+2D8h+var_298], xmm1
0x1800b3e82  mov     ebp, r15d
0x1800b3e85  movaps  xmm1, xmmword ptr cs:aCommandLineArg+30h; "omitted>"
0x1800b3e8c  movaps  [rsp+2D8h+var_288], xmm0
0x1800b3e91  movaps  [rsp+2D8h+var_278], xmm1
0x1800b3e96  mov     [rsp+2D8h+var_268], ax
0x1800b3e9b  call    cs:__imp_GetModuleFileNameW
0x1800b3ea1  test    eax, eax
0x1800b3ea3  jz      loc_1800B3FA2
0x1800b3ea9  xor     r9d, r9d; Context
0x1800b3eac  lea     rdx, SampInitIncludeArguments; InitFn
0x1800b3eb3  xor     r8d, r8d; Parameter
0x1800b3eb6  lea     rcx, InitOnce; InitOnce
0x1800b3ebd  call    cs:__imp_InitOnceExecuteOnce
0x1800b3ec3  mov     r14d, cs:dword_1800F0C04
0x1800b3eca  test    r14d, r14d
0x1800b3ecd  jz      short loc_1800B3F09
0x1800b3ecf  call    cs:__imp_GetCommandLineW
0x1800b3ed5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b3ed9  mov     rsi, rax
0x1800b3edc  lea     rax, [rsp+2D8h+Filename]
0x1800b3ee4  mov     rdx, rcx
0x1800b3ee7  inc     rdx
0x1800b3eea  cmp     [rax+rdx*2], r15w
0x1800b3eef  jnz     short loc_1800B3EE7
0x1800b3ef1  inc     rcx
0x1800b3ef4  cmp     [rsi+rcx*2], r15w
0x1800b3ef9  jnz     short loc_1800B3EF1
0x1800b3efb  lea     rax, [rdx+rcx]
0x1800b3eff  lea     rax, ds:8[rax*2]
0x1800b3f07  jmp     short loc_1800B3F3F
0x1800b3f09  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b3f0d  lea     rdx, [rsp+2D8h+var_2A8]
0x1800b3f12  mov     rax, rcx
0x1800b3f15  mov     rsi, r15
0x1800b3f18  inc     rax
0x1800b3f1b  cmp     [rdx+rax*2], r15w
0x1800b3f20  jnz     short loc_1800B3F18
0x1800b3f22  lea     rdx, [rsp+2D8h+Filename]
0x1800b3f2a  inc     rcx
0x1800b3f2d  cmp     [rdx+rcx*2], r15w
0x1800b3f32  jnz     short loc_1800B3F2A
0x1800b3f34  add     rax, rcx
0x1800b3f37  lea     rax, ds:4[rax*2]
0x1800b3f3f  mov     edx, eax; uBytes
0x1800b3f41  mov     ecx, 40h ; '@'; uFlags
0x1800b3f46  mov     edi, eax
0x1800b3f48  call    cs:__imp_LocalAlloc
0x1800b3f4e  mov     rbx, rax
0x1800b3f51  test    rax, rax
0x1800b3f54  jz      short loc_1800B3FA2
0x1800b3f56  mov     r8d, edi; Size
0x1800b3f59  xor     edx, edx; Val
0x1800b3f5b  mov     rcx, rax; void *
0x1800b3f5e  call    memset_0
0x1800b3f63  test    r14d, r14d
0x1800b3f66  lea     rax, aSS_2; "%s %s"
0x1800b3f6d  lea     rcx, [rsp+2D8h+var_2A8]
0x1800b3f72  mov     edx, edi; unsigned __int64
0x1800b3f74  cmovnz  rcx, rsi
0x1800b3f78  lea     r8, aSS; "%s (%s)"
0x1800b3f7f  mov     [rsp+2D8h+var_2B8], rcx
0x1800b3f84  lea     r9, [rsp+2D8h+Filename]
0x1800b3f8c  mov     rcx, rbx; unsigned __int16 *
0x1800b3f8f  cmovz   r8, rax; unsigned __int16 *
0x1800b3f93  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b3f98  test    eax, eax
0x1800b3f9a  js      short loc_1800B3FA2
0x1800b3f9c  mov     rbp, rbx
0x1800b3f9f  mov     rbx, r15
0x1800b3fa2  mov     rcx, rbx; hMem
0x1800b3fa5  call    cs:__imp_LocalFree
0x1800b3fab  mov     rax, rbp
0x1800b3fae  mov     rcx, [rsp+2D8h+var_48]
0x1800b3fb6  xor     rcx, rsp; StackCookie
0x1800b3fb9  call    __security_check_cookie
0x1800b3fbe  add     rsp, 2A8h
0x1800b3fc5  pop     r15
0x1800b3fc7  pop     r14
0x1800b3fc9  pop     rdi
0x1800b3fca  pop     rsi
0x1800b3fcb  pop     rbp
0x1800b3fcc  pop     rbx
0x1800b3fcd  retn
```
