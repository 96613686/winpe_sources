# Diagnostics::Connector_Uso_Working::ProcessTelemetry(Diagnostics::OTelLogRecord &,Diagnostics::OTelFile &)

- ea: `0x180069510`
- end: `0x1800697b5`
- name: `?ProcessTelemetry@Connector_Uso_Working@Diagnostics@@UEAA_NAEAVOTelLogRecord@2@AEAVOTelFile@2@@Z`
- size: `677`
- prototype: `bool(Diagnostics::Connector_Uso_Working *__hidden this, struct Diagnostics::OTelLogRecord *, struct Diagnostics::OTelFile *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001adcc`
- `0x18001c92c`
- `0x18002964c`
- `0x180029e44`
- `0x18002a6ac`
- `0x18002d4ac`
- `0x18002da90`
- `0x18003b934`
- `0x180069510`
- `0x18008fe00`
- `0x1800961f0`

## string_xrefs

- `0x180069569`: `Microsoft.Windows.Update.Orchestrator.Worker.WorkingState`
- `0x18006971a`: `Microsoft.Windows.Update.Orchestrator.Worker.Working`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char __fastcall Diagnostics::Connector_Uso_Working::ProcessTelemetry(
        Diagnostics::Connector_Uso_Working *this,
        struct Diagnostics::OTelLogRecord *a2,
        struct Diagnostics::OTelFile *a3)
{
  const wchar_t *v6; // rcx
  size_t v7; // r8
  const wchar_t *v8; // rcx
  wchar_t *v9; // rax
  unsigned __int64 v10; // rdx
  char v11; // r8
  __int64 v12; // rax
  wchar_t **v13; // rcx
  int v14; // ebx
  __int64 v15; // rdi
  void *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD v20[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v22; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+68h] [rbp-A0h]
  _BYTE v24[32]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v25[32]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v26[32]; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t *S1[2]; // [rsp+D8h] [rbp-30h] BYREF
  size_t N; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v29; // [rsp+F0h] [rbp-18h]
  char v30; // [rsp+F8h] [rbp-10h]
  _BYTE v31[40]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v32[336]; // [rsp+128h] [rbp+20h] BYREF

  v6 = (const wchar_t *)((char *)a2 + 32);
  if ( *((_QWORD *)a2 + 7) > 7u )
    v6 = *(const wchar_t **)v6;
  if ( *((_QWORD *)a2 + 6) == 57 && !wmemcmp(v6, L"Microsoft.Windows.Update.Orchestrator.Worker.WorkingState", 0x39u) )
  {
    v22 = 0;
    v23 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v22, L"state", 5u);
    Diagnostics::OTelLogRecord::GetAttribute(a2, S1, &v22);
    std::wstring::~wstring((__int64)&v22);
    if ( v30 )
    {
      v7 = N;
      v8 = (const wchar_t *)S1;
      v9 = S1[0];
      v10 = v29;
      if ( v29 > 7 )
        v8 = S1[0];
      if ( N == 1 )
      {
        if ( !wmemcmp(v8, L"1", 1u) )
        {
          v12 = *((_QWORD *)a2 + 16);
          if ( !*((_BYTE *)this + 16) )
            *((_BYTE *)this + 16) = v11;
          *((_QWORD *)this + 1) = v12;
          goto LABEL_20;
        }
        v10 = v29;
        v7 = N;
        v9 = S1[0];
      }
      v13 = S1;
      if ( v10 > 7 )
        v13 = (wchar_t **)v9;
      if ( v7 == 1 && !wmemcmp((const wchar_t *)v13, L"0", 1u) && *((_BYTE *)this + 16) )
      {
        v21[0] = *((_QWORD *)this + 1);
        v14 = v21[0];
        v20[0] = *((_QWORD *)a2 + 16);
        v15 = Diagnostics::DataStyles::TimePoint(v25, v20);
        v16 = (void *)Diagnostics::DataStyles::TimePoint(v24, v21);
        v17 = std::wstring::append(v16);
        v22 = *(_OWORD *)v17;
        v23 = *(_OWORD *)(v17 + 16);
        *(_WORD *)v17 = 0;
        *(_QWORD *)(v17 + 16) = 0;
        *(_QWORD *)(v17 + 24) = 7;
        std::operator+<wchar_t>(v31, &v22, v15);
        std::wstring::~wstring((__int64)&v22);
        std::wstring::~wstring((__int64)v24);
        std::wstring::~wstring((__int64)v25);
        memset(v32, 0, sizeof(v32));
        v18 = std::wstring::wstring((__int64)v26, (__int64)v31);
        v22 = *(_OWORD *)&Diagnostics::OTelLogRecord::DefaultVersion;
        v21[0] = L"Microsoft.Windows.Update.Orchestrator.Worker.Working";
        v21[1] = 52;
        Diagnostics::OTelLogRecord::OTelLogRecord(
          (unsigned int)v32,
          (unsigned int)v20,
          (unsigned int)v21,
          v14,
          v18,
          (__int64)&v22);
        Diagnostics::OTelFile::AppendLogRecord(a3, (const struct Diagnostics::OTelLogRecord *)v32);
        *((_BYTE *)this + 16) = 0;
        Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v32);
        std::wstring::~wstring((__int64)v31);
      }
    }
