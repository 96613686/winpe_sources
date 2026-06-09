# CExecQueue::EnqueueWithoutSleep(CExecRequest *,void * *)

- ea: `0x1800335d0`
- end: `0x1800337cb`
- name: `?EnqueueWithoutSleep@CExecQueue@@QEAAJPEAVCExecRequest@@PEAPEAX@Z`
- size: `507`
- prototype: `__int64 __fastcall(CExecQueue *__hidden this, struct CExecRequest *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800041d0`
- `0x180007e30`
- `0x180028b80`
- `0x1800335d0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033630`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033630`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003369f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003369f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800336ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800336d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800336ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800336d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033793`

## pseudocode

```c
__int64 __fastcall CExecQueue::EnqueueWithoutSleep(CExecQueue *this, struct CExecRequest *a2, void **a3)
{
  CStaticCritSec *v7; // rbp
  HANDLE EventW; // rax
  int i; // edi
  _QWORD *v10; // rax
  __int64 v11; // r14
  unsigned int v12; // ebx
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // [rsp+20h] [rbp-48h] BYREF
  char *v17; // [rsp+28h] [rbp-40h]

  if ( *((_DWORD *)this + 56) )
    return 2147749889LL;
  v7 = (CExecQueue *)((char *)this + 16);
  v17 = (char *)this + 16;
  v16 = 0;
  if ( *((_DWORD *)this + 56) )
    goto LABEL_16;
  if ( !*((_BYTE *)a2 + 28) )
    goto LABEL_32;
  if ( !a3 )
    goto LABEL_8;
  EventW = CreateEventW(0, 0, 0, 0);
  *a3 = EventW;
  if ( !EventW )
  {
LABEL_32:
    CCritSecWrapper::~CCritSecWrapper((CCritSecWrapper *)&v16);
    return 2147749894LL;
  }
  *((_QWORD *)a2 + 1) = EventW;
LABEL_8:
  CStaticCritSec::Enter(v7);
  v16 = 1;
  for ( i = 0; i < *((_DWORD *)this + 14); ++i )
  {
    v10 = (_QWORD *)CFlexArray::operator[]((__int64)this + 56, i);
    v11 = *v10;
    if ( *(_DWORD *)(*v10 + 16LL)
      && (*(unsigned int (__fastcall **)(CExecQueue *, _QWORD, struct CExecRequest *))(*(_QWORD *)this + 48LL))(
           this,
           *v10,
           a2) )
    {
      *(_QWORD *)(v11 + 8) = a2;
      *(_DWORD *)(v11 + 16) = 0;
      SetEvent(*(HANDLE *)(v11 + 32));
      --*((_DWORD *)this + 41);
      LeaveCriticalSection((LPCRITICAL_SECTION)v7);
      v16 = 0;
      v12 = 0;
      goto LABEL_17;
    }
  }
  if ( *((_DWORD *)this + 42) < *((_DWORD *)this + 47) )
  {
    (*(void (__fastcall **)(CExecQueue *, struct CExecRequest *))(*(_QWORD *)this + 144LL))(this, a2);
    v13 = *((_QWORD *)this + 18);
    v14 = 0;
    if ( v13 )
    {
      while ( *(_DWORD *)(v13 + 24) <= *((_DWORD *)a2 + 6) )
      {
        v14 = v13;
        v13 = *(_QWORD *)(v13 + 16);
        if ( !v13 )
          goto LABEL_21;
      }
      *((_QWORD *)a2 + 2) = v13;
    }
    else
    {
LABEL_21:
      *((_QWORD *)this + 19) = a2;
    }
    if ( v14 )
      *(_QWORD *)(v14 + 16) = a2;
    else
      *((_QWORD *)this + 18) = a2;
    ++*((_DWORD *)this + 42);
    while ( 1 )
    {
      v15 = *(_QWORD *)this;
      if ( !v13 )
        break;
      (*(void (__fastcall **)(CExecQueue *, __int64))(v15 + 152))(this, v13);
      v13 = *(_QWORD *)(v13 + 16);
    }
    if ( (*(unsigned int (__fastcall **)(CExecQueue *, struct CExecRequest *))(v15 + 56))(this, a2) )
      (*(void (__fastcall **)(CExecQueue *))(*(_QWORD *)this + 32LL))(this);
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
    v16 = 0;
    CCritSecWrapper::~CCritSecWrapper((CCritSecWrapper *)&v16);
    return 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  v16 = 0;
LABEL_16:
  v12 = -2147217407;
LABEL_17:
  CCritSecWrapper::~CCritSecWrapper((CCritSecWrapper *)&v16);
  return v12;
}

```

## disassembly

