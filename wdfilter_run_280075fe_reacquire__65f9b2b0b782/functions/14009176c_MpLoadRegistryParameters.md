# MpLoadRegistryParameters

- ea: `0x14009176c`
- end: `0x140091c33`
- name: `MpLoadRegistryParameters`
- size: `1223`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14008f314`

## callees

- `0x1400026c0`
- `0x140003d20`
- `0x1400051bc`
- `0x140007030`
- `0x14000c57c`
- `0x140011890`
- `0x1400118d0`
- `0x14009176c`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140091895`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140091895`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400918b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091884`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091884`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091bf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091bf8`

## string_xrefs

- `0x140091869`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 MpLoadRegistryParameters()
{
  __int64 PoolWithTag; // rax
  _DWORD **v1; // rbp
  int v2; // esi
  __int64 v3; // r15
  __int64 *v4; // r14
  int **v5; // rdx
  __int64 *v6; // r8
  _QWORD *v7; // rcx
  __int64 v8; // r9
  int *v9; // rax
  __int64 v10; // rbx
  PVOID SystemRoutineAddress; // rax
  _DWORD **v12; // rdx
  __int64 v13; // r8
  _DWORD *v14; // rcx
  int v15; // eax
  unsigned int v16; // eax
  int v17; // r14d
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int v20; // r14d
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  wchar_t **v23; // rdi
  int **v24; // r14
  int v25; // r8d
  PDEVICE_OBJECT v26; // rcx
  int v27; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  PoolWithTag = MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 1456, 1835880525);
  v1 = (_DWORD **)PoolWithTag;
  if ( PoolWithTag )
  {
    v3 = 25;
    v4 = &qword_1400260E0;
    v5 = &off_1400260D8;
    v6 = &qword_1400260E0;
    v7 = (_QWORD *)(PoolWithTag + 16);
    v8 = 25;
    do
    {
      *((_DWORD *)v7 - 2) = -2147483616;
      *v7 = *(v5 - 1);
      v7 += 7;
      v9 = *v5;
      v5 += 3;
      *(v7 - 4) = v6;
      v6 += 3;
      *(v7 - 6) = v9;
      *((_DWORD *)v7 - 10) = 4;
      *((_DWORD *)v7 - 6) = 4;
      --v8;
    }
    while ( v8 );
    DestinationString = 0;
    v10 = *(_QWORD *)(MpData + 584);
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    v2 = ((__int64 (__fastcall *)(__int64, __int64, _DWORD **, _QWORD, _QWORD))SystemRoutineAddress)(
           0x80000000LL,
           v10,
           v1,
           0,
           0);
    if ( v2 == -1073741772 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          43,
          WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
          KeGetCurrentThread());
      v12 = v1 + 3;
      v13 = 25;
      do
      {
        v14 = *v12;
        v12 += 7;
        v15 = *(_DWORD *)v4;
        v4 += 3;
        *v14 = v15;
        --v13;
      }
      while ( v13 );
      v2 = 0;
    }
    else if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
          KeGetCurrentThread(),
          v2);
      }
      goto LABEL_71;
    }
    _mm_lfence();
    if ( (unsigned int)dword_1400269EC > 0x200 )
      dword_1400269EC = 512;
    v16 = dword_1400269F0;
    if ( (unsigned int)dword_1400269F0 < 0x10 )
    {
      v16 = 16;
      dword_1400269F0 = 16;
    }
    if ( v16 > 0x1000 )
      dword_1400269F0 = 4096;
    v17 = 1000;
    if ( (unsigned int)(dword_1400269C4 - 1) <= 0x3E6 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          45,
          WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
          (unsigned int)dword_1400269C4,
          1000);
      dword_1400269C4 = 1000;
    }
    if ( (unsigned int)(dword_1400269C8 - 1) <= 0x3E6 )
    {
      dword_1400269C8 = 1000;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_b960013237753183ac7a6d55d666ce86_Traceguids, 1000, 1000);
    }
    if ( (unsigned int)(dword_1400269CC - 1) <= 0x62 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          47,
          WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
          (unsigned int)dword_1400269CC,
          100);
      dword_1400269CC = 100;
    }
    if ( (unsigned int)dword_140026A0C >= 0x3E8 )
    {
      v17 = 30000;
      if ( (unsigned int)dword_140026A0C <= 0x7530 )
        goto LABEL_50;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
      {
LABEL_49:
        dword_140026A0C = v17;
LABEL_50:
        v20 = 6;
        if ( (unsigned int)dword_140026A10 >= 6 )
        {
          v20 = 40;
          if ( (unsigned int)dword_140026A10 <= 0x28 )
            goto LABEL_60;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
          {
LABEL_59:
            dword_140026A10 = v20;
LABEL_60:
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
            {
              v23 = &off_1400260D0;
              v24 = v1 + 3;
              do
              {
                v25 = **v24;
                if ( v25 == *((_DWORD *)v23 + 4) )
                {
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
                  {
                    goto LABEL_70;
                  }
                  v27 = 53;
                }
                else
                {
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
                  {
                    goto LABEL_70;
                  }
                  v27 = 52;
                }
                WPP_SF_Sd(v26->AttachedDevice, v27, v25, (unsigned int)*v23, **v24);
LABEL_70:
                v24 += 7;
                v23 += 3;
                --v3;
              }
              while ( v3 );
            }
LABEL_71:
            ExFreePoolWithTag(v1, 0x6D6D504Du);
            return (unsigned int)v2;
          }
          v22 = 51;
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
          {
            goto LABEL_59;
          }
          v22 = 50;
        }
        WPP_SF_dd(
          v21->AttachedDevice,
          v22,
          WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
          (unsigned int)dword_140026A10,
          v20);
        goto LABEL_59;
      }
      v19 = 49;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
        goto LABEL_49;
      v19 = 48;
    }
    WPP_SF_dd(
      v18->AttachedDevice,
      v19,
      WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
      (unsigned int)dword_140026A0C,
      v17);
    goto LABEL_49;
  }
  v2 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
      KeGetCurrentThread(),
      -1073741670);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14009176c  mov     rax, rsp
