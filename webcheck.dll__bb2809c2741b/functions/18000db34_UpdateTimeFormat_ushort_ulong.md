# UpdateTimeFormat(ushort *,ulong)

- ea: `0x18000db34`
- end: `0x18000dd38`
- name: `?UpdateTimeFormat@@YAXPEAGK@Z`
- size: `516`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000c88c`

## callees

- `0x180003950`
- `0x180008648`
- `0x18000d90c`
- `0x18000db34`
- `0x180029280`

## import_xrefs

- `KERNEL32!GetLocaleInfoW` at `0x18000db7a`
- `KERNEL32!GetLocaleInfoW` at `0x18000dbab`
- `KERNEL32!GetLocaleInfoW` at `0x18000dbda`
- `KERNEL32!GetLocaleInfoW` at `0x18000dc05`
- `KERNEL32!GetLocaleInfoW` at `0x18000db7a`
- `KERNEL32!GetLocaleInfoW` at `0x18000dbab`
- `KERNEL32!GetLocaleInfoW` at `0x18000dbda`
- `KERNEL32!GetLocaleInfoW` at `0x18000dc05`

## pseudocode

```c
void __fastcall UpdateTimeFormat(unsigned __int16 *a1)
{
  BOOL v2; // edi
  int v3; // esi
  BOOL v4; // r14d
  unsigned int v5; // r11d
  unsigned int v6; // eax
  const unsigned __int16 *v7; // r8
  unsigned __int64 v8; // [rsp+20h] [rbp-89h] BYREF
  WCHAR LCData[80]; // [rsp+30h] [rbp-79h] BYREF

  if ( !GetLocaleInfoW(0x400u, 0x23u, LCData, 80) )
    goto LABEL_24;
  if ( LCData[0] != 48 )
  {
    v2 = 0;
    v3 = 0;
    goto LABEL_6;
  }
  if ( !GetLocaleInfoW(0x400u, 0x1005u, LCData, 80) )
  {
LABEL_24:
    StringCchCopyW(a1, 0x20u, L"hh:mm tt");
    return;
  }
  v3 = 1;
  v2 = LCData[0] == 49;
LABEL_6:
  if ( !GetLocaleInfoW(0x400u, 0x25u, LCData, 80) )
    goto LABEL_24;
  v4 = LCData[0] == 49;
  if ( !GetLocaleInfoW(0x400u, 0x1Eu, LCData, 80) )
    goto LABEL_24;
  v8 = 0;
  if ( (int)StringCchLengthW(LCData, 0x50u, &v8) >= 0 )
    v5 = v8 + (v3 != 0 ? 3 : 0) + v4 + 4;
  v6 = 0;
  if ( v5 <= 0x20 )
    v6 = v5;
  if ( !v6 )
    goto LABEL_24;
  *a1 = 0;
  if ( v3 )
  {
    if ( v2 )
      StringCchCopyW(a1, 0x20u, L"tt ");
    StringCchCatW(a1, 0x20u, L"h");
    if ( !v4 )
      goto LABEL_21;
    v7 = L"h";
  }
  else
  {
    StringCchCatW(a1, 0x20u, L"H");
    if ( !v4 )
      goto LABEL_21;
    v7 = L"H";
  }
  StringCchCatW(a1, 0x20u, v7);
LABEL_21:
  StringCchCatW(a1, 0x20u, LCData);
  StringCchCatW(a1, 0x20u, L"mm");
  if ( v3 )
  {
    if ( !v2 )
      StringCchCatW(a1, 0x20u, L" tt");
  }
}

