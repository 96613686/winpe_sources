# ATL::CDacl::RemoveAllAces(void)

- ea: `0x1400021b0`
- end: `0x1400021db`
- name: `?RemoveAllAces@CDacl@ATL@@UEAAXXZ`
- size: `43`
- prototype: `void __fastcall(void **this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140002c50`

## import_xrefs

- `msvcrt!free` at `0x1400021c7`
- `msvcrt!free` at `0x1400021c7`

## pseudocode

```c
void __fastcall ATL::CDacl::RemoveAllAces(void **this)
{
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::SetCount(this + 3);
  free(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x1400021b0  push    rbx
0x1400021b2  sub     rsp, 20h
0x1400021b6  mov     rbx, rcx
0x1400021b9  add     rcx, 18h
0x1400021bd  call    ?SetCount@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::SetCount(unsigned __int64,int)
0x1400021c2  nop
0x1400021c3  mov     rcx, [rbx+8]; Block
0x1400021c7  call    cs:__imp_free
0x1400021cd  mov     qword ptr [rbx+8], 0
0x1400021d5  add     rsp, 20h
0x1400021d9  pop     rbx
0x1400021da  retn
```
