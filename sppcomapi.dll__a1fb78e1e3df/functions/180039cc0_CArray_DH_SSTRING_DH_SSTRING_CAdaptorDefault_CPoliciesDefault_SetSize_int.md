# CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x180039cc0`
- end: `0x180039e2c`
- name: `?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180037118`
- `0x1800376c0`
- `0x180038090`
- `0x180039398`

## callees

- `0x180003520`
- `0x180004288`
- `0x180039cc0`
- `0x18003c512`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039cfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039d71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039db4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039df8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039cfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039d71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039db4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039df8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039d86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039dc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039d86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039dc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039e0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039d0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039d0f`

## pseudocode

```c
__int64 __fastcall CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(__int64 a1, int a2)
{
  __int64 v2; // rsi
  void *v3; // rbx
  int v5; // ebp
  HANDLE v6; // rax
  void *v7; // rax
  unsigned int v8; // edi
  void *v9; // r12
  void *v10; // r13
  int v11; // r14d
  __int64 *v12; // r15
  __int64 v13; // rbx
  HANDLE ProcessHeap; // rax
  void *v15; // r14
  HANDLE v16; // rax
  void *v17; // rax

  v2 = a2;
  v3 = 0;
  if ( *(_DWORD *)a1 == a2 )
  {
LABEL_20:
    v8 = 0;
    goto LABEL_21;
  }
  v5 = *(_DWORD *)(a1 + 4);
  if ( a2 < v5 )
    v5 = a2;
  if ( a2 <= 0 )
  {
LABEL_9:
    v9 = v3;
    v10 = v3;
    if ( (int)v2 < *(_DWORD *)(a1 + 4) )
    {
      v11 = v2;
      do
      {
        v12 = (__int64 *)(*(_QWORD *)(a1 + 8) + 8LL * v11);
        if ( v12 )
        {
          v13 = *v12;
          if ( *v12 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, (LPVOID)(v13 - 4));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            *v12 = 0;
          }
        }
        ++v11;
      }
      while ( v11 < *(_DWORD *)(a1 + 4) );
    }
    v15 = *(void **)(a1 + 8);
    if ( v15 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v15);
      *(_QWORD *)(a1 + 8) = 0;
    }
    v17 = 0;
    if ( v9 )
      v17 = v10;
    *(_QWORD *)(a1 + 8) = v17;
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)a1 = v2;
    goto LABEL_20;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = GetProcessHeap();
  v7 = HeapAlloc(v6, 0, 8 * v2);
  v3 = v7;
  if ( v7 )
  {
    if ( v5 )
      memcpy_0(v7, *(const void **)(a1 + 8), 8LL * v5);
    goto LABEL_9;
  }
  v8 = -2147024882;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
LABEL_21:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  return v8;
}

