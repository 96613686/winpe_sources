# CThumbnailCache::GetThumbnailStream(IShellItem *,uint,WTS_FLAGS,void *,THUMBNAILSTREAMINFO *,_GUID const &,void * *)

- ea: `0x18002a5f0`
- end: `0x18002a81e`
- name: `?GetThumbnailStream@CThumbnailCache@@UEAAJPEAUIShellItem@@IW4WTS_FLAGS@@PEAXPEAUTHUMBNAILSTREAMINFO@@AEBU_GUID@@PEAPEAX@Z`
- size: `558`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this, struct IShellItem *, unsigned int, enum WTS_FLAGS, void *, struct THUMBNAILSTREAMINFO *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003624`
- `0x18000a300`
- `0x18002a5f0`
- `0x18002a824`
- `0x180035830`
- `0x180043904`
- `0x1800439b0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CThumbnailCache::GetThumbnailStream(
        CThumbnailCache *this,
        struct IShellItem *a2,
        unsigned int a3,
        __int32 a4,
        void *a5,
        struct THUMBNAILSTREAMINFO *a6,
        const struct _GUID *a7,
        void **a8)
{
  int v12; // edx
  int v13; // ecx
  int ThumbnailInternal; // ebx
  __int64 v15; // rax
  __int64 *v16; // rcx
  int v18; // edx
  int v19; // ecx
  LPVOID v20; // [rsp+58h] [rbp-39h] BYREF
  __int64 *v21; // [rsp+60h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-29h] BYREF
  __int64 v23; // [rsp+70h] [rbp-21h]
  __int64 v24; // [rsp+78h] [rbp-19h]

  *(_OWORD *)a6 = 0;
  *((_OWORD *)a6 + 1) = 0;
  *a8 = 0;
  if ( !a2 )
    return 2147500035LL;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v20 = 0;
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetDisplayName)(
           a2,
           2147581953LL,
           &v20) < 0 )
    {
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
        McTemplateU0zdq_EventWriteTransfer(v19, v18, (unsigned int)&unk_1800509F8, a3, a4);
    }
    else
    {
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
        McTemplateU0zdq_EventWriteTransfer(v19, v18, (_DWORD)v20, a3, a4);
      CoTaskMemFree(v20);
    }
  }
  v21 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  ThumbnailInternal = CThumbnailCache::_GetThumbnailInternal(
                        (__int64)this,
                        a2,
                        a3,
                        (enum WTS_FLAGS)a4,
                        0,
                        a5,
                        &v21,
                        (enum WTS_CACHEFLAGS *)a6,
                        (struct THUMBNAILSTREAMINFO *)((char *)a6 + 4));
  if ( ThumbnailInternal >= 0 )
  {
    ThumbnailInternal = (*(__int64 (__fastcall **)(__int64 *, char *))(*v21 + 72))(v21, (char *)a6 + 20);
    if ( ThumbnailInternal >= 0 )
    {
      pv = 0;
      v23 = 0;
      v24 = 0;
      v15 = *v21;
      v23 = -1;
      v24 = -1;
      ThumbnailInternal = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v15 + 80))(v21, &pv);
      if ( ThumbnailInternal >= 0 )
      {
        *((_DWORD *)a6 + 7) = GetStreamTypeFromContentType(pv);
        ThumbnailInternal = (*(__int64 (__fastcall **)(__int64 *, __int64, const struct _GUID *, void **))(*v21 + 48))(
                              v21,
                              3,
                              a7,
                              a8);
      }
      v13 = (int)pv;
      if ( pv )
        CoTaskMemFree(pv);
    }
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McTemplateU0dqddd_EventWriteTransfer(
      v13,
      v12,
      ThumbnailInternal,
      *(_DWORD *)a6,
      *((_DWORD *)a6 + 5),
      *((_DWORD *)a6 + 6),
      *((_DWORD *)a6 + 7));
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
  }
  return (unsigned int)ThumbnailInternal;
}

