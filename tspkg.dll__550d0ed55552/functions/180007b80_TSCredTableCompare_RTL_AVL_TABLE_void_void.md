# TSCredTableCompare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x180007b80`
- end: `0x180007bd4`
- name: `?TSCredTableCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `84`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007b80`

## pseudocode

```c
__int64 __fastcall TSCredTableCompare(struct _RTL_AVL_TABLE *Table, __int64 *FirstStruct, __int64 *SecondStruct)
{
  __int64 v3; // r9
  __int64 v4; // r8
  unsigned __int64 v5; // rcx
  __int64 result; // rax
  unsigned __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // edx

  v3 = *SecondStruct;
  v4 = *FirstStruct;
  v5 = *(_QWORD *)(v3 + 128);
  if ( *(_QWORD *)(*FirstStruct + 128) > v5 )
    return 1;
  if ( *(_QWORD *)(*FirstStruct + 128) < v5 )
    return 0;
  v7 = *(_QWORD *)(v3 + 120);
  if ( *(_QWORD *)(v4 + 120) > v7 )
    return 1;
  if ( *(_QWORD *)(v4 + 120) < v7 )
    return 0;
  v8 = *(_DWORD *)(v3 + 116);
  if ( *(_DWORD *)(v4 + 116) > v8 )
    return 1;
  if ( *(_DWORD *)(v4 + 116) < v8 )
    return 0;
  v9 = *(_DWORD *)(v3 + 112);
  v10 = *(_DWORD *)(v4 + 112);
  if ( v10 > v9 )
    return 1;
  result = 2;
  if ( v10 < v9 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180007b80  mov     r9, [r8]
0x180007b83  mov     r8, [rdx]
0x180007b86  mov     rcx, [r9+80h]
0x180007b8d  cmp     [r8+80h], rcx
0x180007b94  ja      short loc_180007BCE
0x180007b96  jnb     short loc_180007B9B
0x180007b98  xor     eax, eax
0x180007b9a  retn
0x180007b9b  mov     rax, [r9+78h]
0x180007b9f  cmp     [r8+78h], rax
0x180007ba3  ja      short loc_180007BCE
0x180007ba5  jb      short loc_180007B98
0x180007ba7  mov     eax, [r9+74h]
0x180007bab  cmp     [r8+74h], eax
0x180007baf  jg      short loc_180007BCE
0x180007bb1  jl      short loc_180007B98
0x180007bb3  mov     ecx, [r9+70h]
0x180007bb7  mov     edx, [r8+70h]
0x180007bbb  cmp     edx, ecx
0x180007bbd  ja      short loc_180007BCE
0x180007bbf  xor     r8d, r8d
0x180007bc2  mov     eax, 2
0x180007bc7  cmp     edx, ecx
0x180007bc9  cmovb   eax, r8d
0x180007bcd  retn
0x180007bce  mov     eax, 1
0x180007bd3  retn
```
