# WdcHandleMonitor::AddHandle(ulong,void *,ulong,ushort const *)

- ea: `0x180038024`
- end: `0x18003876b`
- name: `?AddHandle@WdcHandleMonitor@@AEAAJKPEAXKPEBG@Z`
- size: `1863`
- prototype: `__int64 __fastcall(WdcHandleMonitor *this, unsigned int, void *, unsigned int, wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, loader_planting`

## callers

- `0x180081a90`

## callees

- `0x1800071e0`
- `0x1800088b0`
- `0x180008ab0`
- `0x18000b854`
- `0x18000ff88`
- `0x180015060`
- `0x18001cb20`
- `0x180038024`
- `0x18003a3c0`
- `0x18008179c`
- `0x180084e04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180038582`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180038582`
- `ntdll!RtlNtStatusToDosError` at `0x1800380b4`
- `ntdll!RtlNtStatusToDosError` at `0x180038162`
- `ntdll!RtlNtStatusToDosError` at `0x18003845e`
- `ntdll!RtlNtStatusToDosError` at `0x1800380b4`
- `ntdll!RtlNtStatusToDosError` at `0x180038162`
- `ntdll!RtlNtStatusToDosError` at `0x18003845e`
- `ntdll!NtQueryObject` at `0x1800380a8`
- `ntdll!NtQueryObject` at `0x180038156`
- `ntdll!NtQueryObject` at `0x180038452`
- `ntdll!NtQueryObject` at `0x1800380a8`
- `ntdll!NtQueryObject` at `0x180038156`
- `ntdll!NtQueryObject` at `0x180038452`
- `KERNEL32!CreateThread` at `0x1800382e7`
- `KERNEL32!CreateThread` at `0x1800382e7`
- `KERNEL32!CloseHandle` at `0x1800383aa`
- `KERNEL32!CloseHandle` at `0x1800383aa`
- `KERNEL32!GetLastError` at `0x1800382f9`
- `KERNEL32!GetLastError` at `0x180038326`
- `KERNEL32!GetLastError` at `0x1800382f9`
- `KERNEL32!GetLastError` at `0x180038326`
- `KERNEL32!WaitForSingleObject` at `0x180038376`
- `KERNEL32!WaitForSingleObject` at `0x180038376`
- `KERNEL32!ResetEvent` at `0x1800383c1`
- `KERNEL32!ResetEvent` at `0x1800383c1`
- `KERNEL32!SetEvent` at `0x180038364`
- `KERNEL32!SetEvent` at `0x180038364`
- `KERNEL32!TerminateThread` at `0x180038393`
- `KERNEL32!TerminateThread` at `0x180038393`
- `USER32!CharLowerW` at `0x180038575`
- `USER32!CharLowerW` at `0x180038575`
- `OLEAUT32!__imp_SysAllocString` at `0x1800381fa`
- `OLEAUT32!__imp_SysAllocString` at `0x180038529`
- `OLEAUT32!__imp_SysAllocString` at `0x1800381fa`
- `OLEAUT32!__imp_SysAllocString` at `0x180038529`
- `OLEAUT32!__imp_SysFreeString` at `0x1800381e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180038738`
- `OLEAUT32!__imp_SysFreeString` at `0x1800381e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180038738`

## pseudocode

```c
__int64 __fastcall WdcHandleMonitor::AddHandle(
        WdcHandleMonitor *this,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        wchar_t *a5)
{
  __int64 v5; // r14
  signed int v8; // ebx
  NTSTATUS Object; // eax
  const char *v10; // rdx
  int v11; // r8d
  signed int v12; // eax
  const wchar_t **v13; // rbp
  OLECHAR *v14; // r15
  __int64 v15; // r13
  ULONG v16; // ebx
  const wchar_t **v17; // rax
  const wchar_t **v18; // rdi
  NTSTATUS v19; // eax
  const char *v20; // rdx
  unsigned __int16 **v21; // r8
  signed int v22; // eax
  const wchar_t **v23; // rcx
  OLECHAR *v24; // rcx
  const OLECHAR *v25; // rbx
  BSTR v26; // rax
  ULONG v27; // ebp
  const wchar_t **v28; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  signed int v31; // eax
  void *v32; // rcx
  char *v33; // rcx
  __int64 i; // rbx
  NTSTATUS v35; // ecx
  NTSTATUS v36; // eax
  signed int v37; // eax
  unsigned int v38; // r9d
  unsigned __int16 *v39; // r14
  int v40; // eax
  const OLECHAR *v41; // rbx
  BSTR v42; // rax
  unsigned int v43; // edi
  WdcHandleMonitor *v44; // rcx
  char *v45; // rcx
  __int64 v46; // rax
  struct _WDC_HANDLE_INFO *v47; // r14
  char *v48; // rbp
  char **v49; // rdi
  char ***v50; // rax
  __int64 v51; // rcx
  _WORD *v52; // rcx
  int ImageName; // eax
  char ***v54; // rax
  __int64 v55; // rcx
  char ***v56; // rax
  __int64 v57; // rcx
  char *v58; // rsi
  __int64 v59; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-C8h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-C8h]
  const wchar_t **v63; // [rsp+30h] [rbp-B8h]
  const wchar_t **v64; // [rsp+38h] [rbp-B0h]
  struct _WDC_HANDLE_INFO *v66; // [rsp+48h] [rbp-A0h] BYREF
  void *v67; // [rsp+50h] [rbp-98h]
  wchar_t *SubStr; // [rsp+58h] [rbp-90h]
  _OWORD ObjectInformation[2]; // [rsp+60h] [rbp-88h] BYREF
  __int128 v70; // [rsp+80h] [rbp-68h]
  __int64 v71; // [rsp+90h] [rbp-58h]

  memset(ObjectInformation, 0, sizeof(ObjectInformation));
  SubStr = a5;
  v5 = a4;
  v66 = 0;
  v71 = 0;
  v70 = 0;
  if ( a4 >= 0x40 )
    return (unsigned int)-2147467259;
  Object = NtQueryObject(a3, ObjectBasicInformation, ObjectInformation, 0x38u, 0);
  if ( Object )
  {
    v12 = RtlNtStatusToDosError(Object);
    v8 = 0;
    if ( v12 )
    {
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      else
        v8 = v12;
    }
    if ( v8 < 0 )
    {
      LODWORD(ReturnLength) = v8;
LABEL_10:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
        "WdcHandleMonitor::AddHandle",
        0,
        L"FAILURE: 0x%08x",
        ReturnLength);
      return (unsigned int)v8;
    }
  }
  v13 = 0;
  v64 = 0;
  v14 = 0;
  v67 = 0;
  v15 = v5;
  if ( !*((_QWORD *)this + v5 + 1184) )
  {
    v16 = DWORD2(v70) + 8;
    v17 = (const wchar_t **)WdcAlloc((unsigned int)(DWORD2(v70) + 8), v10, v11);
    v18 = v17;
    if ( !v17 )
    {
      v8 = -2147024882;
      LODWORD(ReturnLength) = -2147024882;
      goto LABEL_10;
    }
    v19 = NtQueryObject(a3, ObjectTypeInformation, v17, v16, 0);
    if ( v19 )
    {
      v22 = RtlNtStatusToDosError(v19);
      v8 = 0;
      if ( v22 )
      {
        if ( v22 > 0 )
          v8 = (unsigned __int16)v22 | 0x80070000;
        else
          v8 = v22;
      }
      if ( v8 < 0 )
      {
        LODWORD(ReturnLength) = v8;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
          "WdcHandleMonitor::AddHandle",
          0,
          L"FAILURE: 0x%08x",
          ReturnLength);
LABEL_66:
        WdcFree(v18, v20, (int)v21);
        goto LABEL_101;
      }
    }
    v64 = v18;
    if ( !*(_WORD *)v18 )
    {
      v8 = 0;
      v23 = v18;
LABEL_102:
      WdcFree(v23, v20, (int)v21);
      goto LABEL_103;
    }
    if ( !wcscmp_0(v18[1], L"File") )
      *((_DWORD *)this + 2496) = v5;
    v24 = (OLECHAR *)*((_QWORD *)this + v5 + 1184);
    v25 = v18[1];
    if ( v24 )
    {
      SysFreeString(v24);
      *((_QWORD *)this + v5 + 1184) = 0;
    }
    v26 = SysAllocString(v25);
    if ( v25 && !v26 )
    {
      LODWORD(ReturnLength) = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        ReturnLength);
      LODWORD(ReturnLengtha) = -2147024882;
      v8 = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
        "WdcHandleMonitor::AddHandle",
        0,
        L"FAILURE: 0x%08x",
        ReturnLengtha);
      v23 = v18;
      goto LABEL_102;
    }
    *((_QWORD *)this + v5 + 1184) = v26;
  }
  v27 = DWORD1(v70);
  if ( !DWORD1(v70) )
    v27 = 520;
  v28 = (const wchar_t **)WdcAlloc(v27, v10, v11);
  v18 = v28;
  if ( !v28 )
  {
    LODWORD(ReturnLength) = -2147024882;
    v8 = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
      "WdcHandleMonitor::AddHandle",
      0,
      L"FAILURE: 0x%08x",
      ReturnLength);
    v13 = 0;
    goto LABEL_101;
  }
  if ( (_DWORD)v5 != *((_DWORD *)this + 2496) )
  {
    v36 = NtQueryObject(a3, ObjectNameInformation, v28, v27, 0);
    if ( !v36 )
      goto LABEL_56;
    v35 = v36;
    goto LABEL_60;
  }
  if ( !*((_QWORD *)this + 1170) )
  {
    Thread = CreateThread(0, 0, QueryNameThreadProc, (char *)this + 9368, 0, 0);
    *((_QWORD *)this + 1170) = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( !LastError )
        goto LABEL_53;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 < 0 )
        goto LABEL_54;
    }
    if ( *((_QWORD *)this + 1170) != -1 )
      goto LABEL_47;
    v31 = GetLastError();
    v8 = v31;
    if ( v31 )
    {
      if ( v31 > 0 )
        v8 = (unsigned __int16)v31 | 0x80070000;
      if ( v8 >= 0 )
        goto LABEL_47;
LABEL_54:
      LODWORD(ReturnLength) = v8;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
        "WdcHandleMonitor::AddHandle",
        0,
        L"FAILURE: 0x%08x",
        ReturnLength);
