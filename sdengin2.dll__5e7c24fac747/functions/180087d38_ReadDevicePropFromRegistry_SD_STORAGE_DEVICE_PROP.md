# ReadDevicePropFromRegistry(_SD_STORAGE_DEVICE_PROP *)

- ea: `0x180087d38`
- end: `0x180088108`
- name: `?ReadDevicePropFromRegistry@@YAJPEAU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `976`
- prototype: `__int64 __fastcall(struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058eb4`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180070ac0`
- `0x180087d38`
- `0x1800885bc`
- `0x180094758`
- `0x180094d2c`
- `0x1800c97da`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087e0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800880be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800880da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087e0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800880be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800880da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087dd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087e36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087dd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087e36`

## string_xrefs

- `0x180087d50`: `ReadDevicePropFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadDevicePropFromRegistry(struct _SD_STORAGE_DEVICE_PROP *a1)
{
  __int64 v2; // rcx
  struct _SD_STORAGE_DEVICE_PROP *v3; // rax
  int v4; // eax
  bool v5; // sf
  __int16 v6; // ax
  int v7; // eax
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  unsigned int v16; // ebx
  int DWORD; // [rsp+30h] [rbp-89h] BYREF
  __int16 v19; // [rsp+34h] [rbp-85h]
  __int16 v20; // [rsp+36h] [rbp-83h]
  unsigned __int16 *v21[2]; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int16 *v22[2]; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int16 *v23[2]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int16 *v24[2]; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int64 v25[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v26; // [rsp+C0h] [rbp+7h]
  __int128 v27; // [rsp+D0h] [rbp+17h]
  __int128 v28; // [rsp+E0h] [rbp+27h]
  __int128 v29; // [rsp+F0h] [rbp+37h]
  HKEY hKey; // [rsp+120h] [rbp+67h] BYREF
  HKEY phkResult; // [rsp+128h] [rbp+6Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&DWORD, "ReadDevicePropFromRegistry", 753, 2);
  phkResult = 0;
  hKey = 0;
  memset_0(v21, 0, 0x90u);
  if ( a1 )
  {
    v2 = 144;
    v3 = a1;
    do
    {
      *(_BYTE *)v3 = 0;
      v3 = (struct _SD_STORAGE_DEVICE_PROP *)((char *)v3 + 1);
      --v2;
    }
    while ( v2 );
    DWORD = 0;
    v19 = 762;
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\ScheduleParams",
           0,
           0x20019u,
           &phkResult);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    DWORD = v4;
    v5 = v4 < 0;
    v6 = 764;
    if ( !v5 )
    {
      v19 = 764;
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      v7 = RegOpenKeyExW(phkResult, L"TargetDevice", 0, 0x20019u, &hKey);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      DWORD = v7;
      v5 = v7 < 0;
      v6 = 765;
      if ( !v5 )
      {
        v19 = 765;
        DWORD = SxRegReadDWORD(hKey, L"Type", (unsigned int *)&v24[1], 0);
        v6 = 767;
        if ( DWORD >= 0 )
        {
          v19 = 767;
          DWORD = SxRegReadULONGLONG(hKey, L"TotalSize", v25, 0);
          v6 = 768;
          if ( DWORD >= 0 )
          {
            v19 = 768;
            DWORD = SxRegReadULONGLONG(hKey, L"Freespace", &v25[1], 0);
            v6 = 769;
            if ( DWORD >= 0 )
            {
              v19 = 769;
              DWORD = ReadStringFromRegistry(hKey, L"PresentableName", v21, 0);
              v6 = 771;
              if ( DWORD >= 0 )
              {
                v19 = 771;
                DWORD = ReadStringFromRegistry(hKey, L"UniqueName", &v21[1], 0);
                v6 = 772;
                if ( DWORD >= 0 )
                {
                  v19 = 772;
                  DWORD = ReadStringFromRegistry(hKey, L"Label", v22, 1);
                  v6 = 773;
                  if ( DWORD >= 0 )
                  {
                    v19 = 773;
                    DWORD = ReadStringFromRegistry(hKey, L"DeviceVendor", &v22[1], 1);
                    v6 = 775;
                    if ( DWORD >= 0 )
                    {
                      v19 = 775;
                      DWORD = ReadStringFromRegistry(hKey, L"DeviceProduct", v23, 1);
                      v6 = 776;
                      if ( DWORD >= 0 )
                      {
                        v19 = 776;
                        DWORD = ReadStringFromRegistry(hKey, L"DeviceVersion", &v23[1], 1);
                        v6 = 777;
                        if ( DWORD >= 0 )
                        {
                          v19 = 777;
                          DWORD = ReadStringFromRegistry(hKey, L"DeviceSerial", v24, 1);
                          if ( DWORD >= 0 )
                          {
                            v8 = *(_OWORD *)v22;
                            *(_OWORD *)a1 = *(_OWORD *)v21;
                            v9 = *(_OWORD *)v23;
                            *((_OWORD *)a1 + 1) = v8;
                            v10 = *(_OWORD *)v24;
                            *((_OWORD *)a1 + 2) = v9;
                            v11 = *(_OWORD *)v25;
                            *((_OWORD *)a1 + 3) = v10;
                            v12 = v26;
                            *((_OWORD *)a1 + 4) = v11;
                            v13 = v27;
                            *((_OWORD *)a1 + 5) = v12;
                            v14 = v28;
                            *((_OWORD *)a1 + 6) = v13;
                            v15 = v29;
                            *((_OWORD *)a1 + 7) = v14;
                            *((_OWORD *)a1 + 8) = v15;
                            memset_0(v21, 0, 0x90u);
                            DWORD = 0;
                            v19 = 789;
                            goto LABEL_26;
                          }
                          v6 = 778;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    DWORD = -2147024809;
    v6 = 762;
  }
  v20 = v6;
LABEL_26:
  CleanupStorageDeviceProp(v21);
  v16 = DWORD;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DWORD);
  return v16;
}

```

## disassembly

```asm
0x180087d38  mov     [rsp-8+arg_10], rbx
0x180087d3d  push    rbp
0x180087d3e  push    rdi
0x180087d3f  push    r12
0x180087d41  lea     rbp, [rsp-47h]
0x180087d46  sub     rsp, 100h
0x180087d4d  mov     rdi, rcx
0x180087d50  lea     rdx, aReaddeviceprop; "ReadDevicePropFromRegistry"
0x180087d57  lea     rcx, [rsp+110h+var_E0]; this
0x180087d5c  mov     r9d, 2; unsigned __int16
0x180087d62  mov     r8d, 2F1h; unsigned __int16
0x180087d68  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180087d6d  xor     ebx, ebx
0x180087d6f  lea     rcx, [rbp+57h+var_A0]; void *
0x180087d73  mov     r12d, 90h
0x180087d79  mov     [rbp+57h+arg_8], rbx
0x180087d7d  mov     r8d, r12d; Size
0x180087d80  mov     [rbp+57h+hKey], rbx
0x180087d84  xor     edx, edx; Val
0x180087d86  call    memset_0
0x180087d8b  test    rdi, rdi
0x180087d8e  jz      loc_180088091
0x180087d94  mov     ecx, r12d
0x180087d97  mov     rax, rdi
0x180087d9a  mov     [rax], bl
0x180087d9c  inc     rax
0x180087d9f  sub     rcx, 1
0x180087da3  jnz     short loc_180087D9A
0x180087da5  mov     eax, 2FAh
0x180087daa  mov     [rsp+110h+var_E0], ebx
0x180087dae  mov     [rsp+110h+var_DC], ax
0x180087db3  lea     rdx, c_wszSafedocsSchedulingKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180087dba  lea     rax, [rbp+57h+arg_8]
0x180087dbe  mov     r9d, 20019h; samDesired
0x180087dc4  xor     r8d, r8d; ulOptions
0x180087dc7  mov     [rsp+110h+phkResult], rax; phkResult
0x180087dcc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087dd3  call    cs:__imp_RegOpenKeyExW
0x180087dd9  mov     ebx, 80070000h
0x180087dde  test    eax, eax
0x180087de0  jle     short loc_180087DE7
0x180087de2  movzx   eax, ax
0x180087de5  or      eax, ebx
0x180087de7  mov     [rsp+110h+var_E0], eax
0x180087deb  test    eax, eax
0x180087ded  mov     eax, 2FCh
0x180087df2  js      loc_18008809E
0x180087df8  mov     rcx, [rbp+57h+hKey]; hKey
0x180087dfc  mov     [rsp+110h+var_DC], ax
0x180087e01  lea     rax, [rcx-1]
0x180087e05  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180087e09  ja      short loc_180087E19
0x180087e0b  call    cs:__imp_RegCloseKey
0x180087e11  mov     [rbp+57h+hKey], 0
0x180087e19  mov     rcx, [rbp+57h+arg_8]; hKey
0x180087e1d  lea     rax, [rbp+57h+hKey]
0x180087e21  mov     r9d, 20019h; samDesired
0x180087e27  mov     [rsp+110h+phkResult], rax; phkResult
0x180087e2c  xor     r8d, r8d; ulOptions
0x180087e2f  lea     rdx, c_wszSafedocsDeviceTarget; "TargetDevice"
0x180087e36  call    cs:__imp_RegOpenKeyExW
0x180087e3c  test    eax, eax
0x180087e3e  jle     short loc_180087E45
0x180087e40  movzx   eax, ax
0x180087e43  or      eax, ebx
0x180087e45  mov     [rsp+110h+var_E0], eax
0x180087e49  test    eax, eax
0x180087e4b  mov     eax, 2FDh
0x180087e50  js      loc_18008809E
0x180087e56  mov     rcx, [rbp+57h+hKey]; hKey
0x180087e5a  lea     r8, [rbp+57h+var_70+8]; unsigned int *
0x180087e5e  xor     r9d, r9d; int
0x180087e61  mov     [rsp+110h+var_DC], ax
0x180087e66  lea     rdx, c_wszSafedocsDeviceType; "Type"
0x180087e6d  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180087e72  mov     [rsp+110h+var_E0], eax
0x180087e76  test    eax, eax
0x180087e78  mov     eax, 2FFh
0x180087e7d  js      loc_18008809E
0x180087e83  mov     rcx, [rbp+57h+hKey]; hKey
0x180087e87  lea     r8, [rbp+57h+var_60]; unsigned __int64 *
0x180087e8b  xor     r9d, r9d; int
0x180087e8e  mov     [rsp+110h+var_DC], ax
0x180087e93  lea     rdx, c_wszSafedocsDeviceSize; "TotalSize"
0x180087e9a  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x180087e9f  mov     [rsp+110h+var_E0], eax
0x180087ea3  test    eax, eax
0x180087ea5  mov     eax, 300h
0x180087eaa  js      loc_18008809E
0x180087eb0  mov     rcx, [rbp+57h+hKey]; hKey
0x180087eb4  lea     r8, [rbp+57h+var_60+8]; unsigned __int64 *
0x180087eb8  xor     r9d, r9d; int
0x180087ebb  mov     [rsp+110h+var_DC], ax
0x180087ec0  lea     rdx, c_wszSafedocsDeviceFree; "Freespace"
0x180087ec7  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x180087ecc  mov     [rsp+110h+var_E0], eax
0x180087ed0  test    eax, eax
0x180087ed2  mov     eax, 301h
0x180087ed7  js      loc_18008809E
0x180087edd  mov     rcx, [rbp+57h+hKey]; hKey
0x180087ee1  lea     r8, [rbp+57h+var_A0]; unsigned __int16 **
0x180087ee5  xor     r9d, r9d; int
0x180087ee8  mov     [rsp+110h+var_DC], ax
0x180087eed  lea     rdx, c_wszSafedocsDevicePresentableName; "PresentableName"
0x180087ef4  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180087ef9  mov     [rsp+110h+var_E0], eax
0x180087efd  test    eax, eax
0x180087eff  mov     eax, 303h
0x180087f04  js      loc_18008809E
0x180087f0a  mov     rcx, [rbp+57h+hKey]; hKey
0x180087f0e  lea     r8, [rbp+57h+var_A0+8]; unsigned __int16 **
0x180087f12  xor     r9d, r9d; int
0x180087f15  mov     [rsp+110h+var_DC], ax
0x180087f1a  lea     rdx, c_wszSafedocsDeviceUniqueName; "UniqueName"
0x180087f21  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180087f26  mov     [rsp+110h+var_E0], eax
0x180087f2a  test    eax, eax
0x180087f2c  mov     eax, 304h
0x180087f31  js      loc_18008809E
0x180087f37  mov     rcx, [rbp+57h+hKey]; hKey
0x180087f3b  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x180087f3f  mov     r9d, 1; int
0x180087f45  mov     [rsp+110h+var_DC], ax
0x180087f4a  lea     rdx, c_wszSafedocsDeviceLabel; "Label"
0x180087f51  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180087f56  mov     [rsp+110h+var_E0], eax
0x180087f5a  test    eax, eax
0x180087f5c  mov     eax, 305h
0x180087f61  js      loc_18008809E
0x180087f67  mov     rcx, [rbp+57h+hKey]; hKey
0x180087f6b  lea     r8, [rbp+57h+var_90+8]; unsigned __int16 **
0x180087f6f  mov     r9d, 1; int
0x180087f75  mov     [rsp+110h+var_DC], ax
0x180087f7a  lea     rdx, c_wszSafedocsDeviceVendor; "DeviceVendor"
0x180087f81  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180087f86  mov     [rsp+110h+var_E0], eax
0x180087f8a  test    eax, eax
0x180087f8c  mov     eax, 307h
0x180087f91  js      loc_18008809E
0x180087f97  mov     rcx, [rbp+57h+hKey]; hKey
0x180087f9b  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x180087f9f  mov     r9d, 1; int
0x180087fa5  mov     [rsp+110h+var_DC], ax
0x180087faa  lea     rdx, c_wszSafedocsDeviceProduct; "DeviceProduct"
0x180087fb1  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180087fb6  mov     [rsp+110h+var_E0], eax
0x180087fba  test    eax, eax
0x180087fbc  mov     eax, 308h
0x180087fc1  js      loc_18008809E
0x180087fc7  mov     rcx, [rbp+57h+hKey]; hKey
0x180087fcb  lea     r8, [rbp+57h+var_80+8]; unsigned __int16 **
0x180087fcf  mov     r9d, 1; int
0x180087fd5  mov     [rsp+110h+var_DC], ax
0x180087fda  lea     rdx, c_wszSafedocsDeviceVersion; "DeviceVersion"
0x180087fe1  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180087fe6  mov     [rsp+110h+var_E0], eax
0x180087fea  test    eax, eax
0x180087fec  mov     eax, 309h
0x180087ff1  js      loc_18008809E
0x180087ff7  mov     rcx, [rbp+57h+hKey]; hKey
0x180087ffb  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x180087fff  mov     r9d, 1; int
0x180088005  mov     [rsp+110h+var_DC], ax
0x18008800a  lea     rdx, c_wszSafedocsDeviceSerial; "DeviceSerial"
0x180088011  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180088016  mov     [rsp+110h+var_E0], eax
0x18008801a  test    eax, eax
0x18008801c  jns     short loc_180088025
0x18008801e  mov     eax, 30Ah
0x180088023  jmp     short loc_18008809E
0x180088025  movaps  xmm0, xmmword ptr [rbp+57h+var_A0]
0x180088029  lea     rcx, [rbp+57h+var_A0]; void *
0x18008802d  movaps  xmm1, xmmword ptr [rbp+57h+var_90]
0x180088031  mov     r8, r12; Size
0x180088034  movups  xmmword ptr [rdi], xmm0
0x180088037  xor     edx, edx; Val
0x180088039  movaps  xmm0, xmmword ptr [rbp+57h+var_80]
0x18008803d  movups  xmmword ptr [rdi+10h], xmm1
0x180088041  movaps  xmm1, xmmword ptr [rbp+57h+var_70]
0x180088045  movups  xmmword ptr [rdi+20h], xmm0
0x180088049  movaps  xmm0, xmmword ptr [rbp+57h+var_60]
0x18008804d  movups  xmmword ptr [rdi+30h], xmm1
0x180088051  movaps  xmm1, [rbp+57h+var_50]
0x180088055  movups  xmmword ptr [rdi+40h], xmm0
0x180088059  movaps  xmm0, [rbp+57h+var_40]
0x18008805d  movups  xmmword ptr [rdi+50h], xmm1
0x180088061  movaps  xmm1, [rbp+57h+var_30]
0x180088065  movups  xmmword ptr [rdi+60h], xmm0
0x180088069  movaps  xmm0, [rbp+57h+var_20]
0x18008806d  movups  xmmword ptr [rdi+70h], xmm1
0x180088071  movups  xmmword ptr [rdi+80h], xmm0
0x180088078  call    memset_0
0x18008807d  mov     eax, 315h
0x180088082  mov     [rsp+110h+var_E0], 0
0x18008808a  mov     [rsp+110h+var_DC], ax
0x18008808f  jmp     short loc_1800880A3
0x180088091  mov     [rsp+110h+var_E0], 80070057h
0x180088099  mov     eax, 2FAh
0x18008809e  mov     [rsp+110h+var_DA], ax
0x1800880a3  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 **
0x1800880a7  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x1800880ac  mov     rcx, [rbp+57h+hKey]; hKey
0x1800880b0  mov     ebx, [rsp+110h+var_E0]
0x1800880b4  lea     rax, [rcx-1]
0x1800880b8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800880bc  ja      short loc_1800880CC
0x1800880be  call    cs:__imp_RegCloseKey
0x1800880c4  mov     [rbp+57h+hKey], 0
0x1800880cc  mov     rcx, [rbp+57h+arg_8]; hKey
0x1800880d0  lea     rdx, [rcx-1]
0x1800880d4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800880d8  ja      short loc_1800880E8
0x1800880da  call    cs:__imp_RegCloseKey
0x1800880e0  mov     [rbp+57h+arg_8], 0
0x1800880e8  lea     rcx, [rsp+110h+var_E0]; this
0x1800880ed  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800880f2  mov     eax, ebx
0x1800880f4  mov     rbx, [rsp+110h+arg_10]
0x1800880fc  add     rsp, 100h
0x180088103  pop     r12
0x180088105  pop     rdi
0x180088106  pop     rbp
0x180088107  retn
```
