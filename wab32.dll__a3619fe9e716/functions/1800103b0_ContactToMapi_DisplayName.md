# _ContactToMapi_DisplayName

- ea: `0x1800103b0`
- end: `0x18001056b`
- name: `_ContactToMapi_DisplayName`
- size: `443`
- prototype: `__int64 __fastcall(struct IContactProperties *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f74`
- `0x1800103b0`
- `0x180010890`
- `0x180013950`
- `0x180045494`
- `0x180079f40`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18001049e`
- `SHLWAPI!PathFindExtensionW` at `0x18001049e`
- `SHLWAPI!PathFindFileNameW` at `0x18001048a`
- `SHLWAPI!PathFindFileNameW` at `0x18001048a`
- `KERNEL32!LocalFree` at `0x1800104f2`
- `KERNEL32!LocalFree` at `0x1800104f2`

## pseudocode

```c
__int64 __fastcall ContactToMapi_DisplayName(struct IContactProperties *a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  int v7; // ebx
  const WCHAR *v8; // rdi
  const WCHAR *v9; // rcx
  const unsigned __int16 *FileNameW; // rsi
  LPWSTR ExtensionW; // rbx
  void *v12; // rcx
  struct IContact *v14; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v15; // [rsp+28h] [rbp-D8h] BYREF
  void *v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR pszPath[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v19[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v20[264]; // [rsp+280h] [rbp+180h] BYREF

  STRW::STRW((STRW *)&v15, v19, 0x104u);
  STRW::STRW((STRW *)&v17, v20, 0x104u);
  v14 = 0;
  v6 = ContactToMapi_LabeledString(a1);
  if ( v6 == -2147024893 )
  {
    v6 = ((__int64 (__fastcall *)(struct IContactProperties *, GUID *, struct IContact **))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_f941b671_bda7_4f77_884a_f46462f226a7,
           &v14);
    if ( v6 >= 0 )
    {
      if ( GetPathFromContact(v14, (struct STRW *)&v17) >= 0 )
      {
        v7 = v17;
        v8 = &Str;
        v9 = &Str;
        if ( v17 )
          v9 = pszPath[0];
        FileNameW = PathFindFileNameW(v9);
        if ( v7 )
          v8 = pszPath[0];
        ExtensionW = PathFindExtensionW(v8);
        memset_0(v16, 0, 2LL * v15);
        v15 = 0;
        v6 = STRW::Append((STRW *)&v15, FileNameW, ExtensionW - FileNameW);
        if ( v6 >= 0 )
        {
          v12 = *(void **)(a2 + 8);
          *(_DWORD *)a2 = *(_DWORD *)(a3 + 24);
          if ( v12 )
          {
            LocalFree(v12);
            *(_QWORD *)(a2 + 8) = 0;
          }
          v6 = LocalAllocFromSTRW((unsigned __int16 **)(a2 + 8), (const struct STRW *)&v15);
          if ( v6 >= 0 )
            v6 = 0;
        }
      }
      else
      {
        v6 = -2147024893;
      }
    }
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v14);
  v17 = 0;
  BUFFER::ReleaseStorage((BUFFER *)pszPath);
  v15 = 0;
  BUFFER::ReleaseStorage((BUFFER *)&v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800103b0  mov     [rsp-8+arg_18], rbx
0x1800103b5  push    rbp
0x1800103b6  push    rsi
0x1800103b7  push    rdi
0x1800103b8  push    r14
0x1800103ba  push    r15
0x1800103bc  lea     rbp, [rsp-3A0h]
0x1800103c4  sub     rsp, 4A0h
0x1800103cb  mov     rax, cs:__security_cookie
0x1800103d2  xor     rax, rsp
0x1800103d5  mov     [rbp+3C0h+var_30], rax
0x1800103dc  mov     r15, r8
0x1800103df  mov     rdi, rcx
0x1800103e2  mov     ebx, 104h
0x1800103e7  lea     rcx, [rsp+4C0h+var_498]; this
0x1800103ec  mov     r14, rdx
0x1800103ef  mov     r8d, ebx; unsigned int
0x1800103f2  lea     rdx, [rsp+4C0h+var_450]; unsigned __int16 *
0x1800103f7  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x1800103fc  mov     r8d, ebx; unsigned int
0x1800103ff  lea     rcx, [rsp+4C0h+var_478]; this
0x180010404  lea     rdx, [rbp+3C0h+var_240]; unsigned __int16 *
0x18001040b  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180010410  mov     r8, r15
0x180010413  mov     [rsp+4C0h+var_4A0], 0
0x18001041c  mov     rcx, rdi; struct IContactProperties *
0x18001041f  mov     rdx, r14
0x180010422  call    _ContactToMapi_LabeledString
0x180010427  mov     esi, 80070003h
0x18001042c  mov     ebx, eax
0x18001042e  cmp     eax, esi
0x180010430  jnz     loc_180010515
0x180010436  mov     rax, [rdi]
0x180010439  lea     r8, [rsp+4C0h+var_4A0]
0x18001043e  lea     rdx, _GUID_f941b671_bda7_4f77_884a_f46462f226a7
0x180010445  mov     rcx, rdi
0x180010448  mov     rax, [rax]
0x18001044b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010450  mov     ebx, eax
0x180010452  test    eax, eax
0x180010454  js      loc_180010515
0x18001045a  mov     rcx, [rsp+4C0h+var_4A0]; struct IContact *
0x18001045f  lea     rdx, [rsp+4C0h+var_478]; struct STRW *
0x180010464  call    ?GetPathFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetPathFromContact(IContact *,STRW *)
0x180010469  test    eax, eax
0x18001046b  jns     short loc_180010474
0x18001046d  mov     ebx, esi
0x18001046f  jmp     loc_180010515
0x180010474  mov     ebx, [rsp+4C0h+var_478]
0x180010478  lea     rdi, Str
0x18001047f  test    ebx, ebx
0x180010481  mov     rcx, rdi
0x180010484  cmovnz  rcx, [rsp+4C0h+pszPath]; pszPath
0x18001048a  call    cs:__imp_PathFindFileNameW
0x180010490  test    ebx, ebx
0x180010492  mov     rsi, rax
0x180010495  cmovnz  rdi, [rsp+4C0h+pszPath]
0x18001049b  mov     rcx, rdi; pszPath
0x18001049e  call    cs:__imp_PathFindExtensionW
0x1800104a4  mov     r8d, [rsp+4C0h+var_498]
0x1800104a9  xor     edx, edx; Val
0x1800104ab  mov     rcx, [rsp+4C0h+var_490]; void *
0x1800104b0  add     r8, r8; Size
0x1800104b3  mov     rbx, rax
0x1800104b6  call    memset_0
0x1800104bb  sub     rbx, rsi
0x1800104be  mov     [rsp+4C0h+var_498], 0
0x1800104c6  sar     rbx, 1
0x1800104c9  lea     rcx, [rsp+4C0h+var_498]; this
0x1800104ce  mov     r8, rbx; unsigned __int64
0x1800104d1  mov     rdx, rsi; unsigned __int16 *
0x1800104d4  call    ?Append@STRW@@QEAAJPEBG_K@Z; STRW::Append(ushort const *,unsigned __int64)
0x1800104d9  mov     ebx, eax
0x1800104db  test    eax, eax
0x1800104dd  js      short loc_180010515
0x1800104df  mov     eax, [r15+18h]
0x1800104e3  lea     rbx, [r14+8]
0x1800104e7  mov     rcx, [rbx]; hMem
0x1800104ea  mov     [r14], eax
0x1800104ed  test    rcx, rcx
0x1800104f0  jz      short loc_1800104FF
0x1800104f2  call    cs:__imp_LocalFree
0x1800104f8  mov     qword ptr [rbx], 0
0x1800104ff  lea     rdx, [rsp+4C0h+var_498]; struct STRW *
0x180010504  mov     rcx, rbx; unsigned __int16 **
0x180010507  call    ?LocalAllocFromSTRW@@YAJPEAPEAGPEBVSTRW@@@Z; LocalAllocFromSTRW(ushort * *,STRW const *)
0x18001050c  mov     ebx, eax
0x18001050e  xor     eax, eax
0x180010510  test    ebx, ebx
0x180010512  cmovns  ebx, eax
0x180010515  lea     rcx, [rsp+4C0h+var_4A0]
0x18001051a  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18001051f  lea     rcx, [rsp+4C0h+pszPath]; this
0x180010524  mov     [rsp+4C0h+var_478], 0
0x18001052c  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180010531  lea     rcx, [rsp+4C0h+var_490]; this
0x180010536  mov     [rsp+4C0h+var_498], 0
0x18001053e  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180010543  mov     eax, ebx
0x180010545  mov     rcx, [rbp+3C0h+var_30]
0x18001054c  xor     rcx, rsp; StackCookie
0x18001054f  call    __security_check_cookie
0x180010554  mov     rbx, [rsp+4C0h+arg_18]
0x18001055c  add     rsp, 4A0h
0x180010563  pop     r15
0x180010565  pop     r14
0x180010567  pop     rdi
0x180010568  pop     rsi
0x180010569  pop     rbp
0x18001056a  retn
```
