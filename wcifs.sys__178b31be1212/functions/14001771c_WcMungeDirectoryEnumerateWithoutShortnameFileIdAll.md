# WcMungeDirectoryEnumerateWithoutShortnameFileIdAll

- ea: `0x14001771c`
- end: `0x1400179ee`
- name: `WcMungeDirectoryEnumerateWithoutShortnameFileIdAll`
- size: `722`
- prototype: `__int64 __fastcall(int, char, _DWORD *, char, int, unsigned int, unsigned int *, unsigned int, char, unsigned int **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
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
- `0x1400144e4`
- `0x14001452c`
- `0x14001771c`

## pseudocode

```c
__int64 __fastcall WcMungeDirectoryEnumerateWithoutShortnameFileIdAll(
        int a1,
        char a2,
        _DWORD *a3,
        char a4,
        int a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int a8,
        char a9,
        unsigned int **a10,
        unsigned int *a11)
{
  unsigned int v13; // edi
  unsigned int v14; // ebx
  _UNKNOWN **v15; // rdx
  unsigned int v16; // r13d
  unsigned int v17; // r14d
  int v18; // edx
  unsigned int v19; // edx
  unsigned int *v20; // r14
  int ULongFromUser; // eax
  unsigned int v22; // eax
  void *v23; // rdx
  void *v24; // rcx
  void *v25; // rcx
  unsigned int v27; // [rsp+A0h] [rbp+18h]

  v13 = 0;
  v14 = 0;
  if ( a1 != 80 )
  {
    v15 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 3;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        (_DWORD)v15,
        18,
        18,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        63,
        a1,
        0);
    }
    v13 = -1073741637;
    goto LABEL_53;
  }
  v16 = a3[15];
  v17 = v16 + 96;
  v27 = v16 + 96;
  if ( a8 < v16 + 96 && (a8 < 0x60 || !a2) )
    goto LABEL_53;
  if ( v16 >= a8 - 96 )
    v16 = a8 - 96;
  if ( a9 )
    RtlCopyToUser(a7, a3, 0x60u);
  else
    RtlCopyVolatileMemory(a7, a3, 0x60u);
  v18 = a3[17];
  if ( v18 == a5 )
  {
    v19 = a3[14] & 0xFFFFE9FF;
    if ( !v19 )
      v19 = 128;
LABEL_24:
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v19);
    else
      a7[14] = v19;
    if ( a9 )
      RtlWriteULongToUser(a7 + 17, 0);
    else
      a7[17] = 0;
    goto LABEL_30;
  }
  if ( (a6 & 0xFFF0000) == 0
    && a6 > 2
    && (a6 & 0xC0000000) != 0x40000000
    && (a6 & 0x30000000) != 0x30000000
    && v18 == a6 )
  {
    v19 = a3[14] & 0xFFFFE9FF;
    if ( !v19 )
      v19 = 128;
    goto LABEL_24;
  }
LABEL_30:
  if ( !a4 )
  {
    v20 = a7 + 14;
    if ( a9 )
      ULongFromUser = RtlReadULongFromUser(a7 + 14);
    else
      ULongFromUser = *v20;
    v22 = ULongFromUser & 0xFFFFBFFF;
    if ( a9 )
      RtlWriteULongToUser(a7 + 14, v22);
    else
      *v20 = v22;
    v17 = v27;
  }
  v23 = a3 + 24;
  v24 = a7 + 24;
  if ( a9 )
    RtlCopyToUser(v24, v23, v16);
  else
    RtlCopyVolatileMemory(v24, v23, v16);
  if ( !a4 )
  {
    if ( a9 )
      RtlWriteULong64ToUser((_QWORD *)a7 + 9, -1);
    else
      *((_QWORD *)a7 + 9) = -1;
    v25 = a7 + 20;
    if ( a9 )
      RtlSetUserMemory(v25, 0xFFu, 0x10u);
    else
      RtlSetVolatileMemory(v25, 255, 0x10u);
  }
  if ( a9 )
    RtlWriteULongToUser(a7, 0);
  else
    *a7 = 0;
  *a10 = a7;
  v14 = v16 + 96;
  if ( v16 + 96 < v17 )
    v13 = -2147483643;
LABEL_53:
  *a11 = v14;
  return v13;
}

