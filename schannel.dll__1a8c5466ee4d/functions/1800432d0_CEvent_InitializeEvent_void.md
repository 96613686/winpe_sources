# CEvent::InitializeEvent(void)

- ea: `0x1800432d0`
- end: `0x180043318`
- name: `?InitializeEvent@CEvent@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(CEvent *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800432d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043304`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800432ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800432ed`

## pseudocode

```c
signed int __fastcall CEvent::InitializeEvent(CEvent *this)
{
  HANDLE EventW; // rax
  signed int result; // eax

  if ( *((_QWORD *)this + 1) )
    return 0;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 1) = EventW;
  if ( EventW )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800432d0  push    rbx
0x1800432d2  sub     rsp, 20h
0x1800432d6  cmp     qword ptr [rcx+8], 0
0x1800432db  mov     rbx, rcx
0x1800432de  jnz     short loc_1800432FC
0x1800432e0  mov     edx, 1; bManualReset
0x1800432e5  xor     r9d, r9d; lpName
0x1800432e8  mov     r8d, edx; bInitialState
0x1800432eb  xor     ecx, ecx; lpEventAttributes
0x1800432ed  call    cs:__imp_CreateEventW
0x1800432f3  mov     [rbx+8], rax
0x1800432f7  test    rax, rax
0x1800432fa  jz      short loc_180043304
0x1800432fc  xor     eax, eax
0x1800432fe  add     rsp, 20h
0x180043302  pop     rbx
0x180043303  retn
0x180043304  call    cs:__imp_GetLastError
0x18004330a  test    eax, eax
0x18004330c  jle     short loc_1800432FE
0x18004330e  movzx   eax, ax
0x180043311  or      eax, 80070000h
0x180043316  jmp     short loc_1800432FE
```
