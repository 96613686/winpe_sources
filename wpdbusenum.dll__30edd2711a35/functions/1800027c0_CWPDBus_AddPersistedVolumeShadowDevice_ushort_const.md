# CWPDBus::AddPersistedVolumeShadowDevice(ushort const *)

- ea: `0x1800027c0`
- end: `0x180002a65`
- name: `?AddPersistedVolumeShadowDevice@CWPDBus@@QEAAJPEBG@Z`
- size: `677`
- prototype: `__int64 __fastcall(CWPDBus *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800018c0`
- `0x18000e260`

## callees

- `0x1800027c0`
- `0x180002a70`
- `0x180007f28`
- `0x1800097d0`
- `0x18000a192`
- `0x18000e080`
- `0x18000e8e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000295e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000295e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002898`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002898`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000288b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000288b`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x1800029c3`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x1800029c3`

## pseudocode

```c
__int64 __fastcall CWPDBus::AddPersistedVolumeShadowDevice(CWPDBus *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  CONFIGRET Device_Interface_PropertyW; // eax
  signed int v6; // eax
  unsigned int v7; // edi
  CPnPNotification *v8; // rcx
  int v9; // edx
  wchar_t *v10; // rax
  int v11; // eax
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-C0h] BYREF
  ULONG PropertyBufferSize; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+60h] [rbp-A0h]
  __int128 v18; // [rsp+70h] [rbp-90h]
  __int128 v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+90h] [rbp-70h]
  DEVPROPKEY v21; // [rsp+A0h] [rbp-60h] BYREF
  int v22; // [rsp+B4h] [rbp-4Ch]
  __int64 v23; // [rsp+B8h] [rbp-48h]
  int v24; // [rsp+C0h] [rbp-40h]
  int v25; // [rsp+C4h] [rbp-3Ch]
  const unsigned __int16 *v26; // [rsp+C8h] [rbp-38h]
  wchar_t PropertyBuffer[200]; // [rsp+D0h] [rbp-30h] BYREF

  v21 = DEVPKEY_WpdFs_VolumePath;
  v22 = 0;
  v3 = -1;
  v23 = 0;
  v24 = 18;
  while ( a2[++v3] != 0 )
    ;
  v26 = a2;
  v25 = 2 * v3 + 2;
  memset_0(PropertyBuffer, 0, sizeof(PropertyBuffer));
  v15 = 0;
  v20 = 0;
  PropertyBufferSize = 400;
  PropertyType = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                 a2,
                                 &DEVPKEY_Device_InstanceId,
                                 &PropertyType,
                                 (PBYTE)PropertyBuffer,
                                 &PropertyBufferSize,
                                 0);
  v6 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( (v7 & 0x80000000) != 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v9 = 10;
    goto LABEL_13;
  }
  if ( PropertyType != 18 )
  {
    v7 = -2147418113;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v9 = 11;
LABEL_13:
    WPP_SF_Sd(*((_QWORD *)v8 + 2), v9, (unsigned int)WPP_ed24c69f74d33f0c5f9b1d214265ee94_Traceguids, (_DWORD)a2, v7);
    v8 = WPP_GLOBAL_Control;
LABEL_14:
    if ( v8 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
      WPP_SF_Sd(*((_QWORD *)v8 + 2), 28, (unsigned int)&WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids, (_DWORD)a2, v7);
    return v7;
  }
  v10 = wcsrchr(PropertyBuffer, 0x5Cu);
  LODWORD(v16) = 72;
  DWORD2(v18) = 10;
  *((_QWORD *)&v16 + 1) = v10 + 1;
  *((_QWORD *)&v17 + 1) = L"wpdbusenum\\fs";
  v11 = SwDeviceCreate(L"WPDBUSENUM", PropertyBuffer, &v16, 1, &v21, CWPDBus::SwDeviceCallback, 0, &v15);
  v7 = v11;
  if ( v11 == -2147024713 )
  {
    Service_Release();
    return 0;
  }
  else if ( v11 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids, v15);
    }
  }
  else if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids,
      (unsigned int)v11);
  }
  return v7;
}

```

## disassembly

