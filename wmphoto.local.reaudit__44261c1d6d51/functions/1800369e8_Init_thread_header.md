# _Init_thread_header

- ea: `0x1800369e8`
- end: `0x180036a4d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b180`

## callees

- `0x1800369e8`
- `0x180036a9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036a46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369f8`

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
0x1800369e8  push    rbx
0x1800369ea  sub     rsp, 20h
0x1800369ee  mov     rbx, rcx
0x1800369f1  lea     rcx, CriticalSection; lpCriticalSection
0x1800369f8  call    cs:__imp_EnterCriticalSection
0x1800369fe  cmp     dword ptr [rbx], 0
0x180036a01  jnz     short loc_180036A12
0x180036a03  mov     dword ptr [rbx], 0FFFFFFFFh
0x180036a09  jmp     short loc_180036A3A
0x180036a0b  call    _Init_thread_wait_v2
0x180036a10  jmp     short loc_1800369FE
0x180036a12  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180036a15  jz      short loc_180036A0B
0x180036a17  mov     rax, gs:58h
0x180036a20  mov     ecx, cs:_tls_index
0x180036a26  mov     r8d, 4
0x180036a2c  mov     rdx, [rax+rcx*8]
0x180036a30  mov     eax, cs:_Init_global_epoch
0x180036a36  mov     [r8+rdx], eax
0x180036a3a  lea     rcx, CriticalSection
0x180036a41  add     rsp, 20h
0x180036a45  pop     rbx
0x180036a46  jmp     cs:__imp_LeaveCriticalSection
```
