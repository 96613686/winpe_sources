# CLocalDisconnectPlugin::GetCurrentConnectedUser(IUserData *,IConnectedUser * *)

- ea: `0x18005acac`
- end: `0x18005ae3e`
- name: `?GetCurrentConnectedUser@CLocalDisconnectPlugin@@AEAAJPEAUIUserData@@PEAPEAUIConnectedUser@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(CLocalDisconnectPlugin *__hidden this, struct IUserData *, struct IConnectedUser **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180059ba8`
- `0x18005a6f0`
- `0x18005b6d0`

## callees

- `0x180006a54`
- `0x180006a74`
- `0x18005acac`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005ad8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005ad8e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ad1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ae2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ad1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ae2d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005add8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005add8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ad61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ae1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ad61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ae1e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005ad37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005ad37`

## string_xrefs

- `0x18005acfd`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005ad45`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005ada3`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`

## pseudocode

```c
__int64 __fastcall CLocalDisconnectPlugin::GetCurrentConnectedUser(
        CLocalDisconnectPlugin *this,
        struct IUserData *a2,
        struct IConnectedUser **a3)
{
  __int64 v3; // rax
  int v5; // eax
  HRESULT LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, PSID, _QWORD, struct IConnectedUser **); // rbx
  DWORD LengthSid; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  CLocalDisconnectPlugin *v16; // [rsp+60h] [rbp+28h] BYREF
  PSID Sid; // [rsp+68h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+38h] BYREF
  LPVOID v19; // [rsp+78h] [rbp+40h] BYREF

  v16 = this;
  *a3 = 0;
  v3 = *(_QWORD *)a2;
  LODWORD(v16) = 0;
  bstrString = 0;
  v5 = (*(__int64 (__fastcall **)(struct IUserData *, const WCHAR *, BSTR *, CLocalDisconnectPlugin **))(v3 + 88))(
         a2,
         L"SID",
         &bstrString,
         &v16);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x243,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v5,
      ppv);
LABEL_3:
    if ( bstrString )
      SysFreeString(bstrString);
    return (unsigned int)LastError;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(bstrString, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x246,
                  (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
                  v8);
LABEL_8:
    if ( Sid )
      LocalFree(Sid);
    goto LABEL_3;
  }
  v19 = 0;
  LastError = CoCreateInstance(
                &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
                0,
                1u,
                &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
                &v19);
  if ( LastError < 0 )
  {
    v9 = 588;
    goto LABEL_12;
  }
  v10 = v19;
  v11 = *(__int64 (__fastcall **)(LPVOID, PSID, _QWORD, struct IConnectedUser **))(*(_QWORD *)v19 + 64LL);
  LengthSid = GetLengthSid(Sid);
  LastError = v11(v10, Sid, LengthSid, a3);
  if ( LastError < 0 )
  {
    v9 = 592;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)LastError,
      ppva);
    if ( v19 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    goto LABEL_8;
  }
  if ( v19 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  if ( Sid )
    LocalFree(Sid);
  if ( bstrString )
    SysFreeString(bstrString);
  return 0;
}

```

## disassembly

