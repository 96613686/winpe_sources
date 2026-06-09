# ATL::CComObject<CPreflistFolder>::Release(void)

- ea: `0x18000b660`
- end: `0x18000b6bd`
- name: `?Release@?$CComObject@VCPreflistFolder@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b6d0`
- `0x18000b6e0`
- `0x18000b6f0`
- `0x18000b700`
- `0x18000b710`
- `0x18000b720`
- `0x18000b730`
- `0x18000b740`

## callees

- `0x180002c70`
- `0x18000b660`
- `0x18000b914`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPreflistFolder>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 20);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b660  mov     [rsp+arg_8], rbx
0x18000b665  push    rdi
0x18000b666  sub     rsp, 20h
0x18000b66a  mov     rbx, rcx
0x18000b66d  add     rcx, 50h ; 'P'; volatile int *
0x18000b671  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000b676  mov     edi, eax
0x18000b678  test    eax, eax
0x18000b67a  jnz     short loc_18000B6B0
0x18000b67c  lea     rcx, [rsp+28h+arg_0]; this
0x18000b681  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000b686  test    rbx, rbx
0x18000b689  jz      short loc_18000B69D
0x18000b68b  mov     rdx, [rbx]
0x18000b68e  mov     rcx, rbx
0x18000b691  mov     rax, [rdx+30h]
0x18000b695  lea     edx, [rdi+1]
0x18000b698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b69d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b6a4  mov     rax, [rcx]
0x18000b6a7  mov     rax, [rax+10h]
0x18000b6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6b0  mov     rbx, [rsp+28h+arg_8]
0x18000b6b5  mov     eax, edi
0x18000b6b7  add     rsp, 20h
0x18000b6bb  pop     rdi
0x18000b6bc  retn
```
