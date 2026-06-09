# _lambda_c3b66c2853dd3999b1f49c259e2ee05d_::operator()(void)

- ea: `0x14002d640`
- end: `0x14002da2b`
- name: `??R_lambda_c3b66c2853dd3999b1f49c259e2ee05d_@@QEBA@XZ`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002f2c0`

## callees

- `0x140005530`
- `0x140006314`
- `0x140006338`
- `0x140009858`
- `0x14000b744`
- `0x14000c010`
- `0x14000ccac`
- `0x14000e07c`
- `0x140010e18`
- `0x14001f6b4`
- `0x14002a754`
- `0x14002c2e4`
- `0x14002ca90`
- `0x14002cf68`
- `0x14002d640`
- `0x14002f160`
- `0x140060764`
- `0x140060f58`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x14002d7a6`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x14002d7a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002d697`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002d697`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall _lambda_c3b66c2853dd3999b1f49c259e2ee05d_::operator()(__int64 **a1)
{
  HRESULT v2; // eax
  int v3; // edi
  int v4; // eax
  int v5; // edi
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // edi
  Private::Format *v10; // rbx
  unsigned __int64 v11; // r8
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdi
  bool v15; // bl
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 *v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rcx
  LPVOID v22; // rcx
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v30[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+78h] [rbp-88h]
  char *pExceptionObject[5]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v33[4]; // [rsp+B0h] [rbp-50h] BYREF
  char *v34[6]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD v35[72]; // [rsp+100h] [rbp+0h] BYREF

  ppv = 0;
  v2 = CoCreateInstance(
         &GUID_69fd9e81_bbab_464f_9670_1180b07a665b,
         0,
         0x17u,
         &GUID_00000000_0000_0000_c000_000000000046,
         &ppv);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_e7b9cb8ab80e3315707dab84e44f73be_Traceguids,
        (unsigned int)v2);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v3);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v24 = 0;
  v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
         ppv,
         &GUID_5d0d3d28_d388_4773_90b5_7d509cbbe251,
         &v24);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_e7b9cb8ab80e3315707dab84e44f73be_Traceguids,
        (unsigned int)v4);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v23 = 0;
  v26 = 0;
  std::wstring::wstring((__int64)v33, (__int64)(*a1 + 13));
  v6 = (const unsigned __int16 *)v33;
  if ( v33[3] > (unsigned __int16 *)7 )
    v6 = v33[0];
  _bstr_t::_bstr_t((_bstr_t *)&v27, v6);
  std::wstring::~wstring((char **)v33);
  if ( v27 )
    v7 = *v27;
  else
    v7 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int64 *))(*(_QWORD *)v24 + 40LL))(v24, v7, &v23, &v26);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_e7b9cb8ab80e3315707dab84e44f73be_Traceguids,
        (unsigned int)v8);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v9);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *(_OWORD *)v30 = 0;
  v31 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)v30,
    L"Engine reconnected - StateFlags:{0} NextChangeTime:{1}",
    0x36u);
  v10 = (Private::Format *)StringAlgo::FormatString(v34, v30);
  memset_0(v35, 0, 0x82u);
  _o__ui64tow_s(v23, v35, 65);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  v11 = -1;
  do
    ++v11;
  while ( v35[v11] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v30, v35, v11);
  v12 = (const unsigned __int16 *)v30;
  if ( *((_QWORD *)&v31 + 1) > 7u )
    v12 = v30[0];
  Private::Format::Replace(v10, v12);
  std::wstring::~wstring((char **)v30);
  wpc::Logging::ToShortDebugString<_FILETIME>(pExceptionObject, &v26);
  v13 = Private::Format::operator%<std::wstring>(v10);
  wpc::UI::Logging::MonitorUILogger::LogMessage(v13);
  std::wstring::~wstring(pExceptionObject);
  std::wstring::~wstring(v34);
  v14 = **a1;
  v29 = v26;
  v15 = 1;
  LOBYTE(v30[0]) = v23 & 1;
  BYTE1(v30[0]) = (v23 & 2) != 0;
  v28 = &v29;
  stdext::try_execute<_lambda_d7af73a1599184f0b8e6a0613d31fdf1_>(&v30[1], &v28);
  LOBYTE(v17) = v30[0];
  if ( LOBYTE(v30[0]) )
    v15 = BYTE1(v30[0]) != 0;
  LOBYTE(v16) = v15;
  wpc::TimeLimits::UI::UICallbackImpl::UpdateEnforcementState(v14, v17, v16, &v30[1]);
  v18 = *a1;
  v19 = v24;
  if ( (*a1)[2] != v24 )
  {
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
    v20 = v18[2];
    v18[2] = v19;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  _bstr_t::~_bstr_t((_bstr_t *)&v27);
  v21 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
  }
}

