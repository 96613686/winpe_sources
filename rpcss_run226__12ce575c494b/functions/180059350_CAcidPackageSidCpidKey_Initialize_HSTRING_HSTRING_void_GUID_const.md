# CAcidPackageSidCpidKey::Initialize(HSTRING__ *,HSTRING__ *,void *,_GUID const &)

- ea: `0x180059350`
- end: `0x1800594cf`
- name: `?Initialize@CAcidPackageSidCpidKey@@QEAAJPEAUHSTRING__@@0PEAXAEBU_GUID@@@Z`
- size: `383`
- prototype: `int(CAcidPackageSidCpidKey *__hidden this, HSTRING, HSTRING, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a908`
- `0x1800591b0`

## callees

- `0x18001ec28`
- `0x18002ba28`
- `0x180059350`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005944c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005947b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005944c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005947b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059409`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059409`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005942c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005942c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800593f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800593f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800593a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800593a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180059386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800593b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180059386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800593b5`

## string_xrefs

- `0x18005945c`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`
- `0x18005948d`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`
- `0x1800594b2`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`

## pseudocode

```c
__int64 __fastcall CAcidPackageSidCpidKey::Initialize(
        HSTRING *this,
        HSTRING a2,
        HSTRING a3,
        void *a4,
        const struct _GUID *a5)
{
  HSTRING *v5; // rdi
  HRESULT v10; // edi
  HSTRING *v11; // rdi
  __int64 result; // rax
  DWORD LengthSid; // esi
  HSTRING v14; // rax
  HSTRING v15; // rdi
  const char *v16; // r9
  HSTRING v17; // r8
  unsigned int LastError; // ebx
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = this + 1;
  if ( !a2 || a2 != *v5 )
  {
    WindowsDeleteString(*v5);
    *v5 = 0;
    v10 = WindowsDuplicateString(a2, v5);
    if ( v10 < 0 )
    {
      v19 = 176;
      goto LABEL_19;
    }
  }
  v11 = this + 2;
  if ( !a3 || a3 != *v11 )
  {
    WindowsDeleteString(*v11);
    *v11 = 0;
    v10 = WindowsDuplicateString(a3, this + 2);
    if ( v10 < 0 )
    {
      v19 = 177;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\ServerTableKey.hpp",
        (const char *)(unsigned int)v10,
        v20);
      return (unsigned int)v10;
    }
  }
  if ( !a4 )
  {
LABEL_6:
    result = 0;
    *((struct _GUID *)this + 2) = *a5;
    return result;
  }
  LengthSid = GetLengthSid(a4);
  v14 = (HSTRING)HeapAlloc(g_hHeap, 0, LengthSid);
  v15 = v14;
  if ( v14 )
  {
    memset_0(v14, 0, LengthSid);
    if ( CopySid(LengthSid, v15, a4) )
    {
      v17 = this[3];
      this[3] = v15;
      if ( v17 )
        HeapFree(g_hHeap, 0, v17);
      goto LABEL_6;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xB8,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\ServerTableKey.hpp",
                  v16);
    HeapFree(g_hHeap, 0, v15);
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\ServerTableKey.hpp",
      (const char *)0x8007000ELL,
      v20);
  }
  return LastError;
}

```

## disassembly

