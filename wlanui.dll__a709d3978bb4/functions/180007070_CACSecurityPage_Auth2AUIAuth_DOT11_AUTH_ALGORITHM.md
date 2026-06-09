# CACSecurityPage::Auth2AUIAuth(_DOT11_AUTH_ALGORITHM)

- ea: `0x180007070`
- end: `0x1800070e0`
- name: `?Auth2AUIAuth@CACSecurityPage@@AEAA?AW4AUI_DOT11_AUTH_ALGORITHM@@W4_DOT11_AUTH_ALGORITHM@@@Z`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c050`
- `0x18000c824`

## callees

- `0x180007070`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::Auth2AUIAuth(__int64 a1, int a2)
{
  unsigned int v2; // ecx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx

  v2 = 1;
  if ( a2 > 6 )
  {
    v7 = a2 - 7;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 == 2 )
            return 11;
        }
        else
        {
          return 9;
        }
      }
      else
      {
        return 8;
      }
    }
    else
    {
      return 7;
    }
  }
  else if ( a2 == 6 )
  {
    return 6;
  }
  else
  {
    v3 = a2 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            if ( v6 == 1 )
              return 5;
          }
          else
          {
            return 4;
          }
        }
        else
        {
          return 3;
        }
      }
      else
      {
        return 2;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180007070  mov     ecx, 1
0x180007075  cmp     edx, 6
0x180007078  jg      short loc_1800070B3
0x18000707a  jz      short loc_1800070AC
0x18000707c  sub     edx, ecx
0x18000707e  jz      short loc_1800070DD
0x180007080  sub     edx, ecx
0x180007082  jz      short loc_1800070A5
0x180007084  sub     edx, ecx
0x180007086  jz      short loc_18000709E
0x180007088  sub     edx, ecx
0x18000708a  jz      short loc_180007097
0x18000708c  cmp     edx, ecx
0x18000708e  jnz     short loc_1800070DD
0x180007090  mov     ecx, 5
0x180007095  jmp     short loc_1800070DD
0x180007097  mov     ecx, 4
0x18000709c  jmp     short loc_1800070DD
0x18000709e  mov     ecx, 3
0x1800070a3  jmp     short loc_1800070DD
0x1800070a5  mov     ecx, 2
0x1800070aa  jmp     short loc_1800070DD
0x1800070ac  mov     ecx, 6
0x1800070b1  jmp     short loc_1800070DD
0x1800070b3  sub     edx, 7
0x1800070b6  jz      short loc_1800070D8
0x1800070b8  sub     edx, ecx
0x1800070ba  jz      short loc_1800070D1
0x1800070bc  sub     edx, ecx
0x1800070be  jz      short loc_1800070CA
0x1800070c0  cmp     edx, 2
0x1800070c3  jnz     short loc_1800070DD
0x1800070c5  lea     ecx, [rdx+9]
0x1800070c8  jmp     short loc_1800070DD
0x1800070ca  mov     ecx, 9
0x1800070cf  jmp     short loc_1800070DD
0x1800070d1  mov     ecx, 8
0x1800070d6  jmp     short loc_1800070DD
0x1800070d8  mov     ecx, 7
0x1800070dd  mov     eax, ecx
0x1800070df  retn
```
