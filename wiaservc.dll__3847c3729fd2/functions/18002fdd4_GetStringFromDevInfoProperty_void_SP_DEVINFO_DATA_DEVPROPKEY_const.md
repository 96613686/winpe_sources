# GetStringFromDevInfoProperty(void *,_SP_DEVINFO_DATA *,_DEVPROPKEY const *)

- ea: `0x18002fdd4`
- end: `0x18002fed4`
- name: `?GetStringFromDevInfoProperty@@YA?AV?$CSimpleStringBase@G@@PEAXPEAU_SP_DEVINFO_DATA@@PEBU_DEVPROPKEY@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18002fc10`
- `0x1800466e8`

## callees

- `0x18000f4fc`
- `0x18002fdd4`
- `0x180034658`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002fe2c`
- `KERNEL32!GetLastError` at `0x18002fe9d`
- `KERNEL32!GetLastError` at `0x18002fe2c`
- `KERNEL32!GetLastError` at `0x18002fe9d`
- `ole32!CoTaskMemFree` at `0x18002feb6`
- `ole32!CoTaskMemFree` at `0x18002feb6`
- `ole32!CoTaskMemAlloc` at `0x18002fe49`
- `ole32!CoTaskMemAlloc` at `0x18002fe49`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18002fe22`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18002fe93`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18002fe22`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18002fe93`

## pseudocode

```c
__int64 __fastcall GetStringFromDevInfoProperty(
        __int64 a1,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
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
  if ( !SetupDiGetDevicePropertyW(a2, a3, a4, PropertyType, 0, 0, (PDWORD)&cb, 0) )
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
        if ( !SetupDiGetDevicePropertyW(a2, a3, a4, PropertyType, PropertyBuffer, cb, (PDWORD)&cb, 0) )
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
0x18002fdd4  mov     rax, rsp
0x18002fdd7  mov     [rax+10h], rbx
0x18002fddb  mov     [rax+18h], rbp
0x18002fddf  push    rsi
0x18002fde0  push    rdi
0x18002fde1  push    r14
0x18002fde3  sub     rsp, 50h
0x18002fde7  xor     ebx, ebx
0x18002fde9  mov     dword ptr [rax+8], 0
0x18002fdf0  mov     [rax-30h], ebx
0x18002fdf3  mov     rsi, r9
0x18002fdf6  mov     [rax-28h], ebx
0x18002fdf9  lea     rax, [rax+8]
0x18002fdfd  mov     rbp, r8
0x18002fe00  mov     [rsp+68h+RequiredSize], rax; RequiredSize
0x18002fe05  mov     r14, rdx
0x18002fe08  mov     [rsp+68h+PropertyBufferSize], ebx; PropertyBufferSize
0x18002fe0c  mov     rdi, rcx
0x18002fe0f  mov     [rsp+68h+PropertyBuffer], rbx; PropertyBuffer
0x18002fe14  lea     r9, [rsp+68h+PropertyType]; PropertyType
0x18002fe19  mov     r8, rsi; PropertyKey
0x18002fe1c  mov     rdx, rbp; DeviceInfoData
0x18002fe1f  mov     rcx, r14; DeviceInfoSet
0x18002fe22  call    cs:__imp_SetupDiGetDevicePropertyW
0x18002fe28  test    eax, eax
0x18002fe2a  jnz     short loc_18002FEA3
0x18002fe2c  call    cs:__imp_GetLastError
0x18002fe32  test    eax, eax
0x18002fe34  jle     short loc_18002FE3E
0x18002fe36  movzx   eax, ax
0x18002fe39  or      eax, 80070000h
0x18002fe3e  cmp     eax, 8007007Ah
0x18002fe43  jnz     short loc_18002FEA3
0x18002fe45  mov     ecx, dword ptr [rsp+68h+cb]; cb
0x18002fe49  call    cs:__imp_CoTaskMemAlloc
0x18002fe4f  mov     rbx, rax
0x18002fe52  test    rax, rax
0x18002fe55  jz      short loc_18002FEA3
0x18002fe57  mov     r8d, dword ptr [rsp+68h+cb]; Size
0x18002fe5c  xor     edx, edx; Val
0x18002fe5e  mov     rcx, rax; void *
0x18002fe61  call    memset_0
0x18002fe66  mov     ecx, dword ptr [rsp+68h+cb]
0x18002fe6a  lea     rax, [rsp+68h+cb]
0x18002fe6f  mov     [rsp+68h+Flags], 0; Flags
0x18002fe77  lea     r9, [rsp+68h+PropertyType]; PropertyType
0x18002fe7c  mov     [rsp+68h+RequiredSize], rax; RequiredSize
0x18002fe81  mov     r8, rsi; PropertyKey
0x18002fe84  mov     [rsp+68h+PropertyBufferSize], ecx; PropertyBufferSize
0x18002fe88  mov     rdx, rbp; DeviceInfoData
0x18002fe8b  mov     rcx, r14; DeviceInfoSet
0x18002fe8e  mov     [rsp+68h+PropertyBuffer], rbx; PropertyBuffer
0x18002fe93  call    cs:__imp_SetupDiGetDevicePropertyW
0x18002fe99  test    eax, eax
0x18002fe9b  jnz     short loc_18002FEA3
0x18002fe9d  call    cs:__imp_GetLastError
0x18002fea3  mov     rdx, rbx
0x18002fea6  mov     rcx, rdi
0x18002fea9  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18002feae  test    rbx, rbx
0x18002feb1  jz      short loc_18002FEBC
0x18002feb3  mov     rcx, rbx; pv
0x18002feb6  call    cs:__imp_CoTaskMemFree
0x18002febc  lea     r11, [rsp+68h+var_18]
0x18002fec1  mov     rax, rdi
0x18002fec4  mov     rbx, [r11+28h]
0x18002fec8  mov     rbp, [r11+30h]
0x18002fecc  mov     rsp, r11
0x18002fecf  pop     r14
0x18002fed1  pop     rdi
0x18002fed2  pop     rsi
0x18002fed3  retn
```
