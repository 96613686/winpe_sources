# DiskListPopulateLayoutInfo(_ASR_DISK_INFO * *,ulong *)

- ea: `0x140021558`
- end: `0x140021962`
- name: `?DiskListPopulateLayoutInfo@@YAHPEAPEAU_ASR_DISK_INFO@@PEAK@Z`
- size: `1034`
- prototype: `__int64 __fastcall(struct _ASR_DISK_INFO **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140059980`
- `0x1400768c4`

## callees

- `0x140010170`
- `0x14001f7b4`
- `0x14001f930`
- `0x140021558`
- `0x140021ca0`
- `0x14002228c`
- `0x14003b0c0`
- `0x14005b208`
- `0x140091560`
- `0x1400d257c`
- `0x1400d6d50`
- `0x1400d7c94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002192e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002192e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400216a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400216a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002164c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400218db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002164c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400218db`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140021674`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140021674`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400216d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021919`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400216d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021919`

## pseudocode

```c
__int64 __fastcall DiskListPopulateLayoutInfo(struct _ASR_DISK_INFO **a1, unsigned int *a2)
{
  struct _ASR_DISK_INFO **v3; // rax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v4; // rcx
  unsigned int v5; // ebp
  unsigned int *v6; // r15
  struct _ASR_DISK_INFO *v7; // rdi
  __int64 FileW; // rbx
  DWORD v9; // r14d
  int DiskLayout; // edx
  __int64 LastError; // r12
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned __int16 *v15; // r9
  struct _ASR_DISK_INFO *v16; // rax
  struct _ASR_DISK_INFO *v17; // rax
  unsigned int v18; // eax
  int v19; // eax
  int v20; // eax
  int dwFlagsAndAttributes; // [rsp+28h] [rbp-B0h]
  int dwFlagsAndAttributesa; // [rsp+28h] [rbp-B0h]
  int v24; // [rsp+40h] [rbp-98h]
  void *v25; // [rsp+48h] [rbp-90h] BYREF
  struct _ASR_DISK_INFO **v26; // [rsp+50h] [rbp-88h]
  _QWORD *v27; // [rsp+58h] [rbp-80h]
  unsigned __int16 v28[12]; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int16 v29[20]; // [rsp+78h] [rbp-60h] BYREF

  v26 = a1;
  v3 = a1;
  v4 = WPP_GLOBAL_Control;
  v5 = 1;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x100000000LL) != 0 )
  {
    WPP_SF_S(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      10,
      WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids,
      L"DiskListPopulateLayoutInfo");
    v4 = WPP_GLOBAL_Control;
    v3 = v26;
  }
  v6 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    v7 = *v3;
    FileW = -1;
    v24 = 0;
    v9 = 0;
    v27 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v7 )
          goto LABEL_41;
        if ( v4 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (v4->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
        {
          WPP_SF_S(
            *(_QWORD *)v4->Gpt.DiskId.Data4,
            73,
            WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
            *((_QWORD *)v7 + 1));
        }
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle((HANDLE)FileW);
        FileW = (__int64)CreateFileW(*((LPCWSTR *)v7 + 1), 0, 3u, 0, 3u, 0x80u, 0);
        if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          DiskLayout = v24;
        }
        else
        {
          DiskLayout = AsrpGetDiskLayout((char *)FileW, v7);
          v24 = DiskLayout;
        }
        if ( !DiskLayout )
          break;
        if ( a2 )
        {
          v18 = *((_DWORD *)v7 + 16);
          if ( v18 > *a2 )
            *a2 = v18;
        }
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            76,
            WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
            *((unsigned int *)v7 + 16));
          v4 = WPP_GLOBAL_Control;
        }
        v27 = v7;
        v7 = *(struct _ASR_DISK_INFO **)v7;
      }
      LastError = GetLastError();
      v12 = StringCchPrintfW(v29, 0x14u, L"0x%x", LastError);
      if ( v12 < 0 )
        break;
      CoTaskMemFree(v6);
      v6 = 0;
      v25 = 0;
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL
        && (v13 = DoDiskIoctlCall((HANDLE)FileW, 0x2D1080u, 0, 0, &v25, 0), v6 = (unsigned int *)v25, v13) )
      {
        v14 = StringCchPrintfW(v28, 0xAu, L"%d", *((unsigned int *)v25 + 1));
        if ( v14 < 0 )
        {
          v5 = 0;
          v9 = WIN32_FROM_HRESULT((unsigned int)v14);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v19 = StringCchPrintfW(v28, 0xAu, L"%d", v6[1]);
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              75,
              (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
              v19,
              "::StringCchPrintf(ARRAY_COUNT_PARAM(wszDeviceNumber), L\"%d\", pStorageDeviceNumber->DeviceNumber)",
              dwFlagsAndAttributesa);
          }
          goto LABEL_43;
        }
        v15 = v28;
      }
      else
      {
        v15 = (unsigned __int16 *)*((_QWORD *)v7 + 1);
      }
      LogEvent(0xA001u, 2u, 2, v15, v29);
      v16 = *(struct _ASR_DISK_INFO **)v7;
      if ( v27 )
        *v27 = v16;
      else
        *v26 = v16;
      v17 = DiskListFreeDiskInfo(v7);
      v4 = WPP_GLOBAL_Control;
      v7 = v17;
    }
    v5 = 0;
    v9 = WIN32_FROM_HRESULT((unsigned int)v12);
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v20 = StringCchPrintfW(v29, 0x14u, L"0x%x", (unsigned int)LastError);
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        74,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        v20,
        "::StringCchPrintf(ARRAY_COUNT_PARAM(wszErrorCodeString), L\"0x%x\", dwError)",
        dwFlagsAndAttributes);
    }
LABEL_41:
    if ( FileW && FileW != -1 )
LABEL_43:
      CloseHandle((HANDLE)FileW);
  }
  else
  {
    v5 = 0;
    v9 = 87;
    if ( v4 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (v4->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)v4->Gpt.DiskId.Data4,
        72,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        87,
        "ppDiskList");
    }
  }
  CoTaskMemFree(v6);
  TraceFunctionExit(L"DiskListPopulateLayoutInfo");
  SetLastError(v9);
  return v5;
}

```

