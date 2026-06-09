# CWMIContext::WriteWarning(wchar_t const *)

- ea: `0x180006560`
- end: `0x180006591`
- name: `?WriteWarning@CWMIContext@@UEAAXPEB_W@Z`
- size: `49`
- prototype: `void __fastcall(CWMIContext *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006560`
- `0x18002d010`

## pseudocode

```c
void __fastcall CWMIContext::WriteWarning(CWMIContext *this, const wchar_t *a2)
{
  __int64 v2; // rcx

  if ( a2 )
  {
    v2 = *((_QWORD *)this + 7);
    if ( v2 )
    {
      if ( *(_QWORD *)v2 )
        (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *))(*(_QWORD *)v2 + 160LL))(v2, 0, a2);
    }
  }
}

```

## disassembly

```asm
0x180006560  sub     rsp, 28h
0x180006564  test    rdx, rdx
0x180006567  jz      short loc_18000658B
0x180006569  mov     rcx, [rcx+38h]
0x18000656d  test    rcx, rcx
0x180006570  jz      short loc_18000658B
0x180006572  mov     rax, [rcx]
0x180006575  test    rax, rax
0x180006578  jz      short loc_18000658B
0x18000657a  mov     rax, [rax+0A0h]
0x180006581  mov     r8, rdx
0x180006584  xor     edx, edx
0x180006586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000658b  add     rsp, 28h
0x18000658f  retn
```
