# CACSecurityPage::AUIAuth2Auth(AUI_DOT11_AUTH_ALGORITHM)

- ea: `0x180006f98`
- end: `0x180007008`
- name: `?AUIAuth2Auth@CACSecurityPage@@AEAA?AW4_DOT11_AUTH_ALGORITHM@@W4AUI_DOT11_AUTH_ALGORITHM@@@Z`
- size: `112`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007ae4`
- `0x180009380`
- `0x18000bd88`
- `0x18000d834`

## callees

- `0x180006f98`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::AUIAuth2Auth(__int64 a1, int a2)
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
0x180006f98  mov     ecx, 1
0x180006f9d  cmp     edx, 6
0x180006fa0  jg      short loc_180006FDB
0x180006fa2  jz      short loc_180006FD4
0x180006fa4  sub     edx, ecx
0x180006fa6  jz      short loc_180007005
0x180006fa8  sub     edx, ecx
0x180006faa  jz      short loc_180006FCD
0x180006fac  sub     edx, ecx
0x180006fae  jz      short loc_180006FC6
0x180006fb0  sub     edx, ecx
0x180006fb2  jz      short loc_180006FBF
0x180006fb4  cmp     edx, ecx
0x180006fb6  jnz     short loc_180007005
0x180006fb8  mov     ecx, 5
0x180006fbd  jmp     short loc_180007005
0x180006fbf  mov     ecx, 4
0x180006fc4  jmp     short loc_180007005
0x180006fc6  mov     ecx, 3
0x180006fcb  jmp     short loc_180007005
0x180006fcd  mov     ecx, 2
0x180006fd2  jmp     short loc_180007005
0x180006fd4  mov     ecx, 6
0x180006fd9  jmp     short loc_180007005
0x180006fdb  sub     edx, 7
0x180006fde  jz      short loc_180007000
0x180006fe0  sub     edx, ecx
0x180006fe2  jz      short loc_180006FF9
0x180006fe4  sub     edx, ecx
0x180006fe6  jz      short loc_180006FF2
0x180006fe8  sub     edx, 2
0x180006feb  jnz     short loc_180007005
0x180006fed  lea     ecx, [rdx+0Bh]
0x180006ff0  jmp     short loc_180007005
0x180006ff2  mov     ecx, 9
0x180006ff7  jmp     short loc_180007005
0x180006ff9  mov     ecx, 8
0x180006ffe  jmp     short loc_180007005
0x180007000  mov     ecx, 7
0x180007005  mov     eax, ecx
0x180007007  retn
```
