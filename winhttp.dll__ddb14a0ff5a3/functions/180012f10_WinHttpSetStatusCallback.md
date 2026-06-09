# WinHttpSetStatusCallback

- ea: `0x180012f10`
- end: `0x18001366c`
- name: `WinHttpSetStatusCallback`
- size: `1884`
- prototype: `WINHTTP_STATUS_CALLBACK __stdcall(HINTERNET hInternet, WINHTTP_STATUS_CALLBACK lpfnInternetCallback, DWORD dwNotificationFlags, DWORD_PTR dwReserved)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001137c`
- `0x18009d99c`
- `0x1800bcc00`

## callees

- `0x180010f50`
- `0x180012f10`
- `0x180013680`
- `0x180013778`
- `0x180033404`
- `0x1800354c0`
- `0x18003b0e0`
- `0x18003bc60`
- `0x18007d010`
- `0x18007db18`
- `0x1800a1d10`
- `0x1800b0fac`
- `0x1800b1e94`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800db758`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800132f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800135c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800132f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800135c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013180`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013371`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013180`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013371`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800132eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800135b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800132eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800135b8`
- `ntdll!EtwEventActivityIdControl` at `0x180013086`
- `ntdll!EtwEventActivityIdControl` at `0x1800130bd`
- `ntdll!EtwEventActivityIdControl` at `0x180013164`
- `ntdll!EtwEventActivityIdControl` at `0x180013086`
- `ntdll!EtwEventActivityIdControl` at `0x1800130bd`
- `ntdll!EtwEventActivityIdControl` at `0x180013164`

## pseudocode

