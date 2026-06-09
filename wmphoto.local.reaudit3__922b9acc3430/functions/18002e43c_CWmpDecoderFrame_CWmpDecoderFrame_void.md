# CWmpDecoderFrame::~CWmpDecoderFrame(void)

- ea: `0x18002e43c`
- end: `0x18002e55d`
- name: `??1CWmpDecoderFrame@@UEAA@XZ`
- size: `289`
- prototype: `void __fastcall(CWmpDecoderFrame *this, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002e2fc`
- `0x18002e400`

## callees

- `0x18002e43c`
- `0x18002e798`
- `0x180036834`
- `0x180038e50`
- `0x180039c70`
- `0x180045010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18002e4eb`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18002e4eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e531`

## pseudocode

```c
void __fastcall CWmpDecoderFrame::~CWmpDecoderFrame(CWmpDecoderFrame *this, unsigned __int64 a2)
{
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &CWmpDecoderFrame::`vftable'{for `CWmpCodecFrameBase'};
  *((_QWORD *)this + 8290) = &CWmpDecoderFrame::`vftable'{for `IWICBitmapFrameDecode'};
  *((_QWORD *)this + 8291) = &CWmpDecoderFrame::`vftable'{for `IWICBitmapSourceTransform2'};
  *((_QWORD *)this + 8292) = &CWmpDecoderFrame::`vftable'{for `IWICMetadataBlockReader'};
  *((_QWORD *)this + 8293) = &CWmpDecoderFrame::`vftable'{for `IWICProgressiveLevelControl'};
  *((_QWORD *)this + 8294) = &CWmpDecoderFrame::`vftable'{for `IWICDisplayAdaptationControl'};
  *((_QWORD *)this + 8295) = &CWmpDecoderFrame::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 8296) = &CWmpDecoderFrame::`vftable'{for `IWMPhotoElementaryStream'};
  v3 = (void *)*((_QWORD *)this + 8342);
  if ( v3 )
  {
    operator delete(v3, a2);
    *((_QWORD *)this + 8342) = 0;
    *((_DWORD *)this + 16682) = 0;
  }
  CWmpDecoderFrame::HrClearCache(this);
  v4 = (void *)*((_QWORD *)this + 8288);
  if ( v4 )
  {
    _aligned_free(v4);
    *((_QWORD *)this + 8288) = 0;
  }
  v5 = *((_QWORD *)this + 8305);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 8305) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 8306);
  if ( v6 )
    CoTaskMemFree(v6);
  _InterlockedDecrement(&g_refcntWMPCodec);
  HDRConverter::~HDRConverter((CWmpDecoderFrame *)((char *)this + 66608));
  CWmpCodecFrameBase::~CWmpCodecFrameBase(this);
}

```

## disassembly

```asm
0x18002e43c  push    rbx
0x18002e43e  sub     rsp, 20h
0x18002e442  mov     rbx, rcx
0x18002e445  lea     rax, ??_7CWmpDecoderFrame@@6BCWmpCodecFrameBase@@@; const CWmpDecoderFrame::`vftable'{for `CWmpCodecFrameBase'}
0x18002e44c  mov     [rcx], rax
0x18002e44f  lea     rax, ??_7CWmpDecoderFrame@@6BIWICBitmapFrameDecode@@@; const CWmpDecoderFrame::`vftable'{for `IWICBitmapFrameDecode'}
0x18002e456  mov     [rcx+10310h], rax
0x18002e45d  lea     rax, ??_7CWmpDecoderFrame@@6BIWICBitmapSourceTransform2@@@; const CWmpDecoderFrame::`vftable'{for `IWICBitmapSourceTransform2'}
0x18002e464  mov     [rcx+10318h], rax
0x18002e46b  lea     rax, ??_7CWmpDecoderFrame@@6BIWICMetadataBlockReader@@@; const CWmpDecoderFrame::`vftable'{for `IWICMetadataBlockReader'}
0x18002e472  mov     [rcx+10320h], rax
0x18002e479  lea     rax, ??_7CWmpDecoderFrame@@6BIWICProgressiveLevelControl@@@; const CWmpDecoderFrame::`vftable'{for `IWICProgressiveLevelControl'}
0x18002e480  mov     [rcx+10328h], rax
0x18002e487  lea     rax, ??_7CWmpDecoderFrame@@6BIWICDisplayAdaptationControl@@@; const CWmpDecoderFrame::`vftable'{for `IWICDisplayAdaptationControl'}
0x18002e48e  mov     [rcx+10330h], rax
0x18002e495  lea     rax, ??_7CWmpDecoderFrame@@6BIWICStreamProvider@@@; const CWmpDecoderFrame::`vftable'{for `IWICStreamProvider'}
0x18002e49c  mov     [rcx+10338h], rax
0x18002e4a3  lea     rax, ??_7CWmpDecoderFrame@@6BIWMPhotoElementaryStream@@@; const CWmpDecoderFrame::`vftable'{for `IWMPhotoElementaryStream'}
0x18002e4aa  mov     [rcx+10340h], rax
0x18002e4b1  mov     rcx, [rcx+104B0h]; void *
0x18002e4b8  test    rcx, rcx
0x18002e4bb  jz      short loc_18002E4D7
0x18002e4bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e4c2  mov     qword ptr [rbx+104B0h], 0
0x18002e4cd  mov     dword ptr [rbx+104A8h], 0
0x18002e4d7  mov     rcx, rbx; this
0x18002e4da  call    ?HrClearCache@CWmpDecoderFrame@@MEAAJXZ; CWmpDecoderFrame::HrClearCache(void)
0x18002e4df  mov     rcx, [rbx+10300h]; Block
0x18002e4e6  test    rcx, rcx
0x18002e4e9  jz      short loc_18002E502
0x18002e4eb  call    cs:__imp__aligned_free
0x18002e4f2  nop     dword ptr [rax+rax+00h]
0x18002e4f7  mov     qword ptr [rbx+10300h], 0
0x18002e502  mov     rcx, [rbx+10388h]
0x18002e509  test    rcx, rcx
0x18002e50c  jz      short loc_18002E525
0x18002e50e  mov     rax, [rcx]
0x18002e511  mov     rax, [rax+10h]
0x18002e515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e51a  mov     qword ptr [rbx+10388h], 0
0x18002e525  mov     rcx, [rbx+10390h]; pv
0x18002e52c  test    rcx, rcx
0x18002e52f  jz      short loc_18002E53D
0x18002e531  call    cs:__imp_CoTaskMemFree
0x18002e538  nop     dword ptr [rax+rax+00h]
0x18002e53d  lock dec cs:?g_refcntWMPCodec@@3JA; long g_refcntWMPCodec
0x18002e544  lea     rcx, [rbx+10430h]; this
0x18002e54b  call    ??1HDRConverter@@QEAA@XZ; HDRConverter::~HDRConverter(void)
0x18002e550  mov     rcx, rbx; this
0x18002e553  add     rsp, 20h
0x18002e557  pop     rbx
0x18002e558  jmp     ??1CWmpCodecFrameBase@@UEAA@XZ; CWmpCodecFrameBase::~CWmpCodecFrameBase(void)
```
