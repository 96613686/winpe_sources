# SetUpChannelDataStruct(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ *,ELF_LOG_TYPE,bool)

- ea: `0x180004264`
- end: `0x1800047aa`
- name: `?SetUpChannelDataStruct@@YAJV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAUHKEY__@@W4ELF_LOG_TYPE@@_N@Z`
- size: `1350`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, installer_update`

## callers

- `0x1800053ac`
- `0x180078c1c`
- `0x1800c4170`

## callees

- `0x180004264`
- `0x180004980`
- `0x180004a3c`
- `0x180004c74`
- `0x1800054d8`
- `0x180014bd0`
- `0x18001722c`
- `0x180017b60`
- `0x18001c310`
- `0x18001c320`
- `0x18002de70`
- `0x180086f1c`
- `0x180087144`
- `0x1800872c0`
- `0x180088928`
- `0x180088a10`
- `0x18008b224`
- `0x18008c540`
- `0x18008d400`
- `0x1800919c4`
- `0x180091b80`
- `0x180092008`
- `0x180092ee4`
- `0x1800c19a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000434d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000434d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800044ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004642`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800044ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004642`
- `RPCRT4!RpcImpersonateClient` at `0x18000459f`
- `RPCRT4!RpcImpersonateClient` at `0x18000459f`
- `RPCRT4!RpcRevertToSelf` at `0x1800045d8`
- `RPCRT4!RpcRevertToSelf` at `0x1800045d8`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800045a7`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800045a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SetUpChannelDataStruct(_QWORD *a1, __int128 *a2, HKEY a3, int a4, char a5)
{
  __int64 v8; // r15
  _QWORD *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  _QWORD *v12; // rsi
  __int64 v13; // rcx
  char v14; // r12
  __int64 LogFileFromName; // rdi
  int v16; // eax
  unsigned int v17; // edx
  int v18; // ebx
  unsigned int ModuleType; // eax
  int updated; // eax
  void *v21; // r14
  void *v22; // rcx
  void *v24; // rax
  __int64 v25; // rax
  RPC_STATUS v26; // eax
  int v27; // eax
  _QWORD *v28; // rax
  PVOID *v29; // rcx
  void *v30; // [rsp+38h] [rbp-41h] BYREF
  __int64 v31; // [rsp+40h] [rbp-39h] BYREF
  struct LOGMODULE *v32; // [rsp+48h] [rbp-31h]
  __int128 v33; // [rsp+58h] [rbp-21h] BYREF
  __int128 v34; // [rsp+68h] [rbp-11h] BYREF
  void *v35[2]; // [rsp+78h] [rbp-1h] BYREF
  _BYTE v36[64]; // [rsp+88h] [rbp+Fh] BYREF
  _QWORD *v37; // [rsp+D8h] [rbp+5Fh] BYREF
  HKEY v38; // [rsp+E8h] [rbp+6Fh]

  v38 = a3;
  v37 = a1;
  v8 = 0;
  v31 = 0;
  if ( !a1[1] && a4 == 2 || !*((_QWORD *)a2 + 1) )
    return (unsigned int)-1073741811;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  v33 = *a2;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v35) )
    goto LABEL_82;
  v9 = MIDL_user_allocate(0x28u);
  v12 = v9;
  if ( v9 )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      v9,
      v35,
      v10,
      v11);
    *(_QWORD *)(v13 + 32) = 0;
  }
  else
  {
    v12 = 0;
  }
  v30 = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids);
    }
    goto LABEL_26;
  }
  if ( a4 != 2 || (v14 = 0, v33 = *(_OWORD *)a1, (LogFileFromName = FindLogFileFromName(&v33)) == 0) )
  {
    v33 = *a2;
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v35) )
    {
      v24 = MIDL_user_allocate(0x88u);
      if ( v24 )
      {
        v25 = LOGFILE::LOGFILE(v24, v35);
        v8 = v25;
        v31 = v25;
        if ( v25 )
        {
          v14 = 4;
          LogFileFromName = v25;
          goto LABEL_9;
        }
      }
      else
      {
        v31 = 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids);
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v12);
      utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(
        v12,
        40);
LABEL_26:
      if ( v35[0] != v36 )
        operator delete(v35[0]);
      return (unsigned int)-1073741801;
    }
    utl::unique_ptr<LOGMODULE,utl::default_delete<LOGMODULE>>::~unique_ptr<LOGMODULE,utl::default_delete<LOGMODULE>>(&v30);
LABEL_82:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
    utl::unique_ptr<LOGFILE,utl::default_delete<LOGFILE>>::~unique_ptr<LOGFILE,utl::default_delete<LOGFILE>>(&v31);
    return 3221225495LL;
  }
LABEL_9:
  v32 = (struct LOGMODULE *)5;
  *(_QWORD *)&v33 = LogFileFromName + 120;
  AcquireSRWLockExclusive((PSRWLOCK)(LogFileFromName + 120));
  _InterlockedIncrement((volatile signed __int32 *)(LogFileFromName + 128));
  v12[4] = LogFileFromName;
  if ( a4 == 2 )
  {
    v26 = RpcImpersonateClient(0);
    v27 = I_RpcMapWin32Status(v26);
    v18 = v27;
    if ( v27 < 0 )
    {
      v29 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_33:
        _InterlockedDecrement((volatile signed __int32 *)(LogFileFromName + 128));
LABEL_34:
        v21 = v30;
        goto LABEL_35;
      }
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_68:
        if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x1000) != 0 && *((_BYTE *)v29 + 25) >= 2u )
          WPP_SF_Sd((unsigned int)v29[2], 16, (unsigned int)&WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids, *v37, v18);
        goto LABEL_33;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids,
        (unsigned int)v27);
    }
    else
    {
      v34 = *(_OWORD *)v37;
      v18 = OpenLogFile(LogFileFromName, &v34);
      RpcRevertToSelf();
      if ( v18 >= 0 )
      {
        v14 |= 1u;
        goto LABEL_54;
      }
    }
    v29 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_68;
  }
  if ( *(&gInitStatus + 1) < 2u )
    goto LABEL_13;
  v16 = AddChannelToSingleLog(LogFileFromName);
  v18 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids,
        *v37,
        v16);
    }
    goto LABEL_33;
  }
  v14 |= 1u;
LABEL_13:
  v34 = *a2;
  ModuleType = GetModuleType(&v34);
  if ( ModuleType == 2 )
  {
    v32 = ElfDefaultLogModule;
    ElfDefaultLogModule = (struct LOGMODULE *)v12;
  }
  updated = ElfpUpdateCustomSD((struct LOGFILE *)LogFileFromName, ModuleType, v38, 1);
  v18 = updated;
  if ( updated < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids,
        *v37,
        updated);
    }
    if ( (v14 & 1) != 0 )
      goto LABEL_34;
    goto LABEL_33;
  }
LABEL_54:
  if ( v8 )
  {
    v28 = (_QWORD *)v8;
    v8 = 0;
    v37 = v28;
    if ( !(unsigned __int8)LinkLogFile(&v37) )
    {
      v21 = v30;
      goto LABEL_84;
    }
  }
  v21 = 0;
  v37 = v12;
  if ( !(unsigned __int8)LinkLogModule(&v37) )
  {
LABEL_84:
    v18 = -1073741801;
    if ( (v14 & 1) != 0 )
      goto LABEL_36;
    _InterlockedDecrement((volatile signed __int32 *)(LogFileFromName + 128));
LABEL_35:
    if ( (v14 & 1) == 0 )
    {
LABEL_37:
      if ( v32 != (struct LOGMODULE *)5 )
        ElfDefaultLogModule = v32;
      ReleaseSRWLockExclusive((PSRWLOCK)(LogFileFromName + 120));
      if ( v21 )
      {
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v21);
        utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(
          v21,
          40);
      }
      v22 = v35[0];
      if ( v35[0] != v36 )
        operator delete(v35[0]);
      if ( v8 )
        utl::default_delete<LOGFILE>::operator()(v22, v8);
      return (unsigned int)v18;
    }
LABEL_36:
    CloseLogFile((struct LOGFILE *)LogFileFromName, v17, 0);
    goto LABEL_37;
  }
  if ( a4 != 2 && !a5 )
    SetUpModules(v38, (struct LOGFILE *)LogFileFromName, 0);
  ReleaseSRWLockExclusive((PSRWLOCK)(LogFileFromName + 120));
  if ( v35[0] != v36 )
    operator delete(v35[0]);
  return 0;
}

```

