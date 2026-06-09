# LOG_WRITER::AppendSanitizedStringOrHyphen(STRU *,char *,ulong,char,int)

- ea: `0x180002c28`
- end: `0x180002d2f`
- name: `?AppendSanitizedStringOrHyphen@LOG_WRITER@@AEAAJPEAVSTRU@@PEADKDH@Z`
- size: `263`
- prototype: `__int64 __fastcall(LOG_WRITER *this, struct STRU *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003718`

## callees

- `0x180002c28`
- `0x18000e9a0`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180002d04`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002d04`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002c69`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002c69`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x180002c82`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x180002c82`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180002cab`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180002cab`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002cca`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002ce1`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002cca`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002ce1`
- `iisutil!?AppendA@STRU@@QEAAJPEBDK@Z` at `0x180002cf8`
- `iisutil!?AppendA@STRU@@QEAAJPEBDK@Z` at `0x180002cf8`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::AppendSanitizedStringOrHyphen(
        LOG_WRITER *this,
        struct STRU *a2,
        char *a3,
        unsigned int a4)
{
  int v7; // ebx
  int v8; // edi
  const char *v9; // rdx
  char v11; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v12[32]; // [rsp+28h] [rbp-41h] BYREF
  const char *v13; // [rsp+48h] [rbp-21h]
  unsigned int v14; // [rsp+58h] [rbp-11h]
  char v15[32]; // [rsp+60h] [rbp-9h] BYREF

  v11 = 43;
  STRA::STRA((STRA *)v12, v15, 0x20u);
  if ( a4 )
  {
    v7 = STRA::Resize((STRA *)v12, a4 + v14 + 2);
    if ( v7 >= 0 )
    {
      v8 = 0;
      while ( 1 )
      {
        if ( (unsigned __int8)*a3 <= 0x20u || (v9 = a3, *a3 == 127) )
          v9 = &v11;
        v7 = STRA::Append((STRA *)v12, v9, 1u);
        if ( v7 < 0 )
          break;
        ++a3;
        if ( ++v8 >= a4 )
          goto LABEL_11;
      }
    }
  }
  else
  {
    v7 = STRA::Append((STRA *)v12, "-");
    if ( v7 >= 0 )
    {
LABEL_11:
      v7 = STRA::Append((STRA *)v12, " ");
      if ( v7 >= 0 )
        v7 = STRU::AppendA(a2, v13, v14);
    }
  }
  STRA::~STRA((STRA *)v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002c28  mov     [rsp-8+arg_0], rbx
0x180002c2d  push    rbp
0x180002c2e  push    rsi
0x180002c2f  push    rdi
0x180002c30  push    r14
0x180002c32  push    r15
0x180002c34  lea     rbp, [rsp-27h]
0x180002c39  sub     rsp, 90h
0x180002c40  mov     rax, cs:__security_cookie
0x180002c47  xor     rax, rsp
0x180002c4a  mov     [rbp+47h+var_30], rax
0x180002c4e  mov     r14d, r9d
0x180002c51  mov     rsi, r8
0x180002c54  mov     r15, rdx
0x180002c57  mov     [rbp+47h+var_90], 2Bh ; '+'
0x180002c5b  mov     r8d, 20h ; ' '
0x180002c61  lea     rdx, [rbp+47h+var_50]
0x180002c65  lea     rcx, [rbp+47h+var_88]
0x180002c69  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002c6f  nop
0x180002c70  lea     rcx, [rbp+47h+var_88]
0x180002c74  test    r14d, r14d
0x180002c77  jz      short loc_180002CC3
0x180002c79  mov     edx, [rbp+47h+var_58]
0x180002c7c  add     edx, 2
0x180002c7f  add     edx, r14d
0x180002c82  call    cs:__imp_?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x180002c88  mov     ebx, eax
0x180002c8a  test    eax, eax
0x180002c8c  js      short loc_180002D00
0x180002c8e  xor     edi, edi
0x180002c90  cmp     byte ptr [rsi], 20h ; ' '
0x180002c93  jbe     short loc_180002C9D
0x180002c95  cmp     byte ptr [rsi], 7Fh
0x180002c98  mov     rdx, rsi
0x180002c9b  jnz     short loc_180002CA1
0x180002c9d  lea     rdx, [rbp+47h+var_90]
0x180002ca1  mov     r8d, 1
0x180002ca7  lea     rcx, [rbp+47h+var_88]
0x180002cab  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180002cb1  mov     ebx, eax
0x180002cb3  test    eax, eax
0x180002cb5  js      short loc_180002D00
0x180002cb7  inc     rsi
0x180002cba  inc     edi
0x180002cbc  cmp     edi, r14d
0x180002cbf  jb      short loc_180002C90
0x180002cc1  jmp     short loc_180002CD6
0x180002cc3  lea     rdx, asc_180012088; "-"
0x180002cca  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180002cd0  mov     ebx, eax
0x180002cd2  test    eax, eax
0x180002cd4  js      short loc_180002D00
0x180002cd6  lea     rdx, asc_1800121E4; " "
0x180002cdd  lea     rcx, [rbp+47h+var_88]
0x180002ce1  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180002ce7  mov     ebx, eax
0x180002ce9  test    eax, eax
0x180002ceb  js      short loc_180002D00
0x180002ced  mov     r8d, [rbp+47h+var_58]
0x180002cf1  mov     rdx, [rbp+47h+var_68]
0x180002cf5  mov     rcx, r15
0x180002cf8  call    cs:__imp_?AppendA@STRU@@QEAAJPEBDK@Z; STRU::AppendA(char const *,ulong)
0x180002cfe  mov     ebx, eax
0x180002d00  lea     rcx, [rbp+47h+var_88]
0x180002d04  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002d0a  mov     eax, ebx
0x180002d0c  mov     rcx, [rbp+47h+var_30]
0x180002d10  xor     rcx, rsp; StackCookie
0x180002d13  call    __security_check_cookie
0x180002d18  mov     rbx, [rsp+0B0h+arg_0]
0x180002d20  add     rsp, 90h
0x180002d27  pop     r15
0x180002d29  pop     r14
0x180002d2b  pop     rdi
0x180002d2c  pop     rsi
0x180002d2d  pop     rbp
0x180002d2e  retn
```
