# xxxWindowFromPoint

- ea: `0x14000d2fc`
- end: `0x14000d615`
- name: `xxxWindowFromPoint`
- size: `793`
- prototype: `struct tagWND *__fastcall(struct tagPOINT, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000d260`
- `0x14000d2b0`

## callees

- `0x14000d2fc`
- `0x14000d61c`
- `0x14000d74c`
- `0x14000e388`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14000d57c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14000d57c`
- `ntoskrnl!KeBugCheckEx` at `0x14000d5c5`
- `ntoskrnl!KeBugCheckEx` at `0x14000d5e8`
- `ntoskrnl!KeBugCheckEx` at `0x14000d5c5`
- `ntoskrnl!KeBugCheckEx` at `0x14000d5e8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d313`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d354`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d3b0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d41c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d467`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d4b5`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d313`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d354`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d3b0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d41c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d467`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14000d4b5`
- `win32kbase!HMPkheFromPhe` at `0x14000d525`
- `win32kbase!HMPkheFromPhe` at `0x14000d525`
- `win32kbase!IsWindowDesktopComposed` at `0x14000d398`
- `win32kbase!IsWindowDesktopComposed` at `0x14000d398`
- `win32kbase!HMLockObject` at `0x14000d389`
- `win32kbase!HMLockObject` at `0x14000d3ea`
- `win32kbase!HMLockObject` at `0x14000d389`
- `win32kbase!HMLockObject` at `0x14000d3ea`
- `win32kbase!HMUnlockObject` at `0x14000d45b`
- `win32kbase!HMUnlockObject` at `0x14000d4a6`
- `win32kbase!HMUnlockObject` at `0x14000d45b`
- `win32kbase!HMUnlockObject` at `0x14000d4a6`
- `WIN32K!W32GetUserSessionState` at `0x14000d4d9`
- `WIN32K!W32GetUserSessionState` at `0x14000d4f2`
- `WIN32K!W32GetUserSessionState` at `0x14000d501`
- `WIN32K!W32GetUserSessionState` at `0x14000d4d9`
- `WIN32K!W32GetUserSessionState` at `0x14000d4f2`
- `WIN32K!W32GetUserSessionState` at `0x14000d501`

## pseudocode

