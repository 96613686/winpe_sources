# CWorkspace::UnregisterAllFileAssociations(void)

- ea: `0x1800396d4`
- end: `0x180039a50`
- name: `?UnregisterAllFileAssociations@CWorkspace@@QEAAJXZ`
- size: `892`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002e6fc`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x1800396d4`
- `0x180052af8`
- `0x180056a98`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039a30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039a30`
- `SHELL32!SHChangeNotify` at `0x1800399f2`
- `SHELL32!SHChangeNotify` at `0x1800399f2`
- `ktmw32!CreateTransaction` at `0x1800397bc`
- `ktmw32!CreateTransaction` at `0x1800397bc`
- `ktmw32!CommitTransaction` at `0x18003996e`
- `ktmw32!CommitTransaction` at `0x18003996e`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CWorkspace::UnregisterAllFileAssociations(CWorkspace *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  char *v3; // rsi
  unsigned int v4; // eax
  HANDLE Transaction; // rdi
  signed int LastError; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  signed int v9; // eax
  char *v10; // r14
  int v11; // ebx
  unsigned int v12; // eax
  int v13; // ebx
  unsigned int v14; // eax
  signed int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  signed int v18; // eax
  unsigned int v20; // [rsp+40h] [rbp-38h]
  CWorkspaceFtaAppRegistration *v21; // [rsp+88h] [rbp+10h] BYREF
  CWorkspaceFileAssociation *v22; // [rsp+90h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      276,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v3 = (char *)this + 744;
  if ( *((_DWORD *)this + 191) )
  {
    Transaction = CreateTransaction(0, 0, 1u, 0, 0, 0x2710u, (LPWSTR)L"Unregistering File Associations");
    if ( Transaction == (HANDLE)-1LL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v8, v7);
      }
      v9 = GetLastError();
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
      return (unsigned int)v9;
    }
    else
    {
      v21 = 0;
      v10 = (char *)this + 832;
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 104) + 64LL))((char *)this + 832);
      while ( (*(unsigned int (__fastcall **)(char *, CWorkspaceFtaAppRegistration **))(*(_QWORD *)v10 + 72LL))(
                v10,
                &v21) )
      {
        v11 = CWorkspaceFtaAppRegistration::Uninstall(v21, Transaction);
        if ( v11 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v12, v11);
        }
      }
      v22 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 64LL))(v3);
      while ( (*(unsigned int (__fastcall **)(char *, CWorkspaceFileAssociation **))(*(_QWORD *)v3 + 72LL))(v3, &v22) )
      {
        v13 = CWorkspaceFileAssociation::Uninstall(v22, Transaction);
        if ( v13 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 280, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v14, v13);
        }
      }
      if ( CommitTransaction(Transaction) )
      {
        SHChangeNotify(0x8000000, 0, 0, 0);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 24LL))(v3);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 24LL))(v10);
        v20 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = GetLastError();
          v16 = v15;
          if ( v15 > 0 )
            v16 = (unsigned __int16)v15 | 0x80070000;
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v17, v16);
        }
        v18 = GetLastError();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        v20 = v18;
      }
      CloseHandle(Transaction);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v4);
    }
    return 1;
  }
  return v20;
}

```

## disassembly

