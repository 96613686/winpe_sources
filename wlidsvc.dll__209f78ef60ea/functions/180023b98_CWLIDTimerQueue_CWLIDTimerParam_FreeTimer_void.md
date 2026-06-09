# CWLIDTimerQueue::CWLIDTimerParam::FreeTimer(void)

- ea: `0x180023b98`
- end: `0x180023cfd`
- name: `?FreeTimer@CWLIDTimerParam@CWLIDTimerQueue@@QEAAXXZ`
- size: `357`
- prototype: `void __fastcall(CWLIDTimerQueue::CWLIDTimerParam *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180023b50`
- `0x1800a0ca0`

## callees

- `0x180019690`
- `0x180023b98`
- `0x180023d24`
- `0x1800a4784`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ce1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023bc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023bc8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023c26`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023c26`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180023c09`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180023c09`

## string_xrefs

- `0x180023ca0`: `DeleteTimerQueueTimer failed for Queue %p and timer %p with hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWLIDTimerQueue::CWLIDTimerParam::FreeTimer(CWLIDTimerQueue::CWLIDTimerParam *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  signed int LastError; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  signed int v7; // [rsp+30h] [rbp-38h]
  void *v8; // [rsp+40h] [rbp-28h] BYREF
  HANDLE Token; // [rsp+48h] [rbp-20h]
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+50h] [rbp-18h]
  char v11; // [rsp+58h] [rbp-10h]
  unsigned int pExceptionObject; // [rsp+70h] [rbp+8h] BYREF

  if ( *(_QWORD *)this )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      v3 = v2 + 2;
      v10 = v2 + 2;
      EnterCriticalSection(v2 + 2);
      v11 = 1;
      if ( *(_QWORD *)(*((_QWORD *)this + 1) + 48LL) )
      {
        LODWORD(v8) = 0;
        Token = 0;
        CAutoRevertToSelf::Revert(&v8, 0);
        if ( !DeleteTimerQueueTimer(*(HANDLE *)(*((_QWORD *)this + 1) + 48LL), *(HANDLE *)this, 0)
          && GetLastError() != 997 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v7 = LastError;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\Live\\identity\\Include\\TimerQueue.h",
            0x52u,
            L"DeleteTimerQueueTimer failed for Queue %p and timer %p with hr=0x%x",
            *(_QWORD *)(*((_QWORD *)this + 1) + 48LL),
            *(_QWORD *)this,
            v7);
        }
        if ( !(_DWORD)v8 )
          goto LABEL_8;
        if ( Token )
        {
          if ( !SetThreadToken(0, Token) )
          {
            v5 = GetLastError();
            v6 = v5;
            if ( v5 > 0 )
              v6 = (unsigned __int16)v5 | 0x80070000;
            if ( Token )
              CloseHandle(Token);
            pExceptionObject = v6;
            throw (long *)&pExceptionObject;
          }
LABEL_8:
          if ( Token )
            CloseHandle(Token);
        }
      }
      *(_QWORD *)this = 0;
      *((_QWORD *)this + 1) = 0;
      LeaveCriticalSection(v3);
    }
  }
}

```

## disassembly

