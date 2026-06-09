# GetUSBDiskSpeedInformation

- ea: `0x18000f74c`
- end: `0x18000f9e6`
- name: `GetUSBDiskSpeedInformation`
- size: `666`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1800074fc`

## callees

- `0x180002410`
- `0x180002e4a`
- `0x18000e928`
- `0x18000f3cc`
- `0x18000f4f4`
- `0x18000f594`
- `0x18000f600`
- `0x18000f74c`
- `0x18000fb20`
- `0x18000fbf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8bc`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000f7dc`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000f7dc`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000f9c2`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000f9c2`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000f8a5`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000f8a5`

## pseudocode

```c
__int64 __fastcall GetUSBDiskSpeedInformation(int a1, __int64 a2)
{
  unsigned __int16 *v4; // rsi
  void *DeviceInfoList; // rax
  void *v6; // rdi
  unsigned int LastError; // ebx
  char v8; // al
  const struct _GUID *v9; // rdx
  unsigned int SymbolicLinkDevice; // eax
  unsigned __int16 v11; // dx
  char v12; // al
  unsigned __int16 v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  _USB_DEVICE_SPEED v15; // [rsp+34h] [rbp-CCh] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h]
  __int128 v20; // [rsp+68h] [rbp-98h]
  __int128 v21; // [rsp+78h] [rbp-88h] BYREF
  __int128 v22; // [rsp+88h] [rbp-78h]
  __int128 v23; // [rsp+98h] [rbp-68h]
  _OWORD v24[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v25[48]; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v26[3]; // [rsp+F8h] [rbp-8h] BYREF

  v15 = UsbLowSpeed;
  v16 = 0;
  v14[0] = 0;
  v4 = 0;
  v17 = 0;
  memset(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  memset(v25, 0, sizeof(v25));
  v18 = 0;
  v19 = 0;
  v20 = 0;
  DeviceInfoList = (void *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v6 = DeviceInfoList;
  if ( DeviceInfoList == (void *)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_23;
  }
  LastError = AddDeviceInterface(DeviceInfoList, &GUID_DEVINTERFACE_DISK);
  if ( !LastError )
  {
    LastError = AddDeviceInterface(v6, &GUID_DEVINTERFACE_USB_HUB);
    if ( !LastError )
    {
      LastError = FindMatchingDeviceInfoData(v6, a1, (struct _DO_DEVINFO_DATA *)v26);
      if ( !LastError )
      {
        LastError = GetParentDevice(v6, (struct _DO_DEVINFO_DATA *)v26, (struct _DEVPROPKEY *)v25);
        if ( !LastError )
        {
          LastError = GetParentDevice(v6, (struct _DO_DEVINFO_DATA *)v25, (struct _DEVPROPKEY *)&v18);
          if ( !LastError )
          {
            memset(v24, 0, sizeof(v24));
            LODWORD(v24[0]) = 32;
            if ( (unsigned int)DevObjEnumDeviceInterfaces(v6, &v18, &GUID_DEVINTERFACE_USB_HUB, 0, v24) )
            {
              v8 = 1;
            }
            else
            {
              if ( GetLastError() == 259 )
                goto LABEL_16;
              LastError = GetLastError();
              v8 = 0;
              if ( LastError )
                goto LABEL_23;
            }
            if ( v8 )
            {
              LastError = GetParentHubPortNumber(v6, (struct _DO_DEVINFO_DATA *)v25, v14);
              if ( LastError )
                goto LABEL_23;
              v21 = v18;
              v22 = v19;
              v23 = v20;
LABEL_18:
              SymbolicLinkDevice = GetSymbolicLinkDevice(v6, v9, (struct _DO_DEVINFO_DATA *)&v21, &v17);
              v4 = v17;
              LastError = SymbolicLinkDevice;
              if ( !SymbolicLinkDevice )
              {
                LastError = UsbHelper_GetDeviceSpeed(v17, v14[0], &v15);
                if ( !LastError )
                {
                  v11 = v14[0];
                  *(_DWORD *)(a2 + 4) = v15;
                  LastError = UsbHelper_GetDeviceSpeedInformation(
                                v4,
                                v11,
                                (union _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS *)&v16);
                  if ( !LastError )
                  {
                    v12 = v16;
                    *(_BYTE *)a2 = (v16 & 2) != 0;
                    if ( (v12 & 1) != 0 )
                      *(_DWORD *)(a2 + 4) = 3;
                  }
                }
              }
              goto LABEL_23;
            }
LABEL_16:
            LastError = GetParentHubPortNumber(v6, (struct _DO_DEVINFO_DATA *)&v18, v14);
            if ( LastError )
              goto LABEL_23;
            LastError = GetParentDevice(v6, (struct _DO_DEVINFO_DATA *)&v18, (struct _DEVPROPKEY *)&v21);
            if ( LastError )
              goto LABEL_23;
            goto LABEL_18;
          }
        }
      }
    }
  }
LABEL_23:
  free(v4);
  if ( v6 != (void *)-1LL )
    DevObjDestroyDeviceInfoList(v6);
  return LastError;
}

```

## disassembly

```asm
0x18000f74c  push    rbp
0x18000f74e  push    rbx
0x18000f74f  push    rsi
0x18000f750  push    rdi
0x18000f751  push    r14
0x18000f753  push    r15
0x18000f755  lea     rbp, [rsp-38h]
0x18000f75a  sub     rsp, 138h
0x18000f761  mov     rax, cs:__security_cookie
0x18000f768  xor     rax, rsp
0x18000f76b  mov     [rbp+60h+var_38], rax
0x18000f76f  xorps   xmm0, xmm0
0x18000f772  mov     [rsp+160h+var_12C], 0
0x18000f77a  xorps   xmm1, xmm1
0x18000f77d  mov     [rsp+160h+var_128], 0
0x18000f785  xor     eax, eax
0x18000f787  mov     r14, rdx
0x18000f78a  mov     r15d, ecx
0x18000f78d  mov     [rsp+160h+var_130], ax
0x18000f792  xor     esi, esi
0x18000f794  mov     [rsp+160h+var_140], rax
0x18000f799  xor     edx, edx
0x18000f79b  mov     [rsp+160h+var_120], rsi
0x18000f7a0  xor     ecx, ecx
0x18000f7a2  xor     r9d, r9d
0x18000f7a5  xor     r8d, r8d
0x18000f7a8  movups  [rbp+60h+var_68], xmm0
0x18000f7ac  movups  [rbp+60h+var_58], xmm0
0x18000f7b0  movups  [rbp+60h+var_48], xmm0
0x18000f7b4  movups  [rsp+160h+var_E8], xmm1
0x18000f7b9  movups  [rbp+60h+var_D8], xmm1
0x18000f7bd  movups  [rbp+60h+var_C8], xmm1
0x18000f7c1  movups  [rbp+60h+var_98], xmm0
0x18000f7c5  movups  [rbp+60h+var_88], xmm0
0x18000f7c9  movups  [rbp+60h+var_78], xmm0
0x18000f7cd  movups  [rsp+160h+var_118], xmm1
0x18000f7d2  movups  [rsp+160h+var_108], xmm1
0x18000f7d7  movups  [rsp+160h+var_F8], xmm1
0x18000f7dc  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000f7e2  mov     rdi, rax
0x18000f7e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f7e9  jnz     short loc_18000F7F8
0x18000f7eb  call    cs:__imp_GetLastError
0x18000f7f1  mov     ebx, eax
0x18000f7f3  jmp     loc_18000F9B1
0x18000f7f8  lea     rdx, GUID_DEVINTERFACE_DISK; struct _GUID *
0x18000f7ff  mov     rcx, rdi; void *
0x18000f802  call    ?AddDeviceInterface@@YAKPEAXPEBU_GUID@@@Z; AddDeviceInterface(void *,_GUID const *)
0x18000f807  mov     ebx, eax
0x18000f809  test    eax, eax
0x18000f80b  jnz     loc_18000F9B1
0x18000f811  lea     rdx, GUID_DEVINTERFACE_USB_HUB; struct _GUID *
0x18000f818  mov     rcx, rdi; void *
0x18000f81b  call    ?AddDeviceInterface@@YAKPEAXPEBU_GUID@@@Z; AddDeviceInterface(void *,_GUID const *)
0x18000f820  mov     ebx, eax
0x18000f822  test    eax, eax
0x18000f824  jnz     loc_18000F9B1
0x18000f82a  lea     r8, [rbp+60h+var_68]; struct _DO_DEVINFO_DATA *
0x18000f82e  mov     edx, r15d; unsigned int
0x18000f831  mov     rcx, rdi; void *
0x18000f834  call    ?FindMatchingDeviceInfoData@@YAKPEAXKPEAU_DO_DEVINFO_DATA@@@Z; FindMatchingDeviceInfoData(void *,ulong,_DO_DEVINFO_DATA *)
0x18000f839  mov     ebx, eax
0x18000f83b  test    eax, eax
0x18000f83d  jnz     loc_18000F9B1
0x18000f843  lea     r8, [rbp+60h+var_98]; struct _DO_DEVINFO_DATA *
0x18000f847  mov     rcx, rdi; void *
0x18000f84a  lea     rdx, [rbp+60h+var_68]; struct _DO_DEVINFO_DATA *
0x18000f84e  call    ?GetParentDevice@@YAKPEAXPEAU_DO_DEVINFO_DATA@@1@Z; GetParentDevice(void *,_DO_DEVINFO_DATA *,_DO_DEVINFO_DATA *)
0x18000f853  mov     ebx, eax
0x18000f855  test    eax, eax
0x18000f857  jnz     loc_18000F9B1
0x18000f85d  lea     r8, [rsp+160h+var_118]; struct _DO_DEVINFO_DATA *
0x18000f862  mov     rcx, rdi; void *
0x18000f865  lea     rdx, [rbp+60h+var_98]; struct _DO_DEVINFO_DATA *
0x18000f869  call    ?GetParentDevice@@YAKPEAXPEAU_DO_DEVINFO_DATA@@1@Z; GetParentDevice(void *,_DO_DEVINFO_DATA *,_DO_DEVINFO_DATA *)
0x18000f86e  mov     ebx, eax
0x18000f870  test    eax, eax
0x18000f872  jnz     loc_18000F9B1
0x18000f878  xorps   xmm0, xmm0
0x18000f87b  lea     rax, [rbp+60h+var_B8]
0x18000f87f  movups  [rbp+60h+var_B8], xmm0
0x18000f883  xor     r9d, r9d
0x18000f886  mov     dword ptr [rbp+60h+var_B8], 20h ; ' '
0x18000f88d  lea     r8, GUID_DEVINTERFACE_USB_HUB
0x18000f894  mov     [rsp+160h+var_140], rax
0x18000f899  lea     rdx, [rsp+160h+var_118]
0x18000f89e  mov     rcx, rdi
0x18000f8a1  movups  [rbp+60h+var_A8], xmm0
0x18000f8a5  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18000f8ab  test    eax, eax
0x18000f8ad  jnz     short loc_18000F8CF
0x18000f8af  call    cs:__imp_GetLastError
0x18000f8b5  cmp     eax, 103h
0x18000f8ba  jz      short loc_18000F90E
0x18000f8bc  call    cs:__imp_GetLastError
0x18000f8c2  mov     ebx, eax
0x18000f8c4  xor     al, al
0x18000f8c6  test    ebx, ebx
0x18000f8c8  jz      short loc_18000F8D1
0x18000f8ca  jmp     loc_18000F9B1
0x18000f8cf  mov     al, 1
0x18000f8d1  test    al, al
0x18000f8d3  jz      short loc_18000F90E
0x18000f8d5  lea     r8, [rsp+160h+var_130]; unsigned __int16 *
0x18000f8da  mov     rcx, rdi; void *
0x18000f8dd  lea     rdx, [rbp+60h+var_98]; struct _DO_DEVINFO_DATA *
0x18000f8e1  call    ?GetParentHubPortNumber@@YAKPEAXPEAU_DO_DEVINFO_DATA@@PEAG@Z; GetParentHubPortNumber(void *,_DO_DEVINFO_DATA *,ushort *)
0x18000f8e6  mov     ebx, eax
0x18000f8e8  test    eax, eax
0x18000f8ea  jnz     loc_18000F9B1
0x18000f8f0  movups  xmm0, [rsp+160h+var_118]
0x18000f8f5  movups  xmm1, [rsp+160h+var_108]
0x18000f8fa  movups  [rsp+160h+var_E8], xmm0
0x18000f8ff  movups  xmm0, [rsp+160h+var_F8]
0x18000f904  movups  [rbp+60h+var_D8], xmm1
0x18000f908  movups  [rbp+60h+var_C8], xmm0
0x18000f90c  jmp     short loc_18000F942
0x18000f90e  lea     r8, [rsp+160h+var_130]; unsigned __int16 *
0x18000f913  mov     rcx, rdi; void *
0x18000f916  lea     rdx, [rsp+160h+var_118]; struct _DO_DEVINFO_DATA *
0x18000f91b  call    ?GetParentHubPortNumber@@YAKPEAXPEAU_DO_DEVINFO_DATA@@PEAG@Z; GetParentHubPortNumber(void *,_DO_DEVINFO_DATA *,ushort *)
0x18000f920  mov     ebx, eax
0x18000f922  test    eax, eax
0x18000f924  jnz     loc_18000F9B1
0x18000f92a  lea     r8, [rsp+160h+var_E8]; struct _DO_DEVINFO_DATA *
0x18000f92f  mov     rcx, rdi; void *
0x18000f932  lea     rdx, [rsp+160h+var_118]; struct _DO_DEVINFO_DATA *
0x18000f937  call    ?GetParentDevice@@YAKPEAXPEAU_DO_DEVINFO_DATA@@1@Z; GetParentDevice(void *,_DO_DEVINFO_DATA *,_DO_DEVINFO_DATA *)
0x18000f93c  mov     ebx, eax
0x18000f93e  test    eax, eax
0x18000f940  jnz     short loc_18000F9B1
0x18000f942  lea     r9, [rsp+160h+var_120]; unsigned __int16 **
0x18000f947  mov     rcx, rdi; void *
0x18000f94a  lea     r8, [rsp+160h+var_E8]; struct _DO_DEVINFO_DATA *
0x18000f94f  call    ?GetSymbolicLinkDevice@@YAKPEAXPEBU_GUID@@PEAU_DO_DEVINFO_DATA@@PEAPEAG@Z; GetSymbolicLinkDevice(void *,_GUID const *,_DO_DEVINFO_DATA *,ushort * *)
0x18000f954  mov     rsi, [rsp+160h+var_120]
0x18000f959  mov     ebx, eax
0x18000f95b  test    eax, eax
0x18000f95d  jnz     short loc_18000F9B1
0x18000f95f  movzx   edx, [rsp+160h+var_130]; unsigned __int16
0x18000f964  lea     r8, [rsp+160h+var_12C]; enum _USB_DEVICE_SPEED *
0x18000f969  mov     rcx, rsi; unsigned __int16 *
0x18000f96c  call    ?UsbHelper_GetDeviceSpeed@@YAKPEAGGPEAW4_USB_DEVICE_SPEED@@@Z; UsbHelper_GetDeviceSpeed(ushort *,ushort,_USB_DEVICE_SPEED *)
0x18000f971  mov     ebx, eax
0x18000f973  test    eax, eax
0x18000f975  jnz     short loc_18000F9B1
0x18000f977  mov     eax, [rsp+160h+var_12C]
0x18000f97b  lea     r8, [rsp+160h+var_128]; union _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS *
0x18000f980  movzx   edx, [rsp+160h+var_130]; unsigned __int16
0x18000f985  mov     rcx, rsi; unsigned __int16 *
0x18000f988  mov     [r14+4], eax
0x18000f98c  call    ?UsbHelper_GetDeviceSpeedInformation@@YAKPEAGGPEAT_USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS@@@Z; UsbHelper_GetDeviceSpeedInformation(ushort *,ushort,_USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS *)
0x18000f991  mov     ebx, eax
0x18000f993  test    eax, eax
0x18000f995  jnz     short loc_18000F9B1
0x18000f997  mov     eax, [rsp+160h+var_128]
0x18000f99b  mov     ecx, eax
0x18000f99d  shr     ecx, 1
0x18000f99f  and     cl, 1
0x18000f9a2  mov     [r14], cl
0x18000f9a5  test    al, 1
0x18000f9a7  jz      short loc_18000F9B1
0x18000f9a9  mov     dword ptr [r14+4], 3
0x18000f9b1  mov     rcx, rsi; Block
0x18000f9b4  call    free
0x18000f9b9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f9bd  jz      short loc_18000F9C8
0x18000f9bf  mov     rcx, rdi
0x18000f9c2  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18000f9c8  mov     eax, ebx
0x18000f9ca  mov     rcx, [rbp+60h+var_38]
0x18000f9ce  xor     rcx, rsp; StackCookie
0x18000f9d1  call    __security_check_cookie
0x18000f9d6  add     rsp, 138h
0x18000f9dd  pop     r15
0x18000f9df  pop     r14
0x18000f9e1  pop     rdi
0x18000f9e2  pop     rsi
0x18000f9e3  pop     rbx
0x18000f9e4  pop     rbp
0x18000f9e5  retn
```
