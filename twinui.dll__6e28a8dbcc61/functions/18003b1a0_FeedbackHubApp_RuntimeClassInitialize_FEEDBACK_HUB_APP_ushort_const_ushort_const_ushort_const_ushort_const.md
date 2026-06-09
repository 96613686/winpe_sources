# FeedbackHubApp::RuntimeClassInitialize(FEEDBACK_HUB_APP,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18003b1a0`
- end: `0x18003b2f4`
- name: `?RuntimeClassInitialize@FeedbackHubApp@@QEAAJW4FEEDBACK_HUB_APP@@PEBG111@Z`
- size: `340`
- prototype: `int __high(enum FEEDBACK_HUB_APP, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800fe6e8`
- `0x1800fe810`

## callees

- `0x18003b1a0`
- `0x18003c5e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b20b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b20b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b1e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b25a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b2b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b1e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b25a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b2b9`

## pseudocode

```c
__int64 __fastcall FeedbackHubApp::RuntimeClassInitialize(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const WCHAR *sourceString,
        const WCHAR *a6)
{
  __int64 v6; // rbx
  __int64 v7; // rdi
  HSTRING *v8; // r14
  HRESULT String; // edi
  HSTRING *v13; // r14
  __int64 v14; // rdi
  HSTRING *v15; // r14
  __int64 v16; // rdi
  __int64 v17; // rdx
  HRESULT v19; // eax
  unsigned int v20; // ebx
  int v21; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = -1;
  *(_DWORD *)(a1 + 16) = a2;
  v7 = -1;
  v8 = (HSTRING *)(a1 + 24);
  do
    ++v7;
  while ( a3[v7] );
  WindowsDeleteString(*v8);
  *v8 = 0;
  String = WindowsCreateString(a3, v7, v8);
  if ( String < 0 )
  {
    v17 = 34;
    goto LABEL_11;
  }
  v13 = (HSTRING *)(a1 + 32);
  v14 = -1;
  do
    ++v14;
  while ( a4[v14] );
  WindowsDeleteString(*v13);
  *v13 = 0;
  String = WindowsCreateString(a4, v14, (HSTRING *)(a1 + 32));
  if ( String < 0 )
  {
    v17 = 35;
    goto LABEL_11;
  }
  v15 = (HSTRING *)(a1 + 40);
  v16 = -1;
  do
    ++v16;
  while ( sourceString[v16] );
  WindowsDeleteString(*v15);
  *v15 = 0;
  String = WindowsCreateString(sourceString, v16, (HSTRING *)(a1 + 40));
  if ( String < 0 )
  {
    v17 = 36;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"shell\\twinui\\feedback\\lib\\FeedbackHubApp.h",
      (const char *)(unsigned int)String,
      v21);
    return (unsigned int)String;
  }
  do
    ++v6;
  while ( a6[v6] );
  WindowsDeleteString(*(HSTRING *)(a1 + 48));
  *(_QWORD *)(a1 + 48) = 0;
  v19 = WindowsCreateString(a6, v6, (HSTRING *)(a1 + 48));
  v20 = v19;
  if ( v19 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25,
    (unsigned int)"shell\\twinui\\feedback\\lib\\FeedbackHubApp.h",
    (const char *)(unsigned int)v19,
    v21);
  return v20;
}

```

## disassembly

