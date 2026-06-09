# CMDEContentServer::UpdateConnectionInfo(IMFNetEvent *)

- ea: `0x1400307dc`
- end: `0x140030ae8`
- name: `?UpdateConnectionInfo@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@@Z`
- size: `780`
- prototype: `__int64 __fastcall(CMDEContentServer *__hidden this, struct IMFNetEvent *)`
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003fc9c`
- `0x14008c944`
- `0x14008d94c`

## callees

- `0x1400065e0`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c920`
- `0x1400105a0`
- `0x140015100`
- `0x140018df0`
- `0x140024688`
- `0x1400307dc`
- `0x140045f20`
- `0x14005480c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x140030a55`
- `KERNEL32!CompareStringOrdinal` at `0x140030a55`
- `ole32!PropVariantClear` at `0x140030a7b`
- `ole32!PropVariantClear` at `0x140030a85`
- `ole32!PropVariantClear` at `0x140030a7b`
- `ole32!PropVariantClear` at `0x140030a85`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMDEContentServer::UpdateConnectionInfo(CMDEContentServer *this, struct IMFNetEvent *a2)
{
  const WCHAR *v4; // rbx
  int v5; // esi
  unsigned int v6; // edi
  LPCWCH *v7; // rdi
  unsigned int v9; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v10; // [rsp+34h] [rbp-45h] BYREF
  const WCHAR *v11; // [rsp+38h] [rbp-41h] BYREF
  __int64 v12; // [rsp+40h] [rbp-39h] BYREF
  __int64 v13; // [rsp+48h] [rbp-31h] BYREF
  const void *v14; // [rsp+50h] [rbp-29h] BYREF
  __int64 v15; // [rsp+58h] [rbp-21h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v17; // [rsp+70h] [rbp-9h]
  PROPVARIANT v18[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v19; // [rsp+88h] [rbp+Fh]
  __int64 v20; // [rsp+90h] [rbp+17h]
  __int128 v21; // [rsp+98h] [rbp+1Fh] BYREF
  int v22; // [rsp+A8h] [rbp+2Fh]

  *(_OWORD *)v18 = 0;
  v19 = 0;
  *(_OWORD *)pvar = 0;
  v17 = 0;
  v12 = 0;
  v20 = 0;
  v4 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v11 = v4;
  v5 = (*(__int64 (__fastcall **)(struct IMFNetEvent *, GUID *, __int64 *))(*(_QWORD *)a2 + 304LL))(
         a2,
         &IID_IPropertyStore,
         &v12);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v5 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      277,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v5,
      v12);
  }
  if ( v5 >= 0 )
  {
    v21 = MFNETVROOT_CONNECTIONMANAGER;
    v22 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v12 + 40LL))(v12, &v21, v18);
    if ( v5 >= 0 )
    {
      v13 = 0;
      if ( LOWORD(v18[0]) != 13
        || !v18[1]
        || (**(int (__fastcall ***)(PROPVARIANT, GUID *, __int64 *))v18[1])(
             v18[1],
             &GUID_120c85a1_1764_437e_93bf_40d5cdac64cb,
             &v13) < 0 )
      {
        goto LABEL_27;
      }
      v9 = 0;
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v13 + 32LL))(v13, &v9);
      v6 = 0;
      if ( v9 )
      {
        do
        {
          v15 = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v13 + 40LL))(v13, v6, &v15) >= 0 )
          {
            v10 = 0;
            if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 24LL))(v15, &v10) >= 0 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v14);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                &v14,
                L"%d",
                v10);
              if ( v6 )
                ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&v11, L",");
              ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&v11, &v14);
              ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v14);
            }
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
          ++v6;
        }
        while ( v6 < v9 );
        v4 = v11;
      }
      if ( (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v12 + 40LL))(
             v12,
             qword_1400BF698,
             pvar) < 0 )
        goto LABEL_27;
      if ( LOWORD(pvar[0]) == 19 )
      {
        if ( !LODWORD(pvar[1]) )
        {
          v7 = (LPCWCH *)((char *)this + 480);
          goto LABEL_24;
        }
        if ( LODWORD(pvar[1]) == 2 )
        {
          v7 = (LPCWCH *)((char *)this + 488);
LABEL_24:
          if ( CompareStringOrdinal(*v7, -1, v4, -1, 0) != 2 )
          {
            ATL::CSimpleStringT<unsigned short,0>::operator=(v7, &v11);
            *((_DWORD *)this + 118) = 1;
          }
        }
      }
      PropVariantClear(pvar);
LABEL_27:
      PropVariantClear(v18);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400307dc  mov     [rsp-8+arg_10], rbx
