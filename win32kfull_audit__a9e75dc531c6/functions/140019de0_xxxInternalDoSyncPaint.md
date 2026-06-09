# xxxInternalDoSyncPaint

- ea: `0x140019de0`
- end: `0x14001a172`
- name: `xxxInternalDoSyncPaint`
- size: `914`
- prototype: `void __fastcall(struct tagWND *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140019de0`
- `0x1400ebc3c`
- `0x1401e2164`

## callees

- `0x140019de0`
- `0x14001a180`
- `0x14001aa20`
- `0x14001adf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14001a0d4`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14001a0d4`
- `ntoskrnl!KeBugCheckEx` at `0x14001a113`
- `ntoskrnl!KeBugCheckEx` at `0x14001a113`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019e8e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019eab`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019ef7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019f39`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001a034`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019e8e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019eab`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019ef7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019f39`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001a034`
- `win32kbase!HMPkheFromPhe` at `0x140019faa`
- `win32kbase!HMPkheFromPhe` at `0x140019faa`
- `win32kbase!HMLockObject` at `0x14001a01d`
- `win32kbase!HMLockObject` at `0x14001a01d`
- `win32kbase!HMUnlockObject` at `0x14001a06f`
- `win32kbase!HMUnlockObject` at `0x14001a06f`
- `win32kbase!Win32AllocPoolZInit` at `0x14001a12a`
- `win32kbase!Win32AllocPoolZInit` at `0x14001a12a`
- `win32kbase!Win32FreePool` at `0x14001a0ed`
- `win32kbase!Win32FreePool` at `0x14001a0ed`
- `WIN32K!W32GetUserSessionState` at `0x140019e23`
- `WIN32K!W32GetUserSessionState` at `0x140019e41`
- `WIN32K!W32GetUserSessionState` at `0x140019ecd`
- `WIN32K!W32GetUserSessionState` at `0x140019ee4`
- `WIN32K!W32GetUserSessionState` at `0x140019f5c`
- `WIN32K!W32GetUserSessionState` at `0x140019f79`
- `WIN32K!W32GetUserSessionState` at `0x140019f88`
- `WIN32K!W32GetUserSessionState` at `0x140019e23`
- `WIN32K!W32GetUserSessionState` at `0x140019e41`
- `WIN32K!W32GetUserSessionState` at `0x140019ecd`
- `WIN32K!W32GetUserSessionState` at `0x140019ee4`
- `WIN32K!W32GetUserSessionState` at `0x140019f5c`
- `WIN32K!W32GetUserSessionState` at `0x140019f79`
- `WIN32K!W32GetUserSessionState` at `0x140019f88`

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
  __int64 v15; // rdx
  struct tagBWL *v16; // r12
  _QWORD *v17; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r13
  __int64 v37; // rbx
  _QWORD *i; // rsi
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 UserSessionState; // rdi
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdi
  __int64 v51; // r8
  ULONG_PTR *v52; // r14
  ULONG_PTR v53; // rbx
  ULONG_PTR v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  ULONG_PTR *v57; // rax
  ULONG_PTR v58; // r8
  ULONG_PTR *v59; // rcx
  __int64 v60; // rax
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
      v60 = Win32AllocPoolZInit(296, 1819767637);
      v11 = v60;
      if ( !v60 )
        return;
      *(_QWORD *)(v60 + 16) = v60 + 280;
    }
    *(_QWORD *)(v11 + 8) = v11 + 32;
    *(_QWORD *)(v11 + 24) = 0;
    v14 = InternalBuildHwndList((struct tagBWL *)v11, v8, 2u);
    v16 = v14;
    v17 = (_QWORD *)*((_QWORD *)v14 + 1);
    if ( (unsigned __int64)v17 >= *((_QWORD *)v14 + 2) )
    {
      Win32FreePool(v14);
    }
    else
    {
      *v17 = 1;
      CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v17, v15);
      if ( CurrentThreadWin32Thread )
        v20 = *CurrentThreadWin32Thread;
      else
        v20 = 0;
      *((_QWORD *)v16 + 3) = v20;
      v21 = (__int64 *)PsGetCurrentThreadWin32Thread(v20, v19);
      if ( v21 )
        v26 = *v21;
      else
        v26 = 0;
      *((_QWORD *)v16 + 3) = v26;
      v27 = *(_QWORD *)(W32GetUserSessionState(v23, v22, v24, v25) + 63008);
      *(_QWORD *)v16 = v27;
      *(_QWORD *)(W32GetUserSessionState(v27, v28, v29, v30) + 63008) = v16;
      v33 = (__int64 *)PsGetCurrentThreadWin32Thread(v32, v31);
      if ( v33 )
        v36 = *v33;
      else
        v36 = 0;
      v37 = *((_QWORD *)v16 + 4);
      for ( i = (_QWORD *)((char *)v16 + 32); v37 != 1; ++i )
      {
        if ( v37 )
        {
          PsGetCurrentThreadWin32Thread(v35, v34);
          v35 = *(_QWORD *)(W32GetUserSessionState(v40, v39, v41, v42) + 19704);
          if ( (unsigned __int64)(unsigned __int16)v37 < *(_QWORD *)(v35 + 8) )
          {
            UserSessionState = W32GetUserSessionState(v35, v34, v43, v44);
            v50 = *(_DWORD *)(W32GetUserSessionState(v47, v46, v48, v49) + 19728) * (unsigned int)(unsigned __int16)v37
                + *(_QWORD *)(UserSessionState + 19720);
            v52 = (ULONG_PTR *)HMPkheFromPhe(v50);
            LOWORD(v37) = WORD1(v37) & 0x7FFF;
            if ( ((WORD1(v37) & 0x7FFF) == *(_WORD *)(v50 + 26)
               || (_WORD)v37 == 0x7FFF
               || !(_WORD)v37 && PsGetCurrentProcessWow64Process(v35, v34, v51))
              && (*(_BYTE *)(v50 + 25) & 1) == 0
              && *(_BYTE *)(v50 + 24) == 1 )
            {
              v53 = *v52;
              if ( *v52 )
              {
                if ( (*(_BYTE *)(*(_QWORD *)(v53 + 40) + 31LL) & 0x40) == 0 || v36 == *(_QWORD *)(v53 + 16) )
                {
                  v54 = *v52;
                  BugCheckParameter3[0] = *(_QWORD *)(v36 + 448);
                  *(_QWORD *)(v36 + 448) = BugCheckParameter3;
                  BugCheckParameter3[1] = v53;
                  HMLockObject(v54);
                  xxxInternalDoSyncPaint(v53, a2);
                  v57 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v56, v55);
                  if ( v57 )
                    v58 = *v57;
                  else
                    v58 = 0;
                  v59 = *(ULONG_PTR **)(v58 + 448);
                  if ( v59 != BugCheckParameter3 )
                    KeBugCheckEx(0x164u, 0x3Bu, v58, (ULONG_PTR)BugCheckParameter3, 0);
                  *(_QWORD *)(v58 + 448) = *v59;
                  HMUnlockObject(v59[1]);
                }
              }
            }
          }
        }
        v37 = i[1];
      }
      FreeHwndList(v16);
    }
  }
}

```

