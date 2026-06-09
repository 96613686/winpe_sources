# CImageCache::~CImageCache(void)

- ea: `0x18000af80`
- end: `0x18000b02c`
- name: `??1CImageCache@@QEAA@XZ`
- size: `172`
- prototype: `void __fastcall(CImageCache *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b3ac`

## callees

- `0x1800027c8`
- `0x1800028a8`
- `0x180006bf0`
- `0x18000aeac`
- `0x18000af80`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000afcd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000afcd`
- `KERNEL32!FreeLibrary` at `0x18000aff2`
- `KERNEL32!FreeLibrary` at `0x18000aff2`
- `WdsCommonLib!??1CMRSWLock@@QEAA@XZ` at `0x18000b020`

## string_xrefs

- `0x18000afb2`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`

## pseudocode

```c
void __fastcall CImageCache::~CImageCache(CImageCache *this)
{
  char *v1; // rdi
  unsigned int v3; // eax
  __int64 v4; // rdx
  void *v5; // rcx
  HMODULE v6; // rcx

  v1 = (char *)this + 128;
  CDynArray<CImageCache::Image *,CDeallocatePointer>::Clear((char *)this + 128);
  v3 = CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::Shutdown((char *)this + 176);
  ElValidateWin32_0(v3, v4, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 185);
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 )
  {
    operator delete[](v5);
    *((_QWORD *)this + 15) = 0;
  }
  CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::~CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>((struct _RTL_CRITICAL_SECTION *)((char *)this + 176));
  v6 = (HMODULE)*((_QWORD *)this + 20);
  if ( v6 )
  {
    FreeLibrary(v6);
    *((_QWORD *)this + 20) = 0;
  }
  CDynArray<CImageCache::Image *,CDeallocatePointer>::Clear(v1);
  CMRSWLock::~CMRSWLock(this);
}

```

## disassembly

```asm
0x18000af80  mov     [rsp+arg_0], rbx
0x18000af85  mov     [rsp+arg_8], rsi
0x18000af8a  push    rdi
0x18000af8b  sub     rsp, 20h
0x18000af8f  lea     rdi, [rcx+80h]
0x18000af96  mov     rbx, rcx
0x18000af99  mov     rcx, rdi
0x18000af9c  call    ?Clear@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CImageCache::Image *,CDeallocatePointer>::Clear(void)
0x18000afa1  lea     rsi, [rbx+0B0h]
0x18000afa8  mov     rcx, rsi
0x18000afab  call    ?Shutdown@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAAKXZ; CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::Shutdown(void)
0x18000afb0  mov     ecx, eax
0x18000afb2  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000afb9  mov     r9d, 0B9h
0x18000afbf  call    ElValidateWin32_0
0x18000afc4  mov     rcx, [rbx+78h]
0x18000afc8  test    rcx, rcx
0x18000afcb  jz      short loc_18000AFDE
0x18000afcd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000afd4  nop     dword ptr [rax+rax+00h]
0x18000afd9  and     qword ptr [rbx+78h], 0
0x18000afde  mov     rcx, rsi
0x18000afe1  call    ??1?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAA@XZ; CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::~CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>(void)
0x18000afe6  mov     rcx, [rbx+0A0h]; hLibModule
0x18000afed  test    rcx, rcx
0x18000aff0  jz      short loc_18000B006
0x18000aff2  call    cs:__imp_FreeLibrary
0x18000aff9  nop     dword ptr [rax+rax+00h]
0x18000affe  and     qword ptr [rbx+0A0h], 0
0x18000b006  mov     rcx, rdi
0x18000b009  call    ?Clear@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CImageCache::Image *,CDeallocatePointer>::Clear(void)
0x18000b00e  mov     rcx, rbx
0x18000b011  mov     rbx, [rsp+28h+arg_0]
0x18000b016  mov     rsi, [rsp+28h+arg_8]
0x18000b01b  add     rsp, 20h
0x18000b01f  pop     rdi
0x18000b020  jmp     cs:__imp_??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
```
