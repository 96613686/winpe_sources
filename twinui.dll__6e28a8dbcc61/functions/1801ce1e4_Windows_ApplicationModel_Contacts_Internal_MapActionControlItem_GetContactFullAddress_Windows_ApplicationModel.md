# Windows::ApplicationModel::Contacts::Internal::MapActionControlItem::GetContactFullAddress(Windows::ApplicationModel::Contacts::IContactAddress *,HSTRING__ * *)

- ea: `0x1801ce1e4`
- end: `0x1801ce3fa`
- name: `?GetContactFullAddress@MapActionControlItem@Internal@Contacts@ApplicationModel@Windows@@AEAAJPEAUIContactAddress@345@PEAPEAUHSTRING__@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Contacts::Internal::MapActionControlItem *__hidden this, struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801d0670`

## callees

- `0x180027cc8`
- `0x180027ee4`
- `0x18006d08c`
- `0x1801ce1e4`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce273`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce2a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce2d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce273`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce2a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce2d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce3e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce308`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce317`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce335`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce308`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce317`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce335`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ce344`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::MapActionControlItem::GetContactFullAddress(
        Windows::ApplicationModel::Contacts::Internal::MapActionControlItem *this,
        struct Windows::ApplicationModel::Contacts::IContactAddress *a2,
        HSTRING *a3)
{
  __int64 v4; // rax
  __int64 (__fastcall *v6)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  int v7; // ebx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 v10; // rax
  __int64 (__fastcall *v11)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // r14
  PCWSTR v17; // rsi
  PCWSTR v18; // rdi
  PCWSTR v19; // rbx
  PCWSTR v20; // rax
  HSTRING v21; // rax
  HSTRING v22; // rcx
  HSTRING v24; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v25[2]; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-18h] BYREF
  HSTRING v27; // [rsp+B0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+48h] BYREF
  HSTRING v29; // [rsp+C0h] [rbp+50h] BYREF
  HSTRING v30; // [rsp+C8h] [rbp+58h] BYREF

  v27 = (HSTRING)this;
  *a3 = 0;
  v4 = *(_QWORD *)a2;
  v25[0] = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v4 + 48);
  WindowsDeleteString(0);
  v25[0] = 0;
  v7 = v6(a2, v25);
  if ( v7 >= 0 )
  {
    v8 = *(_QWORD *)a2;
    v24 = 0;
    v9 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v8 + 64);
    WindowsDeleteString(0);
    v24 = 0;
    v7 = v9(a2, &v24);
    if ( v7 >= 0 )
    {
      v10 = *(_QWORD *)a2;
      v30 = 0;
      v11 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v10 + 80);
      WindowsDeleteString(0);
      v30 = 0;
      v7 = v11(a2, &v30);
      if ( v7 >= 0 )
      {
        v12 = *(_QWORD *)a2;
        v29 = 0;
        v13 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v12 + 112);
        WindowsDeleteString(0);
        v29 = 0;
        v7 = v13(a2, &v29);
        if ( v7 >= 0 )
        {
          v14 = *(_QWORD *)a2;
          string = 0;
          v15 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v14 + 96);
          WindowsDeleteString(0);
          string = 0;
          v7 = v15(a2, &string);
          if ( v7 >= 0 )
          {
            memset(v26, 0, sizeof(v26));
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v17 = WindowsGetStringRawBuffer(v29, 0);
            v18 = WindowsGetStringRawBuffer(v30, 0);
            v19 = WindowsGetStringRawBuffer(v24, 0);
            v20 = WindowsGetStringRawBuffer(v25[0], 0);
            v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                   v26,
                   L"%s,%s,%s,%s,%s",
                   v20,
                   v19,
                   v18,
                   v17,
                   StringRawBuffer);
            if ( v7 >= 0 )
            {
              v25[1] = (HSTRING)v26[0];
              v27 = 0;
              v7 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v27);
              if ( v7 < 0 )
              {
                v22 = v27;
              }
              else
              {
                v21 = v27;
                v22 = 0;
                v27 = 0;
                *a3 = v21;
              }
              WindowsDeleteString(v22);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v26);
          }
          WindowsDeleteString(string);
        }
        WindowsDeleteString(v29);
      }
      WindowsDeleteString(v30);
    }
    WindowsDeleteString(v24);
  }
  WindowsDeleteString(v25[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801ce1e4  mov     [rsp-38h+arg_0], rcx
0x1801ce1e9  push    rbp
0x1801ce1ea  push    rbx
0x1801ce1eb  push    rsi
0x1801ce1ec  push    rdi
0x1801ce1ed  push    r12
0x1801ce1ef  push    r14
0x1801ce1f1  push    r15
0x1801ce1f3  mov     rbp, rsp
0x1801ce1f6  sub     rsp, 70h
0x1801ce1fa  xor     r12d, r12d
0x1801ce1fd  xor     ecx, ecx; string
0x1801ce1ff  mov     [r8], r12
0x1801ce202  mov     r15, r8
0x1801ce205  mov     rax, [rdx]
0x1801ce208  mov     rdi, rdx
0x1801ce20b  mov     [rbp+var_28], r12
0x1801ce20f  mov     rbx, [rax+30h]
0x1801ce213  call    cs:__imp_WindowsDeleteString
0x1801ce219  lea     rdx, [rbp+var_28]
0x1801ce21d  mov     [rbp+var_28], r12
0x1801ce221  mov     rcx, rdi
0x1801ce224  mov     rax, rbx
0x1801ce227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce22c  mov     ebx, eax
0x1801ce22e  test    eax, eax
0x1801ce230  js      loc_1801CE3DF
0x1801ce236  mov     rax, [rdi]
0x1801ce239  xor     ecx, ecx; string
0x1801ce23b  mov     [rbp+var_30], r12
0x1801ce23f  mov     rbx, [rax+40h]
0x1801ce243  call    cs:__imp_WindowsDeleteString
0x1801ce249  lea     rdx, [rbp+var_30]
0x1801ce24d  mov     [rbp+var_30], r12
0x1801ce251  mov     rcx, rdi
0x1801ce254  mov     rax, rbx
0x1801ce257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce25c  mov     ebx, eax
0x1801ce25e  test    eax, eax
0x1801ce260  js      loc_1801CE3D5
0x1801ce266  mov     rax, [rdi]
0x1801ce269  xor     ecx, ecx; string
0x1801ce26b  mov     [rbp+arg_18], r12
0x1801ce26f  mov     rbx, [rax+50h]
0x1801ce273  call    cs:__imp_WindowsDeleteString
0x1801ce279  lea     rdx, [rbp+arg_18]
0x1801ce27d  mov     [rbp+arg_18], r12
0x1801ce281  mov     rcx, rdi
0x1801ce284  mov     rax, rbx
0x1801ce287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce28c  mov     ebx, eax
0x1801ce28e  test    eax, eax
0x1801ce290  js      loc_1801CE3CB
0x1801ce296  mov     rax, [rdi]
0x1801ce299  xor     ecx, ecx; string
0x1801ce29b  mov     [rbp+arg_10], r12
0x1801ce29f  mov     rbx, [rax+70h]
0x1801ce2a3  call    cs:__imp_WindowsDeleteString
0x1801ce2a9  lea     rdx, [rbp+arg_10]
0x1801ce2ad  mov     [rbp+arg_10], r12
0x1801ce2b1  mov     rcx, rdi
0x1801ce2b4  mov     rax, rbx
0x1801ce2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce2bc  mov     ebx, eax
0x1801ce2be  test    eax, eax
0x1801ce2c0  js      loc_1801CE3C1
0x1801ce2c6  mov     rax, [rdi]
0x1801ce2c9  xor     ecx, ecx; string
0x1801ce2cb  mov     [rbp+string], r12
0x1801ce2cf  mov     rbx, [rax+60h]
0x1801ce2d3  call    cs:__imp_WindowsDeleteString
0x1801ce2d9  lea     rdx, [rbp+string]
0x1801ce2dd  mov     [rbp+string], r12
0x1801ce2e1  mov     rcx, rdi
0x1801ce2e4  mov     rax, rbx
0x1801ce2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce2ec  mov     ebx, eax
0x1801ce2ee  test    eax, eax
0x1801ce2f0  js      loc_1801CE3B7
0x1801ce2f6  mov     rcx, [rbp+string]; string
0x1801ce2fa  xor     edx, edx; length
0x1801ce2fc  mov     [rbp+var_18], r12
0x1801ce300  mov     [rbp+var_10], r12
0x1801ce304  mov     [rbp+var_8], r12
0x1801ce308  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ce30e  mov     rcx, [rbp+arg_10]; string
0x1801ce312  xor     edx, edx; length
0x1801ce314  mov     r14, rax
0x1801ce317  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ce31d  mov     rcx, [rbp+arg_18]; string
0x1801ce321  xor     edx, edx; length
0x1801ce323  mov     rsi, rax
0x1801ce326  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ce32c  mov     rcx, [rbp+var_30]; string
0x1801ce330  xor     edx, edx; length
0x1801ce332  mov     rdi, rax
0x1801ce335  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ce33b  mov     rcx, [rbp+var_28]; string
0x1801ce33f  xor     edx, edx; length
0x1801ce341  mov     rbx, rax
0x1801ce344  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ce34a  mov     [rsp+70h+var_40], r14
0x1801ce34f  lea     rdx, aSSSSS; "%s,%s,%s,%s,%s"
0x1801ce356  mov     r8, rax
0x1801ce359  mov     [rsp+70h+var_48], rsi
0x1801ce35e  mov     r9, rbx
0x1801ce361  mov     [rsp+70h+var_50], rdi
0x1801ce366  lea     rcx, [rbp+var_18]
0x1801ce36a  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801ce36f  mov     ebx, eax
0x1801ce371  test    eax, eax
0x1801ce373  js      short loc_1801CE3AE
0x1801ce375  mov     rax, [rbp+var_18]
0x1801ce379  lea     rdx, [rbp+var_20]
0x1801ce37d  lea     rcx, [rbp+arg_0]; string
0x1801ce381  mov     [rbp+var_20], rax
0x1801ce385  mov     [rbp+arg_0], r12
0x1801ce389  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ce38e  mov     ebx, eax
0x1801ce390  test    eax, eax
0x1801ce392  js      short loc_1801CE3A4
0x1801ce394  mov     rax, [rbp+arg_0]
0x1801ce398  mov     ecx, r12d
0x1801ce39b  mov     [rbp+arg_0], rcx
0x1801ce39f  mov     [r15], rax
0x1801ce3a2  jmp     short loc_1801CE3A8
0x1801ce3a4  mov     rcx, [rbp+arg_0]; string
0x1801ce3a8  call    cs:__imp_WindowsDeleteString
0x1801ce3ae  lea     rcx, [rbp+var_18]
0x1801ce3b2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801ce3b7  mov     rcx, [rbp+string]; string
0x1801ce3bb  call    cs:__imp_WindowsDeleteString
0x1801ce3c1  mov     rcx, [rbp+arg_10]; string
0x1801ce3c5  call    cs:__imp_WindowsDeleteString
0x1801ce3cb  mov     rcx, [rbp+arg_18]; string
0x1801ce3cf  call    cs:__imp_WindowsDeleteString
0x1801ce3d5  mov     rcx, [rbp+var_30]; string
0x1801ce3d9  call    cs:__imp_WindowsDeleteString
0x1801ce3df  mov     rcx, [rbp+var_28]; string
0x1801ce3e3  call    cs:__imp_WindowsDeleteString
0x1801ce3e9  mov     eax, ebx
0x1801ce3eb  add     rsp, 70h
0x1801ce3ef  pop     r15
0x1801ce3f1  pop     r14
0x1801ce3f3  pop     r12
0x1801ce3f5  pop     rdi
0x1801ce3f6  pop     rsi
0x1801ce3f7  pop     rbx
0x1801ce3f8  pop     rbp
0x1801ce3f9  retn
```
