# CUpdate::IsUpdateServiceRegistered(bool *)

- ea: `0x18005aa60`
- end: `0x18005ace5`
- name: `?IsUpdateServiceRegistered@CUpdate@@AEAAJPEA_N@Z`
- size: `645`
- prototype: `__int64 __fastcall(CUpdate *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005a160`

## callees

- `0x180006ac4`
- `0x18005aa60`
- `0x1800914bc`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005aad5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005aad5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ac01`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ac01`
- `OLEAUT32!__imp_SysFreeString` at `0x18005aba3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ac14`
- `OLEAUT32!__imp_SysFreeString` at `0x18005acbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18005aba3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ac14`
- `OLEAUT32!__imp_SysFreeString` at `0x18005acbf`

## string_xrefs

- `0x18005ab4e`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005acaa`: `C:\__w\1\s\src\Client\comapi\Update.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CUpdate::IsUpdateServiceRegistered(CUpdate *this, bool *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rdx
  LPVOID v6; // rbx
  __int64 (__fastcall *v7)(LPVOID, __int64 *); // rdi
  unsigned int v8; // esi
  int v9; // eax
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, BSTR *); // rdi
  OLECHAR *v12; // rax
  __int64 v14; // rdx
  int ppv; // [rsp+20h] [rbp-59h]
  _BYTE v16[80]; // [rsp+30h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+7h] BYREF
  int v18; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+90h] [rbp+17h] BYREF
  __int64 v20; // [rsp+98h] [rbp+1Fh] BYREF
  LPVOID v21; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v21 = 0;
  v19 = 0;
  v18 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 4758;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    goto LABEL_24;
  }
  *a2 = 0;
  v4 = CoCreateInstance(
         &GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21,
         0,
         0x17u,
         &GUID_23857e3c_02ba_44a3_9423_b1c900805f37,
         &v21);
  if ( v4 < 0 )
  {
    v5 = 4765;
    goto LABEL_11;
  }
  v6 = v21;
  v7 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v21 + 56LL);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  v4 = v7(v6, &v19);
  if ( v4 < 0 )
  {
    v5 = 4767;
    goto LABEL_11;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 72LL))(v19, &v18);
  if ( v4 < 0 )
  {
    v5 = 4768;
    goto LABEL_11;
  }
  v8 = 0;
  if ( v18 <= 0 )
  {
LABEL_23:
    v4 = 0;
  }
  else
  {
    while ( 1 )
    {
      v20 = 0;
      bstrString = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 56LL))(v19, v8, &v20);
      v4 = v9;
      if ( v9 < 0 )
        break;
      v10 = v20;
      v11 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v20 + 120LL);
      SysFreeString(bstrString);
      bstrString = 0;
      v9 = v11(v10, &bstrString);
      v4 = v9;
      if ( v9 < 0 )
      {
        v14 = 4776;
        goto LABEL_31;
      }
      v12 = (OLECHAR *)Trace::GuidToString::GuidToString(
                         (Trace::GuidToString *)v16,
                         (const struct _GUID *)((char *)this + 936));
      if ( bstrString == v12 || bstrString && v12 && CompareStringW(0x7Fu, 1u, bstrString, -1, v12, -1) == 2 )
        *a2 = 1;
      SysFreeString(bstrString);
      bstrString = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( (int)++v8 >= v18 )
        goto LABEL_23;
    }
    v14 = 4775;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    SysFreeString(bstrString);
    bstrString = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
