# CThemeCplCore::GetParentWindow(void)

- ea: `0x180035ae8`
- end: `0x180035b9b`
- name: `?GetParentWindow@CThemeCplCore@@QEAAPEAUHWND__@@XZ`
- size: `179`
- prototype: `HWND __fastcall(CThemeCplCore *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180036314`
- `0x1800374bc`
- `0x1800376c8`
- `0x180038590`

## callees

- `0x180035ae8`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x180035b6f`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x180035b6f`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180035b57`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180035b57`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x180035b28`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x180035b28`

## pseudocode

```c
HWND __fastcall CThemeCplCore::GetParentWindow(CThemeCplCore *this)
{
  HWND *v1; // rbx
  IUnknown **v2; // rdi
  IUnknown *v3; // rcx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v1 = (HWND *)((char *)this + 32);
  if ( !*((_QWORD *)this + 4) )
  {
    v2 = (IUnknown **)((char *)this + 40);
    if ( *((_QWORD *)this + 5)
      || IUnknown_GetSite(
           (IUnknown *)((*((_QWORD *)this + 3) + 208LL) & -(__int64)(*((_QWORD *)this + 3) != 0)),
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)this + 5) >= 0 )
    {
      v3 = *v2;
      ppvOut = 0;
      if ( IUnknown_QueryService(
             v3,
             (const GUID *const)&SID_STopLevelBrowser,
             &GUID_00000000_0000_0000_c000_000000000046,
             &ppvOut) >= 0 )
      {
        IUnknown_GetWindow((IUnknown *)ppvOut, v1);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
    }
  }
  return *v1;
}

```

## disassembly

```asm
0x180035ae8  mov     [rsp+arg_8], rbx
0x180035aed  push    rdi
0x180035aee  sub     rsp, 20h
0x180035af2  lea     rbx, [rcx+20h]
0x180035af6  cmp     qword ptr [rbx], 0
0x180035afa  jnz     loc_180035B8C
0x180035b00  lea     rdi, [rcx+28h]
0x180035b04  cmp     qword ptr [rdi], 0
0x180035b08  jnz     short loc_180035B38
0x180035b0a  mov     rax, [rcx+18h]
0x180035b0e  mov     r8, rdi; ppv
0x180035b11  lea     rdx, [rax+0D0h]
0x180035b18  neg     rax
0x180035b1b  sbb     rcx, rcx
0x180035b1e  and     rcx, rdx; punk
0x180035b21  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180035b28  call    cs:__imp_IUnknown_GetSite
0x180035b2f  nop     dword ptr [rax+rax+00h]
0x180035b34  test    eax, eax
0x180035b36  js      short loc_180035B8C
0x180035b38  mov     rcx, [rdi]; punk
0x180035b3b  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180035b40  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180035b47  mov     [rsp+28h+ppvOut], 0
0x180035b50  lea     rdx, SID_STopLevelBrowser; guidService
0x180035b57  call    cs:__imp_IUnknown_QueryService
0x180035b5e  nop     dword ptr [rax+rax+00h]
0x180035b63  test    eax, eax
0x180035b65  js      short loc_180035B8C
0x180035b67  mov     rcx, [rsp+28h+ppvOut]; punk
0x180035b6c  mov     rdx, rbx; phwnd
0x180035b6f  call    cs:__imp_IUnknown_GetWindow
0x180035b76  nop     dword ptr [rax+rax+00h]
0x180035b7b  mov     rcx, [rsp+28h+ppvOut]
0x180035b80  mov     rdx, [rcx]
0x180035b83  mov     rax, [rdx+10h]
0x180035b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b8c  mov     rax, [rbx]
0x180035b8f  mov     rbx, [rsp+28h+arg_8]
0x180035b94  add     rsp, 20h
0x180035b98  pop     rdi
0x180035b99  retn
```
