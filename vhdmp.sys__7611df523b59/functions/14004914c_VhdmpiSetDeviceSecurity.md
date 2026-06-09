# VhdmpiSetDeviceSecurity

- ea: `0x14004914c`
- end: `0x1400491d7`
- name: `VhdmpiSetDeviceSecurity`
- size: `139`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400b71a0`

## callees

- `0x14004914c`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140049186`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140049186`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400491a5`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400491a5`
- `ntoskrnl!ZwClose` at `0x1400491bd`
- `ntoskrnl!ZwClose` at `0x1400491bd`

## pseudocode

```c
__int64 __fastcall VhdmpiSetDeviceSecurity(void *a1, void *a2)
{
  NTSTATUS v3; // ebx
  HANDLE Handle; // [rsp+60h] [rbp+18h] BYREF

  Handle = 0;
  v3 = ObOpenObjectByPointer(a1, 0x200u, 0, 0x40000u, 0, 0, &Handle);
  if ( v3 >= 0 )
    v3 = ZwSetSecurityObject(Handle, 4u, a2);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14004914c  mov     r11, rsp
0x14004914f  mov     [r11+8], rbx
0x140049153  push    rdi
0x140049154  sub     rsp, 40h
0x140049158  lea     rax, [r11+18h]
0x14004915c  mov     qword ptr [r11+18h], 0
0x140049164  mov     [r11-18h], rax
0x140049168  mov     rdi, rdx
0x14004916b  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140049170  mov     r9d, 40000h; DesiredAccess
0x140049176  xor     r8d, r8d; PassedAccessState
0x140049179  mov     qword ptr [r11-28h], 0
0x140049181  mov     edx, 200h; HandleAttributes
0x140049186  call    cs:__imp_ObOpenObjectByPointer
0x14004918d  nop     dword ptr [rax+rax+00h]
0x140049192  mov     ebx, eax
0x140049194  test    eax, eax
0x140049196  js      short loc_1400491B3
0x140049198  mov     rcx, [rsp+48h+Handle]; Handle
0x14004919d  mov     r8, rdi; SecurityDescriptor
0x1400491a0  mov     edx, 4; SecurityInformation
0x1400491a5  call    cs:__imp_ZwSetSecurityObject
0x1400491ac  nop     dword ptr [rax+rax+00h]
0x1400491b1  mov     ebx, eax
0x1400491b3  mov     rcx, [rsp+48h+Handle]; Handle
0x1400491b8  test    rcx, rcx
0x1400491bb  jz      short loc_1400491C9
0x1400491bd  call    cs:__imp_ZwClose
0x1400491c4  nop     dword ptr [rax+rax+00h]
0x1400491c9  mov     eax, ebx
0x1400491cb  mov     rbx, [rsp+48h+arg_0]
0x1400491d0  add     rsp, 40h
0x1400491d4  pop     rdi
0x1400491d5  retn
```
