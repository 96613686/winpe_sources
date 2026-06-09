# CVaultGenericPropertyCollection<ECredPropertyId,5>::DeserializeCollection(uchar * &,ulong &)

- ea: `0x180005df0`
- end: `0x1800062a0`
- name: `?DeserializeCollection@?$CVaultGenericPropertyCollection@W4ECredPropertyId@@$04@@QEAAKAEAPEAEAEAK@Z`
- size: `1200`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006680`
- `0x18002a9e0`

## callees

- `0x180005df0`
- `0x1800062a8`
- `0x180028de4`
- `0x18002f340`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006059`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006059`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180005ffc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180005ffc`

## pseudocode

```c
__int64 __fastcall CVaultGenericPropertyCollection<enum ECredPropertyId,5>::DeserializeCollection(
        __int64 a1,
        _DWORD **a2,
        int *a3)
{
  __int64 v5; // rdi
  unsigned int v6; // ebx
  int v7; // ecx
  __int64 result; // rax
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rsi
  _DWORD *v12; // rax
  int v13; // r13d
  _DWORD *v14; // rcx
  int v15; // eax
  _WORD *v16; // rdx
  unsigned int v17; // r12d
  unsigned int v18; // eax
  const void *v19; // rdi
  HLOCAL v20; // rax
  unsigned int v21; // r13d
  SIZE_T v22; // rsi
  char *v23; // rbp
  __int64 i; // rbx
  _QWORD *v25; // r11
  HLOCAL v26; // rax
  __int64 v27; // r9
  __int64 v28; // r10
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // xmm1_8
  int v32; // [rsp+20h] [rbp-78h]
  _DWORD *v33; // [rsp+28h] [rbp-70h] BYREF
  __int64 v34; // [rsp+30h] [rbp-68h]
  _QWORD *v35; // [rsp+38h] [rbp-60h]
  __int128 v36; // [rsp+40h] [rbp-58h] BYREF
  __int64 v37; // [rsp+50h] [rbp-48h]
  unsigned int Source2; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v40; // [rsp+B8h] [rbp+20h]

  v5 = a1;
  if ( !*a3 )
  {
    v6 = 0;
    v40 = 0;
LABEL_46:
    v7 = 5;
    goto LABEL_6;
  }
  if ( (unsigned int)*a3 < 4 )
    return 122;
  v6 = *(*a2)++;
  *a3 -= 4;
  v40 = v6;
  if ( v6 > 0x100 )
    return 87;
  if ( v6 < 5 )
    goto LABEL_46;
  v7 = v6;
LABEL_6:
  *(_DWORD *)v5 = v7;
  result = CVaultGenericPropertyCollection<enum EVaultPropertyId,0>::CreateProperties(v5);
  if ( (_DWORD)result )
    return result;
  v9 = 0;
  v35 = (_QWORD *)(v5 + 8);
  while ( 1 )
  {
    v32 = v9;
    if ( (unsigned int)v9 >= v6 )
      break;
    if ( (unsigned int)*a3 < 4 )
      return 122;
    v10 = *(_QWORD *)(v5 + 8);
    v35 = (_QWORD *)(v5 + 8);
    v11 = *(_QWORD *)(v10 + 8 * v9);
    v12 = *a2;
    v34 = v11;
    *(_DWORD *)v11 = *v12;
    ++*a2;
    *a3 -= 4;
    v13 = *a3;
    v14 = *a2;
    if ( (unsigned int)*a3 < 4 )
      return 122;
    v15 = *v14;
    v16 = v14 + 1;
    *(_DWORD *)(v11 + 8) = *v14;
    v17 = v13 - 4;
    v33 = v14 + 1;
    Source2 = v13 - 4;
    if ( v15 == 7 )
    {
      LOWORD(Source2) = 0;
      if ( v17 < 4 )
      {
        result = 122;
        goto LABEL_20;
      }
      v22 = *(unsigned int *)v16;
      v23 = (char *)(v14 + 2);
      v17 = v13 - 8;
      if ( (unsigned int)v22 < 2 )
      {
        result = 0;
        *(_QWORD *)(v34 + 16) = 0;
        goto LABEL_20;
      }
      if ( (unsigned int)v22 > v13 - 8 )
      {
        result = 122;
        goto LABEL_20;
      }
      if ( (v22 & 1) != 0 )
      {
        result = 1358;
        goto LABEL_20;
      }
      for ( i = 0; ; i = (unsigned int)(i + 2) )
      {
        if ( (unsigned int)i >= (unsigned int)v22 )
          goto LABEL_37;
        if ( RtlCompareMemory(&v23[i], &Source2, 2u) == 2 )
          break;
      }
      if ( (unsigned int)i != v22 - 2 )
      {
LABEL_37:
        result = 1358;
        goto LABEL_18;
      }
      v26 = LocalAlloc(0x40u, v22);
      *(_QWORD *)(v34 + 16) = v26;
      if ( v26 )
      {
        memcpy_0(v26, v23, v22);
        v17 -= v22;
        result = 0;
      }
      else
      {
        result = 14;
      }
    }
    else
    {
      if ( v15 != 8 )
      {
        switch ( v15 )
        {
          case 0:
            result = VaultDeserialize<unsigned char>(&v33, &Source2, v11 + 16);
            v17 = Source2;
            goto LABEL_19;
          case 1:
          case 2:
            if ( v17 >= 2 )
            {
              v17 = v13 - 6;
              *(_WORD *)(v11 + 16) = *v16;
              result = 0;
            }
            else
            {
              result = 122;
            }
            goto LABEL_20;
          case 3:
          case 4:
            if ( v17 >= 4 )
            {
              v17 = v13 - 8;
              *(_DWORD *)(v11 + 16) = *(_DWORD *)v16;
              result = 0;
            }
            else
            {
              result = 122;
            }
            goto LABEL_20;
          case 5:
            if ( v17 >= 8 )
            {
              v17 = v13 - 12;
              *(_QWORD *)(v11 + 16) = *(_QWORD *)v16;
              result = 0;
            }
            else
            {
              result = 122;
            }
            goto LABEL_20;
          case 6:
            if ( v17 < 0x10 )
            {
              result = 122;
            }
            else
            {
              v17 = v13 - 20;
              result = 0;
              *(_OWORD *)(v11 + 16) = *(_OWORD *)v16;
            }
            goto LABEL_20;
          case 10:
            goto LABEL_13;
          default:
            result = 87;
            break;
        }
        return result;
      }
LABEL_13:
      *(_OWORD *)(v11 + 16) = 0;
      if ( v17 < 4 )
      {
        result = 122;
        goto LABEL_20;
      }
      v18 = *(_DWORD *)v16;
      *(_DWORD *)(v11 + 16) = *(_DWORD *)v16;
      v19 = v14 + 2;
      v33 = v14 + 2;
      v17 = v13 - 8;
      if ( v18 > v13 - 8 )
      {
        v6 = v40;
        result = 122;
        v5 = a1;
        goto LABEL_20;
      }
      if ( !v18 )
      {
        v6 = v40;
        result = 0;
        v5 = a1;
        goto LABEL_20;
      }
      v20 = LocalAlloc(0x40u, v18);
      *(_QWORD *)(v11 + 24) = v20;
      if ( v20 )
      {
        memcpy_0(v20, v19, *(unsigned int *)(v11 + 16));
        v17 -= *(_DWORD *)(v11 + 16);
        result = 0;
      }
      else
      {
        result = 14;
      }
    }
LABEL_18:
    v5 = a1;
    v6 = v40;
LABEL_19:
    LODWORD(v9) = v32;
LABEL_20:
    if ( (_DWORD)result )
      return result;
    v21 = v13 - v17;
    *a2 = (_DWORD *)((char *)*a2 + v21);
    *a3 -= v21;
    v9 = (unsigned int)(v9 + 1);
  }
  v25 = v35;
  while ( v6 < *(_DWORD *)v5 )
  {
    v27 = 32LL * v6;
    v28 = 8LL * v6;
    **(_DWORD **)(v28 + *v25) = *(_DWORD *)(v27 + *(_QWORD *)(v5 + 16));
    v29 = *(_QWORD *)(v5 + 16);
    v30 = *(_QWORD *)(v28 + *v25);
    v31 = *(_QWORD *)(v27 + v29 + 24);
    v36 = *(_OWORD *)(v27 + v29 + 8);
    v37 = v31;
    result = CVaultGenericProperty<enum ECredPropertyId>::SetPropertyValue(v30, &v36);
    if ( (_DWORD)result )
      return result;
    ++v6;
    v25 = (_QWORD *)(v5 + 8);
  }
  *(_DWORD *)(v5 + 24) = 1;
  return 0;
}

```

