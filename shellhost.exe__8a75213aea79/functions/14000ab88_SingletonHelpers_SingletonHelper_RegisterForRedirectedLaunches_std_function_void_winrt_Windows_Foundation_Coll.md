# SingletonHelpers::SingletonHelper::RegisterForRedirectedLaunches(std::function<void (winrt::Windows::Foundation::Collections::ValueSet const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)>)

- ea: `0x14000ab88`
- end: `0x14000acb2`
- name: `?RegisterForRedirectedLaunches@SingletonHelper@SingletonHelpers@@QEAAXV?$function@$$A6AXAEBUValueSet@Collections@Foundation@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@std@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005b72c`

## callees

- `0x14000ab50`
- `0x14000ab88`
- `0x14000acb8`
- `0x14000acdc`
- `0x14000ad00`
- `0x140046a30`
- `0x140053000`
- `0x140057044`
- `0x14005d1c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ac7d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000ac7d`

## string_xrefs

- `0x14000abad`: `shellcommon\internal\shell\inc\SingletonHelpers.h`
- `0x14000ac28`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SingletonHelpers::SingletonHelper::RegisterForRedirectedLaunches(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  const char *v8; // r9
  __int64 v9; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r8d
  unsigned int lpData; // [rsp+20h] [rbp-30h]
  HKEY v14[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  _QWORD *Data; // [rsp+70h] [rbp+20h] BYREF
  __int64 v18; // [rsp+78h] [rbp+28h]
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  v18 = a2;
  if ( !a1[14] )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
      a4);
  std::function<void (winrt::Windows::Foundation::Collections::ValueSet const &,std::wstring const &)>::operator=(a1 + 33);
  ConnectionlessEndpoint::Initialize(a1 + 16, a1);
  v6 = a1 + 5;
  if ( a1[8] > 7u )
    v6 = (_QWORD *)*v6;
  Data = v6;
  wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(v14, &Data);
  v7 = a1 + 1;
  if ( a1[4] > 7u )
    v7 = (_QWORD *)*v7;
  Data = v7;
  wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(v15, &Data);
  if ( !a1[14] )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE6,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
      v8);
  v9 = a1[17];
  SingletonHelpers::details::GetSingletonSessionSubKey(&hKey, v15, v14, 0x20006u);
  LODWORD(Data) = v9;
  v10 = RegSetKeyValueW(hKey, 0, L"CommunicationHWND", 4u, &Data, 4u);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xEC, v11, (const char *)v10, lpData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return std::_Func_class<void,>::~_Func_class<void,>(a2);
}

```

## disassembly

```asm
0x14000ab88  mov     [rsp-18h+arg_8], rdx
0x14000ab8d  push    rbp
0x14000ab8e  push    rbx
0x14000ab8f  push    rdi
0x14000ab90  mov     rbp, rsp
0x14000ab93  sub     rsp, 50h
0x14000ab97  mov     rdi, rdx
0x14000ab9a  mov     rbx, rcx
0x14000ab9d  cmp     qword ptr [rcx+70h], 0
0x14000aba2  setz    al
0x14000aba5  mov     rcx, [rbp+18h]; this
0x14000aba9  test    al, al
0x14000abab  jz      short loc_14000ABBF
0x14000abad  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Sing"...
0x14000abb4  mov     edx, 1DFh; void *
0x14000abb9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000abbf  lea     rcx, [rbx+108h]
0x14000abc6  call    ??4?$function@$$A6AXAEBUValueSet@Collections@Foundation@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (winrt::Windows::Foundation::Collections::ValueSet const &,std::wstring const &)>::operator=(std::function<void (winrt::Windows::Foundation::Collections::ValueSet const &,std::wstring const &)> const &)
0x14000abcb  lea     rcx, [rbx+80h]
0x14000abd2  mov     rdx, rbx
0x14000abd5  call    ?Initialize@ConnectionlessEndpoint@@QEAAXPEAVFlowEndpointMessageReceiver@@KW4EndpointInitializationOptions@@@Z; ConnectionlessEndpoint::Initialize(FlowEndpointMessageReceiver *,ulong,EndpointInitializationOptions)
0x14000abda  lea     rax, [rbx+28h]
0x14000abde  cmp     qword ptr [rax+18h], 7
0x14000abe3  jbe     short loc_14000ABE8
0x14000abe5  mov     rax, [rax]
0x14000abe8  mov     [rbp+Data], rax
0x14000abec  lea     rdx, [rbp+Data]
0x14000abf0  lea     rcx, [rbp+var_20]
0x14000abf4  call    ??$?0PEBG$0A@@?$basic_zstring_view@G@wil@@QEAA@$$QEAPEBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const * &&)
0x14000abf9  lea     rcx, [rbx+8]
0x14000abfd  cmp     qword ptr [rcx+18h], 7
0x14000ac02  jbe     short loc_14000AC07
0x14000ac04  mov     rcx, [rcx]
0x14000ac07  mov     [rbp+Data], rcx
0x14000ac0b  lea     rdx, [rbp+Data]
0x14000ac0f  lea     rcx, [rbp+var_10]
0x14000ac13  call    ??$?0PEBG$0A@@?$basic_zstring_view@G@wil@@QEAA@$$QEAPEBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const * &&)
0x14000ac18  cmp     qword ptr [rbx+70h], 0
0x14000ac1d  setz    al
0x14000ac20  mov     rcx, [rbp+18h]; this
0x14000ac24  test    al, al
0x14000ac26  jz      short loc_14000AC3A
0x14000ac28  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Sing"...
0x14000ac2f  mov     edx, 0E6h; void *
0x14000ac34  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000ac3a  mov     rbx, [rbx+88h]
0x14000ac41  mov     r9d, 20006h
0x14000ac47  lea     r8, [rbp+var_20]
0x14000ac4b  lea     rdx, [rbp+var_10]
0x14000ac4f  lea     rcx, [rbp+hKey]
0x14000ac53  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &,ulong)
0x14000ac58  nop
0x14000ac59  mov     dword ptr [rbp+Data], ebx
0x14000ac5c  mov     r9d, 4; dwType
0x14000ac62  mov     [rsp+50h+cbData], r9d; cbData
0x14000ac67  lea     rax, [rbp+Data]
0x14000ac6b  mov     [rsp+50h+lpData], rax; unsigned int
0x14000ac70  mov     r8, cs:lpValueName; lpValueName
0x14000ac77  xor     edx, edx; lpSubKey
0x14000ac79  mov     rcx, [rbp+hKey]; hKey
0x14000ac7d  call    cs:__imp_RegSetKeyValueW
0x14000ac83  mov     rcx, [rbp+18h]; this
0x14000ac87  test    eax, eax
0x14000ac89  jz      short loc_14000AC99
0x14000ac8b  mov     r9d, eax; char *
0x14000ac8e  mov     edx, 0ECh; void *
0x14000ac93  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000ac99  lea     rcx, [rbp+hKey]
0x14000ac9d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000aca2  nop
0x14000aca3  mov     rcx, rdi
0x14000aca6  add     rsp, 50h
0x14000acaa  pop     rdi
0x14000acab  pop     rbx
0x14000acac  pop     rbp
0x14000acad  jmp     ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
```
