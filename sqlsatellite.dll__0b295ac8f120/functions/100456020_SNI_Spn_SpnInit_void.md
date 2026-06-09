# SNI_Spn::SpnInit(void)

- ea: `0x100456020`
- end: `0x100456570`
- name: `?SpnInit@SNI_Spn@@SAKXZ`
- size: `1360`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x10042a070`

## callees

- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x1004555d0`
- `0x100456020`
- `0x100456580`
- `0x100486af0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1004560c7`
- `KERNEL32!SetLastError` at `0x10045622c`
- `KERNEL32!SetLastError` at `0x1004562e7`
- `KERNEL32!SetLastError` at `0x10045643e`
- `KERNEL32!SetLastError` at `0x1004560c7`
- `KERNEL32!SetLastError` at `0x10045622c`
- `KERNEL32!SetLastError` at `0x1004562e7`
- `KERNEL32!SetLastError` at `0x10045643e`
- `KERNEL32!GetProcAddress` at `0x100456141`
- `KERNEL32!GetProcAddress` at `0x10045615f`
- `KERNEL32!GetProcAddress` at `0x10045617d`
- `KERNEL32!GetProcAddress` at `0x10045619b`
- `KERNEL32!GetProcAddress` at `0x1004561b9`
- `KERNEL32!GetProcAddress` at `0x1004561d7`
- `KERNEL32!GetProcAddress` at `0x1004561f5`
- `KERNEL32!GetProcAddress` at `0x10045628c`
- `KERNEL32!GetProcAddress` at `0x1004562aa`
- `KERNEL32!GetProcAddress` at `0x100456347`
- `KERNEL32!GetProcAddress` at `0x100456364`
- `KERNEL32!GetProcAddress` at `0x100456141`
- `KERNEL32!GetProcAddress` at `0x10045615f`
- `KERNEL32!GetProcAddress` at `0x10045617d`
- `KERNEL32!GetProcAddress` at `0x10045619b`
- `KERNEL32!GetProcAddress` at `0x1004561b9`
- `KERNEL32!GetProcAddress` at `0x1004561d7`
- `KERNEL32!GetProcAddress` at `0x1004561f5`
- `KERNEL32!GetProcAddress` at `0x10045628c`
- `KERNEL32!GetProcAddress` at `0x1004562aa`
- `KERNEL32!GetProcAddress` at `0x100456347`
- `KERNEL32!GetProcAddress` at `0x100456364`
- `KERNEL32!GetLastError` at `0x100456444`
- `KERNEL32!GetLastError` at `0x100456444`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100456100`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x10045626b`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100456326`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100456100`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x10045626b`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100456326`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004563e4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004563e4`
- `sqldk!SystemThread_TlsIndex` at `0x100456387`
- `sqldk!SystemThread_TlsOffset` at `0x100456390`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004563ab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004563ab`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1004560ec`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x100456257`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x100456312`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1004560ec`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x100456257`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x100456312`

## string_xrefs

