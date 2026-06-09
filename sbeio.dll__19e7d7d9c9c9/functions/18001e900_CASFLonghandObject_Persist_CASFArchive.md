# CASFLonghandObject::Persist(CASFArchive &)

- ea: `0x18001e900`
- end: `0x18001e940`
- name: `?Persist@CASFLonghandObject@@UEAAJAEAVCASFArchive@@@Z`
- size: `64`
- prototype: `int(CASFLonghandObject *__hidden this, struct CASFArchive *)`
- caller_count: `31`
- callee_count: `3`
- tags: ``

## callers

- `0x18001da90`
- `0x18001dc30`
- `0x18001dce0`
- `0x18001de50`
- `0x18001def0`
- `0x18001df60`
- `0x18001e080`
- `0x18001e190`
- `0x18001e2e0`
- `0x18001e360`
- `0x18001e3d0`
- `0x18001e440`
- `0x18001e4c0`
- `0x18001e5a0`
- `0x18001e640`
- `0x18001e730`
- `0x18001e790`
- `0x18001e850`
- `0x18001e9c0`
- `0x18001ea80`
- `0x18001eb10`
- `0x18001ebb0`
- `0x18001ecf0`
- `0x18001eea0`
- `0x18001efa0`
- `0x18001f0c0`
- `0x18001f380`
- `0x18001f400`
- `0x18001f4c0`
- `0x18001f620`
- `0x180028580`

## callees

- `0x18001e900`
- `0x180026748`
- `0x1800267b0`

## pseudocode

```c
__int64 __fastcall CASFLonghandObject::Persist(CASFLonghandObject *this, struct CASFArchive *a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ecx

  result = CASFArchive::StoreGUID(a2, (const struct _GUID *)this + 1);
  if ( (int)result >= 0 )
  {
    v5 = CASFArchive::StoreQWORD(a2, *((_QWORD *)this + 4));
    v6 = 0;
    if ( v5 < 0 )
      return (unsigned int)v5;
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18001e900  mov     [rsp+arg_0], rbx
0x18001e905  push    rdi
0x18001e906  sub     rsp, 20h
0x18001e90a  mov     rbx, rdx
0x18001e90d  mov     rdi, rcx
0x18001e910  lea     rdx, [rcx+10h]; struct _GUID *
0x18001e914  mov     rcx, rbx; this
0x18001e917  call    ?StoreGUID@CASFArchive@@QEAAJAEBU_GUID@@@Z; CASFArchive::StoreGUID(_GUID const &)
0x18001e91c  test    eax, eax
0x18001e91e  js      short loc_18001E935
0x18001e920  mov     rdx, [rdi+20h]; unsigned __int64
0x18001e924  mov     rcx, rbx; this
0x18001e927  call    ?StoreQWORD@CASFArchive@@QEAAJ_K@Z; CASFArchive::StoreQWORD(unsigned __int64)
0x18001e92c  xor     ecx, ecx
0x18001e92e  test    eax, eax
0x18001e930  cmovs   ecx, eax
0x18001e933  mov     eax, ecx
0x18001e935  mov     rbx, [rsp+28h+arg_0]
0x18001e93a  add     rsp, 20h
0x18001e93e  pop     rdi
0x18001e93f  retn
```
