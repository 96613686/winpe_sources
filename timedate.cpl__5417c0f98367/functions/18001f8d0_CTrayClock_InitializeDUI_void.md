# CTrayClock::_InitializeDUI(void)

- ea: `0x18001f8d0`
- end: `0x18001f91f`
- name: `?_InitializeDUI@CTrayClock@@AEAAJXZ`
- size: `79`
- prototype: `__int64 __fastcall(CTrayClock *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f928`
- `0x18001fa38`

## callees

- `0x18001f8d0`

## import_xrefs

- `DUI70!InitThread` at `0x18001f8fe`
- `DUI70!InitThread` at `0x18001f8fe`
- `DUI70!UnInitProcessPriv` at `0x18001f911`
- `DUI70!UnInitProcessPriv` at `0x18001f911`
- `DUI70!InitProcessPriv` at `0x18001f8ed`
- `DUI70!InitProcessPriv` at `0x18001f8ed`

## pseudocode

```c
__int64 __fastcall CTrayClock::_InitializeDUI(CTrayClock *this, __int64 a2, __int64 a3)
{
  int inited; // ebx

  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, &_ImageBase, a3);
  if ( inited >= 0 )
  {
    inited = InitThread(2);
    if ( inited < 0 )
      UnInitProcessPriv(&_ImageBase);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001f8d0  push    rbx
0x18001f8d2  sub     rsp, 30h
0x18001f8d6  mov     r9b, 1
0x18001f8d9  mov     [rsp+38h+var_18], 1
0x18001f8de  mov     r8b, r9b
0x18001f8e1  lea     rdx, __ImageBase
0x18001f8e8  mov     ecx, 0Eh
0x18001f8ed  call    cs:__imp_InitProcessPriv
0x18001f8f3  mov     ebx, eax
0x18001f8f5  test    eax, eax
0x18001f8f7  js      short loc_18001F917
0x18001f8f9  mov     ecx, 2
0x18001f8fe  call    cs:__imp_InitThread
0x18001f904  mov     ebx, eax
0x18001f906  test    eax, eax
0x18001f908  jns     short loc_18001F917
0x18001f90a  lea     rcx, __ImageBase
0x18001f911  call    cs:__imp_UnInitProcessPriv
0x18001f917  mov     eax, ebx
0x18001f919  add     rsp, 30h
0x18001f91d  pop     rbx
0x18001f91e  retn
```
