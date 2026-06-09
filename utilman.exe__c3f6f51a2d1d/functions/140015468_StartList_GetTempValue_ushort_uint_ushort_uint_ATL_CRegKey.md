# StartList::GetTempValue(ushort *,uint,ushort *,uint,ATL::CRegKey &)

- ea: `0x140015468`
- end: `0x1400155f7`
- name: `?GetTempValue@StartList@@AEAAXPEAGI0IAEAVCRegKey@ATL@@@Z`
- size: `399`
- prototype: `void(StartList *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140015fb8`

## callees

- `0x14000ea8c`
- `0x14000eb0c`
- `0x14000f5b8`
- `0x1400135a4`
- `0x1400135f0`
- `0x1400137c4`
- `0x140013ea0`
- `0x1400151e0`
- `0x140015468`
- `0x1400179f0`

## string_xrefs

- `0x14001549d`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StartList::GetTempValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        HKEY *a6)
{
  __int64 v9; // rcx
  const unsigned __int16 **v10; // rbx
  unsigned int v11; // r8d
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  _BYTE v15[352]; // [rsp+20h] [rbp-178h] BYREF
  __int64 v16; // [rsp+1A8h] [rbp+10h] BYREF
  unsigned int v17; // [rsp+1B0h] [rbp+18h] BYREF

  v17 = a3;
  *a2 = 0;
  *a4 = 0;
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)a6,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
                        0x2001Fu) )
  {
    v17 = 0;
    ATManager::ATManager((ATManager *)v15);
    v9 = *(_QWORD *)ATManager::GetAccommodations(v15);
    v16 = v9;
    while ( v16 )
    {
      v10 = *(const unsigned __int16 ***)ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
                                           v9,
                                           &v16);
      if ( (unsigned __int8)ATL::operator!=(v10 + 5) )
      {
        if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)a6, *v10, &v17) )
        {
          v11 = v17;
          if ( (v17 & 2) != 0 )
          {
            *((_DWORD *)this + 74) = 1;
            v17 = v11 & 0xFFFFFFFD;
            ATL::CRegKey::SetDWORDValue(a6, *v10, v11 & 0xFFFFFFFD);
            v13 = -1;
            if ( (v17 & 1) != 0 )
            {
              do
                ++v13;
              while ( a2[v13] );
              if ( v13 )
                StringCbCatW(a2, v12, L",");
              v14 = a2;
            }
            else
            {
              do
                ++v13;
              while ( a4[v13] );
              if ( v13 )
                StringCbCatW(a4, v12, L",");
              v14 = a4;
            }
            StringCbCatW(v14, v12, *v10);
          }
        }
      }
    }
    ATManager::~ATManager((ATManager *)v15);
  }
}

```

## disassembly

```asm
0x140015468  mov     [rsp+arg_0], rbx
0x14001546d  mov     [rsp+arg_18], rsi
0x140015472  mov     [rsp+arg_10], r8d
0x140015477  push    rdi
0x140015478  push    r14
0x14001547a  push    r15
0x14001547c  sub     rsp, 180h
0x140015483  mov     rdi, r9
0x140015486  mov     rsi, rdx
0x140015489  mov     r14, rcx
0x14001548c  xor     r15d, r15d
0x14001548f  mov     [rdx], r15w
0x140015493  mov     [r9], r15w
0x140015497  mov     r9d, 2001Fh; unsigned int
0x14001549d  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400154a4  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1400154ab  mov     rcx, [rsp+198h+arg_28]; this
0x1400154b3  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400154b8  test    eax, eax
0x1400154ba  jnz     loc_1400155DD
0x1400154c0  mov     [rsp+198h+arg_10], r15d
0x1400154c8  lea     rcx, [rsp+198h+var_178]; this
0x1400154cd  call    ??0ATManager@@QEAA@XZ; ATManager::ATManager(void)
0x1400154d2  nop
0x1400154d3  lea     rcx, [rsp+198h+var_178]
0x1400154d8  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x1400154dd  mov     rcx, [rax]
0x1400154e0  mov     [rsp+198h+arg_8], rcx
0x1400154e8  test    rcx, rcx
0x1400154eb  jz      loc_1400155D3
0x1400154f1  lea     rdx, [rsp+198h+arg_8]
0x1400154f9  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x1400154fe  mov     rbx, [rax]
0x140015501  lea     rcx, [rbx+28h]
0x140015505  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001550a  test    al, al
0x14001550c  jz      loc_1400155C5
0x140015512  lea     r8, [rsp+198h+arg_10]; unsigned int *
0x14001551a  mov     rdx, [rbx]; unsigned __int16 *
0x14001551d  mov     rcx, [rsp+198h+arg_28]; this
0x140015525  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001552a  test    eax, eax
0x14001552c  jnz     loc_1400155C5
0x140015532  mov     r8d, [rsp+198h+arg_10]
0x14001553a  test    r8b, 2
0x14001553e  jz      loc_1400155C5
0x140015544  mov     dword ptr [r14+128h], 1
0x14001554f  and     r8d, 0FFFFFFFDh; unsigned int
0x140015553  mov     [rsp+198h+arg_10], r8d
0x14001555b  mov     rdx, [rbx]; unsigned __int16 *
0x14001555e  mov     rcx, [rsp+198h+arg_28]; this
0x140015566  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x14001556b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001556f  test    byte ptr [rsp+198h+arg_10], 1
0x140015577  jz      short loc_14001559C
0x140015579  inc     rax
0x14001557c  cmp     [rsi+rax*2], r15w
0x140015581  jnz     short loc_140015579
0x140015583  test    rax, rax
0x140015586  jz      short loc_140015597
0x140015588  lea     r8, asc_14002D6B4; ","
0x14001558f  mov     rcx, rsi; unsigned __int16 *
0x140015592  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140015597  mov     rcx, rsi
0x14001559a  jmp     short loc_1400155BD
0x14001559c  inc     rax
0x14001559f  cmp     [rdi+rax*2], r15w
0x1400155a4  jnz     short loc_14001559C
0x1400155a6  test    rax, rax
0x1400155a9  jz      short loc_1400155BA
0x1400155ab  lea     r8, asc_14002D6B4; ","
0x1400155b2  mov     rcx, rdi; unsigned __int16 *
0x1400155b5  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400155ba  mov     rcx, rdi; unsigned __int16 *
0x1400155bd  mov     r8, [rbx]; unsigned __int16 *
0x1400155c0  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400155c5  cmp     [rsp+198h+arg_8], r15
0x1400155cd  jnz     loc_1400154F1
0x1400155d3  lea     rcx, [rsp+198h+var_178]; this
0x1400155d8  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x1400155dd  lea     r11, [rsp+198h+var_18]
0x1400155e5  mov     rbx, [r11+20h]
0x1400155e9  mov     rsi, [r11+38h]
0x1400155ed  mov     rsp, r11
0x1400155f0  pop     r15
0x1400155f2  pop     r14
0x1400155f4  pop     rdi
0x1400155f5  retn
```
