# CASFCompatibilityObject::Restore(CASFArchive &)

- ea: `0x1800212d0`
- end: `0x180021347`
- name: `?Restore@CASFCompatibilityObject@@UEAAJAEAVCASFArchive@@@Z`
- size: `119`
- prototype: `int(CASFCompatibilityObject *__hidden this, struct CASFArchive *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001d100`
- `0x1800212d0`
- `0x180022980`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CASFCompatibilityObject::Restore(CASFCompatibilityObject *this, struct CASFArchive *a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  result = CASFLonghandObject::Restore(this, a2);
  if ( (int)result >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(CASFCompatibilityObject *))(*(_QWORD *)this + 32LL))(this) - 24;
    result = CASFArchive::LoadBYTE(a2, (unsigned __int8 *)this + 56, &v5);
    if ( (int)result >= 0 )
    {
      result = CASFArchive::LoadBYTE(a2, (unsigned __int8 *)this + 57, &v5);
      if ( (int)result >= 0 )
        return v5 != 0 ? 0xC00D07E2 : 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800212d0  mov     [rsp+arg_0], rbx
0x1800212d5  push    rdi
0x1800212d6  sub     rsp, 20h
0x1800212da  mov     rdi, rdx
0x1800212dd  mov     rbx, rcx
0x1800212e0  call    ?Restore@CASFLonghandObject@@UEAAJAEAVCASFArchive@@@Z; CASFLonghandObject::Restore(CASFArchive &)
0x1800212e5  test    eax, eax
0x1800212e7  js      short loc_18002133C
0x1800212e9  mov     rax, [rbx]
0x1800212ec  mov     rcx, rbx
0x1800212ef  mov     rax, [rax+20h]
0x1800212f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212f8  sub     rax, 18h
0x1800212fc  lea     rdx, [rbx+38h]; unsigned __int8 *
0x180021300  lea     r8, [rsp+28h+arg_10]; unsigned __int64 *
0x180021305  mov     [rsp+28h+arg_10], rax
0x18002130a  mov     rcx, rdi; this
0x18002130d  call    ?LoadBYTE@CASFArchive@@QEAAJAEAEPEA_K@Z; CASFArchive::LoadBYTE(uchar &,unsigned __int64 *)
0x180021312  test    eax, eax
0x180021314  js      short loc_18002133C
0x180021316  lea     rdx, [rbx+39h]; unsigned __int8 *
0x18002131a  mov     rcx, rdi; this
0x18002131d  lea     r8, [rsp+28h+arg_10]; unsigned __int64 *
0x180021322  call    ?LoadBYTE@CASFArchive@@QEAAJAEAEPEA_K@Z; CASFArchive::LoadBYTE(uchar &,unsigned __int64 *)
0x180021327  test    eax, eax
0x180021329  js      short loc_18002133C
0x18002132b  xor     eax, eax
0x18002132d  sub     rax, [rsp+28h+arg_10]
0x180021332  neg     rax
0x180021335  sbb     eax, eax
0x180021337  and     eax, 0C00D07E2h
0x18002133c  mov     rbx, [rsp+28h+arg_0]
0x180021341  add     rsp, 20h
0x180021345  pop     rdi
0x180021346  retn
```
