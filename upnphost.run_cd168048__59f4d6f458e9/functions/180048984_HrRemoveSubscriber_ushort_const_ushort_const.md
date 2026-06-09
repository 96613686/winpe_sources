# HrRemoveSubscriber(ushort const *,ushort const *)

- ea: `0x180048984`
- end: `0x180048bc1`
- name: `?HrRemoveSubscriber@@YAJPEBG0@Z`
- size: `573`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180033040`
- `0x180035fd0`

## callees

- `0x1800200f4`
- `0x1800209c8`
- `0x180027ca4`
- `0x18003b210`
- `0x18003b904`
- `0x180048984`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048a62`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048a62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048b6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048b6f`

## string_xrefs

- `0x1800489c6`: `HrRemoveSubscriber`
- `0x180048b95`: `HrRemoveSubscriber`

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
0x180048984  push    rbx
0x180048986  push    rbp
0x180048987  push    rsi
0x180048988  push    rdi
0x180048989  push    r12
0x18004898b  push    r13
0x18004898d  push    r14
0x18004898f  push    r15
0x180048991  sub     rsp, 38h
0x180048995  cmp     cs:?g_fEventApiInitialized@@3HA, 0; int g_fEventApiInitialized
0x18004899c  mov     r12, rdx
0x18004899f  mov     r14, rcx
0x1800489a2  jnz     short loc_1800489E9
0x1800489a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800489ab  lea     rsi, WPP_GLOBAL_Control
0x1800489b2  mov     ebx, 80004005h
0x1800489b7  cmp     rcx, rsi
0x1800489ba  jz      short loc_1800489E2
0x1800489bc  test    byte ptr [rcx+1Ch], 1
0x1800489c0  jz      short loc_1800489E2
0x1800489c2  mov     rcx, [rcx+10h]
0x1800489c6  lea     r9, aHrremovesubscr; "HrRemoveSubscriber"
0x1800489cd  mov     edx, 4Fh ; 'O'
0x1800489d2  mov     dword ptr [rsp+78h+var_58], ebx
0x1800489d6  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x1800489dd  call    WPP_SF_sd
0x1800489e2  mov     eax, ebx
0x1800489e4  jmp     loc_180048BAF
0x1800489e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800489f0  lea     rsi, WPP_GLOBAL_Control
0x1800489f7  lea     rbp, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x1800489fe  mov     r13d, 800h
0x180048a04  cmp     rcx, rsi
0x180048a07  jz      short loc_180048A28
0x180048a09  test    [rcx+1Ch], r13d
0x180048a0d  jz      short loc_180048A28
0x180048a0f  mov     rcx, [rcx+10h]
0x180048a13  mov     edx, 50h ; 'P'
0x180048a18  mov     r9, r12
0x180048a1b  mov     [rsp+78h+var_58], r14
0x180048a20  mov     r8, rbp
0x180048a23  call    WPP_SF_SS
0x180048a28  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180048a2f  call    cs:__imp_EnterCriticalSection
0x180048a36  nop     dword ptr [rax+rax+00h]
0x180048a3b  mov     rcx, r14; unsigned __int16 *
0x180048a3e  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180048a43  mov     rdi, rax
0x180048a46  test    rax, rax
0x180048a49  jz      loc_180048B3D
0x180048a4f  mov     r15, [rax+10h]
0x180048a53  mov     rbx, r15
0x180048a56  test    r15, r15
0x180048a59  jz      short loc_180048A81
0x180048a5b  mov     rcx, [rbx+28h]
0x180048a5f  mov     rdx, r12
0x180048a62  call    cs:__imp__o__wcsicmp
0x180048a69  nop     dword ptr [rax+rax+00h]
0x180048a6e  test    eax, eax
0x180048a70  jz      short loc_180048ABE
0x180048a72  mov     r15, rbx
0x180048a75  mov     rbx, [rbx+110h]
0x180048a7c  test    rbx, rbx
0x180048a7f  jnz     short loc_180048A5B
0x180048a81  mov     edi, 80070002h
0x180048a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180048a8d  cmp     rcx, rsi
0x180048a90  jz      loc_180048B68
0x180048a96  test    [rcx+1Ch], r13d
0x180048a9a  jz      loc_180048B68
0x180048aa0  mov     rcx, [rcx+10h]
0x180048aa4  mov     edx, 53h ; 'S'
0x180048aa9  mov     r9, r12
0x180048aac  mov     [rsp+78h+var_58], r14
0x180048ab1  mov     r8, rbp
0x180048ab4  call    WPP_SF_SS
0x180048ab9  jmp     loc_180048B68
0x180048abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180048ac5  cmp     rcx, rsi
0x180048ac8  jz      short loc_180048AED
0x180048aca  test    [rcx+1Ch], r13d
0x180048ace  jz      short loc_180048AED
0x180048ad0  mov     rax, [rdi]
0x180048ad3  mov     edx, 51h ; 'Q'
0x180048ad8  mov     r9, [rbx+28h]
0x180048adc  mov     r8, rbp
0x180048adf  mov     rcx, [rcx+10h]
0x180048ae3  mov     [rsp+78h+var_58], rax
0x180048ae8  call    WPP_SF_SS
0x180048aed  mov     rax, [rbx+110h]
0x180048af4  cmp     rbx, [rdi+10h]
0x180048af8  jnz     short loc_180048B00
0x180048afa  mov     [rdi+10h], rax
0x180048afe  jmp     short loc_180048B07
0x180048b00  mov     [r15+110h], rax
0x180048b07  dec     dword ptr [rdi+8]
0x180048b0a  xor     edi, edi
0x180048b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b13  cmp     rcx, rsi
0x180048b16  jz      short loc_180048B30
0x180048b18  test    [rcx+1Ch], r13d
0x180048b1c  jz      short loc_180048B30
0x180048b1e  mov     rcx, [rcx+10h]
0x180048b22  lea     edx, [rdi+52h]
0x180048b25  mov     r9, r12
0x180048b28  mov     r8, rbp
0x180048b2b  call    WPP_SF_S
0x180048b30  mov     rcx, rbx; struct UPNP_SUBSCRIBER *
0x180048b33  mov     [rbx], rdi
0x180048b36  call    ?QueueOrExecuteSubscriptionDeletion@@YAXPEAUUPNP_SUBSCRIBER@@@Z; QueueOrExecuteSubscriptionDeletion(UPNP_SUBSCRIBER *)
0x180048b3b  jmp     short loc_180048B68
0x180048b3d  mov     edi, 80070002h
0x180048b42  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b49  cmp     rcx, rsi
0x180048b4c  jz      short loc_180048B68
0x180048b4e  test    [rcx+1Ch], r13d
0x180048b52  jz      short loc_180048B68
0x180048b54  mov     rcx, [rcx+10h]
0x180048b58  mov     edx, 54h ; 'T'
0x180048b5d  mov     r9, r14
0x180048b60  mov     r8, rbp
0x180048b63  call    WPP_SF_S
0x180048b68  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180048b6f  call    cs:__imp_LeaveCriticalSection
0x180048b76  nop     dword ptr [rax+rax+00h]
0x180048b7b  test    edi, edi
0x180048b7d  jz      short loc_180048BAD
0x180048b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b86  cmp     rcx, rsi
0x180048b89  jz      short loc_180048BAD
0x180048b8b  test    byte ptr [rcx+1Ch], 1
0x180048b8f  jz      short loc_180048BAD
0x180048b91  mov     rcx, [rcx+10h]
0x180048b95  lea     r9, aHrremovesubscr; "HrRemoveSubscriber"
0x180048b9c  mov     edx, 55h ; 'U'
0x180048ba1  mov     dword ptr [rsp+78h+var_58], edi
0x180048ba5  mov     r8, rbp
0x180048ba8  call    WPP_SF_sd
0x180048bad  mov     eax, edi
0x180048baf  add     rsp, 38h
0x180048bb3  pop     r15
0x180048bb5  pop     r14
0x180048bb7  pop     r13
0x180048bb9  pop     r12
0x180048bbb  pop     rdi
0x180048bbc  pop     rsi
0x180048bbd  pop     rbp
0x180048bbe  pop     rbx
0x180048bbf  retn
```
