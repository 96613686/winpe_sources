# CExecQueue::Enqueue(CExecRequest *,void * *)

- ea: `0x180003bb0`
- end: `0x180003dc9`
- name: `?Enqueue@CExecQueue@@UEAAJPEAVCExecRequest@@PEAPEAX@Z`
- size: `537`
- prototype: `__int64 __fastcall(CExecQueue *__hidden this, struct CExecRequest *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003bb0`
- `0x1800041d0`
- `0x180007e30`
- `0x180028b80`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003d86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003d86`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003c5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CExecQueue::Enqueue(CExecQueue *this, struct CExecRequest *a2, void **a3)
{
  CStaticCritSec *v6; // r14
  int i; // ebx
  _QWORD *v8; // rax
  __int64 v9; // rbp
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // ebx
  HANDLE EventW; // rax
  int v16; // [rsp+20h] [rbp-48h] BYREF
  char *v17; // [rsp+28h] [rbp-40h]

  if ( *((_DWORD *)this + 56) )
    return 2147749889LL;
  v6 = (CExecQueue *)((char *)this + 16);
  v17 = (char *)this + 16;
  v16 = 0;
  if ( *((_DWORD *)this + 56) )
    return 2147749889LL;
  if ( !*((_BYTE *)a2 + 28) )
    goto LABEL_31;
  if ( a3 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *a3 = EventW;
    if ( EventW )
    {
      *((_QWORD *)a2 + 1) = EventW;
      goto LABEL_5;
    }
LABEL_31:
    CCritSecWrapper::~CCritSecWrapper((CCritSecWrapper *)&v16);
    return 2147749894LL;
  }
LABEL_5:
  CStaticCritSec::Enter(v6);
  v16 = 1;
  for ( i = 0; i < *((_DWORD *)this + 14); ++i )
  {
    v8 = (_QWORD *)CFlexArray::operator[]((__int64)this + 56, i);
    v9 = *v8;
    if ( *(_DWORD *)(*v8 + 16LL)
      && (*(unsigned int (__fastcall **)(CExecQueue *, _QWORD, struct CExecRequest *))(*(_QWORD *)this + 48LL))(
           this,
           *v8,
           a2) )
    {
      *(_QWORD *)(v9 + 8) = a2;
      *(_DWORD *)(v9 + 16) = 0;
      SetEvent(*(HANDLE *)(v9 + 32));
      --*((_DWORD *)this + 41);
      LeaveCriticalSection((LPCRITICAL_SECTION)v6);
      v16 = 0;
      return 0;
    }
  }
  if ( *((_DWORD *)this + 42) >= *((_DWORD *)this + 47) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    v16 = 0;
    return 2147749889LL;
  }
  (*(void (__fastcall **)(CExecQueue *, struct CExecRequest *))(*(_QWORD *)this + 144LL))(this, a2);
  v11 = *((_QWORD *)this + 18);
  v12 = 0;
  if ( v11 )
  {
    while ( *(_DWORD *)(v11 + 24) <= *((_DWORD *)a2 + 6) )
    {
      v12 = v11;
      v11 = *(_QWORD *)(v11 + 16);
      if ( !v11 )
        goto LABEL_17;
    }
    *((_QWORD *)a2 + 2) = v11;
  }
  else
  {
LABEL_17:
    *((_QWORD *)this + 19) = a2;
  }
  if ( v12 )
    *(_QWORD *)(v12 + 16) = a2;
  else
    *((_QWORD *)this + 18) = a2;
  ++*((_DWORD *)this + 42);
  while ( 1 )
  {
    v13 = *(_QWORD *)this;
    if ( !v11 )
      break;
    (*(void (__fastcall **)(CExecQueue *, __int64))(v13 + 152))(this, v11);
    v11 = *(_QWORD *)(v11 + 16);
  }
  if ( (*(unsigned int (__fastcall **)(CExecQueue *, struct CExecRequest *))(v13 + 56))(this, a2) )
    (*(void (__fastcall **)(CExecQueue *))(*(_QWORD *)this + 32LL))(this);
  v14 = *((_DWORD *)this + 42);
  LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  v16 = 0;
  (*(void (__fastcall **)(CExecQueue *, _QWORD))(*(_QWORD *)this + 128LL))(this, v14);
  return 0;
}

```

## disassembly