```asm
0x18005acac  mov     [rsp-20h+arg_0], rcx
0x18005acb1  push    rbp
0x18005acb2  push    rbx
0x18005acb3  push    rsi
0x18005acb4  push    rdi
0x18005acb5  mov     rbp, rsp
0x18005acb8  sub     rsp, 38h
0x18005acbc  mov     qword ptr [r8], 0
0x18005acc3  lea     r9, [rbp+arg_0]
0x18005acc7  mov     rax, [rdx]
0x18005acca  mov     rsi, r8
0x18005accd  mov     rcx, rdx
0x18005acd0  mov     dword ptr [rbp+arg_0], 0
0x18005acd7  lea     r8, [rbp+bstrString]
0x18005acdb  mov     [rbp+bstrString], 0
0x18005ace3  lea     rdx, aSid_0; "SID"
0x18005acea  mov     rax, [rax+58h]
0x18005acee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005acf3  mov     ebx, eax
0x18005acf5  test    eax, eax
0x18005acf7  jns     short loc_18005AD27
0x18005acf9  mov     rcx, [rbp+20h]; this
0x18005acfd  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005ad04  mov     r9d, eax; char *
0x18005ad07  mov     edx, 243h; void *
0x18005ad0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ad11  mov     rcx, [rbp+bstrString]; bstrString
0x18005ad15  test    rcx, rcx
0x18005ad18  jz      short loc_18005AD20
0x18005ad1a  call    cs:__imp_SysFreeString
0x18005ad20  mov     eax, ebx
0x18005ad22  jmp     loc_18005AE35
0x18005ad27  mov     rcx, [rbp+bstrString]; StringSid
0x18005ad2b  lea     rdx, [rbp+Sid]; Sid
0x18005ad2f  mov     [rbp+Sid], 0
0x18005ad37  call    cs:__imp_ConvertStringSidToSidW
0x18005ad3d  test    eax, eax
0x18005ad3f  jnz     short loc_18005AD69
0x18005ad41  mov     rcx, [rbp+20h]; this
0x18005ad45  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005ad4c  mov     edx, 246h; void *
0x18005ad51  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005ad56  mov     ebx, eax
0x18005ad58  mov     rcx, [rbp+Sid]; hMem
0x18005ad5c  test    rcx, rcx
0x18005ad5f  jz      short loc_18005AD11
0x18005ad61  call    cs:__imp_LocalFree
0x18005ad67  jmp     short loc_18005AD11
0x18005ad69  xor     edx, edx; pUnkOuter
0x18005ad6b  mov     [rbp+arg_18], 0
0x18005ad73  lea     rax, [rbp+arg_18]
0x18005ad77  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x18005ad7e  mov     qword ptr [rsp+38h+ppv], rax; int
0x18005ad83  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x18005ad8a  lea     r8d, [rdx+1]; dwClsContext
0x18005ad8e  call    cs:__imp_CoCreateInstance
0x18005ad94  mov     ebx, eax
0x18005ad96  test    eax, eax
0x18005ad98  jns     short loc_18005ADC9
0x18005ad9a  mov     edx, 24Ch; void *
0x18005ad9f  mov     rcx, [rbp+20h]; this
0x18005ada3  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005adaa  mov     r9d, ebx; char *
0x18005adad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005adb2  mov     rcx, [rbp+arg_18]
0x18005adb6  test    rcx, rcx
0x18005adb9  jz      short loc_18005AD58
0x18005adbb  mov     rdx, [rcx]
0x18005adbe  mov     rax, [rdx+10h]
0x18005adc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005adc7  jmp     short loc_18005AD58
0x18005adc9  mov     rdi, [rbp+arg_18]
0x18005adcd  mov     rcx, [rbp+Sid]; pSid
0x18005add1  mov     rax, [rdi]
0x18005add4  mov     rbx, [rax+40h]
0x18005add8  call    cs:__imp_GetLengthSid
0x18005adde  mov     rdx, [rbp+Sid]
0x18005ade2  mov     r9, rsi
0x18005ade5  mov     r8d, eax
0x18005ade8  mov     rcx, rdi
0x18005adeb  mov     rax, rbx
0x18005adee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005adf3  mov     ebx, eax
0x18005adf5  test    eax, eax
0x18005adf7  jns     short loc_18005AE00
0x18005adf9  mov     edx, 250h
0x18005adfe  jmp     short loc_18005AD9F
0x18005ae00  mov     rcx, [rbp+arg_18]
0x18005ae04  test    rcx, rcx
0x18005ae07  jz      short loc_18005AE15
0x18005ae09  mov     rax, [rcx]
0x18005ae0c  mov     rax, [rax+10h]
0x18005ae10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae15  mov     rcx, [rbp+Sid]; hMem
0x18005ae19  test    rcx, rcx
0x18005ae1c  jz      short loc_18005AE24
0x18005ae1e  call    cs:__imp_LocalFree
0x18005ae24  mov     rcx, [rbp+bstrString]; bstrString
0x18005ae28  test    rcx, rcx
0x18005ae2b  jz      short loc_18005AE33
0x18005ae2d  call    cs:__imp_SysFreeString
0x18005ae33  xor     eax, eax
0x18005ae35  add     rsp, 38h
0x18005ae39  pop     rdi
0x18005ae3a  pop     rsi
0x18005ae3b  pop     rbx
0x18005ae3c  pop     rbp
0x18005ae3d  retn
```
