# UdfUpdateVolumeStructures

- ea: `0x140039938`
- end: `0x140039d0e`
- name: `UdfUpdateVolumeStructures`
- size: `982`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x140017c08`
- `0x140031d9c`

## callees

- `0x140009450`
- `0x14000a870`
- `0x14000b128`
- `0x14000c21c`
- `0x14000e5d8`
- `0x14001bc30`
- `0x14001bd80`
- `0x14002fe08`
- `0x140039938`
- `0x140049bb0`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140039cd7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039cd7`

## pseudocode

```c
__int64 __fastcall UdfUpdateVolumeStructures(__int64 a1, __int64 a2, char a3)
{
  __int64 result; // rax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // ebx
  char v11; // r15
  int v12; // ecx
  int v13; // ecx
  unsigned int *v14; // rsi
  __int64 v15; // rcx
  int v16; // esi
  _DWORD *v17; // rsi
  __int64 v18; // rcx
  _DWORD *v19; // rbx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned int v22; // [rsp+44h] [rbp-84h]
  int v23; // [rsp+44h] [rbp-84h]
  _QWORD v24[3]; // [rsp+50h] [rbp-78h] BYREF
  __int128 v25; // [rsp+68h] [rbp-60h] BYREF
  __int128 v26; // [rsp+78h] [rbp-50h]
  int v27; // [rsp+88h] [rbp-40h]

  v24[1] = a1;
  v24[2] = a2;
  v24[0] = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  result = UdfReadTrackInfo(*(_QWORD *)(a2 + 24), *(unsigned int *)(a2 + 480), &v25, 36);
  if ( (int)result >= 0 )
  {
    if ( a3 )
    {
      LOBYTE(v22) = HIBYTE(v25);
      BYTE1(v22) = BYTE14(v25);
      BYTE2(v22) = BYTE13(v25);
      HIBYTE(v22) = BYTE12(v25);
      v7 = v22;
      if ( v22 < 0xFEF0 )
        v7 = 65264;
      *(_DWORD *)(a2 + 684) = v7;
    }
    else
    {
      LOBYTE(v23) = BYTE11(v26);
      BYTE1(v23) = BYTE10(v26);
      BYTE2(v23) = BYTE9(v26);
      HIBYTE(v23) = BYTE8(v26);
      *(_BYTE *)(a2 + 684) = HIBYTE(v25);
      *(_BYTE *)(a2 + 685) = BYTE14(v25);
      *(_BYTE *)(a2 + 686) = BYTE13(v25);
      *(_BYTE *)(a2 + 687) = BYTE12(v25);
      v7 = v23;
    }
    v8 = *(_QWORD *)(a2 + 16);
    v9 = 56LL * *(unsigned __int16 *)(v8 + 92);
    v10 = v7 - *(_DWORD *)(v9 + v8 + 104);
    if ( !a3 )
      v10 = v10 - *(_DWORD *)(v8 + 32) - 256;
    if ( *(_DWORD *)(v9 + v8 + 108) == v10 )
    {
      return 0;
    }
    else
    {
      v11 = 0;
      v12 = *(_DWORD *)(a2 + 660);
      *(_DWORD *)(a2 + 668) += v10 - v12;
      *(_DWORD *)(a2 + 664) += v10 - v12;
      if ( a3 )
      {
        v13 = v12 - v10;
        *(_DWORD *)(a2 + 680) = v13;
        *(_DWORD *)(a2 + 680) = *(_DWORD *)(v8 + 32) + 256 + v13;
      }
      *(_DWORD *)(a2 + 660) = v10;
      v14 = *(unsigned int **)(56LL * *(unsigned __int16 *)(v8 + 92) + v8 + 128);
      v14[48] = v10;
      UdfUpdateChecksumAndCrc(v14, 512);
      v16 = UdfReadWriteSectors(
              a1,
              (union _LARGE_INTEGER)((unsigned __int64)v14[3] << *(_DWORD *)(a2 + 72)),
              *(unsigned int *)(a2 + 68),
              1,
              v14,
              *(PDEVICE_OBJECT *)(a2 + 24),
              1);
      if ( v16 >= 0 )
      {
        *(_DWORD *)(56LL * *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 92LL) + *(_QWORD *)(a2 + 16) + 108) = v10;
        UdfAcquireResource(a1, a2 + 552, 0, 0);
        v11 = 1;
        UdfMapOrPinBitmapLbnRange(a1, 0, 0);
        if ( a3 )
        {
          v17 = *(_DWORD **)(*(_QWORD *)(a2 + 104) + 24LL);
          memmove(v17, *(const void **)(a2 + 512), *(unsigned int *)(a2 + 88));
        }
        else
        {
          v17 = *(_DWORD **)(a2 + 512);
        }
        v17[4] = v10;
        v17[5] = (unsigned int)(v10 + 7) >> 3;
        UdfUpdateChecksumAndCrc(v17, 24);
        UdfUnpinCurrentBitmapPage(v18, a2, 0);
        v16 = UdfReadWriteSectors(
                a1,
                (union _LARGE_INTEGER)((unsigned __int64)(unsigned int)(*(_DWORD *)(56LL
                                                                                  * *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 92LL)
                                                                                  + *(_QWORD *)(a2 + 16)
                                                                                  + 104)
                                                                      + *(_DWORD *)(56LL
                                                                                  * *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 92LL)
                                                                                  + *(_QWORD *)(a2 + 16)
                                                                                  + 120)) << *(_DWORD *)(a2 + 72)),
                *(unsigned int *)(a2 + 88),
                1,
                v17,
                *(PDEVICE_OBJECT *)(a2 + 24),
                1);
        if ( v16 >= 0 )
        {
          if ( a3 )
          {
            v19 = *(_DWORD **)(a2 + 1424);
            v20 = (unsigned int)(2 * v19[18]);
            v19[19] = 48;
            *(_OWORD *)&v19[v20 + 20] = UdfMsRegId;
            *(_OWORD *)&v19[v20 + 24] = xmmword_140025350;
            v19[*(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 92LL) + 20] = *(_DWORD *)(a2 + 668);
            v21 = (unsigned int)v19[18] + (unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 92LL);
            v19[v21 + 20] = *(_DWORD *)(a2 + 660);
            v24[0] = MEMORY[0xFFFFF78000000014];
            UdfConvertNtTimeToUdfTime(v21, v24, v19 + 4);
            UdfUpdateChecksumAndCrc(v19, (unsigned int)(v19[19] + 80 + 8 * v19[18]));
            v16 = UdfReadWriteSectors(
                    a1,
                    (union _LARGE_INTEGER)(unsigned int)(*(_DWORD *)(a2 + 1400) << *(_DWORD *)(a2 + 72)),
                    *(unsigned int *)(a2 + 68),
                    1,
                    v19,
                    *(PDEVICE_OBJECT *)(a2 + 24),
                    1);
          }
        }
      }
      if ( v11 )
      {
        UdfUnpinCurrentBitmapPage(v15, a2, 0);
        ExReleaseResourceLite((PERESOURCE)(a2 + 552));
      }
      return (unsigned int)v16;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140039938  mov     r11, rsp
0x14003993b  mov     [r11+18h], rbx
0x14003993f  push    rsi
0x140039940  push    rdi
0x140039941  push    r12
0x140039943  push    r14
0x140039945  push    r15
0x140039947  sub     rsp, 0A0h
0x14003994e  mov     rax, cs:__security_cookie
0x140039955  xor     rax, rsp
0x140039958  mov     [rsp+0C8h+var_38], rax
0x140039960  mov     r14b, r8b
0x140039963  mov     rdi, rdx
0x140039966  mov     r12, rcx
0x140039969  mov     [rsp+0C8h+var_70], rcx
0x14003996e  mov     [rsp+0C8h+var_68], rdx
0x140039973  mov     qword ptr [r11-78h], 0
0x14003997b  xorps   xmm0, xmm0
0x14003997e  xor     eax, eax
0x140039980  movups  [rsp+0C8h+var_60], xmm0
0x140039985  movups  [rsp+0C8h+var_50], xmm0
0x14003998a  mov     [r11-40h], eax
0x14003998e  lea     r9d, [rax+24h]
0x140039992  lea     r8, [r11-60h]
0x140039996  mov     edx, [rdx+1E0h]
0x14003999c  mov     rcx, [rdi+18h]
0x1400399a0  call    UdfReadTrackInfo
0x1400399a5  test    eax, eax
0x1400399a7  js      loc_140039CE5
0x1400399ad  test    r14b, r14b
0x1400399b0  jz      short loc_1400399E8
0x1400399b2  mov     al, byte ptr [rsp+0C8h+var_60+0Fh]
0x1400399b6  mov     byte ptr [rsp+0C8h+var_84], al
0x1400399ba  mov     al, byte ptr [rsp+0C8h+var_60+0Eh]
0x1400399be  mov     byte ptr [rsp+0C8h+var_84+1], al
0x1400399c2  mov     al, byte ptr [rsp+0C8h+var_60+0Dh]
0x1400399c6  mov     byte ptr [rsp+0C8h+var_84+2], al
0x1400399ca  mov     al, byte ptr [rsp+0C8h+var_60+0Ch]
0x1400399ce  mov     byte ptr [rsp+0C8h+var_84+3], al
0x1400399d2  mov     ebx, [rsp+0C8h+var_84]
0x1400399d6  mov     eax, 0FEF0h
0x1400399db  cmp     ebx, eax
0x1400399dd  cmovb   ebx, eax
0x1400399e0  mov     [rdi+2ACh], ebx
0x1400399e6  jmp     short loc_140039A40
0x1400399e8  mov     al, byte ptr [rsp+0C8h+var_50+0Bh]
0x1400399ef  mov     byte ptr [rsp+0C8h+var_84], al
0x1400399f3  mov     al, byte ptr [rsp+0C8h+var_50+0Ah]
0x1400399fa  mov     byte ptr [rsp+0C8h+var_84+1], al
0x1400399fe  mov     al, byte ptr [rsp+0C8h+var_50+9]
0x140039a05  mov     byte ptr [rsp+0C8h+var_84+2], al
0x140039a09  mov     al, byte ptr [rsp+0C8h+var_50+8]
0x140039a10  mov     byte ptr [rsp+0C8h+var_84+3], al
0x140039a14  mov     al, byte ptr [rsp+0C8h+var_60+0Fh]
0x140039a18  mov     [rdi+2ACh], al
0x140039a1e  mov     al, byte ptr [rsp+0C8h+var_60+0Eh]
0x140039a22  mov     [rdi+2ADh], al
0x140039a28  mov     al, byte ptr [rsp+0C8h+var_60+0Dh]
0x140039a2c  mov     [rdi+2AEh], al
0x140039a32  mov     al, byte ptr [rsp+0C8h+var_60+0Ch]
0x140039a36  mov     [rdi+2AFh], al
0x140039a3c  mov     ebx, [rsp+0C8h+var_84]
0x140039a40  mov     rdx, [rdi+10h]
0x140039a44  movzx   eax, word ptr [rdx+5Ch]
0x140039a48  imul    rcx, rax, 38h ; '8'
0x140039a4c  sub     ebx, [rcx+rdx+68h]
0x140039a50  test    r14b, r14b
0x140039a53  jnz     short loc_140039A5E
0x140039a55  sub     ebx, [rdx+20h]
0x140039a58  sub     ebx, 100h
0x140039a5e  cmp     [rcx+rdx+6Ch], ebx
0x140039a62  jnz     short loc_140039A6B
0x140039a64  xor     eax, eax
0x140039a66  jmp     loc_140039CE5
0x140039a6b  xor     r15b, r15b
0x140039a6e  mov     [rsp+0C8h+var_88], r15b
0x140039a73  mov     ecx, [rdi+294h]
0x140039a79  mov     eax, ebx
0x140039a7b  sub     eax, ecx
0x140039a7d  add     [rdi+29Ch], eax
0x140039a83  add     [rdi+298h], eax
0x140039a89  test    r14b, r14b
0x140039a8c  jz      short loc_140039AA6
0x140039a8e  sub     ecx, ebx
0x140039a90  mov     [rdi+2A8h], ecx
0x140039a96  mov     eax, [rdx+20h]
0x140039a99  add     eax, 100h
0x140039a9e  add     ecx, eax
0x140039aa0  mov     [rdi+2A8h], ecx
0x140039aa6  mov     [rdi+294h], ebx
0x140039aac  movzx   eax, word ptr [rdx+5Ch]
0x140039ab0  imul    rcx, rax, 38h ; '8'
0x140039ab4  mov     rsi, [rcx+rdx+80h]
0x140039abc  mov     [rsi+0C0h], ebx
0x140039ac2  mov     edx, 200h
0x140039ac7  mov     rcx, rsi
0x140039aca  call    UdfUpdateChecksumAndCrc
0x140039acf  nop
0x140039ad0  mov     edx, [rsi+0Ch]
0x140039ad3  mov     ecx, [rdi+48h]
0x140039ad6  shl     rdx, cl
0x140039ad9  mov     [rsp+0C8h+var_98], 1
0x140039ade  mov     rax, [rdi+18h]
0x140039ae2  mov     [rsp+0C8h+var_A0], rax
0x140039ae7  mov     [rsp+0C8h+var_A8], rsi
0x140039aec  mov     r9b, 1
0x140039aef  mov     r8d, [rdi+44h]
0x140039af3  mov     rcx, r12
0x140039af6  call    UdfReadWriteSectors
0x140039afb  mov     esi, eax
0x140039afd  mov     [rsp+0C8h+var_80], eax
0x140039b01  test    eax, eax
0x140039b03  js      loc_140039CA1
0x140039b09  mov     rdx, [rdi+10h]
0x140039b0d  movzx   eax, word ptr [rdx+5Ch]
0x140039b11  imul    rcx, rax, 38h ; '8'
0x140039b15  mov     [rcx+rdx+6Ch], ebx
0x140039b19  lea     rdx, [rdi+228h]
0x140039b20  xor     r9d, r9d
0x140039b23  xor     r8d, r8d
0x140039b26  mov     rcx, r12
0x140039b29  call    UdfAcquireResource
0x140039b2e  mov     r15b, 1
0x140039b31  mov     [rsp+0C8h+var_88], r15b
0x140039b36  xor     r8d, r8d
0x140039b39  xor     edx, edx
0x140039b3b  mov     rcx, r12
0x140039b3e  call    UdfMapOrPinBitmapLbnRange
0x140039b43  test    r14b, r14b
0x140039b46  jz      short loc_140039B65
0x140039b48  mov     rax, [rdi+68h]
0x140039b4c  mov     rsi, [rax+18h]
0x140039b50  mov     r8d, [rdi+58h]; Size
0x140039b54  mov     rdx, [rdi+200h]; Src
0x140039b5b  mov     rcx, rsi; void *
0x140039b5e  call    memmove
0x140039b63  jmp     short loc_140039B6C
0x140039b65  mov     rsi, [rdi+200h]
0x140039b6c  mov     [rsi+10h], ebx
0x140039b6f  lea     eax, [rbx+7]
0x140039b72  shr     eax, 3
0x140039b75  mov     [rsi+14h], eax
0x140039b78  mov     edx, 18h
0x140039b7d  mov     rcx, rsi
0x140039b80  call    UdfUpdateChecksumAndCrc
0x140039b85  xor     r8d, r8d
0x140039b88  mov     rdx, rdi
0x140039b8b  call    UdfUnpinCurrentBitmapPage
0x140039b90  mov     rdx, [rdi+10h]
0x140039b94  movzx   eax, word ptr [rdx+5Ch]
0x140039b98  imul    rcx, rax, 38h ; '8'
0x140039b9c  mov     eax, [rcx+rdx+78h]
0x140039ba0  add     eax, [rcx+rdx+68h]
0x140039ba4  mov     edx, eax
0x140039ba6  mov     ecx, [rdi+48h]
0x140039ba9  shl     rdx, cl
0x140039bac  mov     [rsp+0C8h+var_98], r15b
0x140039bb1  mov     rax, [rdi+18h]
0x140039bb5  mov     [rsp+0C8h+var_A0], rax
0x140039bba  mov     [rsp+0C8h+var_A8], rsi
0x140039bbf  mov     r9b, r15b
0x140039bc2  mov     r8d, [rdi+58h]
0x140039bc6  mov     rcx, r12
0x140039bc9  call    UdfReadWriteSectors
0x140039bce  mov     esi, eax
0x140039bd0  mov     [rsp+0C8h+var_80], eax
0x140039bd4  test    eax, eax
0x140039bd6  js      loc_140039CA1
0x140039bdc  test    r14b, r14b
0x140039bdf  jz      loc_140039CA1
0x140039be5  mov     rbx, [rdi+590h]
0x140039bec  mov     eax, [rbx+48h]
0x140039bef  add     eax, eax
0x140039bf1  mov     dword ptr [rbx+4Ch], 30h ; '0'
0x140039bf8  movups  xmm0, cs:UdfMsRegId
0x140039bff  movups  xmmword ptr [rbx+rax*4+50h], xmm0
0x140039c04  movups  xmm1, cs:xmmword_140025350
0x140039c0b  movups  xmmword ptr [rbx+rax*4+60h], xmm1
0x140039c10  mov     rax, [rdi+10h]
0x140039c14  movzx   ecx, word ptr [rax+5Ch]
0x140039c18  mov     eax, [rdi+29Ch]
0x140039c1e  mov     [rbx+rcx*4+50h], eax
0x140039c22  mov     rax, [rdi+10h]
0x140039c26  movzx   ecx, word ptr [rax+5Ch]
0x140039c2a  mov     eax, [rbx+48h]
0x140039c2d  add     rcx, rax
0x140039c30  mov     eax, [rdi+294h]
0x140039c36  mov     [rbx+rcx*4+50h], eax
0x140039c3a  mov     rax, 0FFFFF78000000014h
0x140039c44  mov     rax, [rax]
0x140039c47  mov     [rsp+0C8h+var_78], rax
0x140039c4c  lea     r8, [rbx+10h]
0x140039c50  lea     rdx, [rsp+0C8h+var_78]
0x140039c55  call    UdfConvertNtTimeToUdfTime
0x140039c5a  mov     edx, [rbx+48h]
0x140039c5d  mov     eax, [rbx+4Ch]
0x140039c60  add     eax, 50h ; 'P'
0x140039c63  lea     edx, [rax+rdx*8]
0x140039c66  mov     rcx, rbx
0x140039c69  call    UdfUpdateChecksumAndCrc
0x140039c6e  mov     ecx, [rdi+48h]
0x140039c71  mov     edx, [rdi+578h]
0x140039c77  shl     edx, cl
0x140039c79  mov     [rsp+0C8h+var_98], r15b
0x140039c7e  mov     rax, [rdi+18h]
0x140039c82  mov     [rsp+0C8h+var_A0], rax
0x140039c87  mov     [rsp+0C8h+var_A8], rbx
0x140039c8c  mov     r9b, r15b
0x140039c8f  mov     r8d, [rdi+44h]
0x140039c93  mov     rcx, r12
0x140039c96  call    UdfReadWriteSectors
0x140039c9b  mov     esi, eax
0x140039c9d  mov     [rsp+0C8h+var_80], eax
0x140039ca1  jmp     short loc_140039CC0
0x140039ca3  mov     rax, [rsp+0C8h+var_70]
0x140039ca8  mov     esi, [rax+18h]
0x140039cab  mov     [rsp+0C8h+var_80], esi
0x140039caf  mov     dword ptr [rax+18h], 0
0x140039cb6  mov     r15b, [rsp+0C8h+var_88]
0x140039cbb  mov     rdi, [rsp+0C8h+var_68]
0x140039cc0  test    r15b, r15b
0x140039cc3  jz      short loc_140039CE3
0x140039cc5  xor     r8d, r8d
0x140039cc8  mov     rdx, rdi
0x140039ccb  call    UdfUnpinCurrentBitmapPage
0x140039cd0  lea     rcx, [rdi+228h]; Resource
0x140039cd7  call    cs:__imp_ExReleaseResourceLite
0x140039cde  nop     dword ptr [rax+rax+00h]
0x140039ce3  mov     eax, esi
0x140039ce5  mov     rcx, [rsp+0C8h+var_38]
0x140039ced  xor     rcx, rsp; StackCookie
0x140039cf0  call    __security_check_cookie
0x140039cf5  mov     rbx, [rsp+0C8h+arg_10]
0x140039cfd  add     rsp, 0A0h
0x140039d04  pop     r15
0x140039d06  pop     r14
0x140039d08  pop     r12
0x140039d0a  pop     rdi
0x140039d0b  pop     rsi
0x140039d0c  retn
0x14005c1a4  push    rbp
0x14005c1a6  sub     rsp, 40h
0x14005c1aa  mov     rbp, rdx
0x14005c1ad  mov     rdx, rcx
0x14005c1b0  mov     rcx, [rbp+58h]
0x14005c1b4  call    UdfExceptionFilter
0x14005c1b9  nop
0x14005c1ba  add     rsp, 40h
0x14005c1be  pop     rbp
0x14005c1bf  retn
```
