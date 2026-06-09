# CWmpEncoderFrame::~CWmpEncoderFrame(void)

- ea: `0x18002e298`
- end: `0x18002e448`
- name: `??1CWmpEncoderFrame@@UEAA@XZ`
- size: `432`
- prototype: `void __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002e240`

## callees

- `0x18002e298`
- `0x18002e450`
- `0x18002e49c`
- `0x18002e4d0`
- `0x1800320a0`
- `0x180034390`
- `0x180044010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18002e3e4`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18002e3e4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e41d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e41d`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18002e412`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18002e412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e3fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e3fa`

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
0x18002e298  push    rbx
0x18002e29a  sub     rsp, 20h
0x18002e29e  mov     rbx, rcx
0x18002e2a1  lea     rax, ??_7CWmpEncoderFrame@@6BCWmpCodecFrameBase@@@; const CWmpEncoderFrame::`vftable'{for `CWmpCodecFrameBase'}
0x18002e2a8  mov     [rcx], rax
0x18002e2ab  lea     rax, ??_7CWmpEncoderFrame@@6BCMTALock@@@; const CWmpEncoderFrame::`vftable'{for `CMTALock'}
0x18002e2b2  mov     [rcx+10310h], rax
0x18002e2b9  lea     rax, ??_7CWmpEncoderFrame@@6BIWICBitmapFrameEncode@@@; const CWmpEncoderFrame::`vftable'{for `IWICBitmapFrameEncode'}
0x18002e2c0  mov     [rcx+10348h], rax
0x18002e2c7  lea     rax, ??_7CWmpEncoderFrame@@6BIWICMetadataBlockWriter@@@; const CWmpEncoderFrame::`vftable'{for `IWICMetadataBlockWriter'}
0x18002e2ce  mov     [rcx+10350h], rax
0x18002e2d5  mov     rcx, [rcx+10420h]
0x18002e2dc  test    rcx, rcx
0x18002e2df  jnz     loc_18002E3C8
0x18002e2e5  mov     rcx, [rbx+10300h]; Block
0x18002e2ec  test    rcx, rcx
0x18002e2ef  jnz     loc_18002E3E4
0x18002e2f5  mov     rcx, [rbx+10408h]; hObject
0x18002e2fc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002e300  jnz     loc_18002E3FA
0x18002e306  mov     rcx, [rbx+10410h]; Block
0x18002e30d  test    rcx, rcx
0x18002e310  jnz     loc_18002E41D
0x18002e316  mov     rcx, [rbx+103E8h]
0x18002e31d  test    rcx, rcx
0x18002e320  jnz     loc_18002E3AC
0x18002e326  mov     rcx, rbx; this
0x18002e329  call    ?ClearColorContext@CWmpEncoderFrame@@UEAAJXZ; CWmpEncoderFrame::ClearColorContext(void)
0x18002e32e  mov     rcx, [rbx+103E0h]; this
0x18002e335  test    rcx, rcx
0x18002e338  jnz     loc_18002E433
0x18002e33e  lock dec cs:?g_refcntWMPCodec@@3JA; long g_refcntWMPCodec
0x18002e345  mov     rcx, [rbx+103F0h]
0x18002e34c  test    rcx, rcx
0x18002e34f  jz      short loc_18002E385
0x18002e351  mov     rdx, [rbx+10400h]
0x18002e358  sub     rdx, rcx
0x18002e35b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002e35f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e364  mov     qword ptr [rbx+103F0h], 0
0x18002e36f  mov     qword ptr [rbx+103F8h], 0
0x18002e37a  mov     qword ptr [rbx+10400h], 0
0x18002e385  lea     rax, ??_7CMTALock@@6B@; const CMTALock::`vftable'
0x18002e38c  mov     [rbx+10310h], rax
0x18002e393  lea     rcx, [rbx+10318h]; this
0x18002e39a  call    ?DeInit@CCriticalSection@@QEAAXXZ; CCriticalSection::DeInit(void)
0x18002e39f  mov     rcx, rbx; this
0x18002e3a2  add     rsp, 20h
0x18002e3a6  pop     rbx
0x18002e3a7  jmp     ??1CWmpCodecFrameBase@@UEAA@XZ; CWmpCodecFrameBase::~CWmpCodecFrameBase(void)
0x18002e3ac  mov     rax, [rcx]
0x18002e3af  mov     rax, [rax+10h]
0x18002e3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3b8  mov     qword ptr [rbx+103E8h], 0
0x18002e3c3  jmp     loc_18002E326
0x18002e3c8  mov     rax, [rcx]
0x18002e3cb  mov     rax, [rax+10h]
0x18002e3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3d4  mov     qword ptr [rbx+10420h], 0
0x18002e3df  jmp     loc_18002E2E5
0x18002e3e4  call    cs:__imp__aligned_free
0x18002e3ea  mov     qword ptr [rbx+10300h], 0
0x18002e3f5  jmp     loc_18002E2F5
0x18002e3fa  call    cs:__imp_CloseHandle
0x18002e400  mov     qword ptr [rbx+10408h], 0FFFFFFFFFFFFFFFFh
0x18002e40b  mov     rcx, [rbx+10410h]; lpFileName
0x18002e412  call    cs:__imp_DeleteFileA
0x18002e418  jmp     loc_18002E306
0x18002e41d  call    cs:__imp_free
0x18002e423  mov     qword ptr [rbx+10410h], 0
0x18002e42e  jmp     loc_18002E316
0x18002e433  call    ?InternalRelease@CWmpCOMBase@@UEAAKXZ; CWmpCOMBase::InternalRelease(void)
0x18002e438  mov     qword ptr [rbx+103E0h], 0
0x18002e443  jmp     loc_18002E33E
```