```asm
0x1800396d4  mov     rax, rsp
0x1800396d7  push    rdi
0x1800396d8  push    r12
0x1800396da  push    r14
0x1800396dc  sub     rsp, 60h
0x1800396e0  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800396e8  mov     [rax+8], rbx
0x1800396ec  mov     [rax+20h], rsi
0x1800396f0  mov     rbx, rcx
0x1800396f3  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFFh
0x1800396fb  lea     r12, WPP_GLOBAL_Control
0x180039702  mov     rax, cs:WPP_GLOBAL_Control
0x180039709  cmp     rax, r12
0x18003970c  jz      short loc_18003973F
0x18003970e  test    byte ptr [rax+1Ch], 1
0x180039712  jz      short loc_18003973F
0x180039714  cmp     byte ptr [rax+19h], 4
0x180039718  jb      short loc_18003973F
0x18003971a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003971f  mov     edx, 114h
0x180039724  mov     r9d, eax
0x180039727  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18003972e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039735  mov     rcx, [rcx+10h]
0x180039739  call    WPP_SF_D
0x18003973e  nop
0x18003973f  lea     rsi, [rbx+2E8h]
0x180039746  cmp     dword ptr [rsi+14h], 0
0x18003974a  jnz     short loc_180039795
0x18003974c  mov     rax, cs:WPP_GLOBAL_Control
0x180039753  cmp     rax, r12
0x180039756  jz      short loc_180039788
0x180039758  test    byte ptr [rax+1Ch], 1
0x18003975c  jz      short loc_180039788
0x18003975e  cmp     byte ptr [rax+19h], 4
0x180039762  jb      short loc_180039788
0x180039764  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180039769  mov     edx, 115h
0x18003976e  mov     r9d, eax
0x180039771  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180039778  mov     rcx, cs:WPP_GLOBAL_Control
0x18003977f  mov     rcx, [rcx+10h]
0x180039783  call    WPP_SF_D
0x180039788  mov     [rsp+78h+var_38], 1
0x180039790  jmp     loc_180039A36
0x180039795  lea     rax, aUnregisteringF; "Unregistering File Associations"
0x18003979c  mov     [rsp+78h+Description], rax; Description
0x1800397a1  mov     [rsp+78h+Timeout], 2710h; Timeout
0x1800397a9  mov     [rsp+78h+IsolationFlags], 0; IsolationFlags
0x1800397b1  xor     r9d, r9d; IsolationLevel
0x1800397b4  xor     edx, edx; UOW
0x1800397b6  xor     ecx, ecx; lpTransactionAttributes
0x1800397b8  lea     r8d, [r9+1]; CreateOptions
0x1800397bc  call    cs:__imp_CreateTransaction
0x1800397c2  mov     rdi, rax
0x1800397c5  mov     [rsp+78h+var_30], rax
0x1800397ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800397ce  jnz     short loc_180039840
0x1800397d0  mov     rax, cs:WPP_GLOBAL_Control
0x1800397d7  cmp     rax, r12
0x1800397da  jz      short loc_180039825
0x1800397dc  test    byte ptr [rax+1Ch], 8
0x1800397e0  jz      short loc_180039825
0x1800397e2  cmp     byte ptr [rax+19h], 2
0x1800397e6  jb      short loc_180039825
0x1800397e8  call    cs:__imp_GetLastError
0x1800397ee  mov     ebx, eax
0x1800397f0  test    eax, eax
0x1800397f2  jle     short loc_1800397FD
0x1800397f4  movzx   ebx, ax
0x1800397f7  or      ebx, 80070000h
0x1800397fd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180039802  mov     edx, 116h
0x180039807  mov     [rsp+78h+IsolationFlags], ebx
0x18003980b  mov     r9d, eax
0x18003980e  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180039815  mov     rcx, cs:WPP_GLOBAL_Control
0x18003981c  mov     rcx, [rcx+10h]
0x180039820  call    WPP_SF_Dd
0x180039825  call    cs:__imp_GetLastError
0x18003982b  test    eax, eax
0x18003982d  jle     short loc_180039837
0x18003982f  movzx   eax, ax
0x180039832  or      eax, 80070000h
0x180039837  mov     [rsp+78h+var_38], eax
0x18003983b  jmp     loc_180039A36
0x180039840  mov     [rsp+78h+arg_8], 0
0x18003984c  lea     r14, [rbx+340h]
0x180039853  mov     rax, [r14]
0x180039856  mov     rcx, r14
0x180039859  mov     rax, [rax+40h]
0x18003985d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039862  mov     rax, [r14]
0x180039865  lea     rdx, [rsp+78h+arg_8]
0x18003986d  mov     rcx, r14
0x180039870  mov     rax, [rax+48h]
0x180039874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039879  test    eax, eax
0x18003987b  jz      short loc_1800398D9
0x18003987d  mov     rdx, rdi; void *
0x180039880  mov     rcx, [rsp+78h+arg_8]; this
0x180039888  call    ?Uninstall@CWorkspaceFtaAppRegistration@@QEAAJPEAX@Z; CWorkspaceFtaAppRegistration::Uninstall(void *)
0x18003988d  mov     ebx, eax
0x18003988f  mov     [rsp+78h+var_38], eax
0x180039893  test    eax, eax
0x180039895  jns     short loc_1800398D7
0x180039897  mov     rcx, cs:WPP_GLOBAL_Control
0x18003989e  cmp     rcx, r12
0x1800398a1  jz      short loc_1800398D7
0x1800398a3  test    byte ptr [rcx+1Ch], 1
0x1800398a7  jz      short loc_1800398D7
0x1800398a9  cmp     byte ptr [rcx+19h], 2
0x1800398ad  jb      short loc_1800398D7
0x1800398af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800398b4  mov     edx, 117h
0x1800398b9  mov     [rsp+78h+IsolationFlags], ebx
0x1800398bd  mov     r9d, eax
0x1800398c0  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800398c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398ce  mov     rcx, [rcx+10h]
0x1800398d2  call    WPP_SF_Dd
0x1800398d7  jmp     short loc_180039862
0x1800398d9  mov     [rsp+78h+arg_10], 0
0x1800398e5  mov     rax, [rsi]
0x1800398e8  mov     rcx, rsi
0x1800398eb  mov     rax, [rax+40h]
0x1800398ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398f4  mov     rax, [rsi]
0x1800398f7  lea     rdx, [rsp+78h+arg_10]
0x1800398ff  mov     rcx, rsi
0x180039902  mov     rax, [rax+48h]
0x180039906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003990b  test    eax, eax
0x18003990d  jz      short loc_18003996B
0x18003990f  mov     rdx, rdi; void *
0x180039912  mov     rcx, [rsp+78h+arg_10]; this
0x18003991a  call    ?Uninstall@CWorkspaceFileAssociation@@QEAAJPEAX@Z; CWorkspaceFileAssociation::Uninstall(void *)
0x18003991f  mov     ebx, eax
0x180039921  mov     [rsp+78h+var_38], eax
0x180039925  test    eax, eax
0x180039927  jns     short loc_180039969
0x180039929  mov     rcx, cs:WPP_GLOBAL_Control
0x180039930  cmp     rcx, r12
0x180039933  jz      short loc_180039969
0x180039935  test    byte ptr [rcx+1Ch], 1
0x180039939  jz      short loc_180039969
0x18003993b  cmp     byte ptr [rcx+19h], 2
0x18003993f  jb      short loc_180039969
0x180039941  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180039946  mov     edx, 118h
0x18003994b  mov     [rsp+78h+IsolationFlags], ebx
0x18003994f  mov     r9d, eax
0x180039952  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180039959  mov     rcx, cs:WPP_GLOBAL_Control
0x180039960  mov     rcx, [rcx+10h]
0x180039964  call    WPP_SF_Dd
0x180039969  jmp     short loc_1800398F4
0x18003996b  mov     rcx, rdi; TransactionHandle
0x18003996e  call    cs:__imp_CommitTransaction
0x180039974  test    eax, eax
0x180039976  jnz     short loc_1800399E5
0x180039978  mov     rax, cs:WPP_GLOBAL_Control
0x18003997f  cmp     rax, r12
0x180039982  jz      short loc_1800399CD
0x180039984  test    byte ptr [rax+1Ch], 8
0x180039988  jz      short loc_1800399CD
0x18003998a  cmp     byte ptr [rax+19h], 2
0x18003998e  jb      short loc_1800399CD
0x180039990  call    cs:__imp_GetLastError
0x180039996  mov     ebx, eax
0x180039998  test    eax, eax
0x18003999a  jle     short loc_1800399A5
0x18003999c  movzx   ebx, ax
0x18003999f  or      ebx, 80070000h
0x1800399a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800399aa  mov     edx, 119h
0x1800399af  mov     [rsp+78h+IsolationFlags], ebx
0x1800399b3  mov     r9d, eax
0x1800399b6  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800399bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800399c4  mov     rcx, [rcx+10h]
0x1800399c8  call    WPP_SF_Dd
0x1800399cd  call    cs:__imp_GetLastError
0x1800399d3  test    eax, eax
0x1800399d5  jle     short loc_1800399DF
0x1800399d7  movzx   eax, ax
0x1800399da  or      eax, 80070000h
0x1800399df  mov     [rsp+78h+var_38], eax
0x1800399e3  jmp     short loc_180039A27
0x1800399e5  xor     r9d, r9d; dwItem2
0x1800399e8  xor     r8d, r8d; dwItem1
0x1800399eb  xor     edx, edx; uFlags
0x1800399ed  mov     ecx, 8000000h; wEventId
0x1800399f2  call    cs:__imp_SHChangeNotify
0x1800399f8  mov     rax, [rsi]
0x1800399fb  mov     rcx, rsi
0x1800399fe  mov     rax, [rax+18h]
0x180039a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a07  mov     rax, [r14]
0x180039a0a  mov     rcx, r14
0x180039a0d  mov     rax, [rax+18h]
0x180039a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a16  mov     [rsp+78h+var_38], 0
0x180039a1e  jmp     short loc_180039A27
0x180039a20  jmp     short $+2
0x180039a22  mov     rdi, [rsp+78h+var_30]
0x180039a27  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180039a2b  jz      short loc_180039A36
0x180039a2d  mov     rcx, rdi; hObject
0x180039a30  call    cs:__imp_CloseHandle
0x180039a36  mov     eax, [rsp+78h+var_38]
0x180039a3a  lea     r11, [rsp+78h+var_18]
0x180039a3f  mov     rbx, [r11+20h]
0x180039a43  mov     rsi, [r11+38h]
0x180039a47  mov     rsp, r11
0x180039a4a  pop     r14
0x180039a4c  pop     r12
0x180039a4e  pop     rdi
0x180039a4f  retn
```
