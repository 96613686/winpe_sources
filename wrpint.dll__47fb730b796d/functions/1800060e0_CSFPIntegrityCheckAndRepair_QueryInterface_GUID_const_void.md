# CSFPIntegrityCheckAndRepair::QueryInterface(_GUID const &,void * *)

- ea: `0x1800060e0`
- end: `0x180006146`
- name: `?QueryInterface@CSFPIntegrityCheckAndRepair@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800060e0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::QueryInterface(
        CSFPIntegrityCheckAndRepair *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_OWORD *)&IID_IUnknown != *(_OWORD *)a2
    && (*(_QWORD *)&GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47.Data1 != *(_QWORD *)&a2->Data1
     || *(_QWORD *)GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47.Data4 != *(_QWORD *)a2->Data4) )
  {
    return 2147500034LL;
  }
  *a3 = this;
  (*(void (__fastcall **)(CSFPIntegrityCheckAndRepair *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x1800060e0  sub     rsp, 28h
0x1800060e4  test    r8, r8
0x1800060e7  jnz     short loc_1800060F0
0x1800060e9  mov     eax, 80004003h
0x1800060ee  jmp     short loc_180006141
0x1800060f0  mov     qword ptr [r8], 0
0x1800060f7  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x1800060fe  cmp     rax, [rdx]
0x180006101  jnz     short loc_180006110
0x180006103  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18000610a  cmp     rax, [rdx+8]
0x18000610e  jz      short loc_180006129
0x180006110  mov     rax, qword ptr cs:_GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47.Data1
0x180006117  cmp     rax, [rdx]
0x18000611a  jnz     short loc_18000613C
0x18000611c  mov     rax, qword ptr cs:_GUID_90ed9faa_a6e5_4671_8e50_1c060f8b9c47.Data4
0x180006123  cmp     rax, [rdx+8]
0x180006127  jnz     short loc_18000613C
0x180006129  mov     [r8], rcx
0x18000612c  mov     rax, [rcx]
0x18000612f  mov     rax, [rax+8]
0x180006133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006138  xor     eax, eax
0x18000613a  jmp     short loc_180006141
0x18000613c  mov     eax, 80004002h
0x180006141  add     rsp, 28h
0x180006145  retn
```
