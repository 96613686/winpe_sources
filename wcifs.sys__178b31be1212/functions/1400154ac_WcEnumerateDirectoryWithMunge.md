# WcEnumerateDirectoryWithMunge

- ea: `0x1400154ac`
- end: `0x140015a6a`
- name: `WcEnumerateDirectoryWithMunge`
- size: `1470`
- prototype: `__int64 __fastcall(int, int, int, __int64, int, char, int, unsigned int, unsigned int, __int64, char, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, loader_planting`

## callers

- `0x140030ac0`

## callees

- `0x140002048`
- `0x140004198`
- `0x140004d7c`
- `0x14001452c`
- `0x1400154ac`
- `0x140028f74`
- `0x14002b71c`
- `0x14002b77c`
- `0x14002b7d8`
- `0x14002b94c`
- `0x14002ba40`
- `0x14002e994`

## pseudocode

```c
__int64 __fastcall WcEnumerateDirectoryWithMunge(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        char a6,
        int a7,
        unsigned int a8,
        unsigned int a9,
        __int64 a10,
        char a11,
        _DWORD *a12)
{
  int v13; // r10d
  unsigned int v14; // eax
  unsigned int v15; // edi
  int v16; // ebx
  unsigned int v17; // r12d
  unsigned int v18; // r12d
  int v19; // r13d
  int v21; // edx
  int v22; // esi
  int v23; // eax
  __int64 v24; // rdx
  int NextEntryFileName; // eax
  __int64 v26; // rax
  bool v27; // zf
  int EnumEntry; // eax
  int v29; // eax
  unsigned int v30; // eax
  int v31; // eax
  __int64 v32; // rax
  char v34; // [rsp+50h] [rbp-98h]
  char v35; // [rsp+51h] [rbp-97h]
  char v36; // [rsp+5Ch] [rbp-8Ch]
  int v37; // [rsp+60h] [rbp-88h]
  unsigned int v38; // [rsp+64h] [rbp-84h]
  __int64 v39; // [rsp+68h] [rbp-80h]
  int v40; // [rsp+70h] [rbp-78h] BYREF
  int v41; // [rsp+74h] [rbp-74h]
  int v42; // [rsp+78h] [rbp-70h]
  unsigned int v43; // [rsp+7Ch] [rbp-6Ch]
  _QWORD v44[2]; // [rsp+80h] [rbp-68h] BYREF
  int v45; // [rsp+90h] [rbp-58h]
  int v46; // [rsp+94h] [rbp-54h]
  unsigned int *v47; // [rsp+98h] [rbp-50h] BYREF
  unsigned int *v48; // [rsp+A0h] [rbp-48h]
  int v50; // [rsp+F8h] [rbp+10h]

  v50 = a2;
  v13 = a1;
  v40 = 0;
  v47 = 0;
  v44[1] = v44;
  v44[0] = v44;
  if ( a3 > 38 )
  {
    v16 = 60;
    if ( a3 == 60 )
    {
      v14 = 88;
      goto LABEL_31;
    }
    if ( a3 == 63 )
    {
      v14 = 114;
      v16 = 63;
      goto LABEL_31;
    }
    if ( a3 != 78 )
    {
      switch ( a3 )
      {
        case 'O':
          v15 = 106;
          v14 = 106;
          goto LABEL_11;
        case 'P':
          v14 = 96;
          v16 = 80;
          break;
        case 'Q':
          v14 = 122;
          v16 = 81;
          break;
        default:
          goto LABEL_85;
      }
LABEL_31:
      v15 = v14;
      goto LABEL_32;
    }
    goto LABEL_19;
  }
  switch ( a3 )
  {
    case 38:
LABEL_19:
      v14 = 80;
      v15 = 80;
      goto LABEL_15;
    case 1:
      v14 = 64;
      goto LABEL_14;
    case 2:
      v14 = 68;
      goto LABEL_14;
    case 3:
      v14 = 94;
      goto LABEL_10;
    case 12:
      v14 = 12;
LABEL_14:
      v15 = 80;
LABEL_15:
      v16 = 78;
      goto LABEL_32;
    case 33:
      v14 = 16;
      v16 = 33;
      goto LABEL_31;
  }
  if ( a3 != 37 )
  {
LABEL_85:
    v22 = -1073741811;
    goto LABEL_86;
  }
  v14 = 104;
LABEL_10:
  v15 = 106;
LABEL_11:
  v16 = 79;
LABEL_32:
  v17 = v15 + a9;
  if ( v15 + a9 < v15 || v17 < v14 )
    goto LABEL_85;
  v18 = v17 - v14;
  v42 = 256;
  v38 = 0;
  v19 = 0;
  v41 = 0;
  v48 = 0;
  v37 = 0;
  v36 = 1;
  v35 = 1;
  v46 = v16;
  v45 = v16;
  if ( v18 > 0x10000 )
    v18 = 0x10000;
  v43 = v18;
  while ( 1 )
  {
    v34 = a6;
    v22 = WcPrepareEnumerationContexts((unsigned int)v44, v13, a2, 0, v18, v16, a6, 0);
    if ( v22 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = 2;
        WPP_RECORDER_SF_sDdd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v21,
          18,
          26,
          (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
          47,
          a3,
          v22);
      }
      goto LABEL_86;
    }
    v39 = v44[0];
    v23 = WcEnumerateDirectory(
            a1,
            v50,
            v16,
            a4,
            a5,
            v34,
            *(_DWORD *)(v44[0] + 64LL),
            *(_QWORD *)(v44[0] + 72LL),
            v44[0] + 60LL);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v26 = v39;
      if ( !*(_DWORD *)(v39 + 60) )
      {
LABEL_53:
        *a12 = v19;
        goto LABEL_86;
      }
      while ( 1 )
      {
        while ( 1 )
        {
          do
          {
            if ( v38 >= a9 )
              goto LABEL_75;
            v27 = (unsigned __int8)WcSkipReparsePointInEnumeration(v26, 2684354591LL) == 0;
            v26 = v39;
          }
          while ( !v27 );
          if ( a3 == 33 )
            break;
LABEL_60:
          EnumEntry = WcTranslateNextEnumEntry(
                        v39,
                        a3,
                        a7,
                        a8,
                        v36,
                        a9 - v38,
                        a10 + v38,
                        a11,
                        (__int64)&v47,
                        (__int64)&v40);
          v22 = EnumEntry;
          if ( EnumEntry == -2147483643 )
          {
            v29 = v40;
            v37 = v40;
            goto LABEL_76;
          }
          if ( EnumEntry < 0 )
            goto LABEL_86;
          v29 = v37;
          if ( !v40 )
            goto LABEL_76;
          if ( v37 )
          {
            if ( a3 == 33 )
            {
              v19 += v37;
            }
            else
            {
              v19 += (v37 + 7) & 0xFFFFFFF8;
              v29 = v37;
            }
            v41 = v19;
          }
          if ( v48 )
          {
            v30 = (v29 + 7) & 0xFFFFFFF8;
            if ( a11 )
              RtlWriteULongToUser(v48, v30);
            else
              *v48 = v30;
            if ( v22 < 0 )
              goto LABEL_86;
          }
          v36 = 0;
          v37 = v40;
          v48 = v47;
          v38 += (v40 + 7) & 0xFFFFFFF8;
          WcAdvanceNextEnumEntry(v39);
          v26 = v39;
          if ( (v34 & 2) != 0 )
            goto LABEL_75;
        }
        v27 = (unsigned __int8)WcSkipReparsePointInEnumeration(v39, *(unsigned int *)(v39 + 20)) == 0;
        v26 = v39;
        if ( v27 )
        {
          if ( !(unsigned __int8)WcSkipReparsePointInEnumeration(v39, a8) )
            goto LABEL_60;
          v26 = v39;
        }
      }
    }
    if ( v23 != -2147483643 )
      break;
    v34 |= 2u;
    NextEntryFileName = WcGetNextEntryFileName(v39, 0);
    if ( !NextEntryFileName )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v24) = 3;
        WPP_RECORDER_SF_sD(
          wil_details_featureDescriptors_a->DeviceExtension,
          v24,
          18,
          27,
          (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
          97);
      }
      NextEntryFileName = 2 * v42;
      if ( v35 )
        NextEntryFileName = v42;
    }
    v42 = NextEntryFileName;
    v18 = NextEntryFileName + v15;
    v43 = NextEntryFileName + v15;
LABEL_75:
    v29 = v37;
LABEL_76:
    v27 = v29 + v19 == 0;
    v19 += v29;
    v41 = v19;
    if ( !v27 )
      goto LABEL_53;
    if ( v22 >= 0 )
    {
      LOBYTE(v24) = 1;
      WcResetEnumContexts(v44, v24);
    }
    else
    {
      WcFreeEnumContexts(v44);
    }
    a6 = v34 & 0xFA;
    v35 = 0;
    v31 = 0;
    if ( v45 != 33 )
      v31 = a5;
    a5 = v31;
    v32 = 0;
    if ( v46 != 33 )
      v32 = a4;
    a4 = v32;
    a2 = v50;
    v13 = a1;
  }
  if ( v23 == -2147483642 && !v35 && !v38 )
    v22 = -1073741809;
LABEL_86:
  WcFreeEnumContexts(v44);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1400154ac  mov     r11, rsp
0x1400154af  mov     [r11+20h], r9
0x1400154b3  mov     [r11+18h], r8d
0x1400154b7  mov     [r11+10h], rdx
0x1400154bb  mov     [r11+8], rcx
0x1400154bf  push    rbx
0x1400154c0  push    rsi
0x1400154c1  push    rdi
0x1400154c2  push    r12
0x1400154c4  push    r13
0x1400154c6  push    r15
0x1400154c8  sub     rsp, 0B8h
0x1400154cf  mov     r15d, r8d
0x1400154d2  mov     r10, rcx
0x1400154d5  mov     [rsp+0E8h+var_78], 0
0x1400154dd  mov     qword ptr [r11-50h], 0
0x1400154e5  lea     rax, [r11-68h]
0x1400154e9  mov     [r11-60h], rax
0x1400154ed  lea     rax, [r11-68h]
0x1400154f1  mov     [r11-68h], rax
0x1400154f5  cmp     r8d, 26h ; '&'
0x1400154f9  jg      short loc_140015572
0x1400154fb  jz      short loc_140015567
0x1400154fd  mov     ecx, r8d
0x140015500  sub     ecx, 1
0x140015503  jz      short loc_140015560
0x140015505  sub     ecx, 1
0x140015508  jz      short loc_140015559
0x14001550a  sub     ecx, 1
0x14001550d  jz      short loc_140015552
0x14001550f  sub     ecx, 9
0x140015512  jz      short loc_140015541
0x140015514  sub     ecx, 15h
0x140015517  jz      short loc_140015534
0x140015519  cmp     ecx, 4
0x14001551c  jnz     loc_140015A44
0x140015522  lea     eax, [rcx+64h]
0x140015525  mov     edi, 6Ah ; 'j'
0x14001552a  mov     ebx, 4Fh ; 'O'
0x14001552f  jmp     loc_1400155CA
0x140015534  mov     eax, 10h
0x140015539  lea     ebx, [rax+11h]
0x14001553c  jmp     loc_1400155C8
0x140015541  mov     eax, 0Ch
0x140015546  mov     edi, 50h ; 'P'
0x14001554b  mov     ebx, 4Eh ; 'N'
0x140015550  jmp     short loc_1400155CA
0x140015552  mov     eax, 5Eh ; '^'
0x140015557  jmp     short loc_140015525
0x140015559  mov     eax, 44h ; 'D'
0x14001555e  jmp     short loc_140015546
0x140015560  mov     eax, 40h ; '@'
0x140015565  jmp     short loc_140015546
0x140015567  mov     ebx, 50h ; 'P'
0x14001556c  mov     eax, ebx
0x14001556e  mov     edi, ebx
0x140015570  jmp     short loc_14001554B
0x140015572  mov     ecx, r8d
0x140015575  mov     ebx, 3Ch ; '<'
0x14001557a  sub     ecx, ebx
0x14001557c  jz      short loc_1400155C3
0x14001557e  sub     ecx, 3
0x140015581  jz      short loc_1400155B9
0x140015583  sub     ecx, 0Fh
0x140015586  jz      short loc_140015567
0x140015588  sub     ecx, 1
0x14001558b  jz      short loc_1400155AD
0x14001558d  sub     ecx, 1
0x140015590  jz      short loc_1400155A3
0x140015592  cmp     ecx, 1
0x140015595  jnz     loc_140015A44
0x14001559b  lea     eax, [rbx+3Eh]
0x14001559e  lea     ebx, [rcx+50h]
0x1400155a1  jmp     short loc_1400155C8
0x1400155a3  mov     eax, 60h ; '`'
0x1400155a8  lea     ebx, [rax-10h]
0x1400155ab  jmp     short loc_1400155C8
0x1400155ad  mov     edi, 6Ah ; 'j'
0x1400155b2  mov     eax, edi
0x1400155b4  jmp     loc_14001552A
0x1400155b9  mov     eax, 72h ; 'r'
0x1400155be  lea     ebx, [rax-33h]
0x1400155c1  jmp     short loc_1400155C8
0x1400155c3  mov     eax, 58h ; 'X'
0x1400155c8  mov     edi, eax
0x1400155ca  mov     [rsp+0E8h+var_94], edi
0x1400155ce  mov     [rsp+0E8h+var_90], ebx
0x1400155d2  mov     r12d, [rsp+0E8h+arg_40]
0x1400155da  add     r12d, edi
0x1400155dd  cmp     r12d, edi
0x1400155e0  jb      loc_140015A44
0x1400155e6  cmp     r12d, eax
0x1400155e9  jb      loc_140015A44
0x1400155ef  sub     r12d, eax
0x1400155f2  mov     [rsp+0E8h+var_70], 100h
0x1400155fa  mov     [rsp+0E8h+var_84], 0
0x140015602  xor     r13d, r13d
0x140015605  mov     [rsp+0E8h+var_74], r13d
0x14001560a  xor     ecx, ecx
0x14001560c  mov     [rsp+0E8h+var_48], rcx
0x140015614  mov     [rsp+0E8h+var_88], ecx
0x140015618  mov     [rsp+0E8h+var_8C], 1
0x14001561d  mov     [rsp+0E8h+var_97], 1
0x140015622  mov     [rsp+0E8h+var_54], ebx
0x140015629  mov     [rsp+0E8h+var_58], ebx
0x140015630  mov     eax, 10000h
0x140015635  cmp     r12d, eax
0x140015638  cmova   r12d, eax
0x14001563c  mov     [rsp+0E8h+var_6C], r12d
0x140015641  mov     cl, [rsp+0E8h+arg_28]
0x140015648  mov     [rsp+0E8h+var_98], cl
0x14001564c  mov     dword ptr [rsp+0E8h+var_B0], 0
0x140015654  mov     byte ptr [rsp+0E8h+var_B8], cl
0x140015658  mov     dword ptr [rsp+0E8h+var_C0], ebx
0x14001565c  mov     dword ptr [rsp+0E8h+var_C8], r12d
0x140015661  xor     r9d, r9d
0x140015664  mov     r8, rdx
0x140015667  mov     rdx, r10
0x14001566a  lea     rcx, [rsp+0E8h+var_68]
0x140015672  call    WcPrepareEnumerationContexts
0x140015677  mov     esi, eax
0x140015679  test    eax, eax
0x14001567b  jns     short loc_1400156DB
0x14001567d  lea     rax, WPP_RECORDER_INITIALIZED
0x140015684  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001568b  jz      loc_140015A49
0x140015691  mov     r9d, 1Ah
0x140015697  mov     dword ptr [rsp+0E8h+var_A8], esi
0x14001569b  mov     dword ptr [rsp+0E8h+var_B0], r15d
0x1400156a0  mov     dword ptr [rsp+0E8h+var_B8], 0C2Fh
0x1400156a8  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x1400156af  mov     [rsp+0E8h+var_C0], rax
0x1400156b4  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x1400156bb  mov     [rsp+0E8h+var_C8], rax
0x1400156c0  lea     r8d, [r9-8]
0x1400156c4  mov     dl, 2
0x1400156c6  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400156cd  mov     rcx, [rcx+40h]
0x1400156d1  call    WPP_RECORDER_SF_sDdd
0x1400156d6  jmp     loc_140015A49
0x1400156db  mov     rcx, [rsp+0E8h+var_68]
0x1400156e3  mov     [rsp+0E8h+var_80], rcx
0x1400156e8  lea     rax, [rcx+3Ch]
0x1400156ec  mov     [rsp+0E8h+var_A8], rax
0x1400156f1  mov     rax, [rcx+48h]
0x1400156f5  mov     [rsp+0E8h+var_B0], rax
0x1400156fa  mov     eax, [rcx+40h]
0x1400156fd  mov     dword ptr [rsp+0E8h+var_B8], eax
0x140015701  mov     al, [rsp+0E8h+var_98]
0x140015705  mov     byte ptr [rsp+0E8h+var_C0], al
0x140015709  mov     eax, [rsp+0E8h+arg_20]
0x140015710  mov     dword ptr [rsp+0E8h+var_C8], eax
0x140015714  mov     r9, [rsp+0E8h+arg_18]
0x14001571c  mov     r8d, ebx
0x14001571f  mov     rdx, [rsp+0E8h+arg_8]
0x140015727  mov     rcx, [rsp+0E8h+arg_0]
0x14001572f  call    WcEnumerateDirectory
0x140015734  mov     esi, eax
0x140015736  test    eax, eax
0x140015738  jns     loc_1400157F6
0x14001573e  cmp     eax, 80000005h
0x140015743  jnz     loc_1400157CB
0x140015749  or      [rsp+0E8h+var_98], 2
0x14001574e  xor     edx, edx
0x140015750  mov     rcx, [rsp+0E8h+var_80]
0x140015755  call    WcGetNextEntryFileName
0x14001575a  test    eax, eax
0x14001575c  jnz     short loc_1400157B7
0x14001575e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140015765  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001576c  jz      short loc_1400157A8
0x14001576e  lea     r9d, [rax+1Bh]
0x140015772  mov     dword ptr [rsp+0E8h+var_B8], 0C61h
0x14001577a  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140015781  mov     [rsp+0E8h+var_C0], rax
0x140015786  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x14001578d  mov     [rsp+0E8h+var_C8], rax
0x140015792  lea     r8d, [r9-9]
0x140015796  mov     dl, 3
0x140015798  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001579f  mov     rcx, [rcx+40h]
0x1400157a3  call    WPP_RECORDER_SF_sD
0x1400157a8  mov     ecx, [rsp+0E8h+var_70]
0x1400157ac  lea     eax, [rcx+rcx]
0x1400157af  cmp     [rsp+0E8h+var_97], 0
0x1400157b4  cmovnz  eax, ecx
0x1400157b7  mov     ecx, eax
0x1400157b9  mov     [rsp+0E8h+var_70], eax
0x1400157bd  lea     r12d, [rax+rdi]
0x1400157c1  mov     [rsp+0E8h+var_6C], r12d
0x1400157c6  jmp     loc_1400159BC
0x1400157cb  cmp     eax, 80000006h
0x1400157d0  jnz     loc_140015A49
0x1400157d6  cmp     [rsp+0E8h+var_97], 0
0x1400157db  jnz     loc_140015A49
0x1400157e1  cmp     [rsp+0E8h+var_84], 0
0x1400157e6  jnz     loc_140015A49
0x1400157ec  mov     esi, 0C000000Fh
0x1400157f1  jmp     loc_140015A49
0x1400157f6  mov     rax, [rsp+0E8h+var_80]
0x1400157fb  cmp     dword ptr [rax+3Ch], 0
0x1400157ff  jnz     short loc_140015816
0x140015801  mov     rax, [rsp+0E8h+arg_58]
0x140015809  mov     [rax], r13d
0x14001580c  jmp     loc_140015A49
0x140015811  mov     rax, [rsp+0E8h+var_80]
0x140015816  mov     ecx, [rsp+0E8h+arg_40]
0x14001581d  cmp     [rsp+0E8h+var_84], ecx
0x140015821  jnb     loc_1400159BC
0x140015827  mov     edx, 0A000001Fh
0x14001582c  mov     rcx, rax
0x14001582f  call    WcSkipReparsePointInEnumeration
0x140015834  test    al, al
0x140015836  mov     rax, [rsp+0E8h+var_80]
0x14001583b  jnz     short loc_140015816
0x14001583d  cmp     r15d, 21h ; '!'
0x140015841  jnz     short loc_14001586A
0x140015843  mov     edx, [rax+14h]
0x140015846  mov     rcx, rax
0x140015849  call    WcSkipReparsePointInEnumeration
0x14001584e  test    al, al
0x140015850  mov     rax, [rsp+0E8h+var_80]
0x140015855  jnz     short loc_140015816
0x140015857  mov     edx, [rsp+0E8h+arg_38]
0x14001585e  mov     rcx, rax
0x140015861  call    WcSkipReparsePointInEnumeration
0x140015866  test    al, al
0x140015868  jnz     short loc_140015811
0x14001586a  mov     edx, [rsp+0E8h+var_84]
0x14001586e  mov     ecx, edx
0x140015870  add     rcx, [rsp+0E8h+arg_48]
0x140015878  mov     eax, [rsp+0E8h+arg_40]
0x14001587f  sub     eax, edx
0x140015881  lea     rdx, [rsp+0E8h+var_78]
0x140015886  mov     [rsp+0E8h+var_A0], rdx
0x14001588b  lea     rdx, [rsp+0E8h+var_50]
0x140015893  mov     [rsp+0E8h+var_A8], rdx
0x140015898  mov     dl, [rsp+0E8h+arg_50]
0x14001589f  mov     byte ptr [rsp+0E8h+var_B0], dl
0x1400158a3  mov     [rsp+0E8h+var_B8], rcx
0x1400158a8  mov     dword ptr [rsp+0E8h+var_C0], eax
0x1400158ac  mov     al, [rsp+0E8h+var_8C]
0x1400158b0  mov     byte ptr [rsp+0E8h+var_C8], al
0x1400158b4  mov     r9d, [rsp+0E8h+arg_38]
0x1400158bc  mov     r8d, [rsp+0E8h+arg_30]
0x1400158c4  mov     edx, r15d
0x1400158c7  mov     rcx, [rsp+0E8h+var_80]
0x1400158cc  call    WcTranslateNextEnumEntry
0x1400158d1  mov     esi, eax
0x1400158d3  cmp     eax, 80000005h
0x1400158d8  jnz     short loc_1400158E7
0x1400158da  mov     eax, [rsp+0E8h+var_78]
0x1400158de  mov     [rsp+0E8h+var_88], eax
0x1400158e2  jmp     loc_1400159C0
0x1400158e7  test    eax, eax
0x1400158e9  js      loc_140015A49
0x1400158ef  mov     eax, [rsp+0E8h+var_88]
0x1400158f3  cmp     [rsp+0E8h+var_78], 0
0x1400158f8  jz      loc_1400159C0
0x1400158fe  test    eax, eax
0x140015900  jz      short loc_14001591F
0x140015902  cmp     r15d, 21h ; '!'
0x140015906  jnz     short loc_14001590D
0x140015908  add     r13d, eax
0x14001590b  jmp     short loc_14001591A
0x14001590d  add     eax, 7
0x140015910  and     eax, 0FFFFFFF8h
0x140015913  add     r13d, eax
0x140015916  mov     eax, [rsp+0E8h+var_88]
0x14001591a  mov     [rsp+0E8h+var_74], r13d
0x14001591f  mov     rcx, [rsp+0E8h+var_48]
0x140015927  test    rcx, rcx
0x14001592a  jz      short loc_14001597B
0x14001592c  add     eax, 7
0x14001592f  and     eax, 0FFFFFFF8h
0x140015932  cmp     [rsp+0E8h+arg_50], 0
0x14001593a  jz      short loc_140015945
0x14001593c  mov     edx, eax
0x14001593e  call    RtlWriteULongToUser
0x140015943  jmp     short loc_140015947
0x140015945  mov     [rcx], eax
0x140015947  jmp     short loc_140015973
0x140015949  mov     esi, 0C00000E8h
0x14001594e  mov     al, [rsp+0E8h+arg_28]
0x140015955  mov     [rsp+0E8h+var_98], al
0x140015959  mov     r15d, [rsp+0E8h+arg_10]
0x140015961  mov     edi, [rsp+0E8h+var_94]
0x140015965  mov     ebx, [rsp+0E8h+var_90]
0x140015969  mov     r12d, [rsp+0E8h+var_6C]
0x14001596e  mov     r13d, [rsp+0E8h+var_74]
0x140015973  test    esi, esi
0x140015975  js      loc_140015A49
0x14001597b  mov     [rsp+0E8h+var_8C], 0
0x140015980  mov     eax, [rsp+0E8h+var_78]
0x140015984  mov     [rsp+0E8h+var_88], eax
0x140015988  mov     rcx, [rsp+0E8h+var_50]
0x140015990  mov     [rsp+0E8h+var_48], rcx
0x140015998  add     eax, 7
0x14001599b  and     eax, 0FFFFFFF8h
0x14001599e  add     [rsp+0E8h+var_84], eax
  ... truncated ...
```
