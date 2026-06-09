# Smb2PerformCopyChunkWorker

- ea: `0x14005a50c`
- end: `0x14005a9b8`
- name: `Smb2PerformCopyChunkWorker`
- size: `1196`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14005a450`
- `0x140068c10`
- `0x140068f48`

## callees

- `0x140013660`
- `0x140013810`
- `0x140022958`
- `0x1400229ac`
- `0x140030c5c`
- `0x14003102c`
- `0x140038490`
- `0x14005a50c`
- `0x140082f60`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x14005a985`
- `ntoskrnl!IoClearActivityIdThread` at `0x14005a985`
- `ntoskrnl!IoSetActivityIdThread` at `0x14005a568`
- `ntoskrnl!IoSetActivityIdThread` at `0x14005a568`

## pseudocode

```c
__int64 __fastcall Smb2PerformCopyChunkWorker(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // rsi
  __int64 v7; // rbp
  char v8; // r14
  unsigned __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 result; // rax
  _DWORD *v21; // rcx
  unsigned int v22; // ecx
  unsigned int v23; // r10d
  __int128 v24; // [rsp+30h] [rbp-48h] BYREF

  v4 = *(_QWORD *)(a1 + 560);
  v6 = *(_QWORD *)(v4 + 216);
  v24 = 0;
  if ( (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    v24 = *(_OWORD *)(a1 + 584);
    v7 = IoSetActivityIdThread(&v24);
    v8 = 1;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  if ( *(_QWORD *)(v4 + 80) )
  {
    Smb2ReferenceObjectFromHandle(a1, a2, a3, a4);
    Smb2DereferenceHandle(*(PVOID *)(v4 + 80));
    *(_QWORD *)(v4 + 80) = 0;
  }
LABEL_6:
  v9 = (unsigned __int64)&WPP_GLOBAL_Control;
  while ( 1 )
  {
    while ( 1 )
    {
      v10 = *(_QWORD *)(a1 + 120);
      if ( *(_DWORD *)(v10 + 48) == -1073741807 )
        *(_DWORD *)(v10 + 48) = -1073741793;
      v11 = *(_QWORD *)(a1 + 120);
      v12 = *(unsigned int *)(v11 + 48);
      if ( *(_DWORD *)(v4 + 408) != 1 )
        break;
      if ( (int)v12 < 0 )
      {
        ++*(_DWORD *)(v4 + 348);
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
        goto LABEL_19;
      }
      v13 = *(unsigned int *)(v4 + 348);
      if ( *(_QWORD *)(v11 + 56) < (unsigned __int64)*(unsigned int *)(v6 + 24 * (v13 + 2)) )
      {
        v14 = v13 + 1;
        v12 = 3221225503LL;
        *(_DWORD *)(v4 + 348) = v14;
        *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = -1073741793;
        goto LABEL_19;
      }
LABEL_45:
      result = Smb2WriteChunk(a1, v13, v11, v9);
      if ( (_DWORD)result == 259 )
        goto LABEL_64;
      v9 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( (int)result < 0 )
      {
        v9 = (unsigned __int64)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            20,
            WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
            a1,
            result,
            *(_DWORD *)(v4 + 348));
          goto LABEL_6;
        }
      }
    }
    if ( *(_DWORD *)(v4 + 408) == 2 )
    {
      ++*(_DWORD *)(v4 + 348);
      *(_DWORD *)(v4 + 344) += *(_DWORD *)(*(_QWORD *)(a1 + 120) + 56LL);
      if ( (int)v12 >= 0 )
        *(_DWORD *)(v4 + 408) = 0;
    }
    else if ( *(_DWORD *)(v4 + 408) == 3 )
    {
      ++*(_DWORD *)(v4 + 348);
    }
LABEL_19:
    *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
    v15 = *(unsigned int *)(v4 + 348);
    if ( (int)v12 < 0 )
      break;
    if ( (unsigned int)v15 >= *(_DWORD *)(v6 + 24) )
    {
      v21 = *(_DWORD **)(v4 + 224);
      if ( *(_BYTE *)(v4 + 414) )
        v15 = *(unsigned int *)(v4 + 416);
      *v21 = v15;
      v21[1] = 0;
      v21[2] = *(_DWORD *)(v4 + 344);
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 12;
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
      goto LABEL_63;
    }
    if ( MEMORY[0xFFFFF78000000014] > Smb2ChunkTimeout + *(_QWORD *)(a1 + 376) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du) )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
            a1,
            *(_DWORD *)(v4 + 348));
          v9 = (unsigned __int64)&WPP_GLOBAL_Control;
        }
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = -1073741643;
      goto LABEL_27;
    }
    v16 = 3 * v15;
    v17 = *(_QWORD *)(v6 + 24 * v15 + 32);
    if ( v17 < 0
      || (v18 = *(unsigned int *)(v6 + 24 * v15 + 48), v18 + v17 < (unsigned __int64)v17)
      || (unsigned __int64)(v18 + v17) > 0x7FFFFFFFFFFFFFFFLL
      || (v19 = *(_QWORD *)(v6 + 8 * v16 + 40), v19 < 0)
      || v19 + v18 < (unsigned __int64)v19
      || (unsigned __int64)(v19 + v18) > 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
          a1,
          -1073741811,
          *(_DWORD *)(v4 + 348));
        v9 = (unsigned __int64)&WPP_GLOBAL_Control;
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = -1073741811;
LABEL_27:
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
      *(_DWORD *)(v4 + 408) = 3;
    }
    else
    {
      result = Smb2ReadChunk(a1, v16, v18, &WPP_GLOBAL_Control);
      v11 = (unsigned int)result;
      if ( (_DWORD)result == 259 )
        goto LABEL_64;
      if ( (int)result >= 0 )
        goto LABEL_45;
      v9 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x1Du)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_2c1ff444f6133b2958c693254061bc13_Traceguids,
          a1,
          result,
          *(_DWORD *)(v4 + 348));
        goto LABEL_6;
      }
    }
  }
  v12 = *(_QWORD *)(v4 + 224);
  if ( *(_BYTE *)(v4 + 414) )
  {
    *(_QWORD *)v12 = 0;
    v15 = *(unsigned int *)(v4 + 344);
    *(_DWORD *)(v12 + 8) = v15;
    *(_DWORD *)(v6 + 48) = *(_DWORD *)(v4 + 420);
    v22 = *(_DWORD *)(v4 + 416);
    if ( v22 )
    {
      v9 = 0;
      do
      {
        v23 = *(_DWORD *)(v6 + 24 * ((unsigned int)v9 + 2LL));
        if ( (unsigned int)v15 < v23 )
          break;
        ++*(_DWORD *)v12;
        v15 = (unsigned int)v15 - v23;
        v22 = *(_DWORD *)(v4 + 416);
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 < v22 );
    }
    if ( *(_DWORD *)v12 < v22 )
      *(_DWORD *)(v12 + 4) = v15;
  }
  else
  {
    *(_DWORD *)v12 = v15 - 1;
    *(_DWORD *)(v12 + 4) = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 56LL);
    *(_DWORD *)(v12 + 8) = *(_DWORD *)(v4 + 344);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 12;
  *(_BYTE *)(v4 + 197) = 1;
LABEL_63:
  result = Smb2ContinueIoctl(a1, v12, v15, v9);
LABEL_64:
  if ( v8 )
    return IoClearActivityIdThread(v7);
  return result;
}

```