```

## disassembly

```asm
0x180039cc0  push    rbx
0x180039cc2  push    rbp
0x180039cc3  push    rsi
0x180039cc4  push    rdi
0x180039cc5  push    r12
0x180039cc7  push    r13
0x180039cc9  push    r14
0x180039ccb  push    r15
0x180039ccd  sub     rsp, 28h
0x180039cd1  movsxd  rsi, edx
0x180039cd4  xor     ebx, ebx
0x180039cd6  mov     rdi, rcx
0x180039cd9  cmp     [rcx], esi
0x180039cdb  jz      loc_180039DEA
0x180039ce1  mov     ebp, [rcx+4]
0x180039ce4  cmp     esi, ebp
0x180039ce6  cmovl   ebp, esi
0x180039ce9  test    edx, edx
0x180039ceb  jle     short loc_180039D4B
0x180039ced  xor     ecx, ecx
0x180039cef  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039cf4  mov     rbx, rsi
0x180039cf7  shl     rbx, 3
0x180039cfb  call    cs:__imp_GetProcessHeap
0x180039d02  nop     dword ptr [rax+rax+00h]
0x180039d07  mov     r8, rbx; dwBytes
0x180039d0a  xor     edx, edx; dwFlags
0x180039d0c  mov     rcx, rax; hHeap
0x180039d0f  call    cs:__imp_HeapAlloc
0x180039d16  nop     dword ptr [rax+rax+00h]
0x180039d1b  mov     rbx, rax
0x180039d1e  test    rax, rax
0x180039d21  jnz     short loc_180039D34
0x180039d23  mov     edi, 8007000Eh
0x180039d28  mov     ecx, edi
0x180039d2a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039d2f  jmp     loc_180039DEC
0x180039d34  test    ebp, ebp
0x180039d36  jz      short loc_180039D4B
0x180039d38  mov     rdx, [rdi+8]; Src
0x180039d3c  mov     rcx, rax; void *
0x180039d3f  movsxd  r8, ebp
0x180039d42  shl     r8, 3; Size
0x180039d46  call    memcpy_0
0x180039d4b  mov     r12, rbx
0x180039d4e  mov     r13, rbx
0x180039d51  cmp     esi, [rdi+4]
0x180039d54  jge     short loc_180039DA9
0x180039d56  mov     r14d, esi
0x180039d59  mov     rcx, [rdi+8]
0x180039d5d  movsxd  rax, r14d
0x180039d60  lea     r15, [rcx+rax*8]
0x180039d64  test    r15, r15
0x180039d67  jz      short loc_180039DA0
0x180039d69  mov     rbx, [r15]
0x180039d6c  test    rbx, rbx
0x180039d6f  jz      short loc_180039DA0
0x180039d71  call    cs:__imp_GetProcessHeap
0x180039d78  nop     dword ptr [rax+rax+00h]
0x180039d7d  lea     r8, [rbx-4]; lpMem
0x180039d81  xor     edx, edx; dwFlags
0x180039d83  mov     rcx, rax; hHeap
0x180039d86  call    cs:__imp_HeapFree
0x180039d8d  nop     dword ptr [rax+rax+00h]
0x180039d92  xor     ecx, ecx
0x180039d94  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039d99  mov     qword ptr [r15], 0
0x180039da0  inc     r14d
0x180039da3  cmp     r14d, [rdi+4]
0x180039da7  jl      short loc_180039D59
0x180039da9  mov     r14, [rdi+8]
0x180039dad  xor     ebx, ebx
0x180039daf  test    r14, r14
0x180039db2  jz      short loc_180039DD8
0x180039db4  call    cs:__imp_GetProcessHeap
0x180039dbb  nop     dword ptr [rax+rax+00h]
0x180039dc0  mov     r8, r14; lpMem
0x180039dc3  xor     edx, edx; dwFlags
0x180039dc5  mov     rcx, rax; hHeap
0x180039dc8  call    cs:__imp_HeapFree
0x180039dcf  nop     dword ptr [rax+rax+00h]
0x180039dd4  mov     [rdi+8], rbx
0x180039dd8  xor     eax, eax
0x180039dda  test    r12, r12
0x180039ddd  cmovnz  rax, r13
0x180039de1  mov     [rdi+8], rax
0x180039de5  mov     [rdi+4], ebp
0x180039de8  mov     [rdi], esi
0x180039dea  xor     edi, edi
0x180039dec  mov     ecx, edi
0x180039dee  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039df3  test    rbx, rbx
0x180039df6  jz      short loc_180039E18
0x180039df8  call    cs:__imp_GetProcessHeap
0x180039dff  nop     dword ptr [rax+rax+00h]
0x180039e04  mov     r8, rbx; lpMem
0x180039e07  xor     edx, edx; dwFlags
0x180039e09  mov     rcx, rax; hHeap
0x180039e0c  call    cs:__imp_HeapFree
0x180039e13  nop     dword ptr [rax+rax+00h]
0x180039e18  mov     eax, edi
0x180039e1a  add     rsp, 28h
0x180039e1e  pop     r15
0x180039e20  pop     r14
0x180039e22  pop     r13
0x180039e24  pop     r12
0x180039e26  pop     rdi
0x180039e27  pop     rsi
0x180039e28  pop     rbp
0x180039e29  pop     rbx
0x180039e2a  retn
```
