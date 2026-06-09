# zzzAttachThreadInput

- ea: `0x1401a95fc`
- end: `0x1401a9ac4`
- name: `zzzAttachThreadInput`
- size: `1224`
- prototype: `__int64 __fastcall(struct tagTHREADINFO *, struct tagTHREADINFO *, unsigned int)`
- caller_count: `9`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400068e4`
- `0x14013f4b4`
- `0x14015393c`
- `0x1401a8530`
- `0x1401a8c50`
- `0x1401a93f0`
- `0x1401a9504`
- `0x14027f2ec`
- `0x140298754`

## callees

- `0x1400e2cb0`
- `0x1401a95fc`
- `0x1402ae184`
- `0x1402ae3a8`
- `0x1402aeac4`
- `0x1402aeb1c`
- `0x1402aebcc`
- `0x1402b2be0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401a9a80`
- `ntoskrnl!KeSetEvent` at `0x1401a9aa6`
- `ntoskrnl!KeSetEvent` at `0x1401a9a80`
- `ntoskrnl!KeSetEvent` at `0x1401a9aa6`
- `win32kbase!?IsSameAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z` at `0x1401a97ca`
- `win32kbase!?IsSameAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z` at `0x1401a97ca`
- `win32kbase!?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401a9781`
- `win32kbase!?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401a979f`
- `win32kbase!?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401a9781`
- `win32kbase!?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z` at `0x1401a979f`
- `win32kbase!IsDesktopApp` at `0x1401a9890`
- `win32kbase!IsDesktopApp` at `0x1401a9890`
- `win32kbase!EtwTraceUIPIInputError` at `0x1401a9710`
- `win32kbase!EtwTraceUIPIInputError` at `0x1401a9710`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401a96bf`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401a973e`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401a96bf`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1401a973e`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401a98a7`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401a98be`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401a98a7`
- `win32kbase!IsImmersiveAppRestricted` at `0x1401a98be`
- `win32kbase!Win32AllocPoolZInit` at `0x1401a9976`
- `win32kbase!Win32AllocPoolZInit` at `0x1401a9976`
- `win32kbase!Win32FreePool` at `0x1401a9a49`
- `win32kbase!Win32FreePool` at `0x1401a9a49`
- `WIN32K!W32GetUserSessionState` at `0x1401a984b`
- `WIN32K!W32GetUserSessionState` at `0x1401a992c`
- `WIN32K!W32GetUserSessionState` at `0x1401a99b1`
- `WIN32K!W32GetUserSessionState` at `0x1401a99c7`
- `WIN32K!W32GetUserSessionState` at `0x1401a984b`
- `WIN32K!W32GetUserSessionState` at `0x1401a992c`
- `WIN32K!W32GetUserSessionState` at `0x1401a99b1`
- `WIN32K!W32GetUserSessionState` at `0x1401a99c7`

## pseudocode

