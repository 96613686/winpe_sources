# CiUpdatePolicyHistory

- ea: `0x18004b744`
- end: `0x18004b79c`
- name: `CiUpdatePolicyHistory`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180011090`
- `0x1800492f8`

## callees

- `0x18004b63c`
- `0x18004b744`
- `0x18004b7a4`

## pseudocode

```c
__int64 __fastcall CiUpdatePolicyHistory(__int64 a1, __int64 a2)
{
  int v3; // ebx
  unsigned int v5; // [rsp+40h] [rbp+18h] BYREF
  __int64 v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v5 = 0;
  v3 = CiGenerateAttestationReport(a2, &v6, &v5);
  if ( v3 >= 0 )
    CipAddAttestationReportToHistory(a1, v6, v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004b744  mov     r11, rsp
0x18004b747  mov     [r11+8], rbx
0x18004b74b  push    rdi
0x18004b74c  sub     rsp, 20h
0x18004b750  mov     rax, rdx
0x18004b753  mov     qword ptr [r11+20h], 0
0x18004b75b  mov     rdi, rcx
0x18004b75e  mov     [rsp+28h+arg_10], 0
0x18004b766  mov     rcx, rax
0x18004b769  lea     r8, [r11+18h]
0x18004b76d  lea     rdx, [r11+20h]
0x18004b771  call    CiGenerateAttestationReport
0x18004b776  mov     ebx, eax
0x18004b778  test    eax, eax
0x18004b77a  js      short loc_18004B78E
0x18004b77c  mov     r8d, [rsp+28h+arg_10]
0x18004b781  mov     rcx, rdi
0x18004b784  mov     rdx, [rsp+28h+arg_18]
0x18004b789  call    CipAddAttestationReportToHistory
0x18004b78e  mov     eax, ebx
0x18004b790  mov     rbx, [rsp+28h+arg_0]
0x18004b795  add     rsp, 20h
0x18004b799  pop     rdi
0x18004b79a  retn
```
