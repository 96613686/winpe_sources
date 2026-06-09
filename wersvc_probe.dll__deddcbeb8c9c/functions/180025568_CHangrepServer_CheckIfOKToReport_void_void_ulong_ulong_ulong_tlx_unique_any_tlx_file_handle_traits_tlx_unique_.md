# CHangrepServer::_CheckIfOKToReport(void *,void *,ulong,ulong,ulong,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180025568`
- end: `0x180025a03`
- name: `?_CheckIfOKToReport@CHangrepServer@@AEAAJPEAX0KKKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@1@Z`
- size: `1179`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800248f4`

## callees

- `0x180006a80`
- `0x180007cf8`
- `0x18000fbfc`
- `0x180011ef8`
- `0x18001e3c4`
- `0x180025568`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800255d4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800255d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18002588d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800259e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18002588d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800259e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800255f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800255f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025667`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002592c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002592c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800256f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800256f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800258e6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800258e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800255ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800255cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800258a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800259ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800259fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800255ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800255cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800258a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800259ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800259fb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025783`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025902`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025783`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025902`

## pseudocode

```c
__int64 __fastcall CHangrepServer::_CheckIfOKToReport(
        __int64 a1,
        void *a2,
        void *a3,
        DWORD a4,
        DWORD dwThreadId,
        DWORD dwDesiredAccess,
        void **a7,
        void **a8)
{
  void **v8; // rsi
  char *v12; // rcx
  void **v13; // rdi
  void *v14; // rcx
  DWORD ProcessId; // r14d
  void **v16; // rax
  signed int LastError; // eax
  unsigned int v18; // ebx
  void **v19; // rax
  signed int v20; // eax
  HANDLE *v21; // rcx
  __int64 v22; // rdx
  signed int v23; // eax
  DWORD v24; // ebx
  HANDLE v25; // rax
  void *v26; // rcx
  signed int v27; // eax
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  HANDLE v30; // rax
  void *v31; // rcx
  signed int v32; // eax
  HANDLE v33; // rax
  void *v34; // rcx
  signed int v35; // eax
  HANDLE v37; // rax
  void *v38; // rcx
  HANDLE hToken[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v40; // [rsp+70h] [rbp+8h] BYREF

  v40 = a1;
  v8 = a7;
  hToken[0] = 0;
  v12 = (char *)*a7;
  *a7 = 0;
  if ( v12 != (char *)-1LL && v12 + 1 != (char *)1 )
    CloseHandle(v12);
  v13 = a8;
  v14 = *a8;
  *a8 = 0;
  if ( (unsigned __int64)v14 + 1 > 1 )
    CloseHandle(v14);
  ProcessId = GetProcessId(a2);
  v16 = (void **)tlx::replace<tlx::file_handle_traits>(hToken);
  if ( OpenThreadToken(a3, 0xAu, 1, v16) )
    goto LABEL_22;
  LastError = GetLastError();
  v18 = LastError;
  if ( LastError > 0 )
    v18 = (unsigned __int16)LastError | 0x80070000;
  if ( v18 == -2147023888 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids);
    v19 = (void **)tlx::replace<tlx::file_handle_traits>(hToken);
    if ( !OpenProcessToken(a2, 0xAu, v19) )
    {
      v20 = GetLastError();
      v18 = v20;
      if ( v20 > 0 )
        v18 = (unsigned __int16)v20 | 0x80070000;
      v21 = (HANDLE *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 13;
LABEL_18:
        WPP_SF_d(v21[2], v22, &WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v18);
LABEL_60:
        v21 = (HANDLE *)WPP_GLOBAL_Control;
        goto LABEL_61;
      }
      goto LABEL_61;
    }
LABEL_22:
    if ( !ImpersonateLoggedOnUser(hToken[0]) )
    {
      v23 = GetLastError();
      v18 = v23;
      if ( v23 > 0 )
        v18 = (unsigned __int16)v23 | 0x80070000;
      v21 = (HANDLE *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v22 = 15;
        goto LABEL_18;
      }
      goto LABEL_61;
    }
    v24 = dwDesiredAccess;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids,
        ProcessId,
        dwDesiredAccess,
        a4);
    v25 = OpenProcess(v24, 0, a4);
    v26 = *v8;
    *v8 = v25;
    if ( (unsigned __int64)v26 + 1 > 1 )
      CloseHandle(v26);
    if ( (unsigned __int64)*v8 + 1 > 1 )
    {
      if ( !dwThreadId )
        goto LABEL_58;
      v30 = OpenThread(0x800u, 0, dwThreadId);
      v31 = *v13;
      *v13 = v30;
      if ( (unsigned __int64)v31 + 1 > 1 )
        CloseHandle(v31);
      if ( (unsigned __int64)*v13 + 1 > 1 )
      {
LABEL_58:
        v18 = 0;
        goto LABEL_59;
      }
      v32 = GetLastError();
      v18 = v32;
      if ( v32 > 0 )
        v18 = (unsigned __int16)v32 | 0x80070000;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_59;
      v29 = 20;
    }
    else
    {
      v27 = GetLastError();
      v18 = v27;
      if ( v27 > 0 )
        v18 = (unsigned __int16)v27 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v18);
      LODWORD(v40) = 0;
      if ( (int)UtilGetTokenIntegrityRid(hToken[0], (unsigned int *)&v40) >= 0 && (unsigned int)v40 >= 0x4000 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids);
        v18 = 1;
        goto LABEL_59;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_59:
        RevertToSelf();
        goto LABEL_60;
      }
      v29 = 19;
    }
    WPP_SF_d(v28[2], v29, &WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v18);
    goto LABEL_59;
  }
  v21 = (HANDLE *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v22 = 14;
    goto LABEL_18;
  }
LABEL_61:
  if ( v18 != 1 )
  {
LABEL_70:
    if ( (v18 & 0x80000000) != 0 )
    {
      if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 )
        WPP_SF_d(v21[2], 23, &WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v18);
      v18 = -2147024891;
    }
    goto LABEL_75;
  }
  v33 = OpenProcess(0x1000u, 0, a4);
  v34 = *v8;
  *v8 = v33;
  if ( (unsigned __int64)v34 + 1 > 1 )
    CloseHandle(v34);
  if ( (unsigned __int64)*v8 + 1 <= 1 )
  {
    v35 = GetLastError();
    v18 = v35;
    if ( v35 > 0 )
      v18 = (unsigned __int16)v35 | 0x80070000;
    v21 = (HANDLE *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v18);
      v21 = (HANDLE *)WPP_GLOBAL_Control;
    }
    goto LABEL_70;
  }
  if ( dwThreadId )
  {
    v37 = OpenThread(0x800u, 0, dwThreadId);
    v38 = *v13;
    *v13 = v37;
    if ( (unsigned __int64)v38 + 1 > 1 )
      CloseHandle(v38);
  }
LABEL_75:
  if ( (unsigned __int64)hToken[0] + 1 > 1 )
    CloseHandle(hToken[0]);
  return v18;
}

```

