# RDCameraServiceExtension::OnRemoteConnect(ulong)

- ea: `0x180031a98`
- end: `0x180031d1b`
- name: `?OnRemoteConnect@RDCameraServiceExtension@@AEAAXK@Z`
- size: `643`
- prototype: `void __fastcall(RDCameraServiceExtension *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004b90`

## callees

- `0x180007ce0`
- `0x180009590`
- `0x18000a4f0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f75c`
- `0x18000f79c`
- `0x180031508`
- `0x180031a98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031afb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031afb`

## string_xrefs

- `0x180031aed`: `Software\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
void __fastcall RDCameraServiceExtension::OnRemoteConnect(RDCameraServiceExtension *this, unsigned int a2)
{
  LSTATUS ValueW; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  LSTATUS v8; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  char *v13; // rbx
  int v14; // eax
  char v15; // di
  int v16; // eax
  int v17; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v19; // [rsp+78h] [rbp+28h] BYREF
  int v20; // [rsp+80h] [rbp+30h] BYREF
  DWORD v21; // [rsp+88h] [rbp+38h] BYREF

  v19 = a2;
  v18 = 0;
  v20 = 0;
  v21 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
             L"fDisableCameraRedir",
             0x10u,
             0,
             &v20,
             &v21);
  v8 = ValueW;
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v6 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          16,
          WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids,
          CurrentThreadActivityIdPrefix,
          v8);
      }
      goto LABEL_31;
    }
    v10 = 0;
    v20 = 0;
  }
  else
  {
    v10 = v20;
  }
  if ( v10 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 4u )
    {
      goto LABEL_31;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 17;
    goto LABEL_30;
  }
  Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(&v18, v5, v6, v7);
  v13 = (char *)this + 32;
  if ( (unsigned int)SmartArray<RDCameraDeviceManager,unsigned long>::GetAt((char *)this + 32, a2, &v18) && v18 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_31;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 18;
    goto LABEL_30;
  }
  v17 = *((_DWORD *)this + 14);
  *((_DWORD *)this + 14) = v17 + 1;
  Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(&v18, v5, v6, v7);
  v14 = Microsoft::WRL::Details::MakeAndInitialize<RDCameraDeviceManager,RDCameraDeviceManager,HINSTANCE__ * &,utl::shared_ptr<ITsBus> &,unsigned long &,unsigned long,_TP_CALLBACK_ENVIRON_V3 &>(
          (unsigned int)&v18,
          (int)this + 8,
          (int)this + 16,
          (unsigned int)&v19,
          (__int64)&v17,
          (__int64)this + 64);
  v15 = v14;
  if ( v14 >= 0 )
  {
    if ( (unsigned int)SmartArray<RDCameraDeviceManager,unsigned long>::AddAt(v13, a2, v18)
      || *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_31;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 20;
LABEL_30:
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v12,
      WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids,
      v11);
    goto LABEL_31;
  }
  v5 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      19,
      (unsigned int)WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids,
      v16,
      (__int64)"MakeAndInitialize<RDCameraDeviceManager> failed",
      v15);
  }
LABEL_31:
  Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(&v18, v5, v6, v7);
}

```

## disassembly

