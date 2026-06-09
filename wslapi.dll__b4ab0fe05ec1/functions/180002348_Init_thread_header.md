# _Init_thread_header

- ea: `0x180002348`
- end: `0x1800023ad`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800065f0`

## callees

- `0x180002348`
- `0x1800023fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002358`

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
0x180002348  push    rbx
0x18000234a  sub     rsp, 20h
0x18000234e  mov     rbx, rcx
0x180002351  lea     rcx, CriticalSection; lpCriticalSection
0x180002358  call    cs:__imp_EnterCriticalSection
0x18000235e  cmp     dword ptr [rbx], 0
0x180002361  jnz     short loc_180002372
0x180002363  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002369  jmp     short loc_18000239A
0x18000236b  call    _Init_thread_wait_v2
0x180002370  jmp     short loc_18000235E
0x180002372  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002375  jz      short loc_18000236B
0x180002377  mov     rax, gs:58h
0x180002380  mov     ecx, cs:_tls_index
0x180002386  mov     r8d, 4
0x18000238c  mov     rdx, [rax+rcx*8]
0x180002390  mov     eax, cs:_Init_global_epoch
0x180002396  mov     [r8+rdx], eax
0x18000239a  lea     rcx, CriticalSection
0x1800023a1  add     rsp, 20h
0x1800023a5  pop     rbx
0x1800023a6  jmp     cs:__imp_LeaveCriticalSection
```
