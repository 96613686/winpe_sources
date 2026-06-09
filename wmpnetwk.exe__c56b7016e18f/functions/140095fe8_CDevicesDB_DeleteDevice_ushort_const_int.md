# CDevicesDB::DeleteDevice(ushort const *,int)

- ea: `0x140095fe8`
- end: `0x14009646f`
- name: `?DeleteDevice@CDevicesDB@@QEAAJPEBGH@Z`
- size: `1159`
- prototype: `__int64 __fastcall(CDevicesDB *__hidden this, LPCWCH lpString2, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000faac`

## callees

- `0x140006d70`
- `0x140008eac`
- `0x14000b3b0`
- `0x14000c780`
- `0x14000c920`
- `0x14000cb08`
- `0x14000e5e8`
- `0x140020e54`
- `0x14002f6dc`
- `0x140032eec`
- `0x14003f17c`
- `0x140047798`
- `0x14004a79c`
- `0x14009287c`
- `0x140095eac`
- `0x140095fe8`
- `0x140096f4c`
- `0x14009771c`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x140096187`
- `ADVAPI32!RegDeleteValueW` at `0x14009633b`
- `ADVAPI32!RegDeleteValueW` at `0x140096187`
- `ADVAPI32!RegDeleteValueW` at `0x14009633b`
- `KERNEL32!CompareStringOrdinal` at `0x140096076`
- `KERNEL32!CompareStringOrdinal` at `0x140096076`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDevicesDB::DeleteDevice(CDevicesDB *this, LPCWCH lpString2, int a3)
{
  CDevicesDB *v4; // r12
  unsigned int RegKey; // eax
  unsigned int v6; // edi
  PVOID *v7; // r10
  const WCHAR *v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // rdx
  char v11; // al
  char *v12; // rax
  int v13; // eax
  int v14; // esi
  unsigned int v15; // eax
  unsigned int v16; // esi
  unsigned int v17; // esi
  LPCWSTR *v18; // rax
  int v19; // r15d
  _QWORD *v20; // rax
  char v21; // al
  unsigned int v22; // eax
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-29h] BYREF
  __int64 v25; // [rsp+40h] [rbp-21h] BYREF
  __int64 v26; // [rsp+48h] [rbp-19h]
  HKEY v27[3]; // [rsp+50h] [rbp-11h] BYREF
  HKEY hKey[3]; // [rsp+68h] [rbp+7h] BYREF
  HKEY v29[3]; // [rsp+80h] [rbp+1Fh] BYREF
  LPCWSTR lpValueName; // [rsp+E0h] [rbp+7Fh] BYREF

  v4 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, a3, (_DWORD)lpString2, 1);
  }
  memset(hKey, 0, sizeof(hKey));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpValueName);
  if ( CompareStringOrdinal(L"00-00-00-00-00-00", -1, lpString2, -1, 0) == 2 )
  {
    v6 = 0;
    goto LABEL_55;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&lpValueName, lpString2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::MakeUpper(&lpValueName);
  RegKey = CDevicesDB::CreateRegKey(v4, (struct ATL::CRegKey *)hKey, 0);
  v6 = RegKey;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, RegKey);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 )
    goto LABEL_56;
  v8 = lpValueName;
  v9 = DeleteKeyRecursive_64KEY(hKey, lpValueName);
  v6 = v9;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)&WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids,
      (_DWORD)v8,
      v9);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 == 2 )
  {
    v6 = 1168;
    if ( v7 == &WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( (*((_BYTE *)v7 + 28) & 2) == 0 || *((_BYTE *)v7 + 25) < 4u )
      goto LABEL_56;
    v10 = 30;
    goto LABEL_20;
  }
  if ( v6 )
  {
LABEL_56:
    if ( v7 != &WPP_GLOBAL_Control
      && (*((_BYTE *)v7 + 28) & 1) != 0
      && *((unsigned __int8 *)v7 + 25) >= (unsigned int)(v6 != 0 ? 2 : 5) )
    {
      WPP_SF_d(v7[2], 37, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, v6);
    }
    goto LABEL_60;
  }
  v11 = RegDeleteValueW(hKey[0], v8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)&WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids,
      (_DWORD)v8,
      v11);
  }
  if ( (*(__int64 (__fastcall **)(CDevicesDB *))(*(_QWORD *)v4 + 88LL))(v4) )
  {
    v12 = (char *)(*(__int64 (__fastcall **)(CDevicesDB *))(*(_QWORD *)v4 + 88LL))(v4);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      (void **)&lpSubKey,
      v12);
    memset(v27, 0, sizeof(v27));
    v25 = 0;
    v26 = 0;
    v13 = ATL::CRegKey::Open((ATL::CRegKey *)v27, HKEY_LOCAL_MACHINE, lpSubKey, 0x2011Fu);
    v14 = v13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids,
        (_DWORD)lpSubKey,
        v13);
    }
    if ( !v14 )
    {
      v15 = EnumSubKeys(v27, &v25);
      v16 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, v15);
      }
      if ( !v16 )
      {
        v17 = 0;
        if ( (_DWORD)v26 )
        {
          do
          {
            memset(v29, 0, sizeof(v29));
            v18 = (LPCWSTR *)ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::operator[](
                               &v25,
                               v17);
            v19 = ATL::CRegKey::Open((ATL::CRegKey *)v29, v27[0], *v18, 0x2011Fu);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v20 = (_QWORD *)ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::operator[](
                                &v25,
                                v17);
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                (unsigned int)&WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids,
                *v20,
                v19);
            }
            if ( !v19 )
            {
              v21 = RegDeleteValueW(v29[0], v8);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  35,
                  (unsigned int)&WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids,
                  (_DWORD)v8,
                  v21);
              }
            }
            ATL::CRegKey::Close((ATL::CRegKey *)v29);
            ++v17;
          }
          while ( v17 < (unsigned int)v26 );
          v4 = this;
        }
      }
    }
    ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v25);
    ATL::CRegKey::Close((ATL::CRegKey *)v27);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
  }
  v22 = (*(__int64 (__fastcall **)(CDevicesDB *, __int64))(*(_QWORD *)v4 + 72LL))(v4, 1002);
  CEventsDB::SignalEvents(v22, v8, 0, 0);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v10 = 36;
LABEL_20:
      WPP_SF_(v7[2], v10, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids);
LABEL_55:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_56;
    }
    goto LABEL_56;
  }
LABEL_60:
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpValueName);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v6;
}

```

