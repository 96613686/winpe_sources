# AsrpMarkCriticalDisks(_ASR_DISK_INFO *,ushort const *,ulong)

- ea: `0x1400d685c`
- end: `0x1400d6d05`
- name: `?AsrpMarkCriticalDisks@@YAHPEAU_ASR_DISK_INFO@@PEBGK@Z`
- size: `1193`
- prototype: `int(struct _ASR_DISK_INFO *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400768c4`

## callees

- `0x14001f7b4`
- `0x140021ca0`
- `0x14002228c`
- `0x1400235a8`
- `0x140025abc`
- `0x14003b160`
- `0x14005b208`
- `0x140091560`
- `0x1400921dc`
- `0x1400d257c`
- `0x1400d25f8`
- `0x1400d685c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d6cd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d6cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d692f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d6cc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d692f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d6cc2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400d6957`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400d6957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6cab`

## string_xrefs

- `0x1400d6b2f`: `::StringCchCopyN( ARRAY_COUNT_PARAM(wszDevicePath), pwszVolGuid, ASR_CCH_DEVICE_PATH_FORMAT)`

## pseudocode

```c
__int64 __fastcall AsrpMarkCriticalDisks(struct _ASR_DISK_INFO *a1, const unsigned __int16 *a2, unsigned int a3)
{
  _DWORD *v6; // r12
  unsigned int v7; // edi
  DWORD LastError; // esi
  const unsigned __int16 *v9; // r15
  int v10; // eax
  void *dwFlagsAndAttributes; // r11
  unsigned int *v12; // rdx
  unsigned int i; // ecx
  __int64 v14; // rax
  __int64 v15; // rax
  DWORD v16; // eax
  int v17; // edx
  int v18; // eax
  struct _ASR_DISK_INFO *v19; // rsi
  __int64 v20; // r9
  int v21; // eax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v22; // rcx
  unsigned int j; // edx
  unsigned int k; // edx
  LPVOID pv; // [rsp+40h] [rbp-79h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-71h]
  WCHAR FileName[64]; // [rsp+50h] [rbp-69h] BYREF

  TraceFunctionEnter(L"AsrpMarkCriticalDisks");
  pv = 0;
  v6 = 0;
  memset_0(FileName, 0, 0x7Au);
  hObject = 0;
  if ( !a2 )
  {
    v7 = 1;
    LastError = 0;
    goto LABEL_63;
  }
  if ( !a1 )
  {
    v7 = 0;
    LastError = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        91,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        87,
        "pDiskList");
    }
    goto LABEL_63;
  }
  v6 = ASR_ALLOC(4 * a3 + 4);
  if ( !v6 )
  {
    v7 = 0;
    LastError = 14;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        92,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        14,
        "pfCriticalDiskTable");
    }
    goto LABEL_63;
  }
  v7 = 1;
  v9 = a2;
