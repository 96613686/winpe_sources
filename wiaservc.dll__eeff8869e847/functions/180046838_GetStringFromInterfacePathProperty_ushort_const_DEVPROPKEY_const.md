# GetStringFromInterfacePathProperty(ushort const *,_DEVPROPKEY const *)

- ea: `0x180046838`
- end: `0x18004697a`
- name: `?GetStringFromInterfacePathProperty@@YA?AV?$CSimpleStringBase@G@@PEBGPEBU_DEVPROPKEY@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180029290`

## callees

- `0x1800113d8`
- `0x180011a94`
- `0x18002fedc`
- `0x180033cc0`
- `0x180046838`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800468c5`
- `KERNEL32!GetLastError` at `0x1800468fa`
- `KERNEL32!GetLastError` at `0x1800468c5`
- `KERNEL32!GetLastError` at `0x1800468fa`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18004694a`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18004694a`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x1800468f0`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x1800468f0`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800468b6`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800468b6`

## pseudocode

```c
__int64 __fastcall GetStringFromInterfacePathProperty(__int64 a1, const WCHAR *a2, __int64 a3)
{
  _WORD *v4; // rcx
  HDEVINFO DeviceInfoList; // rdi
  signed int LastError; // eax
  signed int v9; // ebx
  signed int v10; // eax
  __int64 StringFromDevInterfaceProperty; // rax
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+20h] [rbp-188h] BYREF
  _QWORD v14[38]; // [rsp+40h] [rbp-168h] BYREF

  *(_QWORD *)a1 = &CSimpleStringBase<unsigned short>::`vftable';
  v4 = (_WORD *)(a1 + 8);
  *(_QWORD *)(a1 + 264) = v4;
  *(_OWORD *)&DeviceInterfaceData.cbSize = 0;
  *v4 = 0;
  *(_QWORD *)(a1 + 272) = 128;
  *(_QWORD *)(a1 + 280) = 16;
  *(_BYTE *)(a1 + 288) = 0;
  *(_OWORD *)&DeviceInterfaceData.InterfaceClassGuid.Data4[4] = 0;
  DeviceInterfaceData.cbSize = 32;
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_13;
  }
  else
  {
    v9 = 0;
  }
  if ( !SetupDiOpenDeviceInterfaceW(DeviceInfoList, a2, 0, &DeviceInterfaceData) )
  {
    v10 = GetLastError();
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( v9 >= 0 )
  {
    StringFromDevInterfaceProperty = GetStringFromDevInterfaceProperty(v14, DeviceInfoList, &DeviceInterfaceData, a3);
    CSimpleStringBase<unsigned short>::operator=(a1, StringFromDevInterfaceProperty);
    v14[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v14);
  }
  if ( DeviceInfoList )
LABEL_13:
    SetupDiDestroyDeviceInfoList(DeviceInfoList);
  return a1;
}

```

## disassembly

```asm
0x180046838  mov     [rsp+arg_18], rbx
0x18004683d  push    rbp
0x18004683e  push    rsi
0x18004683f  push    rdi
0x180046840  push    r12
0x180046842  push    r14
0x180046844  sub     rsp, 180h
0x18004684b  mov     rax, cs:__security_cookie
0x180046852  xor     rax, rsp
0x180046855  mov     [rsp+1A8h+var_38], rax
0x18004685d  mov     rsi, rcx
0x180046860  lea     r12, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180046867  mov     [rcx], r12
0x18004686a  xorps   xmm0, xmm0
0x18004686d  add     rcx, 8
0x180046871  xor     eax, eax
0x180046873  mov     rbp, rdx
0x180046876  mov     r14, r8
0x180046879  mov     [rsi+108h], rcx
0x180046880  xor     edx, edx; hwndParent
0x180046882  movups  xmmword ptr [rsp+1A8h+DeviceInterfaceData.cbSize], xmm0
0x180046887  mov     [rcx], ax
0x18004688a  xor     ecx, ecx; ClassGuid
0x18004688c  mov     qword ptr [rsi+110h], 80h
0x180046897  mov     qword ptr [rsi+118h], 10h
0x1800468a2  mov     byte ptr [rsi+120h], 0
0x1800468a9  movups  xmmword ptr [rsp+1A8h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x1800468ae  mov     [rsp+1A8h+DeviceInterfaceData.cbSize], 20h ; ' '
0x1800468b6  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800468bc  mov     rdi, rax
0x1800468bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800468c3  jnz     short loc_1800468E0
0x1800468c5  call    cs:__imp_GetLastError
0x1800468cb  mov     ebx, eax
0x1800468cd  test    eax, eax
0x1800468cf  jle     short loc_1800468DA
0x1800468d1  movzx   ebx, ax
0x1800468d4  or      ebx, 80070000h
0x1800468da  test    ebx, ebx
0x1800468dc  js      short loc_180046947
0x1800468de  jmp     short loc_1800468E2
0x1800468e0  xor     ebx, ebx
0x1800468e2  lea     r9, [rsp+1A8h+DeviceInterfaceData]; DeviceInterfaceData
0x1800468e7  xor     r8d, r8d; OpenFlags
0x1800468ea  mov     rdx, rbp; DevicePath
0x1800468ed  mov     rcx, rdi; DeviceInfoSet
0x1800468f0  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x1800468f6  test    eax, eax
0x1800468f8  jnz     short loc_18004690F
0x1800468fa  call    cs:__imp_GetLastError
0x180046900  mov     ebx, eax
0x180046902  test    eax, eax
0x180046904  jle     short loc_18004690F
0x180046906  movzx   ebx, ax
0x180046909  or      ebx, 80070000h
0x18004690f  test    ebx, ebx
0x180046911  js      short loc_180046942
0x180046913  mov     r9, r14
0x180046916  lea     r8, [rsp+1A8h+DeviceInterfaceData]
0x18004691b  mov     rdx, rdi
0x18004691e  lea     rcx, [rsp+1A8h+var_168]
0x180046923  call    ?GetStringFromDevInterfaceProperty@@YA?AV?$CSimpleStringBase@G@@PEAXPEAU_SP_DEVICE_INTERFACE_DATA@@PEBU_DEVPROPKEY@@@Z; GetStringFromDevInterfaceProperty(void *,_SP_DEVICE_INTERFACE_DATA *,_DEVPROPKEY const *)
0x180046928  mov     rdx, rax
0x18004692b  mov     rcx, rsi
0x18004692e  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180046933  lea     rcx, [rsp+1A8h+var_168]
0x180046938  mov     [rsp+1A8h+var_168], r12
0x18004693d  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180046942  test    rdi, rdi
0x180046945  jz      short loc_180046950
0x180046947  mov     rcx, rdi; DeviceInfoSet
0x18004694a  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180046950  mov     rax, rsi
0x180046953  mov     rcx, [rsp+1A8h+var_38]
0x18004695b  xor     rcx, rsp; StackCookie
0x18004695e  call    __security_check_cookie
0x180046963  mov     rbx, [rsp+1A8h+arg_18]
0x18004696b  add     rsp, 180h
0x180046972  pop     r14
0x180046974  pop     r12
0x180046976  pop     rdi
0x180046977  pop     rsi
0x180046978  pop     rbp
0x180046979  retn
```
