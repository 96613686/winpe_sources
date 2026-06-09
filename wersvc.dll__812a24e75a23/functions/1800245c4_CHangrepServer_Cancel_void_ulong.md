# CHangrepServer::Cancel(void *,ulong)

- ea: `0x1800245c4`
- end: `0x18002477d`
- name: `?Cancel@CHangrepServer@@QEAAJPEAXK@Z`
- size: `441`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, HANDLE Process, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001a324`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x1800245c4`
- `0x180025aa0`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002461f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800246df`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002461f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800246df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002462b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002462b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024611`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024611`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002476a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002476a`

## pseudocode

```c
__int64 __fastcall CHangrepServer::Cancel(struct _RTL_CRITICAL_SECTION *this, HANDLE Process, unsigned int a3)
{
  DWORD ProcessId; // ebp
  signed int v7; // eax
  unsigned int v8; // ebx
  struct _RTL_CRITICAL_SECTION *HangrepInstanceForPid; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  DWORD v11; // edi
  HANDLE LockSemaphore; // rcx
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, a3);
  EnterCriticalSection(this);
  ProcessId = GetProcessId(Process);
  if ( ProcessId )
  {
    HangrepInstanceForPid = (struct _RTL_CRITICAL_SECTION *)CHangrepServer::_FindHangrepInstanceForPid(
                                                              (CHangrepServer *)this,
                                                              a3);
    v10 = HangrepInstanceForPid;
    if ( HangrepInstanceForPid )
    {
      v11 = 0;
      EnterCriticalSection(HangrepInstanceForPid);
      LockSemaphore = v10[8].LockSemaphore;
      if ( (unsigned __int64)LockSemaphore + 1 > 1 )
      {
        v11 = GetProcessId(LockSemaphore);
        if ( !v11 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids, LastError);
        }
      }
      LeaveCriticalSection(v10);
      if ( v11 == ProcessId )
      {
        CHungApp::Cancel((CHungApp *)v10, 0);
        v8 = 0;
      }
      else
      {
        v8 = -2147024891;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids);
      }
    }
    else
    {
      v8 = -2147024809;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, a3);
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids, v8);
  }
  LeaveCriticalSection(this);
  return v8;
}

```

## disassembly

