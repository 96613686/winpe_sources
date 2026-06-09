# CCabDecompress::FDINotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x1800a0324`
- end: `0x1800a066a`
- name: `?FDINotify@CCabDecompress@@IEAA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(CCabDecompress *__hidden this, enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a08d0`

## callees

- `0x180004c64`
- `0x18000cf50`
- `0x18000db80`
- `0x1800170b0`
- `0x180018000`
- `0x18001c368`
- `0x180020680`
- `0x18007a4b4`
- `0x18009cc50`
- `0x1800a0254`
- `0x1800a02f0`
- `0x1800a0324`
- `0x1800a0810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a054c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a054c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a0361`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a0361`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a0591`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a0591`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a051e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a051e`

## pseudocode

```c
_BOOL8 __fastcall CCabDecompress::FDINotify(HANDLE *this, enum FDINOTIFICATIONTYPE a2, struct FDINOTIFICATION *a3)
{
  __int64 v6; // rsi
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  __int64 v12; // r8
  int v13; // eax
  int UniquePath; // eax
  HANDLE **v15; // rbx
  HANDLE *FileW; // rax
  DWORD LastError; // eax
  char v18; // al
  wchar_t *v19; // rcx
  _QWORD v21[4]; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR lpFileName[10]; // [rsp+60h] [rbp+7h] BYREF
  HANDLE **v23; // [rsp+D0h] [rbp+77h] BYREF

  v6 = -1;
  if ( !a3 || !a3->pv )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = 65;
      goto LABEL_48;
    }
    return v6;
  }
  if ( !WaitForSingleObject(*this, 0) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v8 = 66;
LABEL_48:
      WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
      return v6;
    }
    return v6;
  }
  v9 = a2 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( !v11 )
        return CCabDecompress::static_FDIClose(a3->hf) == 0;
      if ( v11 != 1 )
        return 0;
      goto LABEL_42;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v21);
    v6 = 0;
    v21[1] = v21[0];
    v12 = -1;
    *(_WORD *)v21[0] = 0;
    do
      ++v12;
    while ( a3->psz1[v12] );
    v13 = tlx::_AppendMbcsImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(v21);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          (unsigned int)v13);
      goto LABEL_19;
    }
    UniquePath = UtilGetUniquePath(this[1], v21[0], lpFileName);
    if ( UniquePath < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          v21[0],
          UniquePath);
      goto LABEL_19;
    }
    utl::make_unique<CCabDecompress::_DECOMP_FILE_HANDLE,,0>(&v23);
    v15 = v23;
    if ( !v23 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)((_DWORD)v23 + 69),
          WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          v21[0]);
      goto LABEL_28;
    }
    *v23 = this;
    FileW = (HANDLE *)CreateFileW(lpFileName[0], 0xC0000000, 7u, 0, 1u, 0x80u, 0);
    v15[1] = FileW;
    if ( FileW == (HANDLE *)-1LL )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v18 = ERROR_HR_FROM_WIN32(LastError);
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          (unsigned int)WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          lpFileName[0],
          v18);
      }
      goto LABEL_28;
    }
    if ( !SetFileAttributesW(lpFileName[0], 0x2080u) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
      {
LABEL_41:
        v6 = (__int64)v15;
        v23 = 0;
LABEL_28:
        utl::unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>::~unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>(&v23);
LABEL_19:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v21);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
        return v6;
      }
      if ( (WPP_GLOBAL_Control[14] & 2) == 0 )
      {
LABEL_38:
        if ( v19 != (wchar_t *)&WPP_GLOBAL_Control && (v19[14] & 4) != 0 )
          WPP_SF_S(*((_QWORD *)v19 + 2), 72, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, lpFileName[0]);
        goto LABEL_41;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
    }
    v19 = WPP_GLOBAL_Control;
    goto LABEL_38;
  }
LABEL_42:
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v8 = 73;
    goto LABEL_48;
  }
  return v6;
}

```

## disassembly