```asm
0x1800335d0  push    rbx
0x1800335d2  push    rbp
0x1800335d3  push    rsi
0x1800335d4  push    rdi
0x1800335d5  push    r14
0x1800335d7  push    r15
0x1800335d9  sub     rsp, 38h
0x1800335dd  mov     rdi, r8
0x1800335e0  mov     rsi, rdx
0x1800335e3  mov     rbx, rcx
0x1800335e6  cmp     dword ptr [rcx+0E0h], 0
0x1800335ed  jz      short loc_1800335F9
0x1800335ef  mov     eax, 80041001h
0x1800335f4  jmp     loc_1800337BE
0x1800335f9  lea     rbp, [rcx+10h]
0x1800335fd  mov     [rsp+68h+var_40], rbp
0x180033602  mov     [rsp+68h+var_48], 0
0x18003360a  cmp     dword ptr [rcx+0E0h], 0
0x180033611  jnz     loc_1800336DF
0x180033617  cmp     byte ptr [rdx+1Ch], 0
0x18003361b  jz      loc_1800337AF
0x180033621  test    rdi, rdi
0x180033624  jz      short loc_180033646
0x180033626  xor     r9d, r9d; lpName
0x180033629  xor     r8d, r8d; bInitialState
0x18003362c  xor     edx, edx; bManualReset
0x18003362e  xor     ecx, ecx; lpEventAttributes
0x180033630  call    cs:__imp_CreateEventW
0x180033636  mov     [rdi], rax
0x180033639  test    rax, rax
0x18003363c  jz      loc_1800337AF
0x180033642  mov     [rsi+8], rax
0x180033646  mov     rcx, rbp; this
0x180033649  call    ?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x18003364e  mov     [rsp+68h+var_48], 1
0x180033656  xor     edi, edi
0x180033658  cmp     edi, [rbx+38h]
0x18003365b  jge     short loc_1800336C0
0x18003365d  mov     edx, edi
0x18003365f  lea     rcx, [rbx+38h]
0x180033663  call    ??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180033668  mov     r14, [rax]
0x18003366b  cmp     dword ptr [r14+10h], 0
0x180033670  jz      short loc_18003368B
0x180033672  mov     rax, [rbx]
0x180033675  mov     r8, rsi
0x180033678  mov     rdx, r14
0x18003367b  mov     rcx, rbx
0x18003367e  mov     rax, [rax+30h]
0x180033682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033687  test    eax, eax
0x180033689  jnz     short loc_18003368F
0x18003368b  inc     edi
0x18003368d  jmp     short loc_180033658
0x18003368f  mov     [r14+8], rsi
0x180033693  mov     dword ptr [r14+10h], 0
0x18003369b  mov     rcx, [r14+20h]; hEvent
0x18003369f  call    cs:__imp_SetEvent
0x1800336a5  dec     dword ptr [rbx+0A4h]
0x1800336ab  mov     rcx, rbp; lpCriticalSection
0x1800336ae  call    cs:__imp_LeaveCriticalSection
0x1800336b4  mov     [rsp+68h+var_48], 0
0x1800336bc  xor     ebx, ebx
0x1800336be  jmp     short loc_1800336E4
0x1800336c0  mov     eax, [rbx+0BCh]
0x1800336c6  cmp     [rbx+0A8h], eax
0x1800336cc  jl      short loc_1800336F5
0x1800336ce  mov     rcx, rbp; lpCriticalSection
0x1800336d1  call    cs:__imp_LeaveCriticalSection
0x1800336d7  mov     [rsp+68h+var_48], 0
0x1800336df  mov     ebx, 80041001h
0x1800336e4  lea     rcx, [rsp+68h+var_48]; this
0x1800336e9  call    ??1CCritSecWrapper@@QEAA@XZ; CCritSecWrapper::~CCritSecWrapper(void)
0x1800336ee  mov     eax, ebx
0x1800336f0  jmp     loc_1800337BE
0x1800336f5  mov     rax, [rbx]
0x1800336f8  mov     rdx, rsi
0x1800336fb  mov     rcx, rbx
0x1800336fe  mov     rax, [rax+90h]
0x180033705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003370a  mov     rdi, [rbx+90h]
0x180033711  xor     eax, eax
0x180033713  test    rdi, rdi
0x180033716  jz      short loc_18003372C
0x180033718  mov     ecx, [rsi+18h]
0x18003371b  cmp     [rdi+18h], ecx
0x18003371e  jg      short loc_18003373E
0x180033720  mov     rax, rdi
0x180033723  mov     rdi, [rdi+10h]
0x180033727  test    rdi, rdi
0x18003372a  jnz     short loc_18003371B
0x18003372c  mov     [rbx+98h], rsi
0x180033733  test    rax, rax
0x180033736  jz      short loc_180033744
0x180033738  mov     [rax+10h], rsi
0x18003373c  jmp     short loc_18003374B
0x18003373e  mov     [rsi+10h], rdi
0x180033742  jmp     short loc_180033733
0x180033744  mov     [rbx+90h], rsi
0x18003374b  inc     dword ptr [rbx+0A8h]
0x180033751  jmp     short loc_180033766
0x180033753  mov     rdx, rdi
0x180033756  mov     rax, [rax+98h]
0x18003375d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033762  mov     rdi, [rdi+10h]
0x180033766  mov     rax, [rbx]
0x180033769  mov     rcx, rbx
0x18003376c  test    rdi, rdi
0x18003376f  jnz     short loc_180033753
0x180033771  mov     rdx, rsi
0x180033774  mov     rax, [rax+38h]
0x180033778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003377d  test    eax, eax
0x18003377f  jz      short loc_180033790
0x180033781  mov     rax, [rbx]
0x180033784  mov     rcx, rbx
0x180033787  mov     rax, [rax+20h]
0x18003378b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033790  mov     rcx, rbp; lpCriticalSection
0x180033793  call    cs:__imp_LeaveCriticalSection
0x180033799  mov     [rsp+68h+var_48], 0
0x1800337a1  lea     rcx, [rsp+68h+var_48]; this
0x1800337a6  call    ??1CCritSecWrapper@@QEAA@XZ; CCritSecWrapper::~CCritSecWrapper(void)
0x1800337ab  xor     eax, eax
0x1800337ad  jmp     short loc_1800337BE
0x1800337af  lea     rcx, [rsp+68h+var_48]; this
0x1800337b4  call    ??1CCritSecWrapper@@QEAA@XZ; CCritSecWrapper::~CCritSecWrapper(void)
0x1800337b9  mov     eax, 80041006h
0x1800337be  add     rsp, 38h
0x1800337c2  pop     r15
0x1800337c4  pop     r14
0x1800337c6  pop     rdi
0x1800337c7  pop     rsi
0x1800337c8  pop     rbp
0x1800337c9  pop     rbx
0x1800337ca  retn
```
