# TTTableLength

- ea: `0x180016438`
- end: `0x180016491`
- name: `TTTableLength`
- size: `89`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fd44`
- `0x180012a18`
- `0x18001357c`
- `0x180014f98`
- `0x180016770`
- `0x18001d5f8`
- `0x180027480`
- `0x180028114`
- `0x180028f78`
- `0x180029228`
- `0x180029d3c`

## callees

- `0x180013514`
- `0x180016438`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall TTTableLength(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  if ( !(unsigned int)GetTTDirectory((__int64 *)a1, a2, (__int64)&v4) )
    return 0;
  result = HIDWORD(v4);
  if ( (unsigned int)(DWORD2(v4) + HIDWORD(v4)) < DWORD2(v4)
    || (unsigned int)(DWORD2(v4) + HIDWORD(v4)) > *(_DWORD *)(a1 + 8) )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180016438  push    rbx
0x18001643a  sub     rsp, 40h
0x18001643e  mov     rax, cs:__security_cookie
0x180016445  xor     rax, rsp
0x180016448  mov     [rsp+48h+var_18], rax
0x18001644d  xorps   xmm0, xmm0
0x180016450  lea     r8, [rsp+48h+var_28]
0x180016455  movups  [rsp+48h+var_28], xmm0
0x18001645a  mov     rbx, rcx
0x18001645d  call    GetTTDirectory
0x180016462  test    eax, eax
0x180016464  jnz     short loc_18001647B
0x180016466  xor     eax, eax
0x180016468  mov     rcx, [rsp+48h+var_18]
0x18001646d  xor     rcx, rsp; StackCookie
0x180016470  call    __security_check_cookie
0x180016475  add     rsp, 40h
0x180016479  pop     rbx
0x18001647a  retn
0x18001647b  mov     ecx, dword ptr [rsp+48h+var_28+8]
0x18001647f  mov     eax, dword ptr [rsp+48h+var_28+0Ch]
0x180016483  lea     edx, [rcx+rax]
0x180016486  cmp     edx, ecx
0x180016488  jb      short loc_180016466
0x18001648a  cmp     edx, [rbx+8]
0x18001648d  jbe     short loc_180016468
0x18001648f  jmp     short loc_180016466
```
