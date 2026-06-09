# ReplicationStatusToCopyState(uint)

- ea: `0x180011c60`
- end: `0x180011cbf`
- name: `?ReplicationStatusToCopyState@@YAGI@Z`
- size: `95`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800126cc`
- `0x180014050`

## callees

- `0x180011c60`

## pseudocode

```c
__int64 __fastcall ReplicationStatusToCopyState(unsigned int a1)
{
  __int64 result; // rax
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  bool v8; // zf
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx

  result = 15;
  if ( a1 > 8 )
  {
    v9 = a1 - 9;
    if ( !v9 )
      return 2;
    v10 = v9 - 1;
    if ( !v10 )
      return 2;
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v8 = v13 == 1;
LABEL_10:
          if ( !v8 )
            return result;
        }
        return 2;
      }
    }
    return 4;
  }
  if ( a1 == 8 )
    return 2;
  v2 = a1 - 1;
  if ( !v2 )
    return 4;
  v3 = v2 - 1;
  if ( !v3 )
    return 2;
  v4 = v3 - 1;
  if ( !v4 )
    return 2;
  v5 = v4 - 1;
  if ( !v5 )
    return 5;
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 == 1;
      goto LABEL_10;
    }
    return 2;
  }
  return result;
}

```

## disassembly

```asm
0x180011c60  mov     eax, 0Fh
0x180011c65  cmp     ecx, 8
0x180011c68  ja      short loc_180011C9B
0x180011c6a  jz      short loc_180011C8F
0x180011c6c  sub     ecx, 1
0x180011c6f  jz      short loc_180011CB9
0x180011c71  sub     ecx, 1
0x180011c74  jz      short loc_180011C8F
0x180011c76  sub     ecx, 1
0x180011c79  jz      short loc_180011C8F
0x180011c7b  sub     ecx, 1
0x180011c7e  jz      short loc_180011C95
0x180011c80  sub     ecx, 1
0x180011c83  jz      short locret_180011C94
0x180011c85  sub     ecx, 1
0x180011c88  jz      short loc_180011C8F
0x180011c8a  cmp     ecx, 1
0x180011c8d  jnz     short locret_180011C94
0x180011c8f  mov     eax, 2
0x180011c94  retn
0x180011c95  mov     eax, 5
0x180011c9a  retn
0x180011c9b  sub     ecx, 9
0x180011c9e  jz      short loc_180011C8F
0x180011ca0  sub     ecx, 1
0x180011ca3  jz      short loc_180011C8F
0x180011ca5  sub     ecx, 1
0x180011ca8  jz      short loc_180011CB9
0x180011caa  sub     ecx, 1
0x180011cad  jz      short loc_180011CB9
0x180011caf  sub     ecx, 1
0x180011cb2  jz      short loc_180011C8F
0x180011cb4  sub     ecx, 1
0x180011cb7  jmp     short loc_180011C8D
0x180011cb9  mov     eax, 4
0x180011cbe  retn
```
