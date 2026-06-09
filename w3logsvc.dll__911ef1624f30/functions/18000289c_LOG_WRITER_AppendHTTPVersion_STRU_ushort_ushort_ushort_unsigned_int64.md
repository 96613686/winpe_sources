# LOG_WRITER::AppendHTTPVersion(STRU *,ushort,ushort,ushort *,unsigned __int64)

- ea: `0x18000289c`
- end: `0x1800029ba`
- name: `?AppendHTTPVersion@LOG_WRITER@@AEAAJPEAVSTRU@@GGPEAG_K@Z`
- size: `286`
- prototype: `int __fastcall(LOG_WRITER *this, struct STRU *, unsigned __int16, unsigned __int16, wchar_t *Buffer)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003718`

## callees

- `0x18000289c`
- `0x18000e9a0`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800028e6`
- `msvcrt!_itow_s` at `0x18000292f`
- `msvcrt!_itow_s` at `0x1800028e6`
- `msvcrt!_itow_s` at `0x18000292f`
- `msvcrt!wcscpy_s` at `0x180002918`
- `msvcrt!wcscpy_s` at `0x180002918`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002943`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002955`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002978`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002988`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000299c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002943`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002955`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002978`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002988`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000299c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002900`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002900`

## pseudocode

```c
int __fastcall LOG_WRITER::AppendHTTPVersion(
        LOG_WRITER *this,
        struct STRU *a2,
        unsigned __int16 a3,
        unsigned __int16 a4,
        wchar_t *Buffer)
{
  int v7; // esi
  STRU *v8; // rcx
  int result; // eax
  errno_t v10; // eax
  wchar_t Destination[4]; // [rsp+20h] [rbp-48h] BYREF
  int v12; // [rsp+28h] [rbp-40h]
  __int16 v13; // [rsp+2Ch] [rbp-3Ch]

  v7 = a4;
  *(_QWORD *)Destination = 0;
  v12 = 0;
  v13 = 0;
  if ( _itow_s(a3, Buffer, 0x16u, 10) || wcscpy_s(Destination, 7u, Buffer) )
  {
    v8 = a2;
    return STRU::Append(v8, L"- ", 2u);
  }
  v10 = _itow_s(v7, Buffer, 0x16u, 10);
  v8 = a2;
  if ( v10 )
    return STRU::Append(v8, L"- ", 2u);
  result = STRU::Append(a2, L"HTTP/");
  if ( result >= 0 )
  {
    result = STRU::Append(a2, Destination);
    if ( result >= 0 )
    {
      if ( a3 == 2 && !(_WORD)v7 )
        return STRU::Append(a2, L" ");
      result = STRU::Append(a2, L".");
      if ( result >= 0 )
      {
        result = STRU::Append(a2, Buffer);
        if ( result >= 0 )
          return STRU::Append(a2, L" ");
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000289c  push    rbx
0x18000289e  push    rbp
0x18000289f  push    rsi
0x1800028a0  push    rdi
0x1800028a1  push    r14
0x1800028a3  sub     rsp, 40h
0x1800028a7  mov     rax, cs:__security_cookie
0x1800028ae  xor     rax, rsp
0x1800028b1  mov     [rsp+68h+var_38], rax
0x1800028b6  mov     rdi, [rsp+68h+Buffer]
0x1800028be  xor     eax, eax
0x1800028c0  movzx   ebp, r8w
0x1800028c4  mov     rbx, rdx
0x1800028c7  movzx   esi, r9w
0x1800028cb  mov     ecx, ebp; Value
0x1800028cd  mov     rdx, rdi; Buffer
0x1800028d0  mov     qword ptr [rsp+68h+Destination], rax
0x1800028d5  lea     r9d, [rax+0Ah]; Radix
0x1800028d9  mov     [rsp+68h+var_40], eax
0x1800028dd  lea     r8d, [rax+16h]; BufferCount
0x1800028e1  mov     [rsp+68h+var_3C], ax
0x1800028e6  call    cs:__imp__itow_s
0x1800028ec  test    eax, eax
0x1800028ee  jz      short loc_18000290B
0x1800028f0  mov     rcx, rbx
0x1800028f3  lea     rdx, asc_180012130; "- "
0x1800028fa  mov     r8d, 2
0x180002900  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002906  jmp     loc_1800029A2
0x18000290b  mov     r8, rdi; Source
0x18000290e  lea     rcx, [rsp+68h+Destination]; Destination
0x180002913  mov     edx, 7; SizeInWords
0x180002918  call    cs:__imp_wcscpy_s
0x18000291e  test    eax, eax
0x180002920  jnz     short loc_1800028F0
0x180002922  mov     ecx, esi; Value
0x180002924  lea     r9d, [rax+0Ah]; Radix
0x180002928  lea     r8d, [rax+16h]; BufferCount
0x18000292c  mov     rdx, rdi; Buffer
0x18000292f  call    cs:__imp__itow_s
0x180002935  mov     rcx, rbx
0x180002938  test    eax, eax
0x18000293a  jnz     short loc_1800028F3
0x18000293c  lea     rdx, aHttp; "HTTP/"
0x180002943  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002949  test    eax, eax
0x18000294b  js      short loc_1800029A2
0x18000294d  lea     rdx, [rsp+68h+Destination]
0x180002952  mov     rcx, rbx
0x180002955  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000295b  test    eax, eax
0x18000295d  js      short loc_1800029A2
0x18000295f  mov     eax, 2
0x180002964  cmp     bp, ax
0x180002967  jnz     short loc_18000296E
0x180002969  test    si, si
0x18000296c  jz      short loc_180002992
0x18000296e  lea     rdx, asc_1800121F4; "."
0x180002975  mov     rcx, rbx
0x180002978  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000297e  test    eax, eax
0x180002980  js      short loc_1800029A2
0x180002982  mov     rdx, rdi
0x180002985  mov     rcx, rbx
0x180002988  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000298e  test    eax, eax
0x180002990  js      short loc_1800029A2
0x180002992  lea     rdx, asc_180012138; " "
0x180002999  mov     rcx, rbx
0x18000299c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800029a2  mov     rcx, [rsp+68h+var_38]
0x1800029a7  xor     rcx, rsp; StackCookie
0x1800029aa  call    __security_check_cookie
0x1800029af  add     rsp, 40h
0x1800029b3  pop     r14
0x1800029b5  pop     rdi
0x1800029b6  pop     rsi
0x1800029b7  pop     rbp
0x1800029b8  pop     rbx
0x1800029b9  retn
```
