# _Init_thread_header

- ea: `0x180002704`
- end: `0x180002769`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018934`

## callees

- `0x180002704`
- `0x1800027b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002714`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002714`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002762`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
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
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180002704  push    rbx
0x180002706  sub     rsp, 20h
0x18000270a  mov     rbx, rcx
0x18000270d  lea     rcx, CriticalSection; lpCriticalSection
0x180002714  call    cs:__imp_EnterCriticalSection
0x18000271a  cmp     dword ptr [rbx], 0
0x18000271d  jnz     short loc_18000272E
0x18000271f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002725  jmp     short loc_180002756
0x180002727  call    _Init_thread_wait_v2
0x18000272c  jmp     short loc_18000271A
0x18000272e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002731  jz      short loc_180002727
0x180002733  mov     rax, gs:58h
0x18000273c  mov     ecx, cs:_tls_index
0x180002742  mov     r8d, 4
0x180002748  mov     rdx, [rax+rcx*8]
0x18000274c  mov     eax, cs:_Init_global_epoch
0x180002752  mov     [r8+rdx], eax
0x180002756  lea     rcx, CriticalSection
0x18000275d  add     rsp, 20h
0x180002761  pop     rbx
0x180002762  jmp     cs:__imp_LeaveCriticalSection
```
