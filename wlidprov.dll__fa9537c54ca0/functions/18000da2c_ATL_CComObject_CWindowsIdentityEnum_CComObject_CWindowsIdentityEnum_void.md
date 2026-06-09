# ATL::CComObject<CWindowsIdentityEnum>::~CComObject<CWindowsIdentityEnum>(void)

- ea: `0x18000da2c`
- end: `0x18000da86`
- name: `??1?$CComObject@VCWindowsIdentityEnum@@@ATL@@UEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d9f0`

## callees

- `0x18000da2c`
- `0x18000da8c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da5d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da5d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da7a`

## pseudocode

```c
void __fastcall ATL::CComObject<CWindowsIdentityEnum>::~CComObject<CWindowsIdentityEnum>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CWindowsIdentityEnum>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  CMIDLPtrArray<unsigned short *>::Clear(a1 + 64);
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_BYTE *)(a1 + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
}

```

## disassembly

```asm
0x18000da2c  push    rbx
0x18000da2e  sub     rsp, 20h
0x18000da32  mov     dword ptr [rcx+8], 0C0000001h
0x18000da39  lea     rax, ??_7?$CComObject@VCWindowsIdentityEnum@@@ATL@@6B@; const ATL::CComObject<CWindowsIdentityEnum>::`vftable'
0x18000da40  mov     [rcx], rax
0x18000da43  mov     rbx, rcx
0x18000da46  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000da4d  mov     rax, [rcx]
0x18000da50  mov     rax, [rax+10h]
0x18000da54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da59  lea     rcx, [rbx+58h]; lpCriticalSection
0x18000da5d  call    cs:__imp_DeleteCriticalSection
0x18000da63  lea     rcx, [rbx+40h]
0x18000da67  call    ?Clear@?$CMIDLPtrArray@PEAG@@QEAAXXZ; CMIDLPtrArray<ushort *>::Clear(void)
0x18000da6c  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000da70  cmp     byte ptr [rcx+28h], 0
0x18000da74  jz      short loc_18000DA80
0x18000da76  mov     byte ptr [rcx+28h], 0
0x18000da7a  call    cs:__imp_DeleteCriticalSection
0x18000da80  add     rsp, 20h
0x18000da84  pop     rbx
0x18000da85  retn
```
