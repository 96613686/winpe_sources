# CWmpCOMBase::InternalQueryInterface(_GUID const &,void * *)

- ea: `0x180028920`
- end: `0x180028970`
- name: `?InternalQueryInterface@CWmpCOMBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWmpCOMBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028890`
- `0x180034ea0`
- `0x180038ee0`
- `0x180039170`
- `0x180039630`
- `0x18003a7f0`
- `0x18003a8c0`
- `0x18003b160`

## callees

- `0x180028920`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall CWmpCOMBase::InternalQueryInterface(CWmpCOMBase *this, const struct _GUID *a2, void **a3)
{
  __int64 result; // rax
  __int64 v4; // rax

  result = 2147942487LL;
  if ( a3 )
  {
    v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v4 )
    {
      return (*(__int64 (__fastcall **)(CWmpCOMBase *))(*(_QWORD *)this + 56LL))(this);
    }
    else
    {
      *a3 = this;
      (*(void (__fastcall **)(CWmpCOMBase *))(*(_QWORD *)this + 8LL))(this);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180028920  sub     rsp, 28h
0x180028924  mov     eax, 80070057h
0x180028929  test    r8, r8
0x18002892c  jz      short loc_18002895B
0x18002892e  mov     rax, [rdx]
0x180028931  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180028938  jnz     short loc_180028945
0x18002893a  mov     rax, [rdx+8]
0x18002893e  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180028945  test    rax, rax
0x180028948  jnz     short loc_180028960
0x18002894a  mov     [r8], rcx
0x18002894d  mov     rax, [rcx]
0x180028950  mov     rax, [rax+8]
0x180028954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028959  xor     eax, eax
0x18002895b  add     rsp, 28h
0x18002895f  retn
0x180028960  mov     rax, [rcx]
0x180028963  mov     rax, [rax+38h]
0x180028967  add     rsp, 28h
0x18002896b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
