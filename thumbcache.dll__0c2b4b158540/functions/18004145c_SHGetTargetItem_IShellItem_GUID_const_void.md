# SHGetTargetItem(IShellItem *,_GUID const &,void * *)

- ea: `0x18004145c`
- end: `0x18004152f`
- name: `?SHGetTargetItem@@YAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: `int(struct IShellItem *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180043334`

## callees

- `0x180035830`
- `0x18004145c`
- `0x180049010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800414f7`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800414f7`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x1800414ea`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x1800414ea`

## pseudocode

```c
__int64 __fastcall SHGetTargetItem(struct IShellItem *a1, const struct _GUID *a2, void **a3)
{
  struct IShellItemVtbl *lpVtbl; // rax
  HRESULT v5; // ebx
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp-28h] BYREF
  __int64 v8; // [rsp+38h] [rbp-20h] BYREF

  *a3 = 0;
  lpVtbl = a1->lpVtbl;
  v8 = 0;
  v5 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, __int64 *))lpVtbl->BindToHandler)(
         a1,
         0,
         &BHID_SFUIObject,
         &GUID_000214f9_0000_0000_c000_000000000046,
         &v8);
  if ( v5 >= 0 )
  {
    pidl = 0;
    if ( (*(int (__fastcall **)(__int64, LPCITEMIDLIST *))(*(_QWORD *)v8 + 32LL))(v8, &pidl) >= 0 && pidl )
    {
      v5 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a3);
      ILFree((LPITEMIDLIST)pidl);
    }
    else
    {
      v5 = -2147467259;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004145c  mov     r11, rsp
0x18004145f  mov     [r11+10h], rbx
0x180041463  push    rdi
0x180041464  sub     rsp, 50h
0x180041468  mov     rax, cs:__security_cookie
0x18004146f  xor     rax, rsp
0x180041472  mov     [rsp+58h+var_18], rax
0x180041477  mov     qword ptr [r8], 0
0x18004147e  lea     rdx, [r11-20h]
0x180041482  mov     rax, [rcx]
0x180041485  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x18004148c  mov     rdi, r8
0x18004148f  mov     [r11-38h], rdx
0x180041493  lea     r8, BHID_SFUIObject
0x18004149a  mov     qword ptr [r11-20h], 0
0x1800414a2  xor     edx, edx
0x1800414a4  mov     rax, [rax+18h]
0x1800414a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414ad  mov     ebx, eax
0x1800414af  test    eax, eax
0x1800414b1  js      short loc_180041515
0x1800414b3  mov     rcx, [rsp+58h+var_20]
0x1800414b8  lea     rdx, [rsp+58h+pidl]
0x1800414bd  mov     [rsp+58h+pidl], 0
0x1800414c6  mov     rax, [rcx]
0x1800414c9  mov     rax, [rax+20h]
0x1800414cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414d2  test    eax, eax
0x1800414d4  js      short loc_1800414FF
0x1800414d6  mov     rcx, [rsp+58h+pidl]; pidl
0x1800414db  test    rcx, rcx
0x1800414de  jz      short loc_1800414FF
0x1800414e0  mov     r8, rdi; ppv
0x1800414e3  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800414ea  call    cs:__imp_SHCreateItemFromIDList
0x1800414f0  mov     rcx, [rsp+58h+pidl]; pidl
0x1800414f5  mov     ebx, eax
0x1800414f7  call    cs:__imp_ILFree
0x1800414fd  jmp     short loc_180041504
0x1800414ff  mov     ebx, 80004005h
0x180041504  mov     rcx, [rsp+58h+var_20]
0x180041509  mov     rax, [rcx]
0x18004150c  mov     rax, [rax+10h]
0x180041510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041515  mov     eax, ebx
0x180041517  mov     rcx, [rsp+58h+var_18]
0x18004151c  xor     rcx, rsp; StackCookie
0x18004151f  call    __security_check_cookie
0x180041524  mov     rbx, [rsp+58h+arg_8]
0x180041529  add     rsp, 50h
0x18004152d  pop     rdi
0x18004152e  retn
```
