# StrIOEncTerm

- ea: `0x1800029b8`
- end: `0x180002f1e`
- name: `StrIOEncTerm`
- size: `1382`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800026a4`

## callees

- `0x1800029b8`
- `0x180002f24`
- `0x180002f80`
- `0x18000309c`
- `0x180003760`
- `0x180036c10`
- `0x180044010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180002c32`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180002c32`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002b8d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002bf2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002ebd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002ee0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002efe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002f0c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002b8d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002bf2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002ebd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002ee0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002efe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002f0c`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180002c3f`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180002c3f`

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
0x1800029b8  push    rbx
0x1800029ba  push    rbp
0x1800029bb  push    rsi
0x1800029bc  push    rdi
0x1800029bd  push    r12
0x1800029bf  push    r13
0x1800029c1  push    r14
0x1800029c3  push    r15
0x1800029c5  sub     rsp, 48h
0x1800029c9  mov     rdi, [rcx+8640h]
0x1800029d0  xor     r13d, r13d
0x1800029d3  mov     rbx, rcx
0x1800029d6  test    rdi, rdi
0x1800029d9  jz      loc_180002BC9
0x1800029df  cmp     [rdi+18h], r13
0x1800029e3  jz      loc_180002BC9
0x1800029e9  cmp     [rdi+20h], r13
0x1800029ed  jz      loc_180002BC9
0x1800029f3  mov     r8d, [rdi+8]
0x1800029f7  xor     edx, edx
0x1800029f9  neg     r8d
0x1800029fc  mov     rcx, rdi
0x1800029ff  and     r8d, 7
0x180002a03  call    putBit16z
0x180002a08  cmp     [rbx+88h], r13d
0x180002a0f  jnz     loc_180002CFE
0x180002a15  mov     rcx, rbx
0x180002a18  call    writeIndexTable
0x180002a1d  mov     rdx, rdi
0x180002a20  call    detachISWrite
0x180002a25  cmp     [rbx+86B0h], r13
0x180002a2c  jbe     loc_180002BB6
0x180002a32  mov     r15, [rbx+0C8h]
0x180002a39  mov     rdi, r13
0x180002a3c  mov     r12, [rbx+8648h]
0x180002a43  mov     rdx, [rbx+86A8h]
0x180002a4a  mov     rdx, [rdx+rdi*8]
0x180002a4e  call    detachISWrite
0x180002a53  mov     rax, [rbx+86B0h]
0x180002a5a  inc     rdi
0x180002a5d  cmp     rdi, rax
0x180002a60  jb      short loc_180002A43
0x180002a62  mov     rdi, r13
0x180002a65  test    rax, rax
0x180002a68  jnz     loc_180002E64
0x180002a6e  mov     rdi, r13
0x180002a71  cmp     [rbx+0A4h], r13d
0x180002a78  jnz     loc_180002C6E
0x180002a7e  mov     r14, r13
0x180002a81  mov     rsi, r13
0x180002a84  mov     rdx, r15
0x180002a87  mov     r8, [r12+rdi*8]
0x180002a8b  mov     rax, [rbx+8B48h]
0x180002a92  cmp     [rbx+0A8h], r13d
0x180002a99  jz      loc_180002E8B
0x180002a9f  movzx   ecx, byte ptr [rbx+8630h]
0x180002aa6  imul    rcx, rsi
0x180002aaa  mov     rcx, [rax+rcx*8]
0x180002aae  call    copyTo
0x180002ab3  movzx   eax, byte ptr [rbx+8630h]
0x180002aba  cmp     al, 1
0x180002abc  jbe     loc_180002E91
0x180002ac2  mov     rcx, [rbx+8B48h]
0x180002ac9  mov     rdx, r15
0x180002acc  mov     r8, [r12+rdi*8+8]
0x180002ad1  imul    rax, rsi
0x180002ad5  mov     rcx, [rcx+rax*8+8]
0x180002ada  call    copyTo
0x180002adf  add     rdi, 2
0x180002ae3  movzx   eax, byte ptr [rbx+8630h]
0x180002aea  cmp     al, 2
0x180002aec  ja      loc_180002BCE
0x180002af2  movzx   eax, byte ptr [rbx+8630h]
0x180002af9  cmp     al, 3
0x180002afb  ja      loc_180002E99
0x180002b01  mov     eax, [rbx+0D8h]
0x180002b07  inc     rsi
0x180002b0a  cmp     rsi, rax
0x180002b0d  jbe     loc_180002A84
0x180002b13  mov     eax, [rbx+40DCh]
0x180002b19  inc     r14
0x180002b1c  cmp     r14, rax
0x180002b1f  jbe     loc_180002A81
0x180002b25  mov     rax, [rbx+86F8h]
0x180002b2c  mov     rdi, r13
0x180002b2f  imul    rax, [rbx+86F0h]
0x180002b37  imul    rax, [rbx+0B0h]
0x180002b3f  cmp     rax, 4000000h
0x180002b45  jnb     loc_180002C01
0x180002b4b  cmp     [rbx+86B0h], r13
0x180002b52  jbe     short loc_180002B81
0x180002b54  mov     rax, [rbx+8B48h]
0x180002b5b  test    rax, rax
0x180002b5e  jz      short loc_180002B75
0x180002b60  lea     rcx, [rax+rdi*8]
0x180002b64  mov     rax, [rcx]
0x180002b67  test    rax, rax
0x180002b6a  jz      short loc_180002B75
0x180002b6c  mov     rax, [rax+30h]
0x180002b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b75  inc     rdi
0x180002b78  cmp     rdi, [rbx+86B0h]
0x180002b7f  jb      short loc_180002B54
0x180002b81  mov     rcx, [rbx+8B48h]; Block
0x180002b88  test    rcx, rcx
0x180002b8b  jz      short loc_180002B9A
0x180002b8d  call    cs:__imp_free
0x180002b93  mov     [rbx+8B48h], r13
0x180002b9a  mov     rcx, [rbx+86A8h]; Block
0x180002ba1  test    rcx, rcx
0x180002ba4  jnz     short loc_180002BF2
0x180002ba6  mov     rcx, [rbx+8648h]; Block
0x180002bad  test    rcx, rcx
0x180002bb0  jnz     loc_180002F0C
0x180002bb6  xor     eax, eax
0x180002bb8  add     rsp, 48h
0x180002bbc  pop     r15
0x180002bbe  pop     r14
0x180002bc0  pop     r13
0x180002bc2  pop     r12
0x180002bc4  pop     rdi
0x180002bc5  pop     rsi
0x180002bc6  pop     rbp
0x180002bc7  pop     rbx
0x180002bc8  retn
0x180002bc9  or      eax, 0FFFFFFFFh
0x180002bcc  jmp     short loc_180002BB8
0x180002bce  mov     rcx, [rbx+8B48h]
0x180002bd5  mov     rdx, r15
0x180002bd8  mov     r8, [r12+rdi*8]
0x180002bdc  imul    rax, rsi
0x180002be0  mov     rcx, [rcx+rax*8+10h]
0x180002be5  call    copyTo
0x180002bea  inc     rdi
0x180002bed  jmp     loc_180002AF2
0x180002bf2  call    cs:__imp_free
0x180002bf8  mov     [rbx+86A8h], r13
0x180002bff  jmp     short loc_180002BA6
0x180002c01  lea     rsi, [rbx+8C60h]
0x180002c08  cmp     rdi, [rbx+86B0h]
0x180002c0f  jnb     loc_180002EF2
0x180002c15  mov     rax, [rbx+8B48h]
0x180002c1c  test    rax, rax
0x180002c1f  jz      short loc_180002C5D
0x180002c21  mov     rcx, [rax+rdi*8]
0x180002c25  test    rcx, rcx
0x180002c28  jz      short loc_180002C5D
0x180002c2a  mov     rcx, [rcx]; Stream
0x180002c2d  test    rcx, rcx
0x180002c30  jz      short loc_180002C49
0x180002c32  call    cs:__imp_fclose
0x180002c38  mov     rcx, [rsi]
0x180002c3b  mov     rcx, [rcx+rdi*8]; lpFileName
0x180002c3f  call    cs:__imp_DeleteFileA
0x180002c45  test    eax, eax
0x180002c47  jz      short loc_180002BC9
0x180002c49  mov     rax, [rbx+8B48h]
0x180002c50  mov     rcx, [rax+rdi*8]; Block
0x180002c54  test    rcx, rcx
0x180002c57  jnz     loc_180002EBD
0x180002c5d  mov     rax, [rsi]
0x180002c60  test    rax, rax
0x180002c63  jnz     loc_180002ED3
0x180002c69  inc     rdi
0x180002c6c  jmp     short loc_180002C08
0x180002c6e  cmp     [rbx+8630h], r13b
0x180002c75  jbe     loc_180002B25
0x180002c7b  lea     r14, ds:0[rdi*8]
0x180002c83  mov     rsi, r13
0x180002c86  lea     r13, [r14+r12]
0x180002c8a  mov     eax, [rbx+0D8h]
0x180002c90  xor     ebp, ebp
0x180002c92  movzx   ecx, byte ptr [rbx+8630h]
0x180002c99  lea     r8d, [rax+1]
0x180002c9d  imul    r8, rsi
0x180002ca1  mov     rdx, r15
0x180002ca4  add     r8, rbp
0x180002ca7  imul    r8, rcx
0x180002cab  imul    rcx, rbp
0x180002caf  mov     r8, [r13+r8*8+0]
0x180002cb4  lea     rax, [r14+rcx*8]
0x180002cb8  mov     rcx, [rbx+8B48h]
0x180002cbf  mov     rcx, [rax+rcx]
0x180002cc3  call    copyTo
0x180002cc8  mov     eax, [rbx+0D8h]
0x180002cce  inc     rbp
0x180002cd1  cmp     rbp, rax
0x180002cd4  jbe     short loc_180002C92
0x180002cd6  mov     eax, [rbx+40DCh]
0x180002cdc  inc     rsi
0x180002cdf  cmp     rsi, rax
0x180002ce2  jbe     short loc_180002C8A
0x180002ce4  movzx   eax, byte ptr [rbx+8630h]
0x180002ceb  inc     rdi
0x180002cee  mov     r13d, 0
0x180002cf4  cmp     rdi, rax
0x180002cf7  jb      short loc_180002C7B
0x180002cf9  jmp     loc_180002B25
0x180002cfe  mov     edx, [rbx+40DCh]
0x180002d04  lea     rcx, aDHorizontalTil; "\n%d horizontal tiles:\n"
0x180002d0b  inc     edx
0x180002d0d  call    printf
0x180002d12  mov     esi, r13d
0x180002d15  mov     r8d, esi
0x180002d18  lea     rcx, aOffsetOfTileDI; "    offset of tile %d in MBs: %d\n"
0x180002d1f  mov     edx, esi
0x180002d21  mov     r8d, [rbx+r8*4+40E0h]
0x180002d29  call    printf
0x180002d2e  inc     esi
0x180002d30  cmp     esi, [rbx+40DCh]
0x180002d36  jbe     short loc_180002D15
0x180002d38  mov     edx, [rbx+0D8h]
0x180002d3e  lea     rcx, aDVerticalTiles; "\n%d vertical tiles:\n"
0x180002d45  inc     edx
0x180002d47  call    printf
0x180002d4c  mov     esi, r13d
0x180002d4f  mov     r8d, esi
0x180002d52  lea     rcx, aOffsetOfTileDI; "    offset of tile %d in MBs: %d\n"
0x180002d59  mov     edx, esi
0x180002d5b  mov     r8d, [rbx+r8*4+0DCh]
0x180002d63  call    printf
0x180002d68  inc     esi
0x180002d6a  cmp     esi, [rbx+0D8h]
0x180002d70  jbe     short loc_180002D4F
0x180002d72  cmp     [rbx+0A8h], r13d
0x180002d79  lea     rax, aFrequencyOrder; "\nFrequency order bitstream\n"
0x180002d80  lea     rcx, aSpatialOrderBi; "\nSpatial order bitstream\n"
0x180002d87  cmovnz  rcx, rax; Format
0x180002d8b  call    printf
0x180002d90  cmp     [rbx+85B4h], r13d
0x180002d97  jnz     short loc_180002DAA
0x180002d99  lea     rcx, aStreamingModeN; "\nstreaming mode, no index table.\n"
0x180002da0  call    printf
0x180002da5  jmp     loc_180002A15
0x180002daa  mov     esi, r13d
0x180002dad  cmp     [rbx+0A8h], r13d
0x180002db4  jnz     short loc_180002DFD
0x180002db6  mov     eax, [rbx+0D8h]
0x180002dbc  mov     ebp, r13d
0x180002dbf  mov     r9, [rbx+8648h]
0x180002dc6  lea     rcx, aBitstreamSizeF; "bitstream size for tile (%d, %d): %d.\n"
0x180002dcd  inc     eax
0x180002dcf  mov     r8d, ebp
0x180002dd2  imul    eax, esi
0x180002dd5  mov     edx, esi
0x180002dd7  add     eax, ebp
0x180002dd9  mov     r9d, [r9+rax*8]
0x180002ddd  call    printf
0x180002de2  mov     eax, [rbx+0D8h]
0x180002de8  inc     ebp
0x180002dea  cmp     ebp, eax
0x180002dec  jbe     short loc_180002DBF
0x180002dee  inc     esi
0x180002df0  cmp     esi, [rbx+40DCh]
0x180002df6  jbe     short loc_180002DB6
0x180002df8  jmp     loc_180002A15
0x180002dfd  mov     eax, [rbx+0D8h]
0x180002e03  mov     ebp, r13d
0x180002e06  mov     r9, [rbx+8648h]
0x180002e0d  inc     eax
0x180002e0f  imul    eax, esi
0x180002e12  mov     r8d, ebp
0x180002e15  mov     edx, esi
0x180002e17  add     eax, ebp
0x180002e19  shl     eax, 2
0x180002e1c  mov     ecx, eax
0x180002e1e  mov     eax, [r9+rax*8+18h]
0x180002e23  mov     [rsp+88h+var_58], eax
0x180002e27  mov     eax, [r9+rcx*8+10h]
0x180002e2c  mov     [rsp+88h+var_60], eax
0x180002e30  mov     eax, [r9+rcx*8+8]
0x180002e35  mov     r9d, [r9+rcx*8]
0x180002e39  lea     rcx, aBitstreamSizeO; "bitstream size of (DC, LP, AC, FL) for "...
0x180002e40  mov     [rsp+88h+var_68], eax
0x180002e44  call    printf
0x180002e49  mov     eax, [rbx+0D8h]
0x180002e4f  inc     ebp
0x180002e51  cmp     ebp, eax
0x180002e53  jbe     short loc_180002E06
0x180002e55  inc     esi
0x180002e57  cmp     esi, [rbx+40DCh]
0x180002e5d  jbe     short loc_180002DFD
0x180002e5f  jmp     loc_180002A15
0x180002e64  mov     rax, [rbx+8B48h]
0x180002e6b  xor     edx, edx
0x180002e6d  mov     rcx, [rax+rdi*8]
0x180002e71  mov     rax, [rcx+58h]
0x180002e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7a  inc     rdi
0x180002e7d  cmp     rdi, [rbx+86B0h]
0x180002e84  jb      short loc_180002E64
0x180002e86  jmp     loc_180002A6E
0x180002e8b  mov     rcx, [rax+rsi*8]
0x180002e8f  jmp     short loc_180002EB0
0x180002e91  inc     rdi
0x180002e94  jmp     loc_180002AE3
0x180002e99  mov     rcx, [rbx+8B48h]
0x180002ea0  mov     rdx, r15
0x180002ea3  mov     r8, [r12+rdi*8]
0x180002ea7  imul    rax, rsi
  ... truncated ...
```
