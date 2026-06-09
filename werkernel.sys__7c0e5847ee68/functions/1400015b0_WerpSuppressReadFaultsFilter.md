# WerpSuppressReadFaultsFilter

- ea: `0x1400015b0`
- end: `0x1400015e2`
- name: `WerpSuppressReadFaultsFilter`
- size: `50`
- prototype: `_BOOL8 __fastcall(int, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c010`

## callees

- `0x1400015b0`

## pseudocode

```c
_BOOL8 __fastcall WerpSuppressReadFaultsFilter(int a1, __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rdx

  if ( (unsigned int)(a1 + 1073741819) > 1 )
    return 0;
  if ( *(_QWORD *)(*(_QWORD *)a2 + 32LL) )
    return 0;
  v3 = *(_QWORD *)(*(_QWORD *)a2 + 40LL);
  return v3 >= a3 && v3 < a3 + 248;
}

```

## disassembly

```asm
0x1400015b0  lea     eax, [rcx+3FFFFFFBh]
0x1400015b6  cmp     eax, 1
0x1400015b9  ja      short loc_1400015DF
0x1400015bb  mov     rax, [rdx]
0x1400015be  cmp     qword ptr [rax+20h], 0
0x1400015c3  jnz     short loc_1400015DF
0x1400015c5  mov     rdx, [rax+28h]
0x1400015c9  cmp     rdx, r8
0x1400015cc  jb      short loc_1400015DF
0x1400015ce  xor     eax, eax
0x1400015d0  lea     rcx, [r8+0F8h]
0x1400015d7  cmp     rdx, rcx
0x1400015da  setb    al
0x1400015dd  retn
0x1400015df  xor     eax, eax
0x1400015e1  retn
```
