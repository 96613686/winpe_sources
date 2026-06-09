# LoadBlockedTargetVolumes(CSxStringList *)

- ea: `0x18000f2b4`
- end: `0x18000f5bc`
- name: `?LoadBlockedTargetVolumes@@YAJPEAVCSxStringList@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(struct CSxStringList *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011274`

## callees

- `0x180008240`
- `0x18000b56c`
- `0x18000d984`
- `0x18000f2b4`
- `0x180012914`
- `0x180012a04`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180091e04`
- `0x1800948bc`
- `0x180099a50`
- `0x18009a24c`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f384`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f57a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f384`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f57a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f3b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f3b0`
- `ole32!CoTaskMemFree` at `0x18000f54b`
- `ole32!CoTaskMemFree` at `0x18000f54b`

## pseudocode

```c
__int64 __fastcall LoadBlockedTargetVolumes(struct CSxStringList *a1)
{
  struct CSxStringEntry *v2; // rbx
  unsigned __int16 *v3; // rsi
  __int16 v4; // ax
  int v5; // eax
  unsigned __int16 *v6; // r14
  const unsigned __int16 **v7; // rdi
  __int16 v8; // ax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // edi
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  struct CSxStringEntry *v14; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v15; // [rsp+40h] [rbp-C0h] BYREF
  int inserted; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-B4h]
  __int16 v18; // [rsp+4Eh] [rbp-B2h]
  _QWORD v19[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v20; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szVolumeName; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[526]; // [rsp+A2h] [rbp-5Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&inserted, "LoadBlockedTargetVolumes", 3072, 1);
  hKey = 0;
  v19[0] = qword_1800E8530;
  v19[1] = 0;
  v2 = 0;
  v14 = 0;
  v20 = GUID_NULL;
  v3 = 0;
  v15 = 0;
  szVolumeName = 0;
  memset_0(v22, 0, 0x208u);
  if ( a1 )
  {
    while ( !(unsigned int)CSxList<CSxStringList,CSxStringEntry>::RemoveHead(a1, 0) )
      ;
    inserted = 0;
    v17 = 3087;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
           0,
           0x20019u,
           &hKey) )
    {
      v4 = 3095;
LABEL_7:
      inserted = 1;
      v17 = v4;
      goto LABEL_31;
    }
    v5 = SxRegReadMultiString(hKey, L"BlockedTargetVolumes", &v15);
    v3 = v15;
    if ( v5 < 0 )
    {
      v4 = 3100;
      goto LABEL_7;
    }
    v6 = v15;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !*v6 )
          goto LABEL_31;
        if ( v2 )
        {
          v14 = 0;
          CSxStringEntry::Release(v2);
        }
        inserted = CSxStringEntry::CreateInstance(&v14);
        v2 = v14;
        if ( inserted < 0 )
        {
          v18 = 3109;
          goto LABEL_31;
        }
        v17 = 3109;
        v7 = (const unsigned __int16 **)((char *)v14 + 8);
        inserted = CBsString::Set((struct CSxStringEntry *)((char *)v14 + 8), v6);
        v8 = 3110;
        if ( inserted < 0 )
          goto LABEL_30;
        v17 = 3110;
        v6 += (unsigned int)(*((_DWORD *)v2 + 4) + 1);
        if ( CBsString::ConvertVolumePathToGuid((struct CSxStringEntry *)((char *)v2 + 8), &v20) >= 0 )
          break;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v10 = 32;
          goto LABEL_20;
        }
      }
      if ( (int)SxGetUniqueVolumeForPath(*v7, &szVolumeName) >= 0 )
      {
        inserted = CBsString::Set((struct CSxStringEntry *)((char *)v2 + 8), &szVolumeName);
        v8 = 3132;
        if ( inserted < 0 )
          goto LABEL_30;
        v17 = 3132;
        inserted = CSxList<CSxExtensionSetList,CSxExtensionSet>::InsertTail(a1, v2);
        v8 = 3133;
        if ( inserted < 0 )
          goto LABEL_30;
        v17 = 3133;
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v10 = 33;
LABEL_20:
          WPP_SF_S(v9[2], v10, &WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids, *v7);
        }
      }
    }
  }
  inserted = -2147024809;
  v8 = 3087;
LABEL_30:
  v18 = v8;
LABEL_31:
  CoTaskMemFree(v3);
  v11 = inserted;
  if ( v2 )
    CSxStringEntry::Release(v2);
  CBsString::_Release((CBsString *)v19);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&inserted);
  return v11;
}

```

## disassembly

