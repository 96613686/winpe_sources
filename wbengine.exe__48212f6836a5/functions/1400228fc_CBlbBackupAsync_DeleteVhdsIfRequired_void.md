# CBlbBackupAsync::DeleteVhdsIfRequired(void)

- ea: `0x1400228fc`
- end: `0x140022de5`
- name: `?DeleteVhdsIfRequired@CBlbBackupAsync@@AEAAJXZ`
- size: `1257`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000be04`
- `0x140014260`
- `0x140014384`
- `0x1400228fc`
- `0x140026dfc`
- `0x140028bf8`
- `0x14002c8dc`
- `0x14002ca68`
- `0x14008ca7c`
- `0x14008d3d8`
- `0x14008e8e8`
- `0x140098c04`
- `0x1400d6338`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400ff774`
- `0x140101c50`
- `0x14011bb4c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400229b2`
- `ole32!CoTaskMemFree` at `0x140022c3b`
- `ole32!CoTaskMemFree` at `0x140022c66`
- `ole32!CoTaskMemFree` at `0x140022d75`
- `ole32!CoTaskMemFree` at `0x140022d83`
- `ole32!CoTaskMemFree` at `0x140022d91`
- `ole32!CoTaskMemFree` at `0x140022d9f`
- `ole32!CoTaskMemFree` at `0x1400229b2`
- `ole32!CoTaskMemFree` at `0x140022c3b`
- `ole32!CoTaskMemFree` at `0x140022c66`
- `ole32!CoTaskMemFree` at `0x140022d75`
- `ole32!CoTaskMemFree` at `0x140022d83`
- `ole32!CoTaskMemFree` at `0x140022d91`
- `ole32!CoTaskMemFree` at `0x140022d9f`
- `OLEAUT32!__imp_SysFreeString` at `0x140022b9e`
- `OLEAUT32!__imp_SysFreeString` at `0x140022b9e`

## string_xrefs

