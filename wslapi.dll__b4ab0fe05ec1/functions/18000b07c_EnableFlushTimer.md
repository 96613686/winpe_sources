# EnableFlushTimer

- ea: `0x18000b07c`
- end: `0x18000b0cd`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b230`

## callees

- `0x18000b07c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0b5`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180013600 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18000b07c  sub     rsp, 28h
0x18000b080  test    rcx, rcx
0x18000b083  jz      short loc_18000B0C8
0x18000b085  mov     eax, cs:dword_180013600
0x18000b08b  test    eax, eax
0x18000b08d  jnz     short loc_18000B0C8
0x18000b08f  mov     eax, edx
0x18000b091  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000b098  mov     rdx, rax
0x18000b09b  shr     rdx, 20h
0x18000b09f  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18000b0a3  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18000b0a7  mov     r9d, 1388h; msWindowLength
0x18000b0ad  xor     r8d, r8d; msPeriod
0x18000b0b0  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000b0b5  call    cs:__imp_SetThreadpoolTimer
0x18000b0bb  jmp     short loc_18000B0C8
0x18000b0bd  mov     eax, 1
0x18000b0c2  xchg    eax, cs:dword_180013600
0x18000b0c8  add     rsp, 28h
0x18000b0cc  retn
0x18000c681  push    rbp
0x18000c683  sub     rsp, 20h
0x18000c687  mov     rbp, rdx
0x18000c68a  mov     rax, [rcx]
0x18000c68d  xor     ecx, ecx
0x18000c68f  cmp     dword ptr [rax], 0C000000Dh
0x18000c695  setz    cl
0x18000c698  mov     eax, ecx
0x18000c69a  add     rsp, 20h
0x18000c69e  pop     rbp
0x18000c69f  retn
```
