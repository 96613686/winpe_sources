# WinHvLogHypervisorSystemConfig

- ea: `0x1400080c0`
- end: `0x14000810d`
- name: `WinHvLogHypervisorSystemConfig`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## pseudocode

```c
__int64 WinHvLogHypervisorSystemConfig()
{
  unsigned int v0; // ebx
  _QWORD v2[9]; // [rsp+20h] [rbp-48h] BYREF

  memset(v2, 0, 0x40u);
  WinHvpSetupHypercall(0, 0, (__int64)v2);
  v0 = WinHvpSimplePoolHypercall_CallViaMacro(v2[0], 248);
  ((void (__fastcall *)(_QWORD))v2[7])(v2[0]);
  return v0;
}

```

## disassembly

```asm
0x1400080c0  push    rbx
0x1400080c2  sub     rsp, 60h
0x1400080c6  xor     edx, edx; Val
0x1400080c8  lea     rcx, [rsp+68h+var_48]; void *
0x1400080cd  lea     r8d, [rdx+40h]; Size
0x1400080d1  call    memset
0x1400080d6  lea     r8, [rsp+68h+var_48]
0x1400080db  xor     edx, edx
0x1400080dd  xor     ecx, ecx
0x1400080df  call    WinHvpSetupHypercall
0x1400080e4  mov     rcx, [rsp+68h+var_48]
0x1400080e9  mov     edx, 0F8h
0x1400080ee  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400080f3  mov     rcx, [rsp+68h+var_48]
0x1400080f8  mov     ebx, eax
0x1400080fa  mov     rax, [rsp+68h+var_10]
0x1400080ff  call    _guard_dispatch_icall
0x140008104  mov     eax, ebx
0x140008106  add     rsp, 60h
0x14000810a  pop     rbx
0x14000810b  retn
```
