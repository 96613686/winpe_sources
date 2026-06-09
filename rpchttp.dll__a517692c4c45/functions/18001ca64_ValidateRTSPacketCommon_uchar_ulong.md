# ValidateRTSPacketCommon(uchar *,ulong)

- ea: `0x18001ca64`
- end: `0x18001ca9a`
- name: `?ValidateRTSPacketCommon@@YAPEAEPEAEK@Z`
- size: `54`
- prototype: `unsigned __int8 *__fastcall(unsigned __int8 *, unsigned int)`
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dfe8`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`
- `0x18001c114`
- `0x18001c1c0`
- `0x18001c268`
- `0x18001c288`
- `0x18001c2a8`
- `0x18001c388`
- `0x18001c42c`
- `0x18001c49c`
- `0x18001c4f0`
- `0x18001c5b0`
- `0x18001c6b0`
- `0x18001c714`
- `0x18001c7b4`
- `0x18001c828`
- `0x18001c86c`
- `0x18001c91c`
- `0x18001c960`
- `0x18001c99c`
- `0x18001c9dc`
- `0x18001ca44`

## callees

- `0x18001ca64`

## pseudocode

```c
unsigned __int8 *__fastcall ValidateRTSPacketCommon(unsigned __int8 *a1, unsigned int a2)
{
  if ( a2 >= 0x14
    && *((_WORD *)a1 + 4) == (_WORD)a2
    && *a1 == 5
    && !a1[1]
    && a1[3] == 3
    && a1[4] == 16
    && !*((_WORD *)a1 + 5)
    && !*((_DWORD *)a1 + 3) )
  {
    return a1 + 20;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18001ca64  cmp     edx, 14h
0x18001ca67  jb      short loc_18001CA97
0x18001ca69  cmp     [rcx+8], dx
0x18001ca6d  jnz     short loc_18001CA97
0x18001ca6f  cmp     byte ptr [rcx], 5
0x18001ca72  jnz     short loc_18001CA97
0x18001ca74  xor     eax, eax
0x18001ca76  cmp     [rcx+1], al
0x18001ca79  ja      short loc_18001CA97
0x18001ca7b  cmp     byte ptr [rcx+3], 3
0x18001ca7f  jnz     short loc_18001CA97
0x18001ca81  cmp     byte ptr [rcx+4], 10h
0x18001ca85  jnz     short loc_18001CA97
0x18001ca87  cmp     [rcx+0Ah], ax
0x18001ca8b  jnz     short loc_18001CA97
0x18001ca8d  cmp     [rcx+0Ch], eax
0x18001ca90  jnz     short loc_18001CA97
0x18001ca92  lea     rax, [rcx+14h]
0x18001ca96  retn
0x18001ca97  xor     eax, eax
0x18001ca99  retn
```
