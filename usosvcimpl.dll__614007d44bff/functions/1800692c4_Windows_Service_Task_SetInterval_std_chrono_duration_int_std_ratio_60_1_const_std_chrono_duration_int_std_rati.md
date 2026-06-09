# Windows::Service::Task::SetInterval(std::chrono::duration<int,std::ratio<60,1>> const &,std::chrono::duration<int,std::ratio<60,1>> const &)

- ea: `0x1800692c4`
- end: `0x1800696c7`
- name: `?SetInterval@Task@Service@Windows@@QEAAXAEBV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@0@Z`
- size: `1027`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006be90`

## callees

- `0x1800112d0`
- `0x180011680`
- `0x18002b33c`
- `0x18002bbc0`
- `0x18002e698`
- `0x18003007c`
- `0x180041480`
- `0x1800692c4`
- `0x18006aafc`
- `0x1800dd738`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180069440`
- `OLEAUT32!__imp_SysAllocString` at `0x180069440`
- `OLEAUT32!__imp_SysFreeString` at `0x18006947f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18006947f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800695e8`

## string_xrefs

- `0x18006968b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18006964f`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x180069664`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x180069679`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1800696a0`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1800696b5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall Windows::Service::Task::SetInterval(__int64 a1, unsigned int *a2, unsigned int *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  const wchar_t *v13; // rcx
  __int64 *v14; // rbx
  __int64 (__fastcall *v15)(__int64 *, BSTR); // r15
  const OLECHAR *v16; // rcx
  BSTR v17; // rax
  const char *v18; // r9
  OLECHAR *v19; // rdi
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int128 *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  int v28; // [rsp+20h] [rbp-E0h]
  __int128 Src; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v30; // [rsp+38h] [rbp-C8h]
  __int128 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+58h] [rbp-A8h]
  BSTR v33; // [rsp+68h] [rbp-98h]
  _QWORD v34[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v35[4]; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v36; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v37; // [rsp+B8h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp-40h] BYREF
  BSTR v39; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *String2; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *String1[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v42; // [rsp+E8h] [rbp-18h]
  __int128 v43; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v44; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v28 = 0;
  v37 = 0;
  Windows::Service::Task::GetTimeTrigger(a1, &v37);
  v6 = std::to_wstring(v34, *a2);
  v7 = std::wstring::insert(v6, 0, L"PT", 2);
  Src = 0;
  v30 = 0;
  Src = *(_OWORD *)v7;
  v30 = *(_OWORD *)(v7 + 16);
  *(_WORD *)v7 = 0;
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 24) = 7;
  v8 = std::wstring::append(&Src);
  *(_OWORD *)String1 = 0;
  v42 = 0;
  *(_OWORD *)String1 = *(_OWORD *)v8;
  v42 = *(_OWORD *)(v8 + 16);
  *(_WORD *)v8 = 0;
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  std::wstring::~wstring(&Src);
  std::wstring::~wstring(v34);
  v36 = 0;
  v9 = *v37;
  v36 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v9 + 80))(v37, &v36);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v10,
      0);
  String2 = 0;
  v11 = *v36;
  String2 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v11 + 56))(v36, &String2);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v12,
      0);
  v13 = (const wchar_t *)String1;
  if ( *((_QWORD *)&v42 + 1) > 7u )
    v13 = String1[0];
  if ( wcsicmp(v13, String2) )
  {
    v14 = v36;
    v15 = *(__int64 (__fastcall **)(__int64 *, BSTR))(*v36 + 64);
    v16 = (const OLECHAR *)String1;
    if ( *((_QWORD *)&v42 + 1) > 7u )
      v16 = String1[0];
    v17 = SysAllocString(v16);
    v19 = v17;
    v33 = v17;
    v28 = 35;
    if ( !v17 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v18);
    v20 = v15(v14, v17);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v20,
        35);
    SysFreeString(v19);
    *(_BYTE *)(a1 + 40) = 1;
  }
  v21 = std::to_wstring(v35, *a3);
  v22 = std::wstring::insert(v21, 0, L"PT", 2);
  v31 = 0;
  v32 = 0;
  v31 = *(_OWORD *)v22;
  v32 = *(_OWORD *)(v22 + 16);
  *(_WORD *)v22 = 0;
  *(_QWORD *)(v22 + 16) = 0;
  *(_QWORD *)(v22 + 24) = 7;
  v23 = std::wstring::append(&v31);
  v43 = 0;
  v44 = 0;
  v43 = *(_OWORD *)v23;
  v44 = *(_OWORD *)(v23 + 16);
  *(_WORD *)v23 = 0;
  *(_QWORD *)(v23 + 16) = 0;
  *(_QWORD *)(v23 + 24) = 7;
  std::wstring::~wstring(&v31);
  std::wstring::~wstring(v35);
  v39 = 0;
  v24 = &v43;
  if ( *((_QWORD *)&v44 + 1) > 7u )
    v24 = (__int128 *)v43;
  wil::make_bstr(&v39, v24);
  bstrString = 0;
  v25 = *v37;
  bstrString = 0;
  v26 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v25 + 160))(v37, &bstrString);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v26,
      v28);
  if ( wcsicmp(v39, bstrString) )
  {
    v27 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(*v37 + 168))(v37, v39);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v27,
        v28);
    *(_BYTE *)(a1 + 40) = 1;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v39 )
    SysFreeString(v39);
  std::wstring::~wstring(&v43);
  if ( String2 )
    SysFreeString(String2);
  if ( v36 )
    (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
  std::wstring::~wstring(String1);
  if ( v37 )
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
}

```

