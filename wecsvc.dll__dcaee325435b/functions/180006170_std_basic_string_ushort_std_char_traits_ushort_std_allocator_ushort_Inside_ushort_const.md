# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x180006170`
- end: `0x1800061aa`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `58`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180006508`
- `0x1800066c4`

## callees

- `0x180006170`

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
0x180006170  test    rdx, rdx
0x180006173  jz      short loc_1800061A7
0x180006175  cmp     qword ptr [rcx+18h], 8
0x18000617a  jb      short loc_180006181
0x18000617c  mov     rax, [rcx]
0x18000617f  jmp     short loc_180006184
0x180006181  mov     rax, rcx
0x180006184  cmp     rdx, rax
0x180006187  jb      short loc_1800061A7
0x180006189  cmp     qword ptr [rcx+18h], 8
0x18000618e  jb      short loc_180006195
0x180006190  mov     r8, [rcx]
0x180006193  jmp     short loc_180006198
0x180006195  mov     r8, rcx
0x180006198  mov     rax, [rcx+10h]
0x18000619c  lea     rcx, [r8+rax*2]
0x1800061a0  cmp     rcx, rdx
0x1800061a3  setnbe  al
0x1800061a6  retn
0x1800061a7  xor     al, al
0x1800061a9  retn
```
