# CRWLock2T<CEmptyType>::ReleaseLockEx(void)

- ea: `0x180004340`
- end: `0x1800044d0`
- name: `?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ`
- size: `400`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003020`
- `0x1800050f0`
- `0x18001c300`
- `0x18001c470`
- `0x18001c5e0`
- `0x18001c750`
- `0x18001c8c0`
- `0x18001f5f0`
- `0x18001f760`

## callees

- `0x180004340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800043be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800043be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800044bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800044bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000442b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004469`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000442b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004469`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004350`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004350`

## pseudocode

```c
void __fastcall CRWLock2T<CEmptyType>::ReleaseLockEx(__int64 a1)
{
  DWORD CurrentThreadId; // r15d
  bool v3; // zf
  LONG v4; // edi
  int v5; // eax
  _DWORD *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rax

  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( !*(_DWORD *)(a1 + 76) )
  {
    if ( *(_DWORD *)(a1 + 80) == CurrentThreadId )
    {
      v6 = (_DWORD *)(a1 + 80);
    }
    else
    {
      if ( !*(_QWORD *)(a1 + 88) )
        RaiseException(0xC0000264, 0, 0, 0);
      v6 = 0;
      if ( !*(_DWORD *)(a1 + 96) )
        goto LABEL_19;
      v7 = *(_QWORD *)(a1 + 88);
      v8 = 0;
      while ( *(_DWORD *)(v7 + 8 * v8) != CurrentThreadId )
      {
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= *(_DWORD *)(a1 + 96) )
          goto LABEL_19;
      }
      v6 = (_DWORD *)(v7 + 8 * v8);
      if ( !v6 )
LABEL_19:
        RaiseException(0xC0000264, 0, 0, 0);
    }
    v3 = v6[1]-- == 1;
    if ( v3 )
    {
      *v6 = 0;
      v3 = (*(_DWORD *)(a1 + 64))-- == 1;
      if ( v3 )
      {
        v5 = *(_DWORD *)(a1 + 72);
        if ( v5 )
        {
          *(_DWORD *)(a1 + 76) = 1;
          *(_DWORD *)(a1 + 80) = 1;
          goto LABEL_24;
        }
      }
    }
LABEL_8:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    return;
  }
  v3 = (*(_DWORD *)(a1 + 84))-- == 1;
  if ( !v3 )
    goto LABEL_8;
  --*(_DWORD *)(a1 + 64);
  v4 = *(_DWORD *)(a1 + 68);
  *(_DWORD *)(a1 + 80) = 0;
  if ( v4 )
  {
    *(_DWORD *)(a1 + 76) = 0;
    *(_DWORD *)(a1 + 64) = v4;
    *(_DWORD *)(a1 + 68) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    ReleaseSemaphore(*(HANDLE *)(a1 + 56), v4, 0);
    return;
  }
  v5 = *(_DWORD *)(a1 + 72);
  if ( !v5 )
  {
    *(_DWORD *)(a1 + 76) = 0;
    goto LABEL_8;
  }
  *(_DWORD *)(a1 + 80) = 1;
LABEL_24:
  *(_DWORD *)(a1 + 84) = 1;
  *(_DWORD *)(a1 + 72) = v5 - 1;
  *(_DWORD *)(a1 + 64) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  SetEvent(*(HANDLE *)(a1 + 48));
}

```

## disassembly