```

## disassembly

```asm
0x18002a5f0  push    rbp
0x18002a5f2  push    rbx
0x18002a5f3  push    rsi
0x18002a5f4  push    rdi
0x18002a5f5  push    r12
0x18002a5f7  push    r13
0x18002a5f9  push    r14
0x18002a5fb  push    r15
0x18002a5fd  lea     rbp, [rsp-7]
0x18002a602  sub     rsp, 98h
0x18002a609  mov     rax, cs:__security_cookie
0x18002a610  xor     rax, rsp
0x18002a613  mov     [rbp+3Fh+var_50], rax
0x18002a617  mov     esi, r9d
0x18002a61a  mov     ebx, r8d
0x18002a61d  mov     r14, rdx
0x18002a620  mov     r15, rcx
0x18002a623  mov     rdi, [rbp+3Fh+arg_28]
0x18002a627  mov     r12, [rbp+3Fh+arg_20]
0x18002a62b  mov     rax, [rbp+3Fh+arg_30]
0x18002a62f  mov     [rbp+3Fh+var_80], rax
0x18002a633  mov     r13, [rbp+3Fh+arg_38]
0x18002a63a  xorps   xmm0, xmm0
0x18002a63d  movups  xmmword ptr [rdi], xmm0
0x18002a640  movups  xmmword ptr [rdi+10h], xmm0
0x18002a644  mov     qword ptr [r13+0], 0
0x18002a64c  test    rdx, rdx
0x18002a64f  jz      loc_18002A780
0x18002a655  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002a65c  jnz     loc_18002A787
0x18002a662  mov     [rbp+3Fh+var_70], 0
0x18002a66a  lea     rcx, [rbp+3Fh+var_70]
0x18002a66e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a673  lea     rax, [rdi+4]
0x18002a677  mov     [rsp+0D0h+var_90], rax
0x18002a67c  mov     [rsp+0D0h+var_98], rdi
0x18002a681  lea     rax, [rbp+3Fh+var_70]
0x18002a685  mov     [rsp+0D0h+var_A0], rax
0x18002a68a  mov     [rsp+0D0h+var_A8], r12
0x18002a68f  xor     r12d, r12d
0x18002a692  mov     [rsp+0D0h+var_B0], r12d
0x18002a697  mov     r9d, esi
0x18002a69a  mov     r8d, ebx
0x18002a69d  mov     rdx, r14
0x18002a6a0  mov     rcx, r15
0x18002a6a3  call    ?_GetThumbnailInternal@CThumbnailCache@@AEAAJPEAUIShellItem@@IW4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@PEAXPEAPEAUIBitmapResult@@PEAW4WTS_CACHEFLAGS@@PEAUWTS_THUMBNAILID@@@Z; CThumbnailCache::_GetThumbnailInternal(IShellItem *,uint,WTS_FLAGS,WTS_PRIV_FLAGS,void *,IBitmapResult * *,WTS_CACHEFLAGS *,WTS_THUMBNAILID *)
0x18002a6a8  mov     ebx, eax
0x18002a6aa  test    eax, eax
0x18002a6ac  js      loc_18002A737
0x18002a6b2  mov     rcx, [rbp+3Fh+var_70]
0x18002a6b6  mov     rax, [rcx]
0x18002a6b9  lea     rdx, [rdi+14h]
0x18002a6bd  mov     rax, [rax+48h]
0x18002a6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6c6  mov     ebx, eax
0x18002a6c8  test    eax, eax
0x18002a6ca  js      short loc_18002A737
0x18002a6cc  mov     [rbp+3Fh+pv], r12
0x18002a6d0  mov     [rbp+3Fh+var_60], r12
0x18002a6d4  mov     [rbp+3Fh+var_58], r12
0x18002a6d8  mov     rcx, [rbp+3Fh+var_70]
0x18002a6dc  mov     rax, [rcx]
0x18002a6df  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a6e3  mov     [rbp+3Fh+var_60], rdx
0x18002a6e7  mov     [rbp+3Fh+var_58], rdx
0x18002a6eb  lea     rdx, [rbp+3Fh+pv]
0x18002a6ef  mov     rax, [rax+50h]
0x18002a6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6f8  mov     ebx, eax
0x18002a6fa  test    eax, eax
0x18002a6fc  js      short loc_18002A728
0x18002a6fe  mov     rcx, [rbp+3Fh+pv]
0x18002a702  call    ?GetStreamTypeFromContentType@@YA?AW4WTS_STREAMTYPE@@PEBG@Z; GetStreamTypeFromContentType(ushort const *)
0x18002a707  mov     [rdi+1Ch], eax
0x18002a70a  mov     rcx, [rbp+3Fh+var_70]
0x18002a70e  mov     rax, [rcx]
0x18002a711  mov     r9, r13
0x18002a714  mov     r8, [rbp+3Fh+var_80]
0x18002a718  lea     edx, [r12+3]
0x18002a71d  mov     rax, [rax+30h]
0x18002a721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a726  mov     ebx, eax
0x18002a728  mov     rcx, [rbp+3Fh+pv]; pv
0x18002a72c  test    rcx, rcx
0x18002a72f  jz      short loc_18002A737
0x18002a731  call    cs:__imp_CoTaskMemFree
0x18002a737  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002a73e  jnz     loc_18002A7F8
0x18002a744  mov     rcx, [rbp+3Fh+var_70]
0x18002a748  test    rcx, rcx
0x18002a74b  jz      short loc_18002A75E
0x18002a74d  mov     [rbp+3Fh+var_70], r12
0x18002a751  mov     rax, [rcx]
0x18002a754  mov     rax, [rax+10h]
0x18002a758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a75d  nop
0x18002a75e  mov     eax, ebx
0x18002a760  mov     rcx, [rbp+3Fh+var_50]
0x18002a764  xor     rcx, rsp; StackCookie
0x18002a767  call    __security_check_cookie
0x18002a76c  add     rsp, 98h
0x18002a773  pop     r15
0x18002a775  pop     r14
0x18002a777  pop     r13
0x18002a779  pop     r12
0x18002a77b  pop     rdi
0x18002a77c  pop     rsi
0x18002a77d  pop     rbx
0x18002a77e  pop     rbp
0x18002a77f  retn
0x18002a780  mov     eax, 80004003h
0x18002a785  jmp     short loc_18002A760
0x18002a787  mov     [rbp+3Fh+var_78], 0
0x18002a78f  mov     rax, [rdx]
0x18002a792  lea     r8, [rbp+3Fh+var_78]
0x18002a796  mov     edx, 80018001h
0x18002a79b  mov     rcx, r14
0x18002a79e  mov     rax, [rax+28h]
0x18002a7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7a7  test    eax, eax
0x18002a7a9  js      short loc_18002A7D3
0x18002a7ab  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002a7b2  jz      short loc_18002A7C4
0x18002a7b4  mov     [rsp+0D0h+var_B0], esi
0x18002a7b8  mov     r9d, ebx
0x18002a7bb  mov     r8, [rbp+3Fh+var_78]
0x18002a7bf  call    McTemplateU0zdq_EventWriteTransfer
0x18002a7c4  mov     rcx, [rbp+3Fh+var_78]; pv
0x18002a7c8  call    cs:__imp_CoTaskMemFree
0x18002a7ce  jmp     loc_18002A662
0x18002a7d3  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002a7da  jz      loc_18002A662
0x18002a7e0  mov     [rsp+0D0h+var_B0], esi
0x18002a7e4  mov     r9d, ebx
0x18002a7e7  lea     r8, unk_1800509F8
0x18002a7ee  call    McTemplateU0zdq_EventWriteTransfer
0x18002a7f3  jmp     loc_18002A662
0x18002a7f8  mov     eax, [rdi+1Ch]
0x18002a7fb  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18002a7ff  mov     eax, [rdi+18h]
0x18002a802  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18002a806  mov     eax, [rdi+14h]
0x18002a809  mov     [rsp+0D0h+var_B0], eax
0x18002a80d  mov     r9d, [rdi]
0x18002a810  mov     r8d, ebx
0x18002a813  call    McTemplateU0dqddd_EventWriteTransfer
0x18002a818  jmp     loc_18002A744
```
