# CWSHRemote::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1400028e0`
- end: `0x140002944`
- name: `?GetTypeInfo@CWSHRemote@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `100`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400028e0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000290a`
- `KERNEL32!GetCurrentThreadId` at `0x14000290a`

## pseudocode

```c
__int64 __fastcall CWSHRemote::GetTypeInfo(CWSHRemote *this, int a2, __int64 a3, struct ITypeInfo **a4)
{
  int v7; // ebx

  *a4 = 0;
  if ( a2 )
    return 2147614731LL;
  v7 = *((_DWORD *)this + 10);
  if ( GetCurrentThreadId() != v7 )
    return 2147549183LL;
  *a4 = (struct ITypeInfo *)*((_QWORD *)this + 9);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
  return 0;
}

```

## disassembly

```asm
0x1400028e0  mov     [rsp+arg_0], rbx
0x1400028e5  mov     [rsp+arg_8], rsi
0x1400028ea  push    rdi
0x1400028eb  sub     rsp, 20h
0x1400028ef  mov     qword ptr [r9], 0
0x1400028f6  mov     rsi, r9
0x1400028f9  mov     rdi, rcx
0x1400028fc  test    edx, edx
0x1400028fe  jz      short loc_140002907
0x140002900  mov     eax, 8002000Bh
0x140002905  jmp     short loc_140002934
0x140002907  mov     ebx, [rcx+28h]
0x14000290a  call    cs:__imp_GetCurrentThreadId
0x140002910  cmp     eax, ebx
0x140002912  jz      short loc_14000291B
0x140002914  mov     eax, 8000FFFFh
0x140002919  jmp     short loc_140002934
0x14000291b  mov     rax, [rdi+48h]
0x14000291f  mov     [rsi], rax
0x140002922  mov     rcx, [rdi+48h]
0x140002926  mov     rax, [rcx]
0x140002929  mov     rax, [rax+8]
0x14000292d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002932  xor     eax, eax
0x140002934  mov     rbx, [rsp+28h+arg_0]
0x140002939  mov     rsi, [rsp+28h+arg_8]
0x14000293e  add     rsp, 20h
0x140002942  pop     rdi
0x140002943  retn
```
