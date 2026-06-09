# EnableFlushTimer

- ea: `0x180025b58`
- end: `0x180025ba9`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180025d00`
- `0x180025d50`

## callees

- `0x180025b58`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025b91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025b91`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180040614 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180025b58  sub     rsp, 28h
0x180025b5c  test    rcx, rcx
0x180025b5f  jz      short loc_180025BA4
0x180025b61  mov     eax, cs:dword_180040614
0x180025b67  test    eax, eax
0x180025b69  jnz     short loc_180025BA4
0x180025b6b  mov     eax, edx
0x180025b6d  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180025b74  mov     rdx, rax
0x180025b77  shr     rdx, 20h
0x180025b7b  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x180025b7f  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180025b83  mov     r9d, 1388h; msWindowLength
0x180025b89  xor     r8d, r8d; msPeriod
0x180025b8c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180025b91  call    cs:__imp_SetThreadpoolTimer
0x180025b97  jmp     short loc_180025BA4
0x180025b99  mov     eax, 1
0x180025b9e  xchg    eax, cs:dword_180040614
0x180025ba4  add     rsp, 28h
0x180025ba8  retn
0x18002bc32  push    rbp
0x18002bc34  sub     rsp, 20h
0x18002bc38  mov     rbp, rdx
0x18002bc3b  mov     rax, [rcx]
0x18002bc3e  xor     ecx, ecx
0x18002bc40  cmp     dword ptr [rax], 0C000000Dh
0x18002bc46  setz    cl
0x18002bc49  mov     eax, ecx
0x18002bc4b  add     rsp, 20h
0x18002bc4f  pop     rbp
0x18002bc50  retn
```
