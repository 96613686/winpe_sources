# CThumbnailCacheDataFile::StoreThumbnail(IBitmapResult *,int,int,CThumbnailMoniker const &,WTS_ALPHATYPE)

- ea: `0x18001048c`
- end: `0x180010888`
- name: `?StoreThumbnail@CThumbnailCacheDataFile@@QEAAJPEAUIBitmapResult@@HHAEBVCThumbnailMoniker@@W4WTS_ALPHATYPE@@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(CThumbnailCacheDataFile *this, struct IBitmapResult *, int, int, const struct CThumbnailMoniker *, enum WTS_ALPHATYPE)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001161c`

## callees

- `0x180003624`
- `0x18000b3c0`
- `0x18000d498`
- `0x18000f878`
- `0x18000fcd0`
- `0x18001048c`
- `0x180010890`
- `0x180010aec`
- `0x180010b34`
- `0x180010ba0`
- `0x180012448`
- `0x180020bd8`
- `0x18002a88c`
- `0x18002dc80`
- `0x180035830`
- `0x180045784`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001085e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001085e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800106c1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800106c1`
- `GDI32!GetObjectW` at `0x180010586`
- `GDI32!GetObjectW` at `0x180010586`

## string_xrefs

- `0x180010857`: `Thumbnail Cache: Attempting to replace an entry that is in use\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CThumbnailCacheDataFile::StoreThumbnail(
        CThumbnailCacheDataFile *this,
        struct IBitmapResult *a2,
        int a3,
        int a4,
        const struct CThumbnailMoniker *a5,
        enum WTS_ALPHATYPE a6)
{
  int Error; // ebx
  __int64 (__fastcall *v9)(struct IBitmapResult *, __int64, GUID *, int *); // rbx
  unsigned int v10; // edx
  __int64 v11; // rcx
  struct IStream *v12; // r12
  int v13; // r14d
  unsigned int v14; // esi
  int v15; // eax
  HRESULT v17; // eax
  unsigned int v18; // r15d
  int v19; // eax
  struct CThumbnailMoniker *v20; // r15
  unsigned int v21; // eax
  __int64 ContentTypeFromStreamType; // rax
  unsigned int v23; // [rsp+40h] [rbp-59h] BYREF
  int v24; // [rsp+44h] [rbp-55h] BYREF
  int v25; // [rsp+48h] [rbp-51h]
  int v26; // [rsp+4Ch] [rbp-4Dh]
  struct CThumbnailMoniker *v27; // [rsp+50h] [rbp-49h]
  HANDLE h; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v29; // [rsp+60h] [rbp-39h] BYREF
  int v30[2]; // [rsp+68h] [rbp-31h] BYREF
  void *v31; // [rsp+70h] [rbp-29h] BYREF
  LPSTREAM ppstm; // [rsp+78h] [rbp-21h] BYREF
  _OWORD pv[2]; // [rsp+80h] [rbp-19h] BYREF

