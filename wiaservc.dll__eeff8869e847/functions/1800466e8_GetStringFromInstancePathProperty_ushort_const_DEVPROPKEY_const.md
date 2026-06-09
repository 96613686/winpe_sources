# GetStringFromInstancePathProperty(ushort const *,_DEVPROPKEY const *)

- ea: `0x1800466e8`
- end: `0x180046832`
- name: `?GetStringFromInstancePathProperty@@YA?AV?$CSimpleStringBase@G@@PEBGPEBU_DEVPROPKEY@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180029290`

## callees

- `0x1800113d8`
- `0x180011a94`
- `0x18002fdd4`
- `0x180033cc0`
- `0x1800466e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004676d`
- `KERNEL32!GetLastError` at `0x1800467b2`
- `KERNEL32!GetLastError` at `0x18004676d`
- `KERNEL32!GetLastError` at `0x1800467b2`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180046802`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180046802`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18004675e`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18004675e`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800467a8`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800467a8`

## pseudocode

```c
__int64 __fastcall GetStringFromInstancePathProperty(__int64 a1, const WCHAR *a2, __int64 a3)
{
  _WORD *v4; // rcx
  HDEVINFO DeviceInfoList; // rdi
  signed int LastError; // eax
  signed int v9; // ebx
  signed int v10; // eax
  __int64 StringFromDevInfoProperty; // rax
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+30h] [rbp-188h] BYREF
  _QWORD v14[38]; // [rsp+50h] [rbp-168h] BYREF

  *(_QWORD *)a1 = &CSimpleStringBase<unsigned short>::`vftable';
  v4 = (_WORD *)(a1 + 8);
  *(_QWORD *)(a1 + 264) = v4;
  *(_OWORD *)&DeviceInfoData.cbSize = 0;
  *v4 = 0;
  *(_OWORD *)&DeviceInfoData.ClassGuid.Data4[4] = 0;
  *(_QWORD *)(a1 + 272) = 128;
  *(_QWORD *)(a1 + 280) = 16;
  *(_BYTE *)(a1 + 288) = 0;
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
  DeviceInfoData.cbSize = 32;
  if ( !SetupDiOpenDeviceInfoW(DeviceInfoList, a2, 0, 0, &DeviceInfoData) )
  {
    v10 = GetLastError();
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( v9 >= 0 )
  {
    StringFromDevInfoProperty = GetStringFromDevInfoProperty(v14, DeviceInfoList, &DeviceInfoData, a3);
    CSimpleStringBase<unsigned short>::operator=(a1, StringFromDevInfoProperty);
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
0x1800466e8  mov     [rsp+arg_18], rbx
0x1800466ed  push    rbp
0x1800466ee  push    rsi
0x1800466ef  push    rdi
0x1800466f0  push    r12
0x1800466f2  push    r14
0x1800466f4  sub     rsp, 190h
0x1800466fb  mov     rax, cs:__security_cookie
0x180046702  xor     rax, rsp
0x180046705  mov     [rsp+1B8h+var_38], rax
0x18004670d  mov     rsi, rcx
0x180046710  lea     r12, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180046717  mov     [rcx], r12
0x18004671a  xorps   xmm0, xmm0
0x18004671d  add     rcx, 8
0x180046721  xor     eax, eax
0x180046723  mov     rbp, rdx
0x180046726  mov     r14, r8
0x180046729  mov     [rsi+108h], rcx
0x180046730  xor     edx, edx; hwndParent
0x180046732  movups  xmmword ptr [rsp+1B8h+var_188.cbSize], xmm0
0x180046737  mov     [rcx], ax
0x18004673a  xor     ecx, ecx; ClassGuid
0x18004673c  movups  xmmword ptr [rsp+1B8h+var_188.ClassGuid.Data4+4], xmm0
0x180046741  mov     qword ptr [rsi+110h], 80h
0x18004674c  mov     qword ptr [rsi+118h], 10h
0x180046757  mov     byte ptr [rsi+120h], 0
0x18004675e  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180046764  mov     rdi, rax
0x180046767  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004676b  jnz     short loc_180046788
0x18004676d  call    cs:__imp_GetLastError
0x180046773  mov     ebx, eax
0x180046775  test    eax, eax
0x180046777  jle     short loc_180046782
0x180046779  movzx   ebx, ax
0x18004677c  or      ebx, 80070000h
0x180046782  test    ebx, ebx
0x180046784  js      short loc_1800467FF
0x180046786  jmp     short loc_18004678A
0x180046788  xor     ebx, ebx
0x18004678a  lea     rax, [rsp+1B8h+var_188]
0x18004678f  mov     [rsp+1B8h+var_188.cbSize], 20h ; ' '
0x180046797  xor     r9d, r9d; OpenFlags
0x18004679a  mov     [rsp+1B8h+DeviceInfoData], rax; DeviceInfoData
0x18004679f  xor     r8d, r8d; hwndParent
0x1800467a2  mov     rdx, rbp; DeviceInstanceId
0x1800467a5  mov     rcx, rdi; DeviceInfoSet
0x1800467a8  call    cs:__imp_SetupDiOpenDeviceInfoW
0x1800467ae  test    eax, eax
0x1800467b0  jnz     short loc_1800467C7
0x1800467b2  call    cs:__imp_GetLastError
0x1800467b8  mov     ebx, eax
0x1800467ba  test    eax, eax
0x1800467bc  jle     short loc_1800467C7
0x1800467be  movzx   ebx, ax
0x1800467c1  or      ebx, 80070000h
0x1800467c7  test    ebx, ebx
0x1800467c9  js      short loc_1800467FA
0x1800467cb  mov     r9, r14
0x1800467ce  lea     r8, [rsp+1B8h+var_188]
0x1800467d3  mov     rdx, rdi
0x1800467d6  lea     rcx, [rsp+1B8h+var_168]
0x1800467db  call    ?GetStringFromDevInfoProperty@@YA?AV?$CSimpleStringBase@G@@PEAXPEAU_SP_DEVINFO_DATA@@PEBU_DEVPROPKEY@@@Z; GetStringFromDevInfoProperty(void *,_SP_DEVINFO_DATA *,_DEVPROPKEY const *)
0x1800467e0  mov     rdx, rax
0x1800467e3  mov     rcx, rsi
0x1800467e6  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x1800467eb  lea     rcx, [rsp+1B8h+var_168]
0x1800467f0  mov     [rsp+1B8h+var_168], r12
0x1800467f5  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800467fa  test    rdi, rdi
0x1800467fd  jz      short loc_180046808
0x1800467ff  mov     rcx, rdi; DeviceInfoSet
0x180046802  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180046808  mov     rax, rsi
0x18004680b  mov     rcx, [rsp+1B8h+var_38]
0x180046813  xor     rcx, rsp; StackCookie
0x180046816  call    __security_check_cookie
0x18004681b  mov     rbx, [rsp+1B8h+arg_18]
0x180046823  add     rsp, 190h
0x18004682a  pop     r14
0x18004682c  pop     r12
0x18004682e  pop     rdi
0x18004682f  pop     rsi
0x180046830  pop     rbp
0x180046831  retn
```
