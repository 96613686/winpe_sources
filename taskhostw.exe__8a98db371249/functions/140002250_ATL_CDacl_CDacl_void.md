# ATL::CDacl::~CDacl(void)

- ea: `0x140002250`
- end: `0x1400022c0`
- name: `??1CDacl@ATL@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140009500`
- `0x14000aae0`

## callees

- `0x140002250`
- `0x140002c50`
- `0x140006500`

## import_xrefs

- `msvcrt!free` at `0x140002275`
- `msvcrt!free` at `0x1400022b8`
- `msvcrt!free` at `0x140002275`
- `msvcrt!free` at `0x1400022a4`
- `msvcrt!free` at `0x1400022b8`

## pseudocode

```c
void __fastcall ATL::CDacl::~CDacl(void **this)
{
  void *v2; // rcx

  *this = &ATL::CDacl::`vftable';
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::SetCount(this + 3);
  free(this[1]);
  this[1] = 0;
  v2 = this[3];
  if ( v2 )
  {
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
      v2,
      this[4]);
    free(this[3]);
  }
  *this = &ATL::CAcl::`vftable';
  free(this[1]);
}

```

## disassembly

```asm
0x140002250  mov     [rsp+arg_0], rbx
0x140002255  push    rdi
0x140002256  sub     rsp, 20h
0x14000225a  mov     rbx, rcx
0x14000225d  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x140002264  mov     [rcx], rax
0x140002267  add     rcx, 18h
0x14000226b  call    ?SetCount@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::SetCount(unsigned __int64,int)
0x140002270  nop
0x140002271  mov     rcx, [rbx+8]; Block
0x140002275  call    cs:__imp_free
0x14000227b  mov     qword ptr [rbx+8], 0
0x140002283  mov     rcx, [rbx+18h]
0x140002287  test    rcx, rcx
0x14000228a  jnz     short loc_1400022AB
0x14000228c  lea     rax, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x140002293  mov     [rbx], rax
0x140002296  mov     rcx, [rbx+8]
0x14000229a  mov     rbx, [rsp+28h+arg_0]
0x14000229f  add     rsp, 20h
0x1400022a3  pop     rdi
0x1400022a4  jmp     cs:__imp_free
0x1400022ab  mov     rdx, [rbx+20h]
0x1400022af  call    ?CallDestructors@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@CAXPEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(ATL::CAutoPtr<ATL::CDacl::CAccessAce> *,unsigned __int64)
0x1400022b4  mov     rcx, [rbx+18h]; Block
0x1400022b8  call    cs:__imp_free
0x1400022be  jmp     short loc_14000228C
```
