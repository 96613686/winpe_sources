# CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)

- ea: `0x180019d04`
- end: `0x180019da7`
- name: `??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a0a8`
- `0x18001bd4c`

## callees

- `0x180004288`
- `0x180019d04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d82`

## pseudocode

```c
int __fastcall CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(
        __int64 a1)
{
  void *v2; // rsi
  int v3; // edi
  HANDLE ProcessHeap; // rax
  int result; // eax
  void *v6; // rdi
  HANDLE v7; // rax

  if ( *(_DWORD *)a1 )
  {
    v2 = *(void **)(a1 + 8);
    v3 = 0;
    if ( *(int *)(a1 + 4) <= 0 )
      v3 = *(_DWORD *)(a1 + 4);
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 4) = v3;
    *(_DWORD *)a1 = 0;
  }
  result = CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = *(void **)(a1 + 8);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    result = HeapFree(v7, 0, v6);
    *(_QWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180019d04  mov     [rsp+arg_0], rbx
0x180019d09  mov     [rsp+arg_8], rsi
0x180019d0e  push    rdi
0x180019d0f  sub     rsp, 20h
0x180019d13  cmp     dword ptr [rcx], 0
0x180019d16  mov     rbx, rcx
0x180019d19  jz      short loc_180019D5E
0x180019d1b  mov     rsi, [rcx+8]
0x180019d1f  xor     edi, edi
0x180019d21  cmp     [rcx+4], edi
0x180019d24  cmovle  edi, [rcx+4]
0x180019d28  test    rsi, rsi
0x180019d2b  jz      short loc_180019D4D
0x180019d2d  call    cs:__imp_GetProcessHeap
0x180019d34  nop     dword ptr [rax+rax+00h]
0x180019d39  mov     r8, rsi; lpMem
0x180019d3c  xor     edx, edx; dwFlags
0x180019d3e  mov     rcx, rax; hHeap
0x180019d41  call    cs:__imp_HeapFree
0x180019d48  nop     dword ptr [rax+rax+00h]
0x180019d4d  mov     qword ptr [rbx+8], 0
0x180019d55  mov     [rbx+4], edi
0x180019d58  mov     dword ptr [rbx], 0
0x180019d5e  xor     ecx, ecx
0x180019d60  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180019d65  mov     rdi, [rbx+8]
0x180019d69  test    rdi, rdi
0x180019d6c  jz      short loc_180019D96
0x180019d6e  call    cs:__imp_GetProcessHeap
0x180019d75  nop     dword ptr [rax+rax+00h]
0x180019d7a  mov     r8, rdi; lpMem
0x180019d7d  xor     edx, edx; dwFlags
0x180019d7f  mov     rcx, rax; hHeap
0x180019d82  call    cs:__imp_HeapFree
0x180019d89  nop     dword ptr [rax+rax+00h]
0x180019d8e  mov     qword ptr [rbx+8], 0
0x180019d96  mov     rbx, [rsp+28h+arg_0]
0x180019d9b  mov     rsi, [rsp+28h+arg_8]
0x180019da0  add     rsp, 20h
0x180019da4  pop     rdi
0x180019da5  retn
```
