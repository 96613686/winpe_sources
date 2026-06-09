# CNotification::SchdpSubstituteParameters(tagSAFEARRAY * *)

- ea: `0x180003a94`
- end: `0x180003e08`
- name: `?SchdpSubstituteParameters@CNotification@@AEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `884`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002b88`

## callees

- `0x1800028c4`
- `0x180003a94`
- `0x18000b13c`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings` at `0x180003c31`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180003c96`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180003c31`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180003c96`
- `ntdll!RtlDestroyEnvironment` at `0x180003d82`
- `ntdll!RtlDestroyEnvironment` at `0x180003d82`
- `ntdll!RtlNtStatusToDosError` at `0x180003ca8`
- `ntdll!RtlNtStatusToDosError` at `0x180003ca8`
- `KERNEL32!HeapFree` at `0x180003bcd`
- `KERNEL32!HeapFree` at `0x180003dd5`
- `KERNEL32!HeapFree` at `0x180003bcd`
- `KERNEL32!HeapFree` at `0x180003dd5`
- `KERNEL32!GetProcessHeap` at `0x180003bb9`
- `KERNEL32!GetProcessHeap` at `0x180003c4c`
- `KERNEL32!GetProcessHeap` at `0x180003dc1`
- `KERNEL32!GetProcessHeap` at `0x180003bb9`
- `KERNEL32!GetProcessHeap` at `0x180003c4c`
- `KERNEL32!GetProcessHeap` at `0x180003dc1`
- `KERNEL32!HeapAlloc` at `0x180003c60`
- `KERNEL32!HeapAlloc` at `0x180003c60`
- `OLEAUT32!__imp_SysAllocString` at `0x180003cca`
- `OLEAUT32!__imp_SysAllocString` at `0x180003cca`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ba6`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d97`
- `OLEAUT32!__imp_SysFreeString` at `0x180003db0`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ba6`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d97`
- `OLEAUT32!__imp_SysFreeString` at `0x180003db0`
- `OLEAUT32!__imp_SysStringLen` at `0x180003c02`
- `OLEAUT32!__imp_SysStringLen` at `0x180003c02`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180003de9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180003de9`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180003be8`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180003be8`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180003ce8`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180003ce8`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180003ad7`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180003ad7`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180003b39`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180003b39`

## pseudocode

```c
__int64 __fastcall CNotification::SchdpSubstituteParameters(CNotification *this, struct tagSAFEARRAY **a2)
{
  unsigned int v2; // ebx
  OLECHAR *v4; // rsi
  SAFEARRAY *Vector; // r14
  void *v6; // r15
  SAFEARRAY *v7; // rcx
  HRESULT v8; // eax
  int v9; // eax
  int v10; // r9d
  int v11; // r8d
  int v12; // r12d
  HANDLE ProcessHeap; // rax
  HRESULT Element; // eax
  NTSTATUS v15; // eax
  SIZE_T v16; // rbx
  HANDLE v17; // rax
  signed int v18; // eax
  BSTR v19; // rax
  HRESULT v20; // eax
  HANDLE v21; // rax
  __int64 v23; // [rsp+30h] [rbp-10h] BYREF
  __int64 v24; // [rsp+38h] [rbp-8h]
  LONG rgIndices; // [rsp+80h] [rbp+40h] BYREF
  struct tagSAFEARRAY **v26; // [rsp+88h] [rbp+48h]
  BSTR bstrString; // [rsp+90h] [rbp+50h] BYREF
  PWSTR Environment; // [rsp+98h] [rbp+58h] BYREF

  v26 = a2;
  v2 = 0;
  Environment = 0;
  v4 = 0;
  bstrString = 0;
  Vector = 0;
  v23 = 0;
  v6 = 0;
  v7 = (SAFEARRAY *)*((_QWORD *)this + 2);
  if ( !v7 )
    return v2;
  if ( *((_QWORD *)this + 3) )
  {
    v9 = CNotification::SchdpCreateEnvironment(this, (void **)&Environment);
    v2 = v9;
    if ( v9 >= 0 )
    {
      Vector = SafeArrayCreateVector(8u, 0, *(_DWORD *)(*((_QWORD *)this + 2) + 24LL));
      if ( Vector )
      {
        v12 = *(_DWORD *)(*((_QWORD *)this + 2) + 24LL);
        if ( (unsigned int)v12 > 0x7FFFFFFF )
        {
          v2 = -2147024362;
          v11 = 690;
LABEL_35:
          v10 = v2;
        }
        else
        {
          v2 = 0;
          rgIndices = 0;
          if ( v12 <= 0 )
          {
LABEL_28:
            *v26 = Vector;
            Vector = 0;
            goto LABEL_37;
          }
          while ( 1 )
          {
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            if ( v4 )
            {
              SysFreeString(v4);
              v4 = 0;
            }
            if ( v6 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v6);
              v6 = 0;
            }
            Element = SafeArrayGetElement(*((SAFEARRAY **)this + 2), &rgIndices, &bstrString);
            v2 = Element;
            if ( Element < 0 )
              break;
            v24 = SysStringLen(bstrString);
            v15 = RtlExpandEnvironmentStrings(Environment, bstrString, v24, 0, 0, &v23);
            if ( v15 == -1073741789 )
            {
              v16 = 2 * v23;
              v17 = GetProcessHeap();
              v6 = HeapAlloc(v17, 0, v16);
              if ( !v6 )
              {
                v10 = -2147024882;
                v11 = 716;
                v2 = -2147024882;
                goto LABEL_36;
              }
              v15 = RtlExpandEnvironmentStrings(Environment, bstrString, v24, v6, v23, 0);
            }
            if ( v15 < 0 )
            {
              v18 = RtlNtStatusToDosError(v15);
              v2 = v18;
              if ( v18 > 0 )
                v2 = (unsigned __int16)v18 | 0x80070000;
              if ( (v2 & 0x80000000) != 0 )
              {
                v11 = 727;
                goto LABEL_35;
              }
            }
            v19 = SysAllocString((const OLECHAR *)v6);
            v4 = v19;
            if ( !v19 )
            {
              v10 = -2147024882;
              v11 = 730;
              v2 = -2147024882;
              goto LABEL_36;
            }
            v20 = SafeArrayPutElement(Vector, &rgIndices, v19);
            v2 = v20;
            if ( v20 < 0 )
            {
              v10 = v20;
              v11 = 735;
              goto LABEL_36;
            }
            if ( ++rgIndices >= v12 )
              goto LABEL_28;
          }
          v10 = Element;
          v11 = 703;
        }
      }
      else
      {
        v10 = -2147024882;
        v11 = 687;
        v2 = -2147024882;
      }
    }
    else
    {
      v10 = v9;
      v11 = 682;
    }
LABEL_36:
    SdpDebugTrace(1u, L"CNotification::SchdpSubstituteParameters", v11, v10);
LABEL_37:
    if ( Environment )
      RtlDestroyEnvironment(Environment);
    goto LABEL_39;
  }
  v8 = SafeArrayCopy(v7, a2);
  v2 = v8;
  if ( v8 < 0 )
    SdpDebugTrace(1u, L"CNotification::SchdpSubstituteParameters", 678, v8);
