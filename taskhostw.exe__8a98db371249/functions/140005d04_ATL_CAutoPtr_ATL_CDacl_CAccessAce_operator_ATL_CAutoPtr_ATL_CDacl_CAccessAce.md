# ATL::CAutoPtr<ATL::CDacl::CAccessAce>::operator=(ATL::CAutoPtr<ATL::CDacl::CAccessAce> &)

- ea: `0x140005d04`
- end: `0x140005d4a`
- name: `??4?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAAAEAV01@AEAV01@@Z`
- size: `70`
- prototype: `__int64 (__fastcall ****__fastcall(__int64 (__fastcall ****)(_QWORD, __int64), _QWORD *))(_QWORD, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140005d50`

## callees

- `0x140005d04`
- `0x140005f00`

## pseudocode

```c
__int64 (__fastcall ****__fastcall ATL::CAutoPtr<ATL::CDacl::CAccessAce>::operator=(
        __int64 (__fastcall ****a1)(_QWORD, __int64),
        _QWORD *a2))(_QWORD, __int64)
{
  __int64 (__fastcall ***v4)(_QWORD, __int64); // rax

  if ( *a1 == (__int64 (__fastcall ***)(_QWORD, __int64))*a2 )
  {
    if ( a1 != a2 )
      *a2 = 0;
  }
  else
  {
    ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(a1);
    v4 = (__int64 (__fastcall ***)(_QWORD, __int64))*a2;
    *a2 = 0;
    *a1 = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x140005d04  mov     [rsp+arg_0], rbx
0x140005d09  push    rdi
0x140005d0a  sub     rsp, 20h
0x140005d0e  mov     rax, [rdx]
0x140005d11  mov     rdi, rdx
0x140005d14  mov     rbx, rcx
0x140005d17  cmp     [rcx], rax
0x140005d1a  jnz     short loc_140005D2A
0x140005d1c  cmp     rcx, rdx
0x140005d1f  jz      short loc_140005D3C
0x140005d21  mov     qword ptr [rdx], 0
0x140005d28  jmp     short loc_140005D3C
0x140005d2a  call    ??1?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAA@XZ; ATL::CAutoPtr<ATL::CDacl::CAccessAce>::~CAutoPtr<ATL::CDacl::CAccessAce>(void)
0x140005d2f  mov     rax, [rdi]
0x140005d32  mov     qword ptr [rdi], 0
0x140005d39  mov     [rbx], rax
0x140005d3c  mov     rax, rbx
0x140005d3f  mov     rbx, [rsp+28h+arg_0]
0x140005d44  add     rsp, 20h
0x140005d48  pop     rdi
0x140005d49  retn
```