  v26 = a4;
  v25 = a3;
  v27 = a5;
  ppstm = 0;
  v31 = 0;
  if ( !a2 )
  {
    v17 = CreateStreamOnHGlobal(0, 1, &ppstm);
LABEL_23:
    Error = v17;
    goto LABEL_11;
  }
  v29 = 0;
  Error = (*(__int64 (__fastcall **)(struct IBitmapResult *, unsigned int *))(*(_QWORD *)a2 + 64LL))(a2, &v29);
  if ( Error < 0 )
    goto LABEL_19;
  if ( v29 != 2 )
  {
    v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 119) + 48LL))(*((_QWORD *)this + 119));
    if ( v21 == 1 && a6 == WTSAT_ARGB )
      v21 = 3;
    ContentTypeFromStreamType = GetContentTypeFromStreamType(v21);
    Error = (*(__int64 (__fastcall **)(struct IBitmapResult *, __int64, GUID *, LPSTREAM *))(*(_QWORD *)a2 + 56LL))(
              a2,
              ContentTypeFromStreamType,
              &GUID_0000000c_0000_0000_c000_000000000046,
              &ppstm);
    if ( Error < 0 )
      goto LABEL_19;
    v17 = (*(__int64 (__fastcall **)(struct IBitmapResult *, void **))(*(_QWORD *)a2 + 72LL))(a2, &v31);
    goto LABEL_23;
  }
  *(_QWORD *)v30 = 0;
  v9 = *(__int64 (__fastcall **)(struct IBitmapResult *, __int64, GUID *, int *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v30);
  Error = v9(a2, 2, &GUID_091162a4_bc96_411f_aae8_c5122cd03363, v30);
  if ( Error >= 0 )
  {
    h = 0;
    Error = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**(_QWORD **)v30 + 24LL))(*(_QWORD *)v30, &h);
    if ( Error >= 0 )
    {
      memset(pv, 0, sizeof(pv));
      if ( GetObjectW(h, 32, pv) )
      {
        LODWORD(v31) = WORD2(pv[0]);
        HIDWORD(v31) = WORD4(pv[0]);
LABEL_8:
        Error = (*(__int64 (__fastcall **)(_QWORD, HANDLE, LPSTREAM *, _QWORD))(**((_QWORD **)this + 119) + 32LL))(
                  *((_QWORD *)this + 119),
                  h,
                  &ppstm,
                  (unsigned int)a6);
        goto LABEL_9;
      }
      v31 = 0;
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_8;
    }
  }
