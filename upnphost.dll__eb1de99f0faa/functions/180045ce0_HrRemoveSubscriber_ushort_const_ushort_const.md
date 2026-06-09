# HrRemoveSubscriber(ushort const *,ushort const *)

- ea: `0x180045ce0`
- end: `0x180045f0a`
- name: `?HrRemoveSubscriber@@YAJPEBG0@Z`
- size: `554`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800313b0`
- `0x180034030`

## callees

- `0x18000db4c`
- `0x18000e3ec`
- `0x180026b90`
- `0x180038dc0`
- `0x180039388`
- `0x180045ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045db8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045db8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045d8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045d8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ebf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ebf`

## string_xrefs

- `0x180045d22`: `HrRemoveSubscriber`
- `0x180045edf`: `HrRemoveSubscriber`

## pseudocode

```c
__int64 __fastcall HrRemoveSubscriber(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  struct UPNP_EVENT_SOURCE *EventSource; // rax
  struct UPNP_EVENT_SOURCE *v6; // rdi
  __int64 v7; // r15
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // rax

  if ( g_fEventApiInitialized )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (_DWORD)a2,
        (__int64)a1);
    }
    EnterCriticalSection(&g_csEventApiLock);
    EventSource = PesFindEventSource(a1);
    v6 = EventSource;
    if ( EventSource )
    {
      v7 = *((_QWORD *)EventSource + 2);
      v8 = v7;
      if ( v7 )
      {
        while ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v8 + 40), a2) )
        {
          v7 = v8;
          v8 = *(_QWORD *)(v8 + 272);
          if ( !v8 )
            goto LABEL_13;
        }
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            81,
            (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
            *(_QWORD *)(v8 + 40),
            *(_QWORD *)v6);
        }
        v10 = *(_QWORD *)(v8 + 272);
        if ( v8 == *((_QWORD *)v6 + 2) )
          *((_QWORD *)v6 + 2) = v10;
        else
          *(_QWORD *)(v7 + 272) = v10;
        --*((_DWORD *)v6 + 2);
        v9 = 0;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, a2);
        }
        *(_QWORD *)v8 = 0;
        QueueOrExecuteSubscriptionDeletion((struct UPNP_SUBSCRIBER *)v8);
      }
      else
      {
LABEL_13:
        v9 = -2147024894;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            83,
            (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
            (_DWORD)a2,
            (__int64)a1);
        }
      }
    }
    else
    {
      v9 = -2147024894;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, a1);
      }
    }
    LeaveCriticalSection(&g_csEventApiLock);
    if ( v9 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)"HrRemoveSubscriber",
        v9);
    return v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)"HrRemoveSubscriber",
        5);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180045ce0  push    rbx
