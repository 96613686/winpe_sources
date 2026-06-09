# CPXWizardMutexLock::WaitForLock(ulong,int)

- ea: `0x180012044`
- end: `0x1800122aa`
- name: `?WaitForLock@CPXWizardMutexLock@@QEAAJKH@Z`
- size: `614`
- prototype: `__int64 __fastcall(CPXWizardMutexLock *__hidden this, unsigned int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180011710`
- `0x180011820`
- `0x180011a10`
- `0x180011fac`

## callees

- `0x180003b90`
- `0x180007820`
- `0x180012044`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012257`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012257`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800120d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800120d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012260`
- `USER32!TranslateMessage` at `0x180012159`
- `USER32!TranslateMessage` at `0x180012159`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180012188`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180012188`
- `USER32!PeekMessageW` at `0x18001214a`
- `USER32!PeekMessageW` at `0x18001214a`
- `USER32!DispatchMessageW` at `0x180012164`
- `USER32!DispatchMessageW` at `0x180012164`

## pseudocode

```c
__int64 __fastcall CPXWizardMutexLock::WaitForLock(LPCWSTR *this)
{
  unsigned int v1; // ebx
  PVOID *v2; // rcx
  __int64 v3; // rdx
  HANDLE *v4; // r14
  HANDLE MutexW; // rax
  unsigned int LastErrorHRESULT; // eax
  DWORD v8; // eax
  unsigned int v9; // eax
  struct tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF

  v1 = *(_DWORD *)this;
  if ( *(int *)this < 0 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return v1;
    v3 = 17;
LABEL_38:
    WPP_SF_D(v2[2], v3, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, v1);
    return v1;
  }
  v4 = (HANDLE *)(this + 1);
  if ( !this[1] )
  {
    MutexW = CreateMutexW(0, 0, this[2]);
    *v4 = MutexW;
    if ( !MutexW )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      v1 = LastErrorHRESULT;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids,
          LastErrorHRESULT);
    }
    do
    {
      if ( (v1 & 0x80000000) != 0 )
        goto LABEL_34;
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      v8 = MsgWaitForMultipleObjectsEx(1u, v4, 0x3E8u, 0x1CFFu, 4u);
    }
    while ( v8 == 1 );
    switch ( v8 )
    {
      case 0u:
        v1 = 0;
LABEL_34:
        v2 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_35;
      case 0x80u:
        v1 = 1;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v1;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, 1);
          goto LABEL_34;
        }
LABEL_35:
        if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 0x10) == 0 )
          return v1;
        v3 = 23;
        goto LABEL_38;
      case 0x102u:
        v1 = -2147023436;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids,
            2147943860LL);
        break;
      default:
        v9 = GetLastErrorHRESULT();
        v1 = v9;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, v9);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (v1 & 0x80000000) == 0 )
          goto LABEL_35;
        break;
    }
    ReleaseMutex(*v4);
    CloseHandle(*v4);
    *v4 = 0;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, 2147942405LL);
  return 2147942405LL;
}

