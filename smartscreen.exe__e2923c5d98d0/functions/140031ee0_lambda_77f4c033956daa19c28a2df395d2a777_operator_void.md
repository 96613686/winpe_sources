# _lambda_77f4c033956daa19c28a2df395d2a777_::operator()(void)

- ea: `0x140031ee0`
- end: `0x140032239`
- name: `??R_lambda_77f4c033956daa19c28a2df395d2a777_@@QEBA?AV?$optional@_N@std@@XZ`
- size: `857`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x14001c378`

## callees

- `0x140004190`
- `0x140006c34`
- `0x14000f414`
- `0x1400110c0`
- `0x14001f250`
- `0x140025aa0`
- `0x14002f250`
- `0x140031ee0`
- `0x1400360e0`
- `0x140068010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140031f3d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140031f3d`
- `ntdll!RtlFreeHeap` at `0x1400321b1`
- `ntdll!RtlFreeHeap` at `0x1400321b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140031fa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140031fc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140031fea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003200c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140031fa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140031fc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140031fea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003200c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140031f75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140031f75`

## string_xrefs

- `0x140031f6e`: `apphelp.dll`

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
0x140031ee0  mov     [rsp-8+arg_10], rbx
0x140031ee5  push    rbp
0x140031ee6  push    rsi
0x140031ee7  push    rdi
0x140031ee8  push    r12
0x140031eea  push    r13
0x140031eec  push    r14
0x140031eee  push    r15
0x140031ef0  lea     rbp, [rsp-20h]
0x140031ef5  sub     rsp, 120h
0x140031efc  mov     rax, cs:__security_cookie
0x140031f03  xor     rax, rsp
0x140031f06  mov     [rbp+50h+var_38], rax
0x140031f0a  mov     rdi, rdx
0x140031f0d  mov     rsi, rcx
0x140031f10  lea     rdx, [rbp+50h+var_A0]
0x140031f14  mov     rcx, [rcx]
0x140031f17  call    ?extension@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::extension(void)
0x140031f1c  nop
0x140031f1d  lea     rdx, [rbp+50h+var_C0]
0x140031f21  mov     rcx, rax
0x140031f24  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x140031f29  cmp     qword ptr [rax+18h], 7
0x140031f2e  jbe     short loc_140031F33
0x140031f30  mov     rax, [rax]
0x140031f33  lea     rdx, aExe; ".exe"
0x140031f3a  mov     rcx, rax; String1
0x140031f3d  call    cs:__imp__wcsicmp
0x140031f43  mov     ebx, eax
0x140031f45  lea     rcx, [rbp+50h+var_C0]; this
0x140031f49  call    ??1path@@QEAA@XZ; path::~path(void)
0x140031f4e  nop
0x140031f4f  lea     rcx, [rbp+50h+var_A0]; this
0x140031f53  call    ??1path@@QEAA@XZ; path::~path(void)
0x140031f58  xor     r13d, r13d
0x140031f5b  test    ebx, ebx
0x140031f5d  jnz     short loc_140031F69
0x140031f5f  mov     word ptr [rdi], 100h
0x140031f64  jmp     loc_1400321C7
0x140031f69  xor     r8d, r8d; dwFlags
0x140031f6c  xor     edx, edx; hFile
0x140031f6e  lea     rcx, LibFileName; "apphelp.dll"
0x140031f75  call    cs:__imp_LoadLibraryExW
0x140031f7b  mov     rdx, rax
0x140031f7e  lea     rcx, [rbp+50h+var_D0]
0x140031f82  call    ??0?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@PEAUHINSTANCE__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(HINSTANCE__ *)
0x140031f87  nop
0x140031f88  mov     rcx, [rbp+50h+var_D0]
0x140031f8c  test    rcx, rcx
0x140031f8f  jz      loc_1400321BA
0x140031f95  mov     rcx, [rcx]; hModule
0x140031f98  test    rcx, rcx
0x140031f9b  jz      loc_1400321BA
0x140031fa1  lea     rdx, aApphelpcheckru; "ApphelpCheckRunAppEx"
0x140031fa8  call    cs:__imp_GetProcAddress
0x140031fae  mov     r12, rax
0x140031fb1  mov     rcx, [rbp+50h+var_D0]
0x140031fb5  test    rcx, rcx
0x140031fb8  jz      short loc_140031FBF
0x140031fba  mov     rcx, [rcx]
0x140031fbd  jmp     short loc_140031FC2
0x140031fbf  mov     rcx, r13; hModule
0x140031fc2  lea     rdx, aSdbinitdatabas; "SdbInitDatabaseEx"
0x140031fc9  call    cs:__imp_GetProcAddress
0x140031fcf  mov     r15, rax
0x140031fd2  mov     rcx, [rbp+50h+var_D0]
0x140031fd6  test    rcx, rcx
0x140031fd9  jz      short loc_140031FE0
0x140031fdb  mov     rcx, [rcx]
0x140031fde  jmp     short loc_140031FE3
0x140031fe0  mov     rcx, r13; hModule
0x140031fe3  lea     rdx, aSdbreleasedata; "SdbReleaseDatabase"
0x140031fea  call    cs:__imp_GetProcAddress
0x140031ff0  mov     [rbp+50h+var_58], rax
0x140031ff4  mov     rcx, [rbp+50h+var_D0]
0x140031ff8  test    rcx, rcx
0x140031ffb  jz      short loc_140032002
0x140031ffd  mov     rcx, [rcx]
0x140032000  jmp     short loc_140032005
0x140032002  mov     rcx, r13; hModule
0x140032005  lea     rdx, aSdbshowapphelp; "SdbShowApphelpFromQuery"
0x14003200c  call    cs:__imp_GetProcAddress
0x140032012  mov     r14, rax
0x140032015  test    r12, r12
0x140032018  jz      loc_1400321BA
0x14003201e  test    r15, r15
0x140032021  jz      loc_1400321BA
0x140032027  cmp     [rbp+50h+var_58], r13
0x14003202b  jz      loc_1400321BA
0x140032031  test    rax, rax
0x140032034  jz      loc_1400321BA
0x14003203a  mov     [rbp+50h+var_40], r13d
0x14003203e  mov     [rbp+50h+P], r13
0x140032042  mov     [rbp+50h+var_44], r13d
0x140032046  mov     rax, [rsi+8]
0x14003204a  cmp     [rax+2], r13b
0x14003204e  jz      loc_140032206
0x140032054  movzx   r13d, word ptr [rax]
0x140032058  lea     rdx, [rbp+50h+var_C0]
0x14003205c  mov     rcx, [rsi]
0x14003205f  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x140032064  nop
0x140032065  cmp     qword ptr [rax+18h], 7
0x14003206a  jbe     short loc_14003206F
0x14003206c  mov     rax, [rax]
0x14003206f  mov     rbx, [rbp+58h]
0x140032073  xor     ecx, ecx
0x140032075  mov     [rsp+150h+var_E0], rcx
0x14003207a  mov     [rsp+150h+var_E8], rcx
0x14003207f  mov     [rsp+150h+var_F0], rcx
0x140032084  mov     [rsp+150h+var_F8], rcx
0x140032089  mov     [rsp+150h+var_100], rcx
0x14003208e  lea     rcx, [rbp+50h+var_44]
0x140032092  mov     [rsp+150h+var_108], rcx
0x140032097  lea     rcx, [rbp+50h+P]
0x14003209b  mov     [rsp+150h+var_110], rcx
0x1400320a0  lea     rcx, [rbp+50h+var_40]
0x1400320a4  mov     [rsp+150h+var_118], rcx
0x1400320a9  mov     [rsp+150h+var_120], r13w
0x1400320af  xor     r13d, r13d
0x1400320b2  mov     [rsp+150h+var_128], r13
0x1400320b7  mov     [rsp+150h+var_130], r13
0x1400320bc  mov     r9, rax
0x1400320bf  xor     r8d, r8d
0x1400320c2  xor     edx, edx
0x1400320c4  xor     ecx, ecx
0x1400320c6  mov     rax, r12
0x1400320c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400320ce  test    eax, eax
0x1400320d0  jz      loc_14003220C
0x1400320d6  lea     rcx, [rbp+50h+var_C0]; this
0x1400320da  call    ??1path@@QEAA@XZ; path::~path(void)
0x1400320df  lea     rax, [rbp+50h+P]
0x1400320e3  mov     [rbp+50h+var_A0], rax
0x1400320e7  mov     [rbp+50h+var_98], 1
0x1400320eb  mov     r8, [rsi+8]
0x1400320ef  cmp     [r8+2], r13b
0x1400320f3  jz      loc_140032221
0x1400320f9  movzx   r8d, word ptr [r8]
0x1400320fd  xor     edx, edx
0x1400320ff  xor     ecx, ecx
0x140032101  mov     rax, r15
0x140032104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032109  mov     rbx, rax
0x14003210c  mov     [rbp+50h+var_50], rax
0x140032110  mov     rcx, [rbp+58h]; this
0x140032114  test    rax, rax
0x140032117  jz      loc_140032227
0x14003211d  lea     rax, [rbp+50h+var_58]
0x140032121  mov     [rbp+50h+var_C0], rax
0x140032125  lea     rax, [rbp+50h+var_50]
0x140032129  mov     [rbp+50h+var_B8], rax
0x14003212d  mov     [rbp+50h+var_B0], 1
0x140032131  mov     [rbp+50h+var_48], r13d
0x140032135  mov     r15, [rbp+50h+P]
0x140032139  lea     rdx, [rbp+50h+var_80]
0x14003213d  mov     rcx, [rsi]
0x140032140  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x140032145  nop
0x140032146  cmp     qword ptr [rax+18h], 7
0x14003214b  jbe     short loc_140032150
0x14003214d  mov     rax, [rax]
0x140032150  mov     rsi, [rbp+58h]
0x140032154  lea     rcx, [rbp+50h+var_48]
0x140032158  mov     [rsp+150h+var_130], rcx
0x14003215d  xor     r9d, r9d
0x140032160  mov     r8, r15
0x140032163  mov     rdx, rbx
0x140032166  mov     rcx, rax
0x140032169  mov     rax, r14
0x14003216c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032171  test    eax, eax
0x140032173  jz      short loc_1400321F1
0x140032175  lea     rcx, [rbp+50h+var_80]; this
0x140032179  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003217e  cmp     [rbp+50h+var_48], r13d
0x140032182  setnz   al
0x140032185  mov     [rdi], al
0x140032187  mov     byte ptr [rdi+1], 1
0x14003218b  mov     rcx, [rbp+50h+var_50]
0x14003218f  mov     rax, [rbp+50h+var_58]
0x140032193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032198  nop
0x140032199  mov     r8, [rbp+50h+P]; P
0x14003219d  test    r8, r8
0x1400321a0  jz      short loc_1400321B8
0x1400321a2  mov     rcx, gs:60h
0x1400321ab  xor     edx, edx; Flags
0x1400321ad  mov     rcx, [rcx+30h]; HeapHandle
0x1400321b1  call    cs:__imp_RtlFreeHeap
0x1400321b7  nop
0x1400321b8  jmp     short loc_1400321BE
0x1400321ba  mov     [rdi+1], r13b
0x1400321be  lea     rcx, [rbp+50h+var_D0]
0x1400321c2  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1400321c7  mov     rax, rdi
0x1400321ca  mov     rcx, [rbp+50h+var_38]
0x1400321ce  xor     rcx, rsp; StackCookie
0x1400321d1  call    __security_check_cookie
0x1400321d6  mov     rbx, [rsp+150h+arg_10]
0x1400321de  add     rsp, 120h
0x1400321e5  pop     r15
0x1400321e7  pop     r14
0x1400321e9  pop     r13
0x1400321eb  pop     r12
0x1400321ed  pop     rdi
0x1400321ee  pop     rsi
0x1400321ef  pop     rbp
0x1400321f0  retn
0x1400321f1  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400321f8  mov     edx, 142h; void *
0x1400321fd  mov     rcx, rsi; this
0x140032200  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140032206  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x14003220c  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140032213  mov     edx, 139h; void *
0x140032218  mov     rcx, rbx; this
0x14003221b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140032221  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x140032227  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14003222e  mov     edx, 13Eh; void *
0x140032233  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
