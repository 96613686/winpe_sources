# UncompressFileBase

- ea: `0x180024644`
- end: `0x1800250be`
- name: `UncompressFileBase`
- size: `2682`
- prototype: `__int64 __fastcall(int, int, int, int, size_t, __int64, __int64, int, __int64, size_t Size, __int64, int, __int64, __int64, int, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001bd1c`

## callees

- `0x18000ea60`
- `0x180011788`
- `0x180017344`
- `0x1800219c4`
- `0x180024644`
- `0x1800607b0`
- `0x180060e5a`
- `0x180060e70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180024999`
- `KERNEL32!HeapFree` at `0x180024999`
- `KERNEL32!HeapAlloc` at `0x1800248e1`
- `KERNEL32!HeapAlloc` at `0x1800248e1`
- `KERNEL32!GetLastError` at `0x180024908`
- `KERNEL32!GetLastError` at `0x180024962`
- `KERNEL32!GetLastError` at `0x180024ad2`
- `KERNEL32!GetLastError` at `0x180024c02`
- `KERNEL32!GetLastError` at `0x180024908`
- `KERNEL32!GetLastError` at `0x180024962`
- `KERNEL32!GetLastError` at `0x180024ad2`
- `KERNEL32!GetLastError` at `0x180024c02`
- `KERNEL32!SetLastError` at `0x180024764`
- `KERNEL32!SetLastError` at `0x180024783`
- `KERNEL32!SetLastError` at `0x1800249af`
- `KERNEL32!SetLastError` at `0x180024764`
- `KERNEL32!SetLastError` at `0x180024783`
- `KERNEL32!SetLastError` at `0x1800249af`
- `KERNEL32!GetProcessHeap` at `0x1800248cb`
- `KERNEL32!GetProcessHeap` at `0x180024985`
- `KERNEL32!GetProcessHeap` at `0x1800248cb`
- `KERNEL32!GetProcessHeap` at `0x180024985`
- `ntdll!RtlNtStatusToDosError` at `0x180024d03`
- `ntdll!RtlNtStatusToDosError` at `0x180024d20`
- `ntdll!RtlNtStatusToDosError` at `0x180024f2f`
- `ntdll!RtlNtStatusToDosError` at `0x180024f4c`
- `ntdll!RtlNtStatusToDosError` at `0x180024d03`
- `ntdll!RtlNtStatusToDosError` at `0x180024d20`
- `ntdll!RtlNtStatusToDosError` at `0x180024f2f`
- `ntdll!RtlNtStatusToDosError` at `0x180024f4c`

## string_xrefs

- `0x18002479e`: `UncompressFileBase`
- `0x180024940`: `UncompressFileBase`
- `0x180024a9d`: `UncompressFileBase`
- `0x180024ae3`: `UncompressFileBase`
- `0x180024cdf`: `UncompressFileBase`
- `0x180024d6b`: `UncompressFileBase`
- `0x180024e64`: `UncompressFileBase`
- `0x180024f0b`: `UncompressFileBase`
- `0x180024f7e`: `UncompressFileBase`
- `0x18002502d`: `UncompressFileBase`
- `0x180024a7a`: `Integer overflow after ReadData`
- `0x180024aef`: `ReadData failed`
- `0x180024c16`: `ReadData failed`
- `0x180024d4d`: `WriteData failed during NULL block copy`
- `0x180025026`: `Integer overflow after WriteData`
- `0x180024f88`: `WriteData failed`

## pseudocode

