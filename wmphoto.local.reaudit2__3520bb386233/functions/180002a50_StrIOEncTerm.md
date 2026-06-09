# StrIOEncTerm

- ea: `0x180002a50`
- end: `0x180002feb`
- name: `StrIOEncTerm`
- size: `1435`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000271c`

## callees

- `0x180002a50`
- `0x180002ff4`
- `0x180003050`
- `0x180003170`
- `0x180003830`
- `0x1800371e0`
- `0x180045010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180002cd7`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180002cd7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002c25`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002c91`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002f72`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002f9b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002fbf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002fd3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002c25`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002c91`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002f72`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002f9b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002fbf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002fd3`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180002cea`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180002cea`

## pseudocode

```c
__int64 __fastcall StrIOEncTerm(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // r15
  unsigned __int64 v6; // rdi
  __int64 v7; // r12
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rdi
  __int64 v11; // r14
  unsigned __int64 v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void **v26; // rsi
  __int64 v27; // rax
  FILE **v28; // rcx
  FILE *v29; // rcx
  void *v30; // rcx
  unsigned __int64 v31; // rsi
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rbp
  unsigned int v34; // esi
  unsigned int v35; // esi
  const char *v36; // rcx
  unsigned int v37; // esi
  unsigned int v38; // eax
  unsigned int v39; // ebp
  unsigned int v40; // eax
  unsigned int v41; // ebp
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  void *v45; // rcx

  v1 = *(_QWORD *)(a1 + 34368);
  if ( !v1 || !*(_QWORD *)(v1 + 24) || !*(_QWORD *)(v1 + 32) )
    return 0xFFFFFFFFLL;
  putBit16z(*(_QWORD *)(a1 + 34368), 0, -*(_DWORD *)(v1 + 8) & 7);
  if ( *(_DWORD *)(a1 + 136) )
  {
    printf("\n%d horizontal tiles:\n", *(_DWORD *)(a1 + 16604) + 1);
    v34 = 0;
    do
    {
      printf("    offset of tile %d in MBs: %d\n", v34, *(_DWORD *)(a1 + 4LL * v34 + 16608));
      ++v34;
    }
    while ( v34 <= *(_DWORD *)(a1 + 16604) );
    printf("\n%d vertical tiles:\n", *(_DWORD *)(a1 + 216) + 1);
    v35 = 0;
    do
    {
      printf("    offset of tile %d in MBs: %d\n", v35, *(_DWORD *)(a1 + 4LL * v35 + 220));
      ++v35;
    }
    while ( v35 <= *(_DWORD *)(a1 + 216) );
    v36 = "\nSpatial order bitstream\n";
    if ( *(_DWORD *)(a1 + 168) )
      v36 = "\nFrequency order bitstream\n";
    printf(v36);
    if ( *(_DWORD *)(a1 + 34228) )
    {
      v37 = 0;
      if ( *(_DWORD *)(a1 + 168) )
      {
        do
        {
          v40 = *(_DWORD *)(a1 + 216);
          v41 = 0;
          do
          {
            v42 = 4 * (v41 + v37 * (v40 + 1));
            printf(
              "bitstream size of (DC, LP, AC, FL) for tile (%d, %d): %d %d %d %d.\n",
              v37,
              v41,
              *(_DWORD *)(*(_QWORD *)(a1 + 34376) + 8 * v42),
              *(_DWORD *)(*(_QWORD *)(a1 + 34376) + 8 * v42 + 8),
              *(_DWORD *)(*(_QWORD *)(a1 + 34376) + 8 * v42 + 16),
              *(_DWORD *)(*(_QWORD *)(a1 + 34376) + 8 * v42 + 24));
            v40 = *(_DWORD *)(a1 + 216);
            ++v41;
          }
          while ( v41 <= v40 );
          ++v37;
        }
        while ( v37 <= *(_DWORD *)(a1 + 16604) );
      }
      else
      {
        do
        {
          v38 = *(_DWORD *)(a1 + 216);
          v39 = 0;
          do
          {
            printf(
              "bitstream size for tile (%d, %d): %d.\n",
              v37,
              v39,
              *(_DWORD *)(*(_QWORD *)(a1 + 34376) + 8LL * (v39 + v37 * (v38 + 1))));
            v38 = *(_DWORD *)(a1 + 216);
            ++v39;
          }
          while ( v39 <= v38 );
          ++v37;
        }
        while ( v37 <= *(_DWORD *)(a1 + 16604) );
      }
    }
    else
    {
      printf("\nstreaming mode, no index table.\n");
    }
  }
  writeIndexTable(a1);
  detachISWrite(v3, v1);
  if ( *(_QWORD *)(a1 + 34480) )
  {
    v5 = *(_QWORD *)(a1 + 200);
    v6 = 0;
    v7 = *(_QWORD *)(a1 + 34376);
    do
    {
      detachISWrite(v4, *(_QWORD *)(*(_QWORD *)(a1 + 34472) + 8 * v6));
      v8 = *(_QWORD *)(a1 + 34480);
      ++v6;
    }
    while ( v6 < v8 );
    v9 = 0;
    if ( v8 )
    {
      do
      {
        v43 = *(_QWORD *)(*(_QWORD *)(a1 + 35656) + 8 * v9);
        (*(void (__fastcall **)(__int64, _QWORD))(v43 + 88))(v43, 0);
        ++v9;
      }
      while ( v9 < *(_QWORD *)(a1 + 34480) );
    }
    v10 = 0;
    if ( !*(_DWORD *)(a1 + 164) )
    {
      v11 = 0;
      while ( 1 )
      {
        v12 = 0;
        do
        {
          v13 = v5;
          v14 = *(_QWORD *)(v7 + 8 * v10);
          v15 = *(_QWORD *)(a1 + 35656);
          if ( !*(_DWORD *)(a1 + 168) )
          {
            v44 = *(_QWORD *)(v15 + 8 * v12);
LABEL_73:
            copyTo(v44, v13, v14);
            ++v10;
            goto LABEL_18;
          }
          copyTo(*(_QWORD *)(v15 + 8 * v12 * *(unsigned __int8 *)(a1 + 34352)), v5, v14);
          v16 = *(unsigned __int8 *)(a1 + 34352);
          if ( (unsigned __int8)v16 <= 1u )
          {
            ++v10;
          }
          else
          {
            copyTo(*(_QWORD *)(*(_QWORD *)(a1 + 35656) + 8 * v12 * v16 + 8), v5, *(_QWORD *)(v7 + 8 * v10 + 8));
            v10 += 2LL;
          }
          v17 = *(unsigned __int8 *)(a1 + 34352);
          if ( (unsigned __int8)v17 > 2u )
            copyTo(*(_QWORD *)(*(_QWORD *)(a1 + 35656) + 8 * v12 * v17 + 16), v5, *(_QWORD *)(v7 + 8 * v10++));
          v18 = *(unsigned __int8 *)(a1 + 34352);
          if ( (unsigned __int8)v18 > 3u )
          {
            v13 = v5;
            v14 = *(_QWORD *)(v7 + 8 * v10);
            v44 = *(_QWORD *)(*(_QWORD *)(a1 + 35656) + 8 * v12 * v18 + 24);
            goto LABEL_73;
          }
LABEL_18:
          ++v12;
        }
        while ( v12 <= *(unsigned int *)(a1 + 216) );
        if ( ++v11 > (unsigned __int64)*(unsigned int *)(a1 + 16604) )
          goto LABEL_20;
      }
    }
    if ( *(_BYTE *)(a1 + 34352) )
    {
      do
      {
        v31 = 0;
        do
        {
          LODWORD(v32) = *(_DWORD *)(a1 + 216);
          v33 = 0;
          do
          {
            copyTo(
              *(_QWORD *)(8 * v10 + 8 * v33 * *(unsigned __int8 *)(a1 + 34352) + *(_QWORD *)(a1 + 35656)),
              v5,
              *(_QWORD *)(8 * v10 + v7 + 8 * *(unsigned __int8 *)(a1 + 34352) * (v33 + v31 * (unsigned int)(v32 + 1))));
            v32 = *(unsigned int *)(a1 + 216);
            ++v33;
          }
          while ( v33 <= v32 );
          ++v31;
        }
        while ( v31 <= *(unsigned int *)(a1 + 16604) );
        ++v10;
      }
      while ( v10 < *(unsigned __int8 *)(a1 + 34352) );
    }
LABEL_20:
    v19 = 0;
    if ( *(_QWORD *)(a1 + 176) * *(_QWORD *)(a1 + 34544) * *(_QWORD *)(a1 + 34552) >= 0x4000000u )
    {
      v26 = (void **)(a1 + 35936);
      while ( v19 < *(_QWORD *)(a1 + 34480) )
      {
        v27 = *(_QWORD *)(a1 + 35656);
        if ( v27 )
        {
          v28 = *(FILE ***)(v27 + 8 * v19);
          if ( v28 )
          {
            v29 = *v28;
            if ( v29 )
            {
              fclose(v29);
              if ( !DeleteFileA(*((LPCSTR *)*v26 + v19)) )
                return 0xFFFFFFFFLL;
            }
            v30 = *(void **)(*(_QWORD *)(a1 + 35656) + 8 * v19);
            if ( v30 )
            {
              free(v30);
              *(_QWORD *)(*(_QWORD *)(a1 + 35656) + 8 * v19) = 0;
            }
          }
        }
        if ( *v26 )
        {
          v45 = (void *)*((_QWORD *)*v26 + v19);
          if ( v45 )
          {
            free(v45);
            *((_QWORD *)*v26 + v19) = 0;
          }
        }
        ++v19;
      }
      if ( *v26 )
      {
        free(*v26);
        *v26 = 0;
      }
    }
    else if ( *(_QWORD *)(a1 + 34480) )
    {
      do
      {
        v20 = *(_QWORD *)(a1 + 35656);
        if ( v20 )
        {
          v21 = *(_QWORD *)(v20 + 8 * v19);
          if ( v21 )
            (*(void (**)(void))(v21 + 48))();
        }
        ++v19;
      }
      while ( v19 < *(_QWORD *)(a1 + 34480) );
    }
    v22 = *(void **)(a1 + 35656);
    if ( v22 )
    {
      free(v22);
      *(_QWORD *)(a1 + 35656) = 0;
    }
    v23 = *(void **)(a1 + 34472);
    if ( v23 )
    {
      free(v23);
      *(_QWORD *)(a1 + 34472) = 0;
    }
    v24 = *(void **)(a1 + 34376);
    if ( v24 )
    {
      free(v24);
      *(_QWORD *)(a1 + 34376) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002a50  push    rbx
0x180002a52  push    rbp
0x180002a53  push    rsi
0x180002a54  push    rdi
0x180002a55  push    r12
0x180002a57  push    r13
0x180002a59  push    r14
0x180002a5b  push    r15
0x180002a5d  sub     rsp, 48h
0x180002a61  mov     rdi, [rcx+8640h]
0x180002a68  xor     r13d, r13d
0x180002a6b  mov     rbx, rcx
0x180002a6e  test    rdi, rdi
0x180002a71  jz      loc_180002C68
0x180002a77  cmp     [rdi+18h], r13
0x180002a7b  jz      loc_180002C68
0x180002a81  cmp     [rdi+20h], r13
0x180002a85  jz      loc_180002C68
0x180002a8b  mov     r8d, [rdi+8]
0x180002a8f  xor     edx, edx
0x180002a91  neg     r8d
0x180002a94  mov     rcx, rdi
0x180002a97  and     r8d, 7
0x180002a9b  call    putBit16z
0x180002aa0  cmp     [rbx+88h], r13d
0x180002aa7  jnz     loc_180002DB3
0x180002aad  mov     rcx, rbx
0x180002ab0  call    writeIndexTable
0x180002ab5  mov     rdx, rdi
0x180002ab8  call    detachISWrite
0x180002abd  cmp     [rbx+86B0h], r13
0x180002ac4  jbe     loc_180002C54
0x180002aca  mov     r15, [rbx+0C8h]
0x180002ad1  mov     rdi, r13
0x180002ad4  mov     r12, [rbx+8648h]
0x180002adb  mov     rdx, [rbx+86A8h]
0x180002ae2  mov     rdx, [rdx+rdi*8]
0x180002ae6  call    detachISWrite
0x180002aeb  mov     rax, [rbx+86B0h]
0x180002af2  inc     rdi
0x180002af5  cmp     rdi, rax
0x180002af8  jb      short loc_180002ADB
0x180002afa  mov     rdi, r13
0x180002afd  test    rax, rax
0x180002b00  jnz     loc_180002F19
0x180002b06  mov     rdi, r13
0x180002b09  cmp     [rbx+0A4h], r13d
0x180002b10  jnz     loc_180002D23
0x180002b16  mov     r14, r13
0x180002b19  mov     rsi, r13
0x180002b1c  mov     rdx, r15
0x180002b1f  mov     r8, [r12+rdi*8]
0x180002b23  mov     rax, [rbx+8B48h]
0x180002b2a  cmp     [rbx+0A8h], r13d
0x180002b31  jz      loc_180002F40
0x180002b37  movzx   ecx, byte ptr [rbx+8630h]
0x180002b3e  imul    rcx, rsi
0x180002b42  mov     rcx, [rax+rcx*8]
0x180002b46  call    copyTo
0x180002b4b  movzx   eax, byte ptr [rbx+8630h]
0x180002b52  cmp     al, 1
0x180002b54  jbe     loc_180002F46
0x180002b5a  mov     rcx, [rbx+8B48h]
0x180002b61  mov     rdx, r15
0x180002b64  mov     r8, [r12+rdi*8+8]
0x180002b69  imul    rax, rsi
0x180002b6d  mov     rcx, [rcx+rax*8+8]
0x180002b72  call    copyTo
0x180002b77  add     rdi, 2
0x180002b7b  movzx   eax, byte ptr [rbx+8630h]
0x180002b82  cmp     al, 2
0x180002b84  ja      loc_180002C6D
0x180002b8a  movzx   eax, byte ptr [rbx+8630h]
0x180002b91  cmp     al, 3
0x180002b93  ja      loc_180002F4E
0x180002b99  mov     eax, [rbx+0D8h]
0x180002b9f  inc     rsi
0x180002ba2  cmp     rsi, rax
0x180002ba5  jbe     loc_180002B1C
0x180002bab  mov     eax, [rbx+40DCh]
0x180002bb1  inc     r14
0x180002bb4  cmp     r14, rax
0x180002bb7  jbe     loc_180002B19
0x180002bbd  mov     rax, [rbx+86F8h]
0x180002bc4  mov     rdi, r13
0x180002bc7  imul    rax, [rbx+86F0h]
0x180002bcf  imul    rax, [rbx+0B0h]
0x180002bd7  cmp     rax, 4000000h
0x180002bdd  jnb     loc_180002CA6
0x180002be3  cmp     [rbx+86B0h], r13
0x180002bea  jbe     short loc_180002C19
0x180002bec  mov     rax, [rbx+8B48h]
0x180002bf3  test    rax, rax
0x180002bf6  jz      short loc_180002C0D
0x180002bf8  lea     rcx, [rax+rdi*8]
0x180002bfc  mov     rax, [rcx]
0x180002bff  test    rax, rax
0x180002c02  jz      short loc_180002C0D
0x180002c04  mov     rax, [rax+30h]
0x180002c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c0d  inc     rdi
0x180002c10  cmp     rdi, [rbx+86B0h]
0x180002c17  jb      short loc_180002BEC
0x180002c19  mov     rcx, [rbx+8B48h]; Block
0x180002c20  test    rcx, rcx
0x180002c23  jz      short loc_180002C38
0x180002c25  call    cs:__imp_free
0x180002c2c  nop     dword ptr [rax+rax+00h]
0x180002c31  mov     [rbx+8B48h], r13
0x180002c38  mov     rcx, [rbx+86A8h]; Block
0x180002c3f  test    rcx, rcx
0x180002c42  jnz     short loc_180002C91
0x180002c44  mov     rcx, [rbx+8648h]; Block
0x180002c4b  test    rcx, rcx
0x180002c4e  jnz     loc_180002FD3
0x180002c54  xor     eax, eax
0x180002c56  add     rsp, 48h
0x180002c5a  pop     r15
0x180002c5c  pop     r14
0x180002c5e  pop     r13
0x180002c60  pop     r12
0x180002c62  pop     rdi
0x180002c63  pop     rsi
0x180002c64  pop     rbp
0x180002c65  pop     rbx
0x180002c66  retn
0x180002c68  or      eax, 0FFFFFFFFh
0x180002c6b  jmp     short loc_180002C56
0x180002c6d  mov     rcx, [rbx+8B48h]
0x180002c74  mov     rdx, r15
0x180002c77  mov     r8, [r12+rdi*8]
0x180002c7b  imul    rax, rsi
0x180002c7f  mov     rcx, [rcx+rax*8+10h]
0x180002c84  call    copyTo
0x180002c89  inc     rdi
0x180002c8c  jmp     loc_180002B8A
0x180002c91  call    cs:__imp_free
0x180002c98  nop     dword ptr [rax+rax+00h]
0x180002c9d  mov     [rbx+86A8h], r13
0x180002ca4  jmp     short loc_180002C44
0x180002ca6  lea     rsi, [rbx+8C60h]
0x180002cad  cmp     rdi, [rbx+86B0h]
0x180002cb4  jnb     loc_180002FB3
0x180002cba  mov     rax, [rbx+8B48h]
0x180002cc1  test    rax, rax
0x180002cc4  jz      short loc_180002D12
0x180002cc6  mov     rcx, [rax+rdi*8]
0x180002cca  test    rcx, rcx
0x180002ccd  jz      short loc_180002D12
0x180002ccf  mov     rcx, [rcx]; Stream
0x180002cd2  test    rcx, rcx
0x180002cd5  jz      short loc_180002CFE
0x180002cd7  call    cs:__imp_fclose
0x180002cde  nop     dword ptr [rax+rax+00h]
0x180002ce3  mov     rcx, [rsi]
0x180002ce6  mov     rcx, [rcx+rdi*8]; lpFileName
0x180002cea  call    cs:__imp_DeleteFileA
0x180002cf1  nop     dword ptr [rax+rax+00h]
0x180002cf6  test    eax, eax
0x180002cf8  jz      loc_180002C68
0x180002cfe  mov     rax, [rbx+8B48h]
0x180002d05  mov     rcx, [rax+rdi*8]; Block
0x180002d09  test    rcx, rcx
0x180002d0c  jnz     loc_180002F72
0x180002d12  mov     rax, [rsi]
0x180002d15  test    rax, rax
0x180002d18  jnz     loc_180002F8E
0x180002d1e  inc     rdi
0x180002d21  jmp     short loc_180002CAD
0x180002d23  cmp     [rbx+8630h], r13b
0x180002d2a  jbe     loc_180002BBD
0x180002d30  lea     r14, ds:0[rdi*8]
0x180002d38  mov     rsi, r13
0x180002d3b  lea     r13, [r14+r12]
0x180002d3f  mov     eax, [rbx+0D8h]
0x180002d45  xor     ebp, ebp
0x180002d47  movzx   ecx, byte ptr [rbx+8630h]
0x180002d4e  lea     r8d, [rax+1]
0x180002d52  imul    r8, rsi
0x180002d56  mov     rdx, r15
0x180002d59  add     r8, rbp
0x180002d5c  imul    r8, rcx
0x180002d60  imul    rcx, rbp
0x180002d64  mov     r8, [r13+r8*8+0]
0x180002d69  lea     rax, [r14+rcx*8]
0x180002d6d  mov     rcx, [rbx+8B48h]
0x180002d74  mov     rcx, [rax+rcx]
0x180002d78  call    copyTo
0x180002d7d  mov     eax, [rbx+0D8h]
0x180002d83  inc     rbp
0x180002d86  cmp     rbp, rax
0x180002d89  jbe     short loc_180002D47
0x180002d8b  mov     eax, [rbx+40DCh]
0x180002d91  inc     rsi
0x180002d94  cmp     rsi, rax
0x180002d97  jbe     short loc_180002D3F
0x180002d99  movzx   eax, byte ptr [rbx+8630h]
0x180002da0  inc     rdi
0x180002da3  mov     r13d, 0
0x180002da9  cmp     rdi, rax
0x180002dac  jb      short loc_180002D30
0x180002dae  jmp     loc_180002BBD
0x180002db3  mov     edx, [rbx+40DCh]
0x180002db9  lea     rcx, aDHorizontalTil; "\n%d horizontal tiles:\n"
0x180002dc0  inc     edx
0x180002dc2  call    printf
0x180002dc7  mov     esi, r13d
0x180002dca  mov     r8d, esi
0x180002dcd  lea     rcx, aOffsetOfTileDI; "    offset of tile %d in MBs: %d\n"
0x180002dd4  mov     edx, esi
0x180002dd6  mov     r8d, [rbx+r8*4+40E0h]
0x180002dde  call    printf
0x180002de3  inc     esi
0x180002de5  cmp     esi, [rbx+40DCh]
0x180002deb  jbe     short loc_180002DCA
0x180002ded  mov     edx, [rbx+0D8h]
0x180002df3  lea     rcx, aDVerticalTiles; "\n%d vertical tiles:\n"
0x180002dfa  inc     edx
0x180002dfc  call    printf
0x180002e01  mov     esi, r13d
0x180002e04  mov     r8d, esi
0x180002e07  lea     rcx, aOffsetOfTileDI; "    offset of tile %d in MBs: %d\n"
0x180002e0e  mov     edx, esi
0x180002e10  mov     r8d, [rbx+r8*4+0DCh]
0x180002e18  call    printf
0x180002e1d  inc     esi
0x180002e1f  cmp     esi, [rbx+0D8h]
0x180002e25  jbe     short loc_180002E04
0x180002e27  cmp     [rbx+0A8h], r13d
0x180002e2e  lea     rax, aFrequencyOrder; "\nFrequency order bitstream\n"
0x180002e35  lea     rcx, aSpatialOrderBi; "\nSpatial order bitstream\n"
0x180002e3c  cmovnz  rcx, rax; Format
0x180002e40  call    printf
0x180002e45  cmp     [rbx+85B4h], r13d
0x180002e4c  jnz     short loc_180002E5F
0x180002e4e  lea     rcx, aStreamingModeN; "\nstreaming mode, no index table.\n"
0x180002e55  call    printf
0x180002e5a  jmp     loc_180002AAD
0x180002e5f  mov     esi, r13d
0x180002e62  cmp     [rbx+0A8h], r13d
0x180002e69  jnz     short loc_180002EB2
0x180002e6b  mov     eax, [rbx+0D8h]
0x180002e71  mov     ebp, r13d
0x180002e74  mov     r9, [rbx+8648h]
0x180002e7b  lea     rcx, aBitstreamSizeF; "bitstream size for tile (%d, %d): %d.\n"
0x180002e82  inc     eax
0x180002e84  mov     r8d, ebp
0x180002e87  imul    eax, esi
0x180002e8a  mov     edx, esi
0x180002e8c  add     eax, ebp
0x180002e8e  mov     r9d, [r9+rax*8]
0x180002e92  call    printf
0x180002e97  mov     eax, [rbx+0D8h]
0x180002e9d  inc     ebp
0x180002e9f  cmp     ebp, eax
0x180002ea1  jbe     short loc_180002E74
0x180002ea3  inc     esi
0x180002ea5  cmp     esi, [rbx+40DCh]
0x180002eab  jbe     short loc_180002E6B
0x180002ead  jmp     loc_180002AAD
0x180002eb2  mov     eax, [rbx+0D8h]
0x180002eb8  mov     ebp, r13d
0x180002ebb  mov     r9, [rbx+8648h]
0x180002ec2  inc     eax
0x180002ec4  imul    eax, esi
0x180002ec7  mov     r8d, ebp
0x180002eca  mov     edx, esi
0x180002ecc  add     eax, ebp
0x180002ece  shl     eax, 2
0x180002ed1  mov     ecx, eax
0x180002ed3  mov     eax, [r9+rax*8+18h]
0x180002ed8  mov     [rsp+88h+var_58], eax
0x180002edc  mov     eax, [r9+rcx*8+10h]
0x180002ee1  mov     [rsp+88h+var_60], eax
0x180002ee5  mov     eax, [r9+rcx*8+8]
0x180002eea  mov     r9d, [r9+rcx*8]
0x180002eee  lea     rcx, aBitstreamSizeO; "bitstream size of (DC, LP, AC, FL) for "...
0x180002ef5  mov     [rsp+88h+var_68], eax
0x180002ef9  call    printf
0x180002efe  mov     eax, [rbx+0D8h]
0x180002f04  inc     ebp
0x180002f06  cmp     ebp, eax
0x180002f08  jbe     short loc_180002EBB
0x180002f0a  inc     esi
0x180002f0c  cmp     esi, [rbx+40DCh]
0x180002f12  jbe     short loc_180002EB2
0x180002f14  jmp     loc_180002AAD
0x180002f19  mov     rax, [rbx+8B48h]
0x180002f20  xor     edx, edx
0x180002f22  mov     rcx, [rax+rdi*8]
0x180002f26  mov     rax, [rcx+58h]
0x180002f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f2f  inc     rdi
0x180002f32  cmp     rdi, [rbx+86B0h]
0x180002f39  jb      short loc_180002F19
0x180002f3b  jmp     loc_180002B06
0x180002f40  mov     rcx, [rax+rsi*8]
0x180002f44  jmp     short loc_180002F65
0x180002f46  inc     rdi
0x180002f49  jmp     loc_180002B7B
  ... truncated ...
```
