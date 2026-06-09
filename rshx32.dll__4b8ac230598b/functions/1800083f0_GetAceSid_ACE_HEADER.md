# GetAceSid(_ACE_HEADER *)

- ea: `0x1800083f0`
- end: `0x18000844a`
- name: `?GetAceSid@@YAPEAXPEAU_ACE_HEADER@@@Z`
- size: `90`
- prototype: `struct _ACE_HEADER *__fastcall(struct _ACE_HEADER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800085c0`

## callees

- `0x1800083f0`

## pseudocode

```c
struct _ACE_HEADER *__fastcall GetAceSid(struct _ACE_HEADER *a1)
{
  if ( !a1->AceType || a1->AceType == 1 || a1->AceType == 2 || a1->AceType == 3 )
    return a1 + 2;
  if ( a1->AceType == 4 )
    return a1 + 3;
  if ( a1->AceType == 5 || a1->AceType == 6 || (unsigned int)a1->AceType - 7 < 2 )
    return &a1[4 * (*(_DWORD *)&a1[2] & 1) + 3 + 2 * (*(_DWORD *)&a1[2] & 2)];
  return 0;
}

```

## disassembly

```asm
0x1800083f0  movzx   edx, byte ptr [rcx]
0x1800083f3  mov     r8, rcx
0x1800083f6  test    edx, edx
0x1800083f8  jz      short loc_180008445
0x1800083fa  sub     edx, 1
0x1800083fd  jz      short loc_180008445
0x1800083ff  sub     edx, 1
0x180008402  jz      short loc_180008445
0x180008404  sub     edx, 1
0x180008407  jz      short loc_180008445
0x180008409  sub     edx, 1
0x18000840c  jz      short loc_180008440
0x18000840e  sub     edx, 1
0x180008411  jz      short loc_180008425
0x180008413  sub     edx, 1
0x180008416  jz      short loc_180008425
0x180008418  sub     edx, 1
0x18000841b  jz      short loc_180008425
0x18000841d  cmp     edx, 1
0x180008420  jz      short loc_180008425
0x180008422  xor     eax, eax
0x180008424  retn
0x180008425  mov     ecx, [rcx+8]
0x180008428  mov     eax, ecx
0x18000842a  and     eax, 1
0x18000842d  and     ecx, 2
0x180008430  shl     rax, 4
0x180008434  add     rax, r8
0x180008437  lea     rax, [rax+rcx*8]
0x18000843b  add     rax, 0Ch
0x18000843f  retn
0x180008440  lea     rax, [rcx+0Ch]
0x180008444  retn
0x180008445  lea     rax, [rcx+8]
0x180008449  retn
```
