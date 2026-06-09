# CExpressionHandlerPlugin::Load(void)

- ea: `0x1801bb80c`
- end: `0x1801bbabf`
- name: `?Load@CExpressionHandlerPlugin@@QEAAJXZ`
- size: `691`
- prototype: `__int64 __fastcall(CExpressionHandlerPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801b9330`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x1801b89c0`
- `0x1801b8b34`
- `0x1801bb80c`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801bb9ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801bb9ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801bb9b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801bba92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801bb9b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801bba92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bb9bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bb9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bb9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bb9a9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bb8a6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bb8d7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bb904`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bb931`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bb8a6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bb8d7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bb904`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801bb931`

## string_xrefs

- `0x1801bb90f`: `wuuhosdeployment.dll`
- `0x1801bb86b`: `wuuhext.dll`
- `0x1801bb8e2`: `wuauengcore.dll`
- `0x1801bb8b5`: `wuuhdrv.dll`
- `0x1801bb9e6`: `WUCreateExpressionEvaluator`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CExpressionHandlerPlugin::Load(CExpressionHandlerPlugin *this)
{
  WCHAR *v3; // rbx
  char v4; // di
  wchar_t *UusHandlerSessionName; // rax
  int v6; // edi
  HMODULE v7; // r12
  HMODULE v8; // r15
  DWORD LastError; // ebx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  HMODULE v12; // rcx
  FARPROC ProcAddress; // rax
  const char *v14; // r9
  int v15; // eax
  int lpString2; // [rsp+20h] [rbp-50h]
  int lpString2a; // [rsp+20h] [rbp-50h]
  __int64 v18; // [rsp+48h] [rbp-28h] BYREF
  char v19; // [rsp+50h] [rbp-20h]
  HMODULE hModule; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( *((_QWORD *)this + 6) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\EEManager\\ExpressionManager.cpp",
      (const char *)0x8000000ELL,
      lpString2);
    return 2147483662LL;
  }
  v3 = (WCHAR *)*((_QWORD *)this + 2);
  v4 = 0;
  hModule = 0;
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
  v18 = 0;
  v19 = 1;
  UusHandlerSessionName = (wchar_t *)GetUusHandlerSessionName(v3);
  v6 = UndockedModuleLoader::Load_1(UusHandlerSessionName, v3, v4, (uus::Session **)this + 9, (HMODULE *)&v18);
  if ( v19 )
  {
    v7 = (HMODULE)v18;
    v8 = hModule;
    if ( hModule )
    {
      LastError = GetLastError();
      FreeLibrary(v8);
      SetLastError(LastError);
    }
    hModule = v7;
  }
  if ( v6 < 0 )
  {
    v10 = (unsigned int)v6;
    v11 = 1617;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\EEManager\\ExpressionManager.cpp",
      (const char *)v10,
      lpString2a);
    goto LABEL_30;
  }
  v12 = hModule;
  hModule = 0;
  *((_QWORD *)this + 6) = v12;
  ProcAddress = GetProcAddress(v12, "WUCreateExpressionEvaluator");
  if ( ProcAddress )
  {
    v15 = ((__int64 (__fastcall *)(_QWORD, GUID *, char *))ProcAddress)(
            *(unsigned int *)this,
            &GUID_7c09d778_e310_490c_a68c_5b3227f4a382,
            (char *)this + 56);
    v6 = v15;
    if ( v15 >= 0 )
    {
      v15 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 7))(
              *((_QWORD *)this + 7),
              &GUID_277ea5d1_60de_4944_81e0_b00ef33587fd,
              (char *)this + 64);
      v6 = v15;
      if ( v15 >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8));
        v6 = v15;
        if ( v15 >= 0 )
        {
          v6 = 0;
          goto LABEL_30;
        }
        v11 = 1631;
      }
      else
      {
        v11 = 1629;
      }
    }
    else
    {
      v11 = 1627;
    }
    v10 = (unsigned int)v15;
    goto LABEL_28;
  }
  v6 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x659,
         (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\EEManager\\ExpressionManager.cpp",
         v14);
LABEL_30:
  if ( hModule )
    FreeLibrary(hModule);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801bb80c  mov     [rsp-28h+arg_8], rbx
0x1801bb811  mov     [rsp-28h+arg_10], rsi
0x1801bb816  push    rbp
0x1801bb817  push    rdi
0x1801bb818  push    r12
0x1801bb81a  push    r14
0x1801bb81c  push    r15
0x1801bb81e  mov     rbp, rsp
0x1801bb821  sub     rsp, 70h
0x1801bb825  mov     rax, cs:__security_cookie
0x1801bb82c  xor     rax, rsp
0x1801bb82f  mov     [rbp+var_10], rax
0x1801bb833  mov     rsi, rcx
0x1801bb836  cmp     qword ptr [rcx+30h], 0
0x1801bb83b  jz      short loc_1801BB861
0x1801bb83d  mov     rcx, [rbp+28h]; this
0x1801bb841  mov     ebx, 8000000Eh
0x1801bb846  mov     r9d, ebx; char *
0x1801bb849  lea     r8, aCW1SSrcClientE_60; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1801bb850  mov     edx, 63Bh; void *
0x1801bb855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bb85a  mov     eax, ebx
0x1801bb85c  jmp     loc_1801BBA9A
0x1801bb861  mov     rbx, [rcx+10h]
0x1801bb865  xor     edi, edi
0x1801bb867  mov     [rbp+hModule], rdi
0x1801bb86b  lea     rax, ?c_szWuuhextDll@@3QB_WB; "wuuhext.dll"
0x1801bb872  lea     r14d, [rdi+1]
0x1801bb876  cmp     rbx, rax
0x1801bb879  jz      loc_1801BB93C
0x1801bb87f  test    rbx, rbx
0x1801bb882  jz      loc_1801BB93F
0x1801bb888  or      r15d, 0FFFFFFFFh
0x1801bb88c  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x1801bb891  mov     [rsp+70h+lpString2], rax; lpString2
0x1801bb896  mov     r9d, r15d; cchCount1
0x1801bb899  mov     r8, rbx; lpString1
0x1801bb89c  mov     edx, r14d; dwCmpFlags
0x1801bb89f  lea     r12d, [rdi+7Fh]
0x1801bb8a3  mov     ecx, r12d; Locale
0x1801bb8a6  call    cs:__imp_CompareStringW
0x1801bb8ac  cmp     eax, 2
0x1801bb8af  jz      loc_1801BB93C
0x1801bb8b5  lea     rax, ?c_szWuuhdrvDll@@3QB_WB; "wuuhdrv.dll"
0x1801bb8bc  cmp     rbx, rax
0x1801bb8bf  jz      short loc_1801BB93C
0x1801bb8c1  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x1801bb8c6  mov     [rsp+70h+lpString2], rax; lpString2
0x1801bb8cb  mov     r9d, r15d; cchCount1
0x1801bb8ce  mov     r8, rbx; lpString1
0x1801bb8d1  mov     edx, r14d; dwCmpFlags
0x1801bb8d4  mov     ecx, r12d; Locale
0x1801bb8d7  call    cs:__imp_CompareStringW
0x1801bb8dd  cmp     eax, 2
0x1801bb8e0  jz      short loc_1801BB93C
0x1801bb8e2  lea     rax, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x1801bb8e9  cmp     rbx, rax
0x1801bb8ec  jz      short loc_1801BB93C
0x1801bb8ee  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x1801bb8f3  mov     [rsp+70h+lpString2], rax; lpString2
0x1801bb8f8  mov     r9d, r15d; cchCount1
0x1801bb8fb  mov     r8, rbx; lpString1
0x1801bb8fe  mov     edx, r14d; dwCmpFlags
0x1801bb901  mov     ecx, r12d; Locale
0x1801bb904  call    cs:__imp_CompareStringW
0x1801bb90a  cmp     eax, 2
0x1801bb90d  jz      short loc_1801BB93C
0x1801bb90f  lea     rax, ?c_szWuuhosdeploymentDll@@3QB_WB; "wuuhosdeployment.dll"
0x1801bb916  cmp     rbx, rax
0x1801bb919  jz      short loc_1801BB93C
0x1801bb91b  mov     [rsp+70h+cchCount2], r15d; cchCount2
0x1801bb920  mov     [rsp+70h+lpString2], rax; lpString2
0x1801bb925  mov     r9d, r15d; cchCount1
0x1801bb928  mov     r8, rbx; lpString1
0x1801bb92b  mov     edx, r14d; dwCmpFlags
0x1801bb92e  mov     ecx, r12d; Locale
0x1801bb931  call    cs:__imp_CompareStringW
0x1801bb937  cmp     eax, 2
0x1801bb93a  jnz     short loc_1801BB93F
0x1801bb93c  mov     edi, r14d
0x1801bb93f  lea     rax, [rbp+hModule]
0x1801bb943  mov     [rbp+var_30], rax
0x1801bb947  mov     [rbp+var_28], 0
0x1801bb94f  mov     [rbp+var_20], r14b
0x1801bb953  mov     rcx, rbx; lpString1
0x1801bb956  call    ?GetUusHandlerSessionName@@YAPEB_WPEB_W@Z; GetUusHandlerSessionName(wchar_t const *)
0x1801bb95b  lea     r9, [rsi+48h]
0x1801bb95f  mov     [rsp+70h+var_38], 0
0x1801bb968  mov     [rsp+70h+var_40], 0
0x1801bb971  mov     qword ptr [rsp+70h+cchCount2], 0
0x1801bb97a  lea     rcx, [rbp+var_28]
0x1801bb97e  mov     [rsp+70h+lpString2], rcx; int
0x1801bb983  mov     r8d, edi
0x1801bb986  mov     rdx, rbx; wchar_t *
0x1801bb989  mov     rcx, rax; wchar_t *
0x1801bb98c  call    UndockedModuleLoader__Load_1
0x1801bb991  mov     edi, eax
0x1801bb993  cmp     [rbp+var_20], 0
0x1801bb997  jz      short loc_1801BB9C5
0x1801bb999  mov     r12, [rbp+var_28]
0x1801bb99d  mov     r14, [rbp+var_30]
0x1801bb9a1  mov     r15, [r14]
0x1801bb9a4  test    r15, r15
0x1801bb9a7  jz      short loc_1801BB9C2
0x1801bb9a9  call    cs:__imp_GetLastError
0x1801bb9af  mov     ebx, eax
0x1801bb9b1  mov     rcx, r15; hLibModule
0x1801bb9b4  call    cs:__imp_FreeLibrary
0x1801bb9ba  mov     ecx, ebx; dwErrCode
0x1801bb9bc  call    cs:__imp_SetLastError
0x1801bb9c2  mov     [r14], r12
0x1801bb9c5  test    edi, edi
0x1801bb9c7  jns     short loc_1801BB9D6
0x1801bb9c9  mov     r9d, edi
0x1801bb9cc  mov     edx, 651h
0x1801bb9d1  jmp     loc_1801BBA75
0x1801bb9d6  mov     rcx, [rbp+hModule]; hModule
0x1801bb9da  mov     [rbp+hModule], 0
0x1801bb9e2  mov     [rsi+30h], rcx
0x1801bb9e6  lea     rdx, aWucreateexpres_0; "WUCreateExpressionEvaluator"
0x1801bb9ed  call    cs:__imp_GetProcAddress
0x1801bb9f3  test    rax, rax
0x1801bb9f6  jnz     short loc_1801BBA11
0x1801bb9f8  mov     rcx, [rbp+28h]; this
0x1801bb9fc  lea     r8, aCW1SSrcClientE_60; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1801bba03  mov     edx, 659h; void *
0x1801bba08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801bba0d  mov     edi, eax
0x1801bba0f  jmp     short loc_1801BBA89
0x1801bba11  lea     r8, [rsi+38h]
0x1801bba15  lea     rdx, _GUID_7c09d778_e310_490c_a68c_5b3227f4a382
0x1801bba1c  mov     ecx, [rsi]
0x1801bba1e  call    _guard_dispatch_icall
0x1801bba23  mov     edi, eax
0x1801bba25  test    eax, eax
0x1801bba27  jns     short loc_1801BBA30
0x1801bba29  mov     edx, 65Bh
0x1801bba2e  jmp     short loc_1801BBA72
0x1801bba30  mov     rcx, [rsi+38h]
0x1801bba34  mov     rax, [rcx]
0x1801bba37  lea     r8, [rsi+40h]
0x1801bba3b  lea     rdx, _GUID_277ea5d1_60de_4944_81e0_b00ef33587fd
0x1801bba42  mov     rax, [rax]
0x1801bba45  call    _guard_dispatch_icall
0x1801bba4a  mov     edi, eax
0x1801bba4c  test    eax, eax
0x1801bba4e  jns     short loc_1801BBA57
0x1801bba50  mov     edx, 65Dh
0x1801bba55  jmp     short loc_1801BBA72
0x1801bba57  mov     rcx, [rsi+40h]
0x1801bba5b  mov     rax, [rcx]
0x1801bba5e  mov     rax, [rax+18h]
0x1801bba62  call    _guard_dispatch_icall
0x1801bba67  mov     edi, eax
0x1801bba69  test    eax, eax
0x1801bba6b  jns     short loc_1801BBA87
0x1801bba6d  mov     edx, 65Fh; void *
0x1801bba72  mov     r9d, eax; char *
0x1801bba75  lea     r8, aCW1SSrcClientE_60; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1801bba7c  mov     rcx, [rbp+28h]; this
0x1801bba80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bba85  jmp     short loc_1801BBA89
0x1801bba87  xor     edi, edi
0x1801bba89  mov     rcx, [rbp+hModule]; hLibModule
0x1801bba8d  test    rcx, rcx
0x1801bba90  jz      short loc_1801BBA98
0x1801bba92  call    cs:__imp_FreeLibrary
0x1801bba98  mov     eax, edi
0x1801bba9a  mov     rcx, [rbp+var_10]
0x1801bba9e  xor     rcx, rsp; StackCookie
0x1801bbaa1  call    __security_check_cookie
0x1801bbaa6  lea     r11, [rsp+70h+var_s0]
0x1801bbaab  mov     rbx, [r11+38h]
0x1801bbaaf  mov     rsi, [r11+40h]
0x1801bbab3  mov     rsp, r11
0x1801bbab6  pop     r15
0x1801bbab8  pop     r14
0x1801bbaba  pop     r12
0x1801bbabc  pop     rdi
0x1801bbabd  pop     rbp
0x1801bbabe  retn
```
