# COMAPIHelper::ValidateSessionData(IUpdateCollection *,wchar_t const *)

- ea: `0x18008d4d4`
- end: `0x18008da0a`
- name: `?ValidateSessionData@COMAPIHelper@@YAJPEAUIUpdateCollection@@PEB_W@Z`
- size: `1334`
- prototype: `int(COMAPIHelper *__hidden this, struct IUpdateCollection *, const wchar_t *)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180063558`
- `0x180063a64`
- `0x18006aed4`
- `0x18006b3dc`
- `0x18006ba00`

## callees

- `0x180006ac4`
- `0x180060288`
- `0x18008d4d4`
- `0x18008db64`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008d653`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008d6d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008d653`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008d6d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d8dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d9c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d8dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d9c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d8ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d9b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d8ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d9b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d86b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d891`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d98f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d86b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d891`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d98f`

## string_xrefs

- `0x18008d51b`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d582`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d5ba`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d712`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d754`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d793`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d7d5`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d80d`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d8b7`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d8eb`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d93a`: `C:\__w\1\s\src\Client\commoncomapi\ComHelper.cpp`
- `0x18008d967`: `Operation SessionData %ws has a conflict with first update %ws (SessionData %ws).`
- `0x18008d843`: `Current update %ws (SessionData %ws) has a conflict with first update %ws (SessionData %ws).`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
__int64 __fastcall COMAPIHelper::ValidateSessionData(
        COMAPIHelper *this,
        struct IUpdateCollection *a2,
        const wchar_t *a3)
{
  __int64 v5; // rdx
  int v6; // ebx
  __int64 v8; // rax
  int v9; // eax
  wchar_t **v10; // r8
  unsigned int v11; // esi
  int UpdateSessionData; // eax
  struct IUpdateCollection *v13; // rbx
  unsigned int v14; // r15d
  __int64 v15; // rax
  int v16; // eax
  wchar_t **v17; // r8
  int v18; // eax
  WCHAR *v19; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  HANDLE v31; // rax
  __int64 v32; // rax
  int v33; // eax
  HANDLE v34; // rax
  int lpString2; // [rsp+20h] [rbp-59h]
  int lpString2a; // [rsp+20h] [rbp-59h]
  PCNZWCH v37; // [rsp+50h] [rbp-29h] BYREF
  PCNZWCH lpString1; // [rsp+58h] [rbp-21h] BYREF
  int v39; // [rsp+60h] [rbp-19h] BYREF
  BSTR v40; // [rsp+68h] [rbp-11h] BYREF
  BSTR v41; // [rsp+70h] [rbp-9h] BYREF
  COMAPIHelper *v42; // [rsp+78h] [rbp-1h] BYREF
  COMAPIHelper *v43; // [rsp+80h] [rbp+7h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+Fh] BYREF
  __int64 *v45; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( !this )
  {
    v5 = 58;
LABEL_3:
    v6 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
      (const char *)(unsigned int)v6,
      lpString2);
    return (unsigned int)v6;
  }
  v39 = 0;
  v6 = (*(__int64 (__fastcall **)(COMAPIHelper *, int *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, &v39, a3);
  if ( v6 < 0 )
  {
    v5 = 61;
    goto LABEL_4;
  }
  if ( v39 <= 0 )
  {
    v5 = 63;
    goto LABEL_3;
  }
  v8 = *(_QWORD *)this;
  v43 = 0;
  v9 = (*(__int64 (__fastcall **)(COMAPIHelper *, _QWORD, COMAPIHelper **))(v8 + 56))(this, 0, &v43);
  v11 = v9;
  if ( v9 >= 0 )
  {
    v37 = 0;
    UpdateSessionData = COMAPIHelper::GetUpdateSessionData(v43, (struct IUpdate *)&v37, v10);
    v11 = UpdateSessionData;
    v13 = (struct IUpdateCollection *)v37;
    if ( UpdateSessionData >= 0 )
    {
      v14 = 1;
      if ( v39 <= 1 )
      {
LABEL_25:
        if ( !a2 || !v13 || a2 == v13 || CompareStringW(0x7Fu, 0, (PCNZWCH)a2, -1, (PCNZWCH)v13, -1) == 2 )
        {
          v11 = 0;
        }
        else
        {
          v40 = 0;
          v21 = *(_QWORD *)v43;
          v40 = 0;
          v22 = (*(__int64 (__fastcall **)(COMAPIHelper *, BSTR *))(v21 + 152))(v43, &v40);
          v11 = v22;
          if ( v22 >= 0 )
          {
            v41 = 0;
            v32 = *(_QWORD *)v40;
            v41 = 0;
            v33 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(v32 + 64))(v40, &v41);
            v11 = v33;
            if ( v33 >= 0 )
            {
              v11 = -2145124244;
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x7A,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
                (const char *)0x8024006CLL,
                (int)"Operation SessionData %ws has a conflict with first update %ws (SessionData %ws).",
                (const char *)a2,
                v41,
                v13);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x74,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
                (const char *)(unsigned int)v33,
                lpString2a);
            }
            if ( v41 )
              SysFreeString(v41);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x71,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
              (const char *)(unsigned int)v22,
              lpString2a);
          }
          if ( v40 )
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)v40 + 16LL))(v40);
        }
      }
      else
      {
        while ( 1 )
        {
          v15 = *(_QWORD *)this;
          v42 = 0;
          v16 = (*(__int64 (__fastcall **)(COMAPIHelper *, _QWORD, COMAPIHelper **))(v15 + 56))(this, v14, &v42);
          v11 = v16;
          if ( v16 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4E,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
              (const char *)(unsigned int)v16,
              lpString2);
            goto LABEL_53;
          }
          lpString1 = 0;
          v18 = COMAPIHelper::GetUpdateSessionData(v42, (struct IUpdate *)&lpString1, v17);
          v11 = v18;
          v19 = (WCHAR *)lpString1;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x51,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
              (const char *)(unsigned int)v18,
              lpString2);
            goto LABEL_50;
          }
          if ( lpString1 != (PCNZWCH)v13
            && (!lpString1 || !v13 || CompareStringW(0x7Fu, 0, lpString1, -1, (PCNZWCH)v13, -1) != 2) )
          {
            break;
          }
          if ( v19 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v19);
          }
          if ( v42 )
            (*(void (__fastcall **)(COMAPIHelper *))(*(_QWORD *)v42 + 16LL))(v42);
          if ( (int)++v14 >= v39 )
            goto LABEL_25;
        }
        v41 = 0;
        v23 = *(_QWORD *)v43;
        v41 = 0;
        v24 = (*(__int64 (__fastcall **)(COMAPIHelper *, BSTR *))(v23 + 152))(v43, &v41);
        v11 = v24;
        if ( v24 >= 0 )
        {
          v40 = 0;
          v25 = *(_QWORD *)v41;
          v40 = 0;
          v26 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(v25 + 64))(v41, &v40);
          v11 = v26;
          if ( v26 >= 0 )
          {
            v45 = 0;
            v27 = *(_QWORD *)v42;
            v45 = 0;
            v28 = (*(__int64 (__fastcall **)(COMAPIHelper *, __int64 **))(v27 + 152))(v42, &v45);
            v11 = v28;
            if ( v28 >= 0 )
            {
              bstrString = 0;
              v29 = *v45;
              bstrString = 0;
              v30 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v29 + 64))(v45, &bstrString);
              v11 = v30;
              if ( v30 >= 0 )
              {
                v11 = -2145124244;
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x67,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
                  (const char *)0x8024006CLL,
                  (int)"Current update %ws (SessionData %ws) has a conflict with first update %ws (SessionData %ws).",
                  (const char *)bstrString,
                  v19,
                  v40,
                  v13);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5F,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
                  (const char *)(unsigned int)v30,
                  lpString2);
              }
              if ( bstrString )
                SysFreeString(bstrString);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5C,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
                (const char *)(unsigned int)v28,
                lpString2);
            }
            if ( v45 )
              (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x59,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
              (const char *)(unsigned int)v26,
              lpString2);
          }
          if ( v40 )
            SysFreeString(v40);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
            (const char *)(unsigned int)v24,
            lpString2);
        }
        if ( v41 )
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_50:
        if ( v19 )
        {
          v31 = GetProcessHeap();
          HeapFree(v31, 0, v19);
        }
LABEL_53:
        if ( v42 )
          (*(void (__fastcall **)(COMAPIHelper *))(*(_QWORD *)v42 + 16LL))(v42);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
        (const char *)(unsigned int)UpdateSessionData,
        lpString2);
    }
    if ( v13 )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\commoncomapi\\ComHelper.cpp",
      (const char *)(unsigned int)v9,
      lpString2);
  }
  if ( v43 )
    (*(void (__fastcall **)(COMAPIHelper *))(*(_QWORD *)v43 + 16LL))(v43);
  return v11;
}

```