## disassembly

```asm
0x180025568  mov     rax, rsp
0x18002556b  mov     [rax+10h], rbx
0x18002556f  mov     [rax+18h], rbp
0x180025573  mov     [rax+8], rcx
0x180025577  push    rsi
0x180025578  push    rdi
0x180025579  push    r12
0x18002557b  push    r13
0x18002557d  push    r14
0x18002557f  sub     rsp, 40h
0x180025583  mov     rsi, [rsp+68h+arg_30]
0x18002558b  xor     r14d, r14d
0x18002558e  mov     [rax-38h], r14
0x180025592  mov     r12d, r9d
0x180025595  mov     rbx, r8
0x180025598  mov     rbp, rdx
0x18002559b  mov     rcx, [rsi]; hObject
0x18002559e  lea     r13d, [r14+1]
0x1800255a2  mov     [rsi], r14
0x1800255a5  lea     rax, [rcx+1]
0x1800255a9  cmp     rax, r13
0x1800255ac  jbe     short loc_1800255B4
0x1800255ae  call    cs:__imp_CloseHandle
0x1800255b4  mov     rdi, [rsp+68h+arg_38]
0x1800255bc  mov     rcx, [rdi]; hObject
0x1800255bf  mov     [rdi], r14
0x1800255c2  lea     rax, [rcx+1]
0x1800255c6  cmp     rax, r13
0x1800255c9  jbe     short loc_1800255D1
0x1800255cb  call    cs:__imp_CloseHandle
0x1800255d1  mov     rcx, rbp; Process
0x1800255d4  call    cs:__imp_GetProcessId
0x1800255da  lea     rcx, [rsp+68h+hToken]
0x1800255df  mov     r14d, eax
0x1800255e2  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800255e7  mov     r9, rax; TokenHandle
0x1800255ea  mov     r8d, r13d; OpenAsSelf
0x1800255ed  mov     edx, 0Ah; DesiredAccess
0x1800255f2  mov     rcx, rbx; ThreadHandle
0x1800255f5  call    cs:__imp_OpenThreadToken
0x1800255fb  test    eax, eax
0x1800255fd  jnz     loc_1800256EC
0x180025603  call    cs:__imp_GetLastError
0x180025609  mov     ebx, eax
0x18002560b  test    eax, eax
0x18002560d  jle     short loc_180025618
0x18002560f  movzx   ebx, ax
0x180025612  or      ebx, 80070000h
0x180025618  cmp     ebx, 800703F0h
0x18002561e  jnz     loc_1800256C4
0x180025624  mov     rcx, cs:WPP_GLOBAL_Control
0x18002562b  lea     rax, WPP_GLOBAL_Control
0x180025632  cmp     rcx, rax
0x180025635  jz      short loc_180025652
0x180025637  test    byte ptr [rcx+1Ch], 4
0x18002563b  jz      short loc_180025652
0x18002563d  mov     rcx, [rcx+10h]
0x180025641  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180025648  mov     edx, 0Ch
0x18002564d  call    WPP_SF_
0x180025652  lea     rcx, [rsp+68h+hToken]
0x180025657  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002565c  mov     r8, rax; TokenHandle
0x18002565f  mov     edx, 0Ah; DesiredAccess
0x180025664  mov     rcx, rbp; ProcessHandle
0x180025667  call    cs:__imp_OpenProcessToken
0x18002566d  test    eax, eax
0x18002566f  jnz     short loc_1800256EC
0x180025671  call    cs:__imp_GetLastError
0x180025677  mov     ebx, eax
0x180025679  test    eax, eax
0x18002567b  jle     short loc_180025686
0x18002567d  movzx   ebx, ax
0x180025680  or      ebx, 80070000h
0x180025686  mov     rcx, cs:WPP_GLOBAL_Control
0x18002568d  lea     rbp, WPP_GLOBAL_Control
0x180025694  cmp     rcx, rbp
0x180025697  jz      loc_1800258F3
0x18002569d  test    [rcx+1Ch], r13b
0x1800256a1  jz      loc_1800258F3
0x1800256a7  mov     edx, 0Dh
0x1800256ac  mov     rcx, [rcx+10h]
0x1800256b0  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x1800256b7  mov     r9d, ebx
0x1800256ba  call    WPP_SF_d
0x1800256bf  jmp     loc_1800258EC
0x1800256c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256cb  lea     rbp, WPP_GLOBAL_Control
0x1800256d2  cmp     rcx, rbp
0x1800256d5  jz      loc_1800258F3
0x1800256db  test    [rcx+1Ch], r13b
0x1800256df  jz      loc_1800258F3
0x1800256e5  mov     edx, 0Eh
0x1800256ea  jmp     short loc_1800256AC
0x1800256ec  mov     rcx, [rsp+68h+hToken]; hToken
0x1800256f1  call    cs:__imp_ImpersonateLoggedOnUser
0x1800256f7  test    eax, eax
0x1800256f9  jnz     short loc_18002573B
0x1800256fb  call    cs:__imp_GetLastError
0x180025701  mov     ebx, eax
0x180025703  test    eax, eax
0x180025705  jle     short loc_180025710
0x180025707  movzx   ebx, ax
0x18002570a  or      ebx, 80070000h
0x180025710  mov     rcx, cs:WPP_GLOBAL_Control
0x180025717  lea     rbp, WPP_GLOBAL_Control
0x18002571e  cmp     rcx, rbp
0x180025721  jz      loc_1800258F3
0x180025727  test    [rcx+1Ch], r13b
0x18002572b  jz      loc_1800258F3
0x180025731  mov     edx, 0Fh
0x180025736  jmp     loc_1800256AC
0x18002573b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025742  lea     rbp, WPP_GLOBAL_Control
0x180025749  mov     ebx, [rsp+68h+dwDesiredAccess]
0x180025750  cmp     rcx, rbp
0x180025753  jz      short loc_18002577C
0x180025755  test    byte ptr [rcx+1Ch], 4
0x180025759  jz      short loc_18002577C
0x18002575b  mov     rcx, [rcx+10h]
0x18002575f  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180025766  mov     edx, 10h
0x18002576b  mov     [rsp+68h+var_40], r12d
0x180025770  mov     r9d, r14d
0x180025773  mov     [rsp+68h+var_48], ebx
0x180025777  call    WPP_SF_DDD
0x18002577c  mov     r8d, r12d; dwProcessId
0x18002577f  xor     edx, edx; bInheritHandle
0x180025781  mov     ecx, ebx; dwDesiredAccess
0x180025783  call    cs:__imp_OpenProcess
0x180025789  mov     rcx, [rsi]; hObject
0x18002578c  mov     [rsi], rax
0x18002578f  lea     rax, [rcx+1]
0x180025793  cmp     rax, r13
0x180025796  jbe     short loc_18002579E
0x180025798  call    cs:__imp_CloseHandle
0x18002579e  mov     rax, [rsi]
0x1800257a1  add     rax, r13
0x1800257a4  cmp     rax, r13
0x1800257a7  ja      loc_180025874
0x1800257ad  call    cs:__imp_GetLastError
0x1800257b3  mov     ebx, eax
0x1800257b5  test    eax, eax
0x1800257b7  jle     short loc_1800257C2
0x1800257b9  movzx   ebx, ax
0x1800257bc  or      ebx, 80070000h
0x1800257c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257c9  cmp     rcx, rbp
0x1800257cc  jz      short loc_1800257EC
0x1800257ce  test    byte ptr [rcx+1Ch], 2
0x1800257d2  jz      short loc_1800257EC
0x1800257d4  mov     rcx, [rcx+10h]
0x1800257d8  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x1800257df  mov     edx, 11h
0x1800257e4  mov     r9d, ebx
0x1800257e7  call    WPP_SF_d
0x1800257ec  mov     rcx, [rsp+68h+hToken]; TokenHandle
0x1800257f1  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x1800257f6  mov     dword ptr [rsp+68h+arg_0], 0
0x1800257fe  call    ?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z; UtilGetTokenIntegrityRid(void *,ulong *)
0x180025803  test    eax, eax
0x180025805  js      short loc_180025840
0x180025807  cmp     dword ptr [rsp+68h+arg_0], 4000h
0x18002580f  jb      short loc_180025840
0x180025811  mov     rcx, cs:WPP_GLOBAL_Control
0x180025818  cmp     rcx, rbp
0x18002581b  jz      short loc_180025838
0x18002581d  test    byte ptr [rcx+1Ch], 4
0x180025821  jz      short loc_180025838
0x180025823  mov     rcx, [rcx+10h]
0x180025827  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x18002582e  mov     edx, 12h
0x180025833  call    WPP_SF_
0x180025838  mov     ebx, r13d
0x18002583b  jmp     loc_1800258E6
0x180025840  mov     rcx, cs:WPP_GLOBAL_Control
0x180025847  cmp     rcx, rbp
0x18002584a  jz      loc_1800258E6
0x180025850  test    [rcx+1Ch], r13b
0x180025854  jz      loc_1800258E6
0x18002585a  mov     edx, 13h
0x18002585f  mov     rcx, [rcx+10h]
0x180025863  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x18002586a  mov     r9d, ebx
0x18002586d  call    WPP_SF_d
0x180025872  jmp     short loc_1800258E6
0x180025874  cmp     [rsp+68h+dwThreadId], 0
0x18002587c  jz      short loc_1800258E4
0x18002587e  mov     r8d, [rsp+68h+dwThreadId]; dwThreadId
0x180025886  xor     edx, edx; bInheritHandle
0x180025888  mov     ecx, 800h; dwDesiredAccess
0x18002588d  call    cs:__imp_OpenThread
0x180025893  mov     rcx, [rdi]; hObject
0x180025896  mov     [rdi], rax
0x180025899  lea     rax, [rcx+1]
0x18002589d  cmp     rax, r13
0x1800258a0  jbe     short loc_1800258A8
0x1800258a2  call    cs:__imp_CloseHandle
0x1800258a8  mov     rax, [rdi]
0x1800258ab  add     rax, r13
0x1800258ae  cmp     rax, r13
0x1800258b1  ja      short loc_1800258E4
0x1800258b3  call    cs:__imp_GetLastError
0x1800258b9  mov     ebx, eax
0x1800258bb  test    eax, eax
0x1800258bd  jle     short loc_1800258C8
0x1800258bf  movzx   ebx, ax
0x1800258c2  or      ebx, 80070000h
0x1800258c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258cf  cmp     rcx, rbp
0x1800258d2  jz      short loc_1800258E6
0x1800258d4  test    [rcx+1Ch], r13b
0x1800258d8  jz      short loc_1800258E6
0x1800258da  mov     edx, 14h
0x1800258df  jmp     loc_18002585F
0x1800258e4  xor     ebx, ebx
0x1800258e6  call    cs:__imp_RevertToSelf
0x1800258ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258f3  cmp     ebx, r13d
0x1800258f6  jnz     short loc_180025972
0x1800258f8  mov     r8d, r12d; dwProcessId
0x1800258fb  xor     edx, edx; bInheritHandle
0x1800258fd  mov     ecx, 1000h; dwDesiredAccess
0x180025902  call    cs:__imp_OpenProcess
0x180025908  mov     rcx, [rsi]; hObject
0x18002590b  mov     [rsi], rax
0x18002590e  lea     rax, [rcx+1]
0x180025912  cmp     rax, r13
0x180025915  jbe     short loc_18002591D
0x180025917  call    cs:__imp_CloseHandle
0x18002591d  mov     rax, [rsi]
0x180025920  add     rax, r13
0x180025923  cmp     rax, r13
0x180025926  ja      loc_1800259CD
0x18002592c  call    cs:__imp_GetLastError
0x180025932  mov     ebx, eax
0x180025934  test    eax, eax
0x180025936  jle     short loc_180025941
0x180025938  movzx   ebx, ax
0x18002593b  or      ebx, 80070000h
0x180025941  mov     rcx, cs:WPP_GLOBAL_Control
0x180025948  cmp     rcx, rbp
0x18002594b  jz      short loc_180025972
0x18002594d  test    [rcx+1Ch], r13b
0x180025951  jz      short loc_180025972
0x180025953  mov     rcx, [rcx+10h]
0x180025957  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x18002595e  mov     edx, 15h
0x180025963  mov     r9d, ebx
0x180025966  call    WPP_SF_d
0x18002596b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025972  test    ebx, ebx
0x180025974  jns     short loc_18002599E
0x180025976  cmp     rcx, rbp
0x180025979  jz      short loc_180025999
0x18002597b  test    byte ptr [rcx+1Ch], 4
0x18002597f  jz      short loc_180025999
0x180025981  mov     rcx, [rcx+10h]
0x180025985  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x18002598c  mov     edx, 17h
0x180025991  mov     r9d, ebx
0x180025994  call    WPP_SF_d
0x180025999  mov     ebx, 80070005h
0x18002599e  mov     rcx, [rsp+68h+hToken]; hObject
0x1800259a3  lea     rax, [rcx+1]
0x1800259a7  cmp     rax, r13
0x1800259aa  jbe     short loc_1800259B2
0x1800259ac  call    cs:__imp_CloseHandle
0x1800259b2  lea     r11, [rsp+68h+var_28]
0x1800259b7  mov     eax, ebx
0x1800259b9  mov     rbx, [r11+38h]
0x1800259bd  mov     rbp, [r11+40h]
0x1800259c1  mov     rsp, r11
0x1800259c4  pop     r14
0x1800259c6  pop     r13
0x1800259c8  pop     r12
0x1800259ca  pop     rdi
0x1800259cb  pop     rsi
0x1800259cc  retn
0x1800259cd  cmp     [rsp+68h+dwThreadId], 0
0x1800259d5  jz      short loc_18002599E
0x1800259d7  mov     r8d, [rsp+68h+dwThreadId]; dwThreadId
0x1800259df  xor     edx, edx; bInheritHandle
0x1800259e1  mov     ecx, 800h; dwDesiredAccess
0x1800259e6  call    cs:__imp_OpenThread
0x1800259ec  mov     rcx, [rdi]; hObject
0x1800259ef  mov     [rdi], rax
0x1800259f2  lea     rax, [rcx+1]
0x1800259f6  cmp     rax, r13
0x1800259f9  jbe     short loc_18002599E
0x1800259fb  call    cs:__imp_CloseHandle
0x180025a01  jmp     short loc_18002599E
```
