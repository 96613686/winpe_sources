# StartList::GetSessionValue(ushort *,uint,ATL::CRegKey &,bool)

- ea: `0x140015210`
- end: `0x1400152f9`
- name: `?GetSessionValue@StartList@@AEBAXPEAGIAEAVCRegKey@ATL@@_N@Z`
- size: `233`
- prototype: `void(StartList *__hidden this, unsigned __int16 *, unsigned int, struct ATL::CRegKey *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140014310`
- `0x140015fb8`

## callees

- `0x14000ea8c`
- `0x14000ecdc`
- `0x140015210`
- `0x1400169b8`
- `0x14001827c`
- `0x14001cdb0`

## string_xrefs

- `0x140015295`: `Configuration`
- `0x14001529c`: `SecureConfiguration`

## pseudocode

```c
void __fastcall StartList::GetSessionValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct ATL::CRegKey *a4,
        bool a5)
{
  LPCWSTR *v7; // rax
  unsigned int v8; // edi
  __int64 v9; // r8
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // r8
  StartList *v13; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+50h] [rbp+18h] BYREF

  v14 = a3;
  v13 = this;
  *a2 = 0;
  v7 = (LPCWSTR *)CATUtils::SessionKeyString((__int64)&v13);
  v8 = ATL::CRegKey::Open(a4, HKEY_LOCAL_MACHINE, *v7, 0x2001Fu);
  ATL::CStringData::Release((StartList *)((char *)v13 - 24));
  if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v9, v8);
  v10 = L"SecureConfiguration";
  v14 = 1024;
  if ( !a5 )
    v10 = L"Configuration";
  v11 = ATL::CRegKey::QueryStringValue(a4, v10, a2, &v14);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v12, v11);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x140015210  mov     r11, rsp
0x140015213  mov     [r11+10h], rbx
0x140015217  mov     [r11+18h], r8d
0x14001521b  mov     [r11+8], rcx
0x14001521f  push    rbp
0x140015220  push    rsi
0x140015221  push    rdi
0x140015222  sub     rsp, 20h
0x140015226  xor     eax, eax
0x140015228  lea     rcx, [r11+8]
0x14001522c  mov     [rdx], ax
0x14001522f  mov     rsi, r9
0x140015232  mov     rbx, rdx
0x140015235  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14001523a  mov     r9d, 2001Fh; unsigned int
0x140015240  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140015247  mov     rcx, rsi; this
0x14001524a  mov     r8, [rax]; lpSubKey
0x14001524d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140015252  mov     rcx, [rsp+38h+arg_0]
0x140015257  mov     edi, eax
0x140015259  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001525d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140015262  lea     rbp, WPP_GLOBAL_Control
0x140015269  test    edi, edi
0x14001526b  jz      short loc_140015290
0x14001526d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015274  cmp     rcx, rbp
0x140015277  jz      short loc_140015290
0x140015279  test    byte ptr [rcx+1Ch], 8
0x14001527d  jz      short loc_140015290
0x14001527f  mov     rcx, [rcx+10h]
0x140015283  mov     edx, 20h ; ' '
0x140015288  mov     r9d, edi
0x14001528b  call    WPP_SF_d
0x140015290  cmp     [rsp+38h+arg_20], 0
0x140015295  lea     rax, aConfiguration_0; "Configuration"
0x14001529c  lea     rdx, aSecureconfigur; "SecureConfiguration"
0x1400152a3  mov     [rsp+38h+arg_10], 400h
0x1400152ab  cmovz   rdx, rax; unsigned __int16 *
0x1400152af  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x1400152b4  mov     r8, rbx; unsigned __int16 *
0x1400152b7  mov     rcx, rsi; this
0x1400152ba  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1400152bf  test    eax, eax
0x1400152c1  jz      short loc_1400152EB
0x1400152c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400152ca  cmp     rcx, rbp
0x1400152cd  jz      short loc_1400152E6
0x1400152cf  test    byte ptr [rcx+1Ch], 8
0x1400152d3  jz      short loc_1400152E6
0x1400152d5  mov     rcx, [rcx+10h]
0x1400152d9  mov     edx, 21h ; '!'
0x1400152de  mov     r9d, eax
0x1400152e1  call    WPP_SF_d
0x1400152e6  xor     eax, eax
0x1400152e8  mov     [rbx], ax
0x1400152eb  mov     rbx, [rsp+38h+arg_8]
0x1400152f0  add     rsp, 20h
0x1400152f4  pop     rdi
0x1400152f5  pop     rsi
0x1400152f6  pop     rbp
0x1400152f7  retn
```