## disassembly

```asm
0x140021558  mov     [rsp+arg_10], rbx
0x14002155d  mov     [rsp+arg_18], rbp
0x140021562  push    rsi
0x140021563  push    rdi
0x140021564  push    r12
0x140021566  push    r14
0x140021568  push    r15
0x14002156a  sub     rsp, 0B0h
0x140021571  mov     rax, cs:__security_cookie
0x140021578  xor     rax, rsp
0x14002157b  mov     [rsp+0D8h+var_38], rax
0x140021583  mov     rsi, rdx
0x140021586  mov     [rsp+0D8h+var_88], rcx
0x14002158b  mov     rax, rcx
0x14002158e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021595  lea     r8, WPP_GLOBAL_Control
0x14002159c  mov     ebp, 1
0x1400215a1  cmp     rcx, r8
0x1400215a4  jz      short loc_1400215D9
0x1400215a6  test    [rcx+1Ch], bpl
0x1400215aa  jz      short loc_1400215D9
0x1400215ac  mov     rcx, [rcx+10h]
0x1400215b0  lea     edx, [rbp+9]
0x1400215b3  lea     r9, aDisklistpopula_1; "DiskListPopulateLayoutInfo"
0x1400215ba  lea     r8, WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids
0x1400215c1  call    WPP_SF_S
0x1400215c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215cd  lea     r8, WPP_GLOBAL_Control
0x1400215d4  mov     rax, [rsp+0D8h+var_88]
0x1400215d9  xor     r15d, r15d
0x1400215dc  test    rsi, rsi
0x1400215df  jz      short loc_1400215EB
0x1400215e1  mov     [rsi], r15d
0x1400215e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215eb  test    rax, rax
0x1400215ee  jz      loc_1400218E3
0x1400215f4  mov     rdi, [rax]
0x1400215f7  xor     edx, edx
0x1400215f9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400215fd  mov     [rsp+0D8h+var_98], edx
0x140021601  xor     r14d, r14d
0x140021604  xor     r12d, r12d
0x140021607  mov     [rsp+0D8h+var_80], r12
0x14002160c  mov     r12d, 2
0x140021612  test    rdi, rdi
0x140021615  jz      loc_1400218CD
0x14002161b  cmp     rcx, r8
0x14002161e  jz      short loc_14002163F
0x140021620  test    [rcx+1Ch], r12b
0x140021624  jz      short loc_14002163F
0x140021626  mov     r9, [rdi+8]
0x14002162a  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x140021631  mov     rcx, [rcx+10h]
0x140021635  mov     edx, 49h ; 'I'
0x14002163a  call    WPP_SF_S
0x14002163f  lea     rax, [rbx-1]
0x140021643  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140021647  ja      short loc_140021652
0x140021649  mov     rcx, rbx; hObject
0x14002164c  call    cs:__imp_CloseHandle
0x140021652  mov     rcx, [rdi+8]; lpFileName
0x140021656  mov     eax, 3
0x14002165b  mov     [rsp+0D8h+hTemplateFile], r14; hTemplateFile
0x140021660  mov     r8d, eax; dwShareMode
0x140021663  mov     [rsp+0D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14002166b  xor     r9d, r9d; lpSecurityAttributes
0x14002166e  xor     edx, edx; dwDesiredAccess
0x140021670  mov     [rsp+0D8h+dwCreationDisposition], eax; dwCreationDisposition
0x140021674  call    cs:__imp_CreateFileW
0x14002167a  mov     rbx, rax
0x14002167d  dec     rax
0x140021680  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140021684  ja      short loc_140021699
0x140021686  mov     rdx, rdi; struct _ASR_DISK_INFO *
0x140021689  mov     rcx, rbx; hDevice
0x14002168c  call    ?AsrpGetDiskLayout@@YAHPEAXPEAU_ASR_DISK_INFO@@@Z; AsrpGetDiskLayout(void *,_ASR_DISK_INFO *)
0x140021691  mov     edx, eax
0x140021693  mov     [rsp+0D8h+var_98], eax
0x140021697  jmp     short loc_14002169D
0x140021699  mov     edx, [rsp+0D8h+var_98]
0x14002169d  test    edx, edx
0x14002169f  jnz     loc_14002179D
0x1400216a5  call    cs:__imp_GetLastError
0x1400216ab  lea     r8, a0xX; "0x%x"
0x1400216b2  mov     edx, 14h; unsigned __int64
0x1400216b7  mov     r9d, eax
0x1400216ba  lea     rcx, [rsp+0D8h+var_60]; unsigned __int16 *
0x1400216bf  mov     r12d, eax
0x1400216c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400216c7  test    eax, eax
0x1400216c9  js      loc_140021868
0x1400216cf  mov     rcx, r15; pv
0x1400216d2  call    cs:__imp_CoTaskMemFree
0x1400216d8  xor     r15d, r15d
0x1400216db  lea     rax, [rbx-1]
0x1400216df  mov     [rsp+0D8h+var_90], r15
0x1400216e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400216e8  ja      short loc_140021742
0x1400216ea  lea     rax, [rsp+0D8h+var_90]
0x1400216ef  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], r14; unsigned int *
0x1400216f4  xor     r9d, r9d; nInBufferSize
0x1400216f7  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax; void **
0x1400216fc  xor     r8d, r8d; lpInBuffer
0x1400216ff  mov     edx, 2D1080h; dwIoControlCode
0x140021704  mov     rcx, rbx; hDevice
0x140021707  call    ?DoDiskIoctlCall@@YAHPEAXK0KPEAPEAXPEAK@Z; DoDiskIoctlCall(void *,ulong,void *,ulong,void * *,ulong *)
0x14002170c  mov     r15, [rsp+0D8h+var_90]
0x140021711  test    eax, eax
0x140021713  jz      short loc_140021742
0x140021715  mov     r9d, [r15+4]
0x140021719  lea     r8, aD; "%d"
0x140021720  mov     r12d, 0Ah
0x140021726  lea     rcx, [rsp+0D8h+var_78]; unsigned __int16 *
0x14002172b  mov     edx, r12d; unsigned __int64
0x14002172e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140021733  test    eax, eax
0x140021735  js      loc_1400217F8
0x14002173b  lea     r9, [rsp+0D8h+var_78]
0x140021740  jmp     short loc_140021746
0x140021742  mov     r9, [rdi+8]
0x140021746  lea     rax, [rsp+0D8h+var_60]
0x14002174b  mov     ecx, 0A001h; dwEventID
0x140021750  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax
0x140021755  mov     eax, 2
0x14002175a  mov     r8d, eax; int
0x14002175d  mov     edx, eax; unsigned __int16
0x14002175f  call    ?LogEvent@@YAHKGHZZ; LogEvent(ulong,ushort,int,...)
0x140021764  mov     r12, [rsp+0D8h+var_80]
0x140021769  mov     rax, [rdi]
0x14002176c  test    r12, r12
0x14002176f  jnz     short loc_14002177B
0x140021771  mov     rcx, [rsp+0D8h+var_88]
0x140021776  mov     [rcx], rax
0x140021779  jmp     short loc_14002177F
0x14002177b  mov     [r12], rax
0x14002177f  mov     rcx, rdi; pv
0x140021782  call    ?DiskListFreeDiskInfo@@YAPEAU_ASR_DISK_INFO@@PEAU1@@Z; DiskListFreeDiskInfo(_ASR_DISK_INFO *)
0x140021787  mov     rcx, cs:WPP_GLOBAL_Control
0x14002178e  lea     r8, WPP_GLOBAL_Control
0x140021795  mov     rdi, rax
0x140021798  jmp     loc_14002160C
0x14002179d  test    rsi, rsi
0x1400217a0  jz      short loc_1400217AB
0x1400217a2  mov     eax, [rdi+40h]
0x1400217a5  cmp     eax, [rsi]
0x1400217a7  jbe     short loc_1400217AB
0x1400217a9  mov     [rsi], eax
0x1400217ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400217b2  lea     r8, WPP_GLOBAL_Control
0x1400217b9  cmp     rcx, r8
0x1400217bc  jz      short loc_1400217EB
0x1400217be  test    [rcx+1Ch], r12b
0x1400217c2  jz      short loc_1400217EB
0x1400217c4  mov     r9d, [rdi+40h]
0x1400217c8  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400217cf  mov     rcx, [rcx+10h]
0x1400217d3  mov     edx, 4Ch ; 'L'
0x1400217d8  call    WPP_SF_d
0x1400217dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400217e4  lea     r8, WPP_GLOBAL_Control
0x1400217eb  mov     [rsp+0D8h+var_80], rdi
0x1400217f0  mov     rdi, [rdi]
0x1400217f3  jmp     loc_140021612
0x1400217f8  xor     ebp, ebp
0x1400217fa  mov     ecx, eax
0x1400217fc  call    WIN32_FROM_HRESULT
0x140021801  mov     r14d, eax
0x140021804  mov     rcx, cs:WPP_GLOBAL_Control
0x14002180b  lea     r8, WPP_GLOBAL_Control
0x140021812  cmp     rcx, r8
0x140021815  jz      loc_1400218D8
0x14002181b  test    byte ptr [rcx+1Ch], 8
0x14002181f  jz      loc_1400218D8
0x140021825  mov     r9d, [r15+4]
0x140021829  lea     r8, aD; "%d"
0x140021830  mov     rdx, r12; unsigned __int64
0x140021833  lea     rcx, [rsp+0D8h+var_78]; unsigned __int16 *
0x140021838  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002183d  lea     rcx, aStringcchprint_15; "::StringCchPrintf(ARRAY_COUNT_PARAM(wsz"...
0x140021844  mov     r9d, eax
0x140021847  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rcx
0x14002184c  lea     edx, [rbp+4Bh]
0x14002184f  mov     rcx, cs:WPP_GLOBAL_Control
0x140021856  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x14002185d  mov     rcx, [rcx+10h]
0x140021861  call    WPP_SF_Ds
0x140021866  jmp     short loc_1400218D8
0x140021868  xor     ebp, ebp
0x14002186a  mov     ecx, eax
0x14002186c  call    WIN32_FROM_HRESULT
0x140021871  mov     r14d, eax
0x140021874  mov     rax, cs:WPP_GLOBAL_Control
0x14002187b  lea     r8, WPP_GLOBAL_Control
0x140021882  cmp     rax, r8
0x140021885  jz      short loc_1400218CD
0x140021887  test    byte ptr [rax+1Ch], 8
0x14002188b  jz      short loc_1400218CD
0x14002188d  mov     r9d, r12d
0x140021890  lea     r8, a0xX; "0x%x"
0x140021897  lea     edx, [rbp+14h]; unsigned __int64
0x14002189a  lea     rcx, [rsp+0D8h+var_60]; unsigned __int16 *
0x14002189f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400218a4  lea     rcx, aStringcchprint_9; "::StringCchPrintf(ARRAY_COUNT_PARAM(wsz"...
0x1400218ab  mov     r9d, eax
0x1400218ae  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rcx
0x1400218b3  lea     edx, [rbp+4Ah]
0x1400218b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400218bd  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400218c4  mov     rcx, [rcx+10h]
0x1400218c8  call    WPP_SF_Ds
0x1400218cd  test    rbx, rbx
0x1400218d0  jz      short loc_140021916
0x1400218d2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400218d6  jz      short loc_140021916
0x1400218d8  mov     rcx, rbx; hObject
0x1400218db  call    cs:__imp_CloseHandle
0x1400218e1  jmp     short loc_140021916
0x1400218e3  xor     ebp, ebp
0x1400218e5  lea     r14d, [rbp+57h]
0x1400218e9  cmp     rcx, r8
0x1400218ec  jz      short loc_140021916
0x1400218ee  test    byte ptr [rcx+1Ch], 8
0x1400218f2  jz      short loc_140021916
0x1400218f4  mov     rcx, [rcx+10h]
0x1400218f8  lea     rax, aPpdisklist; "ppDiskList"
0x1400218ff  lea     edx, [rbp+48h]
0x140021902  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax
0x140021907  mov     r9d, r14d
0x14002190a  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x140021911  call    WPP_SF_Ds
0x140021916  mov     rcx, r15; pv
0x140021919  call    cs:__imp_CoTaskMemFree
0x14002191f  lea     rcx, aDisklistpopula_1; "DiskListPopulateLayoutInfo"
0x140021926  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x14002192b  mov     ecx, r14d; dwErrCode
0x14002192e  call    cs:__imp_SetLastError
0x140021934  mov     eax, ebp
0x140021936  mov     rcx, [rsp+0D8h+var_38]
0x14002193e  xor     rcx, rsp; StackCookie
0x140021941  call    __security_check_cookie
0x140021946  lea     r11, [rsp+0D8h+var_28]
0x14002194e  mov     rbx, [r11+40h]
0x140021952  mov     rbp, [r11+48h]
0x140021956  mov     rsp, r11
0x140021959  pop     r15
0x14002195b  pop     r14
0x14002195d  pop     r12
0x14002195f  pop     rdi
0x140021960  pop     rsi
0x140021961  retn
```
