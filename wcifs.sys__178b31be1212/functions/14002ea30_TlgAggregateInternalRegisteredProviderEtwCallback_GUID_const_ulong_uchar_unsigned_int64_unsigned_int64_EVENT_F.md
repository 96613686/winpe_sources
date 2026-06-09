# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14002ea30`
- end: `0x14002eaa5`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `117`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140007d40`
- `0x140022c84`
- `0x14002ea30`
- `0x14002eaac`

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
0x14002ea30  mov     [rsp+arg_0], rbx
0x14002ea35  push    rdi
0x14002ea36  sub     rsp, 40h
0x14002ea3a  mov     rbx, [rsp+48h+arg_30]
0x14002ea42  mov     r11b, r8b
0x14002ea45  mov     edi, edx
0x14002ea47  mov     rax, [rbx+148h]
0x14002ea4e  test    rax, rax
0x14002ea51  jnz     short loc_14002EA6C
0x14002ea53  cmp     edi, 1
0x14002ea56  jnz     short loc_14002EA96
0x14002ea58  mov     rcx, rbx
0x14002ea5b  call    LookUpTableFlushComplete
0x14002ea60  mov     rbx, [rsp+48h+arg_0]
0x14002ea65  add     rsp, 40h
0x14002ea69  pop     rdi
0x14002ea6a  retn
0x14002ea6c  mov     r10, [rbx+150h]
0x14002ea73  mov     r8, [rsp+48h+arg_20]
0x14002ea78  mov     [rsp+48h+var_18], r10
0x14002ea7d  mov     r10, [rsp+48h+arg_28]
0x14002ea82  mov     [rsp+48h+var_20], r10
0x14002ea87  mov     [rsp+48h+var_28], r8
0x14002ea8c  mov     r8b, r11b
0x14002ea8f  call    _guard_dispatch_icall
0x14002ea94  jmp     short loc_14002EA53
0x14002ea96  cmp     edi, 2
0x14002ea99  jnz     short loc_14002EA60
0x14002ea9b  mov     rcx, rbx
0x14002ea9e  call    LookUpTableFlushPartial
0x14002eaa3  jmp     short loc_14002EA60
```
