# TmCreateTimer

- ea: `0x18007b4e8`
- end: `0x18007b631`
- name: `TmCreateTimer`
- size: `329`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007c7c4`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x18007b4e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b5c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b5c9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18007b5b9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18007b5b9`

## pseudocode

```c
__int64 __fastcall TmCreateTimer(PVOID Parameter, __int64 a2, __int64 a3, void **a4)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  DWORD LastError; // eax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      WPP_SF_dd(v6[2], 21, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, 0x7FFFFFFF, 0x7FFFFFFF);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( !Parameter )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    {
      WPP_SF_(v6[2], 22, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = 87;
    goto LABEL_17;
  }
  v7 = 0;
  if ( CreateTimerQueueTimer(a4, g_hTimerQueue, TmTimeoutCallback, Parameter, 0x7FFFFFFFu, 0x7FFFFFFFu, 0) )
    goto LABEL_16;
  LastError = GetLastError();
  v7 = LastError;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, LastError);
LABEL_16:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_17:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_d(v6[2], 24, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18007b4e8  push    rbx
0x18007b4ea  push    rbp
0x18007b4eb  push    rsi
0x18007b4ec  push    rdi
0x18007b4ed  push    r14
0x18007b4ef  sub     rsp, 40h
0x18007b4f3  mov     rsi, r9
0x18007b4f6  mov     rdi, rcx
0x18007b4f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b500  lea     rbp, WPP_GLOBAL_Control
0x18007b507  lea     r14, WPP_ae96259228ce3526774098cd20cb7e4b_Traceguids
0x18007b50e  cmp     rcx, rbp
0x18007b511  jz      short loc_18007B562
0x18007b513  test    byte ptr [rcx+1Ch], 1
0x18007b517  jz      short loc_18007B531
0x18007b519  mov     rcx, [rcx+10h]
0x18007b51d  mov     edx, 14h
0x18007b522  mov     r8, r14
0x18007b525  call    WPP_SF_
0x18007b52a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b531  cmp     rcx, rbp
0x18007b534  jz      short loc_18007B562
0x18007b536  test    byte ptr [rcx+1Ch], 1
0x18007b53a  jz      short loc_18007B562
0x18007b53c  mov     rcx, [rcx+10h]
0x18007b540  mov     edx, 15h
0x18007b545  mov     r9d, 7FFFFFFFh
0x18007b54b  mov     [rsp+68h+DueTime], 7FFFFFFFh
0x18007b553  mov     r8, r14
0x18007b556  call    WPP_SF_dd
0x18007b55b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b562  test    rdi, rdi
0x18007b565  jnz     short loc_18007B58F
0x18007b567  cmp     rcx, rbp
0x18007b56a  jz      short loc_18007B588
0x18007b56c  test    byte ptr [rcx+1Ch], 2
0x18007b570  jz      short loc_18007B588
0x18007b572  mov     rcx, [rcx+10h]
0x18007b576  lea     edx, [rdi+16h]
0x18007b579  mov     r8, r14
0x18007b57c  call    WPP_SF_
0x18007b581  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b588  mov     ebx, 57h ; 'W'
0x18007b58d  jmp     short loc_18007B604
0x18007b58f  mov     rdx, cs:g_hTimerQueue; TimerQueue
0x18007b596  lea     r8, TmTimeoutCallback; Callback
0x18007b59d  xor     ebx, ebx
0x18007b59f  mov     r9, rdi; Parameter
0x18007b5a2  mov     [rsp+68h+Flags], ebx; Flags
0x18007b5a6  mov     rcx, rsi; phNewTimer
0x18007b5a9  mov     [rsp+68h+Period], 7FFFFFFFh; Period
0x18007b5b1  mov     [rsp+68h+DueTime], 7FFFFFFFh; DueTime
0x18007b5b9  call    cs:__imp_CreateTimerQueueTimer
0x18007b5c0  nop     dword ptr [rax+rax+00h]
0x18007b5c5  test    eax, eax
0x18007b5c7  jnz     short loc_18007B5FD
0x18007b5c9  call    cs:__imp_GetLastError
0x18007b5d0  nop     dword ptr [rax+rax+00h]
0x18007b5d5  mov     ebx, eax
0x18007b5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b5de  cmp     rcx, rbp
0x18007b5e1  jz      short loc_18007B623
0x18007b5e3  test    byte ptr [rcx+1Ch], 2
0x18007b5e7  jz      short loc_18007B604
0x18007b5e9  mov     rcx, [rcx+10h]
0x18007b5ed  mov     edx, 17h
0x18007b5f2  mov     r9d, eax
0x18007b5f5  mov     r8, r14
0x18007b5f8  call    WPP_SF_d
0x18007b5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b604  cmp     rcx, rbp
0x18007b607  jz      short loc_18007B623
0x18007b609  test    byte ptr [rcx+1Ch], 1
0x18007b60d  jz      short loc_18007B623
0x18007b60f  mov     rcx, [rcx+10h]
0x18007b613  mov     edx, 18h
0x18007b618  mov     r9d, ebx
0x18007b61b  mov     r8, r14
0x18007b61e  call    WPP_SF_d
0x18007b623  mov     eax, ebx
0x18007b625  add     rsp, 40h
0x18007b629  pop     r14
0x18007b62b  pop     rdi
0x18007b62c  pop     rsi
0x18007b62d  pop     rbp
0x18007b62e  pop     rbx
0x18007b62f  retn
```
