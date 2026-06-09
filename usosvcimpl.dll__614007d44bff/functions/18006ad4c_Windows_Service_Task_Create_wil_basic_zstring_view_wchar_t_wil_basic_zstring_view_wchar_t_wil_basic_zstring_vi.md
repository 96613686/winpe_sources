# Windows::Service::Task::Create(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18006ad4c`
- end: `0x18006b152`
- name: `?Create@Task@Service@Windows@@SA?AV123@V?$basic_zstring_view@_W@wil@@00@Z`
- size: `1030`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006b494`

## callees

- `0x1800112d0`
- `0x18002bbc0`
- `0x180041480`
- `0x180068d48`
- `0x1800690d0`
- `0x18006ad4c`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006aee1`
- `OLEAUT32!__imp_SysAllocString` at `0x18006af33`
- `OLEAUT32!__imp_SysAllocString` at `0x18006aee1`
- `OLEAUT32!__imp_SysAllocString` at `0x18006af33`
- `OLEAUT32!__imp_SysFreeString` at `0x18006af1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006af71`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b011`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b021`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b05d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006af1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006af71`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b011`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b021`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b05d`

## string_xrefs

- `0x18006b119`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18006b140`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18006b107`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18006ad8e`: `Microsoft\Windows\UpdateOrchestrator`
- `0x18006b089`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006b09e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006b0b3`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006b0c8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006b0dd`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006b0f2`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006b12e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Windows::Service::Task::Create(__int64 a1, __int128 *a2, const OLECHAR **a3, __int64 a4)
{
  __int64 v8; // rax
  int v9; // eax
  const OLECHAR *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, BSTR); // r14
  BSTR v21; // rax
  const char *v22; // r9
  OLECHAR *v23; // rdi
  int v24; // eax
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, BSTR); // r14
  BSTR v27; // rax
  const char *v28; // r9
  OLECHAR *v29; // rdi
  int v30; // eax
  _QWORD v32[3]; // [rsp+28h] [rbp-61h] BYREF
  __int128 v33; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v34; // [rsp+50h] [rbp-39h] BYREF
  __int64 v35; // [rsp+58h] [rbp-31h] BYREF
  __int64 v36; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v37; // [rsp+68h] [rbp-21h] BYREF
  __int64 v38; // [rsp+70h] [rbp-19h] BYREF
  int v39[2]; // [rsp+78h] [rbp-11h] BYREF
  BSTR v40; // [rsp+80h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-1h] BYREF
  BSTR v42; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v40 = 0;
  wil::make_bstr(&v40, L"Microsoft\\Windows\\UpdateOrchestrator");
  v32[1] = 0;
  *(_QWORD *)v39 = 0;
  Windows::Service::Task::TaskService((int)v39);
  v34 = 0;
  v8 = **(_QWORD **)v39;
  v34 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v8 + 72))(*(_QWORD *)v39, 0, &v34);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v9,
      0);
  v42 = 0;
  wil::make_bstr(&v42, *a3);
  bstrString = 0;
  v10 = &S1;
  if ( *(_QWORD *)(a4 + 8) )
    v10 = *(const OLECHAR **)a4;
  wil::make_bstr(&bstrString, v10);
  v38 = 0;
  v11 = *v34;
  v38 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 88))(v34, &v38);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v12,
      0);
  v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 176LL))(v38, 0xFFFFFFFFLL);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v13,
      0);
  v37 = 0;
  v14 = *v34;
  v37 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v14 + 136))(v34, &v37);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v15,
      0);
  v36 = 0;
  v16 = *v37;
  v36 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v16 + 96))(v37, 0, &v36);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v17,
      0);
  v35 = 0;
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v36)(
          v36,
          &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
          &v35);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v18,
      0);
  v19 = v35;
  v20 = *(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v35 + 88LL);
  v21 = SysAllocString(*a3);
  v23 = v21;
  v32[0] = v21;
  if ( !v21 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x138D,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  v24 = v20(v19, v21);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v24,
      48);
  SysFreeString(v23);
  v25 = v35;
  v26 = *(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v35 + 104LL);
  v27 = SysAllocString(*(const OLECHAR **)a4);
  v29 = v27;
  v32[0] = v27;
  if ( !v27 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x138D,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v28);
  v30 = v26(v25, v27);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v30,
      80);
  SysFreeString(v29);
  v32[0] = v34;
  if ( v34 )
    (*(void (__fastcall **)(__int64 *))(*v34 + 8))(v34);
  v33 = *a2;
  Windows::Service::Task::Task(a1, (__int64)&v33, v32, 1);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v37 )
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v42 )
    SysFreeString(v42);
  if ( v34 )
    (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
  if ( *(_QWORD *)v39 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
  if ( v40 )
    SysFreeString(v40);
  return a1;
}

```

## disassembly

```asm
0x18006ad4c  push    rbp
0x18006ad4e  push    rbx
0x18006ad4f  push    rsi
0x18006ad50  push    rdi
0x18006ad51  push    r12
0x18006ad53  push    r13
0x18006ad55  push    r14
0x18006ad57  push    r15
0x18006ad59  lea     rbp, [rsp-1Fh]
0x18006ad5e  sub     rsp, 0A8h
0x18006ad65  mov     rax, cs:__security_cookie
0x18006ad6c  xor     rax, rsp
0x18006ad6f  mov     [rbp+57h+var_48], rax
0x18006ad73  mov     rsi, r9
0x18006ad76  mov     rdi, r8
0x18006ad79  mov     r12, rdx
0x18006ad7c  mov     r15, rcx
0x18006ad7f  mov     [rbp+57h+var_60], rcx
0x18006ad83  xor     r13d, r13d
0x18006ad86  mov     [rbp+57h+var_C0], r13d
0x18006ad8a  mov     [rbp+57h+var_60], r13
0x18006ad8e  lea     rdx, sourceString; "Microsoft\\Windows\\UpdateOrchestrator"
0x18006ad95  lea     rcx, [rbp+57h+var_60]
0x18006ad99  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x18006ad9e  nop
0x18006ad9f  mov     [rbp+57h+var_B0], r13
0x18006ada3  mov     qword ptr [rbp+57h+var_68], r13
0x18006ada7  lea     rcx, [rbp+57h+var_68]; int
0x18006adab  call    ?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::TaskService(void)
0x18006adb0  nop
0x18006adb1  mov     [rbp+57h+var_90], r13
0x18006adb5  mov     rcx, qword ptr [rbp+57h+var_68]
0x18006adb9  mov     rax, [rcx]
0x18006adbc  mov     [rbp+57h+var_90], r13
0x18006adc0  lea     r8, [rbp+57h+var_90]
0x18006adc4  xor     edx, edx
0x18006adc6  mov     rax, [rax+48h]
0x18006adca  call    _guard_dispatch_icall
0x18006adcf  mov     rcx, [rbp+5Fh]; this
0x18006add3  test    eax, eax
0x18006add5  js      loc_18006B09B
0x18006addb  mov     [rbp+57h+var_50], r13
0x18006addf  mov     rdx, [rdi]
0x18006ade2  lea     rcx, [rbp+57h+var_50]
0x18006ade6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x18006adeb  nop
0x18006adec  mov     [rbp+57h+bstrString], r13
0x18006adf0  cmp     [rsi+8], r13
0x18006adf4  lea     rdx, S1
0x18006adfb  jz      short loc_18006AE00
0x18006adfd  mov     rdx, [rsi]
0x18006ae00  lea     rcx, [rbp+57h+bstrString]
0x18006ae04  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x18006ae09  nop
0x18006ae0a  mov     [rbp+57h+var_70], r13
0x18006ae0e  mov     rcx, [rbp+57h+var_90]
0x18006ae12  mov     rax, [rcx]
0x18006ae15  mov     [rbp+57h+var_70], r13
0x18006ae19  lea     rdx, [rbp+57h+var_70]
0x18006ae1d  mov     rax, [rax+58h]
0x18006ae21  call    _guard_dispatch_icall
0x18006ae26  mov     rcx, [rbp+5Fh]; this
0x18006ae2a  test    eax, eax
0x18006ae2c  js      loc_18006B0B0
0x18006ae32  or      edx, 0FFFFFFFFh
0x18006ae35  mov     rcx, [rbp+57h+var_70]
0x18006ae39  mov     rax, [rcx]
0x18006ae3c  mov     rax, [rax+0B0h]
0x18006ae43  call    _guard_dispatch_icall
0x18006ae48  mov     rcx, [rbp+5Fh]; this
0x18006ae4c  test    eax, eax
0x18006ae4e  js      loc_18006B0C5
0x18006ae54  mov     [rbp+57h+var_78], r13
0x18006ae58  mov     rcx, [rbp+57h+var_90]
0x18006ae5c  mov     rax, [rcx]
0x18006ae5f  mov     [rbp+57h+var_78], r13
0x18006ae63  lea     rdx, [rbp+57h+var_78]
0x18006ae67  mov     rax, [rax+88h]
0x18006ae6e  call    _guard_dispatch_icall
0x18006ae73  mov     rcx, [rbp+5Fh]; this
0x18006ae77  test    eax, eax
0x18006ae79  js      loc_18006B0DA
0x18006ae7f  mov     [rbp+57h+var_80], r13
0x18006ae83  mov     rcx, [rbp+57h+var_78]
0x18006ae87  mov     rax, [rcx]
0x18006ae8a  mov     [rbp+57h+var_80], r13
0x18006ae8e  lea     r8, [rbp+57h+var_80]
0x18006ae92  xor     edx, edx
0x18006ae94  mov     rax, [rax+60h]
0x18006ae98  call    _guard_dispatch_icall
0x18006ae9d  mov     rcx, [rbp+5Fh]; this
0x18006aea1  test    eax, eax
0x18006aea3  js      loc_18006B0EF
0x18006aea9  mov     rcx, [rbp+57h+var_80]
0x18006aead  mov     [rbp+57h+var_88], r13
0x18006aeb1  mov     rax, [rcx]
0x18006aeb4  lea     r8, [rbp+57h+var_88]
0x18006aeb8  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x18006aebf  mov     rax, [rax]
0x18006aec2  call    _guard_dispatch_icall
0x18006aec7  mov     rcx, [rbp+5Fh]; this
0x18006aecb  test    eax, eax
0x18006aecd  js      loc_18006B104
0x18006aed3  mov     rbx, [rbp+57h+var_88]
0x18006aed7  mov     rax, [rbx]
0x18006aeda  mov     r14, [rax+58h]
0x18006aede  mov     rcx, [rdi]; psz
0x18006aee1  call    cs:__imp_SysAllocString
0x18006aee7  mov     rdi, rax
0x18006aeea  mov     [rbp+57h+var_B8], rax
0x18006aeee  mov     [rbp+57h+var_C0], 30h ; '0'
0x18006aef5  mov     rcx, [rbp+5Fh]; this
0x18006aef9  test    rax, rax
0x18006aefc  jz      loc_18006B119
0x18006af02  mov     rdx, rax
0x18006af05  mov     rcx, rbx
0x18006af08  mov     rax, r14
0x18006af0b  call    _guard_dispatch_icall
0x18006af10  mov     rcx, [rbp+5Fh]; this
0x18006af14  test    eax, eax
0x18006af16  js      loc_18006B12B
0x18006af1c  mov     rcx, rdi; bstrString
0x18006af1f  call    cs:__imp_SysFreeString
0x18006af25  mov     rbx, [rbp+57h+var_88]
0x18006af29  mov     rax, [rbx]
0x18006af2c  mov     r14, [rax+68h]
0x18006af30  mov     rcx, [rsi]; psz
0x18006af33  call    cs:__imp_SysAllocString
0x18006af39  mov     rdi, rax
0x18006af3c  mov     [rbp+57h+var_B8], rax
0x18006af40  mov     [rbp+57h+var_C0], 50h ; 'P'
0x18006af47  mov     rcx, [rbp+5Fh]; this
0x18006af4b  test    rax, rax
0x18006af4e  jz      loc_18006B140
0x18006af54  mov     rdx, rax
0x18006af57  mov     rcx, rbx
0x18006af5a  mov     rax, r14
0x18006af5d  call    _guard_dispatch_icall
0x18006af62  mov     rcx, [rbp+5Fh]; this
0x18006af66  test    eax, eax
0x18006af68  js      loc_18006B086
0x18006af6e  mov     rcx, rdi; bstrString
0x18006af71  call    cs:__imp_SysFreeString
0x18006af77  nop
0x18006af78  mov     rcx, [rbp+57h+var_90]
0x18006af7c  mov     [rbp+57h+var_B8], rcx
0x18006af80  test    rcx, rcx
0x18006af83  jz      short loc_18006AF92
0x18006af85  mov     rax, [rcx]
0x18006af88  mov     rax, [rax+8]
0x18006af8c  call    _guard_dispatch_icall
0x18006af91  nop
0x18006af92  movaps  xmm0, xmmword ptr [r12]
0x18006af97  movdqa  [rbp+57h+var_A0], xmm0
0x18006af9c  mov     r9b, 1
0x18006af9f  lea     r8, [rbp+57h+var_B8]
0x18006afa3  lea     rdx, [rbp+57h+var_A0]
0x18006afa7  mov     rcx, r15
0x18006afaa  call    ??0Task@Service@Windows@@QEAA@V?$basic_zstring_view@_W@wil@@V?$com_ptr_t@UITaskDefinition@@Uerr_exception_policy@wil@@@4@_N@Z; Windows::Service::Task::Task(wil::basic_zstring_view<wchar_t>,wil::com_ptr_t<ITaskDefinition,wil::err_exception_policy>,bool)
0x18006afaf  nop
0x18006afb0  mov     rcx, [rbp+57h+var_88]
0x18006afb4  test    rcx, rcx
0x18006afb7  jz      short loc_18006AFC6
0x18006afb9  mov     rax, [rcx]
0x18006afbc  mov     rax, [rax+10h]
0x18006afc0  call    _guard_dispatch_icall
0x18006afc5  nop
0x18006afc6  mov     rcx, [rbp+57h+var_80]
0x18006afca  test    rcx, rcx
0x18006afcd  jz      short loc_18006AFDC
0x18006afcf  mov     rax, [rcx]
0x18006afd2  mov     rax, [rax+10h]
0x18006afd6  call    _guard_dispatch_icall
0x18006afdb  nop
0x18006afdc  mov     rcx, [rbp+57h+var_78]
0x18006afe0  test    rcx, rcx
0x18006afe3  jz      short loc_18006AFF2
0x18006afe5  mov     rax, [rcx]
0x18006afe8  mov     rax, [rax+10h]
0x18006afec  call    _guard_dispatch_icall
0x18006aff1  nop
0x18006aff2  mov     rcx, [rbp+57h+var_70]
0x18006aff6  test    rcx, rcx
0x18006aff9  jz      short loc_18006B008
0x18006affb  mov     rax, [rcx]
0x18006affe  mov     rax, [rax+10h]
0x18006b002  call    _guard_dispatch_icall
0x18006b007  nop
0x18006b008  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18006b00c  test    rcx, rcx
0x18006b00f  jz      short loc_18006B018
0x18006b011  call    cs:__imp_SysFreeString
0x18006b017  nop
0x18006b018  mov     rcx, [rbp+57h+var_50]; bstrString
0x18006b01c  test    rcx, rcx
0x18006b01f  jz      short loc_18006B028
0x18006b021  call    cs:__imp_SysFreeString
0x18006b027  nop
0x18006b028  mov     rcx, [rbp+57h+var_90]
0x18006b02c  test    rcx, rcx
0x18006b02f  jz      short loc_18006B03E
0x18006b031  mov     rax, [rcx]
0x18006b034  mov     rax, [rax+10h]
0x18006b038  call    _guard_dispatch_icall
0x18006b03d  nop
0x18006b03e  mov     rcx, qword ptr [rbp+57h+var_68]
0x18006b042  test    rcx, rcx
0x18006b045  jz      short loc_18006B054
0x18006b047  mov     rax, [rcx]
0x18006b04a  mov     rax, [rax+10h]
0x18006b04e  call    _guard_dispatch_icall
0x18006b053  nop
0x18006b054  mov     rcx, [rbp+57h+var_60]; bstrString
0x18006b058  test    rcx, rcx
0x18006b05b  jz      short loc_18006B063
0x18006b05d  call    cs:__imp_SysFreeString
0x18006b063  mov     rax, r15
0x18006b066  mov     rcx, [rbp+57h+var_48]
0x18006b06a  xor     rcx, rsp; StackCookie
0x18006b06d  call    __security_check_cookie
0x18006b072  add     rsp, 0A8h
0x18006b079  pop     r15
0x18006b07b  pop     r14
0x18006b07d  pop     r13
0x18006b07f  pop     r12
0x18006b081  pop     rdi
0x18006b082  pop     rsi
0x18006b083  pop     rbx
0x18006b084  pop     rbp
0x18006b085  retn
0x18006b086  mov     r9d, eax; char *
0x18006b089  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006b090  mov     edx, 1D0h; void *
0x18006b095  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b09b  mov     r9d, eax; char *
0x18006b09e  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006b0a5  mov     edx, 1BCh; void *
0x18006b0aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b0b0  mov     r9d, eax; char *
0x18006b0b3  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006b0ba  mov     edx, 1C3h; void *
0x18006b0bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b0c5  mov     r9d, eax; char *
0x18006b0c8  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006b0cf  mov     edx, 1C4h; void *
0x18006b0d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b0da  mov     r9d, eax; char *
0x18006b0dd  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006b0e4  mov     edx, 1C7h; void *
0x18006b0e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b0ef  mov     r9d, eax; char *
0x18006b0f2  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006b0f9  mov     edx, 1CAh; void *
0x18006b0fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b104  mov     r9d, eax; char *
0x18006b107  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18006b10e  mov     edx, 1C96h; void *
0x18006b113  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b119  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18006b120  mov     edx, 138Dh; void *
0x18006b125  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18006b12b  mov     r9d, eax; char *
0x18006b12e  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006b135  mov     edx, 1CEh; void *
0x18006b13a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006b140  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18006b147  mov     edx, 138Dh; void *
0x18006b14c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
