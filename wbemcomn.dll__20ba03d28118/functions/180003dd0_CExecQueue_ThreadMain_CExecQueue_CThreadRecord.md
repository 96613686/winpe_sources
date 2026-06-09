# CExecQueue::ThreadMain(CExecQueue::CThreadRecord *)

- ea: `0x180003dd0`
- end: `0x180003fea`
- name: `?ThreadMain@CExecQueue@@MEAAXPEAVCThreadRecord@1@@Z`
- size: `538`
- prototype: `void(CExecQueue *__hidden this, struct CExecQueue::CThreadRecord *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003dd0`
- `0x1800041d0`
- `0x1800041e8`
- `0x180004750`
- `0x180028b80`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ead`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003fd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ead`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003fd2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180003e16`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180003e16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CExecQueue::ThreadMain(CExecQueue *this, HANDLE *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 v5; // rax
  DWORD v6; // r15d
  unsigned int v7; // ebx
  __int64 v8; // r8
  HANDLE v9; // rdx
  int v10; // [rsp+30h] [rbp-18h] BYREF
  char *v11; // [rsp+38h] [rbp-10h]
  HANDLE pHandles; // [rsp+90h] [rbp+48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v11 = (char *)this + 16;
  v10 = 0;
  if ( (*(int (__fastcall **)(CExecQueue *))(*(_QWORD *)this + 16LL))(this) >= 0 )
  {
    TlsSetValue(mstatic_dwTlsIndex, a2);
    while ( 1 )
    {
      CStaticCritSec::Enter(v4);
      v10 = 1;
      v5 = (*(__int64 (__fastcall **)(CExecQueue *, HANDLE *))(*(_QWORD *)this + 120LL))(this, a2);
      if ( v5 )
        break;
      *((_DWORD *)a2 + 4) = 1;
      ++*((_DWORD *)this + 41);
      v6 = (*(__int64 (__fastcall **)(CExecQueue *, HANDLE *))(*(_QWORD *)this + 72LL))(this, a2);
      LeaveCriticalSection(v4);
      v10 = 0;
      pHandles = a2[4];
      v7 = WbemWaitForMultipleObjects(1u, &pHandles, v6);
      CStaticCritSec::Enter(v4);
      v10 = 1;
      if ( v7 )
      {
        pHandles = a2[4];
        if ( !WbemWaitForMultipleObjects(1u, &pHandles, 0) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v8, a2, a2[1]);
          }
          if ( *((_DWORD *)a2 + 5) || (v9 = a2[1]) == 0 )
          {
            (*(void (__fastcall **)(CExecQueue *, HANDLE *))(*(_QWORD *)this + 40LL))(this, a2);
            LeaveCriticalSection(v4);
            v10 = 0;
            CCritSecWrapper::~CCritSecWrapper((CCritSecWrapper *)&v10);
            return;
          }
          (*(void (__fastcall **)(HANDLE, HANDLE, _QWORD))(*(_QWORD *)*a2 + 160LL))(*a2, v9, 0);
          a2[1] = 0;
        }
        *((_DWORD *)a2 + 4) = 0;
        if ( (*(unsigned int (__fastcall **)(CExecQueue *, HANDLE *, _QWORD))(*(_QWORD *)this + 64LL))(this, a2, v6) )
          goto LABEL_11;
        --*((_DWORD *)this + 41);
        LeaveCriticalSection(v4);
        v10 = 0;
      }
      else
      {
        if ( *((_DWORD *)a2 + 5) || !a2[1] )
        {
LABEL_11:
          (*(void (__fastcall **)(CExecQueue *, HANDLE *))(*(_QWORD *)this + 40LL))(this, a2);
          LeaveCriticalSection(v4);
          v10 = 0;
          return;
        }
LABEL_7:
        LeaveCriticalSection(v4);
        v10 = 0;
        (*(void (__fastcall **)(CExecQueue *, HANDLE *))(*(_QWORD *)this + 104LL))(this, a2);
      }
    }
    a2[1] = (HANDLE)v5;
    goto LABEL_7;
  }
}

```

