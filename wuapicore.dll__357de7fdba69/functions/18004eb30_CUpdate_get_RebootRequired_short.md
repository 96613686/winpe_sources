# CUpdate::get_RebootRequired(short *)

- ea: `0x18004eb30`
- end: `0x18004ed50`
- name: `?get_RebootRequired@CUpdate@@UEAAJPEAF@Z`
- size: `544`
- prototype: `__int64 __fastcall(CUpdate *__hidden this, __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039470`

## callees

- `0x18000588c`
- `0x180006ac4`
- `0x18004e890`
- `0x18004eb30`
- `0x18005dad4`
- `0x180090bc8`
- `0x180091568`
- `0x180091dfc`
- `0x180092d74`
- `0x180093cf4`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004ec01`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ec7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ed08`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ec01`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ec7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ed08`

## string_xrefs

- `0x18004eb6a`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004ec6b`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004ec85`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004ecf2`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004eba4`: `IUpdate::get_RebootRequired called for update %ws`

## pseudocode

```c
__int64 __fastcall CUpdate::get_RebootRequired(CUpdate *this, __int16 *a2)
{
  unsigned int v2; // esi
  __int64 v5; // rdi
  __int16 *v6; // r14
  __int64 v7; // rax
  __int64 (__fastcall *v8)(__int64, BSTR *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  wchar_t **v12; // r9
  unsigned int v13; // ebx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  BSTR v16; // rbx
  __int64 RegKeyPath; // rax
  __int64 v18; // rcx
  int v19; // eax
  int IsCommitRequired; // eax
  __int64 v21; // rdx
  int v22; // ecx
  int v23; // ebx
  int v24; // [rsp+20h] [rbp-99h]
  int v25; // [rsp+20h] [rbp-99h]
  int v26; // [rsp+20h] [rbp-99h]
  _QWORD v27[2]; // [rsp+40h] [rbp-79h] BYREF
  __int64 v28; // [rsp+50h] [rbp-69h]
  char v29[112]; // [rsp+60h] [rbp-59h] BYREF
  __int16 *v30; // [rsp+D0h] [rbp+17h] BYREF
  int v31; // [rsp+D8h] [rbp+1Fh] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp+27h] BYREF
  int v33; // [rsp+E8h] [rbp+2Fh] BYREF
  int v34; // [rsp+ECh] [rbp+33h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = 0;
  v30 = a2;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x494,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)0x80004003LL,
      v24);
    return 2147500035LL;
  }
  *a2 = 0;
  Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v29, (CUpdate *)((char *)this + 672));
  WUTrace(0, 0, 0x10000, 4, 0, L"IUpdate::get_RebootRequired called for update %ws");
  v5 = *((_QWORD *)this + 58);
  v28 = 0;
  v6 = (__int16 *)((char *)this - 16);
  v33 = 0;
  v27[0] = 0;
  v34 = 0;
  v27[1] = &v30;
  v31 = 0;
  v7 = *(_QWORD *)(v5 + 8);
  v27[0] = v6;
  LOBYTE(v28) = 1;
  v8 = *(__int64 (__fastcall **)(__int64, BSTR *))(v7 + 64);
  SysFreeString(0);
  bstrString = 0;
  v9 = v8(v5 + 8, &bstrString);
  v13 = v9;
  if ( v9 < 0 )
  {
    v14 = (unsigned int)v9;
    v15 = 1213;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v14,
      v25);
    SysFreeString(bstrString);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v13,
      v26);
LABEL_18:
    v2 = v13;
    goto LABEL_19;
  }
  v16 = bstrString;
  RegKeyPath = GetRegKeyPath(6, v10, v11, v12);
  v19 = RegQueryDwordValue(v18, RegKeyPath, v16, &v31);
  v13 = v19;
  if ( v19 < 0 )
  {
    if ( (unsigned int)(v19 + 2147024894) > 1 )
    {
      v14 = (unsigned int)v19;
      v15 = 1230;
      goto LABEL_8;
    }
    IsCommitRequired = CUpdate::IsCommitRequired((CUpdate *)v6, &v33, &v34);
    if ( IsCommitRequired < 0 )
    {
      v21 = 1234;
LABEL_15:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)(unsigned int)IsCommitRequired,
        v25);
      goto LABEL_16;
    }
    if ( v33 || v34 )
    {
      v22 = v6[311];
      v31 = (v22 == -1) + 1;
      IsCommitRequired = CreateVolatileUpdateRebootRequiredValue(bstrString, v22 == -1);
      if ( IsCommitRequired < 0 )
      {
        v21 = 1244;
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  v23 = v31;
  SysFreeString(bstrString);
  if ( (unsigned int)(v23 - 1) <= 1 )
  {
    v13 = 0;
    *v30 = -1;
    goto LABEL_18;
  }
LABEL_19:
  wil::details::lambda_call__lambda_f61594dc1a2648e2d24967233f2db30f___::_lambda_call__lambda_f61594dc1a2648e2d24967233f2db30f___(v27);
  return v2;
}

```

