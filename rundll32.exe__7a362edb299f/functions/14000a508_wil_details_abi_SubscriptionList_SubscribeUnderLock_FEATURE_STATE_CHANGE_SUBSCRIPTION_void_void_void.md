# wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000a508`
- end: `0x14000a5b7`
- name: `?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `175`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a40c`
- `0x14000a850`

## callees

- `0x14000220c`
- `0x14000a508`
- `0x14000ab0c`

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
  _QWORD Source[3]; // [rsp+20h] [rbp-18h] BYREF

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
    Source[0] = a3;
    Source[1] = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v4, 0x10u) )
    {
      memcpy_s(
        *((void *const *)v4 + 1),
        (*((_QWORD *)v4 + 2) - *((_QWORD *)v4 + 1)) & -(__int64)(*((_QWORD *)v4 + 1) < *((_QWORD *)v4 + 2)),
        Source,
        0x10u);
      *((_QWORD *)v4 + 1) += 16LL;
      *a2 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((*((_QWORD *)v4 + 1) - *(_QWORD *)v4) >> 4);
    }
  }
}

```

## disassembly

```asm
0x14000a508  mov     [rsp+arg_0], rbx
0x14000a50d  push    rdi
0x14000a50e  sub     rsp, 30h
0x14000a512  lea     rbx, [rcx+28h]
0x14000a516  mov     qword ptr [rdx], 0
0x14000a51d  mov     rcx, [rbx]
0x14000a520  xor     eax, eax
0x14000a522  mov     r10, [rbx+8]
0x14000a526  mov     rdi, rdx
0x14000a529  sub     r10, rcx
0x14000a52c  shr     r10, 4
0x14000a530  test    r10, r10
0x14000a533  jz      short loc_14000A54B
0x14000a535  lea     rdx, [rax+1]
0x14000a539  add     rax, rax
0x14000a53c  cmp     qword ptr [rcx+rax*8], 0
0x14000a541  jz      short loc_14000A5A9
0x14000a543  mov     rax, rdx
0x14000a546  cmp     rdx, r10
0x14000a549  jb      short loc_14000A535
0x14000a54b  mov     edx, 10h; unsigned __int64
0x14000a550  mov     [rsp+38h+Source], r8
0x14000a555  mov     rcx, rbx; this
0x14000a558  mov     [rsp+38h+var_10], r9
0x14000a55d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000a562  test    al, al
0x14000a564  jz      short loc_14000A59E
0x14000a566  mov     rcx, [rbx+8]; Destination
0x14000a56a  lea     r8, [rsp+38h+Source]; Source
0x14000a56f  mov     rax, [rbx+10h]
0x14000a573  mov     r9d, 10h; SourceSize
0x14000a579  sub     rax, rcx
0x14000a57c  cmp     rcx, [rbx+10h]
0x14000a580  sbb     rdx, rdx
0x14000a583  and     rdx, rax; DestinationSize
0x14000a586  call    memcpy_s
0x14000a58b  add     qword ptr [rbx+8], 10h
0x14000a590  mov     rax, [rbx+8]
0x14000a594  sub     rax, [rbx]
0x14000a597  shr     rax, 4
0x14000a59b  mov     [rdi], rax
0x14000a59e  mov     rbx, [rsp+38h+arg_0]
0x14000a5a3  add     rsp, 30h
0x14000a5a7  pop     rdi
0x14000a5a8  retn
0x14000a5a9  mov     [rcx+rax*8], r8
0x14000a5ad  mov     [rcx+rax*8+8], r9
0x14000a5b2  mov     [rdi], rdx
0x14000a5b5  jmp     short loc_14000A59E
```
