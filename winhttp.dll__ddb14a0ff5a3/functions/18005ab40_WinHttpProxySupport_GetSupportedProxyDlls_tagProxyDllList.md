# WinHttpProxySupport::GetSupportedProxyDlls(tagProxyDllList * *)

- ea: `0x18005ab40`
- end: `0x18005ad7b`
- name: `?GetSupportedProxyDlls@WinHttpProxySupport@@UEAAJPEAPEAUtagProxyDllList@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(WinHttpProxySupport *__hidden this, struct tagProxyDllList **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009070`
- `0x18000bfd0`
- `0x18005ab40`
- `0x18005ad90`
- `0x18005af10`
- `0x18005fe50`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005abb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005abe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005abb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005abe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005acbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005aceb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005acbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005aceb`

## string_xrefs

- `0x18005ac48`: `application/x-ns-proxy-autoconfig`

## pseudocode

```c
__int64 __fastcall WinHttpProxySupport::GetSupportedProxyDlls(WinHttpProxySupport *this, struct tagProxyDllList **a2)
{
  void *v3; // rdi
  STRSAFE_LPWSTR v4; // rbx
  int v5; // r14d
  _OWORD *v6; // rax
  _OWORD *v7; // r12
  unsigned int v8; // esi
  LPVOID v9; // r15
  int v10; // eax
  STRSAFE_LPWSTR v11; // r10
  void *v12; // rax
  STRSAFE_LPWSTR pszDest; // [rsp+20h] [rbp-20h] BYREF
  int v15; // [rsp+2Ch] [rbp-14h]
  void *v16; // [rsp+30h] [rbp-10h] BYREF
  void *v17; // [rsp+38h] [rbp-8h] BYREF

  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 56, WPP_7e31abdad6703866b17c79b76f86b5b6_Traceguids);
  v3 = 0;
  HIDWORD(pszDest) = 0;
  v4 = 0;
  v16 = 0;
  v17 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    HIDWORD(pszDest) = 1714;
LABEL_24:
    v8 = v5;
    goto LABEL_25;
  }
  *a2 = 0;
  v15 = 0;
  v6 = CoTaskMemAlloc(0x10u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = -2147024882;
    v15 = 76;
    v5 = -2147024882;
    HIDWORD(pszDest) = 1717;
    goto LABEL_25;
  }
  *v6 = 0;
  v15 = 0;
  v9 = CoTaskMemAlloc(0x18u);
  if ( v9 )
  {
    *(_OWORD *)v9 = 0;
    *((_QWORD *)v9 + 2) = 0;
    v15 = 0;
    pszDest = 0;
    v17 = 0;
    v10 = WxAllocZero<unsigned short,WxCoTaskAllocator>(0x44u, &pszDest);
    v11 = pszDest;
    v5 = v10;
    if ( v10 >= 0 )
    {
      v5 = StringCchCopyW(pszDest, 0x22u, L"application/x-ns-proxy-autoconfig");
      if ( v5 >= 0 )
      {
        v4 = v11;
        v11 = 0;
        pszDest = 0;
        v17 = v4;
      }
      else
      {
        v15 = 548;
      }
    }
    else
    {
      v15 = 544;
    }
    if ( v11 )
      WxCoTaskAllocator::Free((void **)&pszDest);
    if ( v5 >= 0 )
    {
      v5 = WxNewStringW<WxCoTaskAllocator>(L".dat;.js;.pac;.jvs", &v16);
      if ( v5 >= 0 )
      {
        v12 = v16;
        *((_QWORD *)v9 + 2) = v4;
        v4 = 0;
        *((_QWORD *)v9 + 1) = v12;
        *(_DWORD *)v9 = 0;
        v17 = 0;
        v16 = 0;
        *((_DWORD *)v9 + 1) = 1;
        *(_DWORD *)v7 = 1;
        *((_QWORD *)v7 + 1) = v9;
        *a2 = (struct tagProxyDllList *)v7;
        goto LABEL_24;
      }
      v3 = v16;
      HIDWORD(pszDest) = 1723;
    }
    else
    {
      HIDWORD(pszDest) = 1721;
    }
    v8 = v5;
  }
  else
  {
    v8 = -2147024882;
    v15 = 76;
    v5 = -2147024882;
    HIDWORD(pszDest) = 1719;
  }
  CoTaskMemFree(v7);
  if ( v9 )
  {
    WxCoTaskMemFree<unsigned short>((void **)v9 + 1);
    WxCoTaskMemFree<unsigned short>((void **)v9 + 2);
    *(_OWORD *)v9 = 0;
    *((_QWORD *)v9 + 2) = 0;
    CoTaskMemFree(v9);
  }
