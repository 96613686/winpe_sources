# BlbutilShutdownService(ushort *,int,ulong,ulong)

- ea: `0x140090bb0`
- end: `0x140091319`
- name: `?BlbutilShutdownService@@YAJPEAGHKK@Z`
- size: `1897`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140090bb0`
- `0x1400f40ac`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x140090bb0`
- `0x140134d20`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x140090cd6`
- `ADVAPI32!OpenSCManagerW` at `0x140090cd6`
- `ADVAPI32!CloseServiceHandle` at `0x1400912b2`
- `ADVAPI32!CloseServiceHandle` at `0x1400912c0`
- `ADVAPI32!CloseServiceHandle` at `0x1400912b2`
- `ADVAPI32!CloseServiceHandle` at `0x1400912c0`
- `ADVAPI32!OpenServiceW` at `0x140090d54`
- `ADVAPI32!OpenServiceW` at `0x140090d54`
- `ADVAPI32!ControlService` at `0x140090e91`
- `ADVAPI32!ControlService` at `0x140090e91`
- `ADVAPI32!QueryServiceStatus` at `0x140090dca`
- `ADVAPI32!QueryServiceStatus` at `0x140090dca`
- `ADVAPI32!EnumDependentServicesW` at `0x140090f07`
- `ADVAPI32!EnumDependentServicesW` at `0x140090fc5`
- `ADVAPI32!EnumDependentServicesW` at `0x140090f07`
- `ADVAPI32!EnumDependentServicesW` at `0x140090fc5`
- `KERNEL32!GetProcessHeap` at `0x140090f6f`
- `KERNEL32!GetProcessHeap` at `0x140091296`
- `KERNEL32!GetProcessHeap` at `0x140090f6f`
- `KERNEL32!GetProcessHeap` at `0x140091296`
- `KERNEL32!HeapAlloc` at `0x140090f80`
- `KERNEL32!HeapAlloc` at `0x140090f80`
- `KERNEL32!HeapFree` at `0x1400912a4`
- `KERNEL32!HeapFree` at `0x1400912a4`
- `KERNEL32!GetLastError` at `0x140090ce4`
- `KERNEL32!GetLastError` at `0x140090d62`
- `KERNEL32!GetLastError` at `0x140090dd4`
- `KERNEL32!GetLastError` at `0x140090e9f`
- `KERNEL32!GetLastError` at `0x140090f1b`
- `KERNEL32!GetLastError` at `0x140090fcf`
- `KERNEL32!GetLastError` at `0x140090ce4`
- `KERNEL32!GetLastError` at `0x140090d62`
- `KERNEL32!GetLastError` at `0x140090dd4`
- `KERNEL32!GetLastError` at `0x140090e9f`
- `KERNEL32!GetLastError` at `0x140090f1b`
- `KERNEL32!GetLastError` at `0x140090fcf`

## string_xrefs

- `0x140090c38`: `wszServiceName`

## pseudocode

```c
__int64 __fastcall BlbutilShutdownService(unsigned __int16 *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  PVOID *v6; // rcx
  SC_HANDLE v7; // r12
  unsigned __int64 v8; // rdi
  SC_HANDLE v9; // r13
  unsigned int v10; // ebx
  SC_HANDLE v11; // rax
  signed int LastError; // eax
  __int64 v13; // rdx
  SC_HANDLE v14; // rax
  signed int v15; // eax
  int v16; // edx
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  DWORD v20; // ebx
  HANDLE ProcessHeap; // rax
  struct _ENUM_SERVICE_STATUSW *v22; // rax
  struct _ENUM_SERVICE_STATUSW *v23; // rbx
  signed int v24; // eax
  PVOID *v25; // r10
  unsigned int v26; // r14d
  unsigned __int16 *lpServiceName; // rsi
  int v28; // eax
  int v29; // edx
  int v30; // r9d
  HANDLE v31; // rax
  struct _ENUM_SERVICE_STATUSW *lpMem; // [rsp+30h] [rbp-40h]
  DWORD cbBufSize; // [rsp+38h] [rbp-38h] BYREF
  DWORD ServicesReturned; // [rsp+3Ch] [rbp-34h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-30h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = 0;
  cbBufSize = 0;
  v8 = 0;
  ServicesReturned = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !a1 )
  {
    BlbAssert("base\\stor\\blb\\util\\systemutils.cpp", 0x80Fu, "wszServiceName");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
  {
    WPP_SF_S(v6[2], 102, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids, a1);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a4 >= 0xA )
  {
    v9 = 0;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    {
      WPP_SF_S(v6[2], 103, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids, a1);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147418113;
    goto LABEL_93;
  }
  v11 = OpenSCManagerW(0, 0, 1u);
  v9 = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_118;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_93;
    v13 = 104;
LABEL_25:
    WPP_SF_d(v6[2], v13, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids);
    goto LABEL_26;
  }
  v14 = OpenServiceW(v11, a1, 0x2Cu);
  v7 = v14;
  if ( !v14 )
  {
    v15 = GetLastError();
    v10 = v15;
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_118;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_93;
    v16 = 105;
LABEL_34:
    WPP_SF_Sd((unsigned int)v6[2], v16, (unsigned int)&WPP_fb4c4638572137066dde7b1879c15363_Traceguids, (_DWORD)a1, v10);
    goto LABEL_26;
  }
  if ( !QueryServiceStatus(v14, &ServiceStatus) )
  {
    v17 = GetLastError();
    v10 = v17;
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_38;
  }
  if ( ServiceStatus.dwCurrentState == 1 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids, a1);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = 0;
    goto LABEL_93;
  }
  v10 = 0;
  if ( ServiceStatus.dwCurrentState == 3 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_118;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_93;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids, a1);
