# CAcidPackageSidCpidKey::Initialize(HSTRING__ *,HSTRING__ *,void *,_GUID const &)

- ea: `0x18005e70c`
- end: `0x18005e8d2`
- name: `?Initialize@CAcidPackageSidCpidKey@@QEAAJPEAUHSTRING__@@0PEAXAEBU_GUID@@@Z`
- size: `454`
- prototype: `int(CAcidPackageSidCpidKey *__hidden this, HSTRING, HSTRING, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180044d70`
- `0x18005e560`

## callees

- `0x18000ce5c`
- `0x1800210f8`
- `0x18005e70c`
- `0x1800b8428`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e843`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e878`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e843`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e878`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e7ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e7ec`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005e819`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005e819`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e7d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e7d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005e74c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005e787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005e74c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005e787`

## string_xrefs

- `0x18005e859`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`
- `0x18005e890`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`
- `0x18005e8b5`: `onecore\com\combase\rpcss\olescm\ServerTableKey.hpp`

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
0x18005e70c  push    rbx
0x18005e70e  push    rbp
0x18005e70f  push    rsi
0x18005e710  push    rdi
0x18005e711  push    r14; int
0x18005e713  sub     rsp, 20h
0x18005e717  lea     rdi, [rcx+8]
0x18005e71b  mov     r14, r9
0x18005e71e  mov     rsi, r8
0x18005e721  mov     rbp, rdx
0x18005e724  mov     rbx, rcx
0x18005e727  test    rdx, rdx
0x18005e72a  jnz     loc_18005E7BD
0x18005e730  mov     rcx, [rdi]; string
0x18005e733  call    cs:__imp_WindowsDeleteString
0x18005e73a  nop     dword ptr [rax+rax+00h]
0x18005e73f  mov     rdx, rdi; newString
0x18005e742  mov     qword ptr [rdi], 0
0x18005e749  mov     rcx, rbp; string
0x18005e74c  call    cs:__imp_WindowsDuplicateString
0x18005e753  nop     dword ptr [rax+rax+00h]
0x18005e758  mov     edi, eax
0x18005e75a  test    eax, eax
0x18005e75c  js      loc_18005E8CB
0x18005e762  lea     rdi, [rbx+10h]
0x18005e766  test    rsi, rsi
0x18005e769  jnz     short loc_18005E7C8
0x18005e76b  mov     rcx, [rdi]; string
0x18005e76e  call    cs:__imp_WindowsDeleteString
0x18005e775  nop     dword ptr [rax+rax+00h]
0x18005e77a  mov     rdx, rdi; newString
0x18005e77d  mov     qword ptr [rdi], 0
0x18005e784  mov     rcx, rsi; string
0x18005e787  call    cs:__imp_WindowsDuplicateString
0x18005e78e  nop     dword ptr [rax+rax+00h]
0x18005e793  mov     edi, eax
0x18005e795  test    eax, eax
0x18005e797  js      loc_18005E8AB
0x18005e79d  test    r14, r14
0x18005e7a0  jnz     short loc_18005E7CF
0x18005e7a2  mov     rax, [rsp+48h+arg_20]
0x18005e7a7  movups  xmm0, xmmword ptr [rax]
0x18005e7aa  xor     eax, eax
0x18005e7ac  movdqu  xmmword ptr [rbx+20h], xmm0
0x18005e7b1  add     rsp, 20h
0x18005e7b5  pop     r14
0x18005e7b7  pop     rdi
0x18005e7b8  pop     rsi
0x18005e7b9  pop     rbp
0x18005e7ba  pop     rbx
0x18005e7bb  retn
0x18005e7bd  cmp     rbp, [rdi]
0x18005e7c0  jnz     loc_18005E730
0x18005e7c6  jmp     short loc_18005E762
0x18005e7c8  cmp     rsi, [rdi]
0x18005e7cb  jnz     short loc_18005E76B
0x18005e7cd  jmp     short loc_18005E79D
0x18005e7cf  mov     rcx, r14; pSid
0x18005e7d2  call    cs:__imp_GetLengthSid
0x18005e7d9  nop     dword ptr [rax+rax+00h]
0x18005e7de  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005e7e5  xor     edx, edx; dwFlags
0x18005e7e7  mov     r8d, eax; dwBytes
0x18005e7ea  mov     esi, eax
0x18005e7ec  call    cs:__imp_HeapAlloc
0x18005e7f3  nop     dword ptr [rax+rax+00h]
0x18005e7f8  mov     rdi, rax
0x18005e7fb  test    rax, rax
0x18005e7fe  jz      loc_18005E88B
0x18005e804  mov     r8d, esi; Size
0x18005e807  xor     edx, edx; Val
0x18005e809  mov     rcx, rax; void *
0x18005e80c  call    memset_0
0x18005e811  mov     r8, r14; pSourceSid
0x18005e814  mov     rdx, rdi; pDestinationSid
0x18005e817  mov     ecx, esi; nDestinationSidLength
0x18005e819  call    cs:__imp_CopySid
0x18005e820  nop     dword ptr [rax+rax+00h]
0x18005e825  test    eax, eax
0x18005e827  jz      short loc_18005E854
0x18005e829  mov     r8, [rbx+18h]; lpMem
0x18005e82d  mov     [rbx+18h], rdi
0x18005e831  test    r8, r8
0x18005e834  jz      loc_18005E7A2
0x18005e83a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005e841  xor     edx, edx; dwFlags
0x18005e843  call    cs:__imp_HeapFree
0x18005e84a  nop     dword ptr [rax+rax+00h]
0x18005e84f  jmp     loc_18005E7A2
0x18005e854  mov     rcx, [rsp+48h]; this
0x18005e859  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x18005e860  mov     edx, 0B8h; void *
0x18005e865  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005e86a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005e871  mov     r8, rdi; lpMem
0x18005e874  xor     edx, edx; dwFlags
0x18005e876  mov     ebx, eax
0x18005e878  call    cs:__imp_HeapFree
0x18005e87f  nop     dword ptr [rax+rax+00h]
0x18005e884  mov     eax, ebx
0x18005e886  jmp     loc_18005E7B1
0x18005e88b  mov     rcx, [rsp+48h]; this
0x18005e890  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x18005e897  mov     ebx, 8007000Eh
0x18005e89c  mov     edx, 0B7h; void *
0x18005e8a1  mov     r9d, ebx; char *
0x18005e8a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e8a9  jmp     short loc_18005E884
0x18005e8ab  mov     edx, 0B1h; void *
0x18005e8b0  mov     rcx, [rsp+48h]; this
0x18005e8b5  lea     r8, aOnecoreComComb_87; "onecore\\com\\combase\\rpcss\\olescm\\S"...
0x18005e8bc  mov     r9d, edi; char *
0x18005e8bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e8c4  mov     eax, edi
0x18005e8c6  jmp     loc_18005E7B1
0x18005e8cb  mov     edx, 0B0h
0x18005e8d0  jmp     short loc_18005E8B0
```
