# CFileInputStream::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x18007b0a0`
- end: `0x18007b20b`
- name: `?v_MarshalAdditionalData@CFileInputStream@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `363`
- prototype: `int(CFileInputStream *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ddd4`
- `0x18002fa60`
- `0x18002fc28`
- `0x180072978`
- `0x18007b0a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18007b174`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18007b1c6`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18007b174`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18007b1c6`

## pseudocode

```c
__int64 __fastcall CFileInputStream::v_MarshalAdditionalData(
        CFileInputStream *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4,
        DWORD dwDestContext,
        void *pvDestContext,
        DWORD mshlflags)
{
  CMarshaledInterface *v7; // r12
  HRESULT v10; // ebx
  DWORD v11; // ebp
  void *v12; // r14
  LPUNKNOWN pUnk[9]; // [rsp+30h] [rbp-48h] BYREF
  BOOL pv; // [rsp+80h] [rbp+8h] BYREF

  v7 = (CFileInputStream *)((char *)this + 144);
  pv = *((_QWORD *)this + 18) != 0;
  v10 = IStream_Write(a2, (char *)this + 168, 8u);
  if ( v10 >= 0 )
  {
    v10 = IStream_Write(a2, (char *)this + 152, 4u);
    if ( v10 >= 0 )
    {
      v10 = IStream_Write(a2, (char *)this + 156, 4u);
      if ( v10 >= 0 )
      {
        v10 = IStream_Write(a2, &pv, 4u);
        if ( v10 >= 0 )
        {
          v11 = mshlflags;
          v12 = pvDestContext;
          v10 = CoMarshalInterface(
                  a2,
                  &GUID_bb94daad_7836_4d62_9557_2a7b83839b7b,
                  *((LPUNKNOWN *)this + 17),
                  dwDestContext,
                  pvDestContext,
                  mshlflags);
          if ( v10 >= 0 )
          {
            if ( !pv )
              return (unsigned int)CRasFilePlaceholderParams::MarshalAdditionalData(
                                     *((struct CRasFilePlaceholderParams **)this + 25),
                                     a2,
                                     dwDestContext,
                                     v12,
                                     v11);
            pUnk[0] = 0;
            v10 = CMarshaledInterface::Unmarshal<ISyncedStreamReaderInfo>(v7, (void **)pUnk);
            if ( v10 >= 0 )
              v10 = CoMarshalInterface(a2, &GUID_d18e07e4_d7b4_49ee_a04d_55955a063644, pUnk[0], dwDestContext, v12, v11);
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(pUnk);
            if ( v10 >= 0 )
              return (unsigned int)CRasFilePlaceholderParams::MarshalAdditionalData(
                                     *((struct CRasFilePlaceholderParams **)this + 25),
                                     a2,
                                     dwDestContext,
                                     v12,
                                     v11);
          }
        }
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007b0a0  push    rbx
0x18007b0a2  push    rbp
0x18007b0a3  push    rsi
0x18007b0a4  push    rdi
0x18007b0a5  push    r12
0x18007b0a7  push    r14
0x18007b0a9  sub     rsp, 48h
0x18007b0ad  xor     eax, eax
0x18007b0af  lea     r12, [rcx+90h]
0x18007b0b6  cmp     [r12], rax
0x18007b0ba  mov     rdi, rdx
0x18007b0bd  mov     rsi, rcx
0x18007b0c0  lea     rdx, [rcx+0A8h]; pv
0x18007b0c7  setnz   al
0x18007b0ca  mov     r8d, 8; cb
0x18007b0d0  mov     rcx, rdi; pstm
0x18007b0d3  mov     [rsp+78h+pv], eax
0x18007b0da  call    IStream_Write
0x18007b0df  mov     ebx, eax
0x18007b0e1  test    eax, eax
0x18007b0e3  js      loc_18007B1FC
0x18007b0e9  mov     ebp, 4
0x18007b0ee  lea     rdx, [rsi+98h]; pv
0x18007b0f5  mov     r8d, ebp; cb
0x18007b0f8  mov     rcx, rdi; pstm
0x18007b0fb  call    IStream_Write
0x18007b100  mov     ebx, eax
0x18007b102  test    eax, eax
0x18007b104  js      loc_18007B1FC
0x18007b10a  lea     rdx, [rsi+9Ch]; pv
0x18007b111  mov     r8d, ebp; cb
0x18007b114  mov     rcx, rdi; pstm
0x18007b117  call    IStream_Write
0x18007b11c  mov     ebx, eax
0x18007b11e  test    eax, eax
0x18007b120  js      loc_18007B1FC
0x18007b126  mov     r8d, ebp; cb
0x18007b129  lea     rdx, [rsp+78h+pv]; pv
0x18007b131  mov     rcx, rdi; pstm
0x18007b134  call    IStream_Write
0x18007b139  mov     ebx, eax
0x18007b13b  test    eax, eax
0x18007b13d  js      loc_18007B1FC
0x18007b143  mov     ebp, [rsp+78h+arg_30]
0x18007b14a  lea     rdx, _GUID_bb94daad_7836_4d62_9557_2a7b83839b7b; riid
0x18007b151  mov     r14, [rsp+78h+arg_28]
0x18007b159  mov     rcx, rdi; pStm
0x18007b15c  mov     r9d, [rsp+78h+dwDestContext]; dwDestContext
0x18007b164  mov     r8, [rsi+88h]; pUnk
0x18007b16b  mov     [rsp+78h+mshlflags], ebp; mshlflags
0x18007b16f  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x18007b174  call    cs:__imp_CoMarshalInterface
0x18007b17a  mov     ebx, eax
0x18007b17c  test    eax, eax
0x18007b17e  js      short loc_18007B1FC
0x18007b180  cmp     [rsp+78h+pv], 0
0x18007b188  jz      short loc_18007B1DC
0x18007b18a  lea     rdx, [rsp+78h+pUnk]; void **
0x18007b18f  mov     [rsp+78h+pUnk], 0
0x18007b198  mov     rcx, r12; this
0x18007b19b  call    ??$Unmarshal@UISyncedStreamReaderInfo@@@CMarshaledInterface@@QEAAJV?$ComPtrRef@V?$ComPtr@UISyncedStreamReaderInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; CMarshaledInterface::Unmarshal<ISyncedStreamReaderInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncedStreamReaderInfo>>)
0x18007b1a0  mov     ebx, eax
0x18007b1a2  test    eax, eax
0x18007b1a4  js      short loc_18007B1CE
0x18007b1a6  mov     r9d, [rsp+78h+dwDestContext]; dwDestContext
0x18007b1ae  lea     rdx, _GUID_d18e07e4_d7b4_49ee_a04d_55955a063644; riid
0x18007b1b5  mov     r8, [rsp+78h+pUnk]; pUnk
0x18007b1ba  mov     rcx, rdi; pStm
0x18007b1bd  mov     [rsp+78h+mshlflags], ebp; mshlflags
0x18007b1c1  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x18007b1c6  call    cs:__imp_CoMarshalInterface
0x18007b1cc  mov     ebx, eax
0x18007b1ce  lea     rcx, [rsp+78h+pUnk]
0x18007b1d3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007b1d8  test    ebx, ebx
0x18007b1da  js      short loc_18007B1FC
0x18007b1dc  mov     r8d, [rsp+78h+dwDestContext]; unsigned int
0x18007b1e4  mov     r9, r14; void *
0x18007b1e7  mov     rcx, [rsi+0C8h]; struct CRasFilePlaceholderParams *
0x18007b1ee  mov     rdx, rdi; struct IStream *
0x18007b1f1  mov     dword ptr [rsp+78h+pvDestContext], ebp; unsigned int
0x18007b1f5  call    ?MarshalAdditionalData@CRasFilePlaceholderParams@@SAJPEAV1@PEAUIStream@@KPEAXK@Z; CRasFilePlaceholderParams::MarshalAdditionalData(CRasFilePlaceholderParams *,IStream *,ulong,void *,ulong)
0x18007b1fa  mov     ebx, eax
0x18007b1fc  mov     eax, ebx
0x18007b1fe  add     rsp, 48h
0x18007b202  pop     r14
0x18007b204  pop     r12
0x18007b206  pop     rdi
0x18007b207  pop     rsi
0x18007b208  pop     rbp
0x18007b209  pop     rbx
0x18007b20a  retn
```
