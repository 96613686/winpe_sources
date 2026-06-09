# TaskRescheduler::AdjustNextRunTime(ITrigger *,ulong)

- ea: `0x18005242c`
- end: `0x180052567`
- name: `?AdjustNextRunTime@TaskRescheduler@@CAXPEAUITrigger@@K@Z`
- size: `315`
- prototype: `void __fastcall(struct ITrigger *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180052570`

## callees

- `0x1800101fc`
- `0x18003d550`
- `0x180040504`
- `0x18004ee5c`
- `0x1800523f0`
- `0x180052420`
- `0x18005242c`
- `0x180052b98`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800524a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800524a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005246c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005246c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005244f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005244f`

## string_xrefs

- `0x180052484`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800524ed`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x18005252b`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x180052448`: `dmiso8601utils.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TaskRescheduler::AdjustNextRunTime(struct ITrigger *a1, unsigned int a2)
{
  __int64 v2; // rsi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  __int64 v6; // r8
  int v7; // eax
  int v8; // eax
  __int64 v9; // [rsp+20h] [rbp-10h] BYREF
  HMODULE v10; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  v2 = a2;
  Library = LoadLibraryExW(L"dmiso8601utils.dll", 0, 0x800u);
  v10 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "FileTimeToISO8601String");
    if ( !ProcAddress )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
        (const char *)0x8007007FLL,
        v9);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    SystemTimeAsFileTime = wil::FileTime::Add(
                             (wil::FileTime *)&SystemTimeAsFileTime,
                             (const struct _FILETIME *)(600000000 * v2),
                             v6);
    v13 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v13,
      0);
    v7 = ((__int64 (__fastcall *)(struct _FILETIME *, __int64, __int64 *))ProcAddress)(&SystemTimeAsFileTime, 2, &v13);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
        (const char *)(unsigned int)v7,
        v9);
    wil::make_bstr(&v9, v13);
    v8 = ((__int64 (__fastcall *)(struct ITrigger *, __int64))a1->lpVtbl->put_StartBoundary)(a1, v9);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
        (const char *)(unsigned int)v8,
        v9);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x18005242c  mov     [rsp-18h+arg_0], rbx
0x180052431  push    rbp
0x180052432  push    rsi
0x180052433  push    rdi
0x180052434  mov     rbp, rsp
0x180052437  sub     rsp, 30h
0x18005243b  mov     esi, edx
0x18005243d  mov     rdi, rcx
0x180052440  xor     edx, edx; hFile
0x180052442  mov     r8d, 800h; dwFlags
0x180052448  lea     rcx, LibFileName; "dmiso8601utils.dll"
0x18005244f  call    cs:__imp_LoadLibraryExW
0x180052455  mov     [rbp+var_8], rax
0x180052459  test    rax, rax
0x18005245c  jz      loc_180052551
0x180052462  lea     rdx, aFiletimetoiso8; "FileTimeToISO8601String"
0x180052469  mov     rcx, rax; hModule
0x18005246c  call    cs:__imp_GetProcAddress
0x180052472  mov     rbx, rax
0x180052475  mov     rcx, [rbp+18h]; this
0x180052479  test    rax, rax
0x18005247c  jnz     short loc_180052494
0x18005247e  mov     r9d, 8007007Fh; char *
0x180052484  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x18005248b  lea     edx, [rax+5Eh]; void *
0x18005248e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052494  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18005249c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800524a0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800524a6  imul    rdx, rsi, 23C34600h; struct _FILETIME *
0x1800524ad  lea     rcx, [rbp+SystemTimeAsFileTime]; this
0x1800524b1  call    ?Add@FileTime@wil@@YA?AU_FILETIME@@AEBU3@_J@Z; wil::FileTime::Add(_FILETIME const &,__int64)
0x1800524b6  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800524ba  mov     [rbp+arg_18], 0
0x1800524c2  xor     edx, edx
0x1800524c4  lea     rcx, [rbp+arg_18]
0x1800524c8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800524cd  lea     r8, [rbp+arg_18]
0x1800524d1  mov     edx, 2
0x1800524d6  lea     rcx, [rbp+SystemTimeAsFileTime]
0x1800524da  mov     rax, rbx
0x1800524dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524e2  mov     rcx, [rbp+18h]; this
0x1800524e6  test    eax, eax
0x1800524e8  jns     short loc_1800524FF
0x1800524ea  mov     r9d, eax; char *
0x1800524ed  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800524f4  mov     edx, 67h ; 'g'; void *
0x1800524f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800524ff  mov     rdx, [rbp+arg_18]
0x180052503  lea     rcx, [rbp+var_10]
0x180052507  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005250c  nop
0x18005250d  mov     rax, [rdi]
0x180052510  mov     rdx, [rbp+var_10]
0x180052514  mov     rcx, rdi
0x180052517  mov     rax, [rax+78h]
0x18005251b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052520  test    eax, eax
0x180052522  jns     short loc_18005253D
0x180052524  mov     rcx, [rbp+18h]; this
0x180052528  mov     r9d, eax; char *
0x18005252b  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x180052532  mov     edx, 6Ah ; 'j'; void *
0x180052537  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005253d  lea     rcx, [rbp+var_10]
0x180052541  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180052546  nop
0x180052547  lea     rcx, [rbp+arg_18]
0x18005254b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180052550  nop
0x180052551  lea     rcx, [rbp+var_8]
0x180052555  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18005255a  mov     rbx, [rsp+30h+arg_0]
0x18005255f  add     rsp, 30h
0x180052563  pop     rdi
0x180052564  pop     rsi
0x180052565  pop     rbp
0x180052566  retn
```
