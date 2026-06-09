# FilterAndFire(Filter const &,IEnumEventObject *,IFiringControl *)

- ea: `0x1800063e0`
- end: `0x1800064f5`
- name: `?FilterAndFire@@YAJAEBVFilter@@PEAUIEnumEventObject@@PEAUIFiringControl@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(const struct Filter *, struct IEnumEventObject *, struct IFiringControl *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180006140`
- `0x180006220`
- `0x180006300`

## callees

- `0x1800063e0`
- `0x180008300`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall FilterAndFire(const struct Filter *a1, struct IEnumEventObject *a2, struct IFiringControl *a3)
{
  struct IEnumEventObjectVtbl *lpVtbl; // rax
  struct IEnumEventObjectVtbl *v7; // rax
  int v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  lpVtbl = a2->lpVtbl;
  v10 = 0;
  ((void (__fastcall *)(struct IEnumEventObject *))lpVtbl->Reset)(a2);
  while ( 1 )
  {
    v7 = a2->lpVtbl;
    v9 = 1;
    if ( ((unsigned int (__fastcall *)(struct IEnumEventObject *, __int64, __int64 *, int *))v7->Next)(a2, 1, &v10, &v9)
      || v9 != 1 )
    {
      break;
    }
    if ( !((__int64 (__fastcall *)(const struct Filter *, __int64))a1->lpVtbl->QueryInterface)(a1, v10) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_0817695eaa64382de581d5cafd4f276b_Traceguids,
          (unsigned int)a2);
      }
      ((void (__fastcall *)(struct IFiringControl *, __int64))a3->lpVtbl->FireSubscription)(a3, v10);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x1800063e0  mov     [rsp+arg_0], rbx
0x1800063e5  mov     [rsp+arg_10], rbp
0x1800063ea  push    rsi
0x1800063eb  push    rdi
0x1800063ec  push    r14
0x1800063ee  sub     rsp, 30h
0x1800063f2  mov     rax, [rdx]
0x1800063f5  mov     rdi, rcx
0x1800063f8  xor     ebp, ebp
0x1800063fa  mov     rcx, rdx
0x1800063fd  mov     rsi, r8
0x180006400  mov     [rsp+48h+arg_18], rbp
0x180006405  mov     rbx, rdx
0x180006408  mov     rax, [rax+28h]
0x18000640c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006411  lea     r14, WPP_GLOBAL_Control
0x180006418  mov     rax, [rbx]
0x18000641b  lea     r9, [rsp+48h+arg_8]
0x180006420  lea     r8, [rsp+48h+arg_18]
0x180006425  mov     [rsp+48h+arg_8], 1
0x18000642d  mov     edx, 1
0x180006432  mov     rcx, rbx
0x180006435  mov     rax, [rax+20h]
0x180006439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000643e  test    eax, eax
0x180006440  jz      short loc_180006465
0x180006442  mov     rcx, [rsp+48h+arg_18]
0x180006447  test    rcx, rcx
0x18000644a  jnz     loc_1800064E4
0x180006450  mov     rbx, [rsp+48h+arg_0]
0x180006455  xor     eax, eax
0x180006457  mov     rbp, [rsp+48h+arg_10]
0x18000645c  add     rsp, 30h
0x180006460  pop     r14
0x180006462  pop     rdi
0x180006463  pop     rsi
0x180006464  retn
0x180006465  cmp     [rsp+48h+arg_8], 1
0x18000646a  jnz     short loc_180006442
0x18000646c  mov     rax, [rdi]
0x18000646f  mov     rcx, rdi
0x180006472  mov     rdx, [rsp+48h+arg_18]
0x180006477  mov     rax, [rax]
0x18000647a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000647f  test    eax, eax
0x180006481  jz      short loc_18000649E
0x180006483  mov     rcx, [rsp+48h+arg_18]
0x180006488  mov     rax, [rcx]
0x18000648b  mov     rax, [rax+10h]
0x18000648f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006494  mov     [rsp+48h+arg_18], rbp
0x180006499  jmp     loc_180006418
0x18000649e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064a5  cmp     rcx, r14
0x1800064a8  jz      short loc_1800064CE
0x1800064aa  test    byte ptr [rcx+1Ch], 1
0x1800064ae  jz      short loc_1800064CE
0x1800064b0  cmp     byte ptr [rcx+19h], 5
0x1800064b4  jb      short loc_1800064CE
0x1800064b6  mov     rcx, [rcx+10h]
0x1800064ba  lea     r8, WPP_0817695eaa64382de581d5cafd4f276b_Traceguids
0x1800064c1  mov     edx, 0Fh
0x1800064c6  mov     r9d, ebx
0x1800064c9  call    WPP_SF_d
0x1800064ce  mov     rax, [rsi]
0x1800064d1  mov     rcx, rsi
0x1800064d4  mov     rdx, [rsp+48h+arg_18]
0x1800064d9  mov     rax, [rax+38h]
0x1800064dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e2  jmp     short loc_180006483
0x1800064e4  mov     rax, [rcx]
0x1800064e7  mov     rax, [rax+10h]
0x1800064eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064f0  jmp     loc_180006450
```
