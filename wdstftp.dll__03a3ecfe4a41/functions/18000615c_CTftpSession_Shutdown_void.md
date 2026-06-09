# CTftpSession::Shutdown(void)

- ea: `0x18000615c`
- end: `0x180006311`
- name: `?Shutdown@CTftpSession@@QEAAKXZ`
- size: `437`
- prototype: `__int64 __fastcall(CTftpSession *this)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800036ac`
- `0x180004604`
- `0x180005efc`
- `0x180005f7c`

## callees

- `0x180002ccc`
- `0x180002f8c`
- `0x180002ff4`
- `0x18000615c`
- `0x180006318`
- `0x180009d20`
- `0x18000a960`
- `0x18000c168`
- `0x18000d66c`
- `0x18000d84c`
- `0x18003c514`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000620a`
- `KERNEL32!EnterCriticalSection` at `0x18000620a`
- `KERNEL32!LeaveCriticalSection` at `0x180006265`
- `KERNEL32!LeaveCriticalSection` at `0x180006265`
- `KERNEL32!DeleteCriticalSection` at `0x1800062b4`
- `KERNEL32!DeleteCriticalSection` at `0x1800062b4`

## pseudocode

```c
__int64 __fastcall CTftpSession::Shutdown(CTftpSession *this)
{
  int v2; // ebx
  const char *v3; // rdx
  int v4; // r9d
  struct CTftpFileReader *v5; // rbp
  unsigned int *v6; // r14
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  void *v8; // rsi
  char *v10; // [rsp+30h] [rbp-28h] BYREF
  int v11; // [rsp+38h] [rbp-20h]

  CTftpSession::KillClient(this, 0);
  v11 = 0;
  v10 = (char *)this + 2256;
  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(&v10);
  _InterlockedExchange((volatile __int32 *)this + 574, 1);
  v2 = v11;
  if ( v11 )
  {
    CAutoTypeLock<CSpinLock>::Unlock(&v10);
    v2 = v11;
  }
  CTimer<CTftpSession>::Delete((char *)this + 2256);
  if ( v2 )
  {
    CAutoTypeLock<CSpinLock>::Unlock(&v10);
    if ( v11 )
      WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h", 0x16Au, "m_uLockCount == 0", v4, 0);
  }
  ElValidateWin32(0, v3, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0xDCu);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = (struct CTftpFileReader *)*((_QWORD *)this + 305);
  v6 = (unsigned int *)*((_QWORD *)this + 306);
  v7 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 307);
  v8 = (void *)*((_QWORD *)this + 272);
  *((_QWORD *)this + 280) = 0;
  *((_QWORD *)this + 305) = 0;
  *((_QWORD *)this + 306) = 0;
  *((_QWORD *)this + 307) = 0;
  *((_DWORD *)this + 622) = 0;
  *((_QWORD *)this + 272) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v5 )
    CTftpReadFileManager::ReleaseFileReader((LPCRITICAL_SECTION)((char *)lpCriticalSection + 576), v5, v6);
  if ( v7 )
  {
    CTptReadFile::Shutdown(v7);
    CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(&v7[4].LockCount);
    CWIMFile::Shutdown((CWIMFile *)&v7[1].SpinCount);
    DeleteCriticalSection(v7);
    operator delete(v7);
  }
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(0x10000u, L"TftpSession[%s] - Shutdown", v8);
  if ( v8 )
    operator delete(v8);
  return 0;
}