LABEL_24:
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005aa60  mov     [rsp-8+arg_10], rbx
0x18005aa65  mov     [rsp-8+arg_18], rsi
0x18005aa6a  push    rbp
0x18005aa6b  push    rdi
0x18005aa6c  push    r12
0x18005aa6e  push    r14
0x18005aa70  push    r15
0x18005aa72  lea     rbp, [rsp-37h]
0x18005aa77  sub     rsp, 0B0h
0x18005aa7e  mov     rax, cs:__security_cookie
0x18005aa85  xor     rax, rsp
0x18005aa88  mov     [rbp+57h+var_28], rax
0x18005aa8c  mov     r14, rdx
0x18005aa8f  mov     r15, rcx
0x18005aa92  xor     r12d, r12d
0x18005aa95  mov     [rbp+57h+var_30], r12
0x18005aa99  mov     [rbp+57h+var_40], r12
0x18005aa9d  mov     [rbp+57h+var_48], r12d
0x18005aaa1  test    rdx, rdx
0x18005aaa4  jnz     short loc_18005AAB5
0x18005aaa6  mov     ebx, 80004003h
0x18005aaab  mov     edx, 1296h
0x18005aab0  jmp     loc_18005AB47
0x18005aab5  mov     [rdx], r12b
0x18005aab8  lea     rax, [rbp+57h+var_30]
0x18005aabc  mov     [rsp+0D0h+ppv], rax; int
0x18005aac1  lea     r9, _GUID_23857e3c_02ba_44a3_9423_b1c900805f37; riid
0x18005aac8  xor     edx, edx; pUnkOuter
0x18005aaca  lea     r8d, [rdx+17h]; dwClsContext
0x18005aace  lea     rcx, _GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21; rclsid
0x18005aad5  call    cs:__imp_CoCreateInstance
0x18005aadb  mov     ebx, eax
0x18005aadd  test    eax, eax
0x18005aadf  jns     short loc_18005AAE8
0x18005aae1  mov     edx, 129Dh
0x18005aae6  jmp     short loc_18005AB47
0x18005aae8  mov     rbx, [rbp+57h+var_30]
0x18005aaec  mov     rax, [rbx]
0x18005aaef  mov     rdi, [rax+38h]
0x18005aaf3  mov     rcx, [rbp+57h+var_40]
0x18005aaf7  test    rcx, rcx
0x18005aafa  jz      short loc_18005AB0C
0x18005aafc  mov     rax, [rcx]
0x18005aaff  mov     rax, [rax+10h]
0x18005ab03  call    _guard_dispatch_icall
0x18005ab08  mov     [rbp+57h+var_40], r12
0x18005ab0c  lea     rdx, [rbp+57h+var_40]
0x18005ab10  mov     rcx, rbx
0x18005ab13  mov     rax, rdi
0x18005ab16  call    _guard_dispatch_icall
0x18005ab1b  mov     ebx, eax
0x18005ab1d  test    eax, eax
0x18005ab1f  jns     short loc_18005AB28
0x18005ab21  mov     edx, 129Fh
0x18005ab26  jmp     short loc_18005AB47
0x18005ab28  mov     rcx, [rbp+57h+var_40]
0x18005ab2c  mov     rax, [rcx]
0x18005ab2f  lea     rdx, [rbp+57h+var_48]
0x18005ab33  mov     rax, [rax+48h]
0x18005ab37  call    _guard_dispatch_icall
0x18005ab3c  mov     ebx, eax
0x18005ab3e  test    eax, eax
0x18005ab40  jns     short loc_18005AB5F
0x18005ab42  mov     edx, 12A0h; void *
0x18005ab47  mov     rcx, [rbp+5Fh]; this
0x18005ab4b  mov     r9d, ebx; char *
0x18005ab4e  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005ab55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ab5a  jmp     loc_18005AC42
0x18005ab5f  mov     esi, r12d
0x18005ab62  cmp     [rbp+57h+var_48], r12d
0x18005ab66  jle     loc_18005AC3F
0x18005ab6c  mov     [rbp+57h+var_38], r12
0x18005ab70  mov     [rbp+57h+bstrString], r12
0x18005ab74  mov     rcx, [rbp+57h+var_40]
0x18005ab78  mov     rax, [rcx]
0x18005ab7b  lea     r8, [rbp+57h+var_38]
0x18005ab7f  mov     edx, esi
0x18005ab81  mov     rax, [rax+38h]
0x18005ab85  call    _guard_dispatch_icall
0x18005ab8a  mov     ebx, eax
0x18005ab8c  test    eax, eax
0x18005ab8e  js      loc_18005ACA2
0x18005ab94  mov     rbx, [rbp+57h+var_38]
0x18005ab98  mov     rax, [rbx]
0x18005ab9b  mov     rdi, [rax+78h]
0x18005ab9f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005aba3  call    cs:__imp_SysFreeString
0x18005aba9  mov     [rbp+57h+bstrString], r12
0x18005abad  lea     rdx, [rbp+57h+bstrString]
0x18005abb1  mov     rcx, rbx
0x18005abb4  mov     rax, rdi
0x18005abb7  call    _guard_dispatch_icall
0x18005abbc  mov     ebx, eax
0x18005abbe  test    eax, eax
0x18005abc0  js      loc_18005AC9B
0x18005abc6  lea     rdx, [r15+3A8h]; struct _GUID *
0x18005abcd  lea     rcx, [rbp+57h+var_A0]; this
0x18005abd1  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18005abd6  mov     r8, [rbp+57h+bstrString]; lpString1
0x18005abda  cmp     r8, rax
0x18005abdd  jz      short loc_18005AC0C
0x18005abdf  test    r8, r8
0x18005abe2  jz      short loc_18005AC10
0x18005abe4  test    rax, rax
0x18005abe7  jz      short loc_18005AC10
0x18005abe9  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005abf1  mov     [rsp+0D0h+ppv], rax; lpString2
0x18005abf6  or      r9d, 0FFFFFFFFh; cchCount1
0x18005abfa  lea     edx, [r9+2]; dwCmpFlags
0x18005abfe  lea     ecx, [rdx+7Eh]; Locale
0x18005ac01  call    cs:__imp_CompareStringW
0x18005ac07  cmp     eax, 2
0x18005ac0a  jnz     short loc_18005AC10
0x18005ac0c  mov     byte ptr [r14], 1
0x18005ac10  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005ac14  call    cs:__imp_SysFreeString
0x18005ac1a  mov     [rbp+57h+bstrString], r12
0x18005ac1e  mov     rcx, [rbp+57h+var_38]
0x18005ac22  test    rcx, rcx
0x18005ac25  jz      short loc_18005AC34
0x18005ac27  mov     rax, [rcx]
0x18005ac2a  mov     rax, [rax+10h]
0x18005ac2e  call    _guard_dispatch_icall
0x18005ac33  nop
0x18005ac34  inc     esi
0x18005ac36  cmp     esi, [rbp+57h+var_48]
0x18005ac39  jl      loc_18005AB6C
0x18005ac3f  mov     ebx, r12d
0x18005ac42  mov     rcx, [rbp+57h+var_40]
0x18005ac46  test    rcx, rcx
0x18005ac49  jz      short loc_18005AC5B
0x18005ac4b  mov     rax, [rcx]
0x18005ac4e  mov     rax, [rax+10h]
0x18005ac52  call    _guard_dispatch_icall
0x18005ac57  mov     [rbp+57h+var_40], r12
0x18005ac5b  mov     rcx, [rbp+57h+var_30]
0x18005ac5f  test    rcx, rcx
0x18005ac62  jz      short loc_18005AC71
0x18005ac64  mov     rdx, [rcx]
0x18005ac67  mov     rax, [rdx+10h]
0x18005ac6b  call    _guard_dispatch_icall
0x18005ac70  nop
0x18005ac71  mov     eax, ebx
0x18005ac73  mov     rcx, [rbp+57h+var_28]
0x18005ac77  xor     rcx, rsp; StackCookie
0x18005ac7a  call    __security_check_cookie
0x18005ac7f  lea     r11, [rsp+0D0h+var_20]
0x18005ac87  mov     rbx, [r11+40h]
0x18005ac8b  mov     rsi, [r11+48h]
0x18005ac8f  mov     rsp, r11
0x18005ac92  pop     r15
0x18005ac94  pop     r14
0x18005ac96  pop     r12
0x18005ac98  pop     rdi
0x18005ac99  pop     rbp
0x18005ac9a  retn
0x18005ac9b  mov     edx, 12A8h
0x18005aca0  jmp     short loc_18005ACA7
0x18005aca2  mov     edx, 12A7h; void *
0x18005aca7  mov     r9d, eax; char *
0x18005acaa  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005acb1  mov     rcx, [rbp+5Fh]; this
0x18005acb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005acba  nop
0x18005acbb  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005acbf  call    cs:__imp_SysFreeString
0x18005acc5  mov     [rbp+57h+bstrString], r12
0x18005acc9  mov     rcx, [rbp+57h+var_38]
0x18005accd  test    rcx, rcx
0x18005acd0  jz      short loc_18005ACDF
0x18005acd2  mov     rax, [rcx]
0x18005acd5  mov     rax, [rax+10h]
0x18005acd9  call    _guard_dispatch_icall
0x18005acde  nop
0x18005acdf  jmp     loc_18005AC42
```
