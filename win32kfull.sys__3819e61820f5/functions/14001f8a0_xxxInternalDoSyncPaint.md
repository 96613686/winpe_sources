# xxxInternalDoSyncPaint

- ea: `0x14001f8a0`
- end: `0x14001fc32`
- name: `xxxInternalDoSyncPaint`
- size: `914`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14001e700`
- `0x14001f8a0`
- `0x1400c591c`

## callees

- `0x14001f8a0`
- `0x14001fc40`
- `0x1400204e0`
- `0x1400208b0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14001fb94`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14001fb94`
- `ntoskrnl!KeBugCheckEx` at `0x14001fbd3`
- `ntoskrnl!KeBugCheckEx` at `0x14001fbd3`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f94e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f96b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f9b7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f9f9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001faf4`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f94e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f96b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f9b7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f9f9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001faf4`
- `win32kbase!HMPkheFromPhe` at `0x14001fa6a`
- `win32kbase!HMPkheFromPhe` at `0x14001fa6a`
- `win32kbase!HMLockObject` at `0x14001fadd`
- `win32kbase!HMLockObject` at `0x14001fadd`
- `win32kbase!HMUnlockObject` at `0x14001fb2f`
- `win32kbase!HMUnlockObject` at `0x14001fb2f`
- `win32kbase!Win32AllocPoolZInit` at `0x14001fbea`
- `win32kbase!Win32AllocPoolZInit` at `0x14001fbea`
- `win32kbase!Win32FreePool` at `0x14001fbad`
- `win32kbase!Win32FreePool` at `0x14001fbad`
- `WIN32K!W32GetUserSessionState` at `0x14001f8e3`
- `WIN32K!W32GetUserSessionState` at `0x14001f901`
- `WIN32K!W32GetUserSessionState` at `0x14001f98d`
- `WIN32K!W32GetUserSessionState` at `0x14001f9a4`
- `WIN32K!W32GetUserSessionState` at `0x14001fa1c`
- `WIN32K!W32GetUserSessionState` at `0x14001fa39`
- `WIN32K!W32GetUserSessionState` at `0x14001fa48`
- `WIN32K!W32GetUserSessionState` at `0x14001f8e3`
- `WIN32K!W32GetUserSessionState` at `0x14001f901`
- `WIN32K!W32GetUserSessionState` at `0x14001f98d`
- `WIN32K!W32GetUserSessionState` at `0x14001f9a4`
- `WIN32K!W32GetUserSessionState` at `0x14001fa1c`
- `WIN32K!W32GetUserSessionState` at `0x14001fa39`
- `WIN32K!W32GetUserSessionState` at `0x14001fa48`

## pseudocode