```

## disassembly

```asm
0x18000db34  mov     [rsp-8+arg_8], rbx
0x18000db39  mov     [rsp-8+arg_10], rsi
0x18000db3e  push    rbp
0x18000db3f  push    rdi
0x18000db40  push    r12
0x18000db42  push    r14
0x18000db44  push    r15
0x18000db46  lea     rbp, [rsp-37h]
0x18000db4b  sub     rsp, 0E0h
0x18000db52  mov     rax, cs:__security_cookie
0x18000db59  xor     rax, rsp
0x18000db5c  mov     [rbp+57h+var_30], rax
0x18000db60  mov     r12d, 50h ; 'P'
0x18000db66  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000db6a  mov     rbx, rcx
0x18000db6d  mov     r9d, r12d; cchData
0x18000db70  mov     ecx, 400h; Locale
0x18000db75  lea     edx, [r12-2Dh]; LCType
0x18000db7a  call    cs:__imp_GetLocaleInfoW
0x18000db80  lea     r15d, [r12-30h]
0x18000db85  test    eax, eax
0x18000db87  jz      loc_18000DCFE
0x18000db8d  cmp     [rbp+57h+LCData], 30h ; '0'
0x18000db92  jz      short loc_18000DB9A
0x18000db94  xor     edi, edi
0x18000db96  xor     esi, esi
0x18000db98  jmp     short loc_18000DBC9
0x18000db9a  mov     r9d, r12d; cchData
0x18000db9d  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000dba1  mov     edx, 1005h; LCType
0x18000dba6  mov     ecx, 400h; Locale
0x18000dbab  call    cs:__imp_GetLocaleInfoW
0x18000dbb1  test    eax, eax
0x18000dbb3  jz      loc_18000DCFE
0x18000dbb9  xor     edi, edi
0x18000dbbb  mov     esi, 1
0x18000dbc0  cmp     [rbp+57h+LCData], 31h ; '1'
0x18000dbc5  setz    dil
0x18000dbc9  mov     r9d, r12d; cchData
0x18000dbcc  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000dbd0  mov     edx, 25h ; '%'; LCType
0x18000dbd5  mov     ecx, 400h; Locale
0x18000dbda  call    cs:__imp_GetLocaleInfoW
0x18000dbe0  test    eax, eax
0x18000dbe2  jz      loc_18000DCFE
0x18000dbe8  xor     r14d, r14d
0x18000dbeb  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000dbef  cmp     [rbp+57h+LCData], 31h ; '1'
0x18000dbf4  mov     r9d, r12d; cchData
0x18000dbf7  mov     edx, 1Eh; LCType
0x18000dbfc  mov     ecx, 400h; Locale
0x18000dc01  setz    r14b
0x18000dc05  call    cs:__imp_GetLocaleInfoW
0x18000dc0b  mov     r11d, eax
0x18000dc0e  test    eax, eax
0x18000dc10  jz      loc_18000DCFE
0x18000dc16  lea     r8, [rsp+100h+var_E0]; unsigned __int64 *
0x18000dc1b  mov     [rsp+100h+var_E0], 0
0x18000dc24  mov     rdx, r12; unsigned __int64
0x18000dc27  lea     rcx, [rbp+57h+LCData]; unsigned __int16 *
0x18000dc2b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000dc30  test    eax, eax
0x18000dc32  js      short loc_18000DC48
0x18000dc34  mov     eax, esi
0x18000dc36  lea     r11d, [r14+4]
0x18000dc3a  neg     eax
0x18000dc3c  sbb     ecx, ecx
0x18000dc3e  and     ecx, 3
0x18000dc41  add     ecx, dword ptr [rsp+100h+var_E0]
0x18000dc45  add     r11d, ecx
0x18000dc48  xor     eax, eax
0x18000dc4a  cmp     r11d, r15d
0x18000dc4d  cmovbe  eax, r11d
0x18000dc51  test    eax, eax
0x18000dc53  jz      loc_18000DCFE
0x18000dc59  xor     eax, eax
0x18000dc5b  mov     [rbx], ax
0x18000dc5e  test    esi, esi
0x18000dc60  jz      short loc_18000DC98
0x18000dc62  test    edi, edi
0x18000dc64  jz      short loc_18000DC78
0x18000dc66  lea     r8, aTt; "tt "
0x18000dc6d  mov     rdx, r15; unsigned __int64
0x18000dc70  mov     rcx, rbx; unsigned __int16 *
0x18000dc73  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dc78  lea     r8, asc_18002DC80; "h"
0x18000dc7f  mov     rdx, r15; unsigned __int64
0x18000dc82  mov     rcx, rbx; unsigned __int16 *
0x18000dc85  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dc8a  test    r14d, r14d
0x18000dc8d  jz      short loc_18000DCC1
0x18000dc8f  lea     r8, asc_18002DC80; "h"
0x18000dc96  jmp     short loc_18000DCB6
0x18000dc98  lea     r8, asc_18002DC84; "H"
0x18000dc9f  mov     rdx, r15; unsigned __int64
0x18000dca2  mov     rcx, rbx; unsigned __int16 *
0x18000dca5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dcaa  test    r14d, r14d
0x18000dcad  jz      short loc_18000DCC1
0x18000dcaf  lea     r8, asc_18002DC84; "H"
0x18000dcb6  mov     rdx, r15; unsigned __int64
0x18000dcb9  mov     rcx, rbx; unsigned __int16 *
0x18000dcbc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dcc1  lea     r8, [rbp+57h+LCData]; unsigned __int16 *
0x18000dcc5  mov     rdx, r15; unsigned __int64
0x18000dcc8  mov     rcx, rbx; unsigned __int16 *
0x18000dccb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dcd0  lea     r8, aMm; "mm"
0x18000dcd7  mov     rdx, r15; unsigned __int64
0x18000dcda  mov     rcx, rbx; unsigned __int16 *
0x18000dcdd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dce2  test    esi, esi
0x18000dce4  jz      short loc_18000DD10
0x18000dce6  test    edi, edi
0x18000dce8  jnz     short loc_18000DD10
0x18000dcea  lea     r8, aTt_0; " tt"
0x18000dcf1  mov     rdx, r15; unsigned __int64
0x18000dcf4  mov     rcx, rbx; unsigned __int16 *
0x18000dcf7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dcfc  jmp     short loc_18000DD10
0x18000dcfe  lea     r8, aHhMmTt; "hh:mm tt"
0x18000dd05  mov     rdx, r15; unsigned __int64
0x18000dd08  mov     rcx, rbx; unsigned __int16 *
0x18000dd0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dd10  mov     rcx, [rbp+57h+var_30]
0x18000dd14  xor     rcx, rsp; StackCookie
0x18000dd17  call    __security_check_cookie
0x18000dd1c  lea     r11, [rsp+100h+var_20]
0x18000dd24  mov     rbx, [r11+38h]
0x18000dd28  mov     rsi, [r11+40h]
0x18000dd2c  mov     rsp, r11
0x18000dd2f  pop     r15
0x18000dd31  pop     r14
0x18000dd33  pop     r12
0x18000dd35  pop     rdi
0x18000dd36  pop     rbp
0x18000dd37  retn
```