LABEL_6:
  if ( *v9 )
  {
    v10 = StringCchCopyNW(FileName, 0x3Du, v9, 0x3Cu);
    if ( v10 < 0 )
    {
      v7 = (unsigned int)dwFlagsAndAttributes;
      LastError = WIN32_FROM_HRESULT((unsigned int)v10);
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v18 = StringCchCopyNW(FileName, 0x3Du, v9, 0x3Cu);
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          93,
          (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
          v18,
          "::StringCchCopyN( ARRAY_COUNT_PARAM(wszDevicePath), pwszVolGuid, ASR_CCH_DEVICE_PATH_FORMAT)");
      }
      goto LABEL_63;
    }
    FileName[1] = 92;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      dwFlagsAndAttributes = 0;
    }
    hObject = CreateFileW(FileName, 0, 3u, 0, 3u, (DWORD)dwFlagsAndAttributes, dwFlagsAndAttributes);
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v7 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_63;
      }
      v16 = GetLastError();
      v17 = 94;
    }
    else
    {
      CoTaskMemFree(pv);
      pv = 0;
      if ( (unsigned int)DoDiskIoctlCall(hObject, 0x560018u, 0, 0, &pv, 0) )
      {
        v12 = (unsigned int *)pv;
        for ( i = 0; ; ++i )
        {
          if ( i >= *v12 )
          {
            v15 = -1;
            do
              ++v15;
            while ( a2[v15] );
            v9 += v15 + 1;
            goto LABEL_6;
          }
          if ( v12[i + 1] > a3 )
            break;
          v14 = v12[i + 1];
          v6[v14] = 1;
        }
        v7 = 0;
        LastError = WIN32_FROM_HRESULT(2147755025LL);
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            96,
            (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
            -2147212271,
            "VSS_E_CRITICAL_VOLUME_ON_INVALID_DISK");
        }
        goto LABEL_63;
      }
      v7 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_63;
      }
      v16 = GetLastError();
      v17 = 95;
    }
    WPP_SF_DsS(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      v17,
      (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
      v16,
      (__int64)"::GetLastError()",
      (__int64)FileName);
    goto LABEL_63;
  }
  v19 = a1;
  do
  {
    v20 = *((unsigned int *)v19 + 16);
    v21 = v6[v20];
    *((_DWORD *)v19 + 19) = v21;
    if ( !*((_DWORD *)v19 + 22) || !v21 )
      goto LABEL_38;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        97,
        WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        v20);
LABEL_38:
      v22 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)v19 + 19) )
    {
      ++v6[*((unsigned int *)v19 + 16)];
      v22 = WPP_GLOBAL_Control;
    }
    v19 = *(struct _ASR_DISK_INFO **)v19;
  }
  while ( v19 );
  for ( j = 0; j < a3; ++j )
  {
    if ( v6[j] == 1 )
    {
      v7 = 0;
      LastError = 55;
      if ( v22 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (v22->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)v22->Gpt.DiskId.Data4,
          98,
          (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
          55,
          "ERROR_DEV_NOT_EXIST");
      }
      goto LABEL_63;
    }
  }
  LastError = 0;
  do
  {
    for ( k = 0; k < *(_DWORD *)(*((_QWORD *)a1 + 2) + 4LL); ++k )
    {
      if ( *(_DWORD *)(*((_QWORD *)a1 + 5) + 24LL * k + 16) )
      {
        *((_DWORD *)a1 + 19) = 1;
        break;
      }
    }
    a1 = *(struct _ASR_DISK_INFO **)a1;
  }
  while ( a1 );
