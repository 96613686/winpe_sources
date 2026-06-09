# ReplicationStatusToCopyState(uint)

- ea: `0x180011b24`
- end: `0x180011b85`
- name: `?ReplicationStatusToCopyState@@YAGI@Z`
- size: `97`
- prototype: `unsigned __int16 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012594`
- `0x180013f60`

## callees

- `0x180011b24`

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
0x180011b24  mov     eax, 0Fh
0x180011b29  cmp     ecx, 8
0x180011b2c  ja      short loc_180011B61
0x180011b2e  jz      short loc_180011B53
0x180011b30  sub     ecx, 1
0x180011b33  jz      short loc_180011B7F
0x180011b35  sub     ecx, 1
0x180011b38  jz      short loc_180011B53
0x180011b3a  sub     ecx, 1
0x180011b3d  jz      short loc_180011B53
0x180011b3f  sub     ecx, 1
0x180011b42  jz      short loc_180011B5A
0x180011b44  sub     ecx, 1
0x180011b47  jz      short locret_180011B58
0x180011b49  sub     ecx, 1
0x180011b4c  jz      short loc_180011B53
0x180011b4e  cmp     ecx, 1
0x180011b51  jnz     short locret_180011B58
0x180011b53  mov     eax, 2
0x180011b58  retn
0x180011b5a  mov     eax, 5
0x180011b5f  retn
0x180011b61  sub     ecx, 9
0x180011b64  jz      short loc_180011B53
0x180011b66  sub     ecx, 1
0x180011b69  jz      short loc_180011B53
0x180011b6b  sub     ecx, 1
0x180011b6e  jz      short loc_180011B7F
0x180011b70  sub     ecx, 1
0x180011b73  jz      short loc_180011B7F
0x180011b75  sub     ecx, 1
0x180011b78  jz      short loc_180011B53
0x180011b7a  sub     ecx, 1
0x180011b7d  jmp     short loc_180011B51
0x180011b7f  mov     eax, 4
0x180011b84  retn
```
