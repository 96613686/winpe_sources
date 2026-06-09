# CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::Shutdown(void)

- ea: `0x180006bf0`
- end: `0x180006c9f`
- name: `?Shutdown@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAAKXZ`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800027c8`
- `0x18000af80`

## callees

- `0x1800025f0`
- `0x18000277c`
- `0x180002948`
- `0x180006bf0`
- `0x180006da4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180006c7b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006c7b`
- `KERNEL32!UnregisterWait` at `0x180006c46`
- `KERNEL32!UnregisterWait` at `0x180006c46`
- `KERNEL32!FindCloseChangeNotification` at `0x180006c61`
- `KERNEL32!FindCloseChangeNotification` at `0x180006c61`

## pseudocode

```c
__int64 __fastcall CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::Shutdown(
        __int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF

  _InterlockedExchange((volatile __int32 *)(a1 + 40), 1);
  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>((__int64)v6, a1 + 88);
  _InterlockedExchange((volatile __int32 *)(a1 + 128), 1);
  CAutoTypeLock<CSpinLock>::Unlock((__int64)v6);
  CTimer<CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>>::Delete(a1 + 88);
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(v6);
  v2 = *(void **)(a1 + 80);
  if ( v2 )
  {
    UnregisterWait(v2);
    *(_QWORD *)(a1 + 80) = 0;
  }
  v3 = *(void **)(a1 + 72);
  if ( v3 != (void *)-1LL )
  {
    FindCloseChangeNotification(v3);
    *(_QWORD *)(a1 + 72) = -1;
  }
  v4 = *(void **)(a1 + 56);
  if ( v4 )
  {
    operator delete[](v4);
    *(_QWORD *)(a1 + 56) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180006bf0  mov     [rsp+arg_0], rbx
0x180006bf5  mov     [rsp+arg_8], rsi
0x180006bfa  push    rdi
0x180006bfb  sub     rsp, 30h
0x180006bff  mov     rsi, rcx
0x180006c02  lea     rdx, [rcx+58h]
0x180006c06  mov     edi, 1
0x180006c0b  mov     eax, edi
0x180006c0d  xchg    eax, [rcx+28h]
0x180006c10  lea     rcx, [rsp+38h+var_18]
0x180006c15  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x180006c1a  xchg    edi, [rsi+80h]
0x180006c20  lea     rcx, [rsp+38h+var_18]
0x180006c25  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x180006c2a  lea     rcx, [rsi+58h]
0x180006c2e  call    ?Delete@?$CTimer@V?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@@@AEAAXXZ; CTimer<CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>>::Delete(void)
0x180006c33  lea     rcx, [rsp+38h+var_18]
0x180006c38  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180006c3d  mov     rcx, [rsi+50h]; WaitHandle
0x180006c41  test    rcx, rcx
0x180006c44  jz      short loc_180006C57
0x180006c46  call    cs:__imp_UnregisterWait
0x180006c4d  nop     dword ptr [rax+rax+00h]
0x180006c52  and     qword ptr [rsi+50h], 0
0x180006c57  mov     rcx, [rsi+48h]; hChangeHandle
0x180006c5b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006c5f  jz      short loc_180006C72
0x180006c61  call    cs:__imp_FindCloseChangeNotification
0x180006c68  nop     dword ptr [rax+rax+00h]
0x180006c6d  or      qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x180006c72  mov     rcx, [rsi+38h]
0x180006c76  test    rcx, rcx
0x180006c79  jz      short loc_180006C8C
0x180006c7b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006c82  nop     dword ptr [rax+rax+00h]
0x180006c87  and     qword ptr [rsi+38h], 0
0x180006c8c  mov     rbx, [rsp+38h+arg_0]
0x180006c91  xor     eax, eax
0x180006c93  mov     rsi, [rsp+38h+arg_8]
0x180006c98  add     rsp, 30h
0x180006c9c  pop     rdi
0x180006c9d  retn
```
