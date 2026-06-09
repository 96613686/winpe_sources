# StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)

- ea: `0x140014128`
- end: `0x140014288`
- name: `?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z`
- size: `352`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014ffc`
- `0x140015fb8`

## callees

- `0x14000d75c`
- `0x14000ea8c`
- `0x140013b44`
- `0x140013e40`
- `0x140013fa8`
- `0x140014058`
- `0x140014128`
- `0x140014490`
- `0x1400169b8`
- `0x1400171ec`
- `0x140017cc0`

## string_xrefs

- `0x14001417d`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\`

## pseudocode

```c
void __fastcall StartList::BuildConfigList(__int64 a1, __int64 a2)
{
  char v4; // al
  char *v5; // rbx
  LPCWSTR v6; // rdi
  char *v7; // rdi
  _BYTE *v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rax
  ATL::CStringData *v11; // rcx
  __int64 v12; // rbx
  char *v13; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR lpSubKey; // [rsp+28h] [rbp-28h] BYREF
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v16[3]; // [rsp+38h] [rbp-18h] BYREF
  int v17; // [rsp+80h] [rbp+30h] BYREF
  int v18; // [rsp+88h] [rbp+38h] BYREF

  v17 = 0;
  v18 = 44;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
    a1,
    &v13,
    &v18,
    &v17);
  v4 = ATL::operator!=(&v13);
  v5 = v13;
  while ( v4 )
  {
    if ( *((_DWORD *)v5 - 4) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &lpSubKey,
        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs\\");
      ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, v5, *((unsigned int *)v5 - 4));
      v6 = lpSubKey;
      memset(v16, 0, sizeof(v16));
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v16, HKEY_LOCAL_MACHINE, lpSubKey, 0x20019u) )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          a2,
          v5);
      ATL::CRegKey::Close((ATL::CRegKey *)v16);
      ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
    }
    v7 = v5 - 24;
    v8 = *(_BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                      a1,
                      &v15,
                      &v18,
                      &v17);
    v9 = v8 - 24;
    if ( v8 - 24 != v5 - 24 )
    {
      if ( *((int *)v7 + 4) >= 0 && *v9 == *(_QWORD *)v7 )
      {
        v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v9);
        v11 = (ATL::CStringData *)(v5 - 24);
        v12 = v10;
        ATL::CStringData::Release(v11);
        v5 = (char *)(v12 + 24);
        v13 = v5;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v13, v8, *((_DWORD *)v8 - 4));
        v5 = v13;
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    v4 = ATL::operator!=(&v13);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v5 - 24));
}

```

## disassembly

```asm
0x140014128  mov     [rsp-18h+arg_0], rbx
0x14001412d  mov     [rsp-18h+arg_8], rsi
0x140014132  push    rbp
0x140014133  push    rdi
0x140014134  push    r14
0x140014136  mov     rbp, rsp
0x140014139  sub     rsp, 50h
0x14001413d  mov     r14, rdx
0x140014140  mov     [rbp+arg_10], 0
0x140014147  lea     rdx, [rbp+var_30]
0x14001414b  mov     [rbp+arg_18], 2Ch ; ','
0x140014152  lea     r9, [rbp+arg_10]
0x140014156  mov     rsi, rcx
0x140014159  lea     r8, [rbp+arg_18]
0x14001415d  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x140014162  lea     rcx, [rbp+var_30]
0x140014166  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBD@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x14001416b  mov     rbx, [rbp+var_30]
0x14001416f  test    al, al
0x140014171  jz      loc_14001426B
0x140014177  cmp     dword ptr [rbx-10h], 0
0x14001417b  jz      short loc_1400141F3
0x14001417d  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x140014184  lea     rcx, [rbp+lpSubKey]
0x140014188  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001418d  mov     r8d, [rbx-10h]
0x140014191  lea     rcx, [rbp+lpSubKey]
0x140014195  mov     rdx, rbx
0x140014198  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001419d  mov     rdi, [rbp+lpSubKey]
0x1400141a1  lea     rcx, [rbp+var_18]; this
0x1400141a5  mov     r8, rdi; lpSubKey
0x1400141a8  mov     [rbp+var_18], 0
0x1400141b0  mov     r9d, 20019h; unsigned int
0x1400141b6  mov     [rbp+var_10], 0
0x1400141be  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1400141c5  mov     [rbp+var_8], 0
0x1400141cd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400141d2  test    eax, eax
0x1400141d4  jnz     short loc_1400141E1
0x1400141d6  mov     rdx, rbx
0x1400141d9  mov     rcx, r14
0x1400141dc  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x1400141e1  lea     rcx, [rbp+var_18]; this
0x1400141e5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400141ea  lea     rcx, [rdi-18h]; this
0x1400141ee  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400141f3  lea     r9, [rbp+arg_10]
0x1400141f7  mov     rcx, rsi
0x1400141fa  lea     r8, [rbp+arg_18]
0x1400141fe  lea     rdx, [rbp+var_20]
0x140014202  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x140014207  lea     rdi, [rbx-18h]
0x14001420b  mov     rdx, [rax]
0x14001420e  lea     rcx, [rdx-18h]
0x140014212  cmp     rcx, rdi
0x140014215  jz      short loc_140014250
0x140014217  cmp     dword ptr [rdi+10h], 0
0x14001421b  jl      short loc_14001423F
0x14001421d  mov     rax, [rdi]
0x140014220  cmp     [rcx], rax
0x140014223  jnz     short loc_14001423F
0x140014225  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001422a  mov     rcx, rdi; this
0x14001422d  mov     rbx, rax
0x140014230  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140014235  add     rbx, 18h
0x140014239  mov     [rbp+var_30], rbx
0x14001423d  jmp     short loc_140014250
0x14001423f  mov     r8d, [rdx-10h]
0x140014243  lea     rcx, [rbp+var_30]
0x140014247  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001424c  mov     rbx, [rbp+var_30]
0x140014250  mov     rcx, [rbp+var_20]
0x140014254  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140014258  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001425d  lea     rcx, [rbp+var_30]
0x140014261  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBD@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x140014266  jmp     loc_14001416F
0x14001426b  lea     rcx, [rbx-18h]; this
0x14001426f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140014274  mov     rbx, [rsp+50h+arg_0]
0x140014279  mov     rsi, [rsp+50h+arg_8]
0x14001427e  add     rsp, 50h
0x140014282  pop     r14
0x140014284  pop     rdi
0x140014285  pop     rbp
0x140014286  retn
```
