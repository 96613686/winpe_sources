# VerifyHashAlgIsSHA256OrHigher(wchar_t const *)

- ea: `0x180013358`
- end: `0x1800134ba`
- name: `?VerifyHashAlgIsSHA256OrHigher@@YAJPEB_W@Z`
- size: `354`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011b18`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000a5bc`
- `0x18000a804`
- `0x180013358`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800133fa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013427`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013450`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800133fa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013427`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013450`

## pseudocode

```c
__int64 __fastcall VerifyHashAlgIsSHA256OrHigher(const wchar_t *a1, wchar_t a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  const WCHAR *v4; // rbx
  int lpString2; // [rsp+20h] [rbp-48h]
  void *lpMem; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v8; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  lpMem = 0;
  LODWORD(v8) = 0;
  v2 = StringArrayFromDelimitedString(a1, a2, (wchar_t ***)&lpMem, (unsigned int *)&v8);
  if ( v2 >= 0 )
  {
    if ( (_DWORD)v8 == 2 )
    {
      v4 = (const WCHAR *)*((_QWORD *)lpMem + 1);
      if ( L"SHA256" == v4
        || v4
        && (CompareStringW(0x7Fu, 1u, L"SHA256", -1, v4, -1) == 2
         || L"SHA384" == v4
         || CompareStringW(0x7Fu, 1u, L"SHA384", -1, v4, -1) == 2
         || L"SHA512" == v4
         || CompareStringW(0x7Fu, 1u, L"SHA512", -1, v4, -1) == 2) )
      {
        v2 = 0;
        goto LABEL_16;
      }
      lpString2 = 0;
      WUTrace(0, 0, 32, 1);
      v3 = 3743;
    }
    else
    {
      v3 = 3733;
    }
    v2 = -2145078525;
  }
  else
  {
    v3 = 3731;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\wutrust\\lib\\trust.cpp",
    (const char *)(unsigned int)v2,
    lpString2);
LABEL_16:
  SusFreePtrArray(lpMem, (unsigned int)v8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180013358  mov     r11, rsp
0x18001335b  mov     [r11+10h], rbx
0x18001335f  push    rsi
0x180013360  sub     rsp, 60h
0x180013364  mov     rax, cs:__security_cookie
0x18001336b  xor     rax, rsp
0x18001336e  mov     [rsp+68h+var_18], rax
0x180013373  lea     r9, [r11-20h]; unsigned int *
0x180013377  mov     qword ptr [r11-28h], 0
0x18001337f  lea     r8, [r11-28h]; wchar_t ***
0x180013383  mov     dword ptr [rsp+68h+var_20], 0
0x18001338b  call    ?StringArrayFromDelimitedString@@YAJPEB_W_WPEAPEAPEA_WPEAK@Z; StringArrayFromDelimitedString(wchar_t const *,wchar_t,wchar_t * * *,ulong *)
0x180013390  mov     ebx, eax
0x180013392  test    eax, eax
0x180013394  jns     short loc_18001339D
0x180013396  mov     edx, 0E93h
0x18001339b  jmp     short loc_1800133AE
0x18001339d  cmp     dword ptr [rsp+68h+var_20], 2
0x1800133a2  jz      short loc_1800133C7
0x1800133a4  mov     edx, 0E95h; void *
0x1800133a9  mov     ebx, 8024B303h
0x1800133ae  mov     rcx, [rsp+68h]; this
0x1800133b3  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x1800133ba  mov     r9d, ebx; char *
0x1800133bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800133c2  jmp     loc_180013492
0x1800133c7  mov     rax, [rsp+68h+lpMem]
0x1800133cc  lea     r8, aSha256; "SHA256"
0x1800133d3  mov     rbx, [rax+8]
0x1800133d7  cmp     r8, rbx
0x1800133da  jz      loc_180013490
0x1800133e0  test    rbx, rbx
0x1800133e3  jz      short loc_18001345B
0x1800133e5  or      esi, 0FFFFFFFFh
0x1800133e8  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800133ec  mov     r9d, esi; cchCount1
0x1800133ef  mov     [rsp+68h+lpString2], rbx; lpString2
0x1800133f4  lea     edx, [rsi+2]; dwCmpFlags
0x1800133f7  lea     ecx, [rdx+7Eh]; Locale
0x1800133fa  call    cs:__imp_CompareStringW
0x180013400  cmp     eax, 2
0x180013403  jz      loc_180013490
0x180013409  lea     r8, aSha384; "SHA384"
0x180013410  cmp     r8, rbx
0x180013413  jz      short loc_180013490
0x180013415  lea     edx, [rsi+2]; dwCmpFlags
0x180013418  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18001341c  lea     ecx, [rdx+7Eh]; Locale
0x18001341f  mov     [rsp+68h+lpString2], rbx; lpString2
0x180013424  mov     r9d, esi; cchCount1
0x180013427  call    cs:__imp_CompareStringW
0x18001342d  cmp     eax, 2
0x180013430  jz      short loc_180013490
0x180013432  lea     r8, aSha512; "SHA512"
0x180013439  cmp     r8, rbx
0x18001343c  jz      short loc_180013490
0x18001343e  lea     edx, [rsi+2]; dwCmpFlags
0x180013441  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180013445  lea     ecx, [rdx+7Eh]; Locale
0x180013448  mov     [rsp+68h+lpString2], rbx; lpString2
0x18001344d  mov     r9d, esi; cchCount1
0x180013450  call    cs:__imp_CompareStringW
0x180013456  cmp     eax, 2
0x180013459  jz      short loc_180013490
0x18001345b  xor     edx, edx
0x18001345d  mov     [rsp+68h+var_38], rbx
0x180013462  lea     rax, aHashAlgorithmI; "Hash Algorithm is lesser than SHA256. A"...
0x180013469  xor     ecx, ecx
0x18001346b  mov     qword ptr [rsp+68h+cchCount2], rax
0x180013470  mov     [rsp+68h+lpString2], 0
0x180013479  lea     r9d, [rdx+1]
0x18001347d  lea     r8d, [rdx+20h]
0x180013481  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180013486  mov     edx, 0E9Fh
0x18001348b  jmp     loc_1800133A9
0x180013490  xor     ebx, ebx
0x180013492  mov     edx, dword ptr [rsp+68h+var_20]; unsigned __int64
0x180013496  mov     rcx, [rsp+68h+lpMem]; lpMem
0x18001349b  call    ?SusFreePtrArray@@YAXPEAX_K@Z; SusFreePtrArray(void *,unsigned __int64)
0x1800134a0  mov     eax, ebx
0x1800134a2  mov     rcx, [rsp+68h+var_18]
0x1800134a7  xor     rcx, rsp; StackCookie
0x1800134aa  call    __security_check_cookie
0x1800134af  mov     rbx, [rsp+68h+arg_8]
0x1800134b4  add     rsp, 60h
0x1800134b8  pop     rsi
0x1800134b9  retn
```
