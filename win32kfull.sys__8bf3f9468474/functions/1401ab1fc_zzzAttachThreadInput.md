# zzzAttachThreadInput

- ea: `0x1401ab1fc`
- end: `0x1401ab6c4`
- name: `zzzAttachThreadInput`
- size: `1224`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401494f4`
- `0x140162e4c`
- `0x1401aa130`
- `0x1401aa850`
- `0x1401aaff0`
- `0x1401ab104`
- `0x14021f6f4`
- `0x14027d12c`
- `0x140296274`

## callees

- `0x1400bcaa0`
- `0x1401ab1fc`
- `0x1402abd44`
- `0x1402abf68`
- `0x1402ac6dc`
- `0x1402ac734`
- `0x1402ac7e4`
- `0x1402b1230`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401ab680`
- `ntoskrnl!KeSetEvent` at `0x1401ab6a6`
- `ntoskrnl!KeSetEvent` at `0x1401ab680`
- `ntoskrnl!KeSetEvent` at `0x1401ab6a6`
- `win32kbase!?IsSameAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z` at `0x1401ab3ca`
- `win32kbase!?IsSameAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z` at `0x1401ab3ca`
- `win32kbase!?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401ab381`
- `win32kbase!?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401ab39f`
- `win32kbase!?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401ab381`
- `win32kbase!?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401ab39f`
- `win32kbase!IsDesktopApp` at `0x1401ab490`
- `win32kbase!IsDesktopApp` at `0x1401ab490`
- `win32kbase!EtwTraceUIPIInputError` at `0x1401ab310`
- `win32kbase!EtwTraceUIPIInputError` at `0x1401ab310`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401ab2bf`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401ab33e`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401ab2bf`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401ab33e`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401ab4a7`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401ab4be`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401ab4a7`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401ab4be`
- `win32kbase!Win32AllocPoolZInit` at `0x1401ab576`
- `win32kbase!Win32AllocPoolZInit` at `0x1401ab576`
- `win32kbase!Win32FreePool` at `0x1401ab649`
- `win32kbase!Win32FreePool` at `0x1401ab649`
- `WIN32K!W32GetUserSessionState` at `0x1401ab44b`
- `WIN32K!W32GetUserSessionState` at `0x1401ab52c`
- `WIN32K!W32GetUserSessionState` at `0x1401ab5b1`
- `WIN32K!W32GetUserSessionState` at `0x1401ab5c7`
- `WIN32K!W32GetUserSessionState` at `0x1401ab44b`
- `WIN32K!W32GetUserSessionState` at `0x1401ab52c`
- `WIN32K!W32GetUserSessionState` at `0x1401ab5b1`
- `WIN32K!W32GetUserSessionState` at `0x1401ab5c7`

## pseudocode