```

## disassembly

```asm
0x180012044  mov     [rsp+arg_0], rbx
0x180012049  mov     [rsp+arg_8], rdi
0x18001204e  push    r14
0x180012050  sub     rsp, 60h
0x180012054  mov     ebx, [rcx]
0x180012056  test    ebx, ebx
0x180012058  jns     short loc_180012085
0x18001205a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012061  lea     rdi, WPP_GLOBAL_Control
0x180012068  cmp     rcx, rdi
0x18001206b  jz      loc_180012297
0x180012071  test    byte ptr [rcx+1Ch], 4
0x180012075  jz      loc_180012297
0x18001207b  mov     edx, 11h
0x180012080  jmp     loc_180012284
0x180012085  lea     r14, [rcx+8]
0x180012089  cmp     qword ptr [r14], 0
0x18001208d  jz      short loc_1800120CD
0x18001208f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012096  lea     rdi, WPP_GLOBAL_Control
0x18001209d  cmp     rcx, rdi
0x1800120a0  jz      short loc_1800120C3
0x1800120a2  test    byte ptr [rcx+1Ch], 10h
0x1800120a6  jz      short loc_1800120C3
0x1800120a8  mov     rcx, [rcx+10h]
0x1800120ac  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x1800120b3  mov     edx, 12h
0x1800120b8  mov     r9d, 80070005h
0x1800120be  call    WPP_SF_D
0x1800120c3  mov     eax, 80070005h
0x1800120c8  jmp     loc_180012299
0x1800120cd  mov     r8, [rcx+10h]; lpName
0x1800120d1  xor     edx, edx; bInitialOwner
0x1800120d3  xor     ecx, ecx; lpMutexAttributes
0x1800120d5  call    cs:__imp_CreateMutexW
0x1800120db  mov     [r14], rax
0x1800120de  lea     rdi, WPP_GLOBAL_Control
0x1800120e5  test    rax, rax
0x1800120e8  jnz     short loc_18001211B
0x1800120ea  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800120ef  mov     ebx, eax
0x1800120f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120f8  cmp     rcx, rdi
0x1800120fb  jz      short loc_18001211B
0x1800120fd  test    byte ptr [rcx+1Ch], 4
0x180012101  jz      short loc_18001211B
0x180012103  mov     rcx, [rcx+10h]
0x180012107  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x18001210e  mov     edx, 13h
0x180012113  mov     r9d, eax
0x180012116  call    WPP_SF_D
0x18001211b  test    ebx, ebx
0x18001211d  js      loc_18001226D
0x180012123  xorps   xmm0, xmm0
0x180012126  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x18001212b  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x180012130  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x180012135  xor     r9d, r9d; wMsgFilterMax
0x180012138  mov     [rsp+68h+wRemoveMsg], 1; wRemoveMsg
0x180012140  xor     r8d, r8d; wMsgFilterMin
0x180012143  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180012148  xor     edx, edx; hWnd
0x18001214a  call    cs:__imp_PeekMessageW
0x180012150  test    eax, eax
0x180012152  jz      short loc_18001216C
0x180012154  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180012159  call    cs:__imp_TranslateMessage
0x18001215f  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180012164  call    cs:__imp_DispatchMessageW
0x18001216a  jmp     short loc_180012135
0x18001216c  mov     r9d, 1CFFh; dwWakeMask
0x180012172  mov     [rsp+68h+wRemoveMsg], 4; dwFlags
0x18001217a  mov     r8d, 3E8h; dwMilliseconds
0x180012180  mov     rdx, r14; pHandles
0x180012183  mov     ecx, 1; nCount
0x180012188  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18001218e  cmp     eax, 1
0x180012191  jz      short loc_18001211B
0x180012193  test    eax, eax
0x180012195  jnz     short loc_18001219E
0x180012197  xor     ebx, ebx
0x180012199  jmp     loc_18001226D
0x18001219e  cmp     eax, 80h
0x1800121a3  jnz     short loc_1800121DD
0x1800121a5  lea     ebx, [rax-7Fh]
0x1800121a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121af  cmp     rcx, rdi
0x1800121b2  jz      loc_180012297
0x1800121b8  test    byte ptr [rcx+1Ch], 10h
0x1800121bc  jz      loc_180012274
0x1800121c2  mov     rcx, [rcx+10h]
0x1800121c6  lea     edx, [rax-6Ch]
0x1800121c9  mov     r9d, ebx
0x1800121cc  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x1800121d3  call    WPP_SF_D
0x1800121d8  jmp     loc_18001226D
0x1800121dd  cmp     eax, 102h
0x1800121e2  jnz     short loc_180012218
0x1800121e4  mov     ebx, 800705B4h
0x1800121e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121f0  cmp     rcx, rdi
0x1800121f3  jz      short loc_180012254
0x1800121f5  test    byte ptr [rcx+1Ch], 10h
0x1800121f9  jz      short loc_180012254
0x1800121fb  mov     rcx, [rcx+10h]
0x1800121ff  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180012206  mov     edx, 15h
0x18001220b  mov     r9d, 800705B4h
0x180012211  call    WPP_SF_D
0x180012216  jmp     short loc_180012254
0x180012218  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001221d  mov     ebx, eax
0x18001221f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012226  cmp     rcx, rdi
0x180012229  jz      short loc_180012250
0x18001222b  test    byte ptr [rcx+1Ch], 4
0x18001222f  jz      short loc_180012250
0x180012231  mov     rcx, [rcx+10h]
0x180012235  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x18001223c  mov     edx, 16h
0x180012241  mov     r9d, eax
0x180012244  call    WPP_SF_D
0x180012249  mov     rcx, cs:WPP_GLOBAL_Control
0x180012250  test    ebx, ebx
0x180012252  jns     short loc_180012274
0x180012254  mov     rcx, [r14]; hMutex
0x180012257  call    cs:__imp_ReleaseMutex
0x18001225d  mov     rcx, [r14]; hObject
0x180012260  call    cs:__imp_CloseHandle
0x180012266  mov     qword ptr [r14], 0
0x18001226d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012274  cmp     rcx, rdi
0x180012277  jz      short loc_180012297
0x180012279  test    byte ptr [rcx+1Ch], 10h
0x18001227d  jz      short loc_180012297
0x18001227f  mov     edx, 17h
0x180012284  mov     rcx, [rcx+10h]
0x180012288  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x18001228f  mov     r9d, ebx
0x180012292  call    WPP_SF_D
0x180012297  mov     eax, ebx
0x180012299  mov     rbx, [rsp+68h+arg_0]
0x18001229e  mov     rdi, [rsp+68h+arg_8]
0x1800122a3  add     rsp, 60h
0x1800122a7  pop     r14
0x1800122a9  retn
```
