# ExpandEnvStringsA

- ea: `0x18000419c`
- end: `0x1800042ec`
- name: `ExpandEnvStringsA`
- size: `336`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800038c0`
- `0x180004010`
- `0x180004060`

## callees

- `0x18000419c`
- `0x1800059f8`
- `0x1800060e4`
- `0x180006124`
- `0x180009b40`
- `0x180010250`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000422c`
- `KERNEL32!GetLastError` at `0x18000427c`
- `KERNEL32!GetLastError` at `0x18000422c`
- `KERNEL32!GetLastError` at `0x18000427c`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180004220`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180004272`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180004220`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180004272`

## pseudocode

```c
__int64 __fastcall ExpandEnvStringsA(const WCHAR *a1, unsigned __int16 **a2)
{
  int v3; // ebx
  DWORD v4; // eax
  DWORD v5; // ebx
  signed int LastError; // eax
  CHAR *v7; // rdi
  CHAR *v8; // rcx
  CHAR *v9; // rax
  signed int v10; // eax
  int v11; // eax
  LPCSTR lpSrc; // [rsp+30h] [rbp-828h] BYREF
  void *Block; // [rsp+38h] [rbp-820h] BYREF
  CHAR Dst[1024]; // [rsp+40h] [rbp-818h] BYREF
  char v16[1024]; // [rsp+440h] [rbp-418h] BYREF

  lpSrc = 0;
  if ( !a1 || !*a1 )
    return 0;
  Block = 0;
  v3 = PWSZToPSZ(a1, v16, 1024, (char **)&Block, (char **)&lpSrc);
  if ( v3 >= 0 )
  {
    v4 = ExpandEnvironmentStringsA(lpSrc, Dst, 0x400u);
    v5 = v4;
    if ( !v4 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_19;
    }
    if ( v4 <= 0x400 )
    {
      v7 = 0;
      v8 = Dst;
      goto LABEL_15;
    }
    v9 = (CHAR *)operator new(v4 + 1);
    v7 = v9;
    if ( v9 )
    {
      if ( !ExpandEnvironmentStringsA(lpSrc, v9, v5) )
      {
        v10 = GetLastError();
        v3 = v10;
        if ( v10 > 0 )
          v3 = (unsigned __int16)v10 | 0x80070000;
LABEL_18:
        operator delete(v7);
        goto LABEL_19;
      }
      v8 = v7;
LABEL_15:
      v11 = PSZToBSTR(v8, a2);
      v3 = 0;
      if ( v11 < 0 )
        v3 = v11;
      if ( !v7 )
        goto LABEL_19;
      goto LABEL_18;
    }
    v3 = -2147024882;
  }
LABEL_19:
  if ( Block )
    operator delete(Block);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000419c  mov     [rsp+arg_10], rbx
0x1800041a1  mov     [rsp+arg_18], rsi
0x1800041a6  push    rdi
0x1800041a7  sub     rsp, 850h
0x1800041ae  mov     rax, cs:__security_cookie
0x1800041b5  xor     rax, rsp
0x1800041b8  mov     [rsp+858h+var_18], rax
0x1800041c0  mov     [rsp+858h+lpSrc], 0
0x1800041c9  mov     rsi, rdx
0x1800041cc  test    rcx, rcx
0x1800041cf  jz      loc_1800042C5
0x1800041d5  xor     eax, eax
0x1800041d7  cmp     ax, [rcx]
0x1800041da  jz      loc_1800042C5
0x1800041e0  mov     [rsp+858h+Block], rax
0x1800041e5  lea     r9, [rsp+858h+Block]; char **
0x1800041ea  lea     rax, [rsp+858h+lpSrc]
0x1800041ef  mov     edi, 400h
0x1800041f4  mov     r8d, edi; int
0x1800041f7  mov     [rsp+858h+var_838], rax; char **
0x1800041fc  lea     rdx, [rsp+858h+var_418]; char *
0x180004204  call    ?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z; PWSZToPSZ(ushort const *,char *,long,char * *,char * *)
0x180004209  mov     ebx, eax
0x18000420b  test    eax, eax
0x18000420d  js      loc_1800042B2
0x180004213  mov     rcx, [rsp+858h+lpSrc]; lpSrc
0x180004218  lea     rdx, [rsp+858h+Dst]; lpDst
0x18000421d  mov     r8d, edi; nSize
0x180004220  call    cs:__imp_ExpandEnvironmentStringsA
0x180004226  mov     ebx, eax
0x180004228  test    eax, eax
0x18000422a  jnz     short loc_180004243
0x18000422c  call    cs:__imp_GetLastError
0x180004232  mov     ebx, eax
0x180004234  test    eax, eax
0x180004236  jle     short loc_1800042B2
0x180004238  movzx   ebx, ax
0x18000423b  or      ebx, 80070000h
0x180004241  jmp     short loc_1800042B2
0x180004243  cmp     ebx, edi
0x180004245  ja      short loc_180004250
0x180004247  xor     edi, edi
0x180004249  lea     rcx, [rsp+858h+Dst]
0x18000424e  jmp     short loc_180004296
0x180004250  lea     ecx, [rax+1]; Size
0x180004253  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004258  mov     rdi, rax
0x18000425b  test    rax, rax
0x18000425e  jnz     short loc_180004267
0x180004260  mov     ebx, 8007000Eh
0x180004265  jmp     short loc_1800042B2
0x180004267  mov     rcx, [rsp+858h+lpSrc]; lpSrc
0x18000426c  mov     r8d, ebx; nSize
0x18000426f  mov     rdx, rdi; lpDst
0x180004272  call    cs:__imp_ExpandEnvironmentStringsA
0x180004278  test    eax, eax
0x18000427a  jnz     short loc_180004293
0x18000427c  call    cs:__imp_GetLastError
0x180004282  mov     ebx, eax
0x180004284  test    eax, eax
0x180004286  jle     short loc_1800042AA
0x180004288  movzx   ebx, ax
0x18000428b  or      ebx, 80070000h
0x180004291  jmp     short loc_1800042AA
0x180004293  mov     rcx, rdi; lpMultiByteStr
0x180004296  mov     rdx, rsi; unsigned __int16 **
0x180004299  call    ?PSZToBSTR@@YAJPEBDPEAPEAG@Z; PSZToBSTR(char const *,ushort * *)
0x18000429e  xor     ebx, ebx
0x1800042a0  test    eax, eax
0x1800042a2  cmovs   ebx, eax
0x1800042a5  test    rdi, rdi
0x1800042a8  jz      short loc_1800042B2
0x1800042aa  mov     rcx, rdi; Block
0x1800042ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042b2  mov     rcx, [rsp+858h+Block]; Block
0x1800042b7  test    rcx, rcx
0x1800042ba  jz      short loc_1800042C1
0x1800042bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042c1  mov     eax, ebx
0x1800042c3  jmp     short loc_1800042C7
0x1800042c5  xor     eax, eax
0x1800042c7  mov     rcx, [rsp+858h+var_18]
0x1800042cf  xor     rcx, rsp; StackCookie
0x1800042d2  call    __security_check_cookie
0x1800042d7  lea     r11, [rsp+858h+var_8]
0x1800042df  mov     rbx, [r11+20h]
0x1800042e3  mov     rsi, [r11+28h]
0x1800042e7  mov     rsp, r11
0x1800042ea  pop     rdi
0x1800042eb  retn
```
