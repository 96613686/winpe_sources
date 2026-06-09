# CNavigateButton::_Execute(void)

- ea: `0x18001ca2c`
- end: `0x18001cb82`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `342`
- prototype: `void __fastcall(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18001b960`

## callees

- `0x18000291e`
- `0x18001ca2c`
- `0x18001e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001caa1`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001caa1`
- `SHELL32!ShellExecuteExW` at `0x18001cb45`
- `SHELL32!ShellExecuteExW` at `0x18001cb45`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001ca5e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cadf`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cafc`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001ca5e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cadf`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cafc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cb4e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cb57`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cb4e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cb57`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cb7b`

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
            (const struct DirectUI::PropertyInfo *)&off_180020778,
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
           (const struct DirectUI::PropertyInfo *)&off_180020748,
           2,
           0);
    v6 = (const WCHAR *)*((_QWORD *)v5 + 1);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_180020718,
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
0x18001ca2c  mov     [rsp-8+arg_0], rbx
0x18001ca31  mov     [rsp-8+arg_18], rsi
0x18001ca36  push    rbp
0x18001ca37  push    rdi
0x18001ca38  push    r13
0x18001ca3a  push    r14
0x18001ca3c  push    r15
0x18001ca3e  lea     rbp, [rsp-37h]
0x18001ca43  sub     rsp, 90h
0x18001ca4a  xor     r9d, r9d
0x18001ca4d  lea     rdx, off_180020778; "ShellExecute"
0x18001ca54  mov     rbx, rcx
0x18001ca57  lea     esi, [r9+2]
0x18001ca5b  mov     r8d, esi
0x18001ca5e  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001ca64  xor     edi, edi
0x18001ca66  mov     r13, rax
0x18001ca69  mov     r15, [rax+8]
0x18001ca6d  test    r15, r15
0x18001ca70  jz      loc_18001CB5D
0x18001ca76  cmp     [r15], di
0x18001ca7a  jz      loc_18001CB5D
0x18001ca80  mov     rcx, [rbx+0D8h]; punk
0x18001ca87  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18001ca8b  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18001ca92  mov     [rbp+57h+arg_10], rdi
0x18001ca96  lea     rdx, SID_STopLevelBrowser; guidService
0x18001ca9d  mov     [rbp+57h+ppvOut], rdi
0x18001caa1  call    cs:__imp_IUnknown_QueryService
0x18001caa7  test    eax, eax
0x18001caa9  js      short loc_18001CACF
0x18001caab  mov     rcx, [rbp+57h+ppvOut]
0x18001caaf  lea     rdx, [rbp+57h+arg_10]
0x18001cab3  mov     rax, [rcx]
0x18001cab6  mov     rax, [rax+18h]
0x18001caba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cabf  mov     rcx, [rbp+57h+ppvOut]
0x18001cac3  mov     rax, [rcx]
0x18001cac6  mov     rax, [rax+10h]
0x18001caca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cacf  xor     r9d, r9d
0x18001cad2  lea     rdx, off_180020748; "ShellExecuteVerb"
0x18001cad9  mov     r8d, esi
0x18001cadc  mov     rcx, rbx
0x18001cadf  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001cae5  xor     r9d, r9d
0x18001cae8  lea     rdx, off_180020718; "ShellExecuteParams"
0x18001caef  mov     r8d, esi
0x18001caf2  mov     rcx, rbx
0x18001caf5  mov     r14, rax
0x18001caf8  mov     rdi, [rax+8]
0x18001cafc  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001cb02  xor     edx, edx; Val
0x18001cb04  lea     rcx, [rbp+57h+pExecInfo]; void *
0x18001cb08  mov     rsi, rax
0x18001cb0b  mov     rbx, [rax+8]
0x18001cb0f  lea     r8d, [rdx+70h]; Size
0x18001cb13  call    memset_0
0x18001cb18  mov     rcx, [rbp+57h+arg_10]
0x18001cb1c  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x18001cb20  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18001cb24  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x18001cb2b  mov     [rbp+57h+pExecInfo.nShow], 5
0x18001cb32  mov     [rbp+57h+pExecInfo.lpFile], r15
0x18001cb36  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x18001cb3a  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x18001cb3e  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x18001cb45  call    cs:__imp_ShellExecuteExW
0x18001cb4b  mov     rcx, r14
0x18001cb4e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001cb54  mov     rcx, rsi
0x18001cb57  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001cb5d  mov     rcx, r13
0x18001cb60  lea     r11, [rsp+0B0h+var_20]
0x18001cb68  mov     rbx, [r11+30h]
0x18001cb6c  mov     rsi, [r11+48h]
0x18001cb70  mov     rsp, r11
0x18001cb73  pop     r15
0x18001cb75  pop     r14
0x18001cb77  pop     r13
0x18001cb79  pop     rdi
0x18001cb7a  pop     rbp
0x18001cb7b  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
