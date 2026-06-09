# GetStringFromDevInterfaceProperty(void *,_SP_DEVICE_INTERFACE_DATA *,_DEVPROPKEY const *)

- ea: `0x18002fedc`
- end: `0x18002ffdc`
- name: `?GetStringFromDevInterfaceProperty@@YA?AV?$CSimpleStringBase@G@@PEAXPEAU_SP_DEVICE_INTERFACE_DATA@@PEBU_DEVPROPKEY@@@Z`
- size: `256`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000813c`
- `0x1800129fc`
- `0x18002fc10`
- `0x180046838`

## callees

- `0x18000f4fc`
- `0x18002fedc`
- `0x180034658`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002ff34`
- `KERNEL32!GetLastError` at `0x18002ffa5`
- `KERNEL32!GetLastError` at `0x18002ff34`
- `KERNEL32!GetLastError` at `0x18002ffa5`
- `ole32!CoTaskMemFree` at `0x18002ffbe`
- `ole32!CoTaskMemFree` at `0x18002ffbe`
- `ole32!CoTaskMemAlloc` at `0x18002ff51`
- `ole32!CoTaskMemAlloc` at `0x18002ff51`
- `SETUPAPI!SetupDiGetDeviceInterfacePropertyW` at `0x18002ff2a`
- `SETUPAPI!SetupDiGetDeviceInterfacePropertyW` at `0x18002ff9b`
- `SETUPAPI!SetupDiGetDeviceInterfacePropertyW` at `0x18002ff2a`
- `SETUPAPI!SetupDiGetDeviceInterfacePropertyW` at `0x18002ff9b`

## pseudocode

```c
__int64 __fastcall GetStringFromDevInterfaceProperty(
        __int64 a1,
        void *a2,
        struct _SP_DEVICE_INTERFACE_DATA *a3,
        const DEVPROPKEY *a4)
{
  BYTE *PropertyBuffer; // rbx
  signed int LastError; // eax
  BYTE *v10; // rax
  DEVPROPTYPE PropertyType[4]; // [rsp+40h] [rbp-28h] BYREF
  SIZE_T cb; // [rsp+70h] [rbp+8h] BYREF

  PropertyBuffer = 0;
  LODWORD(cb) = 0;
  PropertyType[0] = 0;
  if ( !SetupDiGetDeviceInterfacePropertyW(a2, a3, a4, PropertyType, 0, 0, (PDWORD)&cb, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError == -2147024774 )
    {
      v10 = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
      PropertyBuffer = v10;
      if ( v10 )
      {
        memset_0(v10, 0, (unsigned int)cb);
        if ( !SetupDiGetDeviceInterfacePropertyW(a2, a3, a4, PropertyType, PropertyBuffer, cb, (PDWORD)&cb, 0) )
          GetLastError();
      }
    }
  }
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(a1, PropertyBuffer);
  if ( PropertyBuffer )
    CoTaskMemFree(PropertyBuffer);
  return a1;
}

```

## disassembly

```asm
0x18002fedc  mov     rax, rsp
0x18002fedf  mov     [rax+10h], rbx
0x18002fee3  mov     [rax+18h], rbp
0x18002fee7  push    rsi
0x18002fee8  push    rdi
0x18002fee9  push    r14
0x18002feeb  sub     rsp, 50h
0x18002feef  xor     ebx, ebx
0x18002fef1  mov     dword ptr [rax+8], 0
0x18002fef8  mov     [rax-30h], ebx
0x18002fefb  mov     rsi, r9
0x18002fefe  mov     [rax-28h], ebx
0x18002ff01  lea     rax, [rax+8]
0x18002ff05  mov     rbp, r8
0x18002ff08  mov     [rsp+68h+RequiredSize], rax; RequiredSize
0x18002ff0d  mov     r14, rdx
0x18002ff10  mov     [rsp+68h+PropertyBufferSize], ebx; PropertyBufferSize
0x18002ff14  mov     rdi, rcx
0x18002ff17  mov     [rsp+68h+PropertyBuffer], rbx; PropertyBuffer
0x18002ff1c  lea     r9, [rsp+68h+PropertyType]; PropertyType
0x18002ff21  mov     r8, rsi; PropertyKey
0x18002ff24  mov     rdx, rbp; DeviceInterfaceData
0x18002ff27  mov     rcx, r14; DeviceInfoSet
0x18002ff2a  call    cs:__imp_SetupDiGetDeviceInterfacePropertyW
0x18002ff30  test    eax, eax
0x18002ff32  jnz     short loc_18002FFAB
0x18002ff34  call    cs:__imp_GetLastError
0x18002ff3a  test    eax, eax
0x18002ff3c  jle     short loc_18002FF46
0x18002ff3e  movzx   eax, ax
0x18002ff41  or      eax, 80070000h
0x18002ff46  cmp     eax, 8007007Ah
0x18002ff4b  jnz     short loc_18002FFAB
0x18002ff4d  mov     ecx, dword ptr [rsp+68h+cb]; cb
0x18002ff51  call    cs:__imp_CoTaskMemAlloc
0x18002ff57  mov     rbx, rax
0x18002ff5a  test    rax, rax
0x18002ff5d  jz      short loc_18002FFAB
0x18002ff5f  mov     r8d, dword ptr [rsp+68h+cb]; Size
0x18002ff64  xor     edx, edx; Val
0x18002ff66  mov     rcx, rax; void *
0x18002ff69  call    memset_0
0x18002ff6e  mov     ecx, dword ptr [rsp+68h+cb]
0x18002ff72  lea     rax, [rsp+68h+cb]
0x18002ff77  mov     [rsp+68h+Flags], 0; Flags
0x18002ff7f  lea     r9, [rsp+68h+PropertyType]; PropertyType
0x18002ff84  mov     [rsp+68h+RequiredSize], rax; RequiredSize
0x18002ff89  mov     r8, rsi; PropertyKey
0x18002ff8c  mov     [rsp+68h+PropertyBufferSize], ecx; PropertyBufferSize
0x18002ff90  mov     rdx, rbp; DeviceInterfaceData
0x18002ff93  mov     rcx, r14; DeviceInfoSet
0x18002ff96  mov     [rsp+68h+PropertyBuffer], rbx; PropertyBuffer
0x18002ff9b  call    cs:__imp_SetupDiGetDeviceInterfacePropertyW
0x18002ffa1  test    eax, eax
0x18002ffa3  jnz     short loc_18002FFAB
0x18002ffa5  call    cs:__imp_GetLastError
0x18002ffab  mov     rdx, rbx
0x18002ffae  mov     rcx, rdi
0x18002ffb1  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18002ffb6  test    rbx, rbx
0x18002ffb9  jz      short loc_18002FFC4
0x18002ffbb  mov     rcx, rbx; pv
0x18002ffbe  call    cs:__imp_CoTaskMemFree
0x18002ffc4  lea     r11, [rsp+68h+var_18]
0x18002ffc9  mov     rax, rdi
0x18002ffcc  mov     rbx, [r11+28h]
0x18002ffd0  mov     rbp, [r11+30h]
0x18002ffd4  mov     rsp, r11
0x18002ffd7  pop     r14
0x18002ffd9  pop     rdi
0x18002ffda  pop     rsi
0x18002ffdb  retn
```