- `0x140022c04`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::DeleteVhdsIfRequired(unsigned __int16 **this)
{
  unsigned __int16 **v1; // r12
  unsigned __int16 *v2; // r13
  unsigned __int16 *v3; // r14
  unsigned __int16 *v4; // r15
  int LastBackupInfoForIncremental; // edi
  __int64 i; // rax
  __int64 v7; // rsi
  unsigned __int16 *v8; // r8
  unsigned int v9; // edx
  CBlbImpersonationHelper *v10; // r12
  bool v11; // bl
  int FileAttributes; // eax
  int v13; // ebx
  __int64 *v14; // rax
  UINT v15; // ebx
  int VolumeFriendlyNameForPublisher; // eax
  void *v17; // r12
  unsigned __int16 *v19; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int16 *v21; // [rsp+40h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-30h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-28h] BYREF
  struct _GUID Buf1; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v26; // [rsp+C8h] [rbp+50h] BYREF
  int v27; // [rsp+D0h] [rbp+58h]
  int v28; // [rsp+D8h] [rbp+60h]

  v1 = this;
  v27 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 865, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v2 = 0;
  v3 = 0;
  v20 = 0;
  v4 = 0;
  v21 = 0;
  v19 = 0;
  pv = 0;
  LastBackupInfoForIncremental = CBlbBackupAsync::GetLastBackupInfoForIncremental(
                                   (CBlbBackupAsync *)v1,
                                   (struct _BLBCAT_BACKUP_SET_INFO **)&pv);
  if ( LastBackupInfoForIncremental >= 0 )
  {
    for ( i = 0; ; i = (unsigned int)(v28 + 1) )
    {
      v28 = i;
      if ( (unsigned int)i >= *((_DWORD *)v1 + 92) )
        break;
      v26 = 0;
      v7 = (__int64)&v1[27][184 * i];
      if ( v3 )
      {
        CoTaskMemFree(v3);
        v21 = 0;
      }
      v8 = v1[59];
      v9 = *(_DWORD *)(v7 + 84);
      Buf1 = *(struct _GUID *)(v7 + 68);
      LastBackupInfoForIncremental = BlbGetVhdPath(&Buf1, v9, v8, &v21);
      if ( LastBackupInfoForIncremental < 0
        || (v10 = (CBlbImpersonationHelper *)(v1 + 5),
            LastBackupInfoForIncremental = CBlbImpersonationHelper::ImpersonateCaller(v10, 0),
            LastBackupInfoForIncremental < 0) )
      {
        v3 = v21;
        break;
      }
      v3 = v21;
      v11 = FileExists(v21);
      CBlbImpersonationHelper::Revert(v10);
      if ( !v11 )
        goto LABEL_63;
      LastBackupInfoForIncremental = CBlbImpersonationHelper::ImpersonateCaller(v10, 0);
      if ( LastBackupInfoForIncremental < 0 )
        break;
      FileAttributes = BlbutilGetFileAttributes(v3, &v26);
      LastBackupInfoForIncremental = FileAttributes;
      if ( FileAttributes < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            866,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v3,
            FileAttributes);
        }
        break;
      }
      CBlbImpersonationHelper::Revert(v10);
      if ( !*(_DWORD *)(v7 + 360) && (v26 & 0x4000) != 0 )
        *(_DWORD *)(v7 + 360) = 5;
      if ( pv
        && CBlbVolumeBackupContext::IsSwitchToFullVolumeBackup(
             (CBlbVolumeBackupContext *)v7,
             (struct _BLBCAT_BACKUP_SET_INFO *)pv) )
      {
        *(_DWORD *)(v7 + 360) = 1;
      }
      if ( !*(_DWORD *)(v7 + 360) )
      {
        if ( (v26 & 0x800) != 0 )
        {
          *(_DWORD *)(v7 + 360) = 4;
        }
        else
        {
          LOBYTE(v26) = 0;
          LastBackupInfoForIncremental = CBlbVolumeBackupContext::IsVHDReadable(
                                           (CBlbVolumeBackupContext *)v7,
                                           this[59],
                                           v10,
                                           (unsigned __int8 *)&v26);
          if ( LastBackupInfoForIncremental < 0 )
            break;
          if ( (_BYTE)v26 )
            *(_DWORD *)(v7 + 360) = 3;
        }
        if ( !*(_DWORD *)(v7 + 360) )
        {
          LOBYTE(v26) = 0;
          LastBackupInfoForIncremental = CBlbVolumeBackupContext::HasVolumeSizeChanged(
                                           (CBlbVolumeBackupContext *)v7,
                                           v3,
                                           v10,
                                           (unsigned __int8 *)&v26);
          if ( LastBackupInfoForIncremental < 0 )
            break;
          if ( (_BYTE)v26 )
            *(_DWORD *)(v7 + 360) = 2;
        }
      }
      v13 = *(_DWORD *)(v7 + 360);
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v14 = (__int64 *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, (const struct _GUID *)(v7 + 68));
          v27 |= 1u;
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            867,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v3,
            *v14,
            v13);
        }
        if ( (v27 & 1) != 0 )
        {
          v27 &= ~1u;
          SysFreeString(bstrString[0]);
        }
        LastBackupInfoForIncremental = CBlbImpersonationHelper::ImpersonateCaller(v10, 0);
        if ( LastBackupInfoForIncremental < 0 )
          break;
        LastBackupInfoForIncremental = BlbutilDeleteFile(v3, 0, 0);
        if ( LastBackupInfoForIncremental < 0 )
          break;
        CBlbImpersonationHelper::Revert(v10);
        switch ( *(_DWORD *)(v7 + 360) )
        {
          case 1:
            v15 = 107;
            break;
          case 2:
            v15 = 108;
            break;
          case 3:
            v15 = 109;
            break;
          case 4:
            v15 = 110;
            break;
          case 5:
            v15 = 111;
            break;
          default:
            v15 = 0;
            BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x507Du, "FALSE");
            break;
        }
        if ( v4 )
        {
          CoTaskMemFree(v4);
          v19 = 0;
        }
        LastBackupInfoForIncremental = BlbLoadResourceString(v15, &v19);
        if ( LastBackupInfoForIncremental < 0 )
        {
          v4 = v19;
          break;
        }
        if ( v2 )
        {
          CoTaskMemFree(v2);
          v20 = 0;
        }
        v1 = this;
        VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                           v7 + 68,
                                           *(unsigned int *)(v7 + 84),
                                           *((unsigned int *)this + 84),
                                           &v20);
        v4 = v19;
        LastBackupInfoForIncremental = VolumeFriendlyNameForPublisher;
        v2 = v20;
        if ( VolumeFriendlyNameForPublisher < 0 )
          break;
        Buf1 = *(struct _GUID *)(v7 + 68);
        LastBackupInfoForIncremental = PublishDeleteVhdEvent(&Buf1, v20, v19);
        if ( LastBackupInfoForIncremental < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 868, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          }
          LastBackupInfoForIncremental = 0;
          break;
        }
      }
      else
      {
LABEL_63:
        v1 = this;
      }
    }
  }
  CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(this + 5));
  v17 = pv;
  if ( pv )
  {
    FreeBackupSetContents((struct _BLBCAT_BACKUP_SET_INFO *)pv);
    CoTaskMemFree(v17);
  }
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v2 )
    CoTaskMemFree(v2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 869, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)LastBackupInfoForIncremental;
}