LABEL_26:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_93;
  }
  if ( ControlService(v7, 1u, &ServiceStatus) )
  {
LABEL_38:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_93;
  }
  v18 = GetLastError();
  v10 = v18;
  if ( v18 != 1051 )
  {
    if ( v18 > 0 )
      v10 = (unsigned __int16)v18 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_118;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_93;
    v16 = 118;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids, a1);
  }
  if ( EnumDependentServicesW(v7, 1u, 0, 0, &cbBufSize, &ServicesReturned) )
  {
    v10 = -2147418113;
    goto LABEL_38;
  }
  v19 = GetLastError();
  v10 = v19;
  if ( v19 != 234 )
  {
    if ( v19 > 0 )
      v10 = (unsigned __int16)v19 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_118;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_93;
    v13 = 110;
    goto LABEL_25;
  }
  v20 = cbBufSize;
  ProcessHeap = GetProcessHeap();
  v22 = (struct _ENUM_SERVICE_STATUSW *)HeapAlloc(ProcessHeap, 8u, v20);
  lpMem = v22;
  v23 = v22;
  if ( !v22 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v10 = -2147024882;
    v8 = 0;
    goto LABEL_93;
  }
  if ( !EnumDependentServicesW(v7, 1u, v22, cbBufSize, &cbBufSize, &ServicesReturned) )
  {
    v24 = GetLastError();
    v10 = v24;
    if ( v24 > 0 )
      v10 = (unsigned __int16)v24 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          (unsigned int)&WPP_fb4c4638572137066dde7b1879c15363_Traceguids,
          (_DWORD)a1,
          v10);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_92;
    }
    goto LABEL_117;
  }
  v25 = (PVOID *)WPP_GLOBAL_Control;
  v26 = a4 + 1;
  while ( 1 )
  {
    if ( (unsigned int)v8 >= ServicesReturned )
    {
      if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
        WPP_SF_S(v25[2], 115, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids, a1);
      v28 = BlbutilShutdownService(a1, 0, 0xEA60u, v26);
      v10 = v28;
      if ( v28 >= 0 )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_92;
        }
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids, a1);
      }
      else
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
LABEL_117:
          v8 = (unsigned __int64)lpMem;
          goto LABEL_118;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_92;
        v29 = 116;
        v30 = (int)a1;
