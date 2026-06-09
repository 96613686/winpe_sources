# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000b3d8`
- end: `0x18000b463`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `139`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008588`
- `0x18000b2b0`
- `0x18000b348`

## callees

- `0x18000b3d8`
- `0x18000be9c`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::SubscribeUnderLock(
        wil::details_abi::SubscriptionList *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  char *v4; // rbx
  __int64 v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rax
  unsigned __int64 v8; // r10
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v9; // rdx
  __int64 v10; // rax
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = (char *)this + 40;
  *a2 = 0;
  v5 = *((_QWORD *)this + 5);
  v6 = 0;
  v8 = (unsigned __int64)(*((_QWORD *)v4 + 1) - v5) >> 4;
  if ( v8 )
  {
    while ( 1 )
    {
      v9 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((char *)v6 + 1);
      v10 = 2LL * (_QWORD)v6;
      if ( !*(_QWORD *)(v5 + 8 * v10) )
        break;
      v6 = v9;
      if ( (unsigned __int64)v9 >= v8 )
        goto LABEL_4;
    }
    *(_QWORD *)(v5 + 8 * v10) = a3;
    *(_QWORD *)(v5 + 8 * v10 + 8) = a4;
    *a2 = v9;
  }
  else
  {
LABEL_4:
    v11[0] = a3;
    v11[1] = a4;
    if ( wil::details_abi::heap_buffer::push_back((void **)v4, v11, 0x10u) )
      *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
  }
}

```

## disassembly

```asm
0x18000b3d8  mov     [rsp+arg_0], rbx
0x18000b3dd  push    rdi
0x18000b3de  sub     rsp, 30h
0x18000b3e2  lea     rbx, [rcx+28h]
0x18000b3e6  mov     qword ptr [rdx], 0
0x18000b3ed  mov     rcx, [rbx]
0x18000b3f0  xor     eax, eax
0x18000b3f2  mov     r10, [rbx+8]
0x18000b3f6  mov     rdi, rdx
0x18000b3f9  sub     r10, rcx
0x18000b3fc  shr     r10, 4
0x18000b400  test    r10, r10
0x18000b403  jz      short loc_18000B41B
0x18000b405  lea     rdx, [rax+1]
0x18000b409  add     rax, rax
0x18000b40c  cmp     qword ptr [rcx+rax*8], 0
0x18000b411  jz      short loc_18000B455
0x18000b413  mov     rax, rdx
0x18000b416  cmp     rdx, r10
0x18000b419  jb      short loc_18000B405
0x18000b41b  mov     [rsp+38h+var_18], r8
0x18000b420  lea     rdx, [rsp+38h+var_18]; void *
0x18000b425  mov     r8d, 10h; unsigned __int64
0x18000b42b  mov     [rsp+38h+var_10], r9
0x18000b430  mov     rcx, rbx; this
0x18000b433  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b438  test    al, al
0x18000b43a  jz      short loc_18000B44A
0x18000b43c  mov     rax, [rbx+8]
0x18000b440  sub     rax, [rbx]
0x18000b443  shr     rax, 4
0x18000b447  mov     [rdi], rax
0x18000b44a  mov     rbx, [rsp+38h+arg_0]
0x18000b44f  add     rsp, 30h
0x18000b453  pop     rdi
0x18000b454  retn
0x18000b455  mov     [rcx+rax*8], r8
0x18000b459  mov     [rcx+rax*8+8], r9
0x18000b45e  mov     [rdi], rdx
0x18000b461  jmp     short loc_18000B44A
```
