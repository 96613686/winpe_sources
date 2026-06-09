# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x1801212f0`
- end: `0x180121451`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `353`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1801212f0`
- `0x1801214e8`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121315`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121332`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121352`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18012136e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18012138a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1801213ac`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1801213f6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121411`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18012142a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121444`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121315`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121332`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121352`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18012136e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18012138a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1801213ac`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1801213f6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121411`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18012142a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180121444`

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
0x1801212f0  mov     [rsp+arg_8], rbx
0x1801212f5  mov     [rsp+arg_10], rbp
0x1801212fa  push    rsi
0x1801212fb  push    rdi
0x1801212fc  push    r15
0x1801212fe  sub     rsp, 20h
0x180121302  mov     rdi, rdx
0x180121305  mov     rsi, rcx
0x180121308  lea     rdx, [rcx+6Ch]; pv
0x18012130c  mov     r8d, 10h; cb
0x180121312  mov     rcx, rdi; pstm
0x180121315  call    cs:__imp_IStream_Write
0x18012131b  mov     ebx, eax
0x18012131d  test    eax, eax
0x18012131f  js      loc_1801213D1
0x180121325  lea     rdx, [rsi+7Ch]; pv
0x180121329  mov     r8d, 4; cb
0x18012132f  mov     rcx, rdi; pstm
0x180121332  call    cs:__imp_IStream_Write
0x180121338  mov     ebx, eax
0x18012133a  test    eax, eax
0x18012133c  js      loc_1801213D1
0x180121342  mov     r15d, 1
0x180121348  lea     rdx, [rsi+61h]; pv
0x18012134c  mov     r8d, r15d; cb
0x18012134f  mov     rcx, rdi; pstm
0x180121352  call    cs:__imp_IStream_Write
0x180121358  mov     ebx, eax
0x18012135a  test    eax, eax
0x18012135c  js      short loc_1801213D1
0x18012135e  mov     r8d, r15d; cb
0x180121361  mov     [rsp+38h+pv], 0
0x180121366  lea     rdx, [rsp+38h+pv]; pv
0x18012136b  mov     rcx, rdi; pstm
0x18012136e  call    cs:__imp_IStream_Write
0x180121374  mov     ebx, eax
0x180121376  test    eax, eax
0x180121378  js      short loc_1801213BE
0x18012137a  lea     rbp, [rsi+88h]
0x180121381  mov     r8d, r15d; cb
0x180121384  mov     rdx, rbp; pv
0x180121387  mov     rcx, rdi; pstm
0x18012138a  call    cs:__imp_IStream_Write
0x180121390  mov     ebx, eax
0x180121392  test    eax, eax
0x180121394  js      short loc_1801213BE
0x180121396  cmp     byte ptr [rbp+0], 0
0x18012139a  jnz     short loc_1801213E6
0x18012139c  lea     rbp, [rsi+90h]
0x1801213a3  mov     r8d, r15d; cb
0x1801213a6  mov     rdx, rbp; pv
0x1801213a9  mov     rcx, rdi; pstm
0x1801213ac  call    cs:__imp_IStream_Write
0x1801213b2  mov     ebx, eax
0x1801213b4  test    eax, eax
0x1801213b6  js      short loc_1801213BE
0x1801213b8  cmp     byte ptr [rbp+0], 0
0x1801213bc  jnz     short loc_180121434
0x1801213be  mov     dl, r15b
0x1801213c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x1801213c8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801213cd  test    ebx, ebx
0x1801213cf  jns     short loc_180121404
0x1801213d1  mov     rbp, [rsp+38h+arg_10]
0x1801213d6  mov     eax, ebx
0x1801213d8  mov     rbx, [rsp+38h+arg_8]
0x1801213dd  add     rsp, 20h
0x1801213e1  pop     r15
0x1801213e3  pop     rdi
0x1801213e4  pop     rsi
0x1801213e5  retn
0x1801213e6  lea     rdx, [rsi+8Ch]; pv
0x1801213ed  mov     r8d, 4; cb
0x1801213f3  mov     rcx, rdi; pstm
0x1801213f6  call    cs:__imp_IStream_Write
0x1801213fc  mov     ebx, eax
0x1801213fe  test    eax, eax
0x180121400  jns     short loc_18012139C
0x180121402  jmp     short loc_1801213BE
0x180121404  lea     rdx, [rsi+68h]; pv
0x180121408  mov     r8d, 4; cb
0x18012140e  mov     rcx, rdi; pstm
0x180121411  call    cs:__imp_IStream_Write
0x180121417  mov     ebx, eax
0x180121419  test    eax, eax
0x18012141b  js      short loc_1801213D1
0x18012141d  lea     rdx, [rsi+0A0h]; pv
0x180121424  mov     r8d, r15d; cb
0x180121427  mov     rcx, rdi; pstm
0x18012142a  call    cs:__imp_IStream_Write
0x180121430  mov     ebx, eax
0x180121432  jmp     short loc_1801213D1
0x180121434  lea     rdx, [rsi+94h]; pv
0x18012143b  mov     r8d, 4; cb
0x180121441  mov     rcx, rdi; pstm
0x180121444  call    cs:__imp_IStream_Write
0x18012144a  mov     ebx, eax
0x18012144c  jmp     loc_1801213BE
```