LABEL_39:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  if ( v6 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v6);
  }
  if ( Vector )
    SafeArrayDestroy(Vector);
  return v2;
}

```

## disassembly

```asm
0x180003a94  mov     [rsp-38h+arg_8], rdx
0x180003a99  push    rbp
0x180003a9a  push    rbx
0x180003a9b  push    rsi
0x180003a9c  push    r12
0x180003a9e  push    r13
0x180003aa0  push    r14
0x180003aa2  push    r15
0x180003aa4  mov     rbp, rsp
0x180003aa7  sub     rsp, 40h
0x180003aab  xor     ebx, ebx
0x180003aad  mov     r13, rcx
0x180003ab0  and     [rbp+Environment], rbx
0x180003ab4  xor     esi, esi
0x180003ab6  and     [rbp+bstrString], rbx
0x180003aba  xor     r14d, r14d
0x180003abd  and     [rbp+var_10], rbx
0x180003ac1  xor     r15d, r15d
0x180003ac4  mov     rcx, [rcx+10h]; psa
0x180003ac8  test    rcx, rcx
0x180003acb  jz      loc_180003DF5
0x180003ad1  cmp     [r13+18h], rbx
0x180003ad5  jnz     short loc_180003B0A
0x180003ad7  call    cs:__imp_SafeArrayCopy
0x180003ade  nop     dword ptr [rax+rax+00h]
0x180003ae3  mov     ebx, eax
0x180003ae5  test    eax, eax
0x180003ae7  jns     loc_180003D8E
0x180003aed  mov     r9d, eax; int
0x180003af0  lea     rdx, aCnotificationS_2; "CNotification::SchdpSubstituteParameter"...
0x180003af7  mov     r8d, 2A6h; int
0x180003afd  lea     ecx, [rsi+1]; Level
0x180003b00  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003b05  jmp     loc_180003D8E
0x180003b0a  lea     rdx, [rbp+Environment]; void **
0x180003b0e  mov     rcx, r13; this
0x180003b11  call    ?SchdpCreateEnvironment@CNotification@@AEAAJPEAPEAX@Z; CNotification::SchdpCreateEnvironment(void * *)
0x180003b16  mov     ebx, eax
0x180003b18  test    eax, eax
0x180003b1a  jns     short loc_180003B2A
0x180003b1c  mov     r9d, eax
0x180003b1f  mov     r8d, 2AAh
0x180003b25  jmp     loc_180003D65
0x180003b2a  mov     r8, [r13+10h]
0x180003b2e  mov     ecx, 8; vt
0x180003b33  xor     edx, edx; lLbound
0x180003b35  mov     r8d, [r8+18h]; cElements
0x180003b39  call    cs:__imp_SafeArrayCreateVector
0x180003b40  nop     dword ptr [rax+rax+00h]
0x180003b45  mov     r14, rax
0x180003b48  test    rax, rax
0x180003b4b  jnz     short loc_180003B61
0x180003b4d  mov     r9d, 8007000Eh
0x180003b53  mov     r8d, 2AFh
0x180003b59  mov     ebx, r9d
0x180003b5c  jmp     loc_180003D65
0x180003b61  mov     rax, [r13+10h]
0x180003b65  mov     r12d, [rax+18h]
0x180003b69  cmp     r12d, 7FFFFFFFh
0x180003b70  ja      loc_180003D57
0x180003b76  xor     ebx, ebx
0x180003b78  and     [rbp+rgIndices], ebx
0x180003b7b  test    r12d, r12d
0x180003b7e  jle     loc_180003D0B
0x180003b84  mov     rcx, [rbp+bstrString]; bstrString
0x180003b88  test    rcx, rcx
0x180003b8b  jz      short loc_180003B9E
0x180003b8d  call    cs:__imp_SysFreeString
0x180003b94  nop     dword ptr [rax+rax+00h]
0x180003b99  and     [rbp+bstrString], 0
0x180003b9e  test    rsi, rsi
0x180003ba1  jz      short loc_180003BB4
0x180003ba3  mov     rcx, rsi; bstrString
0x180003ba6  call    cs:__imp_SysFreeString
0x180003bad  nop     dword ptr [rax+rax+00h]
0x180003bb2  xor     esi, esi
0x180003bb4  test    r15, r15
0x180003bb7  jz      short loc_180003BDC
0x180003bb9  call    cs:__imp_GetProcessHeap
0x180003bc0  nop     dword ptr [rax+rax+00h]
0x180003bc5  mov     r8, r15; lpMem
0x180003bc8  xor     edx, edx; dwFlags
0x180003bca  mov     rcx, rax; hHeap
0x180003bcd  call    cs:__imp_HeapFree
0x180003bd4  nop     dword ptr [rax+rax+00h]
0x180003bd9  xor     r15d, r15d
0x180003bdc  mov     rcx, [r13+10h]; psa
0x180003be0  lea     r8, [rbp+bstrString]; pv
0x180003be4  lea     rdx, [rbp+rgIndices]; rgIndices
0x180003be8  call    cs:__imp_SafeArrayGetElement
0x180003bef  nop     dword ptr [rax+rax+00h]
0x180003bf4  mov     ebx, eax
0x180003bf6  test    eax, eax
0x180003bf8  js      loc_180003D4C
0x180003bfe  mov     rcx, [rbp+bstrString]; pbstr
0x180003c02  call    cs:__imp_SysStringLen
0x180003c09  nop     dword ptr [rax+rax+00h]
0x180003c0e  mov     rdx, [rbp+bstrString]
0x180003c12  lea     rcx, [rbp+var_10]
0x180003c16  mov     eax, eax
0x180003c18  xor     r9d, r9d
0x180003c1b  mov     [rsp+40h+var_18], rcx
0x180003c20  mov     r8d, eax
0x180003c23  mov     rcx, [rbp+Environment]
0x180003c27  and     [rsp+40h+var_20], 0
0x180003c2d  mov     [rbp+var_8], rax
0x180003c31  call    cs:__imp_RtlExpandEnvironmentStrings
0x180003c38  nop     dword ptr [rax+rax+00h]
0x180003c3d  cmp     eax, 0C0000023h
0x180003c42  jnz     short loc_180003CA2
0x180003c44  mov     rax, [rbp+var_10]
0x180003c48  lea     rbx, [rax+rax]
0x180003c4c  call    cs:__imp_GetProcessHeap
0x180003c53  nop     dword ptr [rax+rax+00h]
0x180003c58  mov     r8, rbx; dwBytes
0x180003c5b  xor     edx, edx; dwFlags
0x180003c5d  mov     rcx, rax; hHeap
0x180003c60  call    cs:__imp_HeapAlloc
0x180003c67  nop     dword ptr [rax+rax+00h]
0x180003c6c  mov     r15, rax
0x180003c6f  test    rax, rax
0x180003c72  jz      loc_180003D17
0x180003c78  mov     rax, [rbp+var_10]
0x180003c7c  mov     r9, r15
0x180003c7f  and     [rsp+40h+var_18], 0
0x180003c85  mov     r8, [rbp+var_8]
0x180003c89  mov     rdx, [rbp+bstrString]
0x180003c8d  mov     rcx, [rbp+Environment]
0x180003c91  mov     [rsp+40h+var_20], rax
0x180003c96  call    cs:__imp_RtlExpandEnvironmentStrings
0x180003c9d  nop     dword ptr [rax+rax+00h]
0x180003ca2  test    eax, eax
0x180003ca4  jns     short loc_180003CC7
0x180003ca6  mov     ecx, eax; Status
0x180003ca8  call    cs:__imp_RtlNtStatusToDosError
0x180003caf  nop     dword ptr [rax+rax+00h]
0x180003cb4  mov     ebx, eax
0x180003cb6  test    eax, eax
0x180003cb8  jle     short loc_180003CC3
0x180003cba  movzx   ebx, ax
0x180003cbd  or      ebx, 80070000h
0x180003cc3  test    ebx, ebx
0x180003cc5  js      short loc_180003D28
0x180003cc7  mov     rcx, r15; psz
0x180003cca  call    cs:__imp_SysAllocString
0x180003cd1  nop     dword ptr [rax+rax+00h]
0x180003cd6  mov     rsi, rax
0x180003cd9  test    rax, rax
0x180003cdc  jz      short loc_180003D3B
0x180003cde  mov     r8, rax; pv
0x180003ce1  lea     rdx, [rbp+rgIndices]; rgIndices
0x180003ce5  mov     rcx, r14; psa
0x180003ce8  call    cs:__imp_SafeArrayPutElement
0x180003cef  nop     dword ptr [rax+rax+00h]
0x180003cf4  mov     ebx, eax
0x180003cf6  test    eax, eax
0x180003cf8  js      short loc_180003D30
0x180003cfa  mov     eax, [rbp+rgIndices]
0x180003cfd  inc     eax
0x180003cff  mov     [rbp+rgIndices], eax
0x180003d02  cmp     eax, r12d
0x180003d05  jl      loc_180003B84
0x180003d0b  mov     rax, [rbp+arg_8]
0x180003d0f  mov     [rax], r14
0x180003d12  xor     r14d, r14d
0x180003d15  jmp     short loc_180003D76
0x180003d17  mov     r9d, 8007000Eh
0x180003d1d  mov     r8d, 2CCh
0x180003d23  mov     ebx, r9d
0x180003d26  jmp     short loc_180003D65
0x180003d28  mov     r8d, 2D7h
0x180003d2e  jmp     short loc_180003D62
0x180003d30  mov     r9d, eax
0x180003d33  mov     r8d, 2DFh
0x180003d39  jmp     short loc_180003D65
0x180003d3b  mov     r9d, 8007000Eh
0x180003d41  mov     r8d, 2DAh
0x180003d47  mov     ebx, r9d
0x180003d4a  jmp     short loc_180003D65
0x180003d4c  mov     r9d, eax
0x180003d4f  mov     r8d, 2BFh
0x180003d55  jmp     short loc_180003D65
0x180003d57  mov     ebx, 80070216h
0x180003d5c  mov     r8d, 2B2h; int
0x180003d62  mov     r9d, ebx; int
0x180003d65  lea     rdx, aCnotificationS_2; "CNotification::SchdpSubstituteParameter"...
0x180003d6c  mov     ecx, 1; Level
0x180003d71  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003d76  mov     rax, [rbp+Environment]
0x180003d7a  test    rax, rax
0x180003d7d  jz      short loc_180003D8E
0x180003d7f  mov     rcx, rax; Environment
0x180003d82  call    cs:__imp_RtlDestroyEnvironment
0x180003d89  nop     dword ptr [rax+rax+00h]
0x180003d8e  mov     rcx, [rbp+bstrString]; bstrString
0x180003d92  test    rcx, rcx
0x180003d95  jz      short loc_180003DA8
0x180003d97  call    cs:__imp_SysFreeString
0x180003d9e  nop     dword ptr [rax+rax+00h]
0x180003da3  and     [rbp+bstrString], 0
0x180003da8  test    rsi, rsi
0x180003dab  jz      short loc_180003DBC
0x180003dad  mov     rcx, rsi; bstrString
0x180003db0  call    cs:__imp_SysFreeString
0x180003db7  nop     dword ptr [rax+rax+00h]
0x180003dbc  test    r15, r15
0x180003dbf  jz      short loc_180003DE1
0x180003dc1  call    cs:__imp_GetProcessHeap
0x180003dc8  nop     dword ptr [rax+rax+00h]
0x180003dcd  mov     r8, r15; lpMem
0x180003dd0  xor     edx, edx; dwFlags
0x180003dd2  mov     rcx, rax; hHeap
0x180003dd5  call    cs:__imp_HeapFree
0x180003ddc  nop     dword ptr [rax+rax+00h]
0x180003de1  test    r14, r14
0x180003de4  jz      short loc_180003DF5
0x180003de6  mov     rcx, r14; psa
0x180003de9  call    cs:__imp_SafeArrayDestroy
0x180003df0  nop     dword ptr [rax+rax+00h]
0x180003df5  mov     eax, ebx
0x180003df7  add     rsp, 40h
0x180003dfb  pop     r15
0x180003dfd  pop     r14
0x180003dff  pop     r13
0x180003e01  pop     r12
0x180003e03  pop     rsi
0x180003e04  pop     rbx
0x180003e05  pop     rbp
0x180003e06  retn
```
