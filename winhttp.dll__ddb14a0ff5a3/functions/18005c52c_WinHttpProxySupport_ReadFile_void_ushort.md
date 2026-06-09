# WinHttpProxySupport::ReadFile(void *,ushort * *)

- ea: `0x18005c52c`
- end: `0x18005c6f4`
- name: `?ReadFile@WinHttpProxySupport@@AEAAJPEAXPEAPEAG@Z`
- size: `456`
- prototype: `int(WinHttpProxySupport *__hidden this, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18005c2cc`

## callees

- `0x18000bd94`
- `0x18000bfd0`
- `0x18003dc40`
- `0x18005c52c`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c66e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c66e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005c58e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005c58e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005c5f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005c5f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c69d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c69d`

## pseudocode

```c
__int64 __fastcall WinHttpProxySupport::ReadFile(WinHttpProxySupport *this, void *a2, unsigned __int16 **a3)
{
  void *v3; // rbx
  CHAR *v6; // rax
  int v7; // edi
  unsigned int v8; // edi
  DWORD v9; // ebp
  CHAR *v10; // rsi
  CHAR *v11; // rax
  signed int LastError; // eax
  __int64 v14; // [rsp+20h] [rbp-48h]
  void *v15; // [rsp+28h] [rbp-40h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF

  v3 = 0;
  v15 = 0;
  dwNumberOfBytesRead = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 16, WPP_7e31abdad6703866b17c79b76f86b5b6_Traceguids);
  HIDWORD(v14) = 0;
  v6 = (CHAR *)CoTaskMemAlloc(0x186A0u);
  if ( v6 )
  {
    v8 = 0;
    v9 = 100000;
    v10 = v6;
    while ( WinHttpReadData(a2, v6, v9, &dwNumberOfBytesRead) )
    {
      if ( !dwNumberOfBytesRead )
      {
        v7 = WxNewStringAtoWCch<WxCoTaskAllocator>(v10, v8, &v15);
        if ( v7 >= 0 )
        {
          *a3 = (unsigned __int16 *)v15;
          v15 = 0;
        }
        else
        {
          v3 = v15;
          HIDWORD(v14) = 468;
        }
        goto LABEL_22;
      }
      v8 += dwNumberOfBytesRead;
      v9 -= dwNumberOfBytesRead;
      if ( !v9 )
      {
        HIDWORD(v14) = 0;
        v11 = (CHAR *)CoTaskMemRealloc(v10, v8 + 100000);
        if ( !v11 )
        {
          v7 = -2147024882;
          HIDWORD(v14) = 458;
          goto LABEL_22;
        }
        v10 = v11;
        v9 = 100000;
      }
      if ( v8 > 0x100000 )
      {
        v7 = -2146685049;
        HIDWORD(v14) = 463;
        goto LABEL_22;
      }
      v6 = &v10[v8];
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    HIDWORD(v14) = 442;
    if ( v7 >= 0 )
      v7 = -2147418113;
LABEL_22:
    CoTaskMemFree(v10);
  }
  else
  {
    v7 = -2147024882;
    HIDWORD(v14) = 437;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 17, WPP_7e31abdad6703866b17c79b76f86b5b6_Traceguids, (unsigned int)v7, v14);
  if ( v3 )
    WxCoTaskAllocator::Free(&v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005c52c  mov     [rsp+arg_0], rbx
0x18005c531  push    rbp
0x18005c532  push    rsi
0x18005c533  push    rdi
0x18005c534  push    r14
0x18005c536  push    r15
0x18005c538  sub     rsp, 40h
0x18005c53c  mov     rax, cs:__security_cookie
0x18005c543  xor     rax, rsp
0x18005c546  mov     [rsp+68h+var_30], rax
0x18005c54b  xor     ebx, ebx
0x18005c54d  mov     [rsp+68h+var_44], 0
0x18005c555  mov     [rsp+68h+var_40], rbx
0x18005c55a  mov     r14, r8
0x18005c55d  mov     r15, rdx
0x18005c560  mov     [rsp+68h+dwNumberOfBytesRead], 0
0x18005c568  test    byte ptr cs:xmmword_180107A60, 20h
0x18005c56f  jz      short loc_18005C585
0x18005c571  lea     edx, [rbx+10h]
0x18005c574  mov     ecx, 405h
0x18005c579  lea     r8, WPP_7e31abdad6703866b17c79b76f86b5b6_Traceguids
0x18005c580  call    WPP_SF_
0x18005c585  mov     ecx, 186A0h; cb
0x18005c58a  mov     [rsp+68h+var_44], ebx
0x18005c58e  call    cs:__imp_CoTaskMemAlloc
0x18005c594  test    rax, rax
0x18005c597  jnz     short loc_18005C5B3
0x18005c599  mov     [rsp+68h+var_44], 34h ; '4'
0x18005c5a1  mov     edi, 8007000Eh
0x18005c5a6  mov     [rsp+68h+var_44], 1B5h
0x18005c5ae  jmp     loc_18005C6A3
0x18005c5b3  xor     edi, edi
0x18005c5b5  mov     ebp, 186A0h
0x18005c5ba  mov     rsi, rax
0x18005c5bd  lea     r9, [rsp+68h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18005c5c2  mov     r8d, ebp; dwNumberOfBytesToRead
0x18005c5c5  mov     rdx, rax; lpBuffer
0x18005c5c8  mov     rcx, r15; hRequest
0x18005c5cb  call    WinHttpReadData
0x18005c5d0  test    eax, eax
0x18005c5d2  jz      loc_18005C66E
0x18005c5d8  mov     eax, [rsp+68h+dwNumberOfBytesRead]
0x18005c5dc  test    eax, eax
0x18005c5de  jz      short loc_18005C63B
0x18005c5e0  add     edi, eax
0x18005c5e2  sub     ebp, eax
0x18005c5e4  jnz     short loc_18005C606
0x18005c5e6  lea     edx, [rdi+186A0h]; cb
0x18005c5ec  mov     [rsp+68h+var_44], ebx
0x18005c5f0  mov     rcx, rsi; pv
0x18005c5f3  call    cs:__imp_CoTaskMemRealloc
0x18005c5f9  test    rax, rax
0x18005c5fc  jz      short loc_18005C615
0x18005c5fe  mov     rsi, rax
0x18005c601  mov     ebp, 186A0h
0x18005c606  cmp     edi, 100000h
0x18005c60c  ja      short loc_18005C62C
0x18005c60e  mov     eax, edi
0x18005c610  add     rax, rsi
0x18005c613  jmp     short loc_18005C5BD
0x18005c615  mov     [rsp+68h+var_44], 64h ; 'd'
0x18005c61d  mov     edi, 8007000Eh
0x18005c622  mov     [rsp+68h+var_44], 1CAh
0x18005c62a  jmp     short loc_18005C695
0x18005c62c  mov     edi, 800C2F87h
0x18005c631  mov     [rsp+68h+var_44], 1CFh
0x18005c639  jmp     short loc_18005C695
0x18005c63b  lea     r8, [rsp+68h+var_40]
0x18005c640  mov     edx, edi; cbMultiByte
0x18005c642  mov     rcx, rsi; lpMultiByteStr
0x18005c645  call    ??$WxNewStringAtoWCch@VWxCoTaskAllocator@@@@YAJPEBDKPEAPEAG@Z; WxNewStringAtoWCch<WxCoTaskAllocator>(char const *,ulong,ushort * *)
0x18005c64a  mov     edi, eax
0x18005c64c  test    eax, eax
0x18005c64e  jns     short loc_18005C65F
0x18005c650  mov     rbx, [rsp+68h+var_40]
0x18005c655  mov     [rsp+68h+var_44], 1D4h
0x18005c65d  jmp     short loc_18005C695
0x18005c65f  mov     rax, [rsp+68h+var_40]
0x18005c664  mov     [r14], rax
0x18005c667  mov     [rsp+68h+var_40], rbx
0x18005c66c  jmp     short loc_18005C695
0x18005c66e  call    cs:__imp_GetLastError
0x18005c674  mov     edi, eax
0x18005c676  test    eax, eax
0x18005c678  jle     short loc_18005C683
0x18005c67a  movzx   edi, ax
0x18005c67d  or      edi, 80070000h
0x18005c683  test    edi, edi
0x18005c685  mov     [rsp+68h+var_44], 1BAh
0x18005c68d  mov     eax, 8000FFFFh
0x18005c692  cmovns  edi, eax
0x18005c695  test    rsi, rsi
0x18005c698  jz      short loc_18005C6A3
0x18005c69a  mov     rcx, rsi; pv
0x18005c69d  call    cs:__imp_CoTaskMemFree
0x18005c6a3  test    byte ptr cs:xmmword_180107A60, 20h
0x18005c6aa  jz      short loc_18005C6C5
0x18005c6ac  mov     edx, 11h
0x18005c6b1  lea     r8, WPP_7e31abdad6703866b17c79b76f86b5b6_Traceguids
0x18005c6b8  mov     ecx, 405h
0x18005c6bd  mov     r9d, edi
0x18005c6c0  call    WPP_SF_d
0x18005c6c5  test    rbx, rbx
0x18005c6c8  jz      short loc_18005C6D4
0x18005c6ca  lea     rcx, [rsp+68h+var_40]; void **
0x18005c6cf  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18005c6d4  mov     eax, edi
0x18005c6d6  mov     rcx, [rsp+68h+var_30]
0x18005c6db  xor     rcx, rsp; StackCookie
0x18005c6de  call    __security_check_cookie
0x18005c6e3  mov     rbx, [rsp+68h+arg_0]
0x18005c6e8  add     rsp, 40h
0x18005c6ec  pop     r15
0x18005c6ee  pop     r14
0x18005c6f0  pop     rdi
0x18005c6f1  pop     rsi
0x18005c6f2  pop     rbp
0x18005c6f3  retn
```