## disassembly

```asm
0x18008d4d4  mov     [rsp-8+arg_10], rbx
0x18008d4d9  push    rbp
0x18008d4da  push    rsi
0x18008d4db  push    rdi
0x18008d4dc  push    r12
0x18008d4de  push    r13
0x18008d4e0  push    r14
0x18008d4e2  push    r15
0x18008d4e4  lea     rbp, [rsp-27h]
0x18008d4e9  sub     rsp, 0A0h
0x18008d4f0  mov     rax, cs:__security_cookie
0x18008d4f7  xor     rax, rsp
0x18008d4fa  mov     [rbp+57h+var_38], rax
0x18008d4fe  mov     r12, rdx
0x18008d501  mov     r14, rcx
0x18008d504  xor     r13d, r13d
0x18008d507  test    rcx, rcx
0x18008d50a  jnz     short loc_18008D52E
0x18008d50c  lea     edx, [rcx+3Ah]; void *
0x18008d50f  mov     ebx, 80070057h
0x18008d514  mov     rcx, [rbp+5Fh]; this
0x18008d518  mov     r9d, ebx; char *
0x18008d51b  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d522  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d527  mov     eax, ebx
0x18008d529  jmp     loc_18008D9E3
0x18008d52e  mov     [rbp+57h+var_70], r13d
0x18008d532  mov     rax, [rcx]
0x18008d535  lea     rdx, [rbp+57h+var_70]
0x18008d539  mov     rax, [rax+50h]
0x18008d53d  call    _guard_dispatch_icall
0x18008d542  mov     ebx, eax
0x18008d544  test    eax, eax
0x18008d546  jns     short loc_18008D54F
0x18008d548  mov     edx, 3Dh ; '='
0x18008d54d  jmp     short loc_18008D514
0x18008d54f  cmp     [rbp+57h+var_70], r13d
0x18008d553  jg      short loc_18008D55C
0x18008d555  mov     edx, 3Fh ; '?'
0x18008d55a  jmp     short loc_18008D50F
0x18008d55c  mov     rax, [r14]
0x18008d55f  mov     [rbp+57h+var_50], r13
0x18008d563  lea     r8, [rbp+57h+var_50]
0x18008d567  xor     edx, edx
0x18008d569  mov     rcx, r14
0x18008d56c  mov     rax, [rax+38h]
0x18008d570  call    _guard_dispatch_icall
0x18008d575  mov     esi, eax
0x18008d577  test    eax, eax
0x18008d579  jns     short loc_18008D598
0x18008d57b  mov     rcx, [rbp+5Fh]; this
0x18008d57f  mov     r9d, eax; char *
0x18008d582  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d589  mov     edx, 43h ; 'C'; void *
0x18008d58e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d593  jmp     loc_18008D9CB
0x18008d598  mov     [rbp+57h+var_80], r13
0x18008d59c  lea     rdx, [rbp+57h+var_80]; struct IUpdate *
0x18008d5a0  mov     rcx, [rbp+57h+var_50]; this
0x18008d5a4  call    ?GetUpdateSessionData@COMAPIHelper@@YAJAEAUIUpdate@@PEAPEA_W@Z; COMAPIHelper::GetUpdateSessionData(IUpdate &,wchar_t * *)
0x18008d5a9  mov     esi, eax
0x18008d5ab  mov     rbx, [rbp+57h+var_80]
0x18008d5af  test    eax, eax
0x18008d5b1  jns     short loc_18008D5D0
0x18008d5b3  mov     rcx, [rbp+5Fh]; this
0x18008d5b7  mov     r9d, eax; char *
0x18008d5ba  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d5c1  mov     edx, 46h ; 'F'; void *
0x18008d5c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d5cb  jmp     loc_18008D9B1
0x18008d5d0  mov     r15d, 1
0x18008d5d6  cmp     [rbp+57h+var_70], r15d
0x18008d5da  jle     loc_18008D69F
0x18008d5e0  mov     rax, [r14]
0x18008d5e3  mov     [rbp+57h+var_58], r13
0x18008d5e7  lea     r8, [rbp+57h+var_58]
0x18008d5eb  mov     edx, r15d
0x18008d5ee  mov     rcx, r14
0x18008d5f1  mov     rax, [rax+38h]
0x18008d5f5  call    _guard_dispatch_icall
0x18008d5fa  mov     esi, eax
0x18008d5fc  test    eax, eax
0x18008d5fe  js      loc_18008D8E4
0x18008d604  mov     [rbp+57h+lpString1], r13
0x18008d608  lea     rdx, [rbp+57h+lpString1]; struct IUpdate *
0x18008d60c  mov     rcx, [rbp+57h+var_58]; this
0x18008d610  call    ?GetUpdateSessionData@COMAPIHelper@@YAJAEAUIUpdate@@PEAPEA_W@Z; COMAPIHelper::GetUpdateSessionData(IUpdate &,wchar_t * *)
0x18008d615  mov     esi, eax
0x18008d617  mov     rdi, [rbp+57h+lpString1]
0x18008d61b  test    eax, eax
0x18008d61d  js      loc_18008D8B0
0x18008d623  cmp     rdi, rbx
0x18008d626  jz      short loc_18008D662
0x18008d628  test    rdi, rdi
0x18008d62b  jz      loc_18008D728
0x18008d631  test    rbx, rbx
0x18008d634  jz      loc_18008D728
0x18008d63a  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18008d642  mov     [rsp+0D0h+lpString2], rbx; lpString2
0x18008d647  or      r9d, 0FFFFFFFFh; cchCount1
0x18008d64b  mov     r8, rdi; lpString1
0x18008d64e  xor     edx, edx; dwCmpFlags
0x18008d650  lea     ecx, [rdx+7Fh]; Locale
0x18008d653  call    cs:__imp_CompareStringW
0x18008d659  cmp     eax, 2
0x18008d65c  jnz     loc_18008D728
0x18008d662  test    rdi, rdi
0x18008d665  jz      short loc_18008D67C
0x18008d667  call    cs:__imp_GetProcessHeap
0x18008d66d  mov     rcx, rax; hHeap
0x18008d670  mov     r8, rdi; lpMem
0x18008d673  xor     edx, edx; dwFlags
0x18008d675  call    cs:__imp_HeapFree
0x18008d67b  nop
0x18008d67c  mov     rcx, [rbp+57h+var_58]
0x18008d680  test    rcx, rcx
0x18008d683  jz      short loc_18008D692
0x18008d685  mov     rax, [rcx]
0x18008d688  mov     rax, [rax+10h]
0x18008d68c  call    _guard_dispatch_icall
0x18008d691  nop
0x18008d692  inc     r15d
0x18008d695  cmp     r15d, [rbp+57h+var_70]
0x18008d699  jl      loc_18008D5E0
0x18008d69f  test    r12, r12
0x18008d6a2  jz      loc_18008D9AE
0x18008d6a8  test    rbx, rbx
0x18008d6ab  jz      loc_18008D9AE
0x18008d6b1  cmp     r12, rbx
0x18008d6b4  jz      loc_18008D9AE
0x18008d6ba  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18008d6c2  mov     [rsp+0D0h+lpString2], rbx; int
0x18008d6c7  or      r9d, 0FFFFFFFFh; cchCount1
0x18008d6cb  mov     r8, r12; lpString1
0x18008d6ce  xor     edx, edx; dwCmpFlags
0x18008d6d0  lea     ecx, [rdx+7Fh]; Locale
0x18008d6d3  call    cs:__imp_CompareStringW
0x18008d6d9  cmp     eax, 2
0x18008d6dc  jz      loc_18008D9AE
0x18008d6e2  mov     [rbp+57h+var_68], r13
0x18008d6e6  mov     rcx, [rbp+57h+var_50]
0x18008d6ea  mov     rax, [rcx]
0x18008d6ed  mov     [rbp+57h+var_68], r13
0x18008d6f1  lea     rdx, [rbp+57h+var_68]
0x18008d6f5  mov     rax, [rax+98h]
0x18008d6fc  call    _guard_dispatch_icall
0x18008d701  mov     esi, eax
0x18008d703  test    eax, eax
0x18008d705  jns     loc_18008D918
0x18008d70b  mov     rcx, [rbp+5Fh]; this
0x18008d70f  mov     r9d, eax; char *
0x18008d712  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d719  mov     edx, 71h ; 'q'; void *
0x18008d71e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d723  jmp     loc_18008D996
0x18008d728  mov     [rbp+57h+var_60], r13
0x18008d72c  mov     rcx, [rbp+57h+var_50]
0x18008d730  mov     rax, [rcx]
0x18008d733  mov     [rbp+57h+var_60], r13
0x18008d737  lea     rdx, [rbp+57h+var_60]
0x18008d73b  mov     rax, [rax+98h]
0x18008d742  call    _guard_dispatch_icall
0x18008d747  mov     esi, eax
0x18008d749  test    eax, eax
0x18008d74b  jns     short loc_18008D76A
0x18008d74d  mov     rcx, [rbp+5Fh]; this
0x18008d751  mov     r9d, eax; char *
0x18008d754  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d75b  mov     edx, 56h ; 'V'; void *
0x18008d760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d765  jmp     loc_18008D898
0x18008d76a  mov     [rbp+57h+var_68], r13
0x18008d76e  mov     rcx, [rbp+57h+var_60]
0x18008d772  mov     rax, [rcx]
0x18008d775  mov     [rbp+57h+var_68], r13
0x18008d779  lea     rdx, [rbp+57h+var_68]
0x18008d77d  mov     rax, [rax+40h]
0x18008d781  call    _guard_dispatch_icall
0x18008d786  mov     esi, eax
0x18008d788  test    eax, eax
0x18008d78a  jns     short loc_18008D7A9
0x18008d78c  mov     rcx, [rbp+5Fh]; this
0x18008d790  mov     r9d, eax; char *
0x18008d793  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d79a  mov     edx, 59h ; 'Y'; void *
0x18008d79f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d7a4  jmp     loc_18008D888
0x18008d7a9  mov     [rbp+57h+var_40], r13
0x18008d7ad  mov     rcx, [rbp+57h+var_58]
0x18008d7b1  mov     rax, [rcx]
0x18008d7b4  mov     [rbp+57h+var_40], r13
0x18008d7b8  lea     rdx, [rbp+57h+var_40]
0x18008d7bc  mov     rax, [rax+98h]
0x18008d7c3  call    _guard_dispatch_icall
0x18008d7c8  mov     esi, eax
0x18008d7ca  test    eax, eax
0x18008d7cc  jns     short loc_18008D7EB
0x18008d7ce  mov     rcx, [rbp+5Fh]; this
0x18008d7d2  mov     r9d, eax; char *
0x18008d7d5  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d7dc  mov     edx, 5Ch ; '\'; void *
0x18008d7e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d7e6  jmp     loc_18008D872
0x18008d7eb  mov     [rbp+57h+bstrString], r13
0x18008d7ef  mov     rcx, [rbp+57h+var_40]
0x18008d7f3  mov     rax, [rcx]
0x18008d7f6  mov     [rbp+57h+bstrString], r13
0x18008d7fa  lea     rdx, [rbp+57h+bstrString]
0x18008d7fe  mov     rax, [rax+40h]
0x18008d802  call    _guard_dispatch_icall
0x18008d807  mov     esi, eax
0x18008d809  mov     rcx, [rbp+5Fh]; this
0x18008d80d  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d814  test    eax, eax
0x18008d816  jns     short loc_18008D827
0x18008d818  mov     r9d, eax; char *
0x18008d81b  mov     edx, 5Fh ; '_'; void *
0x18008d820  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d825  jmp     short loc_18008D862
0x18008d827  mov     [rsp+0D0h+var_90], rbx
0x18008d82c  mov     rax, [rbp+57h+var_68]
0x18008d830  mov     [rsp+0D0h+var_98], rax
0x18008d835  mov     [rsp+0D0h+var_A0], rdi
0x18008d83a  mov     rax, [rbp+57h+bstrString]
0x18008d83e  mov     qword ptr [rsp+0D0h+cchCount2], rax; char *
0x18008d843  lea     rax, aCurrentUpdateW; "Current update %ws (SessionData %ws) ha"...
0x18008d84a  mov     [rsp+0D0h+lpString2], rax; int
0x18008d84f  mov     esi, 8024006Ch
0x18008d854  mov     r9d, esi; char *
0x18008d857  mov     edx, 67h ; 'g'; void *
0x18008d85c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18008d861  nop
0x18008d862  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18008d866  test    rcx, rcx
0x18008d869  jz      short loc_18008D872
0x18008d86b  call    cs:__imp_SysFreeString
0x18008d871  nop
0x18008d872  mov     rcx, [rbp+57h+var_40]
0x18008d876  test    rcx, rcx
0x18008d879  jz      short loc_18008D888
0x18008d87b  mov     rax, [rcx]
0x18008d87e  mov     rax, [rax+10h]
0x18008d882  call    _guard_dispatch_icall
0x18008d887  nop
0x18008d888  mov     rcx, [rbp+57h+var_68]; bstrString
0x18008d88c  test    rcx, rcx
0x18008d88f  jz      short loc_18008D898
0x18008d891  call    cs:__imp_SysFreeString
0x18008d897  nop
0x18008d898  mov     rcx, [rbp+57h+var_60]
0x18008d89c  test    rcx, rcx
0x18008d89f  jz      short loc_18008D8AE
0x18008d8a1  mov     rax, [rcx]
0x18008d8a4  mov     rax, [rax+10h]
0x18008d8a8  call    _guard_dispatch_icall
0x18008d8ad  nop
0x18008d8ae  jmp     short loc_18008D8C9
0x18008d8b0  mov     rcx, [rbp+5Fh]; this
0x18008d8b4  mov     r9d, eax; char *
0x18008d8b7  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d8be  mov     edx, 51h ; 'Q'; void *
0x18008d8c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d8c8  nop
0x18008d8c9  test    rdi, rdi
0x18008d8cc  jz      short loc_18008D8FD
0x18008d8ce  call    cs:__imp_GetProcessHeap
0x18008d8d4  mov     rcx, rax; hHeap
0x18008d8d7  mov     r8, rdi; lpMem
0x18008d8da  xor     edx, edx; dwFlags
0x18008d8dc  call    cs:__imp_HeapFree
0x18008d8e2  jmp     short loc_18008D8FD
0x18008d8e4  mov     rcx, [rbp+5Fh]; this
0x18008d8e8  mov     r9d, eax; char *
0x18008d8eb  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d8f2  mov     edx, 4Eh ; 'N'; void *
0x18008d8f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d8fc  nop
0x18008d8fd  mov     rcx, [rbp+57h+var_58]
0x18008d901  test    rcx, rcx
0x18008d904  jz      short loc_18008D913
0x18008d906  mov     rax, [rcx]
0x18008d909  mov     rax, [rax+10h]
0x18008d90d  call    _guard_dispatch_icall
0x18008d912  nop
0x18008d913  jmp     loc_18008D9B1
0x18008d918  mov     [rbp+57h+var_60], r13
0x18008d91c  mov     rcx, [rbp+57h+var_68]
0x18008d920  mov     rax, [rcx]
0x18008d923  mov     [rbp+57h+var_60], r13
0x18008d927  lea     rdx, [rbp+57h+var_60]
0x18008d92b  mov     rax, [rax+40h]
0x18008d92f  call    _guard_dispatch_icall
0x18008d934  mov     esi, eax
0x18008d936  mov     rcx, [rbp+5Fh]; this
0x18008d93a  lea     r8, aCW1SSrcClientC_0; "C:\\__w\\1\\s\\src\\Client\\commoncomap"...
0x18008d941  test    eax, eax
0x18008d943  jns     short loc_18008D954
0x18008d945  mov     r9d, eax; char *
0x18008d948  mov     edx, 74h ; 't'; void *
0x18008d94d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
