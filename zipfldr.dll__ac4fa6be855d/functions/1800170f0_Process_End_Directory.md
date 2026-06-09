# Process_End_Directory

- ea: `0x1800170f0`
- end: `0x1800175f7`
- name: `Process_End_Directory`
- size: `1287`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180015dac`
- `0x180016d80`
- `0x18002f584`

## callees

- `0x180005080`
- `0x180005464`
- `0x1800153c4`
- `0x18001548c`
- `0x180015520`
- `0x1800170f0`
- `0x1800177f0`
- `0x180017ba0`
- `0x1800210f0`
- `0x18002115c`
- `0x18002b5e4`
- `0x180036f50`
- `0x18006aae8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001711e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001711e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800171dc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180017474`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800174cf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800171dc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180017474`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800174cf`

## pseudocode

```c
__int64 Process_End_Directory()
{
  char *Value; // rax
  _DWORD *v1; // rbx
  __int64 End_Sig; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int16 *v6; // r12
  unsigned int v7; // edi
  int v8; // r11d
  __int16 v9; // si
  __int64 End_Sig64; // rax
  _OWORD *v11; // r15
  int v12; // eax
  int v13; // eax
  int v14; // r10d
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int16 v24; // ax
  __int16 v25; // ax
  __int16 v26; // ax
  int v27; // eax
  unsigned int v28; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-58h] BYREF

  NumberOfBytesRead = 0;
  Value = (char *)TlsGetValue(dwUnZIPTlsIndex);
  v1 = Value;
  if ( !Value )
    return 4;
  if ( *((_DWORD *)Value + 1076) )
    return 0;
  *(_QWORD *)(Value + 4796) = 0;
  *((_QWORD *)Value + 403) = -1;
  End_Sig = Find_End_Sig(0);
  if ( End_Sig != -3 )
  {
    if ( End_Sig == -4 )
    {
      return 5;
    }
    else
    {
      if ( End_Sig != -1 )
      {
LABEL_8:
        if ( End_Sig == -2 )
        {
          while ( 1 )
          {
            CloseCurrentZIP();
            v19 = v1[3] ? duzMakeMVFromHDName(0, 0xFFFFFFFFLL, (__int64)v1) : MsgCB(*((_QWORD *)v1 + 476), 0, 1, 0, -1);
            if ( v19 != 1 )
              return 48;
            if ( !(unsigned int)CheckCurrentZIP() && OpenCurrentZIP(v21, v20) )
            {
              End_Sig = Find_End_Sig(1);
              goto LABEL_8;
            }
          }
        }
        if ( End_Sig != -1 )
        {
          v5 = *((_QWORD *)v1 + 405);
          *((_QWORD *)v1 + 403) = End_Sig;
          DZSetFilePointer(v5, End_Sig + 4, 0);
          v6 = (__int16 *)(v1 + 1077);
          if ( ReadFile(*((HANDLE *)v1 + 405), v1 + 1077, 0x12u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
          {
            v8 = (unsigned __int16)*v6;
            v9 = -1;
            v7 = 0;
            if ( (_WORD)v8 == 0xFFFF
              || (v14 = *((unsigned __int16 *)v1 + 2155), (_WORD)v14 == 0xFFFF)
              || (v15 = (unsigned int)v1[1080], (_DWORD)v15 == -1)
              || (v16 = (unsigned int)v1[1079], (_DWORD)v16 == -1)
              || (v17 = *((unsigned __int16 *)v1 + 2157), (_WORD)v17 == 0xFFFF)
              || (v18 = *((unsigned __int16 *)v1 + 2156), (_WORD)v18 == 0xFFFF) )
            {
              End_Sig64 = Find_End_Sig64();
              v11 = (_OWORD *)((char *)v1 + 4326);
              if ( End_Sig64 >= 0 )
              {
                v22 = *((_QWORD *)v1 + 405);
                *((_QWORD *)v1 + 403) = End_Sig64;
                DZSetFilePointer(v22, End_Sig64, 0);
                *v11 = 0;
                *(_OWORD *)((char *)v1 + 4342) = 0;
                *(_OWORD *)((char *)v1 + 4358) = 0;
                *(_QWORD *)((char *)v1 + 4374) = 0;
                if ( ReadFile(*((HANDLE *)v1 + 405), (char *)v1 + 4326, 0xCu, &NumberOfBytesRead, 0)
                  && NumberOfBytesRead == 12
                  && *(_DWORD *)v11 == 101075792
                  && (v23 = *(_QWORD *)((char *)v1 + 4330), v23 > 0)
                  && (unsigned __int64)v23 <= 0x2C
                  && ReadFile(*((HANDLE *)v1 + 405), (char *)v1 + 4338, v23, &NumberOfBytesRead, 0)
                  && NumberOfBytesRead == *(_DWORD *)((char *)v1 + 4330) )
                {
                  if ( *(_DWORD *)((char *)v1 + 4342) >= 0xFFFFu )
                    v24 = -1;
                  else
                    v24 = *((_WORD *)v1 + 2171);
                  *v6 = v24;
                  if ( *(_DWORD *)((char *)v1 + 4346) >= 0xFFFFu )
                    v25 = -1;
                  else
                    v25 = *((_WORD *)v1 + 2173);
                  *((_WORD *)v1 + 2155) = v25;
                  if ( *(__int64 *)((char *)v1 + 4350) >= 0xFFFF )
                    v26 = -1;
                  else
                    v26 = *((_WORD *)v1 + 2175);
                  *((_WORD *)v1 + 2156) = v26;
                  if ( *(__int64 *)((char *)v1 + 4358) < 0xFFFF )
                    v9 = *((_WORD *)v1 + 2179);
                  *((_WORD *)v1 + 2157) = v9;
                  if ( *(__int64 *)((char *)v1 + 4366) > 0xFFFFFFFFLL )
                    v27 = -1;
                  else
                    v27 = *(_DWORD *)((char *)v1 + 4366);
                  v1[1079] = v27;
                  if ( *(__int64 *)((char *)v1 + 4374) >= 0xFFFFFFFFLL )
                    v1[1080] = -1;
                  else
                    v1[1080] = *(_DWORD *)((char *)v1 + 4374);
                }
                else
                {
                  *((_QWORD *)v1 + 403) = -1;
                  v7 = 3;
                }
                goto LABEL_19;
              }
              v12 = (unsigned __int16)*v6;
              *(__m128i *)((char *)v1 + 4350) = _mm_unpacklo_epi32(
                                                  _mm_unpacklo_epi16(_mm_cvtsi32_si128(v1[1078]), (__m128i)0LL),
                                                  (__m128i)0LL);
              *(_DWORD *)((char *)v1 + 4342) = v12;
              v13 = *((unsigned __int16 *)v1 + 2155);
              *(__m128i *)((char *)v1 + 4366) = _mm_unpacklo_epi32(
                                                  _mm_loadl_epi64((const __m128i *)(v1 + 1079)),
                                                  (__m128i)0LL);
              *(_DWORD *)v11 = 101075792;
              *(_DWORD *)((char *)v1 + 4346) = v13;
            }
            else
            {
              *(_DWORD *)((char *)v1 + 4326) = 101075792;
              *(_DWORD *)((char *)v1 + 4342) = v8;
              *(_DWORD *)((char *)v1 + 4346) = v14;
              *(_QWORD *)((char *)v1 + 4350) = v18;
              *(_QWORD *)((char *)v1 + 4358) = v17;
              *(_QWORD *)((char *)v1 + 4366) = v16;
              *(_QWORD *)((char *)v1 + 4374) = v15;
            }
            *(_DWORD *)((char *)v1 + 4338) = 1310740;
            *(_QWORD *)((char *)v1 + 4330) = 44;
LABEL_19:
            v1[1076] = 1;
            if ( *(_DWORD *)((char *)v1 + 4342) )
            {
              v1[1199] = 1;
              v28 = DriveFromPath((wchar_t *)v1 + 35248);
              if ( !(unsigned int)IsMediaRemovable(v28) )
                v1[3] = 1;
              v1[1200] = *(_DWORD *)((char *)v1 + 4342);
            }
            else
            {
              v1[1199] = 0;
              if ( *(_DWORD *)((char *)v1 + 4346) )
              {
                if ( *(_QWORD *)((char *)v1 + 4350) == *(_QWORD *)((char *)v1 + 4358) )
                  *(_QWORD *)((char *)v1 + 4342) = 0;
              }
              v1[1200] = 0;
            }
            return v7;
          }
          *((_QWORD *)v1 + 403) = -1;
        }
      }
      return 3;
    }
  }
  v1[1077] = 0xFFFF;
  *(_DWORD *)((char *)v1 + 4342) = -1;
  *(_QWORD *)((char *)v1 + 4358) = 0xFFFFFFFFLL;
  v1[1076] = 1;
  *(_QWORD *)(v1 + 1199) = 1;
  v1[1078] = -65536;
  *(_QWORD *)(v1 + 1079) = 0;
  *((_WORD *)v1 + 2162) = 0;
  *(_DWORD *)((char *)v1 + 4346) = 0;
  *(_QWORD *)((char *)v1 + 4350) = 0;
  *(_QWORD *)((char *)v1 + 4366) = 0;
  *(_QWORD *)((char *)v1 + 4374) = 0;
  return Process_Central_Directory(v4);
}

```

## disassembly

```asm
0x1800170f0  push    rbx
0x1800170f2  push    rbp
0x1800170f3  push    rsi
0x1800170f4  push    rdi
0x1800170f5  push    r12
0x1800170f7  push    r13
0x1800170f9  push    r14
0x1800170fb  push    r15
0x1800170fd  sub     rsp, 48h
0x180017101  mov     rax, cs:__security_cookie
0x180017108  xor     rax, rsp
0x18001710b  mov     [rsp+88h+var_50], rax
0x180017110  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180017116  xor     r13d, r13d
0x180017119  mov     [rsp+88h+NumberOfBytesRead], r13d
0x18001711e  call    cs:__imp_TlsGetValue
0x180017124  mov     rbx, rax
0x180017127  test    rax, rax
0x18001712a  jz      short loc_180017155
0x18001712c  cmp     [rax+10D0h], r13d
0x180017133  jz      short loc_18001715C
0x180017135  xor     eax, eax
0x180017137  mov     rcx, [rsp+88h+var_50]
0x18001713c  xor     rcx, rsp; StackCookie
0x18001713f  call    __security_check_cookie
0x180017144  add     rsp, 48h
0x180017148  pop     r15
0x18001714a  pop     r14
0x18001714c  pop     r13
0x18001714e  pop     r12
0x180017150  pop     rdi
0x180017151  pop     rsi
0x180017152  pop     rbp
0x180017153  pop     rbx
0x180017154  retn
0x180017155  mov     eax, 4
0x18001715a  jmp     short loc_180017137
0x18001715c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017160  mov     [rax+12BCh], r13
0x180017167  xor     ecx, ecx
0x180017169  mov     [rax+0C98h], rdi
0x180017170  call    Find_End_Sig
0x180017175  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017179  jz      loc_1800172C8
0x18001717f  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x180017183  jz      loc_1800173C2
0x180017189  cmp     rax, rdi
0x18001718c  jz      short loc_1800171ED
0x18001718e  lea     r14d, [rdi+2]
0x180017192  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x180017196  jz      loc_1800173CC
0x18001719c  cmp     rax, rdi
0x18001719f  jz      short loc_1800171ED
0x1800171a1  mov     rcx, [rbx+0CA8h]
0x1800171a8  lea     rdx, [rax+4]
0x1800171ac  xor     r8d, r8d
0x1800171af  mov     [rbx+0C98h], rax
0x1800171b6  call    DZSetFilePointer
0x1800171bb  mov     rcx, [rbx+0CA8h]; hFile
0x1800171c2  lea     r12, [rbx+10D4h]
0x1800171c9  mov     rdx, r12; lpBuffer
0x1800171cc  mov     [rsp+88h+lpOverlapped], r13; lpOverlapped
0x1800171d1  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800171d6  mov     r8d, 12h; nNumberOfBytesToRead
0x1800171dc  call    cs:__imp_ReadFile
0x1800171e2  test    eax, eax
0x1800171e4  jnz     short loc_1800171F9
0x1800171e6  mov     [rbx+0C98h], rdi
0x1800171ed  mov     edi, 3
0x1800171f2  mov     eax, edi
0x1800171f4  jmp     loc_180017137
0x1800171f9  cmp     [rsp+88h+NumberOfBytesRead], r13d
0x1800171fe  jz      short loc_1800171E6
0x180017200  movzx   r11d, word ptr [r12]
0x180017205  mov     esi, 0FFFFh
0x18001720a  mov     edi, r13d
0x18001720d  mov     ebp, 0FFFFFFFFh
0x180017212  cmp     r11w, si
0x180017216  jnz     loc_180017337
0x18001721c  call    Find_End_Sig64
0x180017221  lea     r15, [rbx+10E6h]
0x180017228  test    rax, rax
0x18001722b  jns     loc_18001742C
0x180017231  movzx   eax, word ptr [r12]
0x180017236  xorps   xmm0, xmm0
0x180017239  movd    xmm1, dword ptr [rbx+10D8h]
0x180017241  punpcklwd xmm1, xmm0
0x180017245  punpckldq xmm1, xmm0
0x180017249  movdqu  xmmword ptr [rbx+10FEh], xmm1
0x180017251  mov     [rbx+10F6h], eax
0x180017257  movq    xmm1, qword ptr [rbx+10DCh]
0x18001725f  movzx   eax, word ptr [rbx+10D6h]
0x180017266  punpckldq xmm1, xmm0
0x18001726a  movdqu  xmmword ptr [rbx+110Eh], xmm1
0x180017272  mov     dword ptr [r15], 6064B50h
0x180017279  mov     [rbx+10FAh], eax
0x18001727f  mov     dword ptr [rbx+10F2h], 140014h
0x180017289  mov     qword ptr [rbx+10EAh], 2Ch ; ','
0x180017294  mov     [rbx+10D0h], r14d
0x18001729b  cmp     [rbx+10F6h], r13d
0x1800172a2  jnz     loc_1800175A4
0x1800172a8  mov     [rbx+12BCh], r13d
0x1800172af  cmp     [rbx+10FAh], r13d
0x1800172b6  jnz     loc_1800175D7
0x1800172bc  mov     [rbx+12C0h], r13d
0x1800172c3  jmp     loc_1800171F2
0x1800172c8  mov     ebp, 0FFFFFFFFh
0x1800172cd  mov     dword ptr [rbx+10D4h], 0FFFFh
0x1800172d7  mov     r14d, 1
0x1800172dd  mov     [rbx+10F6h], ebp
0x1800172e3  mov     [rbx+1106h], rbp
0x1800172ea  mov     [rbx+10D0h], r14d
0x1800172f1  mov     [rbx+12BCh], r14
0x1800172f8  mov     dword ptr [rbx+10D8h], 0FFFF0000h
0x180017302  mov     [rbx+10DCh], r13
0x180017309  mov     [rbx+10E4h], r13w
0x180017311  mov     [rbx+10FAh], r13d
0x180017318  mov     [rbx+10FEh], r13
0x18001731f  mov     [rbx+110Eh], r13
0x180017326  mov     [rbx+1116h], r13
0x18001732d  call    Process_Central_Directory
0x180017332  jmp     loc_180017137
0x180017337  movzx   r10d, word ptr [rbx+10D6h]
0x18001733f  cmp     r10w, si
0x180017343  jz      loc_18001721C
0x180017349  mov     edx, [rbx+10E0h]
0x18001734f  cmp     edx, ebp
0x180017351  jz      loc_18001721C
0x180017357  mov     ecx, [rbx+10DCh]
0x18001735d  cmp     ecx, ebp
0x18001735f  jz      loc_18001721C
0x180017365  movzx   r9d, word ptr [rbx+10DAh]
0x18001736d  cmp     r9w, si
0x180017371  jz      loc_18001721C
0x180017377  movzx   r8d, word ptr [rbx+10D8h]
0x18001737f  cmp     r8w, si
0x180017383  jz      loc_18001721C
0x180017389  mov     dword ptr [rbx+10E6h], 6064B50h
0x180017393  mov     [rbx+10F6h], r11d
0x18001739a  mov     [rbx+10FAh], r10d
0x1800173a1  mov     [rbx+10FEh], r8
0x1800173a8  mov     [rbx+1106h], r9
0x1800173af  mov     [rbx+110Eh], rcx
0x1800173b6  mov     [rbx+1116h], rdx
0x1800173bd  jmp     loc_18001727F
0x1800173c2  mov     edi, 5
0x1800173c7  jmp     loc_1800171F2
0x1800173cc  call    CloseCurrentZIP
0x1800173d1  cmp     [rbx+0Ch], r13d
0x1800173d5  jz      short loc_1800173E5
0x1800173d7  mov     r8, rbx
0x1800173da  mov     edx, edi
0x1800173dc  xor     ecx, ecx
0x1800173de  call    duzMakeMVFromHDName
0x1800173e3  jmp     short loc_1800173FD
0x1800173e5  mov     rcx, [rbx+0EE0h]
0x1800173ec  xor     r9d, r9d
0x1800173ef  mov     r8d, r14d
0x1800173f2  mov     dword ptr [rsp+88h+lpOverlapped], edi
0x1800173f6  xor     edx, edx
0x1800173f8  call    MsgCB
0x1800173fd  cmp     eax, r14d
0x180017400  jnz     short loc_180017422
0x180017402  call    CheckCurrentZIP
0x180017407  test    eax, eax
0x180017409  jnz     short loc_1800173CC
0x18001740b  call    OpenCurrentZIP
0x180017410  test    rax, rax
0x180017413  jz      short loc_1800173CC
0x180017415  mov     ecx, r14d
0x180017418  call    Find_End_Sig
0x18001741d  jmp     loc_180017192
0x180017422  mov     edi, 30h ; '0'
0x180017427  jmp     loc_1800171F2
0x18001742c  mov     rcx, [rbx+0CA8h]
0x180017433  xor     r8d, r8d
0x180017436  mov     rdx, rax
0x180017439  mov     [rbx+0C98h], rax
0x180017440  call    DZSetFilePointer
0x180017445  xorps   xmm0, xmm0
0x180017448  mov     [rsp+88h+lpOverlapped], r13; lpOverlapped
0x18001744d  movups  xmmword ptr [r15], xmm0
0x180017451  xor     eax, eax
0x180017453  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180017458  movups  xmmword ptr [r15+10h], xmm0
0x18001745d  mov     rdx, r15; lpBuffer
0x180017460  movups  xmmword ptr [r15+20h], xmm0
0x180017465  mov     [r15+30h], rax
0x180017469  lea     r8d, [rax+0Ch]; nNumberOfBytesToRead
0x18001746d  mov     rcx, [rbx+0CA8h]; hFile
0x180017474  call    cs:__imp_ReadFile
0x18001747a  test    eax, eax
0x18001747c  jz      loc_18001758F
0x180017482  cmp     [rsp+88h+NumberOfBytesRead], 0Ch
0x180017487  jnz     loc_18001758F
0x18001748d  cmp     dword ptr [r15], 6064B50h
0x180017494  jnz     loc_18001758F
0x18001749a  mov     rax, [rbx+10EAh]
0x1800174a1  test    rax, rax
0x1800174a4  jle     loc_18001758F
0x1800174aa  cmp     rax, 2Ch ; ','
0x1800174ae  ja      loc_18001758F
0x1800174b4  mov     rcx, [rbx+0CA8h]; hFile
0x1800174bb  lea     rdx, [rbx+10F2h]; lpBuffer
0x1800174c2  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800174c7  mov     [rsp+88h+lpOverlapped], r13; lpOverlapped
0x1800174cc  mov     r8d, eax; nNumberOfBytesToRead
0x1800174cf  call    cs:__imp_ReadFile
0x1800174d5  test    eax, eax
0x1800174d7  jz      loc_18001758F
0x1800174dd  mov     eax, [rbx+10EAh]
0x1800174e3  cmp     [rsp+88h+NumberOfBytesRead], eax
0x1800174e7  jnz     loc_18001758F
0x1800174ed  cmp     [rbx+10F6h], esi
0x1800174f3  jnb     short loc_1800174FE
0x1800174f5  movzx   eax, word ptr [rbx+10F6h]
0x1800174fc  jmp     short loc_180017500
0x1800174fe  mov     eax, esi
0x180017500  mov     [r12], ax
0x180017505  cmp     [rbx+10FAh], esi
0x18001750b  jnb     short loc_180017516
0x18001750d  movzx   eax, word ptr [rbx+10FAh]
0x180017514  jmp     short loc_180017518
0x180017516  mov     eax, esi
0x180017518  mov     [rbx+10D6h], ax
0x18001751f  cmp     [rbx+10FEh], rsi
0x180017526  jge     short loc_180017531
0x180017528  movzx   eax, word ptr [rbx+10FEh]
0x18001752f  jmp     short loc_180017533
0x180017531  mov     eax, esi
0x180017533  mov     [rbx+10D8h], ax
0x18001753a  cmp     [rbx+1106h], rsi
0x180017541  jge     short loc_18001754A
0x180017543  movzx   esi, word ptr [rbx+1106h]
0x18001754a  mov     [rbx+10DAh], si
0x180017551  cmp     [rbx+110Eh], rbp
0x180017558  jg      short loc_180017562
0x18001755a  mov     eax, [rbx+110Eh]
0x180017560  jmp     short loc_180017564
0x180017562  mov     eax, ebp
0x180017564  mov     [rbx+10DCh], eax
0x18001756a  cmp     [rbx+1116h], rbp
0x180017571  jge     short loc_180017584
0x180017573  mov     eax, [rbx+1116h]
0x180017579  mov     [rbx+10E0h], eax
0x18001757f  jmp     loc_180017294
0x180017584  mov     [rbx+10E0h], ebp
0x18001758a  jmp     loc_180017294
0x18001758f  mov     qword ptr [rbx+0C98h], 0FFFFFFFFFFFFFFFFh
0x18001759a  mov     edi, 3
0x18001759f  jmp     loc_180017294
0x1800175a4  lea     rcx, [rbx+11360h]; Str
0x1800175ab  mov     [rbx+12BCh], r14d
0x1800175b2  call    DriveFromPath
0x1800175b7  mov     ecx, eax
0x1800175b9  call    IsMediaRemovable
0x1800175be  test    eax, eax
0x1800175c0  jnz     short loc_1800175C6
0x1800175c2  mov     [rbx+0Ch], r14d
0x1800175c6  mov     eax, [rbx+10F6h]
0x1800175cc  mov     [rbx+12C0h], eax
0x1800175d2  jmp     loc_1800171F2
0x1800175d7  mov     rax, [rbx+1106h]
0x1800175de  cmp     [rbx+10FEh], rax
0x1800175e5  jnz     loc_1800172BC
0x1800175eb  mov     [rbx+10F6h], r13
0x1800175f2  jmp     loc_1800172BC
```
