# CIASMigrationHelper::ConvertEAPBlob(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004bdbc`
- end: `0x18004bfc2`
- name: `?ConvertEAPBlob@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bfc8`

## callees

- `0x18002f240`
- `0x18004115c`
- `0x180047604`
- `0x180047e34`
- `0x180048590`
- `0x180048b24`
- `0x18004bdbc`
- `0x18004d294`
- `0x18004d498`
- `0x180058010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004bea6`
- `KERNEL32!LocalFree` at `0x18004bf16`
- `KERNEL32!LocalFree` at `0x18004bea6`
- `KERNEL32!LocalFree` at `0x18004bf16`
- `OLEAUT32!__imp_VariantClear` at `0x18004be14`
- `OLEAUT32!__imp_VariantClear` at `0x18004bf20`
- `OLEAUT32!__imp_VariantClear` at `0x18004bfa3`
- `OLEAUT32!__imp_VariantClear` at `0x18004be14`
- `OLEAUT32!__imp_VariantClear` at `0x18004bf20`
- `OLEAUT32!__imp_VariantClear` at `0x18004bfa3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004bf98`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004bf98`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004be94`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004be94`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CIASMigrationHelper::ConvertEAPBlob(__int64 a1)
{
  __int64 v2; // rax
  const struct tagVARIANT *v3; // rax
  int v5; // edx
  int v6; // ebx
  unsigned __int8 *v7; // r14
  unsigned int v8; // edi
  SAFEARRAY *Vector; // rsi
  signed int i; // r9d
  __int64 j; // r8
  __int64 v12; // r10
  _BYTE *k; // rcx
  struct IUnknown *v14; // rdi
  int v15; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-39h] BYREF
  SAFEARRAY *psa; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v18; // [rsp+50h] [rbp-19h]
  unsigned __int8 *v19; // [rsp+58h] [rbp-11h]
  VARIANTARG pvargDest; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG v21[2]; // [rsp+80h] [rbp+17h] BYREF
  unsigned int v22; // [rsp+D8h] [rbp+6Fh] BYREF
  HLOCAL hMem; // [rsp+E0h] [rbp+77h] BYREF

  v2 = ((__int64 (*)(void))_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->)();
  v3 = (const struct tagVARIANT *)MSXML2::IXMLDOMNode::GetnodeTypedValue(v2, v21);
  pvarg.vt = 0;
  ATL::CComVariant::InternalCopy((ATL::CComVariant *)&pvarg, v3);
  _variant_t::~_variant_t((_variant_t *)v21);
  if ( pvarg.vt == 8204 )
  {
    VariantClear(&pvarg);
    return 2147942487LL;
  }
  else
  {
    CVariantVector<unsigned char>::CVariantVector<unsigned char>(&psa, &pvarg);
    if ( v18 >= 0x14 )
    {
      v7 = v19;
      v22 = 0;
      hMem = 0;
      v6 = MigrateEAPBlob(*v19, v5, v19 + 20, v18 - 20, (unsigned __int8 **)&hMem, &v22);
      if ( v6 >= 0 )
      {
        v8 = v22;
        Vector = SafeArrayCreateVector(0x11u, 0, v22 + 20);
        if ( Vector )
        {
          for ( i = 0; (unsigned int)i < 0x10; ++i )
            *((_BYTE *)Vector->pvData + i) = v7[i];
          v22 = v8;
          for ( j = 0; j != 4; ++j )
            *((_BYTE *)Vector->pvData + i++) = *((_BYTE *)&v22 + j);
          v12 = 0;
          for ( k = hMem; (unsigned int)v12 < v8; v12 = (unsigned int)(v12 + 1) )
            *((_BYTE *)Vector->pvData + i++) = k[v12];
          LocalFree(k);
          VariantClear(&pvarg);
          pvarg.vt = 8209;
          pvarg.llVal = (LONGLONG)Vector;
          v14 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
          _variant_t::_variant_t(&pvargDest, &pvarg);
          v21[0] = pvargDest;
          v15 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v14->lpVtbl[10].AddRef)(v14, v21);
          if ( v15 < 0 )
            _com_issue_errorex(v15, v14, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
          _variant_t::~_variant_t((_variant_t *)&pvargDest);
        }
        else
        {
          LocalFree(hMem);
          v6 = -2147024882;
        }
      }
    }
    else
    {
      v6 = -2147024809;
    }
    SafeArrayUnaccessData(psa);
    VariantClear(&pvarg);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x18004bdbc  mov     [rsp-8+arg_0], rbx
0x18004bdc1  push    rbp
0x18004bdc2  push    rsi
0x18004bdc3  push    rdi
0x18004bdc4  push    r14
0x18004bdc6  push    r15
0x18004bdc8  lea     rbp, [rsp-37h]
0x18004bdcd  sub     rsp, 0A0h
0x18004bdd4  mov     r15, rcx
0x18004bdd7  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004bddc  lea     rdx, [rbp+57h+var_40]
0x18004bde0  mov     rcx, rax
0x18004bde3  call    ?GetnodeTypedValue@IXMLDOMNode@MSXML2@@QEAA?AV_variant_t@@XZ; MSXML2::IXMLDOMNode::GetnodeTypedValue(void)
0x18004bde8  nop
0x18004bde9  xor     edx, edx
0x18004bdeb  mov     word ptr [rbp+57h+pvarg], dx
0x18004bdef  mov     rdx, rax; struct tagVARIANT *
0x18004bdf2  lea     rcx, [rbp+57h+pvarg]; this
0x18004bdf6  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18004bdfb  nop
0x18004bdfc  lea     rcx, [rbp+57h+var_40]; this
0x18004be00  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004be05  mov     eax, 200Ch
0x18004be0a  cmp     word ptr [rbp+57h+pvarg], ax
0x18004be0e  jnz     short loc_18004BE24
0x18004be10  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004be14  call    cs:__imp_VariantClear
0x18004be1a  mov     eax, 80070057h
0x18004be1f  jmp     loc_18004BFAB
0x18004be24  lea     rdx, [rbp+57h+pvarg]
0x18004be28  lea     rcx, [rbp+57h+psa]
0x18004be2c  call    ??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@@Z; CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *)
0x18004be31  nop
0x18004be32  mov     r9d, [rbp+57h+var_70]
0x18004be36  cmp     r9d, 14h
0x18004be3a  jnb     short loc_18004BE46
0x18004be3c  mov     ebx, 80070057h
0x18004be41  jmp     loc_18004BF94
0x18004be46  mov     r14, [rbp+57h+var_68]
0x18004be4a  mov     [rbp+57h+arg_8], 0
0x18004be51  mov     [rbp+57h+hMem], 0
0x18004be59  add     r9d, 0FFFFFFECh; unsigned int
0x18004be5d  lea     r8, [r14+14h]; unsigned __int8 *
0x18004be61  movzx   ecx, byte ptr [r14]; int
0x18004be65  lea     rax, [rbp+57h+arg_8]
0x18004be69  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x18004be6e  lea     rax, [rbp+57h+hMem]
0x18004be72  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 **
0x18004be77  call    ?MigrateEAPBlob@@YAJHHPEAEKPEAPEAEPEAK@Z; MigrateEAPBlob(int,int,uchar *,ulong,uchar * *,ulong *)
0x18004be7c  mov     ebx, eax
0x18004be7e  test    eax, eax
0x18004be80  js      loc_18004BF94
0x18004be86  mov     edi, [rbp+57h+arg_8]
0x18004be89  lea     r8d, [rdi+14h]; cElements
0x18004be8d  mov     ecx, 11h; vt
0x18004be92  xor     edx, edx; lLbound
0x18004be94  call    cs:__imp_SafeArrayCreateVector
0x18004be9a  mov     rsi, rax
0x18004be9d  test    rax, rax
0x18004bea0  jnz     short loc_18004BEB6
0x18004bea2  mov     rcx, [rbp+57h+hMem]; hMem
0x18004bea6  call    cs:__imp_LocalFree
0x18004beac  mov     ebx, 8007000Eh
0x18004beb1  jmp     loc_18004BF94
0x18004beb6  xor     r9d, r9d
0x18004beb9  movsxd  rdx, r9d
0x18004bebc  mov     rcx, [rsi+10h]
0x18004bec0  mov     al, [rdx+r14]
0x18004bec4  mov     [rdx+rcx], al
0x18004bec7  inc     r9d
0x18004beca  cmp     r9d, 10h
0x18004bece  jb      short loc_18004BEB9
0x18004bed0  mov     [rbp+57h+arg_8], edi
0x18004bed3  xor     r8d, r8d
0x18004bed6  movsxd  rdx, r9d
0x18004bed9  mov     rcx, [rsi+10h]
0x18004bedd  mov     al, byte ptr [rbp+r8+57h+arg_8]
0x18004bee2  mov     [rdx+rcx], al
0x18004bee5  inc     r9d
0x18004bee8  inc     r8
0x18004beeb  cmp     r8, 4
0x18004beef  jnz     short loc_18004BED6
0x18004bef1  xor     r10d, r10d
0x18004bef4  mov     rcx, [rbp+57h+hMem]; hMem
0x18004bef8  test    edi, edi
0x18004befa  jz      short loc_18004BF16
0x18004befc  movsxd  r8, r9d
0x18004beff  mov     rdx, [rsi+10h]
0x18004bf03  mov     al, [r10+rcx]
0x18004bf07  mov     [r8+rdx], al
0x18004bf0b  inc     r9d
0x18004bf0e  inc     r10d
0x18004bf11  cmp     r10d, edi
0x18004bf14  jb      short loc_18004BEFC
0x18004bf16  call    cs:__imp_LocalFree
0x18004bf1c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004bf20  call    cs:__imp_VariantClear
0x18004bf26  mov     eax, 2011h
0x18004bf2b  mov     word ptr [rbp+57h+pvarg], ax
0x18004bf2f  mov     qword ptr [rbp+57h+pvarg+8], rsi
0x18004bf33  mov     rcx, r15
0x18004bf36  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004bf3b  mov     rdi, rax
0x18004bf3e  lea     rdx, [rbp+57h+pvarg]; pvargSrc
0x18004bf42  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x18004bf46  call    ??0_variant_t@@QEAA@AEBUtagVARIANT@@@Z; _variant_t::_variant_t(tagVARIANT const &)
0x18004bf4b  nop
0x18004bf4c  movups  xmm0, xmmword ptr [rbp+57h+pvargDest]
0x18004bf50  movaps  [rbp+57h+var_40], xmm0
0x18004bf54  movsd   xmm1, qword ptr [rbp+57h+pvargDest+10h]
0x18004bf59  movsd   [rbp+57h+var_30], xmm1
0x18004bf5e  mov     rcx, [rdi]
0x18004bf61  mov     rax, [rcx+0F8h]
0x18004bf68  lea     rdx, [rbp+57h+var_40]
0x18004bf6c  mov     rcx, rdi
0x18004bf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf74  test    eax, eax
0x18004bf76  jns     short loc_18004BF8A
0x18004bf78  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x18004bf7f  mov     rdx, rdi; struct IUnknown *
0x18004bf82  mov     ecx, eax; int
0x18004bf84  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18004bf8a  lea     rcx, [rbp+57h+pvargDest]; this
0x18004bf8e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004bf93  nop
0x18004bf94  mov     rcx, [rbp+57h+psa]; psa
0x18004bf98  call    cs:__imp_SafeArrayUnaccessData
0x18004bf9e  nop
0x18004bf9f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004bfa3  call    cs:__imp_VariantClear
0x18004bfa9  mov     eax, ebx
0x18004bfab  mov     rbx, [rsp+0C0h+arg_0]
0x18004bfb3  add     rsp, 0A0h
0x18004bfba  pop     r15
0x18004bfbc  pop     r14
0x18004bfbe  pop     rdi
0x18004bfbf  pop     rsi
0x18004bfc0  pop     rbp
0x18004bfc1  retn
```
