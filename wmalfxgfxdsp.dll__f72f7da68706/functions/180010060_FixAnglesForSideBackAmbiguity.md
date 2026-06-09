# FixAnglesForSideBackAmbiguity

- ea: `0x180010060`
- end: `0x18001014a`
- name: `FixAnglesForSideBackAmbiguity`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000fdb4`

## callees

- `0x180010060`

## pseudocode

```c
char __fastcall FixAnglesForSideBackAmbiguity(__int16 a1, __int16 a2, __int64 a3)
{
  int v4; // edx
  int v6; // r10d
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx

  v4 = a2 & 0x210;
  if ( (a1 & 0x10) != 0 && (LOBYTE(v7) = (a1 & 0x200) == 0, ((v4 == 512) & (unsigned __int8)v7) != 0)
    || (a1 & 0x200) != 0 && (a1 & 0x10) == 0 && v4 == 16 )
  {
    v8 = 0;
    do
    {
      if ( 1 << v8 == 512 )
        break;
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (int)v8 < 11 );
    v9 = 0;
    do
    {
      if ( 1 << v9 == 16 )
        break;
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (int)v9 < 11 );
    v7 = *(_DWORD *)(a3 + 4 * v9);
    *(_DWORD *)(a3 + 4 * v8) = v7;
  }
  v6 = a2 & 0x420;
  if ( (a1 & 0x20) != 0 && (LOBYTE(v7) = (a1 & 0x400) == 0, ((v6 == 1024) & (unsigned __int8)v7) != 0)
    || (a1 & 0x400) != 0 && (a1 & 0x20) == 0 && v6 == 32 )
  {
    v10 = 0;
    do
    {
      if ( 1 << v10 == 1024 )
        break;
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (int)v10 < 11 );
    v11 = 0;
    do
    {
      if ( 1 << v11 == 32 )
        break;
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (int)v11 < 11 );
    v7 = *(_DWORD *)(a3 + 4 * v11);
    *(_DWORD *)(a3 + 4 * v10) = v7;
  }
  return v7;
}

```

## disassembly

```asm
0x180010060  mov     [rsp+arg_0], rbx
0x180010065  mov     r10d, edx
0x180010068  mov     r11d, ecx
0x18001006b  and     edx, 210h
0x180010071  mov     r9d, ecx
0x180010074  mov     ebx, 1
0x180010079  and     r11d, 10h
0x18001007d  jnz     short loc_1800100A6
0x18001007f  bt      r9d, 9
0x180010084  jb      short loc_1800100BD
0x180010086  mov     edx, r9d
0x180010089  and     r10d, 420h
0x180010090  mov     r11d, 400h
0x180010096  and     edx, 20h
0x180010099  jnz     short loc_1800100F9
0x18001009b  test    r11d, r9d
0x18001009e  jnz     short loc_18001010D
0x1800100a0  mov     rbx, [rsp+arg_0]
0x1800100a5  retn
0x1800100a6  cmp     edx, 200h
0x1800100ac  setz    cl
0x1800100af  bt      r9d, 9
0x1800100b4  setnb   al
0x1800100b7  test    al, cl
0x1800100b9  jnz     short loc_1800100C7
0x1800100bb  jmp     short loc_18001007F
0x1800100bd  test    r11d, r11d
0x1800100c0  jnz     short loc_180010086
0x1800100c2  cmp     edx, 10h
0x1800100c5  jnz     short loc_180010086
0x1800100c7  xor     edx, edx
0x1800100c9  mov     ecx, edx
0x1800100cb  mov     eax, ebx
0x1800100cd  shl     eax, cl
0x1800100cf  cmp     eax, 200h
0x1800100d4  jz      short loc_1800100DD
0x1800100d6  add     edx, ebx
0x1800100d8  cmp     edx, 0Bh
0x1800100db  jl      short loc_1800100C9
0x1800100dd  xor     ecx, ecx
0x1800100df  mov     eax, ebx
0x1800100e1  shl     eax, cl
0x1800100e3  cmp     eax, 10h
0x1800100e6  jz      short loc_1800100EF
0x1800100e8  add     ecx, ebx
0x1800100ea  cmp     ecx, 0Bh
0x1800100ed  jl      short loc_1800100DF
0x1800100ef  mov     eax, [r8+rcx*4]
0x1800100f3  mov     [r8+rdx*4], eax
0x1800100f7  jmp     short loc_180010086
0x1800100f9  cmp     r10d, r11d
0x1800100fc  setz    cl
0x1800100ff  bt      r9d, 0Ah
0x180010104  setnb   al
0x180010107  test    al, cl
0x180010109  jnz     short loc_180010117
0x18001010b  jmp     short loc_18001009B
0x18001010d  test    edx, edx
0x18001010f  jnz     short loc_1800100A0
0x180010111  cmp     r10d, 20h ; ' '
0x180010115  jnz     short loc_1800100A0
0x180010117  xor     edx, edx
0x180010119  mov     ecx, edx
0x18001011b  mov     eax, ebx
0x18001011d  shl     eax, cl
0x18001011f  cmp     eax, r11d
0x180010122  jz      short loc_18001012B
0x180010124  add     edx, ebx
0x180010126  cmp     edx, 0Bh
0x180010129  jl      short loc_180010119
0x18001012b  xor     ecx, ecx
0x18001012d  mov     eax, ebx
0x18001012f  shl     eax, cl
0x180010131  cmp     eax, 20h ; ' '
0x180010134  jz      short loc_18001013D
0x180010136  add     ecx, ebx
0x180010138  cmp     ecx, 0Bh
0x18001013b  jl      short loc_18001012D
0x18001013d  mov     eax, [r8+rcx*4]
0x180010141  mov     [r8+rdx*4], eax
0x180010145  jmp     loc_1800100A0
```
