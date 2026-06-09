# Windows::Service::Task::UpdateMaintenanceSettings(std::chrono::duration<int,std::ratio<86400,1>>,std::chrono::duration<int,std::ratio<86400,1>>,bool)

- ea: `0x18006b5b4`
- end: `0x18006bb38`
- name: `?UpdateMaintenanceSettings@Task@Service@Windows@@QEAAXV?$duration@HU?$ratio@$0BFBIA@$00@std@@@chrono@std@@0_N@Z`
- size: `1412`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006c350`
- `0x18006c6c0`

## callees

- `0x1800112d0`
- `0x180011680`
- `0x18002b33c`
- `0x18002bbc0`
- `0x18002e698`
- `0x18003007c`
- `0x18006b5b4`
- `0x1800dd738`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006b7fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b956`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b7fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18006b956`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b840`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b995`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b9b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b9cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b840`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b995`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b9b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b9cc`

## string_xrefs

- `0x18006baea`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18006bb26`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18006ba6f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18006ba45`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006ba5a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006ba84`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006ba99`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006baae`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006bac3`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006bad8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006baff`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006bb14`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall Windows::Service::Task::UpdateMaintenanceSettings(_BYTE *a1, unsigned int a2, unsigned int a3)
{
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const wchar_t *v20; // rdx
  __int64 *v21; // rbx
  __int64 (__fastcall *v22)(__int64 *, BSTR); // r12
  const OLECHAR *v23; // rcx
  BSTR v24; // rax
  const char *v25; // r9
  OLECHAR *v26; // r14
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  const wchar_t *v33; // rdx
  __int64 *v34; // rbx
  __int64 (__fastcall *v35)(__int64 *, BSTR); // r14
  const OLECHAR *v36; // rcx
  BSTR v37; // rax
  const char *v38; // r9
  OLECHAR *v39; // rdi
  int v40; // eax
  int v41; // [rsp+28h] [rbp-E0h]
  __int128 Src_8; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v43; // [rsp+48h] [rbp-C0h]
  __int128 v44; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v45; // [rsp+68h] [rbp-A0h]
  _BYTE v46[32]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v47[32]; // [rsp+98h] [rbp-70h] BYREF
  __int64 *v48; // [rsp+B8h] [rbp-50h] BYREF
  __int16 v49; // [rsp+C0h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t *String1; // [rsp+D0h] [rbp-38h] BYREF
  __int64 *v52; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v53; // [rsp+E0h] [rbp-28h] BYREF
  wchar_t *psz[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v55; // [rsp+F8h] [rbp-10h]
  wchar_t *String2[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v57; // [rsp+118h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v41 = 0;
  v53 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)a1 + 88LL))(*(_QWORD *)a1, &v53);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v6,
      0);
  v52 = 0;
  v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v53)(
         v53,
         &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
         &v52);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v7,
      0);
  v48 = 0;
  v8 = *v52;
  v48 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v8 + 408))(v52, &v48);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x216,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v9,
      0);
  v10 = v48;
  if ( !v48 )
  {
    v11 = *v52;
    v48 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v11 + 424))(v52, &v48);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x21B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v12,
        0);
    v10 = v48;
  }
  v49 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v10 + 96))(v10, &v49);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v13,
      0);
  if ( v49 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v48 + 88))(v48, 0);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x224,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v14,
        0);
    a1[40] = 1;
  }
  String1 = 0;
  v15 = *v48;
  String1 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v15 + 64))(v48, &String1);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v16,
      0);
  v17 = std::to_wstring(v46, a2);
  v18 = std::wstring::insert(v17, 0, L"P", 1);
  Src_8 = 0;
  v43 = 0;
  Src_8 = *(_OWORD *)v18;
  v43 = *(_OWORD *)(v18 + 16);
  *(_WORD *)v18 = 0;
  *(_QWORD *)(v18 + 16) = 0;
  *(_QWORD *)(v18 + 24) = 7;
  v19 = std::wstring::append(&Src_8);
  *(_OWORD *)String2 = 0;
  v57 = 0;
  *(_OWORD *)String2 = *(_OWORD *)v19;
  v57 = *(_OWORD *)(v19 + 16);
  *(_WORD *)v19 = 0;
  *(_QWORD *)(v19 + 16) = 0;
  *(_QWORD *)(v19 + 24) = 7;
  std::wstring::~wstring(&Src_8);
  std::wstring::~wstring(v46);
  v20 = (const wchar_t *)String2;
  if ( *((_QWORD *)&v57 + 1) > 7u )
    v20 = String2[0];
  if ( wcsicmp(String1, v20) )
  {
    v21 = v48;
    v22 = *(__int64 (__fastcall **)(__int64 *, BSTR))(*v48 + 56);
    v23 = (const OLECHAR *)String2;
    if ( *((_QWORD *)&v57 + 1) > 7u )
      v23 = String2[0];
    v24 = SysAllocString(v23);
    v26 = v24;
    v41 = 71;
    if ( !v24 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    v27 = v22(v21, v24);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v27,
        71);
    SysFreeString(v26);
    a1[40] = 1;
  }
  bstrString = 0;
  v28 = *v48;
  bstrString = 0;
  v29 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v28 + 80))(v48, &bstrString);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v29,
      v41);
  v30 = std::to_wstring(v47, a3);
  v31 = std::wstring::insert(v30, 0, L"P", 1);
  v44 = 0;
  v45 = 0;
  v44 = *(_OWORD *)v31;
  v45 = *(_OWORD *)(v31 + 16);
  *(_WORD *)v31 = 0;
  *(_QWORD *)(v31 + 16) = 0;
  *(_QWORD *)(v31 + 24) = 7;
  v32 = std::wstring::append(&v44);
  *(_OWORD *)psz = 0;
  v55 = 0;
  *(_OWORD *)psz = *(_OWORD *)v32;
  v55 = *(_OWORD *)(v32 + 16);
  *(_WORD *)v32 = 0;
  *(_QWORD *)(v32 + 16) = 0;
  *(_QWORD *)(v32 + 24) = 7;
  std::wstring::~wstring(&v44);
  std::wstring::~wstring(v47);
  v33 = (const wchar_t *)psz;
  if ( *((_QWORD *)&v55 + 1) > 7u )
    v33 = psz[0];
  if ( wcsicmp(bstrString, v33) )
  {
    v34 = v48;
    v35 = *(__int64 (__fastcall **)(__int64 *, BSTR))(*v48 + 72);
    v36 = (const OLECHAR *)psz;
    if ( *((_QWORD *)&v55 + 1) > 7u )
      v36 = psz[0];
    v37 = SysAllocString(v36);
    v39 = v37;
    if ( !v37 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v38);
    v40 = v35(v34, v37);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v40,
        63);
    SysFreeString(v39);
    a1[40] = 1;
  }
  std::wstring::~wstring(psz);
  if ( bstrString )
    SysFreeString(bstrString);
  std::wstring::~wstring(String2);
  if ( String1 )
    SysFreeString(String1);
  if ( v48 )
    (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
  if ( v52 )
    (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
}

```

## disassembly

```asm
0x18006b5b4  mov     rax, rsp
0x18006b5b7  mov     [rax+10h], rbx
0x18006b5bb  mov     [rax+18h], rsi
0x18006b5bf  mov     [rax+20h], rdi
0x18006b5c3  push    rbp
0x18006b5c4  push    r12
0x18006b5c6  push    r13
0x18006b5c8  push    r14
0x18006b5ca  push    r15
0x18006b5cc  lea     rbp, [rax-58h]
0x18006b5d0  sub     rsp, 130h
0x18006b5d7  mov     rax, cs:__security_cookie
0x18006b5de  xor     rax, rsp
0x18006b5e1  mov     [rbp+50h+var_30], rax
0x18006b5e5  mov     edi, r8d
0x18006b5e8  mov     ebx, edx
0x18006b5ea  mov     r15, rcx
0x18006b5ed  xor     r13d, r13d
0x18006b5f0  mov     [rsp+150h+var_130], r13d; int
0x18006b5f5  mov     [rbp+50h+var_78], r13
0x18006b5f9  mov     rcx, [rcx]
0x18006b5fc  mov     rax, [rcx]
0x18006b5ff  mov     [rbp+50h+var_78], r13
0x18006b603  lea     rdx, [rbp+50h+var_78]
0x18006b607  mov     rax, [rax+58h]
0x18006b60b  call    _guard_dispatch_icall
0x18006b610  mov     rcx, [rbp+58h]; this
0x18006b614  test    eax, eax
0x18006b616  js      loc_18006BA57
0x18006b61c  mov     rcx, [rbp+50h+var_78]
0x18006b620  mov     [rbp+50h+var_80], r13
0x18006b624  mov     rax, [rcx]
0x18006b627  lea     r8, [rbp+50h+var_80]
0x18006b62b  lea     rdx, _GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528
0x18006b632  mov     rax, [rax]
0x18006b635  call    _guard_dispatch_icall
0x18006b63a  mov     rcx, [rbp+58h]; this
0x18006b63e  test    eax, eax
0x18006b640  js      loc_18006BA6C
0x18006b646  lea     r12d, [r13+1]
0x18006b64a  mov     esi, r12d
0x18006b64d  mov     [rbp+50h+var_A0], r13
0x18006b651  mov     rcx, [rbp+50h+var_80]
0x18006b655  mov     rax, [rcx]
0x18006b658  mov     [rbp+50h+var_A0], r13
0x18006b65c  lea     rdx, [rbp+50h+var_A0]
0x18006b660  mov     rax, [rax+198h]
0x18006b667  call    _guard_dispatch_icall
0x18006b66c  mov     rcx, [rbp+58h]; this
0x18006b670  test    eax, eax
0x18006b672  js      loc_18006BA81
0x18006b678  mov     rcx, [rbp+50h+var_A0]
0x18006b67c  test    rcx, rcx
0x18006b67f  jnz     short loc_18006B6AC
0x18006b681  mov     rcx, [rbp+50h+var_80]
0x18006b685  mov     rax, [rcx]
0x18006b688  mov     [rbp+50h+var_A0], r13
0x18006b68c  lea     rdx, [rbp+50h+var_A0]
0x18006b690  mov     rax, [rax+1A8h]
0x18006b697  call    _guard_dispatch_icall
0x18006b69c  mov     rcx, [rbp+58h]; this
0x18006b6a0  test    eax, eax
0x18006b6a2  js      loc_18006BA96
0x18006b6a8  mov     rcx, [rbp+50h+var_A0]
0x18006b6ac  mov     [rbp+50h+var_98], r13w
0x18006b6b1  mov     rax, [rcx]
0x18006b6b4  lea     rdx, [rbp+50h+var_98]
0x18006b6b8  mov     rax, [rax+60h]
0x18006b6bc  call    _guard_dispatch_icall
0x18006b6c1  mov     rcx, [rbp+58h]; this
0x18006b6c5  test    eax, eax
0x18006b6c7  js      loc_18006BAAB
0x18006b6cd  cmp     [rbp+50h+var_98], r13w
0x18006b6d2  jz      short loc_18006B6F6
0x18006b6d4  xor     edx, edx
0x18006b6d6  mov     rcx, [rbp+50h+var_A0]
0x18006b6da  mov     rax, [rcx]
0x18006b6dd  mov     rax, [rax+58h]
0x18006b6e1  call    _guard_dispatch_icall
0x18006b6e6  mov     rcx, [rbp+58h]; this
0x18006b6ea  test    eax, eax
0x18006b6ec  js      loc_18006BAC0
0x18006b6f2  mov     [r15+28h], r12b
0x18006b6f6  mov     [rbp+50h+String1], r13
0x18006b6fa  mov     rcx, [rbp+50h+var_A0]
0x18006b6fe  mov     rax, [rcx]
0x18006b701  mov     [rbp+50h+String1], r13
0x18006b705  lea     rdx, [rbp+50h+String1]
0x18006b709  mov     rax, [rax+40h]
0x18006b70d  call    _guard_dispatch_icall
0x18006b712  mov     rcx, [rbp+58h]; this
0x18006b716  test    eax, eax
0x18006b718  js      loc_18006BAD5
0x18006b71e  mov     edx, ebx
0x18006b720  lea     rcx, [rsp+150h+var_E0]
0x18006b725  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x18006b72a  nop
0x18006b72b  mov     r9, r12
0x18006b72e  lea     r8, aP; "P"
0x18006b735  xor     edx, edx
0x18006b737  mov     rcx, rax
0x18006b73a  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x18006b73f  xorps   xmm0, xmm0
0x18006b742  movups  [rsp+150h+Src+8], xmm0
0x18006b747  xorps   xmm1, xmm1
0x18006b74a  movdqu  [rsp+150h+var_118+8], xmm1
0x18006b750  movups  xmm0, xmmword ptr [rax]
0x18006b753  movups  [rsp+150h+Src+8], xmm0
0x18006b758  movups  xmm1, xmmword ptr [rax+10h]
0x18006b75c  movups  [rsp+150h+var_118+8], xmm1
0x18006b761  mov     [rax], r13w
0x18006b765  mov     [rax+10h], r13
0x18006b769  mov     r14d, 7
0x18006b76f  mov     [rax+18h], r14
0x18006b773  or      esi, 2
0x18006b776  mov     r8, r12
0x18006b779  lea     rdx, aD_1; "D"
0x18006b780  lea     rcx, [rsp+150h+Src+8]; Src
0x18006b785  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18006b78a  xorps   xmm0, xmm0
0x18006b78d  movups  xmmword ptr [rbp+50h+String2], xmm0
0x18006b791  xorps   xmm1, xmm1
0x18006b794  movdqu  [rbp+50h+var_40], xmm1
0x18006b799  movups  xmm0, xmmword ptr [rax]
0x18006b79c  movups  xmmword ptr [rbp+50h+String2], xmm0
0x18006b7a0  movups  xmm1, xmmword ptr [rax+10h]
0x18006b7a4  movups  [rbp+50h+var_40], xmm1
0x18006b7a8  mov     [rax], r13w
0x18006b7ac  mov     [rax+10h], r13
0x18006b7b0  mov     [rax+18h], r14
0x18006b7b4  or      esi, 4
0x18006b7b7  lea     rcx, [rsp+150h+Src+8]; void *
0x18006b7bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b7c1  nop
0x18006b7c2  lea     rcx, [rsp+150h+var_E0]; void *
0x18006b7c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b7cc  lea     rdx, [rbp+50h+String2]
0x18006b7d0  cmp     qword ptr [rbp+50h+var_40+8], r14
0x18006b7d4  cmova   rdx, [rbp+50h+String2]; String2
0x18006b7d9  mov     rcx, [rbp+50h+String1]; String1
0x18006b7dd  call    _wcsicmp
0x18006b7e2  test    eax, eax
0x18006b7e4  jz      short loc_18006B855
0x18006b7e6  mov     rbx, [rbp+50h+var_A0]
0x18006b7ea  mov     rax, [rbx]
0x18006b7ed  mov     r12, [rax+38h]
0x18006b7f1  lea     rcx, [rbp+50h+String2]
0x18006b7f5  cmp     qword ptr [rbp+50h+var_40+8], r14
0x18006b7f9  cmova   rcx, [rbp+50h+String2]; psz
0x18006b7fe  call    cs:__imp_SysAllocString
0x18006b804  mov     r14, rax
0x18006b807  mov     qword ptr [rsp+150h+Src], rax
0x18006b80c  or      esi, 40h
0x18006b80f  mov     [rsp+150h+var_130], esi; int
0x18006b813  mov     rcx, [rbp+58h]; this
0x18006b817  test    rax, rax
0x18006b81a  jz      loc_18006BAEA
0x18006b820  mov     rdx, rax
0x18006b823  mov     rcx, rbx
0x18006b826  mov     rax, r12
0x18006b829  call    _guard_dispatch_icall
0x18006b82e  mov     rcx, [rbp+58h]; this
0x18006b832  test    eax, eax
0x18006b834  js      loc_18006BAFC
0x18006b83a  and     esi, 0FFFFFFBFh
0x18006b83d  mov     rcx, r14; bstrString
0x18006b840  call    cs:__imp_SysFreeString
0x18006b846  mov     r12d, 1
0x18006b84c  mov     [r15+28h], r12b
0x18006b850  lea     r14d, [r12+6]
0x18006b855  mov     [rbp+50h+bstrString], r13
0x18006b859  mov     rcx, [rbp+50h+var_A0]
0x18006b85d  mov     rax, [rcx]
0x18006b860  mov     [rbp+50h+bstrString], r13
0x18006b864  lea     rdx, [rbp+50h+bstrString]
0x18006b868  mov     rax, [rax+50h]
0x18006b86c  call    _guard_dispatch_icall
0x18006b871  mov     rcx, [rbp+58h]; this
0x18006b875  test    eax, eax
0x18006b877  js      loc_18006BB11
0x18006b87d  mov     edx, edi
0x18006b87f  lea     rcx, [rbp+50h+var_C0]
0x18006b883  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x18006b888  nop
0x18006b889  mov     r9, r12
0x18006b88c  lea     r8, aP; "P"
0x18006b893  xor     edx, edx
0x18006b895  mov     rcx, rax
0x18006b898  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x18006b89d  xorps   xmm0, xmm0
0x18006b8a0  movups  [rsp+150h+var_108+8], xmm0
0x18006b8a5  xorps   xmm1, xmm1
0x18006b8a8  movdqu  xmmword ptr [rsp+150h+var_F8+8], xmm1
0x18006b8ae  movups  xmm0, xmmword ptr [rax]
0x18006b8b1  movups  [rsp+150h+var_108+8], xmm0
0x18006b8b6  movups  xmm1, xmmword ptr [rax+10h]
0x18006b8ba  movups  xmmword ptr [rsp+150h+var_F8+8], xmm1
0x18006b8bf  mov     [rax], r13w
0x18006b8c3  mov     [rax+10h], r13
0x18006b8c7  mov     [rax+18h], r14
0x18006b8cb  or      esi, 8
0x18006b8ce  mov     r8, r12
0x18006b8d1  lea     rdx, aD_1; "D"
0x18006b8d8  lea     rcx, [rsp+150h+var_108+8]; Src
0x18006b8dd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18006b8e2  xorps   xmm0, xmm0
0x18006b8e5  movups  xmmword ptr [rbp+50h+psz], xmm0
0x18006b8e9  xorps   xmm1, xmm1
0x18006b8ec  movdqu  [rbp+50h+var_60], xmm1
0x18006b8f1  movups  xmm0, xmmword ptr [rax]
0x18006b8f4  movups  xmmword ptr [rbp+50h+psz], xmm0
0x18006b8f8  movups  xmm1, xmmword ptr [rax+10h]
0x18006b8fc  movups  [rbp+50h+var_60], xmm1
0x18006b900  mov     [rax], r13w
0x18006b904  mov     [rax+10h], r13
0x18006b908  mov     [rax+18h], r14
0x18006b90c  or      esi, 10h
0x18006b90f  lea     rcx, [rsp+150h+var_108+8]; void *
0x18006b914  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b919  nop
0x18006b91a  lea     rcx, [rbp+50h+var_C0]; void *
0x18006b91e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b923  lea     rdx, [rbp+50h+psz]
0x18006b927  cmp     qword ptr [rbp+50h+var_60+8], r14
0x18006b92b  cmova   rdx, [rbp+50h+psz]; String2
0x18006b930  mov     rcx, [rbp+50h+bstrString]; String1
0x18006b934  call    _wcsicmp
0x18006b939  test    eax, eax
0x18006b93b  jz      short loc_18006B99F
0x18006b93d  mov     rbx, [rbp+50h+var_A0]
0x18006b941  mov     rax, [rbx]
0x18006b944  mov     r14, [rax+48h]
0x18006b948  lea     rcx, [rbp+50h+psz]
0x18006b94c  cmp     qword ptr [rbp+50h+var_60+8], 7
0x18006b951  cmova   rcx, [rbp+50h+psz]; psz
0x18006b956  call    cs:__imp_SysAllocString
0x18006b95c  mov     rdi, rax
0x18006b95f  mov     qword ptr [rsp+150h+Src], rax
0x18006b964  or      esi, 20h
0x18006b967  mov     [rsp+150h+var_130], esi; int
0x18006b96b  mov     rcx, [rbp+58h]; this
0x18006b96f  test    rax, rax
0x18006b972  jz      loc_18006BB26
0x18006b978  mov     rdx, rax
0x18006b97b  mov     rcx, rbx
0x18006b97e  mov     rax, r14
0x18006b981  call    _guard_dispatch_icall
0x18006b986  mov     rcx, [rbp+58h]; this
0x18006b98a  test    eax, eax
0x18006b98c  js      loc_18006BA42
0x18006b992  mov     rcx, rdi; bstrString
0x18006b995  call    cs:__imp_SysFreeString
0x18006b99b  mov     [r15+28h], r12b
0x18006b99f  lea     rcx, [rbp+50h+psz]; void *
0x18006b9a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b9a8  nop
0x18006b9a9  mov     rcx, [rbp+50h+bstrString]; bstrString
0x18006b9ad  test    rcx, rcx
0x18006b9b0  jz      short loc_18006B9B9
0x18006b9b2  call    cs:__imp_SysFreeString
0x18006b9b8  nop
0x18006b9b9  lea     rcx, [rbp+50h+String2]; void *
0x18006b9bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006b9c2  nop
0x18006b9c3  mov     rcx, [rbp+50h+String1]; bstrString
0x18006b9c7  test    rcx, rcx
0x18006b9ca  jz      short loc_18006B9D3
0x18006b9cc  call    cs:__imp_SysFreeString
0x18006b9d2  nop
0x18006b9d3  mov     rcx, [rbp+50h+var_A0]
0x18006b9d7  test    rcx, rcx
0x18006b9da  jz      short loc_18006B9E9
0x18006b9dc  mov     rax, [rcx]
0x18006b9df  mov     rax, [rax+10h]
0x18006b9e3  call    _guard_dispatch_icall
0x18006b9e8  nop
0x18006b9e9  mov     rcx, [rbp+50h+var_80]
0x18006b9ed  test    rcx, rcx
0x18006b9f0  jz      short loc_18006B9FF
0x18006b9f2  mov     rax, [rcx]
0x18006b9f5  mov     rax, [rax+10h]
0x18006b9f9  call    _guard_dispatch_icall
0x18006b9fe  nop
0x18006b9ff  mov     rcx, [rbp+50h+var_78]
0x18006ba03  test    rcx, rcx
0x18006ba06  jz      short loc_18006BA15
0x18006ba08  mov     rax, [rcx]
0x18006ba0b  mov     rax, [rax+10h]
0x18006ba0f  call    _guard_dispatch_icall
0x18006ba14  nop
0x18006ba15  mov     rcx, [rbp+50h+var_30]
0x18006ba19  xor     rcx, rsp; StackCookie
0x18006ba1c  call    __security_check_cookie
0x18006ba21  lea     r11, [rsp+150h+var_20]
0x18006ba29  mov     rbx, [r11+38h]
0x18006ba2d  mov     rsi, [r11+40h]
0x18006ba31  mov     rdi, [r11+48h]
0x18006ba35  mov     rsp, r11
0x18006ba38  pop     r15
0x18006ba3a  pop     r14
  ... truncated ...
```
