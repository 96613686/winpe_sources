# CNavigateButton::_Navigate(void)

- ea: `0x18001cbb4`
- end: `0x18001cc9e`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `234`
- prototype: `void(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001b960`

## callees

- `0x18001b6b8`
- `0x18001cbb4`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18001cc53`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001cc53`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cbd7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cc03`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cc2f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cbd7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cc03`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cc2f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cc77`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cc80`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cc77`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cc80`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cc97`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001cbe0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001cc0c`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001cc38`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001cbe0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001cc0c`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18001cc38`

## pseudocode

```c
void __fastcall CNavigateButton::_Navigate(struct IUnknown **this)
{
  bool v2; // bl
  struct DirectUI::Value *Value; // rsi
  const unsigned __int16 *v4; // rdi
  struct DirectUI::Value *v5; // r14
  const unsigned __int16 *v6; // rbp
  struct DirectUI::Value *v7; // r13
  const WCHAR *v8; // rcx

  v2 = 1;
  Value = DirectUI::Element::GetValue(
            (DirectUI::Element *)this,
            (const struct DirectUI::PropertyInfo *)&off_18002A108,
            1,
            0);
  if ( Value == (struct DirectUI::Value *)DirectUI::Value::GetUnset() )
    v4 = 0;
  else
    v4 = (const unsigned __int16 *)*((_QWORD *)Value + 1);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_18002A138,
         1,
         0);
  if ( v5 == (struct DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = (const unsigned __int16 *)*((_QWORD *)v5 + 1);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_18002A168,
         1,
         0);
  if ( v7 == (struct DirectUI::Value *)DirectUI::Value::GetUnset()
    || (v8 = (const WCHAR *)*((_QWORD *)v7 + 1)) == 0
    || StrCmpICW(v8, L"true") )
  {
    v2 = 0;
  }
  CNavigateButton::Navigate(v4, v6, this[27], v2);
  DirectUI::Value::Release(Value);
  DirectUI::Value::Release(v5);
  DirectUI::Value::Release(v7);
}

```

## disassembly

```asm
0x18001cbb4  push    rbx
0x18001cbb6  push    rbp
0x18001cbb7  push    rsi
0x18001cbb8  push    rdi
0x18001cbb9  push    r13
0x18001cbbb  push    r14
0x18001cbbd  push    r15
0x18001cbbf  sub     rsp, 20h
0x18001cbc3  xor     r9d, r9d
0x18001cbc6  lea     rdx, off_18002A108; "navigationtargetroot"
0x18001cbcd  mov     r15, rcx
0x18001cbd0  lea     ebx, [r9+1]
0x18001cbd4  mov     r8d, ebx
0x18001cbd7  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001cbdd  mov     rsi, rax
0x18001cbe0  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18001cbe6  cmp     rsi, rax
0x18001cbe9  jz      short loc_18001CBF1
0x18001cbeb  mov     rdi, [rsi+8]
0x18001cbef  jmp     short loc_18001CBF3
0x18001cbf1  xor     edi, edi
0x18001cbf3  xor     r9d, r9d
0x18001cbf6  lea     rdx, off_18002A138; "navigationtargetrelative"
0x18001cbfd  mov     r8d, ebx
0x18001cc00  mov     rcx, r15
0x18001cc03  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001cc09  mov     r14, rax
0x18001cc0c  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18001cc12  cmp     r14, rax
0x18001cc15  jz      short loc_18001CC1D
0x18001cc17  mov     rbp, [r14+8]
0x18001cc1b  jmp     short loc_18001CC1F
0x18001cc1d  xor     ebp, ebp
0x18001cc1f  xor     r9d, r9d
0x18001cc22  lea     rdx, off_18002A168; "nobackstack"
0x18001cc29  mov     r8d, ebx
0x18001cc2c  mov     rcx, r15
0x18001cc2f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001cc35  mov     r13, rax
0x18001cc38  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18001cc3e  cmp     r13, rax
0x18001cc41  jz      short loc_18001CC5D
0x18001cc43  mov     rcx, [r13+8]; pszStr1
0x18001cc47  test    rcx, rcx
0x18001cc4a  jz      short loc_18001CC5D
0x18001cc4c  lea     rdx, pszStr2; "true"
0x18001cc53  call    cs:__imp_StrCmpICW
0x18001cc59  test    eax, eax
0x18001cc5b  jz      short loc_18001CC5F
0x18001cc5d  xor     bl, bl
0x18001cc5f  mov     r8, [r15+0D8h]; struct IUnknown *
0x18001cc66  mov     r9b, bl; bool
0x18001cc69  mov     rdx, rbp; unsigned __int16 *
0x18001cc6c  mov     rcx, rdi; unsigned __int16 *
0x18001cc6f  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x18001cc74  mov     rcx, rsi
0x18001cc77  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001cc7d  mov     rcx, r14
0x18001cc80  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001cc86  mov     rcx, r13
0x18001cc89  add     rsp, 20h
0x18001cc8d  pop     r15
0x18001cc8f  pop     r14
0x18001cc91  pop     r13
0x18001cc93  pop     rdi
0x18001cc94  pop     rsi
0x18001cc95  pop     rbp
0x18001cc96  pop     rbx
0x18001cc97  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
