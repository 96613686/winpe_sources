# CWerService::Handler(ulong,ulong,void *)

- ea: `0x1800154e4`
- end: `0x1800157ae`
- name: `?Handler@CWerService@@AEAAKKKPEAX@Z`
- size: `714`
- prototype: `__int64 __fastcall(CWerService *this, int, __int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180018a30`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x1800154e4`
- `0x18001d7c0`
- `0x18001d92c`
- `0x18001e47c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015721`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800154fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800154fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001577d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001577d`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800155f2`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001569b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180015717`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800155f2`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001569b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180015717`

## pseudocode

```c
__int64 __fastcall CWerService::Handler(CWerService *this, int a2, __int64 a3, void *a4)
{
  __int64 v6; // r8
  int v7; // ebx
  int v8; // esi
  int v9; // esi
  int v10; // esi
  int v11; // esi
  int v12; // eax
  signed int LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  signed int v16; // eax
  signed int v17; // eax
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+20h] [rbp-18h]

  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  if ( !*((_QWORD *)this + 38) )
  {
    v7 = -2147023834;
    goto LABEL_48;
  }
  v7 = 0;
  v8 = a2 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 != 28 )
          {
            v7 = -2147024776;
            goto LABEL_48;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v6, *((unsigned int *)this + 53), lpCriticalSection);
          v12 = *((_DWORD *)this + 53);
          if ( (v12 & 1) != 0 )
          {
            v7 = -2147023781;
          }
          else
          {
            *((_DWORD *)this + 53) = v12 | 2;
            if ( *((_DWORD *)this + 78) == 7 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
              v7 = CWerService::_SetServiceStatus(this, 5u);
              if ( v7 >= 0
                && !TrySubmitThreadpoolCallback(
                      CWerService::StaticContinueWorkItem,
                      this,
                      (PTP_CALLBACK_ENVIRON)((char *)this + 232)) )
              {
                LastError = GetLastError();
                v7 = LastError;
                if ( LastError > 0 )
                  v7 = (unsigned __int16)LastError | 0x80070000;
                if ( v7 >= 0 )
                  v7 = -2147467259;
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v15 = 40;
LABEL_26:
                  WPP_SF_d(v14[2], v15, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)v7);
                }
              }
            }
          }
        }
        else
        {
          CWerService::_SetServiceStatus(this, *((_DWORD *)this + 78));
        }
      }
      else
      {
        v7 = CWerService::_SetServiceStatus(this, 5u);
        if ( v7 >= 0
          && !TrySubmitThreadpoolCallback(
                CWerService::StaticContinueWorkItem,
                this,
                (PTP_CALLBACK_ENVIRON)((char *)this + 232)) )
        {
          v16 = GetLastError();
          v7 = v16;
          if ( v16 > 0 )
            v7 = (unsigned __int16)v16 | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147467259;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 37;
            goto LABEL_26;
          }
        }
      }
    }
    else
    {
      v7 = CWerService::_SetServiceStatus(this, 6u);
      if ( v7 >= 0
        && !TrySubmitThreadpoolCallback(
              CWerService::StaticPauseWorkItem,
              this,
              (PTP_CALLBACK_ENVIRON)((char *)this + 232)) )
      {
        v17 = GetLastError();
        v7 = v17;
        if ( v17 > 0 )
          v7 = (unsigned __int16)v17 | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2147467259;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 36;
          goto LABEL_26;
        }
      }
    }
  }
  else
  {
    CWerService::_SignalStop((HANDLE *)this);
  }
LABEL_48:
  LeaveCriticalSection(lpCriticalSection);
  if ( v7 < 0 )
  {
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v7;
  }
  else
  {
    return 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800154e4  mov     [rsp+arg_0], rbx
0x1800154e9  mov     [rsp+arg_8], rsi
0x1800154ee  push    rdi
0x1800154ef  sub     rsp, 30h
0x1800154f3  mov     esi, edx
0x1800154f5  mov     rdi, rcx
0x1800154f8  mov     [rsp+38h+lpCriticalSection], rcx
0x1800154fd  call    cs:__imp_EnterCriticalSection
0x180015503  mov     [rsp+38h+var_10], 1
0x180015508  cmp     qword ptr [rdi+130h], 0
0x180015510  jnz     short loc_18001551C
0x180015512  mov     ebx, 80070426h
0x180015517  jmp     loc_180015778
0x18001551c  xor     ebx, ebx
0x18001551e  sub     esi, 1
0x180015521  jz      loc_180015763
0x180015527  sub     esi, 1
0x18001552a  jz      loc_1800156F3
0x180015530  sub     esi, 1
0x180015533  jz      loc_180015673
0x180015539  sub     esi, 1
0x18001553c  jz      loc_180015660
0x180015542  cmp     esi, 1Ch
0x180015545  jz      short loc_180015551
0x180015547  mov     ebx, 80070078h
0x18001554c  jmp     loc_180015778
0x180015551  lea     rsi, WPP_GLOBAL_Control
0x180015558  mov     rcx, cs:WPP_GLOBAL_Control
0x18001555f  cmp     rcx, rsi
0x180015562  jz      short loc_18001557F
0x180015564  test    byte ptr [rcx+1Ch], 8
0x180015568  jz      short loc_18001557F
0x18001556a  mov     edx, 26h ; '&'
0x18001556f  mov     r9d, [rdi+0D4h]
0x180015576  mov     rcx, [rcx+10h]
0x18001557a  call    WPP_SF_L
0x18001557f  mov     eax, [rdi+0D4h]
0x180015585  test    al, 1
0x180015587  jnz     loc_180015656
0x18001558d  or      eax, 2
0x180015590  mov     [rdi+0D4h], eax
0x180015596  cmp     dword ptr [rdi+138h], 7
0x18001559d  jnz     loc_180015778
0x1800155a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155aa  cmp     rcx, rsi
0x1800155ad  jz      short loc_1800155CA
0x1800155af  test    byte ptr [rcx+1Ch], 8
0x1800155b3  jz      short loc_1800155CA
0x1800155b5  mov     edx, 27h ; '''
0x1800155ba  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800155c1  mov     rcx, [rcx+10h]
0x1800155c5  call    WPP_SF_
0x1800155ca  mov     edx, 5; unsigned int
0x1800155cf  mov     rcx, rdi; this
0x1800155d2  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x1800155d7  mov     ebx, eax
0x1800155d9  test    eax, eax
0x1800155db  js      loc_180015778
0x1800155e1  lea     r8, [rdi+0E8h]; pcbe
0x1800155e8  mov     rdx, rdi; pv
0x1800155eb  lea     rcx, ?StaticContinueWorkItem@CWerService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x1800155f2  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800155f8  test    eax, eax
0x1800155fa  jnz     loc_180015778
0x180015600  call    cs:__imp_GetLastError
0x180015606  mov     ebx, eax
0x180015608  test    eax, eax
0x18001560a  jle     short loc_180015615
0x18001560c  movzx   ebx, ax
0x18001560f  or      ebx, 80070000h
0x180015615  mov     eax, 80004005h
0x18001561a  test    ebx, ebx
0x18001561c  cmovns  ebx, eax
0x18001561f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015626  cmp     rcx, rsi
0x180015629  jz      loc_180015778
0x18001562f  test    byte ptr [rcx+1Ch], 1
0x180015633  jz      loc_180015778
0x180015639  mov     edx, 28h ; '('
0x18001563e  mov     r9d, ebx
0x180015641  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180015648  mov     rcx, [rcx+10h]
0x18001564c  call    WPP_SF_d
0x180015651  jmp     loc_180015778
0x180015656  mov     ebx, 8007045Bh
0x18001565b  jmp     loc_180015778
0x180015660  mov     edx, [rdi+138h]; unsigned int
0x180015666  mov     rcx, rdi; this
0x180015669  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x18001566e  jmp     loc_180015778
0x180015673  mov     edx, 5; unsigned int
0x180015678  mov     rcx, rdi; this
0x18001567b  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x180015680  mov     ebx, eax
0x180015682  test    eax, eax
0x180015684  js      loc_180015778
0x18001568a  lea     r8, [rdi+0E8h]; pcbe
0x180015691  mov     rdx, rdi; pv
0x180015694  lea     rcx, ?StaticContinueWorkItem@CWerService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001569b  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800156a1  test    eax, eax
0x1800156a3  jnz     loc_180015778
0x1800156a9  call    cs:__imp_GetLastError
0x1800156af  mov     ebx, eax
0x1800156b1  test    eax, eax
0x1800156b3  jle     short loc_1800156BE
0x1800156b5  movzx   ebx, ax
0x1800156b8  or      ebx, 80070000h
0x1800156be  mov     eax, 80004005h
0x1800156c3  test    ebx, ebx
0x1800156c5  cmovns  ebx, eax
0x1800156c8  lea     rsi, WPP_GLOBAL_Control
0x1800156cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156d6  cmp     rcx, rsi
0x1800156d9  jz      loc_180015778
0x1800156df  test    byte ptr [rcx+1Ch], 1
0x1800156e3  jz      loc_180015778
0x1800156e9  mov     edx, 25h ; '%'
0x1800156ee  jmp     loc_18001563E
0x1800156f3  mov     edx, 6; unsigned int
0x1800156f8  mov     rcx, rdi; this
0x1800156fb  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x180015700  mov     ebx, eax
0x180015702  test    eax, eax
0x180015704  js      short loc_180015778
0x180015706  lea     r8, [rdi+0E8h]; pcbe
0x18001570d  mov     rdx, rdi; pv
0x180015710  lea     rcx, ?StaticPauseWorkItem@CWerService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180015717  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001571d  test    eax, eax
0x18001571f  jnz     short loc_180015778
0x180015721  call    cs:__imp_GetLastError
0x180015727  mov     ebx, eax
0x180015729  test    eax, eax
0x18001572b  jle     short loc_180015736
0x18001572d  movzx   ebx, ax
0x180015730  or      ebx, 80070000h
0x180015736  mov     eax, 80004005h
0x18001573b  test    ebx, ebx
0x18001573d  cmovns  ebx, eax
0x180015740  lea     rsi, WPP_GLOBAL_Control
0x180015747  mov     rcx, cs:WPP_GLOBAL_Control
0x18001574e  cmp     rcx, rsi
0x180015751  jz      short loc_180015778
0x180015753  test    byte ptr [rcx+1Ch], 1
0x180015757  jz      short loc_180015778
0x180015759  mov     edx, 24h ; '$'
0x18001575e  jmp     loc_18001563E
0x180015763  lea     rdx, [rsp+38h+lpCriticalSection]
0x180015768  mov     rcx, rdi
0x18001576b  call    ?_SignalStop@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_SignalStop(utl::unique_lock<utl::recursive_mutex> &)
0x180015770  cmp     [rsp+38h+var_10], bl
0x180015774  jnz     short loc_180015778
0x180015776  int     2Ch; Windows NT - assertion failure
0x180015778  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x18001577d  call    cs:__imp_LeaveCriticalSection
0x180015783  test    ebx, ebx
0x180015785  js      short loc_18001578B
0x180015787  xor     ebx, ebx
0x180015789  jmp     short loc_18001579C
0x18001578b  mov     eax, ebx
0x18001578d  and     eax, 1FFF0000h
0x180015792  cmp     eax, 70000h
0x180015797  jnz     short loc_18001579C
0x180015799  movzx   ebx, bx
0x18001579c  mov     eax, ebx
0x18001579e  mov     rbx, [rsp+38h+arg_0]
0x1800157a3  mov     rsi, [rsp+38h+arg_8]
0x1800157a8  add     rsp, 30h
0x1800157ac  pop     rdi
0x1800157ad  retn
```
