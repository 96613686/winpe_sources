# CPXWizardMutexLock::WaitForLock(ulong,int)

- ea: `0x1800326c4`
- end: `0x180032935`
- name: `?WaitForLock@CPXWizardMutexLock@@QEAAJKH@Z`
- size: `625`
- prototype: `__int64 __fastcall(CPXWizardMutexLock *__hidden this, unsigned int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180031b98`
- `0x180031d2c`
- `0x180032198`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x1800326c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800328e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800328e7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180032754`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180032754`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800328f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800328f0`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18003280c`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18003280c`
- `USER32!TranslateMessage` at `0x1800327df`
- `USER32!TranslateMessage` at `0x1800327df`
- `USER32!PeekMessageW` at `0x1800327d0`
- `USER32!PeekMessageW` at `0x1800327d0`
- `USER32!DispatchMessageW` at `0x1800327ea`
- `USER32!DispatchMessageW` at `0x1800327ea`

## pseudocode

```c
__int64 __fastcall CPXWizardMutexLock::WaitForLock(LPCWSTR *this, __int64 a2, int a3)
{
  unsigned int v3; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  HANDLE *v7; // r14
  HANDLE MutexW; // rax
  unsigned int LastErrorHRESULT; // eax
  DWORD v11; // eax
  unsigned int v12; // eax
  struct tagMSG Msg; // [rsp+30h] [rbp-58h] BYREF

  v3 = *(_DWORD *)this;
  if ( *(int *)this < 0 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return v3;
    v6 = 17;
LABEL_40:
    WPP_SF_d(v5[2], v6, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, v3);
    return v3;
  }
  v7 = (HANDLE *)(this + 1);
  if ( !this[1] )
  {
    MutexW = CreateMutexW(0, 0, this[2]);
    *v7 = MutexW;
    if ( !MutexW )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      v3 = LastErrorHRESULT;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids,
          LastErrorHRESULT);
    }
    while ( 1 )
    {
      if ( (v3 & 0x80000000) != 0 )
        goto LABEL_36;
      memset(&Msg, 0, sizeof(Msg));
      if ( a3 )
      {
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      v11 = MsgWaitForMultipleObjectsEx(1u, v7, 0x3E8u, 0x1CFFu, 4u);
      if ( v11 != 1 )
        break;
      if ( !a3 )
      {
        v3 = 1;
LABEL_36:
        v5 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_37;
      }
    }
    switch ( v11 )
    {
      case 0u:
        v3 = 0;
        goto LABEL_36;
      case 0x80u:
        v3 = 1;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v3;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, 1);
          goto LABEL_36;
        }
        goto LABEL_37;
      case 0x102u:
        v3 = -2147023436;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids,
            2147943860LL);
        break;
      default:
        v12 = GetLastErrorHRESULT();
        v3 = v12;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, v12);
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (v3 & 0x80000000) == 0 )
        {
LABEL_37:
          if ( v5 == &WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 0x10) == 0 )
            return v3;
          v6 = 23;
          goto LABEL_40;
        }
        break;
    }
    ReleaseMutex(*v7);
    CloseHandle(*v7);
    *v7 = 0;
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, 2147942405LL);
  return 2147942405LL;
}

