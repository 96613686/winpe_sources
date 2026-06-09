# EnableFlushTimer

- ea: `0x180042acc`
- end: `0x180042b1d`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180042c90`

## callees

- `0x180042acc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180042b05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180042b05`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18005C840 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180042acc  sub     rsp, 28h
0x180042ad0  test    rcx, rcx
0x180042ad3  jz      short loc_180042B18
0x180042ad5  mov     eax, cs:dword_18005C840
0x180042adb  test    eax, eax
0x180042add  jnz     short loc_180042B18
0x180042adf  mov     eax, edx
0x180042ae1  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180042ae8  mov     rdx, rax
0x180042aeb  shr     rdx, 20h
0x180042aef  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x180042af3  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180042af7  mov     r9d, 1388h; msWindowLength
0x180042afd  xor     r8d, r8d; msPeriod
0x180042b00  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180042b05  call    cs:__imp_SetThreadpoolTimer
0x180042b0b  jmp     short loc_180042B18
0x180042b0d  mov     eax, 1
0x180042b12  xchg    eax, cs:dword_18005C840
0x180042b18  add     rsp, 28h
0x180042b1c  retn
0x180043726  push    rbp
0x180043728  sub     rsp, 20h
0x18004372c  mov     rbp, rdx
0x18004372f  mov     rax, [rcx]
0x180043732  xor     ecx, ecx
0x180043734  cmp     dword ptr [rax], 0C000000Dh
0x18004373a  setz    cl
0x18004373d  mov     eax, ecx
0x18004373f  add     rsp, 20h
0x180043743  pop     rbp
0x180043744  retn
```
