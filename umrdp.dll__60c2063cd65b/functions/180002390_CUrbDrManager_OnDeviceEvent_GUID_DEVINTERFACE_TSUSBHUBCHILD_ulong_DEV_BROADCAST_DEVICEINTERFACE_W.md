# CUrbDrManager::OnDeviceEvent_GUID_DEVINTERFACE_TSUSBHUBCHILD(ulong,_DEV_BROADCAST_DEVICEINTERFACE_W *)

- ea: `0x180002390`
- end: `0x1800028ea`
- name: `?OnDeviceEvent_GUID_DEVINTERFACE_TSUSBHUBCHILD@CUrbDrManager@@QEAAXKPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z`
- size: `1370`
- prototype: `void(CUrbDrManager *__hidden this, unsigned int, struct _DEV_BROADCAST_DEVICEINTERFACE_W *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180002170`

## callees

- `0x180002390`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000db18`
- `0x18000f75c`
- `0x18000f79c`
- `0x180019d80`
- `0x180019d90`
- `0x18002f980`
- `0x180031258`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000254f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000254f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002656`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x180002804`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x180002804`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x18000279b`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x18000279b`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x1800027d9`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x1800027d9`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x1800027f9`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x1800027f9`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800024ff`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000262b`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800024ff`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000262b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800028b7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800028b7`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180002541`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180002648`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180002541`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180002648`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180002789`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180002789`

## string_xrefs

- `0x1800026a5`: `DevObjOpenDeviceInterface failed`

## pseudocode

