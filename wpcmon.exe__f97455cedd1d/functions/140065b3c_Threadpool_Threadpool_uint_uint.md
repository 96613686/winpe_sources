# Threadpool::Threadpool(uint,uint)

- ea: `0x140065b3c`
- end: `0x140065cee`
- name: `??0Threadpool@@QEAA@II@Z`
- size: `434`
- prototype: `Threadpool *__fastcall(Threadpool *this, __int64, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140040164`
- `0x140090bcc`

## callees

- `0x140005554`
- `0x1400057f0`
- `0x140006314`
- `0x140006338`
- `0x14001f6b4`
- `0x140060f58`
- `0x140065b3c`

## import_xrefs

- `KERNEL32!SetThreadpoolThreadMaximum` at `0x140065c33`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x140065c33`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x140065c23`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x140065c23`
- `KERNEL32!CreateThreadpool` at `0x140065c08`
- `KERNEL32!CreateThreadpool` at `0x140065c08`
- `KERNEL32!InitializeConditionVariable` at `0x140065b9f`
- `KERNEL32!InitializeConditionVariable` at `0x140065b9f`
- `KERNEL32!GetLastError` at `0x140065c89`
- `KERNEL32!GetLastError` at `0x140065c89`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140065b95`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140065b95`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Threadpool *__fastcall Threadpool::Threadpool(Threadpool *this, __int64 a2, int a3)
{
  char *v5; // rbx
  struct _TP_POOL *v6; // rcx
  __int64 v7; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF
  _DWORD *v12; // [rsp+88h] [rbp+20h]

  v5 = (char *)operator new(0x78u);
  *(_QWORD *)v5 = 0;
  memset_0(v5 + 8, 0, 0x48u);
  *((_QWORD *)v5 + 10) = 0;
  *((_QWORD *)v5 + 11) = &LockBox<Private::WorkItemBase *,4294967295>::`vftable';
  *((_QWORD *)v5 + 13) = 0;
  InitializeSRWLock((PSRWLOCK)v5 + 12);
  InitializeConditionVariable((PCONDITION_VARIABLE)v5 + 14);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v12 = operator new(0x18u);
  *(_OWORD *)v12 = 0;
  v12[2] = 1;
  v12[3] = 1;
  *(_QWORD *)v12 = &std::_Ref_count<Private::ThreadpoolImpl>::`vftable';
  *((_QWORD *)v12 + 2) = v5;
  *(_QWORD *)this = v5;
  *((_QWORD *)this + 1) = v12;
  operator delete(0, 0x78u);
  **(_DWORD **)this = 0;
  *(_DWORD *)(*(_QWORD *)this + 4LL) = a3;
  *(_QWORD *)(*(_QWORD *)this + 80LL) = CreateThreadpool(0);
  v6 = *(struct _TP_POOL **)(*(_QWORD *)this + 80LL);
  if ( !v6 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids, v10);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v10);
    throw (ErrorCodeException *)pExceptionObject;
  }
  SetThreadpoolThreadMinimum(v6, **(_DWORD **)this);
  SetThreadpoolThreadMaximum(*(PTP_POOL *)(*(_QWORD *)this + 80LL), *(_DWORD *)(*(_QWORD *)this + 4LL));
  v7 = *(_QWORD *)this;
  *(_DWORD *)(v7 + 8) = 3;
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 24) = 0;
  *(_QWORD *)(v7 + 32) = 0;
  *(_QWORD *)(v7 + 40) = 0;
  *(_QWORD *)(v7 + 48) = 0;
  *(_QWORD *)(v7 + 56) = 0;
  *(_DWORD *)(v7 + 64) = 0;
  *(_DWORD *)(v7 + 68) = 1;
  *(_DWORD *)(v7 + 72) = 72;
  *(_QWORD *)(*(_QWORD *)this + 16LL) = *(_QWORD *)(*(_QWORD *)this + 80LL);
  return this;
}

```

## disassembly

