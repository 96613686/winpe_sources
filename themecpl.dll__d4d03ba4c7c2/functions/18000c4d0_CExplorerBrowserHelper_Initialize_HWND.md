# CExplorerBrowserHelper::Initialize(HWND__ *)

- ea: `0x18000c4d0`
- end: `0x18000c5aa`
- name: `?Initialize@CExplorerBrowserHelper@@UEAAPEAUHWND__@@PEAU2@@Z`
- size: `218`
- prototype: `HWND __fastcall(CExplorerBrowserHelper *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002280`
- `0x18000c4d0`
- `0x18000d460`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000c569`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000c569`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c519`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c519`

## pseudocode

```c
HWND __fastcall CExplorerBrowserHelper::Initialize(LPVOID *this, HWND a2)
{
  IUnknown **v2; // rbx
  IUnknown *v5; // rcx
  HWND phwnd; // [rsp+30h] [rbp-38h] BYREF
  _DWORD v8[2]; // [rsp+38h] [rbp-30h] BYREF
  __int128 v9; // [rsp+40h] [rbp-28h] BYREF

  v2 = (IUnknown **)(this + 9);
  phwnd = 0;
  if ( CoCreateInstance(&CLSID_ExplorerBrowser, 0, 3u, &GUID_dfd3b6b5_c10c_4be9_85f6_a66969f402f6, this + 9) >= 0 )
  {
    v5 = *v2;
    v8[0] = -1;
    v9 = 0;
    v8[1] = 0x1000000;
    if ( ((int (__fastcall *)(IUnknown *, HWND, __int128 *, _DWORD *))v5->lpVtbl[1].QueryInterface)(v5, a2, &v9, v8) < 0
      || (IUnknown_GetWindow(*v2, &phwnd), !phwnd) )
    {
      CExplorerBrowserHelper::_FreeExplorerBrowser((CExplorerBrowserHelper *)this);
    }
  }
  return phwnd;
}

```

## disassembly

```asm
0x18000c4d0  mov     r11, rsp
0x18000c4d3  mov     [r11+18h], rbx
0x18000c4d7  mov     [r11+20h], rsi
0x18000c4db  push    rdi
0x18000c4dc  sub     rsp, 60h
0x18000c4e0  mov     rax, cs:__security_cookie
0x18000c4e7  xor     rax, rsp
0x18000c4ea  mov     [rsp+68h+var_18], rax
0x18000c4ef  lea     rbx, [rcx+48h]
0x18000c4f3  mov     qword ptr [r11-38h], 0
0x18000c4fb  mov     rsi, rdx
0x18000c4fe  mov     [r11-48h], rbx
0x18000c502  xor     edx, edx; pUnkOuter
0x18000c504  lea     r9, _GUID_dfd3b6b5_c10c_4be9_85f6_a66969f402f6; riid
0x18000c50b  mov     rdi, rcx
0x18000c50e  lea     rcx, CLSID_ExplorerBrowser; rclsid
0x18000c515  lea     r8d, [rdx+3]; dwClsContext
0x18000c519  call    cs:__imp_CoCreateInstance
0x18000c520  nop     dword ptr [rax+rax+00h]
0x18000c525  test    eax, eax
0x18000c527  js      short loc_18000C585
0x18000c529  mov     rcx, [rbx]
0x18000c52c  lea     r9, [rsp+68h+var_30]
0x18000c531  xorps   xmm0, xmm0
0x18000c534  mov     [rsp+68h+var_30], 0FFFFFFFFh
0x18000c53c  movups  [rsp+68h+var_28], xmm0
0x18000c541  mov     [rsp+68h+var_2C], 1000000h
0x18000c549  lea     r8, [rsp+68h+var_28]
0x18000c54e  mov     rax, [rcx]
0x18000c551  mov     rdx, rsi
0x18000c554  mov     rax, [rax+18h]
0x18000c558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c55d  test    eax, eax
0x18000c55f  js      short loc_18000C57D
0x18000c561  mov     rcx, [rbx]; punk
0x18000c564  lea     rdx, [rsp+68h+phwnd]; phwnd
0x18000c569  call    cs:__imp_IUnknown_GetWindow
0x18000c570  nop     dword ptr [rax+rax+00h]
0x18000c575  cmp     [rsp+68h+phwnd], 0
0x18000c57b  jnz     short loc_18000C585
0x18000c57d  mov     rcx, rdi; this
0x18000c580  call    ?_FreeExplorerBrowser@CExplorerBrowserHelper@@AEAAXXZ; CExplorerBrowserHelper::_FreeExplorerBrowser(void)
0x18000c585  mov     rax, [rsp+68h+phwnd]
0x18000c58a  mov     rcx, [rsp+68h+var_18]
0x18000c58f  xor     rcx, rsp; StackCookie
0x18000c592  call    __security_check_cookie
0x18000c597  lea     r11, [rsp+68h+var_8]
0x18000c59c  mov     rbx, [r11+20h]
0x18000c5a0  mov     rsi, [r11+28h]
0x18000c5a4  mov     rsp, r11
0x18000c5a7  pop     rdi
0x18000c5a8  retn
```