0x180045ce2  push    rbp
0x180045ce3  push    rsi
0x180045ce4  push    rdi
0x180045ce5  push    r12
0x180045ce7  push    r13
0x180045ce9  push    r14
0x180045ceb  push    r15
0x180045ced  sub     rsp, 38h
0x180045cf1  cmp     cs:?g_fEventApiInitialized@@3HA, 0; int g_fEventApiInitialized
0x180045cf8  mov     r12, rdx
0x180045cfb  mov     r14, rcx
0x180045cfe  jnz     short loc_180045D45
0x180045d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d07  lea     rsi, WPP_GLOBAL_Control
0x180045d0e  mov     ebx, 80004005h
0x180045d13  cmp     rcx, rsi
0x180045d16  jz      short loc_180045D3E
0x180045d18  test    byte ptr [rcx+1Ch], 1
0x180045d1c  jz      short loc_180045D3E
0x180045d1e  mov     rcx, [rcx+10h]
0x180045d22  lea     r9, aHrremovesubscr; "HrRemoveSubscriber"
0x180045d29  mov     edx, 4Fh ; 'O'
0x180045d2e  mov     dword ptr [rsp+78h+var_58], ebx
0x180045d32  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180045d39  call    WPP_SF_sd
0x180045d3e  mov     eax, ebx
0x180045d40  jmp     loc_180045EF9
0x180045d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d4c  lea     rsi, WPP_GLOBAL_Control
0x180045d53  lea     rbp, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180045d5a  mov     r13d, 800h
0x180045d60  cmp     rcx, rsi
0x180045d63  jz      short loc_180045D84
0x180045d65  test    [rcx+1Ch], r13d
0x180045d69  jz      short loc_180045D84
0x180045d6b  mov     rcx, [rcx+10h]
0x180045d6f  mov     edx, 50h ; 'P'
0x180045d74  mov     r9, r12
0x180045d77  mov     [rsp+78h+var_58], r14
0x180045d7c  mov     r8, rbp
0x180045d7f  call    WPP_SF_SS
0x180045d84  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045d8b  call    cs:__imp_EnterCriticalSection
0x180045d91  mov     rcx, r14; unsigned __int16 *
0x180045d94  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180045d99  mov     rdi, rax
0x180045d9c  test    rax, rax
0x180045d9f  jz      loc_180045E8D
0x180045da5  mov     r15, [rax+10h]
0x180045da9  mov     rbx, r15
0x180045dac  test    r15, r15
0x180045daf  jz      short loc_180045DD1
0x180045db1  mov     rcx, [rbx+28h]
0x180045db5  mov     rdx, r12
0x180045db8  call    cs:__imp__o__wcsicmp
0x180045dbe  test    eax, eax
0x180045dc0  jz      short loc_180045E0E
0x180045dc2  mov     r15, rbx
0x180045dc5  mov     rbx, [rbx+110h]
0x180045dcc  test    rbx, rbx
0x180045dcf  jnz     short loc_180045DB1
0x180045dd1  mov     edi, 80070002h
0x180045dd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ddd  cmp     rcx, rsi
0x180045de0  jz      loc_180045EB8
0x180045de6  test    [rcx+1Ch], r13d
0x180045dea  jz      loc_180045EB8
0x180045df0  mov     rcx, [rcx+10h]
0x180045df4  mov     edx, 53h ; 'S'
0x180045df9  mov     r9, r12
0x180045dfc  mov     [rsp+78h+var_58], r14
0x180045e01  mov     r8, rbp
0x180045e04  call    WPP_SF_SS
0x180045e09  jmp     loc_180045EB8
0x180045e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e15  cmp     rcx, rsi
0x180045e18  jz      short loc_180045E3D
0x180045e1a  test    [rcx+1Ch], r13d
0x180045e1e  jz      short loc_180045E3D
0x180045e20  mov     rax, [rdi]
0x180045e23  mov     edx, 51h ; 'Q'
0x180045e28  mov     r9, [rbx+28h]
0x180045e2c  mov     r8, rbp
0x180045e2f  mov     rcx, [rcx+10h]
0x180045e33  mov     [rsp+78h+var_58], rax
0x180045e38  call    WPP_SF_SS
0x180045e3d  mov     rax, [rbx+110h]
0x180045e44  cmp     rbx, [rdi+10h]
0x180045e48  jnz     short loc_180045E50
0x180045e4a  mov     [rdi+10h], rax
0x180045e4e  jmp     short loc_180045E57
0x180045e50  mov     [r15+110h], rax
0x180045e57  dec     dword ptr [rdi+8]
0x180045e5a  xor     edi, edi
0x180045e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e63  cmp     rcx, rsi
0x180045e66  jz      short loc_180045E80
0x180045e68  test    [rcx+1Ch], r13d
0x180045e6c  jz      short loc_180045E80
0x180045e6e  mov     rcx, [rcx+10h]
0x180045e72  lea     edx, [rdi+52h]
0x180045e75  mov     r9, r12
0x180045e78  mov     r8, rbp
0x180045e7b  call    WPP_SF_S
0x180045e80  mov     rcx, rbx; struct UPNP_SUBSCRIBER *
0x180045e83  mov     [rbx], rdi
0x180045e86  call    ?QueueOrExecuteSubscriptionDeletion@@YAXPEAUUPNP_SUBSCRIBER@@@Z; QueueOrExecuteSubscriptionDeletion(UPNP_SUBSCRIBER *)
0x180045e8b  jmp     short loc_180045EB8
0x180045e8d  mov     edi, 80070002h
0x180045e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e99  cmp     rcx, rsi
0x180045e9c  jz      short loc_180045EB8
0x180045e9e  test    [rcx+1Ch], r13d
0x180045ea2  jz      short loc_180045EB8
0x180045ea4  mov     rcx, [rcx+10h]
0x180045ea8  mov     edx, 54h ; 'T'
0x180045ead  mov     r9, r14
0x180045eb0  mov     r8, rbp
0x180045eb3  call    WPP_SF_S
0x180045eb8  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045ebf  call    cs:__imp_LeaveCriticalSection
0x180045ec5  test    edi, edi
0x180045ec7  jz      short loc_180045EF7
0x180045ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ed0  cmp     rcx, rsi
0x180045ed3  jz      short loc_180045EF7
0x180045ed5  test    byte ptr [rcx+1Ch], 1
0x180045ed9  jz      short loc_180045EF7
0x180045edb  mov     rcx, [rcx+10h]
0x180045edf  lea     r9, aHrremovesubscr; "HrRemoveSubscriber"
0x180045ee6  mov     edx, 55h ; 'U'
0x180045eeb  mov     dword ptr [rsp+78h+var_58], edi
0x180045eef  mov     r8, rbp
0x180045ef2  call    WPP_SF_sd
0x180045ef7  mov     eax, edi
0x180045ef9  add     rsp, 38h
0x180045efd  pop     r15
0x180045eff  pop     r14
0x180045f01  pop     r13
0x180045f03  pop     r12
0x180045f05  pop     rdi
0x180045f06  pop     rsi
0x180045f07  pop     rbp
0x180045f08  pop     rbx
0x180045f09  retn
```
