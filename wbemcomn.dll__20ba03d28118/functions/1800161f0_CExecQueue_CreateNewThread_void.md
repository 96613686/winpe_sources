# CExecQueue::CreateNewThread(void)

- ea: `0x1800161f0`
- end: `0x18001632b`
- name: `?CreateNewThread@CExecQueue@@MEAAHXZ`
- size: `315`
- prototype: `__int64 __fastcall(CExecQueue *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180003a80`
- `0x18000a290`
- `0x18000b8b0`
- `0x1800161f0`
- `0x180016730`
- `0x180016760`
- `0x1800298f0`
- `0x180033230`
- `0x180033f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016301`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001631b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016301`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001631b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180016281`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180016281`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CExecQueue::CreateNewThread(CExecQueue *this)
{
  CExecQueue::CThreadRecord *v2; // rax
  unsigned int v3; // edx
  _QWORD *v4; // rbx
  HANDLE v5; // rax
  unsigned int v6; // edx
  unsigned int v8; // edx
  int v9; // [rsp+30h] [rbp-28h]
  DWORD ThreadId; // [rsp+68h] [rbp+10h] BYREF
  LPVOID lpParameter; // [rsp+70h] [rbp+18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp+20h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
  v2 = (CExecQueue::CThreadRecord *)CWin32DefaultArena::WbemMemAlloc(0x28u);
  lpParameter = v2;
  if ( v2 )
    v2 = CExecQueue::CThreadRecord::CThreadRecord(v2, this);
  std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&lpParameter, (__int64)v2);
  v4 = lpParameter;
  if ( !lpParameter || (unsigned int)CFlexArray::Add((CExecQueue *)((char *)this + 56), lpParameter) )
  {
    std::unique_ptr<CExecQueue::CThreadRecord>::~unique_ptr<CExecQueue::CThreadRecord>(
      (CExecQueue::CThreadRecord **)&lpParameter,
      v3);
    LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  else
  {
    ThreadId = 0;
    v5 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CExecQueue::_ThreadEntry, v4, 0, &ThreadId);
    v4[3] = v5;
    if ( v5 )
    {
      std::unique_ptr<CExecQueue::CThreadRecord>::release(&lpParameter);
      ++*((_DWORD *)this + 40);
      v9 = 1;
      std::unique_ptr<CExecQueue::CThreadRecord>::~unique_ptr<CExecQueue::CThreadRecord>(
        (CExecQueue::CThreadRecord **)&lpParameter,
        v8);
      LeaveCriticalSection(lpCriticalSection);
      return 1;
    }
    else
    {
      CFlexArray::RemoveAt((CExecQueue *)((char *)this + 56), *((_DWORD *)this + 14) - 1);
      std::unique_ptr<CExecQueue::CThreadRecord>::~unique_ptr<CExecQueue::CThreadRecord>(
        (CExecQueue::CThreadRecord **)&lpParameter,
        v6);
      LeaveCriticalSection(lpCriticalSection);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800161f0  push    rbx
0x1800161f2  push    rsi
0x1800161f3  push    rdi
0x1800161f4  sub     rsp, 40h
0x1800161f8  mov     rdi, rcx
0x1800161fb  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x1800161ff  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x180016204  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180016209  nop
0x18001620a  mov     ecx, 28h ; '('; unsigned __int64
0x18001620f  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180016214  mov     [rsp+58h+lpParameter], rax
0x180016219  test    rax, rax
0x18001621c  jz      short loc_18001622A
0x18001621e  mov     rdx, rdi; struct CExecQueue *
0x180016221  mov     rcx, rax; this
0x180016224  call    ??0CThreadRecord@CExecQueue@@QEAA@PEAV1@@Z; CExecQueue::CThreadRecord::CThreadRecord(CExecQueue *)
0x180016229  nop
0x18001622a  mov     rdx, rax
0x18001622d  lea     rcx, [rsp+58h+lpParameter]
0x180016232  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x180016237  nop
0x180016238  mov     rbx, [rsp+58h+lpParameter]
0x18001623d  test    rbx, rbx
0x180016240  jz      loc_18001630B
0x180016246  lea     rsi, [rdi+38h]
0x18001624a  mov     rdx, rbx; void *
0x18001624d  mov     rcx, rsi; this
0x180016250  call    ?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180016255  test    eax, eax
0x180016257  jnz     loc_1800162F1
0x18001625d  mov     [rsp+58h+ThreadId], eax
0x180016261  lea     rax, [rsp+58h+ThreadId]
0x180016266  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18001626b  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180016273  mov     r9, rbx; lpParameter
0x180016276  lea     r8, ?_ThreadEntry@CExecQueue@@KAKPEAX@Z; lpStartAddress
0x18001627d  xor     edx, edx; dwStackSize
0x18001627f  xor     ecx, ecx; lpThreadAttributes
0x180016281  call    cs:__imp_CreateThread
0x180016287  mov     [rbx+18h], rax
0x18001628b  test    rax, rax
0x18001628e  jnz     short loc_1800162BD
0x180016290  mov     edx, [rsi]
0x180016292  dec     edx; int
0x180016294  mov     rcx, rsi; this
0x180016297  call    ?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x18001629c  nop
0x18001629d  lea     rcx, [rsp+58h+lpParameter]
0x1800162a2  call    ??1?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAA@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::~unique_ptr<CExecQueue::CThreadRecord>(void)
0x1800162a7  nop
0x1800162a8  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800162ad  call    cs:__imp_LeaveCriticalSection
0x1800162b3  xor     eax, eax
0x1800162b5  add     rsp, 40h
0x1800162b9  pop     rdi
0x1800162ba  pop     rsi
0x1800162bb  pop     rbx
0x1800162bc  retn
0x1800162bd  lea     rcx, [rsp+58h+lpParameter]
0x1800162c2  call    ?release@?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAAPEAVCThreadRecord@CExecQueue@@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::release(void)
0x1800162c7  mov     ebx, 1
0x1800162cc  add     [rdi+0A0h], ebx
0x1800162d2  mov     [rsp+58h+var_28], ebx
0x1800162d6  lea     rcx, [rsp+58h+lpParameter]
0x1800162db  call    ??1?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAA@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::~unique_ptr<CExecQueue::CThreadRecord>(void)
0x1800162e0  nop
0x1800162e1  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800162e6  call    cs:__imp_LeaveCriticalSection
0x1800162ec  nop
0x1800162ed  mov     eax, ebx
0x1800162ef  jmp     short loc_1800162B5
0x1800162f1  lea     rcx, [rsp+58h+lpParameter]
0x1800162f6  call    ??1?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAA@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::~unique_ptr<CExecQueue::CThreadRecord>(void)
0x1800162fb  nop
0x1800162fc  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180016301  call    cs:__imp_LeaveCriticalSection
0x180016307  xor     eax, eax
0x180016309  jmp     short loc_1800162B5
0x18001630b  lea     rcx, [rsp+58h+lpParameter]
0x180016310  call    ??1?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAA@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::~unique_ptr<CExecQueue::CThreadRecord>(void)
0x180016315  nop
0x180016316  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x18001631b  call    cs:__imp_LeaveCriticalSection
0x180016321  xor     eax, eax
0x180016323  jmp     short loc_1800162B5
0x180016325  mov     ebx, [rsp+58h+var_28]
0x180016329  jmp     short loc_1800162ED
```