```

## disassembly

```asm
0x14002d640  mov     [rsp-8+arg_8], rbx
0x14002d645  mov     [rsp-8+arg_10], rsi
0x14002d64a  push    rbp
0x14002d64b  push    rdi
0x14002d64c  push    r14
0x14002d64e  lea     rbp, [rsp-0A0h]
0x14002d656  sub     rsp, 1A0h
0x14002d65d  mov     rax, cs:__security_cookie
0x14002d664  xor     rax, rsp
0x14002d667  mov     [rbp+0B0h+var_20], rax
0x14002d66e  mov     rsi, rcx
0x14002d671  xor     r14d, r14d
0x14002d674  mov     [rsp+1B0h+var_170], r14
0x14002d679  lea     rax, [rsp+1B0h+var_170]
0x14002d67e  mov     [rsp+1B0h+ppv], rax; ppv
0x14002d683  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14002d68a  xor     edx, edx; pUnkOuter
0x14002d68c  lea     r8d, [r14+17h]; dwClsContext
0x14002d690  lea     rcx, _GUID_69fd9e81_bbab_464f_9670_1180b07a665b; rclsid
0x14002d697  call    cs:__imp_CoCreateInstance
0x14002d69d  mov     edi, eax
0x14002d69f  test    eax, eax
0x14002d6a1  js      loc_14002D98F
0x14002d6a7  mov     [rsp+1B0h+var_178], r14
0x14002d6ac  mov     rcx, [rsp+1B0h+var_170]
0x14002d6b1  mov     rax, [rcx]
0x14002d6b4  lea     r8, [rsp+1B0h+var_178]
0x14002d6b9  lea     rdx, _GUID_5d0d3d28_d388_4773_90b5_7d509cbbe251
0x14002d6c0  mov     rax, [rax]
0x14002d6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d6c8  mov     edi, eax
0x14002d6ca  test    eax, eax
0x14002d6cc  js      loc_14002D9DD
0x14002d6d2  mov     [rsp+1B0h+var_180], r14d
0x14002d6d7  mov     [rsp+1B0h+var_168], r14
0x14002d6dc  mov     rdx, [rsi]
0x14002d6df  add     rdx, 68h ; 'h'
0x14002d6e3  lea     rcx, [rbp+0B0h+var_100]
0x14002d6e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002d6ec  nop
0x14002d6ed  lea     rdx, [rbp+0B0h+var_100]
0x14002d6f1  cmp     [rbp+0B0h+var_E8], 7
0x14002d6f6  cmova   rdx, [rbp+0B0h+var_100]; unsigned __int16 *
0x14002d6fb  lea     rcx, [rsp+1B0h+var_160]; this
0x14002d700  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14002d705  nop
0x14002d706  lea     rcx, [rbp+0B0h+var_100]
0x14002d70a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002d70f  mov     rcx, [rsp+1B0h+var_178]
0x14002d714  mov     rax, [rcx]
0x14002d717  mov     r10, [rax+28h]
0x14002d71b  mov     rax, [rsp+1B0h+var_160]
0x14002d720  test    rax, rax
0x14002d723  jz      short loc_14002D72A
0x14002d725  mov     rdx, [rax]
0x14002d728  jmp     short loc_14002D72D
0x14002d72a  mov     rdx, r14
0x14002d72d  lea     r9, [rsp+1B0h+var_168]
0x14002d732  lea     r8, [rsp+1B0h+var_180]
0x14002d737  mov     rax, r10
0x14002d73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d73f  mov     edi, eax
0x14002d741  test    eax, eax
0x14002d743  js      loc_14002D941
0x14002d749  xorps   xmm0, xmm0
0x14002d74c  movups  xmmword ptr [rsp+1B0h+var_148], xmm0
0x14002d751  mov     qword ptr [rsp+1B0h+var_138], r14
0x14002d756  mov     qword ptr [rbp+0B0h+var_138+8], r14
0x14002d75a  mov     r8d, 36h ; '6'
0x14002d760  lea     rdx, aEngineReconnec; "Engine reconnected - StateFlags:{0} Nex"...
0x14002d767  lea     rcx, [rsp+1B0h+var_148]
0x14002d76c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002d771  lea     rdx, [rsp+1B0h+var_148]
0x14002d776  lea     rcx, [rbp+0B0h+var_E0]
0x14002d77a  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x14002d77f  mov     rbx, rax
0x14002d782  xor     edx, edx; Val
0x14002d784  mov     r8d, 82h; Size
0x14002d78a  lea     rcx, [rbp+0B0h+var_B0]; void *
0x14002d78e  call    memset_0
0x14002d793  movsxd  rcx, [rsp+1B0h+var_180]
0x14002d798  mov     r9d, 0Ah
0x14002d79e  lea     r8d, [r9+37h]
0x14002d7a2  lea     rdx, [rbp+0B0h+var_B0]
0x14002d7a6  call    cs:__imp__o__ui64tow_s
0x14002d7ac  xorps   xmm0, xmm0
0x14002d7af  movups  xmmword ptr [rsp+1B0h+var_148], xmm0
0x14002d7b4  xorps   xmm1, xmm1
0x14002d7b7  movdqu  [rsp+1B0h+var_138], xmm1
0x14002d7bd  lea     rax, [rbp+0B0h+var_B0]
0x14002d7c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002d7c5  inc     r8
0x14002d7c8  cmp     [rax+r8*2], r14w
0x14002d7cd  jnz     short loc_14002D7C5
0x14002d7cf  lea     rdx, [rbp+0B0h+var_B0]
0x14002d7d3  lea     rcx, [rsp+1B0h+var_148]
0x14002d7d8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002d7dd  nop
0x14002d7de  lea     rdx, [rsp+1B0h+var_148]
0x14002d7e3  cmp     qword ptr [rbp+0B0h+var_138+8], 7
0x14002d7e8  cmova   rdx, [rsp+1B0h+var_148]; unsigned __int16 *
0x14002d7ee  mov     rcx, rbx; this
0x14002d7f1  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x14002d7f6  nop
0x14002d7f7  lea     rcx, [rsp+1B0h+var_148]
0x14002d7fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002d801  lea     rdx, [rsp+1B0h+var_168]
0x14002d806  lea     rcx, [rbp+0B0h+pExceptionObject]
0x14002d80a  call    ??$ToShortDebugString@U_FILETIME@@@Logging@wpc@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_FILETIME@@@Z; wpc::Logging::ToShortDebugString<_FILETIME>(_FILETIME const &)
0x14002d80f  nop
0x14002d810  mov     rdx, rax
0x14002d813  mov     rcx, rbx; this
0x14002d816  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x14002d81b  mov     rcx, rax
0x14002d81e  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x14002d823  nop
0x14002d824  lea     rcx, [rbp+0B0h+pExceptionObject]
0x14002d828  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002d82d  nop
0x14002d82e  lea     rcx, [rbp+0B0h+var_E0]
0x14002d832  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002d837  mov     rax, [rsi]
0x14002d83a  mov     rdi, [rax]
0x14002d83d  mov     ecx, [rsp+1B0h+var_180]
0x14002d841  mov     rax, [rsp+1B0h+var_168]
0x14002d846  mov     [rsp+1B0h+var_150], rax
0x14002d84b  mov     al, cl
0x14002d84d  mov     bl, 1
0x14002d84f  and     al, bl
0x14002d851  mov     byte ptr [rsp+1B0h+var_148], al
0x14002d855  shr     cl, 1
0x14002d857  and     cl, bl
0x14002d859  mov     byte ptr [rsp+1B0h+var_148+1], cl
0x14002d85d  lea     rax, [rsp+1B0h+var_150]
0x14002d862  mov     [rsp+1B0h+var_158], rax
0x14002d867  lea     rdx, [rsp+1B0h+var_158]
0x14002d86c  lea     rcx, [rsp+1B0h+var_148+8]
0x14002d871  call    ??$try_execute@V_lambda_d7af73a1599184f0b8e6a0613d31fdf1_@@@stdext@@YA?AV?$Optional@VDateTime@@@@AEBV_lambda_d7af73a1599184f0b8e6a0613d31fdf1_@@PEAPEAX@Z; stdext::try_execute<_lambda_d7af73a1599184f0b8e6a0613d31fdf1_>(_lambda_d7af73a1599184f0b8e6a0613d31fdf1_ const &,void * *)
0x14002d876  nop
0x14002d877  mov     dl, byte ptr [rsp+1B0h+var_148]
0x14002d87b  test    dl, dl
0x14002d87d  jz      short loc_14002D889
0x14002d87f  cmp     byte ptr [rsp+1B0h+var_148+1], r14b
0x14002d884  jnz     short loc_14002D889
0x14002d886  mov     bl, r14b
0x14002d889  lea     r9, [rsp+1B0h+var_148+8]
0x14002d88e  mov     r8b, bl
0x14002d891  mov     rcx, rdi
0x14002d894  call    ?UpdateEnforcementState@UICallbackImpl@UI@TimeLimits@wpc@@QEAAX_N0AEBV?$Optional@VDateTime@@@@@Z; wpc::TimeLimits::UI::UICallbackImpl::UpdateEnforcementState(bool,bool,Optional<DateTime> const &)
0x14002d899  nop
0x14002d89a  mov     rdi, [rsi]
0x14002d89d  mov     rbx, [rsp+1B0h+var_178]
0x14002d8a2  cmp     [rdi+10h], rbx
0x14002d8a6  jz      short loc_14002D8D7
0x14002d8a8  test    rbx, rbx
0x14002d8ab  jz      short loc_14002D8BD
0x14002d8ad  mov     rax, [rbx]
0x14002d8b0  mov     rcx, rbx
0x14002d8b3  mov     rax, [rax+8]
0x14002d8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d8bc  nop
0x14002d8bd  mov     rcx, [rdi+10h]
0x14002d8c1  mov     [rdi+10h], rbx
0x14002d8c5  test    rcx, rcx
0x14002d8c8  jz      short loc_14002D8D7
0x14002d8ca  mov     rax, [rcx]
0x14002d8cd  mov     rax, [rax+10h]
0x14002d8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d8d6  nop
0x14002d8d7  lea     rcx, [rsp+1B0h+var_160]; this
0x14002d8dc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002d8e1  nop
0x14002d8e2  mov     rcx, [rsp+1B0h+var_178]
0x14002d8e7  test    rcx, rcx
0x14002d8ea  jz      short loc_14002D8FE
0x14002d8ec  mov     [rsp+1B0h+var_178], r14
0x14002d8f1  mov     rax, [rcx]
0x14002d8f4  mov     rax, [rax+10h]
0x14002d8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d8fd  nop
0x14002d8fe  mov     rcx, [rsp+1B0h+var_170]
0x14002d903  test    rcx, rcx
0x14002d906  jz      short loc_14002D91A
0x14002d908  mov     [rsp+1B0h+var_170], r14
0x14002d90d  mov     rax, [rcx]
0x14002d910  mov     rax, [rax+10h]
0x14002d914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d919  nop
0x14002d91a  mov     rcx, [rbp+0B0h+var_20]
0x14002d921  xor     rcx, rsp; StackCookie
0x14002d924  call    __security_check_cookie
0x14002d929  lea     r11, [rsp+1B0h+var_10]
0x14002d931  mov     rbx, [r11+28h]
0x14002d935  mov     rsi, [r11+30h]
0x14002d939  mov     rsp, r11
0x14002d93c  pop     r14
0x14002d93e  pop     rdi
0x14002d93f  pop     rbp
0x14002d940  retn
0x14002d941  lea     rdx, WPP_GLOBAL_Control
0x14002d948  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d94f  cmp     rcx, rdx
0x14002d952  jz      short loc_14002D973
0x14002d954  mov     bl, 1
0x14002d956  test    [rcx+1Ch], bl
0x14002d959  jz      short loc_14002D973
0x14002d95b  mov     edx, 0Ch
0x14002d960  mov     r9d, edi
0x14002d963  lea     r8, WPP_e7b9cb8ab80e3315707dab84e44f73be_Traceguids
0x14002d96a  mov     rcx, [rcx+10h]
0x14002d96e  call    WPP_SF_d
0x14002d973  mov     edx, edi; int
0x14002d975  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x14002d979  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14002d97e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14002d985  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x14002d989  call    _CxxThrowException_0
0x14002d98f  lea     rdx, WPP_GLOBAL_Control
0x14002d996  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d99d  cmp     rcx, rdx
0x14002d9a0  jz      short loc_14002D9C1
0x14002d9a2  mov     bl, 1
0x14002d9a4  test    [rcx+1Ch], bl
0x14002d9a7  jz      short loc_14002D9C1
0x14002d9a9  mov     edx, 0Ah
0x14002d9ae  mov     r9d, edi
0x14002d9b1  lea     r8, WPP_e7b9cb8ab80e3315707dab84e44f73be_Traceguids
0x14002d9b8  mov     rcx, [rcx+10h]
0x14002d9bc  call    WPP_SF_d
0x14002d9c1  mov     edx, edi; int
0x14002d9c3  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x14002d9c7  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14002d9cc  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14002d9d3  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x14002d9d7  call    _CxxThrowException_0
0x14002d9dd  lea     rdx, WPP_GLOBAL_Control
0x14002d9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d9eb  cmp     rcx, rdx
0x14002d9ee  jz      short loc_14002DA0F
0x14002d9f0  mov     bl, 1
0x14002d9f2  test    [rcx+1Ch], bl
0x14002d9f5  jz      short loc_14002DA0F
0x14002d9f7  mov     edx, 0Bh
0x14002d9fc  mov     r9d, edi
0x14002d9ff  lea     r8, WPP_e7b9cb8ab80e3315707dab84e44f73be_Traceguids
0x14002da06  mov     rcx, [rcx+10h]
0x14002da0a  call    WPP_SF_d
0x14002da0f  mov     edx, edi; int
0x14002da11  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x14002da15  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14002da1a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14002da21  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x14002da25  call    _CxxThrowException_0
```
