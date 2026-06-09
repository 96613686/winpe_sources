# WPP_RECORDER_SF_sDZDld

- ea: `0x140004448`
- end: `0x140004656`
- name: `WPP_RECORDER_SF_sDZDld`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025220`

## callees

- `0x140004448`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004639`
- `WppRecorder!WppAutoLogTrace` at `0x140004639`

## string_xrefs

- `0x140004484`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140004556`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140004581`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDZDld(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        unsigned __int16 *a8,
        ...)
{
  const wchar_t *v8; // rsi
  const wchar_t *v9; // rbx
  __int64 v11; // rdi
  __int64 v12; // rcx
  const wchar_t *v13; // r8
  const wchar_t *v14; // rdx
  bool v15; // zf
  int v17; // [rsp+20h] [rbp-C8h]
  _DWORD v18[18]; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v19; // [rsp+130h] [rbp+48h] BYREF
  va_list va; // [rsp+130h] [rbp+48h]
  __int64 v21; // [rsp+138h] [rbp+50h] BYREF
  va_list va1; // [rsp+138h] [rbp+50h]
  va_list va2; // [rsp+140h] [rbp+58h] BYREF

  va_start(va2, a8);
  va_start(va1, a8);
  va_start(va, a8);
  v19 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v21 = va_arg(va2, _QWORD);
  v8 = L"NULL";
  v9 = a8;
  v18[0] = 2825;
  v11 = 8;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    goto LABEL_11;
  if ( !a8 )
  {
    v12 = 8;
    goto LABEL_7;
  }
  v12 = *a8;
  if ( !*a8 )
  {
LABEL_7:
    v13 = L"NULL";
    goto LABEL_8;
  }
  v13 = (const wchar_t *)*((_QWORD *)a8 + 1);
LABEL_8:
  v14 = a8;
  if ( !a8 )
    v14 = L"\b";
  ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, const char *, __int64, _DWORD *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
    WPP_GLOBAL_Control->AttachedDevice,
    43,
    WPP_852a4bc871f63f63d337338550f67970_Traceguids,
    62,
    "onecore\\base\\fs\\wci\\wcifs\\create.c",
    35,
    v18,
    4,
    v14,
    2,
    v13,
    v12,
    (__int64 *)va,
    4,
    (__int64 *)va1,
    4,
    va2,
    4,
    0);