## disassembly

```asm
0x14005a50c  mov     [rsp+arg_8], rbx
0x14005a511  mov     [rsp+arg_10], rbp
0x14005a516  push    rsi
0x14005a517  push    rdi
0x14005a518  push    r13
0x14005a51a  push    r14
0x14005a51c  push    r15
0x14005a51e  sub     rsp, 50h
0x14005a522  mov     rax, cs:__security_cookie
0x14005a529  xor     rax, rsp
0x14005a52c  mov     [rsp+78h+var_38], rax
0x14005a531  mov     rbx, [rcx+230h]
0x14005a538  xor     r15d, r15d
0x14005a53b  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x14005a542  xorps   xmm0, xmm0
0x14005a545  mov     rdi, rcx
0x14005a548  mov     rsi, [rbx+0D8h]
0x14005a54f  movups  [rsp+78h+var_48], xmm0
0x14005a554  jz      short loc_14005A57C
0x14005a556  movups  xmm0, xmmword ptr [rcx+248h]
0x14005a55d  lea     rcx, [rsp+78h+var_48]
0x14005a562  movdqu  [rsp+78h+var_48], xmm0
0x14005a568  call    cs:__imp_IoSetActivityIdThread
0x14005a56f  nop     dword ptr [rax+rax+00h]
0x14005a574  mov     rbp, rax
0x14005a577  mov     r14b, 1
0x14005a57a  jmp     short loc_14005A582
0x14005a57c  mov     rbp, r15
0x14005a57f  mov     r14b, r15b
0x14005a582  cmp     [rbx+50h], r15
0x14005a586  jz      short loc_14005A59D
0x14005a588  mov     rcx, rdi
0x14005a58b  call    Smb2ReferenceObjectFromHandle
0x14005a590  mov     rcx, [rbx+50h]; P
0x14005a594  call    Smb2DereferenceHandle
0x14005a599  mov     [rbx+50h], r15
0x14005a59d  lea     r9, WPP_GLOBAL_Control
0x14005a5a4  mov     r10, 7FFFFFFFFFFFFFFFh
0x14005a5ae  mov     rax, [rdi+78h]
0x14005a5b2  cmp     dword ptr [rax+30h], 0C0000011h
0x14005a5b9  jnz     short loc_14005A5C2
0x14005a5bb  mov     dword ptr [rax+30h], 0C000001Fh
0x14005a5c2  mov     r8, [rdi+78h]
0x14005a5c6  mov     ecx, [rbx+198h]
0x14005a5cc  mov     edx, [r8+30h]
0x14005a5d0  sub     ecx, 1
0x14005a5d3  jz      short loc_14005A607
0x14005a5d5  sub     ecx, 1
0x14005a5d8  jz      short loc_14005A5E7
0x14005a5da  cmp     ecx, 1
0x14005a5dd  jnz     short loc_14005A657
0x14005a5df  inc     dword ptr [rbx+15Ch]
0x14005a5e5  jmp     short loc_14005A657
0x14005a5e7  inc     dword ptr [rbx+15Ch]
0x14005a5ed  mov     rax, [rdi+78h]
0x14005a5f1  mov     ecx, [rax+38h]
0x14005a5f4  add     [rbx+158h], ecx
0x14005a5fa  test    edx, edx
0x14005a5fc  js      short loc_14005A657
0x14005a5fe  mov     [rbx+198h], r15d
0x14005a605  jmp     short loc_14005A657
0x14005a607  test    edx, edx
0x14005a609  jns     short loc_14005A61B
0x14005a60b  inc     dword ptr [rbx+15Ch]
0x14005a611  mov     rax, [rdi+78h]
0x14005a615  mov     [rax+38h], r15
0x14005a619  jmp     short loc_14005A657
0x14005a61b  mov     edx, [rbx+15Ch]
0x14005a621  lea     rax, [rdx+2]
0x14005a625  lea     rax, [rax+rax*2]
0x14005a629  mov     ecx, [rsi+rax*8]
0x14005a62c  cmp     [r8+38h], rcx
0x14005a630  jnb     loc_14005A81B
0x14005a636  lea     eax, [rdx+1]
0x14005a639  mov     edx, 0C000001Fh
0x14005a63e  mov     [rbx+15Ch], eax
0x14005a644  mov     rax, [rdi+78h]
0x14005a648  mov     [rax+38h], r15
0x14005a64c  mov     rax, [rdi+78h]
0x14005a650  mov     dword ptr [rax+30h], 0C000001Fh
0x14005a657  mov     rax, [rdi+78h]
0x14005a65b  mov     [rax+8], r15
0x14005a65f  mov     r8d, [rbx+15Ch]
0x14005a666  test    edx, edx
0x14005a668  js      loc_14005A8E4
0x14005a66e  cmp     r8d, [rsi+18h]
0x14005a672  jnb     loc_14005A8A4
0x14005a678  mov     rcx, 0FFFFF78000000014h
0x14005a682  mov     rcx, [rcx]
0x14005a685  mov     rdx, [rdi+178h]
0x14005a68c  add     rdx, cs:Smb2ChunkTimeout
0x14005a693  cmp     rcx, rdx
0x14005a696  jle     short loc_14005A6FC
0x14005a698  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005a69f  cmp     rcx, r9
0x14005a6a2  jz      short loc_14005A6DA
0x14005a6a4  bt      dword ptr [rcx+2Ch], 1Dh
0x14005a6a9  jnb     short loc_14005A6DA
0x14005a6ab  cmp     byte ptr [rcx+29h], 1
0x14005a6af  jb      short loc_14005A6DA
0x14005a6b1  mov     eax, [rbx+15Ch]
0x14005a6b7  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x14005a6be  mov     rcx, [rcx+18h]
0x14005a6c2  mov     edx, 11h
0x14005a6c7  mov     r9, rdi
0x14005a6ca  mov     [rsp+78h+var_58], eax
0x14005a6ce  call    WPP_SF_qD
0x14005a6d3  lea     r9, WPP_GLOBAL_Control
0x14005a6da  mov     rax, [rdi+78h]
0x14005a6de  mov     dword ptr [rax+30h], 0C00000B5h
0x14005a6e5  mov     rax, [rdi+78h]
0x14005a6e9  mov     [rax+38h], r15
0x14005a6ed  mov     dword ptr [rbx+198h], 3
0x14005a6f7  jmp     loc_14005A5A4
0x14005a6fc  lea     rdx, [r8+r8*2]
0x14005a700  mov     rcx, [rsi+rdx*8+20h]
0x14005a705  test    rcx, rcx
0x14005a708  js      loc_14005A7C1
0x14005a70e  lea     rax, [r8+r8*2]
0x14005a712  mov     r8d, [rsi+rax*8+30h]
0x14005a717  lea     rax, [r8+rcx]
0x14005a71b  cmp     rax, rcx
0x14005a71e  jb      loc_14005A7C1
0x14005a724  cmp     rax, r10
0x14005a727  ja      loc_14005A7C1
0x14005a72d  mov     rax, [rsi+rdx*8+28h]
0x14005a732  test    rax, rax
0x14005a735  js      loc_14005A7C1
0x14005a73b  lea     rcx, [rax+r8]
0x14005a73f  cmp     rcx, rax
0x14005a742  jb      short loc_14005A7C1
0x14005a744  cmp     rcx, r10
0x14005a747  ja      short loc_14005A7C1
0x14005a749  mov     rcx, rdi
0x14005a74c  call    Smb2ReadChunk
0x14005a751  mov     r8d, eax
0x14005a754  cmp     eax, 103h
0x14005a759  jz      loc_14005A97D
0x14005a75f  test    eax, eax
0x14005a761  jns     loc_14005A81B
0x14005a767  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005a76e  lea     r9, WPP_GLOBAL_Control
0x14005a775  cmp     r10, r9
0x14005a778  jz      loc_14005A5A4
0x14005a77e  bt      dword ptr [r10+2Ch], 1Dh
0x14005a784  jnb     loc_14005A5A4
0x14005a78a  cmp     byte ptr [r10+29h], 1
0x14005a78f  jb      loc_14005A5A4
0x14005a795  mov     eax, [rbx+15Ch]
0x14005a79b  mov     edx, 13h
0x14005a7a0  mov     rcx, [r10+18h]
0x14005a7a4  mov     r9, rdi
0x14005a7a7  mov     [rsp+78h+var_50], eax
0x14005a7ab  mov     [rsp+78h+var_58], r8d
0x14005a7b0  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x14005a7b7  call    WPP_SF_qDD
0x14005a7bc  jmp     loc_14005A59D
0x14005a7c1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005a7c8  cmp     rcx, r9
0x14005a7cb  jz      short loc_14005A80B
0x14005a7cd  bt      dword ptr [rcx+2Ch], 1Dh
0x14005a7d2  jnb     short loc_14005A80B
0x14005a7d4  cmp     byte ptr [rcx+29h], 1
0x14005a7d8  jb      short loc_14005A80B
0x14005a7da  mov     eax, [rbx+15Ch]
0x14005a7e0  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x14005a7e7  mov     rcx, [rcx+18h]
0x14005a7eb  mov     edx, 12h
0x14005a7f0  mov     [rsp+78h+var_50], eax
0x14005a7f4  mov     r9, rdi
0x14005a7f7  mov     [rsp+78h+var_58], 0C000000Dh
0x14005a7ff  call    WPP_SF_qDD
0x14005a804  lea     r9, WPP_GLOBAL_Control
0x14005a80b  mov     rax, [rdi+78h]
0x14005a80f  mov     dword ptr [rax+30h], 0C000000Dh
0x14005a816  jmp     loc_14005A6E5
0x14005a81b  mov     rcx, rdi
0x14005a81e  call    Smb2WriteChunk
0x14005a823  mov     r8d, eax
0x14005a826  cmp     eax, 103h
0x14005a82b  jz      loc_14005A97D
0x14005a831  lea     r9, WPP_GLOBAL_Control
0x14005a838  mov     r10, 7FFFFFFFFFFFFFFFh
0x14005a842  test    eax, eax
0x14005a844  jns     loc_14005A5AE
0x14005a84a  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005a851  lea     r9, WPP_GLOBAL_Control
0x14005a858  cmp     r10, r9
0x14005a85b  jz      loc_14005A5A4
0x14005a861  bt      dword ptr [r10+2Ch], 1Dh
0x14005a867  jnb     loc_14005A5A4
0x14005a86d  cmp     byte ptr [r10+29h], 1
0x14005a872  jb      loc_14005A5A4
0x14005a878  mov     eax, [rbx+15Ch]
0x14005a87e  mov     edx, 14h
0x14005a883  mov     rcx, [r10+18h]
0x14005a887  mov     r9, rdi
0x14005a88a  mov     [rsp+78h+var_50], eax
0x14005a88e  mov     [rsp+78h+var_58], r8d
0x14005a893  lea     r8, WPP_2c1ff444f6133b2958c693254061bc13_Traceguids
0x14005a89a  call    WPP_SF_qDD
0x14005a89f  jmp     loc_14005A59D
0x14005a8a4  mov     rcx, [rbx+0E0h]
0x14005a8ab  cmp     [rbx+19Eh], r15b
0x14005a8b2  jz      short loc_14005A8BB
0x14005a8b4  mov     r8d, [rbx+1A0h]
0x14005a8bb  mov     [rcx], r8d
0x14005a8be  mov     [rcx+4], r15d
0x14005a8c2  mov     eax, [rbx+158h]
0x14005a8c8  mov     [rcx+8], eax
0x14005a8cb  mov     rax, [rdi+78h]
0x14005a8cf  mov     qword ptr [rax+38h], 0Ch
0x14005a8d7  mov     rax, [rdi+78h]
0x14005a8db  mov     [rax+30h], r15d
0x14005a8df  jmp     loc_14005A975
0x14005a8e4  mov     rdx, [rbx+0E0h]
0x14005a8eb  cmp     [rbx+19Eh], r15b
0x14005a8f2  jz      short loc_14005A949
0x14005a8f4  mov     [rdx], r15
0x14005a8f7  mov     r8d, [rbx+158h]
0x14005a8fe  mov     [rdx+8], r8d
0x14005a902  mov     eax, [rbx+1A4h]
0x14005a908  mov     [rsi+30h], eax
0x14005a90b  mov     ecx, [rbx+1A0h]
0x14005a911  test    ecx, ecx
0x14005a913  jz      short loc_14005A93F
0x14005a915  mov     r9d, r15d
0x14005a918  mov     eax, r9d
0x14005a91b  add     rax, 2
0x14005a91f  lea     rax, [rax+rax*2]
0x14005a923  mov     r10d, [rsi+rax*8]
0x14005a927  cmp     r8d, r10d
0x14005a92a  jb      short loc_14005A93F
0x14005a92c  inc     dword ptr [rdx]
0x14005a92e  sub     r8d, r10d
0x14005a931  mov     ecx, [rbx+1A0h]
0x14005a937  inc     r9d
0x14005a93a  cmp     r9d, ecx
0x14005a93d  jb      short loc_14005A918
0x14005a93f  cmp     [rdx], ecx
0x14005a941  jnb     short loc_14005A962
0x14005a943  mov     [rdx+4], r8d
0x14005a947  jmp     short loc_14005A962
0x14005a949  lea     eax, [r8-1]
0x14005a94d  mov     [rdx], eax
0x14005a94f  mov     rax, [rdi+78h]
0x14005a953  mov     ecx, [rax+38h]
0x14005a956  mov     [rdx+4], ecx
0x14005a959  mov     eax, [rbx+158h]
0x14005a95f  mov     [rdx+8], eax
0x14005a962  mov     rax, [rdi+78h]
0x14005a966  mov     qword ptr [rax+38h], 0Ch
0x14005a96e  mov     byte ptr [rbx+0C5h], 1
0x14005a975  mov     rcx, rdi
0x14005a978  call    Smb2ContinueIoctl
0x14005a97d  test    r14b, r14b
0x14005a980  jz      short loc_14005A991
0x14005a982  mov     rcx, rbp
0x14005a985  call    cs:__imp_IoClearActivityIdThread
0x14005a98c  nop     dword ptr [rax+rax+00h]
0x14005a991  mov     rcx, [rsp+78h+var_38]
0x14005a996  xor     rcx, rsp; StackCookie
0x14005a999  call    __security_check_cookie
0x14005a99e  lea     r11, [rsp+78h+var_28]
0x14005a9a3  mov     rbx, [r11+38h]
0x14005a9a7  mov     rbp, [r11+40h]
0x14005a9ab  mov     rsp, r11
0x14005a9ae  pop     r15
0x14005a9b0  pop     r14
0x14005a9b2  pop     r13
0x14005a9b4  pop     rdi
0x14005a9b5  pop     rsi
0x14005a9b6  retn
```
