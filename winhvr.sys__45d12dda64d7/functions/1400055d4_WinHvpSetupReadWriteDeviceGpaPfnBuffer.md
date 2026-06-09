# WinHvpSetupReadWriteDeviceGpaPfnBuffer

- ea: `0x1400055d4`
- end: `0x140005636`
- name: `WinHvpSetupReadWriteDeviceGpaPfnBuffer`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001b700`
- `0x14001b890`

## callees

- `0x1400055d4`
- `0x14000b008`

## import_xrefs

- `ntoskrnl!MmGetPhysicalAddress` at `0x140005609`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140005609`

## pseudocode

```c
void *__fastcall WinHvpSetupReadWriteDeviceGpaPfnBuffer(__int64 a1, unsigned __int64 *a2, _DWORD *a3)
{
  void *result; // rax
  void *v6; // rbx

  result = (void *)WinHvpAllocatePool(64, 4096, 1433815127);
  v6 = result;
  if ( result )
  {
    *a2 = (unsigned __int64)MmGetPhysicalAddress(result).QuadPart >> 12;
    result = v6;
    *a3 = 8;
  }
  return result;
}

```

## disassembly

```asm
0x1400055d4  mov     [rsp+arg_0], rbx
0x1400055d9  mov     [rsp+arg_8], rsi
0x1400055de  push    rdi
0x1400055df  sub     rsp, 20h
0x1400055e3  mov     rdi, r8
0x1400055e6  mov     rsi, rdx
0x1400055e9  mov     edx, 1000h
0x1400055ee  mov     r8d, 55764857h
0x1400055f4  mov     ecx, 40h ; '@'
0x1400055f9  call    WinHvpAllocatePool
0x1400055fe  mov     rbx, rax
0x140005601  test    rax, rax
0x140005604  jz      short loc_140005625
0x140005606  mov     rcx, rbx; BaseAddress
0x140005609  call    cs:__imp_MmGetPhysicalAddress
0x140005610  nop     dword ptr [rax+rax+00h]
0x140005615  shr     rax, 0Ch
0x140005619  mov     [rsi], rax
0x14000561c  mov     rax, rbx
0x14000561f  mov     dword ptr [rdi], 8
0x140005625  mov     rbx, [rsp+28h+arg_0]
0x14000562a  mov     rsi, [rsp+28h+arg_8]
0x14000562f  add     rsp, 20h
0x140005633  pop     rdi
0x140005634  retn
```
