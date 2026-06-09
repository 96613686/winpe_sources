# CUsbDevice::GetInterfaceAssociationDescriptorCount(void)

- ea: `0x1800094c8`
- end: `0x180009517`
- name: `?GetInterfaceAssociationDescriptorCount@CUsbDevice@@QEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(CUsbDevice *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045d0`

## callees

- `0x1800094c8`

## pseudocode

```c
__int64 __fastcall CUsbDevice::GetInterfaceAssociationDescriptorCount(CUsbDevice *this)
{
  unsigned __int8 *v1; // rdx
  unsigned int v3; // r9d
  unsigned __int64 v4; // r8
  unsigned __int8 *v5; // r10
  bool v6; // zf
  unsigned int v7; // ecx

  v1 = (unsigned __int8 *)*((_QWORD *)this + 8);
  if ( !v1 )
    return 0;
  v3 = 0;
  v4 = (unsigned __int64)&v1[*((unsigned __int16 *)v1 + 1)];
  if ( (unsigned __int64)(v1 + 2) < v4 )
  {
    do
    {
      if ( *v1 < 2u )
        break;
      v5 = &v1[*v1];
      if ( (unsigned __int64)v5 >= v4 )
        break;
      v6 = v1[1] == 11;
      v7 = v3 + 1;
      v1 += *v1;
      if ( !v6 )
        v7 = v3;
      v3 = v7;
    }
    while ( (unsigned __int64)(v5 + 2) < v4 );
  }
  return v3;
}

```

## disassembly

```asm
0x1800094c8  mov     rdx, [rcx+40h]
0x1800094cc  test    rdx, rdx
0x1800094cf  jnz     short loc_1800094D4
0x1800094d1  xor     eax, eax
0x1800094d3  retn
0x1800094d4  lea     rax, [rdx+2]
0x1800094d8  xor     r9d, r9d
0x1800094db  movzx   r8d, word ptr [rax]
0x1800094df  add     r8, rdx
0x1800094e2  cmp     rax, r8
0x1800094e5  jnb     short loc_180009513
0x1800094e7  cmp     byte ptr [rdx], 2
0x1800094ea  jb      short loc_180009513
0x1800094ec  movzx   r10d, byte ptr [rdx]
0x1800094f0  add     r10, rdx
0x1800094f3  cmp     r10, r8
0x1800094f6  jnb     short loc_180009513
0x1800094f8  cmp     byte ptr [rdx+1], 0Bh
0x1800094fc  lea     ecx, [r9+1]
0x180009500  mov     rdx, r10
0x180009503  cmovnz  ecx, r9d
0x180009507  mov     r9d, ecx
0x18000950a  lea     rcx, [r10+2]
0x18000950e  cmp     rcx, r8
0x180009511  jb      short loc_1800094E7
0x180009513  mov     eax, r9d
0x180009516  retn
```
