# EnableFlushTimer

- ea: `0x18003db88`
- end: `0x18003dbd9`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006dc0`
- `0x180007b2c`
- `0x18003dbe0`

## callees

- `0x18003db88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003dbc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003dbc1`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18005ADF0 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18003db88  sub     rsp, 28h
0x18003db8c  test    rcx, rcx
0x18003db8f  jz      short loc_18003DBD4
0x18003db91  mov     eax, cs:dword_18005ADF0
0x18003db97  test    eax, eax
0x18003db99  jnz     short loc_18003DBD4
0x18003db9b  mov     eax, edx
0x18003db9d  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18003dba4  mov     rdx, rax
0x18003dba7  shr     rdx, 20h
0x18003dbab  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18003dbaf  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18003dbb3  mov     r9d, 1388h; msWindowLength
0x18003dbb9  xor     r8d, r8d; msPeriod
0x18003dbbc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18003dbc1  call    cs:__imp_SetThreadpoolTimer
0x18003dbc7  jmp     short loc_18003DBD4
0x18003dbc9  mov     eax, 1
0x18003dbce  xchg    eax, cs:dword_18005ADF0
0x18003dbd4  add     rsp, 28h
0x18003dbd8  retn
0x180041364  push    rbp
0x180041366  sub     rsp, 20h
0x18004136a  mov     rbp, rdx
0x18004136d  mov     rax, [rcx]
0x180041370  xor     ecx, ecx
0x180041372  cmp     dword ptr [rax], 0C000000Dh
0x180041378  setz    cl
0x18004137b  mov     eax, ecx
0x18004137d  add     rsp, 20h
0x180041381  pop     rbp
0x180041382  retn
```
