# CWmpCOMBase::InternalQueryInterface(_GUID const &,void * *)

- ea: `0x180028ec0`
- end: `0x180028f11`
- name: `?InternalQueryInterface@CWmpCOMBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `81`
- prototype: `__int64 __fastcall(CWmpCOMBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800296e0`
- `0x180035470`
- `0x1800395a0`
- `0x180039850`
- `0x180039d50`
- `0x18003af80`
- `0x18003b050`
- `0x18003b920`

## callees

- `0x180028ec0`
- `0x180045010`

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
0x180028ec0  sub     rsp, 28h
0x180028ec4  mov     eax, 80070057h
0x180028ec9  test    r8, r8
0x180028ecc  jz      short loc_180028EFB
0x180028ece  mov     rax, [rdx]
0x180028ed1  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180028ed8  jnz     short loc_180028EE5
0x180028eda  mov     rax, [rdx+8]
0x180028ede  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180028ee5  test    rax, rax
0x180028ee8  jnz     short loc_180028F01
0x180028eea  mov     [r8], rcx
0x180028eed  mov     rax, [rcx]
0x180028ef0  mov     rax, [rax+8]
0x180028ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ef9  xor     eax, eax
0x180028efb  add     rsp, 28h
0x180028eff  retn
0x180028f01  mov     rax, [rcx]
0x180028f04  mov     rax, [rax+38h]
0x180028f08  add     rsp, 28h
0x180028f0c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
