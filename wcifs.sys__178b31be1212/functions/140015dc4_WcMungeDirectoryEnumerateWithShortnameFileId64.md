# WcMungeDirectoryEnumerateWithShortnameFileId64

- ea: `0x140015dc4`
- end: `0x14001672d`
- name: `WcMungeDirectoryEnumerateWithShortnameFileId64`
- size: `2409`
- prototype: `__int64 __fastcall(int, char, __int64, char, int, unsigned int, _DWORD *, unsigned int, char, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140029060`

## callees

- `0x1400020c4`
- `0x140007c90`
- `0x140007cb0`
- `0x14001439c`
- `0x140014400`
- `0x14001443c`
- `0x14001449c`
- `0x1400144e4`
- `0x14001452c`
- `0x140015dc4`

## pseudocode

```c
__int64 __fastcall WcMungeDirectoryEnumerateWithShortnameFileId64(
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
  char v11; // r14
  unsigned int v13; // r15d
  unsigned int v14; // edi
  unsigned int v15; // r13d
  unsigned int v16; // r12d
  char v17; // dl
  size_t v18; // r8
  void *v19; // rdx
  void *v20; // rcx
  int v21; // r8d
  unsigned int v22; // edx
  unsigned int *v23; // r14
  int ULongFromUser; // eax
  unsigned int v25; // eax
  void *v26; // rdx
  void *v27; // rcx
  unsigned int v28; // r13d
  int v29; // r8d
  unsigned int v30; // edx
  int *v31; // rcx
  int v32; // eax
  int v33; // eax
  int *v34; // rcx
  unsigned int *v35; // r14
  int v36; // eax
  unsigned int v37; // eax
  _QWORD *v38; // rax
  char v39; // dl
  char *v40; // r14
  size_t v41; // r8
  void *v42; // rdx
  void *v43; // rcx
  void *v44; // rcx
  int v45; // eax
  int *v46; // rcx
  void *v47; // rdx
  void *v48; // rcx
  unsigned int v49; // r13d
  unsigned int v50; // r12d
  int v51; // r8d
  unsigned int v52; // edx
  int *v53; // rcx
  int v54; // eax
  int v55; // eax
  int *v56; // rcx
  unsigned int *v57; // r14
  int v58; // eax
  unsigned int v59; // eax
  char v60; // dl
  size_t v61; // r8
  void *v62; // rdx
  void *v63; // rcx
  int v64; // eax
  int *v65; // rcx
  void *v66; // rdx
  void *v67; // rcx
  int v68; // eax

  v11 = a4;
  v13 = 0;
  v14 = 0;
  if ( a1 != 3 )
  {
    if ( a1 != 37 )
    {
      if ( a1 != 79 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_sDd(
            wil_details_featureDescriptors_a->DeviceExtension,
            3,
            18,
            17,
            (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
            197,
            a1,
            0);
        v13 = -1073741637;
        goto LABEL_203;
      }
      v15 = *(_DWORD *)(a3 + 60);
      v16 = v15 + 106;
      if ( a8 < v15 + 106 && (a8 < 0x6A || !a2) )
        goto LABEL_203;
      if ( v15 >= a8 - 106 )
        v15 = a8 - 106;
      if ( a9 )
        RtlCopyToUser(a7, (void *)a3, 0x50u);
      else
        RtlCopyVolatileMemory(a7, (const void *)a3, 0x50u);
      if ( v11 )
      {
        v17 = *(_BYTE *)(a3 + 80);
        if ( (unsigned __int8)v17 <= 0x18u )
        {
          if ( a9 )
            RtlWriteUCharToUser((_BYTE *)a7 + 80, v17);
          else
            *((_BYTE *)a7 + 80) = v17;
          v18 = *(char *)(a3 + 80);
          v19 = (void *)(a3 + 82);
          v20 = (char *)a7 + 82;
          if ( a9 )
            RtlCopyToUser(v20, v19, v18);
          else
            RtlCopyVolatileMemory(v20, v19, v18);
LABEL_31:
          v21 = *(_DWORD *)(a3 + 68);
          if ( v21 == a5 )
          {
            v22 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
            if ( !v22 )
              v22 = 128;
          }
          else
          {
            if ( (a6 & 0xFFF0000) != 0
              || a6 <= 2
              || (a6 & 0xC0000000) == 0x40000000
              || (a6 & 0x30000000) == 0x30000000
              || v21 != a6 )
            {
LABEL_48:
              if ( !v11 )
              {
                v23 = a7 + 14;
                if ( a9 )
                  ULongFromUser = RtlReadULongFromUser(a7 + 14);
                else
                  ULongFromUser = *v23;
                v25 = ULongFromUser & 0xFFFFBFFF;
                if ( a9 )
                  RtlWriteULongToUser(a7 + 14, v25);
                else
                  *v23 = v25;
              }
              v26 = (void *)(a3 + 106);
              v27 = (char *)a7 + 106;
              if ( a9 )
                RtlCopyToUser(v27, v26, v15);
              else
                RtlCopyVolatileMemory(v27, v26, v15);
              if ( a9 )
                RtlWriteULongToUser(a7, 0);
              else
                *a7 = 0;
              *a10 = a7;
              v14 = v15 + 106;
              goto LABEL_137;
            }
            v22 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
            if ( !v22 )
              v22 = 128;
          }
          if ( a9 )
            RtlWriteULongToUser(a7 + 14, v22);
          else
            a7[14] = v22;
          if ( a9 )
            RtlWriteULongToUser(a7 + 17, 0);
          else
            a7[17] = 0;
          goto LABEL_48;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_sDd(
            wil_details_featureDescriptors_a->DeviceExtension,
            2,
            18,
            16,
            (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
            155,
            *(char *)(a3 + 80),
            1);
      }
      else if ( a9 )
      {
        RtlWriteULong64ToUser((_QWORD *)a7 + 9, -1);
      }
      else
      {
        *((_QWORD *)a7 + 9) = -1;
      }
      if ( a9 )
        RtlWriteUCharToUser((_BYTE *)a7 + 80, 0);
      else
        *((_BYTE *)a7 + 80) = 0;
      goto LABEL_31;
    }
    v28 = *(_DWORD *)(a3 + 60);
    v16 = v28 + 104;
    if ( a8 < v28 + 104 && (a8 < 0x68 || !a2) )
      goto LABEL_203;
    if ( v28 >= a8 - 104 )
      v28 = a8 - 104;
    if ( a9 )
      RtlCopyToUser(a7, (void *)a3, 0x38u);
    else
      RtlCopyVolatileMemory(a7, (const void *)a3, 0x38u);
    v29 = *(_DWORD *)(a3 + 68);
    if ( v29 == a5 )
    {
      v30 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
      if ( !v30 )
        v30 = 128;
    }
    else
    {
      if ( (a6 & 0xFFF0000) != 0
        || a6 <= 2
        || (a6 & 0xC0000000) == 0x40000000
        || (a6 & 0x30000000) == 0x30000000
        || v29 != a6 )
      {
        v33 = *(_DWORD *)(a3 + 56);
        v34 = a7 + 14;
        if ( a9 )
          RtlWriteULongToUser(v34, v33);
        else
          *v34 = v33;
        v31 = a7 + 16;
        if ( (*(_DWORD *)(a3 + 56) & 0x400) != 0 )
        {
          v32 = *(_DWORD *)(a3 + 68);
LABEL_78:
          if ( a9 )
            RtlWriteULongToUser(v31, v32);
          else
            *v31 = v32;
          if ( !v11 )
          {
            v35 = a7 + 14;
            if ( a9 )
              v36 = RtlReadULongFromUser(a7 + 14);
            else
              v36 = *v35;
            v37 = v36 & 0xFFFFBFFF;
            if ( a9 )
              RtlWriteULongToUser(a7 + 14, v37);
            else
              *v35 = v37;
            v11 = a4;
          }
          v38 = a7 + 24;
          if ( v11 )
          {
            if ( a9 )
              RtlWriteULong64ToUser((_QWORD *)a7 + 12, *(_QWORD *)(a3 + 72));
            else
              *v38 = *(_QWORD *)(a3 + 72);
            v39 = *(_BYTE *)(a3 + 80);
            if ( (unsigned __int8)v39 <= 0x18u )
            {
              v40 = (char *)(a7 + 17);
              if ( a9 )
                RtlWriteUCharToUser((_BYTE *)a7 + 68, v39);
              else
                *v40 = v39;
              v41 = *(char *)(a3 + 80);
              v42 = (void *)(a3 + 82);
              v43 = (char *)a7 + 70;
              if ( a9 )
                RtlCopyToUser(v43, v42, v41);
              else
                RtlCopyVolatileMemory(v43, v42, v41);
              goto LABEL_121;
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_sDd(
                wil_details_featureDescriptors_a->DeviceExtension,
                2,
                18,
                15,
                (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
                95,
                *(char *)(a3 + 80),
                1);
          }
          else if ( a9 )
          {
            RtlWriteULong64ToUser((_QWORD *)a7 + 12, -1);
          }
          else
          {
            *v38 = -1;
          }
          v40 = (char *)(a7 + 17);
          if ( a9 )
            RtlWriteUCharToUser((_BYTE *)a7 + 68, 0);
          else
            *v40 = 0;
LABEL_121:
          if ( a9 )
            RtlWriteUCharToUser(v40, 0);
          else
            *v40 = 0;
          v44 = (char *)a7 + 70;
          if ( a9 )
            RtlSetUserMemory(v44, 0, 0x18u);
          else
            RtlSetVolatileMemory(v44, 0, 0x18u);
          v45 = *(_DWORD *)(a3 + 60);
          v46 = a7 + 15;
          if ( a9 )
            RtlWriteULongToUser(v46, v45);
          else
            *v46 = v45;
          v47 = (void *)(a3 + 106);
          v48 = a7 + 26;
          if ( a9 )
            RtlCopyToUser(v48, v47, v28);
          else
            RtlCopyVolatileMemory(v48, v47, v28);
          if ( a9 )
            RtlWriteULongToUser(a7, 0);
          else
            *a7 = 0;
          *a10 = a7;
          v14 = v28 + 104;
LABEL_137:
          if ( v14 < v16 )
            v13 = -2147483643;
          goto LABEL_203;
        }
LABEL_77:
        v32 = *(_DWORD *)(a3 + 64);
        goto LABEL_78;
      }
      v30 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
      if ( !v30 )
        v30 = 128;
    }
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v30);
    else
      a7[14] = v30;
    v31 = a7 + 16;
    goto LABEL_77;
  }
  v49 = *(_DWORD *)(a3 + 60);
  v50 = v49 + 94;
  if ( a8 < v49 + 94 && (a8 < 0x5E || !a2) )
    goto LABEL_203;
  if ( v49 >= a8 - 94 )
    v49 = a8 - 94;
  if ( a9 )
    RtlCopyToUser(a7, (void *)a3, 0x38u);
  else
    RtlCopyVolatileMemory(a7, (const void *)a3, 0x38u);
  v51 = *(_DWORD *)(a3 + 68);
  if ( v51 == a5 )
  {
    v52 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
    if ( !v52 )
      v52 = 128;
LABEL_150:
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v52);
    else
      a7[14] = v52;
    v53 = a7 + 16;
LABEL_154:
    v54 = *(_DWORD *)(a3 + 64);
    goto LABEL_155;
  }
  if ( (a6 & 0xFFF0000) == 0
    && a6 > 2
    && (a6 & 0xC0000000) != 0x40000000
    && (a6 & 0x30000000) != 0x30000000
    && v51 == a6 )
  {
    v52 = *(_DWORD *)(a3 + 56) & 0xFFFFE9FF;
    if ( !v52 )
      v52 = 128;
    goto LABEL_150;
  }
  v55 = *(_DWORD *)(a3 + 56);
  v56 = a7 + 14;
  if ( a9 )
    RtlWriteULongToUser(v56, v55);
  else
    *v56 = v55;
  v53 = a7 + 16;
  if ( (*(_DWORD *)(a3 + 56) & 0x400) == 0 )
    goto LABEL_154;
  v54 = *(_DWORD *)(a3 + 68);
LABEL_155:
  if ( a9 )
    RtlWriteULongToUser(v53, v54);
  else
    *v53 = v54;
  if ( v11 )
    goto LABEL_179;
  v57 = a7 + 14;
  v58 = a9 ? RtlReadULongFromUser(a7 + 14) : *v57;
  v59 = v58 & 0xFFFFBFFF;
  if ( a9 )
    RtlWriteULongToUser(a7 + 14, v59);
  else
    *v57 = v59;
  if ( a4 )
  {
LABEL_179:
    v60 = *(_BYTE *)(a3 + 80);
    if ( (unsigned __int8)v60 <= 0x18u )
    {
      if ( a9 )
        RtlWriteUCharToUser((_BYTE *)a7 + 68, v60);
      else
        *((_BYTE *)a7 + 68) = v60;
      v61 = *(char *)(a3 + 80);
      v62 = (void *)(a3 + 82);
      v63 = (char *)a7 + 70;
      if ( a9 )
        RtlCopyToUser(v63, v62, v61);
      else
        RtlCopyVolatileMemory(v63, v62, v61);
      goto LABEL_191;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        2,
        18,
        14,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        17,
        *(char *)(a3 + 80),
        1);
  }
  if ( a9 )
    RtlWriteUCharToUser((_BYTE *)a7 + 68, 0);
  else
    *((_BYTE *)a7 + 68) = 0;
LABEL_191:
  v64 = *(_DWORD *)(a3 + 60);
  v65 = a7 + 15;
  if ( a9 )
    RtlWriteULongToUser(v65, v64);
  else
    *v65 = v64;
  v66 = (void *)(a3 + 106);
  v67 = (char *)a7 + 94;
  if ( a9 )
    RtlCopyToUser(v67, v66, v49);
  else
    RtlCopyVolatileMemory(v67, v66, v49);
  if ( a9 )
    RtlWriteULongToUser(a7, 0);
  else
    *a7 = 0;
  *a10 = a7;
  v14 = v49 + 94;
  v68 = 0;
  if ( v49 + 94 < v50 )
    v68 = -2147483643;
  v13 = v68;
LABEL_203:
  *a11 = v14;
  return v13;
}

```

