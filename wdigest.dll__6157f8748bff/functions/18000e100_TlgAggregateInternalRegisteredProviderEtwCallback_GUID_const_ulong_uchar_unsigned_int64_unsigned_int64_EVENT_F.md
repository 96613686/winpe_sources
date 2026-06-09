# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000e100`
- end: `0x18000e176`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `118`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e100`
- `0x18000e180`
- `0x180035460`
- `0x180038010`

## pseudocode

```c
void __fastcall TlgAggregateInternalRegisteredProviderEtwCallback(
        const struct _GUID *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int64 a5,
        struct _EVENT_FILTER_DESCRIPTOR *a6,
        const __m128i *a7)
{
  int v7; // edi
  void (__fastcall *v8)(const struct _GUID *, __int64, _QWORD); // rax

  v7 = a2;
  v8 = (void (__fastcall *)(const struct _GUID *, __int64, _QWORD))a7[19].m128i_i64[1];
  if ( v8 )
    v8(a1, a2, (unsigned __int8)a3);
  if ( v7 == 1 )
  {
    LookUpTableFlushComplete(a7, a2, a3, a4);
  }
  else if ( v7 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x18000e100  mov     [rsp+arg_0], rbx
0x18000e105  push    rdi
0x18000e106  sub     rsp, 40h
0x18000e10a  mov     rbx, [rsp+48h+arg_30]
0x18000e112  movzx   r11d, r8b
0x18000e116  mov     edi, edx
0x18000e118  mov     rax, [rbx+138h]
0x18000e11f  test    rax, rax
0x18000e122  jnz     short loc_18000E13C
0x18000e124  cmp     edi, 1
0x18000e127  jnz     short loc_18000E167
0x18000e129  mov     rcx, rbx
0x18000e12c  call    LookUpTableFlushComplete
0x18000e131  mov     rbx, [rsp+48h+arg_0]
0x18000e136  add     rsp, 40h
0x18000e13a  pop     rdi
0x18000e13b  retn
0x18000e13c  mov     r10, [rbx+140h]
0x18000e143  mov     r8, [rsp+48h+arg_20]
0x18000e148  mov     [rsp+48h+var_18], r10
0x18000e14d  mov     r10, [rsp+48h+arg_28]
0x18000e152  mov     [rsp+48h+var_20], r10
0x18000e157  mov     [rsp+48h+var_28], r8
0x18000e15c  movzx   r8d, r11b
0x18000e160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e165  jmp     short loc_18000E124
0x18000e167  cmp     edi, 2
0x18000e16a  jnz     short loc_18000E131
0x18000e16c  mov     rcx, rbx
0x18000e16f  call    LookUpTableFlushPartial
0x18000e174  jmp     short loc_18000E131
```
