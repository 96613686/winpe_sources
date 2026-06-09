# DockedClient::PauseStoreWindowsUpdate(void)

- ea: `0x1800362a0`
- end: `0x18003655f`
- name: `?PauseStoreWindowsUpdate@DockedClient@@UEAAJXZ`
- size: `703`
- prototype: `__int64 __fastcall(DockedClient *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x1800233b8`
- `0x180026f1c`
- `0x1800362a0`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036386`

## string_xrefs

- `0x18003631f`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x1800363b6`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x180036427`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x18003649d`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DockedClient::PauseStoreWindowsUpdate(DockedClient *this)
{
  __int64 *v1; // rax
  __int64 v2; // rbx
  int v3; // eax
  unsigned int v4; // edi
  __int64 *v5; // rdi
  __int64 v6; // rsi
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int v10; // eax
  int v11; // eax
  int v12; // eax
  _QWORD v14[2]; // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-48h] BYREF
  HSTRING string; // [rsp+48h] [rbp-30h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-28h] BYREF
  __int64 v18; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = (__int64 *)wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(v14);
  v2 = *v1;
  *v1 = 0;
  v14[1] = v2;
  if ( v14[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 16LL))(v14[0]);
  v17 = 0;
  v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v2)(
         v2,
         &GUID_20e1713b_cbcc_442d_b441_6440689b8912,
         &v17);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)(unsigned int)v3,
      v14[0]);
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
LABEL_23:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    return v4;
  }
  v5 = v17;
  v6 = *v17;
  string = 0;
  v7 = WindowsCreateStringReference(L"USO", 3u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x18003655DLL);
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v6 + 56))(v5, string, 0);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)(unsigned int)v10,
      v14[0]);
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    goto LABEL_23;
  }
  v18 = 0;
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v2)(
          v2,
          &GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e,
          &v18);
  v4 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)(unsigned int)v11,
      v14[0]);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    goto LABEL_23;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 48LL))(v18);
  v4 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)(unsigned int)v12,
      v14[0]);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    goto LABEL_23;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v17 )
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x1800362a0  mov     [rsp+arg_0], rbx
0x1800362a5  mov     [rsp+arg_8], rsi
0x1800362aa  push    rdi
0x1800362ab  sub     rsp, 70h
0x1800362af  mov     rax, cs:__security_cookie
0x1800362b6  xor     rax, rsp
0x1800362b9  mov     [rsp+78h+var_18], rax
0x1800362be  lea     rcx, [rsp+78h+var_58]
0x1800362c3  call    ??$ActivateInstance@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(ushort const *)
0x1800362c8  mov     rbx, [rax]
0x1800362cb  mov     qword ptr [rax], 0
0x1800362d2  mov     [rsp+78h+var_50], rbx
0x1800362d7  mov     rcx, [rsp+78h+var_58]
0x1800362dc  test    rcx, rcx
0x1800362df  jz      short loc_1800362EE
0x1800362e1  mov     rax, [rcx]
0x1800362e4  mov     rax, [rax+10h]
0x1800362e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362ed  nop
0x1800362ee  mov     [rsp+78h+var_28], 0
0x1800362f7  mov     rax, [rbx]
0x1800362fa  lea     r8, [rsp+78h+var_28]
0x1800362ff  lea     rdx, _GUID_20e1713b_cbcc_442d_b441_6440689b8912
0x180036306  mov     rcx, rbx
0x180036309  mov     rax, [rax]
0x18003630c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036311  mov     edi, eax
0x180036313  test    eax, eax
0x180036315  jns     short loc_18003635F
0x180036317  mov     rcx, [rsp+78h]; this
0x18003631c  mov     r9d, eax; char *
0x18003631f  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180036326  mov     edx, 86h; void *
0x18003632b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036330  nop
0x180036331  mov     rcx, [rsp+78h+var_28]
0x180036336  test    rcx, rcx
0x180036339  jz      short loc_180036348
0x18003633b  mov     rax, [rcx]
0x18003633e  mov     rax, [rax+10h]
0x180036342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036347  nop
0x180036348  mov     rax, [rbx]
0x18003634b  mov     rcx, rbx
0x18003634e  mov     rax, [rax+10h]
0x180036352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036357  nop
0x180036358  mov     eax, edi
0x18003635a  jmp     loc_180036537
0x18003635f  mov     rdi, [rsp+78h+var_28]
0x180036364  mov     rsi, [rdi]
0x180036367  mov     [rsp+78h+string], 0
0x180036370  lea     r9, [rsp+78h+string]; string
0x180036375  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18003637a  mov     edx, 3; length
0x18003637f  lea     rcx, aUso; "USO"
0x180036386  call    cs:__imp_WindowsCreateStringReference
0x18003638c  test    eax, eax
0x18003638e  js      loc_180036556
0x180036394  xor     r8d, r8d
0x180036397  mov     rdx, [rsp+78h+string]
0x18003639c  mov     rcx, rdi
0x18003639f  mov     rax, [rsi+38h]
0x1800363a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363a8  mov     edi, eax
0x1800363aa  test    eax, eax
0x1800363ac  jns     short loc_1800363F6
0x1800363ae  mov     rcx, [rsp+78h]; this
0x1800363b3  mov     r9d, eax; char *
0x1800363b6  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800363bd  mov     edx, 88h; void *
0x1800363c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800363c7  nop
0x1800363c8  mov     rcx, [rsp+78h+var_28]
0x1800363cd  test    rcx, rcx
0x1800363d0  jz      short loc_1800363DF
0x1800363d2  mov     rax, [rcx]
0x1800363d5  mov     rax, [rax+10h]
0x1800363d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363de  nop
0x1800363df  mov     rax, [rbx]
0x1800363e2  mov     rcx, rbx
0x1800363e5  mov     rax, [rax+10h]
0x1800363e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363ee  nop
0x1800363ef  mov     eax, edi
0x1800363f1  jmp     loc_180036537
0x1800363f6  mov     [rsp+78h+var_20], 0
0x1800363ff  mov     rax, [rbx]
0x180036402  lea     r8, [rsp+78h+var_20]
0x180036407  lea     rdx, _GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e
0x18003640e  mov     rcx, rbx
0x180036411  mov     rax, [rax]
0x180036414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036419  mov     edi, eax
0x18003641b  test    eax, eax
0x18003641d  jns     short loc_18003647E
0x18003641f  mov     rcx, [rsp+78h]; this
0x180036424  mov     r9d, eax; char *
0x180036427  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003642e  mov     edx, 8Bh; void *
0x180036433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036438  nop
0x180036439  mov     rcx, [rsp+78h+var_20]
0x18003643e  test    rcx, rcx
0x180036441  jz      short loc_180036450
0x180036443  mov     rax, [rcx]
0x180036446  mov     rax, [rax+10h]
0x18003644a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003644f  nop
0x180036450  mov     rcx, [rsp+78h+var_28]
0x180036455  test    rcx, rcx
0x180036458  jz      short loc_180036467
0x18003645a  mov     rax, [rcx]
0x18003645d  mov     rax, [rax+10h]
0x180036461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036466  nop
0x180036467  mov     rax, [rbx]
0x18003646a  mov     rcx, rbx
0x18003646d  mov     rax, [rax+10h]
0x180036471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036476  nop
0x180036477  mov     eax, edi
0x180036479  jmp     loc_180036537
0x18003647e  mov     rcx, [rsp+78h+var_20]
0x180036483  mov     rax, [rcx]
0x180036486  mov     rax, [rax+30h]
0x18003648a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003648f  mov     edi, eax
0x180036491  test    eax, eax
0x180036493  jns     short loc_1800364F1
0x180036495  mov     rcx, [rsp+78h]; this
0x18003649a  mov     r9d, eax; char *
0x18003649d  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800364a4  mov     edx, 8Ch; void *
0x1800364a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800364ae  nop
0x1800364af  mov     rcx, [rsp+78h+var_20]
0x1800364b4  test    rcx, rcx
0x1800364b7  jz      short loc_1800364C6
0x1800364b9  mov     rax, [rcx]
0x1800364bc  mov     rax, [rax+10h]
0x1800364c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364c5  nop
0x1800364c6  mov     rcx, [rsp+78h+var_28]
0x1800364cb  test    rcx, rcx
0x1800364ce  jz      short loc_1800364DD
0x1800364d0  mov     rax, [rcx]
0x1800364d3  mov     rax, [rax+10h]
0x1800364d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364dc  nop
0x1800364dd  mov     rax, [rbx]
0x1800364e0  mov     rcx, rbx
0x1800364e3  mov     rax, [rax+10h]
0x1800364e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364ec  nop
0x1800364ed  mov     eax, edi
0x1800364ef  jmp     short loc_180036537
0x1800364f1  mov     rcx, [rsp+78h+var_20]
0x1800364f6  test    rcx, rcx
0x1800364f9  jz      short loc_180036508
0x1800364fb  mov     rax, [rcx]
0x1800364fe  mov     rax, [rax+10h]
0x180036502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036507  nop
0x180036508  mov     rcx, [rsp+78h+var_28]
0x18003650d  test    rcx, rcx
0x180036510  jz      short loc_18003651F
0x180036512  mov     rax, [rcx]
0x180036515  mov     rax, [rax+10h]
0x180036519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003651e  nop
0x18003651f  mov     rax, [rbx]
0x180036522  mov     rcx, rbx
0x180036525  mov     rax, [rax+10h]
0x180036529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003652e  nop
0x18003652f  xor     eax, eax
0x180036531  jmp     short loc_180036537
0x180036533  mov     eax, dword ptr [rsp+78h+var_28]
0x180036537  mov     rcx, [rsp+78h+var_18]
0x18003653c  xor     rcx, rsp; StackCookie
0x18003653f  call    __security_check_cookie
0x180036544  lea     r11, [rsp+78h+var_8]
0x180036549  mov     rbx, [r11+10h]
0x18003654d  mov     rsi, [r11+18h]
0x180036551  mov     rsp, r11
0x180036554  pop     rdi
0x180036555  retn
0x180036556  mov     ecx, eax; this
0x180036558  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
