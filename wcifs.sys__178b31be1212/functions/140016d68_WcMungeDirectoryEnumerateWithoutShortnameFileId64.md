# WcMungeDirectoryEnumerateWithoutShortnameFileId64

- ea: `0x140016d68`
- end: `0x140017713`
- name: `WcMungeDirectoryEnumerateWithoutShortnameFileId64`
- size: `2475`
- prototype: `__int64 __fastcall(int, char, __int64, char, int, unsigned int, _DWORD *, unsigned int, char, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140029060`

## callees

- `0x1400020c4`
- `0x140007c90`
- `0x14001439c`
- `0x140014400`
- `0x1400144e4`
- `0x14001452c`
- `0x140016d68`

## pseudocode

```c
__int64 __fastcall WcMungeDirectoryEnumerateWithoutShortnameFileId64(
        int a1,
        char a2,
        __int64 a3,
        char a4,
        int a5,
        unsigned int a6,
        _DWORD *a7,
        unsigned int a8,
        char a9,
        _QWORD *a10,
        unsigned int *a11)
{
  char v11; // r15
  unsigned int v13; // esi
  unsigned int v14; // edi
  _UNKNOWN **v15; // rdx
  unsigned int v16; // r13d
  unsigned int v17; // r12d
  char v18; // r14
  _DWORD *v19; // rdi
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int *v22; // r15
  int ULongFromUser; // eax
  unsigned int v24; // eax
  void *v25; // rdx
  void *v26; // rcx
  int v27; // r8d
  unsigned int v28; // edx
  int *v29; // rcx
  int v30; // eax
  int v31; // eax
  int *v32; // rcx
  unsigned int *v33; // r15
  int v34; // eax
  unsigned int v35; // eax
  _QWORD *v36; // r15
  int v37; // eax
  int *v38; // rcx
  void *v39; // rdx
  void *v40; // rcx
  unsigned int v41; // r14d
  int v42; // eax
  int *v43; // rcx
  int v44; // eax
  int *v45; // rcx
  void *v46; // rdx
  void *v47; // rcx
  unsigned int v48; // r13d
  int v49; // r8d
  unsigned int v50; // edx
  int *v51; // rcx
  int v52; // eax
  int v53; // eax
  int *v54; // rcx
  unsigned int *v55; // r15
  int v56; // eax
  unsigned int v57; // eax
  int v58; // eax
  int *v59; // rcx
  void *v60; // rdx
  void *v61; // rcx
  unsigned int v62; // r13d
  unsigned int v63; // r12d
  int v64; // r8d
  unsigned int v65; // edx
  _DWORD *v66; // rcx
  unsigned int *v67; // r15
  int v68; // eax
  unsigned int v69; // eax
  int v70; // eax
  int *v71; // rcx
  void *v72; // rdx
  void *v73; // rcx
  int v74; // eax

  v11 = a4;
  v13 = 0;
  v14 = 0;
  if ( a1 != 1 )
  {
    if ( a1 != 2 )
    {
      if ( a1 == 12 )
      {
        v41 = *(_DWORD *)(a3 + 60);
        v17 = v41 + 12;
        if ( a8 < v41 + 12 && (a8 < 0xC || !a2) )
          goto LABEL_219;
        if ( v41 >= a8 - 12 )
          v41 = a8 - 12;
        v42 = *(_DWORD *)(a3 + 4);
        v43 = a7 + 1;
        if ( a9 )
          RtlWriteULongToUser(v43, v42);
        else
          *v43 = v42;
        v44 = *(_DWORD *)(a3 + 60);
        v45 = a7 + 2;
        if ( a9 )
          RtlWriteULongToUser(v45, v44);
        else
          *v45 = v44;
        v46 = (void *)(a3 + 80);
        v47 = a7 + 3;
        if ( a9 )
          RtlCopyToUser(v47, v46, v41);
        else
          RtlCopyVolatileMemory(v47, v46, v41);
        if ( a9 )
          RtlWriteULongToUser(a7, 0);
        else
          *a7 = 0;
        *a10 = a7;
        v14 = v41 + 12;
        goto LABEL_123;
      }
      if ( a1 != 38 )
      {
        if ( a1 != 78 )
        {
          v15 = &WPP_RECORDER_INITIALIZED;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v15) = 3;
            WPP_RECORDER_SF_sDd(
              wil_details_featureDescriptors_a->DeviceExtension,
              (_DWORD)v15,
              18,
              13,
              (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
              156,
              a1,
              0);
          }
          v13 = -1073741637;
          goto LABEL_219;
        }
        v16 = *(_DWORD *)(a3 + 60);
        v17 = v16 + 80;
        if ( a8 < v16 + 80 && (a8 < 0x50 || !a2) )
          goto LABEL_219;
        if ( v16 >= a8 - 80 )
          v16 = a8 - 80;
        v18 = a9;
        v19 = a7;
        if ( a9 )
          RtlCopyToUser(a7, (void *)a3, 0x50u);
        else
          RtlCopyVolatileMemory(a7, (const void *)a3, 0x50u);
        v20 = *(_DWORD *)(a3 + 68);
        if ( v20 == a5 )
        {
          v21 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
          if ( !v21 )
            v21 = 128;
        }
        else
        {
          if ( (a6 & 0xFFF0000) != 0
            || a6 <= 2
            || (a6 & 0xC0000000) == 0x40000000
            || (a6 & 0x30000000) == 0x30000000
            || v20 != a6 )
          {
LABEL_34:
            if ( !v11 )
            {
              v22 = a7 + 14;
              if ( a9 )
                ULongFromUser = RtlReadULongFromUser(a7 + 14);
              else
                ULongFromUser = *v22;
              v24 = ULongFromUser & 0xFFFFBFFF;
              if ( a9 )
                RtlWriteULongToUser(a7 + 14, v24);
              else
                *v22 = v24;
              v11 = a4;
            }
            v25 = (void *)(a3 + 80);
            v26 = a7 + 20;
            if ( a9 )
              RtlCopyToUser(v26, v25, v16);
            else
              RtlCopyVolatileMemory(v26, v25, v16);
            if ( !v11 )
            {
              if ( a9 )
                RtlWriteULong64ToUser((_QWORD *)a7 + 9, -1);
              else
                *((_QWORD *)a7 + 9) = -1;
            }
LABEL_49:
            if ( v18 )
              RtlWriteULongToUser(v19, 0);
            else
              *v19 = 0;
            *a10 = v19;
            v14 = v16 + 80;
LABEL_123:
            if ( v14 < v17 )
              v13 = -2147483643;
            goto LABEL_219;
          }
          v21 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
          if ( !v21 )
            v21 = 128;
        }
        if ( a9 )
          RtlWriteULongToUser(a7 + 14, v21);
        else
          a7[14] = v21;
        if ( a9 )
          RtlWriteULongToUser(a7 + 17, 0);
        else
          a7[17] = 0;
        goto LABEL_34;
      }
      v16 = *(_DWORD *)(a3 + 60);
      v17 = v16 + 80;
      if ( a8 < v16 + 80 && (a8 < 0x50 || !a2) )
        goto LABEL_219;
      if ( v16 >= a8 - 80 )
        v16 = a8 - 80;
      v18 = a9;
      v19 = a7;
      if ( a9 )
        RtlCopyToUser(a7, (void *)a3, 0x38u);
      else
        RtlCopyVolatileMemory(a7, (const void *)a3, 0x38u);
      v27 = *(_DWORD *)(a3 + 68);
      if ( v27 == a5 )
      {
        v28 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
        if ( !v28 )
          v28 = 128;
      }
      else
      {
        if ( (a6 & 0xFFF0000) != 0
          || a6 <= 2
          || (a6 & 0xC0000000) == 0x40000000
          || (a6 & 0x30000000) == 0x30000000
          || v27 != a6 )
        {
          v31 = *(_DWORD *)(a3 + 56);
          v32 = a7 + 14;
          if ( a9 )
            RtlWriteULongToUser(v32, v31);
          else
            *v32 = v31;
          v29 = a7 + 16;
          if ( (*(_DWORD *)(a3 + 56) & 0x400) != 0 )
          {
            v30 = *(_DWORD *)(a3 + 68);
            goto LABEL_69;
          }
LABEL_68:
          v30 = *(_DWORD *)(a3 + 64);
LABEL_69:
          if ( a9 )
            RtlWriteULongToUser(v29, v30);
          else
            *v29 = v30;
          if ( !v11 )
          {
            v33 = a7 + 14;
            if ( a9 )
              v34 = RtlReadULongFromUser(a7 + 14);
            else
              v34 = *v33;
            v35 = v34 & 0xFFFFBFFF;
            if ( a9 )
              RtlWriteULongToUser(a7 + 14, v35);
            else
              *v33 = v35;
          }
          v36 = a7 + 18;
          if ( a9 )
            RtlWriteULong64ToUser((_QWORD *)a7 + 9, *(_QWORD *)(a3 + 72));
          else
            *v36 = *(_QWORD *)(a3 + 72);
          if ( !a4 )
          {
            if ( a9 )
              RtlWriteULong64ToUser((_QWORD *)a7 + 9, -1);
            else
              *v36 = -1;
          }
          v37 = *(_DWORD *)(a3 + 60);
          v38 = a7 + 15;
          if ( a9 )
            RtlWriteULongToUser(v38, v37);
          else
            *v38 = v37;
          v39 = (void *)(a3 + 80);
          v40 = a7 + 20;
          if ( a9 )
            RtlCopyToUser(v40, v39, v16);
          else
            RtlCopyVolatileMemory(v40, v39, v16);
          goto LABEL_49;
        }
        v28 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
        if ( !v28 )
          v28 = 128;
      }
      if ( a9 )
        RtlWriteULongToUser(a7 + 14, v28);
      else
        a7[14] = v28;
      v29 = a7 + 16;
      goto LABEL_68;
    }
    v48 = *(_DWORD *)(a3 + 60);
    v17 = v48 + 68;
    if ( a8 < v48 + 68 && (a8 < 0x44 || !a2) )
      goto LABEL_219;
    if ( v48 >= a8 - 68 )
      v48 = a8 - 68;
    if ( a9 )
      RtlCopyToUser(a7, (void *)a3, 0x38u);
    else
      RtlCopyVolatileMemory(a7, (const void *)a3, 0x38u);
    v49 = *(_DWORD *)(a3 + 68);
    if ( v49 == a5 )
    {
      v50 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
      if ( !v50 )
        v50 = 128;
    }
    else
    {
      if ( (a6 & 0xFFF0000) != 0
        || a6 <= 2
        || (a6 & 0xC0000000) == 0x40000000
        || (a6 & 0x30000000) == 0x30000000
        || v49 != a6 )
      {
        v53 = *(_DWORD *)(a3 + 56);
        v54 = a7 + 14;
        if ( a9 )
          RtlWriteULongToUser(v54, v53);
        else
          *v54 = v53;
        v51 = a7 + 16;
        if ( (*(_DWORD *)(a3 + 56) & 0x400) != 0 )
        {
          v52 = *(_DWORD *)(a3 + 68);
          goto LABEL_141;
        }
LABEL_140:
        v52 = *(_DWORD *)(a3 + 64);
LABEL_141:
        if ( a9 )
          RtlWriteULongToUser(v51, v52);
        else
          *v51 = v52;
        if ( !v11 )
        {
          v55 = a7 + 14;
          if ( a9 )
            v56 = RtlReadULongFromUser(a7 + 14);
          else
            v56 = *v55;
          v57 = v56 & 0xFFFFBFFF;
          if ( a9 )
            RtlWriteULongToUser(a7 + 14, v57);
          else
            *v55 = v57;
        }
        v58 = *(_DWORD *)(a3 + 60);
        v59 = a7 + 15;
        if ( a9 )
          RtlWriteULongToUser(v59, v58);
        else
          *v59 = v58;
        v60 = (void *)(a3 + 80);
        v61 = a7 + 17;
        if ( a9 )
          RtlCopyToUser(v61, v60, v48);
        else
          RtlCopyVolatileMemory(v61, v60, v48);
        if ( a9 )
          RtlWriteULongToUser(a7, 0);
        else
          *a7 = 0;
        *a10 = a7;
        v14 = v48 + 68;
        goto LABEL_123;
      }
      v50 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
      if ( !v50 )
        v50 = 128;
    }
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v50);
    else
      a7[14] = v50;
    v51 = a7 + 16;
    goto LABEL_140;
  }
  v62 = *(_DWORD *)(a3 + 60);
  v63 = v62 + 64;
  if ( a8 < v62 + 64 && (a8 < 0x40 || !a2) )
    goto LABEL_219;
  if ( v62 >= a8 - 64 )
    v62 = a8 - 64;
  if ( a9 )
    RtlCopyToUser(a7, (void *)a3, 0x38u);
  else
    RtlCopyVolatileMemory(a7, (const void *)a3, 0x38u);
  v64 = *(_DWORD *)(a3 + 68);
  if ( v64 == a5 )
  {
    v65 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
    if ( !v65 )
      v65 = 128;
  }
  else
  {
    if ( (a6 & 0xFFF0000) != 0
      || a6 <= 2
      || (a6 & 0xC0000000) == 0x40000000
      || (a6 & 0x30000000) == 0x30000000
      || v64 != a6 )
    {
      v66 = a7 + 14;
      if ( !a9 )
      {
        *v66 = *(_DWORD *)(a3 + 56);
        goto LABEL_200;
      }
      v65 = *(_DWORD *)(a3 + 56);
      goto LABEL_198;
    }
    v65 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
    if ( !v65 )
      v65 = 128;
  }
  if ( a9 )
  {
    v66 = a7 + 14;
LABEL_198:
    RtlWriteULongToUser(v66, v65);
    goto LABEL_200;
  }
  a7[14] = v65;
LABEL_200:
  if ( !v11 )
  {
    v67 = a7 + 14;
    if ( a9 )
      v68 = RtlReadULongFromUser(a7 + 14);
    else
      v68 = *v67;
    v69 = v68 & 0xFFFFBFFF;
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v69);
    else
      *v67 = v69;
  }
  v70 = *(_DWORD *)(a3 + 60);
  v71 = a7 + 15;
  if ( a9 )
    RtlWriteULongToUser(v71, v70);
  else
    *v71 = v70;
  v72 = (void *)(a3 + 80);
  v73 = a7 + 16;
  if ( a9 )
    RtlCopyToUser(v73, v72, v62);
  else
    RtlCopyVolatileMemory(v73, v72, v62);
  if ( a9 )
    RtlWriteULongToUser(a7, 0);
  else
    *a7 = 0;
  *a10 = a7;
  v14 = v62 + 64;
  v74 = 0;
  if ( v62 + 64 < v63 )
    v74 = -2147483643;
  v13 = v74;
LABEL_219:
  *a11 = v14;
  return v13;
}

```