```asm
0x18000f2b4  mov     [rsp-8+arg_8], rbx
0x18000f2b9  mov     [rsp-8+arg_10], rsi
0x18000f2be  push    rbp
0x18000f2bf  push    rdi
0x18000f2c0  push    r12
0x18000f2c2  push    r14
0x18000f2c4  push    r15
0x18000f2c6  lea     rbp, [rsp-1C0h]
0x18000f2ce  sub     rsp, 2C0h
0x18000f2d5  mov     rax, cs:__security_cookie
0x18000f2dc  xor     rax, rsp
0x18000f2df  mov     [rbp+1E0h+var_30], rax
0x18000f2e6  mov     r15, rcx
0x18000f2e9  mov     r9d, 1; unsigned __int16
0x18000f2ef  mov     r8d, 0C00h; unsigned __int16
0x18000f2f5  lea     rdx, aLoadblockedtar; "LoadBlockedTargetVolumes"
0x18000f2fc  lea     rcx, [rsp+2E0h+var_298]; this
0x18000f301  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f306  xor     r12d, r12d
0x18000f309  mov     [rsp+2E0h+hKey], r12
0x18000f30e  lea     rax, qword_1800E8530
0x18000f315  mov     [rbp+1E0h+var_260], rax
0x18000f319  mov     [rbp+1E0h+var_258], r12
0x18000f31d  mov     ebx, r12d
0x18000f320  mov     [rsp+2E0h+var_2A8], rbx
0x18000f325  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000f32c  movdqu  xmmword ptr [rbp+1E0h+var_250.Data1], xmm0
0x18000f331  mov     esi, r12d
0x18000f334  mov     [rsp+2E0h+var_2A0], r12
0x18000f339  mov     [rbp+1E0h+szVolumeName], r12w
0x18000f33e  xor     edx, edx; Val
0x18000f340  mov     r8d, 208h; Size
0x18000f346  lea     rcx, [rbp+1E0h+var_23E]; void *
0x18000f34a  call    memset_0
0x18000f34f  test    r15, r15
0x18000f352  jz      loc_18000F536
0x18000f358  xor     edx, edx
0x18000f35a  mov     rcx, r15
0x18000f35d  call    ?RemoveHead@?$CSxList@VCSxStringList@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxList<CSxStringList,CSxStringEntry>::RemoveHead(CSxStringEntry * *)
0x18000f362  test    eax, eax
0x18000f364  jz      short loc_18000F358
0x18000f366  mov     [rsp+2E0h+var_298], r12d
0x18000f36b  mov     eax, 0C0Fh
0x18000f370  mov     [rsp+2E0h+var_294], ax
0x18000f375  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000f37a  lea     rax, [rcx-1]
0x18000f37e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f382  ja      short loc_18000F38F
0x18000f384  call    cs:__imp_RegCloseKey
0x18000f38a  mov     [rsp+2E0h+hKey], r12
0x18000f38f  lea     rax, [rsp+2E0h+hKey]
0x18000f394  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000f399  mov     r9d, 20019h; samDesired
0x18000f39f  xor     r8d, r8d; ulOptions
0x18000f3a2  lea     rdx, c_wszSafedocsUser_Key; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000f3a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f3b0  call    cs:__imp_RegOpenKeyExW
0x18000f3b6  test    eax, eax
0x18000f3b8  jz      short loc_18000F3D1
0x18000f3ba  mov     eax, 0C17h
0x18000f3bf  mov     [rsp+2E0h+var_298], 1
0x18000f3c7  mov     [rsp+2E0h+var_294], ax
0x18000f3cc  jmp     loc_18000F548
0x18000f3d1  lea     r8, [rsp+2E0h+var_2A0]; unsigned __int16 **
0x18000f3d6  lea     rdx, c_wszBlockTargetVolumes; "BlockedTargetVolumes"
0x18000f3dd  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000f3e2  call    ?SxRegReadMultiString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; SxRegReadMultiString(HKEY__ *,ushort const *,ushort * *)
0x18000f3e7  mov     rsi, [rsp+2E0h+var_2A0]
0x18000f3ec  test    eax, eax
0x18000f3ee  jns     short loc_18000F3F7
0x18000f3f0  mov     eax, 0C1Ch
0x18000f3f5  jmp     short loc_18000F3BF
0x18000f3f7  mov     r14, rsi
0x18000f3fa  mov     edi, 0C25h
0x18000f3ff  cmp     [r14], r12w
0x18000f403  jz      loc_18000F548
0x18000f409  test    rbx, rbx
0x18000f40c  jz      short loc_18000F41B
0x18000f40e  mov     [rsp+2E0h+var_2A8], r12
0x18000f413  mov     rcx, rbx; this
0x18000f416  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x18000f41b  lea     rcx, [rsp+2E0h+var_2A8]; struct CSxStringEntry **
0x18000f420  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x18000f425  mov     [rsp+2E0h+var_298], eax
0x18000f429  mov     rbx, [rsp+2E0h+var_2A8]
0x18000f42e  test    eax, eax
0x18000f430  js      loc_18000F52F
0x18000f436  mov     [rsp+2E0h+var_294], di
0x18000f43b  lea     rdi, [rbx+8]
0x18000f43f  mov     rdx, r14; unsigned __int16 *
0x18000f442  mov     rcx, rdi; this
0x18000f445  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000f44a  mov     [rsp+2E0h+var_298], eax
0x18000f44e  test    eax, eax
0x18000f450  mov     eax, 0C26h
0x18000f455  js      loc_18000F543
0x18000f45b  mov     [rsp+2E0h+var_294], ax
0x18000f460  mov     eax, [rbx+10h]
0x18000f463  inc     eax
0x18000f465  lea     r14, [r14+rax*2]
0x18000f469  lea     rdx, [rbp+1E0h+var_250]; struct _GUID *
0x18000f46d  mov     rcx, rdi; this
0x18000f470  call    ?ConvertVolumePathToGuid@CBsString@@QEAAJPEAU_GUID@@@Z; CBsString::ConvertVolumePathToGuid(_GUID *)
0x18000f475  test    eax, eax
0x18000f477  jns     short loc_18000F4B7
0x18000f479  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f480  lea     rax, WPP_GLOBAL_Control
0x18000f487  cmp     rcx, rax
0x18000f48a  jz      loc_18000F3FA
0x18000f490  test    byte ptr [rcx+1Ch], 40h
0x18000f494  jz      loc_18000F3FA
0x18000f49a  mov     edx, 20h ; ' '
0x18000f49f  mov     r9, [rdi]
0x18000f4a2  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000f4a9  mov     rcx, [rcx+10h]
0x18000f4ad  call    WPP_SF_S
0x18000f4b2  jmp     loc_18000F3FA
0x18000f4b7  lea     rdx, [rbp+1E0h+szVolumeName]; lpszVolumeName
0x18000f4bb  mov     rcx, [rdi]; unsigned __int16 *
0x18000f4be  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x18000f4c3  test    eax, eax
0x18000f4c5  jns     short loc_18000F4EF
0x18000f4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4ce  lea     rax, WPP_GLOBAL_Control
0x18000f4d5  cmp     rcx, rax
0x18000f4d8  jz      loc_18000F3FA
0x18000f4de  test    byte ptr [rcx+1Ch], 40h
0x18000f4e2  jz      loc_18000F3FA
0x18000f4e8  mov     edx, 21h ; '!'
0x18000f4ed  jmp     short loc_18000F49F
0x18000f4ef  lea     rdx, [rbp+1E0h+szVolumeName]; unsigned __int16 *
0x18000f4f3  mov     rcx, rdi; this
0x18000f4f6  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000f4fb  mov     [rsp+2E0h+var_298], eax
0x18000f4ff  test    eax, eax
0x18000f501  mov     eax, 0C3Ch
0x18000f506  js      short loc_18000F543
0x18000f508  mov     [rsp+2E0h+var_294], ax
0x18000f50d  mov     rdx, rbx
0x18000f510  mov     rcx, r15
0x18000f513  call    ?InsertTail@?$CSxList@VCSxExtensionSetList@@VCSxExtensionSet@@@@QEAAJPEAVCSxExtensionSet@@@Z; CSxList<CSxExtensionSetList,CSxExtensionSet>::InsertTail(CSxExtensionSet *)
0x18000f518  mov     [rsp+2E0h+var_298], eax
0x18000f51c  test    eax, eax
0x18000f51e  mov     eax, 0C3Dh
0x18000f523  js      short loc_18000F543
0x18000f525  mov     [rsp+2E0h+var_294], ax
0x18000f52a  jmp     loc_18000F3FA
0x18000f52f  mov     [rsp+2E0h+var_292], di
0x18000f534  jmp     short loc_18000F548
0x18000f536  mov     [rsp+2E0h+var_298], 80070057h
0x18000f53e  mov     eax, 0C0Fh
0x18000f543  mov     [rsp+2E0h+var_292], ax
0x18000f548  mov     rcx, rsi; pv
0x18000f54b  call    cs:__imp_CoTaskMemFree
0x18000f551  mov     edi, [rsp+2E0h+var_298]
0x18000f555  test    rbx, rbx
0x18000f558  jz      short loc_18000F562
0x18000f55a  mov     rcx, rbx; this
0x18000f55d  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x18000f562  lea     rcx, [rbp+1E0h+var_260]; this
0x18000f566  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000f56b  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000f570  lea     rdx, [rcx-1]
0x18000f574  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000f578  ja      short loc_18000F585
0x18000f57a  call    cs:__imp_RegCloseKey
0x18000f580  mov     [rsp+2E0h+hKey], r12
0x18000f585  lea     rcx, [rsp+2E0h+var_298]; this
0x18000f58a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f58f  mov     eax, edi
0x18000f591  mov     rcx, [rbp+1E0h+var_30]
0x18000f598  xor     rcx, rsp; StackCookie
0x18000f59b  call    __security_check_cookie
0x18000f5a0  lea     r11, [rsp+2E0h+var_20]
0x18000f5a8  mov     rbx, [r11+38h]
0x18000f5ac  mov     rsi, [r11+40h]
0x18000f5b0  mov     rsp, r11
0x18000f5b3  pop     r15
0x18000f5b5  pop     r14
0x18000f5b7  pop     r12
0x18000f5b9  pop     rdi
0x18000f5ba  pop     rbp
0x18000f5bb  retn
```
