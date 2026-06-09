# CContactManager::_GetMeContact(IContact * *)

- ea: `0x18007fa4c`
- end: `0x18007fc65`
- name: `?_GetMeContact@CContactManager@@AEAAJPEAPEAUIContact@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(CContactManager *__hidden this, struct IContact **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18007ed40`

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f74`
- `0x18007fa4c`
- `0x18007fc6c`
- `0x18007fd24`
- `0x18007ff08`
- `0x1800805ec`
- `0x1800840a4`
- `0x1800861e0`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x18007fbd8`
- `SHLWAPI!StrCmpIW` at `0x18007fbd8`
- `KERNEL32!GetCurrentThreadId` at `0x18007fac7`
- `KERNEL32!GetCurrentThreadId` at `0x18007fac7`

## string_xrefs

- `0x18007fb8d`: `/PATH:`

## pseudocode

```c
__int64 __fastcall CContactManager::_GetMeContact(CContactManager *this, struct IContact **a2)
{
  int v4; // ebx
  struct IContact *v5; // r15
  int MeContactID; // ebx
  int v7; // esi
  const WCHAR *v8; // rsi
  const WCHAR *v9; // rcx
  WCHAR *v10; // rdx
  struct IContact *v12; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+28h] [rbp-D8h] BYREF
  PCWSTR psz1[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR psz2[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *Path; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v19[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v20[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v21[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  STRW::STRW((STRW *)&v15, v19, 0x104u);
  STRW::STRW((STRW *)&v13, v20, 0x104u);
  STRW::STRW((STRW *)&v17, v21, 0x104u);
  v4 = *((_DWORD *)this + 10);
  v5 = 0;
  v12 = 0;
  if ( GetCurrentThreadId() != v4 )
  {
    MeContactID = -2147417842;
    goto LABEL_27;
  }
  if ( !a2 )
  {
    MeContactID = -2147024809;
    goto LABEL_27;
  }
  if ( !*((_DWORD *)this + 11) )
  {
    MeContactID = -2147418113;
    goto LABEL_27;
  }
  *a2 = 0;
  MeContactID = CContactManager::_GetMeContactID(this, (struct STRW *)&v15);
  if ( MeContactID < 0 )
    goto LABEL_27;
  if ( !v15 )
    goto LABEL_25;
  v7 = CContactManager::_Load(this, psz2[0], &v12, 1);
  if ( v7 < 0 )
  {
    CContactManager::_SetMeContactID(this, 0);
    MeContactID = 0;
    if ( v7 != -2147023727 )
      MeContactID = v7;
    goto LABEL_27;
  }
  v5 = v12;
  MeContactID = EasyGetContactID(v12, (struct STRW *)&v13);
  if ( MeContactID >= 0 )
  {
    v8 = &Str;
    v9 = &Str;
    if ( v13 )
      v9 = psz1[0];
    MeContactID = CContactID::FindToken(v9, L"/PATH:", (struct STRW *)&v17);
    if ( MeContactID >= 0 )
    {
      v10 = (WCHAR *)&Str;
      if ( v17 )
        v10 = Path;
      if ( !(unsigned int)CContactManager::_IsContainedPath(this, v10) )
      {
        CContactManager::_SetMeContactID(this, 0);
LABEL_26:
        MeContactID = 0;
        goto LABEL_27;
      }
      if ( v13 )
        v8 = psz1[0];
      if ( StrCmpIW(v8, psz2[0]) )
        CContactManager::_SetMeContactID(this, (const struct STRW *)&v13);
LABEL_25:
      *a2 = v5;
      v12 = 0;
      goto LABEL_26;
    }
  }
LABEL_27:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v12);
  v17 = 0;
  BUFFER::ReleaseStorage((BUFFER *)&Path);
  v13 = 0;
  BUFFER::ReleaseStorage((BUFFER *)psz1);
  v15 = 0;
  BUFFER::ReleaseStorage((BUFFER *)psz2);
  return (unsigned int)MeContactID;
}

```

## disassembly

