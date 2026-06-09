# GetDisplayNameFromContact(IContact *,STRW *)

- ea: `0x1800133d0`
- end: `0x18001359f`
- name: `?GetDisplayNameFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(struct IContact *, struct STRW *)`
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180008fa0`
- `0x1800094b4`
- `0x180012d08`
- `0x18003d2e8`
- `0x180058d50`

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f74`
- `0x180009aec`
- `0x1800133d0`
- `0x1800137a0`
- `0x180013950`
- `0x180079f40`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x1800134d5`
- `SHLWAPI!PathFindExtensionW` at `0x1800134d5`
- `SHLWAPI!PathFindFileNameW` at `0x1800134c1`
- `SHLWAPI!PathFindFileNameW` at `0x1800134c1`
- `USER32!LoadStringW` at `0x180013583`
- `USER32!LoadStringW` at `0x180013583`

## pseudocode

```c
__int64 __fastcall GetDisplayNameFromContact(struct IContact *a1, void **a2)
{
  struct IContactVtbl *lpVtbl; // rax
  int LabeledString; // ebx
  int v6; // ebx
  const WCHAR *v7; // rdi
  const WCHAR *v8; // rcx
  const unsigned __int16 *FileNameW; // rsi
  LPWSTR ExtensionW; // rbx
  bool v11; // sf
  HINSTANCE v13; // rcx
  struct IContactProperties *v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR pszPath[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v18[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(Buffer, 0, 0x208u);
  STRW::STRW((STRW *)&v15, v18, 0x104u);
  lpVtbl = a1->lpVtbl;
  v14 = 0;
  LabeledString = ((__int64 (__fastcall *)(struct IContact *, GUID *, struct IContactProperties **))lpVtbl->QueryInterface)(
                    a1,
                    &GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f,
                    &v14);
  if ( LabeledString < 0 )
    goto LABEL_12;
  LabeledString = GetLabeledString(v14, L"NameCollection", L"/FormattedName", 0, 0, (struct STRW *)a2, 0);
  if ( LabeledString != -2147024893 )
    goto LABEL_9;
  if ( GetPathFromContact(a1, (struct STRW *)&v15) >= 0 )
  {
    v6 = v15;
    v7 = &Str;
    v8 = &Str;
    if ( v15 )
      v8 = pszPath[0];
    FileNameW = PathFindFileNameW(v8);
    if ( v6 )
      v7 = pszPath[0];
    ExtensionW = PathFindExtensionW(v7);
    memset_0(a2[1], 0, 2LL * *(unsigned int *)a2);
    *(_DWORD *)a2 = 0;
    LabeledString = STRW::Append((STRW *)a2, FileNameW, ExtensionW - FileNameW);
LABEL_9:
    v11 = LabeledString < 0;
    goto LABEL_10;
  }
  memset_0(a2[1], 0, 2LL * *(unsigned int *)a2);
  v13 = hinstMapiX;
  *(_DWORD *)a2 = 0;
  LoadStringW(v13, 0x38u, Buffer, 260);
  LabeledString = STRW::Append((STRW *)a2, Buffer);
  v11 = LabeledString < 0;
LABEL_10:
  if ( !v11 )
    LabeledString = 0;
LABEL_12:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v14);
  v15 = 0;
  BUFFER::ReleaseStorage((BUFFER *)pszPath);
  return (unsigned int)LabeledString;
}

```

## disassembly

```asm
0x1800133d0  mov     [rsp-8+arg_10], rbx
0x1800133d5  mov     [rsp-8+arg_18], rsi
0x1800133da  push    rbp
0x1800133db  push    rdi
0x1800133dc  push    r14
0x1800133de  lea     rbp, [rsp-3A0h]
0x1800133e6  sub     rsp, 4A0h
0x1800133ed  mov     rax, cs:__security_cookie
0x1800133f4  xor     rax, rsp
0x1800133f7  mov     [rbp+3B0h+var_20], rax
0x1800133fe  mov     r14, rdx
0x180013401  mov     rdi, rcx
0x180013404  xor     edx, edx; Val
0x180013406  lea     rcx, [rsp+4B0h+Buffer]; void *
0x18001340b  mov     r8d, 208h; Size
0x180013411  call    memset_0
0x180013416  mov     esi, 104h
0x18001341b  lea     rdx, [rbp+3B0h+var_230]; unsigned __int16 *
0x180013422  mov     r8d, esi; unsigned int
0x180013425  lea     rcx, [rsp+4B0h+var_468]; this
0x18001342a  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18001342f  mov     rax, [rdi]
0x180013432  lea     r8, [rsp+4B0h+var_470]
0x180013437  lea     rdx, _GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f
0x18001343e  mov     [rsp+4B0h+var_470], 0
0x180013447  mov     rcx, rdi
0x18001344a  mov     rax, [rax]
0x18001344d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013452  mov     ebx, eax
0x180013454  test    eax, eax
0x180013456  js      loc_180013512
0x18001345c  mov     rcx, [rsp+4B0h+var_470]; struct IContactProperties *
0x180013461  lea     r8, aFormattedname; "/FormattedName"
0x180013468  mov     [rsp+4B0h+var_480], 0; struct CLabelCollection **
0x180013471  lea     rdx, aNamecollection; "NameCollection"
0x180013478  mov     [rsp+4B0h+var_488], r14; struct STRW *
0x18001347d  xor     r9d, r9d; unsigned __int16 **
0x180013480  mov     [rsp+4B0h+var_490], 0; unsigned int
0x180013488  call    ?GetLabeledString@@YAJPEAUIContactProperties@@PEBG1PEAPEBGKPEAVSTRW@@PEAPEAVCLabelCollection@@@Z; GetLabeledString(IContactProperties *,ushort const *,ushort const *,ushort const * *,ulong,STRW *,CLabelCollection * *)
0x18001348d  mov     ebx, eax
0x18001348f  cmp     eax, 80070003h
0x180013494  jnz     short loc_18001350C
0x180013496  lea     rdx, [rsp+4B0h+var_468]; struct STRW *
0x18001349b  mov     rcx, rdi; struct IContact *
0x18001349e  call    ?GetPathFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetPathFromContact(IContact *,STRW *)
0x1800134a3  test    eax, eax
0x1800134a5  js      loc_180013557
0x1800134ab  mov     ebx, [rsp+4B0h+var_468]
0x1800134af  lea     rdi, Str
0x1800134b6  test    ebx, ebx
0x1800134b8  mov     rcx, rdi
0x1800134bb  cmovnz  rcx, [rsp+4B0h+pszPath]; pszPath
0x1800134c1  call    cs:__imp_PathFindFileNameW
0x1800134c7  test    ebx, ebx
0x1800134c9  mov     rsi, rax
0x1800134cc  cmovnz  rdi, [rsp+4B0h+pszPath]
0x1800134d2  mov     rcx, rdi; pszPath
0x1800134d5  call    cs:__imp_PathFindExtensionW
0x1800134db  mov     r8d, [r14]
0x1800134de  xor     edx, edx; Val
0x1800134e0  mov     rcx, [r14+8]; void *
0x1800134e4  add     r8, r8; Size
0x1800134e7  mov     rbx, rax
0x1800134ea  call    memset_0
0x1800134ef  sub     rbx, rsi
0x1800134f2  mov     dword ptr [r14], 0
0x1800134f9  sar     rbx, 1
0x1800134fc  mov     rdx, rsi; unsigned __int16 *
0x1800134ff  mov     r8, rbx; unsigned __int64
0x180013502  mov     rcx, r14; this
0x180013505  call    ?Append@STRW@@QEAAJPEBG_K@Z; STRW::Append(ushort const *,unsigned __int64)
0x18001350a  mov     ebx, eax
0x18001350c  test    ebx, ebx
0x18001350e  js      short loc_180013512
0x180013510  xor     ebx, ebx
0x180013512  lea     rcx, [rsp+4B0h+var_470]
0x180013517  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18001351c  lea     rcx, [rsp+4B0h+pszPath]; this
0x180013521  mov     [rsp+4B0h+var_468], 0
0x180013529  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18001352e  mov     eax, ebx
0x180013530  mov     rcx, [rbp+3B0h+var_20]
0x180013537  xor     rcx, rsp; StackCookie
0x18001353a  call    __security_check_cookie
0x18001353f  lea     r11, [rsp+4B0h+var_10]
0x180013547  mov     rbx, [r11+30h]
0x18001354b  mov     rsi, [r11+38h]
0x18001354f  mov     rsp, r11
0x180013552  pop     r14
0x180013554  pop     rdi
0x180013555  pop     rbp
0x180013556  retn
0x180013557  mov     r8d, [r14]
0x18001355a  xor     edx, edx; Val
0x18001355c  mov     rcx, [r14+8]; void *
0x180013560  add     r8, r8; Size
0x180013563  call    memset_0
0x180013568  mov     rcx, cs:hinstMapiX; hInstance
0x18001356f  lea     r8, [rsp+4B0h+Buffer]; lpBuffer
0x180013574  mov     r9d, esi; cchBufferMax
0x180013577  mov     dword ptr [r14], 0
0x18001357e  mov     edx, 38h ; '8'; uID
0x180013583  call    cs:__imp_LoadStringW
0x180013589  lea     rdx, [rsp+4B0h+Buffer]; unsigned __int16 *
0x18001358e  mov     rcx, r14; this
0x180013591  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180013596  mov     ebx, eax
0x180013598  test    eax, eax
0x18001359a  jmp     loc_18001350E
```
