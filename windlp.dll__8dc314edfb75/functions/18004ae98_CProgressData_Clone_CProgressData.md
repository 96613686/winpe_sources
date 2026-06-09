# CProgressData::Clone(CProgressData * *)

- ea: `0x18004ae98`
- end: `0x18004b04d`
- name: `?Clone@CProgressData@@QEAAJPEAPEAV1@@Z`
- size: `437`
- prototype: `__int64 __fastcall(CProgressData *__hidden this, struct CProgressData **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800471c0`

## callees

- `0x180001ba8`
- `0x180001be8`
- `0x18000aba4`
- `0x18001ce28`
- `0x18001fd60`
- `0x18004ae98`
- `0x18006309c`
- `0x18007ec9a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004aee4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004af92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004aee4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004af92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004afc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b008`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004afc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b008`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b025`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b025`

## pseudocode

```c
__int64 __fastcall CProgressData::Clone(CProgressData *this, struct CProgressData **a2)
{
  char *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // r15
  unsigned int v6; // edi
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  __int64 v9; // r12
  __int64 v10; // r13
  int v11; // eax
  __int64 v13; // [rsp+B0h] [rbp+8h]

  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( a2 )
  {
    v7 = operator new(0x50u);
    v8 = v7;
    if ( v7 )
    {
      memset_0(v7, 0, 0x50u);
      v8[3] = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 3) = 0;
      *((_OWORD *)v8 + 4) = 0;
      CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(v8 + 4));
      CProgressData::Init((CProgressData *)v8);
      v4 = (char *)v8;
      v9 = *((_QWORD *)this + 2);
      v10 = *((_QWORD *)this + 1);
      v13 = *(_QWORD *)this;
      v11 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(v8 + 4));
      v6 = v11;
      if ( v11 >= 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 4));
        *v8 = v13;
        v8[1] = v10;
        v8[2] = v9;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 4));
        v6 = 0;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
      if ( (v6 & 0x80000000) == 0 )
      {
        v4 = 0;
        *a2 = (struct CProgressData *)v8;
        goto LABEL_11;
      }
    }
    else
    {
      v4 = 0;
      v6 = -2147024882;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  LeaveCriticalSection(v5);
  if ( v4 )
  {
    if ( *((_DWORD *)v4 + 18) )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v4 + 32));
      *((_DWORD *)v4 + 18) = 0;
    }
    operator delete(v4);
  }
  return v6;
}

