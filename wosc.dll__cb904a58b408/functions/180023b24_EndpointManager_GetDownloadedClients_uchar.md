# EndpointManager::_GetDownloadedClients(uchar)

- ea: `0x180023b24`
- end: `0x180023cc5`
- name: `?_GetDownloadedClients@EndpointManager@@AEAAAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@E@Z`
- size: `417`
- prototype: `__int64 *__fastcall(__int64 *, char)`
- caller_count: `5`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022a8c`
- `0x180023910`
- `0x180023d20`
- `0x180024188`
- `0x180024318`

## callees

- `0x1800035e0`
- `0x18000540c`
- `0x180005474`
- `0x18000a1b8`
- `0x18000fe24`
- `0x1800101fc`
- `0x180020204`
- `0x180021860`
- `0x180021a20`
- `0x180023b24`
- `0x180023ccc`
- `0x180023d20`
- `0x18002d720`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023c14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023c88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023c14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023c88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023bdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023bdc`

## string_xrefs

- `0x180023ca2`: `onecore\base\flighting\onesettings\libs\configurationsmanager\endpointmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 *__fastcall EndpointManager::_GetDownloadedClients(__int64 *a1, char a2)
{
  __int64 *v4; // rsi
  __int64 v5; // rax
  _QWORD *OurEndpoint; // rax
  _QWORD *PayloadHandler; // rax
  char v8; // bp
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  HSTRING v11; // rdi
  __int64 FixedClients; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  int v16; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v17; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp+18h] BYREF
  char v20; // [rsp+68h] [rbp+20h] BYREF

  v4 = a1 + 2;
  v5 = a1[2];
  if ( v5 )
    return (__int64 *)(v5 + 16);
  OurEndpoint = (_QWORD *)EndpointManager::_GetOurEndpoint((EndpointManager *)a1);
  PayloadHandler = (_QWORD *)ClientEndpoint::GetPayloadHandler(*OurEndpoint, &v16);
  v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*PayloadHandler + 56LL))(*PayloadHandler);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  if ( v8 )
  {
    v9 = (_QWORD *)EndpointManager::_GetOurEndpoint((EndpointManager *)a1);
    v10 = (_QWORD *)ClientEndpoint::GetPayloadHandler(*v9, &v16);
    v11 = (HSTRING)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
    WindowsDeleteString(0);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    FixedClients = EndpointManager::_GetFixedClients(a1);
    StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
    v13 = std::make_unique<OneSettingsClientJson,unsigned short const *,std::map<std::wstring,std::shared_ptr<ClientEndpoint>> const &,0>(
            &v20,
            &StringRawBuffer,
            FixedClients);
    std::unique_ptr<OneSettingsClientJson>::operator=<std::default_delete<OneSettingsClientJson>,0>(v4, v13);
    std::unique_ptr<OneSettingsClientJson>::~unique_ptr<OneSettingsClientJson>(&v20);
    v14 = *v4;
    WindowsDeleteString(v11);
    return (__int64 *)(v14 + 16);
  }
  else
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\endpointmanager.cpp",
        (const char *)0x80070002LL,
        v16);
    if ( dword_1800760F8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_1800760F8);
      if ( dword_1800760F8 == -1 )
      {
        std::map<std::wstring,std::shared_ptr<ClientEndpoint>>::map<std::wstring,std::shared_ptr<ClientEndpoint>>(qword_180076100);
        atexit(EndpointManager::_GetDownloadedClients_::_13_::_dynamic_atexit_destructor_for__mp__);
        Init_thread_footer(&dword_1800760F8);
      }
    }
    WindowsDeleteString(0);
    return qword_180076100;
  }
}

```

## disassembly

