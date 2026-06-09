# ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::Release(void)

- ea: `0x18000cbc0`
- end: `0x18000cc43`
- name: `?Release@?$CComObject@V?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@@ATL@@UEAAKXZ`
- size: `131`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000cbc0`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::Release(
        volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000cbc0  mov     [rsp+arg_0], rbx
0x18000cbc5  push    rdi
0x18000cbc6  sub     rsp, 30h
0x18000cbca  mov     rbx, rcx
0x18000cbcd  mov     r8d, [rcx+8]
0x18000cbd1  mov     ecx, 7FFFFFFFh
0x18000cbd6  jmp     short loc_18000CBEA
0x18000cbd8  lea     edx, [r8-1]
0x18000cbdc  mov     eax, r8d
0x18000cbdf  lock cmpxchg [rbx+8], edx
0x18000cbe4  jz      short loc_18000CBEF
0x18000cbe6  mov     r8d, [rbx+8]
0x18000cbea  cmp     r8d, ecx
0x18000cbed  jnz     short loc_18000CBD8
0x18000cbef  lea     edi, [r8-1]
0x18000cbf3  test    edi, edi
0x18000cbf5  jnz     short loc_18000CC36
0x18000cbf7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cbfe  mov     rax, [rcx]
0x18000cc01  mov     rax, [rax+8]
0x18000cc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc0a  nop
0x18000cc0b  test    rbx, rbx
0x18000cc0e  jz      short loc_18000CC23
0x18000cc10  mov     rax, [rbx]
0x18000cc13  lea     edx, [rdi+1]
0x18000cc16  mov     rcx, rbx
0x18000cc19  mov     rax, [rax+38h]
0x18000cc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc22  nop
0x18000cc23  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cc2a  mov     rdx, [rcx]
0x18000cc2d  mov     rax, [rdx+10h]
0x18000cc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc36  mov     eax, edi
0x18000cc38  mov     rbx, [rsp+38h+arg_0]
0x18000cc3d  add     rsp, 30h
0x18000cc41  pop     rdi
0x18000cc42  retn
```
