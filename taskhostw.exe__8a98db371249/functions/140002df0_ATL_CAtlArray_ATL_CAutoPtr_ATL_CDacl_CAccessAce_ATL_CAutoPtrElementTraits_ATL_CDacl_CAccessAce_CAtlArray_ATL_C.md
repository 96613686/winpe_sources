# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)

- ea: `0x140002df0`
- end: `0x140002e1b`
- name: `??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400022d0`

## callees

- `0x140002df0`
- `0x140006500`

## import_xrefs

- `msvcrt!free` at `0x140002e13`
- `msvcrt!free` at `0x140002e13`

## pseudocode

```c
void __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
      v2,
      *(_QWORD *)(a1 + 8));
    free(*(void **)a1);
  }
}

```

## disassembly

```asm
0x140002df0  push    rbx
0x140002df2  sub     rsp, 20h
0x140002df6  mov     rbx, rcx
0x140002df9  mov     rcx, [rcx]
0x140002dfc  test    rcx, rcx
0x140002dff  jnz     short loc_140002E07
0x140002e01  add     rsp, 20h
0x140002e05  pop     rbx
0x140002e06  retn
0x140002e07  mov     rdx, [rbx+8]
0x140002e0b  call    ?CallDestructors@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@CAXPEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(ATL::CAutoPtr<ATL::CDacl::CAccessAce> *,unsigned __int64)
0x140002e10  mov     rcx, [rbx]; Block
0x140002e13  call    cs:__imp_free
0x140002e19  jmp     short loc_140002E01
```
