# UbpmpAcquireListLockExclusive

- ea: `0x1800017a4`
- end: `0x18000181e`
- name: `UbpmpAcquireListLockExclusive`
- size: `122`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001dc0`
- `0x180012950`
- `0x180012b70`
- `0x1800136b0`

## callees

- `0x1800017a4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800017f0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800017f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800017bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800017cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800017bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800017cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800017fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800017fc`

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
  dword_18004FFD8 = result;
  return result;
}

```

## disassembly

```asm
0x1800017a4  mov     [rsp+arg_0], rbx
0x1800017a9  push    rdi
0x1800017aa  sub     rsp, 20h
0x1800017ae  mov     edi, cs:UbpmpLockTrackerId
0x1800017b4  cmp     edi, 0FFFFFFFFh
0x1800017b7  jz      short loc_1800017E9
0x1800017b9  mov     ecx, edi; dwTlsIndex
0x1800017bb  call    cs:__imp_TlsGetValue
0x1800017c2  nop     dword ptr [rax+rax+00h]
0x1800017c7  mov     ecx, edi; dwTlsIndex
0x1800017c9  mov     rbx, rax
0x1800017cc  call    cs:__imp_TlsGetValue
0x1800017d3  nop     dword ptr [rax+rax+00h]
0x1800017d8  test    qword ptr [rax], 0FFFFFFFFFFFFFFFEh
0x1800017df  jnz     short loc_18000181A
0x1800017e1  or      qword ptr [rbx], 2
0x1800017e5  inc     qword ptr [rbx+10h]
0x1800017e9  lea     rcx, ?g_ConsumerListLock@@3U_CEM_LOCK@@A; _CEM_LOCK g_ConsumerListLock
0x1800017f0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800017f7  nop     dword ptr [rax+rax+00h]
0x1800017fc  call    cs:__imp_GetCurrentThreadId
0x180001803  nop     dword ptr [rax+rax+00h]
0x180001808  mov     rbx, [rsp+28h+arg_0]
0x18000180d  mov     cs:dword_18004FFD8, eax
0x180001813  add     rsp, 20h
0x180001817  pop     rdi
0x180001818  retn
0x18000181a  int     2Ch; Windows NT - assertion failure
0x18000181c  jmp     short loc_1800017E1
```
