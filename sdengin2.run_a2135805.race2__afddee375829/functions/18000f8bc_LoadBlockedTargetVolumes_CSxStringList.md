# LoadBlockedTargetVolumes(CSxStringList *)

- ea: `0x18000f8bc`
- end: `0x18000fbdd`
- name: `?LoadBlockedTargetVolumes@@YAJPEAVCSxStringList@@@Z`
- size: `801`
- prototype: `__int64 __fastcall(struct CSxStringList *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800119c4`

## callees

- `0x1800083e4`
- `0x18000b894`
- `0x18000de10`
- `0x18000f8bc`
- `0x18001316c`
- `0x180013260`
- `0x180072e08`
- `0x180072f14`
- `0x180095fd4`
- `0x180098bc8`
- `0x18009e098`
- `0x18009e904`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f98c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f98c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f9be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f9be`
- `ole32!CoTaskMemFree` at `0x18000fb5f`
- `ole32!CoTaskMemFree` at `0x18000fb5f`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&inserted, "LoadBlockedTargetVolumes", 0xC00u, 1u);
  hKey = 0;
  v19[0] = qword_1800EE510;
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
0x18000f8bc  mov     [rsp-8+arg_8], rbx
0x18000f8c1  mov     [rsp-8+arg_10], rsi
0x18000f8c6  push    rbp
0x18000f8c7  push    rdi
0x18000f8c8  push    r12
0x18000f8ca  push    r14
0x18000f8cc  push    r15
0x18000f8ce  lea     rbp, [rsp-1C0h]
0x18000f8d6  sub     rsp, 2C0h
0x18000f8dd  mov     rax, cs:__security_cookie
0x18000f8e4  xor     rax, rsp
0x18000f8e7  mov     [rbp+1E0h+var_30], rax
0x18000f8ee  mov     r15, rcx
0x18000f8f1  mov     r9d, 1; unsigned __int16
0x18000f8f7  mov     r8d, 0C00h; unsigned __int16
0x18000f8fd  lea     rdx, aLoadblockedtar; "LoadBlockedTargetVolumes"
0x18000f904  lea     rcx, [rsp+2E0h+var_298]; this
0x18000f909  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f90e  xor     r12d, r12d
0x18000f911  mov     [rsp+2E0h+hKey], r12
0x18000f916  lea     rax, qword_1800EE510
0x18000f91d  mov     [rbp+1E0h+var_260], rax
0x18000f921  mov     [rbp+1E0h+var_258], r12
0x18000f925  mov     ebx, r12d
0x18000f928  mov     [rsp+2E0h+var_2A8], rbx
0x18000f92d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000f934  movdqu  xmmword ptr [rbp+1E0h+var_250.Data1], xmm0
0x18000f939  mov     esi, r12d
0x18000f93c  mov     [rsp+2E0h+var_2A0], r12
0x18000f941  mov     [rbp+1E0h+szVolumeName], r12w
0x18000f946  xor     edx, edx; Val
0x18000f948  mov     r8d, 208h; Size
0x18000f94e  lea     rcx, [rbp+1E0h+var_23E]; void *
0x18000f952  call    memset_0
0x18000f957  test    r15, r15
0x18000f95a  jz      loc_18000FB4A
0x18000f960  xor     edx, edx
0x18000f962  mov     rcx, r15
0x18000f965  call    ?RemoveHead@?$CSxList@VCSxStringList@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxList<CSxStringList,CSxStringEntry>::RemoveHead(CSxStringEntry * *)
0x18000f96a  test    eax, eax
0x18000f96c  jz      short loc_18000F960
0x18000f96e  mov     [rsp+2E0h+var_298], r12d
0x18000f973  mov     eax, 0C0Fh
0x18000f978  mov     [rsp+2E0h+var_294], ax
0x18000f97d  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000f982  lea     rax, [rcx-1]
0x18000f986  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f98a  ja      short loc_18000F99D
0x18000f98c  call    cs:__imp_RegCloseKey
0x18000f993  nop     dword ptr [rax+rax+00h]
0x18000f998  mov     [rsp+2E0h+hKey], r12
0x18000f99d  lea     rax, [rsp+2E0h+hKey]
0x18000f9a2  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000f9a7  mov     r9d, 20019h; samDesired
0x18000f9ad  xor     r8d, r8d; ulOptions
0x18000f9b0  lea     rdx, c_wszSafedocsUser_Key; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000f9b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f9be  call    cs:__imp_RegOpenKeyExW
0x18000f9c5  nop     dword ptr [rax+rax+00h]
0x18000f9ca  test    eax, eax
0x18000f9cc  jz      short loc_18000F9E5
0x18000f9ce  mov     eax, 0C17h
0x18000f9d3  mov     [rsp+2E0h+var_298], 1
0x18000f9db  mov     [rsp+2E0h+var_294], ax
0x18000f9e0  jmp     loc_18000FB5C
0x18000f9e5  lea     r8, [rsp+2E0h+var_2A0]; unsigned __int16 **
0x18000f9ea  lea     rdx, c_wszBlockTargetVolumes; "BlockedTargetVolumes"
0x18000f9f1  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000f9f6  call    ?SxRegReadMultiString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; SxRegReadMultiString(HKEY__ *,ushort const *,ushort * *)
0x18000f9fb  mov     rsi, [rsp+2E0h+var_2A0]
0x18000fa00  test    eax, eax
0x18000fa02  jns     short loc_18000FA0B
0x18000fa04  mov     eax, 0C1Ch
0x18000fa09  jmp     short loc_18000F9D3
0x18000fa0b  mov     r14, rsi
0x18000fa0e  mov     edi, 0C25h
0x18000fa13  cmp     [r14], r12w
0x18000fa17  jz      loc_18000FB5C
0x18000fa1d  test    rbx, rbx
0x18000fa20  jz      short loc_18000FA2F
0x18000fa22  mov     [rsp+2E0h+var_2A8], r12
0x18000fa27  mov     rcx, rbx; this
0x18000fa2a  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x18000fa2f  lea     rcx, [rsp+2E0h+var_2A8]; struct CSxStringEntry **
0x18000fa34  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x18000fa39  mov     [rsp+2E0h+var_298], eax
0x18000fa3d  mov     rbx, [rsp+2E0h+var_2A8]
0x18000fa42  test    eax, eax
0x18000fa44  js      loc_18000FB43
0x18000fa4a  mov     [rsp+2E0h+var_294], di
0x18000fa4f  lea     rdi, [rbx+8]
0x18000fa53  mov     rdx, r14; unsigned __int16 *
0x18000fa56  mov     rcx, rdi; this
0x18000fa59  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000fa5e  mov     [rsp+2E0h+var_298], eax
0x18000fa62  test    eax, eax
0x18000fa64  mov     eax, 0C26h
0x18000fa69  js      loc_18000FB57
0x18000fa6f  mov     [rsp+2E0h+var_294], ax
0x18000fa74  mov     eax, [rbx+10h]
0x18000fa77  inc     eax
0x18000fa79  lea     r14, [r14+rax*2]
0x18000fa7d  lea     rdx, [rbp+1E0h+var_250]; struct _GUID *
0x18000fa81  mov     rcx, rdi; this
0x18000fa84  call    ?ConvertVolumePathToGuid@CBsString@@QEAAJPEAU_GUID@@@Z; CBsString::ConvertVolumePathToGuid(_GUID *)
0x18000fa89  test    eax, eax
0x18000fa8b  jns     short loc_18000FACB
0x18000fa8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa94  lea     rax, WPP_GLOBAL_Control
0x18000fa9b  cmp     rcx, rax
0x18000fa9e  jz      loc_18000FA0E
0x18000faa4  test    byte ptr [rcx+1Ch], 40h
0x18000faa8  jz      loc_18000FA0E
0x18000faae  mov     edx, 20h ; ' '
0x18000fab3  mov     r9, [rdi]
0x18000fab6  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000fabd  mov     rcx, [rcx+10h]
0x18000fac1  call    WPP_SF_S
0x18000fac6  jmp     loc_18000FA0E
0x18000facb  lea     rdx, [rbp+1E0h+szVolumeName]; lpszVolumeName
0x18000facf  mov     rcx, [rdi]; unsigned __int16 *
0x18000fad2  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x18000fad7  test    eax, eax
0x18000fad9  jns     short loc_18000FB03
0x18000fadb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fae2  lea     rax, WPP_GLOBAL_Control
0x18000fae9  cmp     rcx, rax
0x18000faec  jz      loc_18000FA0E
0x18000faf2  test    byte ptr [rcx+1Ch], 40h
0x18000faf6  jz      loc_18000FA0E
0x18000fafc  mov     edx, 21h ; '!'
0x18000fb01  jmp     short loc_18000FAB3
0x18000fb03  lea     rdx, [rbp+1E0h+szVolumeName]; unsigned __int16 *
0x18000fb07  mov     rcx, rdi; this
0x18000fb0a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000fb0f  mov     [rsp+2E0h+var_298], eax
0x18000fb13  test    eax, eax
0x18000fb15  mov     eax, 0C3Ch
0x18000fb1a  js      short loc_18000FB57
0x18000fb1c  mov     [rsp+2E0h+var_294], ax
0x18000fb21  mov     rdx, rbx
0x18000fb24  mov     rcx, r15
0x18000fb27  call    ?InsertTail@?$CSxList@VCSxExtensionSetList@@VCSxExtensionSet@@@@QEAAJPEAVCSxExtensionSet@@@Z; CSxList<CSxExtensionSetList,CSxExtensionSet>::InsertTail(CSxExtensionSet *)
0x18000fb2c  mov     [rsp+2E0h+var_298], eax
0x18000fb30  test    eax, eax
0x18000fb32  mov     eax, 0C3Dh
0x18000fb37  js      short loc_18000FB57
0x18000fb39  mov     [rsp+2E0h+var_294], ax
0x18000fb3e  jmp     loc_18000FA0E
0x18000fb43  mov     [rsp+2E0h+var_292], di
0x18000fb48  jmp     short loc_18000FB5C
0x18000fb4a  mov     [rsp+2E0h+var_298], 80070057h
0x18000fb52  mov     eax, 0C0Fh
0x18000fb57  mov     [rsp+2E0h+var_292], ax
0x18000fb5c  mov     rcx, rsi; pv
0x18000fb5f  call    cs:__imp_CoTaskMemFree
0x18000fb66  nop     dword ptr [rax+rax+00h]
0x18000fb6b  mov     edi, [rsp+2E0h+var_298]
0x18000fb6f  test    rbx, rbx
0x18000fb72  jz      short loc_18000FB7C
0x18000fb74  mov     rcx, rbx; this
0x18000fb77  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x18000fb7c  lea     rcx, [rbp+1E0h+var_260]; this
0x18000fb80  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000fb85  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000fb8a  lea     rdx, [rcx-1]
0x18000fb8e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000fb92  ja      short loc_18000FBA5
0x18000fb94  call    cs:__imp_RegCloseKey
0x18000fb9b  nop     dword ptr [rax+rax+00h]
0x18000fba0  mov     [rsp+2E0h+hKey], r12
0x18000fba5  lea     rcx, [rsp+2E0h+var_298]; this
0x18000fbaa  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000fbaf  mov     eax, edi
0x18000fbb1  mov     rcx, [rbp+1E0h+var_30]
0x18000fbb8  xor     rcx, rsp; StackCookie
0x18000fbbb  call    __security_check_cookie
0x18000fbc0  lea     r11, [rsp+2E0h+var_20]
0x18000fbc8  mov     rbx, [r11+38h]
0x18000fbcc  mov     rsi, [r11+40h]
0x18000fbd0  mov     rsp, r11
0x18000fbd3  pop     r15
0x18000fbd5  pop     r14
0x18000fbd7  pop     r12
0x18000fbd9  pop     rdi
0x18000fbda  pop     rbp
0x18000fbdb  retn
```
