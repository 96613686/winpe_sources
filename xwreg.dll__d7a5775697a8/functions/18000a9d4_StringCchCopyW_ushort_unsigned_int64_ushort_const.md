# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000a9d4`
- end: `0x18000aa11`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x180007860`
- `0x180007b28`
- `0x180008b4c`
- `0x1800095c0`
- `0x1800099b4`
- `0x18000a168`
- `0x18000af74`
- `0x18000b114`
- `0x18000b4b8`
- `0x18000bac8`
- `0x18000c240`
- `0x18000c428`
- `0x18000c5c8`
- `0x18000ca6c`
- `0x18000d070`
- `0x18000daac`
- `0x18000ded4`
- `0x18000e140`
- `0x18000e40c`
- `0x18000e61c`
- `0x18000e8bc`
- `0x18000ee04`
- `0x18000f238`
- `0x18000f484`
- `0x18000f7c4`
- `0x180010dcc`

## callees

- `0x18000a9d4`
- `0x18000aa18`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18000a9d4  sub     rsp, 38h
0x18000a9d8  mov     rax, rdx
0x18000a9db  test    rdx, rdx
0x18000a9de  jz      short loc_18000A9FB
0x18000a9e0  cmp     rax, 7FFFFFFFh
0x18000a9e6  jbe     short loc_18000A9EF
0x18000a9e8  mov     edx, 80070057h; cchDest
0x18000a9ed  jmp     short loc_18000AA05
0x18000a9ef  mov     r9, r8; pszSrc
0x18000a9f2  call    StringCopyWorkerW
0x18000a9f7  mov     edx, eax
0x18000a9f9  jmp     short loc_18000AA0A
0x18000a9fb  mov     edx, 80070057h
0x18000aa00  test    rax, rax
0x18000aa03  jz      short loc_18000AA0A
0x18000aa05  xor     eax, eax
0x18000aa07  mov     [rcx], ax
0x18000aa0a  mov     eax, edx
0x18000aa0c  add     rsp, 38h
0x18000aa10  retn
```
