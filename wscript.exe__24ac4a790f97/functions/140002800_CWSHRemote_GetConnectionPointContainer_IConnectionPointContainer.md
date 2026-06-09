# CWSHRemote::GetConnectionPointContainer(IConnectionPointContainer * *)

- ea: `0x140002800`
- end: `0x140002872`
- name: `?GetConnectionPointContainer@CWSHRemote@@UEAAJPEAPEAUIConnectionPointContainer@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, struct IConnectionPointContainer **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002800`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002825`
- `KERNEL32!GetCurrentThreadId` at `0x140002825`

## pseudocode

```c
__int64 __fastcall CWSHRemote::GetConnectionPointContainer(CWSHRemote *this, struct IConnectionPointContainer **a2)
{
  char *v5; // rdi

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)this - 24;
  if ( GetCurrentThreadId() == *((_DWORD *)this + 4) )
  {
    *a2 = (struct IConnectionPointContainer *)(((unsigned __int64)this - 8)
                                             & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64));
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  else
  {
    *a2 = 0;
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x140002800  mov     [rsp+arg_0], rbx
0x140002805  mov     [rsp+arg_8], rsi
0x14000280a  push    rdi
0x14000280b  sub     rsp, 20h
0x14000280f  mov     rbx, rdx
0x140002812  mov     rsi, rcx
0x140002815  test    rdx, rdx
0x140002818  jnz     short loc_140002821
0x14000281a  mov     eax, 80004003h
0x14000281f  jmp     short loc_140002862
0x140002821  lea     rdi, [rcx-18h]
0x140002825  call    cs:__imp_GetCurrentThreadId
0x14000282b  cmp     eax, [rdi+28h]
0x14000282e  jz      short loc_14000283E
0x140002830  mov     qword ptr [rbx], 0
0x140002837  mov     eax, 8000FFFFh
0x14000283c  jmp     short loc_140002862
0x14000283e  lea     r8, [rsi-8]
0x140002842  mov     rax, rdi
0x140002845  neg     rax
0x140002848  mov     rcx, rdi
0x14000284b  sbb     rdx, rdx
0x14000284e  and     rdx, r8
0x140002851  mov     [rbx], rdx
0x140002854  mov     rax, [rdi]
0x140002857  mov     rax, [rax+8]
0x14000285b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002860  xor     eax, eax
0x140002862  mov     rbx, [rsp+28h+arg_0]
0x140002867  mov     rsi, [rsp+28h+arg_8]
0x14000286c  add     rsp, 20h
0x140002870  pop     rdi
0x140002871  retn
```
