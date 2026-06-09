# SymCryptFdefIntBitsizeOfValue

- ea: `0x180002a80`
- end: `0x180002b9e`
- name: `SymCryptFdefIntBitsizeOfValue`
- size: `286`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180023390`
- `0x180023e94`
- `0x180027604`
- `0x180027c78`
- `0x18002ac5c`
- `0x18004f740`

## callees

- `0x180002a80`

## pseudocode

```c
unsigned __int64 __fastcall SymCryptFdefIntBitsizeOfValue(__int64 a1)
{
  int v1; // edi
  int v2; // r10d
  __int64 v3; // rax
  int i; // r9d
  unsigned __int64 v5; // rbx
  unsigned int v6; // edx
  unsigned int v7; // r11d
  unsigned int v8; // ecx
  unsigned int v9; // r9d
  unsigned int v10; // edx
  unsigned int v11; // r10d
  unsigned int v12; // r8d

  v1 = 0;
  v2 = 0;
  LODWORD(v3) = *(_DWORD *)(a1 + 4) << 6 >> 2;
  for ( i = -1; (_DWORD)v3; i &= ~(i & ((unsigned __int64)-(__int64)*(unsigned int *)(a1 + 4 * v3 + 32) >> 32)) )
  {
    v3 = (unsigned int)(v3 - 1);
    v1 |= v3 & i & ((unsigned __int64)-(__int64)*(unsigned int *)(a1 + 4 * v3 + 32) >> 32);
    v2 |= *(_DWORD *)(a1 + 4 * v3 + 32) & i & ((unsigned __int64)-(__int64)*(unsigned int *)(a1 + 4 * v3 + 32) >> 32);
  }
  v5 = (unsigned __int64)-(__int64)(v2 & 0xFFFF0000) >> 32;
  v6 = (unsigned __int16)(v2 & ~(unsigned __int16)((unsigned __int64)-(__int64)(v2 & 0xFFFF0000) >> 32))
     | v5 & ((v2 & 0xFFFF0000) >> 16);
  v7 = -(v6 & 0xFF00) >> 16;
  v8 = v7 & (v6 >> 8) | v6 & (unsigned __int8)~(unsigned __int8)(-(v6 & 0xFF00) >> 16);
  v9 = -(v8 & 0xF0) >> 16;
  v10 = v8 & ~v9 | v9 & (v8 >> 4);
  v11 = -((v8 & (unsigned __int8)~(_BYTE)v9 | v9 & (unsigned __int8)(v8 >> 4)) & 0xC) >> 16;
  v12 = (unsigned __int8)v10 & (unsigned __int8)~(unsigned __int8)(-(v10 & 0xC) >> 16) & 3 | v11 & (v10 >> 2);
  return 32 * v1 + (v12 & 1 | ((v12 & 2) != 0)) + ((v12 >> 1) & 1 | v5 & 0x10 | v7 & 8 | v9 & 4 | v11 & 2);
}

```

## disassembly

```asm
0x180002a80  mov     [rsp+arg_0], rbx
0x180002a85  mov     [rsp+arg_8], rdi
0x180002a8a  mov     eax, [rcx+4]
0x180002a8d  xor     edi, edi
0x180002a8f  shl     eax, 6
0x180002a92  xor     r10d, r10d
0x180002a95  shr     eax, 2
0x180002a98  mov     r11, rcx
0x180002a9b  mov     r9d, 0FFFFFFFFh
0x180002aa1  test    eax, eax
0x180002aa3  jz      short loc_180002AD2
0x180002aa5  dec     eax
0x180002aa7  mov     edx, [r11+rax*4+20h]
0x180002aac  mov     r8d, edx
0x180002aaf  neg     r8
0x180002ab2  shr     r8, 20h
0x180002ab6  and     r8d, r9d
0x180002ab9  mov     ecx, r8d
0x180002abc  and     ecx, eax
0x180002abe  or      edi, ecx
0x180002ac0  mov     ecx, r8d
0x180002ac3  and     ecx, edx
0x180002ac5  not     r8d
0x180002ac8  or      r10d, ecx
0x180002acb  and     r9d, r8d
0x180002ace  test    eax, eax
0x180002ad0  jnz     short loc_180002AA5
0x180002ad2  mov     eax, r10d
0x180002ad5  shl     edi, 5
0x180002ad8  and     eax, 0FFFF0000h
0x180002add  mov     ebx, eax
0x180002adf  mov     edx, eax
0x180002ae1  neg     rbx
0x180002ae4  shr     edx, 10h
0x180002ae7  shr     rbx, 20h
0x180002aeb  and     edx, ebx
0x180002aed  mov     eax, ebx
0x180002aef  not     eax
0x180002af1  and     ebx, 10h
0x180002af4  and     eax, r10d
0x180002af7  movzx   eax, ax
0x180002afa  or      edx, eax
0x180002afc  mov     r11d, edx
0x180002aff  and     r11d, 0FF00h
0x180002b06  neg     r11d
0x180002b09  shr     r11d, 10h
0x180002b0d  mov     eax, r11d
0x180002b10  not     eax
0x180002b12  and     eax, edx
0x180002b14  shr     edx, 8
0x180002b17  movzx   ecx, al
0x180002b1a  and     edx, r11d
0x180002b1d  or      ecx, edx
0x180002b1f  and     r11d, 8
0x180002b23  mov     r9d, ecx
0x180002b26  mov     edx, ecx
0x180002b28  and     r9d, 0F0h
0x180002b2f  shr     edx, 4
0x180002b32  neg     r9d
0x180002b35  shr     r9d, 10h
0x180002b39  mov     eax, r9d
0x180002b3c  and     edx, r9d
0x180002b3f  not     eax
0x180002b41  and     r9d, 4
0x180002b45  and     eax, ecx
0x180002b47  or      edx, eax
0x180002b49  mov     r10d, edx
0x180002b4c  mov     r8d, edx
0x180002b4f  and     r10d, 0Ch
0x180002b53  shr     r8d, 2
0x180002b57  neg     r10d
0x180002b5a  shr     r10d, 10h
0x180002b5e  mov     eax, r10d
0x180002b61  and     r8d, r10d
0x180002b64  and     r10d, 2
0x180002b68  not     eax
0x180002b6a  or      r10d, r9d
0x180002b6d  and     eax, edx
0x180002b6f  and     eax, 3
0x180002b72  or      r10d, r11d
0x180002b75  or      r8d, eax
0x180002b78  or      r10d, ebx
0x180002b7b  mov     rbx, [rsp+arg_0]
0x180002b80  mov     ecx, r8d
0x180002b83  shr     ecx, 1
0x180002b85  and     ecx, 1
0x180002b88  or      r10d, ecx
0x180002b8b  or      ecx, r8d
0x180002b8e  and     ecx, 1
0x180002b91  lea     eax, [rcx+r10]
0x180002b95  add     eax, edi
0x180002b97  mov     rdi, [rsp+arg_8]
0x180002b9c  retn
```
