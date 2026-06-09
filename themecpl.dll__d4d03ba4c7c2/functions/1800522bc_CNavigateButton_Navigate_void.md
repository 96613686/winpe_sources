# CNavigateButton::_Navigate(void)

- ea: `0x1800522bc`
- end: `0x1800523e1`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `293`
- prototype: `void(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180051cf0`

## callees

- `0x180051958`
- `0x1800522bc`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18005237f`
- `SHLWAPI!__imp_StrCmpICW` at `0x18005237f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800523a9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800523b8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800523a9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800523b8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800523d5`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800522df`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180052317`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18005234f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800522df`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180052317`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18005234f`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800522ee`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180052326`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18005235e`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800522ee`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x180052326`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18005235e`

## pseudocode

```c
void __fastcall CNavigateButton::_Navigate(struct IUnknown **this)
{
  unsigned __int8 v2; // bl
  struct DirectUI::Value *Value; // rsi
  const unsigned __int16 *v4; // rdi
  struct DirectUI::Value *v5; // r14
  const unsigned __int16 *v6; // rbp
  struct DirectUI::Value *v7; // r13
  const WCHAR *v8; // rcx

  v2 = 1;
  Value = DirectUI::Element::GetValue(
            (DirectUI::Element *)this,
            (const struct DirectUI::PropertyInfo *)&off_18006F628,
            1,
            0);
  if ( Value == (struct DirectUI::Value *)DirectUI::Value::GetUnset() )
    v4 = 0;
  else
    v4 = (const unsigned __int16 *)*((_QWORD *)Value + 1);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_18006F658,
         1,
         0);
  if ( v5 == (struct DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = (const unsigned __int16 *)*((_QWORD *)v5 + 1);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_18006F688,
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
0x1800522bc  push    rbx
0x1800522be  push    rbp
0x1800522bf  push    rsi
0x1800522c0  push    rdi
0x1800522c1  push    r13
0x1800522c3  push    r14
0x1800522c5  push    r15
0x1800522c7  sub     rsp, 20h
0x1800522cb  xor     r9d, r9d
0x1800522ce  lea     rdx, off_18006F628; "navigationtargetroot"
0x1800522d5  mov     r15, rcx
0x1800522d8  lea     ebx, [r9+1]
0x1800522dc  mov     r8d, ebx
0x1800522df  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800522e6  nop     dword ptr [rax+rax+00h]
0x1800522eb  mov     rsi, rax
0x1800522ee  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x1800522f5  nop     dword ptr [rax+rax+00h]
0x1800522fa  cmp     rsi, rax
0x1800522fd  jz      short loc_180052305
0x1800522ff  mov     rdi, [rsi+8]
0x180052303  jmp     short loc_180052307
0x180052305  xor     edi, edi
0x180052307  xor     r9d, r9d
0x18005230a  lea     rdx, off_18006F658; "navigationtargetrelative"
0x180052311  mov     r8d, ebx
0x180052314  mov     rcx, r15
0x180052317  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18005231e  nop     dword ptr [rax+rax+00h]
0x180052323  mov     r14, rax
0x180052326  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18005232d  nop     dword ptr [rax+rax+00h]
0x180052332  cmp     r14, rax
0x180052335  jz      short loc_18005233D
0x180052337  mov     rbp, [r14+8]
0x18005233b  jmp     short loc_18005233F
0x18005233d  xor     ebp, ebp
0x18005233f  xor     r9d, r9d
0x180052342  lea     rdx, off_18006F688; "nobackstack"
0x180052349  mov     r8d, ebx
0x18005234c  mov     rcx, r15
0x18005234f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180052356  nop     dword ptr [rax+rax+00h]
0x18005235b  mov     r13, rax
0x18005235e  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x180052365  nop     dword ptr [rax+rax+00h]
0x18005236a  cmp     r13, rax
0x18005236d  jz      short loc_18005238F
0x18005236f  mov     rcx, [r13+8]; pszStr1
0x180052373  test    rcx, rcx
0x180052376  jz      short loc_18005238F
0x180052378  lea     rdx, pszStr2; "true"
0x18005237f  call    cs:__imp_StrCmpICW
0x180052386  nop     dword ptr [rax+rax+00h]
0x18005238b  test    eax, eax
0x18005238d  jz      short loc_180052391
0x18005238f  xor     bl, bl
0x180052391  mov     r8, [r15+0D8h]; struct IUnknown *
0x180052398  mov     r9b, bl; bool
0x18005239b  mov     rdx, rbp; unsigned __int16 *
0x18005239e  mov     rcx, rdi; unsigned __int16 *
0x1800523a1  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x1800523a6  mov     rcx, rsi
0x1800523a9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800523b0  nop     dword ptr [rax+rax+00h]
0x1800523b5  mov     rcx, r14
0x1800523b8  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800523bf  nop     dword ptr [rax+rax+00h]
0x1800523c4  mov     rcx, r13
0x1800523c7  add     rsp, 20h
0x1800523cb  pop     r15
0x1800523cd  pop     r14
0x1800523cf  pop     r13
0x1800523d1  pop     rdi
0x1800523d2  pop     rsi
0x1800523d3  pop     rbp
0x1800523d4  pop     rbx
0x1800523d5  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
