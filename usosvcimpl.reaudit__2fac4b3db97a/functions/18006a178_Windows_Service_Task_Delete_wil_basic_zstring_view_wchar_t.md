# Windows::Service::Task::Delete(wil::basic_zstring_view<wchar_t>)

- ea: `0x18006a178`
- end: `0x18006a3fe`
- name: `?Delete@Task@Service@Windows@@SAXV?$basic_zstring_view@_W@wil@@@Z`
- size: `646`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18006c320`
- `0x18006d930`

## callees

- `0x1800112d0`
- `0x180041480`
- `0x180068d48`
- `0x180068ef4`
- `0x18006a178`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006a357`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a37d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a357`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a37d`

## string_xrefs

- `0x18006a1c0`: `Microsoft\Windows\UpdateOrchestrator`
- `0x18006a3c2`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a3d7`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a3ec`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall Windows::Service::Task::Delete(_QWORD *a1)
{
  struct ITaskServiceVtbl *lpVtbl; // rax
  int v3; // eax
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  _QWORD *System; // rax
  __int64 **v8; // rax
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r8
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  _QWORD v14[2]; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v15[8]; // [rsp+30h] [rbp-50h] BYREF
  volatile signed __int32 *v16; // [rsp+38h] [rbp-48h]
  _BYTE v17[8]; // [rsp+40h] [rbp-40h] BYREF
  volatile signed __int32 *v18; // [rsp+48h] [rbp-38h]
  BSTR bstrString; // [rsp+50h] [rbp-30h] BYREF
  __int64 *v20; // [rsp+58h] [rbp-28h] BYREF
  struct ITaskService *v21; // [rsp+60h] [rbp-20h] BYREF
  __int64 v22; // [rsp+68h] [rbp-18h] BYREF
  BSTR v23; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v21 = 0;
  Windows::Service::Task::TaskService((LPVOID *)&v21);
  Windows::Service::Task::EnsureTaskFolderExists(v21);
  v23 = 0;
  wil::make_bstr(&v23, L"Microsoft\\Windows\\UpdateOrchestrator");
  v20 = 0;
  lpVtbl = v21->lpVtbl;
  v20 = 0;
  v3 = ((__int64 (__fastcall *)(struct ITaskService *, BSTR, __int64 **))lpVtbl->GetFolder)(v21, v23, &v20);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v3,
      v14[0]);
  bstrString = 0;
  wil::make_bstr(&bstrString, *a1);
  v22 = 0;
  v4 = *v20;
  v22 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(v4 + 104))(v20, bstrString, &v22);
  if ( (unsigned int)(v5 + 2147024894) > 1 )
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v5,
        v14[0]);
    v6 = (*(__int64 (__fastcall **)(__int64 *, BSTR, _QWORD))(*v20 + 120))(v20, bstrString, 0);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x134,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v6,
        v14[0]);
    System = (_QWORD *)SystemInterface::Service::GetSystem(v17);
    v8 = (__int64 **)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 104LL))(*System, v15);
    v9 = *v8;
    v10 = **v8;
    v11 = -1;
    do
      ++v11;
    while ( bstrString[v11] );
    v14[0] = bstrString;
    v14[1] = v11;
    (*(void (__fastcall **)(__int64 *, _QWORD *))(v10 + 208))(v9, v14);
    v12 = v16;
    if ( v16 )
    {
      if ( !_InterlockedDecrement(v16 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( !_InterlockedDecrement(v12 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v13 = v18;
    if ( v18 )
    {
      if ( !_InterlockedDecrement(v18 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( !_InterlockedDecrement(v13 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v20 )
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
  if ( v23 )
    SysFreeString(v23);
  if ( v21 )
    ((void (__fastcall *)(struct ITaskService *))v21->lpVtbl->Release)(v21);
}

```

## disassembly

```asm
0x18006a178  mov     [rsp-8+arg_8], rbx
0x18006a17d  mov     [rsp-8+arg_10], rsi
0x18006a182  mov     [rsp-8+arg_18], rdi
0x18006a187  push    rbp
0x18006a188  mov     rbp, rsp
0x18006a18b  sub     rsp, 80h
0x18006a192  mov     rax, cs:__security_cookie
0x18006a199  xor     rax, rsp
0x18006a19c  mov     [rbp+var_8], rax
0x18006a1a0  mov     rbx, rcx
0x18006a1a3  xor     edi, edi
0x18006a1a5  mov     [rbp+var_20], rdi
0x18006a1a9  lea     rcx, [rbp+var_20]; int
0x18006a1ad  call    ?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::TaskService(void)
0x18006a1b2  nop
0x18006a1b3  mov     rcx, [rbp+var_20]; struct ITaskService *
0x18006a1b7  call    ?EnsureTaskFolderExists@Task@Service@Windows@@CAXPEAUITaskService@@@Z; Windows::Service::Task::EnsureTaskFolderExists(ITaskService *)
0x18006a1bc  mov     [rbp+var_10], rdi
0x18006a1c0  lea     rdx, sourceString; "Microsoft\\Windows\\UpdateOrchestrator"
0x18006a1c7  lea     rcx, [rbp+var_10]
0x18006a1cb  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x18006a1d0  nop
0x18006a1d1  mov     [rbp+var_28], rdi
0x18006a1d5  mov     rcx, [rbp+var_20]
0x18006a1d9  mov     rax, [rcx]
0x18006a1dc  mov     [rbp+var_28], rdi
0x18006a1e0  lea     r8, [rbp+var_28]
0x18006a1e4  mov     rdx, [rbp+var_10]
0x18006a1e8  mov     rax, [rax+38h]
0x18006a1ec  call    _guard_dispatch_icall
0x18006a1f1  mov     rcx, [rbp+8]; this
0x18006a1f5  test    eax, eax
0x18006a1f7  js      loc_18006A3D4
0x18006a1fd  mov     [rbp+bstrString], rdi
0x18006a201  mov     rdx, [rbx]
0x18006a204  lea     rcx, [rbp+bstrString]
0x18006a208  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x18006a20d  nop
0x18006a20e  mov     [rbp+var_18], rdi
0x18006a212  mov     rcx, [rbp+var_28]
0x18006a216  mov     rax, [rcx]
0x18006a219  mov     [rbp+var_18], rdi
0x18006a21d  lea     r8, [rbp+var_18]
0x18006a221  mov     rdx, [rbp+bstrString]
0x18006a225  mov     rax, [rax+68h]
0x18006a229  call    _guard_dispatch_icall
0x18006a22e  lea     ecx, [rax+7FF8FFFEh]
0x18006a234  cmp     ecx, 1
0x18006a237  jbe     loc_18006A338
0x18006a23d  mov     rcx, [rbp+8]; this
0x18006a241  test    eax, eax
0x18006a243  js      loc_18006A3E9
0x18006a249  mov     rcx, [rbp+var_28]
0x18006a24d  mov     rax, [rcx]
0x18006a250  xor     r8d, r8d
0x18006a253  mov     rdx, [rbp+bstrString]
0x18006a257  mov     rax, [rax+78h]
0x18006a25b  call    _guard_dispatch_icall
0x18006a260  mov     rcx, [rbp+8]; this
0x18006a264  test    eax, eax
0x18006a266  js      loc_18006A3BF
0x18006a26c  lea     rcx, [rbp+var_40]
0x18006a270  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18006a275  nop
0x18006a276  mov     rcx, [rax]
0x18006a279  mov     rax, [rcx]
0x18006a27c  lea     rdx, [rbp+var_50]
0x18006a280  mov     rax, [rax+68h]
0x18006a284  call    _guard_dispatch_icall
0x18006a289  nop
0x18006a28a  mov     rcx, [rax]
0x18006a28d  mov     rax, [rcx]
0x18006a290  mov     rdx, [rbp+bstrString]
0x18006a294  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006a298  mov     r8, rsi
0x18006a29b  inc     r8
0x18006a29e  cmp     [rdx+r8*2], di
0x18006a2a3  jnz     short loc_18006A29B
0x18006a2a5  mov     [rbp+var_60], rdx
0x18006a2a9  mov     [rbp+var_58], r8
0x18006a2ad  lea     rdx, [rbp+var_60]
0x18006a2b1  mov     rax, [rax+0D0h]
0x18006a2b8  call    _guard_dispatch_icall
0x18006a2bd  nop
0x18006a2be  mov     rbx, [rbp+var_48]
0x18006a2c2  test    rbx, rbx
0x18006a2c5  jz      short loc_18006A2FB
0x18006a2c7  mov     eax, esi
0x18006a2c9  lock xadd [rbx+8], eax
0x18006a2ce  add     eax, esi
0x18006a2d0  jnz     short loc_18006A2FB
0x18006a2d2  mov     rax, [rbx]
0x18006a2d5  mov     rcx, rbx
0x18006a2d8  mov     rax, [rax]
0x18006a2db  call    _guard_dispatch_icall
0x18006a2e0  mov     eax, esi
0x18006a2e2  lock xadd [rbx+0Ch], eax
0x18006a2e7  add     eax, esi
0x18006a2e9  jnz     short loc_18006A2FB
0x18006a2eb  mov     rax, [rbx]
0x18006a2ee  mov     rcx, rbx
0x18006a2f1  mov     rax, [rax+8]
0x18006a2f5  call    _guard_dispatch_icall
0x18006a2fa  nop
0x18006a2fb  mov     rbx, [rbp+var_38]
0x18006a2ff  test    rbx, rbx
0x18006a302  jz      short loc_18006A338
0x18006a304  mov     eax, esi
0x18006a306  lock xadd [rbx+8], eax
0x18006a30b  add     eax, esi
0x18006a30d  jnz     short loc_18006A338
0x18006a30f  mov     rax, [rbx]
0x18006a312  mov     rcx, rbx
0x18006a315  mov     rax, [rax]
0x18006a318  call    _guard_dispatch_icall
0x18006a31d  mov     eax, esi
0x18006a31f  lock xadd [rbx+0Ch], eax
0x18006a324  add     eax, esi
0x18006a326  jnz     short loc_18006A338
0x18006a328  mov     rax, [rbx]
0x18006a32b  mov     rcx, rbx
0x18006a32e  mov     rax, [rax+8]
0x18006a332  call    _guard_dispatch_icall
0x18006a337  nop
0x18006a338  mov     rcx, [rbp+var_18]
0x18006a33c  test    rcx, rcx
0x18006a33f  jz      short loc_18006A34E
0x18006a341  mov     rax, [rcx]
0x18006a344  mov     rax, [rax+10h]
0x18006a348  call    _guard_dispatch_icall
0x18006a34d  nop
0x18006a34e  mov     rcx, [rbp+bstrString]; bstrString
0x18006a352  test    rcx, rcx
0x18006a355  jz      short loc_18006A35E
0x18006a357  call    cs:__imp_SysFreeString
0x18006a35d  nop
0x18006a35e  mov     rcx, [rbp+var_28]
0x18006a362  test    rcx, rcx
0x18006a365  jz      short loc_18006A374
0x18006a367  mov     rax, [rcx]
0x18006a36a  mov     rax, [rax+10h]
0x18006a36e  call    _guard_dispatch_icall
0x18006a373  nop
0x18006a374  mov     rcx, [rbp+var_10]; bstrString
0x18006a378  test    rcx, rcx
0x18006a37b  jz      short loc_18006A384
0x18006a37d  call    cs:__imp_SysFreeString
0x18006a383  nop
0x18006a384  mov     rcx, [rbp+var_20]
0x18006a388  test    rcx, rcx
0x18006a38b  jz      short loc_18006A39A
0x18006a38d  mov     rax, [rcx]
0x18006a390  mov     rax, [rax+10h]
0x18006a394  call    _guard_dispatch_icall
0x18006a399  nop
0x18006a39a  mov     rcx, [rbp+var_8]
0x18006a39e  xor     rcx, rsp; StackCookie
0x18006a3a1  call    __security_check_cookie
0x18006a3a6  lea     r11, [rsp+80h+var_s0]
0x18006a3ae  mov     rbx, [r11+18h]
0x18006a3b2  mov     rsi, [r11+20h]
0x18006a3b6  mov     rdi, [r11+28h]
0x18006a3ba  mov     rsp, r11
0x18006a3bd  pop     rbp
0x18006a3be  retn
0x18006a3bf  mov     r9d, eax; char *
0x18006a3c2  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a3c9  mov     edx, 134h; void *
0x18006a3ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a3d4  mov     r9d, eax; char *
0x18006a3d7  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a3de  mov     edx, 124h; void *
0x18006a3e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a3e9  mov     r9d, eax; char *
0x18006a3ec  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a3f3  mov     edx, 131h; void *
0x18006a3f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