## disassembly

```asm
0x140016d68  mov     rax, rsp
0x140016d6b  mov     [rax+8], rbx
0x140016d6f  mov     [rax+10h], rsi
0x140016d73  mov     [rax+20h], r9b
0x140016d77  push    rdi
0x140016d78  push    r12
0x140016d7a  push    r13
0x140016d7c  push    r14
0x140016d7e  push    r15
0x140016d80  sub     rsp, 90h
0x140016d87  mov     r15b, r9b
0x140016d8a  mov     rbx, r8
0x140016d8d  mov     byte ptr [rax-78h], 0
0x140016d91  xor     esi, esi
0x140016d93  xor     edi, edi
0x140016d95  mov     r8d, ecx
0x140016d98  sub     r8d, 1
0x140016d9c  jz      loc_1400174EA
0x140016da2  sub     r8d, 1
0x140016da6  jz      loc_1400172EC
0x140016dac  sub     r8d, 0Ah
0x140016db0  jz      loc_140017219
0x140016db6  sub     r8d, 1Ah
0x140016dba  jz      loc_140016FFD
0x140016dc0  cmp     r8d, 28h ; '('
0x140016dc4  jz      short loc_140016E21
0x140016dc6  lea     rdx, WPP_RECORDER_INITIALIZED
0x140016dcd  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140016dd4  jz      short loc_140016E13
0x140016dd6  lea     r9d, [rsi+0Dh]
0x140016dda  mov     [rax-80h], ecx
0x140016ddd  mov     [rsp+0B8h+var_88], 29Ch
0x140016de5  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140016dec  mov     [rsp+0B8h+var_90], rax
0x140016df1  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x140016df8  mov     [rsp+0B8h+var_98], rax
0x140016dfd  lea     r8d, [rsi+12h]
0x140016e01  mov     dl, 3
0x140016e03  mov     rcx, cs:wil_details_featureDescriptors_a
0x140016e0a  mov     rcx, [rcx+40h]
0x140016e0e  call    WPP_RECORDER_SF_sDd
0x140016e13  mov     esi, 0C00000BBh
0x140016e18  mov     [rsp+0B8h+var_74], esi
0x140016e1c  jmp     loc_1400176DE
0x140016e21  mov     r13d, [rbx+3Ch]
0x140016e25  lea     r12d, [r13+50h]
0x140016e29  mov     eax, [rsp+0B8h+arg_38]
0x140016e30  cmp     eax, r12d
0x140016e33  jnb     short loc_140016E46
0x140016e35  cmp     eax, 50h ; 'P'
0x140016e38  jb      loc_1400176DE
0x140016e3e  test    dl, dl
0x140016e40  jz      loc_1400176DE
0x140016e46  add     eax, 0FFFFFFB0h
0x140016e49  cmp     r13d, eax
0x140016e4c  cmovnb  r13d, eax
0x140016e50  mov     [rsp+0B8h+var_78], 1
0x140016e55  mov     r14b, [rsp+0B8h+arg_40]
0x140016e5d  mov     r8d, 50h ; 'P'; Size
0x140016e63  mov     rdx, rbx; Src
0x140016e66  mov     rdi, [rsp+0B8h+arg_30]
0x140016e6e  mov     rcx, rdi; void *
0x140016e71  test    r14b, r14b
0x140016e74  jz      short loc_140016E7D
0x140016e76  call    RtlCopyToUser
0x140016e7b  jmp     short loc_140016E82
0x140016e7d  call    RtlCopyVolatileMemory
0x140016e82  mov     r8d, [rbx+44h]
0x140016e86  cmp     r8d, [rsp+0B8h+arg_20]
0x140016e8e  jnz     short loc_140016EC4
0x140016e90  mov     edx, [rbx+38h]
0x140016e93  mov     [rsp+0B8h+var_70], edx
0x140016e97  mov     eax, edx
0x140016e99  btr     eax, 0Ah
0x140016e9d  mov     [rsp+0B8h+var_70], eax
0x140016ea1  mov     eax, edx
0x140016ea3  and     eax, 0FFFFEBFFh
0x140016ea8  mov     [rsp+0B8h+var_70], eax
0x140016eac  and     edx, 0FFFFE9FFh
0x140016eb2  mov     [rsp+0B8h+var_70], edx
0x140016eb6  mov     eax, 80h
0x140016ebb  cmovz   edx, eax
0x140016ebe  mov     [rsp+0B8h+var_70], edx
0x140016ec2  jmp     short loc_140016F2E
0x140016ec4  mov     edx, [rsp+0B8h+arg_28]
0x140016ecb  test    edx, 0FFF0000h
0x140016ed1  jnz     loc_140016F5A
0x140016ed7  cmp     edx, 2
0x140016eda  jbe     short loc_140016F5A
0x140016edc  mov     eax, edx
0x140016ede  and     eax, 0C0000000h
0x140016ee3  cmp     eax, 40000000h
0x140016ee8  jz      short loc_140016F5A
0x140016eea  mov     eax, edx
0x140016eec  mov     ecx, 30000000h
0x140016ef1  and     eax, ecx
0x140016ef3  cmp     eax, ecx
0x140016ef5  jz      short loc_140016F5A
0x140016ef7  cmp     r8d, edx
0x140016efa  jnz     short loc_140016F5A
0x140016efc  mov     edx, [rbx+38h]
0x140016eff  mov     [rsp+0B8h+var_68], edx
0x140016f03  mov     eax, edx
0x140016f05  btr     eax, 0Ah
0x140016f09  mov     [rsp+0B8h+var_68], eax
0x140016f0d  mov     eax, edx
0x140016f0f  and     eax, 0FFFFEBFFh
0x140016f14  mov     [rsp+0B8h+var_68], eax
0x140016f18  and     edx, 0FFFFE9FFh
0x140016f1e  mov     [rsp+0B8h+var_68], edx
0x140016f22  mov     eax, 80h
0x140016f27  cmovz   edx, eax
0x140016f2a  mov     [rsp+0B8h+var_68], edx
0x140016f2e  test    r14b, r14b
0x140016f31  jz      short loc_140016F3E
0x140016f33  lea     rcx, [rdi+38h]
0x140016f37  call    RtlWriteULongToUser
0x140016f3c  jmp     short loc_140016F41
0x140016f3e  mov     [rdi+38h], edx
0x140016f41  test    r14b, r14b
0x140016f44  jz      short loc_140016F53
0x140016f46  xor     edx, edx
0x140016f48  lea     rcx, [rdi+44h]
0x140016f4c  call    RtlWriteULongToUser
0x140016f51  jmp     short loc_140016F5A
0x140016f53  mov     dword ptr [rdi+44h], 0
0x140016f5a  test    r15b, r15b
0x140016f5d  jnz     short loc_140016F95
0x140016f5f  lea     r15, [rdi+38h]
0x140016f63  test    r14b, r14b
0x140016f66  jz      short loc_140016F72
0x140016f68  mov     rcx, r15
0x140016f6b  call    RtlReadULongFromUser
0x140016f70  jmp     short loc_140016F75
0x140016f72  mov     eax, [r15]
0x140016f75  btr     eax, 0Eh
0x140016f79  test    r14b, r14b
0x140016f7c  jz      short loc_140016F8A
0x140016f7e  mov     edx, eax
0x140016f80  mov     rcx, r15
0x140016f83  call    RtlWriteULongToUser
0x140016f88  jmp     short loc_140016F8D
0x140016f8a  mov     [r15], eax
0x140016f8d  mov     r15b, [rsp+0B8h+arg_18]
0x140016f95  lea     rdx, [rbx+50h]; Src
0x140016f99  lea     rcx, [rdi+50h]; void *
0x140016f9d  mov     r8d, r13d; Size
0x140016fa0  test    r14b, r14b
0x140016fa3  jz      short loc_140016FAC
0x140016fa5  call    RtlCopyToUser
0x140016faa  jmp     short loc_140016FB1
0x140016fac  call    RtlCopyVolatileMemory
0x140016fb1  test    r15b, r15b
0x140016fb4  jnz     short loc_140016FD2
0x140016fb6  test    r14b, r14b
0x140016fb9  jz      short loc_140016FCA
0x140016fbb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140016fbf  lea     rcx, [rdi+48h]
0x140016fc3  call    RtlWriteULong64ToUser
0x140016fc8  jmp     short loc_140016FD2
0x140016fca  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x140016fd2  test    r14b, r14b
0x140016fd5  jz      short loc_140016FE3
0x140016fd7  xor     edx, edx
0x140016fd9  mov     rcx, rdi
0x140016fdc  call    RtlWriteULongToUser
0x140016fe1  jmp     short loc_140016FE9
0x140016fe3  mov     dword ptr [rdi], 0
0x140016fe9  mov     rax, [rsp+0B8h+arg_48]
0x140016ff1  mov     [rax], rdi
0x140016ff4  lea     edi, [r13+50h]
0x140016ff8  jmp     loc_1400172CD
0x140016ffd  mov     r13d, [rbx+3Ch]
0x140017001  lea     r12d, [r13+50h]
0x140017005  mov     eax, [rsp+0B8h+arg_38]
0x14001700c  cmp     eax, r12d
0x14001700f  jnb     short loc_140017022
0x140017011  cmp     eax, 50h ; 'P'
0x140017014  jb      loc_1400176DE
0x14001701a  test    dl, dl
0x14001701c  jz      loc_1400176DE
0x140017022  add     eax, 0FFFFFFB0h
0x140017025  cmp     r13d, eax
0x140017028  cmovnb  r13d, eax
0x14001702c  mov     [rsp+0B8h+var_78], 1
0x140017031  mov     r14b, [rsp+0B8h+arg_40]
0x140017039  mov     r8d, 38h ; '8'; Size
0x14001703f  mov     rdx, rbx; Src
0x140017042  mov     rdi, [rsp+0B8h+arg_30]
0x14001704a  mov     rcx, rdi; void *
0x14001704d  test    r14b, r14b
0x140017050  jz      short loc_140017059
0x140017052  call    RtlCopyToUser
0x140017057  jmp     short loc_14001705E
0x140017059  call    RtlCopyVolatileMemory
0x14001705e  mov     r8d, [rbx+44h]
0x140017062  cmp     r8d, [rsp+0B8h+arg_20]
0x14001706a  jnz     short loc_1400170CD
0x14001706c  mov     edx, [rbx+38h]
0x14001706f  mov     [rsp+0B8h+var_60], edx
0x140017073  mov     eax, edx
0x140017075  btr     eax, 0Ah
0x140017079  mov     [rsp+0B8h+var_60], eax
0x14001707d  mov     eax, edx
0x14001707f  and     eax, 0FFFFEBFFh
0x140017084  mov     [rsp+0B8h+var_60], eax
0x140017088  and     edx, 0FFFFE9FFh
0x14001708e  mov     [rsp+0B8h+var_60], edx
0x140017092  mov     eax, 80h
0x140017097  cmovz   edx, eax
0x14001709a  mov     [rsp+0B8h+var_60], edx
0x14001709e  test    r14b, r14b
0x1400170a1  jz      short loc_1400170AE
0x1400170a3  lea     rcx, [rdi+38h]
0x1400170a7  call    RtlWriteULongToUser
0x1400170ac  jmp     short loc_1400170B1
0x1400170ae  mov     [rdi+38h], edx
0x1400170b1  lea     rcx, [rdi+40h]
0x1400170b5  mov     eax, [rbx+40h]
0x1400170b8  test    r14b, r14b
0x1400170bb  jz      loc_140017168
0x1400170c1  mov     edx, eax
0x1400170c3  call    RtlWriteULongToUser
0x1400170c8  jmp     loc_14001716A
0x1400170cd  mov     edx, [rsp+0B8h+arg_28]
0x1400170d4  test    edx, 0FFF0000h
0x1400170da  jnz     short loc_140017138
0x1400170dc  cmp     edx, 2
0x1400170df  jbe     short loc_140017138
0x1400170e1  mov     eax, edx
0x1400170e3  and     eax, 0C0000000h
0x1400170e8  cmp     eax, 40000000h
0x1400170ed  jz      short loc_140017138
0x1400170ef  mov     eax, edx
0x1400170f1  mov     ecx, 30000000h
0x1400170f6  and     eax, ecx
0x1400170f8  cmp     eax, ecx
0x1400170fa  jz      short loc_140017138
0x1400170fc  cmp     r8d, edx
0x1400170ff  jnz     short loc_140017138
0x140017101  mov     edx, [rbx+38h]
0x140017104  mov     [rsp+0B8h+var_58], edx
0x140017108  mov     eax, edx
0x14001710a  btr     eax, 0Ah
0x14001710e  mov     [rsp+0B8h+var_58], eax
0x140017112  mov     eax, edx
0x140017114  and     eax, 0FFFFEBFFh
0x140017119  mov     [rsp+0B8h+var_58], eax
0x14001711d  and     edx, 0FFFFE9FFh
0x140017123  mov     [rsp+0B8h+var_58], edx
0x140017127  mov     eax, 80h
0x14001712c  cmovz   edx, eax
0x14001712f  mov     [rsp+0B8h+var_58], edx
0x140017133  jmp     loc_14001709E
0x140017138  mov     eax, [rbx+38h]
0x14001713b  lea     rcx, [rdi+38h]
0x14001713f  test    r14b, r14b
0x140017142  jz      short loc_14001714D
0x140017144  mov     edx, eax
0x140017146  call    RtlWriteULongToUser
0x14001714b  jmp     short loc_14001714F
0x14001714d  mov     [rcx], eax
0x14001714f  lea     rcx, [rdi+40h]
0x140017153  test    dword ptr [rbx+38h], 400h
0x14001715a  jz      loc_1400170B5
0x140017160  mov     eax, [rbx+44h]
0x140017163  jmp     loc_1400170B8
0x140017168  mov     [rcx], eax
0x14001716a  test    r15b, r15b
0x14001716d  jnz     short loc_14001719D
0x14001716f  lea     r15, [rdi+38h]
0x140017173  test    r14b, r14b
0x140017176  jz      short loc_140017182
0x140017178  mov     rcx, r15
0x14001717b  call    RtlReadULongFromUser
0x140017180  jmp     short loc_140017185
0x140017182  mov     eax, [r15]
0x140017185  btr     eax, 0Eh
0x140017189  test    r14b, r14b
0x14001718c  jz      short loc_14001719A
0x14001718e  mov     edx, eax
0x140017190  mov     rcx, r15
0x140017193  call    RtlWriteULongToUser
0x140017198  jmp     short loc_14001719D
0x14001719a  mov     [r15], eax
0x14001719d  mov     rax, [rbx+48h]
0x1400171a1  lea     r15, [rdi+48h]
0x1400171a5  test    r14b, r14b
0x1400171a8  jz      short loc_1400171B7
0x1400171aa  mov     rdx, rax
0x1400171ad  mov     rcx, r15
0x1400171b0  call    RtlWriteULong64ToUser
0x1400171b5  jmp     short loc_1400171BA
0x1400171b7  mov     [r15], rax
0x1400171ba  cmp     [rsp+0B8h+arg_18], 0
0x1400171c2  jnz     short loc_1400171DE
0x1400171c4  test    r14b, r14b
0x1400171c7  jz      short loc_1400171D7
0x1400171c9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400171cd  mov     rcx, r15
  ... truncated ...
```
