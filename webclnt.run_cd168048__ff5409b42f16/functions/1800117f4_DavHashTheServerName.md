# DavHashTheServerName

- ea: `0x1800117f4`
- end: `0x1800118b2`
- name: `DavHashTheServerName`
- size: `190`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180005970`
- `0x180005d38`
- `0x180010478`
- `0x180011c8c`
- `0x180012e2c`
- `0x180013054`

## callees

- `0x18000b7b4`
- `0x18000b99c`
- `0x1800117f4`

## pseudocode

```c
__int64 __fastcall DavHashTheServerName(const wchar_t *a1)
{
  wchar_t v3; // dx
  __int16 v4; // bx
  int v5; // r8d
  const wchar_t *v6; // r10
  int v7; // eax
  int v8; // ecx
  bool v9; // zf
  unsigned int v10; // ebx

  if ( a1 )
  {
    v3 = *a1;
    v4 = 0;
    if ( *a1 )
    {
      v5 = 0;
      v6 = a1;
      do
      {
        v7 = v3 << v5;
        v3 = *++v6;
        v8 = v5 + 4;
        v4 += v7;
        v9 = v5 == 24;
        v5 = 0;
        if ( !v9 )
          v5 = v8;
      }
      while ( v3 );
    }
    v10 = v4 & 0x1FF;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x22u,
        (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
        a1);
    return v10;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x21u, (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids);
    return 512;
  }
}

```

## disassembly

```asm
0x1800117f4  push    rbx
0x1800117f6  sub     rsp, 30h
0x1800117fa  xor     r11d, r11d
0x1800117fd  mov     r9, rcx
0x180011800  test    rcx, rcx
0x180011803  jnz     short loc_180011839
0x180011805  mov     rcx, cs:WPP_GLOBAL_Control
0x18001180c  lea     rax, WPP_GLOBAL_Control
0x180011813  cmp     rcx, rax
0x180011816  jz      short loc_180011832
0x180011818  test    byte ptr [rcx+1Ch], 1
0x18001181c  jz      short loc_180011832
0x18001181e  mov     rcx, [rcx+10h]
0x180011822  lea     edx, [r9+21h]
0x180011826  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001182d  call    WPP_SF_
0x180011832  mov     eax, 200h
0x180011837  jmp     short loc_1800118AC
0x180011839  movzx   edx, word ptr [rcx]
0x18001183c  mov     ebx, r11d
0x18001183f  test    dx, dx
0x180011842  jz      short loc_180011872
0x180011844  mov     r8d, r11d
0x180011847  mov     r10, r9
0x18001184a  mov     ecx, r8d
0x18001184d  movzx   eax, dx
0x180011850  shl     eax, cl
0x180011852  lea     r10, [r10+2]
0x180011856  movzx   edx, word ptr [r10]
0x18001185a  lea     ecx, [r8+4]
0x18001185e  add     ebx, eax
0x180011860  mov     eax, r8d
0x180011863  cmp     eax, 18h
0x180011866  mov     r8d, r11d
0x180011869  cmovnz  r8d, ecx
0x18001186d  test    dx, dx
0x180011870  jnz     short loc_18001184A
0x180011872  and     ebx, 1FFh
0x180011878  mov     rcx, cs:WPP_GLOBAL_Control
0x18001187f  lea     rax, WPP_GLOBAL_Control
0x180011886  cmp     rcx, rax
0x180011889  jz      short loc_1800118AA
0x18001188b  test    byte ptr [rcx+1Ch], 2
0x18001188f  jz      short loc_1800118AA
0x180011891  mov     rcx, [rcx+10h]
0x180011895  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x18001189c  mov     edx, 22h ; '"'
0x1800118a1  mov     [rsp+38h+var_18], ebx
0x1800118a5  call    WPP_SF_Sd
0x1800118aa  mov     eax, ebx
0x1800118ac  add     rsp, 30h
0x1800118b0  pop     rbx
0x1800118b1  retn
```
