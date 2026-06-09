# VerifyXmlChar

- ea: `0x100417b10`
- end: `0x100417b5d`
- name: `VerifyXmlChar`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x10040bc80`
- `0x100417b70`
- `0x100417c20`

## callees

- `0x100417b10`

## pseudocode

```c
__int64 __fastcall VerifyXmlChar(unsigned int a1)
{
  if ( a1 < 0xD800
    && (a1 > 0x1F
     || (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)(unsigned __int16)a1 >> 8] + (unsigned __int8)a1) & 1) != 0)
    || a1 - 57344 <= 0x1FFD
    || a1 - 0x10000 <= 0xFFFFF )
  {
    return 0;
  }
  else
  {
    return 3222072875LL;
  }
}

```

## disassembly

```asm
0x100417b10  cmp     ecx, 0D800h
0x100417b16  jnb     short loc_100417B3A
0x100417b18  cmp     ecx, 1Fh
0x100417b1b  ja      short loc_100417B5A
0x100417b1d  movzx   edx, cx
0x100417b20  lea     r8, ?g_apCharTables@@3PAPEAEA; uchar * near * g_apCharTables
0x100417b27  mov     eax, edx
0x100417b29  movzx   edx, dl
0x100417b2c  shr     rax, 8
0x100417b30  mov     rax, [r8+rax*8]
0x100417b34  test    byte ptr [rdx+rax], 1
0x100417b38  jnz     short loc_100417B5A
0x100417b3a  lea     eax, [rcx-0E000h]
0x100417b40  cmp     eax, 1FFDh
0x100417b45  jbe     short loc_100417B5A
0x100417b47  lea     eax, [rcx-10000h]
0x100417b4d  cmp     eax, 0FFFFFh
0x100417b52  jbe     short loc_100417B5A
0x100417b54  mov     eax, 0C00CEE2Bh
0x100417b59  retn
0x100417b5a  xor     eax, eax
0x100417b5c  retn
```
