# SmpSetCoreProcessIds

- ea: `0x140017954`
- end: `0x140017a1f`
- name: `SmpSetCoreProcessIds`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140001630`
- `0x1400027a0`

## callees

- `0x140001e40`
- `0x140008f80`
- `0x14000d4c0`
- `0x140017954`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x140017988`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140017988`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001799f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400179f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001799f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400179f4`
- `ntdll!RtlWakeAllConditionVariable` at `0x140017a03`
- `ntdll!RtlWakeAllConditionVariable` at `0x140017a03`

## string_xrefs

- `0x1400179aa`: `SmpSetCoreProcessIds`

## pseudocode

```c
__int64 __fastcall SmpSetCoreProcessIds(__int64 a1, PVOID *a2)
{
  __int64 v3; // rbx
  char v4; // r8
  volatile signed __int32 *v5; // rax
  __int64 result; // rax
  int v7; // ebp
  __int64 i; // rdx
  void *v9; // rcx

  v3 = SmpCoreProcessIds + 40LL * (unsigned int)SmpSessionIdToInitialSessionIndex();
  if ( v4 )
    *(_DWORD *)v3 = -1;
  RtlAcquireSRWLockExclusive(v3 + 8);
  v5 = (volatile signed __int32 *)*a2;
  if ( *a2 )
  {
    if ( (v5[2] & 4) != 0 )
    {
      RtlReleaseSRWLockExclusive(v3 + 8);
      return SmpLogFailure("SmpSetCoreProcessIds", 1103, 3221225473LL);
    }
    _InterlockedIncrement(v5);
  }
  v7 = 0;
  for ( i = 0; i != 2; ++i )
  {
    v9 = *(void **)(v3 + 8 * i + 24);
    *(_QWORD *)(v3 + 8 * i + 24) = a2[i];
    a2[i] = v9;
  }
  if ( !*(_DWORD *)(v3 + 4) && *(_QWORD *)(v3 + 32) )
  {
    v7 = 1;
    *(_DWORD *)(v3 + 4) = 1;
  }
  result = RtlReleaseSRWLockExclusive(v3 + 8);
  if ( v7 == 1 )
    result = RtlWakeAllConditionVariable(v3 + 16);
  if ( *a2 )
    return SmpDereferenceKnownSubSys(*a2);
  return result;
}

```

## disassembly

```asm
0x140017954  push    rbx
0x140017956  push    rbp
0x140017957  push    rsi
0x140017958  push    rdi
0x140017959  sub     rsp, 28h
0x14001795d  mov     rsi, rdx
0x140017960  call    SmpSessionIdToInitialSessionIndex
0x140017965  mov     ecx, eax
0x140017967  mov     rax, cs:SmpCoreProcessIds
0x14001796e  lea     r9, [rcx+rcx*4]
0x140017972  lea     rbx, [rax+r9*8]
0x140017976  test    r8b, r8b
0x140017979  jz      short loc_140017981
0x14001797b  mov     dword ptr [rbx], 0FFFFFFFFh
0x140017981  lea     rdi, [rbx+8]
0x140017985  mov     rcx, rdi
0x140017988  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001798e  mov     rax, [rsi]
0x140017991  test    rax, rax
0x140017994  jz      short loc_1400179C1
0x140017996  test    byte ptr [rax+8], 4
0x14001799a  jz      short loc_1400179BE
0x14001799c  mov     rcx, rdi
0x14001799f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400179a5  mov     edx, 44Fh
0x1400179aa  lea     rcx, aSmpsetcoreproc; "SmpSetCoreProcessIds"
0x1400179b1  mov     r8d, 0C0000001h
0x1400179b7  call    SmpLogFailure
0x1400179bc  jmp     short loc_140017A16
0x1400179be  lock inc dword ptr [rax]
0x1400179c1  xor     ebp, ebp
0x1400179c3  xor     edx, edx
0x1400179c5  mov     rax, [rsi+rdx*8]
0x1400179c9  mov     rcx, [rbx+rdx*8+18h]
0x1400179ce  mov     [rbx+rdx*8+18h], rax
0x1400179d3  mov     [rsi+rdx*8], rcx
0x1400179d7  inc     rdx
0x1400179da  cmp     rdx, 2
0x1400179de  jnz     short loc_1400179C5
0x1400179e0  cmp     [rbx+4], ebp
0x1400179e3  jnz     short loc_1400179F1
0x1400179e5  cmp     [rbx+20h], rbp
0x1400179e9  jz      short loc_1400179F1
0x1400179eb  lea     ebp, [rdx-1]
0x1400179ee  mov     [rbx+4], ebp
0x1400179f1  mov     rcx, rdi
0x1400179f4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400179fa  cmp     ebp, 1
0x1400179fd  jnz     short loc_140017A09
0x1400179ff  lea     rcx, [rbx+10h]
0x140017a03  call    cs:__imp_RtlWakeAllConditionVariable
0x140017a09  mov     rcx, [rsi]; BaseAddress
0x140017a0c  test    rcx, rcx
0x140017a0f  jz      short loc_140017A16
0x140017a11  call    SmpDereferenceKnownSubSys
0x140017a16  add     rsp, 28h
0x140017a1a  pop     rdi
0x140017a1b  pop     rsi
0x140017a1c  pop     rbp
0x140017a1d  pop     rbx
0x140017a1e  retn
```
