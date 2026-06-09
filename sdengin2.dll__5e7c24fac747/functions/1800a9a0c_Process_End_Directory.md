# Process_End_Directory

- ea: `0x1800a9a0c`
- end: `0x1800a9eec`
- name: `Process_End_Directory`
- size: `1248`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800a6ee0`
- `0x1800a7fa8`
- `0x1800ab35c`

## callees

- `0x1800a3608`
- `0x1800a6cb0`
- `0x1800a6dc4`
- `0x1800a7194`
- `0x1800a76a0`
- `0x1800a79d4`
- `0x1800a94dc`
- `0x1800a95e8`
- `0x1800a96dc`
- `0x1800a9748`
- `0x1800a9a0c`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800a9b9f`
- `KERNEL32!ReadFile` at `0x1800a9caa`
- `KERNEL32!ReadFile` at `0x1800a9d0f`
- `KERNEL32!ReadFile` at `0x1800a9b9f`
- `KERNEL32!ReadFile` at `0x1800a9caa`
- `KERNEL32!ReadFile` at `0x1800a9d0f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a9a2f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a9a2f`

## pseudocode

```c
__int64 Process_End_Directory()
{
  char *Value; // rax
  _DWORD *v1; // rbx
  __int16 v3; // bp
  __int64 End_Sig; // rax
  __int64 v5; // rcx
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int16 *v8; // r13
  int v9; // r10d
  __int16 v10; // si
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 End_Sig64; // rax
  _OWORD *v16; // r12
  __int64 v17; // rcx
  __int64 v18; // rax
  __int16 v19; // ax
  __int16 v20; // ax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __m128i v24; // xmm1
  unsigned int v25; // eax
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  Value = (char *)TlsGetValue(dwUnZIPTlsIndex);
  v1 = Value;
  if ( !Value )
    return 4;
  if ( *(_DWORD *)(Value + 5382) )
    return 0;
  v3 = -1;
  *(_QWORD *)(Value + 5602) = 0;
  *((_QWORD *)Value + 569) = -1;
  End_Sig = Find_End_Sig(0);
  if ( End_Sig == -3 )
  {
    *((_WORD *)v1 + 2693) = -1;
    v1[1355] = -1;
    *(_QWORD *)(v1 + 1359) = 0xFFFFFFFFLL;
    *(_DWORD *)((char *)v1 + 5382) = 1;
    *(_QWORD *)((char *)v1 + 5602) = 1;
    v1[1347] = 0;
    *((_WORD *)v1 + 2696) = -1;
    *(_QWORD *)((char *)v1 + 5394) = 0;
    *((_WORD *)v1 + 2701) = 0;
    v1[1356] = 0;
    *(_QWORD *)(v1 + 1357) = 0;
    *(_QWORD *)(v1 + 1361) = 0;
    *(_QWORD *)(v1 + 1363) = 0;
    return Process_Central_Directory(v5);
  }
  if ( End_Sig != -4 )
  {
    if ( End_Sig != -1 )
    {
LABEL_10:
      if ( End_Sig == -2 )
      {
        while ( 1 )
        {
          CloseCurrentZIP();
          if ( v1[8] || (unsigned int)MsgCB(*((_QWORD *)v1 + 618), 0, 1, 0, -1) != 1 )
            return 48;
          if ( !(unsigned int)CheckCurrentZIP() && OpenCurrentZIP() )
          {
            End_Sig = Find_End_Sig(1);
            goto LABEL_10;
          }
        }
      }
      if ( End_Sig != -1 )
      {
        v7 = *((_QWORD *)v1 + 571);
        *((_QWORD *)v1 + 569) = End_Sig;
        DZSetFilePointer(v7, End_Sig + 4, 0);
        v8 = (__int16 *)v1 + 2693;
        if ( ReadFile(*((HANDLE *)v1 + 571), (char *)v1 + 5386, 0x12u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
        {
          v9 = *((unsigned __int16 *)v1 + 2694);
          v10 = -1;
          v6 = 0;
          if ( (_WORD)v9 == 0xFFFF
            || (v11 = *(unsigned int *)((char *)v1 + 5398), (_DWORD)v11 == -1)
            || (v12 = *(unsigned int *)((char *)v1 + 5394), (_DWORD)v12 == -1)
            || (v13 = *((unsigned __int16 *)v1 + 2696), (_WORD)v13 == 0xFFFF)
            || (v14 = *((unsigned __int16 *)v1 + 2695), (_WORD)v14 == 0xFFFF) )
          {
            End_Sig64 = Find_End_Sig64();
            v16 = v1 + 1351;
            if ( End_Sig64 >= 0 )
            {
              v17 = *((_QWORD *)v1 + 571);
              *((_QWORD *)v1 + 569) = End_Sig64;
              DZSetFilePointer(v17, End_Sig64, 0);
              *v16 = 0;
              *(_OWORD *)(v1 + 1355) = 0;
              *(_OWORD *)(v1 + 1359) = 0;
              *(_QWORD *)(v1 + 1363) = 0;
              if ( ReadFile(*((HANDLE *)v1 + 571), v1 + 1351, 0xCu, &NumberOfBytesRead, 0) && NumberOfBytesRead == 12 )
              {
                if ( *(_DWORD *)v16 == 101075792
                  && (v18 = *((_QWORD *)v1 + 676), v18 > 0)
                  && (unsigned __int64)v18 <= 0x2C
                  && ReadFile(*((HANDLE *)v1 + 571), v1 + 1354, v18, &NumberOfBytesRead, 0)
                  && NumberOfBytesRead == v1[1352] )
                {
                  if ( v1[1355] < 0xFFFFu )
                    v3 = *((_WORD *)v1 + 2710);
                  *v8 = v3;
                  if ( v1[1356] >= 0xFFFFu )
                    v19 = -1;
                  else
                    v19 = *((_WORD *)v1 + 2712);
                  *((_WORD *)v1 + 2694) = v19;
                  if ( *(__int64 *)(v1 + 1357) >= 0xFFFF )
                    v20 = -1;
                  else
                    v20 = *((_WORD *)v1 + 2714);
                  *((_WORD *)v1 + 2695) = v20;
                  if ( *(__int64 *)(v1 + 1359) < 0xFFFF )
                    v10 = *((_WORD *)v1 + 2718);
                  *((_WORD *)v1 + 2696) = v10;
                  if ( *(__int64 *)(v1 + 1361) > 0xFFFFFFFFLL )
                    v21 = -1;
                  else
                    v21 = v1[1361];
                  *(_DWORD *)((char *)v1 + 5394) = v21;
                  if ( *(__int64 *)(v1 + 1363) >= 0xFFFFFFFFLL )
                    *(_DWORD *)((char *)v1 + 5398) = -1;
                  else
                    *(_DWORD *)((char *)v1 + 5398) = v1[1363];
                }
                else
                {
                  *((_QWORD *)v1 + 569) = -1;
                  v6 = 3;
                }
              }
              else
              {
                *((_QWORD *)v1 + 569) = -1;
                v6 = 3;
              }
              goto LABEL_54;
            }
            v22 = *v8;
            *(__m128i *)(v1 + 1357) = _mm_unpacklo_epi32(
                                        _mm_unpacklo_epi16(
                                          _mm_cvtsi32_si128(*(_DWORD *)((char *)v1 + 5390)),
                                          (__m128i)0LL),
                                        (__m128i)0LL);
            v1[1355] = v22;
            v23 = *((unsigned __int16 *)v1 + 2694);
            v24 = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)((char *)v1 + 5394)), (__m128i)0LL);
            *(_DWORD *)v16 = 101075792;
            *(__m128i *)(v1 + 1361) = v24;
            v1[1356] = v23;
          }
          else
          {
            v1[1355] = *v8;
            v1[1351] = 101075792;
            v1[1356] = v9;
            *(_QWORD *)(v1 + 1357) = v14;
            *(_QWORD *)(v1 + 1359) = v13;
            *(_QWORD *)(v1 + 1361) = v12;
            *(_QWORD *)(v1 + 1363) = v11;
          }
          v1[1354] = 1310740;
          *((_QWORD *)v1 + 676) = 44;
LABEL_54:
          *(_DWORD *)((char *)v1 + 5382) = 1;
          if ( v1[1355] )
          {
            *(_DWORD *)((char *)v1 + 5602) = 1;
            v25 = DriveFromPath((char *)v1 + 71270);
            if ( !(unsigned int)IsMediaRemovable(v25) )
              v1[8] = 1;
            *(_DWORD *)((char *)v1 + 5606) = v1[1355];
          }
          else
          {
            *(_DWORD *)((char *)v1 + 5602) = 0;
            if ( v1[1356] && *(_QWORD *)(v1 + 1357) == *(_QWORD *)(v1 + 1359) )
              *(_QWORD *)(v1 + 1355) = 0;
            *(_DWORD *)((char *)v1 + 5606) = 0;
          }
          return v6;
        }
        *((_QWORD *)v1 + 569) = -1;
      }
    }
    return 3;
  }
  return 5;
}

```