- `0x10045605f`: `sql\common\dk\sni\src\sni_spn.cpp`
- `0x10045620e`: `netapi32.dll`
- `0x10045624e`: `netapi32.dll`
- `0x1004560a2`: `ntdsapi.dll`
- `0x1004560e3`: `ntdsapi.dll`
- `0x1004562c2`: `secur32.dll`
- `0x100456309`: `secur32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 SNI_Spn::SpnInit(void)
{
  __int64 v0; // rcx
  const char *v1; // rax
  DWORD LastError; // ebx
  HMODULE v3; // rdi
  __int64 v4; // rcx
  const char *v5; // rax
  HMODULE v6; // rax
  HMODULE v7; // r15
  __int64 v8; // rcx
  const char *v9; // rax
  HINSTANCE v10; // rax
  HMODULE v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rax
  char *v14; // rax
  char *v15; // rcx
  _QWORD *v16; // rax
  DWORD v17; // ecx
  const wchar_t *v18; // r9
  unsigned int v20; // eax
  __int64 v21; // [rsp+28h] [rbp-E0h]
  HINSTANCE v22; // [rsp+38h] [rbp-D0h] BYREF
  HINSTANCE v23; // [rsp+40h] [rbp-C8h] BYREF
  HINSTANCE v24[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+58h] [rbp-B0h]
  __int128 v26; // [rsp+68h] [rbp-A0h]
  __int128 v27; // [rsp+78h] [rbp-90h]
  __int128 v28; // [rsp+88h] [rbp-80h]
  FARPROC ProcAddress; // [rsp+98h] [rbp-70h]
  int v30; // [rsp+A8h] [rbp-60h]
  HINSTANCE v31[2]; // [rsp+B0h] [rbp-58h] BYREF
  struct IMemObj *v32; // [rsp+C0h] [rbp-48h]
  char *v33; // [rsp+C8h] [rbp-40h]
  const char *v34; // [rsp+D0h] [rbp-38h]
  const char *v35; // [rsp+D8h] [rbp-30h]
  int v36; // [rsp+E0h] [rbp-28h]
  wchar_t v37[264]; // [rsp+E8h] [rbp-20h] BYREF

  v31[1] = (HINSTANCE)-2LL;
  v34 = "sql\\common\\dk\\sni\\src\\sni_spn.cpp";
  v35 = "SNI_Spn::SpnInit";
  v36 = 66;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\sni_spn.cpp", "SNI_Spn::SpnInit", 66, L"API|SNI\n");
  v0 = 261;
  v1 = "ntdsapi.dll";
  while ( 1 )
  {
    LastError = 0;
    if ( !*v1 )
      break;
    ++v1;
    if ( !--v0 )
    {
      SetLastError(0x7Bu);
      v3 = 0;
      goto LABEL_8;
    }
  }
  FastDBCSToUnicode(0, "ntdsapi.dll", -1, v37, 261);
  v3 = SOS_OS::SOSLoadLibraryW(v37, 1, 0, 0);
LABEL_8:
  v31[0] = v3;
  *(_OWORD *)v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  ProcAddress = 0;
  if ( !v3 )
    goto LABEL_38;
  v24[0] = (HINSTANCE)GetProcAddress(v3, DsFunctionNames);
  if ( !v24[0] )
    goto LABEL_38;
  v24[1] = (HINSTANCE)GetProcAddress(v3, "DsBindW");
  if ( !v24[1] )
    goto LABEL_38;
  *(_QWORD *)&v25 = GetProcAddress(v3, "DsUnBindW");
  if ( !(_QWORD)v25 )
    goto LABEL_38;
  *((_QWORD *)&v25 + 1) = GetProcAddress(v3, "DsGetSpnW");
  if ( !*((_QWORD *)&v25 + 1) )
    goto LABEL_38;
  *(_QWORD *)&v26 = GetProcAddress(v3, "DsFreeSpnArrayW");
  if ( !(_QWORD)v26 )
    goto LABEL_38;
  *((_QWORD *)&v26 + 1) = GetProcAddress(v3, "DsWriteAccountSpnW");
  if ( !*((_QWORD *)&v26 + 1) )
    goto LABEL_38;
  *(_QWORD *)&v27 = GetProcAddress(v3, "DsFreeNameResultW");
  if ( !(_QWORD)v27 )
    goto LABEL_38;
  v4 = 261;
  v5 = "netapi32.dll";
  while ( *v5 )
  {
    ++v5;
    if ( !--v4 )
    {
      SetLastError(0x7Bu);
      v23 = 0;
      goto LABEL_38;
    }
  }
  FastDBCSToUnicode(0, "netapi32.dll", -1, v37, 261);
  v6 = SOS_OS::SOSLoadLibraryW(v37, 1, 0, 0);
  v7 = v6;
  v23 = v6;
  if ( !v6 )
    goto LABEL_38;
  *((_QWORD *)&v27 + 1) = GetProcAddress(v6, "DsGetDcNameW");
  if ( !*((_QWORD *)&v27 + 1) )
    goto LABEL_38;
  *(_QWORD *)&v28 = GetProcAddress(v7, "NetApiBufferFree");
  if ( !(_QWORD)v28 )
    goto LABEL_38;
  v8 = 261;
  v9 = "secur32.dll";
  while ( *v9 )
  {
    ++v9;
    if ( !--v8 )
    {
      SetLastError(0x7Bu);
      v22 = 0;
      goto LABEL_38;
    }
  }
  FastDBCSToUnicode(0, "secur32.dll", -1, v37, 261);
  v10 = SOS_OS::SOSLoadLibraryW(v37, 1, 0, 0);
  v11 = v10;
  v22 = v10;
  if ( !v10 )
    goto LABEL_38;
  *((_QWORD *)&v28 + 1) = GetProcAddress(v10, "GetComputerObjectNameW");
  if ( !*((_QWORD *)&v28 + 1) )
    goto LABEL_38;
  ProcAddress = GetProcAddress(v11, "GetUserNameExW");
  if ( !ProcAddress )
    goto LABEL_38;
  v30 = 167;
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  v32 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v13 + 992) + 56LL) + 8LL);
  v14 = (char *)operator new(0x38u, v32, 1, "sql\\common\\dk\\sni\\src\\sni_spn.cpp", 167, 6u);
  v15 = v14;
  v33 = v14;
  if ( v14 )
  {
    v16 = v14 + 8;
    v16[1] = v16;
    *v16 = v16;
    *((_QWORD *)v15 + 3) = 0;
    *((_DWORD *)v15 + 8) = 0;
    *((_DWORD *)v15 + 9) = 1;
    *((_QWORD *)v15 + 5) = 0;
    *(_QWORD *)v15 = &EventAutoInternal<SuspendQueueSLock>::`vftable';
    *((_DWORD *)v15 + 12) = 536871465;
  }
  else
  {
    v15 = 0;
  }
  SNI_Spn::m_peventSpnRegistrationCompleted = (struct SNIAutoEvent *)v15;
  if ( !v15 )
  {
    v17 = 14;
LABEL_37:
    SetLastError(v17);
LABEL_38:
    LastError = GetLastError();
    SNI_Spn::DoSpnTerminate(v31, &v23, &v22, (struct _DsFunctionTable *)v24);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v21) = LastError;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni_spn.cpp", "SNI_Spn::SpnInit", 199, L"RET|SNI%d{WINERR}\n", v21);
    }
    goto LABEL_40;
  }
  v20 = SNIAutoEvent::FInit((SNIAutoEvent *)v15);
  if ( v20 )
  {
    v17 = v20;
    goto LABEL_37;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni_spn.cpp", "SNI_Spn::SpnInit", 183, L"RET|SNI%d{WINERR}\n", 0);
  gDsFunc = *(_OWORD *)v24;
  xmmword_100516DD0 = v25;
  xmmword_100516DE0 = v26;
  xmmword_100516DF0 = v27;
  xmmword_100516E00 = v28;
  qword_100516E10 = (__int64)ProcAddress;
  ghSpnLib = v3;
  ghNetApiLib = v7;
  ghSecur = v11;
LABEL_40:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_spn.cpp", "SNI_Spn::SpnInit", 66, v18);
  return LastError;
}

