# RaidUnitGetDeviceParameters

- ea: `0x1401c0fd0`
- end: `0x1401c13c0`
- name: `RaidUnitGetDeviceParameters`
- size: `1008`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1401c27c8`

## callees

- `0x1400290b0`
- `0x140070754`
- `0x140094d84`
- `0x14009c320`
- `0x14009ce20`
- `0x14014b400`
- `0x14014b800`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1401c10fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401c10fb`
- `ntoskrnl!ZwClose` at `0x1401c1372`
- `ntoskrnl!ZwClose` at `0x1401c1388`
- `ntoskrnl!ZwClose` at `0x1401c1372`
- `ntoskrnl!ZwClose` at `0x1401c1388`
- `ntoskrnl!ZwOpenKey` at `0x1401c1142`
- `ntoskrnl!ZwOpenKey` at `0x1401c1142`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401c129f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401c129f`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1401c10db`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1401c10db`

## pseudocode

```c
int __fastcall RaidUnitGetDeviceParameters(__int64 a1)
{
  __int64 v2; // rcx
  _DWORD *v3; // rsi
  int v4; // eax
  _DWORD *v5; // r14
  _DWORD *v6; // r15
  int v7; // eax
  struct _DEVICE_OBJECT *v8; // rcx
  PDEVICE_OBJECT *Pool; // rax
  PDEVICE_OBJECT *v10; // rdi
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  void *DeviceRegKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[8]; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+98h] [rbp-68h]
  const wchar_t *v18; // [rsp+A0h] [rbp-60h]
  __int64 v19; // [rsp+A8h] [rbp-58h]
  int v20; // [rsp+B0h] [rbp-50h]
  __int64 v21; // [rsp+B8h] [rbp-48h]
  int v22; // [rsp+C0h] [rbp-40h]
  int v23; // [rsp+D0h] [rbp-30h]
  const wchar_t *v24; // [rsp+D8h] [rbp-28h]
  __int64 v25; // [rsp+E0h] [rbp-20h]
  int v26; // [rsp+E8h] [rbp-18h]
  __int64 v27; // [rsp+F0h] [rbp-10h]
  int v28; // [rsp+F8h] [rbp-8h]
  int v29; // [rsp+108h] [rbp+8h]
  const WCHAR *v30; // [rsp+110h] [rbp+10h]
  __int64 v31; // [rsp+118h] [rbp+18h]
  int v32; // [rsp+120h] [rbp+20h]
  __int64 v33; // [rsp+128h] [rbp+28h]
  int v34; // [rsp+130h] [rbp+30h]
  int v35; // [rsp+140h] [rbp+40h]
  const wchar_t *v36; // [rsp+148h] [rbp+48h]
  __int64 v37; // [rsp+150h] [rbp+50h]
  int v38; // [rsp+158h] [rbp+58h]
  __int64 v39; // [rsp+160h] [rbp+60h]
  int v40; // [rsp+168h] [rbp+68h]
  int v41; // [rsp+178h] [rbp+78h]
  const wchar_t *v42; // [rsp+180h] [rbp+80h]
  __int64 v43; // [rsp+188h] [rbp+88h]
  int v44; // [rsp+190h] [rbp+90h]
  __int64 v45; // [rsp+198h] [rbp+98h]
  int v46; // [rsp+1A0h] [rbp+A0h]
  int v47; // [rsp+1B0h] [rbp+B0h]
  const wchar_t *v48; // [rsp+1B8h] [rbp+B8h]
  __int64 v49; // [rsp+1C0h] [rbp+C0h]
  int v50; // [rsp+1C8h] [rbp+C8h]
  __int64 v51; // [rsp+1D0h] [rbp+D0h]
  int v52; // [rsp+1D8h] [rbp+D8h]

  DeviceRegKey = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyHandle = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, a1);
  }
  v2 = *(_QWORD *)(a1 + 24);
  v3 = (_DWORD *)(a1 + 1928);
  *(_DWORD *)(a1 + 1928) = 20;
  v4 = *(_DWORD *)(v2 + 5732);
  if ( v4 )
    *v3 = v4;
  v5 = (_DWORD *)(a1 + 1932);
  v6 = (_DWORD *)(a1 + 1936);
  *(_DWORD *)(a1 + 1932) = 25;
  *(_DWORD *)(a1 + 1936) = 250;
  v7 = *(_DWORD *)(v2 + 5736);
  if ( v7 )
    *v6 = v7;
  v8 = *(struct _DEVICE_OBJECT **)(a1 + 8);
  *(_DWORD *)(a1 + 1940) = 0;
  *(_DWORD *)(a1 + 1948) = -1;
  LODWORD(Pool) = IoOpenDeviceRegistryKey(v8, 1u, 0x20019u, &DeviceRegKey);
  if ( (int)Pool >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Storport");
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(Pool) = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( (int)Pool >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, a1);
      }
      memset_0(v16, 0, 0x188u);
      v19 = a1 + 1932;
      v20 = 67108868;
      v17 = 288;
      v22 = 4;
      v18 = L"QueueFullWaitIoPercentage";
      v23 = 288;
      v24 = L"BusyPauseTime";
      v30 = L"BusyRetryCount";
      v36 = L"EnableLogoETW";
      v42 = L"DisableIdlePowerManagement";
      v43 = a1 + 1944;
      v45 = a1 + 1944;
      v26 = 67108868;
      v28 = 4;
      v29 = 288;
      v32 = 67108868;
      v34 = 4;
      v35 = 288;
      v38 = 67108868;
      v40 = 4;
      v41 = 288;
      v44 = 67108868;
      v46 = 4;
      v47 = 288;
      v50 = 67108868;
      v52 = 4;
      v48 = L"MinimumIdleTimeoutInMS";
      v21 = a1 + 1932;
      v25 = a1 + 1936;
      v27 = a1 + 1936;
      v31 = a1 + 1928;
      v33 = a1 + 1928;
      v37 = a1 + 1940;
      v39 = a1 + 1940;
      v49 = a1 + 1948;
      v51 = a1 + 1948;
      RtlQueryRegistryValuesEx(0x40000000, KeyHandle, v16, 0, 0);
      if ( *v5 > 0x64u )
        *v5 = 25;
      if ( EnableRegistryWatch && !*(_QWORD *)(a1 + 3576) )
      {
        Pool = (PDEVICE_OBJECT *)RaidAllocatePool(64, 192, 1465016658, 0);
        v10 = Pool;
        if ( !Pool )
          goto LABEL_25;
        *Pool = (PDEVICE_OBJECT)a1;
        Pool[1] = (PDEVICE_OBJECT)RaidUnitUpdateDynamicRegistrySettings;
        StorpInitRegistryWatch(KeyHandle);
        StorpWatchForRegistryChanges(v10);
        *(_QWORD *)(a1 + 3576) = v10;
        KeyHandle = 0;
      }
      Pool = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        LODWORD(Pool) = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( ((unsigned __int8)Pool & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          LODWORD(Pool) = WPP_SF_qddd(
                            WPP_GLOBAL_Control->AttachedDevice,
                            70,
                            WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
                            a1,
                            *v3,
                            *v6,
                            *v5);
      }
    }
  }
