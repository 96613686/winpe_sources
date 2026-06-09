# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000b710`
- end: `0x18000b782`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000b280`
- `0x18000b608`
- `0x18000b710`
- `0x18000d010`

## pseudocode

```c
void __fastcall TlgAggregateInternalRegisteredProviderEtwCallback(
        const struct _GUID *a1,
        __int64 a2,
        char a3,
        __int64 a4,
        unsigned __int64 a5,
        struct _EVENT_FILTER_DESCRIPTOR *a6,
        _QWORD *a7)
{
  int v8; // edi
  void (__fastcall *v9)(const struct _GUID *, __int64, unsigned __int64); // rax

  v8 = a2;
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[39];
  if ( v9 )
  {
    LOBYTE(a5) = a3;
    v9(a1, a2, a5);
  }
  if ( v8 == 1 )
  {
    LookUpTableFlushComplete(a7);
  }
  else if ( v8 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x18000b710  mov     [rsp+arg_0], rbx
0x18000b715  push    rdi
0x18000b716  sub     rsp, 40h
0x18000b71a  mov     rbx, [rsp+48h+arg_30]
0x18000b722  mov     r11b, r8b
0x18000b725  mov     edi, edx
0x18000b727  mov     rax, [rbx+138h]
0x18000b72e  test    rax, rax
0x18000b731  jz      short loc_18000B75B
0x18000b733  mov     r10, [rbx+140h]
0x18000b73a  mov     r8, [rsp+48h+arg_20]
0x18000b73f  mov     [rsp+48h+var_18], r10
0x18000b744  mov     r10, [rsp+48h+arg_28]
0x18000b749  mov     [rsp+48h+var_20], r10
0x18000b74e  mov     [rsp+48h+var_28], r8
0x18000b753  mov     r8b, r11b
0x18000b756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75b  cmp     edi, 1
0x18000b75e  jnz     short loc_18000B76A
0x18000b760  mov     rcx, rbx
0x18000b763  call    LookUpTableFlushComplete
0x18000b768  jmp     short loc_18000B777
0x18000b76a  cmp     edi, 2
0x18000b76d  jnz     short loc_18000B777
0x18000b76f  mov     rcx, rbx
0x18000b772  call    LookUpTableFlushPartial
0x18000b777  mov     rbx, [rsp+48h+arg_0]
0x18000b77c  add     rsp, 40h
0x18000b780  pop     rdi
0x18000b781  retn
```
