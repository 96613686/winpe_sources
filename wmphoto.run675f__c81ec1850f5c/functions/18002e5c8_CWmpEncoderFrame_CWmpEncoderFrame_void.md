# CWmpEncoderFrame::~CWmpEncoderFrame(void)

- ea: `0x18002e5c8`
- end: `0x18002e790`
- name: `??1CWmpEncoderFrame@@UEAA@XZ`
- size: `456`
- prototype: `void __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002e570`

## callees

- `0x18002e5c8`
- `0x18002e798`
- `0x18002e7e8`
- `0x18002e820`
- `0x1800323c0`
- `0x180034940`
- `0x180045010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18002e714`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18002e714`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e75f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e75f`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18002e74e`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18002e74e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e730`

## pseudocode

```c
void __fastcall CWmpEncoderFrame::~CWmpEncoderFrame(CWmpEncoderFrame *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  CWmpCOMBase *v7; // rcx
  __int64 v8; // rcx

  *(_QWORD *)this = &CWmpEncoderFrame::`vftable'{for `CWmpCodecFrameBase'};
  *((_QWORD *)this + 8290) = &CWmpEncoderFrame::`vftable'{for `CMTALock'};
  *((_QWORD *)this + 8297) = &CWmpEncoderFrame::`vftable'{for `IWICBitmapFrameEncode'};
  *((_QWORD *)this + 8298) = &CWmpEncoderFrame::`vftable'{for `IWICMetadataBlockWriter'};
  v2 = *((_QWORD *)this + 8324);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 8324) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 8288);
  if ( v3 )
  {
    _aligned_free(v3);
    *((_QWORD *)this + 8288) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 8321);
  if ( v4 != (void *)-1LL )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 8321) = -1;
    DeleteFileA(*((LPCSTR *)this + 8322));
  }
  v5 = (void *)*((_QWORD *)this + 8322);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 8322) = 0;
  }
  v6 = *((_QWORD *)this + 8317);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 8317) = 0;
  }
  CWmpEncoderFrame::ClearColorContext(this);
  v7 = (CWmpCOMBase *)*((_QWORD *)this + 8316);
  if ( v7 )
  {
    CWmpCOMBase::InternalRelease(v7);
    *((_QWORD *)this + 8316) = 0;
  }
  _InterlockedDecrement(&g_refcntWMPCodec);
  v8 = *((_QWORD *)this + 8318);
  if ( v8 )
  {
    std::_Deallocate<16>(v8, (*((_QWORD *)this + 8320) - v8) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 8318) = 0;
    *((_QWORD *)this + 8319) = 0;
    *((_QWORD *)this + 8320) = 0;
  }
  *((_QWORD *)this + 8290) = &CMTALock::`vftable';
  CCriticalSection::DeInit((CWmpEncoderFrame *)((char *)this + 66328));
  CWmpCodecFrameBase::~CWmpCodecFrameBase(this);
}

```

## disassembly

