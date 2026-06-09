# DrvOpen

- ea: `0x180002bf0`
- end: `0x180002c77`
- name: `DrvOpen`
- size: `135`
- prototype: `HDRVR __stdcall(LPCWSTR szDriverName, LPCWSTR szSectionName, LPARAM lParam2)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002bf0`
- `0x180002c80`
- `0x180012d70`

## pseudocode

```c
HDRVR __stdcall DrvOpen(LPCWSTR szDriverName, LPCWSTR szSectionName, LPARAM lParam2)
{
  LPCWSTR v7; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v7 = szSectionName;
    if ( !szSectionName )
      v7 = L"NULL !!";
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids,
      (_DWORD)szDriverName,
      (__int64)v7);
  }
  return (HDRVR)InternalOpenDriver(szDriverName, szSectionName, lParam2);
}

```

## disassembly

```asm
0x180002bf0  mov     [rsp+arg_0], rbx
0x180002bf5  mov     [rsp+arg_8], rsi
0x180002bfa  push    rdi
0x180002bfb  sub     rsp, 30h
0x180002bff  mov     rsi, r8
0x180002c02  mov     rbx, rdx
0x180002c05  mov     rdi, rcx
0x180002c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c0f  lea     rax, WPP_GLOBAL_Control
0x180002c16  cmp     rcx, rax
0x180002c19  jz      short loc_180002C24
0x180002c1b  test    dword ptr [rcx+1Ch], 400000h
0x180002c22  jnz     short loc_180002C41
0x180002c24  mov     r8, rsi
0x180002c27  mov     rdx, rbx
0x180002c2a  mov     rcx, rdi
0x180002c2d  mov     rbx, [rsp+38h+arg_0]
0x180002c32  mov     rsi, [rsp+38h+arg_8]
0x180002c37  add     rsp, 30h
0x180002c3b  pop     rdi
0x180002c3c  jmp     InternalOpenDriver
0x180002c41  cmp     byte ptr [rcx+19h], 4
0x180002c45  jb      short loc_180002C24
0x180002c47  mov     rcx, [rcx+10h]
0x180002c4b  lea     rdx, aNull; "NULL !!"
0x180002c52  test    rbx, rbx
0x180002c55  lea     r8, WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids
0x180002c5c  mov     rax, rbx
0x180002c5f  mov     r9, rdi
0x180002c62  cmovz   rax, rdx
0x180002c66  mov     edx, 0Ah
0x180002c6b  mov     [rsp+38h+var_18], rax
0x180002c70  call    WPP_SF_SS
0x180002c75  jmp     short loc_180002C24
```