```c
__int64 __fastcall UncompressFileBase(
        int a1,
        unsigned int a2,
        unsigned __int64 a3,
        unsigned int a4,
        size_t a5,
        __int64 a6,
        SIZE_T a7,
        unsigned int a8,
        void *a9,
        size_t Size,
        __int64 a11,
        int a12,
        __int64 a13,
        __int64 a14,
        int a15,
        __int64 a16,
        int a17,
        __int64 a18,
        _QWORD *a19)
{
  unsigned __int64 v20; // r14
  __int64 v22; // r13
  __int64 v23; // r15
  SIZE_T v24; // rdi
  int v25; // ecx
  __int64 v27; // rsi
  unsigned int v28; // r10d
  unsigned int v29; // r11d
  unsigned __int64 v30; // rbx
  _BYTE *v31; // rcx
  _BYTE *v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  HANDLE ProcessHeap; // rax
  signed int LastError; // ecx
  NTSTATUS v37; // eax
  int v38; // ebx
  void *v39; // rbx
  HANDLE v40; // rax
  SIZE_T v41; // rcx
  unsigned int v42; // edx
  int v43; // r8d
  int v44; // ebx
  signed __int64 v45; // rax
  signed int v46; // ebx
  NTSTATUS v47; // eax
  unsigned int v48; // ebx
  SIZE_T v49; // rdx
  __int64 v50; // rcx
  __int64 (__fastcall *v51)(__int64, SIZE_T, _QWORD, _QWORD *); // rax
  SIZE_T v52; // rdi
  DWORD v53; // eax
  const char *v54; // r9
  int v55; // ecx
  NTSTATUS v56; // eax
  unsigned int v57; // ecx
  __int64 v58; // r9
  __int64 (__fastcall *v59)(__int64, __int64, void *, __int64, __int64 *); // rax
  __int64 v60; // rcx
  NTSTATUS v61; // eax
  __int64 v62; // rdx
  SIZE_T v63; // rcx
  NTSTATUS v64; // edx
  ULONG v65; // eax
  unsigned int v66; // edx
  unsigned int v67; // eax
  SIZE_T v68; // r8
  __int64 v69; // rcx
  __int64 (__fastcall *v70)(__int64, __int64, void *, __int64, __int64 *); // rax
  NTSTATUS v71; // eax
  __int64 v72; // rdx
  NTSTATUS v73; // edx
  ULONG v74; // eax
  NTSTATUS v75; // eax
  SIZE_T v76; // rax
  __int64 v77; // rax
  NTSTATUS v78[2]; // [rsp+20h] [rbp-E0h]
  int v79; // [rsp+30h] [rbp-D0h]
  DWORD dwErrCode; // [rsp+40h] [rbp-C0h]
  unsigned int v81; // [rsp+44h] [rbp-BCh]
  NTSTATUS Status; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v83; // [rsp+4Ch] [rbp-B4h]
  SIZE_T dwBytes; // [rsp+50h] [rbp-B0h]
  unsigned int v85; // [rsp+58h] [rbp-A8h]
  int v86[2]; // [rsp+60h] [rbp-A0h]
  int v87[2]; // [rsp+68h] [rbp-98h]
  signed __int64 v88; // [rsp+70h] [rbp-90h]
  LPVOID lpMem; // [rsp+78h] [rbp-88h]
  __int64 v90; // [rsp+80h] [rbp-80h]
  __int64 v91; // [rsp+88h] [rbp-78h]
  unsigned int v92; // [rsp+90h] [rbp-70h]
  __int64 v93; // [rsp+98h] [rbp-68h]
  void *v94; // [rsp+A0h] [rbp-60h]
  unsigned int v95; // [rsp+A8h] [rbp-58h]
  __int64 v96; // [rsp+B0h] [rbp-50h]
  __int64 v97; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v98; // [rsp+C0h] [rbp-40h]
  int v99; // [rsp+C8h] [rbp-38h]
  int v100; // [rsp+CCh] [rbp-34h]
  __int64 v101; // [rsp+D0h] [rbp-30h]
  SIZE_T v102; // [rsp+D8h] [rbp-28h]
  __int64 v103; // [rsp+E0h] [rbp-20h]
  __int64 v104; // [rsp+E8h] [rbp-18h]
  __int64 v105; // [rsp+F0h] [rbp-10h]
  _QWORD *v106; // [rsp+F8h] [rbp-8h]
  _QWORD v107[2]; // [rsp+100h] [rbp+0h] BYREF
  int v108; // [rsp+110h] [rbp+10h]
  int v109; // [rsp+114h] [rbp+14h]
  __int64 v110; // [rsp+118h] [rbp+18h]
  __int64 v111; // [rsp+120h] [rbp+20h]
  _BYTE v112[1024]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t Buffer[64]; // [rsp+530h] [rbp+430h] BYREF

  v20 = a3;
  *(_QWORD *)v86 = a6;
  v102 = a7;
  v94 = a9;
  *(_QWORD *)v87 = a13;
  v103 = a16;
  v111 = a11;
  v105 = a18;
  v92 = a2;
  v22 = 0;
  v93 = a3;
  v104 = a14;
  v85 = 0;
  dwErrCode = 0;
  v23 = 0;
  v90 = 0;
  v24 = 0;
  v96 = 0;
  v106 = a19;
  v81 = 1;
  memset_0(v112, 0, sizeof(v112));
  lpMem = 0;
  memset_0(v107, 0, 0x20u);
  memset_0(&v97, 0, 0x20u);
  if ( a19 )
    *a19 = 0;
  if ( !v92 || !a1 )
  {
    SetLastError(0xDu);
    v25 = 0;
    v81 = 0;
LABEL_8:
    if ( (unsigned int)Size >= v92 )
      goto LABEL_10;
    goto LABEL_9;
  }
  if ( a8 >= v92 )
  {
    v25 = 1;
    goto LABEL_8;
  }
LABEL_9:
  SetLastError(0xEAu);
  v25 = 0;
  v81 = 0;
LABEL_10:
  if ( !v25 )
  {
    WIMLogMsg(1, v87[0], v86[0], (int)L"Failed to get img buf", -2147024883, (__int64)L"UncompressFileBase", 75);
    return 0;
  }
  v27 = a5;
  v28 = (__int64)(v92 + a5 - 1) / v92 - 1;
  v91 = v28;
  v29 = 4;
  if ( HIDWORD(a5) )
    v29 = 8;
  v83 = v29;
  if ( (unsigned int)((__int64)(v92 + a5 - 1) / v92) == 1 )
    goto LABEL_38;
  v25 = 0;
  v30 = v28 * (unsigned __int64)v29;
  v81 = 0;
  if ( v30 > 0xFFFFFFFF )
  {
    v38 = 534;
    dwErrCode = 534;
    goto LABEL_28;
  }
  if ( (unsigned int)v30 <= v28 )
    goto LABEL_38;
  dwBytes = (unsigned int)v30;
  if ( (unsigned int)v30 > 0x400 )
  {
    ProcessHeap = GetProcessHeap();
    v31 = HeapAlloc(ProcessHeap, 0, dwBytes);
    lpMem = v31;
    if ( !v31 )
    {
      LastError = GetLastError();
      dwErrCode = LastError;
      v37 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v37 = LastError;
      WIMLogMsg(1, v87[0], v86[0], (int)L"fmalloc failed", v37, (__int64)L"UncompressFileBase", 134);
      goto LABEL_27;
    }
  }
  else
  {
    v31 = v112;
    lpMem = v112;
  }
  v32 = v31;
  v109 = HIDWORD(v93);
  v108 = v20;
  v33 = *(_QWORD *)(v103 + 16);
  v110 = *(_QWORD *)(v103 + 8);
  v81 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD *))v103)(v33, v32, (unsigned int)v30, v107);
  v25 = v81;
  if ( !v81 )
  {
    v46 = GetLastError();
    dwErrCode = v46;
    v47 = (unsigned __int16)v46 | 0x80070000;
    if ( v46 <= 0 )
      v47 = v46;
    WIMLogMsg(2, v87[0], v86[0], (int)L"ReadData failed", v47, (__int64)L"UncompressFileBase", 196);
    v25 = 0;
    v28 = v91;
    v29 = v83;
    goto LABEL_38;
  }
  v34 = dwBytes + v20;
  if ( dwBytes + v20 >= v20 )
  {
    v29 = v83;
    v20 += dwBytes;
    v93 = v34;
    if ( v83 == 4 )
    {
      LODWORD(v90) = *(_DWORD *)lpMem;
      v25 = v81;
    }
    else
    {
      v90 = *(_QWORD *)lpMem;
    }
    a4 -= dwBytes;
    v28 = v91;
    v24 = dwBytes & -(__int64)(a15 != 0);
LABEL_38:
    v38 = dwErrCode;
    goto LABEL_39;
  }
  v20 = -1;
  v81 = 0;
  v38 = 534;
  v93 = -1;
  dwErrCode = 534;
  WIMLogMsg(
    2,
    v87[0],
    v86[0],
    (int)L"Integer overflow after ReadData",
    -2147024362,
    (__int64)L"UncompressFileBase",
    185);
  v28 = v91;
  v25 = 0;
  v29 = v83;
LABEL_39:
  if ( !v25 )
    goto LABEL_28;
  do
  {
    if ( !v27 )
      break;
    v41 = v102;
    dwBytes = v102;
    if ( a8 >= v27 )
    {
      v48 = a4;
    }
    else
    {
      v88 = 0;
      v42 = v85;
      v43 = 1;
      v44 = v22;
      do
      {
        if ( v42 >= v28 )
          break;
        if ( v29 == 4 )
        {
          LODWORD(v88) = *((_DWORD *)lpMem + v42);
          v45 = v88;
        }
        else
        {
          v45 = *((_QWORD *)lpMem + v42);
          v88 = v45;
        }
        if ( v45 > a8 + v22 )
        {
          v43 = 0;
        }
        else
        {
          ++v42;
          v44 = v45;
        }
      }
      while ( v43 );
      v41 = v102;
      v48 = v44 - v22;
    }
    if ( v48 > a8 )
      v48 = a8;
    if ( !v48 )
    {
      memset_0(v94, 0, (unsigned int)Size);
      while ( 1 )
      {
        v25 = 1;
        v81 = 1;
        if ( v27 <= 0 )
          goto LABEL_89;
        v57 = v27;
        if ( (unsigned int)Size < v27 )
          v57 = Size;
        v97 = 0;
        v58 = v57;
        v98 = 0;
        v100 = HIDWORD(v96);
        v101 = *(_QWORD *)(v104 + 8);
        v59 = *(__int64 (__fastcall **)(__int64, __int64, void *, __int64, __int64 *))v104;
        LODWORD(v88) = v57;
        v60 = *(_QWORD *)(v104 + 16);
        v99 = v23;
        v61 = v59(v60, v27, v94, v58, &v97);
        Status = v61;
        if ( v61 < 0 )
        {
          UtilReportError(L"UncompressFileBase", v62, 372, (unsigned int)v61);
          v64 = Status;
          v81 = 0;
          if ( (Status & 0x10000000) != 0 )
          {
            if ( RtlNtStatusToDosError(Status) == 317 )
              v65 = Status;
            else
              v65 = RtlNtStatusToDosError(Status);
            v64 = v65;
            dwErrCode = v65;
          }
          else
          {
            if ( (Status & 0x1FFF0000) == 0x70000 )
              v64 = (unsigned __int16)Status;
            dwErrCode = v64;
          }
          v54 = L"WriteData failed during NULL block copy";
          v56 = (unsigned __int16)v64 | 0x80070000;
          v79 = 398;
          if ( v64 <= 0 )
            v56 = v64;
          goto LABEL_87;
        }
        v63 = v24;
        v23 += (unsigned int)v88;
        v27 -= (unsigned int)v88;
        v96 = v23;
        v24 += (unsigned int)v88;
        if ( !a15 )
          v24 = v63;
      }
    }
    v49 = v41;
    v107[0] = 0;
    v107[1] = 0;
    v50 = *(_QWORD *)(v103 + 16);
    v109 = HIDWORD(v93);
    v110 = *(_QWORD *)(v103 + 8);
    v51 = *(__int64 (__fastcall **)(__int64, SIZE_T, _QWORD, _QWORD *))v103;
    v108 = v20;
    v81 = v51(v50, v49, v48, v107);
    v25 = v81;
    if ( v81 )
    {
      v20 += v48;
      a4 -= v48;
      v93 = v20;
      if ( !a15 )
        goto LABEL_89;
      v52 = v48 + v24;
      CopyProgressUpdate(v105, v52);
      if ( v106 )
        *v106 += v52;
      v24 = 0;
    }
    else
    {
      v53 = GetLastError();
      v79 = 332;
      v54 = L"ReadData failed";
      v55 = v53;
      dwErrCode = v53;
      v56 = (unsigned __int16)v53 | 0x80070000;
      if ( v55 <= 0 )
        v56 = v55;
LABEL_87:
      WIMLogMsg(1, v87[0], v86[0], (int)v54, v56, (__int64)L"UncompressFileBase", v79);
    }
    v25 = v81;
LABEL_89:
    if ( !v25 )
      goto LABEL_27;
    while ( v48 )
    {
      v66 = v92;
      if ( v92 > v27 )
        v66 = v27;
      v95 = v66;
      if ( v85 >= (unsigned int)v91 )
        v67 = v48;
      else
        v67 = v90 - v22;
      LODWORD(v88) = v67;
      if ( v67 >= v92 )
      {
LABEL_105:
        v68 = dwBytes;
        goto LABEL_106;
      }
      if ( !v67 )
      {
        memset_0(v94, 0, v66);
        goto LABEL_103;
      }
      if ( v85 >= (unsigned int)v91 && v67 == (_DWORD)v27 )
        goto LABEL_105;
      Status = 0;
      v78[0] = v66;
      v81 = (*(__int64 (__fastcall **)(__int64, SIZE_T, _QWORD, void *, NTSTATUS *, NTSTATUS *))(v111 + 16))(
              v111,
              dwBytes,
              v67,
              v94,
              *(NTSTATUS **)v78,
              &Status);
      v25 = v81;
      if ( !v81 )
      {
        memset_0(Buffer, 0, sizeof(Buffer));
        dwErrCode = 1392;
        StringCchPrintfW(Buffer, 0x40u, L"file corrupted in block at offset %p", dwBytes);
        WIMLogMsg(2, v87[0], v86[0], (int)Buffer, -2147023504, (__int64)L"UncompressFileBase", 473);
LABEL_103:
        v25 = v81;
      }
      v68 = (SIZE_T)v94;
      v66 = v95;
LABEL_106:
      if ( !v25 )
        goto LABEL_27;
      v97 = 0;
      v98 = 0;
      v69 = *(_QWORD *)(v104 + 16);
      v100 = HIDWORD(v96);
      v101 = *(_QWORD *)(v104 + 8);
      v70 = *(__int64 (__fastcall **)(__int64, __int64, void *, __int64, __int64 *))v104;
      v99 = v23;
      v71 = v70(v69, v27, (void *)v68, v66, &v97);
      Status = v71;
      if ( v71 >= 0 )
      {
        v23 += v95;
        v81 = 1;
        v27 -= v95;
        v96 = v23;
        v76 = v24 + v95;
        if ( !a15 )
          v76 = v24;
        v24 = v76;
        if ( v48 < (unsigned int)v88 )
        {
          v81 = 0;
          dwErrCode = 534;
          v48 = -1;
          WIMLogMsg(
            2,
            v87[0],
            v86[0],
            (int)L"Integer overflow after WriteData",
            -2147024362,
            (__int64)L"UncompressFileBase",
            563);
        }
        else
        {
          v48 -= v88;
          if ( v48 || v27 )
          {
            dwBytes += (unsigned int)v88;
            v22 = v90;
            v77 = v85 + 1;
            v85 = v77;
            if ( (unsigned int)v77 < (unsigned int)v91 )
            {
              if ( v83 == 4 )
                LODWORD(v90) = *((_DWORD *)lpMem + v77);
              else
                v90 = *((_QWORD *)lpMem + v77);
            }
          }
        }
      }
      else
      {
        UtilReportError(L"UncompressFileBase", v72, 508, (unsigned int)v71);
        v73 = Status;
        v81 = 0;
        if ( (Status & 0x10000000) != 0 )
        {
          if ( RtlNtStatusToDosError(Status) == 317 )
            v74 = Status;
          else
            v74 = RtlNtStatusToDosError(Status);
          v73 = v74;
          dwErrCode = v74;
        }
        else
        {
          if ( (Status & 0x1FFF0000) == 0x70000 )
            v73 = (unsigned __int16)Status;
          dwErrCode = v73;
        }
        v75 = (unsigned __int16)v73 | 0x80070000;
        if ( v73 <= 0 )
          v75 = v73;
        WIMLogMsg(2, v87[0], v86[0], (int)L"WriteData failed", v75, (__int64)L"UncompressFileBase", 572);
      }
      v25 = v81;
      if ( !v81 )
        break;
    }
    v28 = v91;
    v29 = v83;
  }
  while ( v25 );
  if ( v25 )
  {
    if ( a15 )
    {
      if ( v24 )
      {
        CopyProgressUpdate(v105, v24);
        if ( v106 )
          *v106 += v24;
      }
    }
    goto LABEL_30;
  }
LABEL_27:
  v38 = dwErrCode;
LABEL_28:
  if ( !v38 )
    dwErrCode = GetLastError();
LABEL_30:
  v39 = lpMem;
  if ( lpMem && lpMem != v112 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v39);
  }
  if ( dwErrCode )
    SetLastError(dwErrCode);
  return v81;
}

```

