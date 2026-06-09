# CSrDrvWuHelper::UpdateDriverWUInfoInCache(__int64)

- ea: `0x18000b3b0`
- end: `0x18000bbd9`
- name: `?UpdateDriverWUInfoInCache@CSrDrvWuHelper@@UEAAJ_J@Z`
- size: `2089`
- prototype: `__int64 __fastcall(CSrDrvWuHelper *this, __int64, __int64, unsigned __int16)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180002658`
- `0x180002818`
- `0x1800029d8`
- `0x180002e9c`
- `0x180003740`
- `0x180003854`
- `0x180003ce0`
- `0x180005df0`
- `0x18000b3b0`
- `0x18000c258`
- `0x18000ca98`
- `0x18000d17c`
- `0x18000d348`
- `0x18000d43c`
- `0x180014dd0`
- `0x180014f38`
- `0x180014fc4`
- `0x180015590`
- `0x180015760`
- `0x1800157be`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `SPP!SppFreeGroupPropArray` at `0x18000bb19`
- `SPP!SppFreeGroupPropArray` at `0x18000bb19`
- `KERNEL32!GetTickCount64` at `0x18000b8b4`
- `KERNEL32!GetTickCount64` at `0x18000ba8a`
- `KERNEL32!GetTickCount64` at `0x18000b8b4`
- `KERNEL32!GetTickCount64` at `0x18000ba8a`
- `ole32!CoCreateInstance` at `0x18000b5a4`
- `ole32!CoCreateInstance` at `0x18000b5a4`
- `ole32!CoTaskMemFree` at `0x18000b740`
- `ole32!CoTaskMemFree` at `0x18000bb05`
- `ole32!CoTaskMemFree` at `0x18000b740`
- `ole32!CoTaskMemFree` at `0x18000bb05`

## string_xrefs

