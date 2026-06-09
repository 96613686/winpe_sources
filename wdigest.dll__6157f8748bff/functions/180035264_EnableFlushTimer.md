# EnableFlushTimer

- ea: `0x180035264`
- end: `0x1800352b5`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180010290`
- `0x180035410`

## callees

- `0x180035264`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003529d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003529d`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180045EC4 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180035264  sub     rsp, 28h
0x180035268  test    rcx, rcx
0x18003526b  jz      short loc_1800352B0
0x18003526d  mov     eax, cs:dword_180045EC4
0x180035273  test    eax, eax
0x180035275  jnz     short loc_1800352B0
0x180035277  mov     eax, edx
0x180035279  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180035280  mov     rdx, rax
0x180035283  shr     rdx, 20h
0x180035287  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18003528b  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18003528f  mov     r9d, 1388h; msWindowLength
0x180035295  xor     r8d, r8d; msPeriod
0x180035298  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18003529d  call    cs:__imp_SetThreadpoolTimer
0x1800352a3  jmp     short loc_1800352B0
0x1800352a5  mov     eax, 1
0x1800352aa  xchg    eax, cs:dword_180045EC4
0x1800352b0  add     rsp, 28h
0x1800352b4  retn
0x18003783c  push    rbp
0x18003783e  sub     rsp, 20h
0x180037842  mov     rbp, rdx
0x180037845  mov     rax, [rcx]
0x180037848  xor     ecx, ecx
0x18003784a  cmp     dword ptr [rax], 0C000000Dh
0x180037850  setz    cl
0x180037853  mov     eax, ecx
0x180037855  add     rsp, 20h
0x180037859  pop     rbp
0x18003785a  retn
```