```c
void __fastcall xxxInternalDoSyncPaint(struct tagWND *a1, unsigned int a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  struct tagWND *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // r9
  struct tagBWL *v14; // rax
  struct tagBWL *v15; // r12
  _QWORD *v16; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v18; // rcx
  __int64 *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r13
  __int64 v33; // rbx
  _QWORD *i; // rsi
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 UserSessionState; // rdi
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdi
  __int64 v48; // rdx
  __int64 v49; // r8
  ULONG_PTR *v50; // r14
  ULONG_PTR v51; // rbx
  ULONG_PTR v52; // rcx
  __int64 v53; // rcx
  ULONG_PTR *v54; // rax
  ULONG_PTR v55; // r8
  ULONG_PTR *v56; // rcx
  __int64 v57; // rax
  ULONG_PTR BugCheckParameter3[2]; // [rsp+30h] [rbp-38h] BYREF

  xxxSimpleDoSyncPaint(a1);
  if ( (a2 & 0x20) != 0 || (a2 & 4) != 0 && (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 2) != 0 )
  {
    v8 = (struct tagWND *)*((_QWORD *)a1 + 14);
    v11 = *(_QWORD *)(W32GetUserSessionState(v5, v4, v6, v7) + 63200);
    if ( v11 )
    {
      *(_QWORD *)(W32GetUserSessionState(v10, v9, v12, v13) + 63200) = 0;
    }
    else
    {
      v57 = Win32AllocPoolZInit(296, 1819767637);
      v11 = v57;
      if ( !v57 )
        return;
      *(_QWORD *)(v57 + 16) = v57 + 280;
    }
    *(_QWORD *)(v11 + 8) = v11 + 32;
    *(_QWORD *)(v11 + 24) = 0;
    v14 = InternalBuildHwndList((struct tagBWL *)v11, v8, 2u);
    v15 = v14;
    v16 = (_QWORD *)*((_QWORD *)v14 + 1);
    if ( (unsigned __int64)v16 >= *((_QWORD *)v14 + 2) )
    {
      Win32FreePool(v14);
    }
    else
    {
      *v16 = 1;
      CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v16);
      if ( CurrentThreadWin32Thread )
        v18 = *CurrentThreadWin32Thread;
      else
        v18 = 0;
      *((_QWORD *)v15 + 3) = v18;
      v19 = (__int64 *)PsGetCurrentThreadWin32Thread(v18);
      if ( v19 )
        v24 = *v19;
      else
        v24 = 0;
      *((_QWORD *)v15 + 3) = v24;
      v25 = *(_QWORD *)(W32GetUserSessionState(v21, v20, v22, v23) + 63008);
      *(_QWORD *)v15 = v25;
      *(_QWORD *)(W32GetUserSessionState(v25, v26, v27, v28) + 63008) = v15;
      v30 = (__int64 *)PsGetCurrentThreadWin32Thread(v29);
      if ( v30 )
        v32 = *v30;
      else
        v32 = 0;
      v33 = *((_QWORD *)v15 + 4);
      for ( i = (_QWORD *)((char *)v15 + 32); v33 != 1; ++i )
      {
        if ( v33 )
        {
          PsGetCurrentThreadWin32Thread(v31);
          v31 = *(_QWORD *)(W32GetUserSessionState(v36, v35, v37, v38) + 19704);
          if ( (unsigned __int64)(unsigned __int16)v33 < *(_QWORD *)(v31 + 8) )
          {
            UserSessionState = W32GetUserSessionState(v31, v39, v40, v41);
            v47 = *(_DWORD *)(W32GetUserSessionState(v44, v43, v45, v46) + 19728) * (unsigned int)(unsigned __int16)v33
                + *(_QWORD *)(UserSessionState + 19720);
            v50 = (ULONG_PTR *)HMPkheFromPhe(v47);
            LOWORD(v33) = WORD1(v33) & 0x7FFF;
            if ( ((WORD1(v33) & 0x7FFF) == *(_WORD *)(v47 + 26)
               || (_WORD)v33 == 0x7FFF
               || !(_WORD)v33 && PsGetCurrentProcessWow64Process(v31, v48, v49))
              && (*(_BYTE *)(v47 + 25) & 1) == 0
              && *(_BYTE *)(v47 + 24) == 1 )
            {
              v51 = *v50;
              if ( *v50 )
              {
                if ( (*(_BYTE *)(*(_QWORD *)(v51 + 40) + 31LL) & 0x40) == 0 || v32 == *(_QWORD *)(v51 + 16) )
                {
                  v52 = *v50;
                  BugCheckParameter3[0] = *(_QWORD *)(v32 + 448);
                  *(_QWORD *)(v32 + 448) = BugCheckParameter3;
                  BugCheckParameter3[1] = v51;
                  HMLockObject(v52);
                  xxxInternalDoSyncPaint(v51, a2);
                  v54 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v53);
                  if ( v54 )
                    v55 = *v54;
                  else
                    v55 = 0;
                  v56 = *(ULONG_PTR **)(v55 + 448);
                  if ( v56 != BugCheckParameter3 )
                    KeBugCheckEx(0x164u, 0x3Bu, v55, (ULONG_PTR)BugCheckParameter3, 0);
                  *(_QWORD *)(v55 + 448) = *v56;
                  HMUnlockObject(v56[1]);
                }
              }
            }
          }
        }
        v33 = i[1];
      }
      FreeHwndList(v15);
    }
  }
}

```

## disassembly

