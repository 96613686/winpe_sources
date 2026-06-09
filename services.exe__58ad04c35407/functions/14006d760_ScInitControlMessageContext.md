# ScInitControlMessageContext

- ea: `0x14006d760`
- end: `0x14006da1b`
- name: `ScInitControlMessageContext`
- size: `699`
- prototype: `__int64 __fastcall(PSID pSourceSid, HANDLE Process, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003ae4c`
- `0x14007a510`

## callees

- `0x140004c58`
- `0x14002e420`
- `0x14006d760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14006d7f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14006d7f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d93e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d93e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14006d934`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14006d934`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006da02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006da02`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14006d88a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14006d88a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14006d77c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14006d77c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14006d986`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14006d986`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14006d8e6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14006d8e6`
- `ntdll!RtlFreeHeap` at `0x14006d9dc`
- `ntdll!RtlFreeHeap` at `0x14006d9f4`
- `ntdll!RtlFreeHeap` at `0x14006d9dc`
- `ntdll!RtlFreeHeap` at `0x14006d9f4`
- `ntdll!RtlInitializeSRWLock` at `0x14006d8d9`
- `ntdll!RtlInitializeSRWLock` at `0x14006d8d9`
- `ntdll!RtlAllocateHeap` at `0x14006d79e`
- `ntdll!RtlAllocateHeap` at `0x14006d848`
- `ntdll!RtlAllocateHeap` at `0x14006d79e`
- `ntdll!RtlAllocateHeap` at `0x14006d848`

## pseudocode

```c
__int64 __fastcall ScInitControlMessageContext(PSID pSourceSid, HANDLE Process, _QWORD *a3)
{
  void *v6; // rbp
  SIZE_T LengthSid; // rdi
  _QWORD *Heap; // rbx
  HANDLE EventW; // rsi
  DWORD LastError; // edi
  PRPC_ASYNC_STATE v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  PVOID v14; // rax
  _QWORD *v15; // rdi
  _QWORD *v16; // rax
  DWORD ProcessId; // eax

  v6 = 0;
  LengthSid = GetLengthSid(pSourceSid);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x90u);
  if ( !Heap )
  {
    EventW = 0;
    LastError = 8;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v12 = 95;
LABEL_5:
      v13 = 8;
LABEL_6:
      WPP_SF_d(v11->StubInfo, v12, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v13);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_32;
    v12 = 96;
    goto LABEL_11;
  }
  v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, LengthSid);
  v6 = v14;
  if ( v14 )
  {
    if ( !CopySid(LengthSid, v14, pSourceSid) )
    {
      LastError = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_32;
      v12 = 98;
      goto LABEL_11;
    }
    v15 = Heap + 1;
    Heap[2] = Heap + 1;
    Heap[1] = Heap + 1;
    RtlInitializeSRWLock(Heap + 16);
    RtlAcquireSRWLockExclusive(&g_ScServiceChannelLock);
    v16 = off_1400BA218;
    if ( *off_1400BA218 != (_UNKNOWN *)&g_ScServiceChannelContextListHead )
      __fastfail(3u);
    *v15 = &g_ScServiceChannelContextListHead;
    Heap[2] = v16;
    *v16 = v15;
    off_1400BA218 = (_UNKNOWN **)(Heap + 1);
    *((_BYTE *)Heap + 141) |= 1u;
    Heap[10] = EventW;
    Heap[11] = v6;
    *(_DWORD *)Heap = 1128486483;
    if ( Process )
    {
      ProcessId = GetProcessId(Process);
      if ( !ProcessId )
      {
        LastError = GetLastError();
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_32;
        }
        v12 = 99;
LABEL_11:
        v13 = LastError;
        goto LABEL_6;
      }
    }
    else
    {
      *((_BYTE *)Heap + 141) |= 0x10u;
      ProcessId = 0;
    }
    *((_DWORD *)Heap + 25) = ProcessId;
    LastError = 0;
    Heap[14] = 1;
    RtlReleaseSRWLockExclusive(&g_ScServiceChannelLock);
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->StubInfo, 100, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, Heap, EventW);
    *a3 = Heap;
    EventW = 0;
    Heap = 0;
    v6 = 0;
    goto LABEL_32;
  }
  LastError = 8;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v12 = 97;
    goto LABEL_5;
  }
LABEL_32:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( EventW )
    CloseHandle(EventW);
  return LastError;
}

