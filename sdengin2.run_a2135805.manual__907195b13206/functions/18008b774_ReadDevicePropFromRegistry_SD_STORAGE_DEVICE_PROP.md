# ReadDevicePropFromRegistry(_SD_STORAGE_DEVICE_PROP *)

- ea: `0x18008b774`
- end: `0x18008bb63`
- name: `?ReadDevicePropFromRegistry@@YAJPEAU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `1007`
- prototype: `__int64 __fastcall(struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005b46c`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x180073ad8`
- `0x18008b774`
- `0x18008c040`
- `0x180098a5c`
- `0x180099064`
- `0x1800cf56a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bb0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bb2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bb0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bb2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b80f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b87e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b80f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b87e`

## string_xrefs

- `0x18008b78c`: `ReadDevicePropFromRegistry`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&DWORD, "ReadDevicePropFromRegistry", 0x2F1u, 2u);
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
0x18008b774  mov     [rsp-8+arg_10], rbx
0x18008b779  push    rbp
0x18008b77a  push    rdi
0x18008b77b  push    r12
0x18008b77d  lea     rbp, [rsp-47h]
0x18008b782  sub     rsp, 100h
0x18008b789  mov     rdi, rcx
0x18008b78c  lea     rdx, aReaddeviceprop; "ReadDevicePropFromRegistry"
0x18008b793  lea     rcx, [rsp+110h+var_E0]; this
0x18008b798  mov     r9d, 2; unsigned __int16
0x18008b79e  mov     r8d, 2F1h; unsigned __int16
0x18008b7a4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008b7a9  xor     ebx, ebx
0x18008b7ab  lea     rcx, [rbp+57h+var_A0]; void *
0x18008b7af  mov     r12d, 90h
0x18008b7b5  mov     [rbp+57h+arg_8], rbx
0x18008b7b9  mov     r8d, r12d; Size
0x18008b7bc  mov     [rbp+57h+hKey], rbx
0x18008b7c0  xor     edx, edx; Val
0x18008b7c2  call    memset_0
0x18008b7c7  test    rdi, rdi
0x18008b7ca  jz      loc_18008BADF
0x18008b7d0  mov     ecx, r12d
0x18008b7d3  mov     rax, rdi
0x18008b7d6  mov     [rax], bl
0x18008b7d8  inc     rax
0x18008b7db  sub     rcx, 1
0x18008b7df  jnz     short loc_18008B7D6
0x18008b7e1  mov     eax, 2FAh
0x18008b7e6  mov     [rsp+110h+var_E0], ebx
0x18008b7ea  mov     [rsp+110h+var_DC], ax
0x18008b7ef  lea     rdx, c_wszSafedocsSchedulingKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008b7f6  lea     rax, [rbp+57h+arg_8]
0x18008b7fa  mov     r9d, 20019h; samDesired
0x18008b800  xor     r8d, r8d; ulOptions
0x18008b803  mov     [rsp+110h+phkResult], rax; phkResult
0x18008b808  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008b80f  call    cs:__imp_RegOpenKeyExW
0x18008b816  nop     dword ptr [rax+rax+00h]
0x18008b81b  mov     ebx, 80070000h
0x18008b820  test    eax, eax
0x18008b822  jle     short loc_18008B829
0x18008b824  movzx   eax, ax
0x18008b827  or      eax, ebx
0x18008b829  mov     [rsp+110h+var_E0], eax
0x18008b82d  test    eax, eax
0x18008b82f  mov     eax, 2FCh
0x18008b834  js      loc_18008BAEC
0x18008b83a  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b83e  mov     [rsp+110h+var_DC], ax
0x18008b843  lea     rax, [rcx-1]
0x18008b847  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008b84b  ja      short loc_18008B861
0x18008b84d  call    cs:__imp_RegCloseKey
0x18008b854  nop     dword ptr [rax+rax+00h]
0x18008b859  mov     [rbp+57h+hKey], 0
0x18008b861  mov     rcx, [rbp+57h+arg_8]; hKey
0x18008b865  lea     rax, [rbp+57h+hKey]
0x18008b869  mov     r9d, 20019h; samDesired
0x18008b86f  mov     [rsp+110h+phkResult], rax; phkResult
0x18008b874  xor     r8d, r8d; ulOptions
0x18008b877  lea     rdx, c_wszSafedocsDeviceTarget; "TargetDevice"
0x18008b87e  call    cs:__imp_RegOpenKeyExW
0x18008b885  nop     dword ptr [rax+rax+00h]
0x18008b88a  test    eax, eax
0x18008b88c  jle     short loc_18008B893
0x18008b88e  movzx   eax, ax
0x18008b891  or      eax, ebx
0x18008b893  mov     [rsp+110h+var_E0], eax
0x18008b897  test    eax, eax
0x18008b899  mov     eax, 2FDh
0x18008b89e  js      loc_18008BAEC
0x18008b8a4  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b8a8  lea     r8, [rbp+57h+var_70+8]; unsigned int *
0x18008b8ac  xor     r9d, r9d; int
0x18008b8af  mov     [rsp+110h+var_DC], ax
0x18008b8b4  lea     rdx, c_wszSafedocsDeviceType; "Type"
0x18008b8bb  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18008b8c0  mov     [rsp+110h+var_E0], eax
0x18008b8c4  test    eax, eax
0x18008b8c6  mov     eax, 2FFh
0x18008b8cb  js      loc_18008BAEC
0x18008b8d1  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b8d5  lea     r8, [rbp+57h+var_60]; unsigned __int64 *
0x18008b8d9  xor     r9d, r9d; int
0x18008b8dc  mov     [rsp+110h+var_DC], ax
0x18008b8e1  lea     rdx, c_wszSafedocsDeviceSize; "TotalSize"
0x18008b8e8  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18008b8ed  mov     [rsp+110h+var_E0], eax
0x18008b8f1  test    eax, eax
0x18008b8f3  mov     eax, 300h
0x18008b8f8  js      loc_18008BAEC
0x18008b8fe  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b902  lea     r8, [rbp+57h+var_60+8]; unsigned __int64 *
0x18008b906  xor     r9d, r9d; int
0x18008b909  mov     [rsp+110h+var_DC], ax
0x18008b90e  lea     rdx, c_wszSafedocsDeviceFree; "Freespace"
0x18008b915  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18008b91a  mov     [rsp+110h+var_E0], eax
0x18008b91e  test    eax, eax
0x18008b920  mov     eax, 301h
0x18008b925  js      loc_18008BAEC
0x18008b92b  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b92f  lea     r8, [rbp+57h+var_A0]; unsigned __int16 **
0x18008b933  xor     r9d, r9d; int
0x18008b936  mov     [rsp+110h+var_DC], ax
0x18008b93b  lea     rdx, c_wszSafedocsDevicePresentableName; "PresentableName"
0x18008b942  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18008b947  mov     [rsp+110h+var_E0], eax
0x18008b94b  test    eax, eax
0x18008b94d  mov     eax, 303h
0x18008b952  js      loc_18008BAEC
0x18008b958  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b95c  lea     r8, [rbp+57h+var_A0+8]; unsigned __int16 **
0x18008b960  xor     r9d, r9d; int
0x18008b963  mov     [rsp+110h+var_DC], ax
0x18008b968  lea     rdx, c_wszSafedocsDeviceUniqueName; "UniqueName"
0x18008b96f  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18008b974  mov     [rsp+110h+var_E0], eax
0x18008b978  test    eax, eax
0x18008b97a  mov     eax, 304h
0x18008b97f  js      loc_18008BAEC
0x18008b985  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b989  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x18008b98d  mov     r9d, 1; int
0x18008b993  mov     [rsp+110h+var_DC], ax
0x18008b998  lea     rdx, c_wszSafedocsDeviceLabel; "Label"
0x18008b99f  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18008b9a4  mov     [rsp+110h+var_E0], eax
0x18008b9a8  test    eax, eax
0x18008b9aa  mov     eax, 305h
0x18008b9af  js      loc_18008BAEC
0x18008b9b5  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b9b9  lea     r8, [rbp+57h+var_90+8]; unsigned __int16 **
0x18008b9bd  mov     r9d, 1; int
0x18008b9c3  mov     [rsp+110h+var_DC], ax
0x18008b9c8  lea     rdx, c_wszSafedocsDeviceVendor; "DeviceVendor"
0x18008b9cf  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18008b9d4  mov     [rsp+110h+var_E0], eax
0x18008b9d8  test    eax, eax
0x18008b9da  mov     eax, 307h
0x18008b9df  js      loc_18008BAEC
0x18008b9e5  mov     rcx, [rbp+57h+hKey]; hKey
0x18008b9e9  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x18008b9ed  mov     r9d, 1; int
0x18008b9f3  mov     [rsp+110h+var_DC], ax
0x18008b9f8  lea     rdx, c_wszSafedocsDeviceProduct; "DeviceProduct"
0x18008b9ff  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18008ba04  mov     [rsp+110h+var_E0], eax
0x18008ba08  test    eax, eax
0x18008ba0a  mov     eax, 308h
0x18008ba0f  js      loc_18008BAEC
0x18008ba15  mov     rcx, [rbp+57h+hKey]; hKey
0x18008ba19  lea     r8, [rbp+57h+var_80+8]; unsigned __int16 **
0x18008ba1d  mov     r9d, 1; int
0x18008ba23  mov     [rsp+110h+var_DC], ax
0x18008ba28  lea     rdx, c_wszSafedocsDeviceVersion; "DeviceVersion"
0x18008ba2f  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18008ba34  mov     [rsp+110h+var_E0], eax
0x18008ba38  test    eax, eax
0x18008ba3a  mov     eax, 309h
0x18008ba3f  js      loc_18008BAEC
0x18008ba45  mov     rcx, [rbp+57h+hKey]; hKey
0x18008ba49  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x18008ba4d  mov     r9d, 1; int
0x18008ba53  mov     [rsp+110h+var_DC], ax
0x18008ba58  lea     rdx, c_wszSafedocsDeviceSerial; "DeviceSerial"
0x18008ba5f  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18008ba64  mov     [rsp+110h+var_E0], eax
0x18008ba68  test    eax, eax
0x18008ba6a  jns     short loc_18008BA73
0x18008ba6c  mov     eax, 30Ah
0x18008ba71  jmp     short loc_18008BAEC
0x18008ba73  movaps  xmm0, xmmword ptr [rbp+57h+var_A0]
0x18008ba77  lea     rcx, [rbp+57h+var_A0]; void *
0x18008ba7b  movaps  xmm1, xmmword ptr [rbp+57h+var_90]
0x18008ba7f  mov     r8, r12; Size
0x18008ba82  movups  xmmword ptr [rdi], xmm0
0x18008ba85  xor     edx, edx; Val
0x18008ba87  movaps  xmm0, xmmword ptr [rbp+57h+var_80]
0x18008ba8b  movups  xmmword ptr [rdi+10h], xmm1
0x18008ba8f  movaps  xmm1, xmmword ptr [rbp+57h+var_70]
0x18008ba93  movups  xmmword ptr [rdi+20h], xmm0
0x18008ba97  movaps  xmm0, xmmword ptr [rbp+57h+var_60]
0x18008ba9b  movups  xmmword ptr [rdi+30h], xmm1
0x18008ba9f  movaps  xmm1, [rbp+57h+var_50]
0x18008baa3  movups  xmmword ptr [rdi+40h], xmm0
0x18008baa7  movaps  xmm0, [rbp+57h+var_40]
0x18008baab  movups  xmmword ptr [rdi+50h], xmm1
0x18008baaf  movaps  xmm1, [rbp+57h+var_30]
0x18008bab3  movups  xmmword ptr [rdi+60h], xmm0
0x18008bab7  movaps  xmm0, [rbp+57h+var_20]
0x18008babb  movups  xmmword ptr [rdi+70h], xmm1
0x18008babf  movups  xmmword ptr [rdi+80h], xmm0
0x18008bac6  call    memset_0
0x18008bacb  mov     eax, 315h
0x18008bad0  mov     [rsp+110h+var_E0], 0
0x18008bad8  mov     [rsp+110h+var_DC], ax
0x18008badd  jmp     short loc_18008BAF1
0x18008badf  mov     [rsp+110h+var_E0], 80070057h
0x18008bae7  mov     eax, 2FAh
0x18008baec  mov     [rsp+110h+var_DA], ax
0x18008baf1  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 **
0x18008baf5  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x18008bafa  mov     rcx, [rbp+57h+hKey]; hKey
0x18008bafe  mov     ebx, [rsp+110h+var_E0]
0x18008bb02  lea     rax, [rcx-1]
0x18008bb06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008bb0a  ja      short loc_18008BB20
0x18008bb0c  call    cs:__imp_RegCloseKey
0x18008bb13  nop     dword ptr [rax+rax+00h]
0x18008bb18  mov     [rbp+57h+hKey], 0
0x18008bb20  mov     rcx, [rbp+57h+arg_8]; hKey
0x18008bb24  lea     rdx, [rcx-1]
0x18008bb28  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18008bb2c  ja      short loc_18008BB42
0x18008bb2e  call    cs:__imp_RegCloseKey
0x18008bb35  nop     dword ptr [rax+rax+00h]
0x18008bb3a  mov     [rbp+57h+arg_8], 0
0x18008bb42  lea     rcx, [rsp+110h+var_E0]; this
0x18008bb47  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008bb4c  mov     eax, ebx
0x18008bb4e  mov     rbx, [rsp+110h+arg_10]
0x18008bb56  add     rsp, 100h
0x18008bb5d  pop     r12
0x18008bb5f  pop     rdi
0x18008bb60  pop     rbp
0x18008bb61  retn
```
