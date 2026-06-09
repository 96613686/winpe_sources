# CMulticastNotification::WdsRequestCompletion(_WDSOVERLAPPED *)

- ea: `0x180018f20`
- end: `0x18001911b`
- name: `?WdsRequestCompletion@CMulticastNotification@@UEAAXPEAU_WDSOVERLAPPED@@@Z`
- size: `507`
- prototype: `void(CMulticastNotification *__hidden this, struct _WDSOVERLAPPED *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180018f20`
- `0x180019124`
- `0x18001a9a8`
- `0x1800227d4`
- `0x180024c14`
- `0x180024ce0`
- `0x180025850`
- `0x1800266a0`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800190a1`
- `KERNEL32!SetEvent` at `0x1800190a1`
- `KERNEL32!LeaveCriticalSection` at `0x180019020`
- `KERNEL32!LeaveCriticalSection` at `0x1800190d1`
- `KERNEL32!LeaveCriticalSection` at `0x180019020`
- `KERNEL32!LeaveCriticalSection` at `0x1800190d1`
- `KERNEL32!EnterCriticalSection` at `0x180018f55`
- `KERNEL32!EnterCriticalSection` at `0x180018f55`
- `WDSSRV!WdsQueryShutdown` at `0x180018f69`
- `WDSSRV!WdsQueryShutdown` at `0x180018f69`

## pseudocode

```c
void __fastcall CMulticastNotification::WdsRequestCompletion(CMulticastNotification *this, struct _WDSOVERLAPPED *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  int v4; // r12d
  unsigned int v6; // r15d
  int v7; // edi
  _QWORD *v8; // r13
  _QWORD *v9; // r15
  _QWORD *v10; // r14
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  void (__fastcall *v14)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void *v15; // rcx
  const char *v16; // rdx
  __int128 v17; // [rsp+30h] [rbp-58h] BYREF
  int v18; // [rsp+44h] [rbp-44h]
  void *Src; // [rsp+98h] [rbp+10h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v4 = 0;
  v18 = 0;
  v6 = 0;
  v17 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v7 = 1;
  if ( !*((_DWORD *)this + 12) && !(unsigned int)WdsQueryShutdown() )
  {
    v8 = (_QWORD *)*((_QWORD *)this + 7);
    if ( v8 )
    {
      v9 = (_QWORD *)*((_QWORD *)&v17 + 1);
      v10 = (_QWORD *)v17;
      do
      {
        Src = v8;
        v8 = (_QWORD *)v8[2];
        v11 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        v12 = v11;
        if ( v11 )
        {
          v11[2] = 0;
          v11[3] = 0;
        }
        else
        {
          v12 = 0;
        }
        if ( !v12 )
        {
          v6 = 8;
          goto LABEL_17;
        }
        memmove_0(v12, Src, 0x20u);
        v12[2] = 0;
        *((_QWORD *)&v17 + 1) = v12;
        if ( v10 )
        {
          v12[3] = v9;
          v9[2] = v12;
        }
        else
        {
          v12[3] = 0;
          v10 = v12;
          *(_QWORD *)&v17 = v12;
        }
        ++v4;
        v9 = v12;
        v18 = v4;
      }
      while ( v8 );
      v7 = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      while ( v10 )
      {
        v13 = v10[1];
        v14 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))*v10;
        v10 = (_QWORD *)v10[2];
        v14(v13, *((unsigned int *)a2 + 14), *((_QWORD *)a2 + 8), *((_QWORD *)a2 + 9));
      }
      v6 = 0;
LABEL_17:
      v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
    }
  }
  if ( a2 )
  {
    if ( (unsigned int)(*((_DWORD *)a2 + 14) - 1) <= 2 )
    {
      v15 = (void *)*((_QWORD *)a2 + 8);
      if ( v15 )
      {
        operator delete(v15);
        *((_QWORD *)a2 + 8) = 0;
      }
    }
    operator delete(a2);
  }
  ListDeleteAllObjects<CMulticastNotification::Callback,CNoLock>(&v17);
  CMRSWLock::ReaderLock((LPCRITICAL_SECTION)((char *)this + 96));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 20, 0xFFFFFFFF) == 1 )
    SetEvent(*((HANDLE *)this + 11));
  CMRSWLock::ReaderRelease((struct _RTL_CRITICAL_SECTION *)((char *)this + 96));
  ElValidateWin32(v6, v16, "base\\eco\\wds\\transport\\server\\mc\\mcnotification.cpp", 0x1FFu);
  if ( v7 )
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180018f20  mov     [rsp+arg_10], rbx
0x180018f25  push    rbp
0x180018f26  push    rsi
0x180018f27  push    rdi
0x180018f28  push    r12
0x180018f2a  push    r13
0x180018f2c  push    r14
0x180018f2e  push    r15
0x180018f30  sub     rsp, 50h
0x180018f34  lea     r14, [rcx+8]
0x180018f38  mov     rbp, rcx
0x180018f3b  xorps   xmm0, xmm0
0x180018f3e  xor     r12d, r12d
0x180018f41  mov     rcx, r14; lpCriticalSection
0x180018f44  mov     [rsp+88h+var_44], r12d
0x180018f49  mov     rsi, rdx
0x180018f4c  xor     r15d, r15d
0x180018f4f  movdqu  [rsp+88h+var_58], xmm0
0x180018f55  call    cs:__imp_EnterCriticalSection
0x180018f5b  lea     edi, [r15+1]
0x180018f5f  cmp     [rbp+30h], r12d
0x180018f63  jnz     loc_180019053
0x180018f69  call    cs:__imp_WdsQueryShutdown
0x180018f6f  test    eax, eax
0x180018f71  jnz     loc_180019053
0x180018f77  mov     r13, [rbp+38h]
0x180018f7b  test    r13, r13
0x180018f7e  jz      loc_180019053
0x180018f84  mov     r15, qword ptr [rsp+88h+var_58+8]
0x180018f89  mov     r14, qword ptr [rsp+88h+var_58]
0x180018f8e  mov     [rsp+88h+Src], r13
0x180018f96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018f9d  mov     r13, [r13+10h]
0x180018fa1  mov     ecx, 20h ; ' '; unsigned __int64
0x180018fa6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018fab  mov     rbx, rax
0x180018fae  test    rax, rax
0x180018fb1  jz      short loc_180018FBF
0x180018fb3  and     qword ptr [rax+10h], 0
0x180018fb8  and     qword ptr [rax+18h], 0
0x180018fbd  jmp     short loc_180018FC1
0x180018fbf  xor     ebx, ebx
0x180018fc1  test    rbx, rbx
0x180018fc4  jz      loc_180019110
0x180018fca  mov     rdx, [rsp+88h+Src]; Src
0x180018fd2  mov     r8d, 20h ; ' '; Size
0x180018fd8  mov     rcx, rbx; void *
0x180018fdb  call    memmove_0
0x180018fe0  and     qword ptr [rbx+10h], 0
0x180018fe5  mov     qword ptr [rsp+88h+var_58+8], rbx
0x180018fea  test    r14, r14
0x180018fed  jnz     short loc_180018FFE
0x180018fef  and     qword ptr [rbx+18h], 0
0x180018ff4  mov     r14, rbx
0x180018ff7  mov     qword ptr [rsp+88h+var_58], rbx
0x180018ffc  jmp     short loc_180019006
0x180018ffe  mov     [rbx+18h], r15
0x180019002  mov     [r15+10h], rbx
0x180019006  add     r12d, edi
0x180019009  mov     r15, rbx
0x18001900c  mov     [rsp+88h+var_44], r12d
0x180019011  test    r13, r13
0x180019014  jnz     loc_180018F8E
0x18001901a  xor     edi, edi
0x18001901c  lea     rcx, [rbp+8]; lpCriticalSection
0x180019020  call    cs:__imp_LeaveCriticalSection
0x180019026  jmp     short loc_180019047
0x180019028  mov     r9, [rsi+48h]
0x18001902c  lea     rax, [r14]
0x18001902f  mov     rcx, [rax+8]
0x180019033  mov     rax, [rax]
0x180019036  mov     r8, [rsi+40h]
0x18001903a  mov     edx, [rsi+38h]
0x18001903d  mov     r14, [r14+10h]
0x180019041  call    cs:__guard_dispatch_icall_fptr
0x180019047  test    r14, r14
0x18001904a  jnz     short loc_180019028
0x18001904c  mov     r15d, edi
0x18001904f  lea     r14, [rbp+8]
0x180019053  test    rsi, rsi
0x180019056  jz      short loc_18001907D
0x180019058  mov     eax, [rsi+38h]
0x18001905b  dec     eax
0x18001905d  cmp     eax, 2
0x180019060  ja      short loc_180019075
0x180019062  mov     rcx, [rsi+40h]; void *
0x180019066  test    rcx, rcx
0x180019069  jz      short loc_180019075
0x18001906b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019070  and     qword ptr [rsi+40h], 0
0x180019075  mov     rcx, rsi; void *
0x180019078  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001907d  lea     rcx, [rsp+88h+var_58]
0x180019082  call    ??$ListDeleteAllObjects@UCallback@CMulticastNotification@@VCNoLock@@@@YAXPEAV?$CList@UCallback@CMulticastNotification@@VCNoLock@@@@@Z; ListDeleteAllObjects<CMulticastNotification::Callback,CNoLock>(CList<CMulticastNotification::Callback,CNoLock> *)
0x180019087  lea     rcx, [rbp+60h]; lpCriticalSection
0x18001908b  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180019090  or      eax, 0FFFFFFFFh
0x180019093  lock xadd [rbp+50h], eax
0x180019098  cmp     eax, 1
0x18001909b  jnz     short loc_1800190A7
0x18001909d  mov     rcx, [rbp+58h]; hEvent
0x1800190a1  call    cs:__imp_SetEvent
0x1800190a7  lea     rcx, [rbp+60h]; this
0x1800190ab  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x1800190b0  mov     r9d, 1FFh; unsigned int
0x1800190b6  lea     r8, aBaseEcoWdsTran_1; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800190bd  mov     ecx, r15d; unsigned int
0x1800190c0  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800190c5  test    edi, edi
0x1800190c7  jz      short loc_1800190F8
0x1800190c9  add     edi, 0FFFFFFFFh
0x1800190cc  jnz     short loc_1800190D7
0x1800190ce  mov     rcx, r14; lpCriticalSection
0x1800190d1  call    cs:__imp_LeaveCriticalSection
0x1800190d7  test    edi, edi
0x1800190d9  jz      short loc_1800190F8
0x1800190db  and     [rsp+88h+var_68], 0
0x1800190e0  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x1800190e7  mov     edx, 16Ah; unsigned int
0x1800190ec  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x1800190f3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800190f8  mov     rbx, [rsp+88h+arg_10]
0x180019100  add     rsp, 50h
0x180019104  pop     r15
0x180019106  pop     r14
0x180019108  pop     r13
0x18001910a  pop     r12
0x18001910c  pop     rdi
0x18001910d  pop     rsi
0x18001910e  pop     rbp
0x18001910f  retn
0x180019110  mov     r15d, 8
0x180019116  jmp     loc_18001904F
```
