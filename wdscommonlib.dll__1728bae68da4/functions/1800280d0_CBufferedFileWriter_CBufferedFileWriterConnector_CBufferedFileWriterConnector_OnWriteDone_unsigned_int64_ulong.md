# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::Write(unsigned __int64,void *,ulong)

- ea: `0x1800280d0`
- end: `0x180028259`
- name: `?Write@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAK_KPEAXK@Z`
- size: `393`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800283b0`

## callees

- `0x18000214c`
- `0x180002158`
- `0x1800024b2`
- `0x180027720`
- `0x1800280d0`
- `0x1800284e0`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002815e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002815e`
- `KERNEL32!EnterCriticalSection` at `0x1800280fb`
- `KERNEL32!EnterCriticalSection` at `0x1800280fb`
- `KERNEL32!LeaveCriticalSection` at `0x180028214`
- `KERNEL32!LeaveCriticalSection` at `0x180028214`

## string_xrefs

- `0x1800281cc`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x1800281fa`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

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
0x1800280d0  mov     rax, rsp
0x1800280d3  mov     [rax+8], rbx
0x1800280d7  mov     [rax+10h], rbp
0x1800280db  mov     [rax+18h], rsi
0x1800280df  mov     [rax+20h], rdi
0x1800280e3  push    r12
0x1800280e5  push    r14
0x1800280e7  push    r15
0x1800280e9  sub     rsp, 30h
0x1800280ed  mov     ebp, r9d
0x1800280f0  mov     r12, r8
0x1800280f3  mov     r15, rdx
0x1800280f6  mov     rbx, rcx
0x1800280f9  xor     esi, esi
0x1800280fb  call    cs:__imp_EnterCriticalSection
0x180028102  nop     dword ptr [rax+rax+00h]
0x180028107  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002810e  lea     ecx, [rsi+28h]; unsigned __int64
0x180028111  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028116  mov     rdi, rax
0x180028119  test    rax, rax
0x18002811c  jz      loc_18002820C
0x180028122  and     [rax+18h], rsi
0x180028126  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002812d  and     [rax+20h], rsi
0x180028131  mov     ecx, ebp; unsigned __int64
0x180028133  and     [rax], rsi
0x180028136  and     [rax+8], esi
0x180028139  and     [rax+10h], rsi
0x18002813d  add     [rbx+40h], rbp
0x180028141  mov     [rax], r15
0x180028144  mov     [rax+8], ebp
0x180028147  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002814c  mov     [rdi+10h], rax
0x180028150  mov     rcx, rax; void *
0x180028153  test    rax, rax
0x180028156  jnz     short loc_18002816F
0x180028158  mov     rcx, rdi
0x18002815b  lea     esi, [rax+8]
0x18002815e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028165  nop     dword ptr [rax+rax+00h]
0x18002816a  jmp     loc_180028211
0x18002816f  mov     r8, rbp; Size
0x180028172  mov     rdx, r12; Src
0x180028175  call    memmove_0
0x18002817a  cmp     [rbx+60h], rsi
0x18002817e  jnz     short loc_180028192
0x180028180  mov     [rbx+68h], rdi
0x180028184  mov     [rbx+60h], rdi
0x180028188  and     [rdi+18h], rsi
0x18002818c  and     [rdi+20h], rsi
0x180028190  jmp     short loc_1800281AA
0x180028192  and     [rdi+18h], rsi
0x180028196  mov     rax, [rbx+68h]
0x18002819a  mov     [rdi+20h], rax
0x18002819e  mov     rax, [rbx+68h]
0x1800281a2  mov     [rax+18h], rdi
0x1800281a6  mov     [rbx+68h], rdi
0x1800281aa  inc     dword ptr [rbx+74h]
0x1800281ad  add     [rbx+58h], ebp
0x1800281b0  cmp     dword ptr [rbx+58h], 8000000h
0x1800281b7  jbe     short loc_1800281E0
0x1800281b9  mov     edx, 733331Ah
0x1800281be  mov     rcx, rbx
0x1800281c1  call    ?MergeAndWriteBuffer@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKK@Z; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::MergeAndWriteBuffer(ulong)
0x1800281c6  mov     r9d, 29Bh
0x1800281cc  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800281d3  mov     ecx, eax
0x1800281d5  mov     esi, eax
0x1800281d7  call    ElValidateWin32_14
0x1800281dc  test    eax, eax
0x1800281de  jnz     short loc_180028211
0x1800281e0  mov     rcx, [rbx+38h]
0x1800281e4  cmp     [rbx+40h], rcx
0x1800281e8  jb      short loc_180028211
0x1800281ea  xor     edx, edx
0x1800281ec  mov     rcx, rbx
0x1800281ef  call    ?MergeAndWriteBuffer@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@AEAAKK@Z; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::MergeAndWriteBuffer(ulong)
0x1800281f4  mov     r9d, 2A4h
0x1800281fa  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180028201  mov     ecx, eax
0x180028203  mov     esi, eax
0x180028205  call    ElValidateWin32_14
0x18002820a  jmp     short loc_180028211
0x18002820c  mov     esi, 8
0x180028211  mov     rcx, rbx; lpCriticalSection
0x180028214  call    cs:__imp_LeaveCriticalSection
0x18002821b  nop     dword ptr [rax+rax+00h]
0x180028220  mov     r9, [rbx+28h]
0x180028224  mov     r8, r12
0x180028227  mov     edx, ebp
0x180028229  xor     ecx, ecx
0x18002822b  mov     rax, [r9]
0x18002822e  mov     r9, [r9+8]
0x180028232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028237  mov     rbx, [rsp+48h+arg_0]
0x18002823c  mov     eax, esi
0x18002823e  mov     rsi, [rsp+48h+arg_10]
0x180028243  mov     rbp, [rsp+48h+arg_8]
0x180028248  mov     rdi, [rsp+48h+arg_18]
0x18002824d  add     rsp, 30h
0x180028251  pop     r15
0x180028253  pop     r14
0x180028255  pop     r12
0x180028257  retn
```
