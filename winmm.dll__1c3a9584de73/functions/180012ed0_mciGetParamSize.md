# mciGetParamSize

- ea: `0x180012ed0`
- end: `0x180012f20`
- name: `mciGetParamSize`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180011610`
- `0x180013408`

## callees

- `0x180012ed0`

## pseudocode

```c
__int64 __fastcall mciGetParamSize(int a1, int a2)
{
  __int64 result; // rax
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx

  result = 8;
  if ( a2 == 4 )
  {
    if ( a1 == 1 )
      return 12;
    if ( a1 == 8 )
      return 0;
    a2 = a1;
  }
  v3 = a2 - 1;
  if ( !v3 )
    return result;
  v4 = v3 - 1;
  if ( !v4 )
    return 4;
  v5 = v4 - 5;
  if ( !v5 )
    return 16;
  v6 = v5 - 1;
  if ( !v6 )
    return 4;
  v7 = v6 - 2;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( (unsigned int)(v8 - 1) >= 2 )
        return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012ed0  mov     eax, 8
0x180012ed5  cmp     edx, 4
0x180012ed8  jnz     short loc_180012EE9
0x180012eda  cmp     ecx, 1
0x180012edd  jnz     short loc_180012EE3
0x180012edf  lea     eax, [rdx+8]
0x180012ee2  retn
0x180012ee3  cmp     ecx, eax
0x180012ee5  jz      short loc_180012F11
0x180012ee7  mov     edx, ecx
0x180012ee9  sub     edx, 1
0x180012eec  jz      short locret_180012F1F
0x180012eee  sub     edx, 1
0x180012ef1  jz      short loc_180012F1A
0x180012ef3  sub     edx, 5
0x180012ef6  jz      short loc_180012F14
0x180012ef8  sub     edx, 1
0x180012efb  jz      short loc_180012F1A
0x180012efd  sub     edx, 2
0x180012f00  jz      short locret_180012F1F
0x180012f02  sub     edx, 1
0x180012f05  jz      short locret_180012F1F
0x180012f07  sub     edx, 1
0x180012f0a  jz      short locret_180012F1F
0x180012f0c  cmp     edx, 1
0x180012f0f  jz      short locret_180012F1F
0x180012f11  xor     eax, eax
0x180012f13  retn
0x180012f14  mov     eax, 10h
0x180012f19  retn
0x180012f1a  mov     eax, 4
0x180012f1f  retn
```
