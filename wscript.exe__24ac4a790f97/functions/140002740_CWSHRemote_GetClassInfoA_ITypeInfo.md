# CWSHRemote::GetClassInfoA(ITypeInfo * *)

- ea: `0x140002740`
- end: `0x14000279e`
- name: `?GetClassInfoA@CWSHRemote@@UEAAJPEAPEAUITypeInfo@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002740`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002758`
- `KERNEL32!GetCurrentThreadId` at `0x140002758`

## pseudocode

```c
__int64 __fastcall CWSHRemote::GetClassInfoA(CWSHRemote *this, struct ITypeInfo **a2)
{
  int v2; // ebx

  v2 = *((_DWORD *)this + 8);
  if ( GetCurrentThreadId() != v2 )
    return 2147549183LL;
  if ( !a2 )
    return 2147500035LL;
  *a2 = (struct ITypeInfo *)*((_QWORD *)this + 9);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
  return 0;
}

```

## disassembly

```asm
0x140002740  mov     [rsp+arg_0], rbx
0x140002745  mov     [rsp+arg_8], rsi
0x14000274a  push    rdi
0x14000274b  sub     rsp, 20h
0x14000274f  mov     ebx, [rcx+20h]
0x140002752  mov     rdi, rdx
0x140002755  mov     rsi, rcx
0x140002758  call    cs:__imp_GetCurrentThreadId
0x14000275e  cmp     eax, ebx
0x140002760  jz      short loc_140002769
0x140002762  mov     eax, 8000FFFFh
0x140002767  jmp     short loc_14000278E
0x140002769  test    rdi, rdi
0x14000276c  jnz     short loc_140002775
0x14000276e  mov     eax, 80004003h
0x140002773  jmp     short loc_14000278E
0x140002775  mov     rax, [rsi+48h]
0x140002779  mov     [rdi], rax
0x14000277c  mov     rcx, [rsi+48h]
0x140002780  mov     rax, [rcx]
0x140002783  mov     rax, [rax+8]
0x140002787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000278c  xor     eax, eax
0x14000278e  mov     rbx, [rsp+28h+arg_0]
0x140002793  mov     rsi, [rsp+28h+arg_8]
0x140002798  add     rsp, 20h
0x14000279c  pop     rdi
0x14000279d  retn
```