```c
WINHTTP_STATUS_CALLBACK __stdcall WinHttpSetStatusCallback(HINTERNET hInternet, WINHTTP_STATUS_CALLBACK lpfnInternetCallback, DWORD dwNotificationFlags, DWORD_PTR dwReserved)
{
  DWORD v8; // eax
  DWORD v9; // esi
  char *v10; // rbx
  unsigned int v11; // edi
  char v12; // al
  __int64 v13; // rdx
  struct _GUID *v14; // rax
  __int64 v15; // rcx
  __int128 *v16; // rbx
  struct _GUID *v17; // rax
  __int64 v18; // rcx
  struct _GUID *v19; // rax
  int v20; // eax
  bool v21; // sf
  int v22; // eax
  bool v23; // sf
  DWORD IsValid; // ebx
  int v25; // eax
  bool v26; // sf
  char v28; // al
  HTTP_REQUEST_HANDLE_OBJECT *v29; // rdi
  int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rdx
  struct _GUID *v33; // rax
  __int64 v34; // rcx
  struct _GUID *v35; // rax
  signed __int32 v36; // esi
  DWORD v37; // ebx
  unsigned __int64 v38; // rcx
  const struct _GUID *v39; // r9
  int v40; // edx
  int v41; // edx
  void (*v42)(void *, unsigned __int64, unsigned int, void *, unsigned int); // rcx
  signed __int32 v43; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v46; // [rsp+20h] [rbp-69h]
  void (*v47)(void *, unsigned __int64, unsigned int, void *, unsigned int); // [rsp+30h] [rbp-59h] BYREF
  HTTP_REQUEST_HANDLE_OBJECT *v48; // [rsp+38h] [rbp-51h] BYREF
  void *v49; // [rsp+40h] [rbp-49h] BYREF
  struct _GUID v50; // [rsp+50h] [rbp-39h] BYREF
  struct _GUID v51; // [rsp+60h] [rbp-29h] BYREF
  int v52; // [rsp+70h] [rbp-19h]
  struct _GUID v53; // [rsp+80h] [rbp-9h] BYREF
  __int128 v54; // [rsp+90h] [rbp+7h] BYREF
  _UNKNOWN *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( !GlobalDataInitialized )
  {
    v8 = GlobalDataInitialize();
    if ( v8 )
    {
      SetLastError(v8);
      return (WINHTTP_STATUS_CALLBACK)-1LL;
    }
  }
  v9 = 0;
  v47 = (void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int))-1LL;
  v48 = 0;
  v51 = 0;
  v52 = 0;
  v49 = 0;
  if ( WinHttpEtwInitialized )
  {
    if ( hInternet )
    {
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_qqD(
          1041,
          10,
          (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
          (_DWORD)hInternet,
          (__int64)&v49);
      if ( (unsigned int)HANDLE_OBJECT::IsValid(hInternet, 1684826455) )
      {
        if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
        {
          v40 = 11;
          goto LABEL_95;
        }
      }
      else
      {
        v10 = (char *)hInternet;
        v11 = HANDLE_OBJECT::Reference((HANDLE_OBJECT *)hInternet);
        v12 = BYTE2(xmmword_180107A50);
        if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
        {
          WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v11, v46);
          v12 = BYTE2(xmmword_180107A50);
        }
        if ( v11 == 6 || !v11 )
          goto LABEL_11;
        if ( (v12 & 2) != 0 )
        {
          v40 = 13;
LABEL_95:
          WPP_SF_qq(
            529,
            v40,
            (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
            (_DWORD)hInternet,
            (__int64)hInternet);
        }
      }
      v10 = 0;
      v11 = 6;
LABEL_11:
      v49 = v10;
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      {
        WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v11, v46);
        v10 = (char *)v49;
      }
      if ( v10 )
      {
        if ( v52 )
        {
          WxEtwSetActivityId(&v51);
          v10 = (char *)v49;
        }
        v13 = 16;
        v14 = &v51;
        v15 = 16;
        v16 = (__int128 *)(v10 + 184);
        do
        {
          LOBYTE(v14->Data1) = 0;
          v14 = (struct _GUID *)((char *)v14 + 1);
          --v15;
        }
        while ( v15 );
        v52 = 0;
        v17 = &v51;
        v54 = 0;
        v18 = 16;
        v53 = 0;
        do
        {
          LOBYTE(v17->Data1) = 0;
          v17 = (struct _GUID *)((char *)v17 + 1);
          --v18;
        }
        while ( v18 );
        v50 = 0;
        v19 = &v53;
        do
        {
          LOBYTE(v19->Data1) = 0;
          v19 = (struct _GUID *)((char *)v19 + 1);
          --v13;
        }
        while ( v13 );
        v20 = EtwEventActivityIdControl(1, &v50);
        v21 = v20 < 0;
        if ( v20 > 0 )
          v21 = 1;
        if ( v21 )
          *(_DWORD *)&v50.Data2 = 128;
        else
          v53 = v50;
        if ( !v16 )
        {
          v43 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
          TickCount = GetTickCount();
          CurrentProcessId = GetCurrentProcessId();
          *(_QWORD *)((char *)&v54 + 4) = __PAIR64__(TickCount, v43);
          v9 = 0;
          v16 = &v54;
          HIDWORD(v54) = CurrentProcessId;
          LODWORD(v54) = (_DWORD)retaddr;
        }
        *(_DWORD *)&v50.Data2 = 0;
        v22 = EtwEventActivityIdControl(2, v16);
        v23 = v22 < 0;
        if ( v22 > 0 )
          v23 = 1;
        if ( v23 )
          *(_DWORD *)&v50.Data2 = 144;
        v51 = v53;
        v52 = 1;
        DereferenceObject(v49);
      }
      goto LABEL_33;
    }
    v32 = 16;
    v33 = &v51;
    v34 = 16;
    do
    {
      LOBYTE(v33->Data1) = 0;
      v33 = (struct _GUID *)((char *)v33 + 1);
      --v34;
    }
    while ( v34 );
    v52 = 0;
    v35 = &v51;
    v50 = 0;
    v53 = 0;
    do
    {
      LOBYTE(v35->Data1) = 0;
      v35 = (struct _GUID *)((char *)v35 + 1);
      --v32;
    }
    while ( v32 );
    WxEtwGetActivityId(&v53);
    v36 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    v37 = GetTickCount();
    *(_DWORD *)&v50.Data4[4] = GetCurrentProcessId();
    v50.Data1 = (unsigned int)retaddr;
    *(_DWORD *)&v50.Data2 = v36;
    *(_DWORD *)v50.Data4 = v37;
    if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfo(v38, &ActivityStart, &v50, v39, v46);
    WxEtwSetActivityId(&v50);
    v52 = 1;
    v9 = 0;
    v51 = v53;
  }
LABEL_33:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_qqD(
      1026,
      26,
      (unsigned int)WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids,
      (_DWORD)hInternet,
      (__int64)lpfnInternetCallback);
  if ( lpfnInternetCallback && !dwNotificationFlags || dwReserved )
  {
    IsValid = 87;
    goto LABEL_38;
  }
  if ( !hInternet )
  {
    IsValid = 12018;
    goto LABEL_38;
  }
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_qqD(
      1041,
      10,
      (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
      (_DWORD)hInternet,
      (__int64)&v48);
  if ( (unsigned int)HANDLE_OBJECT::IsValid(hInternet, 1684826455) )
  {
    if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
    {
      v41 = 11;
      goto LABEL_97;
    }
LABEL_80:
    hInternet = 0;
    IsValid = 6;
    goto LABEL_57;
  }
  IsValid = HANDLE_OBJECT::Reference((HANDLE_OBJECT *)hInternet);
  v28 = BYTE2(xmmword_180107A50);
  if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
  {
    WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, v46);
    v28 = BYTE2(xmmword_180107A50);
  }
  if ( IsValid != 6 && IsValid )
  {
    if ( (v28 & 2) != 0 )
    {
      v41 = 13;
LABEL_97:
      WPP_SF_qq(
        529,
        v41,
        (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
        (_DWORD)hInternet,
        (__int64)hInternet);
      goto LABEL_80;
    }
    goto LABEL_80;
  }
LABEL_57:
  v48 = (HTTP_REQUEST_HANDLE_OBJECT *)hInternet;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, v46);
  if ( !IsValid )
  {
LABEL_60:
    v29 = v48;
    v47 = lpfnInternetCallback;
    if ( lpfnInternetCallback )
      v9 = dwNotificationFlags;
    IsValid = HANDLE_OBJECT::IsValid(v48, 1684826455);
    if ( !IsValid )
    {
      v30 = (*(__int64 (__fastcall **)(HTTP_REQUEST_HANDLE_OBJECT *))(*(_QWORD *)v29 + 8LL))(v29);
      switch ( v30 )
      {
        case 1902465608:
          v31 = HTTP_REQUEST_HANDLE_OBJECT::SafeExchangeStatusCallback(v29, &v47, v9);
LABEL_65:
          IsValid = v31;
          goto LABEL_38;
        case 1398957399:
          v31 = WEB_SOCKET_HANDLE_OBJECT::SetStatusCallback(v29, &v47, v9);
          goto LABEL_65;
        case 1415731024:
        case 1852731203:
          v31 = PROTOCOL_HANDLE_OBJECT::SetStatusCallback(v29, &v47, v9);
          goto LABEL_65;
        case 2037936720:
          v31 = PROXY_RESOLVE_HANDLE_OBJECT::SetStatusCallback(v29, &v47, v9);
          goto LABEL_65;
      }
      IsValid = 0;
      v42 = (void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int))*((_QWORD *)v29 + 21);
      *((_QWORD *)v29 + 21) = v47;
      v47 = v42;
      *((_DWORD *)v29 + 44) = 1;
      *((_DWORD *)v29 + 45) = v9;
    }
LABEL_38:
    if ( v48 )
    {
      DereferenceObject(v48);
      v48 = 0;
    }
    if ( !IsValid )
      goto LABEL_41;
    goto LABEL_92;
  }
  if ( v48 )
  {
    if ( lpfnInternetCallback )
      goto LABEL_38;
    goto LABEL_60;
  }
LABEL_92:
  if ( (xmmword_180107A50 & 4) != 0 )
    WPP_SF_d(514, 27, WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids, IsValid, v46);
LABEL_41:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_q(1026, 28, WPP_f62584367b0a3e41788b993bfa5f71c7_Traceguids);
  if ( v52 )
  {
    *(_DWORD *)&v50.Data2 = 0;
    v25 = EtwEventActivityIdControl(2, &v51);
    v26 = v25 < 0;
    if ( v25 > 0 )
      v26 = 1;
    if ( v26 )
      *(_DWORD *)&v50.Data2 = 144;
  }
  SetLastError(IsValid);
  return v47;
}

```

