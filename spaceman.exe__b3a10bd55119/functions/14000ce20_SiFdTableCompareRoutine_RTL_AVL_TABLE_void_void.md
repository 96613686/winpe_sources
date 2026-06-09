# SiFdTableCompareRoutine(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x14000ce20`
- end: `0x14000ce60`
- name: `?SiFdTableCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `64`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, __int64 *FirstStruct, __int64 *SecondStruct)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000bcf0`
- `0x14000ce20`

## pseudocode

```c
__int64 __fastcall SiFdTableCompareRoutine(struct _RTL_AVL_TABLE *Table, __int64 *FirstStruct, __int64 *SecondStruct)
{
  __int64 v3; // rcx
  __int64 v4; // rdx

  v3 = *FirstStruct;
  v4 = *SecondStruct;
  if ( *(_QWORD *)(v3 + 4) == *(_QWORD *)(*SecondStruct + 4) && *(_QWORD *)(v3 + 12) == *(_QWORD *)(v4 + 12) )
    return 2;
  else
    return (unsigned int)SiIsBetterDrive(*(struct _SU_DRIVE_OBJECT **)(v3 + 88), *(struct _SU_DRIVE_OBJECT **)(v4 + 88)) == 0;
}

```

## disassembly

```asm
0x14000ce20  sub     rsp, 28h
0x14000ce24  mov     rcx, [rdx]
0x14000ce27  mov     rdx, [r8]
0x14000ce2a  mov     rax, [rcx+4]
0x14000ce2e  cmp     rax, [rdx+4]
0x14000ce32  jnz     short loc_14000CE45
0x14000ce34  mov     rax, [rcx+0Ch]
0x14000ce38  cmp     rax, [rdx+0Ch]
0x14000ce3c  jnz     short loc_14000CE45
0x14000ce3e  mov     eax, 2
0x14000ce43  jmp     short loc_14000CE5B
0x14000ce45  mov     rdx, [rdx+58h]; struct _SU_DRIVE_OBJECT *
0x14000ce49  mov     rcx, [rcx+58h]; struct _SU_DRIVE_OBJECT *
0x14000ce4d  call    ?SiIsBetterDrive@@YAHPEAU_SU_DRIVE_OBJECT@@0@Z; SiIsBetterDrive(_SU_DRIVE_OBJECT *,_SU_DRIVE_OBJECT *)
0x14000ce52  xor     ecx, ecx
0x14000ce54  test    eax, eax
0x14000ce56  setz    cl
0x14000ce59  mov     eax, ecx
0x14000ce5b  add     rsp, 28h
0x14000ce5f  retn
```