LABEL_90:
        WPP_SF_Sd((unsigned int)v6[2], v29, (unsigned int)&WPP_fb4c4638572137066dde7b1879c15363_Traceguids, v30, v28);
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_92;
    }
    lpServiceName = v23[v8].lpServiceName;
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
      WPP_SF_S(v25[2], 112, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids, v23[v8].lpServiceName);
    v28 = BlbutilShutdownService(lpServiceName, 0, 0xEA60u, v26);
    v10 = v28;
    if ( v28 < 0 )
      break;
    v25 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        &WPP_fb4c4638572137066dde7b1879c15363_Traceguids,
        lpServiceName);
      v25 = (PVOID *)WPP_GLOBAL_Control;
    }
    v23 = lpMem;
    v8 = (unsigned int)(v8 + 1);
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
  {
    v8 = (unsigned __int64)lpMem;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = 113;
      v30 = (int)lpServiceName;
      goto LABEL_90;
    }
LABEL_92:
    v8 = (unsigned __int64)lpMem;
LABEL_93:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
      WPP_SF_Sd(
        (unsigned int)v6[2],
        119,
        (unsigned int)&WPP_fb4c4638572137066dde7b1879c15363_Traceguids,
        (_DWORD)a1,
        v10);
  }
LABEL_118:
  v31 = GetProcessHeap();
  HeapFree(v31, 0, (LPVOID)v8);
  if ( v7 )
    CloseServiceHandle(v7);
  if ( v9 )
    CloseServiceHandle(v9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_fb4c4638572137066dde7b1879c15363_Traceguids);
  }
  return v10;
}

