# _lambda_77f4c033956daa19c28a2df395d2a777_::operator()(void)

- ea: `0x14003330c`
- end: `0x140033694`
- name: `??R_lambda_77f4c033956daa19c28a2df395d2a777_@@QEBA?AV?$optional@_N@std@@XZ`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x14001d2d4`

## callees

- `0x140004370`
- `0x140006fd8`
- `0x14000fd00`
- `0x140011a0c`
- `0x140020378`
- `0x140026c20`
- `0x140030510`
- `0x14003330c`
- `0x1400375f0`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140033369`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140033369`
- `ntdll!RtlFreeHeap` at `0x140033605`
- `ntdll!RtlFreeHeap` at `0x140033605`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400333e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140033407`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003342e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140033456`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400333e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140033407`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003342e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140033456`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400333a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400333a7`

## string_xrefs

- `0x1400333a0`: `apphelp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool *__fastcall _lambda_77f4c033956daa19c28a2df395d2a777_::operator()(_QWORD *a1, bool *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  int v6; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // r12
  HMODULE v9; // rcx
  FARPROC v10; // r15
  HMODULE v11; // rcx
  HMODULE v12; // rcx
  FARPROC v13; // rax
  unsigned int (__fastcall *v14)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // r14
  __int16 *v15; // rax
  __int16 v16; // r13
  _QWORD *v17; // rax
  const char *v18; // r9
  unsigned __int16 *v19; // r8
  __int64 v20; // rbx
  const char *v21; // r9
  PVOID v22; // r15
  _QWORD *v23; // rax
  const char *v24; // r9
  _QWORD v26[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v27[2]; // [rsp+90h] [rbp-70h] BYREF
  char v28; // [rsp+A0h] [rbp-60h]
  PVOID *p_P; // [rsp+B0h] [rbp-50h] BYREF
  char v30; // [rsp+B8h] [rbp-48h]
  _BYTE v31[32]; // [rsp+D0h] [rbp-30h] BYREF
  PVOID P; // [rsp+F0h] [rbp-10h] BYREF
  FARPROC v33; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v34; // [rsp+100h] [rbp+0h] BYREF
  int v35; // [rsp+108h] [rbp+8h] BYREF
  int v36; // [rsp+10Ch] [rbp+Ch] BYREF
  int v37; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v4 = std::filesystem::path::extension(*a1, &p_P);
  v5 = std::filesystem::path::wstring(v4, v27);
  if ( *(_QWORD *)(v5 + 24) > 7u )
    v5 = *(_QWORD *)v5;
  v6 = _wcsicmp((const wchar_t *)v5, L".exe");
  path::~path((path *)v27);
  path::~path((path *)&p_P);
  if ( v6 )
  {
    Library = LoadLibraryExW(L"apphelp.dll", 0, 0);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(
      v26,
      Library);
    if ( !v26[0] || !*(_QWORD *)v26[0] )
      goto LABEL_32;
    ProcAddress = GetProcAddress(*(HMODULE *)v26[0], "ApphelpCheckRunAppEx");
    v9 = v26[0] ? *(HMODULE *)v26[0] : 0LL;
    v10 = GetProcAddress(v9, "SdbInitDatabaseEx");
    v11 = v26[0] ? *(HMODULE *)v26[0] : 0LL;
    v33 = GetProcAddress(v11, "SdbReleaseDatabase");
    v12 = v26[0] ? *(HMODULE *)v26[0] : 0LL;
    v13 = GetProcAddress(v12, "SdbShowApphelpFromQuery");
    v14 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v13;
    if ( ProcAddress && v10 && v33 && v13 )
    {
      v37 = 0;
      P = 0;
      v36 = 0;
      v15 = (__int16 *)a1[1];
      if ( !*((_BYTE *)v15 + 2) )
        std::_Throw_bad_optional_access();
      v16 = *v15;
      v17 = (_QWORD *)std::filesystem::path::wstring(*a1, v27);
      if ( v17[3] > 7u )
        v17 = (_QWORD *)*v17;
      if ( !((unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD *, _QWORD, _QWORD, __int16, int *, PVOID *, int *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
              0,
              0,
              0,
              v17,
              0,
              0,
              v16,
              &v37,
              &P,
              &v36,
              0,
              0,
              0,
              0,
              0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
          v18);
      path::~path((path *)v27);
      p_P = &P;
      v30 = 1;
      v19 = (unsigned __int16 *)a1[1];
      if ( !*((_BYTE *)v19 + 2) )
        std::_Throw_bad_optional_access();
      v20 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v10)(0, 0, *v19);
      v34 = v20;
      if ( !v20 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x13E,
          (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
          v21);
      v27[0] = &v33;
      v27[1] = &v34;
      v28 = 1;
      v35 = 0;
      v22 = P;
      v23 = (_QWORD *)std::filesystem::path::wstring(*a1, v31);
      if ( v23[3] > 7u )
        v23 = (_QWORD *)*v23;
      if ( !v14(v23, v20, v22, 0, &v35) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x142,
          (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
          v24);
      path::~path((path *)v31);
      *a2 = v35 != 0;
      a2[1] = 1;
      ((void (__fastcall *)(__int64))v33)(v34);
      if ( P )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    }
    else
    {
LABEL_32:
      a2[1] = 0;
    }
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v26);
  }
  else
  {
    *(_WORD *)a2 = 256;
  }
  return a2;
}

```

