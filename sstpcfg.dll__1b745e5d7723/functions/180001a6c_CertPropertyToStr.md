# CertPropertyToStr

- ea: `0x180001a6c`
- end: `0x180001d00`
- name: `CertPropertyToStr`
- size: `660`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003aac`
- `0x180005830`

## callees

- `0x180001a6c`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001bbf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001bbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001bae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001bae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ccb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ccb`
- `CRYPT32!CertGetNameStringW` at `0x180001acd`
- `CRYPT32!CertGetNameStringW` at `0x180001b48`
- `CRYPT32!CertGetNameStringW` at `0x180001c5c`
- `CRYPT32!CertGetNameStringW` at `0x180001acd`
- `CRYPT32!CertGetNameStringW` at `0x180001b48`
- `CRYPT32!CertGetNameStringW` at `0x180001c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c1a`

## pseudocode

```c
__int64 __fastcall CertPropertyToStr(PCCERT_CONTEXT pCertContext, DWORD dwFlags, WCHAR **a3, DWORD *a4)
{
  unsigned int v8; // edi
  DWORD v9; // esi
  DWORD NameStringW; // eax
  __int64 v11; // rdx
  const wchar_t *v12; // r8
  SIZE_T v13; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *pszNameString; // rbx
  __int64 v16; // rbx
  DWORD LastError; // eax
  __int64 v18; // r8
  DWORD v19; // eax
  DWORD v20; // eax
  HANDLE v21; // rax
  int v23; // [rsp+30h] [rbp-848h] BYREF
  _BYTE v24[2044]; // [rsp+34h] [rbp-844h] BYREF

  v23 = 0;
  v8 = 0;
  memset_0(v24, 0, sizeof(v24));
  v9 = 4;
  NameStringW = CertGetNameStringW(pCertContext, 4u, dwFlags, 0, 0, 0);
  *a4 = NameStringW;
  if ( NameStringW > 1 )
    goto LABEL_16;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Cu);
  }
  if ( (_QWORD)xmmword_1800146E0 )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      xmmword_1800146E0,
      L"CertGetNameString for CERT_NAME_SIMPLE_DISPLAY_TYPE failed.");
  v9 = 6;
  NameStringW = CertGetNameStringW(pCertContext, 6u, dwFlags, 0, 0, 0);
  *a4 = NameStringW;
  if ( NameStringW > 1 )
  {
LABEL_16:
    v13 = 2LL * NameStringW;
    ProcessHeap = GetProcessHeap();
    pszNameString = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v13);
    if ( pszNameString )
    {
      v20 = CertGetNameStringW(pCertContext, v9, dwFlags, 0, pszNameString, *a4);
      *a4 = v20;
      if ( v20 > 1 )
      {
        *a3 = pszNameString;
        return 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Fu);
        }
        if ( (_QWORD)xmmword_1800146E0 )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
            gSstpCfgEtwContext,
            xmmword_1800146E0,
            L"CertGetNameString failed.");
        v21 = GetProcessHeap();
        HeapFree(v21, 0, pszNameString);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v16 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_d(v16, 0x2Eu, v18, LastError);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v23) = 0;
        v19 = GetLastError();
        FormatRRASErrorString((wchar_t *)&v23, L"LocalAlloc failed and returned %d", v19);
        v11 = xmmword_1800146E0;
        v12 = (const wchar_t *)&v23;
        goto LABEL_15;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Du);
    }
    v11 = xmmword_1800146E0;
    if ( (_QWORD)xmmword_1800146E0 )
    {
      v12 = L"CertGetNameString for CERT_NAME_DNS_TYPE failed.";
LABEL_15:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v11, v12);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180001a6c  push    rbx
0x180001a6e  push    rbp
0x180001a6f  push    rsi
0x180001a70  push    rdi
0x180001a71  push    r12
0x180001a73  push    r14
0x180001a75  push    r15
0x180001a77  sub     rsp, 840h
0x180001a7e  mov     rax, cs:__security_cookie
0x180001a85  xor     rax, rsp
0x180001a88  mov     [rsp+878h+var_48], rax
0x180001a90  mov     r12, r8
0x180001a93  mov     r15d, edx
0x180001a96  mov     rbp, rcx
0x180001a99  xor     eax, eax
0x180001a9b  xor     edx, edx; Val
0x180001a9d  mov     [rsp+878h+var_848], eax
0x180001aa1  mov     r8d, 7FCh; Size
0x180001aa7  lea     rcx, [rsp+878h+var_844]; void *
0x180001aac  mov     r14, r9
0x180001aaf  xor     edi, edi
0x180001ab1  call    memset_0
0x180001ab6  lea     esi, [rdi+4]
0x180001ab9  mov     [rsp+878h+cchNameString], edi; cchNameString
0x180001abd  mov     edx, esi; dwType
0x180001abf  mov     [rsp+878h+pszNameString], rdi; pszNameString
0x180001ac4  xor     r9d, r9d; pvTypePara
0x180001ac7  mov     r8d, r15d; dwFlags
0x180001aca  mov     rcx, rbp; pCertContext
0x180001acd  call    cs:__imp_CertGetNameStringW
0x180001ad3  mov     [r14], eax
0x180001ad6  lea     rbx, WPP_GLOBAL_Control
0x180001add  cmp     eax, 1
0x180001ae0  ja      loc_180001BA9
0x180001ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001aed  cmp     rcx, rbx
0x180001af0  jz      short loc_180001B0A
0x180001af2  test    byte ptr [rcx+1Ch], 40h
0x180001af6  jz      short loc_180001B0A
0x180001af8  cmp     byte ptr [rcx+19h], 1
0x180001afc  jb      short loc_180001B0A
0x180001afe  mov     rcx, [rcx+10h]
0x180001b02  lea     edx, [rdi+2Ch]
0x180001b05  call    WPP_SF_
0x180001b0a  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180001b11  test    rdx, rdx
0x180001b14  jz      short loc_180001B30
0x180001b16  mov     rcx, cs:gSstpCfgEtwContext
0x180001b1d  lea     r8, aCertgetnamestr; "CertGetNameString for CERT_NAME_SIMPLE_"...
0x180001b24  mov     rax, cs:gSstpCfgTemplateFunc
0x180001b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b30  xor     r9d, r9d; pvTypePara
0x180001b33  mov     [rsp+878h+cchNameString], edi; cchNameString
0x180001b37  mov     r8d, r15d; dwFlags
0x180001b3a  mov     [rsp+878h+pszNameString], rdi; pszNameString
0x180001b3f  mov     rcx, rbp; pCertContext
0x180001b42  lea     esi, [r9+6]
0x180001b46  mov     edx, esi; dwType
0x180001b48  call    cs:__imp_CertGetNameStringW
0x180001b4e  mov     [r14], eax
0x180001b51  cmp     eax, 1
0x180001b54  ja      short loc_180001BA9
0x180001b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b5d  cmp     rcx, rbx
0x180001b60  jz      short loc_180001B7A
0x180001b62  test    byte ptr [rcx+1Ch], 40h
0x180001b66  jz      short loc_180001B7A
0x180001b68  cmp     byte ptr [rcx+19h], 1
0x180001b6c  jb      short loc_180001B7A
0x180001b6e  mov     rcx, [rcx+10h]
0x180001b72  lea     edx, [rsi+27h]
0x180001b75  call    WPP_SF_
0x180001b7a  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180001b81  test    rdx, rdx
0x180001b84  jz      loc_180001CDC
0x180001b8a  lea     r8, aCertgetnamestr_1; "CertGetNameString for CERT_NAME_DNS_TYP"...
0x180001b91  mov     rcx, cs:gSstpCfgEtwContext
0x180001b98  mov     rax, cs:gSstpCfgTemplateFunc
0x180001b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ba4  jmp     loc_180001CDC
0x180001ba9  mov     ebx, eax
0x180001bab  add     rbx, rbx
0x180001bae  call    cs:__imp_GetProcessHeap
0x180001bb4  mov     r8, rbx; dwBytes
0x180001bb7  mov     edx, 8; dwFlags
0x180001bbc  mov     rcx, rax; hHeap
0x180001bbf  call    cs:__imp_HeapAlloc
0x180001bc5  mov     rbx, rax
0x180001bc8  test    rax, rax
0x180001bcb  jnz     short loc_180001C45
0x180001bcd  mov     rbx, cs:WPP_GLOBAL_Control
0x180001bd4  lea     rax, WPP_GLOBAL_Control
0x180001bdb  cmp     rbx, rax
0x180001bde  jz      short loc_180001C06
0x180001be0  test    byte ptr [rbx+1Ch], 40h
0x180001be4  jz      short loc_180001C06
0x180001be6  cmp     byte ptr [rbx+19h], 1
0x180001bea  jb      short loc_180001C06
0x180001bec  mov     rbx, [rbx+10h]
0x180001bf0  call    cs:__imp_GetLastError
0x180001bf6  mov     edx, 2Eh ; '.'
0x180001bfb  mov     rcx, rbx
0x180001bfe  mov     r9d, eax
0x180001c01  call    WPP_SF_d
0x180001c06  cmp     qword ptr cs:xmmword_1800146E0, rdi
0x180001c0d  jz      loc_180001CDC
0x180001c13  xor     eax, eax
0x180001c15  mov     word ptr [rsp+878h+var_848], ax
0x180001c1a  call    cs:__imp_GetLastError
0x180001c20  mov     r8d, eax
0x180001c23  lea     rdx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x180001c2a  lea     rcx, [rsp+878h+var_848]
0x180001c2f  call    FormatRRASErrorString
0x180001c34  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180001c3b  lea     r8, [rsp+878h+var_848]
0x180001c40  jmp     loc_180001B91
0x180001c45  mov     eax, [r14]
0x180001c48  xor     r9d, r9d; pvTypePara
0x180001c4b  mov     [rsp+878h+cchNameString], eax; cchNameString
0x180001c4f  mov     r8d, r15d; dwFlags
0x180001c52  mov     edx, esi; dwType
0x180001c54  mov     [rsp+878h+pszNameString], rbx; pszNameString
0x180001c59  mov     rcx, rbp; pCertContext
0x180001c5c  call    cs:__imp_CertGetNameStringW
0x180001c62  mov     [r14], eax
0x180001c65  cmp     eax, 1
0x180001c68  ja      short loc_180001CD3
0x180001c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c71  lea     rax, WPP_GLOBAL_Control
0x180001c78  cmp     rcx, rax
0x180001c7b  jz      short loc_180001C97
0x180001c7d  test    byte ptr [rcx+1Ch], 40h
0x180001c81  jz      short loc_180001C97
0x180001c83  cmp     byte ptr [rcx+19h], 1
0x180001c87  jb      short loc_180001C97
0x180001c89  mov     rcx, [rcx+10h]
0x180001c8d  mov     edx, 2Fh ; '/'
0x180001c92  call    WPP_SF_
0x180001c97  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180001c9e  test    rdx, rdx
0x180001ca1  jz      short loc_180001CBD
0x180001ca3  mov     rcx, cs:gSstpCfgEtwContext
0x180001caa  lea     r8, aCertgetnamestr_0; "CertGetNameString failed."
0x180001cb1  mov     rax, cs:gSstpCfgTemplateFunc
0x180001cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cbd  call    cs:__imp_GetProcessHeap
0x180001cc3  mov     r8, rbx; lpMem
0x180001cc6  xor     edx, edx; dwFlags
0x180001cc8  mov     rcx, rax; hHeap
0x180001ccb  call    cs:__imp_HeapFree
0x180001cd1  jmp     short loc_180001CDC
0x180001cd3  mov     [r12], rbx
0x180001cd7  mov     edi, 1
0x180001cdc  mov     eax, edi
0x180001cde  mov     rcx, [rsp+878h+var_48]
0x180001ce6  xor     rcx, rsp; StackCookie
0x180001ce9  call    __security_check_cookie
0x180001cee  add     rsp, 840h
0x180001cf5  pop     r15
0x180001cf7  pop     r14
0x180001cf9  pop     r12
0x180001cfb  pop     rdi
0x180001cfc  pop     rsi
0x180001cfd  pop     rbp
0x180001cfe  pop     rbx
0x180001cff  retn
```
