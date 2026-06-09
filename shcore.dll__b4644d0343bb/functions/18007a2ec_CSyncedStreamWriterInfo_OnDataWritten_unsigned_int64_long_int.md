# CSyncedStreamWriterInfo::_OnDataWritten(unsigned __int64,long,int)

- ea: `0x18007a2ec`
- end: `0x18007a3ee`
- name: `?_OnDataWritten@CSyncedStreamWriterInfo@@AEAAJ_KJH@Z`
- size: `258`
- prototype: `__int64 __fastcall(CSyncedStreamWriterInfo *__hidden this, unsigned __int64, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800228dc`
- `0x1800771ec`
- `0x18007afd0`

## callees

- `0x180013578`
- `0x180023730`
- `0x18007a2ec`
- `0x18007a6f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007a3ac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007a3ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007a395`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007a395`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a342`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a342`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007a362`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007a362`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a3d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a3d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a313`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a313`

## pseudocode

```c
__int64 __fastcall CSyncedStreamWriterInfo::_OnDataWritten(
        CSyncedStreamWriterInfo *this,
        unsigned __int64 a2,
        int a3,
        int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  HANDLE EventW; // rax
  __int64 v10; // rbp
  __int64 v11; // rsi
  DWORD v12; // eax
  int v13; // r12d
  __int64 v14; // rcx
  char *v15; // rcx

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  if ( a2 <= **((_QWORD **)this + 5) )
  {
    if ( a3 == 1 )
      goto LABEL_5;
  }
  else if ( a3 == 1 )
  {
    CSyncedStreamWriterInfo::_ResetTimer(this);
LABEL_5:
    EventW = CreateEventW(0, 1, 0, 0);
    v10 = *((_QWORD *)this + 16);
    v11 = (__int64)EventW;
    goto LABEL_7;
  }
  v10 = -1;
  v11 = -1;
LABEL_7:
  v12 = WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF);
  v13 = ResultFromWin32Bool(v12 == 0);
  if ( v13 >= 0 )
  {
    v14 = *((_QWORD *)this + 5);
    *(_QWORD *)v14 = a2;
    *(_QWORD *)(v14 + 8) = v11;
    *(_QWORD *)(v14 + 16) = v10;
    *(_DWORD *)(v14 + 24) = a3;
    *(_DWORD *)(v14 + 28) = a4;
    ReleaseMutex(*((HANDLE *)this + 2));
  }
  v15 = (char *)*((_QWORD *)this + 17);
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    SetEvent(v15);
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 136);
  }
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 136);
  *((_QWORD *)this + 17) = v11;
  LeaveCriticalSection(v4);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18007a2ec  push    rbx
0x18007a2ee  push    rbp
0x18007a2ef  push    rsi
0x18007a2f0  push    rdi
0x18007a2f1  push    r12
0x18007a2f3  push    r13
0x18007a2f5  push    r14
0x18007a2f7  push    r15
0x18007a2f9  sub     rsp, 28h
0x18007a2fd  lea     r14, [rcx+98h]
0x18007a304  mov     rbx, rcx
0x18007a307  mov     rcx, r14; lpCriticalSection
0x18007a30a  mov     r13d, r9d
0x18007a30d  mov     edi, r8d
0x18007a310  mov     r15, rdx
0x18007a313  call    cs:__imp_EnterCriticalSection
0x18007a319  mov     rax, [rbx+28h]
0x18007a31d  cmp     r15, [rax]
0x18007a320  jbe     short loc_18007A331
0x18007a322  cmp     edi, 1
0x18007a325  jnz     short loc_18007A354
0x18007a327  mov     rcx, rbx; this
0x18007a32a  call    ?_ResetTimer@CSyncedStreamWriterInfo@@AEAAXXZ; CSyncedStreamWriterInfo::_ResetTimer(void)
0x18007a32f  jmp     short loc_18007A336
0x18007a331  cmp     edi, 1
0x18007a334  jnz     short loc_18007A354
0x18007a336  xor     r9d, r9d; lpName
0x18007a339  xor     r8d, r8d; bInitialState
0x18007a33c  xor     ecx, ecx; lpEventAttributes
0x18007a33e  lea     edx, [r9+1]; bManualReset
0x18007a342  call    cs:__imp_CreateEventW
0x18007a348  mov     rbp, [rbx+80h]
0x18007a34f  mov     rsi, rax
0x18007a352  jmp     short loc_18007A35B
0x18007a354  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18007a358  mov     rsi, rbp
0x18007a35b  mov     rcx, [rbx+10h]; hHandle
0x18007a35f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007a362  call    cs:__imp_WaitForSingleObject
0x18007a368  xor     ecx, ecx
0x18007a36a  test    eax, eax
0x18007a36c  setz    cl; int
0x18007a36f  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18007a374  mov     r12d, eax
0x18007a377  test    eax, eax
0x18007a379  js      short loc_18007A39B
0x18007a37b  mov     rcx, [rbx+28h]
0x18007a37f  mov     [rcx], r15
0x18007a382  mov     [rcx+8], rsi
0x18007a386  mov     [rcx+10h], rbp
0x18007a38a  mov     [rcx+18h], edi
0x18007a38d  mov     [rcx+1Ch], r13d
0x18007a391  mov     rcx, [rbx+10h]; hMutex
0x18007a395  call    cs:__imp_ReleaseMutex
0x18007a39b  mov     rcx, [rbx+88h]; hEvent
0x18007a3a2  lea     rax, [rcx-1]
0x18007a3a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007a3aa  ja      short loc_18007A3BE
0x18007a3ac  call    cs:__imp_SetEvent
0x18007a3b2  lea     rcx, [rbx+88h]
0x18007a3b9  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18007a3be  lea     rcx, [rbx+88h]
0x18007a3c5  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18007a3ca  mov     rcx, r14; lpCriticalSection
0x18007a3cd  mov     [rbx+88h], rsi
0x18007a3d4  call    cs:__imp_LeaveCriticalSection
0x18007a3da  mov     eax, r12d
0x18007a3dd  add     rsp, 28h
0x18007a3e1  pop     r15
0x18007a3e3  pop     r14
0x18007a3e5  pop     r13
0x18007a3e7  pop     r12
0x18007a3e9  pop     rdi
0x18007a3ea  pop     rsi
0x18007a3eb  pop     rbp
0x18007a3ec  pop     rbx
0x18007a3ed  retn
```
