# CNavigateButton::SetNavigationTarget(ushort const *,ushort const *)

- ea: `0x180017dc0`
- end: `0x180017e57`
- name: `?SetNavigationTarget@CNavigateButton@@QEAAJPEBG0@Z`
- size: `151`
- prototype: `__int64 __fastcall(CNavigateButton *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001601c`

## callees

- `0x180017dc0`

## import_xrefs

- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x180017e00`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x180017e3b`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x180017e00`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x180017e3b`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180017dd8`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180017e1a`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180017dd8`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180017e1a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017e0b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017e46`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017e0b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017e46`

## pseudocode

```c
__int64 __fastcall CNavigateButton::SetNavigationTarget(
        CNavigateButton *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct DirectUI::Value *String; // rax
  DirectUI::Value *v6; // rdi
  int v7; // ebx
  struct DirectUI::Value *v8; // rax
  DirectUI::Value *v9; // rdi

  String = DirectUI::Value::CreateString(&Class, 0);
  v6 = String;
  if ( String )
  {
    v7 = DirectUI::Element::SetValue(this, (const struct DirectUI::PropertyInfo *)&off_1800A1478, 1, String);
    DirectUI::Value::Release(v6);
    if ( v7 < 0 )
      return (unsigned int)v7;
    v8 = DirectUI::Value::CreateString(a3, 0);
    v9 = v8;
    if ( v8 )
    {
      v7 = DirectUI::Element::SetValue(this, (const struct DirectUI::PropertyInfo *)&off_1800A14A8, 1, v8);
      DirectUI::Value::Release(v9);
      return (unsigned int)v7;
    }
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180017dc0  push    rbx
0x180017dc2  push    rbp
0x180017dc3  push    rsi
0x180017dc4  push    rdi
0x180017dc5  sub     rsp, 28h
0x180017dc9  mov     rsi, rcx
0x180017dcc  xor     edx, edx
0x180017dce  lea     rcx, Class
0x180017dd5  mov     rbp, r8
0x180017dd8  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x180017dde  mov     rdi, rax
0x180017de1  test    rax, rax
0x180017de4  jnz     short loc_180017DED
0x180017de6  mov     ebx, 8007000Eh
0x180017deb  jmp     short loc_180017E4C
0x180017ded  mov     r9, rdi
0x180017df0  lea     rdx, off_1800A1478; "navigationtargetroot"
0x180017df7  mov     r8d, 1
0x180017dfd  mov     rcx, rsi
0x180017e00  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x180017e06  mov     rcx, rdi
0x180017e09  mov     ebx, eax
0x180017e0b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180017e11  test    ebx, ebx
0x180017e13  js      short loc_180017E4C
0x180017e15  xor     edx, edx
0x180017e17  mov     rcx, rbp
0x180017e1a  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x180017e20  mov     rdi, rax
0x180017e23  test    rax, rax
0x180017e26  jz      short loc_180017DE6
0x180017e28  mov     r9, rax
0x180017e2b  lea     rdx, off_1800A14A8; "navigationtargetrelative"
0x180017e32  mov     r8d, 1
0x180017e38  mov     rcx, rsi
0x180017e3b  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x180017e41  mov     rcx, rdi
0x180017e44  mov     ebx, eax
0x180017e46  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180017e4c  mov     eax, ebx
0x180017e4e  add     rsp, 28h
0x180017e52  pop     rdi
0x180017e53  pop     rsi
0x180017e54  pop     rbp
0x180017e55  pop     rbx
0x180017e56  retn
```