```asm
0x180031a98  mov     r11, rsp
0x180031a9b  mov     [r11+8], rbx
0x180031a9f  mov     [rsp-18h+arg_8], edx
0x180031aa3  push    rbp
0x180031aa4  push    rsi
0x180031aa5  push    rdi
0x180031aa6  mov     rbp, rsp
0x180031aa9  sub     rsp, 50h
0x180031aad  lea     rax, [rbp+arg_18]
0x180031ab1  mov     [rbp+var_8], 0
0x180031ab9  mov     [r11-38h], rax
0x180031abd  lea     r8, Value; "fDisableCameraRedir"
0x180031ac4  lea     rax, [rbp+arg_10]
0x180031ac8  mov     [rbp+arg_10], 0
0x180031acf  mov     esi, edx
0x180031ad1  mov     [r11-40h], rax
0x180031ad5  mov     rdi, rcx
0x180031ad8  mov     qword ptr [r11-48h], 0
0x180031ae0  mov     r9d, 10h; dwFlags
0x180031ae6  mov     [rbp+arg_18], 4
0x180031aed  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180031af4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180031afb  call    cs:__imp_RegGetValueW
0x180031b01  mov     ebx, eax
0x180031b03  test    eax, eax
0x180031b05  jz      short loc_180031B6D
0x180031b07  cmp     eax, 2
0x180031b0a  jz      short loc_180031B66
0x180031b0c  mov     r8, cs:WPP_GLOBAL_Control
0x180031b13  lea     rcx, WPP_GLOBAL_Control
0x180031b1a  cmp     r8, rcx
0x180031b1d  jz      loc_180031D05
0x180031b23  test    byte ptr [r8+1Ch], 1
0x180031b28  jz      loc_180031D05
0x180031b2e  cmp     byte ptr [r8+19h], 2
0x180031b33  jb      loc_180031D05
0x180031b39  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b45  lea     r8, WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids
0x180031b4c  mov     edx, 10h
0x180031b51  mov     dword ptr [rsp+50h+var_30], ebx
0x180031b55  mov     r9d, eax
0x180031b58  mov     rcx, [rcx+10h]
0x180031b5c  call    WPP_SF_Dd
0x180031b61  jmp     loc_180031D05
0x180031b66  xor     eax, eax
0x180031b68  mov     [rbp+arg_10], eax
0x180031b6b  jmp     short loc_180031B70
0x180031b6d  mov     eax, [rbp+arg_10]
0x180031b70  test    eax, eax
0x180031b72  jz      short loc_180031BAE
0x180031b74  mov     rax, cs:WPP_GLOBAL_Control
0x180031b7b  lea     rcx, WPP_GLOBAL_Control
0x180031b82  cmp     rax, rcx
0x180031b85  jz      loc_180031D05
0x180031b8b  test    byte ptr [rax+1Ch], 1
0x180031b8f  jz      loc_180031D05
0x180031b95  cmp     byte ptr [rax+19h], 4
0x180031b99  jb      loc_180031D05
0x180031b9f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031ba4  mov     edx, 11h
0x180031ba9  jmp     loc_180031CEB
0x180031bae  lea     rcx, [rbp+var_8]
0x180031bb2  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x180031bb7  lea     rbx, [rdi+20h]
0x180031bbb  mov     edx, esi
0x180031bbd  mov     rcx, rbx
0x180031bc0  lea     r8, [rbp+var_8]
0x180031bc4  call    ?GetAt@?$SmartArray@VRDCameraDeviceManager@@K@@QEAAHKPEAPEAVRDCameraDeviceManager@@@Z; SmartArray<RDCameraDeviceManager,ulong>::GetAt(ulong,RDCameraDeviceManager * *)
0x180031bc9  test    eax, eax
0x180031bcb  jz      short loc_180031C0E
0x180031bcd  cmp     [rbp+var_8], 0
0x180031bd2  jz      short loc_180031C0E
0x180031bd4  mov     rax, cs:WPP_GLOBAL_Control
0x180031bdb  lea     rcx, WPP_GLOBAL_Control
0x180031be2  cmp     rax, rcx
0x180031be5  jz      loc_180031D05
0x180031beb  test    byte ptr [rax+1Ch], 1
0x180031bef  jz      loc_180031D05
0x180031bf5  cmp     byte ptr [rax+19h], 2
0x180031bf9  jb      loc_180031D05
0x180031bff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031c04  mov     edx, 12h
0x180031c09  jmp     loc_180031CEB
0x180031c0e  mov     eax, [rdi+38h]
0x180031c11  lea     rcx, [rbp+var_8]
0x180031c15  mov     [rbp+var_10], eax
0x180031c18  inc     eax
0x180031c1a  mov     [rdi+38h], eax
0x180031c1d  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x180031c22  lea     rax, [rdi+40h]
0x180031c26  mov     [rsp+50h+var_28], rax
0x180031c2b  lea     r8, [rdi+10h]
0x180031c2f  lea     rax, [rbp+var_10]
0x180031c33  lea     rdx, [rdi+8]
0x180031c37  mov     [rsp+50h+var_30], rax
0x180031c3c  lea     r9, [rbp+arg_8]
0x180031c40  lea     rcx, [rbp+var_8]
0x180031c44  call    ??$MakeAndInitialize@VRDCameraDeviceManager@@V1@AEAPEAUHINSTANCE__@@AEAV?$shared_ptr@VITsBus@@@utl@@AEAKKAEAU_TP_CALLBACK_ENVIRON_V3@@@Details@WRL@Microsoft@@YAJPEAPEAVRDCameraDeviceManager@@AEAPEAUHINSTANCE__@@AEAV?$shared_ptr@VITsBus@@@utl@@AEAK$$QEAKAEAU_TP_CALLBACK_ENVIRON_V3@@@Z; Microsoft::WRL::Details::MakeAndInitialize<RDCameraDeviceManager,RDCameraDeviceManager,HINSTANCE__ * &,utl::shared_ptr<ITsBus> &,ulong &,ulong,_TP_CALLBACK_ENVIRON_V3 &>(RDCameraDeviceManager * *,HINSTANCE__ * &,utl::shared_ptr<ITsBus> &,ulong &,ulong &&,_TP_CALLBACK_ENVIRON_V3 &)
0x180031c49  mov     edi, eax
0x180031c4b  test    eax, eax
0x180031c4d  jns     short loc_180031CB0
0x180031c4f  mov     rdx, cs:WPP_GLOBAL_Control
0x180031c56  lea     rcx, WPP_GLOBAL_Control
0x180031c5d  cmp     rdx, rcx
0x180031c60  jz      loc_180031D05
0x180031c66  test    byte ptr [rdx+1Ch], 8
0x180031c6a  jz      loc_180031D05
0x180031c70  cmp     byte ptr [rdx+19h], 2
0x180031c74  jb      loc_180031D05
0x180031c7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031c7f  lea     rcx, aMakeandinitial; "MakeAndInitialize<RDCameraDeviceManager"...
0x180031c86  mov     dword ptr [rsp+50h+var_28], edi
0x180031c8a  mov     [rsp+50h+var_30], rcx
0x180031c8f  lea     r8, WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids
0x180031c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c9d  mov     edx, 13h
0x180031ca2  mov     r9d, eax
0x180031ca5  mov     rcx, [rcx+10h]
0x180031ca9  call    WPP_SF_DsD
0x180031cae  jmp     short loc_180031D05
0x180031cb0  mov     r8, [rbp+var_8]
0x180031cb4  mov     edx, esi
0x180031cb6  mov     rcx, rbx
0x180031cb9  call    ?AddAt@?$SmartArray@VRDCameraDeviceManager@@K@@QEAAHKPEAVRDCameraDeviceManager@@@Z; SmartArray<RDCameraDeviceManager,ulong>::AddAt(ulong,RDCameraDeviceManager *)
0x180031cbe  test    eax, eax
0x180031cc0  jnz     short loc_180031D05
0x180031cc2  mov     rax, cs:WPP_GLOBAL_Control
0x180031cc9  lea     rcx, WPP_GLOBAL_Control
0x180031cd0  cmp     rax, rcx
0x180031cd3  jz      short loc_180031D05
0x180031cd5  test    byte ptr [rax+1Ch], 1
0x180031cd9  jz      short loc_180031D05
0x180031cdb  cmp     byte ptr [rax+19h], 2
0x180031cdf  jb      short loc_180031D05
0x180031ce1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031ce6  mov     edx, 14h
0x180031ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180031cf2  lea     r8, WPP_2cb8aca624b93589adfa3ffa58add1bb_Traceguids
0x180031cf9  mov     r9d, eax
0x180031cfc  mov     rcx, [rcx+10h]
0x180031d00  call    WPP_SF_D
0x180031d05  lea     rcx, [rbp+var_8]
0x180031d09  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x180031d0e  mov     rbx, [rsp+50h+arg_0]
0x180031d13  add     rsp, 50h
0x180031d17  pop     rdi
0x180031d18  pop     rsi
0x180031d19  pop     rbp
0x180031d1a  retn
```
