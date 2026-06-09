# _Init_thread_header

- ea: `0x1800022d8`
- end: `0x18000233d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012be0`

## callees

- `0x1800022d8`
- `0x18000238c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002336`
- `KERNEL32!EnterCriticalSection` at `0x1800022e8`
- `KERNEL32!EnterCriticalSection` at `0x1800022e8`

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
0x1800022d8  push    rbx
0x1800022da  sub     rsp, 20h
0x1800022de  mov     rbx, rcx
0x1800022e1  lea     rcx, CriticalSection; lpCriticalSection
0x1800022e8  call    cs:__imp_EnterCriticalSection
0x1800022ee  cmp     dword ptr [rbx], 0
0x1800022f1  jnz     short loc_180002302
0x1800022f3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800022f9  jmp     short loc_18000232A
0x1800022fb  call    _Init_thread_wait_v2
0x180002300  jmp     short loc_1800022EE
0x180002302  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002305  jz      short loc_1800022FB
0x180002307  mov     rax, gs:58h
0x180002310  mov     ecx, cs:_tls_index
0x180002316  mov     r8d, 4
0x18000231c  mov     rdx, [rax+rcx*8]
0x180002320  mov     eax, cs:_Init_global_epoch
0x180002326  mov     [r8+rdx], eax
0x18000232a  lea     rcx, CriticalSection
0x180002331  add     rsp, 20h
0x180002335  pop     rbx
0x180002336  jmp     cs:__imp_LeaveCriticalSection
```