LABEL_25:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 57, WPP_7e31abdad6703866b17c79b76f86b5b6_Traceguids, (unsigned int)v5, pszDest);
  if ( v4 )
    WxCoTaskAllocator::Free(&v17);
  if ( v3 )
    WxCoTaskAllocator::Free(&v16);
  return v8;
}

```

## disassembly

```asm
0x18005ab40  mov     [rsp-28h+arg_0], rbx
0x18005ab45  mov     [rsp-28h+arg_10], rsi
0x18005ab4a  push    rbp
0x18005ab4b  push    rdi
0x18005ab4c  push    r12
0x18005ab4e  push    r14
0x18005ab50  push    r15
0x18005ab52  mov     rbp, rsp
0x18005ab55  sub     rsp, 40h
0x18005ab59  mov     rsi, rdx
0x18005ab5c  test    byte ptr cs:xmmword_180107A60, 20h
0x18005ab63  jz      short loc_18005AB7B
0x18005ab65  mov     edx, 38h ; '8'
0x18005ab6a  lea     r8, WPP_7e31abdad6703866b17c79b76f86b5b6_Traceguids
0x18005ab71  mov     ecx, 405h
0x18005ab76  call    WPP_SF_
0x18005ab7b  xor     edi, edi
0x18005ab7d  mov     dword ptr [rbp+pszDest+4], 0
0x18005ab84  xor     ebx, ebx
0x18005ab86  mov     [rbp+var_10], rdi
0x18005ab8a  mov     [rbp+var_8], rbx
0x18005ab8e  test    rsi, rsi
0x18005ab91  jnz     short loc_18005ABA5
0x18005ab93  mov     r14d, 80070057h
0x18005ab99  mov     dword ptr [rbp+pszDest+4], 6B2h
0x18005aba0  jmp     loc_18005AD1F
0x18005aba5  mov     [rsi], rbx
0x18005aba8  mov     ecx, 10h; cb
0x18005abad  mov     [rbp+var_14], ebx
0x18005abb0  call    cs:__imp_CoTaskMemAlloc
0x18005abb6  mov     r12, rax
0x18005abb9  test    rax, rax
0x18005abbc  jnz     short loc_18005ABD9
0x18005abbe  mov     esi, 8007000Eh
0x18005abc3  mov     [rbp+var_14], 4Ch ; 'L'
0x18005abca  mov     r14d, esi
0x18005abcd  mov     dword ptr [rbp+pszDest+4], 6B5h
0x18005abd4  jmp     loc_18005AD22
0x18005abd9  xorps   xmm0, xmm0
0x18005abdc  movups  xmmword ptr [rax], xmm0
0x18005abdf  mov     ecx, 18h; cb
0x18005abe4  mov     [rbp+var_14], ebx
0x18005abe7  call    cs:__imp_CoTaskMemAlloc
0x18005abed  mov     r15, rax
0x18005abf0  test    rax, rax
0x18005abf3  jnz     short loc_18005AC10
0x18005abf5  mov     esi, 8007000Eh
0x18005abfa  mov     [rbp+var_14], 4Ch ; 'L'
0x18005ac01  mov     r14d, esi
0x18005ac04  mov     dword ptr [rbp+pszDest+4], 6B7h
0x18005ac0b  jmp     loc_18005ACBB
0x18005ac10  xorps   xmm0, xmm0
0x18005ac13  xor     eax, eax
0x18005ac15  movups  xmmword ptr [r15], xmm0
0x18005ac19  mov     [r15+10h], rax
0x18005ac1d  lea     rdx, [rbp+pszDest]
0x18005ac21  mov     [rbp+var_14], eax
0x18005ac24  lea     ecx, [rax+44h]; Size
0x18005ac27  mov     [rbp+pszDest], rax
0x18005ac2b  mov     [rbp+var_8], rbx
0x18005ac2f  call    ??$WxAllocZero@GVWxCoTaskAllocator@@@@YAJKPEAPEAG@Z; WxAllocZero<ushort,WxCoTaskAllocator>(ulong,ushort * *)
0x18005ac34  mov     r10, [rbp+pszDest]
0x18005ac38  mov     r14d, eax
0x18005ac3b  test    eax, eax
0x18005ac3d  jns     short loc_18005AC48
0x18005ac3f  mov     [rbp+var_14], 220h
0x18005ac46  jmp     short loc_18005AC7A
0x18005ac48  lea     r8, aApplicationXNs; "application/x-ns-proxy-autoconfig"
0x18005ac4f  mov     edx, 22h ; '"'; cchDest
0x18005ac54  mov     rcx, r10; pszDest
0x18005ac57  call    StringCchCopyW
0x18005ac5c  mov     r14d, eax
0x18005ac5f  test    eax, eax
0x18005ac61  jns     short loc_18005AC6C
0x18005ac63  mov     [rbp+var_14], 224h
0x18005ac6a  jmp     short loc_18005AC7A
0x18005ac6c  mov     rbx, r10
0x18005ac6f  xor     r10d, r10d
0x18005ac72  mov     [rbp+pszDest], r10
0x18005ac76  mov     [rbp+var_8], rbx
0x18005ac7a  test    r10, r10
0x18005ac7d  jz      short loc_18005AC88
0x18005ac7f  lea     rcx, [rbp+pszDest]; void **
0x18005ac83  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18005ac88  test    r14d, r14d
0x18005ac8b  jns     short loc_18005AC96
0x18005ac8d  mov     dword ptr [rbp+pszDest+4], 6B9h
0x18005ac94  jmp     short loc_18005ACB8
0x18005ac96  lea     rdx, [rbp+var_10]
0x18005ac9a  lea     rcx, aDatJsPacJvs; ".dat;.js;.pac;.jvs"
0x18005aca1  call    ??$WxNewStringW@VWxCoTaskAllocator@@@@YAJPEBGPEAPEAG@Z; WxNewStringW<WxCoTaskAllocator>(ushort const *,ushort * *)
0x18005aca6  mov     r14d, eax
0x18005aca9  test    eax, eax
0x18005acab  jns     short loc_18005ACF3
0x18005acad  mov     rdi, [rbp+var_10]
0x18005acb1  mov     dword ptr [rbp+pszDest+4], 6BBh
0x18005acb8  mov     esi, r14d
0x18005acbb  mov     rcx, r12; pv
0x18005acbe  call    cs:__imp_CoTaskMemFree
0x18005acc4  test    r15, r15
0x18005acc7  jz      short loc_18005AD22
0x18005acc9  lea     rcx, [r15+8]
0x18005accd  call    ??$WxCoTaskMemFree@G@@YAXPEAPEAG@Z; WxCoTaskMemFree<ushort>(ushort * *)
0x18005acd2  lea     rcx, [r15+10h]
0x18005acd6  call    ??$WxCoTaskMemFree@G@@YAXPEAPEAG@Z; WxCoTaskMemFree<ushort>(ushort * *)
0x18005acdb  xorps   xmm0, xmm0
0x18005acde  xor     eax, eax
0x18005ace0  movups  xmmword ptr [r15], xmm0
0x18005ace4  mov     rcx, r15; pv
0x18005ace7  mov     [r15+10h], rax
0x18005aceb  call    cs:__imp_CoTaskMemFree
0x18005acf1  jmp     short loc_18005AD22
0x18005acf3  mov     rax, [rbp+var_10]
0x18005acf7  mov     [r15+10h], rbx
0x18005acfb  xor     ebx, ebx
0x18005acfd  mov     [r15+8], rax
0x18005ad01  mov     [r15], ebx
0x18005ad04  mov     [rbp+var_8], rbx
0x18005ad08  lea     eax, [rbx+1]
0x18005ad0b  mov     [rbp+var_10], rdi
0x18005ad0f  mov     [r15+4], eax
0x18005ad13  mov     [r12], eax
0x18005ad17  mov     [r12+8], r15
0x18005ad1c  mov     [rsi], r12
0x18005ad1f  mov     esi, r14d
0x18005ad22  test    byte ptr cs:xmmword_180107A60, 20h
0x18005ad29  jz      short loc_18005AD44
0x18005ad2b  mov     edx, 39h ; '9'
0x18005ad30  lea     r8, WPP_7e31abdad6703866b17c79b76f86b5b6_Traceguids
0x18005ad37  mov     ecx, 405h
0x18005ad3c  mov     r9d, r14d
0x18005ad3f  call    WPP_SF_d
0x18005ad44  test    rbx, rbx
0x18005ad47  jz      short loc_18005AD52
0x18005ad49  lea     rcx, [rbp+var_8]; void **
0x18005ad4d  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18005ad52  test    rdi, rdi
0x18005ad55  jz      short loc_18005AD60
0x18005ad57  lea     rcx, [rbp+var_10]; void **
0x18005ad5b  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18005ad60  lea     r11, [rsp+40h+var_s0]
0x18005ad65  mov     eax, esi
0x18005ad67  mov     rbx, [r11+30h]
0x18005ad6b  mov     rsi, [r11+40h]
0x18005ad6f  mov     rsp, r11
0x18005ad72  pop     r15
0x18005ad74  pop     r14
0x18005ad76  pop     r12
0x18005ad78  pop     rdi
0x18005ad79  pop     rbp
0x18005ad7a  retn
```