```c
__int64 __fastcall zzzAttachThreadInput(struct tagTHREADINFO *a1, struct tagTHREADINFO *a2, unsigned int a3)
{
  char v6; // r14
  int v7; // r15d
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct tagTHREADINFO *v10; // rbp
  __int64 v11; // r8
  BOOL v12; // r12d
  __int64 v13; // rdx
  const struct tagUIPI_INFO *v14; // r8
  __int64 v15; // r9
  BOOL v16; // esi
  __int64 v17; // rax
  const struct tagUIPI_INFO *v18; // r8
  __int64 v19; // r8
  struct tagTHREADINFO *v20; // rdx
  int v21; // eax
  const struct tagUIPI_INFO *v23; // rdx
  const struct tagUIPI_INFO *v24; // rdx
  bool v25; // r15
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 UserSessionState; // rax
  int v31; // r8d
  int v32; // edx
  __int64 v33; // rax
  __int64 *i; // rcx
  struct tagTHREADINFO *v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  _QWORD *v41; // rsi
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rcx
  __int64 v48; // rdx
  struct tagTHREADINFO *v49; // r8
  _QWORD *v50; // rdx
  __int64 v51; // [rsp+60h] [rbp-48h] BYREF
  int v52; // [rsp+68h] [rbp-40h]

  v6 = 1;
  v7 = a3 & 1;
  v10 = PtiCurrent((__int64)a1, (__int64)a2);
  v12 = (a3 & 0x4000) != 0 && !v7;
  if ( (unsigned int)Feature_UIPIEliminateATIOverride__private_IsEnabledDeviceUsageNoInline(v9, v8, v11) )
    v16 = a1 != v10 || (*((_DWORD *)a1 + 340) & 0x100000) == 0 || (*((_DWORD *)a2 + 340) & 0x40000) == 0;
  else
    v16 = ((a3 >> 15) & 1) == 0;
  if ( a1 != a2 )
  {
    if ( v16 )
    {
      v17 = *((_QWORD *)a2 + 57);
      if ( v17 != *((_QWORD *)a1 + 57) || *((_QWORD *)v10 + 57) != v17 )
      {
        if ( !UIPrivilegeIsolation::CheckAccess(
                (UIPrivilegeIsolation *)(*((_QWORD *)v10 + 57) + 864LL),
                (const struct tagUIPI_INFO *)(*((_QWORD *)a2 + 58) + 544LL),
                v14)
          && *(int *)(*((_QWORD *)v10 + 57) + 12LL) >= 0 )
        {
          v19 = *((_QWORD *)a2 + 58);
          v20 = a2;
LABEL_19:
          v21 = *(_DWORD *)(v19 + 552);
          v51 = *(_QWORD *)(v19 + 544);
          v52 = v21;
          EtwTraceUIPIInputError(v10, v20, v19, &v51, 2);
          return 3221225506LL;
        }
        if ( !UIPrivilegeIsolation::CheckAccess(
                (UIPrivilegeIsolation *)(*((_QWORD *)v10 + 57) + 864LL),
                (const struct tagUIPI_INFO *)(*((_QWORD *)a1 + 58) + 544LL),
                v18)
          && *(int *)(*((_QWORD *)v10 + 57) + 12LL) >= 0 )
        {
          goto LABEL_23;
        }
        if ( (unsigned int)Feature_UIPIBlockCrossACAttach__private_IsEnabledDeviceUsageNoInline()
          && UIPrivilegeIsolation::IsInAppContainer((UIPrivilegeIsolation *)(*((_QWORD *)a1 + 57) + 864LL), v23)
          && UIPrivilegeIsolation::IsInAppContainer((UIPrivilegeIsolation *)(*((_QWORD *)a2 + 57) + 864LL), v24)
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
          v25 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v6 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            tagPROCESSINFO::GetPID(*((tagPROCESSINFO **)a2 + 57));
            tagPROCESSINFO::GetPID(*((tagPROCESSINFO **)a1 + 57));
            UserSessionState = W32GetUserSessionState(v27, v26, v28, v29);
            LOBYTE(v31) = v25;
            LOBYTE(v32) = v6;
            WPP_RECORDER_AND_TRACE_SF_DLDL(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v32,
              v31,
              *(_QWORD *)(UserSessionState + 69152));
          }
          return 3221225506LL;
        }
        if ( (unsigned int)IsDesktopApp(*((_QWORD *)v10 + 57))
          && ((unsigned int)IsImmersiveAppRestricted(*((_QWORD *)a2 + 57))
           || (unsigned int)IsImmersiveAppRestricted(*((_QWORD *)a1 + 57)))
          && !(unsigned int)ExemptedFromImmersiveRestrictions(v10)
          && (*(_DWORD *)(*((_QWORD *)v10 + 57) + 808LL) & 0x100LL) == 0 )
        {
LABEL_23:
          v19 = *((_QWORD *)a1 + 58);
          v20 = a1;
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
    v33 = W32GetUserSessionState(0, v13, v14, v15);
    if ( v7 )
    {
      for ( i = *(__int64 **)(v33 + 16856); ; i = (__int64 *)*i )
      {
        if ( !i )
        {
          v36 = Win32AllocPoolZInit(32, 1767994197);
          v41 = (_QWORD *)v36;
          if ( !v36 )
            return 3221225495LL;
          *(_QWORD *)(v36 + 8) = a1;
          *(_QWORD *)(v36 + 16) = a2;
          *(_DWORD *)(v36 + 24) = 1;
          v43 = *(_QWORD *)(W32GetUserSessionState(v38, v37, v39, v40) + 16856);
          *v41 = v43;
          *(_QWORD *)(W32GetUserSessionState(v43, v44, v45, v46) + 16856) = v41;
          goto LABEL_67;
        }
        v35 = (struct tagTHREADINFO *)i[2];
        if ( v35 == a2 && (struct tagTHREADINFO *)i[1] == a1 )
          break;
        if ( v35 == a1 && (struct tagTHREADINFO *)i[1] == a2 )
          break;
      }
      v42 = *((_DWORD *)i + 6);
      if ( v42 == -1 )
        return 3221225485LL;
      *((_DWORD *)i + 6) = v42 + 1;
      return 0;
    }
    v47 = v33 + 16856;
    v48 = *(_QWORD *)(v33 + 16856);
    if ( v48 )
    {
      while ( 1 )
      {
        v49 = *(struct tagTHREADINFO **)(v48 + 16);
        if ( v49 == a2 && *(struct tagTHREADINFO **)(v48 + 8) == a1 )
          break;
        if ( v49 == a1 && *(struct tagTHREADINFO **)(v48 + 8) == a2 )
          break;
        v47 = v48;
        v48 = *(_QWORD *)v48;
        if ( !v48 )
          return 3221225485LL;
      }
      --*(_DWORD *)(*(_QWORD *)v47 + 24LL);
      v50 = *(_QWORD **)v47;
      if ( !*(_DWORD *)(*(_QWORD *)v47 + 24LL) || v12 )
      {
        *(_QWORD *)v47 = *v50;
        Win32FreePool(v50);
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
0x1401a95fc  push    rbx
0x1401a95fe  push    rbp
0x1401a95ff  push    rsi
0x1401a9600  push    rdi
0x1401a9601  push    r12
0x1401a9603  push    r14
0x1401a9605  push    r15
0x1401a9607  sub     rsp, 70h
0x1401a960b  mov     esi, r8d
0x1401a960e  mov     rdi, rdx
0x1401a9611  mov     rbx, rcx
0x1401a9614  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401a9619  mov     r15d, esi
0x1401a961c  mov     r14d, 1
0x1401a9622  and     r15d, r14d
0x1401a9625  mov     rbp, rax
0x1401a9628  bt      esi, 0Eh
0x1401a962c  jnb     short loc_1401A9638
0x1401a962e  test    r15d, r15d
0x1401a9631  jnz     short loc_1401A9638
0x1401a9633  mov     r12d, r14d
0x1401a9636  jmp     short loc_1401A963B
0x1401a9638  xor     r12d, r12d
0x1401a963b  call    Feature_UIPIEliminateATIOverride__private_IsEnabledDeviceUsageNoInline
0x1401a9640  test    eax, eax
0x1401a9642  jnz     short loc_1401A964E
0x1401a9644  shr     esi, 0Fh
0x1401a9647  not     esi
0x1401a9649  and     esi, r14d
0x1401a964c  jmp     short loc_1401A9674
0x1401a964e  cmp     rbx, rbp
0x1401a9651  jnz     short loc_1401A9671
0x1401a9653  mov     eax, [rbx+550h]
0x1401a9659  bt      rax, 14h
0x1401a965e  jnb     short loc_1401A9671
0x1401a9660  mov     eax, [rdi+550h]
0x1401a9666  bt      rax, 12h
0x1401a966b  jnb     short loc_1401A9671
0x1401a966d  xor     esi, esi
0x1401a966f  jmp     short loc_1401A9674
0x1401a9671  mov     esi, r14d
0x1401a9674  cmp     rbx, rdi
0x1401a9677  jz      loc_1401A9A13
0x1401a967d  test    esi, esi
0x1401a967f  jz      loc_1401A98F2
0x1401a9685  mov     rax, [rdi+1C8h]
0x1401a968c  cmp     rax, [rbx+1C8h]
0x1401a9693  jnz     short loc_1401A96A2
0x1401a9695  cmp     [rbp+1C8h], rax
0x1401a969c  jz      loc_1401A98F2
0x1401a96a2  mov     rdx, [rdi+1D0h]
0x1401a96a9  mov     esi, 360h
0x1401a96ae  mov     rcx, [rbp+1C8h]
0x1401a96b5  add     rdx, 220h
0x1401a96bc  add     rcx, rsi
0x1401a96bf  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1401a96c6  nop     dword ptr [rax+rax+00h]
0x1401a96cb  test    al, al
0x1401a96cd  jnz     short loc_1401A9726
0x1401a96cf  mov     rax, [rbp+1C8h]
0x1401a96d6  cmp     dword ptr [rax+0Ch], 0
0x1401a96da  jl      short loc_1401A9726
0x1401a96dc  mov     r8, [rdi+1D0h]
0x1401a96e3  mov     rdx, rdi
0x1401a96e6  movsd   xmm0, qword ptr [r8+220h]
0x1401a96ef  lea     r9, [rsp+0A8h+var_48]
0x1401a96f4  mov     eax, [r8+228h]
0x1401a96fb  mov     rcx, rbp
0x1401a96fe  movsd   [rsp+0A8h+var_48], xmm0
0x1401a9704  mov     [rsp+0A8h+var_88], 2
0x1401a970c  mov     [rsp+0A8h+var_40], eax
0x1401a9710  call    cs:__imp_EtwTraceUIPIInputError
0x1401a9717  nop     dword ptr [rax+rax+00h]
0x1401a971c  mov     eax, 0C0000022h
0x1401a9721  jmp     loc_1401A9A18
0x1401a9726  mov     rdx, [rbx+1D0h]
0x1401a972d  mov     rcx, [rbp+1C8h]
0x1401a9734  add     rdx, 220h
0x1401a973b  add     rcx, rsi
0x1401a973e  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1401a9745  nop     dword ptr [rax+rax+00h]
0x1401a974a  test    al, al
0x1401a974c  jnz     short loc_1401A976A
0x1401a974e  mov     rax, [rbp+1C8h]
0x1401a9755  cmp     dword ptr [rax+0Ch], 0
0x1401a9759  jl      short loc_1401A976A
0x1401a975b  mov     r8, [rbx+1D0h]
0x1401a9762  mov     rdx, rbx
0x1401a9765  jmp     loc_1401A96E6
0x1401a976a  call    Feature_UIPIBlockCrossACAttach__private_IsEnabledDeviceUsageNoInline
0x1401a976f  test    eax, eax
0x1401a9771  jz      loc_1401A9889
0x1401a9777  mov     rcx, [rbx+1C8h]
0x1401a977e  add     rcx, rsi
0x1401a9781  call    cs:__imp_?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z; UIPrivilegeIsolation::IsInAppContainer(tagUIPI_INFO const &)
0x1401a9788  nop     dword ptr [rax+rax+00h]
0x1401a978d  test    al, al
0x1401a978f  jz      loc_1401A9889
0x1401a9795  mov     rcx, [rdi+1C8h]
0x1401a979c  add     rcx, rsi
0x1401a979f  call    cs:__imp_?IsInAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@@Z; UIPrivilegeIsolation::IsInAppContainer(tagUIPI_INFO const &)
0x1401a97a6  nop     dword ptr [rax+rax+00h]
0x1401a97ab  test    al, al
0x1401a97ad  jz      loc_1401A9889
0x1401a97b3  mov     rdx, [rdi+1C8h]
0x1401a97ba  xor     r8d, r8d
0x1401a97bd  mov     rcx, [rbx+1C8h]
0x1401a97c4  add     rdx, rsi
0x1401a97c7  add     rcx, rsi
0x1401a97ca  call    cs:__imp_?IsSameAppContainer@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::IsSameAppContainer(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x1401a97d1  nop     dword ptr [rax+rax+00h]
0x1401a97d6  test    al, al
0x1401a97d8  jnz     loc_1401A9889
0x1401a97de  mov     rcx, cs:WPP_GLOBAL_Control
0x1401a97e5  lea     rax, WPP_GLOBAL_Control
0x1401a97ec  cmp     rcx, rax
0x1401a97ef  jz      short loc_1401A9800
0x1401a97f1  test    dword ptr [rcx+2Ch], 8000h
0x1401a97f8  jz      short loc_1401A9800
0x1401a97fa  cmp     byte ptr [rcx+29h], 3
0x1401a97fe  jnb     short loc_1401A9803
0x1401a9800  xor     r14b, r14b
0x1401a9803  lea     rax, WPP_RECORDER_INITIALIZED
0x1401a980a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401a9811  setnz   r15b
0x1401a9815  test    r14b, r14b
0x1401a9818  jnz     short loc_1401A9823
0x1401a981a  test    r15b, r15b
0x1401a981d  jz      loc_1401A971C
0x1401a9823  mov     rcx, [rdi+1C8h]; this
0x1401a982a  mov     ebp, [rcx+364h]
0x1401a9830  call    ?GetPID@tagPROCESSINFO@@QEBAKXZ; tagPROCESSINFO::GetPID(void)
0x1401a9835  mov     rcx, [rbx+1C8h]; this
0x1401a983c  mov     esi, eax
0x1401a983e  mov     edi, [rcx+364h]
0x1401a9844  call    ?GetPID@tagPROCESSINFO@@QEBAKXZ; tagPROCESSINFO::GetPID(void)
0x1401a9849  mov     ebx, eax
0x1401a984b  call    cs:__imp_W32GetUserSessionState
0x1401a9852  nop     dword ptr [rax+rax+00h]
0x1401a9857  mov     rcx, cs:WPP_GLOBAL_Control
0x1401a985e  mov     r8b, r15b
0x1401a9861  mov     [rsp+0A8h+var_50], ebp
0x1401a9865  mov     dl, r14b
0x1401a9868  mov     [rsp+0A8h+var_58], esi
0x1401a986c  mov     r9, [rax+10E20h]
0x1401a9873  mov     rcx, [rcx+18h]
0x1401a9877  mov     [rsp+0A8h+var_60], edi
0x1401a987b  mov     [rsp+0A8h+var_68], ebx
0x1401a987f  call    WPP_RECORDER_AND_TRACE_SF_DLDL
0x1401a9884  jmp     loc_1401A971C
0x1401a9889  mov     rcx, [rbp+1C8h]
0x1401a9890  call    cs:__imp_IsDesktopApp
0x1401a9897  nop     dword ptr [rax+rax+00h]
0x1401a989c  test    eax, eax
0x1401a989e  jz      short loc_1401A98F2
0x1401a98a0  mov     rcx, [rdi+1C8h]
0x1401a98a7  call    cs:__imp_IsImmersiveAppRestricted
0x1401a98ae  nop     dword ptr [rax+rax+00h]
0x1401a98b3  test    eax, eax
0x1401a98b5  jnz     short loc_1401A98CE
0x1401a98b7  mov     rcx, [rbx+1C8h]
0x1401a98be  call    cs:__imp_IsImmersiveAppRestricted
0x1401a98c5  nop     dword ptr [rax+rax+00h]
0x1401a98ca  test    eax, eax
0x1401a98cc  jz      short loc_1401A98F2
0x1401a98ce  mov     rcx, rbp
0x1401a98d1  call    ExemptedFromImmersiveRestrictions
0x1401a98d6  test    eax, eax
0x1401a98d8  jnz     short loc_1401A98F2
0x1401a98da  mov     rax, [rbp+1C8h]
0x1401a98e1  mov     ecx, [rax+328h]
0x1401a98e7  bt      rcx, 8
0x1401a98ec  jnb     loc_1401A975B
0x1401a98f2  xor     ecx, ecx
0x1401a98f4  xor     eax, eax
0x1401a98f6  lock cmpxchg [rdi+208h], ecx
0x1401a98fe  test    al, 40h
0x1401a9900  jnz     loc_1401A971C
0x1401a9906  xor     eax, eax
0x1401a9908  lock cmpxchg [rbx+208h], ecx
0x1401a9910  test    al, 40h
0x1401a9912  jnz     loc_1401A971C
0x1401a9918  mov     rax, [rbx+1E8h]
0x1401a991f  cmp     [rdi+1E8h], rax
0x1401a9926  jnz     loc_1401A971C
0x1401a992c  call    cs:__imp_W32GetUserSessionState
0x1401a9933  nop     dword ptr [rax+rax+00h]
0x1401a9938  test    r15d, r15d
0x1401a993b  jz      loc_1401A99DC
0x1401a9941  mov     rcx, [rax+41D8h]
0x1401a9948  jmp     short loc_1401A9967
0x1401a994a  mov     rdx, [rcx+10h]
0x1401a994e  cmp     rdx, rdi
0x1401a9951  jnz     short loc_1401A9959
0x1401a9953  cmp     [rcx+8], rbx
0x1401a9957  jz      short loc_1401A9994
0x1401a9959  cmp     rdx, rbx
0x1401a995c  jnz     short loc_1401A9964
0x1401a995e  cmp     [rcx+8], rdi
0x1401a9962  jz      short loc_1401A9994
0x1401a9964  mov     rcx, [rcx]
0x1401a9967  test    rcx, rcx
0x1401a996a  jnz     short loc_1401A994A
0x1401a996c  mov     edx, 69617355h
0x1401a9971  mov     ecx, 20h ; ' '
0x1401a9976  call    cs:__imp_Win32AllocPoolZInit
0x1401a997d  nop     dword ptr [rax+rax+00h]
0x1401a9982  mov     rsi, rax
0x1401a9985  test    rax, rax
0x1401a9988  jnz     short loc_1401A99A5
0x1401a998a  mov     eax, 0C0000017h
0x1401a998f  jmp     loc_1401A9A18
0x1401a9994  mov     eax, [rcx+18h]
0x1401a9997  cmp     eax, 0FFFFFFFFh
0x1401a999a  jz      short loc_1401A9A13
0x1401a999c  inc     eax
0x1401a999e  mov     [rcx+18h], eax
0x1401a99a1  xor     eax, eax
0x1401a99a3  jmp     short loc_1401A9A18
0x1401a99a5  mov     [rax+8], rbx
0x1401a99a9  mov     [rax+10h], rdi
0x1401a99ad  mov     [rax+18h], r14d
0x1401a99b1  call    cs:__imp_W32GetUserSessionState
0x1401a99b8  nop     dword ptr [rax+rax+00h]
0x1401a99bd  mov     rcx, [rax+41D8h]
0x1401a99c4  mov     [rsi], rcx
0x1401a99c7  call    cs:__imp_W32GetUserSessionState
0x1401a99ce  nop     dword ptr [rax+rax+00h]
0x1401a99d3  mov     [rax+41D8h], rsi
0x1401a99da  jmp     short loc_1401A9A55
0x1401a99dc  lea     rcx, [rax+41D8h]
0x1401a99e3  mov     rdx, [rcx]
0x1401a99e6  test    rdx, rdx
0x1401a99e9  jz      short loc_1401A9A13
0x1401a99eb  mov     r8, [rdx+10h]
0x1401a99ef  cmp     r8, rdi
0x1401a99f2  jnz     short loc_1401A99FA
0x1401a99f4  cmp     [rdx+8], rbx
0x1401a99f8  jz      short loc_1401A9A28
0x1401a99fa  cmp     r8, rbx
0x1401a99fd  jnz     short loc_1401A9A05
0x1401a99ff  cmp     [rdx+8], rdi
0x1401a9a03  jz      short loc_1401A9A28
0x1401a9a05  mov     rax, [rdx]
0x1401a9a08  mov     rcx, rdx
0x1401a9a0b  mov     rdx, rax
0x1401a9a0e  test    rax, rax
0x1401a9a11  jnz     short loc_1401A99EB
0x1401a9a13  mov     eax, 0C000000Dh
0x1401a9a18  add     rsp, 70h
0x1401a9a1c  pop     r15
0x1401a9a1e  pop     r14
0x1401a9a20  pop     r12
0x1401a9a22  pop     rdi
0x1401a9a23  pop     rsi
0x1401a9a24  pop     rbp
0x1401a9a25  pop     rbx
0x1401a9a26  retn
0x1401a9a28  mov     rax, [rcx]
0x1401a9a2b  dec     dword ptr [rax+18h]
0x1401a9a2e  mov     rdx, [rcx]
0x1401a9a31  cmp     dword ptr [rdx+18h], 0
0x1401a9a35  jz      short loc_1401A9A40
0x1401a9a37  test    r12d, r12d
0x1401a9a3a  jz      loc_1401A99A1
0x1401a9a40  mov     rax, [rdx]
0x1401a9a43  mov     [rcx], rax
0x1401a9a46  mov     rcx, rdx
0x1401a9a49  call    cs:__imp_Win32FreePool
0x1401a9a50  nop     dword ptr [rax+rax+00h]
0x1401a9a55  mov     eax, 200h
0x1401a9a5a  or      [rdi+550h], rax
0x1401a9a61  or      [rbx+550h], rax
0x1401a9a68  bt      qword ptr [rbx+550h], 0Ah
0x1401a9a71  jnb     short loc_1401A9A8C
0x1401a9a73  mov     rcx, [rbx+2F8h]; Event
0x1401a9a7a  xor     r8d, r8d; Wait
0x1401a9a7d  mov     edx, r14d; Increment
0x1401a9a80  call    cs:__imp_KeSetEvent
0x1401a9a87  nop     dword ptr [rax+rax+00h]
0x1401a9a8c  mov     eax, [rdi+550h]
0x1401a9a92  bt      rax, 0Ah
0x1401a9a97  jnb     short loc_1401A9AB2
0x1401a9a99  mov     rcx, [rdi+2F8h]; Event
0x1401a9aa0  xor     r8d, r8d; Wait
0x1401a9aa3  mov     edx, r14d; Increment
0x1401a9aa6  call    cs:__imp_KeSetEvent
0x1401a9aad  nop     dword ptr [rax+rax+00h]
0x1401a9ab2  mov     r8, rdi; struct tagTHREADINFO *
0x1401a9ab5  mov     rdx, rbx; struct tagTHREADINFO *
0x1401a9ab8  xor     ecx, ecx; unsigned int
0x1401a9aba  call    ?zzzReattachThreads@@YAXKPEAUtagTHREADINFO@@0@Z; zzzReattachThreads(ulong,tagTHREADINFO *,tagTHREADINFO *)
0x1401a9abf  jmp     loc_1401A99A1
```