```c
void __fastcall CUrbDrManager::OnDeviceEvent_GUID_DEVINTERFACE_TSUSBHUBCHILD(
        CUrbDrManager *this,
        int a2,
        struct _DEV_BROADCAST_DEVICEINTERFACE_W *a3)
{
  void *v5; // rbx
  int DeviceInfoAndDeviceInfoData; // eax
  __int64 v7; // rdx
  void *v8; // r13
  signed int v9; // r14d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // r12d
  unsigned int v15; // edi
  DWORD LastError; // esi
  int DeviceRegistryProperty; // eax
  unsigned int v18; // r14d
  int v19; // edi
  unsigned int v20; // eax
  int DeviceProperty; // eax
  signed int v22; // eax
  unsigned __int64 v23; // rcx
  HDEVINFO DeviceInfoList; // rdi
  BOOL v25; // esi
  int v26; // edi
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // [rsp+48h] [rbp-C0h] BYREF
  void *NeedReboot; // [rsp+50h] [rbp-B8h] BYREF
  int v31; // [rsp+58h] [rbp-B0h]
  int v32; // [rsp+5Ch] [rbp-ACh] BYREF
  _QWORD v33[6]; // [rsp+60h] [rbp-A8h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+90h] [rbp-78h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+B8h] [rbp-50h] BYREF

  NeedReboot = (void *)-1LL;
  LODWORD(v29) = 0;
  v32 = 0;
  v5 = 0;
  memset(v33, 0, sizeof(v33));
  if ( ((a2 - 0x8000) & 0xFFFFFFFB) != 0 )
    goto LABEL_67;
  DeviceInfoAndDeviceInfoData = CUrbDrManager::GetDeviceInfoAndDeviceInfoData(
                                  this,
                                  a3,
                                  &NeedReboot,
                                  (struct _DO_DEVINFO_DATA *)v33);
  v8 = NeedReboot;
  LOBYTE(v9) = DeviceInfoAndDeviceInfoData;
  if ( DeviceInfoAndDeviceInfoData < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 27;
      v12 = "CUrbDrManager::GetDeviceInfoAndDeviceInfoData failed";
LABEL_7:
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        v11,
        (unsigned int)WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v12,
        v9);
    }
    goto LABEL_65;
  }
  if ( a2 != 0x8000 )
  {
    if ( a2 == 32772 && *((_DWORD *)this + 41) )
    {
      LODWORD(NeedReboot) = 0;
      if ( !(unsigned __int8)IsDiUninstallDevicePresent() )
        goto LABEL_63;
      if ( !(unsigned int)DevObjGetDeviceInstanceId(v8, v33, DeviceInstanceId, 200, 0) )
        goto LABEL_63;
      DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
      if ( DeviceInfoList == (HDEVINFO)-1LL )
        goto LABEL_63;
      memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
      DeviceInfoData.cbSize = 32;
      v25 = 0;
      if ( !SetupDiOpenDeviceInfoW(DeviceInfoList, DeviceInstanceId, 0, 0, &DeviceInfoData) )
        v25 = DiUninstallDevice(0, DeviceInfoList, &DeviceInfoData, 0, (PBOOL)&NeedReboot);
      SetupDiDestroyDeviceInfoList(DeviceInfoList);
      if ( v25 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
        {
          v26 = (int)NeedReboot;
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            31,
            WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
            v27,
            v26);
        }
      }
      else
      {
LABEL_63:
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v28 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            32,
            WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
            v28);
        }
      }
    }
    goto LABEL_65;
  }
  v13 = *(_QWORD *)&WPP_GLOBAL_Control;
  v14 = 0;
  v15 = 0;
  LODWORD(NeedReboot) = 0;
  v31 = 12;
  LastError = 1168;
  v9 = -2147023728;
  while ( v15 < 3 )
  {
    if ( v15 )
    {
      v18 = 12;
      if ( v15 != 1 )
        v18 = 0;
      v31 = v18;
      DeviceRegistryProperty = DevObjGetDeviceRegistryProperty(v8, v33, v18, 0, 0, 0, &v29);
    }
    else
    {
      DeviceRegistryProperty = DevObjGetDeviceProperty(v8, v33, DEVPKEY_Device_Text_Description, &v32, 0, 0, &v29, 0);
      v18 = v31;
    }
    if ( DeviceRegistryProperty || (LastError = GetLastError(), LastError != 122) )
    {
      if ( LastError )
      {
        LastError = 13;
        v9 = -2147024883;
      }
      else
      {
        v9 = 0;
      }
      goto LABEL_38;
    }
    operator delete(v5);
    v5 = MIDL_user_allocate(saturated_mul((unsigned __int64)(unsigned int)v29 >> 1, 2u));
    if ( v5 )
    {
      v14 = v29;
      if ( v15 )
        DeviceProperty = DevObjGetDeviceRegistryProperty(v8, v33, v18, 0, v5, v29, &v29);
      else
        DeviceProperty = DevObjGetDeviceProperty(v8, v33, DEVPKEY_Device_Text_Description, &v32, v5, v29, &v29, 0);
      if ( DeviceProperty )
        goto LABEL_46;
      v22 = GetLastError();
      LastError = v22;
      if ( v22 > 0 )
        v9 = (unsigned __int16)v22 | 0x80070000;
      else
        v9 = v22;
      if ( v9 < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v11 = 29;
          v12 = "DevObjOpenDeviceInterface failed";
          goto LABEL_7;
        }
        goto LABEL_65;
      }
      goto LABEL_38;
    }
    LastError = 14;
    v9 = -2147024882;
    v13 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v19 = v29;
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        28,
        WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
        v20,
        v19);
      v15 = (unsigned int)NeedReboot;
LABEL_38:
      v13 = *(_QWORD *)&WPP_GLOBAL_Control;
    }
    LODWORD(NeedReboot) = ++v15;
  }
  if ( v9 >= 0 )
  {
    if ( !v5 )
      goto LABEL_65;
LABEL_46:
    if ( v14 )
    {
      v23 = (unsigned __int64)v14 >> 1;
      *((_WORD *)v5 + v23 - 1) = 0;
      if ( (Microsoft_Windows_TerminalServices_ServerUSBDevicesEnableBits & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(v23, v7, v5);
    }
    goto LABEL_65;
  }
  if ( (unsigned int *)v13 != &WPP_GLOBAL_Control && (*(_BYTE *)(v13 + 28) & 8) != 0 && *(_BYTE *)(v13 + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 30;
    v12 = "Unable to get device's description";
    goto LABEL_7;
  }
LABEL_65:
  if ( v8 != (void *)-1LL )
    DevObjDestroyDeviceInfoList(v8);
LABEL_67:
  operator delete(v5);
}

```

## disassembly