## disassembly

```asm
0x140015dc4  mov     rax, rsp
0x140015dc7  mov     [rax+8], rbx
0x140015dcb  mov     [rax+10h], rsi
0x140015dcf  mov     [rax+20h], r9b
0x140015dd3  push    rdi
0x140015dd4  push    r12
0x140015dd6  push    r13
0x140015dd8  push    r14
0x140015dda  push    r15
0x140015ddc  sub     rsp, 80h
0x140015de3  mov     r14b, r9b
0x140015de6  mov     rbx, r8
0x140015de9  mov     r8d, ecx
0x140015dec  mov     byte ptr [rax-68h], 0
0x140015df0  xor     r15d, r15d
0x140015df3  xor     edi, edi
0x140015df5  cmp     ecx, 3
0x140015df8  jz      loc_140016429
0x140015dfe  cmp     ecx, 25h ; '%'
0x140015e01  jz      loc_1400160EB
0x140015e07  cmp     ecx, 4Fh ; 'O'
0x140015e0a  jz      short loc_140015E69
0x140015e0c  lea     rcx, WPP_RECORDER_INITIALIZED
0x140015e13  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140015e1a  jz      short loc_140015E59
0x140015e1c  lea     r9d, [r15+11h]
0x140015e20  mov     [rax-70h], r8d
0x140015e24  mov     dword ptr [rax-78h], 3C5h
0x140015e2b  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140015e32  mov     [rsp+0A8h+var_80], rax
0x140015e37  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x140015e3e  mov     [rsp+0A8h+var_88], rax
0x140015e43  lea     r8d, [r15+12h]
0x140015e47  mov     dl, 3
0x140015e49  mov     rcx, cs:wil_details_featureDescriptors_a
0x140015e50  mov     rcx, [rcx+40h]
0x140015e54  call    WPP_RECORDER_SF_sDd
0x140015e59  mov     r15d, 0C00000BBh
0x140015e5f  mov     [rsp+0A8h+var_30], r15d
0x140015e64  jmp     loc_1400166F5
0x140015e69  mov     r13d, [rbx+3Ch]
0x140015e6d  lea     r12d, [r13+6Ah]
0x140015e71  mov     eax, [rsp+0A8h+arg_38]
0x140015e78  cmp     eax, r12d
0x140015e7b  jnb     short loc_140015E8E
0x140015e7d  cmp     eax, 6Ah ; 'j'
0x140015e80  jb      loc_1400166F5
0x140015e86  test    dl, dl
0x140015e88  jz      loc_1400166F5
0x140015e8e  add     eax, 0FFFFFF96h
0x140015e91  cmp     r13d, eax
0x140015e94  cmovnb  r13d, eax
0x140015e98  mov     [rsp+0A8h+var_68], 1
0x140015e9d  mov     sil, [rsp+0A8h+arg_40]
0x140015ea5  mov     r8d, 50h ; 'P'; Size
0x140015eab  mov     rdx, rbx; Src
0x140015eae  mov     rdi, [rsp+0A8h+arg_30]
0x140015eb6  mov     rcx, rdi; void *
0x140015eb9  test    sil, sil
0x140015ebc  jz      short loc_140015EC5
0x140015ebe  call    RtlCopyToUser
0x140015ec3  jmp     short loc_140015ECA
0x140015ec5  call    RtlCopyVolatileMemory
0x140015eca  test    r14b, r14b
0x140015ecd  jz      loc_140015F67
0x140015ed3  movsx   edx, byte ptr [rbx+50h]
0x140015ed7  cmp     dl, 18h
0x140015eda  ja      short loc_140015F15
0x140015edc  test    sil, sil
0x140015edf  jz      short loc_140015EEC
0x140015ee1  lea     rcx, [rdi+50h]
0x140015ee5  call    RtlWriteUCharToUser
0x140015eea  jmp     short loc_140015EEF
0x140015eec  mov     [rdi+50h], dl
0x140015eef  movsx   r8, byte ptr [rbx+50h]; Size
0x140015ef4  lea     rdx, [rbx+52h]; Src
0x140015ef8  lea     rcx, [rdi+52h]; void *
0x140015efc  test    sil, sil
0x140015eff  jz      short loc_140015F0B
0x140015f01  call    RtlCopyToUser
0x140015f06  jmp     loc_140015F99
0x140015f0b  call    RtlCopyVolatileMemory
0x140015f10  jmp     loc_140015F99
0x140015f15  lea     rcx, WPP_RECORDER_INITIALIZED
0x140015f1c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140015f23  jz      short loc_140015F83
0x140015f25  mov     r9d, 10h
0x140015f2b  mov     [rsp+0A8h+var_70], edx
0x140015f2f  mov     [rsp+0A8h+var_78], 39Bh
0x140015f37  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140015f3e  mov     [rsp+0A8h+var_80], rax
0x140015f43  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x140015f4a  mov     [rsp+0A8h+var_88], rax
0x140015f4f  lea     r8d, [r9+2]
0x140015f53  mov     dl, 2
0x140015f55  mov     rcx, cs:wil_details_featureDescriptors_a
0x140015f5c  mov     rcx, [rcx+40h]
0x140015f60  call    WPP_RECORDER_SF_sDd
0x140015f65  jmp     short loc_140015F83
0x140015f67  test    sil, sil
0x140015f6a  jz      short loc_140015F7B
0x140015f6c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140015f70  lea     rcx, [rdi+48h]
0x140015f74  call    RtlWriteULong64ToUser
0x140015f79  jmp     short loc_140015F83
0x140015f7b  mov     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x140015f83  test    sil, sil
0x140015f86  jz      short loc_140015F95
0x140015f88  xor     edx, edx
0x140015f8a  lea     rcx, [rdi+50h]
0x140015f8e  call    RtlWriteUCharToUser
0x140015f93  jmp     short loc_140015F99
0x140015f95  mov     byte ptr [rdi+50h], 0
0x140015f99  mov     r8d, [rbx+44h]
0x140015f9d  cmp     r8d, [rsp+0A8h+arg_20]
0x140015fa5  jnz     short loc_140015FDB
0x140015fa7  mov     edx, [rbx+38h]
0x140015faa  mov     [rsp+0A8h+var_60], edx
0x140015fae  mov     eax, edx
0x140015fb0  btr     eax, 0Ah
0x140015fb4  mov     [rsp+0A8h+var_60], eax
0x140015fb8  mov     eax, edx
0x140015fba  and     eax, 0FFFFEBFFh
0x140015fbf  mov     [rsp+0A8h+var_60], eax
0x140015fc3  and     edx, 0FFFFE9FFh
0x140015fc9  mov     [rsp+0A8h+var_60], edx
0x140015fcd  mov     eax, 80h
0x140015fd2  cmovz   edx, eax
0x140015fd5  mov     [rsp+0A8h+var_60], edx
0x140015fd9  jmp     short loc_140016045
0x140015fdb  mov     edx, [rsp+0A8h+arg_28]
0x140015fe2  test    edx, 0FFF0000h
0x140015fe8  jnz     loc_140016071
0x140015fee  cmp     edx, 2
0x140015ff1  jbe     short loc_140016071
0x140015ff3  mov     eax, edx
0x140015ff5  and     eax, 0C0000000h
0x140015ffa  cmp     eax, 40000000h
0x140015fff  jz      short loc_140016071
0x140016001  mov     eax, edx
0x140016003  mov     ecx, 30000000h
0x140016008  and     eax, ecx
0x14001600a  cmp     eax, ecx
0x14001600c  jz      short loc_140016071
0x14001600e  cmp     r8d, edx
0x140016011  jnz     short loc_140016071
0x140016013  mov     edx, [rbx+38h]
0x140016016  mov     [rsp+0A8h+var_58], edx
0x14001601a  mov     eax, edx
0x14001601c  btr     eax, 0Ah
0x140016020  mov     [rsp+0A8h+var_58], eax
0x140016024  mov     eax, edx
0x140016026  and     eax, 0FFFFEBFFh
0x14001602b  mov     [rsp+0A8h+var_58], eax
0x14001602f  and     edx, 0FFFFE9FFh
0x140016035  mov     [rsp+0A8h+var_58], edx
0x140016039  mov     eax, 80h
0x14001603e  cmovz   edx, eax
0x140016041  mov     [rsp+0A8h+var_58], edx
0x140016045  test    sil, sil
0x140016048  jz      short loc_140016055
0x14001604a  lea     rcx, [rdi+38h]
0x14001604e  call    RtlWriteULongToUser
0x140016053  jmp     short loc_140016058
0x140016055  mov     [rdi+38h], edx
0x140016058  test    sil, sil
0x14001605b  jz      short loc_14001606A
0x14001605d  xor     edx, edx
0x14001605f  lea     rcx, [rdi+44h]
0x140016063  call    RtlWriteULongToUser
0x140016068  jmp     short loc_140016071
0x14001606a  mov     dword ptr [rdi+44h], 0
0x140016071  test    r14b, r14b
0x140016074  jnz     short loc_1400160A4
0x140016076  lea     r14, [rdi+38h]
0x14001607a  test    sil, sil
0x14001607d  jz      short loc_140016089
0x14001607f  mov     rcx, r14
0x140016082  call    RtlReadULongFromUser
0x140016087  jmp     short loc_14001608C
0x140016089  mov     eax, [r14]
0x14001608c  btr     eax, 0Eh
0x140016090  test    sil, sil
0x140016093  jz      short loc_1400160A1
0x140016095  mov     edx, eax
0x140016097  mov     rcx, r14
0x14001609a  call    RtlWriteULongToUser
0x14001609f  jmp     short loc_1400160A4
0x1400160a1  mov     [r14], eax
0x1400160a4  lea     rdx, [rbx+6Ah]; Src
0x1400160a8  lea     rcx, [rdi+6Ah]; void *
0x1400160ac  mov     r8d, r13d; Size
0x1400160af  test    sil, sil
0x1400160b2  jz      short loc_1400160BB
0x1400160b4  call    RtlCopyToUser
0x1400160b9  jmp     short loc_1400160C0
0x1400160bb  call    RtlCopyVolatileMemory
0x1400160c0  test    sil, sil
0x1400160c3  jz      short loc_1400160D1
0x1400160c5  xor     edx, edx
0x1400160c7  mov     rcx, rdi
0x1400160ca  call    RtlWriteULongToUser
0x1400160cf  jmp     short loc_1400160D7
0x1400160d1  mov     dword ptr [rdi], 0
0x1400160d7  mov     rax, [rsp+0A8h+arg_48]
0x1400160df  mov     [rax], rdi
0x1400160e2  lea     edi, [r13+6Ah]
0x1400160e6  jmp     loc_14001640C
0x1400160eb  mov     r13d, [rbx+3Ch]
0x1400160ef  lea     r12d, [r13+68h]
0x1400160f3  mov     eax, [rsp+0A8h+arg_38]
0x1400160fa  cmp     eax, r12d
0x1400160fd  jnb     short loc_140016110
0x1400160ff  cmp     eax, 68h ; 'h'
0x140016102  jb      loc_1400166F5
0x140016108  test    dl, dl
0x14001610a  jz      loc_1400166F5
0x140016110  add     eax, 0FFFFFF98h
0x140016113  cmp     r13d, eax
0x140016116  cmovnb  r13d, eax
0x14001611a  mov     [rsp+0A8h+var_68], 1
0x14001611f  mov     sil, [rsp+0A8h+arg_40]
0x140016127  mov     r8d, 38h ; '8'; Size
0x14001612d  mov     rdx, rbx; Src
0x140016130  mov     rdi, [rsp+0A8h+arg_30]
0x140016138  mov     rcx, rdi; void *
0x14001613b  test    sil, sil
0x14001613e  jz      short loc_140016147
0x140016140  call    RtlCopyToUser
0x140016145  jmp     short loc_14001614C
0x140016147  call    RtlCopyVolatileMemory
0x14001614c  mov     r8d, [rbx+44h]
0x140016150  cmp     r8d, [rsp+0A8h+arg_20]
0x140016158  jnz     short loc_1400161BB
0x14001615a  mov     edx, [rbx+38h]
0x14001615d  mov     [rsp+0A8h+var_50], edx
0x140016161  mov     eax, edx
0x140016163  btr     eax, 0Ah
0x140016167  mov     [rsp+0A8h+var_50], eax
0x14001616b  mov     eax, edx
0x14001616d  and     eax, 0FFFFEBFFh
0x140016172  mov     [rsp+0A8h+var_50], eax
0x140016176  and     edx, 0FFFFE9FFh
0x14001617c  mov     [rsp+0A8h+var_50], edx
0x140016180  mov     eax, 80h
0x140016185  cmovz   edx, eax
0x140016188  mov     [rsp+0A8h+var_50], edx
0x14001618c  test    sil, sil
0x14001618f  jz      short loc_14001619C
0x140016191  lea     rcx, [rdi+38h]
0x140016195  call    RtlWriteULongToUser
0x14001619a  jmp     short loc_14001619F
0x14001619c  mov     [rdi+38h], edx
0x14001619f  lea     rcx, [rdi+40h]
0x1400161a3  mov     eax, [rbx+40h]
0x1400161a6  test    sil, sil
0x1400161a9  jz      loc_140016256
0x1400161af  mov     edx, eax
0x1400161b1  call    RtlWriteULongToUser
0x1400161b6  jmp     loc_140016258
0x1400161bb  mov     edx, [rsp+0A8h+arg_28]
0x1400161c2  test    edx, 0FFF0000h
0x1400161c8  jnz     short loc_140016226
0x1400161ca  cmp     edx, 2
0x1400161cd  jbe     short loc_140016226
0x1400161cf  mov     eax, edx
0x1400161d1  and     eax, 0C0000000h
0x1400161d6  cmp     eax, 40000000h
0x1400161db  jz      short loc_140016226
0x1400161dd  mov     eax, edx
0x1400161df  mov     ecx, 30000000h
0x1400161e4  and     eax, ecx
0x1400161e6  cmp     eax, ecx
0x1400161e8  jz      short loc_140016226
0x1400161ea  cmp     r8d, edx
0x1400161ed  jnz     short loc_140016226
0x1400161ef  mov     edx, [rbx+38h]
0x1400161f2  mov     [rsp+0A8h+var_48], edx
0x1400161f6  mov     eax, edx
0x1400161f8  btr     eax, 0Ah
0x1400161fc  mov     [rsp+0A8h+var_48], eax
0x140016200  mov     eax, edx
0x140016202  and     eax, 0FFFFEBFFh
0x140016207  mov     [rsp+0A8h+var_48], eax
0x14001620b  and     edx, 0FFFFE9FFh
0x140016211  mov     [rsp+0A8h+var_48], edx
0x140016215  mov     eax, 80h
0x14001621a  cmovz   edx, eax
0x14001621d  mov     [rsp+0A8h+var_48], edx
0x140016221  jmp     loc_14001618C
0x140016226  mov     eax, [rbx+38h]
0x140016229  lea     rcx, [rdi+38h]
0x14001622d  test    sil, sil
0x140016230  jz      short loc_14001623B
0x140016232  mov     edx, eax
0x140016234  call    RtlWriteULongToUser
0x140016239  jmp     short loc_14001623D
0x14001623b  mov     [rcx], eax
0x14001623d  lea     rcx, [rdi+40h]
0x140016241  test    dword ptr [rbx+38h], 400h
  ... truncated ...
```