## disassembly

```asm
0x18004eb30  mov     [rsp-8+arg_10], rbx
0x18004eb35  mov     [rsp-8+arg_18], rsi
0x18004eb3a  push    rbp
0x18004eb3b  push    rdi
0x18004eb3c  push    r14
0x18004eb3e  lea     rbp, [rsp-47h]
0x18004eb43  sub     rsp, 100h
0x18004eb4a  mov     rax, cs:__security_cookie
0x18004eb51  xor     rax, rsp
0x18004eb54  mov     [rbp+57h+var_20], rax
0x18004eb58  xor     esi, esi
0x18004eb5a  mov     [rbp+57h+var_40], rdx
0x18004eb5e  mov     r14, rcx
0x18004eb61  test    rdx, rdx
0x18004eb64  jnz     short loc_18004EB8A
0x18004eb66  mov     rcx, [rbp+5Fh]; this
0x18004eb6a  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004eb71  mov     ebx, 80004003h
0x18004eb76  mov     edx, 494h; void *
0x18004eb7b  mov     r9d, ebx; char *
0x18004eb7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb83  mov     eax, ebx
0x18004eb85  jmp     loc_18004ED2C
0x18004eb8a  mov     [rdx], si
0x18004eb8d  lea     rdx, [rcx+2A0h]; struct tagDSGlobalUpdateId *
0x18004eb94  lea     rcx, [rbp+57h+var_B0]; this
0x18004eb98  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18004eb9d  mov     [rsp+110h+var_E0], rax
0x18004eba2  xor     edx, edx
0x18004eba4  lea     rax, aIupdateGetRebo; "IUpdate::get_RebootRequired called for "...
0x18004ebab  xor     ecx, ecx
0x18004ebad  mov     [rsp+110h+var_E8], rax
0x18004ebb2  mov     r8d, 10000h
0x18004ebb8  mov     qword ptr [rsp+110h+var_F0], rsi; int
0x18004ebbd  lea     r9d, [rdx+4]
0x18004ebc1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004ebc6  mov     rdi, [r14+1D0h]
0x18004ebcd  xor     eax, eax
0x18004ebcf  mov     [rbp+57h+var_C0], rax
0x18004ebd3  add     r14, 0FFFFFFFFFFFFFFF0h
0x18004ebd7  xorps   xmm0, xmm0
0x18004ebda  mov     [rbp+57h+var_28], esi
0x18004ebdd  movups  [rbp+57h+var_D0], xmm0
0x18004ebe1  lea     rax, [rbp+57h+var_40]
0x18004ebe5  mov     [rbp+57h+var_24], esi
0x18004ebe8  mov     qword ptr [rbp+57h+var_D0+8], rax
0x18004ebec  xor     ecx, ecx; bstrString
0x18004ebee  mov     [rbp+57h+var_38], esi
0x18004ebf1  mov     rax, [rdi+8]
0x18004ebf5  mov     qword ptr [rbp+57h+var_D0], r14
0x18004ebf9  mov     byte ptr [rbp+57h+var_C0], 1
0x18004ebfd  mov     rbx, [rax+40h]
0x18004ec01  call    cs:__imp_SysFreeString
0x18004ec07  lea     rdx, [rbp+57h+bstrString]
0x18004ec0b  mov     [rbp+57h+bstrString], rsi
0x18004ec0f  lea     rcx, [rdi+8]
0x18004ec13  mov     rax, rbx
0x18004ec16  call    _guard_dispatch_icall
0x18004ec1b  mov     ebx, eax
0x18004ec1d  test    eax, eax
0x18004ec1f  jns     short loc_18004EC2B
0x18004ec21  mov     r9d, eax
0x18004ec24  mov     edx, 4BDh
0x18004ec29  jmp     short loc_18004EC67
0x18004ec2b  mov     rbx, [rbp+57h+bstrString]
0x18004ec2f  mov     ecx, 6
0x18004ec34  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x18004ec39  lea     r9, [rbp+57h+var_38]
0x18004ec3d  mov     r8, rbx
0x18004ec40  mov     rdx, rax
0x18004ec43  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)
0x18004ec48  or      edi, 0FFFFFFFFh
0x18004ec4b  mov     ebx, eax
0x18004ec4d  test    eax, eax
0x18004ec4f  jns     loc_18004ED01
0x18004ec55  add     eax, 7FF8FFFEh
0x18004ec5a  cmp     eax, 1
0x18004ec5d  jbe     short loc_18004EC9E
0x18004ec5f  mov     r9d, ebx; char *
0x18004ec62  mov     edx, 4CEh; void *
0x18004ec67  mov     rcx, [rbp+5Fh]; this
0x18004ec6b  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004ec72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec77  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18004ec7b  call    cs:__imp_SysFreeString
0x18004ec81  mov     rcx, [rbp+5Fh]; this
0x18004ec85  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004ec8c  mov     r9d, ebx; char *
0x18004ec8f  mov     edx, 4A5h; void *
0x18004ec94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec99  jmp     loc_18004ED1F
0x18004ec9e  lea     r8, [rbp+57h+var_24]; int *
0x18004eca2  mov     rcx, r14; this
0x18004eca5  lea     rdx, [rbp+57h+var_28]; int *
0x18004eca9  call    ?IsCommitRequired@CUpdate@@AEAAJPEAH0@Z; CUpdate::IsCommitRequired(int *,int *)
0x18004ecae  test    eax, eax
0x18004ecb0  jns     short loc_18004ECB9
0x18004ecb2  mov     edx, 4D2h
0x18004ecb7  jmp     short loc_18004ECEE
0x18004ecb9  cmp     [rbp+57h+var_28], esi
0x18004ecbc  jnz     short loc_18004ECC3
0x18004ecbe  cmp     [rbp+57h+var_24], esi
0x18004ecc1  jz      short loc_18004ED01
0x18004ecc3  movsx   ecx, word ptr [r14+26Eh]
0x18004eccb  mov     eax, esi
0x18004eccd  cmp     ecx, edi
0x18004eccf  setz    al
0x18004ecd2  inc     eax
0x18004ecd4  cmp     ecx, edi
0x18004ecd6  mov     [rbp+57h+var_38], eax
0x18004ecd9  mov     rcx, [rbp+57h+bstrString]; wchar_t *
0x18004ecdd  setz    dl; bool
0x18004ece0  call    ?CreateVolatileUpdateRebootRequiredValue@@YAJPEB_W_N@Z; CreateVolatileUpdateRebootRequiredValue(wchar_t const *,bool)
0x18004ece5  test    eax, eax
0x18004ece7  jns     short loc_18004ED01
0x18004ece9  mov     edx, 4DCh; void *
0x18004ecee  mov     rcx, [rbp+5Fh]; this
0x18004ecf2  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004ecf9  mov     r9d, eax; char *
0x18004ecfc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ed01  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18004ed05  mov     ebx, [rbp+57h+var_38]
0x18004ed08  call    cs:__imp_SysFreeString
0x18004ed0e  lea     eax, [rbx-1]
0x18004ed11  cmp     eax, 1
0x18004ed14  ja      short loc_18004ED21
0x18004ed16  mov     rax, [rbp+57h+var_40]
0x18004ed1a  mov     ebx, esi
0x18004ed1c  mov     [rax], di
0x18004ed1f  mov     esi, ebx
0x18004ed21  lea     rcx, [rbp+57h+var_D0]
0x18004ed25  call    wil__details__lambda_call__lambda_f61594dc1a2648e2d24967233f2db30f______lambda_call__lambda_f61594dc1a2648e2d24967233f2db30f___
0x18004ed2a  mov     eax, esi
0x18004ed2c  mov     rcx, [rbp+57h+var_20]
0x18004ed30  xor     rcx, rsp; StackCookie
0x18004ed33  call    __security_check_cookie
0x18004ed38  lea     r11, [rsp+110h+var_10]
0x18004ed40  mov     rbx, [r11+30h]
0x18004ed44  mov     rsi, [r11+38h]
0x18004ed48  mov     rsp, r11
0x18004ed4b  pop     r14
0x18004ed4d  pop     rdi
0x18004ed4e  pop     rbp
0x18004ed4f  retn
```
