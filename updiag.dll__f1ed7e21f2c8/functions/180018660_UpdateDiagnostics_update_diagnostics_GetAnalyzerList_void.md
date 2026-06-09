# UpdateDiagnostics::update_diagnostics::GetAnalyzerList(void)

- ea: `0x180018660`
- end: `0x18001882d`
- name: `?GetAnalyzerList@update_diagnostics@UpdateDiagnostics@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `461`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000f290`

## callees

- `0x180009548`
- `0x1800182dc`
- `0x1800183a8`
- `0x180018660`
- `0x180018f80`
- `0x180019080`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001876e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001876e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall UpdateDiagnostics::update_diagnostics::GetAnalyzerList(__int64 a1, __int64 *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdi
  _QWORD *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  _QWORD *v9; // rdx
  unsigned int v10; // edi
  PCWSTR StringRawBuffer; // rax
  _QWORD *v12; // rcx
  unsigned __int64 v13; // r8
  unsigned int i; // edi
  void *v15; // rcx
  int v17; // [rsp+20h] [rbp-50h]
  PCWSTR v18; // [rsp+28h] [rbp-48h] BYREF
  __int64 *v19; // [rsp+30h] [rbp-40h]
  unsigned int *v20; // [rsp+38h] [rbp-38h]
  LPVOID *p_pv; // [rsp+40h] [rbp-30h]
  char v22; // [rsp+48h] [rbp-28h]
  unsigned int v23; // [rsp+50h] [rbp-20h] BYREF
  UINT32 length; // [rsp+54h] [rbp-1Ch] BYREF
  LPVOID pv; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v19 = a2;
  pv = 0;
  v23 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, unsigned int *))(**(_QWORD **)(a1 + 8) + 40LL))(
         *(_QWORD *)(a1 + 8),
         &pv,
         &v23);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      (const char *)(unsigned int)v3,
      0);
  v20 = &v23;
  p_pv = &pv;
  v22 = 1;
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v17 = 1;
  v4 = v23;
  v5 = v23;
  if ( v23 )
  {
    v6 = std::_Allocate<16,std::_Default_allocate_traits>(32LL * v23);
    v7 = a2[1];
    v8 = *a2;
    v9 = v6;
    while ( v8 != v7 )
    {
      *(_OWORD *)v9 = 0;
      v9[2] = 0;
      v9[3] = 0;
      *(_OWORD *)v9 = *(_OWORD *)v8;
      *((_OWORD *)v9 + 1) = *(_OWORD *)(v8 + 16);
      *(_WORD *)v8 = 0;
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 7;
      v9 += 4;
      v8 += 32;
    }
    std::vector<std::filesystem::path>::_Change_array(a2, v6, 0, v5, v17, v18, v19, v20, p_pv);
    v4 = v23;
  }
  v10 = 0;
  if ( v4 )
  {
    do
    {
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)pv + v10), &length);
      v18 = StringRawBuffer;
      v12 = (_QWORD *)a2[1];
      if ( v12 == (_QWORD *)a2[2] )
      {
        std::vector<std::wstring>::_Emplace_reallocate<wchar_t const * &,unsigned int &>(a2, a2[1], &v18, &length);
      }
      else
      {
        v13 = length;
        *(_OWORD *)v12 = 0;
        v12[2] = 0;
        v12[3] = 0;
        std::wstring::_Construct<1,wchar_t const *>(v12, StringRawBuffer, v13);
        a2[1] += 32;
      }
      ++v10;
    }
    while ( v10 < v23 );
  }
  for ( i = 0; i < v23; ++i )
    WindowsDeleteString(*((HSTRING *)pv + i));
  v15 = pv;
  pv = 0;
  if ( v15 )
    CoTaskMemFree(v15);
  return a2;
}

