# CShellWrappers::GetDisplayNameFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort *,int)

- ea: `0x18002cda8`
- end: `0x18002cf27`
- name: `?GetDisplayNameFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAGH@Z`
- size: `383`
- prototype: `int(CShellWrappers *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014880`
- `0x18001681c`
- `0x180024950`

## callees

- `0x1800038ac`
- `0x180005cc0`
- `0x18000687c`
- `0x1800094f0`
- `0x18002cda8`
- `0x18002d324`
- `0x18002d474`
- `0x180032010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x18002ce03`
- `SHELL32!SHBindToParent` at `0x18002ce03`
- `SHELL32!__imp_IsUserAnAdmin` at `0x18002ce73`
- `SHELL32!__imp_IsUserAnAdmin` at `0x18002ce73`
- `SHLWAPI!StrRetToBufW` at `0x18002ce63`
- `SHLWAPI!StrRetToBufW` at `0x18002ce63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ceee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ceee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellWrappers::GetDisplayNameFromAbsPidl(
        CShellWrappers *this,
        const ITEMIDLIST *a2,
        unsigned __int16 *a3,
        int a4)
{
  HRESULT PathFromAbsPidl; // ebx
  CShellWrappers *v8; // rcx
  LPCITEMIDLIST ppidlLast; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  void *ppv[2]; // [rsp+40h] [rbp-C0h] BYREF
  STRRET pstr; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v14[264]; // [rsp+160h] [rbp+60h] BYREF

  ppv[0] = 0;
  ppidlLast = 0;
  PathFromAbsPidl = SHBindToParent(a2, &GUID_000214e6_0000_0000_c000_000000000046, ppv, &ppidlLast);
  memset_0(&pstr, 0, sizeof(pstr));
  if ( PathFromAbsPidl >= 0 )
  {
    PathFromAbsPidl = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, _QWORD, STRRET *))(*(_QWORD *)ppv[0] + 88LL))(
                        ppv[0],
                        ppidlLast,
                        0,
                        &pstr);
    if ( PathFromAbsPidl >= 0 )
    {
      PathFromAbsPidl = StrRetToBufW(&pstr, ppidlLast, a3, 0x104u);
      if ( PathFromAbsPidl >= 0 )
      {
        if ( IsUserAnAdmin() )
        {
          pv = 0;
          PathFromAbsPidl = CShellWrappers::GetPathFromAbsPidl(
                              v8,
                              (const struct _ITEMIDLIST_ABSOLUTE *)a2,
                              (unsigned __int16 **)&pv);
          if ( PathFromAbsPidl >= 0 )
          {
            if ( a4 )
            {
              PathFromAbsPidl = CShellWrappers::GetUserNameW((PCWSTR)pv, v14);
              if ( PathFromAbsPidl )
              {
                PathFromAbsPidl = 0;
              }
              else
              {
                StringCchCatW(a3, 0x104u, L" (");
                StringCchCatW(a3, 0x104u, v14);
                StringCchCatW(a3, 0x104u, L")");
              }
              CoTaskMemFree(pv);
            }
          }
        }
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)ppv);
  return (unsigned int)PathFromAbsPidl;
}

```

## disassembly