```asm
0x1800a0324  push    rbp
0x1800a0326  push    rbx
0x1800a0327  push    rsi
0x1800a0328  push    rdi
0x1800a0329  push    r12
0x1800a032b  push    r14
0x1800a032d  lea     rbp, [rsp-2Fh]
0x1800a0332  sub     rsp, 88h
0x1800a0339  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800a033d  mov     rdi, r8
0x1800a0340  mov     ebx, edx
0x1800a0342  mov     r14, rcx
0x1800a0345  mov     rsi, r12
0x1800a0348  test    r8, r8
0x1800a034b  jz      loc_1800A0628
0x1800a0351  cmp     qword ptr [r8+20h], 0
0x1800a0356  jz      loc_1800A0628
0x1800a035c  mov     rcx, [rcx]; hHandle
0x1800a035f  xor     edx, edx; dwMilliseconds
0x1800a0361  call    cs:__imp_WaitForSingleObject
0x1800a0368  nop     dword ptr [rax+rax+00h]
0x1800a036d  test    eax, eax
0x1800a036f  jnz     short loc_1800A039A
0x1800a0371  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0378  lea     rdi, WPP_GLOBAL_Control
0x1800a037f  cmp     rcx, rdi
0x1800a0382  jz      loc_1800A0656
0x1800a0388  test    byte ptr [rcx+1Ch], 4
0x1800a038c  jz      loc_1800A0656
0x1800a0392  lea     edx, [rax+42h]
0x1800a0395  jmp     loc_1800A0646
0x1800a039a  sub     ebx, 1
0x1800a039d  jz      loc_1800A0608
0x1800a03a3  sub     ebx, 1
0x1800a03a6  jz      short loc_1800A03D3
0x1800a03a8  sub     ebx, 1
0x1800a03ab  jz      short loc_1800A03BD
0x1800a03ad  cmp     ebx, 1
0x1800a03b0  jz      loc_1800A0608
0x1800a03b6  xor     esi, esi
0x1800a03b8  jmp     loc_1800A0656
0x1800a03bd  mov     rcx, [rdi+28h]; hf
0x1800a03c1  call    ?static_FDIClose@CCabDecompress@@KAH_J@Z; CCabDecompress::static_FDIClose(__int64)
0x1800a03c6  xor     esi, esi
0x1800a03c8  test    eax, eax
0x1800a03ca  setz    sil
0x1800a03ce  jmp     loc_1800A0656
0x1800a03d3  lea     rcx, [rbp+57h+lpFileName]; void *
0x1800a03d7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a03dc  lea     rcx, [rbp+57h+var_70]; void *
0x1800a03e0  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a03e5  mov     rcx, [rbp+57h+var_70]
0x1800a03e9  xor     esi, esi
0x1800a03eb  xor     eax, eax
0x1800a03ed  mov     [rbp+57h+var_68], rcx
0x1800a03f1  mov     r8, r12
0x1800a03f4  mov     [rcx], ax
0x1800a03f7  mov     rdx, [rdi+8]
0x1800a03fb  inc     r8
0x1800a03fe  cmp     [rdx+r8], al
0x1800a0402  jnz     short loc_1800A03FB
0x1800a0404  lea     rcx, [rbp+57h+var_70]
0x1800a0408  call    ??$_AppendMbcsImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEBD_KII@Z; tlx::_AppendMbcsImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,char const *,unsigned __int64,uint,uint)
0x1800a040d  test    eax, eax
0x1800a040f  jns     short loc_1800A0459
0x1800a0411  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0418  lea     rdi, WPP_GLOBAL_Control
0x1800a041f  cmp     rcx, rdi
0x1800a0422  jz      short loc_1800A0442
0x1800a0424  test    byte ptr [rcx+1Ch], 1
0x1800a0428  jz      short loc_1800A0442
0x1800a042a  mov     rcx, [rcx+10h]
0x1800a042e  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a0435  mov     edx, 43h ; 'C'
0x1800a043a  mov     r9d, eax
0x1800a043d  call    WPP_SF_d
0x1800a0442  lea     rcx, [rbp+57h+var_70]; void *
0x1800a0446  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a044b  lea     rcx, [rbp+57h+lpFileName]; void *
0x1800a044f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a0454  jmp     loc_1800A0656
0x1800a0459  mov     rdx, [rbp+57h+var_70]
0x1800a045d  lea     r8, [rbp+57h+lpFileName]
0x1800a0461  mov     rcx, [r14+8]
0x1800a0465  call    ?UtilGetUniquePath@@YAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetUniquePath(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a046a  test    eax, eax
0x1800a046c  jns     short loc_1800A04A6
0x1800a046e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0475  lea     rdi, WPP_GLOBAL_Control
0x1800a047c  cmp     rcx, rdi
0x1800a047f  jz      short loc_1800A0442
0x1800a0481  test    byte ptr [rcx+1Ch], 1
0x1800a0485  jz      short loc_1800A0442
0x1800a0487  mov     r9, [rbp+57h+var_70]
0x1800a048b  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a0492  mov     rcx, [rcx+10h]
0x1800a0496  mov     edx, 44h ; 'D'
0x1800a049b  mov     [rsp+0B0h+dwCreationDisposition], eax
0x1800a049f  call    WPP_SF_SD
0x1800a04a4  jmp     short loc_1800A0442
0x1800a04a6  lea     rcx, [rbp+57h+arg_10]
0x1800a04aa  call    ??$make_unique@U_DECOMP_FILE_HANDLE@CCabDecompress@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_DECOMP_FILE_HANDLE@CCabDecompress@@U?$default_delete@U_DECOMP_FILE_HANDLE@CCabDecompress@@@utl@@@0@XZ; utl::make_unique<CCabDecompress::_DECOMP_FILE_HANDLE,,0>(void)
0x1800a04af  mov     rbx, [rbp+57h+arg_10]
0x1800a04b3  test    rbx, rbx
0x1800a04b6  jnz     short loc_1800A04F6
0x1800a04b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a04bf  lea     rdi, WPP_GLOBAL_Control
0x1800a04c6  cmp     rcx, rdi
0x1800a04c9  jz      short loc_1800A04E8
0x1800a04cb  test    byte ptr [rcx+1Ch], 1
0x1800a04cf  jz      short loc_1800A04E8
0x1800a04d1  mov     r9, [rbp+57h+var_70]
0x1800a04d5  lea     edx, [rbx+45h]
0x1800a04d8  mov     rcx, [rcx+10h]
0x1800a04dc  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a04e3  call    WPP_SF_S
0x1800a04e8  lea     rcx, [rbp+57h+arg_10]
0x1800a04ec  call    ??1?$unique_ptr@U_DECOMP_FILE_HANDLE@CCabDecompress@@U?$default_delete@U_DECOMP_FILE_HANDLE@CCabDecompress@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>::~unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>(void)
0x1800a04f1  jmp     loc_1800A0442
0x1800a04f6  xor     r9d, r9d; lpSecurityAttributes
0x1800a04f9  mov     [rbx], r14
0x1800a04fc  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800a0500  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a0505  mov     [rsp+0B0h+hTemplateFile], rsi; hTemplateFile
0x1800a050a  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a0512  lea     r8d, [r9+7]; dwShareMode
0x1800a0516  mov     [rsp+0B0h+dwCreationDisposition], 1; dwCreationDisposition
0x1800a051e  call    cs:__imp_CreateFileW
0x1800a0525  nop     dword ptr [rax+rax+00h]
0x1800a052a  mov     [rbx+8], rax
0x1800a052e  cmp     rax, r12
0x1800a0531  jnz     short loc_1800A0588
0x1800a0533  mov     rax, cs:WPP_GLOBAL_Control
0x1800a053a  lea     rdi, WPP_GLOBAL_Control
0x1800a0541  cmp     rax, rdi
0x1800a0544  jz      short loc_1800A04E8
0x1800a0546  test    byte ptr [rax+1Ch], 1
0x1800a054a  jz      short loc_1800A04E8
0x1800a054c  call    cs:__imp_GetLastError
0x1800a0553  nop     dword ptr [rax+rax+00h]
0x1800a0558  mov     ecx, eax; unsigned int
0x1800a055a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a055f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0566  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a056d  mov     r9, [rbp+57h+lpFileName]
0x1800a0571  mov     edx, 46h ; 'F'
0x1800a0576  mov     [rsp+0B0h+dwCreationDisposition], eax
0x1800a057a  mov     rcx, [rcx+10h]
0x1800a057e  call    WPP_SF_SD
0x1800a0583  jmp     loc_1800A04E8
0x1800a0588  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800a058c  mov     edx, 2080h; dwFileAttributes
0x1800a0591  call    cs:__imp_SetFileAttributesW
0x1800a0598  nop     dword ptr [rax+rax+00h]
0x1800a059d  lea     rdi, WPP_GLOBAL_Control
0x1800a05a4  test    eax, eax
0x1800a05a6  jnz     short loc_1800A05CD
0x1800a05a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a05af  cmp     rcx, rdi
0x1800a05b2  jz      short loc_1800A05F8
0x1800a05b4  test    byte ptr [rcx+1Ch], 2
0x1800a05b8  jz      short loc_1800A05D4
0x1800a05ba  mov     rcx, [rcx+10h]
0x1800a05be  lea     edx, [rax+47h]
0x1800a05c1  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a05c8  call    WPP_SF_
0x1800a05cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a05d4  cmp     rcx, rdi
0x1800a05d7  jz      short loc_1800A05F8
0x1800a05d9  test    byte ptr [rcx+1Ch], 4
0x1800a05dd  jz      short loc_1800A05F8
0x1800a05df  mov     r9, [rbp+57h+lpFileName]
0x1800a05e3  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a05ea  mov     rcx, [rcx+10h]
0x1800a05ee  mov     edx, 48h ; 'H'
0x1800a05f3  call    WPP_SF_S
0x1800a05f8  mov     rsi, rbx
0x1800a05fb  mov     [rbp+57h+arg_10], 0
0x1800a0603  jmp     loc_1800A04E8
0x1800a0608  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a060f  lea     rdi, WPP_GLOBAL_Control
0x1800a0616  cmp     rcx, rdi
0x1800a0619  jz      short loc_1800A0656
0x1800a061b  test    byte ptr [rcx+1Ch], 1
0x1800a061f  jz      short loc_1800A0656
0x1800a0621  mov     edx, 49h ; 'I'
0x1800a0626  jmp     short loc_1800A0646
0x1800a0628  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a062f  lea     rdi, WPP_GLOBAL_Control
0x1800a0636  cmp     rcx, rdi
0x1800a0639  jz      short loc_1800A0656
0x1800a063b  test    byte ptr [rcx+1Ch], 1
0x1800a063f  jz      short loc_1800A0656
0x1800a0641  mov     edx, 41h ; 'A'
0x1800a0646  mov     rcx, [rcx+10h]
0x1800a064a  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a0651  call    WPP_SF_
0x1800a0656  mov     rax, rsi
0x1800a0659  add     rsp, 88h
0x1800a0660  pop     r14
0x1800a0662  pop     r12
0x1800a0664  pop     rdi
0x1800a0665  pop     rsi
0x1800a0666  pop     rbx
0x1800a0667  pop     rbp
0x1800a0668  retn
```
