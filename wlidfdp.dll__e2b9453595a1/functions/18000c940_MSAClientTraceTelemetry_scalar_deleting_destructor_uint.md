# MSAClientTraceTelemetry::`scalar deleting destructor'(uint)

- ea: `0x18000c940`
- end: `0x18000c96f`
- name: `??_GMSAClientTraceTelemetry@@UEAAPEAXI@Z`
- size: `47`
- prototype: `MSAClientTraceTelemetry *__fastcall(MSAClientTraceTelemetry *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800027d4`
- `0x18000c910`
- `0x18000c940`

## pseudocode

```c
MSAClientTraceTelemetry *__fastcall MSAClientTraceTelemetry::`scalar deleting destructor'(
        MSAClientTraceTelemetry *this,
        char a2)
{
  wil::TraceLoggingProvider::~TraceLoggingProvider(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c940  mov     [rsp+arg_0], rbx
0x18000c945  push    rdi
0x18000c946  sub     rsp, 20h
0x18000c94a  mov     ebx, edx
0x18000c94c  mov     rdi, rcx
0x18000c94f  call    ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
0x18000c954  test    bl, 1
0x18000c957  jz      short loc_18000C961
0x18000c959  mov     rcx, rdi; Block
0x18000c95c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c961  mov     rbx, [rsp+28h+arg_0]
0x18000c966  mov     rax, rdi
0x18000c969  add     rsp, 20h
0x18000c96d  pop     rdi
0x18000c96e  retn
```
