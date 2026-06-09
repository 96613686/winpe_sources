# _free_base

- ea: `0x10041c24c`
- end: `0x10041c288`
- name: `_free_base`
- size: `60`
- prototype: `void __cdecl(void *Block)`
- caller_count: `43`
- callee_count: `3`
- tags: ``

## callers

- `0x10041a610`
- `0x10041a674`
- `0x10041a800`
- `0x10041a87c`
- `0x10041a994`
- `0x10041aafc`
- `0x10041acb4`
- `0x10041af90`
- `0x10041afe0`
- `0x10041b118`
- `0x10041b49c`
- `0x10041b5e0`
- `0x10041b608`
- `0x10041b774`
- `0x10041b7bc`
- `0x10041b898`
- `0x10041b940`
- `0x10041ba10`
- `0x10041c2a8`
- `0x10041c428`
- `0x10041c5bc`
- `0x10041c804`
- `0x10041c990`
- `0x10041cfdc`
- `0x10041d4c4`
- `0x10041d73c`
- `0x10041dd98`
- `0x10041efd0`
- `0x10041f100`
- `0x10041f5d8`
- `0x10041f784`
- `0x1004203bc`
- `0x100420554`
- `0x100420990`
- `0x100420abc`
- `0x100420b68`
- `0x100421b84`
- `0x100421c3c`
- `0x100421ee0`
- `0x100421ff0`
- `0x100422064`
- `0x10042209c`
- `0x1004223ac`

## callees

- `0x10041c0bc`
- `0x10041c1a8`
- `0x10041c24c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10041c26c`
- `KERNEL32!GetLastError` at `0x10041c26c`
- `KERNEL32!HeapFree` at `0x10041c262`
- `KERNEL32!HeapFree` at `0x10041c262`

## pseudocode

```c
void __cdecl free_base(void *Block)
{
  DWORD LastError; // eax
  int v2; // ebx

  if ( Block )
  {
    if ( !HeapFree(_acrt_heap, 0, Block) )
    {
      LastError = GetLastError();
      v2 = _acrt_errno_from_os_error(LastError);
      *errno() = v2;
    }
  }
}

```

## disassembly

```asm
0x10041c24c  test    rcx, rcx
0x10041c24f  jz      short locret_10041C287
0x10041c251  push    rbx
0x10041c252  sub     rsp, 20h
0x10041c256  mov     r8, rcx; lpMem
0x10041c259  xor     edx, edx; dwFlags
0x10041c25b  mov     rcx, cs:__acrt_heap; hHeap
0x10041c262  call    cs:__imp_HeapFree
0x10041c268  test    eax, eax
0x10041c26a  jnz     short loc_10041C282
0x10041c26c  call    cs:__imp_GetLastError
0x10041c272  mov     ecx, eax
0x10041c274  call    __acrt_errno_from_os_error
0x10041c279  mov     ebx, eax
0x10041c27b  call    _errno
0x10041c280  mov     [rax], ebx
0x10041c282  add     rsp, 20h
0x10041c286  pop     rbx
0x10041c287  retn
```
