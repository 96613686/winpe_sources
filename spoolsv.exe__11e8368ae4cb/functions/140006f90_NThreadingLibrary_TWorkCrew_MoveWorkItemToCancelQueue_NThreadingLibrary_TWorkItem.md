# NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)

- ea: `0x140006f90`
- end: `0x1400070fa`
- name: `?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z`
- size: `362`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, struct NThreadingLibrary::TWorkItem *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140006b30`
- `0x14000a2c0`
- `0x140051848`
- `0x140051ad0`
- `0x140051b80`

## callees

- `0x140006f90`
- `0x140007bdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007057`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400070e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007057`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400070e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000707f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000707f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006fa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006fa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006fae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006fae`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(
        NThreadingLibrary::TWorkCrew *this,
        struct NThreadingLibrary::TWorkItem *a2)
{
  int LastErrorAsHResult; // esi
  char *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r9
  __int64 v8; // rcx
  char *v11; // rcx

  LastErrorAsHResult = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  ++*((_DWORD *)this + 21);
  *((_DWORD *)this + 20) = GetCurrentThreadId();
  if ( !*((_DWORD *)a2 + 18) && *((_QWORD *)a2 + 10) )
  {
    *((_DWORD *)a2 + 18) = 1;
    v5 = (char *)a2 + 32;
    *(_QWORD *)(*((_QWORD *)a2 + 6) + 24LL) = *((_QWORD *)a2 + 7);
    *(_QWORD *)(*((_QWORD *)a2 + 7) + 16LL) = *((_QWORD *)a2 + 6);
    *((_QWORD *)a2 + 6) = (char *)a2 + 32;
    *((_QWORD *)a2 + 7) = (char *)a2 + 32;
    if ( !a2 )
      v5 = 0;
    if ( v5 )
    {
      v6 = *((_QWORD *)v5 + 2);
      if ( !v6 || !*((_QWORD *)v5 + 3) )
        LastErrorAsHResult = -2147467259;
      if ( LastErrorAsHResult >= 0 )
      {
        v7 = *((_QWORD *)this + 21);
        if ( (char *)v6 != v5 )
        {
          v11 = (char *)*((_QWORD *)v5 + 3);
          if ( v11 != v5 )
          {
            *(_QWORD *)(v6 + 24) = v11;
            *(_QWORD *)(*((_QWORD *)v5 + 3) + 16LL) = *((_QWORD *)v5 + 2);
            *((_QWORD *)v5 + 2) = v5;
            *((_QWORD *)v5 + 3) = v5;
          }
        }
        LastErrorAsHResult = 0;
        *(_QWORD *)(*(_QWORD *)(v7 + 16) + 24LL) = v5;
        *((_QWORD *)v5 + 2) = *(_QWORD *)(v7 + 16);
        *((_QWORD *)v5 + 3) = v7;
        *(_QWORD *)(v7 + 16) = v5;
      }
    }
    else
    {
      LastErrorAsHResult = -2147024809;
    }
    if ( !*((_DWORD *)this + 48) )
    {
      if ( SetEvent(*((HANDLE *)this + 23)) )
        LastErrorAsHResult = 0;
      else
        LastErrorAsHResult = GetLastErrorAsHResult(v8);
    }
    --*((_DWORD *)this + 50);
    if ( *((_DWORD *)this + 44) && !*((_DWORD *)this + 50) )
      SetEvent(*((HANDLE *)this + 26));
  }
  if ( (*((_DWORD *)this + 21))-- == 1 )
    *((_DWORD *)this + 20) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140006f90  push    rbx
0x140006f92  push    rbp
0x140006f93  push    rsi
0x140006f94  push    rdi
0x140006f95  sub     rsp, 28h
0x140006f99  mov     rdi, rcx
0x140006f9c  mov     rbp, rdx
0x140006f9f  add     rcx, 28h ; '('; lpCriticalSection
0x140006fa3  xor     esi, esi
0x140006fa5  call    cs:__imp_EnterCriticalSection
0x140006fab  inc     dword ptr [rdi+54h]
0x140006fae  call    cs:__imp_GetCurrentThreadId
0x140006fb4  mov     [rdi+50h], eax
0x140006fb7  cmp     [rbp+48h], esi
0x140006fba  jnz     loc_140007072
0x140006fc0  cmp     [rbp+50h], rsi
0x140006fc4  jz      loc_140007072
0x140006fca  mov     dword ptr [rbp+48h], 1
0x140006fd1  lea     rdx, [rbp+20h]
0x140006fd5  mov     rcx, [rdx+10h]
0x140006fd9  mov     rax, [rdx+18h]
0x140006fdd  mov     [rcx+18h], rax
0x140006fe1  mov     rax, [rdx+10h]
0x140006fe5  mov     rcx, [rdx+18h]
0x140006fe9  mov     [rcx+10h], rax
0x140006fed  xor     eax, eax
0x140006fef  test    rbp, rbp
0x140006ff2  mov     [rdx+10h], rdx
0x140006ff6  mov     [rdx+18h], rdx
0x140006ffa  cmovz   rdx, rax
0x140006ffe  test    rdx, rdx
0x140007001  jz      loc_1400070A8
0x140007007  mov     rax, [rdx+10h]
0x14000700b  test    rax, rax
0x14000700e  jnz     loc_140007099
0x140007014  mov     esi, 80004005h
0x140007019  test    esi, esi
0x14000701b  js      short loc_140007047
0x14000701d  mov     r9, [rdi+0A8h]
0x140007024  cmp     rax, rdx
0x140007027  jnz     loc_1400070AF
0x14000702d  mov     rax, [r9+10h]
0x140007031  xor     esi, esi
0x140007033  mov     [rax+18h], rdx
0x140007037  mov     rax, [r9+10h]
0x14000703b  mov     [rdx+10h], rax
0x14000703f  mov     [rdx+18h], r9
0x140007043  mov     [r9+10h], rdx
0x140007047  cmp     dword ptr [rdi+0C0h], 0
0x14000704e  jnz     short loc_140007063
0x140007050  mov     rcx, [rdi+0B8h]; hEvent
0x140007057  call    cs:__imp_SetEvent
0x14000705d  test    eax, eax
0x14000705f  jz      short loc_140007090
0x140007061  xor     esi, esi
0x140007063  dec     dword ptr [rdi+0C8h]
0x140007069  cmp     dword ptr [rdi+0B0h], 0
0x140007070  jnz     short loc_1400070D9
0x140007072  add     dword ptr [rdi+54h], 0FFFFFFFFh
0x140007076  mov     eax, [rdi+54h]
0x140007079  jz      short loc_1400070F1
0x14000707b  lea     rcx, [rdi+28h]; lpCriticalSection
0x14000707f  call    cs:__imp_LeaveCriticalSection
0x140007085  mov     eax, esi
0x140007087  add     rsp, 28h
0x14000708b  pop     rdi
0x14000708c  pop     rsi
0x14000708d  pop     rbp
0x14000708e  pop     rbx
0x14000708f  retn
0x140007090  call    GetLastErrorAsHResult
0x140007095  mov     esi, eax
0x140007097  jmp     short loc_140007063
0x140007099  cmp     [rdx+18h], rsi
0x14000709d  jnz     loc_140007019
0x1400070a3  jmp     loc_140007014
0x1400070a8  mov     esi, 80070057h
0x1400070ad  jmp     short loc_140007047
0x1400070af  mov     rcx, [rdx+18h]
0x1400070b3  cmp     rcx, rdx
0x1400070b6  jz      loc_14000702D
0x1400070bc  mov     [rax+18h], rcx
0x1400070c0  mov     rcx, [rdx+18h]
0x1400070c4  mov     rax, [rdx+10h]
0x1400070c8  mov     [rcx+10h], rax
0x1400070cc  mov     [rdx+10h], rdx
0x1400070d0  mov     [rdx+18h], rdx
0x1400070d4  jmp     loc_14000702D
0x1400070d9  cmp     dword ptr [rdi+0C8h], 0
0x1400070e0  jnz     short loc_140007072
0x1400070e2  mov     rcx, [rdi+0D0h]; hEvent
0x1400070e9  call    cs:__imp_SetEvent
0x1400070ef  jmp     short loc_140007072
0x1400070f1  mov     dword ptr [rdi+50h], 0
0x1400070f8  jmp     short loc_14000707B
```
