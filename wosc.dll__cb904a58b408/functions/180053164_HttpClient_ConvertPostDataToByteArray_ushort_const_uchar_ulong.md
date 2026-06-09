# HttpClient::ConvertPostDataToByteArray(ushort const *,uchar * *,ulong *)

- ea: `0x180053164`
- end: `0x180053251`
- name: `?ConvertPostDataToByteArray@HttpClient@@CAJPEBGPEAPEAEPEAK@Z`
- size: `237`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053ac0`

## callees

- `0x18000e5ac`
- `0x180031ae0`
- `0x180053164`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800531e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800531e8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800531b0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180053236`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800531b0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180053236`

## string_xrefs

- `0x1800531cd`: `onecore\base\flighting\common\httpclient\httpclient.cpp`

## pseudocode

```c
__int64 __fastcall HttpClient::ConvertPostDataToByteArray(LPCWCH lpWideCharStr, CHAR **a2, unsigned int *a3)
{
  int v6; // eax
  __int64 cbMultiByte; // rdi
  int Error; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  CHAR *v11; // rax
  CHAR *v12; // rbx
  CHAR *i; // rdx
  int lpMultiByteStr; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a3 = 0;
  v6 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( v6 )
  {
    v11 = (CHAR *)CoTaskMemAlloc(v6);
    v12 = v11;
    if ( v11 )
    {
      for ( i = &v11[cbMultiByte]; v11 != i; ++v11 )
        *v11 = 0;
    }
    WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, v12, cbMultiByte, 0, 0);
    *a2 = v12;
    result = 0;
    *a3 = cbMultiByte;
  }
  else
  {
    Error = ResultFromKnownLastError();
    v9 = Error;
    if ( Error < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x191,
        (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
        (const char *)(unsigned int)Error,
        lpMultiByteStr);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180053164  mov     rax, rsp
0x180053167  push    rbx
0x180053168  push    rbp
0x180053169  push    rsi
0x18005316a  push    rdi
0x18005316b  push    r14
0x18005316d  push    r15
0x18005316f  sub     rsp, 48h
0x180053173  mov     qword ptr [rax-40h], 0
0x18005317b  mov     r14, r8
0x18005317e  mov     qword ptr [rax-48h], 0
0x180053186  mov     r15, rdx
0x180053189  mov     dword ptr [r8], 0
0x180053190  mov     rbp, rcx
0x180053193  mov     r8, rcx; lpWideCharStr
0x180053196  mov     dword ptr [rax-50h], 0
0x18005319d  mov     ecx, 0FDE9h; CodePage
0x1800531a2  mov     qword ptr [rax-58h], 0
0x1800531aa  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800531ae  xor     edx, edx; dwFlags
0x1800531b0  call    cs:__imp_WideCharToMultiByte
0x1800531b6  movsxd  rdi, eax
0x1800531b9  test    eax, eax
0x1800531bb  jnz     short loc_1800531E5
0x1800531bd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800531c2  mov     ebx, eax
0x1800531c4  test    eax, eax
0x1800531c6  jns     short loc_1800531E1
0x1800531c8  mov     rcx, [rsp+78h]; this
0x1800531cd  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x1800531d4  mov     r9d, eax; char *
0x1800531d7  mov     edx, 191h; void *
0x1800531dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800531e1  mov     eax, ebx
0x1800531e3  jmp     short loc_180053244
0x1800531e5  mov     rcx, rdi; cb
0x1800531e8  call    cs:__imp_CoTaskMemAlloc
0x1800531ee  mov     rbx, rax
0x1800531f1  test    rax, rax
0x1800531f4  jz      short loc_18005320D
0x1800531f6  lea     rdx, [rdi+rax]
0x1800531fa  cmp     rax, rdx
0x1800531fd  jz      short loc_18005320D
0x1800531ff  xor     r8d, r8d
0x180053202  mov     [rax], r8b
0x180053205  inc     rax
0x180053208  cmp     rax, rdx
0x18005320b  jnz     short loc_1800531FF
0x18005320d  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180053216  or      r9d, 0FFFFFFFFh; cchWideChar
0x18005321a  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180053223  mov     r8, rbp; lpWideCharStr
0x180053226  mov     [rsp+78h+cbMultiByte], edi; cbMultiByte
0x18005322a  xor     edx, edx; dwFlags
0x18005322c  mov     ecx, 0FDE9h; CodePage
0x180053231  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x180053236  call    cs:__imp_WideCharToMultiByte
0x18005323c  mov     [r15], rbx
0x18005323f  xor     eax, eax
0x180053241  mov     [r14], edi
0x180053244  add     rsp, 48h
0x180053248  pop     r15
0x18005324a  pop     r14
0x18005324c  pop     rdi
0x18005324d  pop     rsi
0x18005324e  pop     rbp
0x18005324f  pop     rbx
0x180053250  retn
```
