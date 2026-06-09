# CreateItemFromUserInput(ushort const *,_GUID const &,void * *)

- ea: `0x180022910`
- end: `0x180022a2b`
- name: `?CreateItemFromUserInput@@YAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `283`
- prototype: `int(const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002270c`

## callees

- `0x180022910`
- `0x180022a34`
- `0x180036f50`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x1800229e8`
- `SHELL32!SHCreateItemFromIDList` at `0x1800229e8`
- `SHELL32!__imp_ILFree` at `0x1800229f5`
- `SHELL32!__imp_ILFree` at `0x1800229f5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022960`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022960`

## pseudocode

```c
__int64 __fastcall CreateItemFromUserInput(const unsigned __int16 *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v5; // ebx
  int v6; // eax
  LPVOID v8; // [rsp+30h] [rbp-28h] BYREF
  LPCITEMIDLIST pidl; // [rsp+38h] [rbp-20h] BYREF

  *a3 = 0;
  v8 = 0;
  v5 = CoCreateInstance(&CLSID_ShellUrl, 0, 1u, &GUID_4f33718d_bae1_4f9b_96f2_d2a16e683346, &v8);
  if ( v5 >= 0 )
  {
    SetDefaultShellPath(v8);
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v8 + 184LL))(v8, 0);
    v5 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD))(*(_QWORD *)v8 + 24LL))(
           v8,
           a1,
           v6 | 0x85u);
    if ( v5 >= 0 )
    {
      pidl = 0;
      v5 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST *))(*(_QWORD *)v8 + 56LL))(v8, &pidl);
      if ( v5 >= 0 )
      {
        v5 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a3);
        ILFree((LPITEMIDLIST)pidl);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022910  mov     r11, rsp
0x180022913  mov     [r11+10h], rbx
0x180022917  mov     [r11+20h], rsi
0x18002291b  push    rdi
0x18002291c  sub     rsp, 50h
0x180022920  mov     rax, cs:__security_cookie
0x180022927  xor     rax, rsp
0x18002292a  mov     [rsp+58h+var_18], rax
0x18002292f  xor     edx, edx; pUnkOuter
0x180022931  mov     qword ptr [r8], 0
0x180022938  mov     rdi, r8
0x18002293b  mov     qword ptr [r11-28h], 0
0x180022943  mov     rsi, rcx
0x180022946  lea     rax, [r11-28h]
0x18002294a  lea     r9, _GUID_4f33718d_bae1_4f9b_96f2_d2a16e683346; riid
0x180022951  mov     [r11-38h], rax
0x180022955  lea     r8d, [rdx+1]; dwClsContext
0x180022959  lea     rcx, CLSID_ShellUrl; rclsid
0x180022960  call    cs:__imp_CoCreateInstance
0x180022966  mov     ebx, eax
0x180022968  test    eax, eax
0x18002296a  js      loc_180022A0C
0x180022970  mov     rcx, [rsp+58h+var_28]
0x180022975  call    SetDefaultShellPath
0x18002297a  mov     rcx, [rsp+58h+var_28]
0x18002297f  xor     edx, edx
0x180022981  mov     rax, [rcx]
0x180022984  mov     rax, [rax+0B8h]
0x18002298b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022990  mov     rcx, [rsp+58h+var_28]
0x180022995  mov     r8d, eax
0x180022998  or      r8d, 85h
0x18002299f  mov     rdx, rsi
0x1800229a2  mov     rax, [rcx]
0x1800229a5  mov     rax, [rax+18h]
0x1800229a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229ae  mov     ebx, eax
0x1800229b0  test    eax, eax
0x1800229b2  js      short loc_1800229FB
0x1800229b4  mov     rcx, [rsp+58h+var_28]
0x1800229b9  lea     rdx, [rsp+58h+pidl]
0x1800229be  mov     [rsp+58h+pidl], 0
0x1800229c7  mov     rax, [rcx]
0x1800229ca  mov     rax, [rax+38h]
0x1800229ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229d3  mov     ebx, eax
0x1800229d5  test    eax, eax
0x1800229d7  js      short loc_1800229FB
0x1800229d9  mov     rcx, [rsp+58h+pidl]; pidl
0x1800229de  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800229e5  mov     r8, rdi; ppv
0x1800229e8  call    cs:__imp_SHCreateItemFromIDList
0x1800229ee  mov     rcx, [rsp+58h+pidl]; pidl
0x1800229f3  mov     ebx, eax
0x1800229f5  call    cs:__imp_ILFree
0x1800229fb  mov     rcx, [rsp+58h+var_28]
0x180022a00  mov     rax, [rcx]
0x180022a03  mov     rax, [rax+10h]
0x180022a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a0c  mov     eax, ebx
0x180022a0e  mov     rcx, [rsp+58h+var_18]
0x180022a13  xor     rcx, rsp; StackCookie
0x180022a16  call    __security_check_cookie
0x180022a1b  mov     rbx, [rsp+58h+arg_8]
0x180022a20  mov     rsi, [rsp+58h+arg_18]
0x180022a25  add     rsp, 50h
0x180022a29  pop     rdi
0x180022a2a  retn
```
