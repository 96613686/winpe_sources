# _Init_thread_header

- ea: `0x180036418`
- end: `0x18003647d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002af00`

## callees

- `0x180036418`
- `0x1800364cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036476`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036428`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036428`

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
0x180036418  push    rbx
0x18003641a  sub     rsp, 20h
0x18003641e  mov     rbx, rcx
0x180036421  lea     rcx, CriticalSection; lpCriticalSection
0x180036428  call    cs:__imp_EnterCriticalSection
0x18003642e  cmp     dword ptr [rbx], 0
0x180036431  jnz     short loc_180036442
0x180036433  mov     dword ptr [rbx], 0FFFFFFFFh
0x180036439  jmp     short loc_18003646A
0x18003643b  call    _Init_thread_wait_v2
0x180036440  jmp     short loc_18003642E
0x180036442  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180036445  jz      short loc_18003643B
0x180036447  mov     rax, gs:58h
0x180036450  mov     ecx, cs:_tls_index
0x180036456  mov     r8d, 4
0x18003645c  mov     rdx, [rax+rcx*8]
0x180036460  mov     eax, cs:_Init_global_epoch
0x180036466  mov     [r8+rdx], eax
0x18003646a  lea     rcx, CriticalSection
0x180036471  add     rsp, 20h
0x180036475  pop     rbx
0x180036476  jmp     cs:__imp_LeaveCriticalSection
```