```asm
0x180059350  push    rbx
0x180059352  push    rbp
0x180059353  push    rsi
0x180059354  push    rdi
0x180059355  push    r14; int
0x180059357  sub     rsp, 20h
0x18005935b  lea     rdi, [rcx+8]
0x18005935f  mov     r14, r9
0x180059362  mov     rsi, r8
0x180059365  mov     rbp, rdx
0x180059368  mov     rbx, rcx
0x18005936b  test    rdx, rdx
0x18005936e  jnz     short loc_1800593E4
0x180059370  mov     rcx, [rdi]; string
0x180059373  call    cs:__imp_WindowsDeleteString
0x180059379  mov     rdx, rdi; newString
0x18005937c  mov     qword ptr [rdi], 0
0x180059383  mov     rcx, rbp; string
0x180059386  call    cs:__imp_WindowsDuplicateString
0x18005938c  mov     edi, eax
0x18005938e  test    eax, eax
0x180059390  js      loc_1800594C8
0x180059396  lea     rdi, [rbx+10h]
0x18005939a  test    rsi, rsi
0x18005939d  jnz     short loc_1800593EB
0x18005939f  mov     rcx, [rdi]; string
0x1800593a2  call    cs:__imp_WindowsDeleteString
0x1800593a8  mov     rdx, rdi; newString
0x1800593ab  mov     qword ptr [rdi], 0
0x1800593b2  mov     rcx, rsi; string
0x1800593b5  call    cs:__imp_WindowsDuplicateString
0x1800593bb  mov     edi, eax
0x1800593bd  test    eax, eax
0x1800593bf  js      loc_1800594A8
0x1800593c5  test    r14, r14
0x1800593c8  jnz     short loc_1800593F2
0x1800593ca  mov     rax, [rsp+48h+arg_20]
0x1800593cf  movups  xmm0, xmmword ptr [rax]
0x1800593d2  xor     eax, eax
0x1800593d4  movdqu  xmmword ptr [rbx+20h], xmm0
0x1800593d9  add     rsp, 20h
0x1800593dd  pop     r14
0x1800593df  pop     rdi
0x1800593e0  pop     rsi
0x1800593e1  pop     rbp
0x1800593e2  pop     rbx
0x1800593e3  retn
0x1800593e4  cmp     rbp, [rdi]
0x1800593e7  jnz     short loc_180059370
0x1800593e9  jmp     short loc_180059396
0x1800593eb  cmp     rsi, [rdi]
0x1800593ee  jnz     short loc_18005939F
0x1800593f0  jmp     short loc_1800593C5
0x1800593f2  mov     rcx, r14; pSid
0x1800593f5  call    cs:__imp_GetLengthSid
0x1800593fb  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180059402  xor     edx, edx; dwFlags
0x180059404  mov     r8d, eax; dwBytes
0x180059407  mov     esi, eax
0x180059409  call    cs:__imp_HeapAlloc
0x18005940f  mov     rdi, rax
0x180059412  test    rax, rax
0x180059415  jz      short loc_180059488
0x180059417  mov     r8d, esi; Size
0x18005941a  xor     edx, edx; Val
0x18005941c  mov     rcx, rax; void *
0x18005941f  call    memset_0
0x180059424  mov     r8, r14; pSourceSid
0x180059427  mov     rdx, rdi; pDestinationSid
0x18005942a  mov     ecx, esi; nDestinationSidLength
0x18005942c  call    cs:__imp_CopySid
0x180059432  test    eax, eax
0x180059434  jz      short loc_180059457
0x180059436  mov     r8, [rbx+18h]; lpMem
0x18005943a  mov     [rbx+18h], rdi
0x18005943e  test    r8, r8
0x180059441  jz      short loc_1800593CA
0x180059443  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005944a  xor     edx, edx; dwFlags
0x18005944c  call    cs:__imp_HeapFree
0x180059452  jmp     loc_1800593CA
0x180059457  mov     rcx, [rsp+48h]; this
0x18005945c  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x180059463  mov     edx, 0B8h; void *
0x180059468  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005946d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180059474  mov     r8, rdi; lpMem
0x180059477  xor     edx, edx; dwFlags
0x180059479  mov     ebx, eax
0x18005947b  call    cs:__imp_HeapFree
0x180059481  mov     eax, ebx
0x180059483  jmp     loc_1800593D9
0x180059488  mov     rcx, [rsp+48h]; this
0x18005948d  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x180059494  mov     ebx, 8007000Eh
0x180059499  mov     edx, 0B7h; void *
0x18005949e  mov     r9d, ebx; char *
0x1800594a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800594a6  jmp     short loc_180059481
0x1800594a8  mov     edx, 0B1h; void *
0x1800594ad  mov     rcx, [rsp+48h]; this
0x1800594b2  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x1800594b9  mov     r9d, edi; char *
0x1800594bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800594c1  mov     eax, edi
0x1800594c3  jmp     loc_1800593D9
0x1800594c8  mov     edx, 0B0h
0x1800594cd  jmp     short loc_1800594AD
```
