# _PROG_RESOURCES::RegisterBackup(void)

- ea: `0x180009ce8`
- end: `0x180009d4d`
- name: `?RegisterBackup@_PROG_RESOURCES@@QEAAHXZ`
- size: `101`
- prototype: `__int64 __fastcall(_PROG_RESOURCES *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800098a0`

## callees

- `0x180009ce8`
- `0x180020010`

## import_xrefs

- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009d3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009d3a`
- `wbemcomn!GetMemLogObject` at `0x180009d2f`
- `wbemcomn!GetMemLogObject` at `0x180009d2f`

## pseudocode

```c
__int64 __fastcall _PROG_RESOURCES::RegisterBackup(_PROG_RESOURCES *this)
{
  __int64 v1; // rcx
  int v3; // ebx
  CMemoryLog *MemLogObject; // rax

  v1 = *((_QWORD *)this + 5);
  if ( !v1 )
    return 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)v1 + 24LL))(
         v1,
         _PROG_RESOURCES::_RegisterBackup,
         0,
         &IID_IContextCallback,
         5,
         0);
  if ( v3 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v3);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180009ce8  push    rbx
0x180009cea  sub     rsp, 40h
0x180009cee  mov     rcx, [rcx+28h]
0x180009cf2  test    rcx, rcx
0x180009cf5  jnz     short loc_180009CFB
0x180009cf7  xor     eax, eax
0x180009cf9  jmp     short loc_180009D47
0x180009cfb  mov     rax, [rcx]
0x180009cfe  lea     r9, IID_IContextCallback
0x180009d05  mov     [rsp+48h+var_20], 0
0x180009d0e  lea     rdx, ?_RegisterBackup@_PROG_RESOURCES@@SAJPEAUtagComCallData@@@Z; _PROG_RESOURCES::_RegisterBackup(tagComCallData *)
0x180009d15  xor     r8d, r8d
0x180009d18  mov     [rsp+48h+var_28], 5
0x180009d20  mov     rax, [rax+18h]
0x180009d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d29  mov     ebx, eax
0x180009d2b  test    eax, eax
0x180009d2d  jns     short loc_180009D42
0x180009d2f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009d35  mov     rcx, rax
0x180009d38  mov     edx, ebx
0x180009d3a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009d40  jmp     short loc_180009CF7
0x180009d42  mov     eax, 1
0x180009d47  add     rsp, 40h
0x180009d4b  pop     rbx
0x180009d4c  retn
```
