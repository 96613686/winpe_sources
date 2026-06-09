# _Init_thread_header

- ea: `0x1800043c4`
- end: `0x180004429`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba38`
- `0x18000f410`
- `0x1800142e0`
- `0x18001c32c`

## callees

- `0x1800043c4`
- `0x180004478`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800043d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800043d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004422`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_180034808);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    Init_thread_wait_v2();
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  LeaveCriticalSection(&stru_180034808);
}

```

## disassembly

```asm
0x1800043c4  push    rbx
0x1800043c6  sub     rsp, 20h
0x1800043ca  mov     rbx, rcx
0x1800043cd  lea     rcx, stru_180034808; lpCriticalSection
0x1800043d4  call    cs:__imp_EnterCriticalSection
0x1800043da  cmp     dword ptr [rbx], 0
0x1800043dd  jnz     short loc_1800043EE
0x1800043df  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800043e5  jmp     short loc_180004416
0x1800043e7  call    _Init_thread_wait_v2
0x1800043ec  jmp     short loc_1800043DA
0x1800043ee  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800043f1  jz      short loc_1800043E7
0x1800043f3  mov     rax, gs:58h
0x1800043fc  mov     ecx, cs:_tls_index
0x180004402  mov     r8d, 4
0x180004408  mov     rdx, [rax+rcx*8]
0x18000440c  mov     eax, cs:_Init_global_epoch
0x180004412  mov     [r8+rdx], eax
0x180004416  lea     rcx, stru_180034808
0x18000441d  add     rsp, 20h
0x180004421  pop     rbx
0x180004422  jmp     cs:__imp_LeaveCriticalSection
```