- `0x18000b41a`: `CSrDrvWuHelper::UpdateDriverWUInfoInCache`
- `0x18000b51e`: `System Volume Information\SPP\SppGroupCache`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::UpdateDriverWUInfoInCache(
        CSrDrvWuHelper *this,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  unsigned __int16 ***v5; // rax
  __int64 v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned __int16 ***v9; // rax
  __int16 v10; // ax
  const unsigned __int16 *v11; // r9
  __int64 v12; // r8
  unsigned __int16 v13; // r9
  unsigned int i; // edi
  unsigned int v15; // ecx
  __int64 *v16; // r8
  unsigned int v17; // ebx
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  unsigned __int16 ***v21; // rax
  unsigned __int16 ***v22; // rax
  unsigned int v23; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v26; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v27; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v28; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v29; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v30; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v31; // [rsp+50h] [rbp-B0h]
  unsigned int v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v33; // [rsp+64h] [rbp-9Ch] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 j; // [rsp+80h] [rbp-80h]
  int WindirPathFromGroup; // [rsp+88h] [rbp-78h] BYREF
  __int16 v39; // [rsp+8Ch] [rbp-74h]
  __int16 v40; // [rsp+8Eh] [rbp-72h]
  unsigned __int16 **v41[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 **v42[2]; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID v43; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v44; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v46[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v47[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v48[2]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v49[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v50[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v51; // [rsp+150h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&WindirPathFromGroup,
    "CSrDrvWuHelper::UpdateDriverWUInfoInCache",
    0x57u,
    a4);
  v35 = 0;
  v32 = 0;
  v46[0] = (unsigned __int16 *)qword_18001A620;
  v5 = v41;
  v6 = 16;
  v46[1] = 0;
  v7 = 16;
  v33 = 0;
  pv = 0;
  *(_OWORD *)v41 = 0;
  v44 = (unsigned __int16 *)qword_18001A620;
  *(_OWORD *)v42 = 0;
  v45 = 0;
  v43 = 0;
  v49[0] = qword_18001A620;
  v49[1] = 0;
  v50[0] = qword_18001A620;
  v50[1] = 0;
  v47[0] = qword_18001A620;
  v47[1] = 0;
  v48[0] = qword_18001A620;
  v48[1] = 0;
  do
  {
    *(_BYTE *)v5 = 0;
    v5 = (unsigned __int16 ***)((char *)v5 + 1);
    --v7;
  }
  while ( v7 );
  v8 = 16;
  v9 = v42;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (unsigned __int16 ***)((char *)v9 + 1);
    --v8;
  }
  while ( v8 );
  v10 = 107;
  if ( a2 < 0 )
  {
    WindirPathFromGroup = -2147024809;
    goto LABEL_10;
  }
  WindirPathFromGroup = 0;
  v39 = 107;
  WindirPathFromGroup = CBsString::ExpandEnvironmentStringsW((CBsString *)v46, L"%SystemDrive%");
  v10 = 109;
  if ( WindirPathFromGroup < 0 )
    goto LABEL_10;
  v39 = 109;
  WindirPathFromGroup = CBsString::Append((CBsString *)&v44, v46[0]);
  v10 = 110;
  if ( WindirPathFromGroup < 0 )
    goto LABEL_10;
  v39 = 110;
  if ( !(_DWORD)v45 )
  {
    WindirPathFromGroup = -2147020579;
LABEL_16:
    v10 = 111;
    goto LABEL_10;
  }
  WindirPathFromGroup = CBsString::_CombinePathImpl(
                          (CBsString *)&v44,
                          L"System Volume Information\\SPP\\SppGroupCache",
                          0,
                          v11,
                          (const unsigned __int16 *)ppv,
                          v26,
                          v27,
                          v28,
                          v29,
                          v30,
                          v31);
  if ( WindirPathFromGroup < 0 )
    goto LABEL_16;
  v39 = 111;
  WindirPathFromGroup = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize(
                          (CBsString *)v49,
                          v44);
  v10 = 113;
  if ( WindirPathFromGroup >= 0 )
  {
    v39 = 113;
    WindirPathFromGroup = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize(
                            (CBsString *)v47,
                            v44,
                            v12,
                            v13);
    v10 = 114;
    if ( WindirPathFromGroup >= 0 )
    {
      v39 = 114;
      WindirPathFromGroup = CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, &v43);
      v10 = 116;
      if ( WindirPathFromGroup >= 0 )
      {
        v39 = 116;
        WindirPathFromGroup = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, __int64 *))(*(_QWORD *)v43 + 64LL))(
                                v43,
                                &v32,
                                &v35);
        v10 = 118;
        if ( WindirPathFromGroup >= 0 )
        {
          v39 = 118;
          WindirPathFromGroup = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::EnumUniqueIds(
                                  v49,
                                  &v33,
                                  &pv);
          if ( WindirPathFromGroup < 0 )
            WindirPathFromGroup = 0;
          for ( i = 0; i < v33; ++i )
          {
            v15 = v32;
            v16 = qword_18001A620;
            v36 = qword_18001A620;
            v17 = 0;
            for ( j = 0; v17 < v15; ++v17 )
            {
              v18 = 144LL * v17;
              if ( *(_QWORD *)(v18 + v35) == *((_QWORD *)pv + 2 * i)
                && *(_QWORD *)(v18 + v35 + 8) == *((_QWORD *)pv + 2 * i + 1) )
              {
                WindirPathFromGroup = CSrDrvWuHelper::_GetWindirPathFromGroup(
                                        (const struct _SPP_GROUP_PROP *)(v18 + v35),
                                        (struct CBsString *)&v36);
                if ( WindirPathFromGroup < 0 )
                {
                  v40 = 136;
                  CBsString::_Release((CBsString *)&v36);
                  goto LABEL_40;
                }
                v15 = v32;
                v39 = 136;
                if ( (_DWORD)j )
                  break;
                v16 = v36;
              }
            }
            if ( v17 == v15 )
            {
              v51 = *((_OWORD *)pv + i);
              v19 = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::DeleteDataFromCache(
                      v49,
                      &v51,
                      v16);
              WindirPathFromGroup = v19;
              if ( v19 < 0 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    11,
                    WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids,
                    (unsigned int)v19);
                }
                WindirPathFromGroup = 0;
              }
            }
            CBsString::_Release((CBsString *)&v36);
          }
          CoTaskMemFree(pv);
          pv = 0;
          CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::EnumUniqueIds(
            v47,
            &v33,
            &pv);
        }
      }
    }
  }
