# NtUserPostThreadMessage

- ea: `0x14027a580`
- end: `0x14027a98a`
- name: `NtUserPostThreadMessage`
- size: `1034`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400334e0`
- `0x140082c38`
- `0x1400e2cb0`
- `0x1400e8c20`
- `0x1400eb8c4`
- `0x1400eb95c`
- `0x1401bac50`
- `0x14027a580`
- `0x1402aae84`
- `0x1402c6c90`
- `0x140342fa0`

## import_xrefs

- `win32kbase!GetProcessLuid` at `0x14027a78c`
- `win32kbase!GetProcessLuid` at `0x14027a7a7`
- `win32kbase!GetProcessLuid` at `0x14027a78c`
- `win32kbase!GetProcessLuid` at `0x14027a7a7`
- `win32kbase!?GetTID@tagTHREADINFO@@QEBAKXZ` at `0x14027a6ed`
- `win32kbase!?GetTID@tagTHREADINFO@@QEBAKXZ` at `0x14027a6fe`
- `win32kbase!?GetTID@tagTHREADINFO@@QEBAKXZ` at `0x14027a6ed`
- `win32kbase!?GetTID@tagTHREADINFO@@QEBAKXZ` at `0x14027a6fe`
- `win32kbase!HasTcbPrivilege` at `0x14027a65a`
- `win32kbase!HasTcbPrivilege` at `0x14027a65a`
- `win32kbase!EtwTraceUIPIMsgError` at `0x14027a760`
- `win32kbase!EtwTraceUIPIMsgError` at `0x14027a8a6`
- `win32kbase!EtwTraceUIPIMsgError` at `0x14027a930`
- `win32kbase!EtwTraceUIPIMsgError` at `0x14027a760`
- `win32kbase!EtwTraceUIPIMsgError` at `0x14027a8a6`
- `win32kbase!EtwTraceUIPIMsgError` at `0x14027a930`
- `win32kbase!PtiFromThreadId` at `0x14027a5e2`
- `win32kbase!PtiFromThreadId` at `0x14027a5e2`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x14027a771`
- `win32kbase!?Enforced@UIPrivilegeIsolation@@YA_NXZ` at `0x14027a771`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027a690`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027a86f`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027a908`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027a690`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027a86f`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027a908`
- `win32kbase!EnterCrit` at `0x14027a5ba`
- `win32kbase!EnterCrit` at `0x14027a5ba`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14027a95a`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14027a95a`
- `WIN32K!W32GetUserGdiSessionState` at `0x14027a8c0`
- `WIN32K!W32GetUserGdiSessionState` at `0x14027a8c0`
- `WIN32K!W32GetUserSessionState` at `0x14027a70c`
- `WIN32K!W32GetUserSessionState` at `0x14027a70c`

## pseudocode

