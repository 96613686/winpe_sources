# SampQueryCallingProcessInfo(void)

- ea: `0x1800160d8`
- end: `0x180016282`
- name: `?SampQueryCallingProcessInfo@@YAPEAGXZ`
- size: `426`
- prototype: `unsigned __int16 *(void)`
- caller_count: `50`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001080`
- `0x1800011f0`
- `0x180001450`
- `0x1800016a0`
- `0x180001800`
- `0x180001a30`
- `0x180001c50`
- `0x180001ea0`
- `0x180002390`
- `0x180002530`
- `0x180002870`
- `0x180002a80`
- `0x180002e90`
- `0x1800033c0`
- `0x180003760`
- `0x1800038b0`
- `0x180004dd0`
- `0x18000c650`
- `0x18000c850`
- `0x18000ca60`
- `0x18000ccb0`
- `0x18000d020`
- `0x18000d330`
- `0x18000d630`
- `0x18000d930`
- `0x18000dde0`
- `0x18000e0e0`
- `0x18000e2e0`
- `0x18000e4e0`
- `0x18000e6e0`
- `0x18000e9c0`
- `0x18000eca0`
- `0x18000ef50`
- `0x18000f210`
- `0x18000f5c0`
- `0x18000fed0`
- `0x180010170`
- `0x180010410`
- `0x180010830`
- `0x180010a40`
- `0x180010e70`
- `0x1800110c0`
- `0x1800112c0`
- `0x1800114c0`
- `0x1800116c0`
- `0x180011aa0`
- `0x180011cb0`
- `0x180011ec0`
- `0x1800120d0`
- `0x1800123b0`

## callees

- `0x180006620`
- `0x180006ec2`
- `0x180015cbc`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001614f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001614f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016259`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016259`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800161fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800161fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016171`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016171`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180016183`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180016183`

## string_xrefs

- `0x1800160fa`: `<command line arguments omitted>`

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
    v2 = dword_180027238;
    if ( dword_180027238 )
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
0x1800160d8  push    rbx
0x1800160da  push    rbp
0x1800160db  push    rsi
0x1800160dc  push    rdi
0x1800160dd  push    r14
0x1800160df  push    r15
0x1800160e1  sub     rsp, 2A8h
0x1800160e8  mov     rax, cs:__security_cookie
0x1800160ef  xor     rax, rsp
0x1800160f2  mov     [rsp+2D8h+var_48], rax
0x1800160fa  movaps  xmm0, xmmword ptr cs:aCommandLineArg; "<command line arguments omitted>"
0x180016101  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x180016109  movaps  xmm1, xmmword ptr cs:aCommandLineArg+10h; " line arguments omitted>"
0x180016110  xor     r15d, r15d
0x180016113  movzx   eax, word ptr cs:aCommandLineArg+40h; ""
0x18001611a  mov     r8d, 104h; nSize
0x180016120  movaps  [rsp+2D8h+var_2A8], xmm0
0x180016125  xor     ecx, ecx; hModule
0x180016127  movaps  xmm0, xmmword ptr cs:aCommandLineArg+20h; "guments omitted>"
0x18001612e  mov     ebx, r15d
0x180016131  movaps  [rsp+2D8h+var_298], xmm1
0x180016136  mov     ebp, r15d
0x180016139  movaps  xmm1, xmmword ptr cs:aCommandLineArg+30h; "omitted>"
0x180016140  movaps  [rsp+2D8h+var_288], xmm0
0x180016145  movaps  [rsp+2D8h+var_278], xmm1
0x18001614a  mov     [rsp+2D8h+var_268], ax
0x18001614f  call    cs:__imp_GetModuleFileNameW
0x180016155  test    eax, eax
0x180016157  jz      loc_180016256
0x18001615d  xor     r9d, r9d; Context
0x180016160  lea     rdx, SampInitIncludeArguments; InitFn
0x180016167  xor     r8d, r8d; Parameter
0x18001616a  lea     rcx, InitOnce; InitOnce
0x180016171  call    cs:__imp_InitOnceExecuteOnce
0x180016177  mov     r14d, cs:dword_180027238
0x18001617e  test    r14d, r14d
0x180016181  jz      short loc_1800161BD
0x180016183  call    cs:__imp_GetCommandLineW
0x180016189  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001618d  mov     rsi, rax
0x180016190  lea     rax, [rsp+2D8h+Filename]
0x180016198  mov     rdx, rcx
0x18001619b  inc     rdx
0x18001619e  cmp     [rax+rdx*2], r15w
0x1800161a3  jnz     short loc_18001619B
0x1800161a5  inc     rcx
0x1800161a8  cmp     [rsi+rcx*2], r15w
0x1800161ad  jnz     short loc_1800161A5
0x1800161af  lea     rax, [rdx+rcx]
0x1800161b3  lea     rax, ds:8[rax*2]
0x1800161bb  jmp     short loc_1800161F3
0x1800161bd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800161c1  lea     rdx, [rsp+2D8h+var_2A8]
0x1800161c6  mov     rax, rcx
0x1800161c9  mov     rsi, r15
0x1800161cc  inc     rax
0x1800161cf  cmp     [rdx+rax*2], r15w
0x1800161d4  jnz     short loc_1800161CC
0x1800161d6  lea     rdx, [rsp+2D8h+Filename]
0x1800161de  inc     rcx
0x1800161e1  cmp     [rdx+rcx*2], r15w
0x1800161e6  jnz     short loc_1800161DE
0x1800161e8  add     rax, rcx
0x1800161eb  lea     rax, ds:4[rax*2]
0x1800161f3  mov     edx, eax; uBytes
0x1800161f5  mov     ecx, 40h ; '@'; uFlags
0x1800161fa  mov     edi, eax
0x1800161fc  call    cs:__imp_LocalAlloc
0x180016202  mov     rbx, rax
0x180016205  test    rax, rax
0x180016208  jz      short loc_180016256
0x18001620a  mov     r8d, edi; Size
0x18001620d  xor     edx, edx; Val
0x18001620f  mov     rcx, rax; void *
0x180016212  call    memset_0
0x180016217  test    r14d, r14d
0x18001621a  lea     rax, aSS_0; "%s %s"
0x180016221  lea     rcx, [rsp+2D8h+var_2A8]
0x180016226  mov     edx, edi; unsigned __int64
0x180016228  cmovnz  rcx, rsi
0x18001622c  lea     r8, aSS; "%s (%s)"
0x180016233  mov     [rsp+2D8h+var_2B8], rcx
0x180016238  lea     r9, [rsp+2D8h+Filename]
0x180016240  mov     rcx, rbx; unsigned __int16 *
0x180016243  cmovz   r8, rax; unsigned __int16 *
0x180016247  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001624c  test    eax, eax
0x18001624e  js      short loc_180016256
0x180016250  mov     rbp, rbx
0x180016253  mov     rbx, r15
0x180016256  mov     rcx, rbx; hMem
0x180016259  call    cs:__imp_LocalFree
0x18001625f  mov     rax, rbp
0x180016262  mov     rcx, [rsp+2D8h+var_48]
0x18001626a  xor     rcx, rsp; StackCookie
0x18001626d  call    __security_check_cookie
0x180016272  add     rsp, 2A8h
0x180016279  pop     r15
0x18001627b  pop     r14
0x18001627d  pop     rdi
0x18001627e  pop     rsi
0x18001627f  pop     rbp
0x180016280  pop     rbx
0x180016281  retn
```
