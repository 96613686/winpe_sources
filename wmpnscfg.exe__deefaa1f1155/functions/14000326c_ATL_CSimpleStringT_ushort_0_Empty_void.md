# ATL::CSimpleStringT<ushort,0>::Empty(void)

- ea: `0x14000326c`
- end: `0x1400032ed`
- name: `?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000491c`
- `0x140006fe8`
- `0x140007766`

## callees

- `0x140003004`
- `0x14000326c`
- `0x140008010`

## pseudocode

```c
int *__fastcall ATL::CSimpleStringT<unsigned short,0>::Empty(int **a1)
{
  int *result; // rax
  volatile signed __int32 *v3; // rdx
  __int64 v4; // rdi

  result = *a1;
  v3 = *a1 - 6;
  if ( *((_DWORD *)v3 + 2) )
  {
    if ( *((int *)v3 + 4) >= 0 )
    {
      v4 = *(_QWORD *)v3;
      if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
      result = (int *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4) + 24);
      *a1 = result;
    }
    else
    {
      if ( *(result - 3) < 0 )
        ATL::AtlThrowImpl(-2147024809);
      *(result - 4) = 0;
      *(_WORD *)*a1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000326c  mov     [rsp+arg_0], rbx
0x140003271  push    rdi
0x140003272  sub     rsp, 20h
0x140003276  mov     rax, [rcx]
0x140003279  xor     r8d, r8d
0x14000327c  mov     rbx, rcx
0x14000327f  lea     rdx, [rax-18h]
0x140003283  cmp     [rdx+8], r8d
0x140003287  jz      short loc_1400032D7
0x140003289  cmp     [rdx+10h], r8d
0x14000328d  jge     short loc_1400032A2
0x14000328f  cmp     [rax-0Ch], r8d
0x140003293  jl      short loc_1400032E2
0x140003295  mov     [rax-10h], r8d
0x140003299  mov     rcx, [rcx]
0x14000329c  mov     [rcx], r8w
0x1400032a0  jmp     short loc_1400032D7
0x1400032a2  mov     rdi, [rdx]
0x1400032a5  or      eax, 0FFFFFFFFh
0x1400032a8  lock xadd [rdx+10h], eax
0x1400032ad  sub     eax, 1
0x1400032b0  jg      short loc_1400032C1
0x1400032b2  mov     rcx, [rdx]
0x1400032b5  mov     rax, [rcx]
0x1400032b8  mov     rax, [rax+8]
0x1400032bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032c1  mov     rax, [rdi]
0x1400032c4  mov     rcx, rdi
0x1400032c7  mov     rax, [rax+18h]
0x1400032cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032d0  add     rax, 18h
0x1400032d4  mov     [rbx], rax
0x1400032d7  mov     rbx, [rsp+28h+arg_0]
0x1400032dc  add     rsp, 20h
0x1400032e0  pop     rdi
0x1400032e1  retn
0x1400032e2  mov     ecx, 80070057h; int
0x1400032e7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