```c
__int64 __fastcall zzzAttachThreadInput(struct tagTHREADINFO *a1, struct tagTHREADINFO *a2, unsigned int a3)
{
  char v6; // r14
  int v7; // r15d
  struct tagTHREADINFO *v8; // rbp
  BOOL v9; // r12d
  __int64 v10; // rdx
  const struct tagUIPI_INFO *v11; // r8
  __int64 v12; // r9
  BOOL v13; // esi
  __int64 v14; // rax
  const struct tagUIPI_INFO *v15; // r8
  __int64 v16; // r8
  struct tagTHREADINFO *v17; // rdx
  int v18; // eax
  const struct tagUIPI_INFO *v20; // rdx
  const struct tagUIPI_INFO *v21; // rdx
  bool v22; // r15
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 UserSessionState; // rax
  int v28; // r8d
  int v29; // edx
  __int64 v30; // rax
  __int64 *i; // rcx
  struct tagTHREADINFO *v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  _QWORD *v38; // rsi
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rcx
  __int64 v45; // rdx
  struct tagTHREADINFO *v46; // r8
  _QWORD *v47; // rdx
  __int64 v48; // [rsp+60h] [rbp-48h] BYREF
  int v49; // [rsp+68h] [rbp-40h]

  v6 = 1;
  v7 = a3 & 1;
  v8 = PtiCurrent();
  v9 = (a3 & 0x4000) != 0 && !v7;
  if ( (unsigned int)Feature_UIPIEliminateATIOverride__private_IsEnabledDeviceUsageNoInline() )
    v13 = a1 != v8 || (*((_DWORD *)a1 + 340) & 0x100000) == 0 || (*((_DWORD *)a2 + 340) & 0x40000) == 0;
  else
    v13 = ((a3 >> 15) & 1) == 0;
  if ( a1 != a2 )
  {
    if ( v13 )
    {
      v14 = *((_QWORD *)a2 + 57);
      if ( v14 != *((_QWORD *)a1 + 57) || *((_QWORD *)v8 + 57) != v14 )
      {
        if ( !UIPrivilegeIsolation::CheckAccess(
                (UIPrivilegeIsolation *)(*((_QWORD *)v8 + 57) + 864LL),
                (const struct tagUIPI_INFO *)(*((_QWORD *)a2 + 58) + 544LL),
                v11)
          && *(int *)(*((_QWORD *)v8 + 57) + 12LL) >= 0 )
        {
          v16 = *((_QWORD *)a2 + 58);
          v17 = a2;
LABEL_19:
          v18 = *(_DWORD *)(v16 + 552);
          v48 = *(_QWORD *)(v16 + 544);
          v49 = v18;
          EtwTraceUIPIInputError(v8, v17, v16, &v48, 2);
          return 3221225506LL;
        }
        if ( !UIPrivilegeIsolation::CheckAccess(
                (UIPrivilegeIsolation *)(*((_QWORD *)v8 + 57) + 864LL),
                (const struct tagUIPI_INFO *)(*((_QWORD *)a1 + 58) + 544LL),
                v15)
          && *(int *)(*((_QWORD *)v8 + 57) + 12LL) >= 0 )
        {
          goto LABEL_23;
        }
        if ( (unsigned int)Feature_UIPIBlockCrossACAttach__private_IsEnabledDeviceUsageNoInline()
          && UIPrivilegeIsolation::IsInAppContainer((UIPrivilegeIsolation *)(*((_QWORD *)a1 + 57) + 864LL), v20)
          && UIPrivilegeIsolation::IsInAppContainer((UIPrivilegeIsolation *)(*((_QWORD *)a2 + 57) + 864LL), v21)
          && !(unsigned __int8)UIPrivilegeIsolation::IsSameAppContainer(
                                 *((_QWORD *)a1 + 57) + 864LL,
                                 *((_QWORD *)a2 + 57) + 864LL,
                                 0) )
        {
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
          {
            v6 = 0;
          }
          v22 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v6 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            tagPROCESSINFO::GetPID(*((tagPROCESSINFO **)a2 + 57));
            tagPROCESSINFO::GetPID(*((tagPROCESSINFO **)a1 + 57));
            UserSessionState = W32GetUserSessionState(v24, v23, v25, v26);
            LOBYTE(v28) = v22;
            LOBYTE(v29) = v6;
            WPP_RECORDER_AND_TRACE_SF_DLDL(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v29,
              v28,
              *(_QWORD *)(UserSessionState + 69152));
          }
          return 3221225506LL;
        }
        if ( (unsigned int)IsDesktopApp(*((_QWORD *)v8 + 57))
          && ((unsigned int)IsImmersiveAppRestricted(*((_QWORD *)a2 + 57))
           || (unsigned int)IsImmersiveAppRestricted(*((_QWORD *)a1 + 57)))
          && !(unsigned int)ExemptedFromImmersiveRestrictions(v8)
          && (*(_DWORD *)(*((_QWORD *)v8 + 57) + 808LL) & 0x100LL) == 0 )
        {
LABEL_23:
          v16 = *((_QWORD *)a1 + 58);
          v17 = a1;
          goto LABEL_19;
        }
      }
    }
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)a2 + 130, 0, 0) & 0x40) != 0
      || (_InterlockedCompareExchange((volatile signed __int32 *)a1 + 130, 0, 0) & 0x40) != 0
      || *((_QWORD *)a2 + 61) != *((_QWORD *)a1 + 61) )
    {
      return 3221225506LL;
    }
    v30 = W32GetUserSessionState(0, v10, v11, v12);
    if ( v7 )
    {
      for ( i = *(__int64 **)(v30 + 16856); ; i = (__int64 *)*i )
      {
        if ( !i )
        {
          v33 = Win32AllocPoolZInit(32, 1767994197);
          v38 = (_QWORD *)v33;
          if ( !v33 )
            return 3221225495LL;
          *(_QWORD *)(v33 + 8) = a1;
          *(_QWORD *)(v33 + 16) = a2;
          *(_DWORD *)(v33 + 24) = 1;
          v40 = *(_QWORD *)(W32GetUserSessionState(v35, v34, v36, v37) + 16856);
          *v38 = v40;
          *(_QWORD *)(W32GetUserSessionState(v40, v41, v42, v43) + 16856) = v38;
          goto LABEL_67;
        }
        v32 = (struct tagTHREADINFO *)i[2];
        if ( v32 == a2 && (struct tagTHREADINFO *)i[1] == a1 )
          break;
        if ( v32 == a1 && (struct tagTHREADINFO *)i[1] == a2 )
          break;
      }
      v39 = *((_DWORD *)i + 6);
      if ( v39 == -1 )
        return 3221225485LL;
      *((_DWORD *)i + 6) = v39 + 1;
      return 0;
    }
    v44 = v30 + 16856;
    v45 = *(_QWORD *)(v30 + 16856);
    if ( v45 )
    {
      while ( 1 )
      {
        v46 = *(struct tagTHREADINFO **)(v45 + 16);
        if ( v46 == a2 && *(struct tagTHREADINFO **)(v45 + 8) == a1 )
          break;
        if ( v46 == a1 && *(struct tagTHREADINFO **)(v45 + 8) == a2 )
          break;
        v44 = v45;
        v45 = *(_QWORD *)v45;
        if ( !v45 )
          return 3221225485LL;
      }
      --*(_DWORD *)(*(_QWORD *)v44 + 24LL);
      v47 = *(_QWORD **)v44;
      if ( !*(_DWORD *)(*(_QWORD *)v44 + 24LL) || v9 )
      {
        *(_QWORD *)v44 = *v47;
        Win32FreePool(v47);
LABEL_67:
        *((_QWORD *)a2 + 170) |= 0x200uLL;
        *((_QWORD *)a1 + 170) |= 0x200uLL;
        if ( _bittest64((const signed __int64 *)a1 + 170, 0xAu) )
          KeSetEvent(*((PRKEVENT *)a1 + 95), 1, 0);
        if ( (*((_DWORD *)a2 + 340) & 0x400LL) != 0 )
          KeSetEvent(*((PRKEVENT *)a2 + 95), 1, 0);
        zzzReattachThreads(0, a1, a2);
      }
      return 0;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1401ab1fc  push    rbx
0x1401ab1fe  push    rbp
0x1401ab1ff  push    rsi
0x1401ab200  push    rdi
0x1401ab201  push    r12
0x1401ab203  push    r14
0x1401ab205  push    r15
0x1401ab207  sub     rsp, 70h
0x1401ab20b  mov     esi, r8d
0x1401ab20e  mov     rdi, rdx
0x1401ab211  mov     rbx, rcx
0x1401ab214  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401ab219  mov     r15d, esi
0x1401ab21c  mov     r14d, 1
0x1401ab222  and     r15d, r14d
0x1401ab225  mov     rbp, rax
0x1401ab228  bt      esi, 0Eh
0x1401ab22c  jnb     short loc_1401AB238
0x1401ab22e  test    r15d, r15d
0x1401ab231  jnz     short loc_1401AB238
0x1401ab233  mov     r12d, r14d
0x1401ab236  jmp     short loc_1401AB23B
0x1401ab238  xor     r12d, r12d
0x1401ab23b  call    Feature_UIPIEliminateATIOverride__private_IsEnabledDeviceUsageNoInline
0x1401ab240  test    eax, eax
0x1401ab242  jnz     short loc_1401AB24E
0x1401ab244  shr     esi, 0Fh
0x1401ab247  not     esi
0x1401ab249  and     esi, r14d
0x1401ab24c  jmp     short loc_1401AB274
0x1401ab24e  cmp     rbx, rbp
0x1401ab251  jnz     short loc_1401AB271
0x1401ab253  mov     eax, [rbx+550h]
0x1401ab259  bt      rax, 14h
0x1401ab25e  jnb     short loc_1401AB271
0x1401ab260  mov     eax, [rdi+550h]
0x1401ab266  bt      rax, 12h
0x1401ab26b  jnb     short loc_1401AB271
0x1401ab26d  xor     esi, esi
0x1401ab26f  jmp     short loc_1401AB274
0x1401ab271  mov     esi, r14d
0x1401ab274  cmp     rbx, rdi
0x1401ab277  jz      loc_1401AB613
0x1401ab27d  test    esi, esi
0x1401ab27f  jz      loc_1401AB4F2
0x1401ab285  mov     rax, [rdi+1C8h]
0x1401ab28c  cmp     rax, [rbx+1C8h]
0x1401ab293  jnz     short loc_1401AB2A2
0x1401ab295  cmp     [rbp+1C8h], rax
0x1401ab29c  jz      loc_1401AB4F2
0x1401ab2a2  mov     rdx, [rdi+1D0h]
0x1401ab2a9  mov     esi, 360h
0x1401ab2ae  mov     rcx, [rbp+1C8h]
0x1401ab2b5  add     rdx, 220h
0x1401ab2bc  add     rcx, rsi
0x1401ab2bf  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1401ab2c6  nop     dword ptr [rax+rax+00h]
0x1401ab2cb  test    al, al
0x1401ab2cd  jnz     short loc_1401AB326
0x1401ab2cf  mov     rax, [rbp+1C8h]
0x1401ab2d6  cmp     dword ptr [rax+0Ch], 0
0x1401ab2da  jl      short loc_1401AB326
0x1401ab2dc  mov     r8, [rdi+1D0h]
0x1401ab2e3  mov     rdx, rdi
0x1401ab2e6  movsd   xmm0, qword ptr [r8+220h]
0x1401ab2ef  lea     r9, [rsp+0A8h+var_48]
0x1401ab2f4  mov     eax, [r8+228h]
0x1401ab2fb  mov     rcx, rbp
0x1401ab2fe  movsd   [rsp+0A8h+var_48], xmm0
0x1401ab304  mov     [rsp+0A8h+var_88], 2
0x1401ab30c  mov     [rsp+0A8h+var_40], eax
0x1401ab310  call    cs:__imp_EtwTraceUIPIInputError
0x1401ab317  nop     dword ptr [rax+rax+00h]
0x1401ab31c  mov     eax, 0C0000022h
0x1401ab321  jmp     loc_1401AB618
0x1401ab326  mov     rdx, [rbx+1D0h]
0x1401ab32d  mov     rcx, [rbp+1C8h]
0x1401ab334  add     rdx, 220h
0x1401ab33b  add     rcx, rsi
0x1401ab33e  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1401ab345  nop     dword ptr [rax+rax+00h]
0x1401ab34a  test    al, al
0x1401ab34c  jnz     short loc_1401AB36A
0x1401ab34e  mov     rax, [rbp+1C8h]
0x1401ab355  cmp     dword ptr [rax+0Ch], 0
0x1401ab359  jl      short loc_1401AB36A
0x1401ab35b  mov     r8, [rbx+1D0h]
0x1401ab362  mov     rdx, rbx
0x1401ab365  jmp     loc_1401AB2E6
0x1401ab36a  call    Feature_UIPIBlockCrossACAttach__private_IsEnabledDeviceUsageNoInline
0x1401ab36f  test    eax, eax
0x1401ab371  jz      loc_1401AB489
0x1401ab377  mov     rcx, [rbx+1C8h]
0x1401ab37e  add     rcx, rsi
0x1401ab381  call    cs:__imp_?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z; UIPrivilegeIsolation::IsInAppContainer(tagUIPI_INFO const &)
0x1401ab388  nop     dword ptr [rax+rax+00h]
0x1401ab38d  test    al, al
0x1401ab38f  jz      loc_1401AB489
0x1401ab395  mov     rcx, [rdi+1C8h]
0x1401ab39c  add     rcx, rsi
0x1401ab39f  call    cs:__imp_?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z; UIPrivilegeIsolation::IsInAppContainer(tagUIPI_INFO const &)
0x1401ab3a6  nop     dword ptr [rax+rax+00h]
0x1401ab3ab  test    al, al
0x1401ab3ad  jz      loc_1401AB489
0x1401ab3b3  mov     rdx, [rdi+1C8h]
0x1401ab3ba  xor     r8d, r8d
0x1401ab3bd  mov     rcx, [rbx+1C8h]
0x1401ab3c4  add     rdx, rsi
0x1401ab3c7  add     rcx, rsi
0x1401ab3ca  call    cs:__imp_?IsSameAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::IsSameAppContainer(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x1401ab3d1  nop     dword ptr [rax+rax+00h]
0x1401ab3d6  test    al, al
0x1401ab3d8  jnz     loc_1401AB489
0x1401ab3de  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ab3e5  lea     rax, WPP_GLOBAL_Control
0x1401ab3ec  cmp     rcx, rax
0x1401ab3ef  jz      short loc_1401AB400
0x1401ab3f1  test    dword ptr [rcx+2Ch], 8000h
0x1401ab3f8  jz      short loc_1401AB400
0x1401ab3fa  cmp     byte ptr [rcx+29h], 3
0x1401ab3fe  jnb     short loc_1401AB403
0x1401ab400  xor     r14b, r14b
0x1401ab403  lea     rax, WPP_RECORDER_INITIALIZED
0x1401ab40a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401ab411  setnz   r15b
0x1401ab415  test    r14b, r14b
0x1401ab418  jnz     short loc_1401AB423
0x1401ab41a  test    r15b, r15b
0x1401ab41d  jz      loc_1401AB31C
0x1401ab423  mov     rcx, [rdi+1C8h]; this
0x1401ab42a  mov     ebp, [rcx+364h]
0x1401ab430  call    ?GetPID@tagPROCESSINFO@@QEBAKXZ; tagPROCESSINFO::GetPID(void)
0x1401ab435  mov     rcx, [rbx+1C8h]; this
0x1401ab43c  mov     esi, eax
0x1401ab43e  mov     edi, [rcx+364h]
0x1401ab444  call    ?GetPID@tagPROCESSINFO@@QEBAKXZ; tagPROCESSINFO::GetPID(void)
0x1401ab449  mov     ebx, eax
0x1401ab44b  call    cs:__imp_W32GetUserSessionState
0x1401ab452  nop     dword ptr [rax+rax+00h]
0x1401ab457  mov     rcx, cs:WPP_GLOBAL_Control
0x1401ab45e  mov     r8b, r15b
0x1401ab461  mov     [rsp+0A8h+var_50], ebp
0x1401ab465  mov     dl, r14b
0x1401ab468  mov     [rsp+0A8h+var_58], esi
0x1401ab46c  mov     r9, [rax+10E20h]
0x1401ab473  mov     rcx, [rcx+18h]
0x1401ab477  mov     [rsp+0A8h+var_60], edi
0x1401ab47b  mov     [rsp+0A8h+var_68], ebx
0x1401ab47f  call    WPP_RECORDER_AND_TRACE_SF_DLDL
0x1401ab484  jmp     loc_1401AB31C
0x1401ab489  mov     rcx, [rbp+1C8h]
0x1401ab490  call    cs:__imp_IsDesktopApp
0x1401ab497  nop     dword ptr [rax+rax+00h]
0x1401ab49c  test    eax, eax
0x1401ab49e  jz      short loc_1401AB4F2
0x1401ab4a0  mov     rcx, [rdi+1C8h]
0x1401ab4a7  call    cs:__imp_IsImmersiveAppRestricted
0x1401ab4ae  nop     dword ptr [rax+rax+00h]
0x1401ab4b3  test    eax, eax
0x1401ab4b5  jnz     short loc_1401AB4CE
0x1401ab4b7  mov     rcx, [rbx+1C8h]
0x1401ab4be  call    cs:__imp_IsImmersiveAppRestricted
0x1401ab4c5  nop     dword ptr [rax+rax+00h]
0x1401ab4ca  test    eax, eax
0x1401ab4cc  jz      short loc_1401AB4F2
0x1401ab4ce  mov     rcx, rbp
0x1401ab4d1  call    ExemptedFromImmersiveRestrictions
0x1401ab4d6  test    eax, eax
0x1401ab4d8  jnz     short loc_1401AB4F2
0x1401ab4da  mov     rax, [rbp+1C8h]
0x1401ab4e1  mov     ecx, [rax+328h]
0x1401ab4e7  bt      rcx, 8
0x1401ab4ec  jnb     loc_1401AB35B
0x1401ab4f2  xor     ecx, ecx
0x1401ab4f4  xor     eax, eax
0x1401ab4f6  lock cmpxchg [rdi+208h], ecx
0x1401ab4fe  test    al, 40h
0x1401ab500  jnz     loc_1401AB31C
0x1401ab506  xor     eax, eax
0x1401ab508  lock cmpxchg [rbx+208h], ecx
0x1401ab510  test    al, 40h
0x1401ab512  jnz     loc_1401AB31C
0x1401ab518  mov     rax, [rbx+1E8h]
0x1401ab51f  cmp     [rdi+1E8h], rax
0x1401ab526  jnz     loc_1401AB31C
0x1401ab52c  call    cs:__imp_W32GetUserSessionState
0x1401ab533  nop     dword ptr [rax+rax+00h]
0x1401ab538  test    r15d, r15d
0x1401ab53b  jz      loc_1401AB5DC
0x1401ab541  mov     rcx, [rax+41D8h]
0x1401ab548  jmp     short loc_1401AB567
0x1401ab54a  mov     rdx, [rcx+10h]
0x1401ab54e  cmp     rdx, rdi
0x1401ab551  jnz     short loc_1401AB559
0x1401ab553  cmp     [rcx+8], rbx
0x1401ab557  jz      short loc_1401AB594
0x1401ab559  cmp     rdx, rbx
0x1401ab55c  jnz     short loc_1401AB564
0x1401ab55e  cmp     [rcx+8], rdi
0x1401ab562  jz      short loc_1401AB594
0x1401ab564  mov     rcx, [rcx]
0x1401ab567  test    rcx, rcx
0x1401ab56a  jnz     short loc_1401AB54A
0x1401ab56c  mov     edx, 69617355h
0x1401ab571  mov     ecx, 20h ; ' '
0x1401ab576  call    cs:__imp_Win32AllocPoolZInit
0x1401ab57d  nop     dword ptr [rax+rax+00h]
0x1401ab582  mov     rsi, rax
0x1401ab585  test    rax, rax
0x1401ab588  jnz     short loc_1401AB5A5
0x1401ab58a  mov     eax, 0C0000017h
0x1401ab58f  jmp     loc_1401AB618
0x1401ab594  mov     eax, [rcx+18h]
0x1401ab597  cmp     eax, 0FFFFFFFFh
0x1401ab59a  jz      short loc_1401AB613
0x1401ab59c  inc     eax
0x1401ab59e  mov     [rcx+18h], eax
0x1401ab5a1  xor     eax, eax
0x1401ab5a3  jmp     short loc_1401AB618
0x1401ab5a5  mov     [rax+8], rbx
0x1401ab5a9  mov     [rax+10h], rdi
0x1401ab5ad  mov     [rax+18h], r14d
0x1401ab5b1  call    cs:__imp_W32GetUserSessionState
0x1401ab5b8  nop     dword ptr [rax+rax+00h]
0x1401ab5bd  mov     rcx, [rax+41D8h]
0x1401ab5c4  mov     [rsi], rcx
0x1401ab5c7  call    cs:__imp_W32GetUserSessionState
0x1401ab5ce  nop     dword ptr [rax+rax+00h]
0x1401ab5d3  mov     [rax+41D8h], rsi
0x1401ab5da  jmp     short loc_1401AB655
0x1401ab5dc  lea     rcx, [rax+41D8h]
0x1401ab5e3  mov     rdx, [rcx]
0x1401ab5e6  test    rdx, rdx
0x1401ab5e9  jz      short loc_1401AB613
0x1401ab5eb  mov     r8, [rdx+10h]
0x1401ab5ef  cmp     r8, rdi
0x1401ab5f2  jnz     short loc_1401AB5FA
0x1401ab5f4  cmp     [rdx+8], rbx
0x1401ab5f8  jz      short loc_1401AB628
0x1401ab5fa  cmp     r8, rbx
0x1401ab5fd  jnz     short loc_1401AB605
0x1401ab5ff  cmp     [rdx+8], rdi
0x1401ab603  jz      short loc_1401AB628
0x1401ab605  mov     rax, [rdx]
0x1401ab608  mov     rcx, rdx
0x1401ab60b  mov     rdx, rax
0x1401ab60e  test    rax, rax
0x1401ab611  jnz     short loc_1401AB5EB
0x1401ab613  mov     eax, 0C000000Dh
0x1401ab618  add     rsp, 70h
0x1401ab61c  pop     r15
0x1401ab61e  pop     r14
0x1401ab620  pop     r12
0x1401ab622  pop     rdi
0x1401ab623  pop     rsi
0x1401ab624  pop     rbp
0x1401ab625  pop     rbx
0x1401ab626  retn
0x1401ab628  mov     rax, [rcx]
0x1401ab62b  dec     dword ptr [rax+18h]
0x1401ab62e  mov     rdx, [rcx]
0x1401ab631  cmp     dword ptr [rdx+18h], 0
0x1401ab635  jz      short loc_1401AB640
0x1401ab637  test    r12d, r12d
0x1401ab63a  jz      loc_1401AB5A1
0x1401ab640  mov     rax, [rdx]
0x1401ab643  mov     [rcx], rax
0x1401ab646  mov     rcx, rdx
0x1401ab649  call    cs:__imp_Win32FreePool
0x1401ab650  nop     dword ptr [rax+rax+00h]
0x1401ab655  mov     eax, 200h
0x1401ab65a  or      [rdi+550h], rax
0x1401ab661  or      [rbx+550h], rax
0x1401ab668  bt      qword ptr [rbx+550h], 0Ah
0x1401ab671  jnb     short loc_1401AB68C
0x1401ab673  mov     rcx, [rbx+2F8h]; Event
0x1401ab67a  xor     r8d, r8d; Wait
0x1401ab67d  mov     edx, r14d; Increment
0x1401ab680  call    cs:__imp_KeSetEvent
0x1401ab687  nop     dword ptr [rax+rax+00h]
0x1401ab68c  mov     eax, [rdi+550h]
0x1401ab692  bt      rax, 0Ah
0x1401ab697  jnb     short loc_1401AB6B2
0x1401ab699  mov     rcx, [rdi+2F8h]; Event
0x1401ab6a0  xor     r8d, r8d; Wait
0x1401ab6a3  mov     edx, r14d; Increment
0x1401ab6a6  call    cs:__imp_KeSetEvent
0x1401ab6ad  nop     dword ptr [rax+rax+00h]
0x1401ab6b2  mov     r8, rdi; struct tagTHREADINFO *
0x1401ab6b5  mov     rdx, rbx; struct tagTHREADINFO *
0x1401ab6b8  xor     ecx, ecx; unsigned int
0x1401ab6ba  call    ?zzzReattachThreads@@YAXKPEAUtagTHREADINFO@@0@Z; zzzReattachThreads(ulong,tagTHREADINFO *,tagTHREADINFO *)
0x1401ab6bf  jmp     loc_1401AB5A1
```
