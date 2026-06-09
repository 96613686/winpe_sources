# CDlpActionLayoutUsb::ExportDrivers(HINSTANCE__ *,ushort const *,unsigned __int64)

- ea: `0x180016a74`
- end: `0x180016fa7`
- name: `?ExportDrivers@CDlpActionLayoutUsb@@AEAAJPEAUHINSTANCE__@@PEBG_K@Z`
- size: `1331`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *this, HINSTANCE, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800244d4`

## callees

- `0x18000aba4`
- `0x18000b7f8`
- `0x180012f5c`
- `0x180016a74`
- `0x18001fd60`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d0d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016ac8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016ac8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016f52`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016f52`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180016e6b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180016e6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016b3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016bb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016cff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016b3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016bb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016c32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f5b`

## string_xrefs

- `0x180016bab`: `DismOpenSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CDlpActionLayoutUsb::ExportDrivers(
        CDlpActionLayoutUsb *this,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  __int64 v7; // r13
  HANDLE EventW; // r14
  __int64 (*v9)(void); // r12
  __int64 (*v10)(void); // r15
  signed int v11; // edi
  __int64 *v12; // rbx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  FARPROC ProcAddress; // r14
  signed int LastError; // eax
  __int64 v18; // rcx
  int v19; // eax
  FARPROC v20; // r15
  signed int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  signed int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  signed int v27; // eax
  FARPROC v28; // r12
  signed int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  __int64 v41; // rcx
  int v42; // eax
  int v43; // eax
  HANDLE ProcessHeap; // rax
  int v46; // [rsp+20h] [rbp-60h]
  int v47; // [rsp+20h] [rbp-60h]
  __int64 v48; // [rsp+20h] [rbp-60h]
  signed int v49; // [rsp+28h] [rbp-58h]
  int v50; // [rsp+28h] [rbp-58h]
  int v51; // [rsp+30h] [rbp-50h]
  FARPROC v52; // [rsp+38h] [rbp-48h]
  HANDLE hEvent; // [rsp+40h] [rbp-40h]
  __int64 (*v54)(void); // [rsp+48h] [rbp-38h]
  __int64 v55; // [rsp+50h] [rbp-30h] BYREF
  __int128 v56; // [rsp+58h] [rbp-28h] BYREF
  __int128 v57; // [rsp+68h] [rbp-18h]
  unsigned int v58; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v59; // [rsp+D8h] [rbp+58h]

  v59 = a4;
  v58 = 0;
  v51 = 0;
  v7 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  hEvent = EventW;
  v9 = 0;
  v10 = 0;
  v52 = 0;
  if ( !a2 )
  {
    v11 = -2147024809;
    v12 = (__int64 *)((char *)this + 88);
    v13 = *((_QWORD *)this + 11);
    if ( v13 )
    {
      v14 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v13,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::ExportDrivers",
              2740,
              -2147024809);
      v15 = (unsigned int)v14;
      if ( v14 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
    }
    goto LABEL_71;
  }
  ProcAddress = GetProcAddress(a2, "DismInitialize");
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = (__int64 *)((char *)this + 88);
    if ( *((_QWORD *)this + 11) )
    {
      v18 = 0;
      if ( v11 < 0 )
      {
        v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
                *v12,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::ExportDrivers",
                2743,
                v11);
        v18 = (unsigned int)v19;
        if ( v19 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
    }
    EventW = hEvent;
    goto LABEL_71;
  }
  v20 = GetProcAddress(a2, "DismOpenSession");
  if ( v20 )
  {
    v9 = GetProcAddress(a2, "DismCloseSession");
    v54 = v9;
    if ( !v9 )
    {
      v24 = GetLastError();
      v11 = v24;
      if ( v24 > 0 )
        v11 = (unsigned __int16)v24 | 0x80070000;
      v12 = (__int64 *)((char *)this + 88);
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_33;
      v25 = 0;
      if ( v11 >= 0 )
      {
LABEL_32:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v25);
LABEL_33:
        EventW = hEvent;
LABEL_70:
        v10 = v52;
        goto LABEL_71;
      }
      v49 = v11;
      v46 = 2749;
LABEL_30:
      v26 = CDlpLogT<CEmptyType>::DlpLogFormat(
              *v12,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::ExportDrivers",
              v46,
              v49);
      v25 = (unsigned int)v26;
      if ( v26 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26);
      goto LABEL_32;
    }
    v52 = GetProcAddress(a2, "DismShutdown");
    if ( !v52 )
    {
      v27 = GetLastError();
      v11 = v27;
      if ( v27 > 0 )
        v11 = (unsigned __int16)v27 | 0x80070000;
      v12 = (__int64 *)((char *)this + 88);
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_33;
      v25 = 0;
      if ( v11 >= 0 )
        goto LABEL_32;
      v49 = v11;
      v46 = 2752;
      goto LABEL_30;
    }
    v28 = GetProcAddress(a2, "_DismExportDriver");
    if ( v28 )
    {
      v33 = CDlpHelpersT<CEmptyType>::CombinePath((__int64)a3, (__int64)L"sources\\Drivers", (__int64)&v55);
      v11 = v33;
      v12 = (__int64 *)((char *)this + 88);
      v34 = *((_QWORD *)this + 11);
      if ( v33 < 0 )
      {
        if ( v34 )
        {
          v35 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v34,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutUsb::ExportDrivers",
                  2759,
                  v33);
          v36 = (unsigned int)v35;
          if ( v35 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v35);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v36);
        }
        v7 = v55;
        goto LABEL_49;
      }
      v7 = v55;
      if ( v34 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v34, 2u, (__int64)L"LayoutUsb: Exporting drivers to [%s]...", v55);
      v37 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD))ProcAddress)(2, 0, 0);
      v11 = v37;
      if ( v37 >= 0 )
      {
        v51 = 1;
        v38 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, unsigned int *))v20)(
                L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}",
                0,
                0,
                &v58);
        v11 = v38;
        if ( v38 >= 0 )
        {
          EventW = hEvent;
          ResetEvent(hEvent);
          *(_QWORD *)&v56 = hEvent;
          *(_QWORD *)&v57 = this;
          *((_QWORD *)&v56 + 1) = v59;
          DWORD2(v57) = 0;
          v39 = ((__int64 (__fastcall *)(_QWORD, __int64, HANDLE, void (__fastcall *)(unsigned int, unsigned int, void *), __int128 *))v28)(
                  v58,
                  v7,
                  hEvent,
                  CDlpActionLayoutUsb::DriverExportCallBack,
                  &v56);
          v11 = v39;
          if ( v39 < 0 && *v12 )
          {
            LODWORD(v48) = 2786;
            v40 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    *v12,
                    4u,
                    (__int64)L"%s(%d): Result = 0x%X",
                    L"CDlpActionLayoutUsb::ExportDrivers",
                    v48,
                    v39);
            v41 = (unsigned int)v40;
            if ( v40 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v40);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v41);
          }
          goto LABEL_69;
        }
        v31 = *v12;
        if ( !*v12 )
        {
LABEL_49:
          EventW = hEvent;
LABEL_69:
          v9 = v54;
          goto LABEL_70;
        }
        v50 = v38;
        v47 = 2771;
      }
      else
      {
        v31 = *v12;
        if ( !*v12 )
          goto LABEL_49;
        v50 = v37;
        v47 = 2766;
      }
    }
    else
    {
      v29 = GetLastError();
      v11 = v29;
      if ( v29 > 0 )
        v11 = (unsigned __int16)v29 | 0x80070000;
      v12 = (__int64 *)((char *)this + 88);
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_49;
      v30 = 0;
      if ( v11 >= 0 )
        goto LABEL_48;
      v50 = v11;
      v47 = 2755;
      v31 = *v12;
    }
    v32 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v31,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutUsb::ExportDrivers",
            v47,
            v50);
    v30 = (unsigned int)v32;
    if ( v32 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v32);
LABEL_48:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v30);
    goto LABEL_49;
  }
  v21 = GetLastError();
  v11 = v21;
  if ( v21 > 0 )
    v11 = (unsigned __int16)v21 | 0x80070000;
  v12 = (__int64 *)((char *)this + 88);
  if ( *((_QWORD *)this + 11) )
  {
    v22 = 0;
    if ( v11 < 0 )
    {
      v23 = CDlpLogT<CEmptyType>::DlpLogFormat(
              *v12,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::ExportDrivers",
              2746,
              v11);
      v22 = (unsigned int)v23;
      if ( v23 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v22);
  }
  EventW = hEvent;
  v10 = 0;
LABEL_71:
  if ( v58 )
  {
    v42 = v9();
    if ( v42 < 0 )
    {
      if ( *v12 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          *v12,
          3u,
          (__int64)L"LayoutUsb: Failed to close DISM session: 0x%08x",
          (unsigned int)v42);
    }
  }
  if ( v51 )
  {
    v43 = v10();
    if ( v43 < 0 )
    {
      if ( *v12 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          *v12,
          3u,
          (__int64)L"LayoutUsb: Failed to shutdown DISM: 0x%08x",
          (unsigned int)v43);
    }
  }
  SetEvent(EventW);
  CloseHandle(EventW);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180016a74  mov     [rsp-38h+arg_0], rbx
0x180016a79  mov     [rsp-38h+arg_18], r9
0x180016a7e  push    rbp
0x180016a7f  push    rsi
0x180016a80  push    rdi
0x180016a81  push    r12
0x180016a83  push    r13
0x180016a85  push    r14
0x180016a87  push    r15
0x180016a89  mov     rbp, rsp
0x180016a8c  sub     rsp, 80h
0x180016a93  mov     rdi, r8
0x180016a96  mov     rbx, rdx
0x180016a99  mov     rsi, rcx
0x180016a9c  mov     [rbp+arg_8], 0
0x180016aa3  mov     [rbp+var_50], 0
0x180016aaa  xor     r13d, r13d
0x180016aad  mov     [rbp+var_30], r13
0x180016ab1  xorps   xmm0, xmm0
0x180016ab4  movups  [rbp+var_28], xmm0
0x180016ab8  movups  [rbp+var_18], xmm0
0x180016abc  xor     r9d, r9d; lpName
0x180016abf  xor     r8d, r8d; bInitialState
0x180016ac2  lea     edx, [r13+1]; bManualReset
0x180016ac6  xor     ecx, ecx; lpEventAttributes
0x180016ac8  call    cs:__imp_CreateEventW
0x180016ace  mov     r14, rax
0x180016ad1  mov     [rbp+hEvent], rax
0x180016ad5  xor     r12d, r12d
0x180016ad8  xor     r15d, r15d
0x180016adb  mov     [rbp+var_48], r15
0x180016adf  test    rbx, rbx
0x180016ae2  jnz     short loc_180016B31
0x180016ae4  mov     edi, 80070057h
0x180016ae9  lea     rbx, [rsi+58h]
0x180016aed  mov     rcx, [rbx]
0x180016af0  test    rcx, rcx
0x180016af3  jz      loc_180016EF3
0x180016af9  mov     [rsp+80h+var_58], edi
0x180016afd  mov     dword ptr [rsp+80h+var_60], 0AB4h
0x180016b05  lea     r9, aCdlpactionlayo_25; "CDlpActionLayoutUsb::ExportDrivers"
0x180016b0c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180016b13  lea     edx, [r13+4]
0x180016b17  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180016b1c  mov     ecx, eax
0x180016b1e  test    eax, eax
0x180016b20  jns     short loc_180016B27
0x180016b22  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016b27  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016b2c  jmp     loc_180016EF3
0x180016b31  lea     rdx, aDisminitialize; "DismInitialize"
0x180016b38  mov     rcx, rbx; hModule
0x180016b3b  call    cs:__imp_GetProcAddress
0x180016b41  mov     r14, rax
0x180016b44  test    rax, rax
0x180016b47  jnz     short loc_180016BAB
0x180016b49  call    cs:__imp_GetLastError
0x180016b4f  mov     edi, eax
0x180016b51  test    eax, eax
0x180016b53  jle     short loc_180016B5E
0x180016b55  movzx   edi, ax
0x180016b58  or      edi, 80070000h
0x180016b5e  lea     rbx, [rsi+58h]
0x180016b62  cmp     [rbx], r12
0x180016b65  jz      short loc_180016BA2
0x180016b67  xor     ecx, ecx
0x180016b69  test    edi, edi
0x180016b6b  jns     short loc_180016B9D
0x180016b6d  mov     [rsp+80h+var_58], edi
0x180016b71  mov     dword ptr [rsp+80h+var_60], 0AB7h
0x180016b79  lea     r9, aCdlpactionlayo_25; "CDlpActionLayoutUsb::ExportDrivers"
0x180016b80  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180016b87  lea     edx, [rcx+4]
0x180016b8a  mov     rcx, [rbx]
0x180016b8d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180016b92  mov     ecx, eax
0x180016b94  test    eax, eax
0x180016b96  jns     short loc_180016B9D
0x180016b98  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016b9d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016ba2  mov     r14, [rbp+hEvent]
0x180016ba6  jmp     loc_180016EF3
0x180016bab  lea     rdx, aDismopensessio; "DismOpenSession"
0x180016bb2  mov     rcx, rbx; hModule
0x180016bb5  call    cs:__imp_GetProcAddress
0x180016bbb  mov     r15, rax
0x180016bbe  test    rax, rax
0x180016bc1  jnz     short loc_180016C28
0x180016bc3  call    cs:__imp_GetLastError
0x180016bc9  mov     edi, eax
0x180016bcb  test    eax, eax
0x180016bcd  jle     short loc_180016BD8
0x180016bcf  movzx   edi, ax
0x180016bd2  or      edi, 80070000h
0x180016bd8  lea     rbx, [rsi+58h]
0x180016bdc  cmp     [rbx], r12
0x180016bdf  jz      short loc_180016C1C
0x180016be1  xor     ecx, ecx
0x180016be3  test    edi, edi
0x180016be5  jns     short loc_180016C17
0x180016be7  mov     [rsp+80h+var_58], edi
0x180016beb  mov     dword ptr [rsp+80h+var_60], 0ABAh
0x180016bf3  lea     r9, aCdlpactionlayo_25; "CDlpActionLayoutUsb::ExportDrivers"
0x180016bfa  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180016c01  lea     edx, [rcx+4]
0x180016c04  mov     rcx, [rbx]
0x180016c07  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180016c0c  mov     ecx, eax
0x180016c0e  test    eax, eax
0x180016c10  jns     short loc_180016C17
0x180016c12  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016c17  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016c1c  mov     r14, [rbp+hEvent]
0x180016c20  mov     r15, r12
0x180016c23  jmp     loc_180016EF3
0x180016c28  lea     rdx, aDismclosesessi; "DismCloseSession"
0x180016c2f  mov     rcx, rbx; hModule
0x180016c32  call    cs:__imp_GetProcAddress
0x180016c38  mov     r12, rax
0x180016c3b  mov     [rbp+var_38], rax
0x180016c3f  test    rax, rax
0x180016c42  jnz     short loc_180016CA9
0x180016c44  call    cs:__imp_GetLastError
0x180016c4a  mov     edi, eax
0x180016c4c  test    eax, eax
0x180016c4e  jle     short loc_180016C59
0x180016c50  movzx   edi, ax
0x180016c53  or      edi, 80070000h
0x180016c59  lea     rbx, [rsi+58h]
0x180016c5d  cmp     qword ptr [rbx], 0
0x180016c61  jz      short loc_180016CA0
0x180016c63  xor     ecx, ecx
0x180016c65  test    edi, edi
0x180016c67  jns     short loc_180016C9B
0x180016c69  mov     [rsp+80h+var_58], edi
0x180016c6d  mov     dword ptr [rsp+80h+var_60], 0ABDh
0x180016c75  lea     r9, aCdlpactionlayo_25; "CDlpActionLayoutUsb::ExportDrivers"
0x180016c7c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180016c83  mov     edx, 4
0x180016c88  mov     rcx, [rbx]
0x180016c8b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180016c90  test    eax, eax
0x180016c92  mov     ecx, eax
0x180016c94  jns     short loc_180016C9B
0x180016c96  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016c9b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016ca0  mov     r14, [rbp+hEvent]
0x180016ca4  jmp     loc_180016EEF
0x180016ca9  lea     rdx, aDismshutdown; "DismShutdown"
0x180016cb0  mov     rcx, rbx; hModule
0x180016cb3  call    cs:__imp_GetProcAddress
0x180016cb9  mov     [rbp+var_48], rax
0x180016cbd  test    rax, rax
0x180016cc0  jnz     short loc_180016CF5
0x180016cc2  call    cs:__imp_GetLastError
0x180016cc8  mov     edi, eax
0x180016cca  test    eax, eax
0x180016ccc  jle     short loc_180016CD7
0x180016cce  movzx   edi, ax
0x180016cd1  or      edi, 80070000h
0x180016cd7  lea     rbx, [rsi+58h]
0x180016cdb  cmp     qword ptr [rbx], 0
0x180016cdf  jz      short loc_180016CA0
0x180016ce1  xor     ecx, ecx
0x180016ce3  test    edi, edi
0x180016ce5  jns     short loc_180016C9B
0x180016ce7  mov     [rsp+80h+var_58], edi
0x180016ceb  mov     dword ptr [rsp+80h+var_60], 0AC0h
0x180016cf3  jmp     short loc_180016C75
0x180016cf5  lea     rdx, aDismexportdriv; "_DismExportDriver"
0x180016cfc  mov     rcx, rbx; hModule
0x180016cff  call    cs:__imp_GetProcAddress
0x180016d05  mov     r12, rax
0x180016d08  test    rax, rax
0x180016d0b  jnz     short loc_180016D72
0x180016d0d  call    cs:__imp_GetLastError
0x180016d13  mov     edi, eax
0x180016d15  test    eax, eax
0x180016d17  jle     short loc_180016D22
0x180016d19  movzx   edi, ax
0x180016d1c  or      edi, 80070000h
0x180016d22  lea     rbx, [rsi+58h]
0x180016d26  cmp     qword ptr [rbx], 0
0x180016d2a  jz      short loc_180016D69
0x180016d2c  xor     ecx, ecx
0x180016d2e  test    edi, edi
0x180016d30  jns     short loc_180016D64
0x180016d32  mov     [rsp+80h+var_58], edi
0x180016d36  mov     dword ptr [rsp+80h+var_60], 0AC3h
0x180016d3e  mov     rcx, [rbx]
0x180016d41  lea     r9, aCdlpactionlayo_25; "CDlpActionLayoutUsb::ExportDrivers"
0x180016d48  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180016d4f  mov     edx, 4
0x180016d54  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180016d59  test    eax, eax
0x180016d5b  mov     ecx, eax
0x180016d5d  jns     short loc_180016D64
0x180016d5f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016d64  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016d69  mov     r14, [rbp+hEvent]
0x180016d6d  jmp     loc_180016EEB
0x180016d72  lea     r8, [rbp+var_30]
0x180016d76  lea     rdx, aSourcesDrivers; "sources\\Drivers"
0x180016d7d  mov     rcx, rdi
0x180016d80  call    ?CombinePath@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBG0PEAPEAG@Z; CDlpHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort * *)
0x180016d85  mov     edi, eax
0x180016d87  lea     rbx, [rsi+58h]
0x180016d8b  mov     rcx, [rbx]
0x180016d8e  test    eax, eax
0x180016d90  jns     short loc_180016DD1
0x180016d92  test    rcx, rcx
0x180016d95  jz      short loc_180016DCB
0x180016d97  mov     [rsp+80h+var_58], eax
0x180016d9b  mov     dword ptr [rsp+80h+var_60], 0AC7h
0x180016da3  lea     r9, aCdlpactionlayo_25; "CDlpActionLayoutUsb::ExportDrivers"
0x180016daa  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180016db1  mov     edx, 4
0x180016db6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180016dbb  mov     ecx, eax
0x180016dbd  test    eax, eax
0x180016dbf  jns     short loc_180016DC6
0x180016dc1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016dc6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016dcb  mov     r13, [rbp+var_30]
0x180016dcf  jmp     short loc_180016D69
0x180016dd1  mov     edi, 2
0x180016dd6  mov     r13, [rbp+var_30]
0x180016dda  test    rcx, rcx
0x180016ddd  jz      short loc_180016DF0
0x180016ddf  mov     r9, r13
0x180016de2  lea     r8, aLayoutusbExpor_0; "LayoutUsb: Exporting drivers to [%s]..."
0x180016de9  mov     edx, edi
0x180016deb  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180016df0  xor     r8d, r8d
0x180016df3  xor     edx, edx
0x180016df5  mov     ecx, edi
0x180016df7  mov     rax, r14
0x180016dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dff  mov     edi, eax
0x180016e01  test    eax, eax
0x180016e03  jns     short loc_180016E22
0x180016e05  mov     rcx, [rbx]
0x180016e08  test    rcx, rcx
0x180016e0b  jz      loc_180016D69
0x180016e11  mov     [rsp+80h+var_58], eax
0x180016e15  mov     dword ptr [rsp+80h+var_60], 0ACEh
0x180016e1d  jmp     loc_180016D41
0x180016e22  mov     [rbp+var_50], 1
0x180016e29  lea     r9, [rbp+arg_8]
0x180016e2d  xor     r8d, r8d
0x180016e30  xor     edx, edx
0x180016e32  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x180016e39  mov     rax, r15
0x180016e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e41  mov     edi, eax
0x180016e43  test    eax, eax
0x180016e45  jns     short loc_180016E64
0x180016e47  mov     rcx, [rbx]
0x180016e4a  test    rcx, rcx
0x180016e4d  jz      loc_180016D69
0x180016e53  mov     [rsp+80h+var_58], eax
0x180016e57  mov     dword ptr [rsp+80h+var_60], 0AD3h
0x180016e5f  jmp     loc_180016D41
0x180016e64  mov     r14, [rbp+hEvent]
0x180016e68  mov     rcx, r14; hEvent
0x180016e6b  call    cs:__imp_ResetEvent
0x180016e71  mov     qword ptr [rbp+var_28], r14
0x180016e75  mov     qword ptr [rbp+var_18], rsi
0x180016e79  mov     rax, [rbp+arg_18]
0x180016e7d  mov     qword ptr [rbp+var_28+8], rax
0x180016e81  mov     dword ptr [rbp+var_18+8], 0
0x180016e88  lea     rax, [rbp+var_28]
0x180016e8c  mov     [rsp+80h+var_60], rax
0x180016e91  lea     r9, ?DriverExportCallBack@CDlpActionLayoutUsb@@CAXIIPEAX@Z; CDlpActionLayoutUsb::DriverExportCallBack(uint,uint,void *)
0x180016e98  mov     r8, r14
0x180016e9b  mov     rdx, r13
0x180016e9e  mov     ecx, [rbp+arg_8]
0x180016ea1  mov     rax, r12
0x180016ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ea9  mov     edi, eax
0x180016eab  test    eax, eax
0x180016ead  jns     short loc_180016EEB
0x180016eaf  mov     rcx, [rbx]
0x180016eb2  test    rcx, rcx
0x180016eb5  jz      short loc_180016EEB
0x180016eb7  mov     [rsp+80h+var_58], eax
0x180016ebb  mov     dword ptr [rsp+80h+var_60], 0AE2h
0x180016ec3  lea     r9, aCdlpactionlayo_25; "CDlpActionLayoutUsb::ExportDrivers"
0x180016eca  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180016ed1  mov     edx, 4
0x180016ed6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180016edb  mov     ecx, eax
0x180016edd  test    eax, eax
0x180016edf  jns     short loc_180016EE6
0x180016ee1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016ee6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016eeb  mov     r12, [rbp+var_38]
0x180016eef  mov     r15, [rbp+var_48]
0x180016ef3  mov     esi, 3
0x180016ef8  mov     ecx, [rbp+arg_8]
  ... truncated ...
```
