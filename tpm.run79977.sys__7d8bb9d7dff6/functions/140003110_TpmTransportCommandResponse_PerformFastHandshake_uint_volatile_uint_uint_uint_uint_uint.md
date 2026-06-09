# TpmTransportCommandResponse::PerformFastHandshake(uint volatile *,uint,uint,uint,uint,uint)

- ea: `0x140003110`
- end: `0x1400031ff`
- name: `?PerformFastHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIII@Z`
- size: `239`
- prototype: `__int64 __fastcall(TpmTransportCommandResponse *__hidden this, volatile unsigned int *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002a90`
- `0x140002d80`
- `0x140002f80`
- `0x140003110`

## callees

- `0x140003110`
- `0x1400078b8`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponse::PerformFastHandshake(
        TpmTransportCommandResponse *this,
        volatile unsigned int *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7)
{
  if ( !a2 )
    return 3221225485LL;
  while ( 1 )
  {
    if ( (a6 & *a2) == a5 )
      return 0;
    if ( (a4 & *a2) != a3 )
      break;
    if ( !a7 )
      return 258;
    if ( MEMORY[0xFFFFF78000000008] >= MEMORY[0xFFFFF78000000008] + 10 * (unsigned __int64)a7 )
      return TpmTransportCommandResponse::PerformFastHandshake(this, a2, a3, a4, a5, a6, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_2fc68934a9f83936555335448f322e27_Traceguids);
  return 3221225862LL;
}

```

## disassembly

```asm
0x140003110  push    rsi
0x140003112  sub     rsp, 40h
0x140003116  mov     r11d, r8d
0x140003119  mov     r10, rdx
0x14000311c  mov     rsi, rcx
0x14000311f  test    rdx, rdx
0x140003122  jz      loc_1400031C2
0x140003128  mov     edx, [rsp+48h+arg_30]
0x14000312f  mov     rax, ds:0FFFFF78000000008h
0x140003139  mov     [rsp+48h+arg_0], rbx
0x14000313e  mov     ebx, [rsp+48h+arg_28]
0x140003142  lea     rcx, [rdx+rdx*4]
0x140003146  mov     [rsp+48h+arg_8], rdi
0x14000314b  mov     edi, [rsp+48h+arg_20]
0x14000314f  lea     r8, [rax+rcx*2]
0x140003153  mov     eax, [r10]
0x140003156  mov     ecx, eax
0x140003158  and     ecx, ebx
0x14000315a  cmp     ecx, edi
0x14000315c  jz      short loc_140003199
0x14000315e  and     eax, r9d
0x140003161  cmp     eax, r11d
0x140003164  jnz     short loc_1400031C9
0x140003166  test    edx, edx
0x140003168  jz      short loc_1400031AC
0x14000316a  mov     rax, ds:0FFFFF78000000008h
0x140003174  cmp     rax, r8
0x140003177  jb      short loc_140003153
0x140003179  mov     [rsp+48h+var_18], 0; unsigned int
0x140003181  mov     r8d, r11d; unsigned int
0x140003184  mov     [rsp+48h+var_20], ebx; unsigned int
0x140003188  mov     rdx, r10; volatile unsigned int *
0x14000318b  mov     rcx, rsi; this
0x14000318e  mov     [rsp+48h+var_28], edi; unsigned int
0x140003192  call    ?PerformFastHandshake@TpmTransportCommandResponse@@AEAAJPECIIIIII@Z; TpmTransportCommandResponse::PerformFastHandshake(uint volatile *,uint,uint,uint,uint,uint)
0x140003197  jmp     short loc_14000319B
0x140003199  xor     eax, eax
0x14000319b  mov     rbx, [rsp+48h+arg_0]
0x1400031a0  mov     rdi, [rsp+48h+arg_8]
0x1400031a5  add     rsp, 40h
0x1400031a9  pop     rsi
0x1400031aa  retn
0x1400031ac  mov     rbx, [rsp+48h+arg_0]
0x1400031b1  mov     eax, 102h
0x1400031b6  mov     rdi, [rsp+48h+arg_8]
0x1400031bb  add     rsp, 40h
0x1400031bf  pop     rsi
0x1400031c0  retn
0x1400031c2  mov     eax, 0C000000Dh
0x1400031c7  jmp     short loc_1400031A5
0x1400031c9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400031d0  lea     rax, WPP_GLOBAL_Control
0x1400031d7  cmp     rcx, rax
0x1400031da  jz      short loc_1400031F8
0x1400031dc  mov     eax, [rcx+2Ch]
0x1400031df  test    al, 1
0x1400031e1  jz      short loc_1400031F8
0x1400031e3  mov     rcx, [rcx+18h]
0x1400031e7  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x1400031ee  mov     edx, 14h
0x1400031f3  call    WPP_SF_
0x1400031f8  mov     eax, 0C0000186h
0x1400031fd  jmp     short loc_14000319B
```