```

## disassembly

```asm
0x18000615c  mov     [rsp+arg_0], rbx
0x180006161  mov     [rsp+arg_8], rbp
0x180006166  mov     [rsp+arg_10], rsi
0x18000616b  push    rdi
0x18000616c  push    r14
0x18000616e  push    r15
0x180006170  sub     rsp, 40h
0x180006174  xor     edx, edx; unsigned int
0x180006176  mov     rdi, rcx
0x180006179  call    ?KillClient@CTftpSession@@QEAAKK@Z; CTftpSession::KillClient(ulong)
0x18000617e  and     [rsp+58h+var_20], 0
0x180006183  lea     rsi, [rdi+8D0h]
0x18000618a  lea     rcx, [rsp+58h+var_28]
0x18000618f  mov     [rsp+58h+var_28], rsi
0x180006194  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x180006199  mov     eax, 1
0x18000619e  xchg    eax, [rsi+28h]
0x1800061a1  mov     ebx, [rsp+58h+var_20]
0x1800061a5  test    ebx, ebx
0x1800061a7  jz      short loc_1800061B7
0x1800061a9  lea     rcx, [rsp+58h+var_28]
0x1800061ae  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x1800061b3  mov     ebx, [rsp+58h+var_20]
0x1800061b7  mov     rcx, rsi
0x1800061ba  call    ?Delete@?$CTimer@VCTftpSession@@@@AEAAXXZ; CTimer<CTftpSession>::Delete(void)
0x1800061bf  test    ebx, ebx
0x1800061c1  jz      short loc_1800061F2
0x1800061c3  lea     rcx, [rsp+58h+var_28]
0x1800061c8  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x1800061cd  mov     ebx, [rsp+58h+var_20]
0x1800061d1  test    ebx, ebx
0x1800061d3  jz      short loc_1800061F2
0x1800061d5  and     [rsp+58h+var_38], 0
0x1800061da  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x1800061e1  mov     edx, 16Ah; unsigned int
0x1800061e6  lea     rcx, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x1800061ed  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800061f2  mov     r9d, 0DCh; unsigned int
0x1800061f8  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800061ff  xor     ecx, ecx; unsigned int
0x180006201  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006206  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000620a  call    cs:__imp_EnterCriticalSection
0x180006211  nop     dword ptr [rax+rax+00h]
0x180006216  mov     rbp, [rdi+988h]
0x18000621d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006221  mov     r14, [rdi+990h]
0x180006228  mov     rbx, [rdi+998h]
0x18000622f  mov     rsi, [rdi+880h]
0x180006236  and     qword ptr [rdi+8C0h], 0
0x18000623e  and     qword ptr [rdi+988h], 0
0x180006246  and     qword ptr [rdi+990h], 0
0x18000624e  and     qword ptr [rdi+998h], 0
0x180006256  and     dword ptr [rdi+9B8h], 0
0x18000625d  and     qword ptr [rdi+880h], 0
0x180006265  call    cs:__imp_LeaveCriticalSection
0x18000626c  nop     dword ptr [rax+rax+00h]
0x180006271  test    rbp, rbp
0x180006274  jz      short loc_18000628F
0x180006276  mov     rcx, cs:lpCriticalSection
0x18000627d  mov     r8, r14; void *
0x180006280  add     rcx, 240h; lpCriticalSection
0x180006287  mov     rdx, rbp; this
0x18000628a  call    ?ReleaseFileReader@CTftpReadFileManager@@QEAAXPEAVCTftpFileReader@@PEAX@Z; CTftpReadFileManager::ReleaseFileReader(CTftpFileReader *,void *)
0x18000628f  test    rbx, rbx
0x180006292  jz      short loc_1800062C8
0x180006294  mov     rcx, rbx; lpCriticalSection
0x180006297  call    ?Shutdown@CTptReadFile@@QEAAKXZ; CTptReadFile::Shutdown(void)
0x18000629c  lea     rcx, [rbx+0A8h]
0x1800062a3  call    ??1?$CChildCount@VCTptReadFile@@@@QEAA@XZ; CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(void)
0x1800062a8  lea     rcx, [rbx+48h]; this
0x1800062ac  call    ?Shutdown@CWIMFile@@QEAAKXZ; CWIMFile::Shutdown(void)
0x1800062b1  mov     rcx, rbx; lpCriticalSection
0x1800062b4  call    cs:__imp_DeleteCriticalSection
0x1800062bb  nop     dword ptr [rax+rax+00h]
0x1800062c0  mov     rcx, rbx; void *
0x1800062c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800062c8  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800062cf  test    rax, rax
0x1800062d2  jz      short loc_1800062E9
0x1800062d4  mov     r8, rsi
0x1800062d7  lea     rdx, aTftpsessionSSh; "TftpSession[%s] - Shutdown"
0x1800062de  mov     ecx, 10000h
0x1800062e3  call    cs:__guard_dispatch_icall_fptr
0x1800062e9  test    rsi, rsi
0x1800062ec  jz      short loc_1800062F6
0x1800062ee  mov     rcx, rsi; void *
0x1800062f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800062f6  mov     rbx, [rsp+58h+arg_0]
0x1800062fb  xor     eax, eax
0x1800062fd  mov     rbp, [rsp+58h+arg_8]
0x180006302  mov     rsi, [rsp+58h+arg_10]
0x180006307  add     rsp, 40h
0x18000630b  pop     r15
0x18000630d  pop     r14
0x18000630f  pop     rdi
0x180006310  retn
```
