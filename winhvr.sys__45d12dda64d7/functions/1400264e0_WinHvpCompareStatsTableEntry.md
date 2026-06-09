# WinHvpCompareStatsTableEntry

- ea: `0x1400264e0`
- end: `0x14002654f`
- name: `WinHvpCompareStatsTableEntry`
- size: `111`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400264e0`

## pseudocode

```c
__int64 __fastcall WinHvpCompareStatsTableEntry(
        struct _RTL_GENERIC_TABLE *Table,
        _BYTE *FirstStruct,
        _BYTE *SecondStruct)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  unsigned __int64 v6; // rax
  unsigned int v7; // eax
  bool v8; // cf
  bool v9; // cc
  unsigned int v10; // eax
  unsigned __int8 v11; // al
  unsigned __int8 v13; // al
  unsigned __int8 v14; // cl

  v3 = *(_DWORD *)FirstStruct;
  if ( *(_DWORD *)FirstStruct < *(_DWORD *)SecondStruct )
    return 0;
  if ( v3 > *(_DWORD *)SecondStruct )
    return 1;
  v4 = v3 - 1;
  if ( !v4 )
  {
    v13 = FirstStruct[23];
    v14 = SecondStruct[23];
    if ( v14 <= v13 )
      return 2 - (unsigned int)(v14 < v13);
    return 0;
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = *((_QWORD *)FirstStruct + 1);
    if ( v5 == 0xFFFF )
    {
      v8 = v6 < *((_QWORD *)SecondStruct + 1);
      v9 = v6 <= *((_QWORD *)SecondStruct + 1);
    }
    else
    {
      if ( v6 > *((_QWORD *)SecondStruct + 1) )
        return 1;
      if ( v6 < *((_QWORD *)SecondStruct + 1) )
        return 0;
      v7 = *((_DWORD *)FirstStruct + 4);
      v8 = v7 < *((_DWORD *)SecondStruct + 4);
      v9 = v7 <= *((_DWORD *)SecondStruct + 4);
    }
  }
  else
  {
    v10 = *((_DWORD *)FirstStruct + 2);
    v8 = v10 < *((_DWORD *)SecondStruct + 2);
    v9 = v10 <= *((_DWORD *)SecondStruct + 2);
  }
  if ( v8 )
    return 0;
  if ( !v9 )
    return 1;
  v11 = FirstStruct[23];
  if ( v11 >= SecondStruct[23] )
  {
    if ( v11 <= SecondStruct[23] )
      return 2;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1400264e0  mov     ecx, [rdx]
0x1400264e2  cmp     ecx, [r8]
0x1400264e5  jl      short loc_14002654C
0x1400264e7  jg      short loc_140026545
0x1400264e9  sub     ecx, 1
0x1400264ec  jz      short loc_140026533
0x1400264ee  sub     ecx, 1
0x1400264f1  jz      short loc_140026516
0x1400264f3  mov     rax, [rdx+8]
0x1400264f7  cmp     ecx, 0FFFFh
0x1400264fd  jz      short loc_140026510
0x1400264ff  cmp     rax, [r8+8]
0x140026503  ja      short loc_140026545
0x140026505  jb      short loc_14002654C
0x140026507  mov     eax, [rdx+10h]
0x14002650a  cmp     eax, [r8+10h]
0x14002650e  jmp     short loc_14002651D
0x140026510  cmp     rax, [r8+8]
0x140026514  jmp     short loc_14002651D
0x140026516  mov     eax, [rdx+8]
0x140026519  cmp     eax, [r8+8]
0x14002651d  jb      short loc_14002654C
0x14002651f  ja      short loc_140026545
0x140026521  mov     al, [rdx+17h]
0x140026524  cmp     al, [r8+17h]
0x140026528  jb      short loc_14002654C
0x14002652a  ja      short loc_140026545
0x14002652c  mov     eax, 2
0x140026531  retn
0x140026533  mov     al, [rdx+17h]
0x140026536  mov     cl, [r8+17h]
0x14002653a  cmp     cl, al
0x14002653c  ja      short loc_14002654C
0x14002653e  sbb     eax, eax
0x140026540  add     eax, 2
0x140026543  retn
0x140026545  mov     eax, 1
0x14002654a  retn
0x14002654c  xor     eax, eax
0x14002654e  retn
```
