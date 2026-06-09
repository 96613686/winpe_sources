# xxxWindowFromPoint

- ea: `0x14018752c`
- end: `0x140187845`
- name: `xxxWindowFromPoint`
- size: `793`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140187490`
- `0x1401874e0`

## callees

- `0x14018752c`
- `0x14018784c`
- `0x14018797c`
- `0x1401885b8`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401877ac`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401877ac`
- `ntoskrnl!KeBugCheckEx` at `0x1401877f5`
- `ntoskrnl!KeBugCheckEx` at `0x140187818`
- `ntoskrnl!KeBugCheckEx` at `0x1401877f5`
- `ntoskrnl!KeBugCheckEx` at `0x140187818`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140187543`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140187584`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401875e0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14018764c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140187697`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401876e5`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140187543`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140187584`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401875e0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14018764c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140187697`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401876e5`
- `win32kbase!HMPkheFromPhe` at `0x140187755`
- `win32kbase!HMPkheFromPhe` at `0x140187755`
- `win32kbase!IsWindowDesktopComposed` at `0x1401875c8`
- `win32kbase!IsWindowDesktopComposed` at `0x1401875c8`
- `win32kbase!HMLockObject` at `0x1401875b9`
- `win32kbase!HMLockObject` at `0x14018761a`
- `win32kbase!HMLockObject` at `0x1401875b9`
- `win32kbase!HMLockObject` at `0x14018761a`
- `win32kbase!HMUnlockObject` at `0x14018768b`
- `win32kbase!HMUnlockObject` at `0x1401876d6`
- `win32kbase!HMUnlockObject` at `0x14018768b`
- `win32kbase!HMUnlockObject` at `0x1401876d6`
- `WIN32K!W32GetUserSessionState` at `0x140187709`
- `WIN32K!W32GetUserSessionState` at `0x140187722`
- `WIN32K!W32GetUserSessionState` at `0x140187731`
- `WIN32K!W32GetUserSessionState` at `0x140187709`
- `WIN32K!W32GetUserSessionState` at `0x140187722`
- `WIN32K!W32GetUserSessionState` at `0x140187731`

## pseudocode

```c
struct tagWND *__fastcall xxxWindowFromPoint(struct tagPOINT a1)
{
  __int64 *v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rdi
  ULONG_PTR v6; // rdi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  ULONG_PTR v10; // rsi
  __int64 *v11; // rax
  __int64 v12; // rcx
  int v13; // edi
  __int64 v14; // rcx
  ULONG_PTR *v15; // rax
  ULONG_PTR v16; // rcx
  ULONG_PTR *v17; // rdx
  ULONG_PTR v18; // rcx
  ULONG_PTR *v19; // rax
  ULONG_PTR v20; // rcx
  ULONG_PTR *v21; // rdx
  ULONG_PTR v22; // rcx
  struct tagWND *v23; // rsi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 UserSessionState; // rbx
  __int64 v27; // rcx
  __int64 v28; // rbx
  struct tagWND **v29; // r14
  ULONG_PTR v31[2]; // [rsp+40h] [rbp-28h] BYREF
  ULONG_PTR BugCheckParameter3[3]; // [rsp+50h] [rbp-18h] BYREF
  struct tagPOINT v33; // [rsp+A0h] [rbp+38h] BYREF

