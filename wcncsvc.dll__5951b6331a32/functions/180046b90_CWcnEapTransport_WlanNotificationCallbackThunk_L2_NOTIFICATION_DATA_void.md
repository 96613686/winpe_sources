# CWcnEapTransport::WlanNotificationCallbackThunk(_L2_NOTIFICATION_DATA *,void *)

- ea: `0x180046b90`
- end: `0x180046c88`
- name: `?WlanNotificationCallbackThunk@CWcnEapTransport@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z`
- size: `248`
- prototype: `void __stdcall(PWLAN_NOTIFICATION_DATA, PVOID)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004fb8`
- `0x180046b90`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046c16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046c16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046c3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046c36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046c36`

## pseudocode

```c
void __fastcall CWcnEapTransport::WlanNotificationCallbackThunk(PWLAN_NOTIFICATION_DATA a1, char *a2)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  struct _TP_TIMER *v7; // rcx
  const char *v8; // rax
  __int64 v9; // r10
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 51, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1->NotificationSource == 8 )
  {
    if ( a1->NotificationCode == 7 || a1->NotificationCode - 13 <= 1 )
    {
      pftDueTime = (struct _FILETIME)-5000000LL;
      EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 184));
      v7 = (struct _TP_TIMER *)*((_QWORD *)a2 + 22);
      if ( v7 )
        SetThreadpoolTimer(v7, &pftDueTime, 0, 0x12Cu);
      LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 184));
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 6u )
    {
      v8 = GetIndent(-1);
      WPP_SF_s(*(_QWORD *)(v9 + 16), 52, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v8);
    }
  }
}

```

## disassembly

```asm
0x180046b90  mov     [rsp+arg_8], rbx
0x180046b95  mov     [rsp+arg_10], rsi
0x180046b9a  push    rdi
0x180046b9b  sub     rsp, 20h
0x180046b9f  mov     rdi, rdx
0x180046ba2  mov     rbx, rcx
0x180046ba5  mov     r10, cs:WPP_GLOBAL_Control
0x180046bac  lea     rsi, WPP_GLOBAL_Control
0x180046bb3  cmp     r10, rsi
0x180046bb6  jz      short loc_180046BE8
0x180046bb8  cmp     byte ptr [r10+19h], 6
0x180046bbd  jb      short loc_180046BE8
0x180046bbf  mov     ecx, 1; int
0x180046bc4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180046bc9  mov     rcx, [r10+10h]
0x180046bcd  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x180046bd4  mov     edx, 33h ; '3'
0x180046bd9  mov     r9, rax
0x180046bdc  call    WPP_SF_s
0x180046be1  mov     r10, cs:WPP_GLOBAL_Control
0x180046be8  cmp     dword ptr [rbx], 8
0x180046beb  jnz     loc_180046C78
0x180046bf1  mov     ecx, [rbx+4]
0x180046bf4  sub     ecx, 7
0x180046bf7  jz      short loc_180046C03
0x180046bf9  sub     ecx, 6
0x180046bfc  jz      short loc_180046C03
0x180046bfe  cmp     ecx, 1
0x180046c01  jnz     short loc_180046C4C
0x180046c03  lea     rbx, [rdi+0B8h]
0x180046c0a  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFFB3B4C0h
0x180046c13  mov     rcx, rbx; lpCriticalSection
0x180046c16  call    cs:__imp_EnterCriticalSection
0x180046c1c  mov     rcx, [rdi+0B0h]; pti
0x180046c23  test    rcx, rcx
0x180046c26  jz      short loc_180046C3C
0x180046c28  mov     r9d, 12Ch; msWindowLength
0x180046c2e  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180046c33  xor     r8d, r8d; msPeriod
0x180046c36  call    cs:__imp_SetThreadpoolTimer
0x180046c3c  mov     rcx, rbx; lpCriticalSection
0x180046c3f  call    cs:__imp_LeaveCriticalSection
0x180046c45  mov     r10, cs:WPP_GLOBAL_Control
0x180046c4c  cmp     r10, rsi
0x180046c4f  jz      short loc_180046C78
0x180046c51  cmp     byte ptr [r10+19h], 6
0x180046c56  jb      short loc_180046C78
0x180046c58  or      ecx, 0FFFFFFFFh; int
0x180046c5b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180046c60  mov     rcx, [r10+10h]
0x180046c64  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x180046c6b  mov     edx, 34h ; '4'
0x180046c70  mov     r9, rax
0x180046c73  call    WPP_SF_s
0x180046c78  mov     rbx, [rsp+28h+arg_8]
0x180046c7d  mov     rsi, [rsp+28h+arg_10]
0x180046c82  add     rsp, 20h
0x180046c86  pop     rdi
0x180046c87  retn
```
