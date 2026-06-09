# CCabDecompress::FDINotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x18009ba7c`
- end: `0x18009bda9`
- name: `?FDINotify@CCabDecompress@@IEAA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `813`
- prototype: `_BOOL8 __fastcall(HANDLE *this, enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009bff0`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000dad0`
- `0x180013730`
- `0x180014720`
- `0x18001fe24`
- `0x180076f94`
- `0x1800987e0`
- `0x18009b9b8`
- `0x18009ba48`
- `0x18009ba7c`
- `0x18009bf40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bc98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bc98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009bab9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009bab9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009bcd7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009bcd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009bc70`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009bc70`

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
0x18009ba7c  push    rbp
0x18009ba7e  push    rbx
0x18009ba7f  push    rsi
0x18009ba80  push    rdi
0x18009ba81  push    r12
0x18009ba83  push    r14
0x18009ba85  lea     rbp, [rsp-2Fh]
0x18009ba8a  sub     rsp, 88h
0x18009ba91  or      r12, 0FFFFFFFFFFFFFFFFh
0x18009ba95  mov     rdi, r8
0x18009ba98  mov     ebx, edx
0x18009ba9a  mov     r14, rcx
0x18009ba9d  mov     rsi, r12
0x18009baa0  test    r8, r8
0x18009baa3  jz      loc_18009BD68
0x18009baa9  cmp     qword ptr [r8+20h], 0
0x18009baae  jz      loc_18009BD68
0x18009bab4  mov     rcx, [rcx]; hHandle
0x18009bab7  xor     edx, edx; dwMilliseconds
0x18009bab9  call    cs:__imp_WaitForSingleObject
0x18009babf  test    eax, eax
0x18009bac1  jnz     short loc_18009BAEC
0x18009bac3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009baca  lea     rdi, WPP_GLOBAL_Control
0x18009bad1  cmp     rcx, rdi
0x18009bad4  jz      loc_18009BD96
0x18009bada  test    byte ptr [rcx+1Ch], 4
0x18009bade  jz      loc_18009BD96
0x18009bae4  lea     edx, [rax+42h]
0x18009bae7  jmp     loc_18009BD86
0x18009baec  sub     ebx, 1
0x18009baef  jz      loc_18009BD48
0x18009baf5  sub     ebx, 1
0x18009baf8  jz      short loc_18009BB25
0x18009bafa  sub     ebx, 1
0x18009bafd  jz      short loc_18009BB0F
0x18009baff  cmp     ebx, 1
0x18009bb02  jz      loc_18009BD48
0x18009bb08  xor     esi, esi
0x18009bb0a  jmp     loc_18009BD96
0x18009bb0f  mov     rcx, [rdi+28h]; hf
0x18009bb13  call    ?static_FDIClose@CCabDecompress@@KAH_J@Z; CCabDecompress::static_FDIClose(__int64)
0x18009bb18  xor     esi, esi
0x18009bb1a  test    eax, eax
0x18009bb1c  setz    sil
0x18009bb20  jmp     loc_18009BD96
0x18009bb25  lea     rcx, [rbp+57h+lpFileName]; void *
0x18009bb29  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009bb2e  lea     rcx, [rbp+57h+var_70]; void *
0x18009bb32  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009bb37  mov     rcx, [rbp+57h+var_70]
0x18009bb3b  xor     esi, esi
0x18009bb3d  xor     eax, eax
0x18009bb3f  mov     [rbp+57h+var_68], rcx
0x18009bb43  mov     r8, r12
0x18009bb46  mov     [rcx], ax
0x18009bb49  mov     rdx, [rdi+8]
0x18009bb4d  inc     r8
0x18009bb50  cmp     [rdx+r8], al
0x18009bb54  jnz     short loc_18009BB4D
0x18009bb56  lea     rcx, [rbp+57h+var_70]
0x18009bb5a  call    ??$_AppendMbcsImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEBD_KII@Z; tlx::_AppendMbcsImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,char const *,unsigned __int64,uint,uint)
0x18009bb5f  test    eax, eax
0x18009bb61  jns     short loc_18009BBAB
0x18009bb63  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bb6a  lea     rdi, WPP_GLOBAL_Control
0x18009bb71  cmp     rcx, rdi
0x18009bb74  jz      short loc_18009BB94
0x18009bb76  test    byte ptr [rcx+1Ch], 1
0x18009bb7a  jz      short loc_18009BB94
0x18009bb7c  mov     rcx, [rcx+10h]
0x18009bb80  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bb87  mov     edx, 43h ; 'C'
0x18009bb8c  mov     r9d, eax
0x18009bb8f  call    WPP_SF_d
0x18009bb94  lea     rcx, [rbp+57h+var_70]; void *
0x18009bb98  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009bb9d  lea     rcx, [rbp+57h+lpFileName]; void *
0x18009bba1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009bba6  jmp     loc_18009BD96
0x18009bbab  mov     rdx, [rbp+57h+var_70]
0x18009bbaf  lea     r8, [rbp+57h+lpFileName]
0x18009bbb3  mov     rcx, [r14+8]
0x18009bbb7  call    ?UtilGetUniquePath@@YAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetUniquePath(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18009bbbc  test    eax, eax
0x18009bbbe  jns     short loc_18009BBF8
0x18009bbc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bbc7  lea     rdi, WPP_GLOBAL_Control
0x18009bbce  cmp     rcx, rdi
0x18009bbd1  jz      short loc_18009BB94
0x18009bbd3  test    byte ptr [rcx+1Ch], 1
0x18009bbd7  jz      short loc_18009BB94
0x18009bbd9  mov     r9, [rbp+57h+var_70]
0x18009bbdd  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bbe4  mov     rcx, [rcx+10h]
0x18009bbe8  mov     edx, 44h ; 'D'
0x18009bbed  mov     [rsp+0B0h+dwCreationDisposition], eax
0x18009bbf1  call    WPP_SF_SD
0x18009bbf6  jmp     short loc_18009BB94
0x18009bbf8  lea     rcx, [rbp+57h+arg_10]
0x18009bbfc  call    ??$make_unique@U_DECOMP_FILE_HANDLE@CCabDecompress@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_DECOMP_FILE_HANDLE@CCabDecompress@@U?$default_delete@U_DECOMP_FILE_HANDLE@CCabDecompress@@@utl@@@0@XZ; utl::make_unique<CCabDecompress::_DECOMP_FILE_HANDLE,,0>(void)
0x18009bc01  mov     rbx, [rbp+57h+arg_10]
0x18009bc05  test    rbx, rbx
0x18009bc08  jnz     short loc_18009BC48
0x18009bc0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc11  lea     rdi, WPP_GLOBAL_Control
0x18009bc18  cmp     rcx, rdi
0x18009bc1b  jz      short loc_18009BC3A
0x18009bc1d  test    byte ptr [rcx+1Ch], 1
0x18009bc21  jz      short loc_18009BC3A
0x18009bc23  mov     r9, [rbp+57h+var_70]
0x18009bc27  lea     edx, [rbx+45h]
0x18009bc2a  mov     rcx, [rcx+10h]
0x18009bc2e  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bc35  call    WPP_SF_S
0x18009bc3a  lea     rcx, [rbp+57h+arg_10]
0x18009bc3e  call    ??1?$unique_ptr@U_DECOMP_FILE_HANDLE@CCabDecompress@@U?$default_delete@U_DECOMP_FILE_HANDLE@CCabDecompress@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>::~unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>(void)
0x18009bc43  jmp     loc_18009BB94
0x18009bc48  xor     r9d, r9d; lpSecurityAttributes
0x18009bc4b  mov     [rbx], r14
0x18009bc4e  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18009bc52  mov     edx, 0C0000000h; dwDesiredAccess
0x18009bc57  mov     [rsp+0B0h+hTemplateFile], rsi; hTemplateFile
0x18009bc5c  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009bc64  lea     r8d, [r9+7]; dwShareMode
0x18009bc68  mov     [rsp+0B0h+dwCreationDisposition], 1; dwCreationDisposition
0x18009bc70  call    cs:__imp_CreateFileW
0x18009bc76  mov     [rbx+8], rax
0x18009bc7a  cmp     rax, r12
0x18009bc7d  jnz     short loc_18009BCCE
0x18009bc7f  mov     rax, cs:WPP_GLOBAL_Control
0x18009bc86  lea     rdi, WPP_GLOBAL_Control
0x18009bc8d  cmp     rax, rdi
0x18009bc90  jz      short loc_18009BC3A
0x18009bc92  test    byte ptr [rax+1Ch], 1
0x18009bc96  jz      short loc_18009BC3A
0x18009bc98  call    cs:__imp_GetLastError
0x18009bc9e  mov     ecx, eax; unsigned int
0x18009bca0  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009bca5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bcac  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bcb3  mov     r9, [rbp+57h+lpFileName]
0x18009bcb7  mov     edx, 46h ; 'F'
0x18009bcbc  mov     [rsp+0B0h+dwCreationDisposition], eax
0x18009bcc0  mov     rcx, [rcx+10h]
0x18009bcc4  call    WPP_SF_SD
0x18009bcc9  jmp     loc_18009BC3A
0x18009bcce  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18009bcd2  mov     edx, 2080h; dwFileAttributes
0x18009bcd7  call    cs:__imp_SetFileAttributesW
0x18009bcdd  lea     rdi, WPP_GLOBAL_Control
0x18009bce4  test    eax, eax
0x18009bce6  jnz     short loc_18009BD0D
0x18009bce8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bcef  cmp     rcx, rdi
0x18009bcf2  jz      short loc_18009BD38
0x18009bcf4  test    byte ptr [rcx+1Ch], 2
0x18009bcf8  jz      short loc_18009BD14
0x18009bcfa  mov     rcx, [rcx+10h]
0x18009bcfe  lea     edx, [rax+47h]
0x18009bd01  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bd08  call    WPP_SF_
0x18009bd0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bd14  cmp     rcx, rdi
0x18009bd17  jz      short loc_18009BD38
0x18009bd19  test    byte ptr [rcx+1Ch], 4
0x18009bd1d  jz      short loc_18009BD38
0x18009bd1f  mov     r9, [rbp+57h+lpFileName]
0x18009bd23  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bd2a  mov     rcx, [rcx+10h]
0x18009bd2e  mov     edx, 48h ; 'H'
0x18009bd33  call    WPP_SF_S
0x18009bd38  mov     rsi, rbx
0x18009bd3b  mov     [rbp+57h+arg_10], 0
0x18009bd43  jmp     loc_18009BC3A
0x18009bd48  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bd4f  lea     rdi, WPP_GLOBAL_Control
0x18009bd56  cmp     rcx, rdi
0x18009bd59  jz      short loc_18009BD96
0x18009bd5b  test    byte ptr [rcx+1Ch], 1
0x18009bd5f  jz      short loc_18009BD96
0x18009bd61  mov     edx, 49h ; 'I'
0x18009bd66  jmp     short loc_18009BD86
0x18009bd68  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bd6f  lea     rdi, WPP_GLOBAL_Control
0x18009bd76  cmp     rcx, rdi
0x18009bd79  jz      short loc_18009BD96
0x18009bd7b  test    byte ptr [rcx+1Ch], 1
0x18009bd7f  jz      short loc_18009BD96
0x18009bd81  mov     edx, 41h ; 'A'
0x18009bd86  mov     rcx, [rcx+10h]
0x18009bd8a  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bd91  call    WPP_SF_
0x18009bd96  mov     rax, rsi
0x18009bd99  add     rsp, 88h
0x18009bda0  pop     r14
0x18009bda2  pop     r12
0x18009bda4  pop     rdi
0x18009bda5  pop     rsi
0x18009bda6  pop     rbx
0x18009bda7  pop     rbp
0x18009bda8  retn
```
