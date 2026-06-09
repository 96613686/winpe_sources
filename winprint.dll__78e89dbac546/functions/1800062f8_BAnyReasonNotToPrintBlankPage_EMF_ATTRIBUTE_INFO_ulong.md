# BAnyReasonNotToPrintBlankPage(_EMF_ATTRIBUTE_INFO *,ulong)

- ea: `0x1800062f8`
- end: `0x18000631e`
- name: `?BAnyReasonNotToPrintBlankPage@@YAHPEAU_EMF_ATTRIBUTE_INFO@@K@Z`
- size: `38`
- prototype: `__int64 __fastcall(struct _EMF_ATTRIBUTE_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017d0`
- `0x180007210`

## callees

- `0x1800062f8`

## pseudocode

```c
__int64 __fastcall BAnyReasonNotToPrintBlankPage(struct _EMF_ATTRIBUTE_INFO *a1, unsigned int a2)
{
  unsigned int v2; // r8d

  v2 = 0;
  if ( (*((_BYTE *)a1 + 56) & 2) != 0
    && *((_DWORD *)a1 + 11) <= *((_DWORD *)a1 + 12)
    && (!*((_DWORD *)a1 + 18) || a2 <= *((_DWORD *)a1 + 8)) )
  {
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x1800062f8  xor     r8d, r8d
0x1800062fb  test    byte ptr [rcx+38h], 2
0x1800062ff  jz      short loc_18000631A
0x180006301  mov     eax, [rcx+30h]
0x180006304  cmp     [rcx+2Ch], eax
0x180006307  ja      short loc_18000631A
0x180006309  cmp     [rcx+48h], r8d
0x18000630d  jz      short loc_180006314
0x18000630f  cmp     edx, [rcx+20h]
0x180006312  ja      short loc_18000631A
0x180006314  mov     r8d, 1
0x18000631a  mov     eax, r8d
0x18000631d  retn
```