```c
__int64 __fastcall NtUserPostThreadMessage(unsigned int a1, unsigned int a2, unsigned __int64 a3, __int64 a4)
{
  __int64 v6; // rdi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // esi
  __int64 v12; // rdx
  __int64 v13; // rcx
  tagTHREADINFO *v14; // r15
  int v15; // ecx
  struct tagTHREADINFO *v16; // r14
  __int64 v17; // rcx
  UIPrivilegeIsolation *v18; // rcx
  const struct tagUIPI_INFO *v19; // r8
  char v20; // al
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 UserSessionState; // rax
  int v26; // r8d
  int v27; // edx
  const struct tagUIPI_INFO *v28; // r8
  __int64 v29; // rbx
  __int64 v30; // rdi
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rcx
  const struct tagUIPI_INFO *v35; // r8
  const struct tagUIPI_INFO *v36; // rdx
  char v38; // [rsp+60h] [rbp-19h]
  bool v39; // [rsp+61h] [rbp-18h]
  __int64 v40; // [rsp+68h] [rbp-11h] BYREF
  __int64 v41; // [rsp+70h] [rbp-9h]
  __int64 v42; // [rsp+78h] [rbp-1h] BYREF
  int v43; // [rsp+80h] [rbp+7h]

  v41 = a4;
  v6 = a4;
  EnterCrit(0, 0);
  if ( (a2 & 0xFFFE0000) == 0 )
  {
    v11 = 0;
    v14 = (tagTHREADINFO *)PtiFromThreadId(a1);
    if ( !v14 )
    {
LABEL_4:
      v15 = 1444;
LABEL_5:
      UserSetLastError(v15);
      goto LABEL_42;
    }
    v16 = PtiCurrent(v13, v12);
    if ( *((_QWORD *)v16 + 61) != *((_QWORD *)v14 + 61)
      && (_InterlockedCompareExchange((volatile signed __int32 *)v16 + 130, 0, 0) & 8) == 0
      && !GetDesktopView(*((_QWORD *)v16 + 57), *((_QWORD *)v14 + 61)) )
    {
      v42 = 0;
      v40 = 0;
      if ( !(unsigned __int8)HasTcbPrivilege() )
        goto LABEL_4;
      if ( (unsigned int)Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline(v17) )
      {
        if ( !UIPrivilegeIsolation::CheckAccess(
                (UIPrivilegeIsolation *)(*((_QWORD *)v16 + 57) + 864LL),
                (const struct tagUIPI_INFO *)(*((_QWORD *)v14 + 57) + 864LL),
                v19) )
        {
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000) == 0
            || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
          {
            v20 = 0;
          }
          v38 = v20;
          v39 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v20 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            tagTHREADINFO::GetTID(v14);
            tagTHREADINFO::GetTID(v16);
            UserSessionState = W32GetUserSessionState(v22, v21, v23, v24);
            LOBYTE(v26) = v39;
            LOBYTE(v27) = v38;
            WPP_RECORDER_AND_TRACE_SF_LDD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v27,
              v26,
              *(_QWORD *)(UserSessionState + 69152));
            v6 = v41;
          }
          EtwTraceUIPIMsgError(*((_QWORD *)v16 + 57), *((_QWORD *)v14 + 57), a2, a3, v6);
          goto LABEL_4;
        }
      }
      else if ( UIPrivilegeIsolation::Enforced(v18) )
      {
        if ( !UIPrivilegeIsolation::CheckAccess(
                (UIPrivilegeIsolation *)(*((_QWORD *)v16 + 57) + 864LL),
                (const struct tagUIPI_INFO *)(*((_QWORD *)v14 + 57) + 864LL),
                v28) )
        {
          UserSetLastError(1444);
          EtwTraceUIPIMsgError(*((_QWORD *)v16 + 57), *((_QWORD *)v14 + 57), a2, a3, v6);
          goto LABEL_42;
        }
      }
      else if ( (int)GetProcessLuid(*(_QWORD *)v16, &v42) < 0
             || (int)GetProcessLuid(*(_QWORD *)v14, &v40) < 0
             || v42 != v40 )
      {
        goto LABEL_4;
      }
    }
    v29 = *((_QWORD *)v14 + 57);
    v30 = *((_QWORD *)v16 + 57);
    if ( v29 == v30 )
      goto LABEL_41;
    if ( a2 == 717 )
      goto LABEL_42;
    if ( (unsigned int)IsMessageAllowedAcrossILByReceiver(*((struct tagPROCESSINFO **)v14 + 57), 0, a2)
      || (unsigned int)IsMessageAlwaysAllowedAcrossIL(a2, v31, v32, v33)
      || a2 == 274 && ((a3 - 61472) & 0xFFFFFFFFFFFFFEBFuLL) == 0 && a3 != 61792
      || (!(unsigned int)Feature_MsgUseCSRSSTrueIL__private_IsEnabledDeviceUsageNoInline()
        ? ((v42 = 0, v43 = 0, *(_QWORD *)v29 != *(_QWORD *)(W32GetUserGdiSessionState(v34) + 40))
         ? (v42 = *(_QWORD *)(v29 + 864), v43 = *(_DWORD *)(v29 + 872))
         : (v42 = 0x2000, v43 = 0),
           v36 = (const struct tagUIPI_INFO *)&v42)
        : (v36 = (const struct tagUIPI_INFO *)(v29 + 864)),
          UIPrivilegeIsolation::CheckAccess((UIPrivilegeIsolation *)(v30 + 864), v36, v35)) )
    {
LABEL_41:
      v11 = PostThreadMessage(v14, a2, a3, v41);
      goto LABEL_42;
    }
    EtwTraceUIPIMsgError(v30, v29, a2, a3, v41);
    v15 = 5;
    goto LABEL_5;
  }
  UserSetLastError(87);
  v11 = 0;
LABEL_42:
  UserSessionSwitchLeaveCrit(v9, v8, v10);
  return v11;
}

```

## disassembly

