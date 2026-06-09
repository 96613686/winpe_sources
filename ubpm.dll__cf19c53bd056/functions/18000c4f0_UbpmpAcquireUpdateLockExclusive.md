# UbpmpAcquireUpdateLockExclusive

- ea: `0x18000c4f0`
- end: `0x18000c54e`
- name: `UbpmpAcquireUpdateLockExclusive`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e090`

## callees

- `0x18000c4f0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c52d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c52d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c507`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c512`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c507`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c512`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c533`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c533`

## pseudocode

```c
DWORD UbpmpAcquireUpdateLockExclusive()
{
  DWORD v0; // edi
  _QWORD *Value; // rbx
  DWORD result; // eax

  v0 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    Value = TlsGetValue(UbpmpLockTrackerId);
    if ( *(_QWORD *)TlsGetValue(v0) )
      __int2c();
    *Value |= 1uLL;
    ++Value[1];
  }
  RtlAcquireSRWLockExclusive(&g_ConsumerUpdateLock);
  result = GetCurrentThreadId();
  dword_18004CEC8 = result;
  return result;
}

```

## disassembly

```asm
0x18000c4f0  mov     [rsp+arg_0], rbx
0x18000c4f5  push    rdi
0x18000c4f6  sub     rsp, 20h
0x18000c4fa  mov     edi, cs:UbpmpLockTrackerId
0x18000c500  cmp     edi, 0FFFFFFFFh
0x18000c503  jz      short loc_18000C526
0x18000c505  mov     ecx, edi; dwTlsIndex
0x18000c507  call    cs:__imp_TlsGetValue
0x18000c50d  mov     ecx, edi; dwTlsIndex
0x18000c50f  mov     rbx, rax
0x18000c512  call    cs:__imp_TlsGetValue
0x18000c518  cmp     qword ptr [rax], 0
0x18000c51c  jnz     short loc_18000C54A
0x18000c51e  or      qword ptr [rbx], 1
0x18000c522  inc     qword ptr [rbx+8]
0x18000c526  lea     rcx, ?g_ConsumerUpdateLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerUpdateLock
0x18000c52d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000c533  call    cs:__imp_GetCurrentThreadId
0x18000c539  mov     rbx, [rsp+28h+arg_0]
0x18000c53e  mov     cs:dword_18004CEC8, eax
0x18000c544  add     rsp, 20h
0x18000c548  pop     rdi
0x18000c549  retn
0x18000c54a  int     2Ch; Windows NT - assertion failure
0x18000c54c  jmp     short loc_18000C51E
```
