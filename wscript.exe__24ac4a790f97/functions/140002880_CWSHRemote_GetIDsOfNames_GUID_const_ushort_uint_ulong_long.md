# CWSHRemote::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x140002880`
- end: `0x1400028cd`
- name: `?GetIDsOfNames@CWSHRemote@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `77`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002880`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002895`
- `KERNEL32!GetCurrentThreadId` at `0x140002895`

## pseudocode

```c
__int64 __fastcall CWSHRemote::GetIDsOfNames(
        CWSHRemote *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        unsigned int a5,
        int *a6)
{
  int v6; // ebx

  v6 = *((_DWORD *)this + 10);
  if ( GetCurrentThreadId() == v6 )
    return (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, _QWORD, int *))(**((_QWORD **)this + 9) + 80LL))(
             *((_QWORD *)this + 9),
             a3,
             a4,
             a6);
  else
    return 2147549183LL;
}

```

## disassembly

```asm
0x140002880  push    rbx
0x140002882  push    rbp
0x140002883  push    rsi
0x140002884  push    rdi
0x140002885  sub     rsp, 38h
0x140002889  mov     ebx, [rcx+28h]
0x14000288c  mov     esi, r9d
0x14000288f  mov     rbp, r8
0x140002892  mov     rdi, rcx
0x140002895  call    cs:__imp_GetCurrentThreadId
0x14000289b  cmp     eax, ebx
0x14000289d  jz      short loc_1400028A6
0x14000289f  mov     eax, 8000FFFFh
0x1400028a4  jmp     short loc_1400028C4
0x1400028a6  mov     rcx, [rdi+48h]
0x1400028aa  mov     r8d, esi
0x1400028ad  mov     r9, [rsp+58h+arg_28]
0x1400028b5  mov     rdx, rbp
0x1400028b8  mov     rax, [rcx]
0x1400028bb  mov     rax, [rax+50h]
0x1400028bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028c4  add     rsp, 38h
0x1400028c8  pop     rdi
0x1400028c9  pop     rsi
0x1400028ca  pop     rbp
0x1400028cb  pop     rbx
0x1400028cc  retn
```
