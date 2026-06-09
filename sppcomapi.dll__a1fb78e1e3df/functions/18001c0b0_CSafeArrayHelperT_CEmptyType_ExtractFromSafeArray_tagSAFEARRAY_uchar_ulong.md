# CSafeArrayHelperT<CEmptyType>::ExtractFromSafeArray(tagSAFEARRAY *,uchar * *,ulong *)

- ea: `0x18001c0b0`
- end: `0x18001c1f2`
- name: `?ExtractFromSafeArray@?$CSafeArrayHelperT@VCEmptyType@@@@SAJPEAUtagSAFEARRAY@@PEAPEAEPEAK@Z`
- size: `322`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, __int64 *, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d490`
- `0x18001d630`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001c0b0`
- `0x18003c512`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c102`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c1c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c102`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c1c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c1d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c1d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c116`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c116`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001c142`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001c142`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001c173`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001c173`

## pseudocode

```c
__int64 __fastcall CSafeArrayHelperT<CEmptyType>::ExtractFromSafeArray(SAFEARRAY *psa, __int64 *a2, _DWORD *a3)
{
  __int64 v3; // rax
  char v7; // r9
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rsi
  size_t cElements; // rbp
  HANDLE ProcessHeap; // rax
  HRESULT v13; // eax
  __int64 v14; // rcx
  HANDLE v15; // rax
  void *ppvData; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  ppvData = 0;
  v7 = 1;
  if ( psa->cDims )
  {
    v8 = 0;
    if ( psa->cDims != 1 || psa->cbElements != 1 )
    {
      v9 = -2147024809;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
      v10 = 0;
      goto LABEL_15;
    }
    cElements = psa->rgsabound[0].cElements;
    ProcessHeap = GetProcessHeap();
    v8 = (__int64)HeapAlloc(ProcessHeap, 0, (unsigned int)cElements);
    if ( !v8 )
    {
      v9 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
      v10 = 0;
      goto LABEL_15;
    }
    v13 = SafeArrayAccessData(psa, &ppvData);
    v9 = v13;
    if ( v13 < 0 || (memcpy_0((void *)v8, ppvData, cElements), v13 = SafeArrayUnaccessData(psa), v9 = v13, v13 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
      v10 = v8;
      goto LABEL_15;
    }
    v7 = 0;
    v3 = v8;
  }
  else
  {
    v9 = 0;
    LODWORD(cElements) = 0;
    v8 = 0;
  }
  v14 = 0;
  *a3 = cElements;
  if ( !v7 )
    v14 = v8;
  *a2 = v14;
  v10 = v8 & -(__int64)(v7 != 0);
  v8 = v3 & -(__int64)(v7 != 0);
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v10 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, (LPVOID)v8);
  }
  return v9;
}

```

## disassembly

