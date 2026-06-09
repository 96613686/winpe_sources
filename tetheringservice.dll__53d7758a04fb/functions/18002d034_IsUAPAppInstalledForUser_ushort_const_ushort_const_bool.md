# IsUAPAppInstalledForUser(ushort const *,ushort const *,bool *)

- ea: `0x18002d034`
- end: `0x18002d481`
- name: `?IsUAPAppInstalledForUser@@YAJPEBG0PEA_N@Z`
- size: `1101`
- prototype: `__int64 __fastcall(PCNZWCH sourceString, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002d868`

## callees

- `0x180002590`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000bfb4`
- `0x1800256cc`
- `0x18002d034`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002d16e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002d229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002d16e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002d229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d0bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d0bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002d255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d13f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d3ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d13f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d3ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d442`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d0d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d272`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d0d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d272`

## pseudocode

```c
__int64 __fastcall IsUAPAppInstalledForUser(PCNZWCH sourceString, const unsigned __int16 *a2, bool *a3)
{
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int ActivationFactory; // eax
  __int64 v10; // r9
  HRESULT v11; // ebx
  TetheringServiceTelemetry *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rbx
  UINT32 v17; // edx
  const WCHAR *v18; // rcx
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // eax
  TetheringServiceTelemetry *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  _BYTE v29[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v30; // [rsp+38h] [rbp-31h] BYREF
  HSTRING v31; // [rsp+40h] [rbp-29h] BYREF
  __int64 v32; // [rsp+48h] [rbp-21h] BYREF
  HSTRING v33; // [rsp+50h] [rbp-19h] BYREF
  __int64 v34; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
  }
  *a3 = 0;
  v33 = 0;
  v34 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    JUMPOUT(0x18002D480LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v34);
  v11 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_62;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_56;
    v13 = 55;
    goto LABEL_9;
  }
  v15 = -1;
  if ( a2 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a2[v16] );
    if ( v16 > 0xFFFFFFFF )
    {
      v11 = -2147024362;
      goto LABEL_19;
    }
    WindowsDeleteString(v33);
    v17 = v16;
    v18 = a2;
  }
  else
  {
    WindowsDeleteString(v33);
    v17 = 0;
    v18 = &::sourceString;
  }
  v33 = 0;
  v11 = WindowsCreateString(v18, v17, &v33);
LABEL_19:
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_62;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_56;
    v13 = 56;
    v14 = (unsigned int)v11;
    goto LABEL_10;
  }
  v29[0] = 0;
  if ( sourceString )
  {
    v30 = 0;
    v31 = 0;
    do
      ++v15;
    while ( sourceString[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      v11 = -2147024362;
    }
    else
    {
      WindowsDeleteString(0);
      v31 = 0;
      v11 = WindowsCreateString(sourceString, v15, &v31);
      if ( v11 >= 0 )
      {
        v32 = 0;
        string = 0;
        v19 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.User", 0x25u, &hstringHeader, &string);
        if ( v19 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
          __debugbreak();
        }
        v22 = RoGetActivationFactory(string, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v32);
        v11 = v22;
        if ( v22 >= 0 )
        {
          v22 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v32 + 80LL))(v32, v31, &v30);
          v11 = v22;
          if ( v22 >= 0 )
          {
            v22 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING, _BYTE *))(*(_QWORD *)v34 + 184LL))(
                    v34,
                    v30,
                    v33,
                    v29);
            v11 = v22;
            if ( v22 >= 0 )
            {
              *a3 = v29[0] != 0;
            }
            else
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v24 = 60;
                goto LABEL_37;
              }
            }
          }
          else
          {
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v24 = 59;
              goto LABEL_37;
            }
          }
        }
        else
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v24 = 58;
LABEL_37:
            WPP_SF_d(*((_QWORD *)v23 + 2), v24, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, (unsigned int)v22);
          }
        }
        v25 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
LABEL_53:
        WindowsDeleteString(v31);
        v26 = v30;
        v31 = 0;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        goto LABEL_55;
      }
    }
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids,
        (unsigned int)v11);
    }
    goto LABEL_53;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _BYTE *))(*(_QWORD *)v34 + 184LL))(
                        v34,
                        0,
                        v33,
                        v29);
  v11 = ActivationFactory;
  if ( ActivationFactory >= 0 )
    goto LABEL_55;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_62;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 61;
LABEL_9:
    v14 = (unsigned int)ActivationFactory;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v14);
LABEL_55:
    v12 = WPP_GLOBAL_Control;
  }
LABEL_56:
  if ( v12 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v12 + 28) & 8) != 0 )
    {
      LOBYTE(v10) = *a3;
      WPP_SF_c(*((_QWORD *)v12 + 2), 62, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v10);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)v12 + 2), 63, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, (unsigned int)v11);
  }
LABEL_62:
  v27 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  WindowsDeleteString(v33);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002d034  mov     [rsp-8+arg_18], rbx
0x18002d039  push    rbp
0x18002d03a  push    rsi
0x18002d03b  push    rdi
0x18002d03c  push    r12
0x18002d03e  push    r13
0x18002d040  push    r14
0x18002d042  push    r15
0x18002d044  lea     rbp, [rsp-27h]
0x18002d049  sub     rsp, 90h
0x18002d050  mov     rax, cs:__security_cookie
0x18002d057  xor     rax, rsp
0x18002d05a  mov     [rbp+57h+var_40], rax
0x18002d05e  mov     r15, r8
0x18002d061  mov     rsi, rdx
0x18002d064  mov     r14, rcx
0x18002d067  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d06e  lea     r13, WPP_GLOBAL_Control
0x18002d075  cmp     rcx, r13
0x18002d078  jz      short loc_18002D095
0x18002d07a  test    byte ptr [rcx+1Ch], 8
0x18002d07e  jz      short loc_18002D095
0x18002d080  mov     rcx, [rcx+10h]
0x18002d084  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d08b  mov     edx, 36h ; '6'
0x18002d090  call    WPP_SF_
0x18002d095  xor     r12d, r12d
0x18002d098  lea     r9, [rbp+57h+string]; string
0x18002d09c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002d0a0  mov     [r15], r12b
0x18002d0a3  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18002d0aa  mov     [rbp+57h+var_70], r12
0x18002d0ae  mov     [rbp+57h+var_68], r12
0x18002d0b2  lea     edx, [r12+2Ch]; length
0x18002d0b7  mov     [rbp+57h+string], r12
0x18002d0bb  call    cs:__imp_WindowsCreateStringReference
0x18002d0c1  test    eax, eax
0x18002d0c3  js      loc_18002D479
0x18002d0c9  mov     rcx, [rbp+57h+string]
0x18002d0cd  lea     r8, [rbp+57h+var_68]
0x18002d0d1  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18002d0d8  call    cs:__imp_RoGetActivationFactory
0x18002d0de  mov     ebx, eax
0x18002d0e0  test    eax, eax
0x18002d0e2  jns     short loc_18002D11B
0x18002d0e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0eb  cmp     rcx, r13
0x18002d0ee  jz      loc_18002D425
0x18002d0f4  test    byte ptr [rcx+1Ch], 1
0x18002d0f8  jz      loc_18002D3D8
0x18002d0fe  lea     edx, [r12+37h]
0x18002d103  mov     r9d, eax
0x18002d106  mov     rcx, [rcx+10h]
0x18002d10a  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d111  call    WPP_SF_d
0x18002d116  jmp     loc_18002D3D1
0x18002d11b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002d11f  mov     eax, 0FFFFFFFFh
0x18002d124  test    rsi, rsi
0x18002d127  jz      short loc_18002D153
0x18002d129  mov     rbx, rdi
0x18002d12c  inc     rbx
0x18002d12f  cmp     [rsi+rbx*2], r12w
0x18002d134  jnz     short loc_18002D12C
0x18002d136  cmp     rbx, rax
0x18002d139  ja      short loc_18002D14C
0x18002d13b  mov     rcx, [rbp+57h+var_70]; string
0x18002d13f  call    cs:__imp_WindowsDeleteString
0x18002d145  mov     edx, ebx
0x18002d147  mov     rcx, rsi
0x18002d14a  jmp     short loc_18002D166
0x18002d14c  mov     ebx, 80070216h
0x18002d151  jmp     short loc_18002D17B
0x18002d153  mov     rcx, [rbp+57h+var_70]; string
0x18002d157  call    cs:__imp_WindowsDeleteString
0x18002d15d  xor     edx, edx; length
0x18002d15f  lea     rcx, sourceString; sourceString
0x18002d166  lea     r8, [rbp+57h+var_70]; string
0x18002d16a  mov     [rbp+57h+var_70], r12
0x18002d16e  call    cs:__imp_WindowsCreateString
0x18002d174  mov     ebx, eax
0x18002d176  mov     eax, 0FFFFFFFFh
0x18002d17b  test    ebx, ebx
0x18002d17d  jns     short loc_18002D1A6
0x18002d17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d186  cmp     rcx, r13
0x18002d189  jz      loc_18002D425
0x18002d18f  test    byte ptr [rcx+1Ch], 1
0x18002d193  jz      loc_18002D3D8
0x18002d199  mov     edx, 38h ; '8'
0x18002d19e  mov     r9d, ebx
0x18002d1a1  jmp     loc_18002D106
0x18002d1a6  mov     [rbp+57h+var_90], r12b
0x18002d1aa  test    r14, r14
0x18002d1ad  jnz     short loc_18002D1F9
0x18002d1af  mov     rcx, [rbp+57h+var_68]
0x18002d1b3  lea     r9, [rbp+57h+var_90]
0x18002d1b7  mov     r8, [rbp+57h+var_70]
0x18002d1bb  xor     edx, edx
0x18002d1bd  mov     rax, [rcx]
0x18002d1c0  mov     rax, [rax+0B8h]
0x18002d1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1cc  mov     ebx, eax
0x18002d1ce  test    eax, eax
0x18002d1d0  jns     loc_18002D3D1
0x18002d1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1dd  cmp     rcx, r13
0x18002d1e0  jz      loc_18002D425
0x18002d1e6  test    byte ptr [rcx+1Ch], 1
0x18002d1ea  jz      loc_18002D3D8
0x18002d1f0  lea     edx, [r14+3Dh]
0x18002d1f4  jmp     loc_18002D103
0x18002d1f9  mov     [rbp+57h+var_88], r12
0x18002d1fd  mov     [rbp+57h+var_80], r12
0x18002d201  inc     rdi
0x18002d204  cmp     [r14+rdi*2], r12w
0x18002d209  jnz     short loc_18002D201
0x18002d20b  cmp     rdi, rax
0x18002d20e  ja      loc_18002D37B
0x18002d214  xor     ecx, ecx; string
0x18002d216  call    cs:__imp_WindowsDeleteString
0x18002d21c  mov     edx, edi; length
0x18002d21e  mov     [rbp+57h+var_80], r12
0x18002d222  lea     r8, [rbp+57h+var_80]; string
0x18002d226  mov     rcx, r14; sourceString
0x18002d229  call    cs:__imp_WindowsCreateString
0x18002d22f  mov     ebx, eax
0x18002d231  test    eax, eax
0x18002d233  js      loc_18002D380
0x18002d239  lea     r9, [rbp+57h+string]; string
0x18002d23d  mov     [rbp+57h+var_78], r12
0x18002d241  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002d245  mov     [rbp+57h+string], r12
0x18002d249  mov     edx, 25h ; '%'; length
0x18002d24e  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x18002d255  call    cs:__imp_WindowsCreateStringReference
0x18002d25b  test    eax, eax
0x18002d25d  js      loc_18002D471
0x18002d263  mov     rcx, [rbp+57h+string]
0x18002d267  lea     r8, [rbp+57h+var_78]
0x18002d26b  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x18002d272  call    cs:__imp_RoGetActivationFactory
0x18002d278  mov     ebx, eax
0x18002d27a  test    eax, eax
0x18002d27c  jns     short loc_18002D2CA
0x18002d27e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d285  cmp     rcx, r13
0x18002d288  jz      short loc_18002D2A8
0x18002d28a  test    byte ptr [rcx+1Ch], 1
0x18002d28e  jz      short loc_18002D2A8
0x18002d290  mov     edx, 3Ah ; ':'
0x18002d295  mov     rcx, [rcx+10h]
0x18002d299  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d2a0  mov     r9d, eax
0x18002d2a3  call    WPP_SF_d
0x18002d2a8  mov     rcx, [rbp+57h+var_78]
0x18002d2ac  test    rcx, rcx
0x18002d2af  jz      loc_18002D3AA
0x18002d2b5  mov     [rbp+57h+var_78], r12
0x18002d2b9  mov     rax, [rcx]
0x18002d2bc  mov     rax, [rax+10h]
0x18002d2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2c5  jmp     loc_18002D3AA
0x18002d2ca  mov     rbx, [rbp+57h+var_78]
0x18002d2ce  mov     rcx, [rbp+57h+var_88]
0x18002d2d2  mov     rax, [rbx]
0x18002d2d5  mov     rdi, [rax+50h]
0x18002d2d9  test    rcx, rcx
0x18002d2dc  jz      short loc_18002D2EE
0x18002d2de  mov     [rbp+57h+var_88], r12
0x18002d2e2  mov     rdx, [rcx]
0x18002d2e5  mov     rax, [rdx+10h]
0x18002d2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2ee  mov     rdx, [rbp+57h+var_80]
0x18002d2f2  lea     r8, [rbp+57h+var_88]
0x18002d2f6  mov     rcx, rbx
0x18002d2f9  mov     rax, rdi
0x18002d2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d301  mov     ebx, eax
0x18002d303  test    eax, eax
0x18002d305  jns     short loc_18002D323
0x18002d307  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d30e  cmp     rcx, r13
0x18002d311  jz      short loc_18002D2A8
0x18002d313  test    byte ptr [rcx+1Ch], 1
0x18002d317  jz      short loc_18002D2A8
0x18002d319  mov     edx, 3Bh ; ';'
0x18002d31e  jmp     loc_18002D295
0x18002d323  mov     rcx, [rbp+57h+var_68]
0x18002d327  lea     r9, [rbp+57h+var_90]
0x18002d32b  mov     r8, [rbp+57h+var_70]
0x18002d32f  mov     rdx, [rbp+57h+var_88]
0x18002d333  mov     rax, [rcx]
0x18002d336  mov     rax, [rax+0B8h]
0x18002d33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d342  mov     ebx, eax
0x18002d344  test    eax, eax
0x18002d346  jns     short loc_18002D36C
0x18002d348  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d34f  cmp     rcx, r13
0x18002d352  jz      loc_18002D2A8
0x18002d358  test    byte ptr [rcx+1Ch], 1
0x18002d35c  jz      loc_18002D2A8
0x18002d362  mov     edx, 3Ch ; '<'
0x18002d367  jmp     loc_18002D295
0x18002d36c  cmp     [rbp+57h+var_90], r12b
0x18002d370  setnz   al
0x18002d373  mov     [r15], al
0x18002d376  jmp     loc_18002D2A8
0x18002d37b  mov     ebx, 80070216h
0x18002d380  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d387  cmp     rcx, r13
0x18002d38a  jz      short loc_18002D3AA
0x18002d38c  test    byte ptr [rcx+1Ch], 1
0x18002d390  jz      short loc_18002D3AA
0x18002d392  mov     rcx, [rcx+10h]
0x18002d396  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d39d  mov     edx, 39h ; '9'
0x18002d3a2  mov     r9d, ebx
0x18002d3a5  call    WPP_SF_d
0x18002d3aa  mov     rcx, [rbp+57h+var_80]; string
0x18002d3ae  call    cs:__imp_WindowsDeleteString
0x18002d3b4  mov     rcx, [rbp+57h+var_88]
0x18002d3b8  mov     [rbp+57h+var_80], r12
0x18002d3bc  test    rcx, rcx
0x18002d3bf  jz      short loc_18002D3D1
0x18002d3c1  mov     [rbp+57h+var_88], r12
0x18002d3c5  mov     rax, [rcx]
0x18002d3c8  mov     rax, [rax+10h]
0x18002d3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3d8  cmp     rcx, r13
0x18002d3db  jz      short loc_18002D425
0x18002d3dd  test    byte ptr [rcx+1Ch], 8
0x18002d3e1  jz      short loc_18002D402
0x18002d3e3  mov     r9b, [r15]
0x18002d3e6  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d3ed  mov     rcx, [rcx+10h]
0x18002d3f1  mov     edx, 3Eh ; '>'
0x18002d3f6  call    WPP_SF_c
0x18002d3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d402  cmp     rcx, r13
0x18002d405  jz      short loc_18002D425
0x18002d407  test    byte ptr [rcx+1Ch], 8
0x18002d40b  jz      short loc_18002D425
0x18002d40d  mov     rcx, [rcx+10h]
0x18002d411  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d418  mov     edx, 3Fh ; '?'
0x18002d41d  mov     r9d, ebx
0x18002d420  call    WPP_SF_d
0x18002d425  mov     rcx, [rbp+57h+var_68]
0x18002d429  test    rcx, rcx
0x18002d42c  jz      short loc_18002D43E
0x18002d42e  mov     [rbp+57h+var_68], r12
0x18002d432  mov     rax, [rcx]
0x18002d435  mov     rax, [rax+10h]
0x18002d439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d43e  mov     rcx, [rbp+57h+var_70]; string
0x18002d442  call    cs:__imp_WindowsDeleteString
0x18002d448  mov     eax, ebx
0x18002d44a  mov     rcx, [rbp+57h+var_40]
0x18002d44e  xor     rcx, rsp; StackCookie
0x18002d451  call    __security_check_cookie
0x18002d456  mov     rbx, [rsp+0C0h+arg_18]
0x18002d45e  add     rsp, 90h
0x18002d465  pop     r15
0x18002d467  pop     r14
0x18002d469  pop     r13
0x18002d46b  pop     r12
0x18002d46d  pop     rdi
0x18002d46e  pop     rsi
0x18002d46f  pop     rbp
0x18002d470  retn
0x18002d471  mov     ecx, eax; this
0x18002d473  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002d478  int     3; Trap to Debugger
0x18002d479  mov     ecx, eax; this
0x18002d47b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
