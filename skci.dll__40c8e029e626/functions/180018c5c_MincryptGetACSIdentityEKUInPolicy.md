# MincryptGetACSIdentityEKUInPolicy

- ea: `0x180018c5c`
- end: `0x180018d27`
- name: `MincryptGetACSIdentityEKUInPolicy`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020880`
- `0x180045be0`

## callees

- `0x180018c5c`

## pseudocode

```c
__int64 __fastcall MincryptGetACSIdentityEKUInPolicy(__int64 a1)
{
  __int64 v1; // r11
  unsigned int i; // edx
  __int64 v3; // r10
  __int64 v4; // r8
  unsigned __int8 v5; // r9
  char v6; // r9
  char *v7; // rbx
  unsigned int v8; // ecx
  unsigned __int64 v9; // r8
  char v10; // al
  char v11; // cl

  if ( *(_DWORD *)a1 )
  {
    v1 = *(_QWORD *)(a1 + 16);
    if ( v1 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 0xFFFF0000) == 0 )
      {
        for ( i = 0; i < *(_DWORD *)(v1 + 32); ++i )
        {
          v3 = *(_QWORD *)(v1 + 24) + 16LL * i;
          if ( *(_DWORD *)v3 >= 0xAu )
          {
            v4 = *(_QWORD *)(v3 + 8);
            if ( *(_BYTE *)v4 == 6 )
            {
              v5 = *(_BYTE *)(v4 + 1);
              if ( v5 >= 8u && *(_QWORD *)(v4 + 2) == 0x613782010401062BLL )
              {
                v6 = v5 - 8;
                v7 = (char *)(v4 + 10);
                v8 = 0;
                do
                {
                  if ( !v6 )
                    break;
                  v9 = (unsigned __int64)v8 << 7;
                  if ( v9 > 0xFFFFFFFF )
                    return *(_QWORD *)(v1 + 24) + 16LL * i;
                  v10 = *v7;
                  --v6;
                  v11 = *v7++;
                  v8 = v9 + (v11 & 0x7F);
                }
                while ( v10 < 0 );
                if ( v8 <= 0x3E7 )
                  continue;
                return *(_QWORD *)(v1 + 24) + 16LL * i;
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018c5c  mov     rax, rsp
0x180018c5f  mov     [rax+10h], rbx
0x180018c63  mov     [rax+18h], rdi
0x180018c67  cmp     dword ptr [rcx], 0
0x180018c6a  mov     dword ptr [rax+8], 401062Bh
0x180018c71  mov     dword ptr [rax+0Ch], 61378201h
0x180018c78  jz      loc_180018D19
0x180018c7e  mov     r11, [rcx+10h]
0x180018c82  test    r11, r11
0x180018c85  jz      loc_180018D19
0x180018c8b  test    dword ptr [rcx+8], 0FFFF0000h
0x180018c92  jnz     loc_180018D19
0x180018c98  mov     edi, [r11+20h]
0x180018c9c  xor     edx, edx
0x180018c9e  cmp     edx, edi
0x180018ca0  jnb     short loc_180018D19
0x180018ca2  mov     r10d, edx
0x180018ca5  shl     r10, 4
0x180018ca9  add     r10, [r11+18h]
0x180018cad  cmp     dword ptr [r10], 0Ah
0x180018cb1  jb      short loc_180018D10
0x180018cb3  mov     r8, [r10+8]
0x180018cb7  cmp     byte ptr [r8], 6
0x180018cbb  jnz     short loc_180018D10
0x180018cbd  mov     r9b, [r8+1]
0x180018cc1  cmp     r9b, 8
0x180018cc5  jb      short loc_180018D10
0x180018cc7  mov     rcx, [rsp+arg_0]
0x180018ccc  cmp     rcx, [r8+2]
0x180018cd0  jnz     short loc_180018D10
0x180018cd2  sub     r9b, 8
0x180018cd6  lea     rbx, [r8+0Ah]
0x180018cda  xor     ecx, ecx
0x180018cdc  test    r9b, r9b
0x180018cdf  jz      short loc_180018D08
0x180018ce1  mov     r8d, ecx
0x180018ce4  mov     eax, 0FFFFFFFFh
0x180018ce9  shl     r8, 7
0x180018ced  cmp     r8, rax
0x180018cf0  ja      short loc_180018D14
0x180018cf2  movzx   eax, byte ptr [rbx]
0x180018cf5  add     r9b, 0FFh
0x180018cf9  mov     ecx, eax
0x180018cfb  inc     rbx
0x180018cfe  and     ecx, 7Fh
0x180018d01  add     ecx, r8d
0x180018d04  test    al, al
0x180018d06  js      short loc_180018CDC
0x180018d08  cmp     ecx, 3E7h
0x180018d0e  ja      short loc_180018D14
0x180018d10  inc     edx
0x180018d12  jmp     short loc_180018C9E
0x180018d14  mov     rax, r10
0x180018d17  jmp     short loc_180018D1B
0x180018d19  xor     eax, eax
0x180018d1b  mov     rbx, [rsp+arg_8]
0x180018d20  mov     rdi, [rsp+arg_10]
0x180018d25  retn
```
