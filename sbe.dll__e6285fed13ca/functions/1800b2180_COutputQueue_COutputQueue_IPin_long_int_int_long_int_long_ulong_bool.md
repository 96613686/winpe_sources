# COutputQueue::COutputQueue(IPin *,long *,int,int,long,int,long,ulong,bool)

- ea: `0x1800b2180`
- end: `0x1800b22ef`
- name: `??0COutputQueue@@QEAA@PEAUIPin@@PEAJHHJHJK_N@Z`
- size: `367`
- prototype: `COutputQueue *__usercall@<rax>(COutputQueue *__hidden this@<rcx>, struct IPin *@<rdx>, int *@<r8>, int@<r9d>, int, int, int, int, unsigned int, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002fb50`

## callees

- `0x1800017a0`
- `0x1800017ec`
- `0x180007120`
- `0x1800b2180`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x1800b224e`
- `KERNEL32!CreateSemaphoreW` at `0x1800b224e`
- `KERNEL32!CreateThread` at `0x1800b22bb`
- `KERNEL32!CreateThread` at `0x1800b22bb`
- `KERNEL32!InitializeCriticalSection` at `0x1800b2194`
- `KERNEL32!InitializeCriticalSection` at `0x1800b2194`
- `KERNEL32!GetLastError` at `0x1800b225d`
- `KERNEL32!GetLastError` at `0x1800b225d`
- `KERNEL32!SetThreadPriority` at `0x1800b22cf`
- `KERNEL32!SetThreadPriority` at `0x1800b22cf`

## pseudocode

```c
COutputQueue *__fastcall COutputQueue::COutputQueue(
        COutputQueue *this,
        struct IPin *a2,
        int *a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        unsigned int a9,
        DWORD ThreadId)
{
  int v13; // eax
  void *v14; // rax
  HANDLE SemaphoreW; // rax
  _QWORD *v16; // rax
  HANDLE v17; // rax

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 15) = 1;
  CAMEvent::CAMEvent((COutputQueue *)((char *)this + 80), 0, a3);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 29) = 1;
  *((_BYTE *)this + 120) = 0;
  *(_QWORD *)((char *)this + 124) = 0;
  *((_DWORD *)this + 33) = 0;
  *((_QWORD *)this + 17) = 0;
  if ( *a3 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(struct IPin *, GUID *, char *))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IMemInputPin,
            (char *)this + 48);
    *a3 = v13;
    if ( v13 >= 0 )
    {
      v14 = operator new[](saturated_mul(*((int *)this + 15), 8u));
      *((_QWORD *)this + 12) = v14;
      if ( v14 )
      {
        SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
        *((_QWORD *)this + 9) = SemaphoreW;
        if ( !SemaphoreW )
        {
LABEL_5:
          *a3 = GetLastError() | 0x80070000;
          return this;
        }
        v16 = operator new(0x28u);
        if ( v16 )
        {
          *v16 = 0;
          v16[1] = 0;
          *((_DWORD *)v16 + 4) = 0;
          v16[3] = 1;
          v16[4] = 0;
          *((_QWORD *)this + 8) = v16;
          ThreadId = 0;
          v17 = CreateThread(0, 0, COutputQueue::InitialThreadProc, this, 0, &ThreadId);
          *((_QWORD *)this + 11) = v17;
          if ( v17 )
          {
            SetThreadPriority(v17, 0);
            return this;
          }
          goto LABEL_5;
        }
        *((_QWORD *)this + 8) = 0;
      }
      *a3 = -2147024882;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800b2180  push    rbx
0x1800b2182  push    rbp
0x1800b2183  push    rsi
0x1800b2184  push    rdi
0x1800b2185  push    r14
0x1800b2187  sub     rsp, 30h
0x1800b218b  mov     rdi, r8
0x1800b218e  mov     rsi, rdx
0x1800b2191  mov     rbx, rcx
0x1800b2194  call    cs:__imp_InitializeCriticalSection
0x1800b219a  xor     ebp, ebp
0x1800b219c  mov     [rbx+28h], rsi
0x1800b21a0  lea     rcx, [rbx+50h]; this
0x1800b21a4  mov     [rbx+30h], rbp
0x1800b21a8  mov     r8, rdi; int *
0x1800b21ab  mov     [rbx+38h], ebp
0x1800b21ae  xor     edx, edx; int
0x1800b21b0  mov     [rbx+40h], rbp
0x1800b21b4  mov     [rbx+48h], rbp
0x1800b21b8  mov     dword ptr [rbx+3Ch], 1
0x1800b21bf  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x1800b21c4  mov     [rbx+58h], rbp
0x1800b21c8  mov     [rbx+60h], rbp
0x1800b21cc  mov     [rbx+68h], rbp
0x1800b21d0  mov     [rbx+70h], ebp
0x1800b21d3  mov     dword ptr [rbx+74h], 1
0x1800b21da  mov     [rbx+78h], bpl
0x1800b21de  mov     [rbx+7Ch], rbp
0x1800b21e2  mov     [rbx+84h], ebp
0x1800b21e8  mov     [rbx+88h], rbp
0x1800b21ef  cmp     [rdi], ebp
0x1800b21f1  jl      loc_1800B22E1
0x1800b21f7  mov     rax, [rsi]
0x1800b21fa  lea     r8, [rbx+30h]
0x1800b21fe  lea     rdx, IID_IMemInputPin
0x1800b2205  mov     rcx, rsi
0x1800b2208  mov     rax, [rax]
0x1800b220b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2210  mov     [rdi], eax
0x1800b2212  test    eax, eax
0x1800b2214  js      loc_1800B22E1
0x1800b221a  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800b221e  lea     eax, [rbp+8]
0x1800b2221  mul     rcx
0x1800b2224  lea     rcx, [rbp-1]
0x1800b2228  cmovb   rax, rcx
0x1800b222c  mov     rcx, rax; unsigned __int64
0x1800b222f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b2234  mov     [rbx+60h], rax
0x1800b2238  test    rax, rax
0x1800b223b  jz      loc_1800B22DB
0x1800b2241  xor     r9d, r9d; lpName
0x1800b2244  xor     edx, edx; lInitialCount
0x1800b2246  xor     ecx, ecx; lpSemaphoreAttributes
0x1800b2248  mov     r8d, 7FFFFFFFh; lMaximumCount
0x1800b224e  call    cs:__imp_CreateSemaphoreW
0x1800b2254  mov     [rbx+48h], rax
0x1800b2258  test    rax, rax
0x1800b225b  jnz     short loc_1800B226C
0x1800b225d  call    cs:__imp_GetLastError
0x1800b2263  or      eax, 80070000h
0x1800b2268  mov     [rdi], eax
0x1800b226a  jmp     short loc_1800B22E1
0x1800b226c  mov     ecx, 28h ; '('; Size
0x1800b2271  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2276  test    rax, rax
0x1800b2279  jz      short loc_1800B22D7
0x1800b227b  mov     [rax], rbp
0x1800b227e  lea     r8, ?InitialThreadProc@COutputQueue@@KAKPEAX@Z; lpStartAddress
0x1800b2285  mov     [rax+8], rbp
0x1800b2289  mov     r9, rbx; lpParameter
0x1800b228c  mov     [rax+10h], ebp
0x1800b228f  xor     edx, edx; dwStackSize
0x1800b2291  mov     qword ptr [rax+18h], 1
0x1800b2299  xor     ecx, ecx; lpThreadAttributes
0x1800b229b  mov     [rax+20h], rbp
0x1800b229f  mov     [rbx+40h], rax
0x1800b22a3  lea     rax, [rsp+58h+ThreadId]
0x1800b22ab  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x1800b22b0  mov     [rsp+58h+dwCreationFlags], ebp; dwCreationFlags
0x1800b22b4  mov     [rsp+58h+ThreadId], ebp
0x1800b22bb  call    cs:__imp_CreateThread
0x1800b22c1  mov     [rbx+58h], rax
0x1800b22c5  test    rax, rax
0x1800b22c8  jz      short loc_1800B225D
0x1800b22ca  xor     edx, edx; nPriority
0x1800b22cc  mov     rcx, rax; hThread
0x1800b22cf  call    cs:__imp_SetThreadPriority
0x1800b22d5  jmp     short loc_1800B22E1
0x1800b22d7  mov     [rbx+40h], rbp
0x1800b22db  mov     dword ptr [rdi], 8007000Eh
0x1800b22e1  mov     rax, rbx
0x1800b22e4  add     rsp, 30h
0x1800b22e8  pop     r14
0x1800b22ea  pop     rdi
0x1800b22eb  pop     rsi
0x1800b22ec  pop     rbp
0x1800b22ed  pop     rbx
0x1800b22ee  retn
```
