# RtlTrimNtPathSegment

- ea: `0x18001b698`
- end: `0x18001b746`
- name: `RtlTrimNtPathSegment`
- size: `174`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18001b30c`

## callees

- `0x180007568`
- `0x180007c60`
- `0x18001b698`

## string_xrefs

- `0x18001b6b6`: `onecore\base\lstring\path.cpp`
- `0x18001b6d1`: `RtlTrimNtPathSegment`

## pseudocode

```c
__int64 __fastcall RtlTrimNtPathSegment(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  __int64 v6; // r8
  _QWORD *v7; // r11
  __int64 result; // rax
  __int16 *v9; // r10
  __int64 v10; // r9
  __int16 *v11; // rdx
  __int16 *v12; // rcx
  __int16 v13; // ax

  *a2 = 0;
  *a3 = 0;
  if ( RtlIsLUnicodeStringValid(a1) )
  {
    v9 = (__int16 *)v5[2];
    v10 = v6;
    v11 = v9;
    v12 = (__int16 *)((char *)v9 + *v5);
    if ( v9 < v12 )
    {
      do
      {
        v13 = *v11++;
        if ( v13 != 92 )
          break;
        v10 += 2;
      }
      while ( v11 < v12 );
      if ( v11 < v12 )
      {
        do
        {
          if ( *--v12 != 92 )
            break;
          v6 += 2;
        }
        while ( v12 > v9 );
      }
    }
    *v7 = v10;
    result = 0;
    *a3 = v6;
  }
  else
  {
    RtlReportErrorOrigination((__int64)v5, v4, -1073741811);
    return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001b698  push    rbx
0x18001b69a  sub     rsp, 40h
0x18001b69e  mov     rbx, r8
0x18001b6a1  mov     r11, rdx
0x18001b6a4  xor     r8d, r8d
0x18001b6a7  mov     [rdx], r8
0x18001b6aa  mov     [rbx], r8
0x18001b6ad  call    RtlIsLUnicodeStringValid
0x18001b6b2  test    al, al
0x18001b6b4  jnz     short loc_18001B6F5
0x18001b6b6  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18001b6bd  mov     [rsp+48h+var_18], 224h
0x18001b6c6  mov     [rsp+48h+var_28], rax
0x18001b6cb  mov     r8d, 0C000000Dh
0x18001b6d1  lea     rax, aRtltrimntpaths; "RtlTrimNtPathSegment"
0x18001b6d8  mov     [rsp+48h+var_20], rax
0x18001b6dd  lea     rax, aRtlislunicodes; "RtlIsLUnicodeStringValid(Segment)"
0x18001b6e4  mov     [rsp+48h+var_10], rax
0x18001b6e9  call    RtlReportErrorOrigination
0x18001b6ee  mov     eax, 0C000000Dh
0x18001b6f3  jmp     short loc_18001B740
0x18001b6f5  mov     r10, [rcx+10h]
0x18001b6f9  mov     r9, r8
0x18001b6fc  mov     rcx, [rcx]
0x18001b6ff  mov     rdx, r10
0x18001b702  add     rcx, r10
0x18001b705  cmp     r10, rcx
0x18001b708  jnb     short loc_18001B738
0x18001b70a  movzx   eax, word ptr [rdx]
0x18001b70d  add     rdx, 2
0x18001b711  cmp     ax, 5Ch ; '\'
0x18001b715  jnz     short loc_18001B720
0x18001b717  add     r9, 2
0x18001b71b  cmp     rdx, rcx
0x18001b71e  jb      short loc_18001B70A
0x18001b720  cmp     rdx, rcx
0x18001b723  jnb     short loc_18001B738
0x18001b725  sub     rcx, 2
0x18001b729  cmp     word ptr [rcx], 5Ch ; '\'
0x18001b72d  jnz     short loc_18001B738
0x18001b72f  add     r8, 2
0x18001b733  cmp     rcx, r10
0x18001b736  ja      short loc_18001B725
0x18001b738  mov     [r11], r9
0x18001b73b  xor     eax, eax
0x18001b73d  mov     [rbx], r8
0x18001b740  add     rsp, 40h
0x18001b744  pop     rbx
0x18001b745  retn
```
