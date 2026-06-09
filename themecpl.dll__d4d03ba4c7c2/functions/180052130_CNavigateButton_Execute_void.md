# CNavigateButton::_Execute(void)

- ea: `0x180052130`
- end: `0x1800522b5`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `389`
- prototype: `void __fastcall(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180051cf0`

## callees

- `0x180002f34`
- `0x180052130`
- `0x180057010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180052261`
- `SHELL32!ShellExecuteExW` at `0x180052261`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800521ab`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800521ab`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180052270`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18005227f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180052270`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18005227f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800522a9`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180052162`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800521ef`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180052212`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180052162`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800521ef`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180052212`

## pseudocode

```c
void __fastcall CNavigateButton::_Execute(IUnknown **this)
{
  struct DirectUI::Value *Value; // r13
  const WCHAR *v3; // r15
  IUnknown *v4; // rcx
  struct DirectUI::Value *v5; // r14
  const WCHAR *v6; // rdi
  struct DirectUI::Value *v7; // rsi
  const WCHAR *v8; // rbx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-39h] BYREF
  void *ppvOut; // [rsp+C8h] [rbp+6Fh] BYREF
  HWND v11; // [rsp+D0h] [rbp+77h] BYREF

  Value = DirectUI::Element::GetValue(
            (DirectUI::Element *)this,
            (const struct DirectUI::PropertyInfo *)&off_18005ABE8,
            2,
            0);
  v3 = (const WCHAR *)*((_QWORD *)Value + 1);
  if ( v3 && *v3 )
  {
    v4 = this[27];
    v11 = 0;
    ppvOut = 0;
    if ( IUnknown_QueryService(
           v4,
           (const GUID *const)&SID_STopLevelBrowser,
           &GUID_000214e2_0000_0000_c000_000000000046,
           &ppvOut) >= 0 )
    {
      (*(void (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v11);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    v5 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_18005ABB8,
           2,
           0);
    v6 = (const WCHAR *)*((_QWORD *)v5 + 1);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_18005AB88,
           2,
           0);
    v8 = (const WCHAR *)*((_QWORD *)v7 + 1);
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.hwnd = v11;
    pExecInfo.cbSize = 112;
    pExecInfo.nShow = 5;
    pExecInfo.lpFile = v3;
    pExecInfo.lpVerb = v6;
    pExecInfo.lpParameters = v8;
    pExecInfo.fMask = 67109388;
    ShellExecuteExW(&pExecInfo);
    DirectUI::Value::Release(v5);
    DirectUI::Value::Release(v7);
  }
  DirectUI::Value::Release(Value);
}

```

## disassembly

```asm
0x180052130  mov     [rsp-8+arg_0], rbx
0x180052135  mov     [rsp-8+arg_18], rsi
0x18005213a  push    rbp
0x18005213b  push    rdi
0x18005213c  push    r13
0x18005213e  push    r14
0x180052140  push    r15
0x180052142  lea     rbp, [rsp-37h]
0x180052147  sub     rsp, 90h
0x18005214e  xor     r9d, r9d
0x180052151  lea     rdx, off_18005ABE8; "ShellExecute"
0x180052158  mov     rbx, rcx
0x18005215b  lea     esi, [r9+2]
0x18005215f  mov     r8d, esi
0x180052162  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180052169  nop     dword ptr [rax+rax+00h]
0x18005216e  xor     edi, edi
0x180052170  mov     r13, rax
0x180052173  mov     r15, [rax+8]
0x180052177  test    r15, r15
0x18005217a  jz      loc_18005228B
0x180052180  cmp     [r15], di
0x180052184  jz      loc_18005228B
0x18005218a  mov     rcx, [rbx+0D8h]; punk
0x180052191  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180052195  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18005219c  mov     [rbp+57h+arg_10], rdi
0x1800521a0  lea     rdx, SID_STopLevelBrowser; guidService
0x1800521a7  mov     [rbp+57h+ppvOut], rdi
0x1800521ab  call    cs:__imp_IUnknown_QueryService
0x1800521b2  nop     dword ptr [rax+rax+00h]
0x1800521b7  test    eax, eax
0x1800521b9  js      short loc_1800521DF
0x1800521bb  mov     rcx, [rbp+57h+ppvOut]
0x1800521bf  lea     rdx, [rbp+57h+arg_10]
0x1800521c3  mov     rax, [rcx]
0x1800521c6  mov     rax, [rax+18h]
0x1800521ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521cf  mov     rcx, [rbp+57h+ppvOut]
0x1800521d3  mov     rax, [rcx]
0x1800521d6  mov     rax, [rax+10h]
0x1800521da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521df  xor     r9d, r9d
0x1800521e2  lea     rdx, off_18005ABB8; "ShellExecuteVerb"
0x1800521e9  mov     r8d, esi
0x1800521ec  mov     rcx, rbx
0x1800521ef  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800521f6  nop     dword ptr [rax+rax+00h]
0x1800521fb  xor     r9d, r9d
0x1800521fe  lea     rdx, off_18005AB88; "ShellExecuteParams"
0x180052205  mov     r8d, esi
0x180052208  mov     rcx, rbx
0x18005220b  mov     r14, rax
0x18005220e  mov     rdi, [rax+8]
0x180052212  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180052219  nop     dword ptr [rax+rax+00h]
0x18005221e  xor     edx, edx; Val
0x180052220  lea     rcx, [rbp+57h+pExecInfo]; void *
0x180052224  mov     rsi, rax
0x180052227  mov     rbx, [rax+8]
0x18005222b  lea     r8d, [rdx+70h]; Size
0x18005222f  call    memset_0
0x180052234  mov     rcx, [rbp+57h+arg_10]
0x180052238  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x18005223c  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x180052240  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180052247  mov     [rbp+57h+pExecInfo.nShow], 5
0x18005224e  mov     [rbp+57h+pExecInfo.lpFile], r15
0x180052252  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x180052256  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x18005225a  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x180052261  call    cs:__imp_ShellExecuteExW
0x180052268  nop     dword ptr [rax+rax+00h]
0x18005226d  mov     rcx, r14
0x180052270  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180052277  nop     dword ptr [rax+rax+00h]
0x18005227c  mov     rcx, rsi
0x18005227f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180052286  nop     dword ptr [rax+rax+00h]
0x18005228b  mov     rcx, r13
0x18005228e  lea     r11, [rsp+0B0h+var_20]
0x180052296  mov     rbx, [r11+30h]
0x18005229a  mov     rsi, [r11+48h]
0x18005229e  mov     rsp, r11
0x1800522a1  pop     r15
0x1800522a3  pop     r14
0x1800522a5  pop     r13
0x1800522a7  pop     rdi
0x1800522a8  pop     rbp
0x1800522a9  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