```

## disassembly

```asm
0x100456020  mov     rax, rsp
0x100456023  push    rbp
0x100456024  push    r12
0x100456026  push    r13
0x100456028  push    r14
0x10045602a  push    r15
0x10045602c  lea     rbp, [rax-228h]
0x100456033  sub     rsp, 300h
0x10045603a  mov     [rbp+220h+var_270], 0FFFFFFFFFFFFFFFEh
0x100456042  mov     [rax+8], rbx
0x100456046  mov     [rax+10h], rsi
0x10045604a  mov     [rax+18h], rdi
0x10045604e  mov     rax, cs:__security_cookie
0x100456055  xor     rax, rsp
0x100456058  mov     [rbp+220h+var_30], rax
0x10045605f  lea     r12, aSqlCommonDkSni_9; "sql\\common\\dk\\sni\\src\\sni_spn.cpp"
0x100456066  mov     [rbp+220h+var_258], r12
0x10045606a  lea     r13, aSniSpnSpninit; "SNI_Spn::SpnInit"
0x100456071  mov     [rbp+220h+var_250], r13
0x100456075  mov     [rbp+220h+var_248], 42h ; 'B'
0x10045607c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100456083  jz      short loc_10045609D
0x100456085  lea     r9, aApiSni_0; "API|SNI\n"
0x10045608c  mov     r8d, 42h ; 'B'; int
0x100456092  mov     rdx, r13; char *
0x100456095  mov     rcx, r12; char *
0x100456098  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10045609d  mov     ecx, 105h
0x1004560a2  lea     rax, aNtdsapiDll; "ntdsapi.dll"
0x1004560a9  nop     dword ptr [rax+00000000h]
0x1004560b0  xor     ebx, ebx
0x1004560b2  cmp     [rax], bl
0x1004560b4  jz      short loc_1004560D1
0x1004560b6  inc     rax
0x1004560b9  sub     rcx, 1
0x1004560bd  jnz     short loc_1004560B0
0x1004560bf  test    rcx, rcx
0x1004560c2  jnz     short loc_1004560D1
0x1004560c4  lea     ecx, [rbx+7Bh]; dwErrCode
0x1004560c7  call    cs:__imp_SetLastError
0x1004560cd  mov     edi, ebx
0x1004560cf  jmp     short loc_100456109
0x1004560d1  mov     dword ptr [rsp+320h+var_300], 105h
0x1004560d9  lea     r9, [rbp+220h+var_240]
0x1004560dd  mov     r8d, 0FFFFFFFFh
0x1004560e3  lea     rdx, aNtdsapiDll; "ntdsapi.dll"
0x1004560ea  xor     ecx, ecx
0x1004560ec  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x1004560f2  xor     r9d, r9d
0x1004560f5  xor     r8d, r8d
0x1004560f8  lea     edx, [r9+1]
0x1004560fc  lea     rcx, [rbp+220h+var_240]
0x100456100  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x100456106  mov     rdi, rax
0x100456109  mov     [rbp+220h+var_278], rdi
0x10045610d  xorps   xmm0, xmm0
0x100456110  xor     eax, eax
0x100456112  movups  xmmword ptr [rsp+320h+var_2E8+8], xmm0
0x100456117  movups  [rsp+320h+var_2D8+8], xmm0
0x10045611c  movups  [rsp+320h+var_2C8+8], xmm0
0x100456121  movups  [rsp+320h+var_2B8+8], xmm0
0x100456126  movups  [rbp+220h+var_2A0], xmm0
0x10045612a  mov     [rbp+220h+var_290], rax
0x10045612e  test    rdi, rdi
0x100456131  jz      loc_100456444
0x100456137  mov     rdx, cs:?DsFunctionNames@@3PAPEBDA; lpProcName
0x10045613e  mov     rcx, rdi; hModule
0x100456141  call    cs:__imp_GetProcAddress
0x100456147  mov     [rsp+320h+var_2E8+8], rax
0x10045614c  test    rax, rax
0x10045614f  jz      loc_100456444
0x100456155  mov     rdx, cs:lpProcName; lpProcName
0x10045615c  mov     rcx, rdi; hModule
0x10045615f  call    cs:__imp_GetProcAddress
0x100456165  mov     qword ptr [rsp+320h+var_2D8], rax
0x10045616a  test    rax, rax
0x10045616d  jz      loc_100456444
0x100456173  mov     rdx, cs:off_1004914C0; lpProcName
0x10045617a  mov     rcx, rdi; hModule
0x10045617d  call    cs:__imp_GetProcAddress
0x100456183  mov     qword ptr [rsp+320h+var_2D8+8], rax
0x100456188  test    rax, rax
0x10045618b  jz      loc_100456444
0x100456191  mov     rdx, cs:off_1004914C8; lpProcName
0x100456198  mov     rcx, rdi; hModule
0x10045619b  call    cs:__imp_GetProcAddress
0x1004561a1  mov     qword ptr [rsp+320h+var_2C8], rax
0x1004561a6  test    rax, rax
0x1004561a9  jz      loc_100456444
0x1004561af  mov     rdx, cs:off_1004914D0; lpProcName
0x1004561b6  mov     rcx, rdi; hModule
0x1004561b9  call    cs:__imp_GetProcAddress
0x1004561bf  mov     qword ptr [rsp+320h+var_2C8+8], rax
0x1004561c4  test    rax, rax
0x1004561c7  jz      loc_100456444
0x1004561cd  mov     rdx, cs:off_1004914D8; lpProcName
0x1004561d4  mov     rcx, rdi; hModule
0x1004561d7  call    cs:__imp_GetProcAddress
0x1004561dd  mov     qword ptr [rsp+320h+var_2B8], rax
0x1004561e2  test    rax, rax
0x1004561e5  jz      loc_100456444
0x1004561eb  mov     rdx, cs:off_1004914E0; lpProcName
0x1004561f2  mov     rcx, rdi; hModule
0x1004561f5  call    cs:__imp_GetProcAddress
0x1004561fb  mov     qword ptr [rsp+320h+var_2B8+8], rax
0x100456200  test    rax, rax
0x100456203  jz      loc_100456444
0x100456209  mov     ecx, 105h
0x10045620e  lea     rax, aNetapi32Dll; "netapi32.dll"
0x100456215  cmp     [rax], bl
0x100456217  jz      short loc_10045623C
0x100456219  inc     rax
0x10045621c  sub     rcx, 1
0x100456220  jnz     short loc_100456215
0x100456222  test    rcx, rcx
0x100456225  jnz     short loc_10045623C
0x100456227  mov     ecx, 7Bh ; '{'; dwErrCode
0x10045622c  call    cs:__imp_SetLastError
0x100456232  mov     [rsp+320h+var_2E8], rbx
0x100456237  jmp     loc_100456444
0x10045623c  mov     dword ptr [rsp+320h+var_300], 105h
0x100456244  lea     r9, [rbp+220h+var_240]
0x100456248  mov     r8d, 0FFFFFFFFh
0x10045624e  lea     rdx, aNetapi32Dll; "netapi32.dll"
0x100456255  xor     ecx, ecx
0x100456257  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x10045625d  xor     r9d, r9d
0x100456260  xor     r8d, r8d
0x100456263  lea     edx, [r9+1]
0x100456267  lea     rcx, [rbp+220h+var_240]
0x10045626b  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x100456271  mov     r15, rax
0x100456274  mov     [rsp+320h+var_2E8], rax
0x100456279  test    rax, rax
0x10045627c  jz      loc_100456444
0x100456282  mov     rdx, cs:off_1004914E8; lpProcName
0x100456289  mov     rcx, rax; hModule
0x10045628c  call    cs:__imp_GetProcAddress
0x100456292  mov     [rsp+320h+var_2A8], rax
0x100456297  test    rax, rax
0x10045629a  jz      loc_100456444
0x1004562a0  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x1004562a7  mov     rcx, r15; hModule
0x1004562aa  call    cs:__imp_GetProcAddress
0x1004562b0  mov     qword ptr [rbp+220h+var_2A0], rax
0x1004562b4  test    rax, rax
0x1004562b7  jz      loc_100456444
0x1004562bd  mov     ecx, 105h
0x1004562c2  lea     rax, aSecur32Dll_0; "secur32.dll"
0x1004562c9  nop     dword ptr [rax+00000000h]
0x1004562d0  cmp     [rax], bl
0x1004562d2  jz      short loc_1004562F7
0x1004562d4  inc     rax
0x1004562d7  sub     rcx, 1
0x1004562db  jnz     short loc_1004562D0
0x1004562dd  test    rcx, rcx
0x1004562e0  jnz     short loc_1004562F7
0x1004562e2  mov     ecx, 7Bh ; '{'; dwErrCode
0x1004562e7  call    cs:__imp_SetLastError
0x1004562ed  mov     [rsp+320h+var_2F0], rbx
0x1004562f2  jmp     loc_100456444
0x1004562f7  mov     dword ptr [rsp+320h+var_300], 105h
0x1004562ff  lea     r9, [rbp+220h+var_240]
0x100456303  mov     r8d, 0FFFFFFFFh
0x100456309  lea     rdx, aSecur32Dll_0; "secur32.dll"
0x100456310  xor     ecx, ecx
0x100456312  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x100456318  xor     r9d, r9d
0x10045631b  xor     r8d, r8d
0x10045631e  lea     edx, [r9+1]
0x100456322  lea     rcx, [rbp+220h+var_240]
0x100456326  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x10045632c  mov     r14, rax
0x10045632f  mov     [rsp+320h+var_2F0], rax
0x100456334  test    rax, rax
0x100456337  jz      loc_100456444
0x10045633d  mov     rdx, cs:off_1004914F0; lpProcName
0x100456344  mov     rcx, rax; hModule
0x100456347  call    cs:__imp_GetProcAddress
0x10045634d  mov     qword ptr [rbp+220h+var_2A0+8], rax
0x100456351  test    rax, rax
0x100456354  jz      loc_100456444
0x10045635a  mov     rdx, cs:off_1004914F8; lpProcName
0x100456361  mov     rcx, r14; hModule
0x100456364  call    cs:__imp_GetProcAddress
0x10045636a  mov     [rbp+220h+var_290], rax
0x10045636e  test    rax, rax
0x100456371  jz      loc_100456444
0x100456377  mov     [rbp+220h+var_280], 0A7h
0x10045637e  mov     rdx, gs:58h
0x100456387  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045638e  mov     ecx, [rax]
0x100456390  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100456397  mov     esi, [rax]
0x100456399  add     rsi, [rdx+rcx*8]
0x10045639d  mov     rax, [rsi+100h]
0x1004563a4  test    rax, rax
0x1004563a7  jnz     short loc_1004563B8
0x1004563a9  xor     ecx, ecx
0x1004563ab  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004563b1  mov     rax, [rsi+100h]
0x1004563b8  mov     rax, [rax+3E0h]
0x1004563bf  mov     rcx, [rax+38h]
0x1004563c3  mov     rdx, [rcx+8]
0x1004563c7  mov     [rbp+220h+var_268], rdx
0x1004563cb  mov     byte ptr [rsp+320h+var_2F8], 6
0x1004563d0  mov     dword ptr [rsp+320h+var_300], 0A7h
0x1004563d8  mov     r9, r12
0x1004563db  mov     ecx, 38h ; '8'
0x1004563e0  lea     r8d, [rcx-37h]
0x1004563e4  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004563ea  mov     rcx, rax
0x1004563ed  mov     [rbp+220h+var_260], rax
0x1004563f1  test    rax, rax
0x1004563f4  jz      short loc_100456426
0x1004563f6  add     rax, 8
0x1004563fa  mov     [rax+8], rax
0x1004563fe  mov     [rax], rax
0x100456401  mov     [rcx+18h], rbx
0x100456405  mov     [rcx+20h], ebx
0x100456408  mov     dword ptr [rcx+24h], 1
0x10045640f  mov     [rcx+28h], rbx
0x100456413  lea     rax, ??_7?$EventAutoInternal@USuspendQueueSLock@@@@6B@; const EventAutoInternal<SuspendQueueSLock>::`vftable'
0x10045641a  mov     [rcx], rax
0x10045641d  mov     dword ptr [rcx+30h], 20000229h
0x100456424  jmp     short loc_100456429
0x100456426  mov     rcx, rbx; this
0x100456429  mov     cs:?m_peventSpnRegistrationCompleted@SNI_Spn@@0PEAVSNIAutoEvent@@EA, rcx; SNIAutoEvent * SNI_Spn::m_peventSpnRegistrationCompleted
0x100456430  test    rcx, rcx
0x100456433  jnz     loc_1004564D6
0x100456439  mov     ecx, 0Eh; dwErrCode
0x10045643e  call    cs:__imp_SetLastError
0x100456444  call    cs:__imp_GetLastError
0x10045644a  mov     ebx, eax
0x10045644c  lea     r9, [rsp+320h+var_2E8+8]; struct _DsFunctionTable *
0x100456451  lea     r8, [rsp+320h+var_2F0]; HINSTANCE *
0x100456456  lea     rdx, [rsp+320h+var_2E8]; HINSTANCE *
0x10045645b  lea     rcx, [rbp+220h+var_278]; HINSTANCE *
0x10045645f  call    ?DoSpnTerminate@SNI_Spn@@CAXPEAPEAUHINSTANCE__@@00PEAU_DsFunctionTable@@@Z; SNI_Spn::DoSpnTerminate(HINSTANCE__ * *,HINSTANCE__ * *,HINSTANCE__ * *,_DsFunctionTable *)
0x100456464  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045646b  jz      short loc_10045648A
0x10045646d  mov     dword ptr [rsp+320h+var_300], ebx
0x100456471  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100456478  mov     r8d, 0C7h; int
0x10045647e  mov     rdx, r13; char *
0x100456481  mov     rcx, r12; char *
0x100456484  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100456489  nop
0x10045648a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100456491  jz      short loc_1004564A4
0x100456493  mov     r8d, 42h ; 'B'; int
0x100456499  mov     rdx, r13; char *
0x10045649c  mov     rcx, r12; char *
0x10045649f  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004564a4  mov     eax, ebx
0x1004564a6  mov     rcx, [rbp+220h+var_30]
0x1004564ad  xor     rcx, rsp; StackCookie
0x1004564b0  call    __security_check_cookie
0x1004564b5  lea     r11, [rsp+320h+var_20]
0x1004564bd  mov     rbx, [r11+30h]
0x1004564c1  mov     rsi, [r11+38h]
0x1004564c5  mov     rdi, [r11+40h]
0x1004564c9  mov     rsp, r11
0x1004564cc  pop     r15
0x1004564ce  pop     r14
0x1004564d0  pop     r13
0x1004564d2  pop     r12
0x1004564d4  pop     rbp
0x1004564d5  retn
0x1004564d6  call    ?FInit@SNIAutoEvent@@QEAAKXZ; SNIAutoEvent::FInit(void)
0x1004564db  nop
0x1004564dc  test    eax, eax
0x1004564de  jz      short loc_1004564E7
0x1004564e0  mov     ecx, eax
0x1004564e2  jmp     loc_10045643E
0x1004564e7  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004564ee  jz      short loc_10045650D
0x1004564f0  mov     [rsp+320h+var_300], rbx
0x1004564f5  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004564fc  mov     r8d, 0B7h; int
0x100456502  mov     rdx, r13; char *
0x100456505  mov     rcx, r12; char *
0x100456508  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10045650d  movaps  xmm0, xmmword ptr [rsp+320h+var_2E8+8]
0x100456512  movaps  cs:?gDsFunc@@3U_DsFunctionTable@@A, xmm0; _DsFunctionTable gDsFunc
0x100456519  movaps  xmm1, [rsp+320h+var_2D8+8]
0x10045651e  movaps  cs:xmmword_100516DD0, xmm1
0x100456525  movaps  xmm0, [rsp+320h+var_2C8+8]
0x10045652a  movaps  cs:xmmword_100516DE0, xmm0
0x100456531  movaps  xmm1, [rsp+320h+var_2B8+8]
0x100456536  movaps  cs:xmmword_100516DF0, xmm1
0x10045653d  movaps  xmm0, [rbp+220h+var_2A0]
0x100456541  movaps  cs:xmmword_100516E00, xmm0
0x100456548  movsd   xmm1, [rbp+220h+var_290]
0x10045654d  movsd   cs:qword_100516E10, xmm1
0x100456555  mov     cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * ghSpnLib
0x10045655c  mov     cs:?ghNetApiLib@@3PEAUHINSTANCE__@@EA, r15; HINSTANCE__ * ghNetApiLib
0x100456563  mov     cs:?ghSecur@@3PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * ghSecur
0x10045656a  jmp     loc_10045648A
```
