# UmpoRundownOverrideConfiguration

- ea: `0x180008be0`
- end: `0x180008c6d`
- name: `UmpoRundownOverrideConfiguration`
- size: `141`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180008c80`

## callees

- `0x1800088b0`
- `0x180008be0`
- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180008c65`
- `ntdll!EtwEventWrite` at `0x180008c65`

## pseudocode

```c
__int64 UmpoRundownOverrideConfiguration()
{
  __int64 result; // rax
  __int128 v1; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v2[6]; // [rsp+30h] [rbp-40h] BYREF

  v1 = 0;
  result = UmpoGetSystemConfiguration((int *)&v1);
  if ( !(_DWORD)result )
  {
    v2[0] = &v1;
    v2[1] = 4;
    v2[2] = (char *)&v1 + 12;
    v2[3] = 4;
    v2[4] = (char *)&v1 + 8;
    v2[5] = 4;
    return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_RUNDOWN_OVERRIDE_CONFIGURATION, 3, v2);
  }
  return result;
}

```

## disassembly

```asm
0x180008be0  push    rbp
0x180008be2  mov     rbp, rsp
0x180008be5  sub     rsp, 70h
0x180008be9  mov     rax, cs:__security_cookie
0x180008bf0  xor     rax, rsp
0x180008bf3  mov     [rbp+var_10], rax
0x180008bf7  xorps   xmm0, xmm0
0x180008bfa  lea     rcx, [rbp+var_50]
0x180008bfe  movups  [rbp+var_50], xmm0
0x180008c02  call    UmpoGetSystemConfiguration
0x180008c07  test    eax, eax
0x180008c09  jz      short loc_180008C1D
0x180008c0b  mov     rcx, [rbp+var_10]
0x180008c0f  xor     rcx, rsp; StackCookie
0x180008c12  call    __security_check_cookie
0x180008c17  add     rsp, 70h
0x180008c1b  pop     rbp
0x180008c1c  retn
0x180008c1d  mov     rcx, cs:UmpoProviderHandle
0x180008c24  lea     rax, [rbp+var_50]
0x180008c28  mov     [rbp+var_40], rax
0x180008c2c  lea     r9, [rbp+var_40]
0x180008c30  lea     rax, [rbp+var_50+0Ch]
0x180008c34  mov     [rbp+var_38], 4
0x180008c3c  mov     [rbp+var_30], rax
0x180008c40  lea     rdx, UMPO_EVT_RUNDOWN_OVERRIDE_CONFIGURATION
0x180008c47  lea     rax, [rbp+var_50+8]
0x180008c4b  mov     [rbp+var_28], 4
0x180008c53  mov     r8d, 3
0x180008c59  mov     [rbp+var_20], rax
0x180008c5d  mov     [rbp+var_18], 4
0x180008c65  call    cs:__imp_EtwEventWrite
0x180008c6b  jmp     short loc_180008C0B
```
