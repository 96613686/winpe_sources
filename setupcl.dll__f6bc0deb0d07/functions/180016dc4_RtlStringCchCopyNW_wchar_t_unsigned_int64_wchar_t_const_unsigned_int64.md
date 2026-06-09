# RtlStringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x180016dc4`
- end: `0x180016e20`
- name: `?RtlStringCchCopyNW@@YAJPEA_W_KPEB_W1@Z`
- size: `92`
- prototype: `__int64 __fastcall(wchar_t *, __int64, wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016a5c`

## callees

- `0x180016dc4`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyNW(wchar_t *a1, __int64 a2, wchar_t *a3, unsigned __int64 a4)
{
  __int64 result; // rax
  __int64 v6; // r8
  wchar_t *v7; // rax

  if ( a4 <= 0x7FFFFFFE )
  {
    v6 = 780;
    do
    {
      if ( !a4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --a4;
      --v6;
    }
    while ( v6 );
    v7 = a1 - 1;
    if ( v6 )
      v7 = a1;
    *v7 = 0;
    return v6 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = 3221225485LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180016dc4  xor     edx, edx
0x180016dc6  mov     rax, r8
0x180016dc9  cmp     r9, 7FFFFFFEh
0x180016dd0  jbe     short loc_180016DDB
0x180016dd2  mov     eax, 0C000000Dh
0x180016dd7  mov     [rcx], dx
0x180016dda  retn
0x180016ddb  mov     r8d, 30Ch
0x180016de1  test    r9, r9
0x180016de4  jz      short loc_180016E05
0x180016de6  movzx   r10d, word ptr [rax]
0x180016dea  test    r10w, r10w
0x180016dee  jz      short loc_180016E05
0x180016df0  mov     [rcx], r10w
0x180016df4  add     rax, 2
0x180016df8  add     rcx, 2
0x180016dfc  dec     r9
0x180016dff  sub     r8, 1
0x180016e03  jnz     short loc_180016DE1
0x180016e05  test    r8, r8
0x180016e08  lea     rax, [rcx-2]
0x180016e0c  cmovnz  rax, rcx
0x180016e10  neg     r8
0x180016e13  mov     [rax], dx
0x180016e16  sbb     eax, eax
0x180016e18  not     eax
0x180016e1a  and     eax, 80000005h
0x180016e1f  retn
```
