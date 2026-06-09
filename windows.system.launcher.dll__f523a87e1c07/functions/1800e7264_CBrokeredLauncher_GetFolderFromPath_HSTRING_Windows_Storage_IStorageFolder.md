# CBrokeredLauncher::GetFolderFromPath(HSTRING__ *,Windows::Storage::IStorageFolder * *)

- ea: `0x1800e7264`
- end: `0x1800e73b9`
- name: `?GetFolderFromPath@CBrokeredLauncher@@CAJPEAUHSTRING__@@PEAPEAUIStorageFolder@Storage@Windows@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(HSTRING, struct Windows::Storage::IStorageFolder **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e4598`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x1800689b4`
- `0x1800e7264`

## import_xrefs

- `Windows.Storage!SHCreateItemFromParsingName` at `0x1800e730d`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x1800e730d`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller` at `0x1800e734f`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller` at `0x1800e734f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e7287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e7287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e72c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e73a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e72c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e73a4`

## string_xrefs

- `0x1800e72a3`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800e72da`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800e731d`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800e735f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
__int64 __fastcall CBrokeredLauncher::GetFolderFromPath(HSTRING a1, struct Windows::Storage::IStorageFolder **a2)
{
  PCWSTR StringRawBuffer; // rax
  int v4; // eax
  unsigned int v5; // ebx
  void *v7; // rbx
  HRESULT v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  struct Windows::Storage::IStorageFolder *v13; // [rsp+48h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+30h] BYREF
  void *ppv; // [rsp+58h] [rbp+38h] BYREF

  *a2 = 0;
  pv = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a1, 0);
  v4 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         StringRawBuffer,
         &pv);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C2,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v4,
      savedregs);
    if ( pv )
      CoTaskMemFree(pv);
    return v5;
  }
  v7 = pv;
  if ( !pv )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C3,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)0x8007000ELL,
      savedregs);
    return v5;
  }
  ppv = 0;
  v8 = SHCreateItemFromParsingName((PCWSTR)pv, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v13 = 0;
    v10 = CreateStorageItemFromShellItem_FullTrustCaller(ppv, 4098, &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b, &v13);
    v9 = v10;
    if ( v10 >= 0 )
    {
      *a2 = v13;
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      v9 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C9,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
        (const char *)(unsigned int)v10,
        savedregs);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C6,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v8,
      savedregs);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  CoTaskMemFree(v7);
  return v9;
}

```

## disassembly

```asm
0x1800e7264  mov     [rsp-18h+arg_0], rbx
0x1800e7269  push    rbp
0x1800e726a  push    rsi
0x1800e726b  push    rdi; int
0x1800e726c  mov     rbp, rsp
0x1800e726f  sub     rsp, 20h
0x1800e7273  mov     rsi, rdx
0x1800e7276  mov     qword ptr [rdx], 0
0x1800e727d  xor     edx, edx; length
0x1800e727f  mov     [rbp+pv], 0
0x1800e7287  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e728d  mov     rcx, rax
0x1800e7290  lea     rdx, [rbp+pv]
0x1800e7294  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800e7299  mov     ebx, eax
0x1800e729b  test    eax, eax
0x1800e729d  jns     short loc_1800E72CD
0x1800e729f  mov     rcx, [rbp+18h]; this
0x1800e72a3  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800e72aa  mov     r9d, eax; char *
0x1800e72ad  mov     edx, 5C2h; void *
0x1800e72b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e72b7  mov     rcx, [rbp+pv]; pv
0x1800e72bb  test    rcx, rcx
0x1800e72be  jz      short loc_1800E72C6
0x1800e72c0  call    cs:__imp_CoTaskMemFree
0x1800e72c6  mov     eax, ebx
0x1800e72c8  jmp     loc_1800E73AC
0x1800e72cd  mov     rbx, [rbp+pv]
0x1800e72d1  test    rbx, rbx
0x1800e72d4  jnz     short loc_1800E72F5
0x1800e72d6  mov     rcx, [rbp+18h]; this
0x1800e72da  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800e72e1  mov     ebx, 8007000Eh
0x1800e72e6  mov     edx, 5C3h; void *
0x1800e72eb  mov     r9d, ebx; char *
0x1800e72ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e72f3  jmp     short loc_1800E72C6
0x1800e72f5  lea     r9, [rbp+ppv]; ppv
0x1800e72f9  mov     [rbp+ppv], 0
0x1800e7301  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800e7308  xor     edx, edx; pbc
0x1800e730a  mov     rcx, rbx; pszPath
0x1800e730d  call    cs:__imp_SHCreateItemFromParsingName
0x1800e7313  mov     edi, eax
0x1800e7315  test    eax, eax
0x1800e7317  jns     short loc_1800E7333
0x1800e7319  mov     rcx, [rbp+18h]; this
0x1800e731d  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800e7324  mov     r9d, eax; char *
0x1800e7327  mov     edx, 5C6h; void *
0x1800e732c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7331  jmp     short loc_1800E7398
0x1800e7333  mov     rcx, [rbp+ppv]
0x1800e7337  lea     r9, [rbp+arg_8]
0x1800e733b  lea     r8, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x1800e7342  mov     [rbp+arg_8], 0
0x1800e734a  mov     edx, 1002h
0x1800e734f  call    cs:__imp_CreateStorageItemFromShellItem_FullTrustCaller
0x1800e7355  mov     edi, eax
0x1800e7357  test    eax, eax
0x1800e7359  jns     short loc_1800E737E
0x1800e735b  mov     rcx, [rbp+18h]; this
0x1800e735f  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800e7366  mov     r9d, eax; char *
0x1800e7369  mov     edx, 5C9h; void *
0x1800e736e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7373  lea     rcx, [rbp+arg_8]
0x1800e7377  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e737c  jmp     short loc_1800E7398
0x1800e737e  mov     rax, [rbp+arg_8]
0x1800e7382  lea     rcx, [rbp+arg_8]
0x1800e7386  mov     [rsi], rax
0x1800e7389  mov     [rbp+arg_8], 0
0x1800e7391  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e7396  xor     edi, edi
0x1800e7398  lea     rcx, [rbp+ppv]
0x1800e739c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e73a1  mov     rcx, rbx; pv
0x1800e73a4  call    cs:__imp_CoTaskMemFree
0x1800e73aa  mov     eax, edi
0x1800e73ac  mov     rbx, [rsp+20h+arg_0]
0x1800e73b1  add     rsp, 20h
0x1800e73b5  pop     rdi
0x1800e73b6  pop     rsi
0x1800e73b7  pop     rbp
0x1800e73b8  retn
```
