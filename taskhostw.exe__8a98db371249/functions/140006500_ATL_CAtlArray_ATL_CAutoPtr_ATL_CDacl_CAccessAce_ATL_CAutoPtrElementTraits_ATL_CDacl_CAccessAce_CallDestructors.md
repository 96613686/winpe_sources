# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(ATL::CAutoPtr<ATL::CDacl::CAccessAce> *,unsigned __int64)

- ea: `0x140006500`
- end: `0x140006545`
- name: `?CallDestructors@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@CAXPEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@_K@Z`
- size: `69`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140002250`
- `0x140002df0`
- `0x140009850`

## callees

- `0x140006500`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 i; // rbx
  __int64 (__fastcall ***v5)(_QWORD, __int64); // rcx
  __int64 result; // rax

  if ( a2 )
  {
    for ( i = 0; i < a2; ++i )
    {
      v5 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a1 + 8 * i);
      if ( v5 )
        result = (**v5)(v5, 1);
      *(_QWORD *)(a1 + 8 * i) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006500  test    rdx, rdx
0x140006503  jz      short locret_140006544
0x140006505  push    rbx
0x140006506  push    rbp
0x140006507  push    rsi
0x140006508  push    rdi
0x140006509  sub     rsp, 28h
0x14000650d  xor     ebp, ebp
0x14000650f  mov     rdi, rdx
0x140006512  mov     ebx, ebp
0x140006514  mov     rsi, rcx
0x140006517  mov     rcx, [rsi+rbx*8]
0x14000651b  test    rcx, rcx
0x14000651e  jz      short loc_140006530
0x140006520  mov     rax, [rcx]
0x140006523  mov     edx, 1
0x140006528  mov     rax, [rax]
0x14000652b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006530  mov     [rsi+rbx*8], rbp
0x140006534  inc     rbx
0x140006537  cmp     rbx, rdi
0x14000653a  jb      short loc_140006517
0x14000653c  add     rsp, 28h
0x140006540  pop     rdi
0x140006541  pop     rsi
0x140006542  pop     rbp
0x140006543  pop     rbx
0x140006544  retn
```
