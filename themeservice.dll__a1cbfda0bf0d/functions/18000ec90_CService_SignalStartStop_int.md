# CService::SignalStartStop(int)

- ea: `0x18000ec90`
- end: `0x18000eccc`
- name: `?SignalStartStop@CService@@MEAAJH@Z`
- size: `60`
- prototype: `__int64 __fastcall(CService *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000cf20`

## callees

- `0x18000ec90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ecbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ecbe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ecb5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ecb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eca6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eca6`

## pseudocode

```c
__int64 __fastcall CService::SignalStartStop(CService *this, int a2)
{
  __int64 v2; // rbx
  void *v3; // rcx

  if ( !a2 )
  {
    v2 = *((_QWORD *)this + 10);
    if ( v2 )
    {
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      v3 = *(void **)(v2 + 48);
      if ( v3 )
        SetEvent(v3);
      LeaveCriticalSection((LPCRITICAL_SECTION)v2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ec90  push    rbx
0x18000ec92  sub     rsp, 20h
0x18000ec96  test    edx, edx
0x18000ec98  jnz     short loc_18000ECC4
0x18000ec9a  mov     rbx, [rcx+50h]
0x18000ec9e  test    rbx, rbx
0x18000eca1  jz      short loc_18000ECC4
0x18000eca3  mov     rcx, rbx; lpCriticalSection
0x18000eca6  call    cs:__imp_EnterCriticalSection
0x18000ecac  mov     rcx, [rbx+30h]; hEvent
0x18000ecb0  test    rcx, rcx
0x18000ecb3  jz      short loc_18000ECBB
0x18000ecb5  call    cs:__imp_SetEvent
0x18000ecbb  mov     rcx, rbx; lpCriticalSection
0x18000ecbe  call    cs:__imp_LeaveCriticalSection
0x18000ecc4  xor     eax, eax
0x18000ecc6  add     rsp, 20h
0x18000ecca  pop     rbx
0x18000eccb  retn
```