```asm
0x180023b98  mov     [rsp+arg_8], rbx
0x180023b9d  push    rdi
0x180023b9e  sub     rsp, 60h
0x180023ba2  mov     rbx, rcx
0x180023ba5  cmp     qword ptr [rcx], 0
0x180023ba9  jz      loc_180023C5C
0x180023baf  mov     rax, [rcx+8]
0x180023bb3  test    rax, rax
0x180023bb6  jz      loc_180023C5C
0x180023bbc  lea     rdi, [rax+50h]
0x180023bc0  mov     [rsp+68h+var_18], rdi
0x180023bc5  mov     rcx, rdi; lpCriticalSection
0x180023bc8  call    cs:__imp_EnterCriticalSection
0x180023bce  mov     [rsp+68h+var_10], 1
0x180023bd3  mov     rax, [rbx+8]
0x180023bd7  cmp     qword ptr [rax+30h], 0
0x180023bdc  jz      short loc_180023C44
0x180023bde  mov     dword ptr [rsp+68h+var_28], 0
0x180023be6  mov     [rsp+68h+Token], 0
0x180023bef  xor     edx, edx; int
0x180023bf1  lea     rcx, [rsp+68h+var_28]; this
0x180023bf6  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x180023bfb  mov     rcx, [rbx+8]
0x180023bff  xor     r8d, r8d; CompletionEvent
0x180023c02  mov     rdx, [rbx]; Timer
0x180023c05  mov     rcx, [rcx+30h]; TimerQueue
0x180023c09  call    cs:__imp_DeleteTimerQueueTimer
0x180023c0f  test    eax, eax
0x180023c11  jz      short loc_180023C67
0x180023c13  cmp     dword ptr [rsp+68h+var_28], 0
0x180023c18  jz      short loc_180023C34
0x180023c1a  mov     rdx, [rsp+68h+Token]; Token
0x180023c1f  test    rdx, rdx
0x180023c22  jz      short loc_180023C44
0x180023c24  xor     ecx, ecx; Thread
0x180023c26  call    cs:__imp_SetThreadToken
0x180023c2c  test    eax, eax
0x180023c2e  jz      loc_180023CC2
0x180023c34  mov     rcx, [rsp+68h+Token]; hObject
0x180023c39  test    rcx, rcx
0x180023c3c  jz      short loc_180023C44
0x180023c3e  call    cs:__imp_CloseHandle
0x180023c44  mov     qword ptr [rbx], 0
0x180023c4b  mov     qword ptr [rbx+8], 0
0x180023c53  mov     rcx, rdi; lpCriticalSection
0x180023c56  call    cs:__imp_LeaveCriticalSection
0x180023c5c  mov     rbx, [rsp+68h+arg_8]
0x180023c61  add     rsp, 60h
0x180023c65  pop     rdi
0x180023c66  retn
0x180023c67  call    cs:__imp_GetLastError
0x180023c6d  nop
0x180023c6e  cmp     eax, 3E5h
0x180023c73  jz      short loc_180023C13
0x180023c75  call    cs:__imp_GetLastError
0x180023c7b  test    eax, eax
0x180023c7d  jle     short loc_180023C87
0x180023c7f  movzx   eax, ax
0x180023c82  or      eax, 80070000h
0x180023c87  mov     rcx, [rbx+8]
0x180023c8b  mov     [rsp+68h+var_38], eax
0x180023c8f  mov     rax, [rbx]
0x180023c92  mov     [rsp+68h+var_40], rax
0x180023c97  mov     rax, [rcx+30h]
0x180023c9b  mov     [rsp+68h+var_48], rax
0x180023ca0  lea     r9, aDeletetimerque; "DeleteTimerQueueTimer failed for Queue "...
0x180023ca7  mov     r8d, 52h ; 'R'; unsigned int
0x180023cad  lea     rdx, aOnecoreuapDsEx_81; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180023cb4  lea     ecx, [r8-50h]; unsigned __int8
0x180023cb8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180023cbd  jmp     loc_180023C13
0x180023cc2  call    cs:__imp_GetLastError
0x180023cc8  mov     ebx, eax
0x180023cca  test    eax, eax
0x180023ccc  jle     short loc_180023CD7
0x180023cce  movzx   ebx, ax
0x180023cd1  or      ebx, 80070000h
0x180023cd7  mov     rcx, [rsp+68h+Token]; hObject
0x180023cdc  test    rcx, rcx
0x180023cdf  jz      short loc_180023CE7
0x180023ce1  call    cs:__imp_CloseHandle
0x180023ce7  mov     [rsp+68h+pExceptionObject], ebx
0x180023ceb  lea     rdx, _TI1J; pThrowInfo
0x180023cf2  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180023cf7  call    _CxxThrowException_0
```