```

## disassembly

```asm
0x1400228fc  mov     [rsp-40h+arg_0], rcx
0x140022901  push    rbp
0x140022902  push    rbx
0x140022903  push    rsi
0x140022904  push    rdi
0x140022905  push    r12
0x140022907  push    r13
0x140022909  push    r14
0x14002290b  push    r15
0x14002290d  mov     rbp, rsp
0x140022910  sub     rsp, 78h
0x140022914  mov     r12, rcx
0x140022917  mov     [rbp+arg_10], 0
0x14002291e  mov     rcx, cs:WPP_GLOBAL_Control
0x140022925  lea     rbx, WPP_GLOBAL_Control
0x14002292c  cmp     rcx, rbx
0x14002292f  jz      short loc_140022952
0x140022931  test    byte ptr [rcx+1Ch], 1
0x140022935  jz      short loc_140022952
0x140022937  cmp     byte ptr [rcx+19h], 4
0x14002293b  jb      short loc_140022952
0x14002293d  mov     rcx, [rcx+10h]
0x140022941  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140022948  mov     edx, 361h
0x14002294d  call    WPP_SF_
0x140022952  xor     r13d, r13d
0x140022955  lea     rdx, [rbp+pv]; struct _BLBCAT_BACKUP_SET_INFO **
0x140022959  xor     r14d, r14d
0x14002295c  mov     [rbp+var_40], r13
0x140022960  xor     r15d, r15d
0x140022963  mov     [rbp+var_38], r14
0x140022967  mov     rcx, r12; this
0x14002296a  mov     [rbp+var_48], r15
0x14002296e  mov     [rbp+pv], r13
0x140022972  call    ?GetLastBackupInfoForIncremental@CBlbBackupAsync@@QEAAJPEAPEAU_BLBCAT_BACKUP_SET_INFO@@@Z; CBlbBackupAsync::GetLastBackupInfoForIncremental(_BLBCAT_BACKUP_SET_INFO * *)
0x140022977  mov     edi, eax
0x140022979  test    eax, eax
0x14002297b  js      loc_140022D54
0x140022981  xor     eax, eax
0x140022983  mov     [rbp+arg_18], eax
0x140022986  cmp     eax, [r12+170h]
0x14002298e  jnb     loc_140022D4D
0x140022994  imul    rsi, rax, 170h
0x14002299b  mov     [rbp+arg_8], 0
0x1400229a2  add     rsi, [r12+0D8h]
0x1400229aa  test    r14, r14
0x1400229ad  jz      short loc_1400229C0
0x1400229af  mov     rcx, r14; pv
0x1400229b2  call    cs:__imp_CoTaskMemFree
0x1400229b8  mov     [rbp+var_38], 0
0x1400229c0  movups  xmm0, xmmword ptr [rsi+44h]
0x1400229c4  mov     r8, [r12+1D8h]; unsigned __int16 *
0x1400229cc  lea     r9, [rbp+var_38]; unsigned __int16 **
0x1400229d0  mov     edx, [rsi+54h]; unsigned int
0x1400229d3  lea     rcx, [rbp+Buf1]; Buf1
0x1400229d7  movdqu  xmmword ptr [rbp+Buf1.Data1], xmm0
0x1400229dc  call    ?BlbGetVhdPath@@YAJU_GUID@@KPEAGPEAPEAG@Z; BlbGetVhdPath(_GUID,ulong,ushort *,ushort * *)
0x1400229e1  mov     edi, eax
0x1400229e3  test    eax, eax
0x1400229e5  js      loc_140022D49
0x1400229eb  add     r12, 28h ; '('
0x1400229ef  xor     edx, edx; unsigned __int8
0x1400229f1  mov     rcx, r12; this
0x1400229f4  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x1400229f9  mov     edi, eax
0x1400229fb  test    eax, eax
0x1400229fd  js      loc_140022D49
0x140022a03  mov     r14, [rbp+var_38]
0x140022a07  mov     rcx, r14; unsigned __int16 *
0x140022a0a  call    ?FileExists@@YA_NPEAG@Z; FileExists(ushort *)
0x140022a0f  mov     rcx, r12; this
0x140022a12  mov     bl, al
0x140022a14  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140022a19  test    bl, bl
0x140022a1b  jz      loc_140022CF8
0x140022a21  xor     edx, edx; unsigned __int8
0x140022a23  mov     rcx, r12; this
0x140022a26  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x140022a2b  mov     edi, eax
0x140022a2d  test    eax, eax
0x140022a2f  js      loc_140022D4D
0x140022a35  lea     rdx, [rbp+arg_8]; unsigned int *
0x140022a39  mov     rcx, r14; unsigned __int16 *
0x140022a3c  call    ?BlbutilGetFileAttributes@@YAJPEAGPEAK@Z; BlbutilGetFileAttributes(ushort *,ulong *)
0x140022a41  mov     edi, eax
0x140022a43  test    eax, eax
0x140022a45  js      loc_140022D0C
0x140022a4b  mov     rcx, r12; this
0x140022a4e  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140022a53  cmp     dword ptr [rsi+168h], 0
0x140022a5a  jnz     short loc_140022A6F
0x140022a5c  test    [rbp+arg_8], 4000h
0x140022a63  jz      short loc_140022A6F
0x140022a65  mov     dword ptr [rsi+168h], 5
0x140022a6f  mov     rax, [rbp+pv]
0x140022a73  test    rax, rax
0x140022a76  jz      short loc_140022A91
0x140022a78  mov     rdx, rax; struct _BLBCAT_BACKUP_SET_INFO *
0x140022a7b  mov     rcx, rsi; this
0x140022a7e  call    ?IsSwitchToFullVolumeBackup@CBlbVolumeBackupContext@@QEAAEPEAU_BLBCAT_BACKUP_SET_INFO@@@Z; CBlbVolumeBackupContext::IsSwitchToFullVolumeBackup(_BLBCAT_BACKUP_SET_INFO *)
0x140022a83  test    al, al
0x140022a85  jz      short loc_140022A91
0x140022a87  mov     dword ptr [rsi+168h], 1
0x140022a91  cmp     dword ptr [rsi+168h], 0
0x140022a98  jnz     loc_140022B24
0x140022a9e  test    [rbp+arg_8], 800h
0x140022aa5  jz      short loc_140022AB3
0x140022aa7  mov     dword ptr [rsi+168h], 4
0x140022ab1  jmp     short loc_140022AEB
0x140022ab3  mov     rdx, [rbp+arg_0]
0x140022ab7  lea     r9, [rbp+arg_8]; unsigned __int8 *
0x140022abb  mov     r8, r12; struct CBlbImpersonationHelper *
0x140022abe  mov     byte ptr [rbp+arg_8], 0
0x140022ac2  mov     rcx, rsi; this
0x140022ac5  mov     rdx, [rdx+1D8h]; unsigned __int16 *
0x140022acc  call    ?IsVHDReadable@CBlbVolumeBackupContext@@QEAAJPEAGPEAVCBlbImpersonationHelper@@PEAE@Z; CBlbVolumeBackupContext::IsVHDReadable(ushort *,CBlbImpersonationHelper *,uchar *)
0x140022ad1  mov     edi, eax
0x140022ad3  test    eax, eax
0x140022ad5  js      loc_140022D4D
0x140022adb  cmp     byte ptr [rbp+arg_8], 0
0x140022adf  jz      short loc_140022AEB
0x140022ae1  mov     dword ptr [rsi+168h], 3
0x140022aeb  cmp     dword ptr [rsi+168h], 0
0x140022af2  jnz     short loc_140022B24
0x140022af4  lea     r9, [rbp+arg_8]; unsigned __int8 *
0x140022af8  mov     byte ptr [rbp+arg_8], 0
0x140022afc  mov     r8, r12; struct CBlbImpersonationHelper *
0x140022aff  mov     rdx, r14; unsigned __int16 *
0x140022b02  mov     rcx, rsi; this
0x140022b05  call    ?HasVolumeSizeChanged@CBlbVolumeBackupContext@@QEAAJPEAGPEAVCBlbImpersonationHelper@@PEAE@Z; CBlbVolumeBackupContext::HasVolumeSizeChanged(ushort *,CBlbImpersonationHelper *,uchar *)
0x140022b0a  mov     edi, eax
0x140022b0c  test    eax, eax
0x140022b0e  js      loc_140022D4D
0x140022b14  cmp     byte ptr [rbp+arg_8], 0
0x140022b18  jz      short loc_140022B24
0x140022b1a  mov     dword ptr [rsi+168h], 2
0x140022b24  mov     ebx, [rsi+168h]
0x140022b2a  test    ebx, ebx
0x140022b2c  jz      loc_140022CF8
0x140022b32  mov     rax, cs:WPP_GLOBAL_Control
0x140022b39  lea     rcx, WPP_GLOBAL_Control
0x140022b40  cmp     rax, rcx
0x140022b43  jz      short loc_140022B8D
0x140022b45  test    byte ptr [rax+1Ch], 1
0x140022b49  jz      short loc_140022B8D
0x140022b4b  cmp     byte ptr [rax+19h], 4
0x140022b4f  jb      short loc_140022B8D
0x140022b51  lea     rdx, [rsi+44h]; struct _GUID *
0x140022b55  lea     rcx, [rbp+bstrString]; this
0x140022b59  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x140022b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140022b65  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140022b6c  or      [rbp+arg_10], 1
0x140022b70  mov     edx, 363h
0x140022b75  mov     [rsp+78h+var_50], ebx
0x140022b79  mov     r9, r14
0x140022b7c  mov     rax, [rax]
0x140022b7f  mov     rcx, [rcx+10h]
0x140022b83  mov     [rsp+78h+var_58], rax
0x140022b88  call    WPP_SF_SSD
0x140022b8d  mov     eax, [rbp+arg_10]
0x140022b90  test    al, 1
0x140022b92  jz      short loc_140022BA4
0x140022b94  mov     rcx, [rbp+bstrString]; bstrString
0x140022b98  and     eax, 0FFFFFFFEh
0x140022b9b  mov     [rbp+arg_10], eax
0x140022b9e  call    cs:__imp_SysFreeString
0x140022ba4  xor     edx, edx; unsigned __int8
0x140022ba6  mov     rcx, r12; this
0x140022ba9  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x140022bae  mov     edi, eax
0x140022bb0  test    eax, eax
0x140022bb2  js      loc_140022D4D
0x140022bb8  xor     r8d, r8d; unsigned __int8 *
0x140022bbb  xor     edx, edx; unsigned int *
0x140022bbd  mov     rcx, r14; unsigned __int16 *
0x140022bc0  call    ?BlbutilDeleteFile@@YAJPEAGPEAKPEAE@Z; BlbutilDeleteFile(ushort *,ulong *,uchar *)
0x140022bc5  mov     edi, eax
0x140022bc7  test    eax, eax
0x140022bc9  js      loc_140022D4D
0x140022bcf  mov     rcx, r12; this
0x140022bd2  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140022bd7  mov     ecx, [rsi+168h]
0x140022bdd  sub     ecx, 1
0x140022be0  jz      short loc_140022C2E
0x140022be2  sub     ecx, 1
0x140022be5  jz      short loc_140022C27
0x140022be7  sub     ecx, 1
0x140022bea  jz      short loc_140022C20
0x140022bec  sub     ecx, 1
0x140022bef  jz      short loc_140022C19
0x140022bf1  cmp     ecx, 1
0x140022bf4  jz      short loc_140022C12
0x140022bf6  xor     ebx, ebx
0x140022bf8  lea     r8, aFalse_1; "FALSE"
0x140022bff  mov     edx, 507Dh; unsigned int
0x140022c04  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140022c0b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140022c10  jmp     short loc_140022C33
0x140022c12  mov     ebx, 6Fh ; 'o'
0x140022c17  jmp     short loc_140022C33
0x140022c19  mov     ebx, 6Eh ; 'n'
0x140022c1e  jmp     short loc_140022C33
0x140022c20  mov     ebx, 6Dh ; 'm'
0x140022c25  jmp     short loc_140022C33
0x140022c27  mov     ebx, 6Ch ; 'l'
0x140022c2c  jmp     short loc_140022C33
0x140022c2e  mov     ebx, 6Bh ; 'k'
0x140022c33  test    r15, r15
0x140022c36  jz      short loc_140022C49
0x140022c38  mov     rcx, r15; pv
0x140022c3b  call    cs:__imp_CoTaskMemFree
0x140022c41  mov     [rbp+var_48], 0
0x140022c49  lea     rdx, [rbp+var_48]; unsigned __int16 **
0x140022c4d  mov     ecx, ebx; uID
0x140022c4f  call    ?BlbLoadResourceString@@YAJIPEAPEAG@Z; BlbLoadResourceString(uint,ushort * *)
0x140022c54  mov     edi, eax
0x140022c56  test    eax, eax
0x140022c58  js      loc_140022D06
0x140022c5e  test    r13, r13
0x140022c61  jz      short loc_140022C74
0x140022c63  mov     rcx, r13; pv
0x140022c66  call    cs:__imp_CoTaskMemFree
0x140022c6c  mov     [rbp+var_40], 0
0x140022c74  mov     r12, [rbp+arg_0]
0x140022c78  lea     r9, [rbp+var_40]
0x140022c7c  mov     edx, [rsi+54h]
0x140022c7f  lea     rcx, [rsi+44h]
0x140022c83  mov     r8d, [r12+150h]
0x140022c8b  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAU_GUID@@KW4_BLB_MEDIA_TYPE@@PEAPEAG@Z; GetVolumeFriendlyNameForPublisher(_GUID *,ulong,_BLB_MEDIA_TYPE,ushort * *)
0x140022c90  mov     r15, [rbp+var_48]
0x140022c94  mov     edi, eax
0x140022c96  mov     r13, [rbp+var_40]
0x140022c9a  test    eax, eax
0x140022c9c  js      loc_140022D4D
0x140022ca2  movups  xmm0, xmmword ptr [rsi+44h]
0x140022ca6  mov     r8, r15; unsigned __int16 *
0x140022ca9  lea     rcx, [rbp+Buf1]; struct _GUID
0x140022cad  mov     rdx, r13; unsigned __int16 *
0x140022cb0  movdqu  xmmword ptr [rbp+Buf1.Data1], xmm0
0x140022cb5  call    ?PublishDeleteVhdEvent@@YAJU_GUID@@PEAG1@Z; PublishDeleteVhdEvent(_GUID,ushort *,ushort *)
0x140022cba  mov     edi, eax
0x140022cbc  test    eax, eax
0x140022cbe  jns     short loc_140022CFC
0x140022cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140022cc7  lea     rbx, WPP_GLOBAL_Control
0x140022cce  cmp     rcx, rbx
0x140022cd1  jz      short loc_140022CF4
0x140022cd3  test    byte ptr [rcx+1Ch], 1
0x140022cd7  jz      short loc_140022CF4
0x140022cd9  cmp     byte ptr [rcx+19h], 3
0x140022cdd  jb      short loc_140022CF4
0x140022cdf  mov     rcx, [rcx+10h]
0x140022ce3  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140022cea  mov     edx, 364h
0x140022cef  call    WPP_SF_
0x140022cf4  xor     edi, edi
0x140022cf6  jmp     short loc_140022D54
0x140022cf8  mov     r12, [rbp+arg_0]
0x140022cfc  mov     eax, [rbp+arg_18]
0x140022cff  inc     eax
0x140022d01  jmp     loc_140022983
0x140022d06  mov     r15, [rbp+var_48]
0x140022d0a  jmp     short loc_140022D4D
0x140022d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d13  lea     rbx, WPP_GLOBAL_Control
0x140022d1a  cmp     rcx, rbx
0x140022d1d  jz      short loc_140022D54
0x140022d1f  test    byte ptr [rcx+1Ch], 1
0x140022d23  jz      short loc_140022D54
0x140022d25  cmp     byte ptr [rcx+19h], 2
0x140022d29  jb      short loc_140022D54
0x140022d2b  mov     rcx, [rcx+10h]
0x140022d2f  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140022d36  mov     edx, 362h
0x140022d3b  mov     dword ptr [rsp+78h+var_58], eax
0x140022d3f  mov     r9, r14
0x140022d42  call    WPP_SF_Sd
0x140022d47  jmp     short loc_140022D54
0x140022d49  mov     r14, [rbp+var_38]
0x140022d4d  lea     rbx, WPP_GLOBAL_Control
0x140022d54  mov     rcx, [rbp+arg_0]
0x140022d58  add     rcx, 28h ; '('; this
0x140022d5c  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140022d61  mov     r12, [rbp+pv]
0x140022d65  test    r12, r12
0x140022d68  jz      short loc_140022D7B
0x140022d6a  mov     rcx, r12; struct _BLBCAT_BACKUP_SET_INFO *
0x140022d6d  call    ?FreeBackupSetContents@@YAXPEAU_BLBCAT_BACKUP_SET_INFO@@@Z; FreeBackupSetContents(_BLBCAT_BACKUP_SET_INFO *)
0x140022d72  mov     rcx, r12; pv
0x140022d75  call    cs:__imp_CoTaskMemFree
0x140022d7b  test    r15, r15
0x140022d7e  jz      short loc_140022D89
0x140022d80  mov     rcx, r15; pv
0x140022d83  call    cs:__imp_CoTaskMemFree
0x140022d89  test    r14, r14
0x140022d8c  jz      short loc_140022D97
0x140022d8e  mov     rcx, r14; pv
0x140022d91  call    cs:__imp_CoTaskMemFree
0x140022d97  test    r13, r13
  ... truncated ...
```