```asm
0x18007fa4c  mov     [rsp-8+arg_10], rbx
0x18007fa51  push    rbp
0x18007fa52  push    rsi
0x18007fa53  push    rdi
0x18007fa54  push    r14
0x18007fa56  push    r15
0x18007fa58  lea     rbp, [rsp-5D0h]
0x18007fa60  sub     rsp, 6D0h
0x18007fa67  mov     rax, cs:__security_cookie
0x18007fa6e  xor     rax, rsp
0x18007fa71  mov     [rbp+5F0h+var_30], rax
0x18007fa78  mov     rdi, rcx
0x18007fa7b  mov     ebx, 104h
0x18007fa80  mov     r14, rdx
0x18007fa83  lea     rcx, [rsp+6F0h+var_6A8]; this
0x18007fa88  mov     r8d, ebx; unsigned int
0x18007fa8b  lea     rdx, [rbp+5F0h+var_660]; unsigned __int16 *
0x18007fa8f  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18007fa94  mov     r8d, ebx; unsigned int
0x18007fa97  lea     rcx, [rsp+6F0h+var_6C8]; this
0x18007fa9c  lea     rdx, [rbp+5F0h+var_450]; unsigned __int16 *
0x18007faa3  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18007faa8  mov     r8d, ebx; unsigned int
0x18007faab  lea     rcx, [rsp+6F0h+var_688]; this
0x18007fab0  lea     rdx, [rbp+5F0h+var_240]; unsigned __int16 *
0x18007fab7  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18007fabc  mov     ebx, [rdi+28h]
0x18007fabf  xor     r15d, r15d
0x18007fac2  mov     [rsp+6F0h+var_6D0], r15
0x18007fac7  call    cs:__imp_GetCurrentThreadId
0x18007facd  cmp     eax, ebx
0x18007facf  jz      short loc_18007FADB
0x18007fad1  mov     ebx, 8001010Eh
0x18007fad6  jmp     loc_18007FBFD
0x18007fadb  test    r14, r14
0x18007fade  jnz     short loc_18007FAEA
0x18007fae0  mov     ebx, 80070057h
0x18007fae5  jmp     loc_18007FBFD
0x18007faea  cmp     [rdi+2Ch], r15d
0x18007faee  jnz     short loc_18007FAFA
0x18007faf0  mov     ebx, 8000FFFFh
0x18007faf5  jmp     loc_18007FBFD
0x18007fafa  lea     rdx, [rsp+6F0h+var_6A8]; struct STRW *
0x18007faff  mov     [r14], r15
0x18007fb02  mov     rcx, rdi; this
0x18007fb05  call    ?_GetMeContactID@CContactManager@@AEAAJPEAVSTRW@@@Z; CContactManager::_GetMeContactID(STRW *)
0x18007fb0a  mov     ebx, eax
0x18007fb0c  test    eax, eax
0x18007fb0e  js      loc_18007FBFD
0x18007fb14  cmp     [rsp+6F0h+var_6A8], r15d
0x18007fb19  jz      loc_18007FBEF
0x18007fb1f  mov     rdx, [rsp+6F0h+psz2]; psz1
0x18007fb24  lea     r8, [rsp+6F0h+var_6D0]; struct IContact **
0x18007fb29  mov     r9d, 1; int
0x18007fb2f  mov     rcx, rdi; this
0x18007fb32  call    ?_Load@CContactManager@@AEAAJPEBGPEAPEAUIContact@@H@Z; CContactManager::_Load(ushort const *,IContact * *,int)
0x18007fb37  mov     esi, eax
0x18007fb39  test    eax, eax
0x18007fb3b  jns     short loc_18007FB57
0x18007fb3d  xor     edx, edx; struct STRW *
0x18007fb3f  mov     rcx, rdi; this
0x18007fb42  call    ?_SetMeContactID@CContactManager@@AEAAJPEBVSTRW@@@Z; CContactManager::_SetMeContactID(STRW const *)
0x18007fb47  xor     ebx, ebx
0x18007fb49  cmp     esi, 80070491h
0x18007fb4f  cmovnz  ebx, esi
0x18007fb52  jmp     loc_18007FBFD
0x18007fb57  mov     r15, [rsp+6F0h+var_6D0]
0x18007fb5c  lea     rdx, [rsp+6F0h+var_6C8]; struct STRW *
0x18007fb61  mov     rcx, r15; struct IContact *
0x18007fb64  call    ?EasyGetContactID@@YAJPEAUIContact@@PEAVSTRW@@@Z; EasyGetContactID(IContact *,STRW *)
0x18007fb69  mov     ebx, eax
0x18007fb6b  test    eax, eax
0x18007fb6d  js      loc_18007FBFD
0x18007fb73  cmp     [rsp+6F0h+var_6C8], 0
0x18007fb78  lea     rsi, Str
0x18007fb7f  mov     rcx, rsi
0x18007fb82  lea     r8, [rsp+6F0h+var_688]; this
0x18007fb87  cmovnz  rcx, [rsp+6F0h+psz1]; psz1
0x18007fb8d  lea     rdx, aPath; "/PATH:"
0x18007fb94  call    ?FindToken@CContactID@@SAJPEBG0PEAVSTRW@@@Z; CContactID::FindToken(ushort const *,ushort const *,STRW *)
0x18007fb99  mov     ebx, eax
0x18007fb9b  test    eax, eax
0x18007fb9d  js      short loc_18007FBFD
0x18007fb9f  cmp     [rsp+6F0h+var_688], 0
0x18007fba4  mov     rdx, rsi
0x18007fba7  mov     rcx, rdi; this
0x18007fbaa  cmovnz  rdx, [rsp+6F0h+Path]; Path
0x18007fbb0  call    ?_IsContainedPath@CContactManager@@AEAAHPEBG@Z; CContactManager::_IsContainedPath(ushort const *)
0x18007fbb5  test    eax, eax
0x18007fbb7  jnz     short loc_18007FBC5
0x18007fbb9  xor     edx, edx; struct STRW *
0x18007fbbb  mov     rcx, rdi; this
0x18007fbbe  call    ?_SetMeContactID@CContactManager@@AEAAJPEBVSTRW@@@Z; CContactManager::_SetMeContactID(STRW const *)
0x18007fbc3  jmp     short loc_18007FBFB
0x18007fbc5  cmp     [rsp+6F0h+var_6C8], 0
0x18007fbca  mov     rdx, [rsp+6F0h+psz2]; psz2
0x18007fbcf  cmovnz  rsi, [rsp+6F0h+psz1]
0x18007fbd5  mov     rcx, rsi; psz1
0x18007fbd8  call    cs:__imp_StrCmpIW
0x18007fbde  test    eax, eax
0x18007fbe0  jz      short loc_18007FBEF
0x18007fbe2  lea     rdx, [rsp+6F0h+var_6C8]; struct STRW *
0x18007fbe7  mov     rcx, rdi; this
0x18007fbea  call    ?_SetMeContactID@CContactManager@@AEAAJPEBVSTRW@@@Z; CContactManager::_SetMeContactID(STRW const *)
0x18007fbef  mov     [r14], r15
0x18007fbf2  mov     [rsp+6F0h+var_6D0], 0
0x18007fbfb  xor     ebx, ebx
0x18007fbfd  lea     rcx, [rsp+6F0h+var_6D0]
0x18007fc02  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007fc07  lea     rcx, [rsp+6F0h+Path]; this
0x18007fc0c  mov     [rsp+6F0h+var_688], 0
0x18007fc14  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18007fc19  lea     rcx, [rsp+6F0h+psz1]; this
0x18007fc1e  mov     [rsp+6F0h+var_6C8], 0
0x18007fc26  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18007fc2b  lea     rcx, [rsp+6F0h+psz2]; this
0x18007fc30  mov     [rsp+6F0h+var_6A8], 0
0x18007fc38  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18007fc3d  mov     eax, ebx
0x18007fc3f  mov     rcx, [rbp+5F0h+var_30]
0x18007fc46  xor     rcx, rsp; StackCookie
0x18007fc49  call    __security_check_cookie
0x18007fc4e  mov     rbx, [rsp+6F0h+arg_10]
0x18007fc56  add     rsp, 6D0h
0x18007fc5d  pop     r15
0x18007fc5f  pop     r14
0x18007fc61  pop     rdi
0x18007fc62  pop     rsi
0x18007fc63  pop     rbp
0x18007fc64  retn
```