## disassembly

```asm
0x180005df0  mov     [rsp+arg_0], rcx
0x180005df5  push    rbx
0x180005df6  push    rdi
0x180005df7  push    r14
0x180005df9  push    r15
0x180005dfb  sub     rsp, 78h
0x180005dff  mov     eax, [r8]
0x180005e02  mov     r14, r8
0x180005e05  mov     r15, rdx
0x180005e08  mov     rdi, rcx
0x180005e0b  test    eax, eax
0x180005e0d  jz      loc_1800060FF
0x180005e13  cmp     eax, 4
0x180005e16  jb      loc_180006112
0x180005e1c  mov     rax, [rdx]
0x180005e1f  mov     ebx, [rax]
0x180005e21  add     rax, 4
0x180005e25  mov     [rdx], rax
0x180005e28  add     dword ptr [r8], 0FFFFFFFCh
0x180005e2c  mov     [rsp+98h+arg_18], ebx
0x180005e33  cmp     ebx, 100h
0x180005e39  ja      loc_18000611C
0x180005e3f  cmp     ebx, 5
0x180005e42  jb      loc_180006108
0x180005e48  mov     ecx, ebx
0x180005e4a  mov     rax, rdi
0x180005e4d  mov     [rax], ecx
0x180005e4f  mov     rcx, rdi
0x180005e52  call    ?CreateProperties@?$CVaultGenericPropertyCollection@W4EVaultPropertyId@@$0A@@@AEAAKXZ; CVaultGenericPropertyCollection<EVaultPropertyId,0>::CreateProperties(void)
0x180005e57  test    eax, eax
0x180005e59  jnz     loc_18000603A
0x180005e5f  mov     [rsp+98h+arg_8], rbp
0x180005e67  lea     r9, __ImageBase
0x180005e6e  mov     [rsp+98h+var_28], rsi
0x180005e73  xor     r8d, r8d
0x180005e76  lea     rsi, [rdi+8]
0x180005e7a  mov     [rsp+98h+var_30], r12
0x180005e7f  mov     [rsp+98h+var_60], rsi
0x180005e84  mov     [rsp+98h+var_38], r13
0x180005e89  mov     [rsp+98h+var_78], r8d
0x180005e8e  cmp     r8d, ebx
0x180005e91  jnb     loc_18000600D
0x180005e97  cmp     dword ptr [r14], 4
0x180005e9b  jb      loc_180006202
0x180005ea1  mov     rax, [rdi+8]
0x180005ea5  lea     r11, [rdi+8]
0x180005ea9  mov     [rsp+98h+var_60], r11
0x180005eae  mov     rsi, [rax+r8*8]
0x180005eb2  mov     rax, [r15]
0x180005eb5  mov     [rsp+98h+var_68], rsi
0x180005eba  mov     ecx, [rax]
0x180005ebc  mov     [rsi], ecx
0x180005ebe  add     qword ptr [r15], 4
0x180005ec2  add     dword ptr [r14], 0FFFFFFFCh
0x180005ec6  mov     r13d, [r14]
0x180005ec9  mov     rcx, [r15]
0x180005ecc  cmp     r13d, 4
0x180005ed0  jb      loc_180006202
0x180005ed6  movsxd  rax, dword ptr [rcx]
0x180005ed9  lea     rdx, [rcx+4]
0x180005edd  mov     [rsi+8], eax
0x180005ee0  lea     r12d, [r13-4]
0x180005ee4  mov     [rsp+98h+var_70], rdx
0x180005ee9  mov     [rsp+98h+Source2], r12d
0x180005ef1  cmp     eax, 7
0x180005ef4  jz      loc_180005FA0
0x180005efa  cmp     eax, 8
0x180005efd  jnz     loc_1800060A3
0x180005f03  xorps   xmm0, xmm0; jumptable 00000001800060B7 case 10
0x180005f06  movups  xmmword ptr [rsi+10h], xmm0
0x180005f0a  cmp     r12d, 4
0x180005f0e  jb      loc_1800061B7
0x180005f14  mov     eax, [rdx]
0x180005f16  lea     ebx, [r12-4]
0x180005f1b  mov     [rsi+10h], eax
0x180005f1e  lea     rdi, [rdx+4]
0x180005f22  mov     [rsp+98h+var_70], rdi
0x180005f27  mov     r12d, ebx
0x180005f2a  cmp     eax, ebx
0x180005f2c  ja      loc_1800061C1
0x180005f32  test    eax, eax
0x180005f34  jz      loc_1800060DF
0x180005f3a  mov     edx, eax; uBytes
0x180005f3c  mov     ecx, 40h ; '@'; uFlags
0x180005f41  call    cs:__imp_LocalAlloc
0x180005f47  mov     [rsi+18h], rax
0x180005f4b  test    rax, rax
0x180005f4e  jz      loc_1800061DA
0x180005f54  mov     r8d, [rsi+10h]; Size
0x180005f58  mov     rdx, rdi; Src
0x180005f5b  mov     rcx, rax; void *
0x180005f5e  call    memcpy_0
0x180005f63  sub     r12d, [rsi+10h]
0x180005f67  xor     eax, eax
0x180005f69  mov     rdi, [rsp+98h+arg_0]
0x180005f71  mov     ebx, [rsp+98h+arg_18]
0x180005f78  mov     r8d, [rsp+98h+var_78]
0x180005f7d  lea     r9, __ImageBase
0x180005f84  test    eax, eax
0x180005f86  jnz     loc_180006023
0x180005f8c  sub     r13d, r12d
0x180005f8f  mov     eax, r13d
0x180005f92  add     [r15], rax
0x180005f95  sub     [r14], eax
0x180005f98  inc     r8d
0x180005f9b  jmp     loc_180005E89
0x180005fa0  xor     eax, eax
0x180005fa2  mov     word ptr [rsp+98h+Source2], ax
0x180005faa  cmp     r12d, 4
0x180005fae  jb      loc_1800061E4
0x180005fb4  mov     esi, [rdx]
0x180005fb6  lea     eax, [r12-4]
0x180005fbb  lea     rbp, [rdx+4]
0x180005fbf  mov     r12d, eax
0x180005fc2  cmp     esi, 2
0x180005fc5  jb      loc_18000608F
0x180005fcb  cmp     esi, eax
0x180005fcd  ja      loc_1800061EE
0x180005fd3  test    sil, 1
0x180005fd7  jnz     loc_1800060F5
0x180005fdd  xor     ebx, ebx
0x180005fdf  nop
0x180005fe0  cmp     ebx, esi
0x180005fe2  jnb     loc_180006085
0x180005fe8  lea     rcx, [rbx+rbp]; Source1
0x180005fec  mov     edi, ebx
0x180005fee  mov     r8d, 2; Length
0x180005ff4  lea     rdx, [rsp+98h+Source2]; Source2
0x180005ffc  call    cs:__imp_RtlCompareMemory
0x180006002  cmp     rax, 2
0x180006006  jz      short loc_180006045
0x180006008  add     ebx, 2
0x18000600b  jmp     short loc_180005FE0
0x18000600d  mov     r11, [rsp+98h+var_60]
0x180006012  cmp     ebx, [rdi]
0x180006014  jb      loc_18000620C
0x18000601a  mov     dword ptr [rdi+18h], 1
0x180006021  xor     eax, eax
0x180006023  mov     r12, [rsp+98h+var_30]
0x180006028  mov     r13, [rsp+98h+var_38]
0x18000602d  mov     rbp, [rsp+98h+arg_8]
0x180006035  mov     rsi, [rsp+98h+var_28]
0x18000603a  add     rsp, 78h
0x18000603e  pop     r15
0x180006040  pop     r14
0x180006042  pop     rdi
0x180006043  pop     rbx
0x180006044  retn
0x180006045  lea     rax, [rsi-2]
0x180006049  mov     rbx, rsi
0x18000604c  cmp     rdi, rax
0x18000604f  jnz     short loc_180006085
0x180006051  mov     rdx, rbx; uBytes
0x180006054  mov     ecx, 40h ; '@'; uFlags
0x180006059  call    cs:__imp_LocalAlloc
0x18000605f  mov     rcx, [rsp+98h+var_68]
0x180006064  mov     [rcx+10h], rax
0x180006068  test    rax, rax
0x18000606b  jz      short loc_1800060D5
0x18000606d  mov     r8, rbx; Size
0x180006070  mov     rdx, rbp; Src
0x180006073  mov     rcx, rax; void *
0x180006076  call    memcpy_0
0x18000607b  sub     r12d, esi
0x18000607e  xor     eax, eax
0x180006080  jmp     loc_180005F69
0x180006085  mov     eax, 54Eh
0x18000608a  jmp     loc_180005F69
0x18000608f  mov     rcx, [rsp+98h+var_68]
0x180006094  xor     eax, eax
0x180006096  mov     qword ptr [rcx+10h], 0
0x18000609e  jmp     loc_180005F84
0x1800060a3  cmp     eax, 0Bh; switch 12 cases
0x1800060a6  ja      def_1800060B7; jumptable 00000001800060B7 default case, cases 7-9,11
0x1800060ac  mov     ecx, ds:(jpt_1800060B7 - 180000000h)[r9+rax*4]
0x1800060b4  add     rcx, r9
0x1800060b7  jmp     rcx; switch jump
0x1800060b9  cmp     r12d, 10h; jumptable 00000001800060B7 case 6
0x1800060bd  jb      loc_1800061AD
0x1800060c3  movups  xmm0, xmmword ptr [rdx]
0x1800060c6  add     r12d, 0FFFFFFF0h
0x1800060ca  xor     eax, eax
0x1800060cc  movups  xmmword ptr [rsi+10h], xmm0
0x1800060d0  jmp     loc_180005F84
0x1800060d5  mov     eax, 0Eh
0x1800060da  jmp     loc_180005F69
0x1800060df  mov     ebx, [rsp+98h+arg_18]
0x1800060e6  xor     eax, eax
0x1800060e8  mov     rdi, [rsp+98h+arg_0]
0x1800060f0  jmp     loc_180005F84
0x1800060f5  mov     eax, 54Eh
0x1800060fa  jmp     loc_180005F84
0x1800060ff  xor     ebx, ebx
0x180006101  mov     [rsp+98h+arg_18], ebx
0x180006108  mov     ecx, 5
0x18000610d  jmp     loc_180005E4A
0x180006112  mov     eax, 7Ah ; 'z'
0x180006117  jmp     loc_18000603A
0x18000611c  mov     eax, 57h ; 'W'
0x180006121  jmp     loc_18000603A
0x180006126  cmp     r12d, 2; jumptable 00000001800060B7 cases 1,2
0x18000612a  jnb     short loc_180006136
0x18000612c  mov     eax, 7Ah ; 'z'
0x180006131  jmp     loc_180005F84
0x180006136  movzx   eax, word ptr [rdx]
0x180006139  add     r12d, 0FFFFFFFEh
0x18000613d  mov     [rsi+10h], ax
0x180006141  xor     eax, eax
0x180006143  jmp     loc_180005F84
0x180006148  cmp     r12d, 4; jumptable 00000001800060B7 cases 3,4
0x18000614c  jnb     short loc_180006158
0x18000614e  mov     eax, 7Ah ; 'z'
0x180006153  jmp     loc_180005F84
0x180006158  mov     eax, [rdx]
0x18000615a  add     r12d, 0FFFFFFFCh
0x18000615e  mov     [rsi+10h], eax
0x180006161  xor     eax, eax
0x180006163  jmp     loc_180005F84
0x180006168  cmp     r12d, 8; jumptable 00000001800060B7 case 5
0x18000616c  jnb     short loc_180006178
0x18000616e  mov     eax, 7Ah ; 'z'
0x180006173  jmp     loc_180005F84
0x180006178  mov     rax, [rdx]
0x18000617b  add     r12d, 0FFFFFFF8h
0x18000617f  mov     [rsi+10h], rax
0x180006183  xor     eax, eax
0x180006185  jmp     loc_180005F84
0x18000618a  lea     r8, [rsi+10h]; jumptable 00000001800060B7 case 0
0x18000618e  lea     rdx, [rsp+98h+Source2]
0x180006196  lea     rcx, [rsp+98h+var_70]
0x18000619b  call    ??$VaultDeserialize@E@@YAKAEAPEAEAEAKAEAE@Z; VaultDeserialize<uchar>(uchar * &,ulong &,uchar &)
0x1800061a0  mov     r12d, [rsp+98h+Source2]
0x1800061a8  jmp     loc_180005F78
0x1800061ad  mov     eax, 7Ah ; 'z'
0x1800061b2  jmp     loc_180005F84
0x1800061b7  mov     eax, 7Ah ; 'z'
0x1800061bc  jmp     loc_180005F84
0x1800061c1  mov     ebx, [rsp+98h+arg_18]
0x1800061c8  mov     eax, 7Ah ; 'z'
0x1800061cd  mov     rdi, [rsp+98h+arg_0]
0x1800061d5  jmp     loc_180005F84
0x1800061da  mov     eax, 0Eh
0x1800061df  jmp     loc_180005F69
0x1800061e4  mov     eax, 7Ah ; 'z'
0x1800061e9  jmp     loc_180005F84
0x1800061ee  mov     eax, 7Ah ; 'z'
0x1800061f3  jmp     loc_180005F84
0x1800061f8  mov     eax, 57h ; 'W'; jumptable 00000001800060B7 default case, cases 7-9,11
0x1800061fd  jmp     loc_180006023
0x180006202  mov     eax, 7Ah ; 'z'
0x180006207  jmp     loc_180006023
0x18000620c  mov     r8, [rdi+10h]
0x180006210  mov     eax, ebx
0x180006212  mov     r9d, ebx
0x180006215  shl     r9, 5
0x180006219  lea     r10, ds:0[rax*8]
0x180006221  mov     rax, [r11]
0x180006224  mov     rdx, [r10+rax]
0x180006228  mov     eax, [r9+r8]
0x18000622c  mov     [rdx], eax
0x18000622e  lea     rdx, [rsp+98h+var_58]
0x180006233  mov     rax, [rdi+10h]
0x180006237  mov     rcx, [r11]
0x18000623a  movups  xmm0, xmmword ptr [r9+rax+8]
0x180006240  mov     rcx, [r10+rcx]
0x180006244  movsd   xmm1, qword ptr [r9+rax+18h]
0x18000624b  movaps  [rsp+98h+var_58], xmm0
0x180006250  movsd   [rsp+98h+var_48], xmm1
0x180006256  call    ?SetPropertyValue@?$CVaultGenericProperty@W4ECredPropertyId@@@@QEAAKU_VAULT_VARIANT@@@Z; CVaultGenericProperty<ECredPropertyId>::SetPropertyValue(_VAULT_VARIANT)
0x18000625b  test    eax, eax
0x18000625d  jnz     loc_180006023
0x180006263  inc     ebx
0x180006265  lea     r11, [rdi+8]
0x180006269  jmp     loc_180006012
```