```asm
0x140065b3c  mov     [rsp+arg_8], rbx
0x140065b41  mov     [rsp+arg_0], rcx
0x140065b46  push    rsi
0x140065b47  push    rdi
0x140065b48  push    r14
0x140065b4a  sub     rsp, 50h
0x140065b4e  mov     edi, r8d
0x140065b51  mov     rsi, rcx
0x140065b54  mov     ecx, 78h ; 'x'; Size
0x140065b59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140065b5e  mov     rbx, rax
0x140065b61  mov     [rsp+68h+arg_18], rax
0x140065b69  xor     r14d, r14d
0x140065b6c  mov     [rax], r14
0x140065b6f  lea     rcx, [rax+8]; void *
0x140065b73  xor     edx, edx; Val
0x140065b75  lea     r8d, [r14+48h]; Size
0x140065b79  call    memset_0
0x140065b7e  mov     [rbx+50h], r14
0x140065b82  lea     rax, ??_7?$LockBox@PEAVWorkItemBase@Private@@$0PPPPPPPP@@@6B@; const LockBox<Private::WorkItemBase *,4294967295>::`vftable'
0x140065b89  mov     [rbx+58h], rax
0x140065b8d  mov     [rbx+68h], r14
0x140065b91  lea     rcx, [rbx+60h]; SRWLock
0x140065b95  call    cs:__imp_InitializeSRWLock
0x140065b9b  lea     rcx, [rbx+70h]; ConditionVariable
0x140065b9f  call    cs:__imp_InitializeConditionVariable
0x140065ba5  mov     [rsi], r14
0x140065ba8  mov     [rsi+8], r14
0x140065bac  mov     [rsp+68h+arg_18], rbx
0x140065bb4  lea     ecx, [r14+18h]; Size
0x140065bb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140065bbd  mov     [rsp+68h+arg_18], rax
0x140065bc5  xorps   xmm0, xmm0
0x140065bc8  movups  xmmword ptr [rax], xmm0
0x140065bcb  mov     dword ptr [rax+8], 1
0x140065bd2  mov     dword ptr [rax+0Ch], 1
0x140065bd9  lea     rcx, ??_7?$_Ref_count@UThreadpoolImpl@Private@@@std@@6B@; const std::_Ref_count<Private::ThreadpoolImpl>::`vftable'
0x140065be0  mov     [rax], rcx
0x140065be3  mov     [rax+10h], rbx
0x140065be7  mov     [rsi], rbx
0x140065bea  mov     [rsi+8], rax
0x140065bee  lea     edx, [r14+78h]; unsigned __int64
0x140065bf2  xor     ecx, ecx; void *
0x140065bf4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140065bf9  nop
0x140065bfa  mov     rax, [rsi]
0x140065bfd  mov     [rax], r14d
0x140065c00  mov     rax, [rsi]
0x140065c03  mov     [rax+4], edi
0x140065c06  xor     ecx, ecx; reserved
0x140065c08  call    cs:__imp_CreateThreadpool
0x140065c0e  mov     rcx, [rsi]
0x140065c11  mov     [rcx+50h], rax
0x140065c15  mov     rdx, [rsi]
0x140065c18  mov     rcx, [rdx+50h]; ptpp
0x140065c1c  test    rcx, rcx
0x140065c1f  jz      short loc_140065C89
0x140065c21  mov     edx, [rdx]; cthrdMic
0x140065c23  call    cs:__imp_SetThreadpoolThreadMinimum
0x140065c29  mov     rcx, [rsi]
0x140065c2c  mov     edx, [rcx+4]; cthrdMost
0x140065c2f  mov     rcx, [rcx+50h]; ptpp
0x140065c33  call    cs:__imp_SetThreadpoolThreadMaximum
0x140065c39  mov     rax, [rsi]
0x140065c3c  mov     dword ptr [rax+8], 3
0x140065c43  mov     [rax+10h], r14
0x140065c47  mov     [rax+18h], r14
0x140065c4b  mov     [rax+20h], r14
0x140065c4f  mov     [rax+28h], r14
0x140065c53  mov     [rax+30h], r14
0x140065c57  mov     [rax+38h], r14
0x140065c5b  mov     [rax+40h], r14d
0x140065c5f  mov     dword ptr [rax+44h], 1
0x140065c66  mov     dword ptr [rax+48h], 48h ; 'H'
0x140065c6d  mov     rcx, [rsi]
0x140065c70  mov     rax, [rcx+50h]
0x140065c74  mov     [rcx+10h], rax
0x140065c78  mov     rax, rsi
0x140065c7b  mov     rbx, [rsp+68h+arg_8]
0x140065c80  add     rsp, 50h
0x140065c84  pop     r14
0x140065c86  pop     rdi
0x140065c87  pop     rsi
0x140065c88  retn
0x140065c89  call    cs:__imp_GetLastError
0x140065c8f  nop
0x140065c90  mov     ebx, eax
0x140065c92  test    eax, eax
0x140065c94  jle     short loc_140065C9F
0x140065c96  movzx   ebx, ax
0x140065c99  or      ebx, 80070000h
0x140065c9f  lea     rax, WPP_GLOBAL_Control
0x140065ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x140065cad  cmp     rcx, rax
0x140065cb0  jz      short loc_140065CD0
0x140065cb2  test    byte ptr [rcx+1Ch], 1
0x140065cb6  jz      short loc_140065CD0
0x140065cb8  mov     edx, 0Ah
0x140065cbd  mov     r9d, ebx
0x140065cc0  lea     r8, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids
0x140065cc7  mov     rcx, [rcx+10h]
0x140065ccb  call    WPP_SF_d
0x140065cd0  mov     edx, ebx; int
0x140065cd2  lea     rcx, [rsp+68h+pExceptionObject]; this
0x140065cd7  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140065cdc  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140065ce3  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140065ce8  call    _CxxThrowException_0
```
