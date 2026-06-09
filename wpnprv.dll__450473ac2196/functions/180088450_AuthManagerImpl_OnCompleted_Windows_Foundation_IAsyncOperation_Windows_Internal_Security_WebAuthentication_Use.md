# AuthManagerImpl::OnCompleted(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,char * *,char * *)

- ea: `0x180088450`
- end: `0x180088b54`
- name: `?OnCompleted@AuthManagerImpl@@AEAAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@PEAPEAD1@Z`
- size: `1796`
- prototype: `__int64 __fastcall(AuthManagerImpl *this, __int64 *, LPVOID *, char **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180086e60`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18002f2d8`
- `0x18002f808`
- `0x180086860`
- `0x1800881d4`
- `0x180088450`
- `0x180089100`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180088a7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180088a93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180088a7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180088a93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088a85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088a85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088ab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088ab5`

## pseudocode

```c
__int64 __fastcall AuthManagerImpl::OnCompleted(AuthManagerImpl *this, __int64 *a2, LPVOID *a3, char **a4)
{
  char **v4; // rdi
  PVOID v8; // rcx
  __int64 v9; // rax
  char *v10; // rsi
  __int64 (__fastcall *v11)(__int64 *, __int64 *); // rax
  int v12; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  int i; // eax
  int v27; // edx
  void *v28; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v30; // rax
  __int64 v32; // [rsp+20h] [rbp-30h] BYREF
  char *v33; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  HSTRING v35; // [rsp+38h] [rbp-18h] BYREF
  __int64 v36; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  int v38; // [rsp+98h] [rbp+48h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v40; // [rsp+A8h] [rbp+58h] BYREF

  v4 = a4;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = *((_DWORD *)this + 2) == 1;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, a4);
  }
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
  *a3 = 0;
  *v4 = 0;
  v9 = *a2;
  v10 = 0;
  v32 = 0;
  v36 = 0;
  v40 = 0;
  v11 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 64);
  v38 = 0;
  string = 0;
  v35 = 0;
  lpMem = 0;
  v33 = 0;
  v12 = v11(a2, &v32);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
        (unsigned int)v12);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)v13,
      v32);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_95;
    v15 = 87;
    goto LABEL_15;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 56LL))(v32, &string);
  v13 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
        (unsigned int)v17);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)v13,
      v32);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_95;
    v15 = 89;
    goto LABEL_15;
  }
  v18 = AuthManagerImpl::ConvertHString(this, string, (char **)&lpMem);
  v13 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
        (unsigned int)v18);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2AB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)v13,
      v32);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_95;
    v15 = 91;
    goto LABEL_15;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 48LL))(v32, &v36);
  v13 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
        (unsigned int)v19);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2AF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)v13,
      v32);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_95;
    v15 = 93;
    goto LABEL_15;
  }
  if ( !v36 )
  {
    v13 = -2147024883;
    if ( (byte_1800AFD83 & 1) != 0 )
      McTemplateU0qq_EventWriteTransfer(0, WPNPRV_AUTH_DEVICE_ID_FAILURE, 2147942413LL, *((_DWORD *)this + 2) == 1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, 2147942413LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2BB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)0x8007000DLL,
      v32);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_95;
    v15 = 95;
    v16 = 2147942413LL;
    goto LABEL_50;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 48LL))(v36, 0, &v40);
  v13 = v20;
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
        (unsigned int)v20);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)v13,
      v32);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_95;
    v15 = 97;
    goto LABEL_15;
  }
  v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 64LL))(v40, &v38);
  v13 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
        (unsigned int)v21);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
      (const char *)v13,
      v32);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_95;
    v15 = 99;
    goto LABEL_15;
  }
  if ( v38 < 0 )
  {
    if ( (byte_1800AFD83 & 1) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        v22,
        WPNPRV_AUTH_DEVICE_ID_FAILURE,
        (unsigned int)v38,
        *((_DWORD *)this + 2) == 1);
    goto LABEL_94;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 48LL))(v40, &v35);
  v13 = v23;
  if ( v23 >= 0 )
  {
    v24 = AuthManagerImpl::ConvertHString(this, v35, &v33);
    v13 = v24;
    if ( v24 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          102,
          WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
          (unsigned int)v24);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2CF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
        (const char *)v13,
        v32);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v13);
      v10 = v33;
      goto LABEL_95;
    }
    v10 = v33;
    for ( i = 0; v33[i]; ++i )
    {
      if ( v33[i] == 38 )
      {
        v33[i] = 0;
        break;
      }
    }
    if ( byte_1800AFD82 < 0 )
      McTemplateU0sq_EventWriteTransfer(i, v25, lpMem, *((_DWORD *)this + 2) == 1);
LABEL_94:
    *a3 = lpMem;
    *v4 = v10;
    v10 = 0;
    lpMem = 0;
    v27 = v38;
    if ( (v13 & 0x80000000) == 0 )
      goto LABEL_96;
    goto LABEL_95;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
      (unsigned int)v23);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x2CB,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
    (const char *)v13,
    v32);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
    goto LABEL_95;
  v15 = 101;
LABEL_15:
  v16 = v13;
LABEL_50:
  WPP_SF_d(v14[2], v15, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v16);
LABEL_95:
  v27 = v13;
LABEL_96:
  AuthManagerImpl::LogQos(this, v27);
  v28 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v28);
  }
  if ( v10 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v10);
  }
  if ( string )
  {
    WindowsDeleteString(string);
    string = 0;
  }
  if ( v35 )
  {
    WindowsDeleteString(v35);
    v35 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180088450  mov     [rsp-38h+arg_0], rbx
0x180088455  push    rbp
0x180088456  push    rsi
0x180088457  push    rdi
0x180088458  push    r12
0x18008845a  push    r13
0x18008845c  push    r14
0x18008845e  push    r15
0x180088460  mov     rbp, rsp
0x180088463  sub     rsp, 50h
0x180088467  mov     rdi, r9
0x18008846a  mov     r14, r8
0x18008846d  mov     rbx, rdx
0x180088470  mov     r15, rcx
0x180088473  mov     rcx, cs:WPP_GLOBAL_Control
0x18008847a  lea     r13, WPP_GLOBAL_Control
0x180088481  cmp     rcx, r13
0x180088484  jz      short loc_1800884B0
0x180088486  test    byte ptr [rcx+1Ch], 10h
0x18008848a  jz      short loc_1800884B0
0x18008848c  cmp     byte ptr [rcx+19h], 6
0x180088490  jb      short loc_1800884B0
0x180088492  cmp     dword ptr [r15+8], 1
0x180088497  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x18008849e  mov     rcx, [rcx+10h]
0x1800884a2  mov     edx, 55h ; 'U'
0x1800884a7  setz    r9b
0x1800884ab  call    WPP_SF_c
0x1800884b0  xor     r12d, r12d
0x1800884b3  test    rbx, rbx
0x1800884b6  jnz     short loc_1800884BD
0x1800884b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800884bd  mov     [r14], r12
0x1800884c0  lea     rdx, [rbp+var_30]
0x1800884c4  mov     [rdi], r12
0x1800884c7  mov     rcx, rbx
0x1800884ca  mov     rax, [rbx]
0x1800884cd  mov     rsi, r12
0x1800884d0  mov     [rbp+var_30], r12
0x1800884d4  mov     [rbp+var_10], r12
0x1800884d8  mov     [rbp+arg_18], r12
0x1800884dc  mov     rax, [rax+40h]
0x1800884e0  mov     [rbp+arg_8], r12d
0x1800884e4  mov     [rbp+string], r12
0x1800884e8  mov     [rbp+var_18], r12
0x1800884ec  mov     [rbp+lpMem], r12
0x1800884f0  mov     [rbp+var_28], r12
0x1800884f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800884f9  mov     ebx, eax
0x1800884fb  test    eax, eax
0x1800884fd  jns     short loc_18008856E
0x1800884ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180088506  cmp     rcx, r13
0x180088509  jz      short loc_18008852F
0x18008850b  test    byte ptr [rcx+1Ch], 10h
0x18008850f  jz      short loc_18008852F
0x180088511  cmp     byte ptr [rcx+19h], 2
0x180088515  jb      short loc_18008852F
0x180088517  mov     rcx, [rcx+10h]
0x18008851b  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180088522  mov     edx, 56h ; 'V'
0x180088527  mov     r9d, eax
0x18008852a  call    WPP_SF_d
0x18008852f  mov     rcx, [rbp+38h]; this
0x180088533  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008853a  mov     r9d, ebx; char *
0x18008853d  mov     edx, 2A1h; void *
0x180088542  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180088547  mov     rcx, cs:WPP_GLOBAL_Control
0x18008854e  cmp     rcx, r13
0x180088551  jz      loc_180088A59
0x180088557  test    byte ptr [rcx+1Ch], 80h
0x18008855b  jz      loc_180088A59
0x180088561  mov     edx, 57h ; 'W'
0x180088566  mov     r9d, ebx
0x180088569  jmp     loc_1800887A1
0x18008856e  mov     rcx, [rbp+var_30]
0x180088572  lea     rdx, [rbp+string]
0x180088576  mov     rax, [rcx]
0x180088579  mov     rax, [rax+38h]
0x18008857d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088582  mov     ebx, eax
0x180088584  test    eax, eax
0x180088586  jns     short loc_1800885F4
0x180088588  mov     rcx, cs:WPP_GLOBAL_Control
0x18008858f  cmp     rcx, r13
0x180088592  jz      short loc_1800885B8
0x180088594  test    byte ptr [rcx+1Ch], 10h
0x180088598  jz      short loc_1800885B8
0x18008859a  cmp     byte ptr [rcx+19h], 2
0x18008859e  jb      short loc_1800885B8
0x1800885a0  mov     rcx, [rcx+10h]
0x1800885a4  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x1800885ab  mov     edx, 58h ; 'X'
0x1800885b0  mov     r9d, eax
0x1800885b3  call    WPP_SF_d
0x1800885b8  mov     rcx, [rbp+38h]; this
0x1800885bc  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800885c3  mov     r9d, ebx; char *
0x1800885c6  mov     edx, 2A7h; void *
0x1800885cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800885d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800885d7  cmp     rcx, r13
0x1800885da  jz      loc_180088A59
0x1800885e0  test    byte ptr [rcx+1Ch], 80h
0x1800885e4  jz      loc_180088A59
0x1800885ea  mov     edx, 59h ; 'Y'
0x1800885ef  jmp     loc_180088566
0x1800885f4  mov     rdx, [rbp+string]; HSTRING
0x1800885f8  lea     r8, [rbp+lpMem]; char **
0x1800885fc  mov     rcx, r15; this
0x1800885ff  call    ?ConvertHString@AuthManagerImpl@@AEAAJPEAUHSTRING__@@PEAPEAD@Z; AuthManagerImpl::ConvertHString(HSTRING__ *,char * *)
0x180088604  mov     ebx, eax
0x180088606  test    eax, eax
0x180088608  jns     short loc_180088676
0x18008860a  mov     rcx, cs:WPP_GLOBAL_Control
0x180088611  cmp     rcx, r13
0x180088614  jz      short loc_18008863A
0x180088616  test    byte ptr [rcx+1Ch], 10h
0x18008861a  jz      short loc_18008863A
0x18008861c  cmp     byte ptr [rcx+19h], 2
0x180088620  jb      short loc_18008863A
0x180088622  mov     rcx, [rcx+10h]
0x180088626  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x18008862d  mov     edx, 5Ah ; 'Z'
0x180088632  mov     r9d, eax
0x180088635  call    WPP_SF_d
0x18008863a  mov     rcx, [rbp+38h]; this
0x18008863e  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180088645  mov     r9d, ebx; char *
0x180088648  mov     edx, 2ABh; void *
0x18008864d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180088652  mov     rcx, cs:WPP_GLOBAL_Control
0x180088659  cmp     rcx, r13
0x18008865c  jz      loc_180088A59
0x180088662  test    byte ptr [rcx+1Ch], 80h
0x180088666  jz      loc_180088A59
0x18008866c  mov     edx, 5Bh ; '['
0x180088671  jmp     loc_180088566
0x180088676  mov     rcx, [rbp+var_30]
0x18008867a  lea     rdx, [rbp+var_10]
0x18008867e  mov     rax, [rcx]
0x180088681  mov     rax, [rax+30h]
0x180088685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008868a  mov     ebx, eax
0x18008868c  test    eax, eax
0x18008868e  jns     short loc_1800886FC
0x180088690  mov     rcx, cs:WPP_GLOBAL_Control
0x180088697  cmp     rcx, r13
0x18008869a  jz      short loc_1800886C0
0x18008869c  test    byte ptr [rcx+1Ch], 10h
0x1800886a0  jz      short loc_1800886C0
0x1800886a2  cmp     byte ptr [rcx+19h], 2
0x1800886a6  jb      short loc_1800886C0
0x1800886a8  mov     rcx, [rcx+10h]
0x1800886ac  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x1800886b3  mov     edx, 5Ch ; '\'
0x1800886b8  mov     r9d, eax
0x1800886bb  call    WPP_SF_d
0x1800886c0  mov     rcx, [rbp+38h]; this
0x1800886c4  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800886cb  mov     r9d, ebx; char *
0x1800886ce  mov     edx, 2AFh; void *
0x1800886d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800886d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800886df  cmp     rcx, r13
0x1800886e2  jz      loc_180088A59
0x1800886e8  test    byte ptr [rcx+1Ch], 80h
0x1800886ec  jz      loc_180088A59
0x1800886f2  mov     edx, 5Dh ; ']'
0x1800886f7  jmp     loc_180088566
0x1800886fc  mov     rcx, [rbp+var_10]
0x180088700  test    rcx, rcx
0x180088703  jnz     loc_1800887B6
0x180088709  test    cs:byte_1800AFD83, 1
0x180088710  mov     ebx, 8007000Dh
0x180088715  mov     edi, 8007000Dh
0x18008871a  jz      short loc_180088737
0x18008871c  cmp     dword ptr [r15+8], 1
0x180088721  lea     rdx, WPNPRV_AUTH_DEVICE_ID_FAILURE
0x180088728  mov     r9d, r12d
0x18008872b  mov     r8d, edi
0x18008872e  setz    r9b
0x180088732  call    McTemplateU0qq_EventWriteTransfer
0x180088737  mov     rcx, cs:WPP_GLOBAL_Control
0x18008873e  cmp     rcx, r13
0x180088741  jz      short loc_180088767
0x180088743  test    byte ptr [rcx+1Ch], 10h
0x180088747  jz      short loc_180088767
0x180088749  cmp     byte ptr [rcx+19h], 2
0x18008874d  jb      short loc_180088767
0x18008874f  mov     rcx, [rcx+10h]
0x180088753  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x18008875a  mov     edx, 5Eh ; '^'
0x18008875f  mov     r9d, ebx
0x180088762  call    WPP_SF_d
0x180088767  mov     rcx, [rbp+38h]; this
0x18008876b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180088772  mov     r9d, ebx; char *
0x180088775  mov     edx, 2BBh; void *
0x18008877a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008877f  mov     rcx, cs:WPP_GLOBAL_Control
0x180088786  cmp     rcx, r13
0x180088789  jz      loc_180088A59
0x18008878f  test    byte ptr [rcx+1Ch], 80h
0x180088793  jz      loc_180088A59
0x180088799  mov     edx, 5Fh ; '_'
0x18008879e  mov     r9d, edi
0x1800887a1  mov     rcx, [rcx+10h]
0x1800887a5  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x1800887ac  call    WPP_SF_d
0x1800887b1  jmp     loc_180088A59
0x1800887b6  mov     rax, [rcx]
0x1800887b9  lea     r8, [rbp+arg_18]
0x1800887bd  xor     edx, edx
0x1800887bf  mov     rax, [rax+30h]
0x1800887c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800887c8  mov     ebx, eax
0x1800887ca  test    eax, eax
0x1800887cc  jns     short loc_18008883A
0x1800887ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800887d5  cmp     rcx, r13
0x1800887d8  jz      short loc_1800887FE
0x1800887da  test    byte ptr [rcx+1Ch], 10h
0x1800887de  jz      short loc_1800887FE
0x1800887e0  cmp     byte ptr [rcx+19h], 2
0x1800887e4  jb      short loc_1800887FE
0x1800887e6  mov     rcx, [rcx+10h]
0x1800887ea  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x1800887f1  mov     edx, 60h ; '`'
0x1800887f6  mov     r9d, eax
0x1800887f9  call    WPP_SF_d
0x1800887fe  mov     rcx, [rbp+38h]; this
0x180088802  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180088809  mov     r9d, ebx; char *
0x18008880c  mov     edx, 2C1h; void *
0x180088811  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180088816  mov     rcx, cs:WPP_GLOBAL_Control
0x18008881d  cmp     rcx, r13
0x180088820  jz      loc_180088A59
0x180088826  test    byte ptr [rcx+1Ch], 80h
0x18008882a  jz      loc_180088A59
0x180088830  mov     edx, 61h ; 'a'
0x180088835  jmp     loc_180088566
0x18008883a  mov     rcx, [rbp+arg_18]
0x18008883e  lea     rdx, [rbp+arg_8]
0x180088842  mov     rax, [rcx]
0x180088845  mov     rax, [rax+40h]
0x180088849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008884e  mov     ebx, eax
0x180088850  test    eax, eax
0x180088852  jns     short loc_1800888C0
0x180088854  mov     rcx, cs:WPP_GLOBAL_Control
0x18008885b  cmp     rcx, r13
0x18008885e  jz      short loc_180088884
0x180088860  test    byte ptr [rcx+1Ch], 10h
0x180088864  jz      short loc_180088884
0x180088866  cmp     byte ptr [rcx+19h], 2
0x18008886a  jb      short loc_180088884
0x18008886c  mov     rcx, [rcx+10h]
0x180088870  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180088877  mov     edx, 62h ; 'b'
0x18008887c  mov     r9d, eax
0x18008887f  call    WPP_SF_d
0x180088884  mov     rcx, [rbp+38h]; this
0x180088888  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008888f  mov     r9d, ebx; char *
0x180088892  mov     edx, 2C5h; void *
0x180088897  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008889c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800888a3  cmp     rcx, r13
0x1800888a6  jz      loc_180088A59
0x1800888ac  test    byte ptr [rcx+1Ch], 80h
0x1800888b0  jz      loc_180088A59
0x1800888b6  mov     edx, 63h ; 'c'
0x1800888bb  jmp     loc_180088566
0x1800888c0  cmp     [rbp+arg_8], r12d
0x1800888c4  jl      loc_180088A1C
0x1800888ca  mov     rcx, [rbp+arg_18]
0x1800888ce  lea     rdx, [rbp+var_18]
0x1800888d2  mov     rax, [rcx]
0x1800888d5  mov     rax, [rax+30h]
0x1800888d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800888de  mov     ebx, eax
0x1800888e0  test    eax, eax
0x1800888e2  jns     short loc_180088950
0x1800888e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800888eb  cmp     rcx, r13
0x1800888ee  jz      short loc_180088914
0x1800888f0  test    byte ptr [rcx+1Ch], 10h
0x1800888f4  jz      short loc_180088914
0x1800888f6  cmp     byte ptr [rcx+19h], 2
0x1800888fa  jb      short loc_180088914
0x1800888fc  mov     rcx, [rcx+10h]
0x180088900  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180088907  mov     edx, 64h ; 'd'
0x18008890c  mov     r9d, eax
0x18008890f  call    WPP_SF_d
0x180088914  mov     rcx, [rbp+38h]; this
0x180088918  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
  ... truncated ...
```
