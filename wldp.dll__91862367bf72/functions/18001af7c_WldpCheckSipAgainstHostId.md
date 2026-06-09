# WldpCheckSipAgainstHostId

- ea: `0x18001af7c`
- end: `0x18001b083`
- name: `WldpCheckSipAgainstHostId`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015118`

## callees

- `0x18001af7c`
- `0x18001e628`

## string_xrefs

- `0x18001afd8`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
__int64 __fastcall WldpCheckSipAgainstHostId(_QWORD *a1, int a2, char a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  wil::details::in1diag3 *retaddr; // [rsp+0h] [rbp+0h]

  if ( a3 )
  {
    if ( !a2 )
      return 0;
    v7 = a2 - 1;
    if ( !v7 )
      return 0;
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( !v10 )
        {
          v14 = *a1 - 0x4E084B59603BCC1FLL;
          if ( *a1 == 0x4E084B59603BCC1FLL )
            v14 = a1[1] - 0x51F37E29C6D224B7LL;
LABEL_20:
          if ( v14 )
            goto LABEL_5;
          return 0;
        }
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            if ( v12 != 1 )
            {
              v6 = 1203;
              return wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)v6,
                       (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                       (const char *)0x2029,
                       a5);
            }
            return 0;
          }
          v14 = *a1 - 790769LL;
          if ( *a1 == 790769 )
            v14 = a1[1] - 0x46000000000000C0LL;
          goto LABEL_20;
        }
      }
    }
    v15 = *a1 - 0x11D438CE06C9E010LL;
    if ( *a1 == 0x11D438CE06C9E010LL )
      v15 = a1[1] + 0x6FAF2CB4EFFF5C5ELL;
    if ( !v15 )
      return 0;
    v16 = *a1 - 0x11D438CE1A610570LL;
    if ( *a1 == 0x11D438CE1A610570LL )
      v16 = a1[1] + 0x6FAF2CB4EFFF5C5ELL;
    if ( !v16 )
      return 0;
    v5 = *a1 - 0x4DB527991629F04ELL;
    if ( *a1 == 0x4DB527991629F04ELL )
      v5 = a1[1] + 0x5414E8F01E531A71LL;
    goto LABEL_4;
  }
  v5 = *a1 - 0x11D08E59DE351A42LL;
  if ( *a1 == 0x11D08E59DE351A42LL )
    v5 = a1[1] + 0x116A3DB03FFFB874LL;
LABEL_4:
  if ( v5 )
  {
LABEL_5:
    v6 = 1209;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
             (const char *)0x2029,
             a5);
  }
  return 0;
}

```

## disassembly

```asm
0x18001af7c  test    r8b, r8b
0x18001af7f  jnz     short loc_18001AFA8
0x18001af81  mov     rax, [rcx]
0x18001af84  sub     rax, cs:qword_18004BCD8
0x18001af8b  jnz     short loc_18001AF98
0x18001af8d  mov     rax, [rcx+8]
0x18001af91  sub     rax, cs:qword_18004BCE0
0x18001af98  test    rax, rax
0x18001af9b  jz      loc_18001B028
0x18001afa1  mov     edx, 4B9h
0x18001afa6  jmp     short loc_18001AFD4
0x18001afa8  test    edx, edx
0x18001afaa  jz      short loc_18001B028
0x18001afac  sub     edx, 1
0x18001afaf  jz      short loc_18001B028
0x18001afb1  sub     edx, 1
0x18001afb4  jz      short loc_18001B02B
0x18001afb6  sub     edx, 1
0x18001afb9  jz      short loc_18001B02B
0x18001afbb  sub     edx, 1
0x18001afbe  jz      short loc_18001B003
0x18001afc0  sub     edx, 1
0x18001afc3  jz      short loc_18001B02B
0x18001afc5  sub     edx, 1
0x18001afc8  jz      short loc_18001AFEA
0x18001afca  cmp     edx, 1
0x18001afcd  jz      short loc_18001B028
0x18001afcf  mov     edx, 4B3h; void *
0x18001afd4  mov     rcx, [rsp+0]; this
0x18001afd8  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18001afdf  mov     r9d, 2029h; char *
0x18001afe5  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001afea  mov     rax, [rcx]
0x18001afed  sub     rax, cs:qword_18004BD68
0x18001aff4  jnz     short loc_18001B01A
0x18001aff6  mov     rax, [rcx+8]
0x18001affa  sub     rax, cs:qword_18004BD70
0x18001b001  jmp     short loc_18001B01A
0x18001b003  mov     rax, [rcx]
0x18001b006  sub     rax, cs:qword_18004BD38
0x18001b00d  jnz     short loc_18001B01A
0x18001b00f  mov     rax, [rcx+8]
0x18001b013  sub     rax, cs:qword_18004BD40
0x18001b01a  test    rax, rax
0x18001b01d  setz    al
0x18001b020  test    al, al
0x18001b022  jz      loc_18001AFA1
0x18001b028  xor     eax, eax
0x18001b02a  retn
0x18001b02b  mov     rax, [rcx]
0x18001b02e  sub     rax, cs:qword_18004BD28
0x18001b035  jnz     short loc_18001B042
0x18001b037  mov     rax, [rcx+8]
0x18001b03b  sub     rax, cs:qword_18004BD30
0x18001b042  test    rax, rax
0x18001b045  jz      short loc_18001B028
0x18001b047  mov     rax, [rcx]
0x18001b04a  sub     rax, cs:qword_18004BD58
0x18001b051  jnz     short loc_18001B05E
0x18001b053  mov     rax, [rcx+8]
0x18001b057  sub     rax, cs:qword_18004BD60
0x18001b05e  test    rax, rax
0x18001b061  jz      short loc_18001B028
0x18001b063  mov     rax, [rcx]
0x18001b066  sub     rax, cs:qword_18004BCB8
0x18001b06d  jnz     loc_18001AF98
0x18001b073  mov     rax, [rcx+8]
0x18001b077  sub     rax, cs:qword_18004BCC0
0x18001b07e  jmp     loc_18001AF98
```
