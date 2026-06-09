# WldpCheckDeviceEncryptionNotStarted

- ea: `0x18001ff70`
- end: `0x18002002f`
- name: `WldpCheckDeviceEncryptionNotStarted`
- size: `191`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x18001ff70`
- `0x180020154`
- `0x1800201b4`
- `0x1800201d4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ffce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ffce`

## string_xrefs

- `0x18001ffb2`: `onecore\base\ngscb\wldp\dll\dechecks.cpp`
- `0x18001ffde`: `onecore\base\ngscb\wldp\dll\dechecks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WldpCheckDeviceEncryptionNotStarted(_DWORD *a1)
{
  const char *v3; // r9
  unsigned int v4; // ebx
  FARPROC ProcAddress; // rax
  const char *v6; // r9
  int LastError; // eax
  int v8; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+34h] [rbp-14h] BYREF
  HMODULE hModule[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v8 = 0;
  v9 = 4;
  if ( !a1 )
    return 2147500035LL;
  LoadFveapi(hModule);
  if ( hModule[0] )
  {
    ProcAddress = GetProcAddress(hModule[0], "FveQuery");
    if ( ProcAddress )
    {
      LastError = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, int *, int *))ProcAddress)(4, 0, 0, &v8, &v9);
      if ( LastError >= 0 )
        *a1 = v8 != 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x4A,
                    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\dechecks.cpp",
                    v6);
    }
    v4 = LastError;
  }
  else
  {
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x47,
           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\dechecks.cpp",
           v3);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(hModule);
  return v4;
}

```

## disassembly

```asm
0x18001ff70  push    rbx
0x18001ff72  sub     rsp, 40h
0x18001ff76  mov     rbx, rcx
0x18001ff79  mov     [rsp+48h+var_18], 0
0x18001ff81  mov     [rsp+48h+var_14], 4
0x18001ff89  test    rcx, rcx
0x18001ff8c  jnz     short loc_18001FF98
0x18001ff8e  mov     eax, 80004003h
0x18001ff93  jmp     loc_180020029
0x18001ff98  lea     rcx, [rsp+48h+hModule]
0x18001ff9d  call    ?LoadFveapi@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; LoadFveapi(void)
0x18001ffa2  nop
0x18001ffa3  mov     rcx, [rsp+48h+hModule]; hModule
0x18001ffa8  test    rcx, rcx
0x18001ffab  jnz     short loc_18001FFC7
0x18001ffad  mov     rcx, [rsp+48h]; this
0x18001ffb2  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\wldp\\dll\\dechec"...
0x18001ffb9  mov     edx, 47h ; 'G'; void *
0x18001ffbe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ffc3  mov     ebx, eax
0x18001ffc5  jmp     short loc_18002001D
0x18001ffc7  lea     rdx, aFvequery; "FveQuery"
0x18001ffce  call    cs:__imp_GetProcAddress
0x18001ffd4  test    rax, rax
0x18001ffd7  jnz     short loc_18001FFF0
0x18001ffd9  mov     rcx, [rsp+48h]; this
0x18001ffde  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\wldp\\dll\\dechec"...
0x18001ffe5  lea     edx, [rax+4Ah]; void *
0x18001ffe8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ffed  nop
0x18001ffee  jmp     short loc_18002001B
0x18001fff0  lea     rdx, [rsp+48h+var_14]
0x18001fff5  mov     [rsp+48h+var_28], rdx
0x18001fffa  lea     r9, [rsp+48h+var_18]
0x18001ffff  xor     r8d, r8d
0x180020002  xor     edx, edx
0x180020004  lea     ecx, [rdx+4]
0x180020007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002000c  test    eax, eax
0x18002000e  js      short loc_18002001B
0x180020010  xor     ecx, ecx
0x180020012  cmp     [rsp+48h+var_18], ecx
0x180020016  setnz   cl
0x180020019  mov     [rbx], ecx
0x18002001b  mov     ebx, eax
0x18002001d  lea     rcx, [rsp+48h+hModule]
0x180020022  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180020027  mov     eax, ebx
0x180020029  add     rsp, 40h
0x18002002d  pop     rbx
0x18002002e  retn
```
