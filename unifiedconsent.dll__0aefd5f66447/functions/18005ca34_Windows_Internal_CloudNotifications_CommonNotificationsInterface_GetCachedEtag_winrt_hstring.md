# Windows::Internal::CloudNotifications::CommonNotificationsInterface::GetCachedEtag(winrt::hstring)

- ea: `0x18005ca34`
- end: `0x18005cc4a`
- name: `?GetCachedEtag@CommonNotificationsInterface@CloudNotifications@Internal@Windows@@AEAA?AUhstring@winrt@@U56@@Z`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059840`

## callees

- `0x180002810`
- `0x1800034f7`
- `0x1800035ab`
- `0x18000ebfc`
- `0x18000f44c`
- `0x18003fbf8`
- `0x18005ca34`
- `0x18007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005cb5b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005cbf0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005cb5b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005cbf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cbc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cbc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cb91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cb91`

## string_xrefs

- `0x18005cae2`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005cb9f`: `onecoreuap\shell\clouddirect\cloudnotifications\src\commonnotificationsinterface.cpp`
- `0x18005cb6d`: `Error while retrieving the cached ETag from the registry: 0x%08X`
- `0x18005cae9`: `No cached ETag found in the registry.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HSTRING __fastcall Windows::Internal::CloudNotifications::CommonNotificationsInterface::GetCachedEtag(
        __int64 a1,
        HSTRING a2,
        HSTRING a3)
{
  __int64 v6; // rcx
  const WCHAR *v7; // r8
  __int64 v8; // rbx
  unsigned int v9; // edx
  volatile signed __int32 *v10; // rdi
  int v11; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, _QWORD, PCWSTR, const char *, int); // rbx
  PCWSTR StringRawBuffer; // rax
  int v17; // ebx
  __int64 v18; // rdi
  struct winrt::impl::shared_hstring_header *v19; // rbp
  HSTRING string[4]; // [rsp+40h] [rbp-858h] BYREF
  _WORD Source[1024]; // [rsp+60h] [rbp-838h] BYREF

  string[0] = a2;
  string[2] = a3;
  v6 = *(_QWORD *)(a1 + 104);
  if ( *(_QWORD *)a3 )
    v7 = *(const WCHAR **)(*(_QWORD *)a3 + 16LL);
  else
    v7 = &Name;
  v8 = (*(unsigned int (__fastcall **)(__int64, __int64, const WCHAR *, const wchar_t *, _WORD *, int))(*(_QWORD *)v6 + 40LL))(
         v6,
         -2147483647,
         v7,
         L"SubscriptionEtag",
         Source,
         1024);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 8LL))(*(_QWORD *)(a1 + 104), v8) )
  {
    (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *, const char *, int))(**(_QWORD **)(a1 + 88) + 16LL))(
      *(_QWORD *)(a1 + 88),
      1,
      L"No cached ETag found in the registry.",
      "onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
      752);
    *(_QWORD *)a2 = 0;
    v10 = *(volatile signed __int32 **)a3;
    if ( *(_QWORD *)a3 )
      goto LABEL_6;
  }
  else if ( (int)v8 >= 0 )
  {
    v18 = -1;
    do
      ++v18;
    while ( Source[v18] );
    if ( (_DWORD)v18 )
    {
      v19 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v18, v9);
      memcpy_s((char *)v19 + 28, 2LL * (unsigned int)v18, Source, 2LL * (unsigned int)v18);
    }
    else
    {
      v19 = 0;
    }
    *(_QWORD *)a2 = v19;
    v10 = *(volatile signed __int32 **)a3;
    if ( *(_QWORD *)a3 )
    {
LABEL_6:
      v11 = _InterlockedDecrement(v10 + 6);
      if ( v11 )
      {
        if ( v11 < 0 )
          abort();
        goto LABEL_8;
      }
LABEL_7:
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v10);
LABEL_8:
      *(_QWORD *)a3 = 0;
    }
  }
  else
  {
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      string,
      L"Error while retrieving the cached ETag from the registry: 0x%08X",
      (unsigned int)v8);
    v14 = *(_QWORD *)(a1 + 88);
    v15 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR, const char *, int))(*(_QWORD *)v14 + 16LL);
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    v15(
      v14,
      0,
      StringRawBuffer,
      "onecoreuap\\shell\\clouddirect\\cloudnotifications\\src\\commonnotificationsinterface.cpp",
      766);
    *(_QWORD *)a2 = 0;
    if ( string[0] )
      WindowsDeleteString(string[0]);
    v10 = *(volatile signed __int32 **)a3;
    if ( *(_QWORD *)a3 )
    {
      v17 = _InterlockedDecrement(v10 + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
          abort();
        goto LABEL_8;
      }
      goto LABEL_7;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18005ca34  mov     [rsp+arg_18], rbx
0x18005ca39  push    rbp
0x18005ca3a  push    rsi
0x18005ca3b  push    rdi
0x18005ca3c  push    r14
0x18005ca3e  push    r15
0x18005ca40  sub     rsp, 870h
0x18005ca47  mov     rax, cs:__security_cookie
0x18005ca4e  xor     rax, rsp
0x18005ca51  mov     [rsp+898h+var_38], rax
0x18005ca59  mov     rsi, r8
0x18005ca5c  mov     r14, rdx
0x18005ca5f  mov     rdi, rcx
0x18005ca62  mov     [rsp+898h+string], rdx
0x18005ca67  mov     [rsp+898h+var_848], r8
0x18005ca6c  xor     r15d, r15d
0x18005ca6f  mov     rcx, [rcx+68h]
0x18005ca73  mov     rax, [rcx]
0x18005ca76  mov     r10, [rax+28h]
0x18005ca7a  mov     rax, [r8]
0x18005ca7d  test    rax, rax
0x18005ca80  jz      short loc_18005CA88
0x18005ca82  mov     r8, [rax+10h]
0x18005ca86  jmp     short loc_18005CA8F
0x18005ca88  lea     r8, Name
0x18005ca8f  mov     [rsp+898h+var_870], 400h
0x18005ca97  lea     rax, [rsp+898h+Source]
0x18005ca9c  mov     [rsp+898h+var_878], rax
0x18005caa1  lea     r9, aSubscriptionet; "SubscriptionEtag"
0x18005caa8  mov     rdx, 0FFFFFFFF80000001h
0x18005caaf  mov     rax, r10
0x18005cab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cab7  mov     ebx, eax
0x18005cab9  mov     rcx, [rdi+68h]
0x18005cabd  mov     rax, [rcx]
0x18005cac0  mov     edx, ebx
0x18005cac2  mov     rax, [rax+8]
0x18005cac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cacb  test    al, al
0x18005cacd  jz      loc_18005CB62
0x18005cad3  mov     rcx, [rdi+58h]
0x18005cad7  mov     rax, [rcx]
0x18005cada  mov     dword ptr [rsp+898h+var_878], 2F0h
0x18005cae2  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005cae9  lea     r8, aNoCachedEtagFo; "No cached ETag found in the registry."
0x18005caf0  mov     edx, 1
0x18005caf5  mov     rax, [rax+10h]
0x18005caf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cafe  mov     [r14], r15
0x18005cb01  mov     rdi, [rsi]
0x18005cb04  test    rdi, rdi
0x18005cb07  jz      short loc_18005CB2D
0x18005cb09  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005cb0d  lock xadd [rdi+18h], ebx
0x18005cb12  sub     ebx, 1
0x18005cb15  jnz     short loc_18005CB57
0x18005cb17  nop
0x18005cb18  call    WINRT_IMPL_GetProcessHeap
0x18005cb1d  mov     rcx, rax; hHeap
0x18005cb20  xor     edx, edx; dwFlags
0x18005cb22  mov     r8, rdi; lpMem
0x18005cb25  call    WINRT_IMPL_HeapFree
0x18005cb2a  mov     [rsi], r15
0x18005cb2d  mov     rax, r14
0x18005cb30  mov     rcx, [rsp+898h+var_38]
0x18005cb38  xor     rcx, rsp; StackCookie
0x18005cb3b  call    __security_check_cookie
0x18005cb40  mov     rbx, [rsp+898h+arg_18]
0x18005cb48  add     rsp, 870h
0x18005cb4f  pop     r15
0x18005cb51  pop     r14
0x18005cb53  pop     rdi
0x18005cb54  pop     rsi
0x18005cb55  pop     rbp
0x18005cb56  retn
0x18005cb57  test    ebx, ebx
0x18005cb59  jns     short loc_18005CB2A
0x18005cb5b  call    cs:__imp_abort
0x18005cb62  test    ebx, ebx
0x18005cb64  jns     loc_18005CBF7
0x18005cb6a  mov     r8d, ebx
0x18005cb6d  lea     rdx, aErrorWhileRetr_0; "Error while retrieving the cached ETag "...
0x18005cb74  lea     rcx, [rsp+898h+string]
0x18005cb79  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,...)
0x18005cb7e  nop
0x18005cb7f  mov     rdi, [rdi+58h]
0x18005cb83  mov     rax, [rdi]
0x18005cb86  mov     rbx, [rax+10h]
0x18005cb8a  xor     edx, edx; length
0x18005cb8c  mov     rcx, [rsp+898h+string]; string
0x18005cb91  call    cs:__imp_WindowsGetStringRawBuffer
0x18005cb97  mov     dword ptr [rsp+898h+var_878], 2FEh
0x18005cb9f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\clouddirect\\cloudno"...
0x18005cba6  mov     r8, rax
0x18005cba9  xor     edx, edx
0x18005cbab  mov     rcx, rdi
0x18005cbae  mov     rax, rbx
0x18005cbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbb6  mov     [r14], r15
0x18005cbb9  mov     rcx, [rsp+898h+string]; string
0x18005cbbe  test    rcx, rcx
0x18005cbc1  jz      short loc_18005CBCA
0x18005cbc3  call    cs:__imp_WindowsDeleteString
0x18005cbc9  nop
0x18005cbca  mov     rdi, [rsi]
0x18005cbcd  test    rdi, rdi
0x18005cbd0  jz      loc_18005CB2D
0x18005cbd6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005cbda  lock xadd [rdi+18h], ebx
0x18005cbdf  sub     ebx, 1
0x18005cbe2  jz      loc_18005CB17
0x18005cbe8  test    ebx, ebx
0x18005cbea  jns     loc_18005CB2A
0x18005cbf0  call    cs:__imp_abort
0x18005cbf7  lea     rax, [rsp+898h+Source]
0x18005cbfc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005cc00  mov     rdi, rbx
0x18005cc03  inc     rdi
0x18005cc06  cmp     [rax+rdi*2], r15w
0x18005cc0b  jnz     short loc_18005CC03
0x18005cc0d  test    edi, edi
0x18005cc0f  jnz     short loc_18005CC16
0x18005cc11  mov     rbp, r15
0x18005cc14  jmp     short loc_18005CC36
0x18005cc16  mov     ecx, edi; this
0x18005cc18  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18005cc1d  mov     rbp, rax
0x18005cc20  mov     edx, edi
0x18005cc22  add     rdx, rdx; DestinationSize
0x18005cc25  lea     rcx, [rax+1Ch]; Destination
0x18005cc29  mov     r9, rdx; SourceSize
0x18005cc2c  lea     r8, [rsp+898h+Source]; Source
0x18005cc31  call    memcpy_s
0x18005cc36  mov     [r14], rbp
0x18005cc39  mov     rdi, [rsi]
0x18005cc3c  test    rdi, rdi
0x18005cc3f  jz      loc_18005CB2D
0x18005cc45  jmp     loc_18005CB0D
```
