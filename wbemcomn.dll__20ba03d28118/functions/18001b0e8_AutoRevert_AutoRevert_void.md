# AutoRevert::AutoRevert(void)

- ea: `0x18001b0e8`
- end: `0x18001b13e`
- name: `??0AutoRevert@@QEAA@XZ`
- size: `86`
- prototype: `AutoRevert *__fastcall(AutoRevert *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001ac90`

## callees

- `0x18001b0e8`
- `0x18001b264`
- `0x18001b2e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b12b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b12b`

## pseudocode

```c
AutoRevert *__fastcall AutoRevert::AutoRevert(AutoRevert *this)
{
  HANDLE CurrentThread; // rax
  int v3; // r8d

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_BYTE *)this + 12) = 1;
  CurrentThread = GetCurrentThread();
  if ( (unsigned int)DLOpenThreadToken(CurrentThread, 4u, v3, (void **)this) )
  {
    DLRevertToSelf();
  }
  else if ( GetLastError() != 1008 )
  {
    *((_BYTE *)this + 12) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18001b0e8  push    rbx
0x18001b0ea  sub     rsp, 20h
0x18001b0ee  mov     rbx, rcx
0x18001b0f1  mov     qword ptr [rcx], 0
0x18001b0f8  mov     dword ptr [rcx+8], 0
0x18001b0ff  mov     byte ptr [rcx+0Ch], 1
0x18001b103  call    cs:__imp_GetCurrentThread
0x18001b109  mov     r9, rbx; void **
0x18001b10c  mov     edx, 4; unsigned int
0x18001b111  mov     rcx, rax; void *
0x18001b114  call    ?DLOpenThreadToken@@YAHPEAXKHPEAPEAX@Z; DLOpenThreadToken(void *,ulong,int,void * *)
0x18001b119  test    eax, eax
0x18001b11b  jz      short loc_18001B12B
0x18001b11d  call    ?DLRevertToSelf@@YAHXZ; DLRevertToSelf(void)
0x18001b122  mov     rax, rbx
0x18001b125  add     rsp, 20h
0x18001b129  pop     rbx
0x18001b12a  retn
0x18001b12b  call    cs:__imp_GetLastError
0x18001b131  cmp     eax, 3F0h
0x18001b136  jz      short loc_18001B122
0x18001b138  mov     byte ptr [rbx+0Ch], 0
0x18001b13c  jmp     short loc_18001B122
```