```asm
0x180003bb0  push    rbx
0x180003bb2  push    rbp
0x180003bb3  push    rsi
0x180003bb4  push    rdi
0x180003bb5  push    r14
0x180003bb7  push    r15
0x180003bb9  sub     rsp, 38h
0x180003bbd  mov     rbx, r8
0x180003bc0  mov     rsi, rdx
0x180003bc3  mov     rdi, rcx
0x180003bc6  cmp     dword ptr [rcx+0E0h], 0
0x180003bcd  jnz     loc_180003D72
0x180003bd3  lea     r14, [rcx+10h]
0x180003bd7  mov     [rsp+68h+var_40], r14
0x180003bdc  mov     [rsp+68h+var_48], 0
0x180003be4  cmp     dword ptr [rcx+0E0h], 0
0x180003beb  jnz     loc_180003C9C
0x180003bf1  cmp     byte ptr [rdx+1Ch], 0
0x180003bf5  jz      loc_180003DB5
0x180003bfb  test    rbx, rbx
0x180003bfe  jnz     loc_180003D7C
0x180003c04  mov     rcx, r14; this
0x180003c07  call    ?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180003c0c  mov     [rsp+68h+var_48], 1
0x180003c14  xor     ebx, ebx
0x180003c16  cmp     ebx, [rdi+38h]
0x180003c19  jge     loc_180003CA3
0x180003c1f  mov     edx, ebx
0x180003c21  lea     rcx, [rdi+38h]
0x180003c25  call    ??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180003c2a  mov     rbp, [rax]
0x180003c2d  cmp     dword ptr [rbp+10h], 0
0x180003c31  jnz     short loc_180003C37
0x180003c33  inc     ebx
0x180003c35  jmp     short loc_180003C16
0x180003c37  mov     rax, [rdi]
0x180003c3a  mov     r8, rsi
0x180003c3d  mov     rdx, rbp
0x180003c40  mov     rcx, rdi
0x180003c43  mov     rax, [rax+30h]
0x180003c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4c  test    eax, eax
0x180003c4e  jz      short loc_180003C33
0x180003c50  mov     [rbp+8], rsi
0x180003c54  mov     dword ptr [rbp+10h], 0
0x180003c5b  mov     rcx, [rbp+20h]; hEvent
0x180003c5f  call    cs:__imp_SetEvent
0x180003c65  dec     dword ptr [rdi+0A4h]
0x180003c6b  mov     rcx, r14; lpCriticalSection
0x180003c6e  call    cs:__imp_LeaveCriticalSection
0x180003c74  mov     [rsp+68h+var_48], 0
0x180003c7c  xor     eax, eax
0x180003c7e  add     rsp, 38h
0x180003c82  pop     r15
0x180003c84  pop     r14
0x180003c86  pop     rdi
0x180003c87  pop     rsi
0x180003c88  pop     rbp
0x180003c89  pop     rbx
0x180003c8a  retn
0x180003c8b  mov     rcx, r14; lpCriticalSection
0x180003c8e  call    cs:__imp_LeaveCriticalSection
0x180003c94  mov     [rsp+68h+var_48], 0
0x180003c9c  mov     eax, 80041001h
0x180003ca1  jmp     short loc_180003C7E
0x180003ca3  mov     eax, [rdi+0BCh]
0x180003ca9  cmp     [rdi+0A8h], eax
0x180003caf  jge     short loc_180003C8B
0x180003cb1  mov     rax, [rdi]
0x180003cb4  mov     rdx, rsi
0x180003cb7  mov     rcx, rdi
0x180003cba  mov     rax, [rax+90h]
0x180003cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc6  mov     rbx, [rdi+90h]
0x180003ccd  xor     eax, eax
0x180003ccf  test    rbx, rbx
0x180003cd2  jz      short loc_180003CEC
0x180003cd4  mov     ecx, [rsi+18h]
0x180003cd7  cmp     [rbx+18h], ecx
0x180003cda  jg      loc_180003D6C
0x180003ce0  mov     rax, rbx
0x180003ce3  mov     rbx, [rbx+10h]
0x180003ce7  test    rbx, rbx
0x180003cea  jnz     short loc_180003CD7
0x180003cec  mov     [rdi+98h], rsi
0x180003cf3  test    rax, rax
0x180003cf6  jnz     short loc_180003D66
0x180003cf8  mov     [rdi+90h], rsi
0x180003cff  inc     dword ptr [rdi+0A8h]
0x180003d05  mov     rax, [rdi]
0x180003d08  mov     rcx, rdi
0x180003d0b  test    rbx, rbx
0x180003d0e  jnz     loc_180003D9D
0x180003d14  mov     rdx, rsi
0x180003d17  mov     rax, [rax+38h]
0x180003d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d20  test    eax, eax
0x180003d22  jz      short loc_180003D33
0x180003d24  mov     rax, [rdi]
0x180003d27  mov     rcx, rdi
0x180003d2a  mov     rax, [rax+20h]
0x180003d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d33  mov     ebx, [rdi+0A8h]
0x180003d39  mov     rcx, r14; lpCriticalSection
0x180003d3c  call    cs:__imp_LeaveCriticalSection
0x180003d42  mov     [rsp+68h+var_48], 0
0x180003d4a  mov     rax, [rdi]
0x180003d4d  mov     edx, ebx
0x180003d4f  mov     rcx, rdi
0x180003d52  mov     rax, [rax+80h]
0x180003d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5e  nop
0x180003d5f  xor     eax, eax
0x180003d61  jmp     loc_180003C7E
0x180003d66  mov     [rax+10h], rsi
0x180003d6a  jmp     short loc_180003CFF
0x180003d6c  mov     [rsi+10h], rbx
0x180003d70  jmp     short loc_180003CF3
0x180003d72  mov     eax, 80041001h
0x180003d77  jmp     loc_180003C7E
0x180003d7c  xor     r9d, r9d; lpName
0x180003d7f  xor     r8d, r8d; bInitialState
0x180003d82  xor     edx, edx; bManualReset
0x180003d84  xor     ecx, ecx; lpEventAttributes
0x180003d86  call    cs:__imp_CreateEventW
0x180003d8c  mov     [rbx], rax
0x180003d8f  test    rax, rax
0x180003d92  jz      short loc_180003DB5
0x180003d94  mov     [rsi+8], rax
0x180003d98  jmp     loc_180003C04
0x180003d9d  mov     rdx, rbx
0x180003da0  mov     rax, [rax+98h]
0x180003da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dac  mov     rbx, [rbx+10h]
0x180003db0  jmp     loc_180003D05
0x180003db5  lea     rcx, [rsp+68h+var_48]; this
0x180003dba  call    ??1CCritSecWrapper@@QEAA@XZ; CCritSecWrapper::~CCritSecWrapper(void)
0x180003dbf  mov     eax, 80041006h
0x180003dc4  jmp     loc_180003C7E
```