  v33 = a1;
  v2 = (__int64 *)((__int64 (__fastcall *)(_QWORD))PsGetCurrentThreadWin32Thread)(a1);
  if ( !v2 )
    return 0;
  v4 = *v2;
  if ( !v4 )
    return 0;
  v5 = *(_QWORD *)(v4 + 496);
  if ( !v5 )
    return 0;
  v6 = *(_QWORD *)(v5 + 24);
  if ( !v6 )
    return 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v3);
  if ( CurrentThreadWin32Thread )
    v8 = *CurrentThreadWin32Thread;
  else
    v8 = 0;
  BugCheckParameter3[0] = *(_QWORD *)(v8 + 448);
  *(_QWORD *)(v8 + 448) = BugCheckParameter3;
  BugCheckParameter3[1] = v6;
  HMLockObject(v6);
  if ( (unsigned int)IsWindowDesktopComposed(v6) )
  {
    v10 = *(_QWORD *)(v6 + 112);
    v11 = (__int64 *)PsGetCurrentThreadWin32Thread(v9);
    if ( v11 )
      v12 = *v11;
    else
      v12 = 0;
    v31[0] = *(_QWORD *)(v12 + 448);
    *(_QWORD *)(v12 + 448) = v31;
    v31[1] = v10;
    if ( v10 )
      HMLockObject(v10);
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))xxxDCEWindowHitTest)(
            *(_QWORD *)(v6 + 112),
            0,
            0,
            0,
            a1,
            0,
            3);
    v15 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v14);
    if ( v15 )
      v16 = *v15;
    else
      v16 = 0;
    v17 = *(ULONG_PTR **)(v16 + 448);
    if ( v17 != v31 )
      KeBugCheckEx(0x164u, 0x3Bu, v16, (ULONG_PTR)v31, 0);
    *(_QWORD *)(v16 + 448) = *v17;
    v18 = v17[1];
    if ( v18 )
      HMUnlockObject();
  }
  else
  {
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))xxxWindowHitTest2)(v6, a1, 0, 1);
  }
  v19 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v18);
  if ( v19 )
    v20 = *v19;
  else
    v20 = 0;
  v21 = *(ULONG_PTR **)(v20 + 448);
  if ( v21 != BugCheckParameter3 )
    KeBugCheckEx(0x164u, 0x3Bu, v20, (ULONG_PTR)BugCheckParameter3, 0);
  *(_QWORD *)(v20 + 448) = *v21;
  v22 = v21[1];
  if ( v22 )
    HMUnlockObject();
  v23 = 0;
  PsGetCurrentThreadWin32Thread(v22);
  v25 = *(_QWORD *)(W32GetUserSessionState(v24) + 19704);
  if ( (unsigned __int64)(unsigned __int16)v13 < *(_QWORD *)(v25 + 8) )
  {
    UserSessionState = W32GetUserSessionState(v25);
    v28 = *(_DWORD *)(W32GetUserSessionState(v27) + 19728) * (unsigned int)(unsigned __int16)v13
        + *(_QWORD *)(UserSessionState + 19720);
    v29 = (struct tagWND **)HMPkheFromPhe(v28);
    LOWORD(v13) = HIWORD(v13) & 0x7FFF;
    if ( ((HIWORD(v13) & 0x7FFF) == *(_WORD *)(v28 + 26)
       || (_WORD)v13 == 0x7FFF
       || !(_WORD)v13 && PsGetCurrentProcessWow64Process())
      && (*(_BYTE *)(v28 + 25) & 1) == 0
      && *(_BYTE *)(v28 + 24) == 1 )
    {
      v23 = *v29;
    }
  }
  InputTraceLogging::Win32k::WindowFromPoint(&v33, v23);
  return v23;
}