```asm
0x1800027c0  push    rbp
0x1800027c2  push    rbx
0x1800027c3  push    rsi
0x1800027c4  push    rdi
0x1800027c5  lea     rbp, [rsp-178h]
0x1800027cd  sub     rsp, 278h
0x1800027d4  mov     rax, cs:__security_cookie
0x1800027db  xor     rax, rsp
0x1800027de  mov     [rbp+190h+var_30], rax
0x1800027e5  mov     eax, cs:DEVPKEY_WpdFs_VolumePath.pid
0x1800027eb  xor     esi, esi
0x1800027ed  movups  xmm0, xmmword ptr cs:DEVPKEY_WpdFs_VolumePath.fmtid.Data1
0x1800027f4  mov     [rbp+190h+var_1E0], eax
0x1800027f7  mov     rbx, rdx
0x1800027fa  mov     [rbp+190h+var_1DC], esi
0x1800027fd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002804  movups  [rbp+190h+var_1F0], xmm0
0x180002808  mov     [rbp+190h+var_1D8], rsi
0x18000280c  mov     [rbp+190h+var_1D0], 12h
0x180002813  cmp     [rdx+rax*2+2], si
0x180002818  lea     rax, [rax+1]
0x18000281c  jnz     short loc_180002813
0x18000281e  lea     eax, ds:2[rax*2]
0x180002825  mov     [rbp+190h+var_1C8], rbx
0x180002829  xor     edx, edx; Val
0x18000282b  mov     [rbp+190h+var_1CC], eax
0x18000282e  mov     r8d, 190h; Size
0x180002834  lea     rcx, [rbp+190h+PropertyBuffer]; void *
0x180002838  call    memset_0
0x18000283d  xorps   xmm0, xmm0
0x180002840  mov     [rsp+290h+ulFlags], esi; ulFlags
0x180002844  xor     eax, eax
0x180002846  mov     [rsp+290h+var_248], rsi
0x18000284b  mov     [rbp+190h+var_200], rax
0x18000284f  lea     r9, [rbp+190h+PropertyBuffer]; PropertyBuffer
0x180002853  lea     rax, [rsp+290h+var_24C]
0x180002858  mov     [rsp+290h+var_24C], 190h
0x180002860  lea     r8, [rsp+290h+PropertyType]; PropertyType
0x180002865  mov     [rsp+290h+PropertyBufferSize], rax; PropertyBufferSize
0x18000286a  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x180002871  mov     [rsp+290h+PropertyType], esi
0x180002875  mov     rcx, rbx; pszDeviceInterface
0x180002878  movups  [rsp+290h+var_240], xmm0
0x18000287d  movups  [rsp+290h+var_230], xmm0
0x180002882  movups  [rsp+290h+var_220], xmm0
0x180002887  movups  [rbp+190h+var_210], xmm0
0x18000288b  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180002891  mov     ecx, eax; CmReturnCode
0x180002893  mov     edx, 0Dh; DefaultErr
0x180002898  call    cs:__imp_CM_MapCrToWin32Err
0x18000289e  mov     edi, eax
0x1800028a0  test    eax, eax
0x1800028a2  jle     short loc_1800028AD
0x1800028a4  movzx   edi, ax
0x1800028a7  or      edi, 80070000h
0x1800028ad  test    edi, edi
0x1800028af  jns     short loc_1800028D5
0x1800028b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028b8  lea     rsi, WPP_GLOBAL_Control
0x1800028bf  cmp     rcx, rsi
0x1800028c2  jz      loc_180002A48
0x1800028c8  test    byte ptr [rcx+1Ch], 2
0x1800028cc  jz      short loc_180002921
0x1800028ce  mov     edx, 0Ah
0x1800028d3  jmp     short loc_180002903
0x1800028d5  cmp     [rsp+290h+PropertyType], 12h
0x1800028da  jz      short loc_180002955
0x1800028dc  mov     edi, 8000FFFFh
0x1800028e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028e8  lea     rsi, WPP_GLOBAL_Control
0x1800028ef  cmp     rcx, rsi
0x1800028f2  jz      loc_180002A48
0x1800028f8  test    byte ptr [rcx+1Ch], 2
0x1800028fc  jz      short loc_180002921
0x1800028fe  mov     edx, 0Bh
0x180002903  mov     rcx, [rcx+10h]
0x180002907  lea     r8, WPP_ed24c69f74d33f0c5f9b1d214265ee94_Traceguids
0x18000290e  mov     r9, rbx
0x180002911  mov     dword ptr [rsp+290h+PropertyBufferSize], edi
0x180002915  call    WPP_SF_Sd
0x18000291a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002921  cmp     rcx, rsi
0x180002924  jz      loc_180002A48
0x18000292a  test    byte ptr [rcx+1Ch], 2
0x18000292e  jz      loc_180002A48
0x180002934  mov     rcx, [rcx+10h]
0x180002938  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x18000293f  mov     edx, 1Ch
0x180002944  mov     dword ptr [rsp+290h+PropertyBufferSize], edi
0x180002948  mov     r9, rbx
0x18000294b  call    WPP_SF_Sd
0x180002950  jmp     loc_180002A48
0x180002955  mov     edx, 5Ch ; '\'; Ch
0x18000295a  lea     rcx, [rbp+190h+PropertyBuffer]; Str
0x18000295e  call    cs:__imp_wcsrchr
0x180002964  mov     r9d, 1
0x18000296a  mov     dword ptr [rsp+290h+var_240], 48h ; 'H'
0x180002972  add     rax, 2
0x180002976  mov     dword ptr [rsp+290h+var_220+8], 0Ah
0x18000297e  mov     qword ptr [rsp+290h+var_240+8], rax
0x180002983  lea     r8, [rsp+290h+var_240]
0x180002988  lea     rax, aWpdbusenumFs; "wpdbusenum\\fs"
0x18000298f  mov     qword ptr [rsp+290h+var_230+8], rax
0x180002994  lea     rdx, [rbp+190h+PropertyBuffer]
0x180002998  lea     rax, [rsp+290h+var_248]
0x18000299d  mov     [rsp+290h+var_258], rax
0x1800029a2  lea     rcx, aWpdbusenum; "WPDBUSENUM"
0x1800029a9  lea     rax, ?SwDeviceCallback@CWPDBus@@KAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; CWPDBus::SwDeviceCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x1800029b0  mov     [rsp+290h+var_260], rsi
0x1800029b5  mov     qword ptr [rsp+290h+ulFlags], rax
0x1800029ba  lea     rax, [rbp+190h+var_1F0]
0x1800029be  mov     [rsp+290h+PropertyBufferSize], rax
0x1800029c3  call    cs:__imp_SwDeviceCreate
0x1800029c9  mov     edi, eax
0x1800029cb  cmp     eax, 800700B7h
0x1800029d0  jnz     short loc_1800029DB
0x1800029d2  call    ?Service_Release@@YAJXZ; Service_Release(void)
0x1800029d7  mov     edi, esi
0x1800029d9  jmp     short loc_180002A48
0x1800029db  test    eax, eax
0x1800029dd  jns     short loc_180002A12
0x1800029df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029e6  lea     rsi, WPP_GLOBAL_Control
0x1800029ed  cmp     rcx, rsi
0x1800029f0  jz      short loc_180002A48
0x1800029f2  test    byte ptr [rcx+1Ch], 2
0x1800029f6  jz      short loc_180002A48
0x1800029f8  mov     rcx, [rcx+10h]
0x1800029fc  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x180002a03  mov     edx, 1Dh
0x180002a08  mov     r9d, eax
0x180002a0b  call    WPP_SF_d
0x180002a10  jmp     short loc_180002A48
0x180002a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a19  lea     rsi, WPP_GLOBAL_Control
0x180002a20  cmp     rcx, rsi
0x180002a23  jz      short loc_180002A48
0x180002a25  test    dword ptr [rcx+1Ch], 100h
0x180002a2c  jz      short loc_180002A48
0x180002a2e  mov     r9, [rsp+290h+var_248]
0x180002a33  lea     r8, WPP_3419bf14048c3188c20a09c1c5c9982b_Traceguids
0x180002a3a  mov     rcx, [rcx+10h]
0x180002a3e  mov     edx, 1Eh
0x180002a43  call    WPP_SF_q
0x180002a48  mov     eax, edi
0x180002a4a  mov     rcx, [rbp+190h+var_30]
0x180002a51  xor     rcx, rsp; StackCookie
0x180002a54  call    __security_check_cookie
0x180002a59  add     rsp, 278h
0x180002a60  pop     rdi
0x180002a61  pop     rsi
0x180002a62  pop     rbx
0x180002a63  pop     rbp
0x180002a64  retn
```
