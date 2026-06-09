# GetXmlFilePath(ushort * *)

- ea: `0x1800080dc`
- end: `0x180008234`
- name: `?GetXmlFilePath@@YAKPEAPEAG@Z`
- size: `344`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001072c`
- `0x180011444`
- `0x180011a14`
- `0x180011cd4`

## callees

- `0x1800080dc`
- `0x1800089dc`
- `0x180008b90`
- `0x1800090c0`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180008205`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000813f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000813f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000812c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800081c5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000812c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800081c5`

## string_xrefs

- `0x180008125`: `%windir%\System32\ras\SSTPProxy\ProxyConfig.xml`
- `0x1800081be`: `%windir%\System32\ras\SSTPProxy\ProxyConfig.xml`
- `0x180008166`: `GetXmlFilePath: ExpandEnvironmentStringsW method failed with error %d`

## pseudocode

```c
__int64 __fastcall GetXmlFilePath(unsigned __int16 **a1)
{
  void **v1; // rsi
  unsigned int v2; // edi
  DWORD v3; // eax
  unsigned __int64 v4; // r14
  DWORD LastError; // eax
  WCHAR *v6; // rax
  int v10; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-834h] BYREF
  std::bad_alloc *v12; // [rsp+830h] [rbp-38h] BYREF

  v1 = (void **)a1;
  v2 = 0;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  *v1 = 0;
  v3 = ExpandEnvironmentStringsW(L"%windir%\\System32\\ras\\SSTPProxy\\ProxyConfig.xml", 0, 0);
  v4 = v3;
  if ( v3 || (LastError = GetLastError(), (v2 = LastError) == 0) )
  {
    try
    {
      v6 = (WCHAR *)operator new[](saturated_mul(v4, 2u));
      *v1 = v6;
    }
    catch ( std::bad_alloc *v12 )
    {
      *a1 = 0;
      v2 = 8;
      v1 = (void **)a1;
      goto LABEL_10;
    }
    if ( ExpandEnvironmentStringsW(L"%windir%\\System32\\ras\\SSTPProxy\\ProxyConfig.xml", v6, v4) )
    {
      if ( !v2 )
        return v2;
      goto LABEL_10;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( !LastError )
      return v2;
  }
  if ( (byte_18002E903 & 8) != 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"GetXmlFilePath: ExpandEnvironmentStringsW method failed with error %d", LastError);
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
  }
LABEL_10:
  if ( *v1 )
    operator delete[](*v1);
  *v1 = 0;
  return v2;
}

```

## disassembly

```asm
0x1800080dc  push    rbx
0x1800080de  push    rsi
0x1800080df  push    rdi
0x1800080e0  push    r14
0x1800080e2  sub     rsp, 848h
0x1800080e9  mov     rax, cs:__security_cookie
0x1800080f0  xor     rax, rsp
0x1800080f3  mov     [rsp+868h+var_30], rax
0x1800080fb  mov     rsi, rcx
0x1800080fe  mov     [rsp+868h+var_840], rcx
0x180008103  xor     ebx, ebx
0x180008105  mov     edi, ebx
0x180008107  mov     [rsp+868h+var_838], ebx
0x18000810b  xor     edx, edx; Val
0x18000810d  mov     r8d, 7FCh; Size
0x180008113  lea     rcx, [rsp+868h+var_834]; void *
0x180008118  call    memset_0
0x18000811d  mov     [rsi], rbx
0x180008120  xor     r8d, r8d; nSize
0x180008123  xor     edx, edx; lpDst
0x180008125  lea     rcx, Src; "%windir%\\System32\\ras\\SSTPProxy\\Pro"...
0x18000812c  call    cs:__imp_ExpandEnvironmentStringsW
0x180008133  nop     dword ptr [rax+rax+00h]
0x180008138  mov     r14d, eax
0x18000813b  test    eax, eax
0x18000813d  jnz     short loc_18000819A
0x18000813f  call    cs:__imp_GetLastError
0x180008146  nop     dword ptr [rax+rax+00h]
0x18000814b  mov     edi, eax
0x18000814d  test    eax, eax
0x18000814f  jz      short loc_18000819A
0x180008151  test    cs:byte_18002E903, 8
0x180008158  jz      loc_1800081FD
0x18000815e  mov     word ptr [rsp+868h+var_838], bx
0x180008163  mov     r8d, eax
0x180008166  lea     rdx, aGetxmlfilepath; "GetXmlFilePath: ExpandEnvironmentString"...
0x18000816d  lea     rcx, [rsp+868h+var_838]
0x180008172  call    FormatRRASErrorString
0x180008177  test    cs:byte_18002E903, 8
0x18000817e  jz      short loc_1800081FD
0x180008180  lea     r8, [rsp+868h+var_838]
0x180008185  lea     rdx, RasSSTPSvcTraceError
0x18000818c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008193  call    McTemplateU0z_EventWriteTransfer
0x180008198  jmp     short loc_1800081FD
0x18000819a  mov     eax, 2
0x18000819f  mul     r14
0x1800081a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800081a9  cmovb   rax, rcx
0x1800081ad  mov     rcx, rax; unsigned __int64
0x1800081b0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800081b5  mov     [rsi], rax
0x1800081b8  mov     r8d, r14d; nSize
0x1800081bb  mov     rdx, rax; lpDst
0x1800081be  lea     rcx, Src; "%windir%\\System32\\ras\\SSTPProxy\\Pro"...
0x1800081c5  call    cs:__imp_ExpandEnvironmentStringsW
0x1800081cc  nop     dword ptr [rax+rax+00h]
0x1800081d1  test    eax, eax
0x1800081d3  jnz     short loc_1800081EC
0x1800081d5  call    cs:__imp_GetLastError
0x1800081dc  nop     dword ptr [rax+rax+00h]
0x1800081e1  mov     edi, eax
0x1800081e3  test    eax, eax
0x1800081e5  jz      short loc_180008214
0x1800081e7  jmp     loc_180008151
0x1800081ec  test    edi, edi
0x1800081ee  jnz     short loc_1800081FD
0x1800081f0  jmp     short loc_180008214
0x1800081f2  xor     ebx, ebx
0x1800081f4  mov     edi, [rsp+868h+var_848]
0x1800081f8  mov     rsi, [rsp+868h+var_840]
0x1800081fd  cmp     [rsi], rbx
0x180008200  jz      short loc_180008211
0x180008202  mov     rcx, [rsi]
0x180008205  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000820c  nop     dword ptr [rax+rax+00h]
0x180008211  mov     [rsi], rbx
0x180008214  mov     eax, edi
0x180008216  mov     rcx, [rsp+868h+var_30]
0x18000821e  xor     rcx, rsp; StackCookie
0x180008221  call    __security_check_cookie
0x180008226  add     rsp, 848h
0x18000822d  pop     r14
0x18000822f  pop     rdi
0x180008230  pop     rsi
0x180008231  pop     rbx
0x180008232  retn
```