```

## disassembly

```asm
0x1800326c4  push    rbx
0x1800326c6  push    rbp
0x1800326c7  push    rdi
0x1800326c8  push    r14
0x1800326ca  push    r15
0x1800326cc  sub     rsp, 60h
0x1800326d0  mov     ebx, [rcx]
0x1800326d2  mov     ebp, r8d
0x1800326d5  test    ebx, ebx
0x1800326d7  jns     short loc_180032704
0x1800326d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326e0  lea     rdi, WPP_GLOBAL_Control
0x1800326e7  cmp     rcx, rdi
0x1800326ea  jz      loc_180032927
0x1800326f0  test    byte ptr [rcx+1Ch], 4
0x1800326f4  jz      loc_180032927
0x1800326fa  mov     edx, 11h
0x1800326ff  jmp     loc_180032914
0x180032704  lea     r14, [rcx+8]
0x180032708  cmp     qword ptr [r14], 0
0x18003270c  jz      short loc_18003274C
0x18003270e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032715  lea     rdi, WPP_GLOBAL_Control
0x18003271c  cmp     rcx, rdi
0x18003271f  jz      short loc_180032742
0x180032721  test    byte ptr [rcx+1Ch], 10h
0x180032725  jz      short loc_180032742
0x180032727  mov     rcx, [rcx+10h]
0x18003272b  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180032732  mov     edx, 12h
0x180032737  mov     r9d, 80070005h
0x18003273d  call    WPP_SF_d
0x180032742  mov     eax, 80070005h
0x180032747  jmp     loc_180032929
0x18003274c  mov     r8, [rcx+10h]; lpName
0x180032750  xor     edx, edx; bInitialOwner
0x180032752  xor     ecx, ecx; lpMutexAttributes
0x180032754  call    cs:__imp_CreateMutexW
0x18003275a  mov     [r14], rax
0x18003275d  lea     rdi, WPP_GLOBAL_Control
0x180032764  test    rax, rax
0x180032767  jnz     short loc_18003279A
0x180032769  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18003276e  mov     ebx, eax
0x180032770  mov     rcx, cs:WPP_GLOBAL_Control
0x180032777  cmp     rcx, rdi
0x18003277a  jz      short loc_18003279A
0x18003277c  test    byte ptr [rcx+1Ch], 4
0x180032780  jz      short loc_18003279A
0x180032782  mov     rcx, [rcx+10h]
0x180032786  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x18003278d  mov     edx, 13h
0x180032792  mov     r9d, eax
0x180032795  call    WPP_SF_d
0x18003279a  mov     r15d, 1
0x1800327a0  test    ebx, ebx
0x1800327a2  js      loc_1800328FD
0x1800327a8  xorps   xmm0, xmm0
0x1800327ab  movups  xmmword ptr [rsp+88h+Msg.hwnd], xmm0
0x1800327b0  movups  xmmword ptr [rsp+88h+Msg.wParam], xmm0
0x1800327b5  movups  xmmword ptr [rsp+88h+Msg.time], xmm0
0x1800327ba  test    ebp, ebp
0x1800327bc  jz      short loc_1800327F2
0x1800327be  xor     r9d, r9d; wMsgFilterMax
0x1800327c1  mov     [rsp+88h+wRemoveMsg], r15d; wRemoveMsg
0x1800327c6  xor     r8d, r8d; wMsgFilterMin
0x1800327c9  lea     rcx, [rsp+88h+Msg]; lpMsg
0x1800327ce  xor     edx, edx; hWnd
0x1800327d0  call    cs:__imp_PeekMessageW
0x1800327d6  test    eax, eax
0x1800327d8  jz      short loc_1800327F2
0x1800327da  lea     rcx, [rsp+88h+Msg]; lpMsg
0x1800327df  call    cs:__imp_TranslateMessage
0x1800327e5  lea     rcx, [rsp+88h+Msg]; lpMsg
0x1800327ea  call    cs:__imp_DispatchMessageW
0x1800327f0  jmp     short loc_1800327BE
0x1800327f2  mov     r9d, 1CFFh; dwWakeMask
0x1800327f8  mov     [rsp+88h+wRemoveMsg], 4; dwFlags
0x180032800  mov     r8d, 3E8h; dwMilliseconds
0x180032806  mov     rdx, r14; pHandles
0x180032809  mov     ecx, r15d; nCount
0x18003280c  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180032812  cmp     eax, r15d
0x180032815  jnz     short loc_180032823
0x180032817  test    ebp, ebp
0x180032819  jnz     short loc_1800327A0
0x18003281b  mov     ebx, r15d
0x18003281e  jmp     loc_1800328FD
0x180032823  test    eax, eax
0x180032825  jnz     short loc_18003282E
0x180032827  xor     ebx, ebx
0x180032829  jmp     loc_1800328FD
0x18003282e  cmp     eax, 80h
0x180032833  jnz     short loc_18003286D
0x180032835  mov     ebx, r15d
0x180032838  mov     rcx, cs:WPP_GLOBAL_Control
0x18003283f  cmp     rcx, rdi
0x180032842  jz      loc_180032927
0x180032848  test    byte ptr [rcx+1Ch], 10h
0x18003284c  jz      loc_180032904
0x180032852  mov     rcx, [rcx+10h]
0x180032856  lea     edx, [rax-6Ch]
0x180032859  mov     r9d, r15d
0x18003285c  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180032863  call    WPP_SF_d
0x180032868  jmp     loc_1800328FD
0x18003286d  cmp     eax, 102h
0x180032872  jnz     short loc_1800328A8
0x180032874  mov     ebx, 800705B4h
0x180032879  mov     rcx, cs:WPP_GLOBAL_Control
0x180032880  cmp     rcx, rdi
0x180032883  jz      short loc_1800328E4
0x180032885  test    byte ptr [rcx+1Ch], 10h
0x180032889  jz      short loc_1800328E4
0x18003288b  mov     rcx, [rcx+10h]
0x18003288f  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180032896  mov     edx, 15h
0x18003289b  mov     r9d, 800705B4h
0x1800328a1  call    WPP_SF_d
0x1800328a6  jmp     short loc_1800328E4
0x1800328a8  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800328ad  mov     ebx, eax
0x1800328af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328b6  cmp     rcx, rdi
0x1800328b9  jz      short loc_1800328E0
0x1800328bb  test    byte ptr [rcx+1Ch], 4
0x1800328bf  jz      short loc_1800328E0
0x1800328c1  mov     rcx, [rcx+10h]
0x1800328c5  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x1800328cc  mov     edx, 16h
0x1800328d1  mov     r9d, eax
0x1800328d4  call    WPP_SF_d
0x1800328d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328e0  test    ebx, ebx
0x1800328e2  jns     short loc_180032904
0x1800328e4  mov     rcx, [r14]; hMutex
0x1800328e7  call    cs:__imp_ReleaseMutex
0x1800328ed  mov     rcx, [r14]; hObject
0x1800328f0  call    cs:__imp_CloseHandle
0x1800328f6  mov     qword ptr [r14], 0
0x1800328fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180032904  cmp     rcx, rdi
0x180032907  jz      short loc_180032927
0x180032909  test    byte ptr [rcx+1Ch], 10h
0x18003290d  jz      short loc_180032927
0x18003290f  mov     edx, 17h
0x180032914  mov     rcx, [rcx+10h]
0x180032918  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x18003291f  mov     r9d, ebx
0x180032922  call    WPP_SF_d
0x180032927  mov     eax, ebx
0x180032929  add     rsp, 60h
0x18003292d  pop     r15
0x18003292f  pop     r14
0x180032931  pop     rdi
0x180032932  pop     rbp
0x180032933  pop     rbx
0x180032934  retn
```