```

## disassembly

```asm
0x14001771c  mov     rax, rsp
0x14001771f  mov     [rax+8], rbx
0x140017723  mov     [rax+10h], rsi
0x140017727  push    rdi
0x140017728  push    r12
0x14001772a  push    r13
0x14001772c  push    r14
0x14001772e  push    r15
0x140017730  sub     rsp, 60h
0x140017734  mov     r12b, r9b
0x140017737  mov     r15, r8
0x14001773a  mov     byte ptr [rax-48h], 0
0x14001773e  xor     edi, edi
0x140017740  xor     ebx, ebx
0x140017742  cmp     ecx, 50h ; 'P'
0x140017745  jz      short loc_14001779C
0x140017747  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001774e  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140017755  jz      short loc_140017792
0x140017757  lea     r8d, [rdi+12h]
0x14001775b  mov     r9d, r8d
0x14001775e  mov     [rax-50h], ecx
0x140017761  mov     dword ptr [rax-58h], 43Fh
0x140017768  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x14001776f  mov     [rsp+88h+var_60], rax
0x140017774  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x14001777b  mov     [rsp+88h+var_68], rax
0x140017780  mov     dl, 3
0x140017782  mov     rcx, cs:wil_details_featureDescriptors_a
0x140017789  mov     rcx, [rcx+40h]
0x14001778d  call    WPP_RECORDER_SF_sDd
0x140017792  mov     edi, 0C00000BBh
0x140017797  jmp     loc_1400179B8
0x14001779c  mov     r13d, [r8+3Ch]
0x1400177a0  lea     r14d, [r13+60h]
0x1400177a4  mov     [rsp+88h+arg_10], r14d
0x1400177ac  mov     eax, [rsp+88h+arg_38]
0x1400177b3  cmp     eax, r14d
0x1400177b6  jnb     short loc_1400177C9
0x1400177b8  cmp     eax, 60h ; '`'
0x1400177bb  jb      loc_1400179BC
0x1400177c1  test    dl, dl
0x1400177c3  jz      loc_1400179BC
0x1400177c9  add     eax, 0FFFFFFA0h
0x1400177cc  cmp     r13d, eax
0x1400177cf  cmovnb  r13d, eax
0x1400177d3  mov     [rsp+88h+var_48], 1
0x1400177d8  mov     sil, [rsp+88h+arg_40]
0x1400177e0  mov     r8d, 60h ; '`'; Size
0x1400177e6  mov     rdx, r15; Src
0x1400177e9  mov     rbx, [rsp+88h+arg_30]
0x1400177f1  mov     rcx, rbx; void *
0x1400177f4  test    sil, sil
0x1400177f7  jz      short loc_140017800
0x1400177f9  call    RtlCopyToUser
0x1400177fe  jmp     short loc_140017805
0x140017800  call    RtlCopyVolatileMemory
0x140017805  mov     edx, [r15+44h]
0x140017809  cmp     edx, [rsp+88h+arg_20]
0x140017810  jnz     short loc_140017847
0x140017812  mov     edx, [r15+38h]
0x140017816  mov     [rsp+88h+var_40], edx
0x14001781a  mov     eax, edx
0x14001781c  btr     eax, 0Ah
0x140017820  mov     [rsp+88h+var_40], eax
0x140017824  mov     eax, edx
0x140017826  and     eax, 0FFFFEBFFh
0x14001782b  mov     [rsp+88h+var_40], eax
0x14001782f  and     edx, 0FFFFE9FFh
0x140017835  mov     [rsp+88h+var_40], edx
0x140017839  mov     eax, 80h
0x14001783e  cmovz   edx, eax
0x140017841  mov     [rsp+88h+var_40], edx
0x140017845  jmp     short loc_1400178B8
0x140017847  mov     ecx, [rsp+88h+arg_28]
0x14001784e  test    ecx, 0FFF0000h
0x140017854  jnz     loc_1400178E4
0x14001785a  cmp     ecx, 2
0x14001785d  jbe     loc_1400178E4
0x140017863  mov     eax, ecx
0x140017865  and     eax, 0C0000000h
0x14001786a  cmp     eax, 40000000h
0x14001786f  jz      short loc_1400178E4
0x140017871  mov     eax, ecx
0x140017873  mov     r8d, 30000000h
0x140017879  and     eax, r8d
0x14001787c  cmp     eax, r8d
0x14001787f  jz      short loc_1400178E4
0x140017881  cmp     edx, ecx
0x140017883  jnz     short loc_1400178E4
0x140017885  mov     edx, [r15+38h]
0x140017889  mov     [rsp+88h+var_38], edx
0x14001788d  mov     eax, edx
0x14001788f  btr     eax, 0Ah
0x140017893  mov     [rsp+88h+var_38], eax
0x140017897  mov     eax, edx
0x140017899  and     eax, 0FFFFEBFFh
0x14001789e  mov     [rsp+88h+var_38], eax
0x1400178a2  and     edx, 0FFFFE9FFh
0x1400178a8  mov     [rsp+88h+var_38], edx
0x1400178ac  mov     eax, 80h
0x1400178b1  cmovz   edx, eax
0x1400178b4  mov     [rsp+88h+var_38], edx
0x1400178b8  test    sil, sil
0x1400178bb  jz      short loc_1400178C8
0x1400178bd  lea     rcx, [rbx+38h]
0x1400178c1  call    RtlWriteULongToUser
0x1400178c6  jmp     short loc_1400178CB
0x1400178c8  mov     [rbx+38h], edx
0x1400178cb  test    sil, sil
0x1400178ce  jz      short loc_1400178DD
0x1400178d0  xor     edx, edx
0x1400178d2  lea     rcx, [rbx+44h]
0x1400178d6  call    RtlWriteULongToUser
0x1400178db  jmp     short loc_1400178E4
0x1400178dd  mov     dword ptr [rbx+44h], 0
0x1400178e4  test    r12b, r12b
0x1400178e7  jnz     short loc_14001791F
0x1400178e9  lea     r14, [rbx+38h]
0x1400178ed  test    sil, sil
0x1400178f0  jz      short loc_1400178FC
0x1400178f2  mov     rcx, r14
0x1400178f5  call    RtlReadULongFromUser
0x1400178fa  jmp     short loc_1400178FF
0x1400178fc  mov     eax, [r14]
0x1400178ff  btr     eax, 0Eh
0x140017903  test    sil, sil
0x140017906  jz      short loc_140017914
0x140017908  mov     edx, eax
0x14001790a  mov     rcx, r14
0x14001790d  call    RtlWriteULongToUser
0x140017912  jmp     short loc_140017917
0x140017914  mov     [r14], eax
0x140017917  mov     r14d, [rsp+88h+arg_10]
0x14001791f  lea     rdx, [r15+60h]; Src
0x140017923  lea     rcx, [rbx+60h]; void *
0x140017927  mov     r8d, r13d; Size
0x14001792a  test    sil, sil
0x14001792d  jz      short loc_140017936
0x14001792f  call    RtlCopyToUser
0x140017934  jmp     short loc_14001793B
0x140017936  call    RtlCopyVolatileMemory
0x14001793b  test    r12b, r12b
0x14001793e  jnz     short loc_14001797E
0x140017940  test    sil, sil
0x140017943  jz      short loc_140017954
0x140017945  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140017949  lea     rcx, [rbx+48h]
0x14001794d  call    RtlWriteULong64ToUser
0x140017952  jmp     short loc_14001795C
0x140017954  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x14001795c  lea     rcx, [rbx+50h]; void *
0x140017960  mov     r8d, 10h; Size
0x140017966  test    sil, sil
0x140017969  jz      short loc_140017974
0x14001796b  mov     dl, 0FFh
0x14001796d  call    RtlSetUserMemory
0x140017972  jmp     short loc_14001797E
0x140017974  mov     edx, 0FFh; Val
0x140017979  call    RtlSetVolatileMemory
0x14001797e  test    sil, sil
0x140017981  jz      short loc_14001798F
0x140017983  xor     edx, edx
0x140017985  mov     rcx, rbx
0x140017988  call    RtlWriteULongToUser
0x14001798d  jmp     short loc_140017995
0x14001798f  mov     dword ptr [rbx], 0
0x140017995  mov     rax, [rsp+88h+arg_48]
0x14001799d  mov     [rax], rbx
0x1400179a0  mov     [rsp+88h+var_48], 0
0x1400179a5  lea     ebx, [r13+60h]
0x1400179a9  mov     [rsp+88h+var_2C], ebx
0x1400179ad  mov     eax, 80000005h
0x1400179b2  cmp     ebx, r14d
0x1400179b5  cmovb   edi, eax
0x1400179b8  mov     [rsp+88h+var_30], edi
0x1400179bc  mov     rax, [rsp+88h+arg_50]
0x1400179c4  mov     [rax], ebx
0x1400179c6  jmp     short loc_1400179D1
0x1400179c8  mov     edi, 0C00000E8h
0x1400179cd  mov     [rsp+88h+var_30], edi
0x1400179d1  mov     eax, edi
0x1400179d3  lea     r11, [rsp+88h+var_28]
0x1400179d8  mov     rbx, [r11+30h]
0x1400179dc  mov     rsi, [r11+38h]
0x1400179e0  mov     rsp, r11
0x1400179e3  pop     r15
0x1400179e5  pop     r14
0x1400179e7  pop     r13
0x1400179e9  pop     r12
0x1400179eb  pop     rdi
0x1400179ec  retn
0x140034ead  push    rbp
0x140034eaf  sub     rsp, 40h
0x140034eb3  mov     rbp, rdx
0x140034eb6  xor     eax, eax
0x140034eb8  cmp     [rbp+40h], al
0x140034ebb  setnz   al
0x140034ebe  add     rsp, 40h
0x140034ec2  pop     rbp
0x140034ec3  retn
```
