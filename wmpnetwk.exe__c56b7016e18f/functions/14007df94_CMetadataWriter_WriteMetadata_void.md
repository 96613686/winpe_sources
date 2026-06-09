# CMetadataWriter::WriteMetadata(void)

- ea: `0x14007df94`
- end: `0x14007e19c`
- name: `?WriteMetadata@CMetadataWriter@@QEAAJXZ`
- size: `520`
- prototype: `__int64 __fastcall(CMetadataWriter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14007d920`

## callees

- `0x140024688`
- `0x1400396dc`
- `0x14003d21c`
- `0x140046020`
- `0x140074550`
- `0x14007752c`
- `0x14007da30`
- `0x14007df94`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14007e145`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e155`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e145`
- `OLEAUT32!__imp_SysFreeString` at `0x14007e155`
- `ole32!PropVariantClear` at `0x14007e106`
- `ole32!PropVariantClear` at `0x14007e106`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x14007e08a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x14007e08a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMetadataWriter::WriteMetadata(CMetadataWriter *this)
{
  HRESULT CurrentItem; // edi
  void *v3; // rsi
  struct IPropertyStore *v4; // rbx
  int v5; // ecx
  int v6; // r8d
  unsigned int v7; // esi
  __int64 v8; // r15
  __int64 v9; // r12
  struct IHMEMediaContainer *v11; // [rsp+40h] [rbp-29h] BYREF
  PCWSTR pszPath[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v13; // [rsp+58h] [rbp-11h]
  __int64 v14; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v15; // [rsp+68h] [rbp-1h]
  __int64 v16; // [rsp+70h] [rbp+7h]
  int v17; // [rsp+78h] [rbp+Fh]
  __int64 v18; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int64 v19; // [rsp+88h] [rbp+1Fh]
  __int64 v20; // [rsp+90h] [rbp+27h]
  int v21; // [rsp+98h] [rbp+2Fh]
  void *ppv; // [rsp+D8h] [rbp+6Fh] BYREF
  void *Block; // [rsp+E0h] [rbp+77h] BYREF
  struct IPropertyStore *v24; // [rsp+E8h] [rbp+7Fh] BYREF

  Block = 0;
  LODWORD(ppv) = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  CurrentItem = CMetadataWriter::BuildFilterList(
                  (_DWORD)this,
                  (unsigned int)&Block,
                  (unsigned int)&ppv,
                  (unsigned int)&v14,
                  (__int64)&v18);
  v3 = Block;
  if ( CurrentItem >= 0 )
  {
    v11 = 0;
    v24 = 0;
    CurrentItem = CMetadataWriter::GetCurrentItem(this, (struct _WMCMetadataItem *)Block, (unsigned int)ppv, &v11, &v24);
    if ( CurrentItem >= 0 )
    {
      *(_OWORD *)pszPath = 0;
      v13 = 0;
      v4 = v24;
      if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PCWSTR *))v24->lpVtbl->GetValue)(
             v24,
             &PKEY_ItemUrl,
             pszPath) >= 0
        && LOWORD(pszPath[0]) == 31 )
      {
        Block = 0;
        ppv = 0;
        CurrentItem = SHCreateItemFromParsingName(pszPath[1], 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
        if ( CurrentItem >= 0 )
          CurrentItem = (*(__int64 (__fastcall **)(void *, __int64, GUID *, void **))(*(_QWORD *)ppv + 64LL))(
                          ppv,
                          2,
                          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                          &Block);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        if ( CurrentItem >= 0 )
          CurrentItem = CMetadataWriter::WriteCheckedMetadata(
                          v5,
                          (_DWORD)v3,
                          v6,
                          (_DWORD)v11,
                          (__int64)v4,
                          (__int64)&v14,
                          (__int64)&v18,
                          (__int64)Block);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&Block);
      }
      else
      {
        CurrentItem = -2147220631;
      }
      PropVariantClear((PROPVARIANT *)pszPath);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  }
  operator delete(v3);
  v7 = 0;
  if ( v15 )
  {
    v8 = v14;
    v9 = v18;
    do
    {
      if ( v7 >= v15 || (SysFreeString(*(BSTR *)(v8 + 8LL * v7)), v7 >= v19) )
        ATL::AtlThrowImpl(-2147024809);
      SysFreeString(*(BSTR *)(v9 + 8LL * v7++));
    }
    while ( v7 < v15 );
  }
  ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::~CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>(&v18);
  ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::~CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>(&v14);
  return (unsigned int)CurrentItem;
}

```