## disassembly

```asm
0x1800a9a0c  mov     rax, rsp
0x1800a9a0f  mov     [rax+8], ecx
0x1800a9a12  push    rbx
0x1800a9a13  push    rbp
0x1800a9a14  push    rsi
0x1800a9a15  push    rdi
0x1800a9a16  push    r12
0x1800a9a18  push    r13
0x1800a9a1a  push    r14
0x1800a9a1c  push    r15
0x1800a9a1e  sub     rsp, 38h
0x1800a9a22  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800a9a28  xor     r12d, r12d
0x1800a9a2b  mov     [rax+8], r12d
0x1800a9a2f  call    cs:__imp_TlsGetValue
0x1800a9a35  mov     rbx, rax
0x1800a9a38  test    rax, rax
0x1800a9a3b  jnz     short loc_1800A9A45
0x1800a9a3d  lea     eax, [rbx+4]
0x1800a9a40  jmp     loc_1800A9EDB
0x1800a9a45  cmp     [rax+1506h], r12d
0x1800a9a4c  jz      short loc_1800A9A55
0x1800a9a4e  xor     eax, eax
0x1800a9a50  jmp     loc_1800A9EDB
0x1800a9a55  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800a9a59  mov     [rax+15E2h], r12
0x1800a9a60  xor     ecx, ecx
0x1800a9a62  mov     [rax+11C8h], rbp
0x1800a9a69  call    Find_End_Sig
0x1800a9a6e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a9a72  jnz     short loc_1800A9AE6
0x1800a9a74  mov     r14d, 0FFFFFFFFh
0x1800a9a7a  mov     [rbx+150Ah], bp
0x1800a9a81  lea     r15d, [rbp+2]
0x1800a9a85  mov     [rbx+152Ch], r14d
0x1800a9a8c  mov     [rbx+153Ch], r14
0x1800a9a93  mov     [rbx+1506h], r15d
0x1800a9a9a  mov     [rbx+15E2h], r15
0x1800a9aa1  mov     [rbx+150Ch], r12d
0x1800a9aa8  mov     word ptr [rbx+1510h], 0FFFFh
0x1800a9ab1  mov     [rbx+1512h], r12
0x1800a9ab8  mov     [rbx+151Ah], r12w
0x1800a9ac0  mov     [rbx+1530h], r12d
0x1800a9ac7  mov     [rbx+1534h], r12
0x1800a9ace  mov     [rbx+1544h], r12
0x1800a9ad5  mov     [rbx+154Ch], r12
0x1800a9adc  call    Process_Central_Directory
0x1800a9ae1  jmp     loc_1800A9EDB
0x1800a9ae6  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x1800a9aea  jnz     short loc_1800A9AF4
0x1800a9aec  lea     edi, [rax+9]
0x1800a9aef  jmp     loc_1800A9ED9
0x1800a9af4  cmp     rax, rbp
0x1800a9af7  jz      loc_1800A9ED4
0x1800a9afd  mov     r15d, 1
0x1800a9b03  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800a9b07  jnz     short loc_1800A9B58
0x1800a9b09  call    CloseCurrentZIP
0x1800a9b0e  cmp     [rbx+20h], r12d
0x1800a9b12  jnz     short loc_1800A9B4E
0x1800a9b14  mov     rcx, [rbx+1350h]
0x1800a9b1b  xor     r9d, r9d
0x1800a9b1e  mov     r8d, r15d
0x1800a9b21  mov     dword ptr [rsp+78h+lpOverlapped], ebp
0x1800a9b25  xor     edx, edx
0x1800a9b27  call    MsgCB
0x1800a9b2c  cmp     eax, r15d
0x1800a9b2f  jnz     short loc_1800A9B4E
0x1800a9b31  call    CheckCurrentZIP
0x1800a9b36  test    eax, eax
0x1800a9b38  jnz     short loc_1800A9B09
0x1800a9b3a  call    OpenCurrentZIP
0x1800a9b3f  test    rax, rax
0x1800a9b42  jz      short loc_1800A9B09
0x1800a9b44  mov     ecx, r15d
0x1800a9b47  call    Find_End_Sig
0x1800a9b4c  jmp     short loc_1800A9B03
0x1800a9b4e  mov     edi, 30h ; '0'
0x1800a9b53  jmp     loc_1800A9ED9
0x1800a9b58  cmp     rax, rbp
0x1800a9b5b  jz      loc_1800A9ED4
0x1800a9b61  mov     rcx, [rbx+11D8h]
0x1800a9b68  lea     rdx, [rax+4]
0x1800a9b6c  xor     r8d, r8d
0x1800a9b6f  mov     [rbx+11C8h], rax
0x1800a9b76  call    DZSetFilePointer
0x1800a9b7b  mov     rcx, [rbx+11D8h]; hFile
0x1800a9b82  lea     r13, [rbx+150Ah]
0x1800a9b89  mov     rdx, r13; lpBuffer
0x1800a9b8c  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x1800a9b91  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a9b99  mov     r8d, 12h; nNumberOfBytesToRead
0x1800a9b9f  call    cs:__imp_ReadFile
0x1800a9ba5  test    eax, eax
0x1800a9ba7  jz      loc_1800A9ECD
0x1800a9bad  cmp     [rsp+78h+NumberOfBytesRead], r12d
0x1800a9bb5  jz      loc_1800A9ECD
0x1800a9bbb  movzx   r10d, word ptr [rbx+150Ch]
0x1800a9bc3  mov     esi, 0FFFFh
0x1800a9bc8  mov     edi, r12d
0x1800a9bcb  mov     r14d, 0FFFFFFFFh
0x1800a9bd1  cmp     r10w, si
0x1800a9bd5  jz      short loc_1800A9C46
0x1800a9bd7  mov     edx, [rbx+1516h]
0x1800a9bdd  cmp     edx, r14d
0x1800a9be0  jz      short loc_1800A9C46
0x1800a9be2  mov     ecx, [rbx+1512h]
0x1800a9be8  cmp     ecx, r14d
0x1800a9beb  jz      short loc_1800A9C46
0x1800a9bed  movzx   r9d, word ptr [rbx+1510h]
0x1800a9bf5  cmp     r9w, si
0x1800a9bf9  jz      short loc_1800A9C46
0x1800a9bfb  movzx   r8d, word ptr [rbx+150Eh]
0x1800a9c03  cmp     r8w, si
0x1800a9c07  jz      short loc_1800A9C46
0x1800a9c09  movsx   eax, word ptr [r13+0]
0x1800a9c0e  mov     [rbx+152Ch], eax
0x1800a9c14  mov     dword ptr [rbx+151Ch], 6064B50h
0x1800a9c1e  mov     [rbx+1530h], r10d
0x1800a9c25  mov     [rbx+1534h], r8
0x1800a9c2c  mov     [rbx+153Ch], r9
0x1800a9c33  mov     [rbx+1544h], rcx
0x1800a9c3a  mov     [rbx+154Ch], rdx
0x1800a9c41  jmp     loc_1800A9E44
0x1800a9c46  call    Find_End_Sig64
0x1800a9c4b  lea     r12, [rbx+151Ch]
0x1800a9c52  test    rax, rax
0x1800a9c55  js      loc_1800A9DF2
0x1800a9c5b  mov     rcx, [rbx+11D8h]
0x1800a9c62  xor     r8d, r8d
0x1800a9c65  mov     rdx, rax
0x1800a9c68  mov     [rbx+11C8h], rax
0x1800a9c6f  call    DZSetFilePointer
0x1800a9c74  xorps   xmm0, xmm0
0x1800a9c77  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a9c7f  movups  xmmword ptr [r12], xmm0
0x1800a9c84  xor     eax, eax
0x1800a9c86  mov     rdx, r12; lpBuffer
0x1800a9c89  movups  xmmword ptr [r12+10h], xmm0
0x1800a9c8f  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x1800a9c94  movups  xmmword ptr [r12+20h], xmm0
0x1800a9c9a  mov     [r12+30h], rax
0x1800a9c9f  lea     r8d, [rax+0Ch]; nNumberOfBytesToRead
0x1800a9ca3  mov     rcx, [rbx+11D8h]; hFile
0x1800a9caa  call    cs:__imp_ReadFile
0x1800a9cb0  test    eax, eax
0x1800a9cb2  jz      loc_1800A9DE1
0x1800a9cb8  cmp     [rsp+78h+NumberOfBytesRead], 0Ch
0x1800a9cc0  jnz     loc_1800A9DE1
0x1800a9cc6  cmp     dword ptr [r12], 6064B50h
0x1800a9cce  jnz     loc_1800A9DD0
0x1800a9cd4  mov     rax, [rbx+1520h]
0x1800a9cdb  xor     r12d, r12d
0x1800a9cde  test    rax, rax
0x1800a9ce1  jle     loc_1800A9DD3
0x1800a9ce7  cmp     rax, 2Ch ; ','
0x1800a9ceb  ja      loc_1800A9DD3
0x1800a9cf1  mov     rcx, [rbx+11D8h]; hFile
0x1800a9cf8  lea     rdx, [rbx+1528h]; lpBuffer
0x1800a9cff  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a9d07  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x1800a9d0c  mov     r8d, eax; nNumberOfBytesToRead
0x1800a9d0f  call    cs:__imp_ReadFile
0x1800a9d15  test    eax, eax
0x1800a9d17  jz      loc_1800A9DD3
0x1800a9d1d  mov     eax, [rbx+1520h]
0x1800a9d23  cmp     [rsp+78h+NumberOfBytesRead], eax
0x1800a9d2a  jnz     loc_1800A9DD3
0x1800a9d30  cmp     [rbx+152Ch], esi
0x1800a9d36  jnb     short loc_1800A9D3F
0x1800a9d38  movzx   ebp, word ptr [rbx+152Ch]
0x1800a9d3f  mov     [r13+0], bp
0x1800a9d44  cmp     [rbx+1530h], esi
0x1800a9d4a  jnb     short loc_1800A9D55
0x1800a9d4c  movzx   eax, word ptr [rbx+1530h]
0x1800a9d53  jmp     short loc_1800A9D57
0x1800a9d55  mov     eax, esi
0x1800a9d57  mov     [rbx+150Ch], ax
0x1800a9d5e  cmp     [rbx+1534h], rsi
0x1800a9d65  jge     short loc_1800A9D70
0x1800a9d67  movzx   eax, word ptr [rbx+1534h]
0x1800a9d6e  jmp     short loc_1800A9D72
0x1800a9d70  mov     eax, esi
0x1800a9d72  mov     [rbx+150Eh], ax
0x1800a9d79  cmp     [rbx+153Ch], rsi
0x1800a9d80  jge     short loc_1800A9D89
0x1800a9d82  movzx   esi, word ptr [rbx+153Ch]
0x1800a9d89  mov     [rbx+1510h], si
0x1800a9d90  cmp     [rbx+1544h], r14
0x1800a9d97  jg      short loc_1800A9DA1
0x1800a9d99  mov     eax, [rbx+1544h]
0x1800a9d9f  jmp     short loc_1800A9DA4
0x1800a9da1  mov     eax, r14d
0x1800a9da4  mov     [rbx+1512h], eax
0x1800a9daa  cmp     [rbx+154Ch], r14
0x1800a9db1  jge     short loc_1800A9DC4
0x1800a9db3  mov     eax, [rbx+154Ch]
0x1800a9db9  mov     [rbx+1516h], eax
0x1800a9dbf  jmp     loc_1800A9E59
0x1800a9dc4  mov     [rbx+1516h], r14d
0x1800a9dcb  jmp     loc_1800A9E59
0x1800a9dd0  xor     r12d, r12d
0x1800a9dd3  mov     [rbx+11C8h], rbp
0x1800a9dda  mov     edi, 3
0x1800a9ddf  jmp     short loc_1800A9E59
0x1800a9de1  mov     [rbx+11C8h], rbp
0x1800a9de8  mov     edi, 3
0x1800a9ded  xor     r12d, r12d
0x1800a9df0  jmp     short loc_1800A9E59
0x1800a9df2  movsx   eax, word ptr [r13+0]
0x1800a9df7  xorps   xmm0, xmm0
0x1800a9dfa  movd    xmm1, dword ptr [rbx+150Eh]
0x1800a9e02  punpcklwd xmm1, xmm0
0x1800a9e06  punpckldq xmm1, xmm0
0x1800a9e0a  movdqu  xmmword ptr [rbx+1534h], xmm1
0x1800a9e12  mov     [rbx+152Ch], eax
0x1800a9e18  movq    xmm1, qword ptr [rbx+1512h]
0x1800a9e20  movzx   eax, word ptr [rbx+150Ch]
0x1800a9e27  punpckldq xmm1, xmm0
0x1800a9e2b  mov     dword ptr [r12], 6064B50h
0x1800a9e33  xor     r12d, r12d
0x1800a9e36  movdqu  xmmword ptr [rbx+1544h], xmm1
0x1800a9e3e  mov     [rbx+1530h], eax
0x1800a9e44  mov     dword ptr [rbx+1528h], 140014h
0x1800a9e4e  mov     qword ptr [rbx+1520h], 2Ch ; ','
0x1800a9e59  mov     [rbx+1506h], r15d
0x1800a9e60  cmp     [rbx+152Ch], r12d
0x1800a9e67  jz      short loc_1800A9E99
0x1800a9e69  lea     rcx, [rbx+11666h]; Str1
0x1800a9e70  mov     [rbx+15E2h], r15d
0x1800a9e77  call    DriveFromPath
0x1800a9e7c  mov     ecx, eax
0x1800a9e7e  call    IsMediaRemovable
0x1800a9e83  test    eax, eax
0x1800a9e85  jnz     short loc_1800A9E8B
0x1800a9e87  mov     [rbx+20h], r15d
0x1800a9e8b  mov     eax, [rbx+152Ch]
0x1800a9e91  mov     [rbx+15E6h], eax
0x1800a9e97  jmp     short loc_1800A9ED9
0x1800a9e99  mov     [rbx+15E2h], r12d
0x1800a9ea0  cmp     [rbx+1530h], r12d
0x1800a9ea7  jz      short loc_1800A9EC4
0x1800a9ea9  mov     rax, [rbx+153Ch]
0x1800a9eb0  cmp     [rbx+1534h], rax
0x1800a9eb7  jnz     short loc_1800A9EC4
0x1800a9eb9  mov     qword ptr [rbx+152Ch], 0
0x1800a9ec4  mov     [rbx+15E6h], r12d
0x1800a9ecb  jmp     short loc_1800A9ED9
0x1800a9ecd  mov     [rbx+11C8h], rbp
0x1800a9ed4  mov     edi, 3
0x1800a9ed9  mov     eax, edi
0x1800a9edb  add     rsp, 38h
0x1800a9edf  pop     r15
0x1800a9ee1  pop     r14
0x1800a9ee3  pop     r13
0x1800a9ee5  pop     r12
0x1800a9ee7  pop     rdi
0x1800a9ee8  pop     rsi
0x1800a9ee9  pop     rbp
0x1800a9eea  pop     rbx
0x1800a9eeb  retn
```
