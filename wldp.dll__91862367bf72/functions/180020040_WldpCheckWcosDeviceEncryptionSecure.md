# WldpCheckWcosDeviceEncryptionSecure

- ea: `0x180020040`
- end: `0x18002014d`
- name: `WldpCheckWcosDeviceEncryptionSecure`
- size: `269`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x180020040`
- `0x180020154`
- `0x1800201b4`
- `0x1800201d4`
- `0x180021ec0`
- `0x180022a10`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800200d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800200d2`

## string_xrefs

- `0x1800200b6`: `onecore\base\ngscb\wldp\dll\dechecks.cpp`
- `0x1800200e1`: `onecore\base\ngscb\wldp\dll\dechecks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WldpCheckWcosDeviceEncryptionSecure(_DWORD *a1)
{
  const char *v3; // r9
  unsigned int v4; // ebx
  FARPROC ProcAddress; // rax
  const char *v6; // r9
  int LastError; // eax
  int v8; // [rsp+30h] [rbp-19h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-11h] BYREF
  __int64 v10; // [rsp+40h] [rbp-9h] BYREF
  int v11; // [rsp+48h] [rbp-1h]
  _BYTE v12[64]; // [rsp+50h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v10 = 786433;
  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  v8 = 64;
  if ( !a1 )
    return 2147500035LL;
  LoadFveapi(&hModule);
  if ( hModule )
  {
    ProcAddress = GetProcAddress(hModule, "FveQuery");
    if ( ProcAddress )
    {
      LastError = ((__int64 (__fastcall *)(__int64, __int64 *, __int64, _BYTE *, int *))ProcAddress)(
                    5,
                    &v10,
                    12,
                    v12,
                    &v8);
      if ( LastError >= 0 )
        *a1 = v12[4] != 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x77,
                    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\dechecks.cpp",
                    v6);
    }
    v4 = LastError;
  }
  else
  {
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x74,
           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\dechecks.cpp",
           v3);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
  return v4;
}

```

## disassembly

```asm
0x180020040  mov     [rsp-8+arg_8], rbx
0x180020045  mov     [rsp-8+arg_10], rsi
0x18002004a  push    rbp
0x18002004b  lea     rbp, [rsp-57h]
0x180020050  sub     rsp, 0A0h
0x180020057  mov     rax, cs:__security_cookie
0x18002005e  xor     rax, rsp
0x180020061  mov     [rbp+57h+var_10], rax
0x180020065  mov     rbx, rcx
0x180020068  mov     [rbp+57h+var_60], 0C0001h
0x180020070  mov     esi, 0Ch
0x180020075  xor     eax, eax
0x180020077  mov     [rbp+57h+var_58], eax
0x18002007a  xor     edx, edx; Val
0x18002007c  lea     r8d, [rsi+34h]; Size
0x180020080  lea     rcx, [rbp+57h+var_50]; void *
0x180020084  call    memset_0
0x180020089  mov     [rbp+57h+var_70], 40h ; '@'
0x180020090  test    rbx, rbx
0x180020093  jnz     short loc_18002009F
0x180020095  mov     eax, 80004003h
0x18002009a  jmp     loc_18002012C
0x18002009f  lea     rcx, [rbp+57h+hModule]
0x1800200a3  call    ?LoadFveapi@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; LoadFveapi(void)
0x1800200a8  nop
0x1800200a9  mov     rcx, [rbp+57h+hModule]; hModule
0x1800200ad  test    rcx, rcx
0x1800200b0  jnz     short loc_1800200CB
0x1800200b2  mov     rcx, [rbp+5Fh]; this
0x1800200b6  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\wldp\\dll\\dechec"...
0x1800200bd  mov     edx, 74h ; 't'; void *
0x1800200c2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800200c7  mov     ebx, eax
0x1800200c9  jmp     short loc_180020121
0x1800200cb  lea     rdx, aFvequery; "FveQuery"
0x1800200d2  call    cs:__imp_GetProcAddress
0x1800200d8  test    rax, rax
0x1800200db  jnz     short loc_1800200F3
0x1800200dd  mov     rcx, [rbp+5Fh]; this
0x1800200e1  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\wldp\\dll\\dechec"...
0x1800200e8  lea     edx, [rax+77h]; void *
0x1800200eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800200f0  nop
0x1800200f1  jmp     short loc_18002011F
0x1800200f3  lea     rcx, [rbp+57h+var_70]
0x1800200f7  mov     [rsp+0A0h+var_80], rcx
0x1800200fc  lea     r9, [rbp+57h+var_50]
0x180020100  mov     r8d, esi
0x180020103  lea     rdx, [rbp+57h+var_60]
0x180020107  mov     ecx, 5
0x18002010c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020111  test    eax, eax
0x180020113  js      short loc_18002011F
0x180020115  xor     ecx, ecx
0x180020117  cmp     [rbp+57h+var_4C], cl
0x18002011a  setnz   cl
0x18002011d  mov     [rbx], ecx
0x18002011f  mov     ebx, eax
0x180020121  lea     rcx, [rbp+57h+hModule]
0x180020125  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002012a  mov     eax, ebx
0x18002012c  mov     rcx, [rbp+57h+var_10]
0x180020130  xor     rcx, rsp; StackCookie
0x180020133  call    __security_check_cookie
0x180020138  lea     r11, [rsp+0A0h+var_s0]
0x180020140  mov     rbx, [r11+18h]
0x180020144  mov     rsi, [r11+20h]
0x180020148  mov     rsp, r11
0x18002014b  pop     rbp
0x18002014c  retn
```
