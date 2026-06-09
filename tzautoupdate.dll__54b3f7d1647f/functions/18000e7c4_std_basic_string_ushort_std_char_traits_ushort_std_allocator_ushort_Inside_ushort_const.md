# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x18000e7c4`
- end: `0x18000e7fe`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `58`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000eae0`
- `0x180015938`

## callees

- `0x18000e7c4`

## pseudocode

```c
bool __fastcall std::wstring::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r8

  if ( !a2 )
    return 0;
  v2 = a1[3] < 8u ? a1 : (_QWORD *)*a1;
  if ( a2 < (unsigned __int64)v2 )
    return 0;
  if ( a1[3] < 8u )
    v3 = a1;
  else
    v3 = (_QWORD *)*a1;
  return (unsigned __int64)v3 + 2 * a1[2] > a2;
}

```

## disassembly

```asm
0x18000e7c4  test    rdx, rdx
0x18000e7c7  jz      short loc_18000E7FB
0x18000e7c9  cmp     qword ptr [rcx+18h], 8
0x18000e7ce  jb      short loc_18000E7D5
0x18000e7d0  mov     rax, [rcx]
0x18000e7d3  jmp     short loc_18000E7D8
0x18000e7d5  mov     rax, rcx
0x18000e7d8  cmp     rdx, rax
0x18000e7db  jb      short loc_18000E7FB
0x18000e7dd  cmp     qword ptr [rcx+18h], 8
0x18000e7e2  jb      short loc_18000E7E9
0x18000e7e4  mov     r8, [rcx]
0x18000e7e7  jmp     short loc_18000E7EC
0x18000e7e9  mov     r8, rcx
0x18000e7ec  mov     rax, [rcx+10h]
0x18000e7f0  lea     rcx, [r8+rax*2]
0x18000e7f4  cmp     rcx, rdx
0x18000e7f7  setnbe  al
0x18000e7fa  retn
0x18000e7fb  xor     al, al
0x18000e7fd  retn
```