```

## disassembly

```asm
0x180018660  mov     [rsp-28h+arg_10], rbx
0x180018665  mov     [rsp-28h+arg_18], rsi
0x18001866a  push    rbp
0x18001866b  push    rdi
0x18001866c  push    r12
0x18001866e  push    r14
0x180018670  push    r15
0x180018672  mov     rbp, rsp
0x180018675  sub     rsp, 70h
0x180018679  mov     rax, cs:__security_cookie
0x180018680  xor     rax, rsp
0x180018683  mov     [rbp+var_10], rax
0x180018687  mov     rbx, rdx
0x18001868a  mov     [rbp+var_40], rdx
0x18001868e  xor     esi, esi
0x180018690  mov     [rbp+var_50], esi
0x180018693  mov     [rbp+pv], rsi
0x180018697  mov     [rbp+var_20], esi
0x18001869a  mov     rcx, [rcx+8]
0x18001869e  mov     rax, [rcx]
0x1800186a1  lea     r8, [rbp+var_20]
0x1800186a5  lea     rdx, [rbp+pv]
0x1800186a9  mov     rax, [rax+28h]
0x1800186ad  call    _guard_dispatch_icall
0x1800186b2  mov     rcx, [rbp+28h]; this
0x1800186b6  test    eax, eax
0x1800186b8  js      loc_180018818
0x1800186be  lea     r15, [rbp+var_20]
0x1800186c2  mov     [rbp+var_38], r15
0x1800186c6  lea     r12, [rbp+pv]
0x1800186ca  mov     [rbp+var_30], r12
0x1800186ce  lea     r14d, [rsi+1]
0x1800186d2  mov     [rbp+var_28], r14b
0x1800186d6  xorps   xmm0, xmm0
0x1800186d9  movups  xmmword ptr [rbx], xmm0
0x1800186dc  mov     [rbx], rsi
0x1800186df  mov     [rbx+8], rsi
0x1800186e3  mov     [rbx+10h], rsi
0x1800186e7  mov     [rbp+var_50], r14d
0x1800186eb  mov     eax, [rbp+var_20]
0x1800186ee  mov     edi, eax
0x1800186f0  test    eax, eax
0x1800186f2  jz      short loc_180018757
0x1800186f4  mov     ecx, eax
0x1800186f6  shl     rcx, 5
0x1800186fa  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800186ff  mov     r8, [rbx+8]
0x180018703  mov     rcx, [rbx]
0x180018706  mov     rdx, rax
0x180018709  jmp     short loc_18001873E
0x18001870b  xorps   xmm0, xmm0
0x18001870e  movups  xmmword ptr [rdx], xmm0
0x180018711  mov     [rdx+10h], rsi
0x180018715  mov     [rdx+18h], rsi
0x180018719  movups  xmm0, xmmword ptr [rcx]
0x18001871c  movups  xmmword ptr [rdx], xmm0
0x18001871f  movups  xmm1, xmmword ptr [rcx+10h]
0x180018723  movups  xmmword ptr [rdx+10h], xmm1
0x180018727  mov     [rcx], si
0x18001872a  mov     [rcx+10h], rsi
0x18001872e  mov     qword ptr [rcx+18h], 7
0x180018736  lea     rdx, [rdx+20h]
0x18001873a  add     rcx, 20h ; ' '
0x18001873e  cmp     rcx, r8
0x180018741  jnz     short loc_18001870B
0x180018743  mov     r9, rdi
0x180018746  xor     r8d, r8d
0x180018749  mov     rdx, rax
0x18001874c  mov     rcx, rbx
0x18001874f  call    ?_Change_array@?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@AEAAXQEAVpath@filesystem@2@_K1@Z; std::vector<std::filesystem::path>::_Change_array(std::filesystem::path * const,unsigned __int64,unsigned __int64)
0x180018754  mov     eax, [rbp+var_20]
0x180018757  mov     edi, esi
0x180018759  test    eax, eax
0x18001875b  jz      short loc_1800187BE
0x18001875d  mov     [rbp+length], esi
0x180018760  mov     eax, edi
0x180018762  lea     rdx, [rbp+length]; length
0x180018766  mov     rcx, [rbp+pv]
0x18001876a  mov     rcx, [rcx+rax*8]; string
0x18001876e  call    cs:__imp_WindowsGetStringRawBuffer
0x180018774  mov     [rbp+var_48], rax
0x180018778  mov     rcx, [rbx+8]
0x18001877c  cmp     rcx, [rbx+10h]
0x180018780  jz      short loc_1800187A3
0x180018782  mov     r8d, [rbp+length]
0x180018786  xorps   xmm0, xmm0
0x180018789  movups  xmmword ptr [rcx], xmm0
0x18001878c  mov     [rcx+10h], rsi
0x180018790  mov     [rcx+18h], rsi
0x180018794  mov     rdx, rax
0x180018797  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001879c  add     qword ptr [rbx+8], 20h ; ' '
0x1800187a1  jmp     short loc_1800187B6
0x1800187a3  lea     r9, [rbp+length]
0x1800187a7  lea     r8, [rbp+var_48]
0x1800187ab  mov     rdx, rcx
0x1800187ae  mov     rcx, rbx
0x1800187b1  call    ??$_Emplace_reallocate@AEAPEB_WAEAI@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEAPEB_WAEAI@Z; std::vector<std::wstring>::_Emplace_reallocate<wchar_t const * &,uint &>(std::wstring * const,wchar_t const * &,uint &)
0x1800187b6  add     edi, r14d
0x1800187b9  cmp     edi, [rbp+var_20]
0x1800187bc  jb      short loc_18001875D
0x1800187be  mov     edi, esi
0x1800187c0  cmp     [r15], esi
0x1800187c3  jbe     short loc_1800187DD
0x1800187c5  mov     eax, edi
0x1800187c7  mov     rcx, [r12]
0x1800187cb  mov     rcx, [rcx+rax*8]; string
0x1800187cf  call    cs:__imp_WindowsDeleteString
0x1800187d5  add     edi, r14d
0x1800187d8  cmp     edi, [r15]
0x1800187db  jb      short loc_1800187C5
0x1800187dd  mov     rcx, [rbp+pv]; pv
0x1800187e1  mov     [rbp+pv], rsi
0x1800187e5  test    rcx, rcx
0x1800187e8  jz      short loc_1800187F0
0x1800187ea  call    cs:__imp_CoTaskMemFree
0x1800187f0  mov     rax, rbx
0x1800187f3  mov     rcx, [rbp+var_10]
0x1800187f7  xor     rcx, rsp; StackCookie
0x1800187fa  call    __security_check_cookie
0x1800187ff  lea     r11, [rsp+70h+var_s0]
0x180018804  mov     rbx, [r11+40h]
0x180018808  mov     rsi, [r11+48h]
0x18001880c  mov     rsp, r11
0x18001880f  pop     r15
0x180018811  pop     r14
0x180018813  pop     r12
0x180018815  pop     rdi
0x180018816  pop     rbp
0x180018817  retn
0x180018818  mov     r9d, eax; char *
0x18001881b  lea     r8, aCW1SSrcCalliop_0; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x180018822  mov     edx, 0E1h; void *
0x180018827  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
