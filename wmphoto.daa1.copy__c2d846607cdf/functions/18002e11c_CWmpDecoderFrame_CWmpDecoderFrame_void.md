# CWmpDecoderFrame::~CWmpDecoderFrame(void)

- ea: `0x18002e11c`
- end: `0x18002e231`
- name: `??1CWmpDecoderFrame@@UEAA@XZ`
- size: `277`
- prototype: `void __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002dfdc`
- `0x18002e0e0`

## callees

- `0x18002e11c`
- `0x18002e450`
- `0x180036264`
- `0x1800387f0`
- `0x180039560`
- `0x180044010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18002e1cb`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18002e1cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e20b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e20b`

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
0x18002e11c  push    rbx
0x18002e11e  sub     rsp, 20h
0x18002e122  mov     rbx, rcx
0x18002e125  lea     rax, ??_7CWmpDecoderFrame@@6BCWmpCodecFrameBase@@@; const CWmpDecoderFrame::`vftable'{for `CWmpCodecFrameBase'}
0x18002e12c  mov     [rcx], rax
0x18002e12f  lea     rax, ??_7CWmpDecoderFrame@@6BIWICBitmapFrameDecode@@@; const CWmpDecoderFrame::`vftable'{for `IWICBitmapFrameDecode'}
0x18002e136  mov     [rcx+10310h], rax
0x18002e13d  lea     rax, ??_7CWmpDecoderFrame@@6BIWICBitmapSourceTransform2@@@; const CWmpDecoderFrame::`vftable'{for `IWICBitmapSourceTransform2'}
0x18002e144  mov     [rcx+10318h], rax
0x18002e14b  lea     rax, ??_7CWmpDecoderFrame@@6BIWICMetadataBlockReader@@@; const CWmpDecoderFrame::`vftable'{for `IWICMetadataBlockReader'}
0x18002e152  mov     [rcx+10320h], rax
0x18002e159  lea     rax, ??_7CWmpDecoderFrame@@6BIWICProgressiveLevelControl@@@; const CWmpDecoderFrame::`vftable'{for `IWICProgressiveLevelControl'}
0x18002e160  mov     [rcx+10328h], rax
0x18002e167  lea     rax, ??_7CWmpDecoderFrame@@6BIWICDisplayAdaptationControl@@@; const CWmpDecoderFrame::`vftable'{for `IWICDisplayAdaptationControl'}
0x18002e16e  mov     [rcx+10330h], rax
0x18002e175  lea     rax, ??_7CWmpDecoderFrame@@6BIWICStreamProvider@@@; const CWmpDecoderFrame::`vftable'{for `IWICStreamProvider'}
0x18002e17c  mov     [rcx+10338h], rax
0x18002e183  lea     rax, ??_7CWmpDecoderFrame@@6BIWMPhotoElementaryStream@@@; const CWmpDecoderFrame::`vftable'{for `IWMPhotoElementaryStream'}
0x18002e18a  mov     [rcx+10340h], rax
0x18002e191  mov     rcx, [rcx+104B0h]; void *
0x18002e198  test    rcx, rcx
0x18002e19b  jz      short loc_18002E1B7
0x18002e19d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e1a2  mov     qword ptr [rbx+104B0h], 0
0x18002e1ad  mov     dword ptr [rbx+104A8h], 0
0x18002e1b7  mov     rcx, rbx; this
0x18002e1ba  call    ?HrClearCache@CWmpDecoderFrame@@MEAAJXZ; CWmpDecoderFrame::HrClearCache(void)
0x18002e1bf  mov     rcx, [rbx+10300h]; Block
0x18002e1c6  test    rcx, rcx
0x18002e1c9  jz      short loc_18002E1DC
0x18002e1cb  call    cs:__imp__aligned_free
0x18002e1d1  mov     qword ptr [rbx+10300h], 0
0x18002e1dc  mov     rcx, [rbx+10388h]
0x18002e1e3  test    rcx, rcx
0x18002e1e6  jz      short loc_18002E1FF
0x18002e1e8  mov     rax, [rcx]
0x18002e1eb  mov     rax, [rax+10h]
0x18002e1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1f4  mov     qword ptr [rbx+10388h], 0
0x18002e1ff  mov     rcx, [rbx+10390h]; pv
0x18002e206  test    rcx, rcx
0x18002e209  jz      short loc_18002E211
0x18002e20b  call    cs:__imp_CoTaskMemFree
0x18002e211  lock dec cs:?g_refcntWMPCodec@@3JA; long g_refcntWMPCodec
0x18002e218  lea     rcx, [rbx+10430h]; this
0x18002e21f  call    ??1HDRConverter@@QEAA@XZ; HDRConverter::~HDRConverter(void)
0x18002e224  mov     rcx, rbx; this
0x18002e227  add     rsp, 20h
0x18002e22b  pop     rbx
0x18002e22c  jmp     ??1CWmpCodecFrameBase@@UEAA@XZ; CWmpCodecFrameBase::~CWmpCodecFrameBase(void)
```