LABEL_65:
      v13 = 0;
      goto LABEL_66;
    }
LABEL_53:
    v8 = -2147467259;
    goto LABEL_54;
  }
LABEL_47:
  v32 = (void *)*((_QWORD *)this + 1171);
  *((_QWORD *)this + 1174) = a3;
  *((_QWORD *)this + 1175) = v18;
  *((_DWORD *)this + 2352) = v27;
  SetEvent(v32);
  if ( WaitForSingleObject(*((HANDLE *)this + 1173), 0xC8u) == 258 )
  {
    TerminateThread(*((HANDLE *)this + 1170), 1u);
    v33 = (char *)*((_QWORD *)this + 1170);
    if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v33);
      *((_QWORD *)this + 1170) = 0;
    }
    for ( i = 0; i != 3; ++i )
      ResetEvent(*((HANDLE *)this + i + 1171));
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
      "WdcHandleMonitor::AddHandle",
      0,
      L"Querying object name timeout");
    v8 = -2147467259;
    goto LABEL_65;
  }
  v35 = *((_DWORD *)this + 2353);
  if ( v35 )
  {
LABEL_60:
    v37 = RtlNtStatusToDosError(v35);
    v8 = 0;
    if ( v37 )
    {
      if ( v37 > 0 )
        v8 = (unsigned __int16)v37 | 0x80070000;
      else
        v8 = v37;
    }
    if ( v8 < 0 )
      goto LABEL_65;
  }
