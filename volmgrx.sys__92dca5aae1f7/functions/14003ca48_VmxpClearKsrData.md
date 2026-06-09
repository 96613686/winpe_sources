# VmxpClearKsrData

- ea: `0x14003ca48`
- end: `0x14003cb12`
- name: `VmxpClearKsrData`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003cb18`

## callees

- `0x14001b9a0`
- `0x140033ce0`
- `0x140039a98`
- `0x14003ca48`

## import_xrefs

- `ntoskrnl!ZwDeleteKey` at `0x14003ca97`
- `ntoskrnl!ZwDeleteKey` at `0x14003cadc`
- `ntoskrnl!ZwDeleteKey` at `0x14003ca97`
- `ntoskrnl!ZwDeleteKey` at `0x14003cadc`
- `ntoskrnl!ZwClose` at `0x14003caa8`
- `ntoskrnl!ZwClose` at `0x14003caed`
- `ntoskrnl!ZwClose` at `0x14003caa8`
- `ntoskrnl!ZwClose` at `0x14003caed`

## pseudocode

```c
__int64 VmxpClearKsrData()
{
  VMX_GLOBAL_DATA *v0; // rdi
  __int64 v1; // rdx
  unsigned __int8 v2; // cl
  VMX_DISK_DEVICE *v3; // rax
  VMX_DISK_DEVICE *v4; // rbx
  HANDLE KeyHandle; // [rsp+30h] [rbp+8h] BYREF

  v0 = Global;
  KeyHandle = 0;
  (*((void (__fastcall **)(_QWORD))Global + 5))(*((_QWORD *)Global + 1));
  v3 = (VMX_GLOBAL_DATA *)((char *)Global + 168);
  v4 = (VMX_DISK_DEVICE *)*((_QWORD *)Global + 21);
  while ( v4 != v3 )
  {
    if ( (int)VMX_DISK_DEVICE::OpenDeviceParameterKey(v4, v1, &KeyHandle) >= 0 )
    {
      ZwDeleteKey(KeyHandle);
      ZwClose(KeyHandle);
    }
    v4 = *(VMX_DISK_DEVICE **)v4;
    v3 = (VMX_GLOBAL_DATA *)((char *)Global + 168);
  }
  if ( VmxpOpenKsrKey(v2, &KeyHandle) >= 0 )
  {
    ZwDeleteKey(KeyHandle);
    ZwClose(KeyHandle);
  }
  return (*((__int64 (__fastcall **)(_QWORD))v0 + 6))(*((_QWORD *)v0 + 1));
}

```

## disassembly

```asm
0x14003ca48  mov     [rsp+arg_8], rbx
0x14003ca4d  push    rdi
0x14003ca4e  sub     rsp, 20h
0x14003ca52  mov     rdi, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003ca59  mov     [rsp+28h+KeyHandle], 0
0x14003ca62  mov     rax, [rdi+28h]
0x14003ca66  mov     rcx, [rdi+8]
0x14003ca6a  call    _guard_dispatch_icall
0x14003ca6f  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003ca76  add     rax, 0A8h
0x14003ca7c  mov     rbx, [rax]
0x14003ca7f  jmp     short loc_14003CAC4
0x14003ca81  lea     r8, [rsp+28h+KeyHandle]; void **
0x14003ca86  mov     rcx, rbx; this
0x14003ca89  call    ?OpenDeviceParameterKey@VMX_DISK_DEVICE@@QEAAJEPEAPEAX@Z; VMX_DISK_DEVICE::OpenDeviceParameterKey(uchar,void * *)
0x14003ca8e  test    eax, eax
0x14003ca90  js      short loc_14003CAB4
0x14003ca92  mov     rcx, [rsp+28h+KeyHandle]; KeyHandle
0x14003ca97  call    cs:__imp_ZwDeleteKey
0x14003ca9e  nop     dword ptr [rax+rax+00h]
0x14003caa3  mov     rcx, [rsp+28h+KeyHandle]; Handle
0x14003caa8  call    cs:__imp_ZwClose
0x14003caaf  nop     dword ptr [rax+rax+00h]
0x14003cab4  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003cabb  mov     rbx, [rbx]
0x14003cabe  add     rax, 0A8h
0x14003cac4  cmp     rbx, rax
0x14003cac7  jnz     short loc_14003CA81
0x14003cac9  lea     rdx, [rsp+28h+KeyHandle]; void **
0x14003cace  call    ?VmxpOpenKsrKey@@YAJEPEAPEAX@Z; VmxpOpenKsrKey(uchar,void * *)
0x14003cad3  test    eax, eax
0x14003cad5  js      short loc_14003CAF9
0x14003cad7  mov     rcx, [rsp+28h+KeyHandle]; KeyHandle
0x14003cadc  call    cs:__imp_ZwDeleteKey
0x14003cae3  nop     dword ptr [rax+rax+00h]
0x14003cae8  mov     rcx, [rsp+28h+KeyHandle]; Handle
0x14003caed  call    cs:__imp_ZwClose
0x14003caf4  nop     dword ptr [rax+rax+00h]
0x14003caf9  mov     rax, [rdi+30h]
0x14003cafd  mov     rcx, [rdi+8]
0x14003cb01  call    _guard_dispatch_icall
0x14003cb06  mov     rbx, [rsp+28h+arg_8]
0x14003cb0b  add     rsp, 20h
0x14003cb0f  pop     rdi
0x14003cb10  retn
```
