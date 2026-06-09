# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](unsigned __int64)

- ea: `0x140006770`
- end: `0x140006791`
- name: `??A?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAAAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@1@_K@Z`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140005d50`

## callees

- `0x140006770`
- `0x1400072bc`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
        _QWORD *a1,
        unsigned __int64 a2)
{
  if ( a2 >= a1[1] )
    ATL::PrivateAtlThrow(-2147024809);
  return *a1 + 8 * a2;
}

```

## disassembly

```asm
0x140006770  sub     rsp, 28h
0x140006774  cmp     rdx, [rcx+8]
0x140006778  jnb     short loc_140006786
0x14000677a  mov     rax, [rcx]
0x14000677d  lea     rax, [rax+rdx*8]
0x140006781  add     rsp, 28h
0x140006785  retn
0x140006786  mov     ecx, 80070057h; int
0x14000678b  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
