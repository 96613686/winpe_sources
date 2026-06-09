# Process_End_Directory

- ea: `0x1800aef84`
- end: `0x1800af47d`
- name: `Process_End_Directory`
- size: `1273`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800ac0ec`
- `0x1800ad3c0`
- `0x1800b09b8`

## callees

- `0x1800a8544`
- `0x1800abe84`
- `0x1800abfb8`
- `0x1800ac3cc`
- `0x1800ac9e8`
- `0x1800acd6c`
- `0x1800aea0c`
- `0x1800aeb3c`
- `0x1800aec40`
- `0x1800aecb8`
- `0x1800aef84`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800af11d`
- `KERNEL32!ReadFile` at `0x1800af22e`
- `KERNEL32!ReadFile` at `0x1800af299`
- `KERNEL32!ReadFile` at `0x1800af11d`
- `KERNEL32!ReadFile` at `0x1800af22e`
- `KERNEL32!ReadFile` at `0x1800af299`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800aefa7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800aefa7`

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
0x1800aef84  mov     rax, rsp
0x1800aef87  mov     [rax+8], ecx
0x1800aef8a  push    rbx
0x1800aef8b  push    rbp
0x1800aef8c  push    rsi
0x1800aef8d  push    rdi
0x1800aef8e  push    r12
0x1800aef90  push    r13
0x1800aef92  push    r14
0x1800aef94  push    r15
0x1800aef96  sub     rsp, 38h
0x1800aef9a  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800aefa0  xor     r12d, r12d
0x1800aefa3  mov     [rax+8], r12d
0x1800aefa7  call    cs:__imp_TlsGetValue
0x1800aefae  nop     dword ptr [rax+rax+00h]
0x1800aefb3  mov     rbx, rax
0x1800aefb6  test    rax, rax
0x1800aefb9  jnz     short loc_1800AEFC3
0x1800aefbb  lea     eax, [rbx+4]
0x1800aefbe  jmp     loc_1800AF46B
0x1800aefc3  cmp     [rax+1506h], r12d
0x1800aefca  jz      short loc_1800AEFD3
0x1800aefcc  xor     eax, eax
0x1800aefce  jmp     loc_1800AF46B
0x1800aefd3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800aefd7  mov     [rax+15E2h], r12
0x1800aefde  xor     ecx, ecx
0x1800aefe0  mov     [rax+11C8h], rbp
0x1800aefe7  call    Find_End_Sig
0x1800aefec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800aeff0  jnz     short loc_1800AF064
0x1800aeff2  mov     r14d, 0FFFFFFFFh
0x1800aeff8  mov     [rbx+150Ah], bp
0x1800aefff  lea     r15d, [rbp+2]
0x1800af003  mov     [rbx+152Ch], r14d
0x1800af00a  mov     [rbx+153Ch], r14
0x1800af011  mov     [rbx+1506h], r15d
0x1800af018  mov     [rbx+15E2h], r15
0x1800af01f  mov     [rbx+150Ch], r12d
0x1800af026  mov     word ptr [rbx+1510h], 0FFFFh
0x1800af02f  mov     [rbx+1512h], r12
0x1800af036  mov     [rbx+151Ah], r12w
0x1800af03e  mov     [rbx+1530h], r12d
0x1800af045  mov     [rbx+1534h], r12
0x1800af04c  mov     [rbx+1544h], r12
0x1800af053  mov     [rbx+154Ch], r12
0x1800af05a  call    Process_Central_Directory
0x1800af05f  jmp     loc_1800AF46B
0x1800af064  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x1800af068  jnz     short loc_1800AF072
0x1800af06a  lea     edi, [rax+9]
0x1800af06d  jmp     loc_1800AF469
0x1800af072  cmp     rax, rbp
0x1800af075  jz      loc_1800AF464
0x1800af07b  mov     r15d, 1
0x1800af081  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800af085  jnz     short loc_1800AF0D6
0x1800af087  call    CloseCurrentZIP
0x1800af08c  cmp     [rbx+20h], r12d
0x1800af090  jnz     short loc_1800AF0CC
0x1800af092  mov     rcx, [rbx+1350h]
0x1800af099  xor     r9d, r9d
0x1800af09c  mov     r8d, r15d
0x1800af09f  mov     dword ptr [rsp+78h+lpOverlapped], ebp
0x1800af0a3  xor     edx, edx
0x1800af0a5  call    MsgCB
0x1800af0aa  cmp     eax, r15d
0x1800af0ad  jnz     short loc_1800AF0CC
0x1800af0af  call    CheckCurrentZIP
0x1800af0b4  test    eax, eax
0x1800af0b6  jnz     short loc_1800AF087
0x1800af0b8  call    OpenCurrentZIP
0x1800af0bd  test    rax, rax
0x1800af0c0  jz      short loc_1800AF087
0x1800af0c2  mov     ecx, r15d
0x1800af0c5  call    Find_End_Sig
0x1800af0ca  jmp     short loc_1800AF081
0x1800af0cc  mov     edi, 30h ; '0'
0x1800af0d1  jmp     loc_1800AF469
0x1800af0d6  cmp     rax, rbp
0x1800af0d9  jz      loc_1800AF464
0x1800af0df  mov     rcx, [rbx+11D8h]
0x1800af0e6  lea     rdx, [rax+4]
0x1800af0ea  xor     r8d, r8d
0x1800af0ed  mov     [rbx+11C8h], rax
0x1800af0f4  call    DZSetFilePointer
0x1800af0f9  mov     rcx, [rbx+11D8h]; hFile
0x1800af100  lea     r13, [rbx+150Ah]
0x1800af107  mov     rdx, r13; lpBuffer
0x1800af10a  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x1800af10f  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800af117  mov     r8d, 12h; nNumberOfBytesToRead
0x1800af11d  call    cs:__imp_ReadFile
0x1800af124  nop     dword ptr [rax+rax+00h]
0x1800af129  test    eax, eax
0x1800af12b  jz      loc_1800AF45D
0x1800af131  cmp     [rsp+78h+NumberOfBytesRead], r12d
0x1800af139  jz      loc_1800AF45D
0x1800af13f  movzx   r10d, word ptr [rbx+150Ch]
0x1800af147  mov     esi, 0FFFFh
0x1800af14c  mov     edi, r12d
0x1800af14f  mov     r14d, 0FFFFFFFFh
0x1800af155  cmp     r10w, si
0x1800af159  jz      short loc_1800AF1CA
0x1800af15b  mov     edx, [rbx+1516h]
0x1800af161  cmp     edx, r14d
0x1800af164  jz      short loc_1800AF1CA
0x1800af166  mov     ecx, [rbx+1512h]
0x1800af16c  cmp     ecx, r14d
0x1800af16f  jz      short loc_1800AF1CA
0x1800af171  movzx   r9d, word ptr [rbx+1510h]
0x1800af179  cmp     r9w, si
0x1800af17d  jz      short loc_1800AF1CA
0x1800af17f  movzx   r8d, word ptr [rbx+150Eh]
0x1800af187  cmp     r8w, si
0x1800af18b  jz      short loc_1800AF1CA
0x1800af18d  movsx   eax, word ptr [r13+0]
0x1800af192  mov     [rbx+152Ch], eax
0x1800af198  mov     dword ptr [rbx+151Ch], 6064B50h
0x1800af1a2  mov     [rbx+1530h], r10d
0x1800af1a9  mov     [rbx+1534h], r8
0x1800af1b0  mov     [rbx+153Ch], r9
0x1800af1b7  mov     [rbx+1544h], rcx
0x1800af1be  mov     [rbx+154Ch], rdx
0x1800af1c5  jmp     loc_1800AF3D4
0x1800af1ca  call    Find_End_Sig64
0x1800af1cf  lea     r12, [rbx+151Ch]
0x1800af1d6  test    rax, rax
0x1800af1d9  js      loc_1800AF382
0x1800af1df  mov     rcx, [rbx+11D8h]
0x1800af1e6  xor     r8d, r8d
0x1800af1e9  mov     rdx, rax
0x1800af1ec  mov     [rbx+11C8h], rax
0x1800af1f3  call    DZSetFilePointer
0x1800af1f8  xorps   xmm0, xmm0
0x1800af1fb  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800af203  movups  xmmword ptr [r12], xmm0
0x1800af208  xor     eax, eax
0x1800af20a  mov     rdx, r12; lpBuffer
0x1800af20d  movups  xmmword ptr [r12+10h], xmm0
0x1800af213  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x1800af218  movups  xmmword ptr [r12+20h], xmm0
0x1800af21e  mov     [r12+30h], rax
0x1800af223  lea     r8d, [rax+0Ch]; nNumberOfBytesToRead
0x1800af227  mov     rcx, [rbx+11D8h]; hFile
0x1800af22e  call    cs:__imp_ReadFile
0x1800af235  nop     dword ptr [rax+rax+00h]
0x1800af23a  test    eax, eax
0x1800af23c  jz      loc_1800AF371
0x1800af242  cmp     [rsp+78h+NumberOfBytesRead], 0Ch
0x1800af24a  jnz     loc_1800AF371
0x1800af250  cmp     dword ptr [r12], 6064B50h
0x1800af258  jnz     loc_1800AF360
0x1800af25e  mov     rax, [rbx+1520h]
0x1800af265  xor     r12d, r12d
0x1800af268  test    rax, rax
0x1800af26b  jle     loc_1800AF363
0x1800af271  cmp     rax, 2Ch ; ','
0x1800af275  ja      loc_1800AF363
0x1800af27b  mov     rcx, [rbx+11D8h]; hFile
0x1800af282  lea     rdx, [rbx+1528h]; lpBuffer
0x1800af289  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800af291  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x1800af296  mov     r8d, eax; nNumberOfBytesToRead
0x1800af299  call    cs:__imp_ReadFile
0x1800af2a0  nop     dword ptr [rax+rax+00h]
0x1800af2a5  test    eax, eax
0x1800af2a7  jz      loc_1800AF363
0x1800af2ad  mov     eax, [rbx+1520h]
0x1800af2b3  cmp     [rsp+78h+NumberOfBytesRead], eax
0x1800af2ba  jnz     loc_1800AF363
0x1800af2c0  cmp     [rbx+152Ch], esi
0x1800af2c6  jnb     short loc_1800AF2CF
0x1800af2c8  movzx   ebp, word ptr [rbx+152Ch]
0x1800af2cf  mov     [r13+0], bp
0x1800af2d4  cmp     [rbx+1530h], esi
0x1800af2da  jnb     short loc_1800AF2E5
0x1800af2dc  movzx   eax, word ptr [rbx+1530h]
0x1800af2e3  jmp     short loc_1800AF2E7
0x1800af2e5  mov     eax, esi
0x1800af2e7  mov     [rbx+150Ch], ax
0x1800af2ee  cmp     [rbx+1534h], rsi
0x1800af2f5  jge     short loc_1800AF300
0x1800af2f7  movzx   eax, word ptr [rbx+1534h]
0x1800af2fe  jmp     short loc_1800AF302
0x1800af300  mov     eax, esi
0x1800af302  mov     [rbx+150Eh], ax
0x1800af309  cmp     [rbx+153Ch], rsi
0x1800af310  jge     short loc_1800AF319
0x1800af312  movzx   esi, word ptr [rbx+153Ch]
0x1800af319  mov     [rbx+1510h], si
0x1800af320  cmp     [rbx+1544h], r14
0x1800af327  jg      short loc_1800AF331
0x1800af329  mov     eax, [rbx+1544h]
0x1800af32f  jmp     short loc_1800AF334
0x1800af331  mov     eax, r14d
0x1800af334  mov     [rbx+1512h], eax
0x1800af33a  cmp     [rbx+154Ch], r14
0x1800af341  jge     short loc_1800AF354
0x1800af343  mov     eax, [rbx+154Ch]
0x1800af349  mov     [rbx+1516h], eax
0x1800af34f  jmp     loc_1800AF3E9
0x1800af354  mov     [rbx+1516h], r14d
0x1800af35b  jmp     loc_1800AF3E9
0x1800af360  xor     r12d, r12d
0x1800af363  mov     [rbx+11C8h], rbp
0x1800af36a  mov     edi, 3
0x1800af36f  jmp     short loc_1800AF3E9
0x1800af371  mov     [rbx+11C8h], rbp
0x1800af378  mov     edi, 3
0x1800af37d  xor     r12d, r12d
0x1800af380  jmp     short loc_1800AF3E9
0x1800af382  movsx   eax, word ptr [r13+0]
0x1800af387  xorps   xmm0, xmm0
0x1800af38a  movd    xmm1, dword ptr [rbx+150Eh]
0x1800af392  punpcklwd xmm1, xmm0
0x1800af396  punpckldq xmm1, xmm0
0x1800af39a  movdqu  xmmword ptr [rbx+1534h], xmm1
0x1800af3a2  mov     [rbx+152Ch], eax
0x1800af3a8  movq    xmm1, qword ptr [rbx+1512h]
0x1800af3b0  movzx   eax, word ptr [rbx+150Ch]
0x1800af3b7  punpckldq xmm1, xmm0
0x1800af3bb  mov     dword ptr [r12], 6064B50h
0x1800af3c3  xor     r12d, r12d
0x1800af3c6  movdqu  xmmword ptr [rbx+1544h], xmm1
0x1800af3ce  mov     [rbx+1530h], eax
0x1800af3d4  mov     dword ptr [rbx+1528h], 140014h
0x1800af3de  mov     qword ptr [rbx+1520h], 2Ch ; ','
0x1800af3e9  mov     [rbx+1506h], r15d
0x1800af3f0  cmp     [rbx+152Ch], r12d
0x1800af3f7  jz      short loc_1800AF429
0x1800af3f9  lea     rcx, [rbx+11666h]; Str1
0x1800af400  mov     [rbx+15E2h], r15d
0x1800af407  call    DriveFromPath
0x1800af40c  mov     ecx, eax
0x1800af40e  call    IsMediaRemovable
0x1800af413  test    eax, eax
0x1800af415  jnz     short loc_1800AF41B
0x1800af417  mov     [rbx+20h], r15d
0x1800af41b  mov     eax, [rbx+152Ch]
0x1800af421  mov     [rbx+15E6h], eax
0x1800af427  jmp     short loc_1800AF469
0x1800af429  mov     [rbx+15E2h], r12d
0x1800af430  cmp     [rbx+1530h], r12d
0x1800af437  jz      short loc_1800AF454
0x1800af439  mov     rax, [rbx+153Ch]
0x1800af440  cmp     [rbx+1534h], rax
0x1800af447  jnz     short loc_1800AF454
0x1800af449  mov     qword ptr [rbx+152Ch], 0
0x1800af454  mov     [rbx+15E6h], r12d
0x1800af45b  jmp     short loc_1800AF469
0x1800af45d  mov     [rbx+11C8h], rbp
0x1800af464  mov     edi, 3
0x1800af469  mov     eax, edi
0x1800af46b  add     rsp, 38h
0x1800af46f  pop     r15
0x1800af471  pop     r14
0x1800af473  pop     r13
0x1800af475  pop     r12
0x1800af477  pop     rdi
0x1800af478  pop     rsi
0x1800af479  pop     rbp
0x1800af47a  pop     rbx
0x1800af47b  retn
```