```asm
0x1800245c4  push    rbx
0x1800245c6  push    rbp
0x1800245c7  push    rsi
0x1800245c8  push    rdi
0x1800245c9  push    r14
0x1800245cb  sub     rsp, 30h
0x1800245cf  mov     edi, r8d
0x1800245d2  mov     rbx, rdx
0x1800245d5  mov     rsi, rcx
0x1800245d8  lea     r14, WPP_GLOBAL_Control
0x1800245df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245e6  cmp     rcx, r14
0x1800245e9  jz      short loc_180024609
0x1800245eb  test    byte ptr [rcx+1Ch], 4
0x1800245ef  jz      short loc_180024609
0x1800245f1  mov     edx, 27h ; '''
0x1800245f6  mov     r9d, r8d
0x1800245f9  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180024600  mov     rcx, [rcx+10h]
0x180024604  call    WPP_SF_d
0x180024609  mov     [rsp+58h+var_38], rsi
0x18002460e  mov     rcx, rsi; lpCriticalSection
0x180024611  call    cs:__imp_EnterCriticalSection
0x180024617  mov     [rsp+58h+var_30], 1
0x18002461c  mov     rcx, rbx; Process
0x18002461f  call    cs:__imp_GetProcessId
0x180024625  mov     ebp, eax
0x180024627  test    eax, eax
0x180024629  jnz     short loc_180024677
0x18002462b  call    cs:__imp_GetLastError
0x180024631  mov     ebx, eax
0x180024633  test    eax, eax
0x180024635  jle     short loc_180024640
0x180024637  movzx   ebx, ax
0x18002463a  or      ebx, 80070000h
0x180024640  mov     rcx, cs:WPP_GLOBAL_Control
0x180024647  cmp     rcx, r14
0x18002464a  jz      loc_180024767
0x180024650  test    byte ptr [rcx+1Ch], 1
0x180024654  jz      loc_180024767
0x18002465a  mov     edx, 28h ; '('
0x18002465f  mov     r9d, ebx
0x180024662  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180024669  mov     rcx, [rcx+10h]
0x18002466d  call    WPP_SF_d
0x180024672  jmp     loc_180024767
0x180024677  mov     edx, edi; unsigned int
0x180024679  mov     rcx, rsi; this
0x18002467c  call    ?_FindHangrepInstanceForPid@CHangrepServer@@AEAAPEAVCHungApp@@K@Z; CHangrepServer::_FindHangrepInstanceForPid(ulong)
0x180024681  mov     rbx, rax
0x180024684  test    rax, rax
0x180024687  jnz     short loc_1800246C3
0x180024689  mov     ebx, 80070057h
0x18002468e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024695  cmp     rcx, r14
0x180024698  jz      loc_180024767
0x18002469e  test    byte ptr [rcx+1Ch], 1
0x1800246a2  jz      loc_180024767
0x1800246a8  lea     edx, [rax+29h]
0x1800246ab  mov     r9d, edi
0x1800246ae  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x1800246b5  mov     rcx, [rcx+10h]
0x1800246b9  call    WPP_SF_d
0x1800246be  jmp     loc_180024767
0x1800246c3  xor     edi, edi
0x1800246c5  mov     rcx, rbx; lpCriticalSection
0x1800246c8  call    cs:__imp_EnterCriticalSection
0x1800246ce  mov     rcx, [rbx+158h]; Process
0x1800246d5  lea     rax, [rcx+1]
0x1800246d9  cmp     rax, 1
0x1800246dd  jbe     short loc_180024720
0x1800246df  call    cs:__imp_GetProcessId
0x1800246e5  mov     edi, eax
0x1800246e7  test    eax, eax
0x1800246e9  jnz     short loc_180024720
0x1800246eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800246f2  cmp     rax, r14
0x1800246f5  jz      short loc_180024720
0x1800246f7  test    byte ptr [rax+1Ch], 1
0x1800246fb  jz      short loc_180024720
0x1800246fd  call    cs:__imp_GetLastError
0x180024703  lea     edx, [rdi+73h]
0x180024706  mov     r9d, eax
0x180024709  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x180024710  mov     rcx, cs:WPP_GLOBAL_Control
0x180024717  mov     rcx, [rcx+10h]
0x18002471b  call    WPP_SF_d
0x180024720  mov     rcx, rbx; lpCriticalSection
0x180024723  call    cs:__imp_LeaveCriticalSection
0x180024729  cmp     edi, ebp
0x18002472b  jz      short loc_18002475B
0x18002472d  mov     ebx, 80070005h
0x180024732  mov     rcx, cs:WPP_GLOBAL_Control
0x180024739  cmp     rcx, r14
0x18002473c  jz      short loc_180024767
0x18002473e  test    byte ptr [rcx+1Ch], 1
0x180024742  jz      short loc_180024767
0x180024744  mov     edx, 2Ah ; '*'
0x180024749  lea     r8, WPP_25a1d84fd68832a0b43896ccf2bf8d28_Traceguids
0x180024750  mov     rcx, [rcx+10h]
0x180024754  call    WPP_SF_
0x180024759  jmp     short loc_180024767
0x18002475b  xor     edx, edx; int
0x18002475d  mov     rcx, rbx; this
0x180024760  call    ?Cancel@CHungApp@@QEAAXH@Z; CHungApp::Cancel(int)
0x180024765  xor     ebx, ebx
0x180024767  mov     rcx, rsi; lpCriticalSection
0x18002476a  call    cs:__imp_LeaveCriticalSection
0x180024770  mov     eax, ebx
0x180024772  add     rsp, 30h
0x180024776  pop     r14
0x180024778  pop     rdi
0x180024779  pop     rsi
0x18002477a  pop     rbp
0x18002477b  pop     rbx
0x18002477c  retn
```