```

## disassembly

```asm
0x140090bb0  mov     [rsp-38h+arg_8], rbx
0x140090bb5  push    rbp
0x140090bb6  push    rsi
0x140090bb7  push    rdi
0x140090bb8  push    r12
0x140090bba  push    r13
0x140090bbc  push    r14
0x140090bbe  push    r15
0x140090bc0  mov     rbp, rsp
0x140090bc3  sub     rsp, 70h
0x140090bc7  mov     rax, cs:__security_cookie
0x140090bce  xor     rax, rsp
0x140090bd1  mov     [rbp+var_10], rax
0x140090bd5  mov     esi, r9d
0x140090bd8  mov     r15, rcx
0x140090bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140090be2  lea     rbx, WPP_GLOBAL_Control
0x140090be9  mov     r14d, 1
0x140090bef  cmp     rcx, rbx
0x140090bf2  jz      short loc_140090C1B
0x140090bf4  test    [rcx+1Ch], r14b
0x140090bf8  jz      short loc_140090C1B
0x140090bfa  cmp     byte ptr [rcx+19h], 4
0x140090bfe  jb      short loc_140090C1B
0x140090c00  mov     rcx, [rcx+10h]
0x140090c04  lea     edx, [r14+64h]
0x140090c08  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x140090c0f  call    WPP_SF_
0x140090c14  mov     rcx, cs:WPP_GLOBAL_Control
0x140090c1b  xor     eax, eax
0x140090c1d  xorps   xmm0, xmm0
0x140090c20  xor     r12d, r12d
0x140090c23  mov     [rbp+cbBufSize], eax
0x140090c26  xor     edi, edi
0x140090c28  mov     [rbp+ServicesReturned], eax
0x140090c2b  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x140090c2f  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x140090c33  test    r15, r15
0x140090c36  jnz     short loc_140090C57
0x140090c38  lea     r8, aWszservicename; "wszServiceName"
0x140090c3f  mov     edx, 80Fh; unsigned int
0x140090c44  lea     rcx, aBaseStorBlbUti_4; "base\\stor\\blb\\util\\systemutils.cpp"
0x140090c4b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140090c50  mov     rcx, cs:WPP_GLOBAL_Control
0x140090c57  cmp     rcx, rbx
0x140090c5a  jz      short loc_140090C87
0x140090c5c  test    [rcx+1Ch], r14b
0x140090c60  jz      short loc_140090C87
0x140090c62  cmp     byte ptr [rcx+19h], 4
0x140090c66  jb      short loc_140090C87
0x140090c68  mov     rcx, [rcx+10h]
0x140090c6c  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x140090c73  mov     edx, 66h ; 'f'
0x140090c78  mov     r9, r15
0x140090c7b  call    WPP_SF_S
0x140090c80  mov     rcx, cs:WPP_GLOBAL_Control
0x140090c87  cmp     esi, 0Ah
0x140090c8a  jb      short loc_140090CCF
0x140090c8c  xor     r13d, r13d
0x140090c8f  cmp     rcx, rbx
0x140090c92  jz      short loc_140090CBE
0x140090c94  test    [rcx+1Ch], r14b
0x140090c98  jz      short loc_140090CBE
0x140090c9a  cmp     byte ptr [rcx+19h], 2
0x140090c9e  jb      short loc_140090CBE
0x140090ca0  mov     rcx, [rcx+10h]
0x140090ca4  lea     edx, [r13+67h]
0x140090ca8  mov     r9, r15
0x140090cab  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x140090cb2  call    WPP_SF_S
0x140090cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140090cbe  mov     ebx, 8000FFFFh
0x140090cc3  lea     rsi, WPP_GLOBAL_Control
0x140090cca  jmp     loc_140091142
0x140090ccf  mov     r8d, r14d; dwDesiredAccess
0x140090cd2  xor     edx, edx; lpDatabaseName
0x140090cd4  xor     ecx, ecx; lpMachineName
0x140090cd6  call    cs:__imp_OpenSCManagerW
0x140090cdc  mov     r13, rax
0x140090cdf  test    rax, rax
0x140090ce2  jnz     short loc_140090D48
0x140090ce4  call    cs:__imp_GetLastError
0x140090cea  mov     ebx, eax
0x140090cec  test    eax, eax
0x140090cee  jle     short loc_140090CF9
0x140090cf0  movzx   ebx, ax
0x140090cf3  or      ebx, 80070000h
0x140090cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x140090d00  lea     rsi, WPP_GLOBAL_Control
0x140090d07  cmp     rcx, rsi
0x140090d0a  jz      loc_14009128F
0x140090d10  test    [rcx+1Ch], r14b
0x140090d14  jz      loc_140091142
0x140090d1a  cmp     byte ptr [rcx+19h], 2
0x140090d1e  jb      loc_140091142
0x140090d24  mov     edx, 68h ; 'h'
0x140090d29  mov     rcx, [rcx+10h]
0x140090d2d  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x140090d34  mov     r9d, ebx
0x140090d37  call    WPP_SF_d
0x140090d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140090d43  jmp     loc_140091142
0x140090d48  mov     r8d, 2Ch ; ','; dwDesiredAccess
0x140090d4e  mov     rdx, r15; lpServiceName
0x140090d51  mov     rcx, rax; hSCManager
0x140090d54  call    cs:__imp_OpenServiceW
0x140090d5a  mov     r12, rax
0x140090d5d  test    rax, rax
0x140090d60  jnz     short loc_140090DC3
0x140090d62  call    cs:__imp_GetLastError
0x140090d68  mov     ebx, eax
0x140090d6a  test    eax, eax
0x140090d6c  jle     short loc_140090D77
0x140090d6e  movzx   ebx, ax
0x140090d71  or      ebx, 80070000h
0x140090d77  mov     rcx, cs:WPP_GLOBAL_Control
0x140090d7e  lea     rsi, WPP_GLOBAL_Control
0x140090d85  cmp     rcx, rsi
0x140090d88  jz      loc_14009128F
0x140090d8e  test    [rcx+1Ch], r14b
0x140090d92  jz      loc_140091142
0x140090d98  cmp     byte ptr [rcx+19h], 2
0x140090d9c  jb      loc_140091142
0x140090da2  mov     edx, 69h ; 'i'
0x140090da7  mov     rcx, [rcx+10h]
0x140090dab  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x140090db2  mov     r9, r15
0x140090db5  mov     dword ptr [rsp+70h+pcbBytesNeeded], ebx
0x140090db9  call    WPP_SF_Sd
0x140090dbe  jmp     loc_140090D3C
0x140090dc3  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x140090dc7  mov     rcx, r12; hService
0x140090dca  call    cs:__imp_QueryServiceStatus
0x140090dd0  test    eax, eax
0x140090dd2  jnz     short loc_140090DF5
0x140090dd4  call    cs:__imp_GetLastError
0x140090dda  mov     ebx, eax
0x140090ddc  test    eax, eax
0x140090dde  jle     short loc_140090DE9
0x140090de0  movzx   ebx, ax
0x140090de3  or      ebx, 80070000h
0x140090de9  mov     rcx, cs:WPP_GLOBAL_Control
0x140090df0  jmp     loc_140090CC3
0x140090df5  cmp     [rbp+ServiceStatus.dwCurrentState], r14d
0x140090df9  jnz     short loc_140090E39
0x140090dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140090e02  cmp     rcx, rbx
0x140090e05  jz      short loc_140090E32
0x140090e07  test    [rcx+1Ch], r14b
0x140090e0b  jz      short loc_140090E32
0x140090e0d  cmp     byte ptr [rcx+19h], 4
0x140090e11  jb      short loc_140090E32
0x140090e13  mov     rcx, [rcx+10h]
0x140090e17  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x140090e1e  mov     edx, 6Ah ; 'j'
0x140090e23  mov     r9, r15
0x140090e26  call    WPP_SF_S
0x140090e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140090e32  xor     ebx, ebx
0x140090e34  jmp     loc_140090CC3
0x140090e39  xor     ebx, ebx
0x140090e3b  cmp     [rbp+ServiceStatus.dwCurrentState], 3
0x140090e3f  jnz     short loc_140090E87
0x140090e41  mov     rcx, cs:WPP_GLOBAL_Control
0x140090e48  lea     rsi, WPP_GLOBAL_Control
0x140090e4f  cmp     rcx, rsi
0x140090e52  jz      loc_14009128F
0x140090e58  test    [rcx+1Ch], r14b
0x140090e5c  jz      loc_140091142
0x140090e62  cmp     byte ptr [rcx+19h], 4
0x140090e66  jb      loc_140091142
0x140090e6c  mov     rcx, [rcx+10h]
0x140090e70  lea     edx, [rbx+6Bh]
0x140090e73  mov     r9, r15
0x140090e76  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x140090e7d  call    WPP_SF_S
0x140090e82  jmp     loc_140090D3C
0x140090e87  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x140090e8b  mov     edx, r14d; dwControl
0x140090e8e  mov     rcx, r12; hService
0x140090e91  call    cs:__imp_ControlService
0x140090e97  test    eax, eax
0x140090e99  jnz     loc_140090DE9
0x140090e9f  call    cs:__imp_GetLastError
0x140090ea5  mov     ebx, eax
0x140090ea7  cmp     eax, 41Bh
0x140090eac  jnz     loc_140091247
0x140090eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140090eb9  lea     rax, WPP_GLOBAL_Control
0x140090ec0  cmp     rcx, rax
0x140090ec3  jz      short loc_140090EE9
0x140090ec5  test    [rcx+1Ch], r14b
0x140090ec9  jz      short loc_140090EE9
0x140090ecb  cmp     byte ptr [rcx+19h], 4
0x140090ecf  jb      short loc_140090EE9
0x140090ed1  mov     rcx, [rcx+10h]
0x140090ed5  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x140090edc  mov     edx, 6Dh ; 'm'
0x140090ee1  mov     r9, r15
0x140090ee4  call    WPP_SF_S
0x140090ee9  lea     rax, [rbp+ServicesReturned]
0x140090eed  xor     r9d, r9d; cbBufSize
0x140090ef0  mov     [rsp+70h+lpServicesReturned], rax; lpServicesReturned
0x140090ef5  xor     r8d, r8d; lpServices
0x140090ef8  lea     rax, [rbp+cbBufSize]
0x140090efc  mov     edx, r14d; dwServiceState
0x140090eff  mov     rcx, r12; hService
0x140090f02  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140090f07  call    cs:__imp_EnumDependentServicesW
0x140090f0d  test    eax, eax
0x140090f0f  jz      short loc_140090F1B
0x140090f11  mov     ebx, 8000FFFFh
0x140090f16  jmp     loc_140090DE9
0x140090f1b  call    cs:__imp_GetLastError
0x140090f21  mov     ebx, eax
0x140090f23  cmp     eax, 0EAh
0x140090f28  jz      short loc_140090F6C
0x140090f2a  test    eax, eax
0x140090f2c  jle     short loc_140090F37
0x140090f2e  movzx   ebx, ax
0x140090f31  or      ebx, 80070000h
0x140090f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140090f3e  lea     rsi, WPP_GLOBAL_Control
0x140090f45  cmp     rcx, rsi
0x140090f48  jz      loc_14009128F
0x140090f4e  test    [rcx+1Ch], r14b
0x140090f52  jz      loc_140091142
0x140090f58  cmp     byte ptr [rcx+19h], 2
0x140090f5c  jb      loc_140091142
0x140090f62  mov     edx, 6Eh ; 'n'
0x140090f67  jmp     loc_140090D29
0x140090f6c  mov     ebx, [rbp+cbBufSize]
0x140090f6f  call    cs:__imp_GetProcessHeap
0x140090f75  mov     r8d, ebx; dwBytes
0x140090f78  mov     edx, 8; dwFlags
0x140090f7d  mov     rcx, rax; hHeap
0x140090f80  call    cs:__imp_HeapAlloc
0x140090f86  mov     [rbp+lpMem], rax
0x140090f8a  mov     rbx, rax
0x140090f8d  test    rax, rax
0x140090f90  jnz     short loc_140090FA6
0x140090f92  mov     rcx, cs:WPP_GLOBAL_Control
0x140090f99  mov     ebx, 8007000Eh
0x140090f9e  mov     rdi, rax
0x140090fa1  jmp     loc_140090CC3
0x140090fa6  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x140090faa  lea     rax, [rbp+ServicesReturned]
0x140090fae  mov     [rsp+70h+lpServicesReturned], rax; lpServicesReturned
0x140090fb3  mov     r8, rbx; lpServices
0x140090fb6  lea     rax, [rbp+cbBufSize]
0x140090fba  mov     edx, r14d; dwServiceState
0x140090fbd  mov     rcx, r12; hService
0x140090fc0  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140090fc5  call    cs:__imp_EnumDependentServicesW
0x140090fcb  test    eax, eax
0x140090fcd  jnz     short loc_140091037
0x140090fcf  call    cs:__imp_GetLastError
0x140090fd5  mov     ebx, eax
0x140090fd7  test    eax, eax
0x140090fd9  jle     short loc_140090FE4
0x140090fdb  movzx   ebx, ax
0x140090fde  or      ebx, 80070000h
0x140090fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x140090feb  lea     rsi, WPP_GLOBAL_Control
0x140090ff2  cmp     rcx, rsi
0x140090ff5  jz      loc_14009128B
0x140090ffb  test    [rcx+1Ch], r14b
0x140090fff  jz      loc_14009113E
0x140091005  cmp     byte ptr [rcx+19h], 2
0x140091009  jb      loc_14009113E
0x14009100f  mov     rcx, [rcx+10h]
0x140091013  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x14009101a  mov     edx, 6Fh ; 'o'
0x14009101f  mov     dword ptr [rsp+70h+pcbBytesNeeded], ebx
0x140091023  mov     r9, r15
0x140091026  call    WPP_SF_Sd
0x14009102b  mov     rcx, cs:WPP_GLOBAL_Control
0x140091032  jmp     loc_14009113E
0x140091037  mov     r10, cs:WPP_GLOBAL_Control
0x14009103e  lea     r14d, [rsi+1]
0x140091042  cmp     edi, [rbp+ServicesReturned]
0x140091045  jnb     loc_140091180
0x14009104b  lea     rcx, [rdi+rdi*2]
0x14009104f  add     rcx, rcx
0x140091052  mov     rsi, [rbx+rcx*8]
0x140091056  lea     rax, WPP_GLOBAL_Control
0x14009105d  cmp     r10, rax
0x140091060  jz      short loc_140091088
0x140091062  test    byte ptr [r10+1Ch], 1
0x140091067  jz      short loc_140091088
0x140091069  cmp     byte ptr [r10+19h], 4
0x14009106e  jb      short loc_140091088
0x140091070  mov     rcx, [r10+10h]
0x140091074  lea     r8, WPP_fb4c4638572137066dde7b1879c15363_Traceguids
0x14009107b  mov     edx, 70h ; 'p'
0x140091080  mov     r9, rsi
0x140091083  call    WPP_SF_S
0x140091088  mov     r9d, r14d; unsigned int
0x14009108b  xor     edx, edx; int
0x14009108d  mov     r8d, 0EA60h; unsigned int
  ... truncated ...
```