LABEL_63:
  CoTaskMemFree(pv);
  CoTaskMemFree(v6);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  TraceFunctionExit(L"AsrpMarkCriticalDisks");
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x1400d685c  mov     [rsp-8+arg_18], rbx
0x1400d6861  push    rbp
0x1400d6862  push    rsi
0x1400d6863  push    rdi
0x1400d6864  push    r12
0x1400d6866  push    r13
0x1400d6868  push    r14
0x1400d686a  push    r15
0x1400d686c  lea     rbp, [rsp-27h]
0x1400d6871  sub     rsp, 0E0h
0x1400d6878  mov     rax, cs:__security_cookie
0x1400d687f  xor     rax, rsp
0x1400d6882  mov     [rbp+57h+var_40], rax
0x1400d6886  mov     r13d, r8d
0x1400d6889  mov     rsi, rdx
0x1400d688c  mov     r14, rcx
0x1400d688f  lea     rcx, aAsrpmarkcritic_2; "AsrpMarkCriticalDisks"
0x1400d6896  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d689b  xor     ebx, ebx
0x1400d689d  lea     rcx, [rbp+57h+FileName]; void *
0x1400d68a1  xor     edx, edx; Val
0x1400d68a3  mov     [rbp+57h+pv], rbx
0x1400d68a7  mov     r12d, ebx
0x1400d68aa  lea     r8d, [rbx+7Ah]; Size
0x1400d68ae  call    memset_0
0x1400d68b3  mov     [rbp+57h+hObject], rbx
0x1400d68b7  test    rsi, rsi
0x1400d68ba  jnz     short loc_1400D68C6
0x1400d68bc  lea     edi, [rbx+1]
0x1400d68bf  mov     esi, ebx
0x1400d68c1  jmp     loc_1400D6C9E
0x1400d68c6  test    r14, r14
0x1400d68c9  jz      loc_1400D6C5C
0x1400d68cf  lea     ecx, ds:4[r13*4]; Size
0x1400d68d7  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x1400d68dc  xor     r11d, r11d
0x1400d68df  mov     r12, rax
0x1400d68e2  test    rax, rax
0x1400d68e5  jz      loc_1400D6C2F
0x1400d68eb  lea     edi, [r11+1]
0x1400d68ef  mov     r15, rsi
0x1400d68f2  lea     ebx, [rdi+5Bh]
0x1400d68f5  cmp     [r15], r11w
0x1400d68f9  jz      loc_1400D6B4F
0x1400d68ff  mov     r9d, 3Ch ; '<'; unsigned __int64
0x1400d6905  lea     rcx, [rbp+57h+FileName]; unsigned __int16 *
0x1400d6909  mov     r8, r15; unsigned __int16 *
0x1400d690c  lea     edx, [r9+1]; unsigned __int64
0x1400d6910  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400d6915  test    eax, eax
0x1400d6917  js      loc_1400D6AEC
0x1400d691d  mov     rcx, [rbp+57h+hObject]; hObject
0x1400d6921  mov     [rbp+57h+var_BE], bx
0x1400d6925  lea     rax, [rcx-1]
0x1400d6929  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d692d  ja      short loc_1400D6938
0x1400d692f  call    cs:__imp_CloseHandle
0x1400d6935  xor     r11d, r11d
0x1400d6938  mov     eax, 3
0x1400d693d  mov     [rsp+110h+hTemplateFile], r11; hTemplateFile
0x1400d6942  mov     [rsp+110h+dwFlagsAndAttributes], r11d; dwFlagsAndAttributes
0x1400d6947  lea     rcx, [rbp+57h+FileName]; lpFileName
0x1400d694b  mov     r8d, eax; dwShareMode
0x1400d694e  mov     [rsp+110h+dwCreationDisposition], eax; dwCreationDisposition
0x1400d6952  xor     r9d, r9d; lpSecurityAttributes
0x1400d6955  xor     edx, edx; dwDesiredAccess
0x1400d6957  call    cs:__imp_CreateFileW
0x1400d695d  mov     [rbp+57h+hObject], rax
0x1400d6961  dec     rax
0x1400d6964  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d6968  ja      loc_1400D6AB2
0x1400d696e  mov     rcx, [rbp+57h+pv]; pv
0x1400d6972  call    cs:__imp_CoTaskMemFree
0x1400d6978  mov     rcx, [rbp+57h+hObject]; hDevice
0x1400d697c  xor     eax, eax
0x1400d697e  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax; unsigned int *
0x1400d6983  xor     r9d, r9d; nInBufferSize
0x1400d6986  mov     [rbp+57h+pv], rax
0x1400d698a  xor     r8d, r8d; lpInBuffer
0x1400d698d  lea     rax, [rbp+57h+pv]
0x1400d6991  mov     edx, 560018h; dwIoControlCode
0x1400d6996  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; void **
0x1400d699b  call    ?DoDiskIoctlCall@@YAHPEAXK0KPEAPEAXPEAK@Z; DoDiskIoctlCall(void *,ulong,void *,ulong,void * *,ulong *)
0x1400d69a0  xor     r11d, r11d
0x1400d69a3  test    eax, eax
0x1400d69a5  jz      loc_1400D6A47
0x1400d69ab  mov     rdx, [rbp+57h+pv]
0x1400d69af  mov     ecx, r11d
0x1400d69b2  mov     [rbp+57h+pv], rdx
0x1400d69b6  cmp     ecx, [rdx]
0x1400d69b8  jnb     short loc_1400D69CF
0x1400d69ba  mov     eax, ecx
0x1400d69bc  cmp     [rdx+rax*4+4], r13d
0x1400d69c1  ja      short loc_1400D69EA
0x1400d69c3  mov     eax, [rdx+rax*4+4]
0x1400d69c7  add     ecx, edi
0x1400d69c9  mov     [r12+rax*4], edi
0x1400d69cd  jmp     short loc_1400D69B6
0x1400d69cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400d69d3  inc     rax
0x1400d69d6  cmp     [rsi+rax*2], r11w
0x1400d69db  jnz     short loc_1400D69D3
0x1400d69dd  lea     r15, [r15+rax*2]
0x1400d69e1  add     r15, 2
0x1400d69e5  jmp     loc_1400D68F5
0x1400d69ea  mov     r14d, 80042411h
0x1400d69f0  mov     edi, r11d
0x1400d69f3  mov     ecx, r14d
0x1400d69f6  call    WIN32_FROM_HRESULT
0x1400d69fb  mov     esi, eax
0x1400d69fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6a04  lea     rbx, WPP_GLOBAL_Control
0x1400d6a0b  cmp     rcx, rbx
0x1400d6a0e  jz      loc_1400D6C9E
0x1400d6a14  test    byte ptr [rcx+1Ch], 8
0x1400d6a18  jz      loc_1400D6C9E
0x1400d6a1e  lea     rax, aVssECriticalVo; "VSS_E_CRITICAL_VOLUME_ON_INVALID_DISK"
0x1400d6a25  mov     edx, 60h ; '`'
0x1400d6a2a  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1400d6a2f  mov     r9d, r14d
0x1400d6a32  mov     rcx, [rcx+10h]
0x1400d6a36  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400d6a3d  call    WPP_SF_Ds
0x1400d6a42  jmp     loc_1400D6C9E
0x1400d6a47  mov     edi, r11d
0x1400d6a4a  call    cs:__imp_GetLastError
0x1400d6a50  mov     esi, eax
0x1400d6a52  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6a59  lea     rbx, WPP_GLOBAL_Control
0x1400d6a60  cmp     rax, rbx
0x1400d6a63  jz      loc_1400D6C9E
0x1400d6a69  test    byte ptr [rax+1Ch], 8
0x1400d6a6d  jz      loc_1400D6C9E
0x1400d6a73  call    cs:__imp_GetLastError
0x1400d6a79  mov     edx, 5Fh ; '_'
0x1400d6a7e  lea     rcx, [rbp+57h+FileName]
0x1400d6a82  mov     r9d, eax
0x1400d6a85  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rcx
0x1400d6a8a  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400d6a91  lea     rcx, aGetlasterror_0; "::GetLastError()"
0x1400d6a98  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx
0x1400d6a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6aa4  mov     rcx, [rcx+10h]
0x1400d6aa8  call    WPP_SF_DsS
0x1400d6aad  jmp     loc_1400D6C9E
0x1400d6ab2  xor     eax, eax
0x1400d6ab4  mov     edi, eax
0x1400d6ab6  call    cs:__imp_GetLastError
0x1400d6abc  mov     esi, eax
0x1400d6abe  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6ac5  lea     rbx, WPP_GLOBAL_Control
0x1400d6acc  cmp     rax, rbx
0x1400d6acf  jz      loc_1400D6C9E
0x1400d6ad5  test    byte ptr [rax+1Ch], 8
0x1400d6ad9  jz      loc_1400D6C9E
0x1400d6adf  call    cs:__imp_GetLastError
0x1400d6ae5  mov     edx, 5Eh ; '^'
0x1400d6aea  jmp     short loc_1400D6A7E
0x1400d6aec  mov     ecx, eax
0x1400d6aee  mov     edi, r11d
0x1400d6af1  call    WIN32_FROM_HRESULT
0x1400d6af6  mov     esi, eax
0x1400d6af8  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6aff  lea     rbx, WPP_GLOBAL_Control
0x1400d6b06  cmp     rax, rbx
0x1400d6b09  jz      loc_1400D6C9E
0x1400d6b0f  test    byte ptr [rax+1Ch], 8
0x1400d6b13  jz      loc_1400D6C9E
0x1400d6b19  mov     r9d, 3Ch ; '<'; unsigned __int64
0x1400d6b1f  lea     rcx, [rbp+57h+FileName]; unsigned __int16 *
0x1400d6b23  mov     r8, r15; unsigned __int16 *
0x1400d6b26  lea     edx, [r9+1]; unsigned __int64
0x1400d6b2a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400d6b2f  lea     rcx, aStringcchcopyn_8; "::StringCchCopyN( ARRAY_COUNT_PARAM(wsz"...
0x1400d6b36  mov     edx, 5Dh ; ']'
0x1400d6b3b  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx
0x1400d6b40  mov     r9d, eax
0x1400d6b43  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6b4a  jmp     loc_1400D6A32
0x1400d6b4f  mov     rsi, r14
0x1400d6b52  lea     rbx, WPP_GLOBAL_Control
0x1400d6b59  mov     r9d, [rsi+40h]
0x1400d6b5d  mov     eax, [r12+r9*4]
0x1400d6b61  mov     [rsi+4Ch], eax
0x1400d6b64  cmp     [rsi+58h], r11d
0x1400d6b68  jz      short loc_1400D6B98
0x1400d6b6a  test    eax, eax
0x1400d6b6c  jz      short loc_1400D6B98
0x1400d6b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6b75  cmp     rcx, rbx
0x1400d6b78  jz      short loc_1400D6B9F
0x1400d6b7a  test    byte ptr [rcx+1Ch], 2
0x1400d6b7e  jz      short loc_1400D6B9F
0x1400d6b80  mov     rcx, [rcx+10h]
0x1400d6b84  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400d6b8b  mov     edx, 61h ; 'a'
0x1400d6b90  call    WPP_SF_d
0x1400d6b95  xor     r11d, r11d
0x1400d6b98  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6b9f  cmp     [rsi+4Ch], r11d
0x1400d6ba3  jz      short loc_1400D6BB3
0x1400d6ba5  mov     eax, [rsi+40h]
0x1400d6ba8  add     [r12+rax*4], edi
0x1400d6bac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6bb3  mov     rsi, [rsi]
0x1400d6bb6  test    rsi, rsi
0x1400d6bb9  jnz     short loc_1400D6B59
0x1400d6bbb  mov     edx, r11d
0x1400d6bbe  cmp     edx, r13d
0x1400d6bc1  jnb     short loc_1400D6BF9
0x1400d6bc3  mov     eax, edx
0x1400d6bc5  cmp     [r12+rax*4], edi
0x1400d6bc9  jz      short loc_1400D6BCF
0x1400d6bcb  add     edx, edi
0x1400d6bcd  jmp     short loc_1400D6BBE
0x1400d6bcf  mov     edi, r11d
0x1400d6bd2  mov     esi, 37h ; '7'
0x1400d6bd7  cmp     rcx, rbx
0x1400d6bda  jz      loc_1400D6C9E
0x1400d6be0  test    byte ptr [rcx+1Ch], 8
0x1400d6be4  jz      loc_1400D6C9E
0x1400d6bea  lea     edx, [rsi+2Bh]
0x1400d6bed  lea     rax, aErrorDevNotExi; "ERROR_DEV_NOT_EXIST"
0x1400d6bf4  jmp     loc_1400D6C86
0x1400d6bf9  mov     esi, r11d
0x1400d6bfc  mov     rax, [r14+10h]
0x1400d6c00  mov     edx, r11d
0x1400d6c03  mov     r8d, [rax+4]
0x1400d6c07  cmp     edx, r8d
0x1400d6c0a  jnb     short loc_1400D6C25
0x1400d6c0c  mov     eax, edx
0x1400d6c0e  lea     rcx, [rax+rax*2]
0x1400d6c12  mov     rax, [r14+28h]
0x1400d6c16  cmp     [rax+rcx*8+10h], r11d
0x1400d6c1b  jnz     short loc_1400D6C21
0x1400d6c1d  add     edx, edi
0x1400d6c1f  jmp     short loc_1400D6C07
0x1400d6c21  mov     [r14+4Ch], edi
0x1400d6c25  mov     r14, [r14]
0x1400d6c28  test    r14, r14
0x1400d6c2b  jnz     short loc_1400D6BFC
0x1400d6c2d  jmp     short loc_1400D6C9E
0x1400d6c2f  mov     edi, r11d
0x1400d6c32  mov     esi, 0Eh
0x1400d6c37  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6c3e  lea     rbx, WPP_GLOBAL_Control
0x1400d6c45  cmp     rcx, rbx
0x1400d6c48  jz      short loc_1400D6C9E
0x1400d6c4a  test    byte ptr [rcx+1Ch], 8
0x1400d6c4e  jz      short loc_1400D6C9E
0x1400d6c50  lea     edx, [rsi+4Eh]
0x1400d6c53  lea     rax, aPfcriticaldisk; "pfCriticalDiskTable"
0x1400d6c5a  jmp     short loc_1400D6C86
0x1400d6c5c  mov     edi, ebx
0x1400d6c5e  mov     esi, 57h ; 'W'
0x1400d6c63  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6c6a  lea     rbx, WPP_GLOBAL_Control
0x1400d6c71  cmp     rcx, rbx
0x1400d6c74  jz      short loc_1400D6C9E
0x1400d6c76  test    byte ptr [rcx+1Ch], 8
0x1400d6c7a  jz      short loc_1400D6C9E
0x1400d6c7c  lea     edx, [rsi+4]
0x1400d6c7f  lea     rax, aPdisklist; "pDiskList"
0x1400d6c86  mov     rcx, [rcx+10h]
0x1400d6c8a  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400d6c91  mov     r9d, esi
0x1400d6c94  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1400d6c99  call    WPP_SF_Ds
0x1400d6c9e  mov     rcx, [rbp+57h+pv]; pv
0x1400d6ca2  call    cs:__imp_CoTaskMemFree
0x1400d6ca8  mov     rcx, r12; pv
0x1400d6cab  call    cs:__imp_CoTaskMemFree
0x1400d6cb1  mov     rax, [rbp+57h+hObject]
0x1400d6cb5  lea     rdx, [rax-1]
0x1400d6cb9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400d6cbd  ja      short loc_1400D6CC8
0x1400d6cbf  mov     rcx, rax; hObject
0x1400d6cc2  call    cs:__imp_CloseHandle
0x1400d6cc8  lea     rcx, aAsrpmarkcritic_2; "AsrpMarkCriticalDisks"
0x1400d6ccf  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d6cd4  mov     ecx, esi; dwErrCode
0x1400d6cd6  call    cs:__imp_SetLastError
0x1400d6cdc  mov     eax, edi
0x1400d6cde  mov     rcx, [rbp+57h+var_40]
0x1400d6ce2  xor     rcx, rsp; StackCookie
0x1400d6ce5  call    __security_check_cookie
0x1400d6cea  mov     rbx, [rsp+110h+arg_18]
0x1400d6cf2  add     rsp, 0E0h
0x1400d6cf9  pop     r15
0x1400d6cfb  pop     r14
0x1400d6cfd  pop     r13
0x1400d6cff  pop     r12
0x1400d6d01  pop     rdi
0x1400d6d02  pop     rsi
0x1400d6d03  pop     rbp
0x1400d6d04  retn
```