## disassembly

```asm
0x140019de0  push    rbx
0x140019de2  push    r15
0x140019de4  sub     rsp, 58h
0x140019de8  mov     r15d, edx
0x140019deb  mov     rbx, rcx
0x140019dee  call    xxxSimpleDoSyncPaint
0x140019df3  test    r15b, 20h
0x140019df7  jnz     short loc_140019E12
0x140019df9  test    r15b, 4
0x140019dfd  jz      short loc_140019E09
0x140019dff  mov     rax, [rbx+28h]
0x140019e03  test    byte ptr [rax+1Fh], 2
0x140019e07  jnz     short loc_140019E12
0x140019e09  add     rsp, 58h
0x140019e0d  pop     r15
0x140019e0f  pop     rbx
0x140019e10  retn
0x140019e12  mov     [rsp+68h+arg_8], rsi
0x140019e17  mov     [rsp+68h+arg_10], rdi
0x140019e1f  mov     rdi, [rbx+70h]
0x140019e23  call    cs:__imp_W32GetUserSessionState
0x140019e2a  nop     dword ptr [rax+rax+00h]
0x140019e2f  xor     esi, esi
0x140019e31  mov     rbx, [rax+0F6E0h]
0x140019e38  test    rbx, rbx
0x140019e3b  jz      loc_14001A120
0x140019e41  call    cs:__imp_W32GetUserSessionState
0x140019e48  nop     dword ptr [rax+rax+00h]
0x140019e4d  mov     [rax+0F6E0h], rsi
0x140019e54  lea     rcx, [rbx+20h]
0x140019e58  mov     [rsp+68h+var_18], r12
0x140019e5d  mov     [rbx+8], rcx
0x140019e61  mov     r8d, 2; unsigned int
0x140019e67  mov     rcx, rbx; struct tagBWL *
0x140019e6a  mov     [rbx+18h], rsi
0x140019e6e  mov     rdx, rdi; struct tagWND *
0x140019e71  call    ?InternalBuildHwndList@@YAPEAUtagBWL@@PEAU1@PEAUtagWND@@I@Z; InternalBuildHwndList(tagBWL *,tagWND *,uint)
0x140019e76  mov     r12, rax
0x140019e79  mov     rcx, [rax+8]
0x140019e7d  cmp     rcx, [rax+10h]
0x140019e81  jnb     loc_14001A0EA
0x140019e87  mov     qword ptr [rcx], 1
0x140019e8e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140019e95  nop     dword ptr [rax+rax+00h]
0x140019e9a  test    rax, rax
0x140019e9d  jz      loc_14001A162
0x140019ea3  mov     rcx, [rax]
0x140019ea6  mov     [r12+18h], rcx
0x140019eab  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140019eb2  nop     dword ptr [rax+rax+00h]
0x140019eb7  test    rax, rax
0x140019eba  jz      loc_14001A16A
0x140019ec0  mov     rax, [rax]
0x140019ec3  mov     [rsp+68h+var_20], r13
0x140019ec8  mov     [r12+18h], rax
0x140019ecd  call    cs:__imp_W32GetUserSessionState
0x140019ed4  nop     dword ptr [rax+rax+00h]
0x140019ed9  mov     rcx, [rax+0F620h]
0x140019ee0  mov     [r12], rcx
0x140019ee4  call    cs:__imp_W32GetUserSessionState
0x140019eeb  nop     dword ptr [rax+rax+00h]
0x140019ef0  mov     [rax+0F620h], r12
0x140019ef7  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140019efe  nop     dword ptr [rax+rax+00h]
0x140019f03  test    rax, rax
0x140019f06  jz      loc_14001A15A
0x140019f0c  mov     r13, [rax]
0x140019f0f  mov     rbx, [r12+20h]
0x140019f14  lea     rsi, [r12+20h]
0x140019f19  mov     [rsp+68h+arg_0], rbp
0x140019f1e  mov     [rsp+68h+var_28], r14
0x140019f23  cmp     rbx, 1
0x140019f27  jz      loc_14001A08D
0x140019f2d  nop     dword ptr [rax]
0x140019f30  test    rbx, rbx
0x140019f33  jz      loc_14001A07B
0x140019f39  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140019f40  nop     dword ptr [rax+rax+00h]
0x140019f45  test    rax, rax
0x140019f48  jz      short loc_140019F59
0x140019f4a  mov     rax, [rax]
0x140019f4d  test    rax, rax
0x140019f50  jz      short loc_140019F59
0x140019f52  mov     rax, [rax+200h]
0x140019f59  movzx   ebp, bx
0x140019f5c  call    cs:__imp_W32GetUserSessionState
0x140019f63  nop     dword ptr [rax+rax+00h]
0x140019f68  mov     rcx, [rax+4CF8h]
0x140019f6f  cmp     rbp, [rcx+8]
0x140019f73  jnb     loc_14001A07B
0x140019f79  call    cs:__imp_W32GetUserSessionState
0x140019f80  nop     dword ptr [rax+rax+00h]
0x140019f85  mov     rdi, rax
0x140019f88  call    cs:__imp_W32GetUserSessionState
0x140019f8f  nop     dword ptr [rax+rax+00h]
0x140019f94  mov     rdi, [rdi+4D08h]
0x140019f9b  imul    ebp, [rax+4D10h]
0x140019fa2  mov     ecx, ebp
0x140019fa4  add     rdi, rcx
0x140019fa7  mov     rcx, rdi
0x140019faa  call    cs:__imp_HMPkheFromPhe
0x140019fb1  nop     dword ptr [rax+rax+00h]
0x140019fb6  shr     rbx, 10h
0x140019fba  mov     r14, rax
0x140019fbd  mov     eax, 7FFFh
0x140019fc2  and     bx, ax
0x140019fc5  cmp     bx, [rdi+1Ah]
0x140019fc9  jnz     loc_14001A0C6
0x140019fcf  test    byte ptr [rdi+19h], 1
0x140019fd3  jnz     loc_14001A07B
0x140019fd9  cmp     byte ptr [rdi+18h], 1
0x140019fdd  jnz     loc_14001A07B
0x140019fe3  mov     rbx, [r14]
0x140019fe6  test    rbx, rbx
0x140019fe9  jz      loc_14001A07B
0x140019fef  mov     rax, [rbx+28h]
0x140019ff3  test    byte ptr [rax+1Fh], 40h
0x140019ff7  jnz     loc_14001A0BB
0x140019ffd  mov     rax, [r13+1C0h]
0x14001a004  mov     rcx, rbx
0x14001a007  mov     [rsp+68h+BugCheckParameter3], rax
0x14001a00c  lea     rax, [rsp+68h+BugCheckParameter3]
0x14001a011  mov     [r13+1C0h], rax
0x14001a018  mov     [rsp+68h+var_30], rbx
0x14001a01d  call    cs:__imp_HMLockObject
0x14001a024  nop     dword ptr [rax+rax+00h]
0x14001a029  mov     edx, r15d
0x14001a02c  mov     rcx, rbx
0x14001a02f  call    xxxInternalDoSyncPaint
0x14001a034  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001a03b  nop     dword ptr [rax+rax+00h]
0x14001a040  test    rax, rax
0x14001a043  jz      loc_14001A152
0x14001a049  mov     r8, [rax]; BugCheckParameter2
0x14001a04c  mov     rcx, [r8+1C0h]
0x14001a053  lea     rax, [rsp+68h+BugCheckParameter3]
0x14001a058  cmp     rcx, rax
0x14001a05b  jnz     loc_14001A0FB
0x14001a061  mov     rax, [rcx]
0x14001a064  mov     [r8+1C0h], rax
0x14001a06b  mov     rcx, [rcx+8]
0x14001a06f  call    cs:__imp_HMUnlockObject
0x14001a076  nop     dword ptr [rax+rax+00h]
0x14001a07b  mov     rbx, [rsi+8]
0x14001a07f  add     rsi, 8
0x14001a083  cmp     rbx, 1
0x14001a087  jnz     loc_140019F30
0x14001a08d  mov     rcx, r12
0x14001a090  call    FreeHwndList
0x14001a095  mov     rbp, [rsp+68h+arg_0]
0x14001a09a  mov     r14, [rsp+68h+var_28]
0x14001a09f  mov     r13, [rsp+68h+var_20]
0x14001a0a4  mov     r12, [rsp+68h+var_18]
0x14001a0a9  mov     rsi, [rsp+68h+arg_8]
0x14001a0ae  mov     rdi, [rsp+68h+arg_10]
0x14001a0b6  jmp     loc_140019E09
0x14001a0bb  cmp     r13, [rbx+10h]
0x14001a0bf  jnz     short loc_14001A07B
0x14001a0c1  jmp     loc_140019FFD
0x14001a0c6  cmp     bx, ax
0x14001a0c9  jz      loc_140019FCF
0x14001a0cf  test    bx, bx
0x14001a0d2  jnz     short loc_14001A07B
0x14001a0d4  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14001a0db  nop     dword ptr [rax+rax+00h]
0x14001a0e0  test    rax, rax
0x14001a0e3  jz      short loc_14001A07B
0x14001a0e5  jmp     loc_140019FCF
0x14001a0ea  mov     rcx, r12
0x14001a0ed  call    cs:__imp_Win32FreePool
0x14001a0f4  nop     dword ptr [rax+rax+00h]
0x14001a0f9  jmp     short loc_14001A0A4
0x14001a0fb  lea     r9, [rsp+68h+BugCheckParameter3]; BugCheckParameter3
0x14001a100  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x14001a109  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14001a10e  mov     ecx, 164h; BugCheckCode
0x14001a113  call    cs:__imp_KeBugCheckEx
0x14001a120  mov     edx, 6C777355h
0x14001a125  mov     ecx, 128h
0x14001a12a  call    cs:__imp_Win32AllocPoolZInit
0x14001a131  nop     dword ptr [rax+rax+00h]
0x14001a136  mov     rbx, rax
0x14001a139  test    rax, rax
0x14001a13c  jz      loc_14001A0A9
0x14001a142  lea     rcx, [rax+118h]
0x14001a149  mov     [rax+10h], rcx
0x14001a14d  jmp     loc_140019E54
0x14001a152  xor     r8d, r8d
0x14001a155  jmp     loc_14001A04C
0x14001a15a  mov     r13, rsi
0x14001a15d  jmp     loc_140019F0F
0x14001a162  mov     rcx, rsi
0x14001a165  jmp     loc_140019EA6
0x14001a16a  mov     rax, rsi
0x14001a16d  jmp     loc_140019EC3
```
