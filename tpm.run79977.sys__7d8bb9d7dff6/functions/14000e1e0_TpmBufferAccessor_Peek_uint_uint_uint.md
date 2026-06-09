# TpmBufferAccessor::Peek<uint>(uint,uint *)

- ea: `0x14000e1e0`
- end: `0x14000e224`
- name: `??$Peek@I@TpmBufferAccessor@@QEAAJIPEAI@Z`
- size: `68`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ba38`
- `0x14000bbdc`
- `0x1400128a8`
- `0x140012abc`
- `0x14001300c`
- `0x1400135d0`
- `0x14001f3f0`

## callees

- `0x14000e1e0`

## pseudocode

```c
__int64 __fastcall TpmBufferAccessor::Peek<unsigned int>(__int64 a1, unsigned int a2, _BYTE *a3)
{
  _BYTE *v3; // rdx
  __int64 result; // rax

  if ( a2 + 4 < a2 || (unsigned __int64)a2 + 4 > *(unsigned int *)(a1 + 8) )
    return 2147483653LL;
  v3 = (_BYTE *)(a2 + *(_QWORD *)a1);
  result = 0;
  *a3 = v3[3];
  a3[1] = v3[2];
  a3[2] = v3[1];
  a3[3] = *v3;
  return result;
}

```

## disassembly

```asm
0x14000e1e0  lea     eax, [rdx+4]
0x14000e1e3  cmp     eax, edx
0x14000e1e5  jb      short loc_14000E21E
0x14000e1e7  mov     r9d, edx
0x14000e1ea  mov     edx, [rcx+8]
0x14000e1ed  lea     rax, [r9+4]
0x14000e1f1  cmp     rax, rdx
0x14000e1f4  ja      short loc_14000E21E
0x14000e1f6  mov     rdx, [rcx]
0x14000e1f9  add     rdx, r9
0x14000e1fc  xor     eax, eax
0x14000e1fe  movzx   ecx, byte ptr [rdx+3]
0x14000e202  mov     [r8], cl
0x14000e205  movzx   ecx, byte ptr [rdx+2]
0x14000e209  mov     [r8+1], cl
0x14000e20d  movzx   ecx, byte ptr [rdx+1]
0x14000e211  mov     [r8+2], cl
0x14000e215  movzx   ecx, byte ptr [rdx]
0x14000e218  mov     [r8+3], cl
0x14000e21c  retn
0x14000e21e  mov     eax, 80000005h
0x14000e223  retn
```