## disassembly

```asm
0x180004264  mov     rax, rsp
0x180004267  mov     [rax+10h], rbx
0x18000426b  mov     [rax+18h], r8
0x18000426f  mov     [rax+8], rcx
0x180004273  push    rbp
0x180004274  push    rsi
0x180004275  push    rdi
0x180004276  push    r12
0x180004278  push    r13
0x18000427a  push    r14
0x18000427c  push    r15
0x18000427e  lea     rbp, [rax-57h]
0x180004282  sub     rsp, 90h
0x180004289  mov     r13d, r9d
0x18000428c  mov     r14, rdx
0x18000428f  mov     rbx, rcx
0x180004292  xor     r15d, r15d
0x180004295  mov     [rbp+4Fh+var_88], r15
0x180004299  lea     edi, [r15+2]
0x18000429d  cmp     [rcx+8], r15
0x1800042a1  jz      loc_180004733
0x1800042a7  cmp     qword ptr [rdx+8], 0
0x1800042ac  jz      loc_180004729
0x1800042b2  lea     rcx, [rbp+4Fh+var_50]; void *
0x1800042b6  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800042bb  nop
0x1800042bc  movaps  xmm0, xmmword ptr [r14]
0x1800042c0  movdqa  [rbp+4Fh+var_70], xmm0
0x1800042c5  lea     rdx, [rbp+4Fh+var_70]
0x1800042c9  lea     rcx, [rbp+4Fh+var_50]
0x1800042cd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800042d2  test    al, al
0x1800042d4  jz      loc_180004747
0x1800042da  mov     ecx, 28h ; '('; size
0x1800042df  call    MIDL_user_allocate
0x1800042e4  mov     rsi, rax
0x1800042e7  test    rax, rax
0x1800042ea  jz      loc_180004536
0x1800042f0  lea     rdx, [rbp+4Fh+var_50]
0x1800042f4  mov     rcx, rax
0x1800042f7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1800042fc  mov     qword ptr [rcx+20h], 0
0x180004304  mov     [rbp+4Fh+var_90], rsi
0x180004308  test    rsi, rsi
0x18000430b  jz      loc_180004426
0x180004311  cmp     r13d, edi
0x180004314  jnz     loc_180004542
0x18000431a  xor     r12d, r12d
0x18000431d  movaps  xmm0, xmmword ptr [rbx]
0x180004320  movdqa  [rbp+4Fh+var_70], xmm0
0x180004325  lea     rcx, [rbp+4Fh+var_70]
0x180004329  call    FindLogFileFromName
0x18000432e  mov     rdi, rax
0x180004331  test    rax, rax
0x180004334  jz      loc_18000453D
0x18000433a  mov     [rbp+4Fh+var_80], 5
0x180004342  lea     rax, [rdi+78h]
0x180004346  mov     qword ptr [rbp+4Fh+var_70], rax
0x18000434a  mov     rcx, rax; SRWLock
0x18000434d  call    cs:__imp_AcquireSRWLockExclusive
0x180004353  nop
0x180004354  lock inc dword ptr [rdi+80h]
0x18000435b  mov     [rsi+20h], rdi
0x18000435f  mov     ecx, 2
0x180004364  cmp     r13d, ecx
0x180004367  jz      loc_18000459D
0x18000436d  mov     eax, cs:?gInitStatus@@3TInitStatus@@A; InitStatus gInitStatus
0x180004373  shr     eax, 10h
0x180004376  cmp     ax, cx
0x180004379  jb      short loc_180004391
0x18000437b  mov     rcx, rdi
0x18000437e  call    AddChannelToSingleLog
0x180004383  mov     ebx, eax
0x180004385  test    eax, eax
0x180004387  js      loc_18000447A
0x18000438d  or      r12d, 1
0x180004391  movaps  xmm0, xmmword ptr [r14]
0x180004395  movdqa  [rbp+4Fh+var_60], xmm0
0x18000439a  lea     rcx, [rbp+4Fh+var_60]
0x18000439e  call    ?GetModuleType@@YA?AW4ELF_LOGFILE_TYPE@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; GetModuleType(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800043a3  cmp     eax, 2
0x1800043a6  jnz     short loc_1800043BA
0x1800043a8  mov     rcx, cs:?ElfDefaultLogModule@@3PEAULOGMODULE@@EA; LOGMODULE * ElfDefaultLogModule
0x1800043af  mov     [rbp+4Fh+var_80], rcx
0x1800043b3  mov     cs:?ElfDefaultLogModule@@3PEAULOGMODULE@@EA, rsi; LOGMODULE * ElfDefaultLogModule
0x1800043ba  mov     r9b, 1; bool
0x1800043bd  mov     r8, [rbp+4Fh+arg_10]; HKEY
0x1800043c1  mov     edx, eax; unsigned int
0x1800043c3  mov     rcx, rdi; struct LOGFILE *
0x1800043c6  call    ?ElfpUpdateCustomSD@@YAJPEAULOGFILE@@KPEAUHKEY__@@_N@Z; ElfpUpdateCustomSD(LOGFILE *,ulong,HKEY__ *,bool)
0x1800043cb  mov     ebx, eax
0x1800043cd  test    eax, eax
0x1800043cf  jns     loc_1800045EA
0x1800043d5  lea     r14, WPP_GLOBAL_Control
0x1800043dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043e3  cmp     rcx, r14
0x1800043e6  jz      short loc_180004417
0x1800043e8  test    dword ptr [rcx+1Ch], 1000h
0x1800043ef  jz      short loc_180004417
0x1800043f1  cmp     byte ptr [rcx+19h], 2
0x1800043f5  jb      short loc_180004417
0x1800043f7  mov     edx, 12h
0x1800043fc  mov     [rsp+20h], eax
0x180004400  mov     rax, [rbp+4Fh+arg_0]
0x180004404  mov     r9, [rax]
0x180004407  lea     r8, WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids
0x18000440e  mov     rcx, [rcx+10h]
0x180004412  call    WPP_SF_Sd
0x180004417  test    r12b, 1
0x18000441b  jnz     loc_1800044C3
0x180004421  jmp     loc_1800044BC
0x180004426  lea     r14, WPP_GLOBAL_Control
0x18000442d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004434  cmp     rcx, r14
0x180004437  jz      short loc_18000445E
0x180004439  test    dword ptr [rcx+1Ch], 1000h
0x180004440  jz      short loc_18000445E
0x180004442  cmp     [rcx+19h], dil
0x180004446  jb      short loc_18000445E
0x180004448  mov     edx, 0Dh
0x18000444d  lea     r8, WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids
0x180004454  mov     rcx, [rcx+10h]
0x180004458  call    WPP_SF_
0x18000445d  nop
0x18000445e  lea     rax, [rbp+4Fh+var_40]
0x180004462  mov     rcx, [rbp+4Fh+var_50]; void *
0x180004466  cmp     rcx, rax
0x180004469  jz      short loc_180004470
0x18000446b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004470  mov     ebx, 0C0000017h
0x180004475  jmp     loc_180004519
0x18000447a  lea     r14, WPP_GLOBAL_Control
0x180004481  mov     rcx, cs:WPP_GLOBAL_Control
0x180004488  cmp     rcx, r14
0x18000448b  jz      short loc_1800044BC
0x18000448d  test    dword ptr [rcx+1Ch], 1000h
0x180004494  jz      short loc_1800044BC
0x180004496  cmp     byte ptr [rcx+19h], 2
0x18000449a  jb      short loc_1800044BC
0x18000449c  mov     edx, 11h
0x1800044a1  mov     [rsp+20h], eax
0x1800044a5  mov     rax, [rbp+4Fh+arg_0]
0x1800044a9  mov     r9, [rax]
0x1800044ac  lea     r8, WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids
0x1800044b3  mov     rcx, [rcx+10h]
0x1800044b7  call    WPP_SF_Sd
0x1800044bc  lock dec dword ptr [rdi+80h]
0x1800044c3  mov     r14, [rbp+4Fh+var_90]
0x1800044c7  test    r12b, 1
0x1800044cb  jz      short loc_1800044D8
0x1800044cd  xor     r8d, r8d; int
0x1800044d0  mov     rcx, rdi; struct LOGFILE *
0x1800044d3  call    ?CloseLogFile@@YAJPEAULOGFILE@@KH@Z; CloseLogFile(LOGFILE *,ulong,int)
0x1800044d8  mov     rax, [rbp+4Fh+var_80]
0x1800044dc  cmp     rax, 5
0x1800044e0  jz      short loc_1800044E9
0x1800044e2  mov     cs:?ElfDefaultLogModule@@3PEAULOGMODULE@@EA, rax; LOGMODULE * ElfDefaultLogModule
0x1800044e9  lea     rcx, [rdi+78h]; SRWLock
0x1800044ed  call    cs:__imp_ReleaseSRWLockExclusive
0x1800044f3  nop
0x1800044f4  test    r14, r14
0x1800044f7  jnz     loc_180004783
0x1800044fd  lea     rax, [rbp+4Fh+var_40]
0x180004501  mov     rcx, [rbp+4Fh+var_50]; void *
0x180004505  cmp     rcx, rax
0x180004508  jz      short loc_180004510
0x18000450a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000450f  nop
0x180004510  test    r15, r15
0x180004513  jnz     loc_18000479D
0x180004519  mov     eax, ebx
0x18000451b  mov     rbx, [rsp+0C0h+arg_8]
0x180004523  add     rsp, 90h
0x18000452a  pop     r15
0x18000452c  pop     r14
0x18000452e  pop     r13
0x180004530  pop     r12
0x180004532  pop     rdi
0x180004533  pop     rsi
0x180004534  pop     rbp
0x180004535  retn
0x180004536  xor     esi, esi
0x180004538  jmp     loc_180004304
0x18000453d  mov     edi, 2
0x180004542  movaps  xmm0, xmmword ptr [r14]
0x180004546  movdqa  [rbp+4Fh+var_70], xmm0
0x18000454b  lea     rdx, [rbp+4Fh+var_70]
0x18000454f  lea     rcx, [rbp+4Fh+var_50]
0x180004553  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180004558  test    al, al
0x18000455a  jz      loc_18000473D
0x180004560  mov     ecx, 88h; size
0x180004565  call    MIDL_user_allocate
0x18000456a  test    rax, rax
0x18000456d  jz      loc_1800046CF
0x180004573  lea     rdx, [rbp+4Fh+var_50]
0x180004577  mov     rcx, rax
0x18000457a  call    ??0LOGFILE@@QEAA@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; LOGFILE::LOGFILE(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000457f  mov     r15, rax
0x180004582  mov     [rbp+4Fh+var_88], rax
0x180004586  test    rax, rax
0x180004589  jz      loc_1800046D7
0x18000458f  mov     r12d, 4
0x180004595  mov     rdi, rax
0x180004598  jmp     loc_18000433A
0x18000459d  xor     ecx, ecx; BindingHandle
0x18000459f  call    cs:__imp_RpcImpersonateClient
0x1800045a5  mov     ecx, eax; Status
0x1800045a7  call    cs:__imp_I_RpcMapWin32Status
0x1800045ad  mov     ebx, eax
0x1800045af  lea     r14, WPP_GLOBAL_Control
0x1800045b6  test    eax, eax
0x1800045b8  js      loc_180004663
0x1800045be  mov     rax, [rbp+4Fh+arg_0]
0x1800045c2  movaps  xmm0, xmmword ptr [rax]
0x1800045c5  movdqa  [rbp+4Fh+var_60], xmm0
0x1800045ca  lea     rdx, [rbp+4Fh+var_60]
0x1800045ce  mov     rcx, rdi
0x1800045d1  call    ?OpenLogFile@@YAJPEAULOGFILE@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; OpenLogFile(LOGFILE *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800045d6  mov     ebx, eax
0x1800045d8  call    cs:__imp_RpcRevertToSelf
0x1800045de  test    ebx, ebx
0x1800045e0  js      loc_18000469A
0x1800045e6  or      r12d, 1
0x1800045ea  test    r15, r15
0x1800045ed  jz      short loc_18000460A
0x1800045ef  mov     rax, r15
0x1800045f2  xor     r15d, r15d
0x1800045f5  mov     [rbp+4Fh+arg_0], rax
0x1800045f9  lea     rcx, [rbp+4Fh+arg_0]
0x1800045fd  call    ?LinkLogFile@@YA_NV?$unique_ptr@ULOGFILE@@U?$default_delete@ULOGFILE@@@utl@@@utl@@@Z; LinkLogFile(utl::unique_ptr<LOGFILE,utl::default_delete<LOGFILE>>)
0x180004602  test    al, al
0x180004604  jz      loc_180004764
0x18000460a  xor     r14d, r14d
0x18000460d  mov     [rbp+4Fh+arg_0], rsi
0x180004611  lea     rcx, [rbp+4Fh+arg_0]
0x180004615  call    LinkLogModule
0x18000461a  test    al, al
0x18000461c  jz      loc_180004768
0x180004622  cmp     r13d, 2
0x180004626  jz      short loc_18000463E
0x180004628  cmp     [rbp+4Fh+arg_20], r14b
0x18000462c  jnz     short loc_18000463E
0x18000462e  xor     r8d, r8d; bool
0x180004631  mov     rdx, rdi; struct LOGFILE *
0x180004634  mov     rcx, [rbp+4Fh+arg_10]; HKEY
0x180004638  call    ?SetUpModules@@YAJPEAUHKEY__@@PEAULOGFILE@@_N@Z; SetUpModules(HKEY__ *,LOGFILE *,bool)
0x18000463d  nop
0x18000463e  lea     rcx, [rdi+78h]; SRWLock
0x180004642  call    cs:__imp_ReleaseSRWLockExclusive
0x180004648  nop
0x180004649  lea     rax, [rbp+4Fh+var_40]
0x18000464d  mov     rcx, [rbp+4Fh+var_50]; void *
0x180004651  cmp     rcx, rax
0x180004654  jz      short loc_18000465C
0x180004656  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000465b  nop
0x18000465c  xor     eax, eax
0x18000465e  jmp     loc_18000451B
0x180004663  mov     rcx, cs:WPP_GLOBAL_Control
0x18000466a  cmp     rcx, r14
0x18000466d  jz      loc_1800044BC
0x180004673  test    dword ptr [rcx+1Ch], 1000h
0x18000467a  jz      short loc_1800046A1
0x18000467c  cmp     byte ptr [rcx+19h], 2
0x180004680  jb      short loc_1800046A1
0x180004682  mov     edx, 0Fh
0x180004687  mov     r9d, eax
0x18000468a  lea     r8, WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids
0x180004691  mov     rcx, [rcx+10h]
0x180004695  call    WPP_SF_d
0x18000469a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046a1  cmp     rcx, r14
0x1800046a4  jz      loc_1800044BC
0x1800046aa  test    dword ptr [rcx+1Ch], 1000h
0x1800046b1  jz      loc_1800044BC
0x1800046b7  cmp     byte ptr [rcx+19h], 2
0x1800046bb  jb      loc_1800044BC
0x1800046c1  mov     edx, 10h
0x1800046c6  mov     [rsp+20h], ebx
0x1800046ca  jmp     loc_1800044A5
0x1800046cf  mov     [rbp+4Fh+var_88], 0
0x1800046d7  lea     r14, WPP_GLOBAL_Control
0x1800046de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046e5  cmp     rcx, r14
0x1800046e8  jz      short loc_18000470F
0x1800046ea  test    dword ptr [rcx+1Ch], 1000h
0x1800046f1  jz      short loc_18000470F
0x1800046f3  cmp     [rcx+19h], dil
0x1800046f7  jb      short loc_18000470F
0x1800046f9  mov     edx, 0Eh
0x1800046fe  lea     r8, WPP_d1296d8604b13c4c1d9eb2f0da500a46_Traceguids
0x180004705  mov     rcx, [rcx+10h]
0x180004709  call    WPP_SF_
0x18000470e  nop
0x18000470f  mov     rcx, rsi; void *
0x180004712  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180004717  mov     edx, 28h ; '('
0x18000471c  mov     rcx, rsi
0x18000471f  call    ?_FreeRefCount@?$_RefCountVtable@V?$_RefCountStored@VPublisherManifestResource@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@UEAAXXZ; utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(void)
  ... truncated ...
```