LABEL_9:
  v11 = *(_QWORD *)v30;
  if ( *(_QWORD *)v30 )
  {
    *(_QWORD *)v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
LABEL_11:
  if ( Error >= 0 )
  {
    v12 = ppstm;
    h = v31;
    Error = CNamedMutex::Acquire((CThumbnailCacheDataFile *)((char *)this + 8), v10);
    if ( Error >= 0 )
    {
      Error = CThumbnailCacheDataFile::_CheckForCacheReset(this);
      if ( Error < 0 )
        goto LABEL_18;
      Error = CThumbnailCacheDataFile::_RemapOrGrowMapping(this, 0);
      if ( Error < 0 )
        goto LABEL_18;
      v13 = 0;
      v30[0] = 0;
      v14 = 0;
      v29 = 0;
      v24 = 0;
      v23 = 0;
      v15 = CThumbnailCacheIndex::Delete(*((_QWORD *)this + 4), *(_QWORD *)a5, *((unsigned int *)this + 106), 2, &v23);
      Error = v15;
      if ( v15 >= 0 )
      {
        v18 = v23;
        v19 = CThumbnailCacheIndex::CheckThumbnailNotInUse(*((_QWORD *)this + 4), v23, *((unsigned int *)this + 106));
        Error = v19;
        if ( v19 < 0 )
        {
          if ( v19 == -2147024864 )
          {
            OutputDebugStringW(L"Thumbnail Cache: Attempting to replace an entry that is in use\n");
            Error = 0;
          }
        }
        else
        {
          Error = CThumbnailCacheDataFile::_ReplaceThumbnailAtOffset(
                    this,
                    v18,
                    v12,
                    v27,
                    (const struct tagSIZE *)&h,
                    &v24);
          if ( Error >= 0 )
          {
            v14 = v18;
            v29 = v18;
            goto LABEL_27;
          }
        }
      }
      else if ( v15 == -2147287038 )
      {
        goto LABEL_27;
      }
      if ( Error < 0 )
      {
LABEL_18:
        CNamedMutex::Release((CThumbnailCacheDataFile *)((char *)this + 8));
        goto LABEL_19;
      }
LABEL_27:
      v20 = v27;
      if ( !v24 )
      {
        Error = CThumbnailCacheDataFile::_TryAppendThumbnail(this, v12, v27, v25, (const struct tagSIZE *)&h, &v29, v30);
        if ( Error < 0 )
          goto LABEL_18;
        v13 = v30[0];
        if ( !v30[0] )
        {
          Error = CThumbnailCacheDataFile::_ReclaimThumbnail(this, v12, v20, (const struct tagSIZE *)&h, &v29);
          if ( Error < 0 )
            goto LABEL_18;
        }
        v14 = v29;
      }
      if ( !v13
        || (Error = CThumbnailCacheIndex::IncrementThumbnailCount(*((_QWORD *)this + 4), *((unsigned int *)this + 106)),
            Error >= 0) )
      {
        Error = CThumbnailCacheIndex::Insert(*((_QWORD *)this + 4), v20, *((unsigned int *)this + 106), h, v14, v26);
      }
      goto LABEL_18;
    }
  }
LABEL_19:
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001048c  mov     [rsp-8+arg_10], rbx
0x180010491  push    rbp
0x180010492  push    rsi
0x180010493  push    rdi
0x180010494  push    r12
0x180010496  push    r13
0x180010498  push    r14
0x18001049a  push    r15
0x18001049c  lea     rbp, [rsp-17h]
0x1800104a1  sub     rsp, 0B0h
0x1800104a8  mov     rax, cs:__security_cookie
0x1800104af  xor     rax, rsp
0x1800104b2  mov     [rbp+47h+var_40], rax
0x1800104b6  mov     [rbp+47h+var_94], r9d
0x1800104ba  mov     [rbp+47h+var_98], r8d
0x1800104be  mov     rsi, rdx
0x1800104c1  mov     rdi, rcx
0x1800104c4  mov     r15, [rbp+47h+arg_20]
0x1800104c8  mov     [rbp+47h+var_90], r15
0x1800104cc  mov     [rbp+47h+ppstm], 0
0x1800104d4  mov     [rbp+47h+var_70], 0
0x1800104dc  test    rdx, rdx
0x1800104df  jz      loc_1800106B6
0x1800104e5  mov     [rbp+47h+var_80], 0
0x1800104ec  mov     rax, [rdx]
0x1800104ef  lea     rdx, [rbp+47h+var_80]
0x1800104f3  mov     rcx, rsi
0x1800104f6  mov     rax, [rax+40h]
0x1800104fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104ff  mov     ebx, eax
0x180010501  test    eax, eax
0x180010503  js      loc_180010677
0x180010509  cmp     [rbp+47h+var_80], 2
0x18001050d  jnz     loc_1800107DD
0x180010513  mov     qword ptr [rbp+47h+var_78], 0
0x18001051b  mov     rax, [rsi]
0x18001051e  mov     rbx, [rax+30h]
0x180010522  lea     rcx, [rbp+47h+var_78]
0x180010526  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001052b  lea     r9, [rbp+47h+var_78]
0x18001052f  lea     r8, _GUID_091162a4_bc96_411f_aae8_c5122cd03363
0x180010536  mov     edx, 2
0x18001053b  mov     rcx, rsi
0x18001053e  mov     rax, rbx
0x180010541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010546  mov     ebx, eax
0x180010548  test    eax, eax
0x18001054a  js      short loc_1800105C3
0x18001054c  mov     [rbp+47h+h], 0
0x180010554  mov     rcx, qword ptr [rbp+47h+var_78]
0x180010558  mov     rax, [rcx]
0x18001055b  lea     rdx, [rbp+47h+h]
0x18001055f  mov     rax, [rax+18h]
0x180010563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010568  mov     ebx, eax
0x18001056a  test    eax, eax
0x18001056c  js      short loc_1800105C3
0x18001056e  xorps   xmm0, xmm0
0x180010571  movups  [rbp+47h+pv], xmm0
0x180010575  movups  [rbp+47h+var_50], xmm0
0x180010579  lea     r8, [rbp+47h+pv]; pv
0x18001057d  mov     edx, 20h ; ' '; c
0x180010582  mov     rcx, [rbp+47h+h]; h
0x180010586  call    cs:__imp_GetObjectW
0x18001058c  test    eax, eax
0x18001058e  jz      loc_18001086B
0x180010594  movzx   eax, word ptr [rbp+47h+pv+4]
0x180010598  mov     dword ptr [rbp+47h+var_70], eax
0x18001059b  movzx   eax, word ptr [rbp+47h+pv+8]
0x18001059f  mov     dword ptr [rbp+47h+var_70+4], eax
0x1800105a2  mov     rcx, [rdi+3B8h]
0x1800105a9  mov     rax, [rcx]
0x1800105ac  mov     r9d, [rbp+47h+arg_28]
0x1800105b0  lea     r8, [rbp+47h+ppstm]
0x1800105b4  mov     rdx, [rbp+47h+h]
0x1800105b8  mov     rax, [rax+20h]
0x1800105bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105c1  mov     ebx, eax
0x1800105c3  mov     rcx, qword ptr [rbp+47h+var_78]
0x1800105c7  test    rcx, rcx
0x1800105ca  jz      short loc_1800105E1
0x1800105cc  mov     qword ptr [rbp+47h+var_78], 0
0x1800105d4  mov     rax, [rcx]
0x1800105d7  mov     rax, [rax+10h]
0x1800105db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105e0  nop
0x1800105e1  test    ebx, ebx
0x1800105e3  js      loc_180010677
0x1800105e9  mov     r12, [rbp+47h+ppstm]
0x1800105ed  mov     rax, [rbp+47h+var_70]
0x1800105f1  mov     [rbp+47h+h], rax
0x1800105f5  lea     rcx, [rdi+8]; this
0x1800105f9  call    ?Acquire@CNamedMutex@@QEAAJK@Z; CNamedMutex::Acquire(ulong)
0x1800105fe  mov     ebx, eax
0x180010600  test    eax, eax
0x180010602  js      short loc_180010677
0x180010604  mov     rcx, rdi; this
0x180010607  call    ?_CheckForCacheReset@CThumbnailCacheDataFile@@AEAAJXZ; CThumbnailCacheDataFile::_CheckForCacheReset(void)
0x18001060c  mov     ebx, eax
0x18001060e  test    eax, eax
0x180010610  js      short loc_18001066D
0x180010612  xor     edx, edx; unsigned int
0x180010614  mov     rcx, rdi; this
0x180010617  call    ?_RemapOrGrowMapping@CThumbnailCacheDataFile@@AEAAJK@Z; CThumbnailCacheDataFile::_RemapOrGrowMapping(ulong)
0x18001061c  mov     ebx, eax
0x18001061e  test    eax, eax
0x180010620  js      short loc_18001066D
0x180010622  xor     r14d, r14d
0x180010625  mov     [rbp+47h+var_78], r14d
0x180010629  xor     esi, esi
0x18001062b  mov     [rbp+47h+var_80], esi
0x18001062e  mov     [rbp+47h+var_9C], esi
0x180010631  mov     [rbp+47h+var_A0], esi
0x180010634  lea     rax, [rbp+47h+var_A0]
0x180010638  mov     [rsp+0E0h+var_C0], rax
0x18001063d  lea     r9d, [r14+2]
0x180010641  mov     r8d, [rdi+1A8h]
0x180010648  mov     rdx, [r15]
0x18001064b  mov     rcx, [rdi+20h]
0x18001064f  call    ?Delete@CThumbnailCacheIndex@@QEAAJ_KW4THUMBSIZE@@KPEAK@Z; CThumbnailCacheIndex::Delete(unsigned __int64,THUMBSIZE,ulong,ulong *)
0x180010654  mov     ebx, eax
0x180010656  test    eax, eax
0x180010658  jns     short loc_1800106CE
0x18001065a  cmp     eax, 80030002h
0x18001065f  jz      loc_180010724
0x180010665  test    ebx, ebx
0x180010667  jns     loc_180010724
0x18001066d  lea     rcx, [rdi+8]; this
0x180010671  call    ?Release@CNamedMutex@@QEAAJXZ; CNamedMutex::Release(void)
0x180010676  nop
0x180010677  mov     rcx, [rbp+47h+ppstm]
0x18001067b  test    rcx, rcx
0x18001067e  jz      short loc_18001068D
0x180010680  mov     rax, [rcx]
0x180010683  mov     rax, [rax+10h]
0x180010687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001068c  nop
0x18001068d  mov     eax, ebx
0x18001068f  mov     rcx, [rbp+47h+var_40]
0x180010693  xor     rcx, rsp; StackCookie
0x180010696  call    __security_check_cookie
0x18001069b  mov     rbx, [rsp+0E0h+arg_10]
0x1800106a3  add     rsp, 0B0h
0x1800106aa  pop     r15
0x1800106ac  pop     r14
0x1800106ae  pop     r13
0x1800106b0  pop     r12
0x1800106b2  pop     rdi
0x1800106b3  pop     rsi
0x1800106b4  pop     rbp
0x1800106b5  retn
0x1800106b6  lea     r8, [rbp+47h+ppstm]; ppstm
0x1800106ba  mov     edx, 1; fDeleteOnRelease
0x1800106bf  xor     ecx, ecx; hGlobal
0x1800106c1  call    cs:__imp_CreateStreamOnHGlobal
0x1800106c7  mov     ebx, eax
0x1800106c9  jmp     loc_1800105E1
0x1800106ce  mov     r8d, [rdi+1A8h]
0x1800106d5  mov     r15d, [rbp+47h+var_A0]
0x1800106d9  mov     edx, r15d
0x1800106dc  mov     rcx, [rdi+20h]
0x1800106e0  call    ?CheckThumbnailNotInUse@CThumbnailCacheIndex@@QEAAJKW4THUMBSIZE@@@Z; CThumbnailCacheIndex::CheckThumbnailNotInUse(ulong,THUMBSIZE)
0x1800106e5  mov     ebx, eax
0x1800106e7  test    eax, eax
0x1800106e9  js      loc_18001084C
0x1800106ef  lea     rax, [rbp+47h+var_9C]
0x1800106f3  mov     [rsp+0E0h+var_B8], rax; int *
0x1800106f8  lea     rax, [rbp+47h+h]
0x1800106fc  mov     [rsp+0E0h+var_C0], rax; struct tagSIZE *
0x180010701  mov     r9, [rbp+47h+var_90]; struct CThumbnailMoniker *
0x180010705  mov     r8, r12; struct IStream *
0x180010708  mov     edx, r15d; unsigned int
0x18001070b  mov     rcx, rdi; this
0x18001070e  call    ?_ReplaceThumbnailAtOffset@CThumbnailCacheDataFile@@AEAAJKPEAUIStream@@AEBVCThumbnailMoniker@@AEBUtagSIZE@@PEAH@Z; CThumbnailCacheDataFile::_ReplaceThumbnailAtOffset(ulong,IStream *,CThumbnailMoniker const &,tagSIZE const &,int *)
0x180010713  mov     ebx, eax
0x180010715  test    eax, eax
0x180010717  js      loc_180010665
0x18001071d  mov     esi, r15d
0x180010720  mov     [rbp+47h+var_80], r15d
0x180010724  mov     r15, [rbp+47h+var_90]
0x180010728  cmp     [rbp+47h+var_9C], r14d
0x18001072c  jnz     short loc_180010796
0x18001072e  lea     rax, [rbp+47h+var_78]
0x180010732  mov     [rsp+0E0h+var_B0], rax; int *
0x180010737  lea     rax, [rbp+47h+var_80]
0x18001073b  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x180010740  lea     rax, [rbp+47h+h]
0x180010744  mov     [rsp+0E0h+var_C0], rax; struct tagSIZE *
0x180010749  mov     r9d, [rbp+47h+var_98]; int
0x18001074d  mov     r8, r15; struct CThumbnailMoniker *
0x180010750  mov     rdx, r12; struct IStream *
0x180010753  mov     rcx, rdi; this
0x180010756  call    ?_TryAppendThumbnail@CThumbnailCacheDataFile@@AEAAJPEAUIStream@@AEBVCThumbnailMoniker@@HAEBUtagSIZE@@PEAKPEAH@Z; CThumbnailCacheDataFile::_TryAppendThumbnail(IStream *,CThumbnailMoniker const &,int,tagSIZE const &,ulong *,int *)
0x18001075b  mov     ebx, eax
0x18001075d  test    eax, eax
0x18001075f  js      loc_18001066D
0x180010765  mov     r14d, [rbp+47h+var_78]
0x180010769  test    r14d, r14d
0x18001076c  jnz     short loc_180010793
0x18001076e  lea     rax, [rbp+47h+var_80]
0x180010772  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x180010777  lea     r9, [rbp+47h+h]; struct tagSIZE *
0x18001077b  mov     r8, r15; struct CThumbnailMoniker *
0x18001077e  mov     rdx, r12; struct IStream *
0x180010781  mov     rcx, rdi; this
0x180010784  call    ?_ReclaimThumbnail@CThumbnailCacheDataFile@@AEAAJPEAUIStream@@AEBVCThumbnailMoniker@@AEBUtagSIZE@@PEAK@Z; CThumbnailCacheDataFile::_ReclaimThumbnail(IStream *,CThumbnailMoniker const &,tagSIZE const &,ulong *)
0x180010789  mov     ebx, eax
0x18001078b  test    eax, eax
0x18001078d  js      loc_18001066D
0x180010793  mov     esi, [rbp+47h+var_80]
0x180010796  test    r14d, r14d
0x180010799  jz      short loc_1800107B4
0x18001079b  mov     edx, [rdi+1A8h]
0x1800107a1  mov     rcx, [rdi+20h]
0x1800107a5  call    ?IncrementThumbnailCount@CThumbnailCacheIndex@@QEAAJW4THUMBSIZE@@@Z; CThumbnailCacheIndex::IncrementThumbnailCount(THUMBSIZE)
0x1800107aa  mov     ebx, eax
0x1800107ac  test    eax, eax
0x1800107ae  js      loc_18001066D
0x1800107b4  mov     eax, [rbp+47h+var_94]
0x1800107b7  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800107bb  mov     dword ptr [rsp+0E0h+var_C0], esi
0x1800107bf  mov     r9, [rbp+47h+h]
0x1800107c3  mov     r8d, [rdi+1A8h]
0x1800107ca  mov     rdx, r15
0x1800107cd  mov     rcx, [rdi+20h]
0x1800107d1  call    ?Insert@CThumbnailCacheIndex@@QEAAJAEBVCThumbnailMoniker@@W4THUMBSIZE@@UtagSIZE@@KH@Z; CThumbnailCacheIndex::Insert(CThumbnailMoniker const &,THUMBSIZE,tagSIZE,ulong,int)
0x1800107d6  mov     ebx, eax
0x1800107d8  jmp     loc_18001066D
0x1800107dd  mov     rcx, [rdi+3B8h]
0x1800107e4  mov     rax, [rcx]
0x1800107e7  mov     rax, [rax+30h]
0x1800107eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f0  cmp     eax, 1
0x1800107f3  jz      short loc_18001083E
0x1800107f5  mov     ecx, eax
0x1800107f7  call    ?GetContentTypeFromStreamType@@YAPEBGW4WTS_STREAMTYPE@@@Z; GetContentTypeFromStreamType(WTS_STREAMTYPE)
0x1800107fc  mov     rcx, [rsi]
0x1800107ff  mov     r10, [rcx+38h]
0x180010803  lea     r9, [rbp+47h+ppstm]
0x180010807  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x18001080e  mov     rdx, rax
0x180010811  mov     rcx, rsi
0x180010814  mov     rax, r10
0x180010817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001081c  mov     ebx, eax
0x18001081e  test    eax, eax
0x180010820  js      loc_180010677
0x180010826  mov     rax, [rsi]
0x180010829  lea     rdx, [rbp+47h+var_70]
0x18001082d  mov     rcx, rsi
0x180010830  mov     rax, [rax+48h]
0x180010834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010839  jmp     loc_1800106C7
0x18001083e  mov     ecx, 3
0x180010843  cmp     [rbp+47h+arg_28], 2
0x180010847  cmovz   eax, ecx
0x18001084a  jmp     short loc_1800107F5
0x18001084c  cmp     eax, 80070020h
0x180010851  jnz     loc_180010665
0x180010857  lea     rcx, OutputString; "Thumbnail Cache: Attempting to replace "...
0x18001085e  call    cs:__imp_OutputDebugStringW
0x180010864  xor     ebx, ebx
0x180010866  jmp     loc_180010665
0x18001086b  mov     [rbp+47h+var_70], 0
0x180010873  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180010878  mov     ebx, eax
0x18001087a  test    eax, eax
0x18001087c  jns     loc_1800105A2
0x180010882  jmp     loc_1800105C3
```