## disassembly

```asm
0x180012f10  push    rbp
0x180012f12  push    r12
0x180012f14  push    r13
0x180012f16  push    r14
0x180012f18  push    r15
0x180012f1a  lea     rbp, [rsp-37h]
0x180012f1f  sub     rsp, 0C0h
0x180012f26  mov     rax, cs:__security_cookie
0x180012f2d  xor     rax, rsp
0x180012f30  mov     [rbp+57h+var_40], rax
0x180012f34  cmp     cs:?GlobalDataInitialized@@3HA, 0; int GlobalDataInitialized
0x180012f3b  mov     r12, r9
0x180012f3e  mov     r13d, r8d
0x180012f41  mov     r15, rdx
0x180012f44  mov     r14, rcx
0x180012f47  jnz     short loc_180012F56
0x180012f49  call    ?GlobalDataInitialize@@YAKXZ; GlobalDataInitialize(void)
0x180012f4e  test    eax, eax
0x180012f50  jnz     loc_18001336F
0x180012f56  mov     [rsp+0E0h+arg_18], rbx
0x180012f5e  xor     eax, eax
0x180012f60  mov     [rsp+0E0h+var_28], rsi
0x180012f68  xorps   xmm0, xmm0
0x180012f6b  xor     esi, esi
0x180012f6d  mov     [rsp+0E0h+var_30], rdi
0x180012f75  cmp     cs:?WinHttpEtwInitialized@@3EA, al; uchar WinHttpEtwInitialized
0x180012f7b  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFFh
0x180012f83  mov     [rbp+57h+var_A8], rsi
0x180012f87  movups  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x180012f8b  mov     [rbp+57h+var_70], eax
0x180012f8e  mov     [rbp+57h+var_A0], rsi
0x180012f92  jz      loc_1800130EF
0x180012f98  test    r14, r14
0x180012f9b  jz      loc_18001328E
0x180012fa1  test    byte ptr cs:xmmword_180107A60+2, 2
0x180012fa8  jnz     loc_180013467
0x180012fae  mov     edx, 646C6957h
0x180012fb3  mov     rcx, r14
0x180012fb6  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x180012fbb  test    eax, eax
0x180012fbd  jnz     loc_180013274
0x180012fc3  mov     rcx, r14; this
0x180012fc6  mov     rbx, r14
0x180012fc9  call    ?Reference@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::Reference(void)
0x180012fce  mov     edi, eax
0x180012fd0  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x180012fd7  test    al, 2
0x180012fd9  jnz     loc_1800134D7
0x180012fdf  cmp     edi, 6
0x180012fe2  jnz     loc_18001333B
0x180012fe8  mov     [rbp+57h+var_A0], rbx
0x180012fec  test    byte ptr cs:xmmword_180107A60+2, 2
0x180012ff3  jnz     loc_180013492
0x180012ff9  test    rbx, rbx
0x180012ffc  jz      loc_1800130EF
0x180013002  cmp     [rbp+57h+var_70], esi
0x180013005  jnz     loc_18001338D
0x18001300b  mov     edx, 10h
0x180013010  lea     rax, [rbp+57h+var_80]
0x180013014  mov     ecx, edx
0x180013016  add     rbx, 0B8h
0x18001301d  nop     dword ptr [rax]
0x180013020  mov     [rax], sil
0x180013023  lea     rax, [rax+1]
0x180013027  sub     rcx, 1
0x18001302b  jnz     short loc_180013020
0x18001302d  xorps   xmm0, xmm0
0x180013030  mov     [rbp+57h+var_70], esi
0x180013033  xorps   xmm1, xmm1
0x180013036  lea     rax, [rbp+57h+var_80]
0x18001303a  movups  [rbp+57h+var_50], xmm0
0x18001303e  mov     rcx, rdx
0x180013041  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x180013045  nop     word ptr [rax+rax+00000000h]
0x180013050  mov     [rax], sil
0x180013053  lea     rax, [rax+1]
0x180013057  sub     rcx, 1
0x18001305b  jnz     short loc_180013050
0x18001305d  xorps   xmm0, xmm0
0x180013060  mov     dword ptr [rbp+57h+var_90.Data2], esi
0x180013063  movups  xmmword ptr [rbp-39h], xmm0
0x180013067  lea     rax, [rbp+57h+var_60]
0x18001306b  nop     dword ptr [rax+rax+00h]
0x180013070  mov     [rax], sil
0x180013073  lea     rax, [rax+1]
0x180013077  sub     rdx, 1
0x18001307b  jnz     short loc_180013070
0x18001307d  lea     rdx, [rbp+57h+var_90]
0x180013081  mov     ecx, 1
0x180013086  call    cs:__imp_EtwEventActivityIdControl
0x18001308c  test    eax, eax
0x18001308e  jle     short loc_18001309A
0x180013090  movzx   eax, ax
0x180013093  or      eax, 80070000h
0x180013098  test    eax, eax
0x18001309a  js      loc_18001358B
0x1800130a0  movaps  xmm0, xmmword ptr [rbp+57h+var_90.Data1]
0x1800130a4  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x1800130a9  test    rbx, rbx
0x1800130ac  jz      loc_1800135A5
0x1800130b2  mov     rdx, rbx
0x1800130b5  mov     dword ptr [rbp+57h+var_90.Data2], esi
0x1800130b8  mov     ecx, 2
0x1800130bd  call    cs:__imp_EtwEventActivityIdControl
0x1800130c3  test    eax, eax
0x1800130c5  jle     short loc_1800130D1
0x1800130c7  movzx   eax, ax
0x1800130ca  or      eax, 80070000h
0x1800130cf  test    eax, eax
0x1800130d1  js      loc_1800135DD
0x1800130d7  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x1800130db  mov     rcx, [rbp+57h+var_A0]; void *
0x1800130df  movups  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x1800130e3  mov     [rbp+57h+var_70], 1
0x1800130ea  call    ?DereferenceObject@@YAKPEAX@Z; DereferenceObject(void *)
0x1800130ef  test    byte ptr cs:xmmword_180107A60, 4
0x1800130f6  jnz     loc_1800135E9
0x1800130fc  test    r15, r15
0x1800130ff  jz      loc_1800131AF
0x180013105  test    r13d, r13d
0x180013108  jnz     loc_1800131AF
0x18001310e  mov     ebx, 57h ; 'W'
0x180013113  mov     rcx, [rbp+57h+var_A8]; void *
0x180013117  test    rcx, rcx
0x18001311a  jz      short loc_180013129
0x18001311c  call    ?DereferenceObject@@YAKPEAX@Z; DereferenceObject(void *)
0x180013121  mov     [rbp+57h+var_A8], 0
0x180013129  test    ebx, ebx
0x18001312b  jnz     loc_180013419
0x180013131  test    byte ptr cs:xmmword_180107A60, 4
0x180013138  mov     rdi, [rsp+0E0h+var_30]
0x180013140  mov     rsi, [rsp+0E0h+var_28]
0x180013148  jnz     loc_18001364D
0x18001314e  cmp     [rbp+57h+var_70], 0
0x180013152  jz      short loc_18001317E
0x180013154  lea     rdx, [rbp+57h+var_80]
0x180013158  mov     dword ptr [rbp+57h+var_90.Data2], 0
0x18001315f  mov     ecx, 2
0x180013164  call    cs:__imp_EtwEventActivityIdControl
0x18001316a  test    eax, eax
0x18001316c  jle     short loc_180013178
0x18001316e  movzx   eax, ax
0x180013171  or      eax, 80070000h
0x180013176  test    eax, eax
0x180013178  js      loc_18001357F
0x18001317e  mov     ecx, ebx; dwErrCode
0x180013180  call    cs:__imp_SetLastError
0x180013186  mov     rax, [rbp+57h+var_B0]
0x18001318a  mov     rbx, [rsp+0E0h+arg_18]
0x180013192  mov     rcx, [rbp+57h+var_40]
0x180013196  xor     rcx, rsp; StackCookie
0x180013199  call    __security_check_cookie
0x18001319e  add     rsp, 0C0h
0x1800131a5  pop     r15
0x1800131a7  pop     r14
0x1800131a9  pop     r13
0x1800131ab  pop     r12
0x1800131ad  pop     rbp
0x1800131ae  retn
0x1800131af  test    r12, r12
0x1800131b2  jnz     loc_18001310E
0x1800131b8  test    r14, r14
0x1800131bb  jz      loc_180013383
0x1800131c1  test    byte ptr cs:xmmword_180107A60+2, 2
0x1800131c8  jnz     loc_1800134FC
0x1800131ce  mov     edx, 646C6957h
0x1800131d3  mov     rcx, r14
0x1800131d6  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x1800131db  test    eax, eax
0x1800131dd  jnz     loc_180013355
0x1800131e3  mov     rcx, r14; this
0x1800131e6  call    ?Reference@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::Reference(void)
0x1800131eb  mov     ebx, eax
0x1800131ed  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x1800131f4  test    al, 2
0x1800131f6  jnz     loc_18001355A
0x1800131fc  cmp     ebx, 6
0x1800131ff  jnz     loc_18001339F
0x180013205  mov     [rbp+57h+var_A8], r14
0x180013209  test    byte ptr cs:xmmword_180107A60+2, 2
0x180013210  jnz     loc_180013527
0x180013216  test    ebx, ebx
0x180013218  jnz     loc_18001340E
0x18001321e  mov     rdi, [rbp+57h+var_A8]
0x180013222  test    r15, r15
0x180013225  mov     rcx, rdi
0x180013228  mov     [rbp+57h+var_B0], r15
0x18001322c  mov     edx, 646C6957h
0x180013231  cmovnz  esi, r13d
0x180013235  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18001323a  mov     ebx, eax
0x18001323c  test    eax, eax
0x18001323e  jnz     loc_180013113
0x180013244  mov     rax, [rdi]
0x180013247  mov     rcx, rdi
0x18001324a  mov     rax, [rax+8]
0x18001324e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013253  cmp     eax, 71655248h
0x180013258  jnz     loc_1800133B5
0x18001325e  mov     r8d, esi; unsigned int
0x180013261  lea     rdx, [rbp+57h+var_B0]; void (**)(void *, unsigned __int64, unsigned int, void *, unsigned int)
0x180013265  mov     rcx, rdi; this
0x180013268  call    ?SafeExchangeStatusCallback@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEAP6AXPEAX_KK0K@ZK@Z; HTTP_REQUEST_HANDLE_OBJECT::SafeExchangeStatusCallback(void (**)(void *,unsigned __int64,ulong,void *,ulong),ulong)
0x18001326d  mov     ebx, eax
0x18001326f  jmp     loc_180013113
0x180013274  test    byte ptr cs:xmmword_180107A50+2, 2
0x18001327b  jnz     loc_180013444
0x180013281  mov     rbx, rsi
0x180013284  mov     edi, 6
0x180013289  jmp     loc_180012FE8
0x18001328e  mov     edx, 10h
0x180013293  lea     rax, [rbp+57h+var_80]
0x180013297  mov     ecx, edx
0x180013299  nop     dword ptr [rax+00000000h]
0x1800132a0  mov     [rax], sil
0x1800132a3  lea     rax, [rax+1]
0x1800132a7  sub     rcx, 1
0x1800132ab  jnz     short loc_1800132A0
0x1800132ad  xorps   xmm0, xmm0
0x1800132b0  mov     [rbp+57h+var_70], esi
0x1800132b3  xorps   xmm1, xmm1
0x1800132b6  lea     rax, [rbp+57h+var_80]
0x1800132ba  movups  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800132be  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x1800132c2  mov     [rax], sil
0x1800132c5  lea     rax, [rax+1]
0x1800132c9  sub     rdx, 1
0x1800132cd  jnz     short loc_1800132C2
0x1800132cf  lea     rcx, [rbp+57h+var_60]; struct _GUID *
0x1800132d3  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x1800132d8  mov     rdi, [rbp+5Fh]
0x1800132dc  mov     esi, 1
0x1800132e1  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x1800132e9  inc     esi
0x1800132eb  call    cs:__imp_GetTickCount
0x1800132f1  mov     ebx, eax
0x1800132f3  call    cs:__imp_GetCurrentProcessId
0x1800132f9  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, 0; int g_fEtwCorrelationProviderInitialized
0x180013300  mov     dword ptr [rbp+57h+var_90.Data4+4], eax
0x180013303  mov     [rbp+57h+var_90.Data1], edi
0x180013306  mov     dword ptr [rbp+57h+var_90.Data2], esi
0x180013309  mov     dword ptr [rbp+57h+var_90.Data4], ebx
0x18001330c  jz      short loc_18001331C
0x18001330e  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180013314  test    eax, eax
0x180013316  jnz     loc_180013545
0x18001331c  lea     rcx, [rbp+57h+var_90]; struct _GUID *
0x180013320  call    ?WxEtwSetActivityId@@YAXPEBU_GUID@@@Z; WxEtwSetActivityId(_GUID const *)
0x180013325  movups  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x180013329  mov     [rbp+57h+var_70], 1
0x180013330  xor     esi, esi
0x180013332  movups  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x180013336  jmp     loc_1800130EF
0x18001333b  test    edi, edi
0x18001333d  jz      loc_180012FE8
0x180013343  test    al, 2
0x180013345  jz      loc_180013281
0x18001334b  mov     edx, 0Dh
0x180013350  jmp     loc_180013449
0x180013355  test    byte ptr cs:xmmword_180107A50+2, 2
0x18001335c  jnz     loc_1800134B4
0x180013362  mov     r14, rsi
0x180013365  mov     ebx, 6
0x18001336a  jmp     loc_180013205
0x18001336f  mov     ecx, eax; dwErrCode
0x180013371  call    cs:__imp_SetLastError
0x180013377  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001337e  jmp     loc_180013192
0x180013383  mov     ebx, 2EF2h
0x180013388  jmp     loc_180013113
0x18001338d  lea     rcx, [rbp+57h+var_80]; struct _GUID *
0x180013391  call    ?WxEtwSetActivityId@@YAXPEBU_GUID@@@Z; WxEtwSetActivityId(_GUID const *)
0x180013396  mov     rbx, [rbp+57h+var_A0]
0x18001339a  jmp     loc_18001300B
0x18001339f  test    ebx, ebx
0x1800133a1  jz      loc_180013205
0x1800133a7  test    al, 2
0x1800133a9  jz      short loc_180013362
0x1800133ab  mov     edx, 0Dh
0x1800133b0  jmp     loc_1800134B9
0x1800133b5  cmp     eax, 53626557h
0x1800133ba  jz      loc_180013639
0x1800133c0  cmp     eax, 54625750h
0x1800133c5  jz      loc_180013625
0x1800133cb  cmp     eax, 6E6E6F43h
0x1800133d0  jz      loc_180013625
0x1800133d6  cmp     eax, 79787250h
0x1800133db  jz      loc_180013611
0x1800133e1  mov     rax, [rbp+57h+var_B0]
0x1800133e5  xor     ebx, ebx
0x1800133e7  mov     rcx, [rdi+0A8h]
0x1800133ee  mov     [rdi+0A8h], rax
0x1800133f5  mov     [rbp+57h+var_B0], rcx
0x1800133f9  mov     dword ptr [rdi+0B0h], 1
0x180013403  mov     [rdi+0B4h], esi
0x180013409  jmp     loc_180013113
0x18001340e  cmp     [rbp+57h+var_A8], 0
0x180013413  jnz     loc_180013597
0x180013419  test    byte ptr cs:xmmword_180107A50, 4
0x180013420  jz      loc_180013131
  ... truncated ...
```