```c
struct tagWND *__fastcall xxxWindowFromPoint(struct tagPOINT a1, __int64 a2)
{
  __int64 *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi
  ULONG_PTR v8; // rdi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  ULONG_PTR v16; // rsi
  __int64 *v17; // rax
  __int64 v18; // rcx
  int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // rcx
  ULONG_PTR *v22; // rax
  ULONG_PTR v23; // rcx
  ULONG_PTR *v24; // rdx
  ULONG_PTR v25; // rcx
  ULONG_PTR *v26; // rax
  ULONG_PTR v27; // rcx
  ULONG_PTR *v28; // rdx
  ULONG_PTR v29; // rcx
  struct tagWND *v30; // rsi
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 UserSessionState; // rbx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  struct tagWND **v48; // r14
  ULONG_PTR v50[2]; // [rsp+40h] [rbp-28h] BYREF
  ULONG_PTR BugCheckParameter3[3]; // [rsp+50h] [rbp-18h] BYREF
  struct tagPOINT v52; // [rsp+A0h] [rbp+38h] BYREF

  v52 = a1;
  v3 = (__int64 *)((__int64 (__fastcall *)(_QWORD, _QWORD))PsGetCurrentThreadWin32Thread)(a1, a2);
  if ( !v3 )
    return 0;
  v6 = *v3;
  if ( !v6 )
    return 0;
  v7 = *(_QWORD *)(v6 + 496);
  if ( !v7 )
    return 0;
  v8 = *(_QWORD *)(v7 + 24);
  if ( !v8 )
    return 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v5, v4);
  if ( CurrentThreadWin32Thread )
    v10 = *CurrentThreadWin32Thread;
  else
    v10 = 0;
  BugCheckParameter3[0] = *(_QWORD *)(v10 + 448);
  *(_QWORD *)(v10 + 448) = BugCheckParameter3;
  BugCheckParameter3[1] = v8;
  HMLockObject(v8);
  if ( (unsigned int)IsWindowDesktopComposed(v8, v11, v12, v13) )
  {
    v16 = *(_QWORD *)(v8 + 112);
    v17 = (__int64 *)PsGetCurrentThreadWin32Thread(v15, v14);
    if ( v17 )
      v18 = *v17;
    else
      v18 = 0;
    v50[0] = *(_QWORD *)(v18 + 448);
    *(_QWORD *)(v18 + 448) = v50;
    v50[1] = v16;
    if ( v16 )
      HMLockObject(v16);
    v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))xxxDCEWindowHitTest)(
            *(_QWORD *)(v8 + 112),
            0,
            0,
            0,
            a1,
            0,
            3);
    v22 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v21, v20);
    if ( v22 )
      v23 = *v22;
    else
      v23 = 0;
    v24 = *(ULONG_PTR **)(v23 + 448);
    if ( v24 != v50 )
      KeBugCheckEx(0x164u, 0x3Bu, v23, (ULONG_PTR)v50, 0);
    *(_QWORD *)(v23 + 448) = *v24;
    v25 = v24[1];
    if ( v25 )
      HMUnlockObject(v25);
  }
  else
  {
    v19 = xxxWindowHitTest2(v8, a1, 0, 1);
  }
  v26 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v25, v24);
  if ( v26 )
    v27 = *v26;
  else
    v27 = 0;
  v28 = *(ULONG_PTR **)(v27 + 448);
  if ( v28 != BugCheckParameter3 )
    KeBugCheckEx(0x164u, 0x3Bu, v27, (ULONG_PTR)BugCheckParameter3, 0);
  *(_QWORD *)(v27 + 448) = *v28;
  v29 = v28[1];
  if ( v29 )
    HMUnlockObject(v29);
  v30 = 0;
  PsGetCurrentThreadWin32Thread(v29, v28);
  v36 = *(_QWORD *)(W32GetUserSessionState(v32, v31, v33, v34) + 19704);
  if ( (unsigned __int64)(unsigned __int16)v19 < *(_QWORD *)(v36 + 8) )
  {
    UserSessionState = W32GetUserSessionState(v36, v35, v37, v38);
    v44 = *(_DWORD *)(W32GetUserSessionState(v41, v40, v42, v43) + 19728) * (unsigned int)(unsigned __int16)v19
        + *(_QWORD *)(UserSessionState + 19720);
    v48 = (struct tagWND **)HMPkheFromPhe(v44);
    LOWORD(v19) = HIWORD(v19) & 0x7FFF;
    if ( ((HIWORD(v19) & 0x7FFF) == *(_WORD *)(v44 + 26)
       || (_WORD)v19 == 0x7FFF
       || !(_WORD)v19 && PsGetCurrentProcessWow64Process(v46, v45, v47))
      && (*(_BYTE *)(v44 + 25) & 1) == 0
      && *(_BYTE *)(v44 + 24) == 1 )
    {
      v30 = *v48;
    }
  }
  InputTraceLogging::Win32k::WindowFromPoint(&v52, v30);
  return v30;
}

```

## disassembly

