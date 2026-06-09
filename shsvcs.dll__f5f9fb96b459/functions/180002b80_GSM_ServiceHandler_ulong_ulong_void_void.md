# GSM::_ServiceHandler(ulong,ulong,void *,void *)

- ea: `0x180002b80`
- end: `0x180002e5c`
- name: `?_ServiceHandler@GSM@@YAKKKPEAX0@Z`
- size: `732`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, char *lpContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180002b80`
- `0x180003570`
- `0x18001b404`
- `0x180032c46`
- `0x180032c52`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002c8d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002dab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ccc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002d8d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002d8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002d80`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002d80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002dbd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002dbd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002cbe`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002cbe`

## pseudocode

```c
__int64 __fastcall GSM::_ServiceHandler(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, char *lpContext)
{
  int v9; // r13d
  _DWORD *v10; // rax
  _DWORD *v11; // r14
  unsigned int v12; // edi
  HANDLE ProcessHeap; // rax
  void *v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  CRefCounted *v16; // rcx
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  __int64 v18; // rax
  bool v19; // zf
  int v20; // eax

  if ( !lpContext )
    return 0;
  if ( dwControl == 4 )
  {
    if ( GSM::g_loadedcontext == 1
      && !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)lpContext + 6), (LPSERVICE_STATUS)(lpContext + 8)) )
    {
      GetLastError();
    }
    return 0;
  }
  if ( dwControl == 1 )
  {
    v20 = 0;
    if ( !*((_DWORD *)lpContext + 18) )
    {
      v20 = 1;
      *((_DWORD *)lpContext + 18) = 1;
    }
    v9 = 0;
    if ( !v20 )
      return 0;
  }
  else
  {
    if ( *((_DWORD *)lpContext + 18) )
      return 0;
    v9 = 0;
    if ( dwControl == 11 && lpEventData && lpEventData[1] == 6 )
    {
      if ( dwEventType == 32769 )
      {
        v9 = 1;
      }
      else if ( dwEventType == 32774
             && (!memcmp_0(&GUID_IO_VOLUME_LOCK, lpEventData + 8, 0x10u)
              || !memcmp_0(&GUID_IO_VOLUME_LOCK_FAILED, lpEventData + 8, 0x10u)
              || !memcmp_0(&GUID_IO_VOLUME_UNLOCK, lpEventData + 8, 0x10u)) )
      {
        v9 = 1;
      }
    }
  }
  EnterCriticalSection(&stru_18003E3F0);
  v10 = operator new(0x28u);
  v11 = v10;
  if ( !v10 )
  {
LABEL_20:
    LeaveCriticalSection(&stru_18003E3F0);
    return 0;
  }
  v10[2] = 1;
  *(_QWORD *)v10 = &CServiceControlEvent::`vftable';
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 4) = 0;
  if ( (dwControl == 11 || dwControl == 14) && lpEventData )
  {
    v12 = *lpEventData;
    ProcessHeap = GetProcessHeap();
    v14 = HeapAlloc(ProcessHeap, 0, v12);
    *((_QWORD *)v11 + 4) = v14;
    if ( !v14 )
    {
      CRefCounted::Release((CRefCounted *)v11);
      goto LABEL_20;
    }
    v11[6] = dwControl;
    v11[7] = dwEventType;
    memcpy_0(v14, lpEventData, *lpEventData);
  }
  else
  {
    v10[6] = dwControl;
    v10[7] = dwEventType;
  }
  _InterlockedIncrement(v11 + 2);
  v15 = (struct _RTL_CRITICAL_SECTION *)(lpContext + 648);
  if ( lpContext == (char *)-640LL )
    v15 = 0;
  EnterCriticalSection(v15);
  v16 = *(CRefCounted **)&lpContext[8 * *((unsigned int *)lpContext + 78) + 320];
  if ( v16 )
    CRefCounted::Release(v16);
  *(_QWORD *)&lpContext[8 * (*((_DWORD *)lpContext + 78))++ + 320] = v11;
  if ( *((_DWORD *)lpContext + 78) == 40 )
    *((_DWORD *)lpContext + 78) = 0;
  v17 = 0;
  if ( lpContext != (char *)-640LL )
    v17 = (struct _RTL_CRITICAL_SECTION *)(lpContext + 648);
  LeaveCriticalSection(v17);
  *((_QWORD *)v11 + 2) = 0;
  v18 = *((_QWORD *)lpContext + 8);
  if ( v18 )
    *(_QWORD *)(v18 + 16) = v11;
  v19 = *((_QWORD *)lpContext + 7) == 0;
  *((_QWORD *)lpContext + 8) = v11;
  if ( v19 )
    *((_QWORD *)lpContext + 7) = v11;
  SetEvent(*((HANDLE *)lpContext + 35));
  ResetEvent(*((HANDLE *)lpContext + 36));
  LeaveCriticalSection(&stru_18003E3F0);
  if ( v9 )
  {
    Sleep(0);
    WaitForSingleObject(*((HANDLE *)lpContext + 36), 0x1388u);
  }
  return 0;
}

