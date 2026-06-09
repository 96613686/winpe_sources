# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14003d550`
- end: `0x14003d5c3`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140011640`
- `0x140025fb4`
- `0x14003d550`
- `0x14003d5cc`

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
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[41];
  if ( v9 )
  {
    LOBYTE(a5) = a3;
    v9(a1, a2, a5);
  }
  if ( v8 == 1 )
  {
    LookUpTableFlushComplete((__int64)a7);
  }
  else if ( v8 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x14003d550  mov     [rsp+arg_0], rbx
0x14003d555  push    rdi
0x14003d556  sub     rsp, 40h
0x14003d55a  mov     rbx, [rsp+48h+arg_30]
0x14003d562  mov     r11b, r8b
0x14003d565  mov     edi, edx
0x14003d567  mov     rax, [rbx+148h]
0x14003d56e  test    rax, rax
0x14003d571  jz      short loc_14003D59B
0x14003d573  mov     r10, [rbx+150h]
0x14003d57a  mov     r8, [rsp+48h+arg_20]
0x14003d57f  mov     [rsp+48h+var_18], r10
0x14003d584  mov     r10, [rsp+48h+arg_28]
0x14003d589  mov     [rsp+48h+var_20], r10
0x14003d58e  mov     [rsp+48h+var_28], r8
0x14003d593  mov     r8b, r11b
0x14003d596  call    _guard_dispatch_icall
0x14003d59b  cmp     edi, 1
0x14003d59e  jnz     short loc_14003D5AA
0x14003d5a0  mov     rcx, rbx
0x14003d5a3  call    LookUpTableFlushComplete
0x14003d5a8  jmp     short loc_14003D5B7
0x14003d5aa  cmp     edi, 2
0x14003d5ad  jnz     short loc_14003D5B7
0x14003d5af  mov     rcx, rbx
0x14003d5b2  call    LookUpTableFlushPartial
0x14003d5b7  mov     rbx, [rsp+48h+arg_0]
0x14003d5bc  add     rsp, 40h
0x14003d5c0  pop     rdi
0x14003d5c1  retn
```
