# CWSHRemote::CError::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x1400016f0`
- end: `0x14000173d`
- name: `?GetIDsOfNames@CError@CWSHRemote@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `77`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400016f0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001705`
- `KERNEL32!GetCurrentThreadId` at `0x140001705`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::GetIDsOfNames(
        CWSHRemote::CError *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        unsigned int a5,
        int *a6)
{
  int v6; // ebx

  v6 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() == v6 )
    return (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, _QWORD, int *))(**((_QWORD **)this + 7) + 80LL))(
             *((_QWORD *)this + 7),
             a3,
             a4,
             a6);
  else
    return 2147549183LL;
}

```

## disassembly

```asm
0x1400016f0  push    rbx
0x1400016f2  push    rbp
0x1400016f3  push    rsi
0x1400016f4  push    rdi
0x1400016f5  sub     rsp, 38h
0x1400016f9  mov     ebx, [rcx+0Ch]
0x1400016fc  mov     esi, r9d
0x1400016ff  mov     rbp, r8
0x140001702  mov     rdi, rcx
0x140001705  call    cs:__imp_GetCurrentThreadId
0x14000170b  cmp     eax, ebx
0x14000170d  jz      short loc_140001716
0x14000170f  mov     eax, 8000FFFFh
0x140001714  jmp     short loc_140001734
0x140001716  mov     rcx, [rdi+38h]
0x14000171a  mov     r8d, esi
0x14000171d  mov     r9, [rsp+58h+arg_28]
0x140001725  mov     rdx, rbp
0x140001728  mov     rax, [rcx]
0x14000172b  mov     rax, [rax+50h]
0x14000172f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001734  add     rsp, 38h
0x140001738  pop     rdi
0x140001739  pop     rsi
0x14000173a  pop     rbp
0x14000173b  pop     rbx
0x14000173c  retn
```
