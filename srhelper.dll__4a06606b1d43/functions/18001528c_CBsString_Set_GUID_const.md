# CBsString::Set(_GUID const &)

- ea: `0x18001528c`
- end: `0x1800152e8`
- name: `?Set@CBsString@@QEAAJAEBU_GUID@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(const void **this, const struct _GUID *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029d8`
- `0x180002e9c`
- `0x180003968`
- `0x180003b24`
- `0x18000572c`

## callees

- `0x18001509c`
- `0x18001528c`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800152c9`
- `ole32!StringFromGUID2` at `0x1800152c9`

## pseudocode

```c
__int64 __fastcall CBsString::Set(const void **this, const struct _GUID *a2)
{
  int v4; // ebx

  if ( a2 )
  {
    v4 = CBsString::ExtendBuffer(this, 0x26u);
    if ( v4 >= 0 )
    {
      StringFromGUID2(a2, (LPOLESTR)*this, 39);
      *((_DWORD *)this + 2) = 38;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001528c  mov     [rsp+arg_0], rbx
0x180015291  mov     [rsp+arg_8], rsi
0x180015296  push    rdi
0x180015297  sub     rsp, 20h
0x18001529b  mov     rsi, rdx
0x18001529e  mov     rdi, rcx
0x1800152a1  test    rdx, rdx
0x1800152a4  jnz     short loc_1800152AD
0x1800152a6  mov     ebx, 80070057h
0x1800152ab  jmp     short loc_1800152D6
0x1800152ad  mov     edx, 26h ; '&'; unsigned int
0x1800152b2  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800152b7  mov     ebx, eax
0x1800152b9  test    eax, eax
0x1800152bb  js      short loc_1800152D6
0x1800152bd  mov     rdx, [rdi]; lpsz
0x1800152c0  mov     r8d, 27h ; '''; cchMax
0x1800152c6  mov     rcx, rsi; rguid
0x1800152c9  call    cs:__imp_StringFromGUID2
0x1800152cf  mov     dword ptr [rdi+8], 26h ; '&'
0x1800152d6  mov     rsi, [rsp+28h+arg_8]
0x1800152db  mov     eax, ebx
0x1800152dd  mov     rbx, [rsp+28h+arg_0]
0x1800152e2  add     rsp, 20h
0x1800152e6  pop     rdi
0x1800152e7  retn
```
