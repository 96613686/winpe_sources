# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14002e9e0`
- end: `0x14002ea55`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `117`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140007d40`
- `0x140022c34`
- `0x14002e9e0`
- `0x14002ea5c`

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
0x14002e9e0  mov     [rsp+arg_0], rbx
0x14002e9e5  push    rdi
0x14002e9e6  sub     rsp, 40h
0x14002e9ea  mov     rbx, [rsp+48h+arg_30]
0x14002e9f2  mov     r11b, r8b
0x14002e9f5  mov     edi, edx
0x14002e9f7  mov     rax, [rbx+148h]
0x14002e9fe  test    rax, rax
0x14002ea01  jnz     short loc_14002EA1C
0x14002ea03  cmp     edi, 1
0x14002ea06  jnz     short loc_14002EA46
0x14002ea08  mov     rcx, rbx
0x14002ea0b  call    LookUpTableFlushComplete
0x14002ea10  mov     rbx, [rsp+48h+arg_0]
0x14002ea15  add     rsp, 40h
0x14002ea19  pop     rdi
0x14002ea1a  retn
0x14002ea1c  mov     r10, [rbx+150h]
0x14002ea23  mov     r8, [rsp+48h+arg_20]
0x14002ea28  mov     [rsp+48h+var_18], r10
0x14002ea2d  mov     r10, [rsp+48h+arg_28]
0x14002ea32  mov     [rsp+48h+var_20], r10
0x14002ea37  mov     [rsp+48h+var_28], r8
0x14002ea3c  mov     r8b, r11b
0x14002ea3f  call    _guard_dispatch_icall
0x14002ea44  jmp     short loc_14002EA03
0x14002ea46  cmp     edi, 2
0x14002ea49  jnz     short loc_14002EA10
0x14002ea4b  mov     rcx, rbx
0x14002ea4e  call    LookUpTableFlushPartial
0x14002ea53  jmp     short loc_14002EA10
```
