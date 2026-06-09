# RegConfigInitialize

- ea: `0x18000ad88`
- end: `0x18000ade2`
- name: `RegConfigInitialize`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009f20`
- `0x18000abfc`

## callees

- `0x18000a714`
- `0x18000ad88`

## pseudocode

```c
__int64 __fastcall RegConfigInitialize(_DWORD *a1)
{
  __int64 result; // rax

  *a1 = 0;
  a1[7] = 1;
  a1[6] = 1;
  a1[1] = 2048;
  a1[3] = 1500;
  result = Feature_Servicing_SmartCardKspPqcSupport__private_IsEnabledDeviceUsageNoInline();
  if ( (_DWORD)result )
  {
    a1[8] = 1;
    a1[9] = 1;
  }
  a1[5] = 1;
  a1[4] = 1;
  a1[10] = 0;
  a1[2] = 0;
  return result;
}

```

## disassembly

```asm
0x18000ad88  mov     [rsp+arg_0], rbx
0x18000ad8d  push    rdi
0x18000ad8e  sub     rsp, 20h
0x18000ad92  mov     edi, 1
0x18000ad97  mov     dword ptr [rcx], 0
0x18000ad9d  mov     [rcx+1Ch], edi
0x18000ada0  mov     rbx, rcx
0x18000ada3  mov     [rcx+18h], edi
0x18000ada6  mov     dword ptr [rcx+4], 800h
0x18000adad  mov     dword ptr [rcx+0Ch], 5DCh
0x18000adb4  call    Feature_Servicing_SmartCardKspPqcSupport__private_IsEnabledDeviceUsageNoInline
0x18000adb9  test    eax, eax
0x18000adbb  jz      short loc_18000ADC3
0x18000adbd  mov     [rbx+20h], edi
0x18000adc0  mov     [rbx+24h], edi
0x18000adc3  mov     [rbx+14h], edi
0x18000adc6  mov     [rbx+10h], edi
0x18000adc9  mov     dword ptr [rbx+28h], 0
0x18000add0  mov     dword ptr [rbx+8], 0
0x18000add7  mov     rbx, [rsp+28h+arg_0]
0x18000addc  add     rsp, 20h
0x18000ade0  pop     rdi
0x18000ade1  retn
```