```

## disassembly

```asm
0x14018752c  mov     qword ptr [rsp-30h+arg_0.x], rcx
0x140187531  push    rbp
0x140187532  push    rbx
0x140187533  push    rsi
0x140187534  push    rdi
0x140187535  push    r14
0x140187537  push    r15
0x140187539  mov     rbp, rsp
0x14018753c  sub     rsp, 68h
0x140187540  mov     rbx, rcx
0x140187543  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14018754a  nop     dword ptr [rax+rax+00h]
0x14018754f  xor     r15d, r15d
0x140187552  test    rax, rax
0x140187555  jz      loc_1401877BF
0x14018755b  mov     rax, [rax]
0x14018755e  test    rax, rax
0x140187561  jz      loc_1401877BF
0x140187567  mov     rdi, [rax+1F0h]
0x14018756e  test    rdi, rdi
0x140187571  jz      loc_1401877BF
0x140187577  mov     rdi, [rdi+18h]
0x14018757b  test    rdi, rdi
0x14018757e  jz      loc_1401877BF
0x140187584  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14018758b  nop     dword ptr [rax+rax+00h]
0x140187590  test    rax, rax
0x140187593  jz      loc_140187825
0x140187599  mov     rcx, [rax]
0x14018759c  mov     rax, [rcx+1C0h]
0x1401875a3  mov     [rbp+BugCheckParameter3], rax
0x1401875a7  lea     rax, [rbp+BugCheckParameter3]
0x1401875ab  mov     [rcx+1C0h], rax
0x1401875b2  mov     rcx, rdi
0x1401875b5  mov     [rbp+var_10], rdi
0x1401875b9  call    cs:__imp_HMLockObject
0x1401875c0  nop     dword ptr [rax+rax+00h]
0x1401875c5  mov     rcx, rdi
0x1401875c8  call    cs:__imp_IsWindowDesktopComposed
0x1401875cf  nop     dword ptr [rax+rax+00h]
0x1401875d4  test    eax, eax
0x1401875d6  jz      loc_1401877C3
0x1401875dc  mov     rsi, [rdi+70h]
0x1401875e0  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1401875e7  nop     dword ptr [rax+rax+00h]
0x1401875ec  test    rax, rax
0x1401875ef  jz      loc_14018782D
0x1401875f5  mov     rcx, [rax]
0x1401875f8  mov     rax, [rcx+1C0h]
0x1401875ff  mov     [rbp+var_28], rax
0x140187603  lea     rax, [rbp+var_28]
0x140187607  mov     [rcx+1C0h], rax
0x14018760e  mov     [rbp+var_20], rsi
0x140187612  test    rsi, rsi
0x140187615  jz      short loc_140187626
0x140187617  mov     rcx, rsi
0x14018761a  call    cs:__imp_HMLockObject
0x140187621  nop     dword ptr [rax+rax+00h]
0x140187626  mov     rcx, [rdi+70h]
0x14018762a  xor     r9d, r9d
0x14018762d  mov     [rsp+68h+var_38], 3
0x140187635  xor     r8d, r8d
0x140187638  mov     [rsp+68h+var_40], r15
0x14018763d  xor     edx, edx
0x14018763f  mov     [rsp+68h+BugCheckParameter4], rbx
0x140187644  call    ?xxxDCEWindowHitTest@@YAPEAUHWND__@@PEAUtagWND@@I_K_JUtagPOINT@@PEAHW4WindowHitTestOption@@@Z; xxxDCEWindowHitTest(tagWND *,uint,unsigned __int64,__int64,tagPOINT,int *,WindowHitTestOption)
0x140187649  mov     rdi, rax
0x14018764c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140187653  nop     dword ptr [rax+rax+00h]
0x140187658  test    rax, rax
0x14018765b  jz      loc_140187835
0x140187661  mov     rcx, [rax]
0x140187664  mov     rdx, [rcx+1C0h]
0x14018766b  lea     rax, [rbp+var_28]
0x14018766f  cmp     rdx, rax
0x140187672  jnz     loc_140187802
0x140187678  mov     rax, [rdx]
0x14018767b  mov     [rcx+1C0h], rax
0x140187682  mov     rcx, [rdx+8]
0x140187686  test    rcx, rcx
0x140187689  jz      short loc_140187697
0x14018768b  call    cs:__imp_HMUnlockObject
0x140187692  nop     dword ptr [rax+rax+00h]
0x140187697  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14018769e  nop     dword ptr [rax+rax+00h]
0x1401876a3  test    rax, rax
0x1401876a6  jz      loc_14018783D
0x1401876ac  mov     rcx, [rax]
0x1401876af  mov     rdx, [rcx+1C0h]
0x1401876b6  lea     rax, [rbp+BugCheckParameter3]
0x1401876ba  cmp     rdx, rax
0x1401876bd  jnz     loc_1401877DF
0x1401876c3  mov     rax, [rdx]
0x1401876c6  mov     [rcx+1C0h], rax
0x1401876cd  mov     rcx, [rdx+8]
0x1401876d1  test    rcx, rcx
0x1401876d4  jz      short loc_1401876E2
0x1401876d6  call    cs:__imp_HMUnlockObject
0x1401876dd  nop     dword ptr [rax+rax+00h]
0x1401876e2  mov     rsi, r15
0x1401876e5  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1401876ec  nop     dword ptr [rax+rax+00h]
0x1401876f1  test    rax, rax
0x1401876f4  jz      short loc_140187705
0x1401876f6  mov     rax, [rax]
0x1401876f9  test    rax, rax
0x1401876fc  jz      short loc_140187705
0x1401876fe  mov     rax, [rax+200h]
0x140187705  movzx   r14d, di
0x140187709  call    cs:__imp_W32GetUserSessionState
0x140187710  nop     dword ptr [rax+rax+00h]
0x140187715  mov     rcx, [rax+4CF8h]
0x14018771c  cmp     r14, [rcx+8]
0x140187720  jnb     short loc_140187785
0x140187722  call    cs:__imp_W32GetUserSessionState
0x140187729  nop     dword ptr [rax+rax+00h]
0x14018772e  mov     rbx, rax
0x140187731  call    cs:__imp_W32GetUserSessionState
0x140187738  nop     dword ptr [rax+rax+00h]
0x14018773d  mov     rbx, [rbx+4D08h]
0x140187744  imul    r14d, [rax+4D10h]
0x14018774c  mov     ecx, r14d
0x14018774f  add     rbx, rcx
0x140187752  mov     rcx, rbx
0x140187755  call    cs:__imp_HMPkheFromPhe
0x14018775c  nop     dword ptr [rax+rax+00h]
0x140187761  shr     rdi, 10h
0x140187765  mov     r14, rax
0x140187768  mov     eax, 7FFFh
0x14018776d  and     di, ax
0x140187770  cmp     di, [rbx+1Ah]
0x140187774  jnz     short loc_1401877A2
0x140187776  test    byte ptr [rbx+19h], 1
0x14018777a  jnz     short loc_140187785
0x14018777c  cmp     byte ptr [rbx+18h], 1
0x140187780  jnz     short loc_140187785
0x140187782  mov     rsi, [r14]
0x140187785  mov     rdx, rsi; struct tagWND *
0x140187788  lea     rcx, [rbp+arg_0]; struct tagPOINT *
0x14018778c  call    ?WindowFromPoint@Win32k@InputTraceLogging@@SAXAEBUtagPOINT@@PEAUtagWND@@@Z; InputTraceLogging::Win32k::WindowFromPoint(tagPOINT const &,tagWND *)
0x140187791  mov     rax, rsi
0x140187794  add     rsp, 68h
0x140187798  pop     r15
0x14018779a  pop     r14
0x14018779c  pop     rdi
0x14018779d  pop     rsi
0x14018779e  pop     rbx
0x14018779f  pop     rbp
0x1401877a0  retn
0x1401877a2  cmp     di, ax
0x1401877a5  jz      short loc_140187776
0x1401877a7  test    di, di
0x1401877aa  jnz     short loc_140187785
0x1401877ac  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401877b3  nop     dword ptr [rax+rax+00h]
0x1401877b8  test    rax, rax
0x1401877bb  jz      short loc_140187785
0x1401877bd  jmp     short loc_140187776
0x1401877bf  xor     eax, eax
0x1401877c1  jmp     short loc_140187794
0x1401877c3  mov     r9d, 1
0x1401877c9  xor     r8d, r8d
0x1401877cc  mov     rdx, rbx
0x1401877cf  mov     rcx, rdi
0x1401877d2  call    ?xxxWindowHitTest2@@YAPEAUHWND__@@PEAUtagWND@@UtagPOINT@@PEAHW4WindowHitTestOption@@@Z; xxxWindowHitTest2(tagWND *,tagPOINT,int *,WindowHitTestOption)
0x1401877d7  mov     rdi, rax
0x1401877da  jmp     loc_140187697
0x1401877df  mov     r8, rcx; BugCheckParameter2
0x1401877e2  mov     [rsp+68h+BugCheckParameter4], r15; BugCheckParameter4
0x1401877e7  mov     ecx, 164h; BugCheckCode
0x1401877ec  lea     r9, [rbp+BugCheckParameter3]; BugCheckParameter3
0x1401877f0  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x1401877f5  call    cs:__imp_KeBugCheckEx
0x140187802  mov     r8, rcx; BugCheckParameter2
0x140187805  mov     [rsp+68h+BugCheckParameter4], r15; BugCheckParameter4
0x14018780a  mov     ecx, 164h; BugCheckCode
0x14018780f  lea     r9, [rbp+var_28]; BugCheckParameter3
0x140187813  mov     edx, 3Bh ; ';'; BugCheckParameter1
0x140187818  call    cs:__imp_KeBugCheckEx
0x140187825  mov     rcx, r15
0x140187828  jmp     loc_14018759C
0x14018782d  mov     rcx, r15
0x140187830  jmp     loc_1401875F8
0x140187835  mov     rcx, r15
0x140187838  jmp     loc_140187664
0x14018783d  mov     rcx, r15
0x140187840  jmp     loc_1401876AF
```
