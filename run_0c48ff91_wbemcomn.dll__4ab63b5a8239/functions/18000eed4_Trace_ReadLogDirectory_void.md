# __Trace::ReadLogDirectory(void)

- ea: `0x18000eed4`
- end: `0x18000f2b1`
- name: `?ReadLogDirectory@__Trace@@AEAAXXZ`
- size: `989`
- prototype: `void __fastcall(__Trace *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x18000ab30`
- `0x18000eed4`
- `0x18000f4c0`
- `0x18000f670`
- `0x18000f8a0`
- `0x18001016c`
- `0x180011e40`
- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x180028d80`
- `0x180028de4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ef4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ef4b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000f063`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000f0df`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000f063`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000f0df`

## string_xrefs

- `0x18000ef10`: `Logging Directory`
- `0x18000f11a`: `Logging Directory`
- `0x18000f1cc`: `Logging Directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __Trace::ReadLogDirectory(const WCHAR *this)
{
  int Str; // eax
  WCHAR *v2; // rdi
  UINT SystemDirectoryW; // eax
  __int64 v4; // rdx
  WCHAR *v5; // rax
  unsigned int v6; // edi
  __int64 v7; // r8
  __int64 v8; // rax
  const wchar_t *v9; // rcx
  __int64 v10; // rbx
  _WORD *v11; // rdx
  _WORD *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  WCHAR *v18; // r8
  WCHAR v19; // r9
  unsigned int v20; // r14d
  WCHAR *v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // [rsp+30h] [rbp-58h] BYREF
  __int64 v27; // [rsp+38h] [rbp-50h]
  int v28; // [rsp+44h] [rbp-44h]
  LPCWSTR lpString; // [rsp+90h] [rbp+8h] BYREF

  lpString = this;
  Registry::Registry((Registry *)&v26, L"Software\\Microsoft\\WBEM\\CIMOM", 3u);
  lpString = 0;
  Str = Registry::GetStr((Registry *)&v26, L"Logging Directory", (unsigned __int16 **)&lpString);
  v2 = (WCHAR *)lpString;
  if ( Str == 1 || lstrlenW(lpString) > 260 )
  {
    CMUILocale::_Free(v2);
    SystemDirectoryW = GetSystemDirectoryW(PathName, 0x105u);
    v4 = 261;
    if ( SystemDirectoryW )
    {
      v5 = PathName;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v4;
      }
      while ( v4 );
      v6 = v4 == 0 ? 0x80070057 : 0;
      v7 = (261 - v4) & -(__int64)(v4 != 0);
      if ( !v4 )
        goto LABEL_47;
      v8 = 2147483646;
      v9 = L"\\WBEM\\Logs\\";
      v10 = 261 - v7;
      v11 = (_WORD *)&__g_traceInfo + v7 + 6;
      if ( 261 != v7 )
      {
        do
        {
          if ( !v8 )
            break;
          LODWORD(v7) = *v9;
          if ( !(_WORD)v7 )
            break;
          ++v9;
          *v11++ = v7;
          --v8;
          --v10;
        }
        while ( v10 );
      }
      v6 = v10 == 0 ? 0x8007007A : 0;
      v12 = v11 - 1;
      if ( v10 )
        v12 = v11;
      *v12 = 0;
      if ( !v10 )
      {
LABEL_47:
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v6);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v6);
        }
      }
      v13 = -1;
      do
        ++v13;
      while ( PathName[v13] );
      if ( v27 )
        v28 = DLRegSetValueExW(v27, (unsigned int)L"Logging Directory", v7, 1, (__int64)PathName, 2 * (int)v13 + 2);
    }
    else
    {
      v24 = StringCchCopyW(PathName, 0x105u, L"c:\\");
      v25 = v24;
      if ( v24 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v24);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v25);
        }
      }
    }
  }
  else
  {
    v15 = 2147483646;
    v16 = v2;
    v17 = 261;
    v18 = PathName;
    do
    {
      if ( !v15 )
        break;
      v19 = *v16;
      if ( !*v16 )
        break;
      ++v16;
      *v18++ = v19;
      --v15;
      --v17;
    }
    while ( v17 );
    v20 = v17 == 0 ? 0x8007007A : 0;
    v21 = v18 - 1;
    if ( v17 )
      v21 = v18;
    *v21 = 0;
    if ( !v17 )
    {
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v20);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v20);
      }
    }
    if ( *((_WORD *)&__g_traceInfo + lstrlenW(PathName) + 5) != 92 )
    {
      v22 = StringCchCatW(PathName, 0x105u, L"\\");
      v23 = v22;
      if ( v22 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v22);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v23);
        }
      }
      Registry::SetStr((Registry *)&v26, L"Logging Directory", PathName);
    }
    CMUILocale::_Free(v2);
  }
  TestDirExistAndCreateWithSDIfNotThere(
    PathName,
    L"D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)(A;CIOI;GRGWDTSD;;;NS)(A;CIOI;GRGWSD;;;LS)");
  v14 = v27;
  if ( v27 )
  {
    DLRegCloseKey(v27);
    v14 = v27;
  }
  if ( v26 != v14 )
    DLRegCloseKey(v26);
}

```

