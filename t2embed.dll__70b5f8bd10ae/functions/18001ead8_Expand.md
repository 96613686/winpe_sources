# Expand

- ea: `0x18001ead8`
- end: `0x18001ebba`
- name: `Expand`
- size: `226`
- prototype: `__int64 __fastcall(LPSTR lpFileName, LPSTR)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022fcc`

## callees

- `0x18001ead8`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!LZClose` at `0x18001eb68`
- `KERNEL32!LZClose` at `0x18001eba1`
- `KERNEL32!LZClose` at `0x18001eba9`
- `KERNEL32!LZClose` at `0x18001eb68`
- `KERNEL32!LZClose` at `0x18001eba1`
- `KERNEL32!LZClose` at `0x18001eba9`
- `KERNEL32!LZOpenFileA` at `0x18001eb3d`
- `KERNEL32!LZOpenFileA` at `0x18001eb5a`
- `KERNEL32!LZOpenFileA` at `0x18001eb3d`
- `KERNEL32!LZOpenFileA` at `0x18001eb5a`
- `KERNEL32!LZCopy` at `0x18001eb97`
- `KERNEL32!LZCopy` at `0x18001eb97`

## pseudocode

```c
_BOOL8 __fastcall Expand(LPSTR lpFileName, LPSTR a2)
{
  int v4; // edi
  int v5; // eax
  INT v6; // esi
  LONG v8; // ebx
  _OFSTRUCT ReOpenBuf; // [rsp+20h] [rbp-138h] BYREF
  struct _OFSTRUCT v10; // [rsp+B0h] [rbp-A8h] BYREF

  memset_0(&ReOpenBuf, 0, sizeof(ReOpenBuf));
  memset_0(&v10, 0, sizeof(v10));
  if ( !lpFileName )
    return 0;
  if ( !a2 )
    return 0;
  v4 = LZOpenFileA(lpFileName, &ReOpenBuf, 0);
  if ( v4 < 0 )
    return 0;
  v5 = LZOpenFileA(a2, &v10, 0x1000u);
  v6 = v5;
  if ( v5 < 0 )
  {
    LZClose(v4);
    return 0;
  }
  v8 = LZCopy(v4, v5);
  LZClose(v4);
  LZClose(v6);
  return v8 >= 0;
}

```

## disassembly

```asm
0x18001ead8  mov     [rsp+arg_10], rbx
0x18001eadd  mov     [rsp+arg_18], rsi
0x18001eae2  push    rdi
0x18001eae3  sub     rsp, 150h
0x18001eaea  mov     rax, cs:__security_cookie
0x18001eaf1  xor     rax, rsp
0x18001eaf4  mov     [rsp+158h+var_18], rax
0x18001eafc  mov     rbx, rdx
0x18001eaff  mov     rdi, rcx
0x18001eb02  mov     esi, 88h
0x18001eb07  lea     rcx, [rsp+158h+ReOpenBuf]; void *
0x18001eb0c  mov     r8d, esi; Size
0x18001eb0f  xor     edx, edx; Val
0x18001eb11  call    memset_0
0x18001eb16  mov     r8d, esi; Size
0x18001eb19  lea     rcx, [rsp+158h+var_A8]; void *
0x18001eb21  xor     edx, edx; Val
0x18001eb23  call    memset_0
0x18001eb28  test    rdi, rdi
0x18001eb2b  jz      short loc_18001EB6E
0x18001eb2d  test    rbx, rbx
0x18001eb30  jz      short loc_18001EB6E
0x18001eb32  xor     r8d, r8d; wStyle
0x18001eb35  lea     rdx, [rsp+158h+ReOpenBuf]; lpReOpenBuf
0x18001eb3a  mov     rcx, rdi; lpFileName
0x18001eb3d  call    cs:__imp_LZOpenFileA
0x18001eb43  mov     edi, eax
0x18001eb45  test    eax, eax
0x18001eb47  js      short loc_18001EB6E
0x18001eb49  mov     r8d, 1000h; wStyle
0x18001eb4f  lea     rdx, [rsp+158h+var_A8]; lpReOpenBuf
0x18001eb57  mov     rcx, rbx; lpFileName
0x18001eb5a  call    cs:__imp_LZOpenFileA
0x18001eb60  mov     esi, eax
0x18001eb62  mov     ecx, edi; hfSource
0x18001eb64  test    eax, eax
0x18001eb66  jns     short loc_18001EB95
0x18001eb68  call    cs:__imp_LZClose
0x18001eb6e  xor     eax, eax
0x18001eb70  mov     rcx, [rsp+158h+var_18]
0x18001eb78  xor     rcx, rsp; StackCookie
0x18001eb7b  call    __security_check_cookie
0x18001eb80  lea     r11, [rsp+158h+var_8]
0x18001eb88  mov     rbx, [r11+20h]
0x18001eb8c  mov     rsi, [r11+28h]
0x18001eb90  mov     rsp, r11
0x18001eb93  pop     rdi
0x18001eb94  retn
0x18001eb95  mov     edx, esi; hfDest
0x18001eb97  call    cs:__imp_LZCopy
0x18001eb9d  mov     ecx, edi; hFile
0x18001eb9f  mov     ebx, eax
0x18001eba1  call    cs:__imp_LZClose
0x18001eba7  mov     ecx, esi; hFile
0x18001eba9  call    cs:__imp_LZClose
0x18001ebaf  test    ebx, ebx
0x18001ebb1  js      short loc_18001EB6E
0x18001ebb3  mov     eax, 1
0x18001ebb8  jmp     short loc_18001EB70
```
