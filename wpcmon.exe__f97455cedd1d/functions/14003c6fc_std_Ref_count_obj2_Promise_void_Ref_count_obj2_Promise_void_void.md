# std::_Ref_count_obj2<Promise<void>>::_Ref_count_obj2<Promise<void>>(void)

- ea: `0x14003c6fc`
- end: `0x14003c7f3`
- name: `??$?0$$V@?$_Ref_count_obj2@V?$Promise@X@@@std@@QEAA@XZ`
- size: `247`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14003d594`
- `0x14003f2ac`
- `0x14003f7d8`
- `0x140042704`
- `0x140043fa4`
- `0x140044830`

## callees

- `0x1400057f0`
- `0x140006314`
- `0x140006338`
- `0x14003c6fc`
- `0x140060f58`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14003c78b`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14003c78b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14003c79d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14003c79d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Ref_count_obj2<Promise<void>>::_Ref_count_obj2<Promise<void>>(__int64 a1)
{
  _QWORD *v2; // r14
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-48h] BYREF
  char *v5; // [rsp+88h] [rbp+10h]

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<Promise<void>>::`vftable';
  v2 = (_QWORD *)(a1 + 16);
  v5 = (char *)operator new(0x68u);
  *(_OWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 1;
  *((_DWORD *)v5 + 3) = 1;
  *(_QWORD *)v5 = &std::_Ref_count_obj2<Private::FutureData<void>>::`vftable';
  *((_QWORD *)v5 + 4) = 0;
  *((_QWORD *)v5 + 2) = &Private::FutureData<void>::`vftable';
  *((_QWORD *)v5 + 3) = &LockBox<Private::FutureData<void>::ResultInfo,4294967295>::`vftable';
  memset_0(v5 + 40, 0, 0x40u);
  __ExceptionPtrCreate(v5 + 72);
  *((_QWORD *)v5 + 12) = 0;
  InitializeSRWLock((PSRWLOCK)v5 + 4);
  *v2 = v5 + 16;
  v2[1] = v5;
  if ( v5 == (char *)-16LL )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x14003c6fc  mov     r11, rsp
0x14003c6ff  mov     [r11+18h], rbx
0x14003c703  mov     [r11+20h], rsi
0x14003c707  push    rdi
0x14003c708  push    r14
0x14003c70a  push    r15
0x14003c70c  sub     rsp, 60h
0x14003c710  mov     r15, rcx
0x14003c713  mov     ebx, 1
0x14003c718  mov     [rcx+8], ebx
0x14003c71b  mov     [rcx+0Ch], ebx
0x14003c71e  lea     rax, ??_7?$_Ref_count_obj2@V?$Promise@X@@@std@@6B@; const std::_Ref_count_obj2<Promise<void>>::`vftable'
0x14003c725  mov     [rcx], rax
0x14003c728  lea     r14, [rcx+10h]
0x14003c72c  mov     [r11+8], r14
0x14003c730  lea     ecx, [rbx+67h]; Size
0x14003c733  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003c738  mov     rsi, rax
0x14003c73b  mov     [rsp+78h+arg_8], rax
0x14003c743  xorps   xmm0, xmm0
0x14003c746  movups  xmmword ptr [rax], xmm0
0x14003c749  mov     [rax+8], ebx
0x14003c74c  mov     [rax+0Ch], ebx
0x14003c74f  lea     rax, ??_7?$_Ref_count_obj2@U?$FutureData@X@Private@@@std@@6B@; const std::_Ref_count_obj2<Private::FutureData<void>>::`vftable'
0x14003c756  mov     [rsi], rax
0x14003c759  lea     rdi, [rsi+10h]
0x14003c75d  xor     eax, eax
0x14003c75f  mov     [rdi+10h], rax
0x14003c763  lea     rax, ??_7?$FutureData@X@Private@@6B@; const Private::FutureData<void>::`vftable'
0x14003c76a  mov     [rdi], rax
0x14003c76d  lea     rax, ??_7?$LockBox@UResultInfo@?$FutureData@X@Private@@$0PPPPPPPP@@@6B@; const LockBox<Private::FutureData<void>::ResultInfo,4294967295>::`vftable'
0x14003c774  mov     [rdi+8], rax
0x14003c778  xor     edx, edx; Val
0x14003c77a  lea     r8d, [rbx+3Fh]; Size
0x14003c77e  lea     rcx, [rdi+18h]; void *
0x14003c782  call    memset_0
0x14003c787  lea     rcx, [rdi+38h]
0x14003c78b  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14003c791  mov     qword ptr [rdi+50h], 0
0x14003c799  lea     rcx, [rdi+10h]; SRWLock
0x14003c79d  call    cs:__imp_InitializeSRWLock
0x14003c7a3  nop
0x14003c7a4  mov     [r14], rdi
0x14003c7a7  mov     [r14+8], rsi
0x14003c7ab  xorps   xmm0, xmm0
0x14003c7ae  movdqu  [rsp+78h+var_58], xmm0
0x14003c7b4  test    rdi, rdi
0x14003c7b7  jz      short loc_14003C7D2
0x14003c7b9  mov     rax, r15
0x14003c7bc  lea     r11, [rsp+78h+var_18]
0x14003c7c1  mov     rbx, [r11+30h]
0x14003c7c5  mov     rsi, [r11+38h]
0x14003c7c9  mov     rsp, r11
0x14003c7cc  pop     r15
0x14003c7ce  pop     r14
0x14003c7d0  pop     rdi
0x14003c7d1  retn
0x14003c7d2  mov     edx, 8000FFFFh; int
0x14003c7d7  lea     rcx, [rsp+78h+pExceptionObject]; this
0x14003c7dc  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14003c7e1  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14003c7e8  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14003c7ed  call    _CxxThrowException_0
```