```

## disassembly

```asm
0x18004ae98  mov     r11, rsp
0x18004ae9b  push    rbx
0x18004ae9c  push    rbp
0x18004ae9d  push    rsi
0x18004ae9e  push    rdi
0x18004ae9f  push    r12
0x18004aea1  push    r13
0x18004aea3  push    r14
0x18004aea5  push    r15
0x18004aea7  sub     rsp, 68h
0x18004aeab  mov     r14, rdx
0x18004aeae  mov     rdi, rcx
0x18004aeb1  xor     ebx, ebx
0x18004aeb3  mov     [r11+8], rbx
0x18004aeb7  mov     [r11-70h], rbx
0x18004aebb  xorps   xmm0, xmm0
0x18004aebe  xor     eax, eax
0x18004aec0  movups  [rsp+0A8h+var_88], xmm0
0x18004aec5  mov     [r11-78h], rax
0x18004aec9  lea     rax, [rcx+18h]
0x18004aecd  mov     [r11-80h], rax
0x18004aed1  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x18004aed8  mov     qword ptr [rsp+0A8h+var_88], rcx
0x18004aedd  lea     r15, [rax+8]
0x18004aee1  mov     rcx, r15; lpCriticalSection
0x18004aee4  call    cs:__imp_EnterCriticalSection
0x18004aeea  mov     [rsp+0A8h+var_78], 1
0x18004aef2  test    r14, r14
0x18004aef5  jnz     short loc_18004AF01
0x18004aef7  mov     edi, 80070057h
0x18004aefc  jmp     loc_18004AFEE
0x18004af01  mov     ebx, 50h ; 'P'
0x18004af06  mov     ecx, ebx; Size
0x18004af08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004af0d  mov     rsi, rax
0x18004af10  mov     [rsp+0A8h+arg_0], rax
0x18004af18  test    rax, rax
0x18004af1b  jz      loc_18004AFE7
0x18004af21  mov     r8d, ebx; Size
0x18004af24  xor     edx, edx; Val
0x18004af26  mov     rcx, rax; void *
0x18004af29  call    memset_0
0x18004af2e  mov     qword ptr [rsi+18h], 0
0x18004af36  lea     rcx, [rsi+20h]; this
0x18004af3a  xorps   xmm0, xmm0
0x18004af3d  movups  xmmword ptr [rcx], xmm0
0x18004af40  movups  xmmword ptr [rcx+10h], xmm0
0x18004af44  movups  xmmword ptr [rcx+20h], xmm0
0x18004af48  call    ?Init@CExclusiveAcquireLock@@QEAAJXZ; CExclusiveAcquireLock::Init(void)
0x18004af4d  mov     rcx, rsi; this
0x18004af50  call    ?Init@CProgressData@@QEAAJXZ; CProgressData::Init(void)
0x18004af55  test    rsi, rsi
0x18004af58  jz      loc_18004AFE7
0x18004af5e  mov     rbx, rsi
0x18004af61  mov     r12, [rdi+10h]
0x18004af65  mov     r13, [rdi+8]
0x18004af69  mov     rax, [rdi]
0x18004af6c  mov     [rsp+0A8h+arg_0], rax
0x18004af74  lea     rbp, [rsi+20h]
0x18004af78  mov     rcx, rbp; this
0x18004af7b  call    ?Init@CExclusiveAcquireLock@@QEAAJXZ; CExclusiveAcquireLock::Init(void)
0x18004af80  mov     edi, eax
0x18004af82  test    eax, eax
0x18004af84  jns     short loc_18004AF8F
0x18004af86  mov     ecx, eax
0x18004af88  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004af8d  jmp     short loc_18004AFD5
0x18004af8f  mov     rcx, rbp; lpCriticalSection
0x18004af92  call    cs:__imp_EnterCriticalSection
0x18004af98  mov     [rsp+0A8h+var_58], 1
0x18004afa0  mov     rax, [rsp+0A8h+arg_0]
0x18004afa8  mov     [rsi], rax
0x18004afab  mov     [rsi+8], r13
0x18004afaf  mov     [rsi+10h], r12
0x18004afb3  xor     ecx, ecx
0x18004afb5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004afba  mov     eax, [rsp+0A8h+var_58]
0x18004afbe  test    eax, eax
0x18004afc0  jz      short loc_18004AFD3
0x18004afc2  mov     rcx, rbp; lpCriticalSection
0x18004afc5  call    cs:__imp_LeaveCriticalSection
0x18004afcb  mov     [rsp+0A8h+var_58], 0
0x18004afd3  xor     edi, edi
0x18004afd5  mov     ecx, edi
0x18004afd7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004afdc  test    edi, edi
0x18004afde  js      short loc_18004AFEE
0x18004afe0  xor     ebx, ebx
0x18004afe2  mov     [r14], rsi
0x18004afe5  jmp     short loc_18004AFF5
0x18004afe7  xor     ebx, ebx
0x18004afe9  mov     edi, 8007000Eh
0x18004afee  mov     ecx, edi
0x18004aff0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004aff5  mov     ecx, edi
0x18004aff7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004affc  nop
0x18004affd  mov     eax, [rsp+0A8h+var_78]
0x18004b001  test    eax, eax
0x18004b003  jz      short loc_18004B016
0x18004b005  mov     rcx, r15; lpCriticalSection
0x18004b008  call    cs:__imp_LeaveCriticalSection
0x18004b00e  mov     [rsp+0A8h+var_78], 0
0x18004b016  test    rbx, rbx
0x18004b019  jz      short loc_18004B03A
0x18004b01b  cmp     dword ptr [rbx+48h], 0
0x18004b01f  jz      short loc_18004B032
0x18004b021  lea     rcx, [rbx+20h]; lpCriticalSection
0x18004b025  call    cs:__imp_DeleteCriticalSection
0x18004b02b  mov     dword ptr [rbx+48h], 0
0x18004b032  mov     rcx, rbx; Block
0x18004b035  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b03a  mov     eax, edi
0x18004b03c  add     rsp, 68h
0x18004b040  pop     r15
0x18004b042  pop     r14
0x18004b044  pop     r13
0x18004b046  pop     r12
0x18004b048  pop     rdi
0x18004b049  pop     rsi
0x18004b04a  pop     rbp
0x18004b04b  pop     rbx
0x18004b04c  retn
```
