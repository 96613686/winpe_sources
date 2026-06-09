# UbpmpAcquireListLockExclusive

- ea: `0x18000ad3c`
- end: `0x18000ad9d`
- name: `UbpmpAcquireListLockExclusive`
- size: `97`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000aba0`
- `0x18000c650`
- `0x18000d5c0`
- `0x18000e090`
- `0x180017d70`

## callees

- `0x18000ad3c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ad7c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ad7c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ad53`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ad5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ad53`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ad5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad82`

## pseudocode

```c
DWORD UbpmpAcquireListLockExclusive()
{
  DWORD v0; // edi
  _QWORD *Value; // rbx
  DWORD result; // eax

  v0 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    Value = TlsGetValue(UbpmpLockTrackerId);
    if ( (*(_QWORD *)TlsGetValue(v0) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      __int2c();
    *Value |= 2uLL;
    ++Value[2];
  }
  RtlAcquireSRWLockExclusive(&g_ConsumerListLock);
  result = GetCurrentThreadId();
  dword_18004CED8 = result;
  return result;
}

```

## disassembly

```asm
0x18000ad3c  mov     [rsp+arg_0], rbx
0x18000ad41  push    rdi
0x18000ad42  sub     rsp, 20h
0x18000ad46  mov     edi, cs:UbpmpLockTrackerId
0x18000ad4c  cmp     edi, 0FFFFFFFFh
0x18000ad4f  jz      short loc_18000AD75
0x18000ad51  mov     ecx, edi; dwTlsIndex
0x18000ad53  call    cs:__imp_TlsGetValue
0x18000ad59  mov     ecx, edi; dwTlsIndex
0x18000ad5b  mov     rbx, rax
0x18000ad5e  call    cs:__imp_TlsGetValue
0x18000ad64  test    qword ptr [rax], 0FFFFFFFFFFFFFFFEh
0x18000ad6b  jnz     short loc_18000AD99
0x18000ad6d  or      qword ptr [rbx], 2
0x18000ad71  inc     qword ptr [rbx+10h]
0x18000ad75  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x18000ad7c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000ad82  call    cs:__imp_GetCurrentThreadId
0x18000ad88  mov     rbx, [rsp+28h+arg_0]
0x18000ad8d  mov     cs:dword_18004CED8, eax
0x18000ad93  add     rsp, 20h
0x18000ad97  pop     rdi
0x18000ad98  retn
0x18000ad99  int     2Ch; Windows NT - assertion failure
0x18000ad9b  jmp     short loc_18000AD6D
```
