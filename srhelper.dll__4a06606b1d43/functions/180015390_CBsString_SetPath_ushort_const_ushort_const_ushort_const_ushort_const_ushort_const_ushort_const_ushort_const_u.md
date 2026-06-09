# CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180015390`
- end: `0x1800153bb`
- name: `?SetPath@CBsString@@QEAAJPEBG000000000@Z`
- size: `43`
- prototype: `__int64 __fastcall(CBsString *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800029d8`
- `0x180002e9c`
- `0x180003968`
- `0x180003b24`
- `0x1800055a4`
- `0x18000bf70`

## callees

- `0x180015390`
- `0x180015590`

## pseudocode

```c
__int64 __fastcall CBsString::SetPath(
        CBsString *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  _WORD *v5; // rdx

  if ( !a2 || !*a2 )
    return 2147942487LL;
  if ( *((_DWORD *)this + 2) )
  {
    v5 = *(_WORD **)this;
    *((_DWORD *)this + 2) = 0;
    *v5 = 0;
  }
  return CBsString::_CombinePathImpl(this, a2, a3, a2);
}

```

## disassembly

```asm
0x180015390  xor     eax, eax
0x180015392  mov     r9, rdx; unsigned __int16 *
0x180015395  test    rdx, rdx
0x180015398  jz      short loc_1800153B5
0x18001539a  cmp     [rdx], ax
0x18001539d  jz      short loc_1800153B5
0x18001539f  cmp     [rcx+8], eax
0x1800153a2  jz      short loc_1800153AD
0x1800153a4  mov     rdx, [rcx]
0x1800153a7  mov     [rcx+8], eax
0x1800153aa  mov     [rdx], ax
0x1800153ad  mov     rdx, r9; unsigned __int16 *
0x1800153b0  jmp     ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800153b5  mov     eax, 80070057h
0x1800153ba  retn
```