## disassembly

```asm
0x18000eed4  mov     [rsp+lpString], rcx
0x18000eed9  push    rbx
0x18000eeda  push    rbp
0x18000eedb  push    rsi
0x18000eedc  push    rdi
0x18000eedd  push    r14
0x18000eedf  push    r15
0x18000eee1  sub     rsp, 58h
0x18000eee5  mov     r8d, 3; unsigned int
0x18000eeeb  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000eef2  lea     rcx, [rsp+88h+var_58]; this
0x18000eef7  call    ??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x18000eefc  nop
0x18000eefd  xor     r15d, r15d
0x18000ef00  mov     [rsp+88h+lpString], r15
0x18000ef08  lea     r8, [rsp+88h+lpString]; unsigned __int16 **
0x18000ef10  lea     rdx, aLoggingDirecto; "Logging Directory"
0x18000ef17  lea     rcx, [rsp+88h+var_58]; this
0x18000ef1c  call    ?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z; Registry::GetStr(ushort const *,ushort * *)
0x18000ef21  mov     rdi, [rsp+88h+lpString]
0x18000ef29  cmp     eax, 1
0x18000ef2c  jnz     loc_18000F060
0x18000ef32  mov     rcx, rdi; void *
0x18000ef35  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18000ef3a  mov     ebx, 105h
0x18000ef3f  mov     edx, ebx; uSize
0x18000ef41  lea     rsi, PathName
0x18000ef48  mov     rcx, rsi; lpBuffer
0x18000ef4b  call    cs:__imp_GetSystemDirectoryW
0x18000ef51  mov     edx, ebx; unsigned __int64
0x18000ef53  test    eax, eax
0x18000ef55  jz      loc_18000F1E2
0x18000ef5b  mov     rax, rsi
0x18000ef5e  cmp     [rax], r15w
0x18000ef62  jz      short loc_18000EF6E
0x18000ef64  add     rax, 2
0x18000ef68  sub     rdx, 1
0x18000ef6c  jnz     short loc_18000EF5E
0x18000ef6e  mov     rax, rdx
0x18000ef71  neg     rax
0x18000ef74  sbb     edi, edi
0x18000ef76  not     edi
0x18000ef78  and     edi, 80070057h
0x18000ef7e  mov     rax, rdx
0x18000ef81  mov     rcx, rbx
0x18000ef84  sub     rcx, rdx
0x18000ef87  neg     rax
0x18000ef8a  sbb     r8, r8
0x18000ef8d  and     r8, rcx
0x18000ef90  test    rdx, rdx
0x18000ef93  jz      loc_18000F251
0x18000ef99  mov     eax, 7FFFFFFEh
0x18000ef9e  lea     rcx, aWbemLogs; "\\WBEM\\Logs\\"
0x18000efa5  sub     rbx, r8
0x18000efa8  lea     rdx, ?__g_traceInfo@@3V__Trace@@A; __Trace __g_traceInfo
0x18000efaf  lea     rdx, [rdx+r8*2]
0x18000efb3  lea     rdx, [rdx+0Ch]
0x18000efb7  jz      short loc_18000EFDD
0x18000efb9  test    rax, rax
0x18000efbc  jz      short loc_18000EFDD
0x18000efbe  movzx   r8d, word ptr [rcx]
0x18000efc2  test    r8w, r8w
0x18000efc6  jz      short loc_18000EFDD
0x18000efc8  add     rcx, 2
0x18000efcc  mov     [rdx], r8w
0x18000efd0  add     rdx, 2
0x18000efd4  dec     rax
0x18000efd7  sub     rbx, 1
0x18000efdb  jnz     short loc_18000EFB9
0x18000efdd  mov     rax, rbx
0x18000efe0  neg     rax
0x18000efe3  sbb     edi, edi
0x18000efe5  not     edi
0x18000efe7  and     edi, 8007007Ah
0x18000efed  lea     rcx, [rdx-2]
0x18000eff1  test    rbx, rbx
0x18000eff4  cmovnz  rcx, rdx
0x18000eff8  mov     [rcx], r15w
0x18000effc  jz      loc_18000F251
0x18000f002  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f006  inc     rax
0x18000f009  cmp     [rsi+rax*2], r15w
0x18000f00e  jnz     short loc_18000F006
0x18000f010  mov     rcx, [rsp+88h+var_50]
0x18000f015  test    rcx, rcx
0x18000f018  jnz     loc_18000F104
0x18000f01e  lea     rdx, aDPACioiGaBaACi; "D:P(A;CIOI;GA;;;BA)(A;CIOI;GA;;;SY)(A;C"...
0x18000f025  mov     rcx, rsi; lpPathName
0x18000f028  call    ?TestDirExistAndCreateWithSDIfNotThere@@YAJPEAG0@Z; TestDirExistAndCreateWithSDIfNotThere(ushort *,ushort *)
0x18000f02d  nop
0x18000f02e  mov     rax, [rsp+88h+var_50]
0x18000f033  test    rax, rax
0x18000f036  jz      short loc_18000F045
0x18000f038  mov     rcx, rax
0x18000f03b  call    DLRegCloseKey
0x18000f040  mov     rax, [rsp+88h+var_50]
0x18000f045  mov     rcx, [rsp+88h+var_58]
0x18000f04a  cmp     rcx, rax
0x18000f04d  jnz     loc_18000F2A7
0x18000f053  add     rsp, 58h
0x18000f057  pop     r15
0x18000f059  pop     r14
0x18000f05b  pop     rdi
0x18000f05c  pop     rsi
0x18000f05d  pop     rbp
0x18000f05e  pop     rbx
0x18000f05f  retn
0x18000f060  mov     rcx, rdi; lpString
0x18000f063  call    cs:__imp_lstrlenW
0x18000f069  cmp     eax, 104h
0x18000f06e  jg      loc_18000EF32
0x18000f074  mov     eax, 7FFFFFFEh
0x18000f079  mov     rcx, rdi
0x18000f07c  mov     ebx, 105h
0x18000f081  mov     edx, ebx
0x18000f083  lea     rsi, PathName
0x18000f08a  mov     r8, rsi
0x18000f08d  test    rax, rax
0x18000f090  jz      short loc_18000F0B1
0x18000f092  movzx   r9d, word ptr [rcx]
0x18000f096  test    r9w, r9w
0x18000f09a  jz      short loc_18000F0B1
0x18000f09c  add     rcx, 2
0x18000f0a0  mov     [r8], r9w
0x18000f0a4  add     r8, 2
0x18000f0a8  dec     rax
0x18000f0ab  sub     rdx, 1
0x18000f0af  jnz     short loc_18000F08D
0x18000f0b1  mov     rax, rdx
0x18000f0b4  neg     rax
0x18000f0b7  sbb     r14d, r14d
0x18000f0ba  not     r14d
0x18000f0bd  and     r14d, 8007007Ah
0x18000f0c4  lea     rcx, [r8-2]
0x18000f0c8  test    rdx, rdx
0x18000f0cb  cmovnz  rcx, r8
0x18000f0cf  mov     [rcx], r15w
0x18000f0d3  lea     rbp, WPP_GLOBAL_Control
0x18000f0da  jz      short loc_18000F12F
0x18000f0dc  mov     rcx, rsi; lpString
0x18000f0df  call    cs:__imp_lstrlenW
0x18000f0e5  movsxd  rcx, eax
0x18000f0e8  lea     rdx, ?__g_traceInfo@@3V__Trace@@A; __Trace __g_traceInfo
0x18000f0ef  cmp     word ptr [rdx+rcx*2+0Ah], 5Ch ; '\'
0x18000f0f5  jnz     short loc_18000F173
0x18000f0f7  mov     rcx, rdi; void *
0x18000f0fa  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18000f0ff  jmp     loc_18000F01E
0x18000f104  lea     eax, ds:2[rax*2]
0x18000f10b  mov     [rsp+88h+var_60], eax
0x18000f10f  mov     [rsp+88h+var_68], rsi
0x18000f114  mov     r9d, 1
0x18000f11a  lea     rdx, aLoggingDirecto; "Logging Directory"
0x18000f121  call    DLRegSetValueExW
0x18000f126  mov     [rsp+88h+var_44], eax
0x18000f12a  jmp     loc_18000F01E
0x18000f12f  mov     edx, r14d; int
0x18000f132  lea     rcx, unk_18006A9C0; this
0x18000f139  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f13e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f145  cmp     rcx, rbp
0x18000f148  jz      short loc_18000F0DC
0x18000f14a  test    byte ptr [rcx+1Ch], 1
0x18000f14e  jz      short loc_18000F0DC
0x18000f150  cmp     byte ptr [rcx+19h], 2
0x18000f154  jb      short loc_18000F0DC
0x18000f156  mov     edx, 11h
0x18000f15b  mov     r9d, r14d
0x18000f15e  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18000f165  mov     rcx, [rcx+10h]
0x18000f169  call    WPP_SF_D
0x18000f16e  jmp     loc_18000F0DC
0x18000f173  lea     r8, asc_18004CC00; "\\"
0x18000f17a  mov     rdx, rbx; unsigned __int64
0x18000f17d  mov     rcx, rsi; unsigned __int16 *
0x18000f180  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f185  mov     ebx, eax
0x18000f187  test    eax, eax
0x18000f189  jns     short loc_18000F1C9
0x18000f18b  mov     edx, eax; int
0x18000f18d  lea     rcx, unk_18006A9C0; this
0x18000f194  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f199  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1a0  cmp     rcx, rbp
0x18000f1a3  jz      short loc_18000F1C9
0x18000f1a5  test    byte ptr [rcx+1Ch], 1
0x18000f1a9  jz      short loc_18000F1C9
0x18000f1ab  cmp     byte ptr [rcx+19h], 2
0x18000f1af  jb      short loc_18000F1C9
0x18000f1b1  mov     edx, 12h
0x18000f1b6  mov     r9d, ebx
0x18000f1b9  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18000f1c0  mov     rcx, [rcx+10h]
0x18000f1c4  call    WPP_SF_D
0x18000f1c9  mov     r8, rsi; unsigned __int16 *
0x18000f1cc  lea     rdx, aLoggingDirecto; "Logging Directory"
0x18000f1d3  lea     rcx, [rsp+88h+var_58]; this
0x18000f1d8  call    ?SetStr@Registry@@QEAAHPEBG0@Z; Registry::SetStr(ushort const *,ushort const *)
0x18000f1dd  jmp     loc_18000F0F7
0x18000f1e2  lea     r8, aC; "c:\\"
0x18000f1e9  mov     rcx, rsi; unsigned __int16 *
0x18000f1ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f1f1  mov     ebx, eax
0x18000f1f3  test    eax, eax
0x18000f1f5  jns     loc_18000F01E
0x18000f1fb  mov     edx, eax; int
0x18000f1fd  lea     rcx, unk_18006A9C0; this
0x18000f204  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f209  lea     rbp, WPP_GLOBAL_Control
0x18000f210  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f217  cmp     rcx, rbp
0x18000f21a  jz      loc_18000F01E
0x18000f220  test    byte ptr [rcx+1Ch], 1
0x18000f224  jz      loc_18000F01E
0x18000f22a  cmp     byte ptr [rcx+19h], 2
0x18000f22e  jb      loc_18000F01E
0x18000f234  mov     edx, 0Fh
0x18000f239  mov     r9d, ebx
0x18000f23c  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18000f243  mov     rcx, [rcx+10h]
0x18000f247  call    WPP_SF_D
0x18000f24c  jmp     loc_18000F01E
0x18000f251  mov     edx, edi; int
0x18000f253  lea     rcx, unk_18006A9C0; this
0x18000f25a  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f25f  lea     rbp, WPP_GLOBAL_Control
0x18000f266  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f26d  cmp     rcx, rbp
0x18000f270  jz      loc_18000F002
0x18000f276  test    byte ptr [rcx+1Ch], 1
0x18000f27a  jz      loc_18000F002
0x18000f280  cmp     byte ptr [rcx+19h], 2
0x18000f284  jb      loc_18000F002
0x18000f28a  mov     edx, 10h
0x18000f28f  mov     r9d, edi
0x18000f292  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18000f299  mov     rcx, [rcx+10h]
0x18000f29d  call    WPP_SF_D
0x18000f2a2  jmp     loc_18000F002
0x18000f2a7  call    DLRegCloseKey
0x18000f2ac  jmp     loc_18000F053
```
