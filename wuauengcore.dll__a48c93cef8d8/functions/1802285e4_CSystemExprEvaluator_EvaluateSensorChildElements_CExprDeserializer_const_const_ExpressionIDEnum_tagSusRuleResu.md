# CSystemExprEvaluator::EvaluateSensorChildElements(CExprDeserializer const * const,ExpressionIDEnum,tagSusRuleResult *)

- ea: `0x1802285e4`
- end: `0x1802289f7`
- name: `?EvaluateSensorChildElements@CSystemExprEvaluator@@AEBAJQEBVCExprDeserializer@@W4ExpressionIDEnum@@PEAW4tagSusRuleResult@@@Z`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180226250`

## callees

- `0x1802285e4`
- `0x18022a154`
- `0x18022a26c`
- `0x18022a384`
- `0x18022a49c`
- `0x18022a5b4`
- `0x18022a6cc`
- `0x18022a7e4`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228861`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228895`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1802288c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1802288fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228931`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228964`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228997`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228861`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228895`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1802288c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1802288fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228931`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228964`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180228997`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180228719`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180228719`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802287d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802287d7`
- `RPCRT4!UuidFromStringW` at `0x1802286d0`
- `RPCRT4!UuidFromStringW` at `0x1802286d0`

## string_xrefs

- `0x180228870`: `Compass`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSystemExprEvaluator::EvaluateSensorChildElements(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  unsigned int v5; // edi
  int v6; // ebx
  int v7; // r10d
  __int64 v8; // rax
  WCHAR *v9; // r14
  __int64 v10; // rcx
  unsigned int v11; // r11d
  __int64 v12; // r9
  int v13; // r8d
  unsigned int i; // esi
  int v15; // eax
  unsigned int v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-40h] BYREF
  __int64 v20; // [rsp+48h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v22; // [rsp+60h] [rbp-20h]
  UUID Uuid; // [rsp+68h] [rbp-18h] BYREF

  v5 = -2147467259;
  v6 = 0;
  if ( !a2 || !a4 )
    return (unsigned int)-2147024809;
  *a4 = -1;
  if ( a3 == 60 )
  {
    v7 = 186;
  }
  else
  {
    if ( a3 != 61 )
      return v5;
    v7 = 187;
  }
  if ( !*(_DWORD *)(a2 + 24) )
    return (unsigned int)-2145067006;
  v8 = *(_QWORD *)(a2 + 8);
  if ( !v8 )
    return (unsigned int)-2145067006;
  v9 = 0;
  v10 = 0;
  v11 = *(_DWORD *)(v8 + 8);
  if ( !v11 )
    goto LABEL_16;
  v12 = *(_QWORD *)(a2 + 16);
  while ( *(_DWORD *)(v12 + 24LL * (unsigned int)v10) != v7 )
  {
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= v11 )
      goto LABEL_16;
  }
  if ( *(_DWORD *)(v12 + 24LL * (unsigned int)v10 + 8) != 8 )
    return (unsigned int)-2145067006;
  v9 = *(WCHAR **)(v12 + 24LL * (unsigned int)v10 + 16);
