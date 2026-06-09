# CShellWrappers::GetPathFromChildPidl(IShellFolder *,_ITEMID_CHILD const *,ushort * *,int)

- ea: `0x18002d3a0`
- end: `0x18002d46b`
- name: `?GetPathFromChildPidl@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAPEAGH@Z`
- size: `203`
- prototype: `int(CShellWrappers *__hidden this, struct IShellFolder *, const struct _ITEMID_CHILD *, unsigned __int16 **, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180025b24`
- `0x18002cc10`
- `0x18002d324`

## callees

- `0x18000687c`
- `0x18001d568`
- `0x18002d3a0`
- `0x180032010`

## import_xrefs

- `SHLWAPI!StrRetToStrW` at `0x18002d411`
- `SHLWAPI!StrRetToStrW` at `0x18002d411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d441`

## pseudocode

```c
__int64 __fastcall CShellWrappers::GetPathFromChildPidl(
        WCHAR *this,
        struct IShellFolder *a2,
        const ITEMIDLIST *a3,
        unsigned __int16 **a4,
        int a5)
{
  int v8; // eax
  HRESULT v9; // ebx
  STRRET pstr; // [rsp+30h] [rbp-118h] BYREF
  LPWSTR ppsz; // [rsp+150h] [rbp+8h] BYREF

  ppsz = this;
  memset_0(&pstr, 0, sizeof(pstr));
  v8 = ((__int64 (__fastcall *)(struct IShellFolder *, const ITEMIDLIST *, __int64, STRRET *))a2->lpVtbl->GetDisplayNameOf)(
         a2,
         a3,
         0x8000,
         &pstr);
  ppsz = 0;
  v9 = v8;
  if ( v8 >= 0 )
  {
    v9 = StrRetToStrW(&pstr, a3, &ppsz);
    if ( v9 >= 0 )
    {
      if ( a5 )
      {
        v9 = PathDupNormalize(ppsz, a4);
        CoTaskMemFree(ppsz);
      }
      else
      {
        *a4 = ppsz;
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002d3a0  mov     [rsp+arg_8], rbx
0x18002d3a5  mov     [rsp+arg_10], rsi
0x18002d3aa  mov     [rsp+ppsz], rcx
0x18002d3af  push    rdi
0x18002d3b0  sub     rsp, 140h
0x18002d3b7  mov     rsi, r8
0x18002d3ba  lea     rcx, [rsp+148h+pstr]; void *
0x18002d3bf  mov     rbx, rdx
0x18002d3c2  mov     r8d, 110h; Size
0x18002d3c8  xor     edx, edx; Val
0x18002d3ca  mov     rdi, r9
0x18002d3cd  call    memset_0
0x18002d3d2  mov     rax, [rbx]
0x18002d3d5  lea     r9, [rsp+148h+pstr]
0x18002d3da  mov     r8d, 8000h
0x18002d3e0  mov     rdx, rsi
0x18002d3e3  mov     rcx, rbx
0x18002d3e6  mov     rax, [rax+58h]
0x18002d3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3ef  mov     [rsp+148h+ppsz], 0
0x18002d3fb  mov     ebx, eax
0x18002d3fd  test    eax, eax
0x18002d3ff  js      short loc_18002D454
0x18002d401  lea     r8, [rsp+148h+ppsz]; ppsz
0x18002d409  mov     rdx, rsi; pidl
0x18002d40c  lea     rcx, [rsp+148h+pstr]; pstr
0x18002d411  call    cs:__imp_StrRetToStrW
0x18002d417  mov     ebx, eax
0x18002d419  test    eax, eax
0x18002d41b  js      short loc_18002D454
0x18002d41d  cmp     [rsp+148h+arg_20], 0
0x18002d425  jz      short loc_18002D449
0x18002d427  mov     rcx, [rsp+148h+ppsz]; unsigned __int16 *
0x18002d42f  mov     rdx, rdi; unsigned __int16 **
0x18002d432  call    ?PathDupNormalize@@YAJPEBGPEAPEAG@Z; PathDupNormalize(ushort const *,ushort * *)
0x18002d437  mov     rcx, [rsp+148h+ppsz]; pv
0x18002d43f  mov     ebx, eax
0x18002d441  call    cs:__imp_CoTaskMemFree
0x18002d447  jmp     short loc_18002D454
0x18002d449  mov     rax, [rsp+148h+ppsz]
0x18002d451  mov     [rdi], rax
0x18002d454  lea     r11, [rsp+148h+var_8]
0x18002d45c  mov     eax, ebx
0x18002d45e  mov     rbx, [r11+18h]
0x18002d462  mov     rsi, [r11+20h]
0x18002d466  mov     rsp, r11
0x18002d469  pop     rdi
0x18002d46a  retn
```
