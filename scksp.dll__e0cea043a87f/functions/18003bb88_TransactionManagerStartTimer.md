# TransactionManagerStartTimer

- ea: `0x18003bb88`
- end: `0x18003bc90`
- name: `TransactionManagerStartTimer`
- size: `264`
- prototype: `__int64 __fastcall(struct _CARD_STATE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001594c`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x18003b920`
- `0x18003bb88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc1f`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18003bbe9`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18003bbe9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003bc3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003bc3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bc0d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003bc0d`

## pseudocode

```c
__int64 __fastcall TransactionManagerStartTimer(struct _CARD_STATE *a1)
{
  PFILETIME v1; // rsi
  DWORD LastError; // edi
  struct _TP_TIMER *v4; // rcx
  __int64 v5; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax

  v1 = g_pTransactionManagerState;
  LastError = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids, WPP_pszIndent);
  }
  v4 = (struct _TP_TIMER *)*((_QWORD *)a1 + 75);
  if ( !v4 || !IsThreadpoolTimerSet(v4) )
  {
    ThreadpoolTimer = (struct _TP_TIMER *)*((_QWORD *)a1 + 75);
    if ( ThreadpoolTimer
      || (ThreadpoolTimer = CreateThreadpoolTimer(TransactionManagerTimeoutHandler, a1, (PTP_CALLBACK_ENVIRON)&v1[2]),
          (*((_QWORD *)a1 + 75) = ThreadpoolTimer) != 0) )
    {
      SetThreadpoolTimer(ThreadpoolTimer, v1, 0, 0);
    }
    else
    {
      LastError = GetLastError();
      TransactionManagerForceEndTransaction(a1);
    }
  }
  WppTraceIndent(v5, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003bb88  push    rbx
0x18003bb8a  push    rbp
0x18003bb8b  push    rsi
0x18003bb8c  push    rdi
0x18003bb8d  sub     rsp, 38h
0x18003bb91  mov     rsi, cs:?g_pTransactionManagerState@@3PEAU_TRANSACTION_MANAGER_STATE@@EA; _TRANSACTION_MANAGER_STATE * g_pTransactionManagerState
0x18003bb98  xor     edi, edi
0x18003bb9a  xor     edx, edx
0x18003bb9c  mov     rbx, rcx
0x18003bb9f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003bba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bbab  lea     rbp, WPP_GLOBAL_Control
0x18003bbb2  cmp     rcx, rbp
0x18003bbb5  jz      short loc_18003BBDD
0x18003bbb7  test    byte ptr [rcx+1Ch], 2
0x18003bbbb  jz      short loc_18003BBDD
0x18003bbbd  cmp     byte ptr [rcx+19h], 5
0x18003bbc1  jb      short loc_18003BBDD
0x18003bbc3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003bbca  lea     edx, [rdi+20h]
0x18003bbcd  mov     rcx, [rcx+10h]
0x18003bbd1  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18003bbd8  call    WPP_SF_s
0x18003bbdd  mov     rcx, [rbx+258h]; pti
0x18003bbe4  test    rcx, rcx
0x18003bbe7  jz      short loc_18003BBF3
0x18003bbe9  call    cs:__imp_IsThreadpoolTimerSet
0x18003bbef  test    eax, eax
0x18003bbf1  jnz     short loc_18003BC43
0x18003bbf3  mov     rax, [rbx+258h]
0x18003bbfa  test    rax, rax
0x18003bbfd  jnz     short loc_18003BC31
0x18003bbff  lea     r8, [rsi+10h]; pcbe
0x18003bc03  mov     rdx, rbx; pv
0x18003bc06  lea     rcx, ?TransactionManagerTimeoutHandler@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003bc0d  call    cs:__imp_CreateThreadpoolTimer
0x18003bc13  mov     [rbx+258h], rax
0x18003bc1a  test    rax, rax
0x18003bc1d  jnz     short loc_18003BC31
0x18003bc1f  call    cs:__imp_GetLastError
0x18003bc25  mov     rcx, rbx; struct _CARD_STATE *
0x18003bc28  mov     edi, eax
0x18003bc2a  call    TransactionManagerForceEndTransaction
0x18003bc2f  jmp     short loc_18003BC43
0x18003bc31  xor     r9d, r9d; msWindowLength
0x18003bc34  xor     r8d, r8d; msPeriod
0x18003bc37  mov     rdx, rsi; pftDueTime
0x18003bc3a  mov     rcx, rax; pti
0x18003bc3d  call    cs:__imp_SetThreadpoolTimer
0x18003bc43  mov     edx, 1
0x18003bc48  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003bc4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bc54  cmp     rcx, rbp
0x18003bc57  jz      short loc_18003BC85
0x18003bc59  test    byte ptr [rcx+1Ch], 2
0x18003bc5d  jz      short loc_18003BC85
0x18003bc5f  cmp     byte ptr [rcx+19h], 5
0x18003bc63  jb      short loc_18003BC85
0x18003bc65  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003bc6c  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18003bc73  mov     rcx, [rcx+10h]
0x18003bc77  mov     edx, 21h ; '!'
0x18003bc7c  mov     [rsp+58h+var_38], edi
0x18003bc80  call    WPP_SF_sd
0x18003bc85  mov     eax, edi
0x18003bc87  add     rsp, 38h
0x18003bc8b  pop     rdi
0x18003bc8c  pop     rsi
0x18003bc8d  pop     rbp
0x18003bc8e  pop     rbx
0x18003bc8f  retn
```