LABEL_11:
  v15 = a8 == 0;
  if ( a8 )
  {
    v11 = *a8;
    if ( *a8 )
      v8 = (const wchar_t *)*((_QWORD *)a8 + 1);
    v15 = a8 == 0;
  }
  if ( v15 )
    v9 = L"\b";
  LOWORD(v17) = 62;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *, int, const char *, __int64, _DWORD *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))WppAutoLogTrace)(
           a1,
           2,
           5,
           WPP_852a4bc871f63f63d337338550f67970_Traceguids,
           v17,
           "onecore\\base\\fs\\wci\\wcifs\\create.c",
           35,
           v18,
           4,
           v9,
           2,
           v8,
           v11,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x140004448  mov     rax, rsp
0x14000444b  push    rbx
0x14000444c  push    rbp
0x14000444d  push    rsi
0x14000444e  push    rdi
0x14000444f  push    r14
0x140004451  push    r15
0x140004453  sub     rsp, 0B8h
0x14000445a  mov     r10, cs:WPP_GLOBAL_Control
0x140004461  lea     rsi, aNull_0; "NULL"
0x140004468  mov     rbx, [rsp+0E8h+arg_38]
0x140004470  lea     r9, asc_14000A7D0; "\b"
0x140004477  xor     r14d, r14d
0x14000447a  mov     dword ptr [rax-48h], 0B09h
0x140004481  mov     rbp, rcx
0x140004484  lea     rcx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x14000448b  mov     eax, [r10+2Ch]
0x14000448f  lea     edi, [r14+8]
0x140004493  lea     r11d, [r14+3Eh]
0x140004497  lea     r15d, [r14+4]
0x14000449b  test    al, 10h
0x14000449d  jz      loc_140004588
0x1400044a3  cmp     byte ptr [r10+29h], 2
0x1400044a8  jb      loc_140004588
0x1400044ae  test    rbx, rbx
0x1400044b1  jz      short loc_1400044C2
0x1400044b3  movzx   ecx, word ptr [rbx]
0x1400044b6  cmp     [rbx], r14w
0x1400044ba  jz      short loc_1400044C5
0x1400044bc  mov     r8, [rbx+8]
0x1400044c0  jmp     short loc_1400044C8
0x1400044c2  mov     rcx, rdi
0x1400044c5  mov     r8, rsi
0x1400044c8  mov     rax, cs:pfnWppTraceMessage
0x1400044cf  test    rbx, rbx
0x1400044d2  mov     [rsp+0E8h+var_58], r14
0x1400044da  mov     rdx, rbx
0x1400044dd  mov     [rsp+0E8h+var_60], r15
0x1400044e5  cmovz   rdx, r9
0x1400044e9  lea     r9, [rsp+0E8h+arg_50]
0x1400044f1  mov     [rsp+0E8h+var_68], r9
0x1400044f9  lea     r9, [rsp+0E8h+arg_48]
0x140004501  mov     [rsp+0E8h+var_70], r15
0x140004506  mov     [rsp+0E8h+var_78], r9
0x14000450b  lea     r9, [rsp+0E8h+arg_40]
0x140004513  mov     [rsp+0E8h+var_80], r15
0x140004518  mov     [rsp+0E8h+var_88], r9
0x14000451d  mov     r9d, r11d
0x140004520  mov     [rsp+0E8h+var_90], rcx
0x140004525  lea     rcx, [rsp+0E8h+var_48]
0x14000452d  mov     [rsp+0E8h+var_98], r8
0x140004532  lea     r8, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140004539  mov     [rsp+0E8h+var_A0], 2
0x140004542  mov     [rsp+0E8h+var_A8], rdx
0x140004547  mov     edx, 2Bh ; '+'
0x14000454c  mov     [rsp+0E8h+var_B0], r15
0x140004551  mov     [rsp+0E8h+var_B8], rcx
0x140004556  lea     rcx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x14000455d  mov     [rsp+0E8h+var_C0], 23h ; '#'
0x140004566  mov     [rsp+0E8h+var_C8], rcx
0x14000456b  mov     rcx, [r10+18h]
0x14000456f  call    _guard_dispatch_icall
0x140004574  lea     r9, asc_14000A7D0; "\b"
0x14000457b  mov     r11d, 3Eh ; '>'
0x140004581  lea     rcx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140004588  test    rbx, rbx
0x14000458b  jz      short loc_14000459D
0x14000458d  movzx   edi, word ptr [rbx]
0x140004590  cmp     [rbx], r14w
0x140004594  jz      short loc_14000459A
0x140004596  mov     rsi, [rbx+8]
0x14000459a  test    rbx, rbx
0x14000459d  mov     [rsp+0E8h+var_50], r14
0x1400045a5  lea     rax, [rsp+0E8h+arg_50]
0x1400045ad  mov     [rsp+0E8h+var_58], r15
0x1400045b5  cmovz   rbx, r9
0x1400045b9  mov     [rsp+0E8h+var_60], rax
0x1400045c1  lea     r9, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400045c8  mov     [rsp+0E8h+var_68], r15
0x1400045d0  lea     rax, [rsp+0E8h+arg_48]
0x1400045d8  mov     [rsp+0E8h+var_70], rax
0x1400045dd  mov     edx, 2
0x1400045e2  mov     [rsp+0E8h+var_78], r15
0x1400045e7  lea     rax, [rsp+0E8h+arg_40]
0x1400045ef  mov     [rsp+0E8h+var_80], rax
0x1400045f4  lea     rax, [rsp+0E8h+var_48]
0x1400045fc  mov     [rsp+0E8h+var_88], rdi
0x140004601  mov     [rsp+0E8h+var_90], rsi
0x140004606  lea     r8d, [rdx+3]
0x14000460a  mov     [rsp+0E8h+var_98], 2
0x140004613  mov     [rsp+0E8h+var_A0], rbx
0x140004618  mov     [rsp+0E8h+var_A8], r15
0x14000461d  mov     [rsp+0E8h+var_B0], rax
0x140004622  mov     [rsp+0E8h+var_B8], 23h ; '#'
0x14000462b  mov     [rsp+0E8h+var_C0], rcx
0x140004630  mov     rcx, rbp
0x140004633  mov     word ptr [rsp+0E8h+var_C8], r11w
0x140004639  call    cs:__imp_WppAutoLogTrace
0x140004640  nop     dword ptr [rax+rax+00h]
0x140004645  add     rsp, 0B8h
0x14000464c  pop     r15
0x14000464e  pop     r14
0x140004650  pop     rdi
0x140004651  pop     rsi
0x140004652  pop     rbp
0x140004653  pop     rbx
0x140004654  retn
```