```asm
0x14000d2fc  mov     qword ptr [rsp-30h+arg_0.x], rcx
0x14000d301  push    rbp
0x14000d302  push    rbx
0x14000d303  push    rsi
0x14000d304  push    rdi
0x14000d305  push    r14
0x14000d307  push    r15
0x14000d309  mov     rbp, rsp
0x14000d30c  sub     rsp, 68h
0x14000d310  mov     rbx, rcx
0x14000d313  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14000d31a  nop     dword ptr [rax+rax+00h]
0x14000d31f  xor     r15d, r15d
0x14000d322  test    rax, rax
0x14000d325  jz      loc_14000D58F
0x14000d32b  mov     rax, [rax]
0x14000d32e  test    rax, rax
0x14000d331  jz      loc_14000D58F
0x14000d337  mov     rdi, [rax+1F0h]
0x14000d33e  test    rdi, rdi
0x14000d341  jz      loc_14000D58F
0x14000d347  mov     rdi, [rdi+18h]
0x14000d34b  test    rdi, rdi
0x14000d34e  jz      loc_14000D58F
0x14000d354  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14000d35b  nop     dword ptr [rax+rax+00h]
0x14000d360  test    rax, rax
0x14000d363  jz      loc_14000D5F5
0x14000d369  mov     rcx, [rax]
0x14000d36c  mov     rax, [rcx+1C0h]
0x14000d373  mov     [rbp+BugCheckParameter3], rax
0x14000d377  lea     rax, [rbp+BugCheckParameter3]
0x14000d37b  mov     [rcx+1C0h], rax
0x14000d382  mov     rcx, rdi
0x14000d385  mov     [rbp+var_10], rdi
0x14000d389  call    cs:__imp_HMLockObject
0x14000d390  nop     dword ptr [rax+rax+00h]
0x14000d395  mov     rcx, rdi
0x14000d398  call    cs:__imp_IsWindowDesktopComposed
0x14000d39f  nop     dword ptr [rax+rax+00h]
0x14000d3a4  test    eax, eax
0x14000d3a6  jz      loc_14000D593
0x14000d3ac  mov     rsi, [rdi+70h]
0x14000d3b0  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14000d3b7  nop     dword ptr [rax+rax+00h]
0x14000d3bc  test    rax, rax
0x14000d3bf  jz      loc_14000D5FD
0x14000d3c5  mov     rcx, [rax]
0x14000d3c8  mov     rax, [rcx+1C0h]
0x14000d3cf  mov     [rbp+var_28], rax
0x14000d3d3  lea     rax, [rbp+var_28]
0x14000d3d7  mov     [rcx+1C0h], rax
0x14000d3de  mov     [rbp+var_20], rsi
0x14000d3e2  test    rsi, rsi
0x14000d3e5  jz      short loc_14000D3F6
0x14000d3e7  mov     rcx, rsi
0x14000d3ea  call    cs:__imp_HMLockObject
0x14000d3f1  nop     dword ptr [rax+rax+00h]
0x14000d3f6  mov     rcx, [rdi+70h]
0x14000d3fa  xor     r9d, r9d
0x14000d3fd  mov     [rsp+68h+var_38], 3
0x14000d405  xor     r8d, r8d
0x14000d408  mov     [rsp+68h+var_40], r15
0x14000d40d  xor     edx, edx
0x14000d40f  mov     [rsp+68h+BugCheckParameter4], rbx
0x14000d414  call    ?xxxDCEWindowHitTest@@YAPEAUHWND__@@PEAUtagWND@@I_K_JUtagPOINT@@PEAHW4WindowHitTestOption@@@Z; xxxDCEWindowHitTest(tagWND *,uint,unsigned __int64,__int64,tagPOINT,int *,WindowHitTestOption)
0x14000d419  mov     rdi, rax
0x14000d41c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14000d423  nop     dword ptr [rax+rax+00h]
0x14000d428  test    rax, rax
0x14000d42b  jz      loc_14000D605
0x14000d431  mov     rcx, [rax]
0x14000d434  mov     rdx, [rcx+1C0h]
0x14000d43b  lea     rax, [rbp+var_28]
0x14000d43f  cmp     rdx, rax
0x14000d442  jnz     loc_14000D5D2
0x14000d448  mov     rax, [rdx]
0x14000d44b  mov     [rcx+1C0h], rax
0x14000d452  mov     rcx, [rdx+8]
0x14000d456  test    rcx, rcx
0x14000d459  jz      short loc_14000D467
0x14000d45b  call    cs:__imp_HMUnlockObject
0x14000d462  nop     dword ptr [rax+rax+00h]
0x14000d467  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14000d46e  nop     dword ptr [rax+rax+00h]
0x14000d473  test    rax, rax
0x14000d476  jz      loc_14000D60D
0x14000d47c  mov     rcx, [rax]
0x14000d47f  mov     rdx, [rcx+1C0h]
0x14000d486  lea     rax, [rbp+BugCheckParameter3]
0x14000d48a  cmp     rdx, rax
0x14000d48d  jnz     loc_14000D5AF
0x14000d493  mov     rax, [rdx]
0x14000d496  mov     [rcx+1C0h], rax
0x14000d49d  mov     rcx, [rdx+8]
0x14000d4a1  test    rcx, rcx
0x14000d4a4  jz      short loc_14000D4B2
0x14000d4a6  call    cs:__imp_HMUnlockObject
0x14000d4ad  nop     dword ptr [rax+rax+00h]
0x14000d4b2  mov     rsi, r15
0x14000d4b5  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14000d4bc  nop     dword ptr [rax+rax+00h]
0x14000d4c1  test    rax, rax
0x14000d4c4  jz      short loc_14000D4D5
0x14000d4c6  mov     rax, [rax]
0x14000d4c9  test    rax, rax
0x14000d4cc  jz      short loc_14000D4D5
0x14000d4ce  mov     rax, [rax+200h]
0x14000d4d5  movzx   r14d, di
0x14000d4d9  call    cs:__imp_W32GetUserSessionState
0x14000d4e0  nop     dword ptr [rax+rax+00h]
0x14000d4e5  mov     rcx, [rax+4CF8h]
0x14000d4ec  cmp     r14, [rcx+8]
0x14000d4f0  jnb     short loc_14000D555
0x14000d4f2  call    cs:__imp_W32GetUserSessionState
0x14000d4f9  nop     dword ptr [rax+rax+00h]
0x14000d4fe  mov     rbx, rax
0x14000d501  call    cs:__imp_W32GetUserSessionState
0x14000d508  nop     dword ptr [rax+rax+00h]
0x14000d50d  mov     rbx, [rbx+4D08h]
0x14000d514  imul    r14d, [rax+4D10h]
0x14000d51c  mov     ecx, r14d
0x14000d51f  add     rbx, rcx
0x14000d522  mov     rcx, rbx
0x14000d525  call    cs:__imp_HMPkheFromPhe
0x14000d52c  nop     dword ptr [rax+rax+00h]
0x14000d531  shr     rdi, 10h
0x14000d535  mov     r14, rax
0x14000d538  mov     eax, 7FFFh
0x14000d53d  and     di, ax
0x14000d540  cmp     di, [rbx+1Ah]
0x14000d544  jnz     short loc_14000D572
0x14000d546  test    byte ptr [rbx+19h], 1
0x14000d54a  jnz     short loc_14000D555
0x14000d54c  cmp     byte ptr [rbx+18h], 1
0x14000d550  jnz     short loc_14000D555
0x14000d552  mov     rsi, [r14]
0x14000d555  mov     rdx, rsi; struct tagWND *
0x14000d558  lea     rcx, [rbp+arg_0]; struct tagPOINT *
0x14000d55c  call    ?WindowFromPoint@Win32k@InputTraceLogging@@SAXAEBUtagPOINT@@PEAUtagWND@@@Z; InputTraceLogging::Win32k::WindowFromPoint(tagPOINT const &,tagWND *)
0x14000d561  mov     rax, rsi
0x14000d564  add     rsp, 68h
0x14000d568  pop     r15
0x14000d56a  pop     r14
0x14000d56c  pop     rdi
0x14000d56d  pop     rsi
0x14000d56e  pop     rbx
0x14000d56f  pop     rbp
0x14000d570  retn
0x14000d572  cmp     di, ax
0x14000d575  jz      short loc_14000D546
0x14000d577  test    di, di
0x14000d57a  jnz     short loc_14000D555
0x14000d57c  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14000d583  nop     dword ptr [rax+rax+00h]
0x14000d588  test    rax, rax
0x14000d58b  jz      short loc_14000D555
0x14000d58d  jmp     short loc_14000D546
0x14000d58f  xor     eax, eax
0x14000d591  jmp     short loc_14000D564
0x14000d593  mov     r9d, 1
0x14000d599  xor     r8d, r8d
0x14000d59c  mov     rdx, rbx
0x14000d59f  mov     rcx, rdi
0x14000d5a2  call    ?xxxWindowHitTest2@@YAPEAUHWND__@@PEAUtagWND@@UtagPOINT@@PEAHW4WindowHitTestOption@@@Z; xxxWindowHitTest2(tagWND *,tagPOINT,int *,WindowHitTestOption)
0x14000d5a7  mov     rdi, rax
0x14000d5aa  jmp     loc_14000D467
0x14000d5af  mov     r8, rcx; BugCheckParameter2
0x14000d5b2  mov     [rsp+68h+BugCheckParameter4], r15; BugCheckParameter4
0x14000d5b7  mov     ecx, 164h; BugCheckCode
0x14000d5bc  lea     r9, [rbp+BugCheckParameter3]; BugCheckParameter3
0x14000d5c0  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14000d5c5  call    cs:__imp_KeBugCheckEx
0x14000d5d2  mov     r8, rcx; BugCheckParameter2
0x14000d5d5  mov     [rsp+68h+BugCheckParameter4], r15; BugCheckParameter4
0x14000d5da  mov     ecx, 164h; BugCheckCode
0x14000d5df  lea     r9, [rbp+var_28]; BugCheckParameter3
0x14000d5e3  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x14000d5e8  call    cs:__imp_KeBugCheckEx
0x14000d5f5  mov     rcx, r15
0x14000d5f8  jmp     loc_14000D36C
0x14000d5fd  mov     rcx, r15
0x14000d600  jmp     loc_14000D3C8
0x14000d605  mov     rcx, r15
0x14000d608  jmp     loc_14000D434
0x14000d60d  mov     rcx, r15
0x14000d610  jmp     loc_14000D47F
```
