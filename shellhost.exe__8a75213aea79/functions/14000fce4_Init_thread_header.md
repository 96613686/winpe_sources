# _Init_thread_header

- ea: `0x14000fce4`
- end: `0x14000fd49`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400080f8`
- `0x140020a80`
- `0x140027b80`
- `0x140031810`
- `0x140035bd0`
- `0x14003b360`
- `0x140044360`
- `0x1400584cc`

## callees

- `0x14000fce4`
- `0x14000fd98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000fd42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fcf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fcf4`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_140082FB0);
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
  LeaveCriticalSection(&stru_140082FB0);
}

```

## disassembly

```asm
0x14000fce4  push    rbx
0x14000fce6  sub     rsp, 20h
0x14000fcea  mov     rbx, rcx
0x14000fced  lea     rcx, stru_140082FB0; lpCriticalSection
0x14000fcf4  call    cs:__imp_EnterCriticalSection
0x14000fcfa  cmp     dword ptr [rbx], 0
0x14000fcfd  jnz     short loc_14000FD0E
0x14000fcff  mov     dword ptr [rbx], 0FFFFFFFFh
0x14000fd05  jmp     short loc_14000FD36
0x14000fd07  call    _Init_thread_wait_v2
0x14000fd0c  jmp     short loc_14000FCFA
0x14000fd0e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x14000fd11  jz      short loc_14000FD07
0x14000fd13  mov     rax, gs:58h
0x14000fd1c  mov     ecx, cs:_tls_index
0x14000fd22  mov     r8d, 4
0x14000fd28  mov     rdx, [rax+rcx*8]
0x14000fd2c  mov     eax, cs:_Init_global_epoch
0x14000fd32  mov     [r8+rdx], eax
0x14000fd36  lea     rcx, stru_140082FB0
0x14000fd3d  add     rsp, 20h
0x14000fd41  pop     rbx
0x14000fd42  jmp     cs:__imp_LeaveCriticalSection
```