0x14009176f  mov     [rax+8], rbx
0x140091773  mov     [rax+10h], rbp
0x140091777  mov     [rax+18h], rsi
0x14009177b  mov     [rax+20h], rdi
0x14009177f  push    r12
0x140091781  push    r14
0x140091783  push    r15
0x140091785  sub     rsp, 50h
0x140091789  mov     rax, cs:__security_cookie
0x140091790  xor     rax, rsp
0x140091793  mov     [rsp+68h+var_28], rax
0x140091798  mov     ecx, cs:ExDefaultNonPagedPoolType
0x14009179e  mov     edx, 5B0h
0x1400917a3  mov     r8d, 6D6D504Dh
0x1400917a9  call    MpAllocatePoolWithTag
0x1400917ae  mov     rbp, rax
0x1400917b1  test    rax, rax
0x1400917b4  jnz     short loc_14009180D
0x1400917b6  mov     esi, 0C000009Ah
0x1400917bb  mov     rax, cs:WPP_GLOBAL_Control
0x1400917c2  lea     rbx, WPP_GLOBAL_Control
0x1400917c9  cmp     rax, rbx
0x1400917cc  jz      loc_140091C04
0x1400917d2  mov     eax, [rax+2Ch]
0x1400917d5  test    al, 1
0x1400917d7  jz      loc_140091C04
0x1400917dd  mov     r9, gs:188h
0x1400917e6  lea     edx, [rbp+2Ah]
0x1400917e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400917f0  lea     r8, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x1400917f7  mov     dword ptr [rsp+68h+var_48], 0C000009Ah
0x1400917ff  mov     rcx, [rcx+18h]
0x140091803  call    WPP_SF_qD
0x140091808  jmp     loc_140091C04
0x14009180d  mov     r15d, 19h
0x140091813  lea     r14, qword_1400260E0
0x14009181a  lea     rdx, off_1400260D8
0x140091821  mov     r8, r14
0x140091824  lea     rcx, [rax+10h]
0x140091828  mov     r9d, r15d
0x14009182b  lea     r12d, [r15-15h]
0x14009182f  mov     dword ptr [rcx-8], 80000020h
0x140091836  mov     rax, [rdx-8]
0x14009183a  mov     [rcx], rax
0x14009183d  lea     rcx, [rcx+38h]
0x140091841  mov     rax, [rdx]
0x140091844  lea     rdx, [rdx+18h]
0x140091848  mov     [rcx-20h], r8
0x14009184c  add     r8, 18h
0x140091850  mov     [rcx-30h], rax
0x140091854  mov     [rcx-28h], r12d
0x140091858  mov     [rcx-18h], r12d
0x14009185c  sub     r9, 1
0x140091860  jnz     short loc_14009182F
0x140091862  mov     rax, cs:MpData
0x140091869  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140091870  xorps   xmm0, xmm0
0x140091873  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140091878  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14009187d  mov     rbx, [rax+248h]
0x140091884  call    cs:__imp_RtlInitUnicodeString
0x14009188b  nop     dword ptr [rax+rax+00h]
0x140091890  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x140091895  call    cs:__imp_MmGetSystemRoutineAddress
0x14009189c  nop     dword ptr [rax+rax+00h]
0x1400918a1  mov     r8, rbp
0x1400918a4  mov     [rsp+68h+var_48], 0
0x1400918ad  test    rax, rax
0x1400918b0  mov     rdx, rbx
0x1400918b3  mov     ecx, 80000000h
0x1400918b8  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400918c0  xor     r9d, r9d
0x1400918c3  call    cs:__guard_dispatch_icall_fptr
0x1400918c9  lea     rbx, WPP_GLOBAL_Control
0x1400918d0  mov     esi, eax
0x1400918d2  lea     rdi, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x1400918d9  cmp     eax, 0C0000034h
0x1400918de  jnz     loc_140091A79
0x1400918e4  mov     rax, cs:WPP_GLOBAL_Control
0x1400918eb  cmp     rax, rbx
0x1400918ee  jz      short loc_140091919
0x1400918f0  mov     eax, [rax+2Ch]
0x1400918f3  test    r12b, al
0x1400918f6  jz      short loc_140091919
0x1400918f8  mov     r9, gs:188h
0x140091901  mov     edx, 2Bh ; '+'
0x140091906  mov     rcx, cs:WPP_GLOBAL_Control
0x14009190d  mov     r8, rdi
0x140091910  mov     rcx, [rcx+18h]
0x140091914  call    WPP_SF_q
0x140091919  lea     rdx, [rbp+18h]
0x14009191d  mov     r8, r15
0x140091920  mov     rcx, [rdx]
0x140091923  lea     rdx, [rdx+38h]
0x140091927  mov     eax, [r14]
0x14009192a  lea     r14, [r14+18h]
0x14009192e  mov     [rcx], eax
0x140091930  sub     r8, 1
0x140091934  jnz     short loc_140091920
0x140091936  xor     esi, esi
0x140091938  lfence
0x14009193b  mov     eax, 200h
0x140091940  cmp     cs:dword_1400269EC, eax
0x140091946  jbe     short loc_14009194E
0x140091948  mov     cs:dword_1400269EC, eax
0x14009194e  mov     eax, cs:dword_1400269F0
0x140091954  mov     r12d, 10h
0x14009195a  cmp     eax, r12d
0x14009195d  jnb     short loc_140091968
0x14009195f  mov     eax, r12d
0x140091962  mov     cs:dword_1400269F0, eax
0x140091968  mov     ecx, 1000h
0x14009196d  cmp     eax, ecx
0x14009196f  jbe     short loc_140091977
0x140091971  mov     cs:dword_1400269F0, ecx
0x140091977  mov     r9d, cs:dword_1400269C4
0x14009197e  mov     r14d, 3E8h
0x140091984  lea     eax, [r9-1]
0x140091988  cmp     eax, 3E6h
0x14009198d  ja      short loc_1400919C0
0x14009198f  mov     rcx, cs:WPP_GLOBAL_Control
0x140091996  cmp     rcx, rbx
0x140091999  jz      short loc_1400919B9
0x14009199b  mov     eax, [rcx+2Ch]
0x14009199e  test    r12b, al
0x1400919a1  jz      short loc_1400919B9
0x1400919a3  mov     rcx, [rcx+18h]
0x1400919a7  mov     edx, 2Dh ; '-'
0x1400919ac  mov     r8, rdi
0x1400919af  mov     dword ptr [rsp+68h+var_48], r14d
0x1400919b4  call    WPP_SF_dd
0x1400919b9  mov     cs:dword_1400269C4, r14d
0x1400919c0  mov     eax, cs:dword_1400269C8
0x1400919c6  dec     eax
0x1400919c8  cmp     eax, 3E6h
0x1400919cd  ja      short loc_140091A03
0x1400919cf  mov     cs:dword_1400269C8, r14d
0x1400919d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400919dd  cmp     rcx, rbx
0x1400919e0  jz      short loc_140091A03
0x1400919e2  mov     eax, [rcx+2Ch]
0x1400919e5  test    r12b, al
0x1400919e8  jz      short loc_140091A03
0x1400919ea  mov     rcx, [rcx+18h]
0x1400919ee  mov     edx, 2Eh ; '.'
0x1400919f3  mov     r9d, r14d
0x1400919f6  mov     dword ptr [rsp+68h+var_48], r14d
0x1400919fb  mov     r8, rdi
0x1400919fe  call    WPP_SF_dd
0x140091a03  mov     r9d, cs:dword_1400269CC
0x140091a0a  lea     eax, [r9-1]
0x140091a0e  cmp     eax, 62h ; 'b'
0x140091a11  ja      short loc_140091A4A
0x140091a13  mov     rcx, cs:WPP_GLOBAL_Control
0x140091a1a  cmp     rcx, rbx
0x140091a1d  jz      short loc_140091A40
0x140091a1f  mov     eax, [rcx+2Ch]
0x140091a22  test    r12b, al
0x140091a25  jz      short loc_140091A40
0x140091a27  mov     rcx, [rcx+18h]
0x140091a2b  mov     edx, 2Fh ; '/'
0x140091a30  mov     r8, rdi
0x140091a33  mov     dword ptr [rsp+68h+var_48], 64h ; 'd'
0x140091a3b  call    WPP_SF_dd
0x140091a40  mov     cs:dword_1400269CC, 64h ; 'd'
0x140091a4a  mov     r9d, cs:dword_140026A0C
0x140091a51  cmp     r9d, r14d
0x140091a54  jnb     short loc_140091AD4
0x140091a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140091a5d  cmp     rcx, rbx
0x140091a60  jz      loc_140091B09
0x140091a66  mov     eax, [rcx+2Ch]
0x140091a69  test    r12b, al
0x140091a6c  jz      loc_140091B09
0x140091a72  mov     edx, 30h ; '0'
0x140091a77  jmp     short loc_140091AF8
0x140091a79  test    esi, esi
0x140091a7b  jns     loc_140091938
0x140091a81  mov     rax, cs:WPP_GLOBAL_Control
0x140091a88  lea     rbx, WPP_GLOBAL_Control
0x140091a8f  cmp     rax, rbx
0x140091a92  jz      loc_140091BF0
0x140091a98  mov     eax, [rax+2Ch]
0x140091a9b  test    al, 1
0x140091a9d  jz      loc_140091BF0
0x140091aa3  lfence
0x140091aa6  mov     r9, gs:188h
0x140091aaf  lea     r8, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x140091ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140091abd  mov     edx, 2Ch ; ','
0x140091ac2  mov     dword ptr [rsp+68h+var_48], esi
0x140091ac6  mov     rcx, [rcx+18h]
0x140091aca  call    WPP_SF_qD
0x140091acf  jmp     loc_140091BF0
0x140091ad4  mov     r14d, 7530h
0x140091ada  cmp     r9d, r14d
0x140091add  jbe     short loc_140091B10
0x140091adf  mov     rcx, cs:WPP_GLOBAL_Control
0x140091ae6  cmp     rcx, rbx
0x140091ae9  jz      short loc_140091B09
0x140091aeb  mov     eax, [rcx+2Ch]
0x140091aee  test    r12b, al
0x140091af1  jz      short loc_140091B09
0x140091af3  mov     edx, 31h ; '1'
0x140091af8  mov     rcx, [rcx+18h]
0x140091afc  mov     r8, rdi
0x140091aff  mov     dword ptr [rsp+68h+var_48], r14d
0x140091b04  call    WPP_SF_dd
0x140091b09  mov     cs:dword_140026A0C, r14d
0x140091b10  mov     r9d, cs:dword_140026A10
0x140091b17  mov     r14d, 6
0x140091b1d  cmp     r9d, r14d
0x140091b20  jnb     short loc_140091B3C
0x140091b22  mov     rcx, cs:WPP_GLOBAL_Control
0x140091b29  cmp     rcx, rbx
0x140091b2c  jz      short loc_140091B70
0x140091b2e  mov     eax, [rcx+2Ch]
0x140091b31  test    r12b, al
0x140091b34  jz      short loc_140091B70
0x140091b36  lea     edx, [r14+2Ch]
0x140091b3a  jmp     short loc_140091B5F
0x140091b3c  mov     r14d, 28h ; '('
0x140091b42  cmp     r9d, r14d
0x140091b45  jbe     short loc_140091B77
0x140091b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140091b4e  cmp     rcx, rbx
0x140091b51  jz      short loc_140091B70
0x140091b53  mov     eax, [rcx+2Ch]
0x140091b56  test    r12b, al
0x140091b59  jz      short loc_140091B70
0x140091b5b  lea     edx, [r14+0Bh]
0x140091b5f  mov     rcx, [rcx+18h]
0x140091b63  mov     r8, rdi
0x140091b66  mov     dword ptr [rsp+68h+var_48], r14d
0x140091b6b  call    WPP_SF_dd
0x140091b70  mov     cs:dword_140026A10, r14d
0x140091b77  mov     rax, cs:WPP_GLOBAL_Control
0x140091b7e  mov     ecx, [rax+2Ch]
0x140091b81  test    r12b, cl
0x140091b84  jz      short loc_140091BF0
0x140091b86  lea     rdi, off_1400260D0; "ResetToUnknownTimer"
0x140091b8d  lea     r14, [rbp+18h]
0x140091b91  mov     rax, [r14]
0x140091b94  mov     r8d, [rax]
0x140091b97  cmp     r8d, [rdi+10h]
0x140091b9b  jz      short loc_140091BB8
0x140091b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140091ba4  cmp     rcx, rbx
0x140091ba7  jz      short loc_140091BE2
0x140091ba9  mov     eax, [rcx+2Ch]
0x140091bac  test    r12b, al
0x140091baf  jz      short loc_140091BE2
0x140091bb1  mov     edx, 34h ; '4'
0x140091bb6  jmp     short loc_140091BD1
0x140091bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140091bbf  cmp     rcx, rbx
0x140091bc2  jz      short loc_140091BE2
0x140091bc4  mov     eax, [rcx+2Ch]
0x140091bc7  test    r12b, al
0x140091bca  jz      short loc_140091BE2
0x140091bcc  mov     edx, 35h ; '5'
0x140091bd1  mov     r9, [rdi]
0x140091bd4  mov     rcx, [rcx+18h]
0x140091bd8  mov     dword ptr [rsp+68h+var_48], r8d
0x140091bdd  call    WPP_SF_Sd
0x140091be2  add     r14, 38h ; '8'
0x140091be6  add     rdi, 18h
0x140091bea  sub     r15, 1
0x140091bee  jnz     short loc_140091B91
0x140091bf0  mov     edx, 6D6D504Dh; Tag
0x140091bf5  mov     rcx, rbp; P
0x140091bf8  call    cs:__imp_ExFreePoolWithTag
0x140091bff  nop     dword ptr [rax+rax+00h]
0x140091c04  mov     eax, esi
0x140091c06  mov     rcx, [rsp+68h+var_28]
0x140091c0b  xor     rcx, rsp; StackCookie
0x140091c0e  call    __security_check_cookie
0x140091c13  lea     r11, [rsp+68h+var_18]
0x140091c18  mov     rbx, [r11+20h]
0x140091c1c  mov     rbp, [r11+28h]
0x140091c20  mov     rsi, [r11+30h]
0x140091c24  mov     rdi, [r11+38h]
0x140091c28  mov     rsp, r11
0x140091c2b  pop     r15
0x140091c2d  pop     r14
0x140091c2f  pop     r12
0x140091c31  retn
```