## disassembly

```asm
0x1800692c4  mov     [rsp-8+arg_18], rbx
0x1800692c9  push    rbp
0x1800692ca  push    rsi
0x1800692cb  push    rdi
0x1800692cc  push    r12
0x1800692ce  push    r13
0x1800692d0  push    r14
0x1800692d2  push    r15
0x1800692d4  lea     rbp, [rsp-20h]
0x1800692d9  sub     rsp, 120h
0x1800692e0  mov     rax, cs:__security_cookie
0x1800692e7  xor     rax, rsp
0x1800692ea  mov     [rbp+50h+var_38], rax
0x1800692ee  mov     r12, r8
0x1800692f1  mov     rbx, rdx
0x1800692f4  mov     r14, rcx
0x1800692f7  xor     r13d, r13d
0x1800692fa  mov     esi, r13d
0x1800692fd  mov     [rsp+150h+var_130], r13d; int
0x180069302  mov     [rbp+50h+var_98], r13
0x180069306  lea     rdx, [rbp+50h+var_98]
0x18006930a  call    ?GetTimeTrigger@Task@Service@Windows@@AEAA?AV?$com_ptr_t@UITimeTrigger@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::GetTimeTrigger(void)
0x18006930f  nop
0x180069310  mov     edx, [rbx]
0x180069312  lea     rcx, [rsp+150h+var_E0]
0x180069317  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x18006931c  nop
0x18006931d  lea     r9d, [r13+2]
0x180069321  lea     r8, aPt; "PT"
0x180069328  xor     edx, edx
0x18006932a  mov     rcx, rax
0x18006932d  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x180069332  xorps   xmm0, xmm0
0x180069335  movups  [rsp+150h+Src], xmm0
0x18006933a  xorps   xmm1, xmm1
0x18006933d  movdqu  [rsp+150h+var_118], xmm1
0x180069343  movups  xmm0, xmmword ptr [rax]
0x180069346  movups  [rsp+150h+Src], xmm0
0x18006934b  movups  xmm1, xmmword ptr [rax+10h]
0x18006934f  movups  [rsp+150h+var_118], xmm1
0x180069354  mov     [rax], r13w
0x180069358  mov     [rax+10h], r13
0x18006935c  lea     edi, [r13+7]
0x180069360  mov     [rax+18h], rdi
0x180069364  or      esi, 1
0x180069367  lea     r8d, [r13+1]
0x18006936b  lea     rdx, aM; "M"
0x180069372  lea     rcx, [rsp+150h+Src]; Src
0x180069377  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18006937c  xorps   xmm0, xmm0
0x18006937f  movups  xmmword ptr [rbp+50h+String1], xmm0
0x180069383  xorps   xmm1, xmm1
0x180069386  movdqu  [rbp+50h+var_68], xmm1
0x18006938b  movups  xmm0, xmmword ptr [rax]
0x18006938e  movups  xmmword ptr [rbp+50h+String1], xmm0
0x180069392  movups  xmm1, xmmword ptr [rax+10h]
0x180069396  movups  [rbp+50h+var_68], xmm1
0x18006939a  mov     [rax], r13w
0x18006939e  mov     [rax+10h], r13
0x1800693a2  mov     [rax+18h], rdi
0x1800693a6  or      esi, 2
0x1800693a9  lea     rcx, [rsp+150h+Src]; void *
0x1800693ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800693b3  nop
0x1800693b4  lea     rcx, [rsp+150h+var_E0]; void *
0x1800693b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800693be  mov     [rbp+50h+var_A0], r13
0x1800693c2  mov     rcx, [rbp+50h+var_98]
0x1800693c6  mov     rax, [rcx]
0x1800693c9  mov     [rbp+50h+var_A0], r13
0x1800693cd  lea     rdx, [rbp+50h+var_A0]
0x1800693d1  mov     rax, [rax+50h]
0x1800693d5  call    _guard_dispatch_icall
0x1800693da  mov     rcx, [rbp+58h]; this
0x1800693de  test    eax, eax
0x1800693e0  js      loc_180069661
0x1800693e6  mov     [rbp+50h+String2], r13
0x1800693ea  mov     rcx, [rbp+50h+var_A0]
0x1800693ee  mov     rax, [rcx]
0x1800693f1  mov     [rbp+50h+String2], r13
0x1800693f5  lea     rdx, [rbp+50h+String2]
0x1800693f9  mov     rax, [rax+38h]
0x1800693fd  call    _guard_dispatch_icall
0x180069402  mov     rcx, [rbp+58h]; this
0x180069406  test    eax, eax
0x180069408  js      loc_180069676
0x18006940e  lea     rcx, [rbp+50h+String1]
0x180069412  cmp     qword ptr [rbp+50h+var_68+8], rdi
0x180069416  cmova   rcx, [rbp+50h+String1]; String1
0x18006941b  mov     rdx, [rbp+50h+String2]; String2
0x18006941f  call    _wcsicmp
0x180069424  test    eax, eax
0x180069426  jz      short loc_18006948E
0x180069428  mov     rbx, [rbp+50h+var_A0]
0x18006942c  mov     rax, [rbx]
0x18006942f  mov     r15, [rax+40h]
0x180069433  lea     rcx, [rbp+50h+String1]
0x180069437  cmp     qword ptr [rbp+50h+var_68+8], rdi
0x18006943b  cmova   rcx, [rbp+50h+String1]; psz
0x180069440  call    cs:__imp_SysAllocString
0x180069446  mov     rdi, rax
0x180069449  mov     [rsp+150h+var_E8], rax
0x18006944e  or      esi, 20h
0x180069451  mov     [rsp+150h+var_130], esi; int
0x180069455  mov     rcx, [rbp+58h]; this
0x180069459  test    rax, rax
0x18006945c  jz      loc_18006968B
0x180069462  mov     rdx, rax
0x180069465  mov     rcx, rbx
0x180069468  mov     rax, r15
0x18006946b  call    _guard_dispatch_icall
0x180069470  mov     rcx, [rbp+58h]; this
0x180069474  test    eax, eax
0x180069476  js      loc_18006969D
0x18006947c  mov     rcx, rdi; bstrString
0x18006947f  call    cs:__imp_SysFreeString
0x180069485  mov     byte ptr [r14+28h], 1
0x18006948a  lea     edi, [r13+7]
0x18006948e  mov     edx, [r12]
0x180069492  lea     rcx, [rbp+50h+var_C0]
0x180069496  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x18006949b  nop
0x18006949c  mov     r9d, 2
0x1800694a2  lea     r8, aPt; "PT"
0x1800694a9  xor     edx, edx
0x1800694ab  mov     rcx, rax
0x1800694ae  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800694b3  xorps   xmm0, xmm0
0x1800694b6  movups  [rsp+150h+var_108], xmm0
0x1800694bb  xorps   xmm1, xmm1
0x1800694be  movdqu  [rsp+150h+var_F8], xmm1
0x1800694c4  movups  xmm0, xmmword ptr [rax]
0x1800694c7  movups  [rsp+150h+var_108], xmm0
0x1800694cc  movups  xmm1, xmmword ptr [rax+10h]
0x1800694d0  movups  [rsp+150h+var_F8], xmm1
0x1800694d5  mov     [rax], r13w
0x1800694d9  mov     [rax+10h], r13
0x1800694dd  mov     [rax+18h], rdi
0x1800694e1  mov     r8d, 1
0x1800694e7  lea     rdx, aM; "M"
0x1800694ee  lea     rcx, [rsp+150h+var_108]; Src
0x1800694f3  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800694f8  xorps   xmm0, xmm0
0x1800694fb  movups  [rbp+50h+var_58], xmm0
0x1800694ff  xorps   xmm1, xmm1
0x180069502  movdqu  [rbp+50h+var_48], xmm1
0x180069507  movups  xmm0, xmmword ptr [rax]
0x18006950a  movups  [rbp+50h+var_58], xmm0
0x18006950e  movups  xmm1, xmmword ptr [rax+10h]
0x180069512  movups  [rbp+50h+var_48], xmm1
0x180069516  mov     [rax], r13w
0x18006951a  mov     [rax+10h], r13
0x18006951e  mov     [rax+18h], rdi
0x180069522  lea     rcx, [rsp+150h+var_108]; void *
0x180069527  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006952c  nop
0x18006952d  lea     rcx, [rbp+50h+var_C0]; void *
0x180069531  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069536  mov     [rbp+50h+var_88], r13
0x18006953a  lea     rdx, [rbp+50h+var_58]
0x18006953e  cmp     qword ptr [rbp+50h+var_48+8], rdi
0x180069542  cmova   rdx, qword ptr [rbp+50h+var_58]
0x180069547  lea     rcx, [rbp+50h+var_88]
0x18006954b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x180069550  nop
0x180069551  mov     [rbp+50h+bstrString], r13
0x180069555  mov     rcx, [rbp+50h+var_98]
0x180069559  mov     rax, [rcx]
0x18006955c  mov     [rbp+50h+bstrString], r13
0x180069560  lea     rdx, [rbp+50h+bstrString]
0x180069564  mov     rax, [rax+0A0h]
0x18006956b  call    _guard_dispatch_icall
0x180069570  mov     rcx, [rbp+58h]; this
0x180069574  test    eax, eax
0x180069576  js      loc_1800696B2
0x18006957c  mov     rdx, [rbp+50h+bstrString]; String2
0x180069580  mov     rcx, [rbp+50h+var_88]; String1
0x180069584  call    _wcsicmp
0x180069589  test    eax, eax
0x18006958b  jz      short loc_1800695B5
0x18006958d  mov     rcx, [rbp+50h+var_98]
0x180069591  mov     rax, [rcx]
0x180069594  mov     rdx, [rbp+50h+var_88]
0x180069598  mov     rax, [rax+0A8h]
0x18006959f  call    _guard_dispatch_icall
0x1800695a4  mov     rcx, [rbp+58h]; this
0x1800695a8  test    eax, eax
0x1800695aa  js      loc_18006964C
0x1800695b0  mov     byte ptr [r14+28h], 1
0x1800695b5  mov     rcx, [rbp+50h+bstrString]; bstrString
0x1800695b9  test    rcx, rcx
0x1800695bc  jz      short loc_1800695C5
0x1800695be  call    cs:__imp_SysFreeString
0x1800695c4  nop
0x1800695c5  mov     rcx, [rbp+50h+var_88]; bstrString
0x1800695c9  test    rcx, rcx
0x1800695cc  jz      short loc_1800695D5
0x1800695ce  call    cs:__imp_SysFreeString
0x1800695d4  nop
0x1800695d5  lea     rcx, [rbp+50h+var_58]; void *
0x1800695d9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800695de  nop
0x1800695df  mov     rcx, [rbp+50h+String2]; bstrString
0x1800695e3  test    rcx, rcx
0x1800695e6  jz      short loc_1800695EF
0x1800695e8  call    cs:__imp_SysFreeString
0x1800695ee  nop
0x1800695ef  mov     rcx, [rbp+50h+var_A0]
0x1800695f3  test    rcx, rcx
0x1800695f6  jz      short loc_180069605
0x1800695f8  mov     rax, [rcx]
0x1800695fb  mov     rax, [rax+10h]
0x1800695ff  call    _guard_dispatch_icall
0x180069604  nop
0x180069605  lea     rcx, [rbp+50h+String1]; void *
0x180069609  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006960e  nop
0x18006960f  mov     rcx, [rbp+50h+var_98]
0x180069613  test    rcx, rcx
0x180069616  jz      short loc_180069625
0x180069618  mov     rax, [rcx]
0x18006961b  mov     rax, [rax+10h]
0x18006961f  call    _guard_dispatch_icall
0x180069624  nop
0x180069625  mov     rcx, [rbp+50h+var_38]
0x180069629  xor     rcx, rsp; StackCookie
0x18006962c  call    __security_check_cookie
0x180069631  mov     rbx, [rsp+150h+arg_18]
0x180069639  add     rsp, 120h
0x180069640  pop     r15
0x180069642  pop     r14
0x180069644  pop     r13
0x180069646  pop     r12
0x180069648  pop     rdi
0x180069649  pop     rsi
0x18006964a  pop     rbp
0x18006964b  retn
0x18006964c  mov     r9d, eax; char *
0x18006964f  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180069656  mov     edx, 73h ; 's'; void *
0x18006965b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069661  mov     r9d, eax; char *
0x180069664  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006966b  mov     edx, 61h ; 'a'; void *
0x180069670  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069676  mov     r9d, eax; char *
0x180069679  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180069680  mov     edx, 64h ; 'd'; void *
0x180069685  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006968b  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180069692  mov     edx, 138Dh; void *
0x180069697  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18006969d  mov     r9d, eax; char *
0x1800696a0  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800696a7  mov     edx, 67h ; 'g'; void *
0x1800696ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800696b2  mov     r9d, eax; char *
0x1800696b5  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800696bc  mov     edx, 70h ; 'p'; void *
0x1800696c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
