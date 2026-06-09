# CUpdatePolicyReader::Start(IUnknown *,wchar_t *)

- ea: `0x18000cfc0`
- end: `0x18000d1a6`
- name: `?Start@CUpdatePolicyReader@@UEAAJPEAUIUnknown@@PEA_W@Z`
- size: `486`
- prototype: `__int64 __fastcall(CUpdatePolicyReader *__hidden this, struct IUnknown *, wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000aac0`
- `0x18000cfc0`
- `0x18000e0dc`
- `0x180010260`
- `0x1800236b8`
- `0x18002402c`
- `0x18002ffd0`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d080`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d112`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d080`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d112`

## string_xrefs

- `0x18000d006`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000d046`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000d0b3`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`

## pseudocode

```c
__int64 __fastcall CUpdatePolicyReader::Start(CUpdatePolicyReader *this, struct IUnknown *a2, wchar_t *a3)
{
  unsigned int v4; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  int v6; // eax
  char v7; // di
  ULONGLONG TickCount64; // r14
  int refreshed; // eax
  int v10; // ebx
  __int64 v11; // rdx
  __int128 *v12; // rax
  int v14; // [rsp+20h] [rbp-60h]
  ULONGLONG v15; // [rsp+30h] [rbp-50h] BYREF
  __int128 *v16; // [rsp+38h] [rbp-48h] BYREF
  char v17; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v18[3]; // [rsp+41h] [rbp-3Fh] BYREF
  int v19; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 v20; // [rsp+48h] [rbp-38h] BYREF
  __int128 v21; // [rsp+50h] [rbp-30h] BYREF
  __m128i si128; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
      (const char *)0x80070057LL,
      v14);
    return v4;
  }
  lpVtbl = a2->lpVtbl;
  v20 = 0;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         &v20);
  v4 = v6;
  if ( v6 >= 0 )
  {
    v21 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v21) = 0;
    v7 = 0;
    v18[0] = 0;
    v17 = 0;
    TickCount64 = GetTickCount64();
    v19 = 0;
    refreshed = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)this - 1) + 72LL))((char *)this - 8, &v19);
    v10 = refreshed;
    if ( refreshed < 0 )
    {
      v11 = 279;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
        (const char *)(unsigned int)refreshed,
        v14);
      goto LABEL_14;
    }
    if ( v19 )
    {
      v7 = 1;
      refreshed = PolicyRefreshCacheHelper::WaitForGPWNFEvents();
      v10 = refreshed;
      if ( refreshed < 0 )
      {
        v11 = 285;
        goto LABEL_7;
      }
      refreshed = PolicyRefreshCacheHelper::RefreshGPCache(&v21, v18, &v17);
      v10 = refreshed;
      if ( refreshed < 0 )
      {
        v11 = 289;
        goto LABEL_7;
      }
    }
    v10 = 0;
LABEL_14:
    v19 = v10;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 32LL))(v20, (unsigned int)v10);
    v15 = GetTickCount64() - TickCount64;
    if ( v7 || v10 < 0 )
    {
      v12 = &v21;
      if ( si128.m128i_i64[1] > 7uLL )
        v12 = (__int128 *)v21;
      v16 = v12;
      UpdatePolicyTelemetry::GPPolicyRefresh<wchar_t const *,bool &,bool &,unsigned __int64 &,long &>(
        (unsigned int)&v16,
        (unsigned int)v18,
        (unsigned int)&v17,
        (unsigned int)&v15,
        (__int64)&v19);
    }
    v4 = 0;
    std::wstring::~wstring(&v21);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10A,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
    (const char *)(unsigned int)v6,
    v14);
LABEL_20:
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return v4;
}

