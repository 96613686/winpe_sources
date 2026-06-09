# PathUnExpandEnvStringsForUserW

- ea: `0x1800030f0`
- end: `0x180003364`
- name: `PathUnExpandEnvStringsForUserW`
- size: `628`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030f0`
- `0x180003370`
- `0x180003474`
- `0x180003560`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003292`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003292`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800032a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800032b2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800032a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800032b2`

## string_xrefs

- `0x18000324b`: `\\%COMPUTERNAME%`

## pseudocode

```c
__int64 __fastcall PathUnExpandEnvStringsForUserW(
        void *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // rsi
  const WCHAR *v8; // r12
  unsigned int v9; // eax
  unsigned int v10; // r15d
  __int64 v11; // r13
  int v12; // ebx
  __int64 v13; // rdx
  unsigned __int64 v14; // r8
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rdx
  WCHAR String1[264]; // [rsp+30h] [rbp-268h] BYREF

  v4 = a4;
  if ( !a3 )
    return 0;
  if ( !a2 )
  {
    if ( a4 )
      *a3 = 0;
    return 0;
  }
  v8 = L"%APPDATA%";
  v9 = SHExpandEnvironmentStringsForUserW(a1, L"%APPDATA%", String1, 0x104u);
  v10 = 1;
  if ( !v9
    || (v11 = v9 - 1, CompareStringW(0x800u, 0x10000001u, String1, v9 - 1, a2, v9 - 1) != 2)
    || (v12 = lstrlenW(a2) - v11, v12 + lstrlenW(L"%APPDATA%") >= (int)v4) )
  {
    if ( _UnExpandEnvironmentString(SHExpandEnvironmentStringsForUserW, a1, a2, L"%USERPROFILE%", a3, v4)
      || _UnExpandEnvironmentString(SHExpandEnvironmentStringsForUserW, a1, a2, L"%ALLUSERSPROFILE%", a3, v4)
      || _UnExpandEnvironmentString(SHExpandEnvironmentStringsForUserW, a1, a2, L"%ProgramFiles(x86)%", a3, v4)
      || _UnExpandEnvironmentString(SHExpandEnvironmentStringsForUserW, a1, a2, L"%ProgramFiles%", a3, v4)
      || _UnExpandEnvironmentString(SHExpandEnvironmentStringsForUserW, a1, a2, L"%SystemRoot%", a3, v4)
      || _UnExpandEnvironmentString(SHExpandEnvironmentStringsForUserW, a1, a2, L"%SystemDrive%", a3, v4)
      || _UnExpandEnvironmentString(SHExpandEnvironmentStringsForUserW, a1, a2, L"\\\\%COMPUTERNAME%", a3, v4) )
    {
      return v10;
    }
    return 0;
  }
  if ( (_DWORD)v4 )
  {
    if ( v4 > 0x7FFFFFFF )
    {
      *a3 = 0;
    }
    else
    {
      v13 = 2147483646;
      v14 = v4;
      v15 = a3;
      do
      {
        if ( !v13 )
          break;
        if ( !*v8 )
          break;
        *v15++ = *v8++;
        --v13;
        --v14;
      }
      while ( v14 );
      v16 = v15 - 1;
      if ( v14 )
        v16 = v15;
      *v16 = 0;
    }
  }
  StringCchCatW(a3, v4, &a2[v11]);
  return v10;
}

```

## disassembly