LABEL_56:
  v63 = v18;
  v13 = v18;
  if ( !*(_WORD *)v18 )
  {
    v8 = 0;
    goto LABEL_101;
  }
  if ( (_DWORD)v5 == *((_DWORD *)this + 2496) )
  {
    v67 = WdcAlloc(0x800u, v20, (int)v21);
    v39 = (unsigned __int16 *)v67;
    if ( !v67 )
    {
LABEL_69:
      v8 = -2147024882;
      LODWORD(ReturnLength) = -2147024882;
LABEL_70:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
        "WdcHandleMonitor::AddHandle",
        0,
        L"FAILURE: 0x%08x",
        ReturnLength);
      goto LABEL_101;
    }
    *(_WORD *)v67 = 0;
    v40 = WdcDiskMonitor::DeviceNameToDosName(*(WdcDiskMonitor **)(*((_QWORD *)this + 1019) + 128LL), v18[1], v39, v38);
    v8 = v40;
    if ( v40 < 0 )
      goto LABEL_72;
    if ( !v40 )
    {
      v40 = StringCchCopyW((unsigned __int16 *)v18[1], *((unsigned __int16 *)v18 + 1), v39);
      v8 = v40;
      if ( v40 < 0 )
        goto LABEL_72;
    }
  }
  v41 = v18[1];
  v42 = SysAllocString(v41);
  v14 = v42;
  if ( v41 && !v42 )
  {
    LODWORD(ReturnLength) = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
      "WdcAssignString",
      0,
      L"FAILURE: 0x%08x",
      ReturnLength);
    goto LABEL_69;
  }
  if ( SubStr )
  {
    CharLowerW((LPWSTR)v18[1]);
    if ( !wcsstr(v18[1], SubStr) )
    {
      v8 = 1;
      goto LABEL_101;
    }
  }
  v43 = WdcHashString(v18[1]);
  v40 = WdcHandleMonitor::CreateEntry(v44, &v66);
  v8 = v40;
  if ( v40 < 0 )
  {
LABEL_72:
    LODWORD(ReturnLength) = v40;
    goto LABEL_70;
  }
  v45 = (char *)this + 16 * (v43 % 0x1F7) + 104;
  v46 = *(_QWORD *)v45;
  if ( *(char **)(*(_QWORD *)v45 + 8LL) != v45 )
    goto LABEL_110;
  v47 = v66;
  v20 = (const char *)a2;
  *(_QWORD *)v66 = v46;
  v48 = (char *)v47 + 16;
  *((_QWORD *)v47 + 1) = v45;
  v49 = (char **)((char *)v47 + 16);
  *(_QWORD *)(v46 + 8) = v47;
  *(_QWORD *)v45 = v47;
  *((double *)v47 + 14) = (double)(int)a2;
  *((_DWORD *)v47 + 26) |= 1u;
  if ( *((struct _WDC_HANDLE_INFO **)v47 + 2) == (struct _WDC_HANDLE_INFO *)((char *)v47 + 16) )
  {
    v50 = (char ***)((char *)this + 88);
    v51 = *((_QWORD *)this + 11);
    if ( *(WdcHandleMonitor **)(v51 + 8) != (WdcHandleMonitor *)((char *)this + 88) )
      goto LABEL_110;
    *v49 = (char *)v51;
    *((_QWORD *)v47 + 3) = v50;
    *(_QWORD *)(v51 + 8) = v49;
    *v50 = v49;
  }
  v21 = (unsigned __int16 **)((char *)v47 + 96);
  v52 = (_WORD *)*((_QWORD *)v47 + 12);
  if ( !v52 || !*v52 )
  {
    ImageName = WdcTraceControl::GetImageName(*((WdcTraceControl **)this + 1019), a2, v21, 1);
    v8 = ImageName;
    if ( ImageName < 0 || ImageName == 1 )
    {
      v8 = 0;
    }
    else
    {
      *((_DWORD *)v47 + 22) |= 1u;
      if ( *v49 == v48 )
      {
        v54 = (char ***)((char *)this + 88);
        v55 = *((_QWORD *)this + 11);
        if ( *(WdcHandleMonitor **)(v55 + 8) != (WdcHandleMonitor *)((char *)this + 88) )
          goto LABEL_110;
        *v49 = (char *)v55;
        *((_QWORD *)v47 + 3) = v54;
        *(_QWORD *)(v55 + 8) = v49;
        *v54 = v49;
      }
    }
  }
  *((_QWORD *)v47 + 16) = *((_QWORD *)this + v15 + 1184);
  *((_DWORD *)v47 + 30) |= 1u;
  if ( *v49 == v48 )
  {
    v56 = (char ***)((char *)this + 88);
    v57 = *((_QWORD *)this + 11);
    if ( *(WdcHandleMonitor **)(v57 + 8) != (WdcHandleMonitor *)((char *)this + 88) )
      goto LABEL_110;
    *v49 = (char *)v57;
    *((_QWORD *)v47 + 3) = v56;
    *(_QWORD *)(v57 + 8) = v49;
    *v56 = v49;
  }
  *((_QWORD *)v47 + 18) = v14;
  v14 = 0;
  *((_DWORD *)v47 + 34) |= 1u;
  if ( *v49 == v48 )
  {
    v58 = (char *)this + 88;
    v59 = *(_QWORD *)v58;
    if ( *(char **)(*(_QWORD *)v58 + 8LL) == v58 )
    {
      *v49 = (char *)v59;
      *((_QWORD *)v47 + 3) = v58;
      *(_QWORD *)(v59 + 8) = v49;
      *(_QWORD *)v58 = v49;
      goto LABEL_100;
    }
LABEL_110:
    __fastfail(3u);
  }
