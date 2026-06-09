# CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x18001d750`
- end: `0x18001d859`
- name: `?SetSize@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ca2c`
- `0x18001cc48`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001d750`
- `0x18003c512`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d7e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d827`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d7e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d827`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d7fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d83b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d7fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d83b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d79d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d79d`

## pseudocode

```c
__int64 __fastcall CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(
        __int64 a1,
        int a2)
{
  __int64 v2; // rsi
  void *v3; // rbx
  int v5; // ebp
  HANDLE v6; // rax
  void *v7; // rax
  unsigned int v8; // edi
  void *v9; // r14
  HANDLE ProcessHeap; // rax
  void *v11; // rax

  v2 = a2;
  v3 = 0;
  if ( *(_DWORD *)a1 == a2 )
  {
LABEL_14:
    v8 = 0;
    goto LABEL_15;
  }
  v5 = *(_DWORD *)(a1 + 4);
  if ( a2 < v5 )
    v5 = a2;
  if ( a2 <= 0 )
  {
LABEL_9:
    v9 = *(void **)(a1 + 8);
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
    v11 = 0;
    if ( v3 )
      v11 = v3;
    *(_QWORD *)(a1 + 8) = v11;
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)a1 = v2;
    goto LABEL_14;
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
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  return v8;
}

```

## disassembly

```asm
0x18001d750  push    rbx
0x18001d752  push    rbp
0x18001d753  push    rsi
0x18001d754  push    rdi
0x18001d755  push    r12
0x18001d757  push    r14
0x18001d759  push    r15
0x18001d75b  sub     rsp, 20h
0x18001d75f  movsxd  rsi, edx
0x18001d762  xor     ebx, ebx
0x18001d764  mov     rdi, rcx
0x18001d767  cmp     [rcx], esi
0x18001d769  jz      loc_18001D819
0x18001d76f  mov     ebp, [rcx+4]
0x18001d772  cmp     esi, ebp
0x18001d774  cmovl   ebp, esi
0x18001d777  test    edx, edx
0x18001d779  jle     short loc_18001D7D6
0x18001d77b  xor     ecx, ecx
0x18001d77d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d782  mov     rbx, rsi
0x18001d785  shl     rbx, 3
0x18001d789  call    cs:__imp_GetProcessHeap
0x18001d790  nop     dword ptr [rax+rax+00h]
0x18001d795  mov     r8, rbx; dwBytes
0x18001d798  xor     edx, edx; dwFlags
0x18001d79a  mov     rcx, rax; hHeap
0x18001d79d  call    cs:__imp_HeapAlloc
0x18001d7a4  nop     dword ptr [rax+rax+00h]
0x18001d7a9  mov     rbx, rax
0x18001d7ac  test    rax, rax
0x18001d7af  jnz     short loc_18001D7BF
0x18001d7b1  mov     edi, 8007000Eh
0x18001d7b6  mov     ecx, edi
0x18001d7b8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d7bd  jmp     short loc_18001D81B
0x18001d7bf  test    ebp, ebp
0x18001d7c1  jz      short loc_18001D7D6
0x18001d7c3  mov     rdx, [rdi+8]; Src
0x18001d7c7  mov     rcx, rax; void *
0x18001d7ca  movsxd  r8, ebp
0x18001d7cd  shl     r8, 3; Size
0x18001d7d1  call    memcpy_0
0x18001d7d6  mov     r14, [rdi+8]
0x18001d7da  mov     r15, rbx
0x18001d7dd  mov     r12, rbx
0x18001d7e0  xor     ebx, ebx
0x18001d7e2  test    r14, r14
0x18001d7e5  jz      short loc_18001D807
0x18001d7e7  call    cs:__imp_GetProcessHeap
0x18001d7ee  nop     dword ptr [rax+rax+00h]
0x18001d7f3  mov     r8, r14; lpMem
0x18001d7f6  xor     edx, edx; dwFlags
0x18001d7f8  mov     rcx, rax; hHeap
0x18001d7fb  call    cs:__imp_HeapFree
0x18001d802  nop     dword ptr [rax+rax+00h]
0x18001d807  xor     eax, eax
0x18001d809  test    r15, r15
0x18001d80c  cmovnz  rax, r12
0x18001d810  mov     [rdi+8], rax
0x18001d814  mov     [rdi+4], ebp
0x18001d817  mov     [rdi], esi
0x18001d819  xor     edi, edi
0x18001d81b  mov     ecx, edi
0x18001d81d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d822  test    rbx, rbx
0x18001d825  jz      short loc_18001D847
0x18001d827  call    cs:__imp_GetProcessHeap
0x18001d82e  nop     dword ptr [rax+rax+00h]
0x18001d833  mov     r8, rbx; lpMem
0x18001d836  xor     edx, edx; dwFlags
0x18001d838  mov     rcx, rax; hHeap
0x18001d83b  call    cs:__imp_HeapFree
0x18001d842  nop     dword ptr [rax+rax+00h]
0x18001d847  mov     eax, edi
0x18001d849  add     rsp, 20h
0x18001d84d  pop     r15
0x18001d84f  pop     r14
0x18001d851  pop     r12
0x18001d853  pop     rdi
0x18001d854  pop     rsi
0x18001d855  pop     rbp
0x18001d856  pop     rbx
0x18001d857  retn
```
