# WerpCancelReport

- ea: `0x14000d1d0`
- end: `0x14000d2a2`
- name: `WerpCancelReport`
- size: `210`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000c570`
- `0x14000c6f0`

## callees

- `0x14000d1d0`
- `0x14000dfd0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000d1f8`
- `ntoskrnl!DbgPrintEx` at `0x14000d288`
- `ntoskrnl!DbgPrintEx` at `0x14000d1f8`
- `ntoskrnl!DbgPrintEx` at `0x14000d288`
- `ntoskrnl!ZwClose` at `0x14000d257`
- `ntoskrnl!ZwClose` at `0x14000d257`
- `ntoskrnl!ZwDeleteKey` at `0x14000d246`
- `ntoskrnl!ZwDeleteKey` at `0x14000d266`
- `ntoskrnl!ZwDeleteKey` at `0x14000d246`
- `ntoskrnl!ZwDeleteKey` at `0x14000d266`

## string_xrefs

- `0x14000d27b`: `WERKERNELHOST: ZwDeleteKey failed with 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpCancelReport(HANDLE KeyHandle)
{
  int v3; // ebx
  HANDLE KeyHandlea; // [rsp+40h] [rbp+8h] BYREF

  KeyHandlea = 0;
  if ( KeyHandle )
  {
    v3 = WerpCreateRegistryKey(KeyHandle, L"Busy", 0x10000u, 1, &KeyHandlea, 0);
    if ( v3 >= 0 && KeyHandlea )
    {
      ZwDeleteKey(KeyHandlea);
      ZwClose(KeyHandlea);
    }
    if ( ZwDeleteKey(KeyHandle) < 0 )
      DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwDeleteKey failed with 0x%x\n", v3);
    return (unsigned int)v3;
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Invalid handle passed to WerpCancelReport\n");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000d1d0  mov     [rsp+arg_8], rbx
0x14000d1d5  push    rdi
0x14000d1d6  sub     rsp, 30h
0x14000d1da  mov     [rsp+38h+KeyHandle], 0
0x14000d1e3  mov     rdi, rcx
0x14000d1e6  test    rcx, rcx
0x14000d1e9  jnz     short loc_14000D20E
0x14000d1eb  lea     edx, [rcx+1]; Level
0x14000d1ee  lea     ecx, [rdi+5]; ComponentId
0x14000d1f1  lea     r8, aWerkernelhostI_1; "WERKERNELHOST: Invalid handle passed to"...
0x14000d1f8  call    cs:__imp_DbgPrintEx
0x14000d1ff  nop     dword ptr [rax+rax+00h]
0x14000d204  mov     eax, 0C000000Dh
0x14000d209  jmp     loc_14000D296
0x14000d20e  lea     rax, [rsp+38h+KeyHandle]
0x14000d213  mov     [rsp+38h+var_10], 0
0x14000d21c  mov     r9b, 1
0x14000d21f  mov     [rsp+38h+var_18], rax
0x14000d224  mov     r8d, 10000h
0x14000d22a  lea     rdx, aBusy; "Busy"
0x14000d231  call    WerpCreateRegistryKey
0x14000d236  mov     ebx, eax
0x14000d238  test    eax, eax
0x14000d23a  js      short loc_14000D263
0x14000d23c  mov     rcx, [rsp+38h+KeyHandle]; KeyHandle
0x14000d241  test    rcx, rcx
0x14000d244  jz      short loc_14000D263
0x14000d246  call    cs:__imp_ZwDeleteKey
0x14000d24d  nop     dword ptr [rax+rax+00h]
0x14000d252  mov     rcx, [rsp+38h+KeyHandle]; Handle
0x14000d257  call    cs:__imp_ZwClose
0x14000d25e  nop     dword ptr [rax+rax+00h]
0x14000d263  mov     rcx, rdi; KeyHandle
0x14000d266  call    cs:__imp_ZwDeleteKey
0x14000d26d  nop     dword ptr [rax+rax+00h]
0x14000d272  test    eax, eax
0x14000d274  jns     short loc_14000D294
0x14000d276  mov     edx, 1; Level
0x14000d27b  lea     r8, aWerkernelhostZ_10; "WERKERNELHOST: ZwDeleteKey failed with "...
0x14000d282  mov     r9d, ebx
0x14000d285  lea     ecx, [rdx+4]; ComponentId
0x14000d288  call    cs:__imp_DbgPrintEx
0x14000d28f  nop     dword ptr [rax+rax+00h]
0x14000d294  mov     eax, ebx
0x14000d296  mov     rbx, [rsp+38h+arg_8]
0x14000d29b  add     rsp, 30h
0x14000d29f  pop     rdi
0x14000d2a0  retn
```
