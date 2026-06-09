# ContactHasOriginalName(IContact *)

- ea: `0x180008fa0`
- end: `0x1800090c9`
- name: `?ContactHasOriginalName@@YAHPEAUIContact@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(struct IContact *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180009918`
- `0x18000faf0`
- `0x1800121f0`

## callees

- `0x180006f7c`
- `0x180008f74`
- `0x180008fa0`
- `0x1800133d0`
- `0x180013950`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000903b`
- `SHLWAPI!PathFindFileNameW` at `0x18000906c`
- `SHLWAPI!PathFindFileNameW` at `0x18000903b`
- `SHLWAPI!PathFindFileNameW` at `0x18000906c`
- `SHLWAPI!StrCmpNIW` at `0x180009055`
- `SHLWAPI!StrCmpNIW` at `0x180009055`

## pseudocode

```c
__int64 __fastcall ContactHasOriginalName(struct IContact *a1)
{
  unsigned int v2; // ebx
  const WCHAR *v3; // rdi
  int v4; // ebx
  const WCHAR *v5; // rcx
  const WCHAR *FileNameW; // rax
  const WCHAR *v7; // rcx
  LPWSTR v8; // rax
  void *nChar; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR psz1[3]; // [rsp+28h] [rbp-D8h] BYREF
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszPath[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v14[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v15[264]; // [rsp+270h] [rbp+170h] BYREF

  STRW::STRW((STRW *)&v12, v14, 0x104u);
  STRW::STRW((STRW *)&nChar, v15, 0x104u);
  if ( GetPathFromContact(a1, (struct STRW *)&v12) < 0 )
    goto LABEL_2;
  if ( (int)GetDisplayNameFromContact(a1, &nChar) < 0 )
    goto LABEL_12;
  v3 = &Str;
  v4 = (int)nChar;
  v5 = &Str;
  if ( v12 )
    v5 = pszPath[0];
  FileNameW = PathFindFileNameW(v5);
  v7 = &Str;
  if ( (_DWORD)nChar )
    v7 = psz1[0];
  if ( StrCmpNIW(v7, FileNameW, v4) )
    goto LABEL_12;
  if ( v12 )
    v3 = pszPath[0];
  v8 = PathFindFileNameW(v3);
  if ( v8[(unsigned int)nChar] == 46 )
LABEL_2:
    v2 = 1;
  else
LABEL_12:
    v2 = 0;
  LODWORD(nChar) = 0;
  BUFFER::ReleaseStorage((BUFFER *)psz1);
  v12 = 0;
  BUFFER::ReleaseStorage((BUFFER *)pszPath);
  return v2;
}

```

## disassembly

```asm
0x180008fa0  mov     [rsp-8+arg_8], rbx
0x180008fa5  mov     [rsp-8+arg_10], rdi
0x180008faa  push    rbp
0x180008fab  lea     rbp, [rsp-390h]
0x180008fb3  sub     rsp, 490h
0x180008fba  mov     rax, cs:__security_cookie
0x180008fc1  xor     rax, rsp
0x180008fc4  mov     [rbp+390h+var_10], rax
0x180008fcb  mov     rbx, rcx
0x180008fce  lea     rdx, [rsp+490h+var_430]; unsigned __int16 *
0x180008fd3  mov     edi, 104h
0x180008fd8  lea     rcx, [rsp+490h+var_450]; this
0x180008fdd  mov     r8d, edi; unsigned int
0x180008fe0  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180008fe5  mov     r8d, edi; unsigned int
0x180008fe8  lea     rcx, [rsp+490h+nChar]; this
0x180008fed  lea     rdx, [rbp+390h+var_220]; unsigned __int16 *
0x180008ff4  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180008ff9  mov     rcx, rbx; struct IContact *
0x180008ffc  lea     rdx, [rsp+490h+var_450]; struct STRW *
0x180009001  call    ?GetPathFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetPathFromContact(IContact *,STRW *)
0x180009006  test    eax, eax
0x180009008  jns     short loc_180009011
0x18000900a  mov     ebx, 1
0x18000900f  jmp     short loc_18000907F
0x180009011  lea     rdx, [rsp+490h+nChar]; struct STRW *
0x180009016  mov     rcx, rbx; struct IContact *
0x180009019  call    ?GetDisplayNameFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetDisplayNameFromContact(IContact *,STRW *)
0x18000901e  test    eax, eax
0x180009020  js      short loc_18000907D
0x180009022  cmp     [rsp+490h+var_450], 0
0x180009027  lea     rdi, Str
0x18000902e  mov     ebx, dword ptr [rsp+490h+nChar]
0x180009032  mov     rcx, rdi
0x180009035  cmovnz  rcx, [rsp+490h+pszPath]; pszPath
0x18000903b  call    cs:__imp_PathFindFileNameW
0x180009041  cmp     dword ptr [rsp+490h+nChar], 0
0x180009046  mov     rcx, rdi
0x180009049  mov     r8d, ebx; nChar
0x18000904c  mov     rdx, rax; psz2
0x18000904f  cmovnz  rcx, [rsp+490h+psz1]; psz1
0x180009055  call    cs:__imp_StrCmpNIW
0x18000905b  test    eax, eax
0x18000905d  jnz     short loc_18000907D
0x18000905f  cmp     [rsp+490h+var_450], eax
0x180009063  cmovnz  rdi, [rsp+490h+pszPath]
0x180009069  mov     rcx, rdi; pszPath
0x18000906c  call    cs:__imp_PathFindFileNameW
0x180009072  mov     ecx, dword ptr [rsp+490h+nChar]
0x180009076  cmp     word ptr [rax+rcx*2], 2Eh ; '.'
0x18000907b  jz      short loc_18000900A
0x18000907d  xor     ebx, ebx
0x18000907f  lea     rcx, [rsp+490h+psz1]; this
0x180009084  mov     dword ptr [rsp+490h+nChar], 0
0x18000908c  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180009091  lea     rcx, [rsp+490h+pszPath]; this
0x180009096  mov     [rsp+490h+var_450], 0
0x18000909e  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x1800090a3  mov     eax, ebx
0x1800090a5  mov     rcx, [rbp+390h+var_10]
0x1800090ac  xor     rcx, rsp; StackCookie
0x1800090af  call    __security_check_cookie
0x1800090b4  lea     r11, [rsp+490h+var_s0]
0x1800090bc  mov     rbx, [r11+18h]
0x1800090c0  mov     rdi, [r11+20h]
0x1800090c4  mov     rsp, r11
0x1800090c7  pop     rbp
0x1800090c8  retn
```
