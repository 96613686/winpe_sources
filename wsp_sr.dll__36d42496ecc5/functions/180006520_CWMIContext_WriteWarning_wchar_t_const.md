# CWMIContext::WriteWarning(wchar_t const *)

- ea: `0x180006520`
- end: `0x180006550`
- name: `?WriteWarning@CWMIContext@@UEAAXPEB_W@Z`
- size: `48`
- prototype: `void __fastcall(CWMIContext *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006520`
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
0x180006520  sub     rsp, 28h
0x180006524  test    rdx, rdx
0x180006527  jz      short loc_18000654B
0x180006529  mov     rcx, [rcx+38h]
0x18000652d  test    rcx, rcx
0x180006530  jz      short loc_18000654B
0x180006532  mov     rax, [rcx]
0x180006535  test    rax, rax
0x180006538  jz      short loc_18000654B
0x18000653a  mov     rax, [rax+0A0h]
0x180006541  mov     r8, rdx
0x180006544  xor     edx, edx
0x180006546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654b  add     rsp, 28h
0x18000654f  retn
```