## disassembly

```asm
0x14007df94  mov     [rsp-8+arg_0], rbx
0x14007df99  push    rbp
0x14007df9a  push    rsi
0x14007df9b  push    rdi
0x14007df9c  push    r12
0x14007df9e  push    r15
0x14007dfa0  lea     rbp, [rsp-37h]
0x14007dfa5  sub     rsp, 0A0h
0x14007dfac  mov     rbx, rcx
0x14007dfaf  xor     r15d, r15d
0x14007dfb2  mov     [rbp+57h+Block], r15
0x14007dfb6  mov     dword ptr [rbp+57h+ppv], r15d
0x14007dfba  mov     [rbp+57h+var_60], r15
0x14007dfbe  mov     [rbp+57h+var_58], r15
0x14007dfc2  mov     [rbp+57h+var_50], r15
0x14007dfc6  mov     [rbp+57h+var_48], r15d
0x14007dfca  mov     [rbp+57h+var_40], r15
0x14007dfce  mov     [rbp+57h+var_38], r15
0x14007dfd2  mov     [rbp+57h+var_30], r15
0x14007dfd6  mov     [rbp+57h+var_28], r15d
0x14007dfda  lea     rax, [rbp+57h+var_40]
0x14007dfde  mov     [rsp+0C0h+var_A0], rax
0x14007dfe3  lea     r9, [rbp+57h+var_60]
0x14007dfe7  lea     r8, [rbp+57h+ppv]
0x14007dfeb  lea     rdx, [rbp+57h+Block]
0x14007dfef  call    ?BuildFilterList@CMetadataWriter@@IEAAJPEAPEAU_WMCMetadataItem@@PEAKAEAV?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@2@Z; CMetadataWriter::BuildFilterList(_WMCMetadataItem * *,ulong *,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> &,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> &)
0x14007dff4  mov     edi, eax
0x14007dff6  mov     rsi, [rbp+57h+Block]
0x14007dffa  test    eax, eax
0x14007dffc  js      loc_14007E120
0x14007e002  mov     [rbp+57h+var_80], r15
0x14007e006  mov     [rbp+57h+arg_18], r15
0x14007e00a  lea     rax, [rbp+57h+arg_18]
0x14007e00e  mov     [rsp+0C0h+var_A0], rax; struct IPropertyStore **
0x14007e013  lea     r9, [rbp+57h+var_80]; struct IHMEMediaContainer **
0x14007e017  mov     r8d, dword ptr [rbp+57h+ppv]; unsigned int
0x14007e01b  mov     rdx, rsi; struct _WMCMetadataItem *
0x14007e01e  mov     rcx, rbx; this
0x14007e021  call    ?GetCurrentItem@CMetadataWriter@@IEAAJPEAU_WMCMetadataItem@@KPEAPEAUIHMEMediaContainer@@PEAPEAUIPropertyStore@@@Z; CMetadataWriter::GetCurrentItem(_WMCMetadataItem *,ulong,IHMEMediaContainer * *,IPropertyStore * *)
0x14007e026  mov     edi, eax
0x14007e028  test    eax, eax
0x14007e02a  js      loc_14007E10D
0x14007e030  xorps   xmm0, xmm0
0x14007e033  xor     eax, eax
0x14007e035  movups  xmmword ptr [rbp+57h+pszPath], xmm0
0x14007e039  mov     [rbp+57h+var_68], rax
0x14007e03d  mov     rbx, [rbp+57h+arg_18]
0x14007e041  mov     rax, [rbx]
0x14007e044  lea     r8, [rbp+57h+pszPath]
0x14007e048  lea     rdx, PKEY_ItemUrl
0x14007e04f  mov     rcx, rbx
0x14007e052  mov     rax, [rax+28h]
0x14007e056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e05b  test    eax, eax
0x14007e05d  js      loc_14007E0FD
0x14007e063  lea     eax, [r15+1Fh]
0x14007e067  cmp     ax, word ptr [rbp+57h+pszPath]
0x14007e06b  jnz     loc_14007E0FD
0x14007e071  mov     [rbp+57h+Block], r15
0x14007e075  mov     [rbp+57h+ppv], r15
0x14007e079  lea     r9, [rbp+57h+ppv]; ppv
0x14007e07d  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x14007e084  xor     edx, edx; pbc
0x14007e086  mov     rcx, [rbp+57h+pszPath+8]; pszPath
0x14007e08a  call    cs:__imp_SHCreateItemFromParsingName
0x14007e090  mov     edi, eax
0x14007e092  test    eax, eax
0x14007e094  js      short loc_14007E0B7
0x14007e096  mov     rcx, [rbp+57h+ppv]
0x14007e09a  mov     rax, [rcx]
0x14007e09d  lea     r9, [rbp+57h+Block]
0x14007e0a1  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x14007e0a8  lea     edx, [r15+2]
0x14007e0ac  mov     rax, [rax+40h]
0x14007e0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e0b5  mov     edi, eax
0x14007e0b7  lea     rcx, [rbp+57h+ppv]
0x14007e0bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007e0c0  test    edi, edi
0x14007e0c2  js      short loc_14007E0F2
0x14007e0c4  mov     rax, [rbp+57h+Block]
0x14007e0c8  mov     [rsp+0C0h+var_88], rax
0x14007e0cd  lea     rax, [rbp+57h+var_40]
0x14007e0d1  mov     [rsp+0C0h+var_90], rax
0x14007e0d6  lea     rax, [rbp+57h+var_60]
0x14007e0da  mov     [rsp+0C0h+var_98], rax
0x14007e0df  mov     [rsp+0C0h+var_A0], rbx
0x14007e0e4  mov     r9, [rbp+57h+var_80]
0x14007e0e8  mov     rdx, rsi
0x14007e0eb  call    ?WriteCheckedMetadata@CMetadataWriter@@IEAAJPEAU_WMCMetadataItem@@KPEAUIHMEMediaContainer@@PEAUIPropertyStore@@AEBV?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@32@Z; CMetadataWriter::WriteCheckedMetadata(_WMCMetadataItem *,ulong,IHMEMediaContainer *,IPropertyStore *,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> const &,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> const &,IPropertyStore *)
0x14007e0f0  mov     edi, eax
0x14007e0f2  lea     rcx, [rbp+57h+Block]
0x14007e0f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007e0fb  jmp     short loc_14007E102
0x14007e0fd  mov     edi, 80040369h
0x14007e102  lea     rcx, [rbp+57h+pszPath]; pvar
0x14007e106  call    cs:__imp_PropVariantClear
0x14007e10c  nop
0x14007e10d  lea     rcx, [rbp+57h+arg_18]
0x14007e111  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007e116  nop
0x14007e117  lea     rcx, [rbp+57h+var_80]
0x14007e11b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14007e120  mov     rcx, rsi; Block
0x14007e123  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14007e128  mov     esi, r15d
0x14007e12b  cmp     [rbp+57h+var_58], r15
0x14007e12f  jbe     short loc_14007E165
0x14007e131  mov     r15, [rbp+57h+var_60]
0x14007e135  mov     r12, [rbp+57h+var_40]
0x14007e139  mov     ebx, esi
0x14007e13b  cmp     rbx, [rbp+57h+var_58]
0x14007e13f  jnb     short loc_14007E191
0x14007e141  mov     rcx, [r15+rbx*8]; bstrString
0x14007e145  call    cs:__imp_SysFreeString
0x14007e14b  cmp     rbx, [rbp+57h+var_38]
0x14007e14f  jnb     short loc_14007E191
0x14007e151  mov     rcx, [r12+rbx*8]; bstrString
0x14007e155  call    cs:__imp_SysFreeString
0x14007e15b  inc     esi
0x14007e15d  mov     eax, esi
0x14007e15f  cmp     rax, [rbp+57h+var_58]
0x14007e163  jb      short loc_14007E139
0x14007e165  lea     rcx, [rbp+57h+var_40]
0x14007e169  call    ??1?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>>::~CAtlArray<ushort *,ATL::CElementTraits<ushort *>>(void)
0x14007e16e  nop
0x14007e16f  lea     rcx, [rbp+57h+var_60]
0x14007e173  call    ??1?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>>::~CAtlArray<ushort *,ATL::CElementTraits<ushort *>>(void)
0x14007e178  mov     eax, edi
0x14007e17a  mov     rbx, [rsp+0C0h+arg_0]
0x14007e182  add     rsp, 0A0h
0x14007e189  pop     r15
0x14007e18b  pop     r12
0x14007e18d  pop     rdi
0x14007e18e  pop     rsi
0x14007e18f  pop     rbp
0x14007e190  retn
0x14007e191  mov     ecx, 80070057h; int
0x14007e196  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
