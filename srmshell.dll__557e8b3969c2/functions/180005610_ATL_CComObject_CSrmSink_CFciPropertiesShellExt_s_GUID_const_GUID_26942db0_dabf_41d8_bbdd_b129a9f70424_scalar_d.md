# ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::`scalar deleting destructor'(uint)

- ea: `0x180005610`
- end: `0x180005681`
- name: `??_G?$CComObject@V?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@@ATL@@UEAAPEAXI@Z`
- size: `113`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180005610`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005670`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005670`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005661`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005661`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  char *v4; // rbx

  *(_QWORD *)a1 = &ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::`vftable';
  v4 = (char *)(a1 + 2);
  a1[2] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( v4[48] )
  {
    v4[48] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180005610  mov     [rsp+arg_0], rcx
0x180005615  push    rbx
0x180005616  push    rsi
0x180005617  push    rdi
0x180005618  sub     rsp, 20h
0x18000561c  mov     esi, edx
0x18000561e  mov     rdi, rcx
0x180005621  lea     rax, ??_7?$CComObject@V?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@@ATL@@6B@; const ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::`vftable'
0x180005628  mov     [rcx], rax
0x18000562b  lea     rbx, [rcx+8]
0x18000562f  mov     dword ptr [rbx], 0C0000001h
0x180005635  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000563c  mov     rax, [rcx]
0x18000563f  mov     rax, [rax+10h]
0x180005643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005648  nop
0x180005649  mov     [rsp+38h+arg_10], rbx
0x18000564e  lea     rcx, [rbx+8]; lpCriticalSection
0x180005652  mov     [rsp+38h+arg_18], rcx
0x180005657  cmp     byte ptr [rcx+28h], 0
0x18000565b  jz      short loc_180005667
0x18000565d  mov     byte ptr [rcx+28h], 0
0x180005661  call    cs:__imp_DeleteCriticalSection
0x180005667  test    sil, 1
0x18000566b  jz      short loc_180005676
0x18000566d  mov     rcx, rdi
0x180005670  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005676  mov     rax, rdi
0x180005679  add     rsp, 20h
0x18000567d  pop     rdi
0x18000567e  pop     rsi
0x18000567f  pop     rbx
0x180005680  retn
```
