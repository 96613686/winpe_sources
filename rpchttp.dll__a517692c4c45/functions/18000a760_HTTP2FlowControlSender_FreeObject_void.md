# HTTP2FlowControlSender::FreeObject(void)

- ea: `0x18000a760`
- end: `0x18000a78e`
- name: `?FreeObject@HTTP2FlowControlSender@@UEAAXXZ`
- size: `46`
- prototype: `void __fastcall(HTTP2FlowControlSender *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a760`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000a787`

## pseudocode

```c
void __fastcall HTTP2FlowControlSender::FreeObject(HTTP2FlowControlSender *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x18000a760  push    rbx
0x18000a762  sub     rsp, 20h
0x18000a766  mov     rbx, rcx
0x18000a769  mov     rcx, [rcx+8]
0x18000a76d  test    rcx, rcx
0x18000a770  jz      short loc_18000A77E
0x18000a772  mov     rax, [rcx]
0x18000a775  mov     rax, [rax+38h]
0x18000a779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a77e  lea     rcx, [rbx+30h]
0x18000a782  add     rsp, 20h
0x18000a786  pop     rbx
0x18000a787  jmp     cs:__imp_RtlDeleteCriticalSection
```
