# SdpDebugPrint(ulong,char const *,...)

- ea: `0x18000b094`
- end: `0x18000b134`
- name: `?SdpDebugPrint@@YAXKPEBDZZ`
- size: `160`
- prototype: `void(ULONG Level, const char *Format, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b13c`
- `0x18000b234`

## callees

- `0x18000b094`
- `0x18000c860`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x18000b0d0`
- `msvcrt!_vsnprintf` at `0x18000b0d0`
- `ntdll!DbgPrintEx` at `0x18000b104`
- `ntdll!DbgPrintEx` at `0x18000b104`

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
0x18000b094  mov     r11, rsp
0x18000b097  mov     [r11+10h], rdx
0x18000b09b  mov     [r11+18h], r8
0x18000b09f  mov     [r11+20h], r9
0x18000b0a3  push    rbx
0x18000b0a4  sub     rsp, 440h
0x18000b0ab  mov     rax, cs:__security_cookie
0x18000b0b2  xor     rax, rsp
0x18000b0b5  mov     [rsp+448h+var_18], rax
0x18000b0bd  mov     ebx, ecx
0x18000b0bf  lea     r9, [r11+18h]; ArgList
0x18000b0c3  mov     r8, rdx; Format
0x18000b0c6  lea     rcx, [rsp+448h+Buffer]; Buffer
0x18000b0cb  mov     edx, 3FFh; BufferCount
0x18000b0d0  call    cs:__imp__vsnprintf
0x18000b0d7  nop     dword ptr [rax+rax+00h]
0x18000b0dc  test    eax, eax
0x18000b0de  js      short loc_18000B112
0x18000b0e0  cmp     eax, 3FFh
0x18000b0e5  ja      short loc_18000B112
0x18000b0e7  jnz     short loc_18000B0F1
0x18000b0e9  mov     [rsp+448h+var_19], 0
0x18000b0f1  lea     r9, [rsp+448h+Buffer]
0x18000b0f6  mov     edx, ebx; Level
0x18000b0f8  lea     r8, Format; "%s"
0x18000b0ff  mov     ecx, 81h; ComponentId
0x18000b104  call    cs:__imp_DbgPrintEx
0x18000b10b  nop     dword ptr [rax+rax+00h]
0x18000b110  jmp     short loc_18000B11A
0x18000b112  mov     [rsp+448h+var_19], 0
0x18000b11a  mov     rcx, [rsp+448h+var_18]
0x18000b122  xor     rcx, rsp; StackCookie
0x18000b125  call    __security_check_cookie
0x18000b12a  add     rsp, 440h
0x18000b131  pop     rbx
0x18000b132  retn
```
