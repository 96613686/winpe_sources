# CWdsMetadataValue::GetStringValue(ushort const * *)

- ea: `0x1800098a4`
- end: `0x1800098d5`
- name: `?GetStringValue@CWdsMetadataValue@@QEBAKPEAPEBG@Z`
- size: `49`
- prototype: `unsigned int __fastcall(CWdsMetadataValue *__hidden this, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800055b0`
- `0x180009990`
- `0x18000bc94`

## callees

- `0x1800098a4`
- `0x18000c274`

## pseudocode

```c
__int64 __fastcall CWdsMetadataValue::GetStringValue(CWdsMetadataValue *this, const unsigned __int16 **a2)
{
  unsigned int v2; // r8d

  v2 = 0;
  if ( *(_DWORD *)this == 1 )
    *a2 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  else
    return (unsigned int)ElValidateWin32_1(0xDu, (__int64)a2, 0, 0x60Fu);
  return v2;
}

```

## disassembly

```asm
0x1800098a4  sub     rsp, 28h
0x1800098a8  xor     r8d, r8d
0x1800098ab  cmp     dword ptr [rcx], 1
0x1800098ae  jnz     short loc_1800098B9
0x1800098b0  mov     rax, [rcx+8]
0x1800098b4  mov     [rdx], rax
0x1800098b7  jmp     short loc_1800098CC
0x1800098b9  mov     ecx, 0Dh
0x1800098be  mov     r9d, 60Fh
0x1800098c4  call    ElValidateWin32_1
0x1800098c9  mov     r8d, eax
0x1800098cc  mov     eax, r8d
0x1800098cf  add     rsp, 28h
0x1800098d3  retn
```
