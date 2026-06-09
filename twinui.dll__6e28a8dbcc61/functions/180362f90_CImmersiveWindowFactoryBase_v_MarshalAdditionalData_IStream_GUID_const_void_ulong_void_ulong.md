# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180362f90`
- end: `0x1803630ea`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `346`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180362bd0`
- `0x180362f90`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180362fb5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180362fd2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180362ff2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180363012`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18036302e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18036304e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18036306a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18036308c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803630b4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803630cd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180362fb5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180362fd2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180362ff2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180363012`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18036302e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18036304e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18036306a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18036308c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803630b4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1803630cd`

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
0x180362f90  mov     [rsp+arg_8], rbx
0x180362f95  mov     [rsp+arg_10], rbp
0x180362f9a  push    rsi
0x180362f9b  push    rdi
0x180362f9c  push    r15
0x180362f9e  sub     rsp, 20h
0x180362fa2  mov     rdi, rdx
0x180362fa5  mov     rsi, rcx
0x180362fa8  lea     rdx, [rcx+6Ch]; pv
0x180362fac  mov     r8d, 10h; cb
0x180362fb2  mov     rcx, rdi; pstm
0x180362fb5  call    cs:__imp_IStream_Write
0x180362fbb  mov     ebx, eax
0x180362fbd  test    eax, eax
0x180362fbf  js      loc_1803630D5
0x180362fc5  lea     rdx, [rsi+7Ch]; pv
0x180362fc9  mov     r8d, 4; cb
0x180362fcf  mov     rcx, rdi; pstm
0x180362fd2  call    cs:__imp_IStream_Write
0x180362fd8  mov     ebx, eax
0x180362fda  test    eax, eax
0x180362fdc  js      loc_1803630D5
0x180362fe2  mov     r15d, 1
0x180362fe8  lea     rdx, [rsi+61h]; pv
0x180362fec  mov     r8d, r15d; cb
0x180362fef  mov     rcx, rdi; pstm
0x180362ff2  call    cs:__imp_IStream_Write
0x180362ff8  mov     ebx, eax
0x180362ffa  test    eax, eax
0x180362ffc  js      loc_1803630D5
0x180363002  mov     r8d, r15d; cb
0x180363005  mov     [rsp+38h+pv], 0
0x18036300a  lea     rdx, [rsp+38h+pv]; pv
0x18036300f  mov     rcx, rdi; pstm
0x180363012  call    cs:__imp_IStream_Write
0x180363018  mov     ebx, eax
0x18036301a  test    eax, eax
0x18036301c  js      short loc_180363094
0x18036301e  lea     rbp, [rsi+88h]
0x180363025  mov     r8d, r15d; cb
0x180363028  mov     rdx, rbp; pv
0x18036302b  mov     rcx, rdi; pstm
0x18036302e  call    cs:__imp_IStream_Write
0x180363034  mov     ebx, eax
0x180363036  test    eax, eax
0x180363038  js      short loc_180363094
0x18036303a  cmp     byte ptr [rbp+0], 0
0x18036303e  jz      short loc_18036305A
0x180363040  lea     rdx, [rsi+8Ch]; pv
0x180363047  mov     rcx, rdi; pstm
0x18036304a  lea     r8d, [r15+3]; cb
0x18036304e  call    cs:__imp_IStream_Write
0x180363054  mov     ebx, eax
0x180363056  test    eax, eax
0x180363058  js      short loc_180363094
0x18036305a  lea     rbp, [rsi+90h]
0x180363061  mov     r8d, r15d; cb
0x180363064  mov     rdx, rbp; pv
0x180363067  mov     rcx, rdi; pstm
0x18036306a  call    cs:__imp_IStream_Write
0x180363070  mov     ebx, eax
0x180363072  test    eax, eax
0x180363074  js      short loc_180363094
0x180363076  cmp     byte ptr [rbp+0], 0
0x18036307a  jz      short loc_180363094
0x18036307c  lea     rdx, [rsi+94h]; pv
0x180363083  mov     r8d, 4; cb
0x180363089  mov     rcx, rdi; pstm
0x18036308c  call    cs:__imp_IStream_Write
0x180363092  mov     ebx, eax
0x180363094  mov     dl, r15b
0x180363097  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x18036309e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1803630a3  test    ebx, ebx
0x1803630a5  js      short loc_1803630D5
0x1803630a7  lea     rdx, [rsi+68h]; pv
0x1803630ab  mov     r8d, 4; cb
0x1803630b1  mov     rcx, rdi; pstm
0x1803630b4  call    cs:__imp_IStream_Write
0x1803630ba  mov     ebx, eax
0x1803630bc  test    eax, eax
0x1803630be  js      short loc_1803630D5
0x1803630c0  lea     rdx, [rsi+0A0h]; pv
0x1803630c7  mov     r8d, r15d; cb
0x1803630ca  mov     rcx, rdi; pstm
0x1803630cd  call    cs:__imp_IStream_Write
0x1803630d3  mov     ebx, eax
0x1803630d5  mov     rbp, [rsp+38h+arg_10]
0x1803630da  mov     eax, ebx
0x1803630dc  mov     rbx, [rsp+38h+arg_8]
0x1803630e1  add     rsp, 20h
0x1803630e5  pop     r15
0x1803630e7  pop     rdi
0x1803630e8  pop     rsi
0x1803630e9  retn
```
