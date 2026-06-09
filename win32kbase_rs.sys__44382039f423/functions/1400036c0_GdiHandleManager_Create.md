# GdiHandleManager_Create

- ea: `0x1400036c0`
- end: `0x140003724`
- name: `GdiHandleManager_Create`
- size: `100`
- prototype: `__int64 __fastcall(int, int, int, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400036c0`
- `0x14000a400`
- `0x140017a10`

## pseudocode

```c
__int64 __fastcall GdiHandleManager_Create(int a1, int a2, int a3, char a4)
{
  __int64 result; // rax
  __int64 v5; // [rsp+0h] [rbp-48h] BYREF
  char v6; // [rsp+30h] [rbp-18h] BYREF
  __int64 v7; // [rsp+38h] [rbp-10h]
  __int64 v8; // [rsp+40h] [rbp-8h]

  RNvMs_NtCs1fYFp9lPHeY_14handle_manager16GdiHandleManagerNtB4_16GdiHandleManager6Create(
    (unsigned int)&v6,
    a1,
    a2,
    a3,
    a4);
  if ( (v6 & 1) != 0 )
    result = 0;
  else
    result = v7;
  if ( _security_cookie != ((unsigned __int64)&v5 ^ v8) )
    JUMPOUT(0x140003723LL);
  return result;
}

```

## disassembly

```asm
0x1400036c0  sub     rsp, 48h
0x1400036c4  mov     eax, r8d
0x1400036c7  mov     r8, rdx
0x1400036ca  mov     edx, ecx
0x1400036cc  mov     rcx, cs:__security_cookie
0x1400036d3  xor     rcx, rsp
0x1400036d6  mov     [rsp+48h+var_8], rcx
0x1400036db  mov     [rsp+48h+var_28], r9b
0x1400036e0  lea     rcx, [rsp+48h+var_18]
0x1400036e5  mov     r9d, eax
0x1400036e8  call    _RNvMs_NtCs1fYFp9lPHeY_14handle_manager16GdiHandleManagerNtB4_16GdiHandleManager6Create
0x1400036ed  test    [rsp+48h+var_18], 1
0x1400036f2  jnz     short loc_1400036FB
0x1400036f4  mov     rax, [rsp+48h+var_10]
0x1400036f9  jmp     short loc_1400036FD
0x1400036fb  xor     eax, eax
0x1400036fd  mov     rcx, [rsp+48h+var_8]
0x140003702  xor     rcx, rsp
0x140003705  mov     rdx, cs:__security_cookie
0x14000370c  cmp     rdx, rcx
0x14000370f  jnz     short loc_140003716
0x140003711  add     rsp, 48h
0x140003715  retn
0x140003716  mov     rcx, [rsp+48h+var_8]
0x14000371b  xor     rcx, rsp; StackCookie
0x14000371e  call    __security_check_cookie
```