LABEL_100:
  v13 = v63;
LABEL_101:
  v23 = v64;
  if ( v64 )
    goto LABEL_102;
LABEL_103:
  if ( v13 )
    WdcFree(v13, v20, (int)v21);
  if ( v67 )
    WdcFree(v67, v20, (int)v21);
  if ( v14 )
    SysFreeString(v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180038024  mov     r11, rsp
0x180038027  push    rbx
0x180038028  push    rbp
0x180038029  push    rsi
0x18003802a  push    rdi
0x18003802b  push    r12
0x18003802d  push    r13
0x18003802f  push    r14
0x180038031  push    r15
0x180038033  sub     rsp, 0A8h
0x18003803a  mov     rax, cs:__security_cookie
0x180038041  xor     rax, rsp
0x180038044  mov     [rsp+0E8h+var_50], rax
0x18003804c  mov     rax, [rsp+0E8h+arg_20]
0x180038054  xorps   xmm0, xmm0
0x180038057  movups  [rsp+0E8h+ObjectInformation], xmm0
0x18003805c  mov     [rsp+0E8h+SubStr], rax
0x180038061  xor     eax, eax
0x180038063  mov     r14d, r9d
0x180038066  mov     r12, r8
0x180038069  mov     dword ptr [rsp+0E8h+var_A8], edx
0x18003806d  mov     rsi, rcx
0x180038070  mov     [rsp+0E8h+var_A0], rax
0x180038075  movups  [rsp+0E8h+var_78], xmm0
0x18003807a  mov     [r11-58h], rax
0x18003807e  movups  xmmword ptr [r11-68h], xmm0
0x180038083  cmp     r9d, 40h ; '@'
0x180038087  jb      short loc_180038093
0x180038089  mov     ebx, 80004005h
0x18003808e  jmp     loc_18003873E
0x180038093  mov     r9d, 38h ; '8'; ObjectInformationLength
0x180038099  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x18003809e  lea     r8, [rsp+0E8h+ObjectInformation]; ObjectInformation
0x1800380a3  xor     edx, edx; ObjectInformationClass
0x1800380a5  mov     rcx, r12; Handle
0x1800380a8  call    cs:__imp_NtQueryObject
0x1800380ae  test    eax, eax
0x1800380b0  jz      short loc_1800380F9
0x1800380b2  mov     ecx, eax; Status
0x1800380b4  call    cs:__imp_RtlNtStatusToDosError
0x1800380ba  xor     ebx, ebx
0x1800380bc  test    eax, eax
0x1800380be  jz      short loc_1800380CF
0x1800380c0  jg      short loc_1800380C6
0x1800380c2  mov     ebx, eax
0x1800380c4  jmp     short loc_1800380CF
0x1800380c6  movzx   ebx, ax
0x1800380c9  or      ebx, 80070000h
0x1800380cf  test    ebx, ebx
0x1800380d1  jns     short loc_1800380F9
0x1800380d3  mov     dword ptr [rsp+0E8h+ReturnLength], ebx
0x1800380d7  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800380de  xor     r8d, r8d; int
0x1800380e1  lea     rdx, aWdchandlemonit_0; "WdcHandleMonitor::AddHandle"
0x1800380e8  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x1800380ef  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800380f4  jmp     loc_18003873E
0x1800380f9  xor     ebp, ebp
0x1800380fb  mov     [rsp+0E8h+var_B0], 0
0x180038104  xor     r15d, r15d
0x180038107  mov     [rsp+0E8h+var_98], rbp
0x18003810c  mov     r13, r14
0x18003810f  cmp     [rsi+r14*8+2500h], rbp
0x180038117  jnz     loc_180038265
0x18003811d  mov     ebx, [rsp+0E8h+var_60]
0x180038124  add     ebx, 8
0x180038127  mov     ecx, ebx; dwBytes
0x180038129  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18003812e  mov     rdi, rax
0x180038131  test    rax, rax
0x180038134  jnz     short loc_180038143
0x180038136  mov     edi, 8007000Eh
0x18003813b  mov     ebx, edi
0x18003813d  mov     dword ptr [rsp+0E8h+ReturnLength], edi
0x180038141  jmp     short loc_1800380D7
0x180038143  mov     r9d, ebx; ObjectInformationLength
0x180038146  mov     [rsp+0E8h+ReturnLength], rbp; ReturnLength
0x18003814b  mov     r8, rdi; ObjectInformation
0x18003814e  mov     edx, 2; ObjectInformationClass
0x180038153  mov     rcx, r12; Handle
0x180038156  call    cs:__imp_NtQueryObject
0x18003815c  test    eax, eax
0x18003815e  jz      short loc_1800381A7
0x180038160  mov     ecx, eax; Status
0x180038162  call    cs:__imp_RtlNtStatusToDosError
0x180038168  xor     ebx, ebx
0x18003816a  test    eax, eax
0x18003816c  jz      short loc_18003817D
0x18003816e  jg      short loc_180038174
0x180038170  mov     ebx, eax
0x180038172  jmp     short loc_18003817D
0x180038174  movzx   ebx, ax
0x180038177  or      ebx, 80070000h
0x18003817d  test    ebx, ebx
0x18003817f  jns     short loc_1800381A7
0x180038181  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180038188  mov     dword ptr [rsp+0E8h+ReturnLength], ebx
0x18003818c  xor     r8d, r8d; int
0x18003818f  lea     rdx, aWdchandlemonit_0; "WdcHandleMonitor::AddHandle"
0x180038196  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x18003819d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800381a2  jmp     loc_180038480
0x1800381a7  xor     eax, eax
0x1800381a9  mov     [rsp+0E8h+var_B0], rdi
0x1800381ae  cmp     ax, [rdi]
0x1800381b1  jnz     short loc_1800381BD
0x1800381b3  xor     ebx, ebx
0x1800381b5  mov     rcx, rdi
0x1800381b8  jmp     loc_18003870C
0x1800381bd  mov     rcx, [rdi+8]; String1
0x1800381c1  lea     rdx, aFile_0; "File"
0x1800381c8  call    wcscmp_0
0x1800381cd  test    eax, eax
0x1800381cf  jnz     short loc_1800381D8
0x1800381d1  mov     [rsi+2700h], r14d
0x1800381d8  mov     rcx, [rsi+r14*8+2500h]; bstrString
0x1800381e0  mov     rbx, [rdi+8]
0x1800381e4  test    rcx, rcx
0x1800381e7  jz      short loc_1800381F7
0x1800381e9  call    cs:__imp_SysFreeString
0x1800381ef  mov     [rsi+r14*8+2500h], rbp
0x1800381f7  mov     rcx, rbx; psz
0x1800381fa  call    cs:__imp_SysAllocString
0x180038200  test    rbx, rbx
0x180038203  jz      short loc_18003825D
0x180038205  test    rax, rax
0x180038208  jnz     short loc_18003825D
0x18003820a  mov     edi, 8007000Eh
0x18003820f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180038216  xor     r8d, r8d; int
0x180038219  mov     dword ptr [rsp+0E8h+ReturnLength], edi
0x18003821d  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180038224  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18003822b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180038230  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180038237  mov     dword ptr [rsp+0E8h+ReturnLength], edi
0x18003823b  xor     r8d, r8d; int
0x18003823e  lea     rdx, aWdchandlemonit_0; "WdcHandleMonitor::AddHandle"
0x180038245  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x18003824c  mov     ebx, edi
0x18003824e  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180038253  mov     rcx, [rsp+0E8h+var_B0]
0x180038258  jmp     loc_18003870C
0x18003825d  mov     [rsi+r14*8+2500h], rax
0x180038265  mov     ebp, [rsp+0E8h+var_64]
0x18003826c  mov     eax, 208h
0x180038271  test    ebp, ebp
0x180038273  cmovz   ebp, eax
0x180038276  mov     ecx, ebp; dwBytes
0x180038278  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18003827d  mov     rdi, rax
0x180038280  test    rax, rax
0x180038283  jnz     short loc_1800382B5
0x180038285  mov     edi, 8007000Eh
0x18003828a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180038291  xor     r8d, r8d; int
0x180038294  mov     dword ptr [rsp+0E8h+ReturnLength], edi
0x180038298  lea     rdx, aWdchandlemonit_0; "WdcHandleMonitor::AddHandle"
0x18003829f  mov     ebx, edi
0x1800382a1  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x1800382a8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800382ad  mov     rbp, r15
0x1800382b0  jmp     loc_180038702
0x1800382b5  cmp     r14d, [rsi+2700h]
0x1800382bc  jnz     loc_18003843F
0x1800382c2  cmp     [rsi+2490h], r15
0x1800382c9  jnz     short loc_180038349
0x1800382cb  lea     r9, [rsi+2498h]; lpParameter
0x1800382d2  mov     [rsp+0E8h+lpThreadId], r15; lpThreadId
0x1800382d7  lea     r8, ?QueryNameThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800382de  mov     dword ptr [rsp+0E8h+ReturnLength], r15d; dwCreationFlags
0x1800382e3  xor     edx, edx; dwStackSize
0x1800382e5  xor     ecx, ecx; lpThreadAttributes
0x1800382e7  call    cs:__imp_CreateThread
0x1800382ed  mov     [rsi+2490h], rax
0x1800382f4  test    rax, rax
0x1800382f7  jnz     short loc_18003831C
0x1800382f9  call    cs:__imp_GetLastError
0x1800382ff  mov     ebx, eax
0x180038301  test    eax, eax
0x180038303  jz      loc_1800383F7
0x180038309  jle     short loc_180038314
0x18003830b  movzx   ebx, ax
0x18003830e  or      ebx, 80070000h
0x180038314  test    ebx, ebx
0x180038316  js      loc_1800383FC
0x18003831c  cmp     qword ptr [rsi+2490h], 0FFFFFFFFFFFFFFFFh
0x180038324  jnz     short loc_180038349
0x180038326  call    cs:__imp_GetLastError
0x18003832c  mov     ebx, eax
0x18003832e  test    eax, eax
0x180038330  jz      loc_1800383F7
0x180038336  jle     short loc_180038341
0x180038338  movzx   ebx, ax
0x18003833b  or      ebx, 80070000h
0x180038341  test    ebx, ebx
0x180038343  js      loc_1800383FC
0x180038349  mov     rcx, [rsi+2498h]; hEvent
0x180038350  mov     [rsi+24B0h], r12
0x180038357  mov     [rsi+24B8h], rdi
0x18003835e  mov     [rsi+24C0h], ebp
0x180038364  call    cs:__imp_SetEvent
0x18003836a  mov     rcx, [rsi+24A8h]; hHandle
0x180038371  mov     edx, 0C8h; dwMilliseconds
0x180038376  call    cs:__imp_WaitForSingleObject
0x18003837c  cmp     eax, 102h
0x180038381  jnz     loc_18003841F
0x180038387  mov     rcx, [rsi+2490h]; hThread
0x18003838e  mov     edx, 1; dwExitCode
0x180038393  call    cs:__imp_TerminateThread
0x180038399  mov     rcx, [rsi+2490h]; hObject
0x1800383a0  lea     rax, [rcx-1]
0x1800383a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800383a8  ja      short loc_1800383B7
0x1800383aa  call    cs:__imp_CloseHandle
0x1800383b0  mov     [rsi+2490h], r15
0x1800383b7  xor     ebx, ebx
0x1800383b9  mov     rcx, [rsi+rbx*8+2498h]; hEvent
0x1800383c1  call    cs:__imp_ResetEvent
0x1800383c7  inc     rbx
0x1800383ca  cmp     rbx, 3
0x1800383ce  jnz     short loc_1800383B9
0x1800383d0  lea     r9, aQueryingObject; "Querying object name timeout"
0x1800383d7  xor     r8d, r8d; int
0x1800383da  lea     rdx, aWdchandlemonit_0; "WdcHandleMonitor::AddHandle"
0x1800383e1  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x1800383e8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800383ed  mov     ebx, 80004005h
0x1800383f2  jmp     loc_18003847D
0x1800383f7  mov     ebx, 80004005h
0x1800383fc  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180038403  mov     dword ptr [rsp+0E8h+ReturnLength], ebx
0x180038407  xor     r8d, r8d; int
0x18003840a  lea     rdx, aWdchandlemonit_0; "WdcHandleMonitor::AddHandle"
0x180038411  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x180038418  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18003841d  jmp     short loc_18003847D
0x18003841f  mov     ecx, [rsi+24C4h]
0x180038425  test    ecx, ecx
0x180038427  jnz     short loc_18003845E
0x180038429  xor     eax, eax
0x18003842b  mov     [rsp+0E8h+var_B8], rdi
0x180038430  mov     rbp, rdi
0x180038433  cmp     ax, [rdi]
0x180038436  jnz     short loc_18003848D
0x180038438  xor     ebx, ebx
0x18003843a  jmp     loc_180038702
0x18003843f  mov     r9d, ebp; ObjectInformationLength
0x180038442  mov     [rsp+0E8h+ReturnLength], r15; ReturnLength
0x180038447  mov     r8, rdi; ObjectInformation
0x18003844a  mov     edx, 1; ObjectInformationClass
0x18003844f  mov     rcx, r12; Handle
0x180038452  call    cs:__imp_NtQueryObject
0x180038458  test    eax, eax
0x18003845a  jz      short loc_180038429
0x18003845c  mov     ecx, eax; Status
0x18003845e  call    cs:__imp_RtlNtStatusToDosError
0x180038464  xor     ebx, ebx
0x180038466  test    eax, eax
0x180038468  jz      short loc_180038479
0x18003846a  jg      short loc_180038470
0x18003846c  mov     ebx, eax
0x18003846e  jmp     short loc_180038479
0x180038470  movzx   ebx, ax
0x180038473  or      ebx, 80070000h
0x180038479  test    ebx, ebx
0x18003847b  jns     short loc_180038429
0x18003847d  mov     rbp, r15
0x180038480  mov     rcx, rdi; void *
0x180038483  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180038488  jmp     loc_180038702
0x18003848d  cmp     r14d, [rsi+2700h]
0x180038494  jnz     loc_180038522
0x18003849a  mov     ecx, 800h; dwBytes
0x18003849f  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800384a4  mov     [rsp+0E8h+var_98], rax
0x1800384a9  mov     r14, rax
0x1800384ac  test    rax, rax
0x1800384af  jnz     short loc_1800384DE
0x1800384b1  mov     edi, 8007000Eh
0x1800384b6  mov     ebx, edi
0x1800384b8  mov     dword ptr [rsp+0E8h+ReturnLength], edi
0x1800384bc  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800384c3  xor     r8d, r8d; int
0x1800384c6  lea     rdx, aWdchandlemonit_0; "WdcHandleMonitor::AddHandle"
0x1800384cd  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x1800384d4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800384d9  jmp     loc_180038702
0x1800384de  xor     eax, eax
0x1800384e0  mov     [r14], ax
0x1800384e4  mov     rcx, [rsi+1FD8h]
0x1800384eb  mov     r8, r14; unsigned __int16 *
0x1800384ee  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800384f2  mov     rcx, [rcx+80h]; this
0x1800384f9  call    ?DeviceNameToDosName@WdcDiskMonitor@@QEAAJPEBGPEAGK@Z; WdcDiskMonitor::DeviceNameToDosName(ushort const *,ushort *,ulong)
0x1800384fe  mov     ebx, eax
0x180038500  test    eax, eax
0x180038502  jns     short loc_18003850A
0x180038504  mov     dword ptr [rsp+0E8h+ReturnLength], eax
0x180038508  jmp     short loc_1800384BC
  ... truncated ...
```