```asm
0x18002cda8  mov     [rsp-8+arg_0], rbx
0x18002cdad  push    rbp
0x18002cdae  push    rsi
0x18002cdaf  push    rdi
0x18002cdb0  push    r12
0x18002cdb2  push    r14
0x18002cdb4  lea     rbp, [rsp-280h]
0x18002cdbc  sub     rsp, 380h
0x18002cdc3  mov     rax, cs:__security_cookie
0x18002cdca  xor     rax, rsp
0x18002cdcd  mov     [rbp+2A0h+var_30], rax
0x18002cdd4  mov     r14d, r9d
0x18002cdd7  mov     rdi, r8
0x18002cdda  mov     rsi, rdx
0x18002cddd  mov     [rsp+3A0h+ppv], 0
0x18002cde6  mov     [rsp+3A0h+ppidlLast], 0
0x18002cdef  lea     r9, [rsp+3A0h+ppidlLast]; ppidlLast
0x18002cdf4  lea     r8, [rsp+3A0h+ppv]; ppv
0x18002cdf9  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002ce00  mov     rcx, rsi; pidl
0x18002ce03  call    cs:__imp_SHBindToParent
0x18002ce09  mov     ebx, eax
0x18002ce0b  xor     edx, edx; Val
0x18002ce0d  mov     r8d, 110h; Size
0x18002ce13  lea     rcx, [rsp+3A0h+pstr]; void *
0x18002ce18  call    memset_0
0x18002ce1d  test    ebx, ebx
0x18002ce1f  js      loc_18002CEF5
0x18002ce25  mov     rcx, [rsp+3A0h+ppv]
0x18002ce2a  mov     rax, [rcx]
0x18002ce2d  lea     r9, [rsp+3A0h+pstr]
0x18002ce32  xor     r8d, r8d
0x18002ce35  mov     rdx, [rsp+3A0h+ppidlLast]
0x18002ce3a  mov     rax, [rax+58h]
0x18002ce3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce43  mov     ebx, eax
0x18002ce45  test    eax, eax
0x18002ce47  js      loc_18002CEF5
0x18002ce4d  mov     r12d, 104h
0x18002ce53  mov     r9d, r12d; cchBuf
0x18002ce56  mov     r8, rdi; pszBuf
0x18002ce59  mov     rdx, [rsp+3A0h+ppidlLast]; pidl
0x18002ce5e  lea     rcx, [rsp+3A0h+pstr]; pstr
0x18002ce63  call    cs:__imp_StrRetToBufW
0x18002ce69  mov     ebx, eax
0x18002ce6b  test    eax, eax
0x18002ce6d  js      loc_18002CEF5
0x18002ce73  call    cs:__imp_IsUserAnAdmin
0x18002ce79  test    eax, eax
0x18002ce7b  jz      short loc_18002CEF5
0x18002ce7d  mov     [rsp+3A0h+pv], 0
0x18002ce86  lea     r8, [rsp+3A0h+pv]; unsigned __int16 **
0x18002ce8b  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x18002ce8e  call    ?GetPathFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAG@Z; CShellWrappers::GetPathFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort * *)
0x18002ce93  mov     ebx, eax
0x18002ce95  test    eax, eax
0x18002ce97  js      short loc_18002CEF5
0x18002ce99  test    r14d, r14d
0x18002ce9c  jz      short loc_18002CEF5
0x18002ce9e  lea     rdx, [rbp+2A0h+var_240]; unsigned __int16 *
0x18002cea2  mov     rcx, [rsp+3A0h+pv]; pszFirst
0x18002cea7  call    ?GetUserNameW@CShellWrappers@@SAJPEBGPEAG@Z; CShellWrappers::GetUserNameW(ushort const *,ushort *)
0x18002ceac  mov     ebx, eax
0x18002ceae  test    eax, eax
0x18002ceb0  jnz     short loc_18002CEE7
0x18002ceb2  lea     r8, asc_180038614; " ("
0x18002ceb9  mov     edx, r12d; unsigned __int64
0x18002cebc  mov     rcx, rdi; unsigned __int16 *
0x18002cebf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002cec4  lea     r8, [rbp+2A0h+var_240]; unsigned __int16 *
0x18002cec8  mov     edx, r12d; unsigned __int64
0x18002cecb  mov     rcx, rdi; unsigned __int16 *
0x18002cece  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002ced3  lea     r8, asc_180038610; ")"
0x18002ceda  mov     edx, r12d; unsigned __int64
0x18002cedd  mov     rcx, rdi; unsigned __int16 *
0x18002cee0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002cee5  jmp     short loc_18002CEE9
0x18002cee7  xor     ebx, ebx
0x18002cee9  mov     rcx, [rsp+3A0h+pv]; pv
0x18002ceee  call    cs:__imp_CoTaskMemFree
0x18002cef4  nop
0x18002cef5  lea     rcx, [rsp+3A0h+ppv]
0x18002cefa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ceff  mov     eax, ebx
0x18002cf01  mov     rcx, [rbp+2A0h+var_30]
0x18002cf08  xor     rcx, rsp; StackCookie
0x18002cf0b  call    __security_check_cookie
0x18002cf10  mov     rbx, [rsp+3A0h+arg_0]
0x18002cf18  add     rsp, 380h
0x18002cf1f  pop     r14
0x18002cf21  pop     r12
0x18002cf23  pop     rdi
0x18002cf24  pop     rsi
0x18002cf25  pop     rbp
0x18002cf26  retn
```