## disassembly

```asm
0x180003dd0  push    rbp
0x180003dd2  push    rbx
0x180003dd3  push    rsi
0x180003dd4  push    rdi
0x180003dd5  push    r12
0x180003dd7  push    r13
0x180003dd9  push    r14
0x180003ddb  push    r15
0x180003ddd  mov     rbp, rsp
0x180003de0  sub     rsp, 48h
0x180003de4  mov     rdi, rdx
0x180003de7  mov     rsi, rcx
0x180003dea  lea     r14, [rcx+10h]
0x180003dee  mov     [rbp+var_10], r14
0x180003df2  xor     r12d, r12d
0x180003df5  mov     [rbp+var_18], r12d
0x180003df9  mov     rax, [rcx]
0x180003dfc  mov     rax, [rax+10h]
0x180003e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e05  test    eax, eax
0x180003e07  js      loc_180003F3D
0x180003e0d  mov     rdx, rdi; lpTlsValue
0x180003e10  mov     ecx, cs:?mstatic_dwTlsIndex@@3KA; dwTlsIndex
0x180003e16  call    cs:__imp_TlsSetValue
0x180003e1c  lea     r13d, [r12+1]
0x180003e21  mov     rcx, r14; this
0x180003e24  call    ?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180003e29  mov     [rbp+var_18], r13d
0x180003e2d  mov     rax, [rsi]
0x180003e30  mov     rdx, rdi
0x180003e33  mov     rcx, rsi
0x180003e36  mov     rax, [rax+78h]
0x180003e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3f  test    rax, rax
0x180003e42  jnz     loc_180003F4E
0x180003e48  mov     [rdi+10h], r13d
0x180003e4c  add     [rsi+0A4h], r13d
0x180003e53  mov     rax, [rsi]
0x180003e56  mov     rdx, rdi
0x180003e59  mov     rcx, rsi
0x180003e5c  mov     rax, [rax+48h]
0x180003e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e65  mov     r15d, eax
0x180003e68  mov     rcx, r14; lpCriticalSection
0x180003e6b  call    cs:__imp_LeaveCriticalSection
0x180003e71  mov     [rbp+var_18], r12d
0x180003e75  mov     rcx, [rdi+20h]
0x180003e79  mov     [rbp+pHandles], rcx
0x180003e7d  mov     r8d, r15d; dwTimeout
0x180003e80  lea     rdx, [rbp+pHandles]; pHandles
0x180003e84  mov     ecx, r13d; cHandles
0x180003e87  call    ?WbemWaitForMultipleObjects@@YAKKPEAPEAXK@Z; WbemWaitForMultipleObjects(ulong,void * *,ulong)
0x180003e8c  mov     ebx, eax
0x180003e8e  mov     rcx, r14; this
0x180003e91  call    ?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180003e96  mov     [rbp+var_18], r13d
0x180003e9a  test    ebx, ebx
0x180003e9c  jnz     short loc_180003ECE
0x180003e9e  cmp     [rdi+14h], r12d
0x180003ea2  jnz     short loc_180003F1E
0x180003ea4  cmp     [rdi+8], r12
0x180003ea8  jz      short loc_180003F1E
0x180003eaa  mov     rcx, r14; lpCriticalSection
0x180003ead  call    cs:__imp_LeaveCriticalSection
0x180003eb3  mov     [rbp+var_18], r12d
0x180003eb7  mov     rax, [rsi]
0x180003eba  mov     rdx, rdi
0x180003ebd  mov     rcx, rsi
0x180003ec0  mov     rax, [rax+68h]
0x180003ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec9  jmp     loc_180003E21
0x180003ece  mov     rax, [rdi+20h]
0x180003ed2  mov     [rbp+pHandles], rax
0x180003ed6  xor     r8d, r8d; dwTimeout
0x180003ed9  lea     rdx, [rbp+pHandles]; pHandles
0x180003edd  mov     ecx, r13d; cHandles
0x180003ee0  call    ?WbemWaitForMultipleObjects@@YAKKPEAPEAXK@Z; WbemWaitForMultipleObjects(ulong,void * *,ulong)
0x180003ee5  test    eax, eax
0x180003ee7  jz      short loc_180003F57
0x180003ee9  mov     [rdi+10h], r12d
0x180003eed  mov     rax, [rsi]
0x180003ef0  mov     r8d, r15d
0x180003ef3  mov     rdx, rdi
0x180003ef6  mov     rcx, rsi
0x180003ef9  mov     rax, [rax+40h]
0x180003efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f02  test    eax, eax
0x180003f04  jnz     short loc_180003F1E
0x180003f06  dec     dword ptr [rsi+0A4h]
0x180003f0c  mov     rcx, r14; lpCriticalSection
0x180003f0f  call    cs:__imp_LeaveCriticalSection
0x180003f15  mov     [rbp+var_18], r12d
0x180003f19  jmp     loc_180003E21
0x180003f1e  mov     rax, [rsi]
0x180003f21  mov     rdx, rdi
0x180003f24  mov     rcx, rsi
0x180003f27  mov     rax, [rax+28h]
0x180003f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f30  mov     rcx, r14; lpCriticalSection
0x180003f33  call    cs:__imp_LeaveCriticalSection
0x180003f39  mov     [rbp+var_18], r12d
0x180003f3d  add     rsp, 48h
0x180003f41  pop     r15
0x180003f43  pop     r14
0x180003f45  pop     r13
0x180003f47  pop     r12
0x180003f49  pop     rdi
0x180003f4a  pop     rsi
0x180003f4b  pop     rbx
0x180003f4c  pop     rbp
0x180003f4d  retn
0x180003f4e  mov     [rdi+8], rax
0x180003f52  jmp     loc_180003EAA
0x180003f57  lea     rax, WPP_GLOBAL_Control
0x180003f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f65  cmp     rcx, rax
0x180003f68  jz      short loc_180003F90
0x180003f6a  test    [rcx+1Ch], r13b
0x180003f6e  jz      short loc_180003F90
0x180003f70  cmp     byte ptr [rcx+19h], 5
0x180003f74  jb      short loc_180003F90
0x180003f76  mov     edx, 11h
0x180003f7b  mov     rax, [rdi+8]
0x180003f7f  mov     [rsp+48h+var_28], rax
0x180003f84  mov     r9, rdi
0x180003f87  mov     rcx, [rcx+10h]
0x180003f8b  call    WPP_SF_qq
0x180003f90  cmp     [rdi+14h], r12d
0x180003f94  jnz     short loc_180003FBD
0x180003f96  mov     rdx, [rdi+8]
0x180003f9a  test    rdx, rdx
0x180003f9d  jz      short loc_180003FBD
0x180003f9f  mov     rcx, [rdi]
0x180003fa2  mov     rax, [rcx]
0x180003fa5  xor     r8d, r8d
0x180003fa8  mov     rax, [rax+0A0h]
0x180003faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb4  mov     [rdi+8], r12
0x180003fb8  jmp     loc_180003EE9
0x180003fbd  mov     rax, [rsi]
0x180003fc0  mov     rdx, rdi
0x180003fc3  mov     rcx, rsi
0x180003fc6  mov     rax, [rax+28h]
0x180003fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fcf  mov     rcx, r14; lpCriticalSection
0x180003fd2  call    cs:__imp_LeaveCriticalSection
0x180003fd8  mov     [rbp+var_18], r12d
0x180003fdc  lea     rcx, [rbp+var_18]; this
0x180003fe0  call    ??1CCritSecWrapper@@QEAA@XZ; CCritSecWrapper::~CCritSecWrapper(void)
0x180003fe5  jmp     loc_180003F3D
```