```asm
0x1800030f0  push    rbx
0x1800030f2  push    rbp
0x1800030f3  push    rsi
0x1800030f4  push    rdi
0x1800030f5  push    r12
0x1800030f7  push    r13
0x1800030f9  push    r14
0x1800030fb  push    r15
0x1800030fd  sub     rsp, 258h
0x180003104  mov     rax, cs:__security_cookie
0x18000310b  xor     rax, rsp
0x18000310e  mov     [rsp+298h+var_58], rax
0x180003116  xor     ebx, ebx
0x180003118  mov     esi, r9d
0x18000311b  mov     rdi, r8
0x18000311e  mov     r14, rdx
0x180003121  mov     rbp, rcx
0x180003124  test    r8, r8
0x180003127  jz      loc_18000335F
0x18000312d  test    rdx, rdx
0x180003130  jz      loc_180003356
0x180003136  lea     r12, String; "%APPDATA%"
0x18000313d  mov     r9d, 104h; unsigned int
0x180003143  mov     rdx, r12; unsigned __int16 *
0x180003146  lea     r8, [rsp+298h+String1]; unsigned __int16 *
0x18000314b  call    SHExpandEnvironmentStringsForUserW
0x180003150  lea     r15d, [rbx+1]
0x180003154  test    eax, eax
0x180003156  jnz     loc_180003272
0x18000315c  lea     r12, SHExpandEnvironmentStringsForUserW
0x180003163  mov     [rsp+298h+cchCount2], esi; unsigned int
0x180003167  mov     rcx, r12; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x18000316a  mov     [rsp+298h+lpString2], rdi; unsigned __int16 *
0x18000316f  lea     r9, aUserprofile_1; "%USERPROFILE%"
0x180003176  mov     r8, r14; unsigned __int16 *
0x180003179  mov     rdx, rbp; void *
0x18000317c  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x180003181  test    eax, eax
0x180003183  jnz     loc_180003322
0x180003189  mov     [rsp+298h+cchCount2], esi; unsigned int
0x18000318d  lea     r9, aAllusersprofil; "%ALLUSERSPROFILE%"
0x180003194  mov     r8, r14; unsigned __int16 *
0x180003197  mov     [rsp+298h+lpString2], rdi; unsigned __int16 *
0x18000319c  mov     rdx, rbp; void *
0x18000319f  mov     rcx, r12; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x1800031a2  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x1800031a7  test    eax, eax
0x1800031a9  jnz     loc_180003322
0x1800031af  mov     [rsp+298h+cchCount2], esi; unsigned int
0x1800031b3  lea     r9, aProgramfilesX8_0; "%ProgramFiles(x86)%"
0x1800031ba  mov     r8, r14; unsigned __int16 *
0x1800031bd  mov     [rsp+298h+lpString2], rdi; unsigned __int16 *
0x1800031c2  mov     rdx, rbp; void *
0x1800031c5  mov     rcx, r12; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x1800031c8  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x1800031cd  test    eax, eax
0x1800031cf  jnz     loc_180003322
0x1800031d5  mov     [rsp+298h+cchCount2], esi; unsigned int
0x1800031d9  lea     r9, aProgramfiles; "%ProgramFiles%"
0x1800031e0  mov     r8, r14; unsigned __int16 *
0x1800031e3  mov     [rsp+298h+lpString2], rdi; unsigned __int16 *
0x1800031e8  mov     rdx, rbp; void *
0x1800031eb  mov     rcx, r12; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x1800031ee  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x1800031f3  test    eax, eax
0x1800031f5  jnz     loc_180003322
0x1800031fb  mov     [rsp+298h+cchCount2], esi; unsigned int
0x1800031ff  lea     r9, aSystemroot_1; "%SystemRoot%"
0x180003206  mov     r8, r14; unsigned __int16 *
0x180003209  mov     [rsp+298h+lpString2], rdi; unsigned __int16 *
0x18000320e  mov     rdx, rbp; void *
0x180003211  mov     rcx, r12; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x180003214  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x180003219  test    eax, eax
0x18000321b  jnz     loc_180003322
0x180003221  mov     [rsp+298h+cchCount2], esi; unsigned int
0x180003225  lea     r9, aSystemdrive_0; "%SystemDrive%"
0x18000322c  mov     r8, r14; unsigned __int16 *
0x18000322f  mov     [rsp+298h+lpString2], rdi; unsigned __int16 *
0x180003234  mov     rdx, rbp; void *
0x180003237  mov     rcx, r12; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x18000323a  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x18000323f  test    eax, eax
0x180003241  jnz     loc_180003322
0x180003247  mov     [rsp+298h+cchCount2], esi; unsigned int
0x18000324b  lea     r9, aComputername; "\\\\%COMPUTERNAME%"
0x180003252  mov     r8, r14; unsigned __int16 *
0x180003255  mov     [rsp+298h+lpString2], rdi; unsigned __int16 *
0x18000325a  mov     rdx, rbp; void *
0x18000325d  mov     rcx, r12; unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int)
0x180003260  call    ?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z; _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)
0x180003265  test    eax, eax
0x180003267  jnz     loc_180003322
0x18000326d  jmp     loc_18000335F
0x180003272  lea     r13d, [rax-1]
0x180003276  mov     edx, 10000001h; dwCmpFlags
0x18000327b  mov     [rsp+298h+cchCount2], r13d; cchCount2
0x180003280  lea     r8, [rsp+298h+String1]; lpString1
0x180003285  mov     r9d, r13d; cchCount1
0x180003288  mov     [rsp+298h+lpString2], r14; lpString2
0x18000328d  mov     ecx, 800h; Locale
0x180003292  call    cs:__imp_CompareStringW
0x180003298  cmp     eax, 2
0x18000329b  jnz     loc_18000315C
0x1800032a1  mov     rcx, r14; lpString
0x1800032a4  call    cs:__imp_lstrlenW
0x1800032aa  mov     ebx, eax
0x1800032ac  mov     rcx, r12; lpString
0x1800032af  sub     ebx, r13d
0x1800032b2  call    cs:__imp_lstrlenW
0x1800032b8  add     eax, ebx
0x1800032ba  cmp     eax, esi
0x1800032bc  jge     loc_18000334F
0x1800032c2  xor     r10d, r10d
0x1800032c5  mov     rcx, rsi
0x1800032c8  test    esi, esi
0x1800032ca  jz      short loc_180003313
0x1800032cc  cmp     rcx, 7FFFFFFFh
0x1800032d3  ja      short loc_180003349
0x1800032d5  mov     edx, 7FFFFFFEh
0x1800032da  mov     r8, rcx
0x1800032dd  mov     rax, rdi
0x1800032e0  test    rdx, rdx
0x1800032e3  jz      short loc_180003304
0x1800032e5  movzx   r9d, word ptr [r12]
0x1800032ea  test    r9w, r9w
0x1800032ee  jz      short loc_180003304
0x1800032f0  mov     [rax], r9w
0x1800032f4  add     r12, 2
0x1800032f8  add     rax, 2
0x1800032fc  sub     rdx, r15
0x1800032ff  sub     r8, r15
0x180003302  jnz     short loc_1800032E0
0x180003304  test    r8, r8
0x180003307  lea     rdx, [rax-2]
0x18000330b  cmovnz  rdx, rax
0x18000330f  mov     [rdx], r10w
0x180003313  mov     rdx, rcx; unsigned __int64
0x180003316  lea     r8, [r14+r13*2]; unsigned __int16 *
0x18000331a  mov     rcx, rdi; unsigned __int16 *
0x18000331d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003322  mov     eax, r15d
0x180003325  mov     rcx, [rsp+298h+var_58]
0x18000332d  xor     rcx, rsp; StackCookie
0x180003330  call    __security_check_cookie
0x180003335  add     rsp, 258h
0x18000333c  pop     r15
0x18000333e  pop     r14
0x180003340  pop     r13
0x180003342  pop     r12
0x180003344  pop     rdi
0x180003345  pop     rsi
0x180003346  pop     rbp
0x180003347  pop     rbx
0x180003348  retn
0x180003349  mov     [rdi], r10w
0x18000334d  jmp     short loc_180003313
0x18000334f  xor     ebx, ebx
0x180003351  jmp     loc_18000315C
0x180003356  test    r9d, r9d
0x180003359  jz      short loc_18000335F
0x18000335b  mov     [r8], bx
0x18000335f  mov     r15d, ebx
0x180003362  jmp     short loc_180003322
```
