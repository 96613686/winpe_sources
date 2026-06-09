# JobStore::CreateXmlFolder(ushort const *,ushort const *)

- ea: `0x180021418`
- end: `0x180021776`
- name: `?CreateXmlFolder@JobStore@@QEAAJPEBG0@Z`
- size: `862`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001d7ac`
- `0x18001fa60`
- `0x18001fe44`
- `0x18006fed4`

## callees

- `0x18000cc40`
- `0x1800213d8`
- `0x180021418`
- `0x180022d80`
- `0x1800301f0`
- `0x18004e810`
- `0x180059140`
- `0x18006f17c`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021577`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180021551`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002170e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180021551`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002170e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021492`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021492`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18002164d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x18002164d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18002168e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18002168e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobStore::CreateXmlFolder(JobStore *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int XmlFileSystemPath; // ebx
  struct _SECURITY_ATTRIBUTES *v8; // r14
  void *v9; // rbx
  unsigned int v10; // edi
  signed int LastError; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  LPWSTR v14; // r15
  LPWSTR v15; // rax
  LPWSTR v16; // rsi
  WCHAR v17; // ax
  _WORD *v18; // rdi
  struct _SECURITY_ATTRIBUTES *v19; // rdx
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  void **v21; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( !JobStore::GetUseXmlStore(this) )
    return 0;
  lpMem = 0;
  XmlFileSystemPath = JobStore::GetXmlFileSystemPath(this, a2, &lpMem);
  if ( XmlFileSystemPath >= 0 )
  {
    v21 = &ATL::CSecurityDesc::`vftable';
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v8 = 0;
    v9 = lpMem;
    if ( a3 )
    {
      if ( !ATL::CSecurityDesc::FromString((ATL::CSecurityDesc *)&v21, a3) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
            (_DWORD)a3,
            58);
        }
        v10 = -2147023558;
        goto LABEL_49;
      }
      v24 = v22;
      LODWORD(v23) = 24;
      LODWORD(v25) = 0;
      v8 = (struct _SECURITY_ATTRIBUTES *)&v23;
    }
    if ( !CreateDirectoryW((LPCWSTR)v9, v8) )
    {
      memset_0(pszPath, 0, 0x208u);
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError != 3 )
      {
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
            (_DWORD)v9,
            v10);
        }
        goto LABEL_49;
      }
      if ( (int)StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)v9) < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v13 = 29;
LABEL_28:
        WPP_SF_Sd(v12[2], v13, (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, (_DWORD)v9, 206);
LABEL_29:
        v10 = -2147024690;
LABEL_49:
        v21 = &ATL::CSecurityDesc::`vftable';
        ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v21);
        operator delete(v9);
        return v10;
      }
      v14 = PathAddBackslashW(pszPath);
      if ( !v14 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v13 = 30;
        goto LABEL_28;
      }
      v15 = PathSkipRootW(pszPath);
      v16 = v15;
      if ( !v15 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v13 = 31;
        goto LABEL_28;
      }
      if ( *v15 )
      {
        do
        {
          v17 = *v16;
          do
          {
            if ( v17 == 92 )
              break;
            v17 = *++v16;
          }
          while ( *v16 );
          if ( !*v16 )
            break;
          *v16 = 0;
          v18 = v16 + 1;
          v19 = v8;
          if ( v16 + 1 != v14 )
            v19 = 0;
          CreateDirectoryW(pszPath, v19);
          *v16++ = 92;
        }
        while ( *v18 );
      }
    }
    v10 = 0;
    goto LABEL_49;
  }
  if ( lpMem )
    HeapFree(g_PrivateHeap, 0, lpMem);
  return (unsigned int)XmlFileSystemPath;
}