0x1400307e1  mov     [rsp-8+arg_18], rsi
0x1400307e6  push    rbp
0x1400307e7  push    rdi
0x1400307e8  push    r14
0x1400307ea  lea     rbp, [rsp-47h]
0x1400307ef  sub     rsp, 0C0h
0x1400307f6  mov     rax, cs:__security_cookie
0x1400307fd  xor     rax, rsp
0x140030800  mov     [rbp+57h+var_20], rax
0x140030804  mov     rdi, rdx
0x140030807  mov     r14, rcx
0x14003080a  xorps   xmm0, xmm0
0x14003080d  xor     eax, eax
0x14003080f  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x140030813  mov     [rbp+57h+var_48], rax
0x140030817  xorps   xmm1, xmm1
0x14003081a  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x14003081e  mov     [rbp+57h+var_60], rax
0x140030822  mov     [rbp+57h+var_90], rax
0x140030826  mov     [rbp+57h+var_40], rax
0x14003082a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140030831  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140030838  mov     rax, [rax+18h]
0x14003083c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030841  lea     rbx, [rax+18h]
0x140030845  mov     [rbp+57h+var_98], rbx
0x140030849  mov     rax, [rdi]
0x14003084c  lea     r8, [rbp+57h+var_90]
0x140030850  lea     rdx, IID_IPropertyStore
0x140030857  mov     rcx, rdi
0x14003085a  mov     rax, [rax+130h]
0x140030861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030866  mov     esi, eax
0x140030868  lea     rax, WPP_GLOBAL_Control
0x14003086f  mov     rcx, cs:WPP_GLOBAL_Control
0x140030876  cmp     rcx, rax
0x140030879  jz      short loc_1400308B5
0x14003087b  test    byte ptr [rcx+1Ch], 2
0x14003087f  jz      short loc_1400308B5
0x140030881  mov     edx, esi
0x140030883  sar     edx, 1Fh
0x140030886  and     edx, 0FFFFFFFDh
0x140030889  add     edx, 5
0x14003088c  movzx   eax, byte ptr [rcx+19h]
0x140030890  cmp     eax, edx
0x140030892  jb      short loc_1400308B5
0x140030894  mov     edx, 115h
0x140030899  mov     rax, [rbp+57h+var_90]
0x14003089d  mov     qword ptr [rsp+0D0h+bIgnoreCase], rax
0x1400308a2  mov     r9d, esi
0x1400308a5  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x1400308ac  mov     rcx, [rcx+10h]
0x1400308b0  call    WPP_SF_dq
0x1400308b5  test    esi, esi
0x1400308b7  js      loc_140030AA2
0x1400308bd  movups  xmm0, cs:MFNETVROOT_CONNECTIONMANAGER
0x1400308c4  movdqu  [rbp+57h+var_38], xmm0
0x1400308c9  mov     [rbp+57h+var_28], 0
0x1400308d0  mov     rcx, [rbp+57h+var_90]
0x1400308d4  mov     rax, [rcx]
0x1400308d7  lea     r8, [rbp+57h+var_58]
0x1400308db  lea     rdx, [rbp+57h+var_38]
0x1400308df  mov     rax, [rax+28h]
0x1400308e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400308e8  mov     esi, eax
0x1400308ea  test    eax, eax
0x1400308ec  js      loc_140030AA2
0x1400308f2  mov     [rbp+57h+var_88], 0
0x1400308fa  mov     eax, 0Dh
0x1400308ff  cmp     ax, word ptr [rbp+57h+var_58]
0x140030903  jnz     loc_140030A81
0x140030909  mov     rcx, [rbp+57h+var_58+8]
0x14003090d  test    rcx, rcx
0x140030910  jz      loc_140030A81
0x140030916  mov     rax, [rcx]
0x140030919  lea     r8, [rbp+57h+var_88]
0x14003091d  lea     rdx, _GUID_120c85a1_1764_437e_93bf_40d5cdac64cb
0x140030924  mov     rax, [rax]
0x140030927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003092c  test    eax, eax
0x14003092e  js      loc_140030A81
0x140030934  mov     [rbp+57h+var_A0], 0
0x14003093b  mov     rcx, [rbp+57h+var_88]
0x14003093f  mov     rax, [rcx]
0x140030942  lea     rdx, [rbp+57h+var_A0]
0x140030946  mov     rax, [rax+20h]
0x14003094a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003094f  xor     edi, edi
0x140030951  cmp     [rbp+57h+var_A0], edi
0x140030954  jbe     loc_1400309FB
0x14003095a  mov     [rbp+57h+var_78], 0
0x140030962  mov     rcx, [rbp+57h+var_88]
0x140030966  mov     rax, [rcx]
0x140030969  lea     r8, [rbp+57h+var_78]
0x14003096d  mov     edx, edi
0x14003096f  mov     rax, [rax+28h]
0x140030973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030978  test    eax, eax
0x14003097a  js      short loc_1400309E3
0x14003097c  mov     [rbp+57h+var_9C], 0
0x140030983  mov     rcx, [rbp+57h+var_78]
0x140030987  mov     rax, [rcx]
0x14003098a  lea     rdx, [rbp+57h+var_9C]
0x14003098e  mov     rax, [rax+18h]
0x140030992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030997  test    eax, eax
0x140030999  js      short loc_1400309E3
0x14003099b  lea     rcx, [rbp+57h+var_80]
0x14003099f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x1400309a4  mov     r8d, [rbp+57h+var_9C]
0x1400309a8  lea     rdx, aD; "%d"
0x1400309af  lea     rcx, [rbp+57h+var_80]
0x1400309b3  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x1400309b8  test    edi, edi
0x1400309ba  jz      short loc_1400309CC
0x1400309bc  lea     rdx, asc_1400A3E98; ","
0x1400309c3  lea     rcx, [rbp+57h+var_98]
0x1400309c7  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1400309cc  lea     rdx, [rbp+57h+var_80]
0x1400309d0  lea     rcx, [rbp+57h+var_98]
0x1400309d4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x1400309d9  lea     rcx, [rbp+57h+var_80]
0x1400309dd  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400309e2  nop
0x1400309e3  lea     rcx, [rbp+57h+var_78]
0x1400309e7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400309ec  inc     edi
0x1400309ee  cmp     edi, [rbp+57h+var_A0]
0x1400309f1  jb      loc_14003095A
0x1400309f7  mov     rbx, [rbp+57h+var_98]
0x1400309fb  mov     rcx, [rbp+57h+var_90]
0x1400309ff  mov     rax, [rcx]
0x140030a02  lea     r8, [rbp+57h+pvar]
0x140030a06  lea     rdx, qword_1400BF698
0x140030a0d  mov     rax, [rax+28h]
0x140030a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030a16  test    eax, eax
0x140030a18  js      short loc_140030A81
0x140030a1a  mov     eax, 13h
0x140030a1f  cmp     ax, word ptr [rbp+57h+pvar]
0x140030a23  jnz     short loc_140030A77
0x140030a25  mov     eax, dword ptr [rbp+57h+pvar+8]
0x140030a28  test    eax, eax
0x140030a2a  jnz     short loc_140030A35
0x140030a2c  lea     rdi, [r14+1E0h]
0x140030a33  jmp     short loc_140030A41
0x140030a35  cmp     eax, 2
0x140030a38  jnz     short loc_140030A77
0x140030a3a  lea     rdi, [r14+1E8h]
0x140030a41  or      edx, 0FFFFFFFFh; cchCount1
0x140030a44  mov     [rsp+0D0h+bIgnoreCase], 0; bIgnoreCase
0x140030a4c  mov     r9d, edx; cchCount2
0x140030a4f  mov     r8, rbx; lpString2
0x140030a52  mov     rcx, [rdi]; lpString1
0x140030a55  call    cs:__imp_CompareStringOrdinal
0x140030a5b  cmp     eax, 2
0x140030a5e  jz      short loc_140030A77
0x140030a60  lea     rdx, [rbp+57h+var_98]
0x140030a64  mov     rcx, rdi
0x140030a67  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140030a6c  mov     dword ptr [r14+1D8h], 1
0x140030a77  lea     rcx, [rbp+57h+pvar]; pvar
0x140030a7b  call    cs:__imp_PropVariantClear
0x140030a81  lea     rcx, [rbp+57h+var_58]; pvar
0x140030a85  call    cs:__imp_PropVariantClear
0x140030a8b  nop
0x140030a8c  mov     rcx, [rbp+57h+var_88]
0x140030a90  test    rcx, rcx
0x140030a93  jz      short loc_140030AA2
0x140030a95  mov     rax, [rcx]
0x140030a98  mov     rax, [rax+10h]
0x140030a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030aa1  nop
0x140030aa2  lea     rcx, [rbx-18h]; this
0x140030aa6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140030aab  nop
0x140030aac  mov     rcx, [rbp+57h+var_90]
0x140030ab0  test    rcx, rcx
0x140030ab3  jz      short loc_140030AC2
0x140030ab5  mov     rax, [rcx]
0x140030ab8  mov     rax, [rax+10h]
0x140030abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030ac1  nop
0x140030ac2  mov     eax, esi
0x140030ac4  mov     rcx, [rbp+57h+var_20]
0x140030ac8  xor     rcx, rsp; StackCookie
0x140030acb  call    __security_check_cookie
0x140030ad0  lea     r11, [rsp+0D0h+var_10]
0x140030ad8  mov     rbx, [r11+30h]
0x140030adc  mov     rsi, [r11+38h]
0x140030ae0  mov     rsp, r11
0x140030ae3  pop     r14
0x140030ae5  pop     rdi
0x140030ae6  pop     rbp
0x140030ae7  retn
```
