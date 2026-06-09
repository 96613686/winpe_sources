# CEventsDB::SignalEvents(int,ushort const *,ushort const *,ushort const *)

- ea: `0x14009771c`
- end: `0x140097d4a`
- name: `?SignalEvents@CEventsDB@@SAXHPEBG00@Z`
- size: `1582`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x140036e40`
- `0x1400440e0`
- `0x140095fe8`
- `0x140096b80`

## callees

- `0x140006d70`
- `0x140008eac`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x14000cb08`
- `0x1400105a0`
- `0x140015100`
- `0x140018df0`
- `0x140020e54`
- `0x14002f6dc`
- `0x14003b08c`
- `0x14003cd64`
- `0x14003f17c`
- `0x14003f1bc`
- `0x140047470`
- `0x1400475ec`
- `0x140047798`
- `0x14005387c`
- `0x140053a80`
- `0x14009287c`
- `0x140097428`
- `0x14009771c`
- `0x140098070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140097b98`
- `KERNEL32!GetLastError` at `0x140097b98`
- `KERNEL32!SetEvent` at `0x140097c12`
- `KERNEL32!SetEvent` at `0x140097c12`
- `KERNEL32!OpenEventW` at `0x140097b8a`
- `KERNEL32!OpenEventW` at `0x140097b8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CEventsDB::SignalEvents(
        unsigned int a1,
        char *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // r15d
  unsigned int RegKey; // ebx
  unsigned int v10; // eax
  int v11; // ebx
  PVOID *v12; // rcx
  unsigned int i; // edi
  _QWORD *v14; // rax
  unsigned __int16 *v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // r9d
  unsigned int v20; // eax
  unsigned int v21; // r9d
  unsigned int v22; // eax
  unsigned int v23; // r9d
  unsigned int v24; // eax
  _QWORD *v25; // rax
  HANDLE v26; // rbx
  DWORD LastError; // eax
  PVOID *v28; // rcx
  unsigned int v29; // edx
  unsigned int v30; // eax
  const unsigned __int16 **v31; // rax
  unsigned int v32; // eax
  unsigned int v33; // [rsp+20h] [rbp-79h]
  struct _SECURITY_ATTRIBUTES *v34; // [rsp+30h] [rbp-69h]
  unsigned int *v35; // [rsp+38h] [rbp-61h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-59h] BYREF
  __int64 v37; // [rsp+48h] [rbp-51h] BYREF
  __int64 v38; // [rsp+50h] [rbp-49h]
  LPCWSTR lpName; // [rsp+58h] [rbp-41h] BYREF
  const void *v40; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 *v41; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v42; // [rsp+70h] [rbp-29h] BYREF
  HANDLE v43; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int16 *v44[3]; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int16 *v45; // [rsp+98h] [rbp-1h] BYREF
  HKEY hKey[10]; // [rsp+A0h] [rbp+7h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, (__int64)a4);
  }
  memset(hKey, 0, 24);
  v43 = 0;
  v37 = 0;
  v8 = 0;
  v38 = 0;
  RegKey = CEventsDB::CreateRegKey((struct ATL::CRegKey *)hKey, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, RegKey);
  }
  if ( !RegKey )
  {
    RegKey = EnumSubKeys(hKey, &v37);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, RegKey);
    }
    v8 = v38;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&v45,
    a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&v42,
    (char *)L"ignored");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&v41,
    (char *)L"ignored");
  if ( !RegKey )
  {
    if ( a3 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v42, a3);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids);
      }
    }
    if ( a4 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v41, a4);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids);
      }
    }
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v40);
  if ( RegKey )
  {
LABEL_83:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_84;
  }
  v10 = CreateUUID(&v40);
  v11 = v10;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v10);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpSubKey);
    memset(v44, 0, sizeof(v44));
    for ( i = 0; (int)i < v8; ++i )
    {
      v14 = (_QWORD *)ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::operator[](
                        &v37,
                        i);
      ATL::CSimpleStringT<unsigned short,0>::operator=(&lpSubKey, v14);
      ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, L"\\");
      ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpSubKey, &v40);
      v16 = ATL::CRegKey::Create((ATL::CRegKey *)v44, hKey[0], lpSubKey, v15, v33, 0x2011Fu, v34, v35);
      v17 = v16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v16);
      }
      if ( !v17 )
      {
        v18 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v44, L"Reason", a1);
        v17 = v18;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v18);
        }
        if ( !v17 )
        {
          v20 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v44, L"ID", v45, v19);
          v17 = v20;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v20);
          }
          if ( !v17 )
          {
            v22 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v44, L"Data", v42, v21);
            v17 = v22;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v22);
            }
            if ( !v17 )
            {
              v24 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v44, L"Scope", v41, v23);
              v17 = v24;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v24);
              }
            }
          }
        }
      }
      ATL::CRegKey::Close((ATL::CRegKey *)v44);
      if ( v17 )
        continue;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpName);
      v25 = (_QWORD *)ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::operator[](
                        &v37,
                        i);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
        &lpName,
        L"Global\\%ls",
        *v25);
      v26 = OpenEventW(0x100002u, 0, lpName);
      if ( !v26 )
      {
        LastError = GetLastError();
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_66;
        v29 = 5;
        if ( LastError )
          v29 = 2;
        if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) < v29 )
          goto LABEL_66;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, LastError);
      }
      v28 = (PVOID *)WPP_GLOBAL_Control;
LABEL_66:
      v43 = v26;
      if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 2) != 0 && *((_BYTE *)v28 + 25) >= 4u )
        WPP_SF_q(v28[2], 57, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v26);
      if ( v26 )
      {
        v30 = SetEvent(v26);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v30);
        }
        ATL::CHandle::Close((ATL::CHandle *)&v43);
      }
      else
      {
        v31 = (const unsigned __int16 **)ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::operator[](
                                           &v37,
                                           i);
        v32 = DeleteKeyRecursive_64KEY(hKey, *v31);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids, v32);
        }
      }
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpName);
    }
    ATL::CRegKey::Close((ATL::CRegKey *)v44);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
    goto LABEL_83;
  }
LABEL_84:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_(v12[2], 60, &WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v40);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v41);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v42);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v45);
  ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v37);
  ATL::CHandle::~CHandle((ATL::CHandle *)&v43);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
}

```

