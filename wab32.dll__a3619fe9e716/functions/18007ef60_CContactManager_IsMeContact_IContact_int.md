# CContactManager::IsMeContact(IContact *,int *)

- ea: `0x18007ef60`
- end: `0x18007f19c`
- name: `?IsMeContact@CContactManager@@UEAAJPEAUIContact@@PEAH@Z`
- size: `572`
- prototype: `int(CContactManager *__hidden this, struct IContact *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f74`
- `0x18007ef60`
- `0x18007fc6c`
- `0x1800840a4`
- `0x1800861e0`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x18007f074`
- `SHLWAPI!StrCmpIW` at `0x18007f125`
- `SHLWAPI!StrCmpIW` at `0x18007f074`
- `SHLWAPI!StrCmpIW` at `0x18007f125`
- `SHLWAPI!PathFileExistsW` at `0x18007f0ac`
- `SHLWAPI!PathFileExistsW` at `0x18007f0ac`
- `KERNEL32!GetCurrentThreadId` at `0x18007efdb`
- `KERNEL32!GetCurrentThreadId` at `0x18007efdb`

## string_xrefs

- `0x18007f08e`: `/PATH:`

## pseudocode

```c
__int64 __fastcall CContactManager::IsMeContact(CContactManager *this, struct IContact *a2, int *a3)
{
  int MeContactID; // ebx
  const WCHAR *v7; // rsi
  WCHAR *v8; // rbx
  const WCHAR *v9; // rdx
  const WCHAR *v10; // rcx
  const WCHAR *v11; // rdx
  struct IContact *v13; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v14; // [rsp+28h] [rbp-D8h] BYREF
  PCWSTR psz1[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR psz2[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR pszPath[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v20[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v21[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v22[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v13 = 0;
  STRW::STRW((STRW *)&v14, v20, 0x104u);
  STRW::STRW((STRW *)&v16, v21, 0x104u);
  STRW::STRW((STRW *)&v18, v22, 0x104u);
  if ( GetCurrentThreadId() == *((_DWORD *)this + 2) )
  {
    if ( !a2 || !a3 )
    {
      MeContactID = -2147024809;
      goto LABEL_30;
    }
    *a3 = 0;
    if ( !*((_DWORD *)this + 3) )
    {
      MeContactID = -2147418113;
      goto LABEL_30;
    }
    MeContactID = CContactManager::_GetMeContactID((CContactManager *)((char *)this - 32), (struct STRW *)&v14);
    if ( MeContactID < 0 )
      goto LABEL_30;
    if ( !v14 )
    {
LABEL_9:
      *a3 = 0;
LABEL_10:
      MeContactID = 0;
      goto LABEL_30;
    }
    MeContactID = EasyGetContactID(a2, (struct STRW *)&v16);
    if ( MeContactID < 0 )
      goto LABEL_30;
    v7 = &Str;
    v8 = (WCHAR *)psz1[0];
    v9 = &Str;
    if ( v16 )
      v9 = psz2[0];
    if ( StrCmpIW(psz1[0], v9) )
    {
      if ( (int)CContactID::FindToken(v8, L"/PATH:", (struct STRW *)&v18) < 0 )
        goto LABEL_9;
      v10 = &Str;
      if ( v18 )
        v10 = pszPath[0];
      if ( PathFileExistsW(v10) )
        goto LABEL_10;
      if ( (*(int (__fastcall **)(CContactManager *, struct IContact **))(*(_QWORD *)this + 48LL))(this, &v13) < 0
        || !v13 )
      {
        goto LABEL_9;
      }
      memset_0(v8, 0, 2LL * v14);
      v14 = 0;
      MeContactID = EasyGetContactID(v13, (struct STRW *)&v14);
      if ( MeContactID < 0 )
        goto LABEL_30;
      v11 = &Str;
      if ( v16 )
        v11 = psz2[0];
      if ( v14 )
        v7 = psz1[0];
      if ( StrCmpIW(v7, v11) )
        goto LABEL_10;
    }
    *a3 = 1;
    goto LABEL_10;
  }
  MeContactID = -2147417842;
LABEL_30:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v13);
  v18 = 0;
  BUFFER::ReleaseStorage((BUFFER *)pszPath);
  v16 = 0;
  BUFFER::ReleaseStorage((BUFFER *)psz2);
  v14 = 0;
  BUFFER::ReleaseStorage((BUFFER *)psz1);
  return (unsigned int)MeContactID;
}

```

## disassembly

```asm
0x18007ef60  mov     [rsp-8+arg_18], rbx
0x18007ef65  push    rbp
0x18007ef66  push    rsi
0x18007ef67  push    rdi
0x18007ef68  push    r13
0x18007ef6a  push    r15
0x18007ef6c  lea     rbp, [rsp-5D0h]
0x18007ef74  sub     rsp, 6D0h
0x18007ef7b  mov     rax, cs:__security_cookie
0x18007ef82  xor     rax, rsp
0x18007ef85  mov     [rbp+5F0h+var_30], rax
0x18007ef8c  mov     rdi, r8
0x18007ef8f  mov     r15, rcx
0x18007ef92  mov     ebx, 104h
0x18007ef97  lea     rcx, [rsp+6F0h+var_6C8]; this
0x18007ef9c  mov     rsi, rdx
0x18007ef9f  xor     r13d, r13d
0x18007efa2  mov     r8d, ebx; unsigned int
0x18007efa5  mov     [rsp+6F0h+var_6D0], r13
0x18007efaa  lea     rdx, [rbp+5F0h+var_660]; unsigned __int16 *
0x18007efae  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18007efb3  mov     r8d, ebx; unsigned int
0x18007efb6  lea     rcx, [rsp+6F0h+var_6A8]; this
0x18007efbb  lea     rdx, [rbp+5F0h+var_450]; unsigned __int16 *
0x18007efc2  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18007efc7  mov     r8d, ebx; unsigned int
0x18007efca  lea     rcx, [rsp+6F0h+var_688]; this
0x18007efcf  lea     rdx, [rbp+5F0h+var_240]; unsigned __int16 *
0x18007efd6  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18007efdb  call    cs:__imp_GetCurrentThreadId
0x18007efe1  cmp     eax, [r15+8]
0x18007efe5  jz      short loc_18007EFF1
0x18007efe7  mov     ebx, 8001010Eh
0x18007efec  jmp     loc_18007F13D
0x18007eff1  test    rsi, rsi
0x18007eff4  jz      loc_18007F138
0x18007effa  test    rdi, rdi
0x18007effd  jz      loc_18007F138
0x18007f003  mov     [rdi], r13d
0x18007f006  cmp     [r15+0Ch], r13d
0x18007f00a  jnz     short loc_18007F016
0x18007f00c  mov     ebx, 8000FFFFh
0x18007f011  jmp     loc_18007F13D
0x18007f016  lea     rdx, [rsp+6F0h+var_6C8]; struct STRW *
0x18007f01b  lea     rcx, [r15-20h]; this
0x18007f01f  call    ?_GetMeContactID@CContactManager@@AEAAJPEAVSTRW@@@Z; CContactManager::_GetMeContactID(STRW *)
0x18007f024  mov     ebx, eax
0x18007f026  test    eax, eax
0x18007f028  js      loc_18007F13D
0x18007f02e  cmp     [rsp+6F0h+var_6C8], r13d
0x18007f033  jnz     short loc_18007F040
0x18007f035  mov     [rdi], r13d
0x18007f038  mov     ebx, r13d
0x18007f03b  jmp     loc_18007F13D
0x18007f040  lea     rdx, [rsp+6F0h+var_6A8]; struct STRW *
0x18007f045  mov     rcx, rsi; struct IContact *
0x18007f048  call    ?EasyGetContactID@@YAJPEAUIContact@@PEAVSTRW@@@Z; EasyGetContactID(IContact *,STRW *)
0x18007f04d  mov     ebx, eax
0x18007f04f  test    eax, eax
0x18007f051  js      loc_18007F13D
0x18007f057  cmp     [rsp+6F0h+var_6A8], r13d
0x18007f05c  lea     rsi, Str
0x18007f063  mov     rbx, [rsp+6F0h+psz1]
0x18007f068  mov     rdx, rsi
0x18007f06b  cmovnz  rdx, [rsp+6F0h+psz2]; psz2
0x18007f071  mov     rcx, rbx; psz1
0x18007f074  call    cs:__imp_StrCmpIW
0x18007f07a  test    eax, eax
0x18007f07c  jnz     short loc_18007F086
0x18007f07e  mov     dword ptr [rdi], 1
0x18007f084  jmp     short loc_18007F038
0x18007f086  lea     r8, [rsp+6F0h+var_688]; this
0x18007f08b  mov     rcx, rbx; psz1
0x18007f08e  lea     rdx, aPath; "/PATH:"
0x18007f095  call    ?FindToken@CContactID@@SAJPEBG0PEAVSTRW@@@Z; CContactID::FindToken(ushort const *,ushort const *,STRW *)
0x18007f09a  test    eax, eax
0x18007f09c  js      short loc_18007F035
0x18007f09e  cmp     [rsp+6F0h+var_688], r13d
0x18007f0a3  mov     rcx, rsi
0x18007f0a6  cmovnz  rcx, [rsp+6F0h+pszPath]; pszPath
0x18007f0ac  call    cs:__imp_PathFileExistsW
0x18007f0b2  test    eax, eax
0x18007f0b4  jnz     short loc_18007F038
0x18007f0b6  mov     rax, [r15]
0x18007f0b9  lea     rdx, [rsp+6F0h+var_6D0]
0x18007f0be  mov     rcx, r15
0x18007f0c1  mov     rax, [rax+30h]
0x18007f0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0ca  test    eax, eax
0x18007f0cc  js      loc_18007F035
0x18007f0d2  cmp     [rsp+6F0h+var_6D0], r13
0x18007f0d7  jz      loc_18007F035
0x18007f0dd  mov     r8d, [rsp+6F0h+var_6C8]
0x18007f0e2  xor     edx, edx; Val
0x18007f0e4  add     r8, r8; Size
0x18007f0e7  mov     rcx, rbx; void *
0x18007f0ea  call    memset_0
0x18007f0ef  mov     rcx, [rsp+6F0h+var_6D0]; struct IContact *
0x18007f0f4  lea     rdx, [rsp+6F0h+var_6C8]; struct STRW *
0x18007f0f9  mov     [rsp+6F0h+var_6C8], r13d
0x18007f0fe  call    ?EasyGetContactID@@YAJPEAUIContact@@PEAVSTRW@@@Z; EasyGetContactID(IContact *,STRW *)
0x18007f103  mov     ebx, eax
0x18007f105  test    eax, eax
0x18007f107  js      short loc_18007F13D
0x18007f109  cmp     [rsp+6F0h+var_6A8], r13d
0x18007f10e  mov     rdx, rsi
0x18007f111  cmovnz  rdx, [rsp+6F0h+psz2]; psz2
0x18007f117  cmp     [rsp+6F0h+var_6C8], r13d
0x18007f11c  cmovnz  rsi, [rsp+6F0h+psz1]
0x18007f122  mov     rcx, rsi; psz1
0x18007f125  call    cs:__imp_StrCmpIW
0x18007f12b  test    eax, eax
0x18007f12d  jnz     loc_18007F038
0x18007f133  jmp     loc_18007F07E
0x18007f138  mov     ebx, 80070057h
0x18007f13d  lea     rcx, [rsp+6F0h+var_6D0]
0x18007f142  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007f147  lea     rcx, [rsp+6F0h+pszPath]; this
0x18007f14c  mov     [rsp+6F0h+var_688], r13d
0x18007f151  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18007f156  lea     rcx, [rsp+6F0h+psz2]; this
0x18007f15b  mov     [rsp+6F0h+var_6A8], r13d
0x18007f160  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18007f165  lea     rcx, [rsp+6F0h+psz1]; this
0x18007f16a  mov     [rsp+6F0h+var_6C8], r13d
0x18007f16f  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18007f174  mov     eax, ebx
0x18007f176  mov     rcx, [rbp+5F0h+var_30]
0x18007f17d  xor     rcx, rsp; StackCookie
0x18007f180  call    __security_check_cookie
0x18007f185  mov     rbx, [rsp+6F0h+arg_18]
0x18007f18d  add     rsp, 6D0h
0x18007f194  pop     r15
0x18007f196  pop     r13
0x18007f198  pop     rdi
0x18007f199  pop     rsi
0x18007f19a  pop     rbp
0x18007f19b  retn
```