## disassembly

```asm
0x14003330c  mov     [rsp-8+arg_10], rbx
0x140033311  push    rbp
0x140033312  push    rsi
0x140033313  push    rdi
0x140033314  push    r12
0x140033316  push    r13
0x140033318  push    r14
0x14003331a  push    r15
0x14003331c  lea     rbp, [rsp-20h]
0x140033321  sub     rsp, 120h
0x140033328  mov     rax, cs:__security_cookie
0x14003332f  xor     rax, rsp
0x140033332  mov     [rbp+50h+var_38], rax
0x140033336  mov     rdi, rdx
0x140033339  mov     rsi, rcx
0x14003333c  lea     rdx, [rbp+50h+var_A0]
0x140033340  mov     rcx, [rcx]
0x140033343  call    ?extension@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::extension(void)
0x140033348  nop
0x140033349  lea     rdx, [rbp+50h+var_C0]
0x14003334d  mov     rcx, rax
0x140033350  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x140033355  cmp     qword ptr [rax+18h], 7
0x14003335a  jbe     short loc_14003335F
0x14003335c  mov     rax, [rax]
0x14003335f  lea     rdx, aExe; ".exe"
0x140033366  mov     rcx, rax; String1
0x140033369  call    cs:__imp__wcsicmp
0x140033370  nop     dword ptr [rax+rax+00h]
0x140033375  mov     ebx, eax
0x140033377  lea     rcx, [rbp+50h+var_C0]; this
0x14003337b  call    ??1path@@QEAA@XZ; path::~path(void)
0x140033380  nop
0x140033381  lea     rcx, [rbp+50h+var_A0]; this
0x140033385  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003338a  xor     r13d, r13d
0x14003338d  test    ebx, ebx
0x14003338f  jnz     short loc_14003339B
0x140033391  mov     word ptr [rdi], 100h
0x140033396  jmp     loc_140033621
0x14003339b  xor     r8d, r8d; dwFlags
0x14003339e  xor     edx, edx; hFile
0x1400333a0  lea     rcx, LibFileName; "apphelp.dll"
0x1400333a7  call    cs:__imp_LoadLibraryExW
0x1400333ae  nop     dword ptr [rax+rax+00h]
0x1400333b3  mov     rdx, rax
0x1400333b6  lea     rcx, [rbp+50h+var_D0]
0x1400333ba  call    ??0?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@PEAUHINSTANCE__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(HINSTANCE__ *)
0x1400333bf  nop
0x1400333c0  mov     rcx, [rbp+50h+var_D0]
0x1400333c4  test    rcx, rcx
0x1400333c7  jz      loc_140033614
0x1400333cd  mov     rcx, [rcx]; hModule
0x1400333d0  test    rcx, rcx
0x1400333d3  jz      loc_140033614
0x1400333d9  lea     rdx, aApphelpcheckru; "ApphelpCheckRunAppEx"
0x1400333e0  call    cs:__imp_GetProcAddress
0x1400333e7  nop     dword ptr [rax+rax+00h]
0x1400333ec  mov     r12, rax
0x1400333ef  mov     rcx, [rbp+50h+var_D0]
0x1400333f3  test    rcx, rcx
0x1400333f6  jz      short loc_1400333FD
0x1400333f8  mov     rcx, [rcx]
0x1400333fb  jmp     short loc_140033400
0x1400333fd  mov     rcx, r13; hModule
0x140033400  lea     rdx, aSdbinitdatabas; "SdbInitDatabaseEx"
0x140033407  call    cs:__imp_GetProcAddress
0x14003340e  nop     dword ptr [rax+rax+00h]
0x140033413  mov     r15, rax
0x140033416  mov     rcx, [rbp+50h+var_D0]
0x14003341a  test    rcx, rcx
0x14003341d  jz      short loc_140033424
0x14003341f  mov     rcx, [rcx]
0x140033422  jmp     short loc_140033427
0x140033424  mov     rcx, r13; hModule
0x140033427  lea     rdx, aSdbreleasedata; "SdbReleaseDatabase"
0x14003342e  call    cs:__imp_GetProcAddress
0x140033435  nop     dword ptr [rax+rax+00h]
0x14003343a  mov     [rbp+50h+var_58], rax
0x14003343e  mov     rcx, [rbp+50h+var_D0]
0x140033442  test    rcx, rcx
0x140033445  jz      short loc_14003344C
0x140033447  mov     rcx, [rcx]
0x14003344a  jmp     short loc_14003344F
0x14003344c  mov     rcx, r13; hModule
0x14003344f  lea     rdx, aSdbshowapphelp; "SdbShowApphelpFromQuery"
0x140033456  call    cs:__imp_GetProcAddress
0x14003345d  nop     dword ptr [rax+rax+00h]
0x140033462  mov     r14, rax
0x140033465  test    r12, r12
0x140033468  jz      loc_140033614
0x14003346e  test    r15, r15
0x140033471  jz      loc_140033614
0x140033477  cmp     [rbp+50h+var_58], r13
0x14003347b  jz      loc_140033614
0x140033481  test    rax, rax
0x140033484  jz      loc_140033614
0x14003348a  mov     [rbp+50h+var_40], r13d
0x14003348e  mov     [rbp+50h+P], r13
0x140033492  mov     [rbp+50h+var_44], r13d
0x140033496  mov     rax, [rsi+8]
0x14003349a  cmp     [rax+2], r13b
0x14003349e  jz      loc_140033661
0x1400334a4  movzx   r13d, word ptr [rax]
0x1400334a8  lea     rdx, [rbp+50h+var_C0]
0x1400334ac  mov     rcx, [rsi]
0x1400334af  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x1400334b4  nop
0x1400334b5  cmp     qword ptr [rax+18h], 7
0x1400334ba  jbe     short loc_1400334BF
0x1400334bc  mov     rax, [rax]
0x1400334bf  mov     rbx, [rbp+58h]
0x1400334c3  xor     ecx, ecx
0x1400334c5  mov     [rsp+150h+var_E0], rcx
0x1400334ca  mov     [rsp+150h+var_E8], rcx
0x1400334cf  mov     [rsp+150h+var_F0], rcx
0x1400334d4  mov     [rsp+150h+var_F8], rcx
0x1400334d9  mov     [rsp+150h+var_100], rcx
0x1400334de  lea     rcx, [rbp+50h+var_44]
0x1400334e2  mov     [rsp+150h+var_108], rcx
0x1400334e7  lea     rcx, [rbp+50h+P]
0x1400334eb  mov     [rsp+150h+var_110], rcx
0x1400334f0  lea     rcx, [rbp+50h+var_40]
0x1400334f4  mov     [rsp+150h+var_118], rcx
0x1400334f9  mov     [rsp+150h+var_120], r13w
0x1400334ff  xor     r13d, r13d
0x140033502  mov     [rsp+150h+var_128], r13
0x140033507  mov     [rsp+150h+var_130], r13
0x14003350c  mov     r9, rax
0x14003350f  xor     r8d, r8d
0x140033512  xor     edx, edx
0x140033514  xor     ecx, ecx
0x140033516  mov     rax, r12
0x140033519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003351e  test    eax, eax
0x140033520  jz      loc_140033667
0x140033526  lea     rcx, [rbp+50h+var_C0]; this
0x14003352a  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003352f  lea     rax, [rbp+50h+P]
0x140033533  mov     [rbp+50h+var_A0], rax
0x140033537  mov     [rbp+50h+var_98], 1
0x14003353b  mov     r8, [rsi+8]
0x14003353f  cmp     [r8+2], r13b
0x140033543  jz      loc_14003367C
0x140033549  movzx   r8d, word ptr [r8]
0x14003354d  xor     edx, edx
0x14003354f  xor     ecx, ecx
0x140033551  mov     rax, r15
0x140033554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033559  mov     rbx, rax
0x14003355c  mov     [rbp+50h+var_50], rax
0x140033560  mov     rcx, [rbp+58h]; this
0x140033564  test    rax, rax
0x140033567  jz      loc_140033682
0x14003356d  lea     rax, [rbp+50h+var_58]
0x140033571  mov     [rbp+50h+var_C0], rax
0x140033575  lea     rax, [rbp+50h+var_50]
0x140033579  mov     [rbp+50h+var_B8], rax
0x14003357d  mov     [rbp+50h+var_B0], 1
0x140033581  mov     [rbp+50h+var_48], r13d
0x140033585  mov     r15, [rbp+50h+P]
0x140033589  lea     rdx, [rbp+50h+var_80]
0x14003358d  mov     rcx, [rsi]
0x140033590  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x140033595  nop
0x140033596  cmp     qword ptr [rax+18h], 7
0x14003359b  jbe     short loc_1400335A0
0x14003359d  mov     rax, [rax]
0x1400335a0  mov     rsi, [rbp+58h]
0x1400335a4  lea     rcx, [rbp+50h+var_48]
0x1400335a8  mov     [rsp+150h+var_130], rcx
0x1400335ad  xor     r9d, r9d
0x1400335b0  mov     r8, r15
0x1400335b3  mov     rdx, rbx
0x1400335b6  mov     rcx, rax
0x1400335b9  mov     rax, r14
0x1400335bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400335c1  test    eax, eax
0x1400335c3  jz      loc_14003364C
0x1400335c9  lea     rcx, [rbp+50h+var_80]; this
0x1400335cd  call    ??1path@@QEAA@XZ; path::~path(void)
0x1400335d2  cmp     [rbp+50h+var_48], r13d
0x1400335d6  setnz   al
0x1400335d9  mov     [rdi], al
0x1400335db  mov     byte ptr [rdi+1], 1
0x1400335df  mov     rcx, [rbp+50h+var_50]
0x1400335e3  mov     rax, [rbp+50h+var_58]
0x1400335e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400335ec  nop
0x1400335ed  mov     r8, [rbp+50h+P]; P
0x1400335f1  test    r8, r8
0x1400335f4  jz      short loc_140033612
0x1400335f6  mov     rcx, gs:60h
0x1400335ff  xor     edx, edx; Flags
0x140033601  mov     rcx, [rcx+30h]; HeapHandle
0x140033605  call    cs:__imp_RtlFreeHeap
0x14003360c  nop     dword ptr [rax+rax+00h]
0x140033611  nop
0x140033612  jmp     short loc_140033618
0x140033614  mov     [rdi+1], r13b
0x140033618  lea     rcx, [rbp+50h+var_D0]
0x14003361c  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x140033621  mov     rax, rdi
0x140033624  mov     rcx, [rbp+50h+var_38]
0x140033628  xor     rcx, rsp; StackCookie
0x14003362b  call    __security_check_cookie
0x140033630  mov     rbx, [rsp+150h+arg_10]
0x140033638  add     rsp, 120h
0x14003363f  pop     r15
0x140033641  pop     r14
0x140033643  pop     r13
0x140033645  pop     r12
0x140033647  pop     rdi
0x140033648  pop     rsi
0x140033649  pop     rbp
0x14003364a  retn
0x14003364c  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140033653  mov     edx, 142h; void *
0x140033658  mov     rcx, rsi; this
0x14003365b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140033661  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x140033667  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003366e  mov     edx, 139h; void *
0x140033673  mov     rcx, rbx; this
0x140033676  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14003367c  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x140033682  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140033689  mov     edx, 13Eh; void *
0x14003368e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
