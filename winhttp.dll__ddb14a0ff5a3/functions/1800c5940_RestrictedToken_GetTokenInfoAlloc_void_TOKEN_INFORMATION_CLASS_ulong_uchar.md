# RestrictedToken::GetTokenInfoAlloc(void *,_TOKEN_INFORMATION_CLASS,ulong *,uchar * *)

- ea: `0x1800c5940`
- end: `0x1800c5b24`
- name: `?GetTokenInfoAlloc@RestrictedToken@@AEAAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAKPEAPEAE@Z`
- size: `484`
- prototype: `int(RestrictedToken *__hidden this, void *, enum _TOKEN_INFORMATION_CLASS, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800c5d08`

## callees

- `0x1800081a0`
- `0x18001b480`
- `0x1800a1d10`
- `0x1800c5940`
- `0x1800db6b0`
- `0x1800db758`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c59da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c5a84`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c59da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c5a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c59f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c59f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5a8e`

## pseudocode

```c
__int64 __fastcall RestrictedToken::GetTokenInfoAlloc(
        RestrictedToken *this,
        void *a2,
        enum _TOKEN_INFORMATION_CLASS a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  unsigned __int8 *v5; // rbx
  unsigned int v8; // edi
  __int64 v9; // r9
  signed int LastError; // eax
  __int64 v11; // rcx
  unsigned __int8 *Heap; // rax
  signed int v13; // eax
  DWORD v14; // eax
  PDWORD ReturnLength; // [rsp+20h] [rbp-30h]
  unsigned __int8 *v17; // [rsp+38h] [rbp-18h] BYREF
  DWORD TokenInformationLength; // [rsp+40h] [rbp-10h] BYREF
  DWORD v19; // [rsp+44h] [rbp-Ch] BYREF

  v5 = 0;
  v17 = 0;
  v19 = 0;
  TokenInformationLength = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qqD(
      1029,
      20,
      (unsigned int)WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids,
      (unsigned int)PacWorkerClient::s_RestrictedToken,
      (__int64)a2);
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( GetTokenInformation(a2, TokenGroups, 0, 0, &TokenInformationLength) )
  {
    v8 = -2147418113;
    v9 = 2147549183LL;
    goto LABEL_25;
  }
  LastError = GetLastError();
  v9 = (unsigned int)LastError;
  if ( LastError != 122 )
  {
    if ( !LastError )
    {
      v8 = -2147418113;
      v9 = 2147549183LL;
      goto LABEL_25;
    }
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (int)v9 < 0 )
      goto LABEL_15;
  }
  Heap = (unsigned __int8 *)WxAllocateHeapEx(v11, TokenInformationLength);
  if ( !Heap )
  {
    v9 = 2147942414LL;
LABEL_15:
    v8 = v9;
    goto LABEL_25;
  }
  v5 = Heap;
  v17 = Heap;
  if ( GetTokenInformation(a2, TokenGroups, Heap, TokenInformationLength, &v19) )
  {
    v14 = v19;
    v9 = 0;
    *a5 = v5;
    v5 = 0;
    *a4 = v14;
    v8 = 0;
    v17 = 0;
  }
  else
  {
    v13 = GetLastError();
    v9 = (unsigned int)v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( (int)v9 < 0 )
    {
      v8 = v9;
    }
    else
    {
      v8 = -2147418113;
      v9 = 2147549183LL;
    }
  }
LABEL_25:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 21, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids, v9, ReturnLength);
  if ( v5 )
    WxFreeHeapEx(&v17);
  return v8;
}

```

## disassembly

