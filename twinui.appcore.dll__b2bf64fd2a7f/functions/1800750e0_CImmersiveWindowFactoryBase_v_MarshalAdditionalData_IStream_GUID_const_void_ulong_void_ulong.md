# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x1800750e0`
- end: `0x18007523a`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `346`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180074ed4`
- `0x1800750e0`

## import_xrefs

- `SHCORE!IStream_Write` at `0x180075105`
- `SHCORE!IStream_Write` at `0x180075122`
- `SHCORE!IStream_Write` at `0x180075142`
- `SHCORE!IStream_Write` at `0x180075162`
- `SHCORE!IStream_Write` at `0x18007517e`
- `SHCORE!IStream_Write` at `0x18007519e`
- `SHCORE!IStream_Write` at `0x1800751ba`
- `SHCORE!IStream_Write` at `0x1800751dc`
- `SHCORE!IStream_Write` at `0x180075204`
- `SHCORE!IStream_Write` at `0x18007521d`
- `SHCORE!IStream_Write` at `0x180075105`
- `SHCORE!IStream_Write` at `0x180075122`
- `SHCORE!IStream_Write` at `0x180075142`
- `SHCORE!IStream_Write` at `0x180075162`
- `SHCORE!IStream_Write` at `0x18007517e`
- `SHCORE!IStream_Write` at `0x18007519e`
- `SHCORE!IStream_Write` at `0x1800751ba`
- `SHCORE!IStream_Write` at `0x1800751dc`
- `SHCORE!IStream_Write` at `0x180075204`
- `SHCORE!IStream_Write` at `0x18007521d`

## pseudocode

```c
__int64 __fastcall CImmersiveWindowFactoryBase::v_MarshalAdditionalData(
        CImmersiveWindowFactoryBase *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  char pv; // [rsp+40h] [rbp+8h] BYREF

  v6 = IStream_Write(a2, (char *)this + 108, 0x10u);
  if ( v6 >= 0 )
  {
    v6 = IStream_Write(a2, (char *)this + 124, 4u);
    if ( v6 >= 0 )
    {
      v6 = IStream_Write(a2, (char *)this + 97, 1u);
      if ( v6 >= 0 )
      {
        pv = 0;
        v6 = IStream_Write(a2, &pv, 1u);
        if ( v6 >= 0 )
        {
          v6 = IStream_Write(a2, (char *)this + 136, 1u);
          if ( v6 >= 0 )
          {
            if ( !*((_BYTE *)this + 136) || (v6 = IStream_Write(a2, (char *)this + 140, 4u), v6 >= 0) )
            {
              v6 = IStream_Write(a2, (char *)this + 144, 1u);
              if ( v6 >= 0 )
              {
                if ( *((_BYTE *)this + 144) )
                  v6 = IStream_Write(a2, (char *)this + 148, 4u);
              }
            }
          }
        }
        LOBYTE(v7) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl'::`2'::impl,
          v7);
        if ( v6 >= 0 )
        {
          v6 = IStream_Write(a2, (char *)this + 104, 4u);
          if ( v6 >= 0 )
            return (unsigned int)IStream_Write(a2, (char *)this + 160, 1u);
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800750e0  mov     [rsp+arg_8], rbx
0x1800750e5  mov     [rsp+arg_10], rbp
0x1800750ea  push    rsi
0x1800750eb  push    rdi
0x1800750ec  push    r15
0x1800750ee  sub     rsp, 20h
0x1800750f2  mov     rdi, rdx
0x1800750f5  mov     rsi, rcx
0x1800750f8  lea     rdx, [rcx+6Ch]; pv
0x1800750fc  mov     r8d, 10h; cb
0x180075102  mov     rcx, rdi; pstm
0x180075105  call    cs:__imp_IStream_Write
0x18007510b  mov     ebx, eax
0x18007510d  test    eax, eax
0x18007510f  js      loc_180075225
0x180075115  lea     rdx, [rsi+7Ch]; pv
0x180075119  mov     r8d, 4; cb
0x18007511f  mov     rcx, rdi; pstm
0x180075122  call    cs:__imp_IStream_Write
0x180075128  mov     ebx, eax
0x18007512a  test    eax, eax
0x18007512c  js      loc_180075225
0x180075132  mov     r15d, 1
0x180075138  lea     rdx, [rsi+61h]; pv
0x18007513c  mov     r8d, r15d; cb
0x18007513f  mov     rcx, rdi; pstm
0x180075142  call    cs:__imp_IStream_Write
0x180075148  mov     ebx, eax
0x18007514a  test    eax, eax
0x18007514c  js      loc_180075225
0x180075152  mov     r8d, r15d; cb
0x180075155  mov     [rsp+38h+pv], 0
0x18007515a  lea     rdx, [rsp+38h+pv]; pv
0x18007515f  mov     rcx, rdi; pstm
0x180075162  call    cs:__imp_IStream_Write
0x180075168  mov     ebx, eax
0x18007516a  test    eax, eax
0x18007516c  js      short loc_1800751E4
0x18007516e  lea     rbp, [rsi+88h]
0x180075175  mov     r8d, r15d; cb
0x180075178  mov     rdx, rbp; pv
0x18007517b  mov     rcx, rdi; pstm
0x18007517e  call    cs:__imp_IStream_Write
0x180075184  mov     ebx, eax
0x180075186  test    eax, eax
0x180075188  js      short loc_1800751E4
0x18007518a  cmp     byte ptr [rbp+0], 0
0x18007518e  jz      short loc_1800751AA
0x180075190  lea     rdx, [rsi+8Ch]; pv
0x180075197  mov     rcx, rdi; pstm
0x18007519a  lea     r8d, [r15+3]; cb
0x18007519e  call    cs:__imp_IStream_Write
0x1800751a4  mov     ebx, eax
0x1800751a6  test    eax, eax
0x1800751a8  js      short loc_1800751E4
0x1800751aa  lea     rbp, [rsi+90h]
0x1800751b1  mov     r8d, r15d; cb
0x1800751b4  mov     rdx, rbp; pv
0x1800751b7  mov     rcx, rdi; pstm
0x1800751ba  call    cs:__imp_IStream_Write
0x1800751c0  mov     ebx, eax
0x1800751c2  test    eax, eax
0x1800751c4  js      short loc_1800751E4
0x1800751c6  cmp     byte ptr [rbp+0], 0
0x1800751ca  jz      short loc_1800751E4
0x1800751cc  lea     rdx, [rsi+94h]; pv
0x1800751d3  mov     r8d, 4; cb
0x1800751d9  mov     rcx, rdi; pstm
0x1800751dc  call    cs:__imp_IStream_Write
0x1800751e2  mov     ebx, eax
0x1800751e4  mov     dl, r15b
0x1800751e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x1800751ee  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800751f3  test    ebx, ebx
0x1800751f5  js      short loc_180075225
0x1800751f7  lea     rdx, [rsi+68h]; pv
0x1800751fb  mov     r8d, 4; cb
0x180075201  mov     rcx, rdi; pstm
0x180075204  call    cs:__imp_IStream_Write
0x18007520a  mov     ebx, eax
0x18007520c  test    eax, eax
0x18007520e  js      short loc_180075225
0x180075210  lea     rdx, [rsi+0A0h]; pv
0x180075217  mov     r8d, r15d; cb
0x18007521a  mov     rcx, rdi; pstm
0x18007521d  call    cs:__imp_IStream_Write
0x180075223  mov     ebx, eax
0x180075225  mov     rbp, [rsp+38h+arg_10]
0x18007522a  mov     eax, ebx
0x18007522c  mov     rbx, [rsp+38h+arg_8]
0x180075231  add     rsp, 20h
0x180075235  pop     r15
0x180075237  pop     rdi
0x180075238  pop     rsi
0x180075239  retn
```
