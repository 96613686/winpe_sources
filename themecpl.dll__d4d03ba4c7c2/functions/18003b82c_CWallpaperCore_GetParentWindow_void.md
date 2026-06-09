# CWallpaperCore::GetParentWindow(void)

- ea: `0x18003b82c`
- end: `0x18003b8df`
- name: `?GetParentWindow@CWallpaperCore@@QEAAPEAUHWND__@@XZ`
- size: `179`
- prototype: `HWND __fastcall(CWallpaperCore *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18003f804`
- `0x1800423e0`

## callees

- `0x18003b82c`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18003b8b3`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18003b8b3`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18003b89b`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18003b89b`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18003b86c`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18003b86c`

## pseudocode

```c
HWND __fastcall CWallpaperCore::GetParentWindow(CWallpaperCore *this)
{
  HWND *v1; // rbx
  IUnknown **v2; // rdi
  IUnknown *v3; // rcx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v1 = (HWND *)((char *)this + 48);
  if ( !*((_QWORD *)this + 6) )
  {
    v2 = (IUnknown **)((char *)this + 64);
    if ( *((_QWORD *)this + 8)
      || IUnknown_GetSite(
           (IUnknown *)((*((_QWORD *)this + 5) + 208LL) & -(__int64)(*((_QWORD *)this + 5) != 0)),
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)this + 8) >= 0 )
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
0x18003b82c  mov     [rsp+arg_8], rbx
0x18003b831  push    rdi
0x18003b832  sub     rsp, 20h
0x18003b836  lea     rbx, [rcx+30h]
0x18003b83a  cmp     qword ptr [rbx], 0
0x18003b83e  jnz     loc_18003B8D0
0x18003b844  lea     rdi, [rcx+40h]
0x18003b848  cmp     qword ptr [rdi], 0
0x18003b84c  jnz     short loc_18003B87C
0x18003b84e  mov     rax, [rcx+28h]
0x18003b852  mov     r8, rdi; ppv
0x18003b855  lea     rdx, [rax+0D0h]
0x18003b85c  neg     rax
0x18003b85f  sbb     rcx, rcx
0x18003b862  and     rcx, rdx; punk
0x18003b865  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18003b86c  call    cs:__imp_IUnknown_GetSite
0x18003b873  nop     dword ptr [rax+rax+00h]
0x18003b878  test    eax, eax
0x18003b87a  js      short loc_18003B8D0
0x18003b87c  mov     rcx, [rdi]; punk
0x18003b87f  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18003b884  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18003b88b  mov     [rsp+28h+ppvOut], 0
0x18003b894  lea     rdx, SID_STopLevelBrowser; guidService
0x18003b89b  call    cs:__imp_IUnknown_QueryService
0x18003b8a2  nop     dword ptr [rax+rax+00h]
0x18003b8a7  test    eax, eax
0x18003b8a9  js      short loc_18003B8D0
0x18003b8ab  mov     rcx, [rsp+28h+ppvOut]; punk
0x18003b8b0  mov     rdx, rbx; phwnd
0x18003b8b3  call    cs:__imp_IUnknown_GetWindow
0x18003b8ba  nop     dword ptr [rax+rax+00h]
0x18003b8bf  mov     rcx, [rsp+28h+ppvOut]
0x18003b8c4  mov     rdx, [rcx]
0x18003b8c7  mov     rax, [rdx+10h]
0x18003b8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8d0  mov     rax, [rbx]
0x18003b8d3  mov     rbx, [rsp+28h+arg_8]
0x18003b8d8  add     rsp, 20h
0x18003b8dc  pop     rdi
0x18003b8dd  retn
```