```asm
0x1800c5940  mov     [rsp-18h+arg_0], rbx
0x1800c5945  mov     [rsp-18h+arg_10], rsi
0x1800c594a  push    rbp
0x1800c594b  push    rdi
0x1800c594c  push    r14
0x1800c594e  mov     rbp, rsp
0x1800c5951  sub     rsp, 50h
0x1800c5955  mov     rax, cs:__security_cookie
0x1800c595c  xor     rax, rsp
0x1800c595f  mov     [rbp+var_8], rax
0x1800c5963  mov     rsi, [rbp+arg_20]
0x1800c5967  xor     ebx, ebx
0x1800c5969  mov     [rbp+var_18], rbx
0x1800c596d  mov     rdi, r9
0x1800c5970  mov     [rbp+var_C], ebx
0x1800c5973  mov     r14, rdx
0x1800c5976  mov     [rbp+var_1C], 0
0x1800c597d  mov     [rbp+TokenInformationLength], 0
0x1800c5984  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c598b  jz      short loc_1800C59B5
0x1800c598d  lea     edx, [rbx+14h]
0x1800c5990  mov     [rsp+50h+var_28], 2
0x1800c5998  mov     ecx, 405h
0x1800c599d  mov     [rsp+50h+ReturnLength], r14
0x1800c59a2  lea     r9, ?s_RestrictedToken@PacWorkerClient@@0VRestrictedToken@@A; RestrictedToken PacWorkerClient::s_RestrictedToken
0x1800c59a9  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x1800c59b0  call    WPP_SF_qqD
0x1800c59b5  test    rdi, rdi
0x1800c59b8  jz      short loc_1800C59BC
0x1800c59ba  mov     [rdi], ebx
0x1800c59bc  test    rsi, rsi
0x1800c59bf  jz      short loc_1800C59C4
0x1800c59c1  mov     [rsi], rbx
0x1800c59c4  xor     r9d, r9d; TokenInformationLength
0x1800c59c7  lea     rax, [rbp+TokenInformationLength]
0x1800c59cb  xor     r8d, r8d; TokenInformation
0x1800c59ce  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800c59d3  mov     rcx, r14; TokenHandle
0x1800c59d6  lea     edx, [r9+2]; TokenInformationClass
0x1800c59da  call    cs:__imp_GetTokenInformation
0x1800c59e0  test    eax, eax
0x1800c59e2  jz      short loc_1800C59F8
0x1800c59e4  mov     edi, 8000FFFFh
0x1800c59e9  mov     [rbp+var_1C], 10Ah
0x1800c59f0  mov     r9d, edi
0x1800c59f3  jmp     loc_1800C5AD4
0x1800c59f8  call    cs:__imp_GetLastError
0x1800c59fe  mov     r9d, eax
0x1800c5a01  cmp     eax, 7Ah ; 'z'
0x1800c5a04  jz      short loc_1800C5A3F
0x1800c5a06  test    eax, eax
0x1800c5a08  jnz     short loc_1800C5A1E
0x1800c5a0a  mov     edi, 8000FFFFh
0x1800c5a0f  mov     [rbp+var_1C], 10Fh
0x1800c5a16  mov     r9d, edi
0x1800c5a19  jmp     loc_1800C5AD4
0x1800c5a1e  jle     short loc_1800C5A2B
0x1800c5a20  movzx   r9d, ax
0x1800c5a24  or      r9d, 80070000h
0x1800c5a2b  test    r9d, r9d
0x1800c5a2e  jns     short loc_1800C5A3F
0x1800c5a30  mov     [rbp+var_1C], 110h
0x1800c5a37  mov     edi, r9d
0x1800c5a3a  jmp     loc_1800C5AD4
0x1800c5a3f  mov     edx, [rbp+TokenInformationLength]
0x1800c5a42  mov     [rbp+var_1C], ebx
0x1800c5a45  call    WxAllocateHeapEx
0x1800c5a4a  test    rax, rax
0x1800c5a4d  jnz     short loc_1800C5A65
0x1800c5a4f  mov     [rbp+var_1C], 34h ; '4'
0x1800c5a56  mov     r9d, 8007000Eh
0x1800c5a5c  mov     [rbp+var_1C], 114h
0x1800c5a63  jmp     short loc_1800C5A37
0x1800c5a65  mov     rbx, rax
0x1800c5a68  mov     [rbp+var_18], rax
0x1800c5a6c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800c5a70  lea     rax, [rbp+var_C]
0x1800c5a74  mov     r8, rbx; TokenInformation
0x1800c5a77  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800c5a7c  mov     edx, 2; TokenInformationClass
0x1800c5a81  mov     rcx, r14; TokenHandle
0x1800c5a84  call    cs:__imp_GetTokenInformation
0x1800c5a8a  test    eax, eax
0x1800c5a8c  jnz     short loc_1800C5AC1
0x1800c5a8e  call    cs:__imp_GetLastError
0x1800c5a94  mov     r9d, eax
0x1800c5a97  test    eax, eax
0x1800c5a99  jle     short loc_1800C5AA6
0x1800c5a9b  movzx   r9d, ax
0x1800c5a9f  or      r9d, 80070000h
0x1800c5aa6  test    r9d, r9d
0x1800c5aa9  js      short loc_1800C5AB5
0x1800c5aab  mov     edi, 8000FFFFh
0x1800c5ab0  mov     r9d, edi
0x1800c5ab3  jmp     short loc_1800C5AB8
0x1800c5ab5  mov     edi, r9d
0x1800c5ab8  mov     [rbp+var_1C], 11Ah
0x1800c5abf  jmp     short loc_1800C5AD4
0x1800c5ac1  mov     eax, [rbp+var_C]
0x1800c5ac4  xor     r9d, r9d
0x1800c5ac7  mov     [rsi], rbx
0x1800c5aca  xor     ebx, ebx
0x1800c5acc  mov     [rdi], eax
0x1800c5ace  xor     edi, edi
0x1800c5ad0  mov     [rbp+var_18], rbx
0x1800c5ad4  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c5adb  jz      short loc_1800C5AF3
0x1800c5add  mov     edx, 15h
0x1800c5ae2  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x1800c5ae9  mov     ecx, 405h
0x1800c5aee  call    WPP_SF_d
0x1800c5af3  test    rbx, rbx
0x1800c5af6  jz      short loc_1800C5B01
0x1800c5af8  lea     rcx, [rbp+var_18]
0x1800c5afc  call    WxFreeHeapEx
0x1800c5b01  mov     eax, edi
0x1800c5b03  mov     rcx, [rbp+var_8]
0x1800c5b07  xor     rcx, rsp; StackCookie
0x1800c5b0a  call    __security_check_cookie
0x1800c5b0f  lea     r11, [rsp+50h+var_s0]
0x1800c5b14  mov     rbx, [r11+20h]
0x1800c5b18  mov     rsi, [r11+30h]
0x1800c5b1c  mov     rsp, r11
0x1800c5b1f  pop     r14
0x1800c5b21  pop     rdi
0x1800c5b22  pop     rbp
0x1800c5b23  retn
```