## disassembly

```asm
0x180024644  mov     [rsp-8+arg_0], rbx
0x180024649  push    rbp
0x18002464a  push    rsi
0x18002464b  push    rdi
0x18002464c  push    r12
0x18002464e  push    r13
0x180024650  push    r14
0x180024652  push    r15
0x180024654  lea     rbp, [rsp-4C0h]
0x18002465c  sub     rsp, 5C0h
0x180024663  mov     rax, cs:__security_cookie
0x18002466a  xor     rax, rsp
0x18002466d  mov     [rbp+4F0h+var_40], rax
0x180024674  mov     rax, [rbp+4F0h+arg_28]
0x18002467b  mov     ebx, ecx
0x18002467d  mov     rcx, [rbp+4F0h+arg_50]
0x180024684  mov     r14, r8
0x180024687  mov     rsi, [rbp+4F0h+arg_90]
0x18002468e  mov     r12, r9
0x180024691  mov     qword ptr [rsp+5F0h+var_590], rax
0x180024696  mov     rax, [rbp+4F0h+arg_30]
0x18002469d  mov     [rbp+4F0h+var_518], rax
0x1800246a1  mov     rax, [rbp+4F0h+arg_40]
0x1800246a8  mov     [rbp+4F0h+var_550], rax
0x1800246ac  mov     rax, [rbp+4F0h+arg_60]
0x1800246b3  mov     qword ptr [rsp+5F0h+var_588], rax
0x1800246b8  mov     rax, [rbp+4F0h+arg_78]
0x1800246bf  mov     [rbp+4F0h+var_510], rax
0x1800246c3  mov     rax, [rbp+4F0h+arg_88]
0x1800246ca  mov     [rbp+4F0h+var_4D0], rcx
0x1800246ce  mov     rcx, [rbp+4F0h+arg_68]
0x1800246d5  mov     [rbp+4F0h+var_500], rax
0x1800246d9  xor     eax, eax
0x1800246db  mov     [rbp+4F0h+var_560], edx
0x1800246de  mov     r13d, eax
0x1800246e1  mov     [rbp+4F0h+var_558], r8
0x1800246e5  xor     edx, edx; Val
0x1800246e7  mov     [rbp+4F0h+var_508], rcx
0x1800246eb  mov     r8d, 400h; Size
0x1800246f1  lea     rcx, [rbp+4F0h+var_4C0]; void *
0x1800246f5  mov     [rsp+5F0h+var_598], eax
0x1800246f9  mov     [rsp+5F0h+dwErrCode], eax
0x1800246fd  mov     r15d, eax
0x180024700  mov     [rbp+4F0h+var_570], rax
0x180024704  mov     edi, eax
0x180024706  mov     [rbp+4F0h+var_540], rax
0x18002470a  mov     [rbp+4F0h+var_4F8], rsi
0x18002470e  mov     [rsp+5F0h+var_5AC], 1
0x180024716  call    memset_0
0x18002471b  and     [rsp+5F0h+lpMem], rdi
0x180024720  lea     r8d, [rdi+20h]; Size
0x180024724  xor     edx, edx; Val
0x180024726  lea     rcx, [rbp+4F0h+var_4F0]; void *
0x18002472a  call    memset_0
0x18002472f  xor     edx, edx; Val
0x180024731  lea     r8d, [rdi+20h]; Size
0x180024735  lea     rcx, [rbp+4F0h+var_538]; void *
0x180024739  call    memset_0
0x18002473e  test    rsi, rsi
0x180024741  jz      short loc_180024746
0x180024743  and     [rsi], rdi
0x180024746  mov     esi, [rbp+4F0h+var_560]
0x180024749  test    esi, esi
0x18002474b  jz      short loc_18002475F
0x18002474d  test    ebx, ebx
0x18002474f  jz      short loc_18002475F
0x180024751  cmp     [rbp+4F0h+arg_38], esi
0x180024757  jb      short loc_18002477E
0x180024759  mov     ecx, [rsp+5F0h+var_5AC]
0x18002475d  jmp     short loc_180024776
0x18002475f  mov     ecx, 0Dh; dwErrCode
0x180024764  call    cs:__imp_SetLastError
0x18002476b  nop     dword ptr [rax+rax+00h]
0x180024770  xor     ecx, ecx
0x180024772  mov     [rsp+5F0h+var_5AC], ecx
0x180024776  cmp     dword ptr [rbp+4F0h+Size], esi
0x18002477c  jnb     short loc_180024795
0x18002477e  mov     ecx, 0EAh; dwErrCode
0x180024783  call    cs:__imp_SetLastError
0x18002478a  nop     dword ptr [rax+rax+00h]
0x18002478f  xor     ecx, ecx
0x180024791  mov     [rsp+5F0h+var_5AC], ecx
0x180024795  test    ecx, ecx
0x180024797  jnz     short loc_1800247D7
0x180024799  mov     r8, qword ptr [rsp+5F0h+var_590]; int
0x18002479e  lea     rax, aUncompressfile_0; "UncompressFileBase"
0x1800247a5  mov     rdx, qword ptr [rsp+5F0h+var_588]; int
0x1800247aa  lea     r9, aFailedToGetImg_0; "Failed to get img buf"
0x1800247b1  mov     [rsp+5F0h+var_5C0], 4Bh ; 'K'; int
0x1800247b9  mov     ecx, 1; int
0x1800247be  mov     [rsp+5F0h+var_5C8], rax; __int64
0x1800247c3  mov     [rsp+5F0h+var_5D0], 8007000Dh; Status
0x1800247cb  call    _WIMLogMsg
0x1800247d0  xor     eax, eax
0x1800247d2  jmp     loc_1800249BF
0x1800247d7  mov     r8, rsi
0x1800247da  mov     rsi, [rbp+4F0h+arg_20]
0x1800247e1  lea     rax, [rsi-1]
0x1800247e5  add     rax, r8
0x1800247e8  cqo
0x1800247ea  idiv    r8
0x1800247ed  cmp     dword ptr [rbp+4F0h+arg_20+4], edi
0x1800247f3  mov     edx, 0FFFFFFFFh
0x1800247f8  lea     r10d, [rax-1]
0x1800247fc  mov     eax, 8
0x180024801  mov     [rbp+4F0h+var_568], r10
0x180024805  lea     r11d, [rax-4]
0x180024809  cmovnz  r11d, eax
0x18002480d  mov     [rsp+5F0h+var_5A4], r11d
0x180024812  test    r10d, r10d
0x180024815  jz      loc_180024A05
0x18002481b  xor     ecx, ecx
0x18002481d  mov     ebx, r11d
0x180024820  mov     eax, r10d
0x180024823  imul    rbx, rax
0x180024827  mov     [rsp+5F0h+var_5AC], ecx
0x18002482b  cmp     rbx, rdx
0x18002482e  ja      loc_180024B36
0x180024834  cmp     ebx, r10d
0x180024837  jbe     loc_180024A05
0x18002483d  mov     eax, ebx
0x18002483f  mov     [rsp+5F0h+dwBytes], rax
0x180024844  cmp     ebx, 400h
0x18002484a  ja      short loc_1800248CB
0x18002484c  lea     rcx, [rbp+4F0h+var_4C0]
0x180024850  mov     [rsp+5F0h+lpMem], rcx
0x180024855  mov     r10, [rbp+4F0h+var_510]
0x180024859  lea     r9, [rbp+4F0h+var_4F0]
0x18002485d  mov     eax, dword ptr [rbp+4F0h+var_558+4]
0x180024860  mov     rdx, rcx
0x180024863  mov     [rbp+4F0h+var_4DC], eax
0x180024866  mov     r8d, ebx
0x180024869  mov     [rbp+4F0h+var_4E0], r14d
0x18002486d  mov     rax, [r10+8]
0x180024871  mov     rcx, [r10+10h]
0x180024875  mov     [rbp+4F0h+var_4D8], rax
0x180024879  mov     rax, [r10]
0x18002487c  call    cs:__guard_dispatch_icall_fptr
0x180024882  mov     [rsp+5F0h+var_5AC], eax
0x180024886  mov     ecx, eax
0x180024888  test    eax, eax
0x18002488a  jz      loc_180024AD2
0x180024890  mov     rdx, [rsp+5F0h+dwBytes]
0x180024895  lea     rax, [rdx+r14]
0x180024899  cmp     rax, r14
0x18002489c  jb      loc_180024A75
0x1800248a2  mov     r11d, [rsp+5F0h+var_5A4]
0x1800248a7  mov     r14, rax
0x1800248aa  mov     [rbp+4F0h+var_558], rax
0x1800248ae  mov     rax, [rsp+5F0h+lpMem]
0x1800248b3  cmp     r11d, 4
0x1800248b7  jnz     loc_1800249E9
0x1800248bd  mov     ecx, [rax]
0x1800248bf  mov     dword ptr [rbp+4F0h+var_570], ecx
0x1800248c2  mov     ecx, [rsp+5F0h+var_5AC]
0x1800248c6  jmp     loc_1800249F0
0x1800248cb  call    cs:__imp_GetProcessHeap
0x1800248d2  nop     dword ptr [rax+rax+00h]
0x1800248d7  mov     r8, [rsp+5F0h+dwBytes]; dwBytes
0x1800248dc  xor     edx, edx; dwFlags
0x1800248de  mov     rcx, rax; hHeap
0x1800248e1  call    cs:__imp_HeapAlloc
0x1800248e8  nop     dword ptr [rax+rax+00h]
0x1800248ed  mov     rcx, rax
0x1800248f0  mov     [rsp+5F0h+lpMem], rax
0x1800248f5  mov     rax, [rsp+5F0h+dwBytes]
0x1800248fa  mov     [rsp+5F0h+dwBytes], rax
0x1800248ff  test    rcx, rcx
0x180024902  jnz     loc_180024855
0x180024908  call    cs:__imp_GetLastError
0x18002490f  nop     dword ptr [rax+rax+00h]
0x180024914  mov     r8, qword ptr [rsp+5F0h+var_590]; int
0x180024919  lea     r9, aFmallocFailed; "fmalloc failed"
0x180024920  mov     rdx, qword ptr [rsp+5F0h+var_588]; int
0x180024925  mov     ecx, eax
0x180024927  mov     [rsp+5F0h+dwErrCode], eax
0x18002492b  movzx   eax, ax
0x18002492e  or      eax, 80070000h
0x180024933  mov     [rsp+5F0h+var_5C0], 86h; int
0x18002493b  test    ecx, ecx
0x18002493d  cmovle  eax, ecx
0x180024940  lea     rcx, aUncompressfile_0; "UncompressFileBase"
0x180024947  mov     [rsp+5F0h+var_5C8], rcx; __int64
0x18002494c  mov     ecx, 1; int
0x180024951  mov     [rsp+5F0h+var_5D0], eax; Status
0x180024955  call    _WIMLogMsg
0x18002495a  mov     ebx, [rsp+5F0h+dwErrCode]
0x18002495e  test    ebx, ebx
0x180024960  jnz     short loc_180024972
0x180024962  call    cs:__imp_GetLastError
0x180024969  nop     dword ptr [rax+rax+00h]
0x18002496e  mov     [rsp+5F0h+dwErrCode], eax
0x180024972  mov     rbx, [rsp+5F0h+lpMem]
0x180024977  test    rbx, rbx
0x18002497a  jz      short loc_1800249A5
0x18002497c  lea     rax, [rbp+4F0h+var_4C0]
0x180024980  cmp     rbx, rax
0x180024983  jz      short loc_1800249A5
0x180024985  call    cs:__imp_GetProcessHeap
0x18002498c  nop     dword ptr [rax+rax+00h]
0x180024991  mov     r8, rbx; lpMem
0x180024994  xor     edx, edx; dwFlags
0x180024996  mov     rcx, rax; hHeap
0x180024999  call    cs:__imp_HeapFree
0x1800249a0  nop     dword ptr [rax+rax+00h]
0x1800249a5  mov     eax, [rsp+5F0h+dwErrCode]
0x1800249a9  test    eax, eax
0x1800249ab  jz      short loc_1800249BB
0x1800249ad  mov     ecx, eax; dwErrCode
0x1800249af  call    cs:__imp_SetLastError
0x1800249b6  nop     dword ptr [rax+rax+00h]
0x1800249bb  mov     eax, [rsp+5F0h+var_5AC]
0x1800249bf  mov     rcx, [rbp+4F0h+var_40]
0x1800249c6  xor     rcx, rsp; StackCookie
0x1800249c9  call    __security_check_cookie
0x1800249ce  mov     rbx, [rsp+5F0h+arg_0]
0x1800249d6  add     rsp, 5C0h
0x1800249dd  pop     r15
0x1800249df  pop     r14
0x1800249e1  pop     r13
0x1800249e3  pop     r12
0x1800249e5  pop     rdi
0x1800249e6  pop     rsi
0x1800249e7  pop     rbp
0x1800249e8  retn
0x1800249e9  mov     rax, [rax]
0x1800249ec  mov     [rbp+4F0h+var_570], rax
0x1800249f0  mov     eax, [rbp+4F0h+arg_70]
0x1800249f6  sub     r12, rdx
0x1800249f9  mov     r10, [rbp+4F0h+var_568]
0x1800249fd  neg     eax
0x1800249ff  sbb     rdi, rdi
0x180024a02  and     rdi, rdx
0x180024a05  mov     ebx, [rsp+5F0h+dwErrCode]
0x180024a09  test    ecx, ecx
0x180024a0b  jz      loc_18002495E
0x180024a11  test    rsi, rsi
0x180024a14  jz      loc_18002507F
0x180024a1a  mov     eax, [rbp+4F0h+arg_38]
0x180024a20  mov     rcx, [rbp+4F0h+var_518]
0x180024a24  mov     [rsp+5F0h+dwBytes], rcx
0x180024a29  cmp     rax, rsi
0x180024a2c  jge     loc_180024B6E
0x180024a32  and     [rsp+5F0h+var_580], 0
0x180024a38  lea     rcx, [rax+r13]
0x180024a3c  mov     edx, [rsp+5F0h+var_598]
0x180024a40  mov     r8d, 1
0x180024a46  mov     r9, [rsp+5F0h+lpMem]
0x180024a4b  mov     rbx, r13
0x180024a4e  cmp     edx, r10d
0x180024a51  jnb     loc_180024B65
0x180024a57  mov     eax, edx
0x180024a59  cmp     r11d, 4
0x180024a5d  jnz     loc_180024B44
0x180024a63  mov     eax, [r9+rax*4]
0x180024a67  mov     dword ptr [rsp+5F0h+var_580], eax
0x180024a6b  mov     rax, [rsp+5F0h+var_580]
0x180024a70  jmp     loc_180024B4D
0x180024a75  mov     r8, qword ptr [rsp+5F0h+var_590]; int
0x180024a7a  lea     r9, aIntegerOverflo; "Integer overflow after ReadData"
0x180024a81  mov     rdx, qword ptr [rsp+5F0h+var_588]; int
0x180024a86  or      r14, 0FFFFFFFFFFFFFFFFh
0x180024a8a  xor     eax, eax
0x180024a8c  mov     [rsp+5F0h+var_5C0], 0B9h; int
0x180024a94  mov     [rsp+5F0h+var_5AC], eax
0x180024a98  mov     ebx, 216h
0x180024a9d  lea     rax, aUncompressfile_0; "UncompressFileBase"
0x180024aa4  mov     [rbp+4F0h+var_558], r14
0x180024aa8  mov     [rsp+5F0h+var_5C8], rax; __int64
0x180024aad  lea     ecx, [r14+3]; int
0x180024ab1  mov     [rsp+5F0h+var_5D0], 80070216h; Status
0x180024ab9  mov     [rsp+5F0h+dwErrCode], ebx
0x180024abd  call    _WIMLogMsg
0x180024ac2  mov     r10, [rbp+4F0h+var_568]
0x180024ac6  mov     ecx, edi
0x180024ac8  mov     r11d, [rsp+5F0h+var_5A4]
0x180024acd  jmp     loc_180024A09
0x180024ad2  call    cs:__imp_GetLastError
0x180024ad9  nop     dword ptr [rax+rax+00h]
0x180024ade  mov     r8, qword ptr [rsp+5F0h+var_590]; int
0x180024ae3  lea     rcx, aUncompressfile_0; "UncompressFileBase"
0x180024aea  mov     rdx, qword ptr [rsp+5F0h+var_588]; int
0x180024aef  lea     r9, aReaddataFailed; "ReadData failed"
0x180024af6  mov     ebx, eax
0x180024af8  mov     [rsp+5F0h+dwErrCode], eax
0x180024afc  movzx   eax, ax
0x180024aff  or      eax, 80070000h
0x180024b04  mov     [rsp+5F0h+var_5C0], 0C4h; int
0x180024b0c  mov     [rsp+5F0h+var_5C8], rcx; __int64
0x180024b11  test    ebx, ebx
0x180024b13  mov     ecx, 2; int
0x180024b18  cmovle  eax, ebx
0x180024b1b  mov     [rsp+5F0h+var_5D0], eax; Status
0x180024b1f  call    _WIMLogMsg
0x180024b24  mov     ecx, [rsp+5F0h+var_5AC]
0x180024b28  mov     r10, [rbp+4F0h+var_568]
0x180024b2c  mov     r11d, [rsp+5F0h+var_5A4]
0x180024b31  jmp     loc_180024A05
0x180024b36  mov     ebx, 216h
0x180024b3b  mov     [rsp+5F0h+dwErrCode], ebx
  ... truncated ...
```
