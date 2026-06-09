# CASFCompatibilityObject::Persist(CASFArchive &)

- ea: `0x18001def0`
- end: `0x18001df4c`
- name: `?Persist@CASFCompatibilityObject@@UEAAJAEAVCASFArchive@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(CASFCompatibilityObject *__hidden this, struct CASFArchive *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001def0`
- `0x18001e900`
- `0x18002658c`
- `0x18002b010`

## pseudocode

```c
int __fastcall CASFCompatibilityObject::Persist(CASFCompatibilityObject *this, struct CASFArchive *a2)
{
  int result; // eax
  CASFArchive *v5; // rcx
  int v6; // eax
  int v7; // ecx

  *((_QWORD *)this + 4) = (*(unsigned int (__fastcall **)(CASFCompatibilityObject *))(*(_QWORD *)this + 24LL))(this);
  result = CASFLonghandObject::Persist(this, a2);
  if ( result >= 0 )
  {
    result = CASFArchive::StoreBYTE(a2, *((_BYTE *)this + 56));
    if ( result >= 0 )
    {
      v6 = CASFArchive::StoreBYTE(v5, *((_BYTE *)this + 57));
      v7 = 0;
      if ( v6 < 0 )
        return v6;
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001def0  mov     [rsp+arg_0], rbx
0x18001def5  push    rdi
0x18001def6  sub     rsp, 20h
0x18001defa  mov     rax, [rcx]
0x18001defd  mov     rdi, rdx
0x18001df00  mov     rbx, rcx
0x18001df03  mov     rax, [rax+18h]
0x18001df07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df0c  mov     eax, eax
0x18001df0e  mov     rdx, rdi; struct CASFArchive *
0x18001df11  mov     rcx, rbx; this
0x18001df14  mov     [rbx+20h], rax
0x18001df18  call    ?Persist@CASFLonghandObject@@UEAAJAEAVCASFArchive@@@Z; CASFLonghandObject::Persist(CASFArchive &)
0x18001df1d  test    eax, eax
0x18001df1f  js      short loc_18001DF41
0x18001df21  mov     dl, [rbx+38h]; unsigned __int8
0x18001df24  mov     rcx, rdi; this
0x18001df27  call    ?StoreBYTE@CASFArchive@@QEAAJE@Z; CASFArchive::StoreBYTE(uchar)
0x18001df2c  test    eax, eax
0x18001df2e  js      short loc_18001DF41
0x18001df30  mov     dl, [rbx+39h]; unsigned __int8
0x18001df33  call    ?StoreBYTE@CASFArchive@@QEAAJE@Z; CASFArchive::StoreBYTE(uchar)
0x18001df38  xor     ecx, ecx
0x18001df3a  test    eax, eax
0x18001df3c  cmovs   ecx, eax
0x18001df3f  mov     eax, ecx
0x18001df41  mov     rbx, [rsp+28h+arg_0]
0x18001df46  add     rsp, 20h
0x18001df4a  pop     rdi
0x18001df4b  retn
```
