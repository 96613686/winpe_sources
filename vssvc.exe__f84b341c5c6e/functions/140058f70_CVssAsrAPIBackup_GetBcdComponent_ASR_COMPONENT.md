# CVssAsrAPIBackup::GetBcdComponent(_ASR_COMPONENT *)

- ea: `0x140058f70`
- end: `0x14005947c`
- name: `?GetBcdComponent@CVssAsrAPIBackup@@UEAAJPEAU_ASR_COMPONENT@@@Z`
- size: `1292`
- prototype: `__int64 __fastcall(CVssAsrAPIBackup *__hidden this, struct _ASR_COMPONENT *)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x140010170`
- `0x140021ca0`
- `0x140022628`
- `0x1400227a0`
- `0x1400232ac`
- `0x1400235a8`
- `0x1400242a0`
- `0x14003ade4`
- `0x14005646c`
- `0x140058f70`
- `0x14005a228`
- `0x14005b208`
- `0x140091560`
- `0x1400916f0`
- `0x1400921dc`
- `0x1400d2554`
- `0x1400d257c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005943c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005943c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005905b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400592b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400592d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005905b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400592b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400592d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140059419`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140059419`

## string_xrefs

- `0x140058fa5`: `CVssAsrAPIBackup::GetBcdComponent`
- `0x14005942e`: `CVssAsrAPIBackup::GetBcdComponent`
- `0x1400593f5`: `pComponent`
- `0x1400591a8`: `DevicePathToWin32Path(wszSystemVolumePath, ARRAY_COUNT_PARAM(wszSystemVolumeWin32Path))`
- `0x140059066`: `AsrGetSystemVolumeDevPath(wszSystemVolumePath, ARRAYSIZE(wszSystemVolumePath))`
- `0x14005923a`: `::StringCchCat(ARRAY_COUNT_PARAM(wszSystemVolumeWin32Path), BCD_BOOT_ROOTPATH_EFI)`
- `0x140059292`: `::StringCchCat(ARRAY_COUNT_PARAM(wszSystemVolumeWin32Path), BCD_BOOT_ROOTPATH_BIOS)`
- `0x140059330`: `Component.pwszCaption`
- `0x140059384`: `Component.pwszPath`

## pseudocode

```c
__int64 __fastcall CVssAsrAPIBackup::GetBcdComponent(CVssAsrAPIBackup *this, struct _ASR_COMPONENT *a2)
{
  unsigned int v3; // edx
  int LastError; // ebx
  DWORD v5; // eax
  int v6; // edx
  int v7; // r9d
  struct _DRIVE_LAYOUT_INFORMATION_EX *v8; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  int v11; // r15d
  unsigned int v12; // ebx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  DWORD v20; // eax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v21; // rcx
  int v22; // edx
  const char *v23; // rax
  const char *v25; // [rsp+28h] [rbp-E0h]
  unsigned __int16 *pv; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID pv_8[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v28; // [rsp+50h] [rbp-B8h]
  __int128 v29; // [rsp+60h] [rbp-A8h]
  __int64 v30; // [rsp+70h] [rbp-98h]
  unsigned __int16 v31[264]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 v32; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v33[526]; // [rsp+28Ah] [rbp+182h] BYREF

  TraceFunctionEnter(L"CVssAsrAPIBackup::GetBcdComponent");
  *(_OWORD *)pv_8 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v32 = 0;
  memset_0(v33, 0, 0x206u);
  memset_0(v31, 0, 0x20Au);
  pv = 0;
  if ( a2 )
  {
    *(_OWORD *)a2 = 0;
    *((_OWORD *)a2 + 1) = 0;
    *((_OWORD *)a2 + 2) = 0;
    *((_QWORD *)a2 + 6) = 0;
    if ( (unsigned int)AsrGetSystemVolumeDevPath(&v32, v3) )
    {
      if ( !GetVolumeNameFromDeviceName(&v32, v31, 0x105u) || SystemGetFirmwareType() == FirmwareTypeUefi )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control )
        {
          if ( (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
          {
            WPP_SF_(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              16,
              WPP_f348c201c37c322fb5c01c43990311a7_Traceguids);
            v13 = WPP_GLOBAL_Control;
          }
          if ( v13 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (v13->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
          {
            WPP_SF_(*(_QWORD *)v13->Gpt.DiskId.Data4, 17, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids);
          }
        }
        v14 = StringCchPrintfW(v31, 0x105u, L"\\\\?\\GLOBALROOT%s", &v32);
        if ( v14 < 0 )
        {
          LastError = WIN32_FROM_HRESULT((unsigned int)v14);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v15 = StringCchPrintfW(v31, 0x105u, L"\\\\?\\GLOBALROOT%s", &v32);
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              18,
              (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
              v15,
              "DevicePathToWin32Path(wszSystemVolumePath, ARRAY_COUNT_PARAM(wszSystemVolumeWin32Path))");
          }
          goto LABEL_54;
        }
        v12 = 1;
        v11 = 15;
      }
      else
      {
        v31[1] = 92;
        v9 = -1;
        do
          ++v9;
        while ( v31[v9] );
        v10 = (unsigned int)(v9 - 1);
        if ( v31[v10] == 92 )
        {
          if ( v10 >= 261 )
            _report_rangecheckfailure(v10 * 2, 92);
          v31[(unsigned int)(v9 - 1)] = 0;
        }
        v11 = 3855;
        v12 = 0;
      }
      if ( SystemGetFirmwareType() == FirmwareTypeUefi )
      {
        v16 = StringCchCatW(v31, 0x105u, L"\\EFI\\Microsoft\\Boot");
        if ( v16 < 0 )
        {
          LastError = WIN32_FROM_HRESULT((unsigned int)v16);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v17 = StringCchCatW(v31, 0x105u, L"\\EFI\\Microsoft\\Boot");
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              19,
              (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
              v17,
              "::StringCchCat(ARRAY_COUNT_PARAM(wszSystemVolumeWin32Path), BCD_BOOT_ROOTPATH_EFI)");
          }
          goto LABEL_54;
        }
      }
      else
      {
        v18 = StringCchCatW(v31, 0x105u, L"\\Boot");
        if ( v18 < 0 )
        {
          LastError = WIN32_FROM_HRESULT((unsigned int)v18);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v19 = StringCchCatW(v31, 0x105u, L"\\Boot");
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              20,
              (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
              v19,
              "::StringCchCat(ARRAY_COUNT_PARAM(wszSystemVolumeWin32Path), BCD_BOOT_ROOTPATH_BIOS)");
          }
          goto LABEL_54;
        }
      }
      if ( !(unsigned int)SafeStrFormatResource(0xB004u, &pv) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v20 = GetLastError();
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            21,
            (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
            v20,
            "::GetLastError()");
        }
        goto LABEL_54;
      }
      *(_QWORD *)&v28 = SafeStrClone(pv);
      if ( (_QWORD)v28 )
      {
        *(_QWORD *)&v29 = v12;
        *((_QWORD *)&v29 + 1) = SafeStrClone(v31);
        if ( *((_QWORD *)&v29 + 1) )
        {
          LastError = 0;
          LODWORD(v30) = v11;
          *(_OWORD *)a2 = 0;
          *((_OWORD *)a2 + 1) = v28;
          *((_OWORD *)a2 + 2) = v29;
          *((_QWORD *)a2 + 6) = v30;
          *(_OWORD *)pv_8 = 0;
          v28 = 0;
          v29 = 0;
          v30 = 0;
          goto LABEL_54;
        }
        LastError = 14;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
        {
          goto LABEL_54;
        }
        v22 = 23;
        v23 = "Component.pwszPath";
      }
      else
      {
        LastError = 14;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
        {
          goto LABEL_54;
        }
        v22 = 22;
        v23 = "Component.pwszCaption";
      }
      WPP_SF_Ds(
        *(_QWORD *)v21->Gpt.DiskId.Data4,
        v22,
        (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
        14,
        v23);
      goto LABEL_54;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v5 = GetLastError();
      v6 = 15;
      v25 = "AsrGetSystemVolumeDevPath(wszSystemVolumePath, ARRAYSIZE(wszSystemVolumePath))";
      v7 = v5;
      v8 = WPP_GLOBAL_Control;
LABEL_53:
      WPP_SF_Ds(
        *(_QWORD *)v8->Gpt.DiskId.Data4,
        v6,
        (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
        v7,
        v25);
    }
  }
  else
  {
    LastError = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v6 = 14;
      v25 = "pComponent";
      v7 = 87;
      goto LABEL_53;
    }
  }
LABEL_54:
  CoTaskMemFree(pv);
  pv = 0;
  AsrFreeComponent((__int64)pv_8);
  TraceFunctionExit(L"CVssAsrAPIBackup::GetBcdComponent");
  SetLastError(LastError);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140058f70  mov     rax, rsp
0x140058f73  push    rbp
0x140058f74  push    rbx
0x140058f75  push    rsi
0x140058f76  push    rdi
0x140058f77  push    r12
0x140058f79  push    r13
0x140058f7b  push    r14
0x140058f7d  push    r15
0x140058f7f  lea     rbp, [rax-3F8h]
0x140058f86  sub     rsp, 4B8h
0x140058f8d  movaps  xmmword ptr [rax-58h], xmm6
0x140058f91  mov     rax, cs:__security_cookie
0x140058f98  xor     rax, rsp
0x140058f9b  mov     [rbp+3F0h+var_60], rax
0x140058fa2  mov     r14, rdx
0x140058fa5  lea     rcx, aCvssasrapiback_4; "CVssAsrAPIBackup::GetBcdComponent"
0x140058fac  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x140058fb1  xorps   xmm6, xmm6
0x140058fb4  xor     eax, eax
0x140058fb6  movups  xmmword ptr [rsp+4F0h+pv+8], xmm6
0x140058fbb  movups  [rsp+4F0h+var_4B0+8], xmm6
0x140058fc0  movups  [rsp+4F0h+var_4A0+8], xmm6
0x140058fc5  mov     qword ptr [rsp+4F0h+var_488], rax
0x140058fca  xor     r12d, r12d
0x140058fcd  mov     [rbp+3F0h+var_270], r12w
0x140058fd5  xor     edx, edx; Val
0x140058fd7  mov     r8d, 206h; Size
0x140058fdd  lea     rcx, [rbp+3F0h+var_26E]; void *
0x140058fe4  call    memset_0
0x140058fe9  mov     ebx, 20Ah
0x140058fee  mov     r8d, ebx; Size
0x140058ff1  xor     edx, edx; Val
0x140058ff3  lea     rcx, [rsp+4F0h+var_480]; void *
0x140058ff8  call    memset_0
0x140058ffd  mov     [rsp+4F0h+pv], r12
0x140059002  test    r14, r14
0x140059005  jz      loc_1400593D4
0x14005900b  xorps   xmm0, xmm0
0x14005900e  xor     eax, eax
0x140059010  movups  xmmword ptr [r14], xmm0
0x140059014  movups  xmmword ptr [r14+10h], xmm0
0x140059019  movups  xmmword ptr [r14+20h], xmm0
0x14005901e  mov     [r14+30h], rax
0x140059022  lea     rcx, [rbp+3F0h+var_270]; unsigned __int16 *
0x140059029  call    ?AsrGetSystemVolumeDevPath@@YAHPEAGK@Z; AsrGetSystemVolumeDevPath(ushort *,ulong)
0x14005902e  test    eax, eax
0x140059030  jnz     short loc_140059081
0x140059032  call    cs:__imp_GetLastError
0x140059038  mov     ebx, eax
0x14005903a  lea     rdi, WPP_GLOBAL_Control
0x140059041  mov     rax, cs:WPP_GLOBAL_Control
0x140059048  cmp     rax, rdi
0x14005904b  jz      loc_140059414
0x140059051  test    byte ptr [rax+1Ch], 8
0x140059055  jz      loc_140059414
0x14005905b  call    cs:__imp_GetLastError
0x140059061  lea     edx, [r12+0Fh]
0x140059066  lea     rcx, aAsrgetsystemvo_2; "AsrGetSystemVolumeDevPath(wszSystemVolu"...
0x14005906d  mov     [rsp+20h], rcx
0x140059072  mov     r9d, eax
0x140059075  mov     rcx, cs:WPP_GLOBAL_Control
0x14005907c  jmp     loc_140059404
0x140059081  mov     r13d, 105h
0x140059087  mov     r8d, r13d; unsigned int
0x14005908a  lea     rdx, [rsp+4F0h+var_480]; unsigned __int16 *
0x14005908f  lea     rcx, [rbp+3F0h+var_270]; unsigned __int16 *
0x140059096  call    ?GetVolumeNameFromDeviceName@@YAHPEBGPEAGK@Z; GetVolumeNameFromDeviceName(ushort const *,ushort *,ulong)
0x14005909b  lea     rdi, WPP_GLOBAL_Control
0x1400590a2  lea     rsi, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x1400590a9  test    eax, eax
0x1400590ab  jz      short loc_140059100
0x1400590ad  call    ?SystemGetFirmwareType@@YA?AW4_FIRMWARE_TYPE@@XZ; SystemGetFirmwareType(void)
0x1400590b2  cmp     eax, 2
0x1400590b5  jz      short loc_140059100
0x1400590b7  mov     edx, 5Ch ; '\'
0x1400590bc  mov     [rsp+4F0h+var_480+2], dx
0x1400590c1  lea     rcx, [rsp+4F0h+var_480]
0x1400590c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400590ca  inc     rax
0x1400590cd  cmp     [rcx+rax*2], r12w
0x1400590d2  jnz     short loc_1400590CA
0x1400590d4  lea     ecx, [rax-1]
0x1400590d7  add     rcx, rcx
0x1400590da  cmp     [rsp+rcx+4F0h+var_480], dx
0x1400590df  jnz     short loc_1400590EC
0x1400590e1  cmp     rcx, rbx
0x1400590e4  jnb     short loc_1400590FA
0x1400590e6  mov     [rsp+rcx+4F0h+var_480], r12w
0x1400590ec  mov     r15d, 0F0Fh
0x1400590f2  mov     ebx, r12d
0x1400590f5  jmp     loc_1400591D8
0x1400590fa  call    __report_rangecheckfailure
0x140059100  mov     rcx, cs:WPP_GLOBAL_Control
0x140059107  cmp     rcx, rdi
0x14005910a  jz      short loc_140059146
0x14005910c  test    byte ptr [rcx+1Ch], 2
0x140059110  jz      short loc_14005912A
0x140059112  mov     edx, 10h
0x140059117  mov     r8, rsi
0x14005911a  mov     rcx, [rcx+10h]
0x14005911e  call    WPP_SF_
0x140059123  mov     rcx, cs:WPP_GLOBAL_Control
0x14005912a  cmp     rcx, rdi
0x14005912d  jz      short loc_140059146
0x14005912f  test    byte ptr [rcx+1Ch], 2
0x140059133  jz      short loc_140059146
0x140059135  mov     edx, 11h
0x14005913a  mov     r8, rsi
0x14005913d  mov     rcx, [rcx+10h]
0x140059141  call    WPP_SF_
0x140059146  lea     r9, [rbp+3F0h+var_270]
0x14005914d  lea     r8, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x140059154  mov     rdx, r13; unsigned __int64
0x140059157  lea     rcx, [rsp+4F0h+var_480]; unsigned __int16 *
0x14005915c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140059161  test    eax, eax
0x140059163  jns     short loc_1400591CF
0x140059165  mov     ecx, eax
0x140059167  call    WIN32_FROM_HRESULT
0x14005916c  mov     ebx, eax
0x14005916e  mov     rax, cs:WPP_GLOBAL_Control
0x140059175  cmp     rax, rdi
0x140059178  jz      loc_140059414
0x14005917e  test    byte ptr [rax+1Ch], 8
0x140059182  jz      loc_140059414
0x140059188  lea     r9, [rbp+3F0h+var_270]
0x14005918f  lea     r8, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x140059196  mov     rdx, r13; unsigned __int64
0x140059199  lea     rcx, [rsp+4F0h+var_480]; unsigned __int16 *
0x14005919e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400591a3  mov     edx, 12h
0x1400591a8  lea     rcx, aDevicepathtowi_0; "DevicePathToWin32Path(wszSystemVolumePa"...
0x1400591af  mov     [rsp+20h], rcx
0x1400591b4  mov     r9d, eax
0x1400591b7  mov     r8, rsi
0x1400591ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591c1  mov     rcx, [rcx+10h]
0x1400591c5  call    WPP_SF_Ds
0x1400591ca  jmp     loc_140059414
0x1400591cf  mov     ebx, 1
0x1400591d4  lea     r15d, [rbx+0Eh]
0x1400591d8  call    ?SystemGetFirmwareType@@YA?AW4_FIRMWARE_TYPE@@XZ; SystemGetFirmwareType(void)
0x1400591dd  mov     rdx, r13; unsigned __int64
0x1400591e0  lea     rcx, [rsp+4F0h+var_480]; unsigned __int16 *
0x1400591e5  cmp     eax, 2
0x1400591e8  jnz     short loc_140059246
0x1400591ea  lea     r8, aEfiMicrosoftBo; "\\EFI\\Microsoft\\Boot"
0x1400591f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400591f6  test    eax, eax
0x1400591f8  jns     loc_14005929E
0x1400591fe  mov     ecx, eax
0x140059200  call    WIN32_FROM_HRESULT
0x140059205  mov     ebx, eax
0x140059207  mov     rax, cs:WPP_GLOBAL_Control
0x14005920e  cmp     rax, rdi
0x140059211  jz      loc_140059414
0x140059217  test    byte ptr [rax+1Ch], 8
0x14005921b  jz      loc_140059414
0x140059221  lea     r8, aEfiMicrosoftBo; "\\EFI\\Microsoft\\Boot"
0x140059228  mov     rdx, r13; unsigned __int64
0x14005922b  lea     rcx, [rsp+4F0h+var_480]; unsigned __int16 *
0x140059230  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140059235  mov     edx, 13h
0x14005923a  lea     rcx, aStringcchcatAr; "::StringCchCat(ARRAY_COUNT_PARAM(wszSys"...
0x140059241  jmp     loc_1400591AF
0x140059246  lea     r8, aBoot; "\\Boot"
0x14005924d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140059252  test    eax, eax
0x140059254  jns     short loc_14005929E
0x140059256  mov     ecx, eax
0x140059258  call    WIN32_FROM_HRESULT
0x14005925d  mov     ebx, eax
0x14005925f  mov     rax, cs:WPP_GLOBAL_Control
0x140059266  cmp     rax, rdi
0x140059269  jz      loc_140059414
0x14005926f  test    byte ptr [rax+1Ch], 8
0x140059273  jz      loc_140059414
0x140059279  lea     r8, aBoot; "\\Boot"
0x140059280  mov     rdx, r13; unsigned __int64
0x140059283  lea     rcx, [rsp+4F0h+var_480]; unsigned __int16 *
0x140059288  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005928d  mov     edx, 14h
0x140059292  lea     rcx, aStringcchcatAr_0; "::StringCchCat(ARRAY_COUNT_PARAM(wszSys"...
0x140059299  jmp     loc_1400591AF
0x14005929e  lea     rdx, [rsp+4F0h+pv]; unsigned __int16 **
0x1400592a3  mov     ecx, 0B004h; dwMessageId
0x1400592a8  call    ?SafeStrFormatResource@@YAHKPEAPEAGZZ; SafeStrFormatResource(ulong,ushort * *,...)
0x1400592ad  test    eax, eax
0x1400592af  jnz     short loc_1400592FC
0x1400592b1  call    cs:__imp_GetLastError
0x1400592b7  mov     ebx, eax
0x1400592b9  mov     rax, cs:WPP_GLOBAL_Control
0x1400592c0  cmp     rax, rdi
0x1400592c3  jz      loc_140059414
0x1400592c9  test    byte ptr [rax+1Ch], 8
0x1400592cd  jz      loc_140059414
0x1400592d3  call    cs:__imp_GetLastError
0x1400592d9  mov     edx, 15h
0x1400592de  lea     rcx, aGetlasterror_0; "::GetLastError()"
0x1400592e5  mov     [rsp+20h], rcx
0x1400592ea  mov     r9d, eax
0x1400592ed  mov     r8, rsi
0x1400592f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400592f7  jmp     loc_14005940B
0x1400592fc  mov     rcx, [rsp+4F0h+pv]; unsigned __int16 *
0x140059301  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x140059306  mov     qword ptr [rsp+4F0h+var_4B0+8], rax
0x14005930b  test    rax, rax
0x14005930e  jnz     short loc_140059347
0x140059310  lea     ebx, [rax+0Eh]
0x140059313  mov     rcx, cs:WPP_GLOBAL_Control
0x14005931a  cmp     rcx, rdi
0x14005931d  jz      loc_140059414
0x140059323  test    byte ptr [rcx+1Ch], 8
0x140059327  jz      loc_140059414
0x14005932d  lea     edx, [rax+16h]
0x140059330  lea     rax, aComponentPwszc_0; "Component.pwszCaption"
0x140059337  mov     [rsp+20h], rax
0x14005933c  mov     r9d, ebx
0x14005933f  mov     r8, rsi
0x140059342  jmp     loc_14005940B
0x140059347  mov     dword ptr [rsp+4F0h+var_4A0+8], ebx
0x14005934b  mov     dword ptr [rsp+4F0h+var_4A0+0Ch], r12d
0x140059350  lea     rcx, [rsp+4F0h+var_480]; unsigned __int16 *
0x140059355  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x14005935a  mov     [rsp+4F0h+var_490], rax
0x14005935f  test    rax, rax
0x140059362  jnz     short loc_14005938D
0x140059364  lea     ebx, [rax+0Eh]
0x140059367  mov     rcx, cs:WPP_GLOBAL_Control
0x14005936e  cmp     rcx, rdi
0x140059371  jz      loc_140059414
0x140059377  test    byte ptr [rcx+1Ch], 8
0x14005937b  jz      loc_140059414
0x140059381  lea     edx, [rax+17h]
0x140059384  lea     rax, aComponentPwszp; "Component.pwszPath"
0x14005938b  jmp     short loc_140059337
0x14005938d  mov     ebx, r12d
0x140059390  mov     dword ptr [rsp+4F0h+var_488], r15d
0x140059395  movups  xmmword ptr [r14], xmm6
0x140059399  movups  xmm0, [rsp+4F0h+var_4B0+8]
0x14005939e  movups  xmmword ptr [r14+10h], xmm0
0x1400593a3  movups  xmm1, [rsp+4F0h+var_4A0+8]
0x1400593a8  movups  xmmword ptr [r14+20h], xmm1
0x1400593ad  movsd   xmm0, qword ptr [rsp+4F0h+var_488]
0x1400593b3  movsd   qword ptr [r14+30h], xmm0
0x1400593b9  xorps   xmm1, xmm1
0x1400593bc  xor     eax, eax
0x1400593be  movups  xmmword ptr [rsp+4F0h+pv+8], xmm1
0x1400593c3  movups  [rsp+4F0h+var_4B0+8], xmm1
0x1400593c8  movups  [rsp+4F0h+var_4A0+8], xmm1
0x1400593cd  mov     qword ptr [rsp+4F0h+var_488], rax
0x1400593d2  jmp     short loc_140059414
0x1400593d4  mov     ebx, 57h ; 'W'
0x1400593d9  lea     rdi, WPP_GLOBAL_Control
0x1400593e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400593e7  cmp     rcx, rdi
0x1400593ea  jz      short loc_140059414
0x1400593ec  test    byte ptr [rcx+1Ch], 8
0x1400593f0  jz      short loc_140059414
0x1400593f2  lea     edx, [rbx-49h]
0x1400593f5  lea     rax, aPcomponent; "pComponent"
0x1400593fc  mov     [rsp+20h], rax
0x140059401  mov     r9d, ebx
0x140059404  lea     r8, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x14005940b  mov     rcx, [rcx+10h]
0x14005940f  call    WPP_SF_Ds
0x140059414  mov     rcx, [rsp+4F0h+pv]; pv
0x140059419  call    cs:__imp_CoTaskMemFree
0x14005941f  mov     [rsp+4F0h+pv], r12
0x140059424  lea     rcx, [rsp+4F0h+pv+8]
0x140059429  call    AsrFreeComponent
0x14005942e  lea     rcx, aCvssasrapiback_4; "CVssAsrAPIBackup::GetBcdComponent"
0x140059435  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x14005943a  mov     ecx, ebx; dwErrCode
0x14005943c  call    cs:__imp_SetLastError
0x140059442  test    ebx, ebx
0x140059444  jle     short loc_14005944F
0x140059446  movzx   ebx, bx
0x140059449  or      ebx, 80070000h
0x14005944f  mov     eax, ebx
0x140059451  mov     rcx, [rbp+3F0h+var_60]
0x140059458  xor     rcx, rsp; StackCookie
0x14005945b  call    __security_check_cookie
0x140059460  movaps  xmm6, [rsp+4F0h+var_58+8]
0x140059468  add     rsp, 4B8h
0x14005946f  pop     r15
0x140059471  pop     r14
0x140059473  pop     r13
0x140059475  pop     r12
0x140059477  pop     rdi
0x140059478  pop     rsi
0x140059479  pop     rbx
0x14005947a  pop     rbp
0x14005947b  retn
```