LABEL_20:
    if ( v30 )
      std::wstring::~wstring((__int64)S1);
  }
  return 1;
}

```

## disassembly

```asm
0x180069510  mov     rax, rsp
0x180069513  mov     [rax+20h], rbx
0x180069517  push    rbp
0x180069518  push    rsi
0x180069519  push    rdi
0x18006951a  push    r14
0x18006951c  push    r15
0x18006951e  lea     rbp, [rax-1B8h]
0x180069525  sub     rsp, 290h
0x18006952c  movaps  xmmword ptr [rax-38h], xmm6
0x180069530  mov     rax, cs:__security_cookie
0x180069537  xor     rax, rsp
0x18006953a  mov     [rbp+1B0h+var_40], rax
0x180069541  mov     r14, r8
0x180069544  mov     rdi, rdx
0x180069547  mov     rsi, rcx
0x18006954a  xor     r15d, r15d
0x18006954d  lea     rcx, [rdx+20h]
0x180069551  mov     r8, [rcx+10h]; N
0x180069555  cmp     qword ptr [rcx+18h], 7
0x18006955a  jbe     short loc_18006955F
0x18006955c  mov     rcx, [rcx]; S1
0x18006955f  cmp     r8, 39h ; '9'
0x180069563  jnz     loc_180069788
0x180069569  lea     rdx, aMicrosoftWindo_0; "Microsoft.Windows.Update.Orchestrator.W"...
0x180069570  call    wmemcmp
0x180069575  test    eax, eax
0x180069577  jnz     loc_180069788
0x18006957d  xorps   xmm0, xmm0
0x180069580  movups  [rsp+2B0h+var_268+8], xmm0
0x180069585  xorps   xmm1, xmm1
0x180069588  movdqu  xmmword ptr [rsp+2B0h+var_258+8], xmm1
0x18006958e  lea     r8d, [rax+5]
0x180069592  lea     rdx, aState_1; "state"
0x180069599  lea     rcx, [rsp+2B0h+var_268+8]
0x18006959e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800695a3  nop
0x1800695a4  lea     r8, [rsp+2B0h+var_268+8]
0x1800695a9  lea     rdx, [rbp+1B0h+S1]
0x1800695ad  mov     rcx, rdi
0x1800695b0  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x1800695b5  nop
0x1800695b6  lea     rcx, [rsp+2B0h+var_268+8]
0x1800695bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800695c0  cmp     [rbp+1B0h+var_1C0], r15b
0x1800695c4  jz      loc_180069779
0x1800695ca  mov     r8, [rbp+1B0h+N]; N
0x1800695ce  lea     rcx, [rbp+1B0h+S1]
0x1800695d2  mov     rax, [rbp+1B0h+S1]
0x1800695d6  mov     rdx, [rbp+1B0h+var_1C8]
0x1800695da  cmp     rdx, 7
0x1800695de  cmova   rcx, rax; S1
0x1800695e2  cmp     r8, 1
0x1800695e6  jnz     short loc_18006961E
0x1800695e8  lea     rdx, a1; "1"
0x1800695ef  call    wmemcmp
0x1800695f4  test    eax, eax
0x1800695f6  jnz     short loc_180069612
0x1800695f8  mov     rax, [rdi+80h]
0x1800695ff  cmp     [rsi+10h], r15b
0x180069603  jnz     short loc_180069609
0x180069605  mov     [rsi+10h], r8b
0x180069609  mov     [rsi+8], rax
0x18006960d  jmp     loc_180069779
0x180069612  mov     rdx, [rbp+1B0h+var_1C8]
0x180069616  mov     r8, [rbp+1B0h+N]; N
0x18006961a  mov     rax, [rbp+1B0h+S1]
0x18006961e  lea     rcx, [rbp+1B0h+S1]
0x180069622  cmp     rdx, 7
0x180069626  cmova   rcx, rax; S1
0x18006962a  cmp     r8, 1
0x18006962e  jnz     loc_180069779
0x180069634  lea     rdx, a0; "0"
0x18006963b  call    wmemcmp
0x180069640  test    eax, eax
0x180069642  jnz     loc_180069779
0x180069648  cmp     [rsi+10h], r15b
0x18006964c  jz      loc_180069779
0x180069652  mov     rbx, [rsi+8]
0x180069656  mov     [rsp+2B0h+var_270], rbx
0x18006965b  mov     rax, [rdi+80h]
0x180069662  mov     [rsp+2B0h+var_280], rax
0x180069667  lea     rdx, [rsp+2B0h+var_280]
0x18006966c  lea     rcx, [rbp+1B0h+var_220]
0x180069670  call    ?TimePoint@DataStyles@Diagnostics@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; Diagnostics::DataStyles::TimePoint(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180069675  mov     rdi, rax
0x180069678  lea     rdx, [rsp+2B0h+var_270]
0x18006967d  lea     rcx, [rsp+2B0h+var_240]
0x180069682  call    ?TimePoint@DataStyles@Diagnostics@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; Diagnostics::DataStyles::TimePoint(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180069687  nop
0x180069688  mov     r8d, 1
0x18006968e  lea     rdx, asc_1800A38C0; "-"
0x180069695  mov     rcx, rax; Src
0x180069698  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18006969d  movups  xmm0, xmmword ptr [rax]
0x1800696a0  movups  [rsp+2B0h+var_268+8], xmm0
0x1800696a5  movups  xmm1, xmmword ptr [rax+10h]
0x1800696a9  movups  xmmword ptr [rsp+2B0h+var_258+8], xmm1
0x1800696ae  mov     [rax], r15w
0x1800696b2  mov     [rax+10h], r15
0x1800696b6  mov     qword ptr [rax+18h], 7
0x1800696be  mov     r8, rdi
0x1800696c1  lea     rdx, [rsp+2B0h+var_268+8]
0x1800696c6  lea     rcx, [rbp+1B0h+var_1B8]
0x1800696ca  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800696cf  nop
0x1800696d0  lea     rcx, [rsp+2B0h+var_268+8]
0x1800696d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800696da  nop
0x1800696db  lea     rcx, [rsp+2B0h+var_240]
0x1800696e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800696e5  nop
0x1800696e6  lea     rcx, [rbp+1B0h+var_220]
0x1800696ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800696ef  xor     edx, edx; Val
0x1800696f1  mov     r8d, 150h; Size
0x1800696f7  lea     rcx, [rbp+1B0h+var_190]; void *
0x1800696fb  call    memset
0x180069700  movups  xmm6, xmmword ptr cs:?DefaultVersion@OTelLogRecord@Diagnostics@@0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@B; std::wstring_view const Diagnostics::OTelLogRecord::DefaultVersion
0x180069707  lea     rdx, [rbp+1B0h+var_1B8]
0x18006970b  lea     rcx, [rbp+1B0h+var_200]
0x18006970f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180069714  movdqu  [rsp+2B0h+var_268+8], xmm6
0x18006971a  lea     rcx, aMicrosoftWindo_26; "Microsoft.Windows.Update.Orchestrator.W"...
0x180069721  mov     [rsp+2B0h+var_270], rcx
0x180069726  mov     qword ptr [rsp+2B0h+var_268], 34h ; '4'
0x18006972f  lea     rcx, [rsp+2B0h+var_268+8]
0x180069734  mov     [rsp+2B0h+var_288], rcx
0x180069739  mov     [rsp+2B0h+var_290], rax
0x18006973e  mov     r9, rbx
0x180069741  lea     r8, [rsp+2B0h+var_270]
0x180069746  lea     rdx, [rsp+2B0h+var_280]
0x18006974b  lea     rcx, [rbp+1B0h+var_190]
0x18006974f  call    ??0OTelLogRecord@Diagnostics@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@4@V234@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1@Z; Diagnostics::OTelLogRecord::OTelLogRecord(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &,std::wstring_view,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::wstring,std::wstring_view)
0x180069754  nop
0x180069755  lea     rdx, [rbp+1B0h+var_190]; struct Diagnostics::OTelLogRecord *
0x180069759  mov     rcx, r14; this
0x18006975c  call    ?AppendLogRecord@OTelFile@Diagnostics@@QEAAXAEBVOTelLogRecord@2@@Z; Diagnostics::OTelFile::AppendLogRecord(Diagnostics::OTelLogRecord const &)
0x180069761  mov     [rsi+10h], r15b
0x180069765  lea     rcx, [rbp+1B0h+var_190]; this
0x180069769  call    ??1OTelLogRecord@Diagnostics@@QEAA@XZ; Diagnostics::OTelLogRecord::~OTelLogRecord(void)
0x18006976e  nop
0x18006976f  lea     rcx, [rbp+1B0h+var_1B8]
0x180069773  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069778  nop
0x180069779  cmp     [rbp+1B0h+var_1C0], r15b
0x18006977d  jz      short loc_180069788
0x18006977f  lea     rcx, [rbp+1B0h+S1]
0x180069783  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069788  mov     al, 1
0x18006978a  mov     rcx, [rbp+1B0h+var_40]
0x180069791  xor     rcx, rsp; StackCookie
0x180069794  call    __security_check_cookie
0x180069799  lea     r11, [rsp+2B0h+var_20]
0x1800697a1  mov     rbx, [r11+48h]
0x1800697a5  movaps  xmm6, xmmword ptr [r11-10h]
0x1800697aa  mov     rsp, r11
0x1800697ad  pop     r15
0x1800697af  pop     r14
0x1800697b1  pop     rdi
0x1800697b2  pop     rsi
0x1800697b3  pop     rbp
0x1800697b4  retn
```