## disassembly

```asm
0x140095fe8  mov     rax, rsp
0x140095feb  mov     [rax+10h], rbx
0x140095fef  mov     [rax+18h], rsi
0x140095ff3  mov     [rax+8], rcx
0x140095ff7  push    rbp
0x140095ff8  push    rdi
0x140095ff9  push    r12
0x140095ffb  push    r13
0x140095ffd  push    r15
0x140095fff  lea     rbp, [rax-5Fh]
0x140096003  sub     rsp, 90h
0x14009600a  mov     rbx, rdx
0x14009600d  mov     r12, rcx
0x140096010  lea     r15, WPP_GLOBAL_Control
0x140096017  mov     rcx, cs:WPP_GLOBAL_Control
0x14009601e  cmp     rcx, r15
0x140096021  jz      short loc_140096048
0x140096023  test    byte ptr [rcx+1Ch], 1
0x140096027  jz      short loc_140096048
0x140096029  cmp     byte ptr [rcx+19h], 5
0x14009602d  jb      short loc_140096048
0x14009602f  mov     edx, 1Bh
0x140096034  mov     [rsp+0B0h+bIgnoreCase], 1
0x14009603c  mov     r9, rbx
0x14009603f  mov     rcx, [rcx+10h]
0x140096043  call    WPP_SF_SL
0x140096048  xor     r13d, r13d
0x14009604b  mov     [rbp+57h+hKey], r13
0x14009604f  mov     [rbp+57h+var_48], r13
0x140096053  mov     [rbp+57h+var_40], r13
0x140096057  lea     rcx, [rbp+57h+lpValueName]
0x14009605b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140096060  nop
0x140096061  mov     [rsp+0B0h+bIgnoreCase], r13d; bIgnoreCase
0x140096066  or      edx, 0FFFFFFFFh; cchCount1
0x140096069  mov     r9d, edx; cchCount2
0x14009606c  mov     r8, rbx; lpString2
0x14009606f  lea     rcx, a000000000000; "00-00-00-00-00-00"
0x140096076  call    cs:__imp_CompareStringOrdinal
0x14009607c  lea     rsi, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x140096083  cmp     eax, 2
0x140096086  jz      loc_1400963FE
0x14009608c  mov     rdx, rbx
0x14009608f  lea     rcx, [rbp+57h+lpValueName]
0x140096093  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140096098  lea     rcx, [rbp+57h+lpValueName]
0x14009609c  call    ?MakeUpper@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::MakeUpper(void)
0x1400960a1  xor     r8d, r8d; unsigned __int16 *
0x1400960a4  lea     rdx, [rbp+57h+hKey]; struct ATL::CRegKey *
0x1400960a8  mov     rcx, r12; this
0x1400960ab  call    ?CreateRegKey@CDevicesDB@@AEAAJAEAVCRegKey@ATL@@PEBG@Z; CDevicesDB::CreateRegKey(ATL::CRegKey &,ushort const *)
0x1400960b0  mov     edi, eax
0x1400960b2  mov     r10, cs:WPP_GLOBAL_Control
0x1400960b9  cmp     r10, r15
0x1400960bc  jz      short loc_1400960E6
0x1400960be  test    byte ptr [r10+1Ch], 2
0x1400960c3  jz      short loc_1400960E6
0x1400960c5  cmp     byte ptr [r10+19h], 4
0x1400960ca  jb      short loc_1400960E6
0x1400960cc  lea     edx, [r13+1Ch]
0x1400960d0  mov     r9d, eax
0x1400960d3  mov     r8, rsi
0x1400960d6  mov     rcx, [r10+10h]
0x1400960da  call    WPP_SF_d
0x1400960df  mov     r10, cs:WPP_GLOBAL_Control
0x1400960e6  test    edi, edi
0x1400960e8  jnz     loc_140096408
0x1400960ee  mov     rbx, [rbp+57h+lpValueName]
0x1400960f2  mov     rdx, rbx; unsigned __int16 *
0x1400960f5  lea     rcx, [rbp+57h+hKey]; HKEY *
0x1400960f9  call    ?DeleteKeyRecursive_64KEY@@YAJAEAVCRegKey@ATL@@PEBG@Z; DeleteKeyRecursive_64KEY(ATL::CRegKey &,ushort const *)
0x1400960fe  mov     edi, eax
0x140096100  mov     r10, cs:WPP_GLOBAL_Control
0x140096107  cmp     r10, r15
0x14009610a  jz      short loc_140096139
0x14009610c  test    byte ptr [r10+1Ch], 2
0x140096111  jz      short loc_140096139
0x140096113  cmp     byte ptr [r10+19h], 4
0x140096118  jb      short loc_140096139
0x14009611a  mov     edx, 1Dh
0x14009611f  mov     [rsp+0B0h+bIgnoreCase], eax
0x140096123  mov     r9, rbx
0x140096126  mov     r8, rsi
0x140096129  mov     rcx, [r10+10h]
0x14009612d  call    WPP_SF_Sd
0x140096132  mov     r10, cs:WPP_GLOBAL_Control
0x140096139  cmp     edi, 2
0x14009613c  jnz     short loc_140096178
0x14009613e  mov     edi, 490h
0x140096143  cmp     r10, r15
0x140096146  jz      loc_14009643E
0x14009614c  test    byte ptr [r10+1Ch], 2
0x140096151  jz      loc_140096408
0x140096157  cmp     byte ptr [r10+19h], 4
0x14009615c  jb      loc_140096408
0x140096162  mov     edx, 1Eh
0x140096167  mov     r8, rsi
0x14009616a  mov     rcx, [r10+10h]
0x14009616e  call    WPP_SF_
0x140096173  jmp     loc_140096401
0x140096178  test    edi, edi
0x14009617a  jnz     loc_140096408
0x140096180  mov     rdx, rbx; lpValueName
0x140096183  mov     rcx, [rbp+57h+hKey]; hKey
0x140096187  call    cs:__imp_RegDeleteValueW
0x14009618d  mov     rcx, cs:WPP_GLOBAL_Control
0x140096194  cmp     rcx, r15
0x140096197  jz      short loc_1400961BB
0x140096199  test    byte ptr [rcx+1Ch], 2
0x14009619d  jz      short loc_1400961BB
0x14009619f  cmp     byte ptr [rcx+19h], 4
0x1400961a3  jb      short loc_1400961BB
0x1400961a5  lea     edx, [rdi+1Fh]
0x1400961a8  mov     [rsp+0B0h+bIgnoreCase], eax
0x1400961ac  mov     r9, rbx
0x1400961af  mov     r8, rsi
0x1400961b2  mov     rcx, [rcx+10h]
0x1400961b6  call    WPP_SF_Sd
0x1400961bb  mov     rax, [r12]
0x1400961bf  mov     rcx, r12
0x1400961c2  mov     rax, [rax+58h]
0x1400961c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400961cb  test    rax, rax
0x1400961ce  jz      loc_1400963B5
0x1400961d4  mov     rax, [r12]
0x1400961d8  mov     rcx, r12
0x1400961db  mov     rax, [rax+58h]
0x1400961df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400961e4  mov     rdx, rax
0x1400961e7  lea     rcx, [rbp+57h+lpSubKey]
0x1400961eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400961f0  mov     [rbp+57h+var_68], r13
0x1400961f4  mov     [rbp+57h+var_60], r13
0x1400961f8  mov     [rbp+57h+var_58], r13
0x1400961fc  mov     [rbp+57h+var_78], r13
0x140096200  mov     [rbp+57h+var_70], r13
0x140096204  mov     r9d, 2011Fh; unsigned int
0x14009620a  mov     r8, [rbp+57h+lpSubKey]; lpSubKey
0x14009620e  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140096215  lea     rcx, [rbp+57h+var_68]; this
0x140096219  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14009621e  mov     esi, eax
0x140096220  mov     rcx, cs:WPP_GLOBAL_Control
0x140096227  cmp     rcx, r15
0x14009622a  jz      short loc_140096255
0x14009622c  test    byte ptr [rcx+1Ch], 2
0x140096230  jz      short loc_140096255
0x140096232  cmp     byte ptr [rcx+19h], 4
0x140096236  jb      short loc_140096255
0x140096238  mov     edx, 20h ; ' '
0x14009623d  mov     [rsp+0B0h+bIgnoreCase], eax
0x140096241  mov     r9, [rbp+57h+lpSubKey]
0x140096245  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14009624c  mov     rcx, [rcx+10h]
0x140096250  call    WPP_SF_Sd
0x140096255  test    esi, esi
0x140096257  jnz     loc_140096393
0x14009625d  lea     rdx, [rbp+57h+var_78]
0x140096261  lea     rcx, [rbp+57h+var_68]
0x140096265  call    ?EnumSubKeys@@YAJAEAVCRegKey@ATL@@AEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@2@@Z; EnumSubKeys(ATL::CRegKey &,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> &)
0x14009626a  mov     esi, eax
0x14009626c  mov     rcx, cs:WPP_GLOBAL_Control
0x140096273  cmp     rcx, r15
0x140096276  jz      short loc_14009629C
0x140096278  test    byte ptr [rcx+1Ch], 2
0x14009627c  jz      short loc_14009629C
0x14009627e  cmp     byte ptr [rcx+19h], 4
0x140096282  jb      short loc_14009629C
0x140096284  mov     edx, 21h ; '!'
0x140096289  mov     r9d, eax
0x14009628c  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x140096293  mov     rcx, [rcx+10h]
0x140096297  call    WPP_SF_d
0x14009629c  test    esi, esi
0x14009629e  jnz     loc_140096393
0x1400962a4  mov     esi, r13d
0x1400962a7  cmp     dword ptr [rbp+57h+var_70], r13d
0x1400962ab  jbe     loc_140096393
0x1400962b1  lea     r12, WPP_GLOBAL_Control
0x1400962b8  mov     [rbp+57h+var_38], r13
0x1400962bc  mov     [rbp+57h+var_30], r13
0x1400962c0  mov     [rbp+57h+var_28], r13
0x1400962c4  mov     edx, esi
0x1400962c6  lea     rcx, [rbp+57h+var_78]
0x1400962ca  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x1400962cf  mov     r9d, 2011Fh; unsigned int
0x1400962d5  mov     r8, [rax]; lpSubKey
0x1400962d8  mov     rdx, [rbp+57h+var_68]; hKey
0x1400962dc  lea     rcx, [rbp+57h+var_38]; this
0x1400962e0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400962e5  mov     r15d, eax
0x1400962e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400962ef  cmp     rcx, r12
0x1400962f2  jz      short loc_14009632F
0x1400962f4  test    byte ptr [rcx+1Ch], 2
0x1400962f8  jz      short loc_14009632F
0x1400962fa  cmp     byte ptr [rcx+19h], 4
0x1400962fe  jb      short loc_14009632F
0x140096300  mov     edx, esi
0x140096302  lea     rcx, [rbp+57h+var_78]
0x140096306  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x14009630b  mov     edx, 22h ; '"'
0x140096310  mov     [rsp+0B0h+bIgnoreCase], r15d
0x140096315  mov     r9, [rax]
0x140096318  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14009631f  mov     rcx, cs:WPP_GLOBAL_Control
0x140096326  mov     rcx, [rcx+10h]
0x14009632a  call    WPP_SF_Sd
0x14009632f  test    r15d, r15d
0x140096332  jnz     short loc_140096374
0x140096334  mov     rdx, rbx; lpValueName
0x140096337  mov     rcx, [rbp+57h+var_38]; hKey
0x14009633b  call    cs:__imp_RegDeleteValueW
0x140096341  mov     rcx, cs:WPP_GLOBAL_Control
0x140096348  cmp     rcx, r12
0x14009634b  jz      short loc_140096374
0x14009634d  test    byte ptr [rcx+1Ch], 2
0x140096351  jz      short loc_140096374
0x140096353  cmp     byte ptr [rcx+19h], 4
0x140096357  jb      short loc_140096374
0x140096359  lea     edx, [r15+23h]
0x14009635d  mov     [rsp+0B0h+bIgnoreCase], eax
0x140096361  mov     r9, rbx
0x140096364  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14009636b  mov     rcx, [rcx+10h]
0x14009636f  call    WPP_SF_Sd
0x140096374  lea     rcx, [rbp+57h+var_38]; this
0x140096378  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14009637d  inc     esi
0x14009637f  cmp     esi, dword ptr [rbp+57h+var_70]
0x140096382  jb      loc_1400962B8
0x140096388  mov     r12, [rbp+57h+arg_0]
0x14009638c  lea     r15, WPP_GLOBAL_Control
0x140096393  lea     rcx, [rbp+57h+var_78]
0x140096397  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RemoveAll(void)
0x14009639c  lea     rcx, [rbp+57h+var_68]; this
0x1400963a0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400963a5  lea     rcx, [rbp+57h+lpSubKey]
0x1400963a9  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400963ae  lea     rsi, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x1400963b5  mov     rax, [r12]
0x1400963b9  mov     edx, 3EAh
0x1400963be  mov     rcx, r12
0x1400963c1  mov     rax, [rax+48h]
0x1400963c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400963ca  xor     r9d, r9d; unsigned __int16 *
0x1400963cd  xor     r8d, r8d; unsigned __int16 *
0x1400963d0  mov     rdx, rbx; unsigned __int16 *
0x1400963d3  mov     ecx, eax; unsigned int
0x1400963d5  call    ?SignalEvents@CEventsDB@@SAXHPEBG00@Z; CEventsDB::SignalEvents(int,ushort const *,ushort const *,ushort const *)
0x1400963da  mov     r10, cs:WPP_GLOBAL_Control
0x1400963e1  cmp     r10, r15
0x1400963e4  jz      short loc_14009643E
0x1400963e6  test    byte ptr [r10+1Ch], 2
0x1400963eb  jz      short loc_140096408
0x1400963ed  cmp     byte ptr [r10+19h], 4
0x1400963f2  jb      short loc_140096408
0x1400963f4  mov     edx, 24h ; '$'
0x1400963f9  jmp     loc_140096167
0x1400963fe  mov     edi, r13d
0x140096401  mov     r10, cs:WPP_GLOBAL_Control
0x140096408  cmp     r10, r15
0x14009640b  jz      short loc_14009643E
0x14009640d  test    byte ptr [r10+1Ch], 1
0x140096412  jz      short loc_14009643E
0x140096414  movzx   edx, byte ptr [r10+19h]
0x140096419  mov     eax, edi
0x14009641b  neg     eax
0x14009641d  sbb     ecx, ecx
0x14009641f  and     ecx, 0FFFFFFFDh
0x140096422  add     ecx, 5
0x140096425  cmp     edx, ecx
0x140096427  jb      short loc_14009643E
0x140096429  mov     edx, 25h ; '%'
0x14009642e  mov     r9d, edi
0x140096431  mov     r8, rsi
0x140096434  mov     rcx, [r10+10h]
0x140096438  call    WPP_SF_d
0x14009643d  nop
0x14009643e  lea     rcx, [rbp+57h+lpValueName]
0x140096442  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140096447  nop
0x140096448  lea     rcx, [rbp+57h+hKey]; this
0x14009644c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140096451  mov     eax, edi
0x140096453  lea     r11, [rsp+0B0h+var_20]
0x14009645b  mov     rbx, [r11+38h]
0x14009645f  mov     rsi, [r11+40h]
0x140096463  mov     rsp, r11
0x140096466  pop     r15
0x140096468  pop     r13
0x14009646a  pop     r12
0x14009646c  pop     rdi
0x14009646d  pop     rbp
0x14009646e  retn
```