```

## disassembly

```asm
0x180002b80  push    rbx
0x180002b82  push    rbp
0x180002b83  push    rsi
0x180002b84  push    rdi
0x180002b85  push    r12
0x180002b87  push    r13
0x180002b89  push    r14
0x180002b8b  push    r15
0x180002b8d  sub     rsp, 28h
0x180002b91  mov     rbx, r9
0x180002b94  mov     rbp, r8
0x180002b97  mov     r12d, edx
0x180002b9a  mov     esi, ecx
0x180002b9c  test    r9, r9
0x180002b9f  jz      short loc_180002BB3
0x180002ba1  cmp     ecx, 4
0x180002ba4  jnz     short loc_180002BC6
0x180002ba6  cmp     cs:?g_loadedcontext@GSM@@3W4LOADEDCONTEXT@1@A, 1; GSM::LOADEDCONTEXT GSM::g_loadedcontext
0x180002bad  jz      loc_180002CB6
0x180002bb3  xor     eax, eax
0x180002bb5  add     rsp, 28h
0x180002bb9  pop     r15
0x180002bbb  pop     r14
0x180002bbd  pop     r13
0x180002bbf  pop     r12
0x180002bc1  pop     rdi
0x180002bc2  pop     rsi
0x180002bc3  pop     rbp
0x180002bc4  pop     rbx
0x180002bc5  retn
0x180002bc6  mov     eax, esi
0x180002bc8  sub     eax, 1
0x180002bcb  jz      loc_180002E21
0x180002bd1  cmp     dword ptr [r9+48h], 0
0x180002bd6  jnz     short loc_180002BB3
0x180002bd8  xor     r15d, r15d
0x180002bdb  mov     r13d, r15d
0x180002bde  cmp     esi, 0Bh
0x180002be1  jnz     short loc_180002C32
0x180002be3  test    rbp, rbp
0x180002be6  jz      short loc_180002C32
0x180002be8  cmp     dword ptr [r8+4], 6
0x180002bed  jnz     short loc_180002C32
0x180002bef  cmp     r12d, 8001h
0x180002bf6  jz      loc_180002E16
0x180002bfc  cmp     r12d, 8006h
0x180002c03  jnz     short loc_180002C32
0x180002c05  mov     r8d, 10h; Size
0x180002c0b  lea     rdx, [rbp+20h]; Buf2
0x180002c0f  lea     rcx, GUID_IO_VOLUME_LOCK; Buf1
0x180002c16  call    memcmp_0
0x180002c1b  test    eax, eax
0x180002c1d  jnz     loc_180002DD5
0x180002c23  mov     r13d, 1
0x180002c29  jmp     short loc_180002C32
0x180002c2b  mov     r13d, r15d
0x180002c2e  test    eax, eax
0x180002c30  jz      short loc_180002BB3
0x180002c32  lea     rcx, stru_18003E3F0; lpCriticalSection
0x180002c39  call    cs:__imp_EnterCriticalSection
0x180002c3f  mov     ecx, 28h ; '('; Size
0x180002c44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c49  mov     r14, rax
0x180002c4c  test    rax, rax
0x180002c4f  jz      short loc_180002CA4
0x180002c51  mov     dword ptr [rax+8], 1
0x180002c58  lea     rax, ??_7CServiceControlEvent@@6B@; const CServiceControlEvent::`vftable'
0x180002c5f  mov     [r14], rax
0x180002c62  mov     [r14+10h], r15
0x180002c66  mov     [r14+20h], r15
0x180002c6a  cmp     esi, 0Bh
0x180002c6d  jnz     loc_180002E3F
0x180002c73  test    rbp, rbp
0x180002c76  jz      loc_180002DC8
0x180002c7c  mov     edi, [rbp+0]
0x180002c7f  call    cs:__imp_GetProcessHeap
0x180002c85  mov     r8d, edi; dwBytes
0x180002c88  xor     edx, edx; dwFlags
0x180002c8a  mov     rcx, rax; hHeap
0x180002c8d  call    cs:__imp_HeapAlloc
0x180002c93  mov     [r14+20h], rax
0x180002c97  test    rax, rax
0x180002c9a  jnz     short loc_180002CD7
0x180002c9c  mov     rcx, r14; this
0x180002c9f  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002ca4  lea     rcx, stru_18003E3F0; lpCriticalSection
0x180002cab  call    cs:__imp_LeaveCriticalSection
0x180002cb1  jmp     loc_180002BB3
0x180002cb6  mov     rcx, [r9+30h]; hServiceStatus
0x180002cba  lea     rdx, [r9+8]; lpServiceStatus
0x180002cbe  call    cs:__imp_SetServiceStatus
0x180002cc4  test    eax, eax
0x180002cc6  jnz     loc_180002BB3
0x180002ccc  call    cs:__imp_GetLastError
0x180002cd2  jmp     loc_180002BB3
0x180002cd7  mov     [r14+18h], esi
0x180002cdb  mov     rdx, rbp; Src
0x180002cde  mov     [r14+1Ch], r12d
0x180002ce2  mov     rcx, rax; void *
0x180002ce5  mov     r8d, [rbp+0]; Size
0x180002ce9  call    memcpy_0
0x180002cee  lock inc dword ptr [r14+8]
0x180002cf3  lea     rdi, [rbx+280h]
0x180002cfa  lea     rsi, [rdi+8]
0x180002cfe  test    rdi, rdi
0x180002d01  mov     rcx, rsi
0x180002d04  cmovz   rcx, r15; lpCriticalSection
0x180002d08  call    cs:__imp_EnterCriticalSection
0x180002d0e  mov     eax, [rbx+138h]
0x180002d14  mov     rcx, [rbx+rax*8+140h]; this
0x180002d1c  test    rcx, rcx
0x180002d1f  jnz     loc_180002E49
0x180002d25  mov     eax, [rbx+138h]
0x180002d2b  mov     [rbx+rax*8+140h], r14
0x180002d33  inc     dword ptr [rbx+138h]
0x180002d39  cmp     dword ptr [rbx+138h], 28h ; '('
0x180002d40  jnz     short loc_180002D49
0x180002d42  mov     [rbx+138h], r15d
0x180002d49  test    rdi, rdi
0x180002d4c  mov     rcx, r15
0x180002d4f  cmovnz  rcx, rsi; lpCriticalSection
0x180002d53  call    cs:__imp_LeaveCriticalSection
0x180002d59  mov     [r14+10h], r15
0x180002d5d  mov     rax, [rbx+40h]
0x180002d61  test    rax, rax
0x180002d64  jnz     loc_180002E53
0x180002d6a  cmp     qword ptr [rbx+38h], 0
0x180002d6f  mov     [rbx+40h], r14
0x180002d73  jnz     short loc_180002D79
0x180002d75  mov     [rbx+38h], r14
0x180002d79  mov     rcx, [rbx+118h]; hEvent
0x180002d80  call    cs:__imp_SetEvent
0x180002d86  mov     rcx, [rbx+120h]; hEvent
0x180002d8d  call    cs:__imp_ResetEvent
0x180002d93  lea     rcx, stru_18003E3F0; lpCriticalSection
0x180002d9a  call    cs:__imp_LeaveCriticalSection
0x180002da0  test    r13d, r13d
0x180002da3  jz      loc_180002BB3
0x180002da9  xor     ecx, ecx; dwMilliseconds
0x180002dab  call    cs:__imp_Sleep
0x180002db1  mov     rcx, [rbx+120h]; hHandle
0x180002db8  mov     edx, 1388h; dwMilliseconds
0x180002dbd  call    cs:__imp_WaitForSingleObject
0x180002dc3  jmp     loc_180002BB3
0x180002dc8  mov     [r14+18h], esi
0x180002dcc  mov     [r14+1Ch], r12d
0x180002dd0  jmp     loc_180002CEE
0x180002dd5  mov     r8d, 10h; Size
0x180002ddb  lea     rdx, [rbp+20h]; Buf2
0x180002ddf  lea     rcx, GUID_IO_VOLUME_LOCK_FAILED; Buf1
0x180002de6  call    memcmp_0
0x180002deb  test    eax, eax
0x180002ded  jz      loc_180002C23
0x180002df3  mov     r8d, 10h; Size
0x180002df9  lea     rdx, [rbp+20h]; Buf2
0x180002dfd  lea     rcx, GUID_IO_VOLUME_UNLOCK; Buf1
0x180002e04  call    memcmp_0
0x180002e09  test    eax, eax
0x180002e0b  jnz     loc_180002C32
0x180002e11  jmp     loc_180002C23
0x180002e16  mov     r13d, 1
0x180002e1c  jmp     loc_180002C32
0x180002e21  xor     r15d, r15d
0x180002e24  mov     eax, r15d
0x180002e27  cmp     [r9+48h], eax
0x180002e2b  jnz     loc_180002C2B
0x180002e31  mov     eax, 1
0x180002e36  mov     [r9+48h], eax
0x180002e3a  jmp     loc_180002C2B
0x180002e3f  cmp     esi, 0Eh
0x180002e42  jnz     short loc_180002DC8
0x180002e44  jmp     loc_180002C73
0x180002e49  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002e4e  jmp     loc_180002D25
0x180002e53  mov     [rax+10h], r14
0x180002e57  jmp     loc_180002D6A
```
