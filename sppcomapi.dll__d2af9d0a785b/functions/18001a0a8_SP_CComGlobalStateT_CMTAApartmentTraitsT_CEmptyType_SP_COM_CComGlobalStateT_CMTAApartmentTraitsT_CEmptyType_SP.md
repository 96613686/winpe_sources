# SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(void)

- ea: `0x18001a0a8`
- end: `0x18001a12b`
- name: `??1?$SP@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@V?$SP_COM@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@@@QEAA@XZ`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bd4c`

## callees

- `0x180019d04`
- `0x18001a0a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a10c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a10c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a0d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a0d2`

## pseudocode

```c
void __fastcall SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>::~SP<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>,SP_COM<CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v3; // rcx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      v3 = (void *)v1[8];
      if ( v3 )
      {
        CloseHandle(v3);
        v1[8] = 0;
      }
      CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>((__int64)(v1 + 3));
      CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>((__int64)(v1 + 1));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18001a0a8  mov     [rsp+arg_0], rbx
0x18001a0ad  push    rdi
0x18001a0ae  sub     rsp, 20h
0x18001a0b2  mov     rbx, [rcx]
0x18001a0b5  mov     rdi, rcx
0x18001a0b8  test    rbx, rbx
0x18001a0bb  jz      short loc_18001A11F
0x18001a0bd  or      eax, 0FFFFFFFFh
0x18001a0c0  lock xadd [rbx], eax
0x18001a0c4  cmp     eax, 1
0x18001a0c7  jnz     short loc_18001A118
0x18001a0c9  mov     rcx, [rbx+40h]; hObject
0x18001a0cd  test    rcx, rcx
0x18001a0d0  jz      short loc_18001A0E6
0x18001a0d2  call    cs:__imp_CloseHandle
0x18001a0d9  nop     dword ptr [rax+rax+00h]
0x18001a0de  mov     qword ptr [rbx+40h], 0
0x18001a0e6  lea     rcx, [rbx+18h]
0x18001a0ea  call    ??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)
0x18001a0ef  lea     rcx, [rbx+8]
0x18001a0f3  call    ??1?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::~CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>(void)
0x18001a0f8  call    cs:__imp_GetProcessHeap
0x18001a0ff  nop     dword ptr [rax+rax+00h]
0x18001a104  mov     r8, rbx; lpMem
0x18001a107  xor     edx, edx; dwFlags
0x18001a109  mov     rcx, rax; hHeap
0x18001a10c  call    cs:__imp_HeapFree
0x18001a113  nop     dword ptr [rax+rax+00h]
0x18001a118  mov     qword ptr [rdi], 0
0x18001a11f  mov     rbx, [rsp+28h+arg_0]
0x18001a124  add     rsp, 20h
0x18001a128  pop     rdi
0x18001a129  retn
```
