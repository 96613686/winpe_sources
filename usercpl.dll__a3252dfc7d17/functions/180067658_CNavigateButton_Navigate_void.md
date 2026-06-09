# CNavigateButton::_Navigate(void)

- ea: `0x180067658`
- end: `0x180067742`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(struct IUnknown **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180067040`

## callees

- `0x180066ce8`
- `0x180067658`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800676f7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800676f7`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180067684`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800676b0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800676dc`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180067684`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800676b0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800676dc`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18006767b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800676a7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800676d3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18006767b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800676a7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800676d3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18006771b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180067724`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18006771b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180067724`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18006773b`

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
            (const struct DirectUI::PropertyInfo *)&off_1800A1478,
            1,
            0);
  if ( Value == (struct DirectUI::Value *)DirectUI::Value::GetUnset() )
    v4 = 0;
  else
    v4 = (const unsigned __int16 *)*((_QWORD *)Value + 1);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_1800A14A8,
         1,
         0);
  if ( v5 == (struct DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = (const unsigned __int16 *)*((_QWORD *)v5 + 1);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_1800A14D8,
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
0x180067658  push    rbx
0x18006765a  push    rbp
0x18006765b  push    rsi
0x18006765c  push    rdi
0x18006765d  push    r13
0x18006765f  push    r14
0x180067661  push    r15
0x180067663  sub     rsp, 20h
0x180067667  xor     r9d, r9d
0x18006766a  lea     rdx, off_1800A1478; "navigationtargetroot"
0x180067671  mov     r15, rcx
0x180067674  lea     ebx, [r9+1]
0x180067678  mov     r8d, ebx
0x18006767b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180067681  mov     rsi, rax
0x180067684  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18006768a  cmp     rsi, rax
0x18006768d  jz      short loc_180067695
0x18006768f  mov     rdi, [rsi+8]
0x180067693  jmp     short loc_180067697
0x180067695  xor     edi, edi
0x180067697  xor     r9d, r9d
0x18006769a  lea     rdx, off_1800A14A8; "navigationtargetrelative"
0x1800676a1  mov     r8d, ebx
0x1800676a4  mov     rcx, r15
0x1800676a7  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800676ad  mov     r14, rax
0x1800676b0  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x1800676b6  cmp     r14, rax
0x1800676b9  jz      short loc_1800676C1
0x1800676bb  mov     rbp, [r14+8]
0x1800676bf  jmp     short loc_1800676C3
0x1800676c1  xor     ebp, ebp
0x1800676c3  xor     r9d, r9d
0x1800676c6  lea     rdx, off_1800A14D8; "nobackstack"
0x1800676cd  mov     r8d, ebx
0x1800676d0  mov     rcx, r15
0x1800676d3  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800676d9  mov     r13, rax
0x1800676dc  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x1800676e2  cmp     r13, rax
0x1800676e5  jz      short loc_180067701
0x1800676e7  mov     rcx, [r13+8]; pszStr1
0x1800676eb  test    rcx, rcx
0x1800676ee  jz      short loc_180067701
0x1800676f0  lea     rdx, aTrue; "true"
0x1800676f7  call    cs:__imp_StrCmpICW
0x1800676fd  test    eax, eax
0x1800676ff  jz      short loc_180067703
0x180067701  xor     bl, bl
0x180067703  mov     r8, [r15+0D8h]; struct IUnknown *
0x18006770a  mov     r9b, bl; bool
0x18006770d  mov     rdx, rbp; unsigned __int16 *
0x180067710  mov     rcx, rdi; unsigned __int16 *
0x180067713  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x180067718  mov     rcx, rsi
0x18006771b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180067721  mov     rcx, r14
0x180067724  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18006772a  mov     rcx, r13
0x18006772d  add     rsp, 20h
0x180067731  pop     r15
0x180067733  pop     r14
0x180067735  pop     r13
0x180067737  pop     rdi
0x180067738  pop     rsi
0x180067739  pop     rbp
0x18006773a  pop     rbx
0x18006773b  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
