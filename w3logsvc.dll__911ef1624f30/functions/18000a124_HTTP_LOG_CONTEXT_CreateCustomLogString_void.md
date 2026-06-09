# HTTP_LOG_CONTEXT::CreateCustomLogString(void)

- ea: `0x18000a124`
- end: `0x18000a288`
- name: `?CreateCustomLogString@HTTP_LOG_CONTEXT@@QEAAJXZ`
- size: `356`
- prototype: `__int64 __fastcall(HTTP_LOG_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a57c`

## callees

- `0x180001008`
- `0x18000a124`
- `0x18000e956`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a237`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18000a21a`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18000a21a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a258`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a258`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a17f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a17f`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000a19d`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000a19d`
- `iisutil!?AppendA@STRU@@QEAAJPEBDK@Z` at `0x18000a1f9`
- `iisutil!?AppendA@STRU@@QEAAJPEBDK@Z` at `0x18000a1f9`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_CONTEXT::CreateCustomLogString(HTTP_LOG_CONTEXT *this)
{
  size_t v2; // rdi
  _BYTE *v3; // rsi
  MULTISZ *v4; // rax
  signed int v5; // ebx
  size_t v6; // r14
  char *v7; // rdi
  MULTISZ *v8; // rcx
  signed int LastError; // eax
  _BYTE v11[32]; // [rsp+28h] [rbp-250h] BYREF
  const unsigned __int16 *v12; // [rsp+48h] [rbp-230h]
  int v13; // [rsp+58h] [rbp-220h]
  unsigned __int16 v14[248]; // [rsp+60h] [rbp-218h] BYREF

  v2 = *((char *)this + 932);
  v3 = (char *)this + 933;
  memset_0(v14, 0, 0x1EAu);
  STRU::STRU((STRU *)v11, v14, 0xF5u);
  v4 = (MULTISZ *)operator new(0x38u);
  if ( v4 )
    v4 = MULTISZ::MULTISZ(v4);
  *((_QWORD *)this + 102) = v4;
  if ( v4 )
  {
    v5 = 0;
    v6 = v2;
    if ( *v3 )
    {
      do
      {
        v7 = (char *)memchr_0(v3, 10, v6);
        *v12 = 0;
        v13 = 0;
        v5 = STRU::AppendA((STRU *)v11, v3, (_DWORD)v7 - (_DWORD)v3);
        if ( v5 < 0 )
          break;
        v8 = (MULTISZ *)*((_QWORD *)this + 102);
        if ( *((_DWORD *)v8 + 12) > 0xF5u )
        {
          v5 = -2147024883;
          break;
        }
        if ( !MULTISZ::Append(v8, v12) )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          break;
        }
        v3 = v7 + 1;
      }
      while ( v7[1] );
    }
  }
  else
  {
    v5 = -2147024882;
  }
  STRU::~STRU((STRU *)v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a124  mov     [rsp+arg_8], rbx
0x18000a129  mov     [rsp+arg_10], rbp
0x18000a12e  push    rsi
0x18000a12f  push    rdi
0x18000a130  push    r14
0x18000a132  sub     rsp, 260h
0x18000a139  mov     rax, cs:__security_cookie
0x18000a140  xor     rax, rsp
0x18000a143  mov     [rsp+278h+var_28], rax
0x18000a14b  mov     rbp, rcx
0x18000a14e  movsx   rdi, byte ptr [rcx+3A4h]
0x18000a156  lea     rsi, [rcx+3A5h]
0x18000a15d  xor     edx, edx; Val
0x18000a15f  mov     r8d, 1EAh; Size
0x18000a165  lea     rcx, [rsp+278h+var_218]; void *
0x18000a16a  call    memset_0
0x18000a16f  mov     r8d, 0F5h
0x18000a175  lea     rdx, [rsp+278h+var_218]
0x18000a17a  lea     rcx, [rsp+278h+var_250]
0x18000a17f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000a185  nop
0x18000a186  mov     ecx, 38h ; '8'; Size
0x18000a18b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a190  mov     [rsp+278h+var_258], rax
0x18000a195  test    rax, rax
0x18000a198  jz      short loc_18000A1A4
0x18000a19a  mov     rcx, rax
0x18000a19d  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000a1a3  nop
0x18000a1a4  mov     [rbp+330h], rax
0x18000a1ab  test    rax, rax
0x18000a1ae  jnz     short loc_18000A1BA
0x18000a1b0  mov     ebx, 8007000Eh
0x18000a1b5  jmp     loc_18000A253
0x18000a1ba  xor     ebx, ebx
0x18000a1bc  mov     r14, rdi
0x18000a1bf  cmp     [rsi], bl
0x18000a1c1  jz      loc_18000A253
0x18000a1c7  mov     r8, r14; MaxCount
0x18000a1ca  mov     edx, 0Ah; Val
0x18000a1cf  mov     rcx, rsi; Buf
0x18000a1d2  call    memchr_0
0x18000a1d7  mov     rdi, rax
0x18000a1da  xor     r8d, r8d
0x18000a1dd  mov     rcx, [rsp+278h+var_230]
0x18000a1e2  mov     [rcx], r8w
0x18000a1e6  mov     [rsp+278h+var_220], r8d
0x18000a1eb  mov     r8d, eax
0x18000a1ee  sub     r8d, esi
0x18000a1f1  mov     rdx, rsi
0x18000a1f4  lea     rcx, [rsp+278h+var_250]
0x18000a1f9  call    cs:__imp_?AppendA@STRU@@QEAAJPEBDK@Z; STRU::AppendA(char const *,ulong)
0x18000a1ff  mov     ebx, eax
0x18000a201  test    eax, eax
0x18000a203  js      short loc_18000A253
0x18000a205  mov     rcx, [rbp+330h]
0x18000a20c  cmp     dword ptr [rcx+30h], 0F5h
0x18000a213  ja      short loc_18000A24E
0x18000a215  mov     rdx, [rsp+278h+var_230]
0x18000a21a  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18000a220  test    eax, eax
0x18000a222  jz      short loc_18000A237
0x18000a224  lea     rsi, [rdi+1]
0x18000a228  sub     edi, esi
0x18000a22a  lea     eax, [rdi+1]
0x18000a22d  sub     r14, rax
0x18000a230  cmp     byte ptr [rsi], 0
0x18000a233  jnz     short loc_18000A1C7
0x18000a235  jmp     short loc_18000A253
0x18000a237  call    cs:__imp_GetLastError
0x18000a23d  mov     ebx, eax
0x18000a23f  test    eax, eax
0x18000a241  jle     short loc_18000A253
0x18000a243  movzx   ebx, ax
0x18000a246  or      ebx, 80070000h
0x18000a24c  jmp     short loc_18000A253
0x18000a24e  mov     ebx, 8007000Dh
0x18000a253  lea     rcx, [rsp+278h+var_250]
0x18000a258  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a25e  mov     eax, ebx
0x18000a260  mov     rcx, [rsp+278h+var_28]
0x18000a268  xor     rcx, rsp; StackCookie
0x18000a26b  call    __security_check_cookie
0x18000a270  lea     r11, [rsp+278h+var_18]
0x18000a278  mov     rbx, [r11+28h]
0x18000a27c  mov     rbp, [r11+30h]
0x18000a280  mov     rsp, r11
0x18000a283  pop     r14
0x18000a285  pop     rdi
0x18000a286  pop     rsi
0x18000a287  retn
```