```

## disassembly

```asm
0x18000cfc0  mov     [rsp-18h+arg_0], rbx
0x18000cfc5  mov     [rsp-18h+arg_10], rsi
0x18000cfca  mov     [rsp-18h+arg_18], rdi
0x18000cfcf  push    rbp
0x18000cfd0  push    r14
0x18000cfd2  push    r15
0x18000cfd4  mov     rbp, rsp
0x18000cfd7  sub     rsp, 80h
0x18000cfde  mov     rax, cs:__security_cookie
0x18000cfe5  xor     rax, rsp
0x18000cfe8  mov     [rbp+var_10], rax
0x18000cfec  mov     r9, rdx
0x18000cfef  mov     rsi, rcx
0x18000cff2  xor     r15d, r15d
0x18000cff5  test    rdx, rdx
0x18000cff8  jnz     short loc_18000D01C
0x18000cffa  mov     rcx, [rbp+18h]; this
0x18000cffe  mov     ebx, 80070057h
0x18000d003  mov     r9d, ebx; char *
0x18000d006  lea     r8, aCW1SSrcClientP_7; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18000d00d  mov     edx, 105h; void *
0x18000d012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d017  jmp     loc_18000D17B
0x18000d01c  mov     rax, [rdx]
0x18000d01f  mov     [rbp+var_38], r15
0x18000d023  lea     r8, [rbp+var_38]
0x18000d027  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000d02e  mov     rcx, r9
0x18000d031  mov     rax, [rax]
0x18000d034  call    _guard_dispatch_icall
0x18000d039  mov     ebx, eax
0x18000d03b  test    eax, eax
0x18000d03d  jns     short loc_18000D05C
0x18000d03f  mov     rcx, [rbp+18h]; this
0x18000d043  mov     r9d, eax; char *
0x18000d046  lea     r8, aCW1SSrcClientP_7; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18000d04d  mov     edx, 10Ah; void *
0x18000d052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d057  jmp     loc_18000D165
0x18000d05c  xorps   xmm0, xmm0
0x18000d05f  movups  [rbp+var_30], xmm0
0x18000d063  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000d06b  movdqu  [rbp+var_20], xmm1
0x18000d070  mov     word ptr [rbp+var_30], r15w
0x18000d075  mov     dil, r15b
0x18000d078  mov     [rbp+var_3F], r15b
0x18000d07c  mov     [rbp+var_40], r15b
0x18000d080  call    cs:__imp_GetTickCount64
0x18000d086  mov     r14, rax
0x18000d089  lea     rcx, [rsi-8]
0x18000d08d  mov     [rbp+var_3C], r15d
0x18000d091  mov     rdx, [rcx]
0x18000d094  mov     rax, [rdx+48h]
0x18000d098  lea     rdx, [rbp+var_3C]
0x18000d09c  call    _guard_dispatch_icall
0x18000d0a1  mov     ebx, eax
0x18000d0a3  test    eax, eax
0x18000d0a5  jns     short loc_18000D0C1
0x18000d0a7  mov     edx, 117h; void *
0x18000d0ac  mov     rcx, [rbp+18h]; this
0x18000d0b0  mov     r9d, eax; char *
0x18000d0b3  lea     r8, aCW1SSrcClientP_7; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18000d0ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0bf  jmp     short loc_18000D0FD
0x18000d0c1  cmp     [rbp+var_3C], r15d
0x18000d0c5  jz      short loc_18000D0FA
0x18000d0c7  mov     dil, 1
0x18000d0ca  call    ?WaitForGPWNFEvents@PolicyRefreshCacheHelper@@SAJXZ; PolicyRefreshCacheHelper::WaitForGPWNFEvents(void)
0x18000d0cf  mov     ebx, eax
0x18000d0d1  test    eax, eax
0x18000d0d3  jns     short loc_18000D0DC
0x18000d0d5  mov     edx, 11Dh
0x18000d0da  jmp     short loc_18000D0AC
0x18000d0dc  lea     r8, [rbp+var_40]
0x18000d0e0  lea     rdx, [rbp+var_3F]
0x18000d0e4  lea     rcx, [rbp+var_30]
0x18000d0e8  call    ?RefreshGPCache@PolicyRefreshCacheHelper@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_N1@Z; PolicyRefreshCacheHelper::RefreshGPCache(std::wstring &,bool &,bool &)
0x18000d0ed  mov     ebx, eax
0x18000d0ef  test    eax, eax
0x18000d0f1  jns     short loc_18000D0FA
0x18000d0f3  mov     edx, 121h
0x18000d0f8  jmp     short loc_18000D0AC
0x18000d0fa  mov     ebx, r15d
0x18000d0fd  mov     [rbp+var_3C], ebx
0x18000d100  mov     rcx, [rbp+var_38]
0x18000d104  mov     rax, [rcx]
0x18000d107  mov     edx, ebx
0x18000d109  mov     rax, [rax+20h]
0x18000d10d  call    _guard_dispatch_icall
0x18000d112  call    cs:__imp_GetTickCount64
0x18000d118  sub     rax, r14
0x18000d11b  mov     [rbp+var_50], rax
0x18000d11f  test    dil, dil
0x18000d122  jnz     short loc_18000D128
0x18000d124  test    ebx, ebx
0x18000d126  jns     short loc_18000D158
0x18000d128  lea     rax, [rbp+var_30]
0x18000d12c  cmp     qword ptr [rbp+var_20+8], 7
0x18000d131  cmova   rax, qword ptr [rbp+var_30]
0x18000d136  mov     [rbp+var_48], rax
0x18000d13a  lea     rax, [rbp+var_3C]
0x18000d13e  mov     qword ptr [rsp+80h+var_60], rax
0x18000d143  lea     r9, [rbp+var_50]
0x18000d147  lea     r8, [rbp+var_40]
0x18000d14b  lea     rdx, [rbp+var_3F]
0x18000d14f  lea     rcx, [rbp+var_48]
0x18000d153  call    ??$GPPolicyRefresh@PEB_WAEA_NAEA_NAEA_KAEAJ@UpdatePolicyTelemetry@@SAX$$QEAPEB_WAEA_N1AEA_KAEAJ@Z; UpdatePolicyTelemetry::GPPolicyRefresh<wchar_t const *,bool &,bool &,unsigned __int64 &,long &>(wchar_t const * &&,bool &,bool &,unsigned __int64 &,long &)
0x18000d158  mov     ebx, r15d
0x18000d15b  lea     rcx, [rbp+var_30]; void *
0x18000d15f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d164  nop
0x18000d165  mov     rcx, [rbp+var_38]
0x18000d169  test    rcx, rcx
0x18000d16c  jz      short loc_18000D17B
0x18000d16e  mov     rdx, [rcx]
0x18000d171  mov     rax, [rdx+10h]
0x18000d175  call    _guard_dispatch_icall
0x18000d17a  nop
0x18000d17b  mov     eax, ebx
0x18000d17d  mov     rcx, [rbp+var_10]
0x18000d181  xor     rcx, rsp; StackCookie
0x18000d184  call    __security_check_cookie
0x18000d189  lea     r11, [rsp+80h+var_s0]
0x18000d191  mov     rbx, [r11+20h]
0x18000d195  mov     rsi, [r11+30h]
0x18000d199  mov     rdi, [r11+38h]
0x18000d19d  mov     rsp, r11
0x18000d1a0  pop     r15
0x18000d1a2  pop     r14
0x18000d1a4  pop     rbp
0x18000d1a5  retn
```