```asm
0x18001c0b0  push    rbx
0x18001c0b2  push    rbp
0x18001c0b3  push    rsi
0x18001c0b4  push    rdi
0x18001c0b5  push    r14
0x18001c0b7  push    r15
0x18001c0b9  sub     rsp, 28h
0x18001c0bd  xor     eax, eax
0x18001c0bf  mov     [rsp+58h+ppvData], 0
0x18001c0c8  mov     r14, r8
0x18001c0cb  mov     r15, rdx
0x18001c0ce  mov     rsi, rcx
0x18001c0d1  lea     r9d, [rax+1]
0x18001c0d5  cmp     ax, [rcx]
0x18001c0d8  jz      loc_18001C18D
0x18001c0de  xor     edi, edi
0x18001c0e0  cmp     r9w, [rcx]
0x18001c0e4  jnz     short loc_18001C0EC
0x18001c0e6  cmp     [rcx+4], r9d
0x18001c0ea  jz      short loc_18001C0FF
0x18001c0ec  mov     ecx, 80070057h
0x18001c0f1  mov     ebx, ecx
0x18001c0f3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c0f8  xor     esi, esi
0x18001c0fa  jmp     loc_18001C1B6
0x18001c0ff  mov     ebp, [rcx+18h]
0x18001c102  call    cs:__imp_GetProcessHeap
0x18001c109  nop     dword ptr [rax+rax+00h]
0x18001c10e  mov     r8d, ebp; dwBytes
0x18001c111  xor     edx, edx; dwFlags
0x18001c113  mov     rcx, rax; hHeap
0x18001c116  call    cs:__imp_HeapAlloc
0x18001c11d  nop     dword ptr [rax+rax+00h]
0x18001c122  mov     rdi, rax
0x18001c125  test    rax, rax
0x18001c128  jnz     short loc_18001C13A
0x18001c12a  mov     ebx, 8007000Eh
0x18001c12f  mov     ecx, ebx
0x18001c131  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c136  xor     esi, esi
0x18001c138  jmp     short loc_18001C1B6
0x18001c13a  lea     rdx, [rsp+58h+ppvData]; ppvData
0x18001c13f  mov     rcx, rsi; psa
0x18001c142  call    cs:__imp_SafeArrayAccessData
0x18001c149  nop     dword ptr [rax+rax+00h]
0x18001c14e  mov     ebx, eax
0x18001c150  test    eax, eax
0x18001c152  jns     short loc_18001C160
0x18001c154  mov     ecx, eax
0x18001c156  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c15b  mov     rsi, rdi
0x18001c15e  jmp     short loc_18001C1B6
0x18001c160  mov     rdx, [rsp+58h+ppvData]; Src
0x18001c165  mov     r8, rbp; Size
0x18001c168  mov     rcx, rdi; void *
0x18001c16b  call    memcpy_0
0x18001c170  mov     rcx, rsi; psa
0x18001c173  call    cs:__imp_SafeArrayUnaccessData
0x18001c17a  nop     dword ptr [rax+rax+00h]
0x18001c17f  mov     ebx, eax
0x18001c181  test    eax, eax
0x18001c183  js      short loc_18001C154
0x18001c185  xor     r9b, r9b
0x18001c188  mov     rax, rdi
0x18001c18b  jmp     short loc_18001C193
0x18001c18d  xor     ebx, ebx
0x18001c18f  xor     ebp, ebp
0x18001c191  xor     edi, edi
0x18001c193  xor     ecx, ecx
0x18001c195  mov     [r14], ebp
0x18001c198  test    r9b, r9b
0x18001c19b  cmovz   rcx, rdi
0x18001c19f  mov     [r15], rcx
0x18001c1a2  mov     cl, r9b
0x18001c1a5  neg     cl
0x18001c1a7  sbb     rsi, rsi
0x18001c1aa  and     rsi, rdi
0x18001c1ad  neg     r9b
0x18001c1b0  sbb     rdi, rdi
0x18001c1b3  and     rdi, rax
0x18001c1b6  mov     ecx, ebx
0x18001c1b8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c1bd  test    rsi, rsi
0x18001c1c0  jz      short loc_18001C1E2
0x18001c1c2  call    cs:__imp_GetProcessHeap
0x18001c1c9  nop     dword ptr [rax+rax+00h]
0x18001c1ce  mov     r8, rdi; lpMem
0x18001c1d1  xor     edx, edx; dwFlags
0x18001c1d3  mov     rcx, rax; hHeap
0x18001c1d6  call    cs:__imp_HeapFree
0x18001c1dd  nop     dword ptr [rax+rax+00h]
0x18001c1e2  mov     eax, ebx
0x18001c1e4  add     rsp, 28h
0x18001c1e8  pop     r15
0x18001c1ea  pop     r14
0x18001c1ec  pop     rdi
0x18001c1ed  pop     rsi
0x18001c1ee  pop     rbp
0x18001c1ef  pop     rbx
0x18001c1f0  retn
```
