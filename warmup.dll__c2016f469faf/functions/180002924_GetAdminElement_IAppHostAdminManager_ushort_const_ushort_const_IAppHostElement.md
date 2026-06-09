# GetAdminElement(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *)

- ea: `0x180002924`
- end: `0x1800029a0`
- name: `?GetAdminElement@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@@Z`
- size: `124`
- prototype: `int(struct IAppHostAdminManager *, const unsigned __int16 *, const unsigned __int16 *, struct IAppHostElement **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003818`
- `0x180003c74`

## callees

- `0x180002924`
- `0x180006010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002939`
- `OLEAUT32!__imp_SysAllocString` at `0x180002945`
- `OLEAUT32!__imp_SysAllocString` at `0x180002939`
- `OLEAUT32!__imp_SysAllocString` at `0x180002945`
- `OLEAUT32!__imp_SysFreeString` at `0x180002981`
- `OLEAUT32!__imp_SysFreeString` at `0x18000298f`
- `OLEAUT32!__imp_SysFreeString` at `0x180002981`
- `OLEAUT32!__imp_SysFreeString` at `0x18000298f`

## pseudocode

```c
__int64 __fastcall GetAdminElement(
        struct IAppHostAdminManager *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IAppHostElement **a4)
{
  OLECHAR *v7; // rdi
  BSTR v8; // rax
  OLECHAR *v9; // rbx
  unsigned int v10; // esi

  v7 = SysAllocString(a2);
  v8 = SysAllocString(a3);
  v9 = v8;
  if ( v7 && v8 )
  {
    v10 = ((__int64 (__fastcall *)(struct IAppHostAdminManager *, BSTR, OLECHAR *, struct IAppHostElement **))a1->lpVtbl->GetAdminSection)(
            a1,
            v8,
            v7,
            a4);
  }
  else
  {
    v10 = -2147024882;
    if ( !v8 )
      goto LABEL_6;
  }
  SysFreeString(v9);
LABEL_6:
  if ( v7 )
    SysFreeString(v7);
  return v10;
}

```

## disassembly

```asm
0x180002924  push    rbx
0x180002926  push    rbp
0x180002927  push    rsi
0x180002928  push    rdi
0x180002929  sub     rsp, 38h
0x18000292d  mov     rsi, rcx
0x180002930  mov     rbp, r9
0x180002933  mov     rcx, rdx; psz
0x180002936  mov     rbx, r8
0x180002939  call    cs:__imp_SysAllocString
0x18000293f  mov     rcx, rbx; psz
0x180002942  mov     rdi, rax
0x180002945  call    cs:__imp_SysAllocString
0x18000294b  mov     rbx, rax
0x18000294e  test    rdi, rdi
0x180002951  jz      short loc_180002974
0x180002953  test    rax, rax
0x180002956  jz      short loc_180002974
0x180002958  mov     rcx, [rsi]
0x18000295b  mov     r9, rbp
0x18000295e  mov     r8, rdi
0x180002961  mov     rdx, rbx
0x180002964  mov     rax, [rcx+18h]
0x180002968  mov     rcx, rsi
0x18000296b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002970  mov     esi, eax
0x180002972  jmp     short loc_18000297E
0x180002974  mov     esi, 8007000Eh
0x180002979  test    rbx, rbx
0x18000297c  jz      short loc_180002987
0x18000297e  mov     rcx, rbx; bstrString
0x180002981  call    cs:__imp_SysFreeString
0x180002987  test    rdi, rdi
0x18000298a  jz      short loc_180002995
0x18000298c  mov     rcx, rdi; bstrString
0x18000298f  call    cs:__imp_SysFreeString
0x180002995  mov     eax, esi
0x180002997  add     rsp, 38h
0x18000299b  pop     rdi
0x18000299c  pop     rsi
0x18000299d  pop     rbp
0x18000299e  pop     rbx
0x18000299f  retn
```
