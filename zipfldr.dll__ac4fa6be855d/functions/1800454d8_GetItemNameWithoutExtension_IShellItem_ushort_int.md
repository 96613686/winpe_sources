# GetItemNameWithoutExtension(IShellItem *,ushort *,int)

- ea: `0x1800454d8`
- end: `0x1800455d6`
- name: `?GetItemNameWithoutExtension@@YAJPEAUIShellItem@@PEAGH@Z`
- size: `254`
- prototype: `int(struct IShellItem *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180045bf8`

## callees

- `0x180010c30`
- `0x18003545c`
- `0x180036f50`
- `0x1800454d8`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18004558f`
- `SHLWAPI!__imp_StrCmpICW` at `0x18004558f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800455a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800455b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800455a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800455b1`

## pseudocode

```c
__int64 __fastcall GetItemNameWithoutExtension(struct IShellItem *a1, unsigned __int16 *a2)
{
  int v4; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  struct IShellItemVtbl *v6; // rax
  LPCWSTR pszStr2; // [rsp+20h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-20h] BYREF
  int v10; // [rsp+30h] [rbp-18h] BYREF

  *a2 = 0;
  pv = 0;
  v4 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, LPVOID *))a1->lpVtbl->GetDisplayName)(a1, 0, &pv);
  if ( v4 >= 0 )
  {
    v4 = StringCchCopyW(a2, 0x104u, (const unsigned __int16 *)pv);
    if ( v4 >= 0 )
    {
      lpVtbl = a1->lpVtbl;
      v10 = 0;
      if ( !((unsigned int (__fastcall *)(struct IShellItem *, __int64, int *))lpVtbl->GetAttributes)(
              a1,
              0x400000,
              &v10) )
      {
        v6 = a1->lpVtbl;
        pszStr2 = 0;
        v4 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPCWSTR *))v6->GetDisplayName)(
               a1,
               2147581953LL,
               &pszStr2);
        if ( v4 >= 0 )
        {
          if ( !StrCmpICW(a2, pszStr2) )
            PathStripExtension(a2);
          CoTaskMemFree((LPVOID)pszStr2);
        }
      }
    }
    CoTaskMemFree(pv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800454d8  mov     r11, rsp
0x1800454db  mov     [r11+18h], rbx
0x1800454df  mov     [r11+20h], rsi
0x1800454e3  push    rdi
0x1800454e4  sub     rsp, 40h
0x1800454e8  mov     rax, cs:__security_cookie
0x1800454ef  xor     rax, rsp
0x1800454f2  mov     [rsp+48h+var_10], rax
0x1800454f7  xor     eax, eax
0x1800454f9  lea     r8, [r11-20h]
0x1800454fd  mov     [rdx], ax
0x180045500  mov     rdi, rdx
0x180045503  mov     [r11-20h], rax
0x180045507  xor     edx, edx
0x180045509  mov     rax, [rcx]
0x18004550c  mov     rsi, rcx
0x18004550f  mov     rax, [rax+28h]
0x180045513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045518  mov     ebx, eax
0x18004551a  test    eax, eax
0x18004551c  js      loc_1800455B7
0x180045522  mov     r8, [rsp+48h+pv]; unsigned __int16 *
0x180045527  mov     edx, 104h; unsigned __int64
0x18004552c  mov     rcx, rdi; unsigned __int16 *
0x18004552f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045534  mov     ebx, eax
0x180045536  test    eax, eax
0x180045538  js      short loc_1800455AC
0x18004553a  mov     rax, [rsi]
0x18004553d  lea     r8, [rsp+48h+var_18]
0x180045542  mov     edx, 400000h
0x180045547  mov     [rsp+48h+var_18], 0
0x18004554f  mov     rcx, rsi
0x180045552  mov     rax, [rax+30h]
0x180045556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004555b  test    eax, eax
0x18004555d  jnz     short loc_1800455AC
0x18004555f  mov     rax, [rsi]
0x180045562  lea     r8, [rsp+48h+pszStr2]
0x180045567  mov     edx, 80018001h
0x18004556c  mov     [rsp+48h+pszStr2], 0
0x180045575  mov     rcx, rsi
0x180045578  mov     rax, [rax+28h]
0x18004557c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045581  mov     ebx, eax
0x180045583  test    eax, eax
0x180045585  js      short loc_1800455AC
0x180045587  mov     rdx, [rsp+48h+pszStr2]; pszStr2
0x18004558c  mov     rcx, rdi; pszStr1
0x18004558f  call    cs:__imp_StrCmpICW
0x180045595  test    eax, eax
0x180045597  jnz     short loc_1800455A1
0x180045599  mov     rcx, rdi; unsigned __int16 *
0x18004559c  call    ?PathStripExtension@@YAXPEAG@Z; PathStripExtension(ushort *)
0x1800455a1  mov     rcx, [rsp+48h+pszStr2]; pv
0x1800455a6  call    cs:__imp_CoTaskMemFree
0x1800455ac  mov     rcx, [rsp+48h+pv]; pv
0x1800455b1  call    cs:__imp_CoTaskMemFree
0x1800455b7  mov     eax, ebx
0x1800455b9  mov     rcx, [rsp+48h+var_10]
0x1800455be  xor     rcx, rsp; StackCookie
0x1800455c1  call    __security_check_cookie
0x1800455c6  mov     rbx, [rsp+48h+arg_10]
0x1800455cb  mov     rsi, [rsp+48h+arg_18]
0x1800455d0  add     rsp, 40h
0x1800455d4  pop     rdi
0x1800455d5  retn
```