```asm
0x18003b1a0  push    rbx
0x18003b1a2  push    rbp
0x18003b1a3  push    rsi
0x18003b1a4  push    rdi
0x18003b1a5  push    r12
0x18003b1a7  push    r14
0x18003b1a9  push    r15; int
0x18003b1ab  sub     rsp, 20h
0x18003b1af  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003b1b3  mov     [rcx+10h], edx
0x18003b1b6  mov     rdi, rbx
0x18003b1b9  lea     r14, [rcx+18h]
0x18003b1bd  xor     r12d, r12d
0x18003b1c0  mov     r15, r9
0x18003b1c3  mov     rbp, r8
0x18003b1c6  mov     rsi, rcx
0x18003b1c9  inc     rdi
0x18003b1cc  cmp     [r8+rdi*2], r12w
0x18003b1d1  jnz     short loc_18003B1C9
0x18003b1d3  mov     rcx, [r14]; string
0x18003b1d6  call    cs:__imp_WindowsDeleteString
0x18003b1dc  mov     r8, r14; string
0x18003b1df  mov     [r14], r12
0x18003b1e2  mov     edx, edi; length
0x18003b1e4  mov     rcx, rbp; sourceString
0x18003b1e7  call    cs:__imp_WindowsCreateString
0x18003b1ed  mov     edi, eax
0x18003b1ef  test    eax, eax
0x18003b1f1  js      loc_18003B2C9
0x18003b1f7  lea     r14, [rsi+20h]
0x18003b1fb  mov     rdi, rbx
0x18003b1fe  inc     rdi
0x18003b201  cmp     [r15+rdi*2], r12w
0x18003b206  jnz     short loc_18003B1FE
0x18003b208  mov     rcx, [r14]; string
0x18003b20b  call    cs:__imp_WindowsDeleteString
0x18003b211  mov     r8, r14; string
0x18003b214  mov     [r14], r12
0x18003b217  mov     edx, edi; length
0x18003b219  mov     rcx, r15; sourceString
0x18003b21c  call    cs:__imp_WindowsCreateString
0x18003b222  mov     edi, eax
0x18003b224  test    eax, eax
0x18003b226  js      loc_18003B2D0
0x18003b22c  mov     rbp, [rsp+58h+sourceString]
0x18003b234  lea     r14, [rsi+28h]
0x18003b238  mov     rdi, rbx
0x18003b23b  inc     rdi
0x18003b23e  cmp     [rbp+rdi*2+0], r12w
0x18003b244  jnz     short loc_18003B23B
0x18003b246  mov     rcx, [r14]; string
0x18003b249  call    cs:__imp_WindowsDeleteString
0x18003b24f  mov     r8, r14; string
0x18003b252  mov     [r14], r12
0x18003b255  mov     edx, edi; length
0x18003b257  mov     rcx, rbp; sourceString
0x18003b25a  call    cs:__imp_WindowsCreateString
0x18003b260  mov     edi, eax
0x18003b262  test    eax, eax
0x18003b264  jns     short loc_18003B290
0x18003b266  mov     edx, 24h ; '$'; void *
0x18003b26b  mov     rcx, [rsp+58h]; this
0x18003b270  lea     r8, aShellTwinuiFee_3; "shell\\twinui\\feedback\\lib\\FeedbackH"...
0x18003b277  mov     r9d, edi; char *
0x18003b27a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b27f  mov     eax, edi
0x18003b281  add     rsp, 20h
0x18003b285  pop     r15
0x18003b287  pop     r14
0x18003b289  pop     r12
0x18003b28b  pop     rdi
0x18003b28c  pop     rsi
0x18003b28d  pop     rbp
0x18003b28e  pop     rbx
0x18003b28f  retn
0x18003b290  mov     rdi, [rsp+58h+arg_28]
0x18003b298  inc     rbx
0x18003b29b  cmp     [rdi+rbx*2], r12w
0x18003b2a0  jnz     short loc_18003B298
0x18003b2a2  mov     rcx, [rsi+30h]; string
0x18003b2a6  call    cs:__imp_WindowsDeleteString
0x18003b2ac  lea     r8, [rsi+30h]; string
0x18003b2b0  mov     [rsi+30h], r12
0x18003b2b4  mov     edx, ebx; length
0x18003b2b6  mov     rcx, rdi; sourceString
0x18003b2b9  call    cs:__imp_WindowsCreateString
0x18003b2bf  mov     ebx, eax
0x18003b2c1  test    eax, eax
0x18003b2c3  js      short loc_18003B2D7
0x18003b2c5  xor     eax, eax
0x18003b2c7  jmp     short loc_18003B281
0x18003b2c9  mov     edx, 22h ; '"'
0x18003b2ce  jmp     short loc_18003B26B
0x18003b2d0  mov     edx, 23h ; '#'
0x18003b2d5  jmp     short loc_18003B26B
0x18003b2d7  mov     rcx, [rsp+58h]; this
0x18003b2dc  lea     r8, aShellTwinuiFee_3; "shell\\twinui\\feedback\\lib\\FeedbackH"...
0x18003b2e3  mov     r9d, ebx; char *
0x18003b2e6  mov     edx, 25h ; '%'; void *
0x18003b2eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b2f0  mov     eax, ebx
0x18003b2f2  jmp     short loc_18003B281
```
