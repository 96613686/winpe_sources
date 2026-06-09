# SBF2::CComSBE2Table::GetDescriptor(__MIDL___MIDL_itf_sbeinternal_0000_0000_0002 * *)

- ea: `0x18009d630`
- end: `0x18009d6c6`
- name: `?GetDescriptor@CComSBE2Table@SBF2@@UEAAJPEAPEAU__MIDL___MIDL_itf_sbeinternal_0000_0000_0002@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(SBF2::CComSBE2Table *__hidden this, struct __MIDL___MIDL_itf_sbeinternal_0000_0000_0002 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18009d630`
- `0x18009e50c`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18009d6b6`
- `KERNEL32!LeaveCriticalSection` at `0x18009d6b6`
- `KERNEL32!EnterCriticalSection` at `0x18009d645`
- `KERNEL32!EnterCriticalSection` at `0x18009d645`
- `ole32!CoTaskMemFree` at `0x18009d6a2`
- `ole32!CoTaskMemFree` at `0x18009d6ad`
- `ole32!CoTaskMemFree` at `0x18009d6a2`
- `ole32!CoTaskMemFree` at `0x18009d6ad`

## pseudocode

```c
__int64 __fastcall SBF2::CComSBE2Table::GetDescriptor(SBF2::CComSBE2Table *this, LPVOID *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v5; // rcx
  int SBFTableHeadToSBE2TableDesc; // ebx
  unsigned int v8; // [rsp+50h] [rbp+8h] BYREF
  LPVOID v9; // [rsp+60h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v5 = *((_QWORD *)this + 1);
  pv = 0;
  v8 = 0;
  v9 = 0;
  SBFTableHeadToSBE2TableDesc = (*(__int64 (__fastcall **)(__int64, LPVOID *, unsigned int *, LPVOID *))(*(_QWORD *)v5 + 24LL))(
                                  v5,
                                  &pv,
                                  &v8,
                                  &v9);
  if ( SBFTableHeadToSBE2TableDesc >= 0 )
    SBFTableHeadToSBE2TableDesc = TranslateAndAllocateSBFTableHeadToSBE2TableDesc(v8, (__int64)v9, a2);
  CoTaskMemFree(pv);
  CoTaskMemFree(v9);
  LeaveCriticalSection(v2);
  return (unsigned int)SBFTableHeadToSBE2TableDesc;
}

```

## disassembly

```asm
0x18009d630  push    rbx
0x18009d632  push    rsi
0x18009d633  push    rdi
0x18009d634  sub     rsp, 30h
0x18009d638  lea     rdi, [rcx+10h]
0x18009d63c  mov     rbx, rcx
0x18009d63f  mov     rcx, rdi; lpCriticalSection
0x18009d642  mov     rsi, rdx
0x18009d645  call    cs:__imp_EnterCriticalSection
0x18009d64b  mov     rcx, [rbx+8]
0x18009d64f  lea     r9, [rsp+48h+arg_10]
0x18009d654  mov     [rsp+48h+pv], 0
0x18009d65d  lea     r8, [rsp+48h+arg_0]
0x18009d662  mov     [rsp+48h+arg_0], 0
0x18009d66a  lea     rdx, [rsp+48h+pv]
0x18009d66f  mov     [rsp+48h+arg_10], 0
0x18009d678  mov     rax, [rcx]
0x18009d67b  mov     rax, [rax+18h]
0x18009d67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d684  mov     ebx, eax
0x18009d686  test    eax, eax
0x18009d688  js      short loc_18009D69D
0x18009d68a  mov     rdx, [rsp+48h+arg_10]
0x18009d68f  mov     r8, rsi
0x18009d692  mov     ecx, [rsp+48h+arg_0]
0x18009d696  call    TranslateAndAllocateSBFTableHeadToSBE2TableDesc
0x18009d69b  mov     ebx, eax
0x18009d69d  mov     rcx, [rsp+48h+pv]; pv
0x18009d6a2  call    cs:__imp_CoTaskMemFree
0x18009d6a8  mov     rcx, [rsp+48h+arg_10]; pv
0x18009d6ad  call    cs:__imp_CoTaskMemFree
0x18009d6b3  mov     rcx, rdi; lpCriticalSection
0x18009d6b6  call    cs:__imp_LeaveCriticalSection
0x18009d6bc  mov     eax, ebx
0x18009d6be  add     rsp, 30h
0x18009d6c2  pop     rdi
0x18009d6c3  pop     rsi
0x18009d6c4  pop     rbx
0x18009d6c5  retn
```