```asm
0x14027a580  push    rbp
0x14027a582  push    rbx
0x14027a583  push    rsi
0x14027a584  push    rdi
0x14027a585  push    r12
0x14027a587  push    r13
0x14027a589  push    r14
0x14027a58b  push    r15
0x14027a58d  lea     rbp, [rsp-1Fh]
0x14027a592  sub     rsp, 98h
0x14027a599  mov     rax, cs:__security_cookie
0x14027a5a0  xor     rax, rsp
0x14027a5a3  mov     [rbp+57h+var_48], rax
0x14027a5a7  mov     r12d, edx
0x14027a5aa  mov     [rbp+57h+var_60], r9
0x14027a5ae  mov     ebx, ecx
0x14027a5b0  xor     edx, edx
0x14027a5b2  xor     ecx, ecx
0x14027a5b4  mov     rdi, r9
0x14027a5b7  mov     r13, r8
0x14027a5ba  call    cs:__imp_EnterCrit
0x14027a5c1  nop     dword ptr [rax+rax+00h]
0x14027a5c6  test    r12d, 0FFFE0000h
0x14027a5cd  jz      short loc_14027A5E0
0x14027a5cf  mov     ecx, 57h ; 'W'
0x14027a5d4  call    UserSetLastError
0x14027a5d9  xor     esi, esi
0x14027a5db  jmp     loc_14027A95A
0x14027a5e0  mov     ecx, ebx
0x14027a5e2  call    cs:__imp_PtiFromThreadId
0x14027a5e9  nop     dword ptr [rax+rax+00h]
0x14027a5ee  xor     esi, esi
0x14027a5f0  mov     r15, rax
0x14027a5f3  test    rax, rax
0x14027a5f6  jnz     short loc_14027A607
0x14027a5f8  mov     ecx, 5A4h
0x14027a5fd  call    UserSetLastError
0x14027a602  jmp     loc_14027A95A
0x14027a607  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14027a60c  mov     r14, rax
0x14027a60f  mov     rax, [r15+1E8h]
0x14027a616  cmp     [r14+1E8h], rax
0x14027a61d  jz      loc_14027A7D3
0x14027a623  xor     eax, eax
0x14027a625  lock cmpxchg [r14+208h], esi
0x14027a62e  test    al, 8
0x14027a630  jnz     loc_14027A7D3
0x14027a636  mov     rdx, [r15+1E8h]
0x14027a63d  mov     rcx, [r14+1C8h]
0x14027a644  call    GetDesktopView
0x14027a649  test    rax, rax
0x14027a64c  jnz     loc_14027A7D3
0x14027a652  mov     [rbp+57h+var_58], rsi
0x14027a656  mov     [rbp+57h+var_68], rsi
0x14027a65a  call    cs:__imp_HasTcbPrivilege
0x14027a661  nop     dword ptr [rax+rax+00h]
0x14027a666  test    al, al
0x14027a668  jz      short loc_14027A5F8
0x14027a66a  call    Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline
0x14027a66f  test    eax, eax
0x14027a671  jz      loc_14027A771
0x14027a677  mov     rdx, [r15+1C8h]
0x14027a67e  mov     eax, 360h
0x14027a683  mov     rcx, [r14+1C8h]
0x14027a68a  add     rdx, rax
0x14027a68d  add     rcx, rax
0x14027a690  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x14027a697  nop     dword ptr [rax+rax+00h]
0x14027a69c  test    al, al
0x14027a69e  jnz     loc_14027A7D3
0x14027a6a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14027a6ab  lea     rax, WPP_GLOBAL_Control
0x14027a6b2  cmp     rcx, rax
0x14027a6b5  jz      short loc_14027A6C8
0x14027a6b7  test    dword ptr [rcx+2Ch], 8000h
0x14027a6be  jz      short loc_14027A6C8
0x14027a6c0  cmp     byte ptr [rcx+29h], 3
0x14027a6c4  mov     al, 1
0x14027a6c6  jnb     short loc_14027A6CB
0x14027a6c8  mov     al, sil
0x14027a6cb  lea     rcx, WPP_RECORDER_INITIALIZED
0x14027a6d2  mov     [rbp+57h+var_70], al
0x14027a6d5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14027a6dc  setnz   cl
0x14027a6df  mov     [rbp+57h+var_6F], cl
0x14027a6e2  test    al, al
0x14027a6e4  jnz     short loc_14027A6EA
0x14027a6e6  test    cl, cl
0x14027a6e8  jz      short loc_14027A747
0x14027a6ea  mov     rcx, r15
0x14027a6ed  call    cs:__imp_?GetTID@tagTHREADINFO@@QEBAKXZ; tagTHREADINFO::GetTID(void)
0x14027a6f4  nop     dword ptr [rax+rax+00h]
0x14027a6f9  mov     rcx, r14
0x14027a6fc  mov     edi, eax
0x14027a6fe  call    cs:__imp_?GetTID@tagTHREADINFO@@QEBAKXZ; tagTHREADINFO::GetTID(void)
0x14027a705  nop     dword ptr [rax+rax+00h]
0x14027a70a  mov     ebx, eax
0x14027a70c  call    cs:__imp_W32GetUserSessionState
0x14027a713  nop     dword ptr [rax+rax+00h]
0x14027a718  mov     rcx, cs:WPP_GLOBAL_Control
0x14027a71f  mov     r8b, [rbp+57h+var_6F]
0x14027a723  mov     dl, [rbp+57h+var_70]
0x14027a726  mov     r9, [rax+10E20h]
0x14027a72d  mov     rcx, [rcx+18h]
0x14027a731  mov     [rsp+0D0h+var_80], edi
0x14027a735  mov     [rsp+0D0h+var_88], ebx
0x14027a739  mov     [rsp+0D0h+var_90], r12d
0x14027a73e  call    WPP_RECORDER_AND_TRACE_SF_LDD
0x14027a743  mov     rdi, [rbp+57h+var_60]
0x14027a747  mov     rdx, [r15+1C8h]
0x14027a74e  mov     r9, r13
0x14027a751  mov     rcx, [r14+1C8h]
0x14027a758  mov     r8d, r12d
0x14027a75b  mov     [rsp+0D0h+var_B0], rdi
0x14027a760  call    cs:__imp_EtwTraceUIPIMsgError
0x14027a767  nop     dword ptr [rax+rax+00h]
0x14027a76c  jmp     loc_14027A5F8
0x14027a771  call    cs:__imp_?Enforced@UIPrivilegeIsolation@@YA_NXZ; UIPrivilegeIsolation::Enforced(void)
0x14027a778  nop     dword ptr [rax+rax+00h]
0x14027a77d  test    al, al
0x14027a77f  jnz     loc_14027A856
0x14027a785  mov     rcx, [r14]
0x14027a788  lea     rdx, [rbp+57h+var_58]
0x14027a78c  call    cs:__imp_GetProcessLuid
0x14027a793  nop     dword ptr [rax+rax+00h]
0x14027a798  test    eax, eax
0x14027a79a  js      loc_14027A5F8
0x14027a7a0  mov     rcx, [r15]
0x14027a7a3  lea     rdx, [rbp+57h+var_68]
0x14027a7a7  call    cs:__imp_GetProcessLuid
0x14027a7ae  nop     dword ptr [rax+rax+00h]
0x14027a7b3  test    eax, eax
0x14027a7b5  js      loc_14027A5F8
0x14027a7bb  mov     eax, dword ptr [rbp+57h+var_68]
0x14027a7be  cmp     dword ptr [rbp+57h+var_58], eax
0x14027a7c1  jnz     loc_14027A5F8
0x14027a7c7  mov     eax, dword ptr [rbp+57h+var_68+4]
0x14027a7ca  cmp     dword ptr [rbp+57h+var_58+4], eax
0x14027a7cd  jnz     loc_14027A5F8
0x14027a7d3  mov     rbx, [r15+1C8h]
0x14027a7da  mov     rdi, [r14+1C8h]
0x14027a7e1  cmp     rbx, rdi
0x14027a7e4  jz      loc_14027A946
0x14027a7ea  cmp     r12d, 2CDh
0x14027a7f1  jz      loc_14027A95A
0x14027a7f7  mov     r8d, r12d; unsigned int
0x14027a7fa  xor     edx, edx; struct tagWND *
0x14027a7fc  mov     rcx, rbx; struct tagPROCESSINFO *
0x14027a7ff  call    ?IsMessageAllowedAcrossILByReceiver@@YAHPEAUtagPROCESSINFO@@PEAUtagWND@@I@Z; IsMessageAllowedAcrossILByReceiver(tagPROCESSINFO *,tagWND *,uint)
0x14027a804  test    eax, eax
0x14027a806  jnz     loc_14027A946
0x14027a80c  mov     ecx, r12d; unsigned int
0x14027a80f  call    ?IsMessageAlwaysAllowedAcrossIL@@YAHI@Z; IsMessageAlwaysAllowedAcrossIL(uint)
0x14027a814  test    eax, eax
0x14027a816  jnz     loc_14027A946
0x14027a81c  cmp     r12d, 112h
0x14027a823  jnz     short loc_14027A841
0x14027a825  lea     rax, [r13-0F020h]
0x14027a82c  test    rax, 0FFFFFFFFFFFFFEBFh
0x14027a832  jnz     short loc_14027A841
0x14027a834  cmp     r13, 0F160h
0x14027a83b  jnz     loc_14027A946
0x14027a841  call    Feature_MsgUseCSRSSTrueIL__private_IsEnabledDeviceUsageNoInline
0x14027a846  test    eax, eax
0x14027a848  jz      short loc_14027A8B7
0x14027a84a  lea     rdx, [rbx+360h]
0x14027a851  jmp     loc_14027A901
0x14027a856  mov     rdx, [r15+1C8h]
0x14027a85d  mov     eax, 360h
0x14027a862  mov     rcx, [r14+1C8h]
0x14027a869  add     rdx, rax
0x14027a86c  add     rcx, rax
0x14027a86f  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x14027a876  nop     dword ptr [rax+rax+00h]
0x14027a87b  test    al, al
0x14027a87d  jnz     loc_14027A7D3
0x14027a883  mov     ecx, 5A4h
0x14027a888  call    UserSetLastError
0x14027a88d  mov     rdx, [r15+1C8h]
0x14027a894  mov     r9, r13
0x14027a897  mov     rcx, [r14+1C8h]
0x14027a89e  mov     r8d, r12d
0x14027a8a1  mov     [rsp+0D0h+var_B0], rdi
0x14027a8a6  call    cs:__imp_EtwTraceUIPIMsgError
0x14027a8ad  nop     dword ptr [rax+rax+00h]
0x14027a8b2  jmp     loc_14027A95A
0x14027a8b7  xor     eax, eax
0x14027a8b9  mov     [rbp+57h+var_58], rax
0x14027a8bd  mov     [rbp+57h+var_50], eax
0x14027a8c0  call    cs:__imp_W32GetUserGdiSessionState
0x14027a8c7  nop     dword ptr [rax+rax+00h]
0x14027a8cc  mov     rcx, [rax+28h]
0x14027a8d0  cmp     [rbx], rcx
0x14027a8d3  jnz     short loc_14027A8E2
0x14027a8d5  mov     [rbp+57h+var_58], 2000h
0x14027a8dd  mov     [rbp+57h+var_50], esi
0x14027a8e0  jmp     short loc_14027A8FD
0x14027a8e2  mov     eax, [rbx+360h]
0x14027a8e8  mov     dword ptr [rbp+57h+var_58], eax
0x14027a8eb  mov     eax, [rbx+364h]
0x14027a8f1  mov     dword ptr [rbp+57h+var_58+4], eax
0x14027a8f4  mov     eax, [rbx+368h]
0x14027a8fa  mov     [rbp+57h+var_50], eax
0x14027a8fd  lea     rdx, [rbp+57h+var_58]
0x14027a901  lea     rcx, [rdi+360h]
0x14027a908  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x14027a90f  nop     dword ptr [rax+rax+00h]
0x14027a914  movzx   eax, al
0x14027a917  test    eax, eax
0x14027a919  jnz     short loc_14027A946
0x14027a91b  mov     r9, [rbp+57h+var_60]
0x14027a91f  mov     r8d, r12d
0x14027a922  mov     [rsp+0D0h+var_B0], r9
0x14027a927  mov     rdx, rbx
0x14027a92a  mov     r9, r13
0x14027a92d  mov     rcx, rdi
0x14027a930  call    cs:__imp_EtwTraceUIPIMsgError
0x14027a937  nop     dword ptr [rax+rax+00h]
0x14027a93c  mov     ecx, 5
0x14027a941  jmp     loc_14027A5FD
0x14027a946  mov     r9, [rbp+57h+var_60]
0x14027a94a  mov     r8, r13
0x14027a94d  mov     edx, r12d
0x14027a950  mov     rcx, r15
0x14027a953  call    _PostThreadMessage
0x14027a958  mov     esi, eax
0x14027a95a  call    cs:__imp_UserSessionSwitchLeaveCrit
0x14027a961  nop     dword ptr [rax+rax+00h]
0x14027a966  movsxd  rax, esi
0x14027a969  mov     rcx, [rbp+57h+var_48]
0x14027a96d  xor     rcx, rsp; StackCookie
0x14027a970  call    __security_check_cookie
0x14027a975  add     rsp, 98h
0x14027a97c  pop     r15
0x14027a97e  pop     r14
0x14027a980  pop     r13
0x14027a982  pop     r12
0x14027a984  pop     rdi
0x14027a985  pop     rsi
0x14027a986  pop     rbx
0x14027a987  pop     rbp
0x14027a988  retn
```
