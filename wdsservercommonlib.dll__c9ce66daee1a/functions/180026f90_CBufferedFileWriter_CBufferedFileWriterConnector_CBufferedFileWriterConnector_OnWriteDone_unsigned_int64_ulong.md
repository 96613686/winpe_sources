# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::Write(unsigned __int64,void *,ulong)

- ea: `0x180026f90`
- end: `0x180027112`
- name: `?Write@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAK_KPEAXK@Z`
- size: `386`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027260`

## callees

- `0x18000179c`
- `0x1800017a8`
- `0x180026600`
- `0x180026f90`
- `0x180027390`
- `0x18002e468`
- `0x18002f3ae`
- `0x180030010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180026fbb`
- `KERNEL32!EnterCriticalSection` at `0x180026fbb`
- `KERNEL32!LeaveCriticalSection` at `0x1800270cd`
- `KERNEL32!LeaveCriticalSection` at `0x1800270cd`

## string_xrefs

- `0x180027085`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x1800270b3`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

## pseudocode

```c
__int64 __fastcall CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::Write(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2,
        const void *a3,
        unsigned int a4)
{
  size_t v4; // rbp
  __int64 v8; // rsi
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  void *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx

  v4 = a4;
  LODWORD(v8) = 0;
  EnterCriticalSection(lpCriticalSection);
  v9 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( v9 )
  {
    v9[3] = 0;
    v9[4] = 0;
    *v9 = 0;
    *((_DWORD *)v9 + 2) = 0;
    v9[2] = 0;
    lpCriticalSection[1].LockSemaphore = (char *)lpCriticalSection[1].LockSemaphore + v4;
    *v9 = a2;
    *((_DWORD *)v9 + 2) = v4;
    v11 = operator new[]((unsigned int)v4, (const struct std::nothrow_t *)&std::nothrow);
    v10[2] = v11;
    if ( v11 )
    {
      memmove_0(v11, a3, v4);
      if ( lpCriticalSection[2].OwningThread )
      {
        v10[3] = 0;
        v10[4] = lpCriticalSection[2].LockSemaphore;
        *((_QWORD *)lpCriticalSection[2].LockSemaphore + 3) = v10;
        lpCriticalSection[2].LockSemaphore = v10;
      }
      else
      {
        lpCriticalSection[2].LockSemaphore = v10;
        lpCriticalSection[2].OwningThread = v10;
        v10[3] = 0;
        v10[4] = 0;
      }
      ++HIDWORD(lpCriticalSection[2].SpinCount);
      lpCriticalSection[2].LockCount += v4;
      if ( lpCriticalSection[2].LockCount <= 0x8000000u
        || (v8 = (unsigned int)CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::MergeAndWriteBuffer(
                                 (__int64)lpCriticalSection,
                                 0x733331Au),
            !(unsigned int)ElValidateWin32_14(
                             v8,
                             v12,
                             "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
                             667)) )
      {
        if ( lpCriticalSection[1].LockSemaphore >= lpCriticalSection[1].OwningThread )
        {
          v8 = (unsigned int)CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::MergeAndWriteBuffer(
                               (__int64)lpCriticalSection,
                               0);
          ElValidateWin32_14(v8, v13, "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h", 676);
        }
      }
    }
    else
    {
      LODWORD(v8) = 8;
      operator delete(v10);
    }
  }
  else
  {
    LODWORD(v8) = 8;
  }
  LeaveCriticalSection(lpCriticalSection);
  ((void (__fastcall *)(_QWORD, _QWORD, const void *, struct _RTL_CRITICAL_SECTION *))lpCriticalSection[1].DebugInfo->Type)(
    0,
    (unsigned int)v4,
    a3,
    lpCriticalSection[1].DebugInfo->CriticalSection);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180026f90  mov     rax, rsp
0x180026f93  mov     [rax+8], rbx
0x180026f97  mov     [rax+10h], rbp
0x180026f9b  mov     [rax+18h], rsi
0x180026f9f  mov     [rax+20h], rdi
0x180026fa3  push    r12
0x180026fa5  push    r14
0x180026fa7  push    r15
0x180026fa9  sub     rsp, 30h
0x180026fad  mov     ebp, r9d
0x180026fb0  mov     r12, r8
0x180026fb3  mov     r15, rdx
0x180026fb6  mov     rbx, rcx
0x180026fb9  xor     esi, esi
0x180026fbb  call    cs:__imp_EnterCriticalSection
0x180026fc2  nop     dword ptr [rax+rax+00h]
0x180026fc7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026fce  lea     ecx, [rsi+28h]; unsigned __int64
0x180026fd1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026fd6  mov     rdi, rax
0x180026fd9  test    rax, rax
0x180026fdc  jz      loc_1800270C5
0x180026fe2  and     [rax+18h], rsi
0x180026fe6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026fed  and     [rax+20h], rsi
0x180026ff1  mov     ecx, ebp; unsigned __int64
0x180026ff3  and     [rax], rsi
0x180026ff6  and     [rax+8], esi
0x180026ff9  and     [rax+10h], rsi
0x180026ffd  add     [rbx+40h], rbp
0x180027001  mov     [rax], r15
0x180027004  mov     [rax+8], ebp
0x180027007  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002700c  mov     [rdi+10h], rax
0x180027010  mov     rcx, rax; void *
0x180027013  test    rax, rax
0x180027016  jnz     short loc_180027028
0x180027018  mov     rcx, rdi; lpMem
0x18002701b  lea     esi, [rax+8]
0x18002701e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027023  jmp     loc_1800270CA
0x180027028  mov     r8, rbp; Size
0x18002702b  mov     rdx, r12; Src
0x18002702e  call    memmove_0
0x180027033  cmp     [rbx+60h], rsi
0x180027037  jnz     short loc_18002704B
0x180027039  mov     [rbx+68h], rdi
0x18002703d  mov     [rbx+60h], rdi
0x180027041  and     [rdi+18h], rsi
0x180027045  and     [rdi+20h], rsi
0x180027049  jmp     short loc_180027063
0x18002704b  and     [rdi+18h], rsi
0x18002704f  mov     rax, [rbx+68h]
0x180027053  mov     [rdi+20h], rax
0x180027057  mov     rax, [rbx+68h]
0x18002705b  mov     [rax+18h], rdi
0x18002705f  mov     [rbx+68h], rdi
0x180027063  inc     dword ptr [rbx+74h]
0x180027066  add     [rbx+58h], ebp
0x180027069  cmp     dword ptr [rbx+58h], 8000000h
0x180027070  jbe     short loc_180027099
0x180027072  mov     edx, 733331Ah
0x180027077  mov     rcx, rbx
0x18002707a  call    ?MergeAndWriteBuffer@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKK@Z; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::MergeAndWriteBuffer(ulong)
0x18002707f  mov     r9d, 29Bh
0x180027085  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x18002708c  mov     ecx, eax
0x18002708e  mov     esi, eax
0x180027090  call    ElValidateWin32_14
0x180027095  test    eax, eax
0x180027097  jnz     short loc_1800270CA
0x180027099  mov     rcx, [rbx+38h]
0x18002709d  cmp     [rbx+40h], rcx
0x1800270a1  jb      short loc_1800270CA
0x1800270a3  xor     edx, edx
0x1800270a5  mov     rcx, rbx
0x1800270a8  call    ?MergeAndWriteBuffer@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKK@Z; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::MergeAndWriteBuffer(ulong)
0x1800270ad  mov     r9d, 2A4h
0x1800270b3  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800270ba  mov     ecx, eax
0x1800270bc  mov     esi, eax
0x1800270be  call    ElValidateWin32_14
0x1800270c3  jmp     short loc_1800270CA
0x1800270c5  mov     esi, 8
0x1800270ca  mov     rcx, rbx; lpCriticalSection
0x1800270cd  call    cs:__imp_LeaveCriticalSection
0x1800270d4  nop     dword ptr [rax+rax+00h]
0x1800270d9  mov     r9, [rbx+28h]
0x1800270dd  mov     r8, r12
0x1800270e0  mov     edx, ebp
0x1800270e2  xor     ecx, ecx
0x1800270e4  mov     rax, [r9]
0x1800270e7  mov     r9, [r9+8]
0x1800270eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270f0  mov     rbx, [rsp+48h+arg_0]
0x1800270f5  mov     eax, esi
0x1800270f7  mov     rsi, [rsp+48h+arg_10]
0x1800270fc  mov     rbp, [rsp+48h+arg_8]
0x180027101  mov     rdi, [rsp+48h+arg_18]
0x180027106  add     rsp, 30h
0x18002710a  pop     r15
0x18002710c  pop     r14
0x18002710e  pop     r12
0x180027110  retn
```
