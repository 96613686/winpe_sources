# CUHPlugin::LoadDllIfNeeded(void)

- ea: `0x1801bcb14`
- end: `0x1801bcd14`
- name: `?LoadDllIfNeeded@CUHPlugin@@QEAAJXZ`
- size: `512`
- prototype: `__int64 __fastcall(CUHPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801bc334`

## callees

- `0x18000def4`
- `0x1801b89c0`
- `0x1801b8b34`
- `0x1801bcb14`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801bcc9f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801bcce7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801bcc9f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801bcce7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bcca7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bcca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bcc94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bcc94`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bcb91`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bcbc2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bcbef`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bcc1c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bcb91`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bcbc2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bcbef`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bcc1c`

## string_xrefs

- `0x1801bcbfa`: `wuuhosdeployment.dll`
- `0x1801bcb56`: `wuuhext.dll`
- `0x1801bcbcd`: `wuauengcore.dll`
- `0x1801bcba0`: `wuuhdrv.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUHPlugin::LoadDllIfNeeded(CUHPlugin *this)
{
  WCHAR *v3; // rbx
  char v4; // di
  wchar_t *UusHandlerSessionName; // rax
  int v6; // edi
  __int64 v7; // r12
  HMODULE v8; // r15
  DWORD LastError; // ebx
  HMODULE v10; // rcx
  HMODULE v11; // rax
  int lpString2; // [rsp+20h] [rbp-50h]
  __int64 v13; // [rsp+48h] [rbp-28h] BYREF
  char v14; // [rsp+50h] [rbp-20h]
  HMODULE v15; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( *((_QWORD *)this + 7) )
    return 0;
  v3 = (WCHAR *)*((_QWORD *)this + 5);
  v4 = 0;
  v15 = 0;
  if ( v3 == L"wuuhext.dll"
    || v3
    && (CompareStringW(0x7Fu, 1u, v3, -1, L"wuuhext.dll", -1) == 2
     || v3 == L"wuuhdrv.dll"
     || CompareStringW(0x7Fu, 1u, v3, -1, L"wuuhdrv.dll", -1) == 2
     || v3 == L"wuauengcore.dll"
     || CompareStringW(0x7Fu, 1u, v3, -1, L"wuauengcore.dll", -1) == 2
     || v3 == L"wuuhosdeployment.dll"
     || CompareStringW(0x7Fu, 1u, v3, -1, L"wuuhosdeployment.dll", -1) == 2) )
  {
    v4 = 1;
  }
  v13 = 0;
  v14 = 1;
  UusHandlerSessionName = (wchar_t *)GetUusHandlerSessionName(v3);
  v6 = UndockedModuleLoader::Load_1(UusHandlerSessionName, v3, v4, (uus::Session **)this + 8, (HMODULE *)&v13);
  if ( v14 )
  {
    v7 = v13;
    v8 = v15;
    if ( v15 )
    {
      LastError = GetLastError();
      FreeLibrary(v8);
      SetLastError(LastError);
    }
    v15 = (HMODULE)v7;
  }
  if ( v6 >= 0 )
  {
    v11 = v15;
    v10 = 0;
    v15 = 0;
    *((_QWORD *)this + 7) = v11;
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\UHManager\\uhmgr.cpp",
      (const char *)(unsigned int)v6,
      lpString2);
    v10 = v15;
  }
  if ( v10 )
    FreeLibrary(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801bcb14  mov     [rsp-28h+arg_8], rbx
0x1801bcb19  mov     [rsp-28h+arg_10], rsi
0x1801bcb1e  push    rbp
0x1801bcb1f  push    rdi
0x1801bcb20  push    r12
0x1801bcb22  push    r14
0x1801bcb24  push    r15
0x1801bcb26  mov     rbp, rsp
0x1801bcb29  sub     rsp, 70h
0x1801bcb2d  mov     rax, cs:__security_cookie
0x1801bcb34  xor     rax, rsp
0x1801bcb37  mov     [rbp+var_10], rax
0x1801bcb3b  mov     rsi, rcx
0x1801bcb3e  cmp     qword ptr [rcx+38h], 0
0x1801bcb43  jz      short loc_1801BCB4C
0x1801bcb45  xor     eax, eax
0x1801bcb47  jmp     loc_1801BCCEF
0x1801bcb4c  mov     rbx, [rcx+28h]
0x1801bcb50  xor     edi, edi
0x1801bcb52  mov     [rbp+var_18], rdi
0x1801bcb56  lea     rax, ?c_szWuuhextDll@@3QB_WB; "wuuhext.dll"
0x1801bcb5d  lea     r14d, [rdi+1]
0x1801bcb61  cmp     rbx, rax
0x1801bcb64  jz      loc_1801BCC27
0x1801bcb6a  test    rbx, rbx
0x1801bcb6d  jz      loc_1801BCC2A
0x1801bcb73  or      r15d, 0FFFFFFFFh
0x1801bcb77  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x1801bcb7c  mov     [rsp+70h+lpString2], rax; lpString2
0x1801bcb81  mov     r9d, r15d; cchCount1
0x1801bcb84  mov     r8, rbx; lpString1
0x1801bcb87  mov     edx, r14d; dwCmpFlags
0x1801bcb8a  lea     r12d, [rdi+7Fh]
0x1801bcb8e  mov     ecx, r12d; Locale
0x1801bcb91  call    cs:__imp_CompareStringW
0x1801bcb97  cmp     eax, 2
0x1801bcb9a  jz      loc_1801BCC27
0x1801bcba0  lea     rax, ?c_szWuuhdrvDll@@3QB_WB; "wuuhdrv.dll"
0x1801bcba7  cmp     rbx, rax
0x1801bcbaa  jz      short loc_1801BCC27
0x1801bcbac  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x1801bcbb1  mov     [rsp+70h+lpString2], rax; lpString2
0x1801bcbb6  mov     r9d, r15d; cchCount1
0x1801bcbb9  mov     r8, rbx; lpString1
0x1801bcbbc  mov     edx, r14d; dwCmpFlags
0x1801bcbbf  mov     ecx, r12d; Locale
0x1801bcbc2  call    cs:__imp_CompareStringW
0x1801bcbc8  cmp     eax, 2
0x1801bcbcb  jz      short loc_1801BCC27
0x1801bcbcd  lea     rax, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x1801bcbd4  cmp     rbx, rax
0x1801bcbd7  jz      short loc_1801BCC27
0x1801bcbd9  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x1801bcbde  mov     [rsp+70h+lpString2], rax; lpString2
0x1801bcbe3  mov     r9d, r15d; cchCount1
0x1801bcbe6  mov     r8, rbx; lpString1
0x1801bcbe9  mov     edx, r14d; dwCmpFlags
0x1801bcbec  mov     ecx, r12d; Locale
0x1801bcbef  call    cs:__imp_CompareStringW
0x1801bcbf5  cmp     eax, 2
0x1801bcbf8  jz      short loc_1801BCC27
0x1801bcbfa  lea     rax, ?c_szWuuhosdeploymentDll@@3QB_WB; "wuuhosdeployment.dll"
0x1801bcc01  cmp     rbx, rax
0x1801bcc04  jz      short loc_1801BCC27
0x1801bcc06  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x1801bcc0b  mov     [rsp+70h+lpString2], rax; lpString2
0x1801bcc10  mov     r9d, r15d; cchCount1
0x1801bcc13  mov     r8, rbx; lpString1
0x1801bcc16  mov     edx, r14d; dwCmpFlags
0x1801bcc19  mov     ecx, r12d; Locale
0x1801bcc1c  call    cs:__imp_CompareStringW
0x1801bcc22  cmp     eax, 2
0x1801bcc25  jnz     short loc_1801BCC2A
0x1801bcc27  mov     edi, r14d
0x1801bcc2a  lea     rax, [rbp+var_18]
0x1801bcc2e  mov     [rbp+var_30], rax
0x1801bcc32  mov     [rbp+var_28], 0
0x1801bcc3a  mov     [rbp+var_20], r14b
0x1801bcc3e  mov     rcx, rbx; lpString1
0x1801bcc41  call    ?GetUusHandlerSessionName@@YAPEB_WPEB_W@Z; GetUusHandlerSessionName(wchar_t const *)
0x1801bcc46  lea     r9, [rsi+40h]
0x1801bcc4a  mov     [rsp+70h+var_38], 0
0x1801bcc53  mov     [rsp+70h+var_40], 0
0x1801bcc5c  mov     qword ptr [rsp+70h+cchCount2], 0
0x1801bcc65  lea     rcx, [rbp+var_28]
0x1801bcc69  mov     [rsp+70h+lpString2], rcx; int
0x1801bcc6e  mov     r8d, edi
0x1801bcc71  mov     rdx, rbx; wchar_t *
0x1801bcc74  mov     rcx, rax; wchar_t *
0x1801bcc77  call    UndockedModuleLoader__Load_1
0x1801bcc7c  mov     edi, eax
0x1801bcc7e  cmp     [rbp+var_20], 0
0x1801bcc82  jz      short loc_1801BCCB0
0x1801bcc84  mov     r12, [rbp+var_28]
0x1801bcc88  mov     r14, [rbp+var_30]
0x1801bcc8c  mov     r15, [r14]
0x1801bcc8f  test    r15, r15
0x1801bcc92  jz      short loc_1801BCCAD
0x1801bcc94  call    cs:__imp_GetLastError
0x1801bcc9a  mov     ebx, eax
0x1801bcc9c  mov     rcx, r15; hLibModule
0x1801bcc9f  call    cs:__imp_FreeLibrary
0x1801bcca5  mov     ecx, ebx; dwErrCode
0x1801bcca7  call    cs:__imp_SetLastError
0x1801bccad  mov     [r14], r12
0x1801bccb0  test    edi, edi
0x1801bccb2  jns     short loc_1801BCCD2
0x1801bccb4  mov     rcx, [rbp+28h]; this
0x1801bccb8  mov     r9d, edi; char *
0x1801bccbb  lea     r8, aCW1SSrcClientE_15; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1801bccc2  mov     edx, 1F3h; void *
0x1801bccc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bcccc  mov     rcx, [rbp+var_18]
0x1801bccd0  jmp     short loc_1801BCCE2
0x1801bccd2  mov     rax, [rbp+var_18]
0x1801bccd6  xor     ecx, ecx; hLibModule
0x1801bccd8  mov     [rbp+var_18], rcx
0x1801bccdc  mov     [rsi+38h], rax
0x1801bcce0  xor     edi, edi
0x1801bcce2  test    rcx, rcx
0x1801bcce5  jz      short loc_1801BCCED
0x1801bcce7  call    cs:__imp_FreeLibrary
0x1801bcced  mov     eax, edi
0x1801bccef  mov     rcx, [rbp+var_10]
0x1801bccf3  xor     rcx, rsp; StackCookie
0x1801bccf6  call    __security_check_cookie
0x1801bccfb  lea     r11, [rsp+70h+var_s0]
0x1801bcd00  mov     rbx, [r11+38h]
0x1801bcd04  mov     rsi, [r11+40h]
0x1801bcd08  mov     rsp, r11
0x1801bcd0b  pop     r15
0x1801bcd0d  pop     r14
0x1801bcd0f  pop     r12
0x1801bcd11  pop     rdi
0x1801bcd12  pop     rbp
0x1801bcd13  retn
```