## disassembly

```asm
0x14009771c  push    rbp
0x14009771e  push    rbx
0x14009771f  push    rsi
0x140097720  push    rdi
0x140097721  push    r12
0x140097723  push    r14
0x140097725  push    r15
0x140097727  lea     rbp, [rsp-27h]
0x14009772c  sub     rsp, 0C0h
0x140097733  mov     rsi, r9
0x140097736  mov     rdi, r8
0x140097739  mov     r14, rdx
0x14009773c  mov     r12d, ecx
0x14009773f  lea     rax, WPP_GLOBAL_Control
0x140097746  mov     rcx, cs:WPP_GLOBAL_Control
0x14009774d  cmp     rcx, rax
0x140097750  jz      short loc_140097779
0x140097752  test    byte ptr [rcx+1Ch], 1
0x140097756  jz      short loc_140097779
0x140097758  cmp     byte ptr [rcx+19h], 5
0x14009775c  jb      short loc_140097779
0x14009775e  mov     [rsp+0F0h+var_C0], r9; struct _SECURITY_ATTRIBUTES *
0x140097763  mov     qword ptr [rsp+0F0h+var_C8], r8; __int64
0x140097768  mov     qword ptr [rsp+0F0h+var_D0], rdx; unsigned int
0x14009776d  mov     r9d, r12d
0x140097770  mov     rcx, [rcx+10h]; LoggerHandle
0x140097774  call    WPP_SF_dSSS
0x140097779  mov     [rbp+57h+hKey], 0
0x140097781  mov     [rbp+57h+var_48], 0
0x140097789  mov     [rbp+57h+var_40], 0
0x140097791  mov     [rbp+57h+var_78], 0
0x140097799  mov     [rbp+57h+var_A8], 0
0x1400977a1  xor     r15d, r15d
0x1400977a4  mov     [rbp+57h+var_A0], r15
0x1400977a8  xor     edx, edx; lpSubKey
0x1400977aa  lea     rcx, [rbp+57h+hKey]; this
0x1400977ae  call    ?CreateRegKey@CEventsDB@@CAJAEAVCRegKey@ATL@@PEBG@Z; CEventsDB::CreateRegKey(ATL::CRegKey &,ushort const *)
0x1400977b3  mov     ebx, eax
0x1400977b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400977bc  lea     rax, WPP_GLOBAL_Control
0x1400977c3  cmp     rcx, rax
0x1400977c6  jz      short loc_1400977EB
0x1400977c8  test    byte ptr [rcx+1Ch], 2
0x1400977cc  jz      short loc_1400977EB
0x1400977ce  cmp     byte ptr [rcx+19h], 4
0x1400977d2  jb      short loc_1400977EB
0x1400977d4  lea     edx, [r15+2Eh]
0x1400977d8  mov     r9d, ebx
0x1400977db  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x1400977e2  mov     rcx, [rcx+10h]
0x1400977e6  call    WPP_SF_d
0x1400977eb  test    ebx, ebx
0x1400977ed  jnz     short loc_140097839
0x1400977ef  lea     rdx, [rbp+57h+var_A8]
0x1400977f3  lea     rcx, [rbp+57h+hKey]
0x1400977f7  call    ?EnumSubKeys@@YAJAEAVCRegKey@ATL@@AEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@2@@Z; EnumSubKeys(ATL::CRegKey &,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> &)
0x1400977fc  mov     ebx, eax
0x1400977fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140097805  lea     rax, WPP_GLOBAL_Control
0x14009780c  cmp     rcx, rax
0x14009780f  jz      short loc_140097835
0x140097811  test    byte ptr [rcx+1Ch], 2
0x140097815  jz      short loc_140097835
0x140097817  cmp     byte ptr [rcx+19h], 4
0x14009781b  jb      short loc_140097835
0x14009781d  mov     edx, 2Fh ; '/'
0x140097822  mov     r9d, ebx
0x140097825  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x14009782c  mov     rcx, [rcx+10h]
0x140097830  call    WPP_SF_d
0x140097835  mov     r15d, dword ptr [rbp+57h+var_A0]
0x140097839  mov     rdx, r14
0x14009783c  lea     rcx, [rbp+57h+var_58]
0x140097840  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140097845  nop
0x140097846  lea     rdx, aIgnored; "ignored"
0x14009784d  lea     rcx, [rbp+57h+var_80]
0x140097851  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140097856  nop
0x140097857  lea     rdx, aIgnored; "ignored"
0x14009785e  lea     rcx, [rbp+57h+var_88]
0x140097862  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140097867  nop
0x140097868  test    ebx, ebx
0x14009786a  jnz     loc_1400978FF
0x140097870  test    rdi, rdi
0x140097873  jz      short loc_1400978B5
0x140097875  mov     rdx, rdi
0x140097878  lea     rcx, [rbp+57h+var_80]
0x14009787c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140097881  mov     rcx, cs:WPP_GLOBAL_Control
0x140097888  lea     rdi, WPP_GLOBAL_Control
0x14009788f  cmp     rcx, rdi
0x140097892  jz      short loc_1400978BC
0x140097894  test    byte ptr [rcx+1Ch], 2
0x140097898  jz      short loc_1400978BC
0x14009789a  cmp     byte ptr [rcx+19h], 4
0x14009789e  jb      short loc_1400978BC
0x1400978a0  lea     edx, [rbx+30h]
0x1400978a3  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x1400978aa  mov     rcx, [rcx+10h]
0x1400978ae  call    WPP_SF_
0x1400978b3  jmp     short loc_1400978BC
0x1400978b5  lea     rdi, WPP_GLOBAL_Control
0x1400978bc  test    rsi, rsi
0x1400978bf  jz      short loc_1400978FF
0x1400978c1  mov     rdx, rsi
0x1400978c4  lea     rcx, [rbp+57h+var_88]
0x1400978c8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1400978cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400978d4  mov     esi, 2
0x1400978d9  cmp     rcx, rdi
0x1400978dc  jz      short loc_140097904
0x1400978de  test    [rcx+1Ch], sil
0x1400978e2  jz      short loc_140097904
0x1400978e4  cmp     byte ptr [rcx+19h], 4
0x1400978e8  jb      short loc_140097904
0x1400978ea  lea     edx, [rsi+2Fh]
0x1400978ed  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x1400978f4  mov     rcx, [rcx+10h]
0x1400978f8  call    WPP_SF_
0x1400978fd  jmp     short loc_140097904
0x1400978ff  mov     esi, 2
0x140097904  lea     rcx, [rbp+57h+var_90]
0x140097908  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14009790d  nop
0x14009790e  test    ebx, ebx
0x140097910  jnz     loc_140097CC4
0x140097916  lea     rcx, [rbp+57h+var_90]
0x14009791a  call    ?CreateUUID@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CreateUUID(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14009791f  mov     ebx, eax
0x140097921  mov     rcx, cs:WPP_GLOBAL_Control
0x140097928  lea     r14, WPP_GLOBAL_Control
0x14009792f  cmp     rcx, r14
0x140097932  jz      short loc_14009795F
0x140097934  test    [rcx+1Ch], sil
0x140097938  jz      short loc_14009795F
0x14009793a  cmp     byte ptr [rcx+19h], 4
0x14009793e  jb      short loc_14009795F
0x140097940  mov     edx, 32h ; '2'
0x140097945  mov     r9d, eax
0x140097948  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x14009794f  mov     rcx, [rcx+10h]
0x140097953  call    WPP_SF_d
0x140097958  mov     rcx, cs:WPP_GLOBAL_Control
0x14009795f  test    ebx, ebx
0x140097961  js      loc_140097CD2
0x140097967  lea     rcx, [rbp+57h+lpSubKey]
0x14009796b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140097970  nop
0x140097971  mov     [rbp+57h+var_70], 0
0x140097979  mov     [rbp+57h+var_68], 0
0x140097981  mov     [rbp+57h+var_60], 0
0x140097989  xor     edi, edi
0x14009798b  test    r15d, r15d
0x14009798e  jle     loc_140097CAF
0x140097994  mov     edx, edi
0x140097996  lea     rcx, [rbp+57h+var_A8]
0x14009799a  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x14009799f  mov     rdx, rax
0x1400979a2  lea     rcx, [rbp+57h+lpSubKey]
0x1400979a6  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400979ab  lea     rdx, asc_1400A283C; "\\"
0x1400979b2  lea     rcx, [rbp+57h+lpSubKey]
0x1400979b6  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1400979bb  lea     rdx, [rbp+57h+var_90]
0x1400979bf  lea     rcx, [rbp+57h+lpSubKey]
0x1400979c3  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x1400979c8  mov     [rsp+0F0h+var_C8], 2011Fh; unsigned int
0x1400979d0  mov     r8, [rbp+57h+lpSubKey]; lpSubKey
0x1400979d4  mov     rdx, [rbp+57h+hKey]; hKey
0x1400979d8  lea     rcx, [rbp+57h+var_70]; this
0x1400979dc  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1400979e1  mov     ebx, eax
0x1400979e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400979ea  cmp     rcx, r14
0x1400979ed  jz      short loc_140097A13
0x1400979ef  test    [rcx+1Ch], sil
0x1400979f3  jz      short loc_140097A13
0x1400979f5  cmp     byte ptr [rcx+19h], 4
0x1400979f9  jb      short loc_140097A13
0x1400979fb  mov     edx, 33h ; '3'
0x140097a00  mov     r9d, eax
0x140097a03  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x140097a0a  mov     rcx, [rcx+10h]
0x140097a0e  call    WPP_SF_d
0x140097a13  test    ebx, ebx
0x140097a15  jnz     loc_140097B46
0x140097a1b  mov     r8d, r12d; unsigned int
0x140097a1e  lea     rdx, aReason; "Reason"
0x140097a25  lea     rcx, [rbp+57h+var_70]; this
0x140097a29  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x140097a2e  mov     ebx, eax
0x140097a30  mov     rcx, cs:WPP_GLOBAL_Control
0x140097a37  cmp     rcx, r14
0x140097a3a  jz      short loc_140097A60
0x140097a3c  test    [rcx+1Ch], sil
0x140097a40  jz      short loc_140097A60
0x140097a42  cmp     byte ptr [rcx+19h], 4
0x140097a46  jb      short loc_140097A60
0x140097a48  mov     edx, 34h ; '4'
0x140097a4d  mov     r9d, eax
0x140097a50  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x140097a57  mov     rcx, [rcx+10h]
0x140097a5b  call    WPP_SF_d
0x140097a60  test    ebx, ebx
0x140097a62  jnz     loc_140097B46
0x140097a68  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x140097a6c  lea     rdx, aId; "ID"
0x140097a73  lea     rcx, [rbp+57h+var_70]; this
0x140097a77  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140097a7c  mov     ebx, eax
0x140097a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140097a85  cmp     rcx, r14
0x140097a88  jz      short loc_140097AAE
0x140097a8a  test    [rcx+1Ch], sil
0x140097a8e  jz      short loc_140097AAE
0x140097a90  cmp     byte ptr [rcx+19h], 4
0x140097a94  jb      short loc_140097AAE
0x140097a96  mov     edx, 35h ; '5'
0x140097a9b  mov     r9d, eax
0x140097a9e  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x140097aa5  mov     rcx, [rcx+10h]
0x140097aa9  call    WPP_SF_d
0x140097aae  test    ebx, ebx
0x140097ab0  jnz     loc_140097B46
0x140097ab6  mov     r8, [rbp+57h+var_80]; unsigned __int16 *
0x140097aba  lea     rdx, aData; "Data"
0x140097ac1  lea     rcx, [rbp+57h+var_70]; this
0x140097ac5  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140097aca  mov     ebx, eax
0x140097acc  mov     rcx, cs:WPP_GLOBAL_Control
0x140097ad3  cmp     rcx, r14
0x140097ad6  jz      short loc_140097AFC
0x140097ad8  test    [rcx+1Ch], sil
0x140097adc  jz      short loc_140097AFC
0x140097ade  cmp     byte ptr [rcx+19h], 4
0x140097ae2  jb      short loc_140097AFC
0x140097ae4  mov     edx, 36h ; '6'
0x140097ae9  mov     r9d, eax
0x140097aec  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x140097af3  mov     rcx, [rcx+10h]
0x140097af7  call    WPP_SF_d
0x140097afc  test    ebx, ebx
0x140097afe  jnz     short loc_140097B46
0x140097b00  mov     r8, [rbp+57h+var_88]; unsigned __int16 *
0x140097b04  lea     rdx, aScope; "Scope"
0x140097b0b  lea     rcx, [rbp+57h+var_70]; this
0x140097b0f  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140097b14  mov     ebx, eax
0x140097b16  mov     rcx, cs:WPP_GLOBAL_Control
0x140097b1d  cmp     rcx, r14
0x140097b20  jz      short loc_140097B46
0x140097b22  test    [rcx+1Ch], sil
0x140097b26  jz      short loc_140097B46
0x140097b28  cmp     byte ptr [rcx+19h], 4
0x140097b2c  jb      short loc_140097B46
0x140097b2e  mov     edx, 37h ; '7'
0x140097b33  mov     r9d, eax
0x140097b36  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x140097b3d  mov     rcx, [rcx+10h]
0x140097b41  call    WPP_SF_d
0x140097b46  lea     rcx, [rbp+57h+var_70]; this
0x140097b4a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140097b4f  test    ebx, ebx
0x140097b51  jnz     loc_140097CA4
0x140097b57  lea     rcx, [rbp+57h+lpName]
0x140097b5b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140097b60  nop
0x140097b61  mov     edx, edi
0x140097b63  lea     rcx, [rbp+57h+var_A8]
0x140097b67  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x140097b6c  mov     r8, [rax]
0x140097b6f  lea     rdx, aGlobalLs; "Global\\%ls"
0x140097b76  lea     rcx, [rbp+57h+lpName]
0x140097b7a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x140097b7f  mov     r8, [rbp+57h+lpName]; lpName
0x140097b83  xor     edx, edx; bInheritHandle
0x140097b85  mov     ecx, 100002h; dwDesiredAccess
0x140097b8a  call    cs:__imp_OpenEventW
0x140097b90  mov     rbx, rax
0x140097b93  test    rax, rax
0x140097b96  jnz     short loc_140097BD6
0x140097b98  call    cs:__imp_GetLastError
0x140097b9e  mov     r9d, eax
0x140097ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x140097ba8  cmp     rcx, r14
0x140097bab  jz      short loc_140097BDD
0x140097bad  test    [rcx+1Ch], sil
0x140097bb1  jz      short loc_140097BDD
0x140097bb3  lea     edx, [rbx+5]
0x140097bb6  test    eax, eax
0x140097bb8  cmovnz  edx, esi
0x140097bbb  movzx   eax, byte ptr [rcx+19h]
0x140097bbf  cmp     eax, edx
0x140097bc1  jb      short loc_140097BDD
0x140097bc3  lea     edx, [rbx+38h]
0x140097bc6  lea     r8, WPP_f558c0a7dc9c3d0124824e0ee88c58e1_Traceguids
0x140097bcd  mov     rcx, [rcx+10h]
0x140097bd1  call    WPP_SF_d
  ... truncated ...
```
