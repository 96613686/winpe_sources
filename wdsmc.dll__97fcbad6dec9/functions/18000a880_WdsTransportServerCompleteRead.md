# WdsTransportServerCompleteRead

- ea: `0x18000a880`
- end: `0x18000a976`
- name: `WdsTransportServerCompleteRead`
- size: `246`
- prototype: `HRESULT __stdcall(HANDLE hProvider, ULONG ulBytesRead, PVOID pvUserData, HRESULT hReadResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a880`
- `0x18001a9a8`
- `0x180024c14`
- `0x180024ce0`
- `0x180026d70`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000a956`
- `KERNEL32!SetEvent` at `0x18000a956`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8e3`
- `KERNEL32!LeaveCriticalSection` at `0x18000a91b`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8e3`
- `KERNEL32!LeaveCriticalSection` at `0x18000a91b`
- `KERNEL32!EnterCriticalSection` at `0x18000a8b7`
- `KERNEL32!EnterCriticalSection` at `0x18000a8f6`
- `KERNEL32!EnterCriticalSection` at `0x18000a8b7`
- `KERNEL32!EnterCriticalSection` at `0x18000a8f6`

## pseudocode

```c
HRESULT __stdcall WdsTransportServerCompleteRead(
        HANDLE hProvider,
        ULONG ulBytesRead,
        PVOID pvUserData,
        HRESULT hReadResult)
{
  __int64 v4; // rsi
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  __int64 v8; // rcx
  void (*v9)(void); // rax
  __int64 v10; // rax

  v4 = ulBytesRead;
  if ( hReadResult < 0 && (hReadResult & 0x1FFF0000) == 0x70000 )
    hReadResult = (unsigned __int16)hReadResult;
  v6 = *(struct _RTL_CRITICAL_SECTION **)pvUserData;
  v7 = *(struct _RTL_CRITICAL_SECTION **)pvUserData;
  if ( hReadResult )
  {
    EnterCriticalSection(v7);
    v8 = *((_QWORD *)pvUserData + 1);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      *((_QWORD *)pvUserData + 1) = 0;
    }
    operator delete(pvUserData);
    LeaveCriticalSection(v6);
    v9 = *(void (**)(void))(*(_QWORD *)v6[1].DebugInfo + 48LL);
  }
  else
  {
    EnterCriticalSection(v7);
    v10 = *((_QWORD *)pvUserData + 1);
    *((_DWORD *)pvUserData + 4) = 1;
    *(_DWORD *)(v10 + 48) = v4;
    *((_QWORD *)pvUserData + 4) = v4 + *((_QWORD *)pvUserData + 3) - 1LL;
    LeaveCriticalSection(v6);
    v9 = *(void (**)(void))(*(_QWORD *)&v6[1].DebugInfo[307].EntryCount + 24LL);
  }
  v9();
  CMRSWLock::ReaderLock((struct _RTL_CRITICAL_SECTION *)((char *)v6 + 88));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v6[1].SpinCount, 0xFFFFFFFF) == 1 )
    SetEvent(v6[2].DebugInfo);
  CMRSWLock::ReaderRelease((struct _RTL_CRITICAL_SECTION *)((char *)v6 + 88));
  return 0;
}

```

## disassembly

```asm
0x18000a880  mov     [rsp+arg_0], rbx
0x18000a885  mov     [rsp+arg_8], rsi
0x18000a88a  push    rdi
0x18000a88b  sub     rsp, 20h
0x18000a88f  mov     esi, edx
0x18000a891  mov     rdi, r8
0x18000a894  test    r9d, r9d
0x18000a897  jns     short loc_18000A8AC
0x18000a899  mov     eax, r9d
0x18000a89c  and     eax, 1FFF0000h
0x18000a8a1  cmp     eax, 70000h
0x18000a8a6  jnz     short loc_18000A8AC
0x18000a8a8  movzx   r9d, r9w
0x18000a8ac  mov     rbx, [r8]
0x18000a8af  mov     rcx, rbx; lpCriticalSection
0x18000a8b2  test    r9d, r9d
0x18000a8b5  jz      short loc_18000A8F6
0x18000a8b7  call    cs:__imp_EnterCriticalSection
0x18000a8bd  mov     rcx, [rdi+8]
0x18000a8c1  test    rcx, rcx
0x18000a8c4  jz      short loc_18000A8D8
0x18000a8c6  mov     rax, [rcx]
0x18000a8c9  mov     rax, [rax+8]
0x18000a8cd  call    cs:__guard_dispatch_icall_fptr
0x18000a8d3  and     qword ptr [rdi+8], 0
0x18000a8d8  mov     rcx, rdi; void *
0x18000a8db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a8e0  mov     rcx, rbx; lpCriticalSection
0x18000a8e3  call    cs:__imp_LeaveCriticalSection
0x18000a8e9  mov     rcx, [rbx+28h]
0x18000a8ed  mov     rax, [rcx]
0x18000a8f0  mov     rax, [rax+30h]
0x18000a8f4  jmp     short loc_18000A933
0x18000a8f6  call    cs:__imp_EnterCriticalSection
0x18000a8fc  mov     rax, [rdi+8]
0x18000a900  mov     dword ptr [rdi+10h], 1
0x18000a907  mov     [rax+30h], esi
0x18000a90a  mov     rcx, [rdi+18h]
0x18000a90e  dec     rcx
0x18000a911  add     rcx, rsi
0x18000a914  mov     [rdi+20h], rcx
0x18000a918  mov     rcx, rbx; lpCriticalSection
0x18000a91b  call    cs:__imp_LeaveCriticalSection
0x18000a921  mov     rcx, [rbx+28h]
0x18000a925  add     rcx, 39B0h
0x18000a92c  mov     rax, [rcx]
0x18000a92f  mov     rax, [rax+18h]
0x18000a933  call    cs:__guard_dispatch_icall_fptr
0x18000a939  lea     rdi, [rbx+58h]
0x18000a93d  mov     rcx, rdi; lpCriticalSection
0x18000a940  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x18000a945  or      eax, 0FFFFFFFFh
0x18000a948  lock xadd [rbx+48h], eax
0x18000a94d  cmp     eax, 1
0x18000a950  jnz     short loc_18000A95C
0x18000a952  mov     rcx, [rbx+50h]; hEvent
0x18000a956  call    cs:__imp_SetEvent
0x18000a95c  mov     rcx, rdi; this
0x18000a95f  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000a964  mov     rbx, [rsp+28h+arg_0]
0x18000a969  xor     eax, eax
0x18000a96b  mov     rsi, [rsp+28h+arg_8]
0x18000a970  add     rsp, 20h
0x18000a974  pop     rdi
0x18000a975  retn
```
