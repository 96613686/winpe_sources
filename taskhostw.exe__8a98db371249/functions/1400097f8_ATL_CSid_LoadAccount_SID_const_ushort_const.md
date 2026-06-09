# ATL::CSid::LoadAccount(_SID const *,ushort const *)

- ea: `0x1400097f8`
- end: `0x14000983d`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z`
- size: `69`
- prototype: `bool __fastcall(ATL::CSid *__hidden this, const struct _SID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140009430`

## callees

- `0x140006c10`
- `0x140009680`
- `0x140009724`
- `0x1400097f8`

## pseudocode

```c
bool __fastcall ATL::CSid::LoadAccount(ATL::CSid *this, struct _SID *a2, const unsigned __int16 *a3)
{
  bool result; // al

  ATL::CSid::Clear(this);
  if ( !a2 )
    return 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 112);
  try
  {
    ATL::CSid::Copy(this, a2);
    result = 1;
  }
  catch ( ... )
  {
    ATL::CSid::Clear(this);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1400097f8  mov     [rsp+arg_8], rbx
0x1400097fd  mov     [rsp+arg_0], rcx
0x140009802  push    rdi
0x140009803  sub     rsp, 20h
0x140009807  mov     rdi, rdx
0x14000980a  mov     rbx, rcx
0x14000980d  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x140009812  test    rdi, rdi
0x140009815  jz      short loc_14000982F
0x140009817  lea     rcx, [rbx+70h]
0x14000981b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140009820  mov     rdx, rdi; struct _SID *
0x140009823  mov     rcx, rbx; this
0x140009826  call    ?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z; ATL::CSid::Copy(_SID const &)
0x14000982b  mov     al, 1
0x14000982d  jmp     short loc_140009831
0x14000982f  xor     al, al
0x140009831  mov     rbx, [rsp+28h+arg_8]
0x140009836  add     rsp, 20h
0x14000983a  pop     rdi
0x14000983b  retn
```
