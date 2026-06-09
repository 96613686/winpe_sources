# CTimer<CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>>::_TimerCallback(void *,uchar)

- ea: `0x18000ace0`
- end: `0x18000ad58`
- name: `?_TimerCallback@?$CTimer@V?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@@@SAXPEAXE@Z`
- size: `120`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800025f0`
- `0x18000277c`
- `0x180006da4`
- `0x1800096b8`
- `0x18000ace0`
- `0x18000aeac`

## pseudocode

```c
void __fastcall CTimer<CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>>::_TimerCallback(
        volatile signed __int32 *a1)
{
  BOOL v2; // ebx
  __int64 v3; // rcx
  unsigned int v4; // eax
  __int64 v5; // rdx
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>((__int64)v6, (__int64)a1);
  v2 = _InterlockedExchangeAdd(a1 + 10, 0) == 0;
  CAutoTypeLock<CSpinLock>::Unlock((__int64)v6);
  if ( v2 )
  {
    v3 = *((_QWORD *)a1 + 4);
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 40), 0) )
    {
      v4 = CImageCache::OnDirectoryChange(*(CImageCache **)(v3 + 48));
      ElValidateWin32_0(v4, v5, "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h", 135);
    }
  }
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(v6);
}

```

## disassembly

```asm
0x18000ace0  mov     [rsp+arg_0], rbx
0x18000ace5  push    rdi
0x18000ace6  sub     rsp, 30h
0x18000acea  mov     rdi, rcx
0x18000aced  mov     rdx, rcx
0x18000acf0  lea     rcx, [rsp+38h+var_18]
0x18000acf5  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x18000acfa  xor     eax, eax
0x18000acfc  lock xadd [rdi+28h], eax
0x18000ad01  xor     ebx, ebx
0x18000ad03  lea     rcx, [rsp+38h+var_18]
0x18000ad08  test    eax, eax
0x18000ad0a  setz    bl
0x18000ad0d  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000ad12  test    ebx, ebx
0x18000ad14  jz      short loc_18000AD42
0x18000ad16  mov     rcx, [rdi+20h]
0x18000ad1a  xor     eax, eax
0x18000ad1c  lock xadd [rcx+28h], eax
0x18000ad21  test    eax, eax
0x18000ad23  jnz     short loc_18000AD42
0x18000ad25  mov     rcx, [rcx+30h]; this
0x18000ad29  call    ?OnDirectoryChange@CImageCache@@QEAAKXZ; CImageCache::OnDirectoryChange(void)
0x18000ad2e  mov     ecx, eax
0x18000ad30  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x18000ad37  mov     r9d, 87h
0x18000ad3d  call    ElValidateWin32_0
0x18000ad42  lea     rcx, [rsp+38h+var_18]
0x18000ad47  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000ad4c  mov     rbx, [rsp+38h+arg_0]
0x18000ad51  add     rsp, 30h
0x18000ad55  pop     rdi
0x18000ad56  retn
```