LABEL_10:
  v40 = v10;
LABEL_40:
  Free_StringArray((unsigned int *)v41, &v41[1]);
  v20 = 16;
  v21 = v41;
  do
  {
    *(_BYTE *)v21 = 0;
    v21 = (unsigned __int16 ***)((char *)v21 + 1);
    --v20;
  }
  while ( v20 );
  Free_StringArray((unsigned int *)v42, &v42[1]);
  v22 = v42;
  do
  {
    *(_BYTE *)v22 = 0;
    v22 = (unsigned __int16 ***)((char *)v22 + 1);
    --v6;
  }
  while ( v6 );
  CoTaskMemFree(pv);
  pv = 0;
  SppFreeGroupPropArray(v32, &v35);
  v23 = WindirPathFromGroup;
  CBsString::_Release((CBsString *)v48);
  CBsString::_Release((CBsString *)v47);
  CBsString::_Release((CBsString *)v50);
  CBsString::_Release((CBsString *)v49);
  if ( v43 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 16LL))(v43);
  CBsString::_Release((CBsString *)&v44);
  CBsString::_Release((CBsString *)v46);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&WindirPathFromGroup);
  return v23;
}

```

## disassembly

```asm
0x18000b3b0  push    rbp
0x18000b3b2  push    rbx
0x18000b3b3  push    rsi
0x18000b3b4  push    rdi
0x18000b3b5  push    r12
0x18000b3b7  push    r13
0x18000b3b9  push    r14
0x18000b3bb  push    r15
0x18000b3bd  lea     rbp, [rsp-0C8h]
0x18000b3c5  sub     rsp, 1C8h
0x18000b3cc  mov     rax, cs:__security_cookie
0x18000b3d3  xor     rax, rsp
0x18000b3d6  mov     [rbp+100h+var_50], rax
0x18000b3dd  mov     r12, rdx
0x18000b3e0  mov     r13, rcx
0x18000b3e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3ea  lea     rax, WPP_GLOBAL_Control
0x18000b3f1  cmp     rcx, rax
0x18000b3f4  jz      short loc_18000B414
0x18000b3f6  test    dword ptr [rcx+1Ch], 20000000h
0x18000b3fd  jz      short loc_18000B414
0x18000b3ff  mov     rcx, [rcx+10h]
0x18000b403  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000b40a  mov     edx, 0Ah
0x18000b40f  call    WPP_SF_
0x18000b414  mov     r8d, 57h ; 'W'; unsigned __int16
0x18000b41a  lea     rdx, aCsrdrvwuhelper_5; "CSrDrvWuHelper::UpdateDriverWUInfoInCac"...
0x18000b421  lea     rcx, [rbp+100h+var_178]; this
0x18000b425  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000b42a  xor     esi, esi
0x18000b42c  lea     rbx, qword_18001A620
0x18000b433  xorps   xmm0, xmm0
0x18000b436  mov     [rsp+200h+var_190], rsi
0x18000b43b  xorps   xmm1, xmm1
0x18000b43e  mov     [rsp+200h+var_1A0], esi
0x18000b442  mov     [rbp+100h+var_100], rbx
0x18000b446  lea     rax, [rbp+100h+var_138]
0x18000b44a  lea     r15d, [rsi+10h]
0x18000b44e  mov     [rbp+100h+var_F8], rsi
0x18000b452  mov     ecx, r15d
0x18000b455  mov     [rsp+200h+var_19C], esi
0x18000b459  mov     [rsp+200h+pv], rsi
0x18000b45e  movups  xmmword ptr [rbp+100h+var_138], xmm0
0x18000b462  mov     [rbp+100h+var_110], rbx
0x18000b466  movups  xmmword ptr [rbp+100h+var_128], xmm1
0x18000b46a  mov     [rbp+100h+var_108], rsi
0x18000b46e  mov     [rbp+100h+var_118], rsi
0x18000b472  mov     [rbp+100h+var_D0], rbx
0x18000b476  mov     [rbp+100h+var_C8], rsi
0x18000b47a  mov     [rbp+100h+var_C0], rbx
0x18000b47e  mov     [rbp+100h+var_B8], rsi
0x18000b482  mov     [rbp+100h+var_F0], rbx
0x18000b486  mov     [rbp+100h+var_E8], rsi
0x18000b48a  mov     [rbp+100h+var_E0], rbx
0x18000b48e  mov     [rbp+100h+var_D8], rsi
0x18000b492  mov     [rax], sil
0x18000b495  inc     rax
0x18000b498  sub     rcx, 1
0x18000b49c  jnz     short loc_18000B492
0x18000b49e  mov     rcx, r15
0x18000b4a1  lea     rax, [rbp+100h+var_128]
0x18000b4a5  mov     [rax], sil
0x18000b4a8  inc     rax
0x18000b4ab  sub     rcx, 1
0x18000b4af  jnz     short loc_18000B4A5
0x18000b4b1  lea     eax, [rcx+6Bh]
0x18000b4b4  test    r12, r12
0x18000b4b7  jns     short loc_18000B4C9
0x18000b4b9  mov     [rbp+100h+var_178], 80070057h
0x18000b4c0  mov     [rbp+100h+var_172], ax
0x18000b4c4  jmp     loc_18000BAC3
0x18000b4c9  lea     rdx, Src; "%SystemDrive%"
0x18000b4d0  mov     [rbp+100h+var_178], esi
0x18000b4d3  lea     rcx, [rbp+100h+var_100]; this
0x18000b4d7  mov     [rbp+100h+var_174], ax
0x18000b4db  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x18000b4e0  mov     [rbp+100h+var_178], eax
0x18000b4e3  test    eax, eax
0x18000b4e5  mov     eax, 6Dh ; 'm'
0x18000b4ea  js      short loc_18000B4C0
0x18000b4ec  mov     [rbp+100h+var_174], ax
0x18000b4f0  mov     rdx, [rbp+100h+var_100]; unsigned __int16 *
0x18000b4f4  lea     rcx, [rbp+100h+var_110]; this
0x18000b4f8  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000b4fd  mov     [rbp+100h+var_178], eax
0x18000b500  test    eax, eax
0x18000b502  mov     eax, 6Eh ; 'n'
0x18000b507  js      short loc_18000B4C0
0x18000b509  mov     [rbp+100h+var_174], ax
0x18000b50d  cmp     dword ptr [rbp+100h+var_108], esi
0x18000b510  jnz     short loc_18000B51B
0x18000b512  mov     [rbp+100h+var_178], 800710DDh
0x18000b519  jmp     short loc_18000B535
0x18000b51b  xor     r8d, r8d; unsigned __int16 *
0x18000b51e  lea     rdx, aSystemVolumeIn_0; "System Volume Information\\SPP\\SppGrou"...
0x18000b525  lea     rcx, [rbp+100h+var_110]; this
0x18000b529  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000b52e  mov     [rbp+100h+var_178], eax
0x18000b531  test    eax, eax
0x18000b533  jns     short loc_18000B53C
0x18000b535  mov     eax, 6Fh ; 'o'
0x18000b53a  jmp     short loc_18000B4C0
0x18000b53c  mov     rdx, [rbp+100h+var_110]; unsigned __int16 *
0x18000b540  lea     rcx, [rbp+100h+var_D0]; this
0x18000b544  mov     eax, 6Fh ; 'o'
0x18000b549  mov     [rbp+100h+var_174], ax
0x18000b54d  call    ?Initialize@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJPEBG0@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize(ushort const *,ushort const *)
0x18000b552  mov     [rbp+100h+var_178], eax
0x18000b555  test    eax, eax
0x18000b557  mov     eax, 71h ; 'q'
0x18000b55c  js      loc_18000B4C0
0x18000b562  mov     rdx, [rbp+100h+var_110]; unsigned __int16 *
0x18000b566  lea     rcx, [rbp+100h+var_F0]; this
0x18000b56a  mov     [rbp+100h+var_174], ax
0x18000b56e  call    ?Initialize@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJPEBG0@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize(ushort const *,ushort const *)
0x18000b573  mov     [rbp+100h+var_178], eax
0x18000b576  test    eax, eax
0x18000b578  mov     eax, 72h ; 'r'
0x18000b57d  js      loc_18000B4C0
0x18000b583  xor     edx, edx; pUnkOuter
0x18000b585  mov     [rbp+100h+var_174], ax
0x18000b589  lea     rax, [rbp+100h+var_118]
0x18000b58d  lea     r9, IID_ISharedProtectionPoints; riid
0x18000b594  mov     [rsp+200h+ppv], rax; ppv
0x18000b599  lea     rcx, CLSID_SPP; rclsid
0x18000b5a0  lea     r8d, [rdx+1]; dwClsContext
0x18000b5a4  call    cs:__imp_CoCreateInstance
0x18000b5aa  mov     [rbp+100h+var_178], eax
0x18000b5ad  test    eax, eax
0x18000b5af  mov     eax, 74h ; 't'
0x18000b5b4  js      loc_18000B4C0
0x18000b5ba  mov     rcx, [rbp+100h+var_118]
0x18000b5be  lea     r8, [rsp+200h+var_190]
0x18000b5c3  mov     [rbp+100h+var_174], ax
0x18000b5c7  lea     rdx, [rsp+200h+var_1A0]
0x18000b5cc  mov     rax, [rcx]
0x18000b5cf  mov     rax, [rax+40h]
0x18000b5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5d8  mov     [rbp+100h+var_178], eax
0x18000b5db  test    eax, eax
0x18000b5dd  mov     eax, 76h ; 'v'
0x18000b5e2  js      loc_18000B4C0
0x18000b5e8  lea     r8, [rsp+200h+pv]
0x18000b5ed  mov     [rbp+100h+var_174], ax
0x18000b5f1  lea     rdx, [rsp+200h+var_19C]
0x18000b5f6  mov     r14d, esi
0x18000b5f9  lea     rcx, [rbp+100h+var_D0]
0x18000b5fd  call    ?EnumUniqueIds@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJPEAKPEAPEAU_GUID@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::EnumUniqueIds(ulong *,_GUID * *)
0x18000b602  mov     [rbp+100h+var_178], eax
0x18000b605  test    eax, eax
0x18000b607  jns     short loc_18000B60F
0x18000b609  mov     [rbp+100h+var_178], esi
0x18000b60c  mov     r14d, eax
0x18000b60f  mov     edi, esi
0x18000b611  cmp     [rsp+200h+var_19C], esi
0x18000b615  jbe     loc_18000B73B
0x18000b61b  mov     ecx, [rsp+200h+var_1A0]
0x18000b61f  mov     r8, rbx
0x18000b622  mov     [rsp+200h+var_188], rbx
0x18000b627  mov     ebx, esi
0x18000b629  mov     [rbp+100h+var_180], rsi
0x18000b62d  test    ecx, ecx
0x18000b62f  jz      loc_18000B6B6
0x18000b635  mov     edx, dword ptr [rbp+100h+var_180]
0x18000b638  mov     esi, edi
0x18000b63a  add     rsi, rsi
0x18000b63d  mov     r11, [rsp+200h+var_190]
0x18000b642  mov     r10, [rsp+200h+pv]
0x18000b647  mov     eax, ebx
0x18000b649  lea     r9, [rax+rax*8]
0x18000b64d  shl     r9, 4
0x18000b651  mov     rax, [r9+r11]
0x18000b655  cmp     rax, [r10+rsi*8]
0x18000b659  jnz     short loc_18000B6AE
0x18000b65b  mov     rax, [r9+r11+8]
0x18000b660  cmp     rax, [r10+rsi*8+8]
0x18000b665  jnz     short loc_18000B6AE
0x18000b667  test    edx, edx
0x18000b669  jz      short loc_18000B678
0x18000b66b  xor     eax, eax
0x18000b66d  mov     dword ptr [rbp+100h+var_180], 0
0x18000b674  mov     [r8], ax
0x18000b678  mov     rcx, [rsp+200h+var_190]
0x18000b67d  lea     rdx, [rsp+200h+var_188]; struct CBsString *
0x18000b682  add     rcx, r9; struct _SPP_GROUP_PROP *
0x18000b685  call    ?_GetWindirPathFromGroup@CSrDrvWuHelper@@CAJPEBU_SPP_GROUP_PROP@@PEAVCBsString@@@Z; CSrDrvWuHelper::_GetWindirPathFromGroup(_SPP_GROUP_PROP const *,CBsString *)
0x18000b68a  mov     [rbp+100h+var_178], eax
0x18000b68d  test    eax, eax
0x18000b68f  mov     eax, 88h
0x18000b694  js      loc_18000B89F
0x18000b69a  mov     edx, dword ptr [rbp+100h+var_180]
0x18000b69d  mov     ecx, [rsp+200h+var_1A0]
0x18000b6a1  mov     [rbp+100h+var_174], ax
0x18000b6a5  test    edx, edx
0x18000b6a7  jnz     short loc_18000B6B4
0x18000b6a9  mov     r8, [rsp+200h+var_188]
0x18000b6ae  inc     ebx
0x18000b6b0  cmp     ebx, ecx
0x18000b6b2  jb      short loc_18000B63D
0x18000b6b4  xor     esi, esi
0x18000b6b6  cmp     ebx, ecx
0x18000b6b8  jnz     short loc_18000B71E
0x18000b6ba  mov     rax, [rsp+200h+pv]
0x18000b6bf  lea     rdx, [rbp+100h+var_B0]
0x18000b6c3  mov     ecx, edi
0x18000b6c5  add     rcx, rcx
0x18000b6c8  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000b6cc  lea     rcx, [rbp+100h+var_D0]
0x18000b6d0  movdqu  [rbp+100h+var_B0], xmm0
0x18000b6d5  call    ?DeleteDataFromCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJU_GUID@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::DeleteDataFromCache(_GUID)
0x18000b6da  mov     [rbp+100h+var_178], eax
0x18000b6dd  test    eax, eax
0x18000b6df  jns     short loc_18000B71E
0x18000b6e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6e8  lea     rdx, WPP_GLOBAL_Control
0x18000b6ef  cmp     rcx, rdx
0x18000b6f2  jz      short loc_18000B718
0x18000b6f4  test    dword ptr [rcx+1Ch], 4000000h
0x18000b6fb  jz      short loc_18000B718
0x18000b6fd  mov     rcx, [rcx+10h]
0x18000b701  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000b708  mov     edx, 0Bh
0x18000b70d  mov     r9d, eax
0x18000b710  call    WPP_SF_D
0x18000b715  mov     eax, [rbp+100h+var_178]
0x18000b718  mov     r14d, eax
0x18000b71b  mov     [rbp+100h+var_178], esi
0x18000b71e  lea     rcx, [rsp+200h+var_188]; this
0x18000b723  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000b728  inc     edi
0x18000b72a  lea     rbx, qword_18001A620
0x18000b731  cmp     edi, [rsp+200h+var_19C]
0x18000b735  jb      loc_18000B61B
0x18000b73b  mov     rcx, [rsp+200h+pv]; pv
0x18000b740  call    cs:__imp_CoTaskMemFree
0x18000b746  lea     r8, [rsp+200h+pv]
0x18000b74b  mov     [rsp+200h+pv], rsi
0x18000b750  lea     rdx, [rsp+200h+var_19C]
0x18000b755  lea     rcx, [rbp+100h+var_F0]
0x18000b759  call    ?EnumUniqueIds@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJPEAKPEAPEAU_GUID@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::EnumUniqueIds(ulong *,_GUID * *)
0x18000b75e  mov     [rbp+100h+var_178], eax
0x18000b761  test    eax, eax
0x18000b763  mov     eax, 0A2h
0x18000b768  js      loc_18000B4C0
0x18000b76e  mov     edi, esi
0x18000b770  mov     [rbp+100h+var_174], ax
0x18000b774  cmp     [rsp+200h+var_19C], esi
0x18000b778  jbe     loc_18000B8B4
0x18000b77e  mov     ecx, [rsp+200h+var_1A0]
0x18000b782  mov     r8, rbx
0x18000b785  mov     [rsp+200h+var_188], rbx
0x18000b78a  mov     ebx, esi
0x18000b78c  mov     [rbp+100h+var_180], rsi
0x18000b790  test    ecx, ecx
0x18000b792  jz      loc_18000B819
0x18000b798  mov     edx, dword ptr [rbp+100h+var_180]
0x18000b79b  mov     esi, edi
0x18000b79d  add     rsi, rsi
0x18000b7a0  mov     r11, [rsp+200h+var_190]
0x18000b7a5  mov     r10, [rsp+200h+pv]
0x18000b7aa  mov     eax, ebx
0x18000b7ac  lea     r9, [rax+rax*8]
0x18000b7b0  shl     r9, 4
0x18000b7b4  mov     rax, [r9+r11]
0x18000b7b8  cmp     rax, [r10+rsi*8]
0x18000b7bc  jnz     short loc_18000B811
0x18000b7be  mov     rax, [r9+r11+8]
0x18000b7c3  cmp     rax, [r10+rsi*8+8]
0x18000b7c8  jnz     short loc_18000B811
0x18000b7ca  test    edx, edx
0x18000b7cc  jz      short loc_18000B7DB
0x18000b7ce  xor     eax, eax
0x18000b7d0  mov     dword ptr [rbp+100h+var_180], 0
0x18000b7d7  mov     [r8], ax
0x18000b7db  mov     rcx, [rsp+200h+var_190]
0x18000b7e0  lea     rdx, [rsp+200h+var_188]; struct CBsString *
0x18000b7e5  add     rcx, r9; struct _SPP_GROUP_PROP *
0x18000b7e8  call    ?_GetWindirPathFromGroup@CSrDrvWuHelper@@CAJPEBU_SPP_GROUP_PROP@@PEAVCBsString@@@Z; CSrDrvWuHelper::_GetWindirPathFromGroup(_SPP_GROUP_PROP const *,CBsString *)
0x18000b7ed  mov     [rbp+100h+var_178], eax
0x18000b7f0  test    eax, eax
0x18000b7f2  mov     eax, 0ADh
0x18000b7f7  js      loc_18000B89F
0x18000b7fd  mov     edx, dword ptr [rbp+100h+var_180]
0x18000b800  mov     ecx, [rsp+200h+var_1A0]
0x18000b804  mov     [rbp+100h+var_174], ax
0x18000b808  test    edx, edx
0x18000b80a  jnz     short loc_18000B817
0x18000b80c  mov     r8, [rsp+200h+var_188]
0x18000b811  inc     ebx
0x18000b813  cmp     ebx, ecx
0x18000b815  jb      short loc_18000B7A0
0x18000b817  xor     esi, esi
0x18000b819  cmp     ebx, ecx
0x18000b81b  jnz     short loc_18000B881
0x18000b81d  mov     rax, [rsp+200h+pv]
0x18000b822  lea     rdx, [rbp+100h+var_B0]
0x18000b826  mov     ecx, edi
0x18000b828  add     rcx, rcx
0x18000b82b  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000b82f  lea     rcx, [rbp+100h+var_F0]
  ... truncated ...
```
