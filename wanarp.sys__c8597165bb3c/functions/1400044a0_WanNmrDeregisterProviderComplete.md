# WanNmrDeregisterProviderComplete

- ea: `0x1400044a0`
- end: `0x1400044dc`
- name: `WanNmrDeregisterProviderComplete`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000474c`
- `0x140004780`

## callees

- `0x1400044a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400044ca`
- `ntoskrnl!KeSetEvent` at `0x1400044ca`

## pseudocode

```c
LONG __fastcall WanNmrDeregisterProviderComplete(__int64 a1)
{
  LONG result; // eax

  *(_QWORD *)(a1 + 72) = 0;
  result = _InterlockedDecrement(&g_DriverRefCount);
  if ( result == -1 )
    return KeSetEvent(&g_DriverRefCountEvent, 0, 0);
  return result;
}

```

## disassembly

```asm
0x1400044a0  sub     rsp, 28h
0x1400044a4  mov     qword ptr [rcx+48h], 0
0x1400044ac  or      eax, 0FFFFFFFFh
0x1400044af  lock xadd cs:g_DriverRefCount, eax
0x1400044b7  dec     eax
0x1400044b9  cmp     eax, 0FFFFFFFFh
0x1400044bc  jnz     short loc_1400044D6
0x1400044be  xor     r8d, r8d; Wait
0x1400044c1  lea     rcx, g_DriverRefCountEvent; Event
0x1400044c8  xor     edx, edx; Increment
0x1400044ca  call    cs:__imp_KeSetEvent
0x1400044d1  nop     dword ptr [rax+rax+00h]
0x1400044d6  add     rsp, 28h
0x1400044da  retn
```
