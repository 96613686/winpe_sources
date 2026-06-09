# IsComputerLocalEx(ushort const *,_COMPUTER_NAME_FORMAT)

- ea: `0x18004161c`
- end: `0x18004168e`
- name: `?IsComputerLocalEx@@YAHPEBGW4_COMPUTER_NAME_FORMAT@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(wchar_t *String2, COMPUTER_NAME_FORMAT NameType)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800548c0`

## callees

- `0x18004161c`
- `0x180055030`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180041662`
- `msvcrt!_wcsicmp` at `0x180041662`
- `KERNEL32!GetComputerNameExW` at `0x180041650`
- `KERNEL32!GetComputerNameExW` at `0x180041650`

## pseudocode

```c
_BOOL8 __fastcall IsComputerLocalEx(wchar_t *String2, COMPUTER_NAME_FORMAT NameType)
{
  DWORD nSize[4]; // [rsp+20h] [rbp-228h] BYREF
  WCHAR Buffer[256]; // [rsp+30h] [rbp-218h] BYREF

  nSize[0] = 256;
  return GetComputerNameExW(NameType, Buffer, nSize) && !_wcsicmp(Buffer, String2);
}

```

## disassembly

```asm
0x18004161c  push    rbx
0x18004161e  sub     rsp, 240h
0x180041625  mov     rax, cs:__security_cookie
0x18004162c  xor     rax, rsp
0x18004162f  mov     [rsp+248h+var_18], rax
0x180041637  mov     eax, edx
0x180041639  mov     [rsp+248h+nSize], 100h
0x180041641  mov     rbx, rcx
0x180041644  lea     r8, [rsp+248h+nSize]; nSize
0x180041649  mov     ecx, eax; NameType
0x18004164b  lea     rdx, [rsp+248h+Buffer]; lpBuffer
0x180041650  call    cs:__imp_GetComputerNameExW
0x180041656  test    eax, eax
0x180041658  jz      short loc_180041673
0x18004165a  mov     rdx, rbx; String2
0x18004165d  lea     rcx, [rsp+248h+Buffer]; String1
0x180041662  call    cs:__imp__wcsicmp
0x180041668  test    eax, eax
0x18004166a  jnz     short loc_180041673
0x18004166c  mov     eax, 1
0x180041671  jmp     short loc_180041675
0x180041673  xor     eax, eax
0x180041675  mov     rcx, [rsp+248h+var_18]
0x18004167d  xor     rcx, rsp; StackCookie
0x180041680  call    __security_check_cookie
0x180041685  add     rsp, 240h
0x18004168c  pop     rbx
0x18004168d  retn
```
