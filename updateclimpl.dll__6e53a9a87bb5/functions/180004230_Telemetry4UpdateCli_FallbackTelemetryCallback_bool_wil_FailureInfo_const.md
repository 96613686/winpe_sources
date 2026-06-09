# Telemetry4UpdateCli::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180004230`
- end: `0x180004264`
- name: `?FallbackTelemetryCallback@Telemetry4UpdateCli@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `52`
- prototype: `void __fastcall(char, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180004158`
- `0x1800148e0`

## pseudocode

```c
void __fastcall Telemetry4UpdateCli::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  struct Telemetry4UpdateCli *v4; // rax
  __int64 v5; // rdx

  v4 = Telemetry4UpdateCli::Instance();
  LOBYTE(v5) = a1;
  (*(void (__fastcall **)(struct Telemetry4UpdateCli *, __int64, const struct wil::FailureInfo *))(*(_QWORD *)v4 + 16LL))(
    v4,
    v5,
    a2);
}

```

## disassembly

```asm
0x180004230  mov     [rsp+arg_0], rbx
0x180004235  push    rdi
0x180004236  sub     rsp, 20h
0x18000423a  mov     rbx, rdx
0x18000423d  mov     dil, cl
0x180004240  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x180004245  mov     rcx, rax
0x180004248  mov     dl, dil
0x18000424b  mov     r8, [rax]
0x18000424e  mov     rax, [r8+10h]
0x180004252  mov     r8, rbx
0x180004255  mov     rbx, [rsp+28h+arg_0]
0x18000425a  add     rsp, 20h
0x18000425e  pop     rdi
0x18000425f  jmp     _guard_dispatch_icall
```