```asm
0x180004340  push    rbx
0x180004342  push    rbp
0x180004343  push    rsi
0x180004344  push    rdi
0x180004345  push    r14
0x180004347  push    r15
0x180004349  sub     rsp, 28h
0x18000434d  mov     rbx, rcx
0x180004350  call    cs:__imp_GetCurrentThreadId
0x180004357  nop     dword ptr [rax+rax+00h]
0x18000435c  lea     rbp, [rbx+8]
0x180004360  mov     r15d, eax
0x180004363  mov     rcx, rbp; lpCriticalSection
0x180004366  call    cs:__imp_EnterCriticalSection
0x18000436d  nop     dword ptr [rax+rax+00h]
0x180004372  cmp     dword ptr [rbx+4Ch], 0
0x180004376  jz      loc_180004404
0x18000437c  or      ecx, 0FFFFFFFFh
0x18000437f  add     [rbx+54h], ecx
0x180004382  jnz     short loc_1800043E7
0x180004384  add     [rbx+40h], ecx
0x180004387  mov     edi, [rbx+44h]
0x18000438a  mov     dword ptr [rbx+50h], 0
0x180004391  test    edi, edi
0x180004393  jz      short loc_1800043CC
0x180004395  mov     rcx, rbp; lpCriticalSection
0x180004398  mov     dword ptr [rbx+4Ch], 0
0x18000439f  mov     [rbx+40h], edi
0x1800043a2  mov     dword ptr [rbx+44h], 0
0x1800043a9  call    cs:__imp_LeaveCriticalSection
0x1800043b0  nop     dword ptr [rax+rax+00h]
0x1800043b5  mov     rcx, [rbx+38h]; hSemaphore
0x1800043b9  xor     r8d, r8d; lpPreviousCount
0x1800043bc  mov     edx, edi; lReleaseCount
0x1800043be  call    cs:__imp_ReleaseSemaphore
0x1800043c5  nop     dword ptr [rax+rax+00h]
0x1800043ca  jmp     short loc_1800043F6
0x1800043cc  mov     eax, [rbx+48h]
0x1800043cf  test    eax, eax
0x1800043d1  jz      short loc_1800043E0
0x1800043d3  mov     esi, 1
0x1800043d8  mov     [rbx+50h], esi
0x1800043db  jmp     loc_1800044A1
0x1800043e0  mov     dword ptr [rbx+4Ch], 0
0x1800043e7  mov     rcx, rbp; lpCriticalSection
0x1800043ea  call    cs:__imp_LeaveCriticalSection
0x1800043f1  nop     dword ptr [rax+rax+00h]
0x1800043f6  add     rsp, 28h
0x1800043fa  pop     r15
0x1800043fc  pop     r14
0x1800043fe  pop     rdi
0x1800043ff  pop     rsi
0x180004400  pop     rbp
0x180004401  pop     rbx
0x180004402  retn
0x180004404  lea     r14, [rbx+50h]
0x180004408  mov     esi, 1
0x18000440d  cmp     [r14], r15d
0x180004410  jnz     short loc_180004417
0x180004412  mov     rdi, r14
0x180004415  jmp     short loc_180004475
0x180004417  cmp     qword ptr [rbx+58h], 0
0x18000441c  jnz     short loc_180004437
0x18000441e  xor     r9d, r9d; lpArguments
0x180004421  xor     r8d, r8d; nNumberOfArguments
0x180004424  xor     edx, edx; dwExceptionFlags
0x180004426  mov     ecx, 0C0000264h; dwExceptionCode
0x18000442b  call    cs:__imp_RaiseException
0x180004432  nop     dword ptr [rax+rax+00h]
0x180004437  xor     edi, edi
0x180004439  cmp     [rbx+60h], edi
0x18000443c  jbe     short loc_18000445C
0x18000443e  mov     rdx, [rbx+58h]
0x180004442  xor     eax, eax
0x180004444  cmp     [rdx+rax*8], r15d
0x180004448  jz      short loc_180004453
0x18000444a  add     eax, esi
0x18000444c  cmp     eax, [rbx+60h]
0x18000444f  jb      short loc_180004444
0x180004451  jmp     short loc_18000445C
0x180004453  lea     rdi, [rdx+rax*8]
0x180004457  test    rdi, rdi
0x18000445a  jnz     short loc_180004475
0x18000445c  xor     r9d, r9d; lpArguments
0x18000445f  xor     r8d, r8d; nNumberOfArguments
0x180004462  xor     edx, edx; dwExceptionFlags
0x180004464  mov     ecx, 0C0000264h; dwExceptionCode
0x180004469  call    cs:__imp_RaiseException
0x180004470  nop     dword ptr [rax+rax+00h]
0x180004475  or      ecx, 0FFFFFFFFh
0x180004478  add     [rdi+4], ecx
0x18000447b  jnz     loc_1800043E7
0x180004481  mov     dword ptr [rdi], 0
0x180004487  add     [rbx+40h], ecx
0x18000448a  jnz     loc_1800043E7
0x180004490  mov     eax, [rbx+48h]
0x180004493  test    eax, eax
0x180004495  jz      loc_1800043E7
0x18000449b  mov     [rbx+4Ch], esi
0x18000449e  mov     [r14], esi
0x1800044a1  dec     eax
0x1800044a3  mov     [rbx+54h], esi
0x1800044a6  mov     rcx, rbp; lpCriticalSection
0x1800044a9  mov     [rbx+48h], eax
0x1800044ac  mov     [rbx+40h], esi
0x1800044af  call    cs:__imp_LeaveCriticalSection
0x1800044b6  nop     dword ptr [rax+rax+00h]
0x1800044bb  mov     rcx, [rbx+30h]; hEvent
0x1800044bf  call    cs:__imp_SetEvent
0x1800044c6  nop     dword ptr [rax+rax+00h]
0x1800044cb  jmp     loc_1800043F6
```