```asm
0x180023b24  mov     [rsp+arg_8], rbx
0x180023b29  push    rbp
0x180023b2a  push    rsi
0x180023b2b  push    rdi
0x180023b2c  sub     rsp, 30h
0x180023b30  mov     dil, dl
0x180023b33  mov     rbx, rcx
0x180023b36  lea     rsi, [rcx+10h]
0x180023b3a  mov     rax, [rsi]
0x180023b3d  test    rax, rax
0x180023b40  jnz     loc_180023CB4
0x180023b46  mov     [rsp+48h+arg_0], rax
0x180023b4b  call    ?_GetOurEndpoint@EndpointManager@@AEAAAEAV?$shared_ptr@VClientEndpoint@@@std@@XZ; EndpointManager::_GetOurEndpoint(void)
0x180023b50  lea     rdx, [rsp+48h+var_28]
0x180023b55  mov     rcx, [rax]
0x180023b58  call    ?GetPayloadHandler@ClientEndpoint@@QEBA?AV?$shared_ptr@VIPayloadHandler@@@std@@XZ; ClientEndpoint::GetPayloadHandler(void)
0x180023b5d  nop
0x180023b5e  mov     rcx, [rax]
0x180023b61  mov     rax, [rcx]
0x180023b64  mov     rax, [rax+38h]
0x180023b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b6d  mov     bpl, al
0x180023b70  mov     rcx, [rsp+48h+var_20]; this
0x180023b75  test    rcx, rcx
0x180023b78  jz      short loc_180023B7F
0x180023b7a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023b7f  test    bpl, bpl
0x180023b82  jz      loc_180023C23
0x180023b88  mov     rcx, rbx
0x180023b8b  call    ?_GetOurEndpoint@EndpointManager@@AEAAAEAV?$shared_ptr@VClientEndpoint@@@std@@XZ; EndpointManager::_GetOurEndpoint(void)
0x180023b90  lea     rdx, [rsp+48h+var_28]
0x180023b95  mov     rcx, [rax]
0x180023b98  call    ?GetPayloadHandler@ClientEndpoint@@QEBA?AV?$shared_ptr@VIPayloadHandler@@@std@@XZ; ClientEndpoint::GetPayloadHandler(void)
0x180023b9d  nop
0x180023b9e  mov     rcx, [rax]
0x180023ba1  mov     rax, [rcx]
0x180023ba4  mov     rax, [rax+10h]
0x180023ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bad  mov     rdi, rax
0x180023bb0  xor     ecx, ecx; string
0x180023bb2  call    cs:__imp_WindowsDeleteString
0x180023bb8  mov     [rsp+48h+arg_0], rdi
0x180023bbd  mov     rcx, [rsp+48h+var_20]; this
0x180023bc2  test    rcx, rcx
0x180023bc5  jz      short loc_180023BCC
0x180023bc7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023bcc  mov     rcx, rbx
0x180023bcf  call    ?_GetFixedClients@EndpointManager@@AEAAAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@XZ; EndpointManager::_GetFixedClients(void)
0x180023bd4  mov     rbx, rax
0x180023bd7  xor     edx, edx; length
0x180023bd9  mov     rcx, rdi; string
0x180023bdc  call    cs:__imp_WindowsGetStringRawBuffer
0x180023be2  mov     [rsp+48h+arg_10], rax
0x180023be7  mov     r8, rbx
0x180023bea  lea     rdx, [rsp+48h+arg_10]
0x180023bef  lea     rcx, [rsp+48h+arg_18]
0x180023bf4  call    ??$make_unique@VOneSettingsClientJson@@PEBGAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@$0A@@std@@YA?AV?$unique_ptr@VOneSettingsClientJson@@U?$default_delete@VOneSettingsClientJson@@@std@@@0@$$QEAPEBGAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@0@@Z; std::make_unique<OneSettingsClientJson,ushort const *,std::map<std::wstring,std::shared_ptr<ClientEndpoint>> const &,0>(ushort const * &&,std::map<std::wstring,std::shared_ptr<ClientEndpoint>> const &)
0x180023bf9  mov     rdx, rax
0x180023bfc  mov     rcx, rsi
0x180023bff  call    ??$?4U?$default_delete@VOneSettingsClientJson@@@std@@$0A@@?$unique_ptr@VOneSettingsClientJson@@U?$default_delete@VOneSettingsClientJson@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<OneSettingsClientJson>::operator=<std::default_delete<OneSettingsClientJson>,0>(std::unique_ptr<OneSettingsClientJson> &&)
0x180023c04  lea     rcx, [rsp+48h+arg_18]
0x180023c09  call    ??1?$unique_ptr@VOneSettingsClientJson@@U?$default_delete@VOneSettingsClientJson@@@std@@@std@@QEAA@XZ; std::unique_ptr<OneSettingsClientJson>::~unique_ptr<OneSettingsClientJson>(void)
0x180023c0e  mov     rbx, [rsi]
0x180023c11  mov     rcx, rdi; string
0x180023c14  call    cs:__imp_WindowsDeleteString
0x180023c1a  lea     rax, [rbx+10h]
0x180023c1e  jmp     loc_180023CB8
0x180023c23  test    dil, dil
0x180023c26  jz      short loc_180023C97
0x180023c28  mov     ecx, cs:_tls_index
0x180023c2e  mov     rax, gs:58h
0x180023c37  mov     edx, 4
0x180023c3c  mov     rax, [rax+rcx*8]
0x180023c40  mov     eax, [rdx+rax]
0x180023c43  cmp     cs:dword_1800760F8, eax
0x180023c49  jle     short loc_180023C86
0x180023c4b  lea     rcx, dword_1800760F8
0x180023c52  call    _Init_thread_header
0x180023c57  cmp     cs:dword_1800760F8, 0FFFFFFFFh
0x180023c5e  jnz     short loc_180023C86
0x180023c60  lea     rcx, qword_180076100
0x180023c67  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::shared_ptr<ClientEndpoint>>::map<std::wstring,std::shared_ptr<ClientEndpoint>>(void)
0x180023c6c  lea     rcx, _EndpointManager___GetDownloadedClients____13____dynamic_atexit_destructor_for__mp__; void (__cdecl *)()
0x180023c73  call    atexit
0x180023c78  nop
0x180023c79  lea     rcx, dword_1800760F8
0x180023c80  call    _Init_thread_footer
0x180023c85  nop
0x180023c86  xor     ecx, ecx; string
0x180023c88  call    cs:__imp_WindowsDeleteString
0x180023c8e  lea     rax, qword_180076100
0x180023c95  jmp     short loc_180023CB8
0x180023c97  mov     rcx, [rsp+48h]; this
0x180023c9c  mov     r9d, 80070002h; char *
0x180023ca2  lea     r8, aOnecoreBaseFli_5; "onecore\\base\\flighting\\onesettings\\"...
0x180023ca9  mov     edx, 106h; void *
0x180023cae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023cb4  add     rax, 10h
0x180023cb8  mov     rbx, [rsp+48h+arg_8]
0x180023cbd  add     rsp, 30h
0x180023cc1  pop     rdi
0x180023cc2  pop     rsi
0x180023cc3  pop     rbp
0x180023cc4  retn
```
