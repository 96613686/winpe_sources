# CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::Initialize(CImageCache *,ulong,ushort const *,int,ulong)

- ea: `0x180008de8`
- end: `0x180008efa`
- name: `?Initialize@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@QEAAKPEAVCImageCache@@KPEBGHK@Z`
- size: `274`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008f9c`

## callees

- `0x1800080a8`
- `0x180008104`
- `0x180008de8`
- `0x180008f00`
- `0x18000a944`
- `0x18000aeac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008e96`
- `KERNEL32!GetLastError` at `0x180008e96`
- `KERNEL32!FindFirstChangeNotificationW` at `0x180008e80`
- `KERNEL32!FindFirstChangeNotificationW` at `0x180008e80`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008e24`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180008e24`

## pseudocode

```c
__int64 __fastcall CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::Initialize(
        __int64 Context,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rdx
  __int64 v8; // rdx
  HANDLE v9; // rax
  DWORD LastError; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  _BYTE v14[24]; // [rsp+40h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v14, Context);
  *(_QWORD *)(Context + 48) = a2;
  *(_DWORD *)(Context + 64) = 5000;
  LODWORD(a2) = DuplicateStringW(a4, (unsigned __int16 **)(Context + 56));
  if ( !(unsigned int)ElValidateWin32_0(
                        (unsigned int)a2,
                        v7,
                        "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h",
                        182) )
  {
    a2 = (unsigned int)CTimer<CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>>::Initialize(
                         Context + 88,
                         Context);
    if ( !(unsigned int)ElValidateWin32_0(a2, v8, "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h", 188) )
    {
      v9 = FindFirstChangeNotificationW(*(LPCWSTR *)(Context + 56), 1, 0x11Fu);
      *(_QWORD *)(Context + 72) = v9;
      if ( v9 == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        LODWORD(a2) = ElValidateWin32_0(
                        LastError,
                        v11,
                        "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h",
                        199);
        if ( !(_DWORD)a2 )
          LODWORD(a2) = 31;
      }
      else
      {
        a2 = (unsigned int)CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::RegisterWait((PVOID)Context);
        ElValidateWin32_0(a2, v12, "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h", 206);
      }
    }
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v14);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180008de8  mov     rax, rsp
0x180008deb  mov     [rax+8], rbx
0x180008def  mov     [rax+10h], rsi
0x180008df3  mov     [rax+18h], rdi
0x180008df7  push    r14
0x180008df9  sub     rsp, 50h
0x180008dfd  mov     rbx, rdx
0x180008e00  mov     rsi, rcx
0x180008e03  mov     rdx, rcx
0x180008e06  mov     rdi, r9
0x180008e09  lea     rcx, [rax-18h]
0x180008e0d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180008e12  lea     rdx, [rsi+38h]
0x180008e16  mov     [rsi+30h], rbx
0x180008e1a  mov     rcx, rdi
0x180008e1d  mov     dword ptr [rsi+40h], 1388h
0x180008e24  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180008e2b  nop     dword ptr [rax+rax+00h]
0x180008e30  lea     rdi, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x180008e37  mov     r9d, 0B6h
0x180008e3d  mov     r8, rdi
0x180008e40  mov     ecx, eax
0x180008e42  mov     ebx, eax
0x180008e44  call    ElValidateWin32_0
0x180008e49  test    eax, eax
0x180008e4b  jnz     loc_180008ED7
0x180008e51  lea     rcx, [rsi+58h]; Parameter
0x180008e55  mov     rdx, rsi
0x180008e58  call    ?Initialize@?$CTimer@V?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@@@QEAAKPEAV?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@PEAXKK1K@Z; CTimer<CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>>::Initialize(CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)> *,void *,ulong,ulong,void *,ulong)
0x180008e5d  mov     r9d, 0BCh
0x180008e63  mov     r8, rdi
0x180008e66  mov     ecx, eax
0x180008e68  mov     ebx, eax
0x180008e6a  call    ElValidateWin32_0
0x180008e6f  test    eax, eax
0x180008e71  jnz     short loc_180008ED7
0x180008e73  mov     rcx, [rsi+38h]; lpPathName
0x180008e77  lea     edx, [rax+1]; bWatchSubtree
0x180008e7a  mov     r8d, 11Fh; dwNotifyFilter
0x180008e80  call    cs:__imp_FindFirstChangeNotificationW
0x180008e87  nop     dword ptr [rax+rax+00h]
0x180008e8c  mov     [rsi+48h], rax
0x180008e90  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008e94  jnz     short loc_180008EBD
0x180008e96  call    cs:__imp_GetLastError
0x180008e9d  nop     dword ptr [rax+rax+00h]
0x180008ea2  mov     r9d, 0C7h
0x180008ea8  mov     r8, rdi
0x180008eab  mov     ecx, eax
0x180008ead  call    ElValidateWin32_0
0x180008eb2  mov     ebx, eax
0x180008eb4  test    eax, eax
0x180008eb6  jnz     short loc_180008ED7
0x180008eb8  lea     ebx, [rax+1Fh]
0x180008ebb  jmp     short loc_180008ED7
0x180008ebd  mov     rcx, rsi; Context
0x180008ec0  call    ?RegisterWait@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@AEAAKXZ; CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::RegisterWait(void)
0x180008ec5  mov     r9d, 0CEh
0x180008ecb  mov     r8, rdi
0x180008ece  mov     ecx, eax
0x180008ed0  mov     ebx, eax
0x180008ed2  call    ElValidateWin32_0
0x180008ed7  lea     rcx, [rsp+58h+var_18]
0x180008edc  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180008ee1  mov     rsi, [rsp+58h+arg_8]
0x180008ee6  mov     eax, ebx
0x180008ee8  mov     rbx, [rsp+58h+arg_0]
0x180008eed  mov     rdi, [rsp+58h+arg_10]
0x180008ef2  add     rsp, 50h
0x180008ef6  pop     r14
0x180008ef8  retn
```
