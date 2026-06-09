# ParseUSBInterfaceAssociationDescriptors

- ea: `0x14000fb68`
- end: `0x14001039d`
- name: `ParseUSBInterfaceAssociationDescriptors`
- size: `2101`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14002aec4`

## callees

- `0x1400088b4`
- `0x14000c2bc`
- `0x14000d568`
- `0x14000e994`
- `0x14000f664`
- `0x14000fb68`
- `0x140013774`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000fc83`
- `ntoskrnl!ExAllocatePool2` at `0x14000fc83`

## pseudocode

```c
__int64 __fastcall ParseUSBInterfaceAssociationDescriptors(__int64 a1, _QWORD *a2, int *a3)
{
  unsigned __int8 *v3; // rbx
  char v4; // r11
  unsigned __int8 *v6; // rcx
  unsigned __int8 v7; // r10
  unsigned __int64 v8; // r13
  char v9; // r14
  unsigned __int8 v10; // r9
  __int64 v11; // rax
  int v12; // esi
  unsigned __int8 v13; // r14
  int v14; // edx
  int v15; // r9d
  int v16; // edx
  int v17; // ecx
  unsigned __int8 v18; // bp
  unsigned __int8 v19; // r12
  unsigned __int8 v20; // r15
  int v21; // edx
  int v22; // edx
  unsigned __int8 *v23; // r8
  char *v24; // r13
  int v25; // edx
  unsigned __int8 *v26; // r9
  unsigned __int8 v27; // dl
  __int64 v28; // r9
  __int64 v29; // rdx
  unsigned __int8 *i; // rcx
  unsigned __int8 v31; // al
  char *v32; // r13
  int v33; // edx
  __int64 v34; // rax
  int v35; // ecx
  int v36; // edx
  int v37; // ecx
  int v39; // [rsp+20h] [rbp-78h]
  void *Src; // [rsp+28h] [rbp-70h]
  size_t Size; // [rsp+30h] [rbp-68h]
  unsigned __int64 v42; // [rsp+40h] [rbp-58h]
  unsigned __int8 *v43; // [rsp+48h] [rbp-50h]
  int v44; // [rsp+A0h] [rbp+8h]
  _QWORD *v45; // [rsp+A8h] [rbp+10h]
  char *P; // [rsp+B8h] [rbp+20h]

  v45 = a2;
  v3 = *(unsigned __int8 **)(a1 + 56);
  v4 = 0;
  P = 0;
  v6 = v3;
  v7 = v3[4];
  v8 = (unsigned __int64)&v3[*((unsigned __int16 *)v3 + 1)];
  v42 = v8;
  v9 = 0;
  v10 = v7;
  while ( (unsigned __int64)v6 < v8 )
  {
    if ( v6[1] == 11 )
    {
      LODWORD(a2) = v6[3];
      if ( (unsigned __int8)a2 > v10 )
      {
        v12 = -1073741668;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_dd(
            *(_QWORD *)(a1 + 1368),
            (_DWORD)a2,
            8,
            33,
            (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
            v6[3],
            v10);
        }
        LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
        Src = *(void **)(a1 + 48);
        v39 = 1229014065;
        goto LABEL_105;
      }
      ++v9;
      v4 = 1;
      v10 -= (unsigned __int8)a2;
    }
    v11 = *v6;
    if ( !(_BYTE)v11 )
      break;
    v6 += v11;
  }
  v12 = 0;
  v13 = v10 + v9;
  if ( !v4 )
    goto LABEL_107;
  if ( v13 > v7 || !v13 || v10 > v7 )
  {
    v12 = -1073741668;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(a1 + 1368),
        (_DWORD)a2,
        8,
        34,
        (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
    }
    LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
    Src = *(void **)(a1 + 48);
    v39 = 1229014066;
LABEL_105:
    v15 = -1610612729;
    v16 = -1073741668;
    goto LABEL_106;
  }
  P = (char *)ExAllocatePool2(64, 88LL * v13, 1130525525);
  if ( P )
  {
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v44 = 0;
    v20 = 0;
    v21 = 1;
    while ( (unsigned __int64)v3 < v8 )
    {
      if ( v3[1] == 11 )
      {
        if ( !(unsigned __int8)ValidateUSBInterfaceAssociationDescriptor(v3, a1) )
        {
          v12 = -1073741668;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v22) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(a1 + 1368),
              v22,
              8,
              36,
              (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
          }
          LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
          Src = *(void **)(a1 + 48);
          v39 = 1229014067;
          goto LABEL_105;
        }
        if ( v13 >= v18 && v20 >= v13 - v18 )
        {
          v12 = -1073741668;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v22) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(a1 + 1368),
              v22,
              8,
              37,
              (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
          }
          LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
          Src = *(void **)(a1 + 48);
          v39 = 1229014068;
          goto LABEL_105;
        }
        if ( v19 )
        {
          v12 = -1073741668;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v22) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(a1 + 1368),
              v22,
              8,
              39,
              (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
          }
          LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
          Src = *(void **)(a1 + 48);
          v39 = 1229014069;
          goto LABEL_105;
        }
        if ( *(_BYTE *)(a1 + 1364) && v3[4] == 1 && !v3[6] )
        {
          ++v18;
          v23 = v3 + 2;
        }
        else
        {
          v24 = &P[88 * v20];
          v12 = InitializeFunctionAssoc(a1, v24, v3[2], v3[3]);
          if ( v12 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v25) = 2;
              WPP_RECORDER_SF_(
                *(_QWORD *)(a1 + 1368),
                v25,
                8,
                40,
                (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
            }
            LODWORD(Size) = 0;
            Src = 0;
            v39 = 1346978098;
            goto LABEL_19;
          }
          v23 = v3 + 2;
          v24[4] = ++v20;
          *((_QWORD *)v24 + 2) = v3;
          v8 = v42;
        }
        v17 = *v23;
        v19 = v3[3];
        v44 = v17;
        v21 = 1;
      }
      else
      {
        v23 = v3 + 2;
      }
      v26 = v3;
      v43 = v3;
      if ( v3[1] == 4 )
      {
        if ( v19 )
        {
          if ( !v3[3] )
          {
            if ( *v23 != (_WORD)v17 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v21) = 2;
                WPP_RECORDER_SF_(
                  *(_QWORD *)(a1 + 1368),
                  v21,
                  8,
                  41,
                  (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
              }
              LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
              RecordStartFailData(a1, v12, 0, -1610612729, 1229014070, *(void **)(a1 + 48), Size);
              v12 = -1073741668;
              goto LABEL_107;
            }
            LOWORD(v17) = v17 + 1;
            v44 = v17;
            --v19;
          }
        }
        else if ( !v3[3] )
        {
          v27 = v3[5];
          if ( v27 == 13 || *(_BYTE *)(a1 + 1364) && v27 == 1 && !v3[7] )
          {
            ++v18;
            v21 = 1;
          }
          else
          {
            if ( v13 >= v18 && v20 >= v13 - v18 )
            {
              v12 = -1073741668;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v21) = 2;
                WPP_RECORDER_SF_(
                  *(_QWORD *)(a1 + 1368),
                  v21,
                  8,
                  42,
                  (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
              }
              LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
              Src = *(void **)(a1 + 48);
              v39 = 1229014071;
              goto LABEL_105;
            }
            v28 = 1;
            if ( v27 == 1 && v3[6] == 1 && !v3[7] )
            {
              v29 = *v3;
              for ( i = &v3[v29]; (unsigned __int64)(i + 2) < v8; i += *i )
              {
                v31 = i[1];
                if ( v31 == 11 || v31 == 4 && (unsigned __int64)(i + 9) < v8 && !i[3] )
                  break;
              }
              if ( (unsigned __int64)(i + 9) < v8 && i[1] == 4 && i[5] == 1 && i[6] == 3 && !i[7] && !i[3] )
              {
                v28 = 2;
                ++v18;
                v3 = &i[*i - v29];
              }
            }
            v32 = &P[88 * v20];
            v12 = InitializeFunctionAssoc(a1, v32, *v23, v28);
            if ( v12 < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v33) = 2;
                WPP_RECORDER_SF_(
                  *(_QWORD *)(a1 + 1368),
                  v33,
                  8,
                  44,
                  (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
              }
              LODWORD(Size) = 0;
              Src = 0;
              v39 = 1346978099;
              goto LABEL_19;
            }
            v26 = v43;
            v21 = 1;
            v32[4] = ++v20;
          }
        }
      }
      v34 = *v26;
      if ( !(_BYTE)v34 )
        break;
      v8 = v42;
      v3 += v34;
      v17 = v44;
    }
    if ( v19 )
    {
      v12 = -1073741668;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v21, 8, 45, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
      }
      LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
      Src = *(void **)(a1 + 48);
      v39 = 1229014072;
    }
    else
    {
      v35 = v13 - v18;
      v36 = v20;
      if ( v20 == v35 )
      {
        if ( v13 <= v18 )
          v37 = 0;
        else
          v37 = v13 - v18;
        *a3 = v37;
        *v45 = P;
        return (unsigned int)v12;
      }
      v12 = -1073741668;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v36) = 2;
        WPP_RECORDER_SF_dd(
          *(_QWORD *)(a1 + 1368),
          v36,
          8,
          46,
          (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
          v35,
          v20);
      }
      LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
      Src = *(void **)(a1 + 48);
      v39 = 1229014073;
    }
    goto LABEL_105;
  }
  v12 = -1073741670;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v14, 8, 35, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
  }
  LODWORD(Size) = 0;
  Src = 0;
  v39 = 1346978097;
LABEL_19:
  v15 = -1610612731;
  v16 = v12;
LABEL_106:
  RecordStartFailData(a1, v16, 0, v15, v39, Src, Size);
LABEL_107:
  *a3 = 0;
  *v45 = 0;
  if ( P )
    CleanFunctionList(P);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000fb68  mov     [rsp+arg_10], r8
0x14000fb6d  mov     [rsp+arg_8], rdx
0x14000fb72  push    rbx
0x14000fb73  push    rbp
0x14000fb74  push    rsi
0x14000fb75  push    rdi
0x14000fb76  push    r12
0x14000fb78  push    r13
0x14000fb7a  push    r14
0x14000fb7c  push    r15
0x14000fb7e  sub     rsp, 58h
0x14000fb82  mov     rbx, [rcx+38h]
0x14000fb86  xor     r11b, r11b
0x14000fb89  mov     rdi, rcx
0x14000fb8c  mov     [rsp+98h+P], 0
0x14000fb98  mov     rcx, rbx
0x14000fb9b  movzx   r13d, word ptr [rbx+2]
0x14000fba0  mov     r10b, [rbx+4]
0x14000fba4  add     r13, rbx
0x14000fba7  mov     [rsp+98h+var_58], r13
0x14000fbac  xor     r14b, r14b
0x14000fbaf  mov     r9b, r10b
0x14000fbb2  mov     eax, 1
0x14000fbb7  cmp     rcx, r13
0x14000fbba  jnb     loc_14000FC49
0x14000fbc0  cmp     byte ptr [rcx+1], 0Bh
0x14000fbc4  jnz     short loc_14000FBD8
0x14000fbc6  movzx   edx, byte ptr [rcx+3]
0x14000fbca  cmp     dl, r9b
0x14000fbcd  ja      short loc_14000FBE4
0x14000fbcf  add     r14b, al
0x14000fbd2  mov     r11b, al
0x14000fbd5  sub     r9b, dl
0x14000fbd8  movzx   eax, byte ptr [rcx]
0x14000fbdb  test    al, al
0x14000fbdd  jz      short loc_14000FC49
0x14000fbdf  add     rcx, rax
0x14000fbe2  jmp     short loc_14000FBB2
0x14000fbe4  mov     ebx, 0C000009Ch
0x14000fbe9  mov     esi, ebx
0x14000fbeb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000fbf2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000fbf9  jz      short loc_14000FC2B
0x14000fbfb  mov     rcx, [rdi+558h]
0x14000fc02  movzx   eax, r9b
0x14000fc06  mov     r9d, 21h ; '!'
0x14000fc0c  mov     dword ptr [rsp+98h+Size], eax
0x14000fc10  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000fc17  mov     dword ptr [rsp+98h+Src], edx
0x14000fc1b  mov     dl, 2
0x14000fc1d  mov     qword ptr [rsp+98h+var_78], rax
0x14000fc22  lea     r8d, [r9-19h]
0x14000fc26  call    WPP_RECORDER_SF_dd
0x14000fc2b  mov     rcx, [rdi+30h]
0x14000fc2f  movzx   eax, word ptr [rcx+2]
0x14000fc33  mov     dword ptr [rsp+98h+Size], eax
0x14000fc37  mov     [rsp+98h+Src], rcx
0x14000fc3c  mov     [rsp+98h+var_78], 49414431h
0x14000fc44  jmp     loc_140010340
0x14000fc49  xor     esi, esi
0x14000fc4b  add     r14b, r9b
0x14000fc4e  test    r11b, r11b
0x14000fc51  jz      loc_140010353
0x14000fc57  cmp     r14b, r10b
0x14000fc5a  ja      loc_1400102EC
0x14000fc60  test    r14b, r14b
0x14000fc63  jz      loc_1400102EC
0x14000fc69  cmp     r9b, r10b
0x14000fc6c  ja      loc_1400102EC
0x14000fc72  movzx   eax, r14b
0x14000fc76  lea     ecx, [rsi+40h]
0x14000fc79  imul    rdx, rax, 58h ; 'X'
0x14000fc7d  mov     r8d, 43627355h
0x14000fc83  call    cs:__imp_ExAllocatePool2
0x14000fc8a  nop     dword ptr [rax+rax+00h]
0x14000fc8f  mov     [rsp+98h+P], rax
0x14000fc97  test    rax, rax
0x14000fc9a  jnz     short loc_14000FCFB
0x14000fc9c  mov     esi, 0C000009Ah
0x14000fca1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000fca8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000fcaf  jz      short loc_14000FCD5
0x14000fcb1  mov     rcx, [rdi+558h]
0x14000fcb8  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000fcbf  mov     r9d, 23h ; '#'
0x14000fcc5  mov     qword ptr [rsp+98h+var_78], rax
0x14000fcca  mov     dl, 2
0x14000fccc  lea     r8d, [r9-1Bh]
0x14000fcd0  call    WPP_RECORDER_SF_
0x14000fcd5  mov     dword ptr [rsp+98h+Size], 0
0x14000fcdd  mov     [rsp+98h+Src], 0
0x14000fce6  mov     [rsp+98h+var_78], 50494131h
0x14000fcee  mov     r9d, 0A0000005h
0x14000fcf4  mov     edx, esi
0x14000fcf6  jmp     loc_140010348
0x14000fcfb  xor     ecx, ecx
0x14000fcfd  xor     bpl, bpl
0x14000fd00  xor     r12b, r12b
0x14000fd03  mov     dword ptr [rsp+98h+arg_0], ecx
0x14000fd0a  xor     r10d, r10d
0x14000fd0d  mov     r15b, r10b
0x14000fd10  lea     edx, [rcx+1]
0x14000fd13  cmp     rbx, r13
0x14000fd16  jnb     loc_1400101D6
0x14000fd1c  cmp     byte ptr [rbx+1], 0Bh
0x14000fd20  jnz     loc_14000FDEB
0x14000fd26  mov     rdx, rdi
0x14000fd29  mov     rcx, rbx
0x14000fd2c  call    ValidateUSBInterfaceAssociationDescriptor
0x14000fd31  test    al, al
0x14000fd33  jz      loc_140010068
0x14000fd39  cmp     r14b, bpl
0x14000fd3c  jb      short loc_14000FD54
0x14000fd3e  movzx   eax, bpl
0x14000fd42  movzx   ecx, r14b
0x14000fd46  sub     ecx, eax
0x14000fd48  movzx   eax, r15b
0x14000fd4c  cmp     eax, ecx
0x14000fd4e  jge     loc_14000FF64
0x14000fd54  test    r12b, r12b
0x14000fd57  jnz     loc_14001000F
0x14000fd5d  cmp     byte ptr [rdi+554h], 0
0x14000fd64  mov     r12d, 1
0x14000fd6a  jz      short loc_14000FD81
0x14000fd6c  cmp     [rbx+4], r12b
0x14000fd70  jnz     short loc_14000FD81
0x14000fd72  cmp     byte ptr [rbx+6], 0
0x14000fd76  jnz     short loc_14000FD81
0x14000fd78  add     bpl, r12b
0x14000fd7b  lea     r8, [rbx+2]
0x14000fd7f  jmp     short loc_14000FDD3
0x14000fd81  movzx   r9d, byte ptr [rbx+3]
0x14000fd86  lea     rdx, [rbx+2]
0x14000fd8a  movzx   r8d, byte ptr [rdx]
0x14000fd8e  mov     rcx, rdi
0x14000fd91  movzx   eax, r15b
0x14000fd95  imul    r13, rax, 58h ; 'X'
0x14000fd99  mov     [rsp+98h+arg_0], rdx
0x14000fda1  add     r13, [rsp+98h+P]
0x14000fda9  mov     rdx, r13
0x14000fdac  call    InitializeFunctionAssoc
0x14000fdb1  mov     esi, eax
0x14000fdb3  test    eax, eax
0x14000fdb5  js      loc_14000FFBD
0x14000fdbb  mov     r8, [rsp+98h+arg_0]
0x14000fdc3  add     r15b, r12b
0x14000fdc6  mov     [r13+4], r15b
0x14000fdca  mov     [r13+10h], rbx
0x14000fdce  mov     r13, [rsp+98h+var_58]
0x14000fdd3  movzx   ecx, byte ptr [r8]
0x14000fdd7  xor     r10d, r10d
0x14000fdda  mov     r12b, [rbx+3]
0x14000fdde  mov     dword ptr [rsp+98h+arg_0], ecx
0x14000fde5  lea     edx, [r10+1]
0x14000fde9  jmp     short loc_14000FDEF
0x14000fdeb  lea     r8, [rbx+2]
0x14000fdef  cmp     byte ptr [rbx+1], 4
0x14000fdf3  mov     r9, rbx
0x14000fdf6  mov     [rsp+98h+var_50], rbx
0x14000fdfb  jnz     loc_14000FF44
0x14000fe01  test    r12b, r12b
0x14000fe04  jz      short loc_14000FE30
0x14000fe06  cmp     [rbx+3], r10b
0x14000fe0a  jnz     loc_14000FF44
0x14000fe10  movzx   eax, byte ptr [r8]
0x14000fe14  cmp     ax, cx
0x14000fe17  jnz     loc_1400100C1
0x14000fe1d  add     cx, dx
0x14000fe20  mov     dword ptr [rsp+98h+arg_0], ecx
0x14000fe27  add     r12b, 0FFh
0x14000fe2b  jmp     loc_14000FF44
0x14000fe30  cmp     [rbx+3], r10b
0x14000fe34  jnz     loc_14000FF44
0x14000fe3a  mov     dl, [rbx+5]
0x14000fe3d  mov     r11d, 1
0x14000fe43  cmp     dl, 0Dh
0x14000fe46  jz      loc_14000FF3C
0x14000fe4c  cmp     [rdi+554h], r10b
0x14000fe53  jz      short loc_14000FE64
0x14000fe55  cmp     dl, r11b
0x14000fe58  jnz     short loc_14000FE64
0x14000fe5a  cmp     [rbx+7], r10b
0x14000fe5e  jz      loc_14000FF3C
0x14000fe64  cmp     r14b, bpl
0x14000fe67  jb      short loc_14000FE7F
0x14000fe69  movzx   eax, bpl
0x14000fe6d  movzx   ecx, r14b
0x14000fe71  sub     ecx, eax
0x14000fe73  movzx   eax, r15b
0x14000fe77  cmp     eax, ecx
0x14000fe79  jge     loc_14001012B
0x14000fe7f  mov     r9d, r11d
0x14000fe82  cmp     dl, r11b
0x14000fe85  jnz     short loc_14000FEFE
0x14000fe87  cmp     [rbx+6], r11b
0x14000fe8b  jnz     short loc_14000FEFE
0x14000fe8d  cmp     [rbx+7], r10b
0x14000fe91  jnz     short loc_14000FEFE
0x14000fe93  movzx   edx, byte ptr [rbx]
0x14000fe96  lea     rcx, [rdx+rbx]
0x14000fe9a  jmp     short loc_14000FEBC
0x14000fe9c  mov     al, [rcx+1]
0x14000fe9f  cmp     al, 0Bh
0x14000fea1  jz      short loc_14000FEC5
0x14000fea3  cmp     al, 4
0x14000fea5  jnz     short loc_14000FEB6
0x14000fea7  lea     rax, [rcx+9]
0x14000feab  cmp     rax, r13
0x14000feae  jnb     short loc_14000FEB6
0x14000feb0  cmp     [rcx+3], r10b
0x14000feb4  jz      short loc_14000FEC5
0x14000feb6  movzx   eax, byte ptr [rcx]
0x14000feb9  add     rcx, rax
0x14000febc  lea     rax, [rcx+2]
0x14000fec0  cmp     rax, r13
0x14000fec3  jb      short loc_14000FE9C
0x14000fec5  lea     rax, [rcx+9]
0x14000fec9  cmp     rax, r13
0x14000fecc  jnb     short loc_14000FEFE
0x14000fece  cmp     byte ptr [rcx+1], 4
0x14000fed2  jnz     short loc_14000FEFE
0x14000fed4  cmp     [rcx+5], r11b
0x14000fed8  jnz     short loc_14000FEFE
0x14000feda  cmp     byte ptr [rcx+6], 3
0x14000fede  jnz     short loc_14000FEFE
0x14000fee0  cmp     [rcx+7], r10b
0x14000fee4  jnz     short loc_14000FEFE
0x14000fee6  cmp     [rcx+3], r10b
0x14000feea  jnz     short loc_14000FEFE
0x14000feec  mov     r9d, 2
0x14000fef2  movzx   ebx, byte ptr [rcx]
0x14000fef5  add     bpl, r11b
0x14000fef8  sub     rbx, rdx
0x14000fefb  add     rbx, rcx
0x14000fefe  movzx   r8d, byte ptr [r8]
0x14000ff02  mov     rcx, rdi
0x14000ff05  movzx   eax, r15b
0x14000ff09  imul    r13, rax, 58h ; 'X'
0x14000ff0d  add     r13, [rsp+98h+P]
0x14000ff15  mov     rdx, r13
0x14000ff18  call    InitializeFunctionAssoc
0x14000ff1d  xor     r10d, r10d
0x14000ff20  mov     esi, eax
0x14000ff22  test    eax, eax
0x14000ff24  js      loc_140010184
0x14000ff2a  mov     r9, [rsp+98h+var_50]
0x14000ff2f  lea     edx, [r10+1]
0x14000ff33  add     r15b, dl
0x14000ff36  mov     [r13+4], r15b
0x14000ff3a  jmp     short loc_14000FF44
0x14000ff3c  add     bpl, r11b
0x14000ff3f  mov     edx, 1
0x14000ff44  movzx   eax, byte ptr [r9]
0x14000ff48  test    al, al
0x14000ff4a  jz      loc_1400101D6
0x14000ff50  mov     r13, [rsp+98h+var_58]
0x14000ff55  add     rbx, rax
0x14000ff58  mov     ecx, dword ptr [rsp+98h+arg_0]
0x14000ff5f  jmp     loc_14000FD13
0x14000ff64  mov     ebx, 0C000009Ch
0x14000ff69  mov     esi, ebx
0x14000ff6b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ff72  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ff79  jz      short loc_14000FF9F
0x14000ff7b  mov     rcx, [rdi+558h]
0x14000ff82  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000ff89  mov     r9d, 25h ; '%'
0x14000ff8f  mov     qword ptr [rsp+98h+var_78], rax
0x14000ff94  mov     dl, 2
0x14000ff96  lea     r8d, [r9-1Dh]
0x14000ff9a  call    WPP_RECORDER_SF_
0x14000ff9f  mov     rcx, [rdi+30h]
0x14000ffa3  movzx   eax, word ptr [rcx+2]
0x14000ffa7  mov     dword ptr [rsp+98h+Size], eax
0x14000ffab  mov     [rsp+98h+Src], rcx
0x14000ffb0  mov     [rsp+98h+var_78], 49414434h
0x14000ffb8  jmp     loc_140010340
0x14000ffbd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ffc4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ffcb  jz      short loc_14000FFF1
0x14000ffcd  mov     rcx, [rdi+558h]
0x14000ffd4  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000ffdb  mov     r9d, 28h ; '('
0x14000ffe1  mov     qword ptr [rsp+98h+var_78], rax
0x14000ffe6  mov     dl, 2
0x14000ffe8  lea     r8d, [r9-20h]
0x14000ffec  call    WPP_RECORDER_SF_
0x14000fff1  mov     dword ptr [rsp+98h+Size], 0
0x14000fff9  mov     [rsp+98h+Src], 0
0x140010002  mov     [rsp+98h+var_78], 50494132h
0x14001000a  jmp     loc_14000FCEE
0x14001000f  mov     ebx, 0C000009Ch
0x140010014  mov     esi, ebx
0x140010016  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001001d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010024  jz      short loc_14001004A
0x140010026  mov     rcx, [rdi+558h]
0x14001002d  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140010034  mov     r9d, 27h ; '''
0x14001003a  mov     qword ptr [rsp+98h+var_78], rax
  ... truncated ...
```
