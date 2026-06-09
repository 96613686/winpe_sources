# encode_uncompressed_block

- ea: `0x14000449c`
- end: `0x14000455f`
- name: `encode_uncompressed_block`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005870`

## callees

- `0x14000449c`
- `0x140005d94`
- `0x14000709c`

## pseudocode

```c
__int64 __fastcall encode_uncompressed_block(__int64 a1, unsigned int a2, int a3)
{
  __int64 i; // rcx
  unsigned int v7; // edx
  unsigned int v8; // r8d
  __int64 result; // rax
  int v10; // edi
  __int64 v11; // rdx

  output_bits(a1, (unsigned int)(*(char *)(a1 + 44) - 16), 0);
  for ( i = 0; i != 3; ++i )
  {
    v7 = *(_DWORD *)(a1 + 4 * i + 88);
    v8 = 0;
    do
    {
      result = *(_QWORD *)(a1 + 2184);
      ++v8;
      *(_BYTE *)result = v7;
      ++*(_QWORD *)(a1 + 2184);
      v7 >>= 8;
    }
    while ( v8 < 4 );
  }
  v10 = a3 & 1;
  while ( a3 )
  {
    --a3;
    v11 = a2++;
    *(_BYTE *)(*(_QWORD *)(a1 + 2184))++ = *(_BYTE *)(v11 + *(_QWORD *)a1);
    result = (unsigned int)(*(_DWORD *)(a1 + 2200) + 1);
    *(_DWORD *)(a1 + 2200) = result;
    if ( (_DWORD)result == 0x8000 )
    {
      result = perform_flush_output_callback(a1);
      *(_BYTE *)(a1 + 2220) = 0;
    }
  }
  if ( v10 )
  {
    result = *(_QWORD *)(a1 + 2184);
    *(_BYTE *)result = 0;
    ++*(_QWORD *)(a1 + 2184);
  }
  *(_BYTE *)(a1 + 44) = 32;
  *(_DWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x14000449c  push    rbx
0x14000449e  push    rbp
0x14000449f  push    rsi
0x1400044a0  push    rdi
0x1400044a1  sub     rsp, 28h
0x1400044a5  mov     ebp, edx
0x1400044a7  mov     esi, r8d
0x1400044aa  movsx   edx, byte ptr [rcx+2Ch]
0x1400044ae  xor     r8d, r8d
0x1400044b1  sub     edx, 10h
0x1400044b4  mov     rbx, rcx
0x1400044b7  call    output_bits
0x1400044bc  xor     ecx, ecx
0x1400044be  mov     edx, [rbx+rcx*4+58h]
0x1400044c2  xor     r8d, r8d
0x1400044c5  mov     rax, [rbx+888h]
0x1400044cc  inc     r8d
0x1400044cf  mov     [rax], dl
0x1400044d1  inc     qword ptr [rbx+888h]
0x1400044d8  shr     edx, 8
0x1400044db  cmp     r8d, 4
0x1400044df  jb      short loc_1400044C5
0x1400044e1  inc     rcx
0x1400044e4  cmp     rcx, 3
0x1400044e8  jnz     short loc_1400044BE
0x1400044ea  mov     edi, esi
0x1400044ec  and     edi, 1
0x1400044ef  jmp     short loc_140004531
0x1400044f1  mov     rax, [rbx]
0x1400044f4  dec     esi
0x1400044f6  mov     rcx, [rbx+888h]
0x1400044fd  mov     edx, ebp
0x1400044ff  inc     ebp
0x140004501  mov     al, [rdx+rax]
0x140004504  mov     [rcx], al
0x140004506  inc     qword ptr [rbx+888h]
0x14000450d  mov     eax, [rbx+898h]
0x140004513  inc     eax
0x140004515  mov     [rbx+898h], eax
0x14000451b  cmp     eax, 8000h
0x140004520  jnz     short loc_140004531
0x140004522  mov     rcx, rbx
0x140004525  call    perform_flush_output_callback
0x14000452a  mov     byte ptr [rbx+8ACh], 0
0x140004531  test    esi, esi
0x140004533  jnz     short loc_1400044F1
0x140004535  test    edi, edi
0x140004537  jz      short loc_14000454A
0x140004539  mov     rax, [rbx+888h]
0x140004540  mov     [rax], sil
0x140004543  inc     qword ptr [rbx+888h]
0x14000454a  mov     byte ptr [rbx+2Ch], 20h ; ' '
0x14000454e  mov     dword ptr [rbx+28h], 0
0x140004555  add     rsp, 28h
0x140004559  pop     rdi
0x14000455a  pop     rsi
0x14000455b  pop     rbp
0x14000455c  pop     rbx
0x14000455d  retn
```
