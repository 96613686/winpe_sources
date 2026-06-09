# CNavigateButton::_Execute(void)

- ea: `0x1800674fc`
- end: `0x180067652`
- name: `?_Execute@CNavigateButton@@AEAAXXZ`
- size: `342`
- prototype: `void __fastcall(IUnknown **this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180067040`

## callees

- `0x1800674fc`
- `0x18007728a`
- `0x180078010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180067615`
- `SHELL32!ShellExecuteExW` at `0x180067615`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18006752e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800675af`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800675cc`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18006752e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800675af`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800675cc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18006761e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180067627`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18006761e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180067627`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18006764b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180067571`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180067571`

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
            (const struct DirectUI::PropertyInfo *)&off_18007ED10,
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
           (const struct DirectUI::PropertyInfo *)&off_18007ECE0,
           2,
           0);
    v6 = (const WCHAR *)*((_QWORD *)v5 + 1);
    v7 = DirectUI::Element::GetValue(
           (DirectUI::Element *)this,
           (const struct DirectUI::PropertyInfo *)&off_18007ECB0,
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
0x1800674fc  mov     [rsp-8+arg_0], rbx
0x180067501  mov     [rsp-8+arg_18], rsi
0x180067506  push    rbp
0x180067507  push    rdi
0x180067508  push    r13
0x18006750a  push    r14
0x18006750c  push    r15
0x18006750e  lea     rbp, [rsp-37h]
0x180067513  sub     rsp, 90h
0x18006751a  xor     r9d, r9d
0x18006751d  lea     rdx, off_18007ED10; "ShellExecute"
0x180067524  mov     rbx, rcx
0x180067527  lea     esi, [r9+2]
0x18006752b  mov     r8d, esi
0x18006752e  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180067534  xor     edi, edi
0x180067536  mov     r13, rax
0x180067539  mov     r15, [rax+8]
0x18006753d  test    r15, r15
0x180067540  jz      loc_18006762D
0x180067546  cmp     [r15], di
0x18006754a  jz      loc_18006762D
0x180067550  mov     rcx, [rbx+0D8h]; punk
0x180067557  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18006755b  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180067562  mov     [rbp+57h+arg_10], rdi
0x180067566  lea     rdx, SID_STopLevelBrowser; guidService
0x18006756d  mov     [rbp+57h+ppvOut], rdi
0x180067571  call    cs:__imp_IUnknown_QueryService
0x180067577  test    eax, eax
0x180067579  js      short loc_18006759F
0x18006757b  mov     rcx, [rbp+57h+ppvOut]
0x18006757f  lea     rdx, [rbp+57h+arg_10]
0x180067583  mov     rax, [rcx]
0x180067586  mov     rax, [rax+18h]
0x18006758a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006758f  mov     rcx, [rbp+57h+ppvOut]
0x180067593  mov     rax, [rcx]
0x180067596  mov     rax, [rax+10h]
0x18006759a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006759f  xor     r9d, r9d
0x1800675a2  lea     rdx, off_18007ECE0; "ShellExecuteVerb"
0x1800675a9  mov     r8d, esi
0x1800675ac  mov     rcx, rbx
0x1800675af  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800675b5  xor     r9d, r9d
0x1800675b8  lea     rdx, off_18007ECB0; "ShellExecuteParams"
0x1800675bf  mov     r8d, esi
0x1800675c2  mov     rcx, rbx
0x1800675c5  mov     r14, rax
0x1800675c8  mov     rdi, [rax+8]
0x1800675cc  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800675d2  xor     edx, edx; Val
0x1800675d4  lea     rcx, [rbp+57h+pExecInfo]; void *
0x1800675d8  mov     rsi, rax
0x1800675db  mov     rbx, [rax+8]
0x1800675df  lea     r8d, [rdx+70h]; Size
0x1800675e3  call    memset_0
0x1800675e8  mov     rcx, [rbp+57h+arg_10]
0x1800675ec  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x1800675f0  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x1800675f4  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x1800675fb  mov     [rbp+57h+pExecInfo.nShow], 5
0x180067602  mov     [rbp+57h+pExecInfo.lpFile], r15
0x180067606  mov     [rbp+57h+pExecInfo.lpVerb], rdi
0x18006760a  mov     [rbp+57h+pExecInfo.lpParameters], rbx
0x18006760e  mov     [rbp+57h+pExecInfo.fMask], 400020Ch
0x180067615  call    cs:__imp_ShellExecuteExW
0x18006761b  mov     rcx, r14
0x18006761e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180067624  mov     rcx, rsi
0x180067627  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18006762d  mov     rcx, r13
0x180067630  lea     r11, [rsp+0B0h+var_20]
0x180067638  mov     rbx, [r11+30h]
0x18006763c  mov     rsi, [r11+48h]
0x180067640  mov     rsp, r11
0x180067643  pop     r15
0x180067645  pop     r14
0x180067647  pop     r13
0x180067649  pop     rdi
0x18006764a  pop     rbp
0x18006764b  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
