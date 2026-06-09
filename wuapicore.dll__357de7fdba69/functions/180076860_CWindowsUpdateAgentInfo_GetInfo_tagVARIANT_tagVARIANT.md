# CWindowsUpdateAgentInfo::GetInfo(tagVARIANT,tagVARIANT *)

- ea: `0x180076860`
- end: `0x180076b30`
- name: `?GetInfo@CWindowsUpdateAgentInfo@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `720`
- prototype: `int(CWindowsUpdateAgentInfo *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180076860`
- `0x180088e40`
- `0x180088f1c`
- `0x180089054`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800768e3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007691c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180076955`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800769fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180076a47`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180076a9e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800768e3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007691c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180076955`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800769fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180076a47`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180076a9e`
- `OLEAUT32!__imp_VariantInit` at `0x18007689e`
- `OLEAUT32!__imp_VariantInit` at `0x18007689e`

## string_xrefs

- `0x1800769c8`: `C:\__w\1\s\src\Client\comapi\WindowsUpdateAgentInfo.cpp`
- `0x180076afe`: `C:\__w\1\s\src\Client\comapi\WindowsUpdateAgentInfo.cpp`
- `0x180076a81`: `AgentVersionString`
- `0x180076a2a`: `AgentMinorVersion`
- `0x1800769de`: `AgentMajorVersion`

## pseudocode

```c
__int64 __fastcall CWindowsUpdateAgentInfo::GetInfo(
        CWindowsUpdateAgentInfo *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  const WCHAR *bstrVal; // rdi
  int EngineVersion; // edi
  __int64 v9; // rdx
  LONG v11; // eax
  int lpString2; // [rsp+20h] [rbp-30h]
  unsigned int v13; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v14[2]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( a3 )
  {
    VariantInit(a3);
    if ( a2->vt != 8 )
    {
      v6 = 66;
LABEL_30:
      v5 = -2147024809;
      goto LABEL_31;
    }
    bstrVal = a2->bstrVal;
    if ( CompareStringW(0x7Fu, 1u, bstrVal, -1, L"ApiMajorVersion", -1) == 2 )
    {
      a3->vt = 3;
      a3->lVal = 8;
      return 0;
    }
    if ( CompareStringW(0x7Fu, 1u, bstrVal, -1, L"ApiMinorVersion", -1) == 2 )
    {
      a3->vt = 3;
      a3->lVal = 0;
      return 0;
    }
    if ( CompareStringW(0x7Fu, 1u, bstrVal, -1, L"ProductVersionString", -1) == 2 )
    {
      v13 = 0;
      v14[0] = 0;
      GetRawFileVersionFromModule(&_ImageBase, 0, &v13, v14);
      EngineVersion = ConvertFileVerToBstr(
                        LOWORD(v14[0]) | v14[0] & 0xFFFF0000 | ((unsigned __int64)(unsigned __int16)v13 << 32),
                        &a3->bstrVal);
      if ( EngineVersion < 0 )
      {
        v9 = 86;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\WindowsUpdateAgentInfo.cpp",
          (const char *)(unsigned int)EngineVersion,
          lpString2);
        return (unsigned int)EngineVersion;
      }
LABEL_27:
      a3->vt = 8;
      return 0;
    }
    if ( CompareStringW(0x7Fu, 1u, bstrVal, -1, L"AgentMajorVersion", -1) == 2 )
    {
      *(_QWORD *)v14 = 0;
      EngineVersion = GetEngineVersion((unsigned __int64 *)v14);
      if ( EngineVersion < 0 )
      {
        v9 = 92;
        goto LABEL_12;
      }
      v11 = HIWORD(v14[1]);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, bstrVal, -1, L"AgentMinorVersion", -1) != 2 )
      {
        if ( CompareStringW(0x7Fu, 1u, bstrVal, -1, L"AgentVersionString", -1) != 2 )
        {
          v6 = 113;
          goto LABEL_30;
        }
        *(_QWORD *)v14 = 0;
        EngineVersion = GetEngineVersion((unsigned __int64 *)v14);
        if ( EngineVersion < 0 )
        {
          v9 = 106;
          goto LABEL_12;
        }
        EngineVersion = ConvertFileVerToBstr(*(unsigned __int64 *)v14, &a3->bstrVal);
        if ( EngineVersion < 0 )
        {
          v9 = 107;
          goto LABEL_12;
        }
        goto LABEL_27;
      }
      *(_QWORD *)v14 = 0;
      EngineVersion = GetEngineVersion((unsigned __int64 *)v14);
      if ( EngineVersion < 0 )
      {
        v9 = 99;
        goto LABEL_12;
      }
      v11 = LOWORD(v14[1]);
    }
    a3->vt = 3;
    a3->lVal = v11;
    return 0;
  }
  v5 = -2147467261;
  v6 = 61;
LABEL_31:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\WindowsUpdateAgentInfo.cpp",
    (const char *)v5,
    lpString2);
  return v5;
}

```

## disassembly

```asm
0x180076860  mov     [rsp-28h+arg_0], rbx
0x180076865  push    rbp
0x180076866  push    rdi
0x180076867  push    r12
0x180076869  push    r14
0x18007686b  push    r15
0x18007686d  mov     rbp, rsp
0x180076870  sub     rsp, 50h
0x180076874  mov     rax, cs:__security_cookie
0x18007687b  xor     rax, rsp
0x18007687e  mov     [rbp+var_10], rax
0x180076882  mov     rbx, r8
0x180076885  mov     rdi, rdx
0x180076888  test    r8, r8
0x18007688b  jnz     short loc_18007689B
0x18007688d  mov     ebx, 80004003h
0x180076892  lea     edx, [r8+3Dh]
0x180076896  jmp     loc_180076AFA
0x18007689b  mov     rcx, rbx; pvarg
0x18007689e  call    cs:__imp_VariantInit
0x1800768a4  mov     eax, 8
0x1800768a9  cmp     [rdi], ax
0x1800768ac  jz      short loc_1800768B6
0x1800768ae  lea     edx, [rax+3Ah]
0x1800768b1  jmp     loc_180076AF5
0x1800768b6  mov     rdi, [rdi+8]
0x1800768ba  lea     rax, aApimajorversio; "ApiMajorVersion"
0x1800768c1  or      r14d, 0FFFFFFFFh
0x1800768c5  mov     r8, rdi; lpString1
0x1800768c8  mov     [rsp+50h+cchCount2], r14d; cchCount2
0x1800768cd  mov     r9d, r14d; cchCount1
0x1800768d0  mov     [rsp+50h+lpString2], rax; lpString2
0x1800768d5  lea     r15d, [r14+2]
0x1800768d9  lea     r12d, [r15+7Eh]
0x1800768dd  mov     edx, r15d; dwCmpFlags
0x1800768e0  mov     ecx, r12d; Locale
0x1800768e3  call    cs:__imp_CompareStringW
0x1800768e9  cmp     eax, 2
0x1800768ec  jnz     short loc_1800768FF
0x1800768ee  mov     word ptr [rbx], 3
0x1800768f3  mov     dword ptr [rbx+8], 8
0x1800768fa  jmp     loc_180076AEC
0x1800768ff  lea     rax, aApiminorversio; "ApiMinorVersion"
0x180076906  mov     [rsp+50h+cchCount2], r14d; cchCount2
0x18007690b  mov     r9d, r14d; cchCount1
0x18007690e  mov     [rsp+50h+lpString2], rax; lpString2
0x180076913  mov     r8, rdi; lpString1
0x180076916  mov     edx, r15d; dwCmpFlags
0x180076919  mov     ecx, r12d; Locale
0x18007691c  call    cs:__imp_CompareStringW
0x180076922  cmp     eax, 2
0x180076925  jnz     short loc_180076938
0x180076927  mov     word ptr [rbx], 3
0x18007692c  mov     dword ptr [rbx+8], 0
0x180076933  jmp     loc_180076AEC
0x180076938  lea     rax, aProductversion; "ProductVersionString"
0x18007693f  mov     [rsp+50h+cchCount2], r14d; cchCount2
0x180076944  mov     r9d, r14d; cchCount1
0x180076947  mov     [rsp+50h+lpString2], rax; int
0x18007694c  mov     r8, rdi; lpString1
0x18007694f  mov     edx, r15d; dwCmpFlags
0x180076952  mov     ecx, r12d; Locale
0x180076955  call    cs:__imp_CompareStringW
0x18007695b  cmp     eax, 2
0x18007695e  jnz     short loc_1800769DE
0x180076960  lea     r9, [rbp+var_18]; unsigned int *
0x180076964  mov     [rbp+var_20], 0
0x18007696b  lea     r8, [rbp+var_20]; unsigned int *
0x18007696f  mov     [rbp+var_18], 0
0x180076976  xor     edx, edx; unsigned __int64
0x180076978  lea     rcx, __ImageBase; hModule
0x18007697f  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x180076984  movzx   eax, word ptr [rbp+var_20]
0x180076988  lea     rdx, [rbx+8]; wchar_t **
0x18007698c  mov     ecx, [rbp+var_20]
0x18007698f  mov     r8, 0FFFFFFFFFFFF0000h
0x180076996  and     rcx, r8
0x180076999  or      rcx, rax
0x18007699c  mov     eax, [rbp+var_18]
0x18007699f  and     rax, r8
0x1800769a2  shl     rcx, 20h
0x1800769a6  or      rcx, rax
0x1800769a9  movzx   eax, word ptr [rbp+var_18]
0x1800769ad  or      rcx, rax; unsigned __int64
0x1800769b0  call    ?ConvertFileVerToBstr@@YAJ_KPEAPEA_W@Z; ConvertFileVerToBstr(unsigned __int64,wchar_t * *)
0x1800769b5  mov     edi, eax
0x1800769b7  test    eax, eax
0x1800769b9  jns     loc_180076AE7
0x1800769bf  mov     edx, 56h ; 'V'; void *
0x1800769c4  mov     rcx, [rbp+28h]; this
0x1800769c8  lea     r8, aCW1SSrcClientC_11; "C:\\__w\\1\\s\\src\\Client\\comapi\\Win"...
0x1800769cf  mov     r9d, edi; char *
0x1800769d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800769d7  mov     eax, edi
0x1800769d9  jmp     loc_180076B0F
0x1800769de  lea     rax, aAgentmajorvers; "AgentMajorVersion"
0x1800769e5  mov     [rsp+50h+cchCount2], r14d; cchCount2
0x1800769ea  mov     r9d, r14d; cchCount1
0x1800769ed  mov     [rsp+50h+lpString2], rax; lpString2
0x1800769f2  mov     r8, rdi; lpString1
0x1800769f5  mov     edx, r15d; dwCmpFlags
0x1800769f8  mov     ecx, r12d; Locale
0x1800769fb  call    cs:__imp_CompareStringW
0x180076a01  cmp     eax, 2
0x180076a04  jnz     short loc_180076A2A
0x180076a06  lea     rcx, [rbp+var_18]; unsigned __int64 *
0x180076a0a  mov     qword ptr [rbp+var_18], 0
0x180076a12  call    ?GetEngineVersion@@YAJPEA_K@Z; GetEngineVersion(unsigned __int64 *)
0x180076a17  mov     edi, eax
0x180076a19  test    eax, eax
0x180076a1b  jns     short loc_180076A24
0x180076a1d  mov     edx, 5Ch ; '\'
0x180076a22  jmp     short loc_1800769C4
0x180076a24  movzx   eax, word ptr [rbp+var_18+6]
0x180076a28  jmp     short loc_180076A77
0x180076a2a  lea     rax, aAgentminorvers; "AgentMinorVersion"
0x180076a31  mov     [rsp+50h+cchCount2], r14d; cchCount2
0x180076a36  mov     r9d, r14d; cchCount1
0x180076a39  mov     [rsp+50h+lpString2], rax; lpString2
0x180076a3e  mov     r8, rdi; lpString1
0x180076a41  mov     edx, r15d; dwCmpFlags
0x180076a44  mov     ecx, r12d; Locale
0x180076a47  call    cs:__imp_CompareStringW
0x180076a4d  cmp     eax, 2
0x180076a50  jnz     short loc_180076A81
0x180076a52  lea     rcx, [rbp+var_18]; unsigned __int64 *
0x180076a56  mov     qword ptr [rbp+var_18], 0
0x180076a5e  call    ?GetEngineVersion@@YAJPEA_K@Z; GetEngineVersion(unsigned __int64 *)
0x180076a63  mov     edi, eax
0x180076a65  test    eax, eax
0x180076a67  jns     short loc_180076A73
0x180076a69  mov     edx, 63h ; 'c'
0x180076a6e  jmp     loc_1800769C4
0x180076a73  movzx   eax, word ptr [rbp+var_18+4]
0x180076a77  mov     word ptr [rbx], 3
0x180076a7c  mov     [rbx+8], eax
0x180076a7f  jmp     short loc_180076AEC
0x180076a81  lea     rax, aAgentversionst; "AgentVersionString"
0x180076a88  mov     [rsp+50h+cchCount2], r14d; cchCount2
0x180076a8d  mov     r9d, r14d; cchCount1
0x180076a90  mov     [rsp+50h+lpString2], rax; int
0x180076a95  mov     r8, rdi; lpString1
0x180076a98  mov     edx, r15d; dwCmpFlags
0x180076a9b  mov     ecx, r12d; Locale
0x180076a9e  call    cs:__imp_CompareStringW
0x180076aa4  cmp     eax, 2
0x180076aa7  jnz     short loc_180076AF0
0x180076aa9  lea     rcx, [rbp+var_18]; unsigned __int64 *
0x180076aad  mov     qword ptr [rbp+var_18], 0
0x180076ab5  call    ?GetEngineVersion@@YAJPEA_K@Z; GetEngineVersion(unsigned __int64 *)
0x180076aba  mov     edi, eax
0x180076abc  test    eax, eax
0x180076abe  jns     short loc_180076ACA
0x180076ac0  mov     edx, 6Ah ; 'j'
0x180076ac5  jmp     loc_1800769C4
0x180076aca  mov     rcx, qword ptr [rbp+var_18]; unsigned __int64
0x180076ace  lea     rdx, [rbx+8]; wchar_t **
0x180076ad2  call    ?ConvertFileVerToBstr@@YAJ_KPEAPEA_W@Z; ConvertFileVerToBstr(unsigned __int64,wchar_t * *)
0x180076ad7  mov     edi, eax
0x180076ad9  test    eax, eax
0x180076adb  jns     short loc_180076AE7
0x180076add  mov     edx, 6Bh ; 'k'
0x180076ae2  jmp     loc_1800769C4
0x180076ae7  mov     word ptr [rbx], 8
0x180076aec  xor     eax, eax
0x180076aee  jmp     short loc_180076B0F
0x180076af0  mov     edx, 71h ; 'q'; void *
0x180076af5  mov     ebx, 80070057h
0x180076afa  mov     rcx, [rbp+28h]; this
0x180076afe  lea     r8, aCW1SSrcClientC_11; "C:\\__w\\1\\s\\src\\Client\\comapi\\Win"...
0x180076b05  mov     r9d, ebx; char *
0x180076b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076b0d  mov     eax, ebx
0x180076b0f  mov     rcx, [rbp+var_10]
0x180076b13  xor     rcx, rsp; StackCookie
0x180076b16  call    __security_check_cookie
0x180076b1b  mov     rbx, [rsp+50h+arg_0]
0x180076b23  add     rsp, 50h
0x180076b27  pop     r15
0x180076b29  pop     r14
0x180076b2b  pop     r12
0x180076b2d  pop     rdi
0x180076b2e  pop     rbp
0x180076b2f  retn
```
