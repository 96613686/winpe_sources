# LDAPClientPrint

- ea: `0x1800037a8`
- end: `0x180003837`
- name: `LDAPClientPrint`
- size: `143`
- prototype: ``
- caller_count: `275`
- callee_count: `4`
- tags: ``

## callers

- `0x1800013c0`
- `0x1800014e0`
- `0x180001550`
- `0x1800016b8`
- `0x180001790`
- `0x1800018d0`
- `0x1800022c0`
- `0x180002770`
- `0x1800030f0`
- `0x1800032d0`
- `0x180003570`
- `0x180003840`
- `0x18000461c`
- `0x180004740`
- `0x180004e60`
- `0x180005170`
- `0x1800057a0`
- `0x1800061a0`
- `0x180006510`
- `0x180006bc0`
- `0x180006d80`
- `0x180008070`
- `0x180008660`
- `0x180008710`
- `0x180009040`
- `0x1800094a0`
- `0x18000a280`
- `0x18000a358`
- `0x18000adb0`
- `0x18000b440`
- `0x18000b5c8`
- `0x18000b760`
- `0x18000b860`
- `0x18000b990`
- `0x18000bb00`
- `0x18000bbf0`
- `0x18000bf40`
- `0x18000c8c4`
- `0x18000ce40`
- `0x18000da50`
- `0x18000df44`
- `0x18000e0d0`
- `0x180011020`
- `0x1800112b0`
- `0x180011c80`
- `0x180011f50`
- `0x180012400`
- `0x180012ab0`
- `0x180013610`
- `0x180014060`

## callees

- `0x1800037a8`
- `0x180032bd8`
- `0x180034510`
- `0x180034f30`

## pseudocode

```c
unsigned int LDAPClientPrint(int a1, const char *a2, ...)
{
  unsigned int result; // eax
  char Buffer[2048]; // [rsp+30h] [rbp-818h] BYREF
  va_list va; // [rsp+860h] [rbp+18h] BYREF

  va_start(va, a2);
  result = vsnprintf(Buffer, 0x7FFu, a2, va);
  if ( result < 0x800 )
  {
    if ( result == 2047 )
      Buffer[2047] = 0;
    return LDAPClientTraceEvent(a1, (__int64)Buffer);
  }
  return result;
}

```

## disassembly

```asm
0x1800037a8  mov     r11, rsp
0x1800037ab  mov     [r11+10h], rdx
0x1800037af  mov     [r11+18h], r8
0x1800037b3  mov     [r11+20h], r9
0x1800037b7  push    rbx
0x1800037b8  sub     rsp, 840h
0x1800037bf  mov     rax, cs:__security_cookie
0x1800037c6  xor     rax, rsp
0x1800037c9  mov     [rsp+848h+var_18], rax
0x1800037d1  mov     ebx, ecx
0x1800037d3  mov     [rsp+848h+var_828], 0
0x1800037dc  mov     r8, rdx; Format
0x1800037df  lea     rcx, [rsp+848h+Buffer]; Buffer
0x1800037e4  mov     edx, 7FFh; BufferCount
0x1800037e9  lea     r9, [r11+18h]; ArgList
0x1800037ed  call    _vsnprintf
0x1800037f2  test    eax, eax
0x1800037f4  js      short loc_180003815
0x1800037f6  cmp     eax, 7FFh
0x1800037fb  ja      short loc_180003815
0x1800037fd  jnz     short loc_180003807
0x1800037ff  mov     [rsp+848h+var_19], 0
0x180003807  lea     rdx, [rsp+848h+Buffer]
0x18000380c  mov     ecx, ebx
0x18000380e  call    LDAPClientTraceEvent
0x180003813  jmp     short loc_18000381D
0x180003815  mov     [rsp+848h+var_19], 0
0x18000381d  mov     rcx, [rsp+848h+var_18]
0x180003825  xor     rcx, rsp; StackCookie
0x180003828  call    __security_check_cookie
0x18000382d  add     rsp, 840h
0x180003834  pop     rbx
0x180003835  retn
```
