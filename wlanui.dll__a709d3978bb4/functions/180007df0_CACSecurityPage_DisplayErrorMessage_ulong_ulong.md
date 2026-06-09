# CACSecurityPage::DisplayErrorMessage(ulong,ulong)

- ea: `0x180007df0`
- end: `0x180007f59`
- name: `?DisplayErrorMessage@CACSecurityPage@@AEAAXKK@Z`
- size: `361`
- prototype: `void(CACSecurityPage *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006a34`
- `0x180009380`
- `0x18000b078`

## callees

- `0x180001e26`
- `0x180007df0`
- `0x18001bf0a`
- `0x18001bf40`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180007eb2`
- `KERNEL32!FormatMessageW` at `0x180007eb2`
- `KERNEL32!LocalFree` at `0x180007f2d`
- `KERNEL32!LocalFree` at `0x180007f2d`
- `USER32!MessageBoxW` at `0x180007f1d`
- `USER32!MessageBoxW` at `0x180007f1d`
- `USER32!LoadStringW` at `0x180007e6b`
- `USER32!LoadStringW` at `0x180007e84`
- `USER32!LoadStringW` at `0x180007e6b`
- `USER32!LoadStringW` at `0x180007e84`

## pseudocode

```c
void __fastcall CACSecurityPage::DisplayErrorMessage(HWND *this, UINT a2, DWORD a3)
{
  HINSTANCE v6; // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  WCHAR lpBuffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Caption[256]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[1024]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(Caption, 0, sizeof(Caption));
  v6 = hInstance;
  *(_QWORD *)lpBuffer = 0;
  LoadStringW(hInstance, a2, Buffer, 1024);
  LoadStringW(v6, 0x4394u, Caption, 256);
  if ( a3 )
  {
    if ( FormatMessageW(0x1100u, 0, a3, 0, lpBuffer, 1u, 0) )
    {
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( Buffer[v8] );
      do
        ++v7;
      while ( *(_WORD *)(*(_QWORD *)lpBuffer + 2 * v7) );
      if ( (unsigned __int64)(v8 + v7) < 0x400 )
        memcpy_0(&Buffer[v8], *(const void **)lpBuffer, 2 * v7 + 2);
    }
  }
  MessageBoxW(this[1], Buffer, Caption, 0x10010u);
  if ( *(_QWORD *)lpBuffer )
    LocalFree(*(HLOCAL *)lpBuffer);
}

```

## disassembly

```asm
0x180007df0  mov     [rsp-8+arg_18], rbx
0x180007df5  push    rbp
0x180007df6  push    rsi
0x180007df7  push    rdi
0x180007df8  push    r14
0x180007dfa  push    r15
0x180007dfc  lea     rbp, [rsp-960h]
0x180007e04  sub     rsp, 0A60h
0x180007e0b  mov     rax, cs:__security_cookie
0x180007e12  xor     rax, rsp
0x180007e15  mov     [rbp+980h+var_30], rax
0x180007e1c  mov     esi, r8d
0x180007e1f  mov     edi, edx
0x180007e21  mov     r14, rcx
0x180007e24  xor     edx, edx; Val
0x180007e26  mov     r8d, 800h; Size
0x180007e2c  lea     rcx, [rbp+980h+Buffer]; void *
0x180007e33  call    memset_0
0x180007e38  xor     edx, edx; Val
0x180007e3a  lea     rcx, [rsp+0A80h+Caption]; void *
0x180007e3f  mov     r8d, 200h; Size
0x180007e45  call    memset_0
0x180007e4a  mov     rbx, cs:hInstance
0x180007e51  lea     r8, [rbp+980h+Buffer]; lpBuffer
0x180007e58  xor     r15d, r15d
0x180007e5b  mov     rcx, rbx; hInstance
0x180007e5e  mov     r9d, 400h; cchBufferMax
0x180007e64  mov     qword ptr [rsp+0A80h+var_A40], r15
0x180007e69  mov     edx, edi; uID
0x180007e6b  call    cs:__imp_LoadStringW
0x180007e71  mov     r9d, 100h; cchBufferMax
0x180007e77  lea     r8, [rsp+0A80h+Caption]; lpBuffer
0x180007e7c  mov     edx, 4394h; uID
0x180007e81  mov     rcx, rbx; hInstance
0x180007e84  call    cs:__imp_LoadStringW
0x180007e8a  test    esi, esi
0x180007e8c  jz      short loc_180007F07
0x180007e8e  mov     [rsp+0A80h+Arguments], r15; Arguments
0x180007e93  lea     rax, [rsp+0A80h+var_A40]
0x180007e98  mov     [rsp+0A80h+nSize], 1; nSize
0x180007ea0  xor     r9d, r9d; dwLanguageId
0x180007ea3  mov     r8d, esi; dwMessageId
0x180007ea6  mov     [rsp+0A80h+lpBuffer], rax; lpBuffer
0x180007eab  xor     edx, edx; lpSource
0x180007ead  mov     ecx, 1100h; dwFlags
0x180007eb2  call    cs:__imp_FormatMessageW
0x180007eb8  test    eax, eax
0x180007eba  jz      short loc_180007F07
0x180007ebc  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007ec0  lea     rax, [rbp+980h+Buffer]
0x180007ec7  mov     r9, r8
0x180007eca  inc     r9
0x180007ecd  cmp     [rax+r9*2], r15w
0x180007ed2  jnz     short loc_180007ECA
0x180007ed4  mov     rdx, qword ptr [rsp+0A80h+var_A40]; Src
0x180007ed9  inc     r8
0x180007edc  cmp     [rdx+r8*2], r15w
0x180007ee1  jnz     short loc_180007ED9
0x180007ee3  lea     rax, [r9+r8]
0x180007ee7  cmp     rax, 400h
0x180007eed  jnb     short loc_180007F07
0x180007eef  lea     rcx, [rbp+980h+Buffer]
0x180007ef6  lea     rcx, [rcx+r9*2]; void *
0x180007efa  lea     r8, ds:2[r8*2]; Size
0x180007f02  call    memcpy_0
0x180007f07  mov     rcx, [r14+8]; hWnd
0x180007f0b  lea     r8, [rsp+0A80h+Caption]; lpCaption
0x180007f10  mov     r9d, 10010h; uType
0x180007f16  lea     rdx, [rbp+980h+Buffer]; lpText
0x180007f1d  call    cs:__imp_MessageBoxW
0x180007f23  mov     rcx, qword ptr [rsp+0A80h+var_A40]; hMem
0x180007f28  test    rcx, rcx
0x180007f2b  jz      short loc_180007F33
0x180007f2d  call    cs:__imp_LocalFree
0x180007f33  mov     rcx, [rbp+980h+var_30]
0x180007f3a  xor     rcx, rsp; StackCookie
0x180007f3d  call    __security_check_cookie
0x180007f42  mov     rbx, [rsp+0A80h+arg_18]
0x180007f4a  add     rsp, 0A60h
0x180007f51  pop     r15
0x180007f53  pop     r14
0x180007f55  pop     rdi
0x180007f56  pop     rsi
0x180007f57  pop     rbp
0x180007f58  retn
```
