# _Init_thread_header

- ea: `0x180002734`
- end: `0x180002799`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001881c`

## callees

- `0x180002734`
- `0x1800027e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002744`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002744`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002792`

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
0x180002734  push    rbx
0x180002736  sub     rsp, 20h
0x18000273a  mov     rbx, rcx
0x18000273d  lea     rcx, CriticalSection; lpCriticalSection
0x180002744  call    cs:__imp_EnterCriticalSection
0x18000274a  cmp     dword ptr [rbx], 0
0x18000274d  jnz     short loc_18000275E
0x18000274f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002755  jmp     short loc_180002786
0x180002757  call    _Init_thread_wait_v2
0x18000275c  jmp     short loc_18000274A
0x18000275e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002761  jz      short loc_180002757
0x180002763  mov     rax, gs:58h
0x18000276c  mov     ecx, cs:_tls_index
0x180002772  mov     r8d, 4
0x180002778  mov     rdx, [rax+rcx*8]
0x18000277c  mov     eax, cs:_Init_global_epoch
0x180002782  mov     [r8+rdx], eax
0x180002786  lea     rcx, CriticalSection
0x18000278d  add     rsp, 20h
0x180002791  pop     rbx
0x180002792  jmp     cs:__imp_LeaveCriticalSection
```
