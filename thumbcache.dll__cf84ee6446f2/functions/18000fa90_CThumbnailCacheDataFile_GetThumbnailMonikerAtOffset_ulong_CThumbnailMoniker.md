# CThumbnailCacheDataFile::GetThumbnailMonikerAtOffset(ulong,CThumbnailMoniker *)

- ea: `0x18000fa90`
- end: `0x18000fbcc`
- name: `?GetThumbnailMonikerAtOffset@CThumbnailCacheDataFile@@QEAAJKPEAVCThumbnailMoniker@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned int, struct CThumbnailMoniker *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013d80`
- `0x1800435b4`

## callees

- `0x18000e624`
- `0x18000fa90`
- `0x1800117b8`
- `0x18001a3ec`
- `0x180027f04`
- `0x180029784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb59`

## pseudocode

```c
__int64 __fastcall CThumbnailCacheDataFile::GetThumbnailMonikerAtOffset(
        RTL_SRWLOCK *this,
        unsigned int a2,
        struct CThumbnailMoniker *a3)
{
  RTL_SRWLOCK *v5; // r15
  CThumbnailCacheDataFile *v6; // rcx
  int v7; // ebx
  struct DataFileEntryHeaderAligned *v8; // rdi
  __int64 v9; // r8
  int v10; // ecx
  __int64 v11; // rax
  int v12; // eax
  unsigned __int64 v13; // rdi
  void *v14; // rcx
  int v15; // edx
  int v16; // ecx
  unsigned int v18; // [rsp+20h] [rbp-58h]
  void *v19[2]; // [rsp+30h] [rbp-48h] BYREF
  CMappingManager *v20; // [rsp+40h] [rbp-38h]
  int v21; // [rsp+48h] [rbp-30h]
  struct DataFileEntryHeaderAligned *v22[2]; // [rsp+50h] [rbp-28h] BYREF
  CMappingManager *v23; // [rsp+60h] [rbp-18h]
  int v24; // [rsp+68h] [rbp-10h]

  *(_OWORD *)v22 = 0;
  v23 = 0;
  v5 = this + 9;
  v7 = CSmartMappedView<DataFileEntryHeaderAligned __unaligned>::MapPartialViewAtOffset(
         (__int64)v22,
         this + 9,
         0,
         a2,
         v18);
  if ( v7 < 0 )
    goto LABEL_13;
  v8 = v22[1];
  v7 = CThumbnailCacheDataFile::_CheckValidHeader(v6, v22[1]);
  if ( v7 < 0 )
    goto LABEL_13;
  v10 = *((_DWORD *)a3 + 3);
  v11 = *((_QWORD *)v8 + 1);
  if ( (v10 & 1) == 0 )
  {
    *(_QWORD *)a3 = v11;
    *((_DWORD *)a3 + 3) = v10 | 1;
LABEL_7:
    v12 = *((_DWORD *)v8 + 4);
    if ( v12 )
    {
      *(_OWORD *)v19 = 0;
      v20 = 0;
      v7 = CSmartMappedView<unsigned short>::MapPartialViewAtOffset(v19, v5, v9, a2 + 56, v12);
      if ( v7 >= 0 )
      {
        v13 = *((unsigned int *)v8 + 4);
        *((_DWORD *)a3 + 3) &= ~2u;
        v14 = (void *)*((_QWORD *)a3 + 2);
        *((_QWORD *)a3 + 2) = 0;
        CoTaskMemFree(v14);
        v7 = _AllocStringWorker<CTCoAllocPolicy>(v16, v15, v19[1], v13 >> 1);
        if ( v7 >= 0 )
          *((_DWORD *)a3 + 3) |= 2u;
      }
      if ( v19[0] )
        CMappingManager::ReleaseView(v20, v19[0], v21);
    }
    else
    {
      v7 = -2147467259;
    }
    goto LABEL_13;
  }
  if ( *(_QWORD *)a3 != v11 )
    v7 = -2147467259;
  if ( v7 >= 0 )
    goto LABEL_7;
LABEL_13:
  if ( v22[0] )
    CMappingManager::ReleaseView(v23, v22[0], v24);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fa90  push    rbp
0x18000fa92  push    rbx
0x18000fa93  push    rsi
0x18000fa94  push    rdi
0x18000fa95  push    r14
0x18000fa97  push    r15
0x18000fa99  mov     rbp, rsp
0x18000fa9c  sub     rsp, 78h
0x18000faa0  mov     rsi, r8
0x18000faa3  mov     r14d, edx
0x18000faa6  xorps   xmm0, xmm0
0x18000faa9  movdqu  xmmword ptr [rbp+var_28], xmm0
0x18000faae  mov     [rbp+var_18], 0
0x18000fab6  lea     r15, [rcx+48h]
0x18000faba  mov     r9d, edx
0x18000fabd  xor     r8d, r8d
0x18000fac0  mov     rdx, r15
0x18000fac3  lea     rcx, [rbp+var_28]
0x18000fac7  call    ?MapPartialViewAtOffset@?$CSmartMappedView@$$CFAUDataFileEntryHeaderAligned@@@@QEAAJPEAVCMappingManager@@HKK@Z; CSmartMappedView<DataFileEntryHeaderAligned>::MapPartialViewAtOffset(CMappingManager *,int,ulong,ulong)
0x18000facc  mov     ebx, eax
0x18000face  test    eax, eax
0x18000fad0  js      loc_18000FB94
0x18000fad6  mov     rdi, [rbp+var_28+8]
0x18000fada  mov     rdx, rdi; struct DataFileEntryHeaderAligned *
0x18000fadd  call    ?_CheckValidHeader@CThumbnailCacheDataFile@@AEAAJPEFBUDataFileEntryHeaderAligned@@@Z; CThumbnailCacheDataFile::_CheckValidHeader(DataFileEntryHeaderAligned const *)
0x18000fae2  mov     ebx, eax
0x18000fae4  test    eax, eax
0x18000fae6  js      loc_18000FB94
0x18000faec  mov     ecx, [rsi+0Ch]
0x18000faef  mov     edx, 80004005h
0x18000faf4  mov     rax, [rdi+8]
0x18000faf8  test    cl, 1
0x18000fafb  jz      loc_18000FBB9
0x18000fb01  cmp     [rsi], rax
0x18000fb04  cmovnz  ebx, edx
0x18000fb07  test    ebx, ebx
0x18000fb09  js      loc_18000FB94
0x18000fb0f  mov     eax, [rdi+10h]
0x18000fb12  test    eax, eax
0x18000fb14  jz      loc_18000FBC7
0x18000fb1a  xorps   xmm0, xmm0
0x18000fb1d  movdqu  xmmword ptr [rbp+var_48], xmm0
0x18000fb22  mov     [rbp+var_38], 0
0x18000fb2a  lea     r9d, [r14+38h]
0x18000fb2e  mov     [rsp+78h+var_58], eax
0x18000fb32  mov     rdx, r15
0x18000fb35  lea     rcx, [rbp+var_48]
0x18000fb39  call    ?MapPartialViewAtOffset@?$CSmartMappedView@G@@QEAAJPEAVCMappingManager@@HKK@Z; CSmartMappedView<ushort>::MapPartialViewAtOffset(CMappingManager *,int,ulong,ulong)
0x18000fb3e  mov     ebx, eax
0x18000fb40  test    eax, eax
0x18000fb42  js      short loc_18000FB7D
0x18000fb44  mov     edi, [rdi+10h]
0x18000fb47  and     dword ptr [rsi+0Ch], 0FFFFFFFDh
0x18000fb4b  lea     rbx, [rsi+10h]
0x18000fb4f  mov     rcx, [rbx]; pv
0x18000fb52  mov     qword ptr [rbx], 0
0x18000fb59  call    cs:__imp_CoTaskMemFree
0x18000fb5f  shr     rdi, 1
0x18000fb62  mov     [rsp+78h+var_50], rbx
0x18000fb67  mov     r9, rdi
0x18000fb6a  mov     r8, [rbp+var_48+8]
0x18000fb6e  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18000fb73  mov     ebx, eax
0x18000fb75  test    eax, eax
0x18000fb77  js      short loc_18000FB7D
0x18000fb79  or      dword ptr [rsi+0Ch], 2
0x18000fb7d  mov     rdx, [rbp+var_48]; void *
0x18000fb81  test    rdx, rdx
0x18000fb84  jz      short loc_18000FB94
0x18000fb86  mov     r8d, [rbp+var_30]; int
0x18000fb8a  mov     rcx, [rbp+var_38]; this
0x18000fb8e  call    ?ReleaseView@CMappingManager@@QEAAJPEAXH@Z; CMappingManager::ReleaseView(void *,int)
0x18000fb93  nop
0x18000fb94  mov     rdx, [rbp+var_28]; void *
0x18000fb98  test    rdx, rdx
0x18000fb9b  jz      short loc_18000FBAA
0x18000fb9d  mov     r8d, [rbp+var_10]; int
0x18000fba1  mov     rcx, [rbp+var_18]; this
0x18000fba5  call    ?ReleaseView@CMappingManager@@QEAAJPEAXH@Z; CMappingManager::ReleaseView(void *,int)
0x18000fbaa  mov     eax, ebx
0x18000fbac  add     rsp, 78h
0x18000fbb0  pop     r15
0x18000fbb2  pop     r14
0x18000fbb4  pop     rdi
0x18000fbb5  pop     rsi
0x18000fbb6  pop     rbx
0x18000fbb7  pop     rbp
0x18000fbb8  retn
0x18000fbb9  mov     [rsi], rax
0x18000fbbc  or      ecx, 1
0x18000fbbf  mov     [rsi+0Ch], ecx
0x18000fbc2  jmp     loc_18000FB0F
0x18000fbc7  mov     ebx, edx
0x18000fbc9  jmp     short loc_18000FB94
```
