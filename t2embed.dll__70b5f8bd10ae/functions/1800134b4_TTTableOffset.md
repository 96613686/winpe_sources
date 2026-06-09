# TTTableOffset

- ea: `0x1800134b4`
- end: `0x18001350c`
- name: `TTTableOffset`
- size: `88`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f298`
- `0x18000fd44`
- `0x18000fe8c`
- `0x180010018`
- `0x1800110d0`
- `0x1800119f8`
- `0x1800120bc`
- `0x180012a18`
- `0x18001357c`
- `0x18001400c`
- `0x180014f98`
- `0x180016770`
- `0x180017480`
- `0x1800190a4`
- `0x18001cb94`
- `0x18001d5f8`
- `0x180028114`
- `0x180028388`
- `0x180028c2c`
- `0x180028f78`
- `0x180029228`
- `0x180029d3c`

## callees

- `0x1800134b4`
- `0x180013514`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall TTTableOffset(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  if ( !(unsigned int)GetTTDirectory((__int64 *)a1, a2, (__int64)&v4) )
    return 0;
  result = DWORD2(v4);
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
0x1800134b4  push    rbx
0x1800134b6  sub     rsp, 40h
0x1800134ba  mov     rax, cs:__security_cookie
0x1800134c1  xor     rax, rsp
0x1800134c4  mov     [rsp+48h+var_18], rax
0x1800134c9  xorps   xmm0, xmm0
0x1800134cc  lea     r8, [rsp+48h+var_28]
0x1800134d1  movups  [rsp+48h+var_28], xmm0
0x1800134d6  mov     rbx, rcx
0x1800134d9  call    GetTTDirectory
0x1800134de  test    eax, eax
0x1800134e0  jz      short loc_1800134F0
0x1800134e2  mov     eax, dword ptr [rsp+48h+var_28+8]
0x1800134e6  mov     edx, dword ptr [rsp+48h+var_28+0Ch]
0x1800134ea  add     edx, eax
0x1800134ec  cmp     edx, eax
0x1800134ee  jnb     short loc_1800134F4
0x1800134f0  xor     eax, eax
0x1800134f2  jmp     short loc_1800134F9
0x1800134f4  cmp     edx, [rbx+8]
0x1800134f7  ja      short loc_1800134F0
0x1800134f9  mov     rcx, [rsp+48h+var_18]
0x1800134fe  xor     rcx, rsp; StackCookie
0x180013501  call    __security_check_cookie
0x180013506  add     rsp, 40h
0x18001350a  pop     rbx
0x18001350b  retn
```
