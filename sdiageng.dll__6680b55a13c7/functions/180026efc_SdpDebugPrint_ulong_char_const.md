# SdpDebugPrint(ulong,char const *,...)

- ea: `0x180026efc`
- end: `0x180026f98`
- name: `?SdpDebugPrint@@YAXKPEBDZZ`
- size: `156`
- prototype: `void(ULONG Level, const char *Format, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007f0c`
- `0x180008184`
- `0x180026fa0`
- `0x180028038`
- `0x1800293a0`

## callees

- `0x180026efc`
- `0x1800298c0`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180026f41`
- `msvcrt!_vsnprintf` at `0x180026f41`
- `ntdll!DbgPrintEx` at `0x180026f6f`
- `ntdll!DbgPrintEx` at `0x180026f6f`

## pseudocode

```c
void SdpDebugPrint(ULONG Level, const char *Format, ...)
{
  unsigned int v3; // eax
  char Buffer[1024]; // [rsp+30h] [rbp-418h] BYREF
  va_list va; // [rsp+460h] [rbp+18h] BYREF

  va_start(va, Format);
  v3 = _vsnprintf(Buffer, 0x3FFu, Format, va);
  if ( v3 < 0x400 )
  {
    if ( v3 == 1023 )
      Buffer[1023] = 0;
    DbgPrintEx(0x81u, Level, "%s", Buffer);
  }
}

```

## disassembly

```asm
0x180026efc  mov     r11, rsp
0x180026eff  mov     [r11+10h], rdx
0x180026f03  mov     [r11+18h], r8
0x180026f07  mov     [r11+20h], r9
0x180026f0b  push    rbx
0x180026f0c  sub     rsp, 440h
0x180026f13  mov     rax, cs:__security_cookie
0x180026f1a  xor     rax, rsp
0x180026f1d  mov     [rsp+448h+var_18], rax
0x180026f25  mov     ebx, ecx
0x180026f27  mov     [rsp+448h+var_428], 0
0x180026f30  mov     r8, rdx; Format
0x180026f33  lea     rcx, [rsp+448h+Buffer]; Buffer
0x180026f38  mov     edx, 3FFh; BufferCount
0x180026f3d  lea     r9, [r11+18h]; ArgList
0x180026f41  call    cs:__imp__vsnprintf
0x180026f47  test    eax, eax
0x180026f49  js      short loc_180026F77
0x180026f4b  cmp     eax, 3FFh
0x180026f50  ja      short loc_180026F77
0x180026f52  jnz     short loc_180026F5C
0x180026f54  mov     [rsp+448h+var_19], 0
0x180026f5c  lea     r9, [rsp+448h+Buffer]
0x180026f61  mov     edx, ebx; Level
0x180026f63  lea     r8, Format; "%s"
0x180026f6a  mov     ecx, 81h; ComponentId
0x180026f6f  call    cs:__imp_DbgPrintEx
0x180026f75  jmp     short loc_180026F7F
0x180026f77  mov     [rsp+448h+var_19], 0
0x180026f7f  mov     rcx, [rsp+448h+var_18]
0x180026f87  xor     rcx, rsp; StackCookie
0x180026f8a  call    __security_check_cookie
0x180026f8f  add     rsp, 440h
0x180026f96  pop     rbx
0x180026f97  retn
```
