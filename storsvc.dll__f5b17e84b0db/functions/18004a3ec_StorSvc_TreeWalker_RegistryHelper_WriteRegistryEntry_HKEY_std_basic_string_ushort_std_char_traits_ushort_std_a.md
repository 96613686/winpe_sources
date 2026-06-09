# StorSvc::TreeWalker::RegistryHelper::WriteRegistryEntry(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,int,bool)

- ea: `0x18004a3ec`
- end: `0x18004a594`
- name: `?WriteRegistryEntry@RegistryHelper@TreeWalker@StorSvc@@CAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1H_N@Z`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180049c18`

## callees

- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180019db4`
- `0x18001c130`
- `0x18004a3ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a49e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a49e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a50d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a565`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a50d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a565`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a440`
- `RPCRT4!RpcRevertToSelf` at `0x18004a4b4`
- `RPCRT4!RpcRevertToSelf` at `0x18004a4b4`
- `RPCRT4!RpcImpersonateClient` at `0x18004a414`
- `RPCRT4!RpcImpersonateClient` at `0x18004a414`

## string_xrefs

- `0x18004a4c6`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`
- `0x18004a52a`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StorSvc::TreeWalker::RegistryHelper::WriteRegistryEntry(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  signed int v6; // ebx
  const WCHAR *v7; // rax
  LSTATUS Key; // eax
  const BYTE *v9; // rax
  DWORD v10; // edx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  int dwOptions; // [rsp+20h] [rbp-48h]
  int dwOptionsa; // [rsp+20h] [rbp-48h]
  HKEY hKey[2]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v18; // [rsp+70h] [rbp+8h]
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a4;
  v18 = a1;
  hKey[0] = 0;
  if ( RpcImpersonateClient(0) )
  {
    v6 = -2147467259;
  }
  else
  {
    hKey[0] = 0;
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    Key = RegCreateKeyExW(HKEY_CURRENT_USER, v7, 0, 0, 0, 0x3000Fu, 0, hKey, 0);
    v6 = Key;
    if ( Key > 0 )
      v6 = (unsigned __int16)Key | 0x80070000;
    RpcRevertToSelf();
    if ( v6 >= 0 )
    {
      v9 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      v11 = RegSetValueExW(hKey[0], L"path", 0, 1u, v9, v10);
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( v6 >= 0 )
      {
        v12 = RegSetValueExW(hKey[0], L"rate", 0, 4u, (const BYTE *)&Data, 4u);
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
          (const char *)(unsigned int)v6,
          dwOptionsa);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
        (const char *)(unsigned int)v6,
        dwOptions);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004a3ec  mov     rax, rsp
0x18004a3ef  mov     [rax+10h], rbx
0x18004a3f3  mov     [rax+18h], rsi
0x18004a3f7  mov     [rax+20h], r9d
0x18004a3fb  mov     [rax+8], rcx
0x18004a3ff  push    rdi
0x18004a400  sub     rsp, 60h
0x18004a404  mov     rsi, r8
0x18004a407  mov     rdi, rdx
0x18004a40a  mov     qword ptr [rax-18h], 0
0x18004a412  xor     ecx, ecx; BindingHandle
0x18004a414  call    cs:__imp_RpcImpersonateClient
0x18004a41a  test    eax, eax
0x18004a41c  jz      short loc_18004A428
0x18004a41e  mov     ebx, 80004005h
0x18004a423  jmp     loc_18004A576
0x18004a428  mov     rbx, [rsp+68h+hKey]
0x18004a42d  test    rbx, rbx
0x18004a430  jz      short loc_18004A451
0x18004a432  lea     rcx, [rsp+68h+arg_0]; this
0x18004a437  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004a43c  nop
0x18004a43d  mov     rcx, rbx; hKey
0x18004a440  call    cs:__imp_RegCloseKey
0x18004a446  nop
0x18004a447  lea     rcx, [rsp+68h+arg_0]; this
0x18004a44c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004a451  mov     [rsp+68h+hKey], 0
0x18004a45a  mov     rcx, rdi
0x18004a45d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a462  mov     rdx, rax; lpSubKey
0x18004a465  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18004a46e  lea     rax, [rsp+68h+hKey]
0x18004a473  mov     [rsp+68h+phkResult], rax; phkResult
0x18004a478  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004a481  mov     [rsp+68h+samDesired], 3000Fh; samDesired
0x18004a489  mov     [rsp+68h+dwOptions], 0; int
0x18004a491  xor     r9d, r9d; lpClass
0x18004a494  xor     r8d, r8d; Reserved
0x18004a497  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18004a49e  call    cs:__imp_RegCreateKeyExW
0x18004a4a4  mov     ebx, eax
0x18004a4a6  mov     edi, 80070000h
0x18004a4ab  test    eax, eax
0x18004a4ad  jle     short loc_18004A4B4
0x18004a4af  movzx   ebx, ax
0x18004a4b2  or      ebx, edi
0x18004a4b4  call    cs:__imp_RpcRevertToSelf
0x18004a4ba  test    ebx, ebx
0x18004a4bc  jns     short loc_18004A4DD
0x18004a4be  mov     rcx, [rsp+68h]; this
0x18004a4c3  mov     r9d, ebx; char *
0x18004a4c6  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x18004a4cd  mov     edx, 6Dh ; 'm'; void *
0x18004a4d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a4d7  nop
0x18004a4d8  jmp     loc_18004A576
0x18004a4dd  mov     eax, [rsi+10h]
0x18004a4e0  lea     edx, ds:2[rax*2]
0x18004a4e7  mov     rcx, rsi
0x18004a4ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a4ef  mov     [rsp+68h+samDesired], edx; cbData
0x18004a4f3  mov     qword ptr [rsp+68h+dwOptions], rax; int
0x18004a4f8  mov     r9d, 1; dwType
0x18004a4fe  xor     r8d, r8d; Reserved
0x18004a501  lea     rdx, aPath; "path"
0x18004a508  mov     rcx, [rsp+68h+hKey]; hKey
0x18004a50d  call    cs:__imp_RegSetValueExW
0x18004a513  mov     ebx, eax
0x18004a515  test    eax, eax
0x18004a517  jle     short loc_18004A51E
0x18004a519  movzx   ebx, ax
0x18004a51c  or      ebx, edi
0x18004a51e  test    ebx, ebx
0x18004a520  jns     short loc_18004A53E
0x18004a522  mov     rcx, [rsp+68h]; this
0x18004a527  mov     r9d, ebx; char *
0x18004a52a  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x18004a531  mov     edx, 6Fh ; 'o'; void *
0x18004a536  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a53b  nop
0x18004a53c  jmp     short loc_18004A576
0x18004a53e  mov     r9d, 4; dwType
0x18004a544  mov     [rsp+68h+samDesired], r9d; cbData
0x18004a549  lea     rax, [rsp+68h+Data]
0x18004a551  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18004a556  xor     r8d, r8d; Reserved
0x18004a559  lea     rdx, aRate; "rate"
0x18004a560  mov     rcx, [rsp+68h+hKey]; hKey
0x18004a565  call    cs:__imp_RegSetValueExW
0x18004a56b  mov     ebx, eax
0x18004a56d  test    eax, eax
0x18004a56f  jle     short loc_18004A576
0x18004a571  movzx   ebx, ax
0x18004a574  or      ebx, edi
0x18004a576  lea     rcx, [rsp+68h+hKey]
0x18004a57b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004a580  mov     eax, ebx
0x18004a582  lea     r11, [rsp+68h+var_8]
0x18004a587  mov     rbx, [r11+18h]
0x18004a58b  mov     rsi, [r11+20h]
0x18004a58f  mov     rsp, r11
0x18004a592  pop     rdi
0x18004a593  retn
```