LABEL_16:
  v5 = 0;
  *a4 = 0;
  v13 = a3 - 60;
  if ( !v13 )
  {
    if ( L"Accelerometer" == v9 )
      goto LABEL_60;
    if ( !v9 )
    {
LABEL_62:
      *a4 = v6;
      return v5;
    }
    if ( CompareStringW(0x7Fu, 1u, L"Accelerometer", -1, v9, -1) == 2 )
    {
LABEL_60:
      v15 = IsSensorPresent_ABI::Windows::Devices::Sensors::IAccelerometerStatics_ABI::Windows::Devices::Sensors::IAccelerometer_(v10);
    }
    else if ( L"Compass" == v9 || CompareStringW(0x7Fu, 1u, L"Compass", -1, v9, -1) == 2 )
    {
      v15 = IsSensorPresent_ABI::Windows::Devices::Sensors::ICompassStatics_ABI::Windows::Devices::Sensors::ICompass_();
    }
    else if ( L"Gyrometer" == v9 || CompareStringW(0x7Fu, 1u, L"Gyrometer", -1, v9, -1) == 2 )
    {
      v15 = IsSensorPresent_ABI::Windows::Devices::Sensors::IGyrometerStatics_ABI::Windows::Devices::Sensors::IGyrometer_();
    }
    else if ( L"Inclinometer" == v9 || CompareStringW(0x7Fu, 1u, L"Inclinometer", -1, v9, -1) == 2 )
    {
      v15 = IsSensorPresent_ABI::Windows::Devices::Sensors::IInclinometerStatics_ABI::Windows::Devices::Sensors::IInclinometer_();
    }
    else if ( L"LightSensor" == v9 || CompareStringW(0x7Fu, 1u, L"LightSensor", -1, v9, -1) == 2 )
    {
      v15 = IsSensorPresent_ABI::Windows::Devices::Sensors::ILightSensorStatics_ABI::Windows::Devices::Sensors::ILightSensor_();
    }
    else if ( L"SimpleOrientation" == v9 || CompareStringW(0x7Fu, 1u, L"SimpleOrientation", -1, v9, -1) == 2 )
    {
      v15 = IsSensorPresent_ABI::Windows::Devices::Sensors::ISimpleOrientationSensorStatics_ABI::Windows::Devices::Sensors::ISimpleOrientationSensor_();
    }
    else
    {
      if ( L"OrientationSensor" != v9 && CompareStringW(0x7Fu, 1u, L"OrientationSensor", -1, v9, -1) != 2 )
        goto LABEL_62;
      v15 = IsSensorPresent_ABI::Windows::Devices::Sensors::IOrientationSensorStatics_ABI::Windows::Devices::Sensors::IOrientationSensor_();
    }
    v6 = v15;
    goto LABEL_62;
  }
  if ( v13 == 1 )
  {
    Uuid = 0;
    ppv = 0;
    if ( UuidFromStringW(v9, &Uuid) )
    {
      *a4 = -1;
      v5 = -2145067006;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      if ( CoCreateInstance(
             &GUID_77a1c827_fcd2_4689_8915_9d613cc5fa3e,
             0,
             1u,
             &GUID_bd77db67_45a8_42dc_8d00_6dcf15f8377a,
             &ppv) >= 0 )
      {
        v17 = 0;
        v18 = 0;
        if ( (*(int (__fastcall **)(LPVOID, UUID *, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, &Uuid, &v18) >= 0
          && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 32LL))(v18, &v17) >= 0 )
        {
          for ( i = 0; i < v17; v5 = 0 )
          {
            v5 = 0;
            if ( *a4 )
              break;
            v20 = 0;
            *(_OWORD *)pvar = 0;
            v22 = 0;
            if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, i, &v20) >= 0
              && (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v20 + 56LL))(
                   v20,
                   &SENSOR_PROPERTY_CONNECTION_TYPE,
                   pvar) >= 0
              && !LOWORD(pvar[1]) )
            {
              *a4 = 1;
            }
            PropVariantClear(pvar);
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            ++i;
          }
        }
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1802285e4  mov     [rsp-28h+arg_0], rbx
0x1802285e9  mov     [rsp-28h+arg_8], rsi
0x1802285ee  mov     [rsp-28h+arg_10], rdi
0x1802285f3  push    rbp
0x1802285f4  push    r12
0x1802285f6  push    r13
0x1802285f8  push    r14
0x1802285fa  push    r15
0x1802285fc  mov     rbp, rsp
0x1802285ff  sub     rsp, 80h
0x180228606  mov     rax, cs:__security_cookie
0x18022860d  xor     rax, rsp
0x180228610  mov     [rbp+var_8], rax
0x180228614  mov     r15, r9
0x180228617  mov     edi, 80004005h
0x18022861c  xor     ebx, ebx
0x18022861e  test    rdx, rdx
0x180228621  jz      loc_1802289C3
0x180228627  test    r9, r9
0x18022862a  jz      loc_1802289C3
0x180228630  or      r12d, 0FFFFFFFFh
0x180228634  mov     [r9], r12d
0x180228637  cmp     r8d, 3Ch ; '<'
0x18022863b  jnz     short loc_180228643
0x18022863d  lea     r10d, [r8+7Eh]
0x180228641  jmp     short loc_180228651
0x180228643  cmp     r8d, 3Dh ; '='
0x180228647  jnz     loc_1802289C8
0x18022864d  lea     r10d, [r8+7Eh]
0x180228651  cmp     [rdx+18h], ebx
0x180228654  jz      loc_1802289BC
0x18022865a  mov     rax, [rdx+8]
0x18022865e  test    rax, rax
0x180228661  jz      loc_1802289BC
0x180228667  mov     r14, rbx
0x18022866a  mov     ecx, ebx
0x18022866c  mov     r11d, [rax+8]
0x180228670  mov     r13d, 1
0x180228676  test    r11d, r11d
0x180228679  jz      short loc_1802286A6
0x18022867b  mov     r9, [rdx+10h]
0x18022867f  mov     eax, ecx
0x180228681  lea     rdx, [rax+rax*2]
0x180228685  cmp     [r9+rdx*8], r10d
0x180228689  jz      short loc_180228695
0x18022868b  add     ecx, r13d
0x18022868e  cmp     ecx, r11d
0x180228691  jb      short loc_18022867F
0x180228693  jmp     short loc_1802286A6
0x180228695  cmp     dword ptr [r9+rdx*8+8], 8
0x18022869b  jnz     loc_1802289BC
0x1802286a1  mov     r14, [r9+rdx*8+10h]
0x1802286a6  mov     edi, ebx
0x1802286a8  mov     [r15], ebx
0x1802286ab  sub     r8d, 3Ch ; '<'
0x1802286af  jz      loc_180228833
0x1802286b5  cmp     r8d, r13d
0x1802286b8  jnz     loc_1802289C8
0x1802286be  xorps   xmm0, xmm0
0x1802286c1  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1802286c5  mov     [rbp+var_40], rbx
0x1802286c9  lea     rdx, [rbp+Uuid]; Uuid
0x1802286cd  mov     rcx, r14; StringUuid
0x1802286d0  call    cs:__imp_UuidFromStringW
0x1802286d6  test    eax, eax
0x1802286d8  jz      short loc_1802286FD
0x1802286da  mov     [r15], r12d
0x1802286dd  mov     edi, 8024E002h
0x1802286e2  mov     rcx, [rbp+var_40]
0x1802286e6  test    rcx, rcx
0x1802286e9  jz      short loc_1802286F8
0x1802286eb  mov     rax, [rcx]
0x1802286ee  mov     rax, [rax+10h]
0x1802286f2  call    _guard_dispatch_icall
0x1802286f7  nop
0x1802286f8  jmp     loc_1802289C8
0x1802286fd  lea     rax, [rbp+var_40]
0x180228701  mov     [rsp+80h+ppv], rax; ppv
0x180228706  lea     r9, _GUID_bd77db67_45a8_42dc_8d00_6dcf15f8377a; riid
0x18022870d  mov     r8d, r13d; dwClsContext
0x180228710  xor     edx, edx; pUnkOuter
0x180228712  lea     rcx, _GUID_77a1c827_fcd2_4689_8915_9d613cc5fa3e; rclsid
0x180228719  call    cs:__imp_CoCreateInstance
0x18022871f  test    eax, eax
0x180228721  js      loc_180228818
0x180228727  mov     [rbp+var_50], ebx
0x18022872a  mov     [rbp+var_48], rbx
0x18022872e  mov     rcx, [rbp+var_40]
0x180228732  mov     rax, [rcx]
0x180228735  lea     r8, [rbp+var_48]
0x180228739  lea     rdx, [rbp+Uuid]
0x18022873d  mov     rax, [rax+20h]
0x180228741  call    _guard_dispatch_icall
0x180228746  test    eax, eax
0x180228748  js      loc_180228802
0x18022874e  mov     rcx, [rbp+var_48]
0x180228752  mov     rax, [rcx]
0x180228755  lea     rdx, [rbp+var_50]
0x180228759  mov     rax, [rax+20h]
0x18022875d  call    _guard_dispatch_icall
0x180228762  test    eax, eax
0x180228764  js      loc_180228802
0x18022876a  mov     esi, ebx
0x18022876c  cmp     [rbp+var_50], ebx
0x18022876f  jbe     loc_180228802
0x180228775  mov     edi, ebx
0x180228777  cmp     [r15], ebx
0x18022877a  jnz     loc_180228802
0x180228780  mov     [rbp+var_38], rbx
0x180228784  xorps   xmm0, xmm0
0x180228787  xor     eax, eax
0x180228789  movups  xmmword ptr [rbp+pvar], xmm0
0x18022878d  mov     [rbp+var_20], rax
0x180228791  mov     rcx, [rbp+var_48]
0x180228795  mov     rax, [rcx]
0x180228798  lea     r8, [rbp+var_38]
0x18022879c  mov     edx, esi
0x18022879e  mov     rax, [rax+18h]
0x1802287a2  call    _guard_dispatch_icall
0x1802287a7  test    eax, eax
0x1802287a9  js      short loc_1802287D3
0x1802287ab  mov     rcx, [rbp+var_38]
0x1802287af  mov     rax, [rcx]
0x1802287b2  lea     r8, [rbp+pvar]
0x1802287b6  lea     rdx, SENSOR_PROPERTY_CONNECTION_TYPE
0x1802287bd  mov     rax, [rax+38h]
0x1802287c1  call    _guard_dispatch_icall
0x1802287c6  test    eax, eax
0x1802287c8  js      short loc_1802287D3
0x1802287ca  cmp     word ptr [rbp+pvar+8], bx
0x1802287ce  jnz     short loc_1802287D3
0x1802287d0  mov     [r15], r13d
0x1802287d3  lea     rcx, [rbp+pvar]; pvar
0x1802287d7  call    cs:__imp_PropVariantClear
0x1802287dd  nop
0x1802287de  mov     rcx, [rbp+var_38]
0x1802287e2  test    rcx, rcx
0x1802287e5  jz      short loc_1802287F4
0x1802287e7  mov     rax, [rcx]
0x1802287ea  mov     rax, [rax+10h]
0x1802287ee  call    _guard_dispatch_icall
0x1802287f3  nop
0x1802287f4  add     esi, r13d
0x1802287f7  mov     edi, ebx
0x1802287f9  cmp     esi, [rbp+var_50]
0x1802287fc  jb      loc_180228775
0x180228802  mov     rcx, [rbp+var_48]
0x180228806  test    rcx, rcx
0x180228809  jz      short loc_180228818
0x18022880b  mov     rax, [rcx]
0x18022880e  mov     rax, [rax+10h]
0x180228812  call    _guard_dispatch_icall
0x180228817  nop
0x180228818  mov     rcx, [rbp+var_40]
0x18022881c  test    rcx, rcx
0x18022881f  jz      short loc_18022882E
0x180228821  mov     rax, [rcx]
0x180228824  mov     rax, [rax+10h]
0x180228828  call    _guard_dispatch_icall
0x18022882d  nop
0x18022882e  jmp     loc_1802289C8
0x180228833  lea     r8, aAccelerometer; "Accelerometer"
0x18022883a  cmp     r8, r14
0x18022883d  jz      loc_1802289B0
0x180228843  test    r14, r14
0x180228846  jz      loc_1802289B7
0x18022884c  mov     [rsp+80h+cchCount2], r12d; cchCount2
0x180228851  mov     [rsp+80h+ppv], r14; lpString2
0x180228856  mov     r9d, r12d; cchCount1
0x180228859  mov     edx, r13d; dwCmpFlags
0x18022885c  mov     ecx, 7Fh; Locale
0x180228861  call    cs:__imp_CompareStringW
0x180228867  cmp     eax, 2
0x18022886a  jz      loc_1802289B0
0x180228870  lea     r8, aCompass; "Compass"
0x180228877  cmp     r8, r14
0x18022887a  jz      loc_1802289A9
0x180228880  mov     [rsp+80h+cchCount2], r12d; cchCount2
0x180228885  mov     [rsp+80h+ppv], r14; lpString2
0x18022888a  mov     r9d, r12d; cchCount1
0x18022888d  mov     edx, r13d; dwCmpFlags
0x180228890  mov     ecx, 7Fh; Locale
0x180228895  call    cs:__imp_CompareStringW
0x18022889b  cmp     eax, 2
0x18022889e  jz      loc_1802289A9
0x1802288a4  lea     r8, aGyrometer; "Gyrometer"
0x1802288ab  cmp     r8, r14
0x1802288ae  jz      short loc_1802288D0
0x1802288b0  mov     [rsp+80h+cchCount2], r12d; cchCount2
0x1802288b5  mov     [rsp+80h+ppv], r14; lpString2
0x1802288ba  mov     r9d, r12d; cchCount1
0x1802288bd  mov     edx, r13d; dwCmpFlags
0x1802288c0  mov     ecx, 7Fh; Locale
0x1802288c5  call    cs:__imp_CompareStringW
0x1802288cb  cmp     eax, 2
0x1802288ce  jnz     short loc_1802288DA
0x1802288d0  call    IsSensorPresent_ABI__Windows__Devices__Sensors__IGyrometerStatics_ABI__Windows__Devices__Sensors__IGyrometer_
0x1802288d5  jmp     loc_1802289B5
0x1802288da  lea     r8, aInclinometer; "Inclinometer"
0x1802288e1  cmp     r8, r14
0x1802288e4  jz      short loc_180228906
0x1802288e6  mov     [rsp+80h+cchCount2], r12d; cchCount2
0x1802288eb  mov     [rsp+80h+ppv], r14; lpString2
0x1802288f0  mov     r9d, r12d; cchCount1
0x1802288f3  mov     edx, r13d; dwCmpFlags
0x1802288f6  mov     ecx, 7Fh; Locale
0x1802288fb  call    cs:__imp_CompareStringW
0x180228901  cmp     eax, 2
0x180228904  jnz     short loc_180228910
0x180228906  call    IsSensorPresent_ABI__Windows__Devices__Sensors__IInclinometerStatics_ABI__Windows__Devices__Sensors__IInclinometer_
0x18022890b  jmp     loc_1802289B5
0x180228910  lea     r8, aLightsensor; "LightSensor"
0x180228917  cmp     r8, r14
0x18022891a  jz      short loc_18022893C
0x18022891c  mov     [rsp+80h+cchCount2], r12d; cchCount2
0x180228921  mov     [rsp+80h+ppv], r14; lpString2
0x180228926  mov     r9d, r12d; cchCount1
0x180228929  mov     edx, r13d; dwCmpFlags
0x18022892c  mov     ecx, 7Fh; Locale
0x180228931  call    cs:__imp_CompareStringW
0x180228937  cmp     eax, 2
0x18022893a  jnz     short loc_180228943
0x18022893c  call    IsSensorPresent_ABI__Windows__Devices__Sensors__ILightSensorStatics_ABI__Windows__Devices__Sensors__ILightSensor_
0x180228941  jmp     short loc_1802289B5
0x180228943  lea     r8, aSimpleorientat; "SimpleOrientation"
0x18022894a  cmp     r8, r14
0x18022894d  jz      short loc_18022896F
0x18022894f  mov     [rsp+80h+cchCount2], r12d; cchCount2
0x180228954  mov     [rsp+80h+ppv], r14; lpString2
0x180228959  mov     r9d, r12d; cchCount1
0x18022895c  mov     edx, r13d; dwCmpFlags
0x18022895f  mov     ecx, 7Fh; Locale
0x180228964  call    cs:__imp_CompareStringW
0x18022896a  cmp     eax, 2
0x18022896d  jnz     short loc_180228976
0x18022896f  call    IsSensorPresent_ABI__Windows__Devices__Sensors__ISimpleOrientationSensorStatics_ABI__Windows__Devices__Sensors__ISimpleOrientationSensor_
0x180228974  jmp     short loc_1802289B5
0x180228976  lea     r8, aOrientationsen; "OrientationSensor"
0x18022897d  cmp     r8, r14
0x180228980  jz      short loc_1802289A2
0x180228982  mov     [rsp+80h+cchCount2], r12d; cchCount2
0x180228987  mov     [rsp+80h+ppv], r14; lpString2
0x18022898c  mov     r9d, r12d; cchCount1
0x18022898f  mov     edx, r13d; dwCmpFlags
0x180228992  mov     ecx, 7Fh; Locale
0x180228997  call    cs:__imp_CompareStringW
0x18022899d  cmp     eax, 2
0x1802289a0  jnz     short loc_1802289B7
0x1802289a2  call    IsSensorPresent_ABI__Windows__Devices__Sensors__IOrientationSensorStatics_ABI__Windows__Devices__Sensors__IOrientationSensor_
0x1802289a7  jmp     short loc_1802289B5
0x1802289a9  call    IsSensorPresent_ABI__Windows__Devices__Sensors__ICompassStatics_ABI__Windows__Devices__Sensors__ICompass_
0x1802289ae  jmp     short loc_1802289B5
0x1802289b0  call    IsSensorPresent_ABI__Windows__Devices__Sensors__IAccelerometerStatics_ABI__Windows__Devices__Sensors__IAccelerometer_
0x1802289b5  mov     ebx, eax
0x1802289b7  mov     [r15], ebx
0x1802289ba  jmp     short loc_1802289C8
0x1802289bc  mov     edi, 8024E002h
0x1802289c1  jmp     short loc_1802289C8
0x1802289c3  mov     edi, 80070057h
0x1802289c8  mov     eax, edi
0x1802289ca  mov     rcx, [rbp+var_8]
0x1802289ce  xor     rcx, rsp; StackCookie
0x1802289d1  call    __security_check_cookie
0x1802289d6  lea     r11, [rsp+80h+var_s0]
0x1802289de  mov     rbx, [r11+30h]
0x1802289e2  mov     rsi, [r11+38h]
0x1802289e6  mov     rdi, [r11+40h]
0x1802289ea  mov     rsp, r11
0x1802289ed  pop     r15
0x1802289ef  pop     r14
0x1802289f1  pop     r13
0x1802289f3  pop     r12
0x1802289f5  pop     rbp
0x1802289f6  retn
```
