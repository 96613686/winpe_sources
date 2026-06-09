# UdfUpdateScbTimeStamps

- ea: `0x14000cb6c`
- end: `0x14000cbc5`
- name: `UdfUpdateScbTimeStamps`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400010f0`
- `0x140004514`
- `0x14001662c`
- `0x1400316e8`
- `0x140051d74`

## callees

- `0x14000cb6c`

## pseudocode

```c
__int64 __fastcall UdfUpdateScbTimeStamps(__int64 a1, __int64 a2, __int64 a3)
{
  _DWORD *v3; // r9
  __int64 result; // rax

  v3 = (_DWORD *)(a3 + 4);
  result = MEMORY[0xFFFFF78000000014];
  if ( ((!a3 || (*v3 & 0x100) == 0) && (*(_QWORD *)(a2 + 472) = MEMORY[0xFFFFF78000000014], !a3) || (*v3 & 0x200) == 0)
    && (*(_QWORD *)(a2 + 480) = result, !a3)
    || (*v3 & 0x400) == 0 )
  {
    *(_QWORD *)(a2 + 488) = result;
  }
  *(_DWORD *)(a2 + 212) |= 0x10000u;
  return result;
}

```

## disassembly

```asm
0x14000cb6c  lea     r9, [r8+4]
0x14000cb70  mov     rax, 0FFFFF78000000014h
0x14000cb7a  mov     rax, [rax]
0x14000cb7d  test    r8, r8
0x14000cb80  jz      short loc_14000CB8B
0x14000cb82  test    dword ptr [r9], 100h
0x14000cb89  jnz     short loc_14000CB97
0x14000cb8b  mov     [rdx+1D8h], rax
0x14000cb92  test    r8, r8
0x14000cb95  jz      short loc_14000CBA0
0x14000cb97  test    dword ptr [r9], 200h
0x14000cb9e  jnz     short loc_14000CBAC
0x14000cba0  mov     [rdx+1E0h], rax
0x14000cba7  test    r8, r8
0x14000cbaa  jz      short loc_14000CBB5
0x14000cbac  test    dword ptr [r9], 400h
0x14000cbb3  jnz     short loc_14000CBBC
0x14000cbb5  mov     [rdx+1E8h], rax
0x14000cbbc  bts     dword ptr [rdx+0D4h], 10h
0x14000cbc4  retn
```
