# CWSHRemote::Terminate(void)

- ea: `0x140002cd0`
- end: `0x140002d3c`
- name: `?Terminate@CWSHRemote@@UEAAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000169c`
- `0x140001864`
- `0x140002cd0`
- `0x140007b3c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002ce5`
- `KERNEL32!GetCurrentThreadId` at `0x140002ce5`

## pseudocode

```c
__int64 __fastcall CWSHRemote::Terminate(CWSHRemote *this)
{
  int v1; // ebx
  CHost *v4; // rcx
  unsigned int v5; // ebx

  v1 = *((_DWORD *)this + 10);
  if ( GetCurrentThreadId() != v1 )
    return 2147549183LL;
  if ( (unsigned int)CCriticalSection::Enter((CWSHRemote *)((char *)this + 120)) )
  {
    v4 = (CHost *)*((_QWORD *)this + 13);
    v5 = 0;
    if ( v4 )
      v5 = CHost::Interrupt(v4, -2147155972);
    CCriticalSection::Leave((CWSHRemote *)((char *)this + 120));
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v5;
}

```

## disassembly

```asm
0x140002cd0  mov     [rsp+arg_0], rbx
0x140002cd5  mov     [rsp+arg_8], rsi
0x140002cda  push    rdi
0x140002cdb  sub     rsp, 20h
0x140002cdf  mov     ebx, [rcx+28h]
0x140002ce2  mov     rdi, rcx
0x140002ce5  call    cs:__imp_GetCurrentThreadId
0x140002ceb  cmp     eax, ebx
0x140002ced  jz      short loc_140002CF6
0x140002cef  mov     eax, 8000FFFFh
0x140002cf4  jmp     short loc_140002D2C
0x140002cf6  lea     rcx, [rdi+78h]; this
0x140002cfa  call    ?Enter@CCriticalSection@@QEAAHXZ; CCriticalSection::Enter(void)
0x140002cff  test    eax, eax
0x140002d01  jz      short loc_140002D25
0x140002d03  mov     rcx, [rdi+68h]; this
0x140002d07  xor     ebx, ebx
0x140002d09  test    rcx, rcx
0x140002d0c  jz      short loc_140002D1A
0x140002d0e  mov     edx, 8004FFFCh; int
0x140002d13  call    ?Interrupt@CHost@@QEAAJJ@Z; CHost::Interrupt(long)
0x140002d18  mov     ebx, eax
0x140002d1a  lea     rcx, [rdi+78h]; this
0x140002d1e  call    ?Leave@CCriticalSection@@QEAAXXZ; CCriticalSection::Leave(void)
0x140002d23  jmp     short loc_140002D2A
0x140002d25  mov     ebx, 80004005h
0x140002d2a  mov     eax, ebx
0x140002d2c  mov     rbx, [rsp+28h+arg_0]
0x140002d31  mov     rsi, [rsp+28h+arg_8]
0x140002d36  add     rsp, 20h
0x140002d3a  pop     rdi
0x140002d3b  retn
```
