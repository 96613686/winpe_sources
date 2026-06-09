# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180009bf0`
- end: `0x180009cde`
- name: `?SvchostPushServiceGlobals@@YAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `238`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800026d0`
- `0x180002adc`
- `0x1800081ec`
- `0x180008b08`
- `0x1800096cc`
- `0x180009998`
- `0x180009bf0`
- `0x18000a1dc`
- `0x18000a498`
- `0x18000f010`

## string_xrefs

- `0x180009ccc`: `onecore\enduser\windowsupdate\muse\orchestrator\core\usosvc\servicedll\dllmain.cpp`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1)
{
  struct _SVCHOST_GLOBAL_DATA *v1; // rbx
  __int64 v2; // rax
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  const struct std::filesystem::path *v4; // rdx
  const unsigned __int16 *v5; // rcx
  const char *v6; // r9
  uus::Session *v7; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v9[4]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v1 = a1;
    v7 = (uus::Session *)operator new(0x10u);
    v2 = uus::Session::Session(v7, L"usosvc.UsoSvcImpl");
    v3 = (void (__fastcall ***)(_QWORD, __int64))g_spPinky;
    g_spPinky = v2;
    if ( v3 )
    {
      (**v3)(v3, 1);
      v2 = g_spPinky;
    }
    uus::Session::GetFullPath(v2, v9);
    if ( std::filesystem::exists((std::filesystem *)v9, v4) )
    {
      v5 = (const unsigned __int16 *)v9;
      if ( v9[3] > (unsigned __int16 *)7 )
        v5 = v9[0];
      GetUsoSvcFunctions(v5);
    }
    std::wstring::~wstring(v9);
  }
  catch ( ... )
  {
    v1 = a1;
  }
  if ( !g_UsoSvcImplModule )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\core\\usosvc\\servicedll\\dllmain.cpp",
      v6);
  g_ServiceHostPushGlobals(v1);
}

```

## disassembly

```asm
0x180009bf0  push    rbx
0x180009bf2  sub     rsp, 60h
0x180009bf6  mov     rax, cs:__security_cookie
0x180009bfd  xor     rax, rsp
0x180009c00  mov     [rsp+68h+var_18], rax
0x180009c05  mov     rbx, rcx
0x180009c08  mov     [rsp+68h+var_40], rcx
0x180009c0d  mov     ecx, 10h; Size
0x180009c12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009c17  mov     [rsp+68h+var_48], rax
0x180009c1c  lea     rdx, aUsosvcUsosvcim; "usosvc.UsoSvcImpl"
0x180009c23  mov     rcx, rax; this
0x180009c26  call    ??0Session@uus@@QEAA@PEBG@Z; uus::Session::Session(ushort const *)
0x180009c2b  nop
0x180009c2c  mov     rcx, cs:?g_spPinky@@3V?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@A; std::unique_ptr<uus::Session> g_spPinky
0x180009c33  mov     cs:?g_spPinky@@3V?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@A, rax; std::unique_ptr<uus::Session> g_spPinky
0x180009c3a  test    rcx, rcx
0x180009c3d  jz      short loc_180009C56
0x180009c3f  mov     rax, [rcx]
0x180009c42  mov     edx, 1
0x180009c47  mov     rax, [rax]
0x180009c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c4f  mov     rax, cs:?g_spPinky@@3V?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@A; std::unique_ptr<uus::Session> g_spPinky
0x180009c56  lea     rdx, [rsp+68h+var_38]
0x180009c5b  mov     rcx, rax
0x180009c5e  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEBG@Z; uus::Session::GetFullPath(ushort const *)
0x180009c63  nop
0x180009c64  lea     rcx, [rsp+68h+var_38]; this
0x180009c69  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x180009c6e  test    al, al
0x180009c70  jz      short loc_180009C89
0x180009c72  lea     rcx, [rsp+68h+var_38]
0x180009c77  cmp     [rsp+68h+var_20], 7
0x180009c7d  cmova   rcx, [rsp+68h+var_38]; unsigned __int16 *
0x180009c83  call    ?GetUsoSvcFunctions@@YAXPEBG@Z; GetUsoSvcFunctions(ushort const *)
0x180009c88  nop
0x180009c89  lea     rcx, [rsp+68h+var_38]
0x180009c8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009c93  nop
0x180009c94  jmp     short loc_180009C9B
0x180009c96  mov     rbx, [rsp+68h+var_40]
0x180009c9b  mov     rcx, [rsp+68h]; this
0x180009ca0  cmp     cs:?g_UsoSvcImplModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_UsoSvcImplModule
0x180009ca8  jz      short loc_180009CCC
0x180009caa  mov     rcx, rbx
0x180009cad  mov     rax, cs:?g_ServiceHostPushGlobals@@3P6AXPEAU_SVCHOST_GLOBAL_DATA@@@ZEA; void (*g_ServiceHostPushGlobals)(_SVCHOST_GLOBAL_DATA *)
0x180009cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cb9  mov     rcx, [rsp+68h+var_18]
0x180009cbe  xor     rcx, rsp; StackCookie
0x180009cc1  call    __security_check_cookie
0x180009cc6  add     rsp, 60h
0x180009cca  pop     rbx
0x180009ccb  retn
0x180009ccc  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180009cd3  mov     edx, 76h ; 'v'; void *
0x180009cd8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