```asm
0x18002e5c8  push    rbx
0x18002e5ca  sub     rsp, 20h
0x18002e5ce  mov     rbx, rcx
0x18002e5d1  lea     rax, ??_7CWmpEncoderFrame@@6BCWmpCodecFrameBase@@@; const CWmpEncoderFrame::`vftable'{for `CWmpCodecFrameBase'}
0x18002e5d8  mov     [rcx], rax
0x18002e5db  lea     rax, ??_7CWmpEncoderFrame@@6BCMTALock@@@; const CWmpEncoderFrame::`vftable'{for `CMTALock'}
0x18002e5e2  mov     [rcx+10310h], rax
0x18002e5e9  lea     rax, ??_7CWmpEncoderFrame@@6BIWICBitmapFrameEncode@@@; const CWmpEncoderFrame::`vftable'{for `IWICBitmapFrameEncode'}
0x18002e5f0  mov     [rcx+10348h], rax
0x18002e5f7  lea     rax, ??_7CWmpEncoderFrame@@6BIWICMetadataBlockWriter@@@; const CWmpEncoderFrame::`vftable'{for `IWICMetadataBlockWriter'}
0x18002e5fe  mov     [rcx+10350h], rax
0x18002e605  mov     rcx, [rcx+10420h]
0x18002e60c  test    rcx, rcx
0x18002e60f  jnz     loc_18002E6F8
0x18002e615  mov     rcx, [rbx+10300h]; Block
0x18002e61c  test    rcx, rcx
0x18002e61f  jnz     loc_18002E714
0x18002e625  mov     rcx, [rbx+10408h]; hObject
0x18002e62c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002e630  jnz     loc_18002E730
0x18002e636  mov     rcx, [rbx+10410h]; Block
0x18002e63d  test    rcx, rcx
0x18002e640  jnz     loc_18002E75F
0x18002e646  mov     rcx, [rbx+103E8h]
0x18002e64d  test    rcx, rcx
0x18002e650  jnz     loc_18002E6DC
0x18002e656  mov     rcx, rbx; this
0x18002e659  call    ?ClearColorContext@CWmpEncoderFrame@@UEAAJXZ; CWmpEncoderFrame::ClearColorContext(void)
0x18002e65e  mov     rcx, [rbx+103E0h]; this
0x18002e665  test    rcx, rcx
0x18002e668  jnz     loc_18002E77B
0x18002e66e  lock dec cs:?g_refcntWMPCodec@@3JA; long g_refcntWMPCodec
0x18002e675  mov     rcx, [rbx+103F0h]
0x18002e67c  test    rcx, rcx
0x18002e67f  jz      short loc_18002E6B5
0x18002e681  mov     rdx, [rbx+10400h]
0x18002e688  sub     rdx, rcx
0x18002e68b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e68f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e694  mov     qword ptr [rbx+103F0h], 0
0x18002e69f  mov     qword ptr [rbx+103F8h], 0
0x18002e6aa  mov     qword ptr [rbx+10400h], 0
0x18002e6b5  lea     rax, ??_7CMTALock@@6B@; const CMTALock::`vftable'
0x18002e6bc  mov     [rbx+10310h], rax
0x18002e6c3  lea     rcx, [rbx+10318h]; this
0x18002e6ca  call    ?DeInit@CCriticalSection@@QEAAXXZ; CCriticalSection::DeInit(void)
0x18002e6cf  mov     rcx, rbx; this
0x18002e6d2  add     rsp, 20h
0x18002e6d6  pop     rbx
0x18002e6d7  jmp     ??1CWmpCodecFrameBase@@UEAA@XZ; CWmpCodecFrameBase::~CWmpCodecFrameBase(void)
0x18002e6dc  mov     rax, [rcx]
0x18002e6df  mov     rax, [rax+10h]
0x18002e6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6e8  mov     qword ptr [rbx+103E8h], 0
0x18002e6f3  jmp     loc_18002E656
0x18002e6f8  mov     rax, [rcx]
0x18002e6fb  mov     rax, [rax+10h]
0x18002e6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e704  mov     qword ptr [rbx+10420h], 0
0x18002e70f  jmp     loc_18002E615
0x18002e714  call    cs:__imp__aligned_free
0x18002e71b  nop     dword ptr [rax+rax+00h]
0x18002e720  mov     qword ptr [rbx+10300h], 0
0x18002e72b  jmp     loc_18002E625
0x18002e730  call    cs:__imp_CloseHandle
0x18002e737  nop     dword ptr [rax+rax+00h]
0x18002e73c  mov     qword ptr [rbx+10408h], 0FFFFFFFFFFFFFFFFh
0x18002e747  mov     rcx, [rbx+10410h]; lpFileName
0x18002e74e  call    cs:__imp_DeleteFileA
0x18002e755  nop     dword ptr [rax+rax+00h]
0x18002e75a  jmp     loc_18002E636
0x18002e75f  call    cs:__imp_free
0x18002e766  nop     dword ptr [rax+rax+00h]
0x18002e76b  mov     qword ptr [rbx+10410h], 0
0x18002e776  jmp     loc_18002E646
0x18002e77b  call    ?InternalRelease@CWmpCOMBase@@UEAAKXZ; CWmpCOMBase::InternalRelease(void)
0x18002e780  mov     qword ptr [rbx+103E0h], 0
0x18002e78b  jmp     loc_18002E66E
```