```

## disassembly

```asm
0x180021418  mov     [rsp-8+arg_18], rbx
0x18002141d  push    rbp
0x18002141e  push    rsi
0x18002141f  push    rdi
0x180021420  push    r12
0x180021422  push    r13
0x180021424  push    r14
0x180021426  push    r15
0x180021428  lea     rbp, [rsp-180h]
0x180021430  sub     rsp, 280h
0x180021437  mov     rax, cs:__security_cookie
0x18002143e  xor     rax, rsp
0x180021441  mov     [rbp+1B0h+var_40], rax
0x180021448  mov     rdi, r8
0x18002144b  mov     rsi, rdx
0x18002144e  mov     rbx, rcx
0x180021451  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x180021456  xor     r12d, r12d
0x180021459  test    al, al
0x18002145b  jnz     short loc_180021464
0x18002145d  xor     eax, eax
0x18002145f  jmp     loc_18002174B
0x180021464  mov     [rsp+2B0h+lpMem], r12
0x180021469  lea     r8, [rsp+2B0h+lpMem]
0x18002146e  mov     rdx, rsi
0x180021471  mov     rcx, rbx
0x180021474  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180021479  mov     ebx, eax
0x18002147b  test    eax, eax
0x18002147d  jns     short loc_1800214A5
0x18002147f  mov     r8, [rsp+2B0h+lpMem]; lpMem
0x180021484  test    r8, r8
0x180021487  jz      short loc_18002149E
0x180021489  xor     edx, edx; dwFlags
0x18002148b  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180021492  call    cs:__imp_HeapFree
0x180021499  nop     dword ptr [rax+rax+00h]
0x18002149e  mov     eax, ebx
0x1800214a0  jmp     loc_18002174B
0x1800214a5  lea     r13, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x1800214ac  mov     [rsp+2B0h+var_278], r13
0x1800214b1  mov     [rsp+2B0h+var_270], r12
0x1800214b6  mov     [rsp+2B0h+var_268], r12
0x1800214bb  mov     [rsp+2B0h+var_260], r12
0x1800214c0  mov     [rsp+2B0h+var_258], r12
0x1800214c5  mov     r14, r12
0x1800214c8  mov     rbx, [rsp+2B0h+lpMem]
0x1800214cd  test    rdi, rdi
0x1800214d0  jz      short loc_18002154B
0x1800214d2  mov     rdx, rdi; StringSecurityDescriptor
0x1800214d5  lea     rcx, [rsp+2B0h+var_278]; this
0x1800214da  call    ?FromString@CSecurityDesc@ATL@@QEAA_NPEBG@Z; ATL::CSecurityDesc::FromString(ushort const *)
0x1800214df  test    al, al
0x1800214e1  jnz     short loc_18002152F
0x1800214e3  lea     rax, WPP_GLOBAL_Control
0x1800214ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214f1  cmp     rcx, rax
0x1800214f4  jz      short loc_180021525
0x1800214f6  test    dword ptr [rcx+1Ch], 40000h
0x1800214fd  jz      short loc_180021525
0x1800214ff  cmp     byte ptr [rcx+19h], 2
0x180021503  jb      short loc_180021525
0x180021505  mov     edx, 1Bh
0x18002150a  mov     [rsp+2B0h+var_290], 53Ah
0x180021512  mov     r9, rdi
0x180021515  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18002151c  mov     rcx, [rcx+10h]
0x180021520  call    WPP_SF_Sd
0x180021525  mov     edi, 8007053Ah
0x18002152a  jmp     loc_180021731
0x18002152f  mov     rax, [rsp+2B0h+var_270]
0x180021534  mov     [rsp+2B0h+var_260], rax
0x180021539  mov     dword ptr [rsp+2B0h+var_268], 18h
0x180021541  mov     dword ptr [rsp+2B0h+var_258], r12d
0x180021546  lea     r14, [rsp+2B0h+var_268]
0x18002154b  mov     rdx, r14; lpSecurityAttributes
0x18002154e  mov     rcx, rbx; lpPathName
0x180021551  call    cs:__imp_CreateDirectoryW
0x180021558  nop     dword ptr [rax+rax+00h]
0x18002155d  test    eax, eax
0x18002155f  jnz     loc_18002172E
0x180021565  xor     edx, edx; Val
0x180021567  mov     r8d, 208h; Size
0x18002156d  lea     rcx, [rsp+2B0h+pszPath]; void *
0x180021572  call    memset_0
0x180021577  call    cs:__imp_GetLastError
0x18002157e  nop     dword ptr [rax+rax+00h]
0x180021583  mov     edi, eax
0x180021585  cmp     eax, 3
0x180021588  jz      short loc_1800215E6
0x18002158a  test    eax, eax
0x18002158c  jle     short loc_180021597
0x18002158e  movzx   edi, ax
0x180021591  or      edi, 80070000h
0x180021597  lea     rax, WPP_GLOBAL_Control
0x18002159e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215a5  cmp     rcx, rax
0x1800215a8  jz      loc_180021731
0x1800215ae  test    dword ptr [rcx+1Ch], 40000h
0x1800215b5  jz      loc_180021731
0x1800215bb  cmp     byte ptr [rcx+19h], 2
0x1800215bf  jb      loc_180021731
0x1800215c5  mov     edx, 1Ch
0x1800215ca  mov     [rsp+2B0h+var_290], edi
0x1800215ce  mov     r9, rbx
0x1800215d1  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800215d8  mov     rcx, [rcx+10h]
0x1800215dc  call    WPP_SF_Sd
0x1800215e1  jmp     loc_180021731
0x1800215e6  mov     r8, rbx; unsigned __int16 *
0x1800215e9  mov     edx, 104h; unsigned __int64
0x1800215ee  lea     rcx, [rsp+2B0h+pszPath]; unsigned __int16 *
0x1800215f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800215f8  test    eax, eax
0x1800215fa  jns     short loc_180021648
0x1800215fc  lea     rax, WPP_GLOBAL_Control
0x180021603  mov     rcx, cs:WPP_GLOBAL_Control
0x18002160a  cmp     rcx, rax
0x18002160d  jz      short loc_18002163E
0x18002160f  test    dword ptr [rcx+1Ch], 40000h
0x180021616  jz      short loc_18002163E
0x180021618  cmp     byte ptr [rcx+19h], 2
0x18002161c  jb      short loc_18002163E
0x18002161e  mov     edx, 1Dh
0x180021623  mov     [rsp+2B0h+var_290], 800700CEh
0x18002162b  mov     r9, rbx
0x18002162e  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180021635  mov     rcx, [rcx+10h]
0x180021639  call    WPP_SF_Sd
0x18002163e  mov     edi, 800700CEh
0x180021643  jmp     loc_180021731
0x180021648  lea     rcx, [rsp+2B0h+pszPath]; pszPath
0x18002164d  call    cs:__imp_PathAddBackslashW
0x180021654  nop     dword ptr [rax+rax+00h]
0x180021659  mov     r15, rax
0x18002165c  test    rax, rax
0x18002165f  jnz     short loc_180021689
0x180021661  lea     rax, WPP_GLOBAL_Control
0x180021668  mov     rcx, cs:WPP_GLOBAL_Control
0x18002166f  cmp     rcx, rax
0x180021672  jz      short loc_18002163E
0x180021674  test    dword ptr [rcx+1Ch], 40000h
0x18002167b  jz      short loc_18002163E
0x18002167d  cmp     byte ptr [rcx+19h], 2
0x180021681  jb      short loc_18002163E
0x180021683  lea     edx, [r15+1Eh]
0x180021687  jmp     short loc_180021623
0x180021689  lea     rcx, [rsp+2B0h+pszPath]; pszPath
0x18002168e  call    cs:__imp_PathSkipRootW
0x180021695  nop     dword ptr [rax+rax+00h]
0x18002169a  mov     rsi, rax
0x18002169d  test    rax, rax
0x1800216a0  jnz     short loc_1800216D0
0x1800216a2  lea     rax, WPP_GLOBAL_Control
0x1800216a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216b0  cmp     rcx, rax
0x1800216b3  jz      short loc_18002163E
0x1800216b5  test    dword ptr [rcx+1Ch], 40000h
0x1800216bc  jz      short loc_18002163E
0x1800216be  cmp     byte ptr [rcx+19h], 2
0x1800216c2  jb      loc_18002163E
0x1800216c8  lea     edx, [rsi+1Fh]
0x1800216cb  jmp     loc_180021623
0x1800216d0  cmp     [rax], r12w
0x1800216d4  jz      short loc_18002172E
0x1800216d6  mov     r13d, 5Ch ; '\'
0x1800216dc  movzx   eax, word ptr [rsi]
0x1800216df  cmp     ax, r13w
0x1800216e3  jz      short loc_1800216F1
0x1800216e5  add     rsi, 2
0x1800216e9  movzx   eax, word ptr [rsi]
0x1800216ec  test    ax, ax
0x1800216ef  jnz     short loc_1800216DF
0x1800216f1  cmp     [rsi], r12w
0x1800216f5  jz      short loc_180021727
0x1800216f7  mov     [rsi], r12w
0x1800216fb  lea     rdi, [rsi+2]
0x1800216ff  mov     rdx, r14
0x180021702  cmp     rdi, r15
0x180021705  cmovnz  rdx, r12; lpSecurityAttributes
0x180021709  lea     rcx, [rsp+2B0h+pszPath]; lpPathName
0x18002170e  call    cs:__imp_CreateDirectoryW
0x180021715  nop     dword ptr [rax+rax+00h]
0x18002171a  mov     [rsi], r13w
0x18002171e  mov     rsi, rdi
0x180021721  cmp     [rdi], r12w
0x180021725  jnz     short loc_1800216DC
0x180021727  lea     r13, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x18002172e  mov     edi, r12d
0x180021731  mov     [rsp+2B0h+var_278], r13
0x180021736  lea     rcx, [rsp+2B0h+var_278]; this
0x18002173b  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x180021740  nop
0x180021741  mov     rcx, rbx; void *
0x180021744  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021749  mov     eax, edi
0x18002174b  mov     rcx, [rbp+1B0h+var_40]
0x180021752  xor     rcx, rsp; StackCookie
0x180021755  call    __security_check_cookie
0x18002175a  mov     rbx, [rsp+2B0h+arg_18]
0x180021762  add     rsp, 280h
0x180021769  pop     r15
0x18002176b  pop     r14
0x18002176d  pop     r13
0x18002176f  pop     r12
0x180021771  pop     rdi
0x180021772  pop     rsi
0x180021773  pop     rbp
0x180021774  retn
```