```asm
0x180002390  mov     r11, rsp
0x180002393  push    rbp
0x180002394  push    rbx
0x180002395  push    rsi
0x180002396  push    rdi
0x180002397  push    r15
0x180002399  lea     rbp, [r11-178h]
0x1800023a0  sub     rsp, 250h
0x1800023a7  mov     rax, cs:__security_cookie
0x1800023ae  xor     rax, rsp
0x1800023b1  mov     [rbp+170h+var_30], rax
0x1800023b8  xor     r15d, r15d
0x1800023bb  mov     qword ptr [rsp+270h+NeedReboot], 0FFFFFFFFFFFFFFFFh
0x1800023c4  xorps   xmm0, xmm0
0x1800023c7  mov     dword ptr [rsp+270h+var_230], r15d
0x1800023cc  lea     eax, [rdx-8000h]
0x1800023d2  mov     dword ptr [rsp+270h+var_220+4], r15d
0x1800023d7  mov     r10, r8
0x1800023da  mov     edi, edx
0x1800023dc  mov     rsi, rcx
0x1800023df  mov     ebx, r15d
0x1800023e2  movups  [rsp+270h+var_220+8], xmm0
0x1800023e7  movups  [rsp+270h+var_210+8], xmm0
0x1800023ec  movups  [rsp+270h+var_200+8], xmm0
0x1800023f1  test    eax, 0FFFFFFFBh
0x1800023f6  jnz     loc_1800028C5
0x1800023fc  mov     [r11+10h], r13
0x180002400  lea     r9, [rsp+270h+var_220+8]; struct _DO_DEVINFO_DATA *
0x180002405  mov     [r11+20h], r14
0x180002409  lea     r8, [rsp+270h+NeedReboot]; void **
0x18000240e  mov     rdx, r10; struct _DEV_BROADCAST_DEVICEINTERFACE_W *
0x180002411  mov     [r11+8], r12
0x180002415  call    ?GetDeviceInfoAndDeviceInfoData@CUrbDrManager@@AEAAJPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@PEAPEAXPEAU_DO_DEVINFO_DATA@@@Z; CUrbDrManager::GetDeviceInfoAndDeviceInfoData(_DEV_BROADCAST_DEVICEINTERFACE_W *,void * *,_DO_DEVINFO_DATA *)
0x18000241a  mov     r13, qword ptr [rsp+270h+NeedReboot]
0x18000241f  mov     r14d, eax
0x180002422  test    eax, eax
0x180002424  jns     short loc_18000248B
0x180002426  mov     rcx, cs:WPP_GLOBAL_Control
0x18000242d  lea     r15, WPP_GLOBAL_Control
0x180002434  cmp     rcx, r15
0x180002437  jz      loc_18000289E
0x18000243d  test    byte ptr [rcx+1Ch], 8
0x180002441  jz      loc_18000289E
0x180002447  cmp     byte ptr [rcx+19h], 2
0x18000244b  jb      loc_18000289E
0x180002451  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180002456  mov     edx, 1Bh
0x18000245b  lea     rcx, aCurbdrmanagerG; "CUrbDrManager::GetDeviceInfoAndDeviceIn"...
0x180002462  mov     dword ptr [rsp+270h+var_248], r14d
0x180002467  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18000246e  mov     [rsp+270h+DeviceInfoData], rcx
0x180002473  mov     r9d, eax
0x180002476  mov     rcx, cs:WPP_GLOBAL_Control
0x18000247d  mov     rcx, [rcx+10h]
0x180002481  call    WPP_SF_DsD
0x180002486  jmp     loc_18000289E
0x18000248b  cmp     edi, 8000h
0x180002491  jnz     loc_180002748
0x180002497  mov     rax, cs:WPP_GLOBAL_Control
0x18000249e  mov     r12d, r15d
0x1800024a1  mov     edi, r15d
0x1800024a4  mov     [rsp+270h+NeedReboot], r15d
0x1800024a9  lea     r15, WPP_GLOBAL_Control
0x1800024b0  mov     dword ptr [rsp+270h+var_220], 0Ch
0x1800024b8  mov     esi, 490h
0x1800024bd  mov     r14d, 80070490h
0x1800024c3  cmp     edi, 3
0x1800024c6  jnb     loc_1800026D7
0x1800024cc  lea     rdx, [rsp+270h+var_220+8]
0x1800024d1  mov     rcx, r13
0x1800024d4  test    edi, edi
0x1800024d6  jnz     short loc_18000250C
0x1800024d8  mov     [rsp+270h+var_238], edi
0x1800024dc  lea     rax, [rsp+270h+var_230]
0x1800024e1  mov     qword ptr [rsp+270h+var_240], rax
0x1800024e6  lea     r9, [rsp+270h+var_220+4]
0x1800024eb  mov     dword ptr [rsp+270h+var_248], edi
0x1800024ef  lea     r8, DEVPKEY_Device_Text_Description
0x1800024f6  mov     [rsp+270h+DeviceInfoData], 0
0x1800024ff  call    cs:__imp_DevObjGetDeviceProperty
0x180002505  mov     r14d, dword ptr [rsp+270h+var_220]
0x18000250a  jmp     short loc_180002547
0x18000250c  xor     eax, eax
0x18000250e  mov     r14d, 0Ch
0x180002514  cmp     edi, 1
0x180002517  cmovnz  r14d, eax
0x18000251b  lea     rax, [rsp+270h+var_230]
0x180002520  mov     qword ptr [rsp+270h+var_240], rax
0x180002525  xor     r9d, r9d
0x180002528  mov     dword ptr [rsp+270h+var_248], 0
0x180002530  mov     r8d, r14d
0x180002533  mov     [rsp+270h+DeviceInfoData], 0
0x18000253c  mov     dword ptr [rsp+270h+var_220], r14d
0x180002541  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180002547  test    eax, eax
0x180002549  jnz     loc_1800026B1
0x18000254f  call    cs:__imp_GetLastError
0x180002555  mov     esi, eax
0x180002557  cmp     eax, 7Ah ; 'z'
0x18000255a  jnz     loc_1800026B1
0x180002560  mov     rcx, rbx; Block
0x180002563  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002568  mov     ecx, dword ptr [rsp+270h+var_230]
0x18000256c  mov     eax, 2
0x180002571  shr     rcx, 1
0x180002574  mul     rcx
0x180002577  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000257e  cmovb   rax, rcx
0x180002582  mov     rcx, rax; size
0x180002585  call    MIDL_user_allocate
0x18000258a  mov     rbx, rax
0x18000258d  test    rax, rax
0x180002590  jnz     short loc_1800025F6
0x180002592  mov     esi, 0Eh
0x180002597  mov     r14d, 8007000Eh
0x18000259d  mov     rax, cs:WPP_GLOBAL_Control
0x1800025a4  cmp     rax, r15
0x1800025a7  jz      loc_1800026CC
0x1800025ad  test    byte ptr [rax+1Ch], 1
0x1800025b1  jz      loc_1800026CC
0x1800025b7  cmp     byte ptr [rax+19h], 2
0x1800025bb  jb      loc_1800026CC
0x1800025c1  mov     edi, dword ptr [rsp+270h+var_230]
0x1800025c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800025ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025d1  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x1800025d8  mov     edx, 1Ch
0x1800025dd  mov     dword ptr [rsp+270h+DeviceInfoData], edi
0x1800025e1  mov     r9d, eax
0x1800025e4  mov     rcx, [rcx+10h]
0x1800025e8  call    WPP_SF_Dd
0x1800025ed  mov     edi, [rsp+270h+NeedReboot]
0x1800025f1  jmp     loc_1800026C5
0x1800025f6  mov     r12d, dword ptr [rsp+270h+var_230]
0x1800025fb  lea     rax, [rsp+270h+var_230]
0x180002600  lea     rdx, [rsp+270h+var_220+8]
0x180002605  mov     rcx, r13
0x180002608  test    edi, edi
0x18000260a  jnz     short loc_180002633
0x18000260c  mov     [rsp+270h+var_238], edi
0x180002610  lea     r9, [rsp+270h+var_220+4]
0x180002615  mov     qword ptr [rsp+270h+var_240], rax
0x18000261a  lea     r8, DEVPKEY_Device_Text_Description
0x180002621  mov     dword ptr [rsp+270h+var_248], r12d
0x180002626  mov     [rsp+270h+DeviceInfoData], rbx
0x18000262b  call    cs:__imp_DevObjGetDeviceProperty
0x180002631  jmp     short loc_18000264E
0x180002633  mov     qword ptr [rsp+270h+var_240], rax
0x180002638  xor     r9d, r9d
0x18000263b  mov     dword ptr [rsp+270h+var_248], r12d
0x180002640  mov     r8d, r14d
0x180002643  mov     [rsp+270h+DeviceInfoData], rbx
0x180002648  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18000264e  test    eax, eax
0x180002650  jnz     loc_180002718
0x180002656  call    cs:__imp_GetLastError
0x18000265c  mov     esi, eax
0x18000265e  test    eax, eax
0x180002660  jg      short loc_180002667
0x180002662  mov     r14d, eax
0x180002665  jmp     short loc_180002672
0x180002667  movzx   r14d, ax
0x18000266b  or      r14d, 80070000h
0x180002672  test    r14d, r14d
0x180002675  jns     short loc_1800026C5
0x180002677  mov     rax, cs:WPP_GLOBAL_Control
0x18000267e  cmp     rax, r15
0x180002681  jz      loc_18000289E
0x180002687  test    byte ptr [rax+1Ch], 8
0x18000268b  jz      loc_18000289E
0x180002691  cmp     byte ptr [rax+19h], 2
0x180002695  jb      loc_18000289E
0x18000269b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800026a0  mov     edx, 1Dh
0x1800026a5  lea     rcx, aDevobjopendevi_1; "DevObjOpenDeviceInterface failed"
0x1800026ac  jmp     loc_180002462
0x1800026b1  test    esi, esi
0x1800026b3  jz      short loc_1800026C2
0x1800026b5  mov     esi, 0Dh
0x1800026ba  mov     r14d, 8007000Dh
0x1800026c0  jmp     short loc_1800026C5
0x1800026c2  mov     r14d, esi
0x1800026c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800026cc  inc     edi
0x1800026ce  mov     [rsp+270h+NeedReboot], edi
0x1800026d2  jmp     loc_1800024C3
0x1800026d7  test    r14d, r14d
0x1800026da  jns     short loc_18000270F
0x1800026dc  cmp     rax, r15
0x1800026df  jz      loc_18000289E
0x1800026e5  test    byte ptr [rax+1Ch], 8
0x1800026e9  jz      loc_18000289E
0x1800026ef  cmp     byte ptr [rax+19h], 2
0x1800026f3  jb      loc_18000289E
0x1800026f9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800026fe  mov     edx, 1Eh
0x180002703  lea     rcx, aUnableToGetDev; "Unable to get device's description"
0x18000270a  jmp     loc_180002462
0x18000270f  test    rbx, rbx
0x180002712  jz      loc_18000289E
0x180002718  test    r12d, r12d
0x18000271b  jz      loc_18000289E
0x180002721  xor     eax, eax
0x180002723  mov     ecx, r12d
0x180002726  shr     rcx, 1
0x180002729  mov     [rbx+rcx*2-2], ax
0x18000272e  test    cs:Microsoft_Windows_TerminalServices_ServerUSBDevicesEnableBits, 10h
0x180002735  jz      loc_18000289E
0x18000273b  mov     r8, rbx
0x18000273e  call    McTemplateU0z_EventWriteTransfer
0x180002743  jmp     loc_18000289E
0x180002748  cmp     edi, 8004h
0x18000274e  jnz     loc_18000289E
0x180002754  cmp     [rsi+0A4h], ebx
0x18000275a  jz      loc_18000289E
0x180002760  mov     [rsp+270h+NeedReboot], r15d
0x180002765  call    IsDiUninstallDevicePresent
0x18000276a  test    al, al
0x18000276c  jz      loc_18000285B
0x180002772  mov     r9d, 0C8h
0x180002778  mov     [rsp+270h+DeviceInfoData], r15
0x18000277d  lea     r8, [rbp+170h+DeviceInstanceId]
0x180002781  mov     rcx, r13
0x180002784  lea     rdx, [rsp+270h+var_220+8]
0x180002789  call    cs:__imp_DevObjGetDeviceInstanceId
0x18000278f  test    eax, eax
0x180002791  jz      loc_18000285B
0x180002797  xor     edx, edx; hwndParent
0x180002799  xor     ecx, ecx; ClassGuid
0x18000279b  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800027a1  mov     rdi, rax
0x1800027a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800027a8  jz      loc_18000285B
0x1800027ae  xorps   xmm0, xmm0
0x1800027b1  lea     rax, [rbp+170h+var_1E8]
0x1800027b5  movups  xmmword ptr [rbp+170h+var_1E8.cbSize], xmm0
0x1800027b9  xor     r9d, r9d; OpenFlags
0x1800027bc  mov     [rbp+170h+var_1E8.cbSize], 20h ; ' '
0x1800027c3  xor     r8d, r8d; hwndParent
0x1800027c6  mov     [rsp+270h+DeviceInfoData], rax; DeviceInfoData
0x1800027cb  lea     rdx, [rbp+170h+DeviceInstanceId]; DeviceInstanceId
0x1800027cf  mov     rcx, rdi; DeviceInfoSet
0x1800027d2  mov     esi, r15d
0x1800027d5  movups  xmmword ptr [rbp+170h+var_1E8.ClassGuid.Data4+4], xmm0
0x1800027d9  call    cs:__imp_SetupDiOpenDeviceInfoW
0x1800027df  test    eax, eax
0x1800027e1  jnz     short loc_180002801
0x1800027e3  lea     rax, [rsp+270h+NeedReboot]
0x1800027e8  xor     r9d, r9d; Flags
0x1800027eb  lea     r8, [rbp+170h+var_1E8]; DeviceInfoData
0x1800027ef  mov     [rsp+270h+DeviceInfoData], rax; NeedReboot
0x1800027f4  mov     rdx, rdi; DeviceInfoSet
0x1800027f7  xor     ecx, ecx; hwndParent
0x1800027f9  call    cs:__imp_DiUninstallDevice
0x1800027ff  mov     esi, eax
0x180002801  mov     rcx, rdi; DeviceInfoSet
0x180002804  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18000280a  test    esi, esi
0x18000280c  jz      short loc_18000285B
0x18000280e  mov     rax, cs:WPP_GLOBAL_Control
0x180002815  lea     r15, WPP_GLOBAL_Control
0x18000281c  cmp     rax, r15
0x18000281f  jz      short loc_18000289E
0x180002821  test    byte ptr [rax+1Ch], 1
0x180002825  jz      short loc_18000289E
0x180002827  cmp     byte ptr [rax+19h], 4
0x18000282b  jb      short loc_18000289E
0x18000282d  mov     edi, [rsp+270h+NeedReboot]
0x180002831  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180002836  mov     rcx, cs:WPP_GLOBAL_Control
0x18000283d  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180002844  mov     edx, 1Fh
0x180002849  mov     dword ptr [rsp+270h+DeviceInfoData], edi
0x18000284d  mov     r9d, eax
0x180002850  mov     rcx, [rcx+10h]
0x180002854  call    WPP_SF_Dd
0x180002859  jmp     short loc_18000289E
0x18000285b  mov     rax, cs:WPP_GLOBAL_Control
0x180002862  lea     r15, WPP_GLOBAL_Control
0x180002869  cmp     rax, r15
0x18000286c  jz      short loc_18000289E
0x18000286e  test    byte ptr [rax+1Ch], 1
0x180002872  jz      short loc_18000289E
0x180002874  cmp     byte ptr [rax+19h], 2
0x180002878  jb      short loc_18000289E
0x18000287a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000287f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002886  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18000288d  mov     edx, 20h ; ' '
0x180002892  mov     r9d, eax
0x180002895  mov     rcx, [rcx+10h]
0x180002899  call    WPP_SF_D
0x18000289e  mov     r14, [rsp+270h+arg_18]
0x1800028a6  mov     r12, [rsp+270h+arg_0]
0x1800028ae  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800028b2  jz      short loc_1800028BD
0x1800028b4  mov     rcx, r13
0x1800028b7  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800028bd  mov     r13, [rsp+270h+arg_8]
0x1800028c5  mov     rcx, rbx; Block
  ... truncated ...
```