LABEL_25:
  if ( DeviceRegKey )
    LODWORD(Pool) = ZwClose(DeviceRegKey);
  if ( KeyHandle )
    LODWORD(Pool) = ZwClose(KeyHandle);
  return (int)Pool;
}

```

## disassembly

```asm
0x1401c0fd0  mov     [rsp-8+arg_8], rbx
0x1401c0fd5  mov     [rsp-8+arg_10], rsi
0x1401c0fda  push    rbp
0x1401c0fdb  push    rdi
0x1401c0fdc  push    r12
0x1401c0fde  push    r14
0x1401c0fe0  push    r15
0x1401c0fe2  lea     rbp, [rsp-130h]
0x1401c0fea  sub     rsp, 230h
0x1401c0ff1  mov     rax, cs:__security_cookie
0x1401c0ff8  xor     rax, rsp
0x1401c0ffb  mov     [rbp+150h+var_30], rax
0x1401c1002  xorps   xmm0, xmm0
0x1401c1005  mov     [rsp+250h+DeviceRegKey], 0
0x1401c100e  movups  xmmword ptr [rsp+250h+ObjectAttributes.Length], xmm0
0x1401c1013  mov     rbx, rcx
0x1401c1016  mov     [rsp+250h+KeyHandle], 0
0x1401c101f  movups  xmmword ptr [rsp+250h+ObjectAttributes.ObjectName], xmm0
0x1401c1024  movups  xmmword ptr [rbp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401c1028  movups  xmmword ptr [rsp+250h+DestinationString.Length], xmm0
0x1401c102d  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c1034  lea     rax, WPP_GLOBAL_Control
0x1401c103b  cmp     rcx, rax
0x1401c103e  jz      short loc_1401C1065
0x1401c1040  mov     eax, [rcx+2Ch]
0x1401c1043  test    al, 2
0x1401c1045  jz      short loc_1401C1065
0x1401c1047  cmp     byte ptr [rcx+29h], 4
0x1401c104b  jb      short loc_1401C1065
0x1401c104d  mov     rcx, [rcx+18h]
0x1401c1051  lea     r8, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids
0x1401c1058  mov     edx, 44h ; 'D'
0x1401c105d  mov     r9, rbx
0x1401c1060  call    WPP_SF_q
0x1401c1065  mov     rcx, [rbx+18h]
0x1401c1069  lea     rsi, [rbx+788h]
0x1401c1070  mov     dword ptr [rsi], 14h
0x1401c1076  mov     eax, [rcx+1664h]
0x1401c107c  test    eax, eax
0x1401c107e  jz      short loc_1401C1082
0x1401c1080  mov     [rsi], eax
0x1401c1082  lea     r14, [rbx+78Ch]
0x1401c1089  lea     r15, [rbx+790h]
0x1401c1090  mov     dword ptr [r14], 19h
0x1401c1097  mov     dword ptr [r15], 0FAh
0x1401c109e  mov     eax, [rcx+1668h]
0x1401c10a4  test    eax, eax
0x1401c10a6  jz      short loc_1401C10AB
0x1401c10a8  mov     [r15], eax
0x1401c10ab  mov     rcx, [rbx+8]; DeviceObject
0x1401c10af  lea     rdi, [rbx+794h]
0x1401c10b6  lea     r12, [rbx+79Ch]
0x1401c10bd  mov     dword ptr [rdi], 0
0x1401c10c3  lea     r9, [rsp+250h+DeviceRegKey]; DeviceRegKey
0x1401c10c8  mov     dword ptr [r12], 0FFFFFFFFh
0x1401c10d0  mov     edx, 1; DevInstKeyType
0x1401c10d5  mov     r8d, 20019h; DesiredAccess
0x1401c10db  call    cs:__imp_IoOpenDeviceRegistryKey
0x1401c10e2  nop     dword ptr [rax+rax+00h]
0x1401c10e7  test    eax, eax
0x1401c10e9  js      loc_1401C1368
0x1401c10ef  lea     rdx, aStorport_0; "Storport"
0x1401c10f6  lea     rcx, [rsp+250h+DestinationString]; DestinationString
0x1401c10fb  call    cs:__imp_RtlInitUnicodeString
0x1401c1102  nop     dword ptr [rax+rax+00h]
0x1401c1107  mov     rax, [rsp+250h+DeviceRegKey]
0x1401c110c  lea     r8, [rsp+250h+ObjectAttributes]; ObjectAttributes
0x1401c1111  mov     [rsp+250h+ObjectAttributes.RootDirectory], rax
0x1401c1116  lea     rcx, [rsp+250h+KeyHandle]; KeyHandle
0x1401c111b  lea     rax, [rsp+250h+DestinationString]
0x1401c1120  mov     [rsp+250h+ObjectAttributes.Length], 30h ; '0'
0x1401c1128  xorps   xmm0, xmm0
0x1401c112b  mov     [rsp+250h+ObjectAttributes.ObjectName], rax
0x1401c1130  mov     edx, 20019h; DesiredAccess
0x1401c1135  mov     [rsp+250h+ObjectAttributes.Attributes], 240h
0x1401c113d  movdqu  xmmword ptr [rbp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401c1142  call    cs:__imp_ZwOpenKey
0x1401c1149  nop     dword ptr [rax+rax+00h]
0x1401c114e  test    eax, eax
0x1401c1150  js      loc_1401C1368
0x1401c1156  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c115d  lea     rax, WPP_GLOBAL_Control
0x1401c1164  cmp     rcx, rax
0x1401c1167  jz      short loc_1401C118E
0x1401c1169  mov     eax, [rcx+2Ch]
0x1401c116c  test    al, 2
0x1401c116e  jz      short loc_1401C118E
0x1401c1170  cmp     byte ptr [rcx+29h], 4
0x1401c1174  jb      short loc_1401C118E
0x1401c1176  mov     rcx, [rcx+18h]
0x1401c117a  lea     r8, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids
0x1401c1181  mov     edx, 45h ; 'E'
0x1401c1186  mov     r9, rbx
0x1401c1189  call    WPP_SF_q
0x1401c118e  xor     edx, edx; Val
0x1401c1190  lea     rcx, [rbp+150h+var_1C0]; void *
0x1401c1194  mov     r8d, 188h; Size
0x1401c119a  call    memset_0
0x1401c119f  mov     ecx, 4000004h
0x1401c11a4  mov     [rbp+150h+var_1A8], r14
0x1401c11a8  mov     edx, 120h
0x1401c11ad  mov     [rbp+150h+var_1A0], ecx
0x1401c11b0  mov     r8d, 4
0x1401c11b6  mov     [rbp+150h+var_1B8], edx
0x1401c11b9  lea     rax, aQueuefullwaiti; "QueueFullWaitIoPercentage"
0x1401c11c0  mov     [rbp+150h+var_190], r8d
0x1401c11c4  mov     [rbp+150h+var_1B0], rax
0x1401c11c8  xor     r9d, r9d
0x1401c11cb  lea     rax, aBusypausetime; "BusyPauseTime"
0x1401c11d2  mov     [rbp+150h+var_180], edx
0x1401c11d5  mov     [rbp+150h+var_178], rax
0x1401c11d9  lea     rax, aBusyretrycount; "BusyRetryCount"
0x1401c11e0  mov     [rbp+150h+var_140], rax
0x1401c11e4  lea     rax, aEnablelogoetw; "EnableLogoETW"
0x1401c11eb  mov     [rbp+150h+var_108], rax
0x1401c11ef  lea     rax, aDisableidlepow; "DisableIdlePowerManagement"
0x1401c11f6  mov     [rbp+150h+var_D0], rax
0x1401c11fd  lea     rax, [rbx+798h]
0x1401c1204  mov     [rbp+150h+var_C8], rax
0x1401c120b  mov     [rbp+150h+var_B8], rax
0x1401c1212  lea     rax, aMinimumidletim; "MinimumIdleTimeoutInMS"
0x1401c1219  mov     [rbp+150h+var_168], ecx
0x1401c121c  mov     [rbp+150h+var_158], r8d
0x1401c1220  mov     [rbp+150h+var_148], edx
0x1401c1223  mov     [rbp+150h+var_130], ecx
0x1401c1226  mov     [rbp+150h+var_120], r8d
0x1401c122a  mov     [rbp+150h+var_110], edx
0x1401c122d  mov     [rbp+150h+var_F8], ecx
0x1401c1230  mov     [rbp+150h+var_E8], r8d
0x1401c1234  mov     [rbp+150h+var_D8], edx
0x1401c1237  mov     [rbp+150h+var_C0], ecx
0x1401c123d  mov     [rbp+150h+var_B0], r8d
0x1401c1244  mov     [rbp+150h+var_A0], edx
0x1401c124a  mov     rdx, [rsp+250h+KeyHandle]
0x1401c124f  mov     [rbp+150h+var_88], ecx
0x1401c1255  mov     ecx, 40000000h
0x1401c125a  mov     [rbp+150h+var_78], r8d
0x1401c1261  lea     r8, [rbp+150h+var_1C0]
0x1401c1265  mov     [rbp+150h+var_98], rax
0x1401c126c  mov     [rbp+150h+var_198], r14
0x1401c1270  mov     [rbp+150h+var_170], r15
0x1401c1274  mov     [rbp+150h+var_160], r15
0x1401c1278  mov     [rbp+150h+var_138], rsi
0x1401c127c  mov     [rbp+150h+var_128], rsi
0x1401c1280  mov     [rbp+150h+var_100], rdi
0x1401c1284  mov     [rbp+150h+var_F0], rdi
0x1401c1288  mov     [rbp+150h+var_90], r12
0x1401c128f  mov     [rbp+150h+var_80], r12
0x1401c1296  mov     [rsp+250h+var_230], 0
0x1401c129f  call    cs:__imp_RtlQueryRegistryValuesEx
0x1401c12a6  nop     dword ptr [rax+rax+00h]
0x1401c12ab  cmp     dword ptr [r14], 64h ; 'd'
0x1401c12af  jbe     short loc_1401C12B8
0x1401c12b1  mov     dword ptr [r14], 19h
0x1401c12b8  cmp     cs:EnableRegistryWatch, 0
0x1401c12bf  jz      short loc_1401C131C
0x1401c12c1  cmp     qword ptr [rbx+0DF8h], 0
0x1401c12c9  jnz     short loc_1401C131C
0x1401c12cb  mov     edx, 0C0h
0x1401c12d0  xor     r9d, r9d
0x1401c12d3  mov     r8d, 57526152h
0x1401c12d9  lea     ecx, [rdx-80h]
0x1401c12dc  call    RaidAllocatePool
0x1401c12e1  mov     rdi, rax
0x1401c12e4  test    rax, rax
0x1401c12e7  jz      short loc_1401C1368
0x1401c12e9  mov     [rax], rbx
0x1401c12ec  mov     rdx, rdi
0x1401c12ef  lea     rax, RaidUnitUpdateDynamicRegistrySettings
0x1401c12f6  mov     [rdi+8], rax
0x1401c12fa  mov     rcx, [rsp+250h+KeyHandle]
0x1401c12ff  call    StorpInitRegistryWatch
0x1401c1304  mov     rcx, rdi
0x1401c1307  call    StorpWatchForRegistryChanges
0x1401c130c  mov     [rbx+0DF8h], rdi
0x1401c1313  mov     [rsp+250h+KeyHandle], 0
0x1401c131c  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c1323  lea     rax, WPP_GLOBAL_Control
0x1401c132a  cmp     rcx, rax
0x1401c132d  jz      short loc_1401C1368
0x1401c132f  mov     eax, [rcx+2Ch]
0x1401c1332  test    al, 2
0x1401c1334  jz      short loc_1401C1368
0x1401c1336  cmp     byte ptr [rcx+29h], 4
0x1401c133a  jb      short loc_1401C1368
0x1401c133c  mov     eax, [r14]
0x1401c133f  lea     r8, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids
0x1401c1346  mov     rcx, [rcx+18h]
0x1401c134a  mov     edx, 46h ; 'F'
0x1401c134f  mov     [rsp+250h+var_220], eax
0x1401c1353  mov     r9, rbx
0x1401c1356  mov     eax, [r15]
0x1401c1359  mov     [rsp+250h+var_228], eax
0x1401c135d  mov     eax, [rsi]
0x1401c135f  mov     dword ptr [rsp+250h+var_230], eax
0x1401c1363  call    WPP_SF_qddd
0x1401c1368  mov     rcx, [rsp+250h+DeviceRegKey]; Handle
0x1401c136d  test    rcx, rcx
0x1401c1370  jz      short loc_1401C137E
0x1401c1372  call    cs:__imp_ZwClose
0x1401c1379  nop     dword ptr [rax+rax+00h]
0x1401c137e  mov     rcx, [rsp+250h+KeyHandle]; Handle
0x1401c1383  test    rcx, rcx
0x1401c1386  jz      short loc_1401C1394
0x1401c1388  call    cs:__imp_ZwClose
0x1401c138f  nop     dword ptr [rax+rax+00h]
0x1401c1394  mov     rcx, [rbp+150h+var_30]
0x1401c139b  xor     rcx, rsp; StackCookie
0x1401c139e  call    __security_check_cookie
0x1401c13a3  lea     r11, [rsp+250h+var_20]
0x1401c13ab  mov     rbx, [r11+38h]
0x1401c13af  mov     rsi, [r11+40h]
0x1401c13b3  mov     rsp, r11
0x1401c13b6  pop     r15
0x1401c13b8  pop     r14
0x1401c13ba  pop     r12
0x1401c13bc  pop     rdi
0x1401c13bd  pop     rbp
0x1401c13be  retn
```