```

## disassembly

```asm
0x14006d760  push    rbx
0x14006d762  push    rbp
0x14006d763  push    rsi
0x14006d764  push    rdi
0x14006d765  push    r12
0x14006d767  push    r13
0x14006d769  push    r14
0x14006d76b  push    r15
0x14006d76d  sub     rsp, 38h
0x14006d771  mov     r12, r8
0x14006d774  mov     r14, rdx
0x14006d777  mov     r15, rcx
0x14006d77a  xor     ebp, ebp
0x14006d77c  call    cs:__imp_GetLengthSid
0x14006d782  mov     rcx, gs:60h
0x14006d78b  lea     r13d, [rbp+8]
0x14006d78f  mov     r8d, 90h; Size
0x14006d795  mov     edi, eax
0x14006d797  mov     edx, r13d; Flags
0x14006d79a  mov     rcx, [rcx+30h]; HeapHandle
0x14006d79e  call    cs:__imp_RtlAllocateHeap
0x14006d7a4  mov     rbx, rax
0x14006d7a7  test    rax, rax
0x14006d7aa  jnz     short loc_14006D7ED
0x14006d7ac  xor     esi, esi
0x14006d7ae  mov     edi, r13d
0x14006d7b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d7b8  lea     rax, WPP_GLOBAL_Control
0x14006d7bf  cmp     rcx, rax
0x14006d7c2  jz      loc_14006D9CA
0x14006d7c8  test    byte ptr [rcx+1Ch], 1
0x14006d7cc  jz      loc_14006D9CA
0x14006d7d2  lea     edx, [rbp+5Fh]
0x14006d7d5  mov     r9d, r13d
0x14006d7d8  mov     rcx, [rcx+10h]
0x14006d7dc  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14006d7e3  call    WPP_SF_d
0x14006d7e8  jmp     loc_14006D9CA
0x14006d7ed  xor     r9d, r9d; lpName
0x14006d7f0  xor     r8d, r8d; bInitialState
0x14006d7f3  xor     edx, edx; bManualReset
0x14006d7f5  xor     ecx, ecx; lpEventAttributes
0x14006d7f7  call    cs:__imp_CreateEventW
0x14006d7fd  mov     rsi, rax
0x14006d800  test    rax, rax
0x14006d803  jnz     short loc_14006D836
0x14006d805  call    cs:__imp_GetLastError
0x14006d80b  mov     edi, eax
0x14006d80d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d814  lea     rax, WPP_GLOBAL_Control
0x14006d81b  cmp     rcx, rax
0x14006d81e  jz      loc_14006D9CA
0x14006d824  test    byte ptr [rcx+1Ch], 1
0x14006d828  jz      loc_14006D9CA
0x14006d82e  lea     edx, [rsi+60h]
0x14006d831  mov     r9d, edi
0x14006d834  jmp     short loc_14006D7D8
0x14006d836  mov     rcx, gs:60h
0x14006d83f  mov     r8, rdi; Size
0x14006d842  xor     edx, edx; Flags
0x14006d844  mov     rcx, [rcx+30h]; HeapHandle
0x14006d848  call    cs:__imp_RtlAllocateHeap
0x14006d84e  mov     rbp, rax
0x14006d851  test    rax, rax
0x14006d854  jnz     short loc_14006D882
0x14006d856  mov     edi, r13d
0x14006d859  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d860  lea     rax, WPP_GLOBAL_Control
0x14006d867  cmp     rcx, rax
0x14006d86a  jz      loc_14006D9CA
0x14006d870  test    byte ptr [rcx+1Ch], 1
0x14006d874  jz      loc_14006D9CA
0x14006d87a  lea     edx, [rbp+61h]
0x14006d87d  jmp     loc_14006D7D5
0x14006d882  mov     r8, r15; pSourceSid
0x14006d885  mov     rdx, rbp; pDestinationSid
0x14006d888  mov     ecx, edi; nDestinationSidLength
0x14006d88a  call    cs:__imp_CopySid
0x14006d890  test    eax, eax
0x14006d892  jnz     short loc_14006D8C7
0x14006d894  call    cs:__imp_GetLastError
0x14006d89a  mov     edi, eax
0x14006d89c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d8a3  lea     rax, WPP_GLOBAL_Control
0x14006d8aa  cmp     rcx, rax
0x14006d8ad  jz      loc_14006D9CA
0x14006d8b3  test    byte ptr [rcx+1Ch], 1
0x14006d8b7  jz      loc_14006D9CA
0x14006d8bd  mov     edx, 62h ; 'b'
0x14006d8c2  jmp     loc_14006D831
0x14006d8c7  lea     rdi, [rbx+8]
0x14006d8cb  lea     rcx, [rbx+80h]
0x14006d8d2  mov     [rdi+8], rdi
0x14006d8d6  mov     [rdi], rdi
0x14006d8d9  call    cs:__imp_RtlInitializeSRWLock
0x14006d8df  lea     rcx, g_ScServiceChannelLock
0x14006d8e6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14006d8ec  mov     rax, cs:off_1400BA218
0x14006d8f3  lea     rcx, g_ScServiceChannelContextListHead
0x14006d8fa  cmp     [rax], rcx
0x14006d8fd  jz      short loc_14006D906
0x14006d8ff  mov     ecx, 3
0x14006d904  int     29h; Win8: RtlFailFast(ecx)
0x14006d906  mov     [rdi], rcx
0x14006d909  mov     [rdi+8], rax
0x14006d90d  mov     [rax], rdi
0x14006d910  mov     cs:off_1400BA218, rdi
0x14006d917  or      byte ptr [rbx+8Dh], 1
0x14006d91e  mov     [rbx+50h], rsi
0x14006d922  mov     [rbx+58h], rbp
0x14006d926  mov     dword ptr [rbx], 43435653h
0x14006d92c  test    r14, r14
0x14006d92f  jz      short loc_14006D969
0x14006d931  mov     rcx, r14; Process
0x14006d934  call    cs:__imp_GetProcessId
0x14006d93a  test    eax, eax
0x14006d93c  jnz     short loc_14006D972
0x14006d93e  call    cs:__imp_GetLastError
0x14006d944  mov     edi, eax
0x14006d946  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d94d  lea     rax, WPP_GLOBAL_Control
0x14006d954  cmp     rcx, rax
0x14006d957  jz      short loc_14006D9CA
0x14006d959  test    byte ptr [rcx+1Ch], 1
0x14006d95d  jz      short loc_14006D9CA
0x14006d95f  mov     edx, 63h ; 'c'
0x14006d964  jmp     loc_14006D831
0x14006d969  or      byte ptr [rbx+8Dh], 10h
0x14006d970  xor     eax, eax
0x14006d972  mov     [rbx+64h], eax
0x14006d975  lea     rcx, g_ScServiceChannelLock
0x14006d97c  xor     edi, edi
0x14006d97e  mov     qword ptr [rbx+70h], 1
0x14006d986  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14006d98c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d993  lea     rax, WPP_GLOBAL_Control
0x14006d99a  cmp     rcx, rax
0x14006d99d  jz      short loc_14006D9C0
0x14006d99f  test    byte ptr [rcx+1Ch], 4
0x14006d9a3  jz      short loc_14006D9C0
0x14006d9a5  mov     rcx, [rcx+10h]
0x14006d9a9  lea     edx, [rdi+64h]
0x14006d9ac  mov     r9, rbx
0x14006d9af  mov     [rsp+78h+var_58], rsi
0x14006d9b4  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14006d9bb  call    WPP_SF_qq
0x14006d9c0  mov     [r12], rbx
0x14006d9c4  xor     esi, esi
0x14006d9c6  xor     ebx, ebx
0x14006d9c8  xor     ebp, ebp
0x14006d9ca  mov     rcx, gs:60h
0x14006d9d3  mov     r8, rbx; P
0x14006d9d6  xor     edx, edx; Flags
0x14006d9d8  mov     rcx, [rcx+30h]; HeapHandle
0x14006d9dc  call    cs:__imp_RtlFreeHeap
0x14006d9e2  mov     rcx, gs:60h
0x14006d9eb  mov     r8, rbp; P
0x14006d9ee  xor     edx, edx; Flags
0x14006d9f0  mov     rcx, [rcx+30h]; HeapHandle
0x14006d9f4  call    cs:__imp_RtlFreeHeap
0x14006d9fa  test    rsi, rsi
0x14006d9fd  jz      short loc_14006DA08
0x14006d9ff  mov     rcx, rsi; hObject
0x14006da02  call    cs:__imp_CloseHandle
0x14006da08  mov     eax, edi
0x14006da0a  add     rsp, 38h
0x14006da0e  pop     r15
0x14006da10  pop     r14
0x14006da12  pop     r13
0x14006da14  pop     r12
0x14006da16  pop     rdi
0x14006da17  pop     rsi
0x14006da18  pop     rbp
0x14006da19  pop     rbx
0x14006da1a  retn
```