```asm
0x14001f8a0  push    rbx
0x14001f8a2  push    r15
0x14001f8a4  sub     rsp, 58h
0x14001f8a8  mov     r15d, edx
0x14001f8ab  mov     rbx, rcx
0x14001f8ae  call    xxxSimpleDoSyncPaint
0x14001f8b3  test    r15b, 20h
0x14001f8b7  jnz     short loc_14001F8D2
0x14001f8b9  test    r15b, 4
0x14001f8bd  jz      short loc_14001F8C9
0x14001f8bf  mov     rax, [rbx+28h]
0x14001f8c3  test    byte ptr [rax+1Fh], 2
0x14001f8c7  jnz     short loc_14001F8D2
0x14001f8c9  add     rsp, 58h
0x14001f8cd  pop     r15
0x14001f8cf  pop     rbx
0x14001f8d0  retn
0x14001f8d2  mov     [rsp+68h+arg_8], rsi
0x14001f8d7  mov     [rsp+68h+arg_10], rdi
0x14001f8df  mov     rdi, [rbx+70h]
0x14001f8e3  call    cs:__imp_W32GetUserSessionState
0x14001f8ea  nop     dword ptr [rax+rax+00h]
0x14001f8ef  xor     esi, esi
0x14001f8f1  mov     rbx, [rax+0F6E0h]
0x14001f8f8  test    rbx, rbx
0x14001f8fb  jz      loc_14001FBE0
0x14001f901  call    cs:__imp_W32GetUserSessionState
0x14001f908  nop     dword ptr [rax+rax+00h]
0x14001f90d  mov     [rax+0F6E0h], rsi
0x14001f914  lea     rcx, [rbx+20h]
0x14001f918  mov     [rsp+68h+var_18], r12
0x14001f91d  mov     [rbx+8], rcx
0x14001f921  mov     r8d, 2; unsigned int
0x14001f927  mov     rcx, rbx; struct tagBWL *
0x14001f92a  mov     [rbx+18h], rsi
0x14001f92e  mov     rdx, rdi; struct tagWND *
0x14001f931  call    ?InternalBuildHwndList@@YAPEAUtagBWL@@PEAU1@PEAUtagWND@@I@Z; InternalBuildHwndList(tagBWL *,tagWND *,uint)
0x14001f936  mov     r12, rax
0x14001f939  mov     rcx, [rax+8]
0x14001f93d  cmp     rcx, [rax+10h]
0x14001f941  jnb     loc_14001FBAA
0x14001f947  mov     qword ptr [rcx], 1
0x14001f94e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001f955  nop     dword ptr [rax+rax+00h]
0x14001f95a  test    rax, rax
0x14001f95d  jz      loc_14001FC22
0x14001f963  mov     rcx, [rax]
0x14001f966  mov     [r12+18h], rcx
0x14001f96b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001f972  nop     dword ptr [rax+rax+00h]
0x14001f977  test    rax, rax
0x14001f97a  jz      loc_14001FC2A
0x14001f980  mov     rax, [rax]
0x14001f983  mov     [rsp+68h+var_20], r13
0x14001f988  mov     [r12+18h], rax
0x14001f98d  call    cs:__imp_W32GetUserSessionState
0x14001f994  nop     dword ptr [rax+rax+00h]
0x14001f999  mov     rcx, [rax+0F620h]
0x14001f9a0  mov     [r12], rcx
0x14001f9a4  call    cs:__imp_W32GetUserSessionState
0x14001f9ab  nop     dword ptr [rax+rax+00h]
0x14001f9b0  mov     [rax+0F620h], r12
0x14001f9b7  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001f9be  nop     dword ptr [rax+rax+00h]
0x14001f9c3  test    rax, rax
0x14001f9c6  jz      loc_14001FC1A
0x14001f9cc  mov     r13, [rax]
0x14001f9cf  mov     rbx, [r12+20h]
0x14001f9d4  lea     rsi, [r12+20h]
0x14001f9d9  mov     [rsp+68h+arg_0], rbp
0x14001f9de  mov     [rsp+68h+var_28], r14
0x14001f9e3  cmp     rbx, 1
0x14001f9e7  jz      loc_14001FB4D
0x14001f9ed  nop     dword ptr [rax]
0x14001f9f0  test    rbx, rbx
0x14001f9f3  jz      loc_14001FB3B
0x14001f9f9  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001fa00  nop     dword ptr [rax+rax+00h]
0x14001fa05  test    rax, rax
0x14001fa08  jz      short loc_14001FA19
0x14001fa0a  mov     rax, [rax]
0x14001fa0d  test    rax, rax
0x14001fa10  jz      short loc_14001FA19
0x14001fa12  mov     rax, [rax+200h]
0x14001fa19  movzx   ebp, bx
0x14001fa1c  call    cs:__imp_W32GetUserSessionState
0x14001fa23  nop     dword ptr [rax+rax+00h]
0x14001fa28  mov     rcx, [rax+4CF8h]
0x14001fa2f  cmp     rbp, [rcx+8]
0x14001fa33  jnb     loc_14001FB3B
0x14001fa39  call    cs:__imp_W32GetUserSessionState
0x14001fa40  nop     dword ptr [rax+rax+00h]
0x14001fa45  mov     rdi, rax
0x14001fa48  call    cs:__imp_W32GetUserSessionState
0x14001fa4f  nop     dword ptr [rax+rax+00h]
0x14001fa54  mov     rdi, [rdi+4D08h]
0x14001fa5b  imul    ebp, [rax+4D10h]
0x14001fa62  mov     ecx, ebp
0x14001fa64  add     rdi, rcx
0x14001fa67  mov     rcx, rdi
0x14001fa6a  call    cs:__imp_HMPkheFromPhe
0x14001fa71  nop     dword ptr [rax+rax+00h]
0x14001fa76  shr     rbx, 10h
0x14001fa7a  mov     r14, rax
0x14001fa7d  mov     eax, 7FFFh
0x14001fa82  and     bx, ax
0x14001fa85  cmp     bx, [rdi+1Ah]
0x14001fa89  jnz     loc_14001FB86
0x14001fa8f  test    byte ptr [rdi+19h], 1
0x14001fa93  jnz     loc_14001FB3B
0x14001fa99  cmp     byte ptr [rdi+18h], 1
0x14001fa9d  jnz     loc_14001FB3B
0x14001faa3  mov     rbx, [r14]
0x14001faa6  test    rbx, rbx
0x14001faa9  jz      loc_14001FB3B
0x14001faaf  mov     rax, [rbx+28h]
0x14001fab3  test    byte ptr [rax+1Fh], 40h
0x14001fab7  jnz     loc_14001FB7B
0x14001fabd  mov     rax, [r13+1C0h]
0x14001fac4  mov     rcx, rbx
0x14001fac7  mov     [rsp+68h+BugCheckParameter3], rax
0x14001facc  lea     rax, [rsp+68h+BugCheckParameter3]
0x14001fad1  mov     [r13+1C0h], rax
0x14001fad8  mov     [rsp+68h+var_30], rbx
0x14001fadd  call    cs:__imp_HMLockObject
0x14001fae4  nop     dword ptr [rax+rax+00h]
0x14001fae9  mov     edx, r15d
0x14001faec  mov     rcx, rbx
0x14001faef  call    xxxInternalDoSyncPaint
0x14001faf4  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001fafb  nop     dword ptr [rax+rax+00h]
0x14001fb00  test    rax, rax
0x14001fb03  jz      loc_14001FC12
0x14001fb09  mov     r8, [rax]; BugCheckParameter2
0x14001fb0c  mov     rcx, [r8+1C0h]
0x14001fb13  lea     rax, [rsp+68h+BugCheckParameter3]
0x14001fb18  cmp     rcx, rax
0x14001fb1b  jnz     loc_14001FBBB
0x14001fb21  mov     rax, [rcx]
0x14001fb24  mov     [r8+1C0h], rax
0x14001fb2b  mov     rcx, [rcx+8]
0x14001fb2f  call    cs:__imp_HMUnlockObject
0x14001fb36  nop     dword ptr [rax+rax+00h]
0x14001fb3b  mov     rbx, [rsi+8]
0x14001fb3f  add     rsi, 8
0x14001fb43  cmp     rbx, 1
0x14001fb47  jnz     loc_14001F9F0
0x14001fb4d  mov     rcx, r12
0x14001fb50  call    FreeHwndList
0x14001fb55  mov     rbp, [rsp+68h+arg_0]
0x14001fb5a  mov     r14, [rsp+68h+var_28]
0x14001fb5f  mov     r13, [rsp+68h+var_20]
0x14001fb64  mov     r12, [rsp+68h+var_18]
0x14001fb69  mov     rsi, [rsp+68h+arg_8]
0x14001fb6e  mov     rdi, [rsp+68h+arg_10]
0x14001fb76  jmp     loc_14001F8C9
0x14001fb7b  cmp     r13, [rbx+10h]
0x14001fb7f  jnz     short loc_14001FB3B
0x14001fb81  jmp     loc_14001FABD
0x14001fb86  cmp     bx, ax
0x14001fb89  jz      loc_14001FA8F
0x14001fb8f  test    bx, bx
0x14001fb92  jnz     short loc_14001FB3B
0x14001fb94  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14001fb9b  nop     dword ptr [rax+rax+00h]
0x14001fba0  test    rax, rax
0x14001fba3  jz      short loc_14001FB3B
0x14001fba5  jmp     loc_14001FA8F
0x14001fbaa  mov     rcx, r12
0x14001fbad  call    cs:__imp_Win32FreePool
0x14001fbb4  nop     dword ptr [rax+rax+00h]
0x14001fbb9  jmp     short loc_14001FB64
0x14001fbbb  lea     r9, [rsp+68h+BugCheckParameter3]; BugCheckParameter3
0x14001fbc0  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x14001fbc9  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14001fbce  mov     ecx, 164h; BugCheckCode
0x14001fbd3  call    cs:__imp_KeBugCheckEx
0x14001fbe0  mov     edx, 6C777355h
0x14001fbe5  mov     ecx, 128h
0x14001fbea  call    cs:__imp_Win32AllocPoolZInit
0x14001fbf1  nop     dword ptr [rax+rax+00h]
0x14001fbf6  mov     rbx, rax
0x14001fbf9  test    rax, rax
0x14001fbfc  jz      loc_14001FB69
0x14001fc02  lea     rcx, [rax+118h]
0x14001fc09  mov     [rax+10h], rcx
0x14001fc0d  jmp     loc_14001F914
0x14001fc12  xor     r8d, r8d
0x14001fc15  jmp     loc_14001FB0C
0x14001fc1a  mov     r13, rsi
0x14001fc1d  jmp     loc_14001F9CF
0x14001fc22  mov     rcx, rsi
0x14001fc25  jmp     loc_14001F966
0x14001fc2a  mov     rax, rsi
0x14001fc2d  jmp     loc_14001F983
```
