# DllGetActivationFactory

- ea: `0x18000f000`
- end: `0x18000f30a`
- name: `DllGetActivationFactory`
- size: `778`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f000`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f199`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f29d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f199`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f29d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f2ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f2ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f250`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f250`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f153`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f153`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000f06a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000f06a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000f054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000f054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f088`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f088`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000f2f9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000f2f9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000f1f8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000f1f8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f039`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f039`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000f26a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000f26a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000f169`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000f2b3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000f169`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000f2b3`

## string_xrefs

- `0x18000f1c3`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *a2)
{
  PCWSTR StringRawBuffer; // rsi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rbx
  RTL_SRWLOCK *v13; // rdi
  void *v14; // rcx
  int v15; // esi
  RTL_SRWLOCK *v17; // rsi
  void *v18; // rcx
  PVOID v19; // rdi
  PVOID Ptr; // [rsp+30h] [rbp-68h] BYREF
  BOOL hasEmbedNull; // [rsp+38h] [rbp-60h] BYREF
  int v22; // [rsp+3Ch] [rbp-5Ch] BYREF
  __int128 v23; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v24[22]; // [rsp+50h] [rbp-48h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180044928 = 1;
  *a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v23 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v24 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v24[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v23);
    return 2147942487LL;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
       + 8;
    v6 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 48))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    while ( v5 < v6 )
    {
      if ( *(_QWORD *)v5 )
      {
        v7 = (*(__int64 (**)(void))(*(_QWORD *)v5 + 8LL))();
        v8 = (unsigned __int16 *)StringRawBuffer;
        v9 = v7 - (_QWORD)StringRawBuffer;
        do
        {
          v10 = *(unsigned __int16 *)((char *)v8 + v9);
          v11 = *v8 - v10;
          if ( v11 )
            break;
          ++v8;
        }
        while ( v10 );
        if ( !v11 )
        {
          _mm_lfence();
          v22 = 1;
          v12 = *(_QWORD *)v5;
          *a2 = 0;
          Ptr = 0;
          if ( **(_QWORD **)(v12 + 24) )
          {
            v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                      + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
            AcquireSRWLockShared(v13);
            v14 = **(void ***)(v12 + 24);
            if ( v14 )
            {
              Ptr = DecodePointer(v14);
              v15 = (**(__int64 (__fastcall ***)(PVOID, GUID *, _QWORD *))Ptr)(
                      Ptr,
                      &GUID_00000035_0000_0000_c000_000000000046,
                      a2);
              if ( v13 )
                ReleaseSRWLockShared(v13);
              return (unsigned int)v15;
            }
            if ( v13 )
              ReleaseSRWLockShared(v13);
          }
          v15 = (*(__int64 (__fastcall **)(int *, __int64, GUID *, PVOID *))v12)(
                  &v22,
                  v12,
                  &GUID_00000035_0000_0000_c000_000000000046,
                  &Ptr);
          if ( v15 >= 0 )
          {
            if ( (v22 & 4) != 0 )
              goto LABEL_25;
            v17 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                      + 56))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
            AcquireSRWLockExclusive(v17);
            v18 = **(void ***)(v12 + 24);
            if ( v18 )
            {
              v19 = DecodePointer(v18);
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)v19 + 8LL))(v19);
            }
            else
            {
              v19 = 0;
              **(_QWORD **)(v12 + 24) = EncodePointer(Ptr);
            }
            if ( v17 )
              ReleaseSRWLockExclusive(v17);
            if ( v19 )
            {
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
            }
            else
            {
LABEL_25:
              v19 = Ptr;
            }
            *a2 = v19;
            return 0;
          }
          return (unsigned int)v15;
        }
      }
      v5 += 8LL;
    }
    RoOriginateError(2147746065LL, string);
    return 2147746065LL;
  }
}

```

## disassembly

```asm
0x18000f000  mov     [rsp+arg_10], rbx
0x18000f005  push    rbp
0x18000f006  push    rsi
0x18000f007  push    rdi
0x18000f008  push    r14
0x18000f00a  push    r15
0x18000f00c  sub     rsp, 70h
0x18000f010  mov     rax, cs:__security_cookie
0x18000f017  xor     rax, rsp
0x18000f01a  mov     [rsp+98h+var_30], rax
0x18000f01f  mov     r14, rdx
0x18000f022  mov     rbp, rcx
0x18000f025  xor     r9d, r9d; Context
0x18000f028  xor     r8d, r8d; Parameter
0x18000f02b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000f032  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000f039  call    cs:__imp_InitOnceExecuteOnce
0x18000f03f  mov     cs:byte_180044928, 1
0x18000f046  xor     r15d, r15d
0x18000f049  mov     [r14], r15
0x18000f04c  mov     [rsp+98h+hasEmbedNull], r15d
0x18000f051  mov     rcx, rbp; string
0x18000f054  call    cs:__imp_WindowsIsStringEmpty
0x18000f05a  test    eax, eax
0x18000f05c  jnz     loc_18000F1C3
0x18000f062  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x18000f067  mov     rcx, rbp; string
0x18000f06a  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18000f070  test    eax, eax
0x18000f072  js      loc_18000F1C3
0x18000f078  cmp     [rsp+98h+hasEmbedNull], 1
0x18000f07d  jz      loc_18000F1C3
0x18000f083  xor     edx, edx; length
0x18000f085  mov     rcx, rbp; string
0x18000f088  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f08e  mov     rsi, rax
0x18000f091  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f098  mov     rax, [rcx+28h]
0x18000f09c  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a8  lea     rbx, [rax+8]
0x18000f0ac  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f0b3  mov     rax, [rcx+30h]
0x18000f0b7  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0c3  mov     rdi, rax
0x18000f0c6  cmp     rbx, rdi
0x18000f0c9  jnb     loc_18000F2F1
0x18000f0cf  mov     rax, [rbx]
0x18000f0d2  test    rax, rax
0x18000f0d5  jz      short loc_18000F10A
0x18000f0d7  mov     rax, [rax+8]
0x18000f0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e0  mov     rcx, rsi
0x18000f0e3  sub     rax, rsi
0x18000f0e6  nop     word ptr [rax+rax+00000000h]
0x18000f0f0  movzx   r8d, word ptr [rcx]
0x18000f0f4  movzx   edx, word ptr [rcx+rax]
0x18000f0f8  sub     r8d, edx
0x18000f0fb  jnz     short loc_18000F105
0x18000f0fd  add     rcx, 2
0x18000f101  test    edx, edx
0x18000f103  jnz     short loc_18000F0F0
0x18000f105  test    r8d, r8d
0x18000f108  jz      short loc_18000F110
0x18000f10a  add     rbx, 8
0x18000f10e  jmp     short loc_18000F0C6
0x18000f110  lfence
0x18000f113  mov     [rsp+98h+var_5C], 1
0x18000f11b  mov     rbx, [rbx]
0x18000f11e  mov     [r14], r15
0x18000f121  mov     [rsp+98h+Ptr], r15
0x18000f126  mov     rax, [rbx+18h]
0x18000f12a  mov     rcx, [rax]
0x18000f12d  test    rcx, rcx
0x18000f130  jz      loc_18000F206
0x18000f136  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f13d  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f144  mov     rax, [rax+38h]
0x18000f148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f14d  mov     rdi, rax
0x18000f150  mov     rcx, rax; SRWLock
0x18000f153  call    cs:__imp_AcquireSRWLockShared
0x18000f159  mov     rcx, [rbx+18h]
0x18000f15d  mov     rcx, [rcx]; Ptr
0x18000f160  test    rcx, rcx
0x18000f163  jz      loc_18000F291
0x18000f169  call    cs:__imp_DecodePointer
0x18000f16f  mov     r9, rax
0x18000f172  mov     [rsp+98h+Ptr], rax
0x18000f177  mov     rcx, [rax]
0x18000f17a  mov     rax, [rcx]
0x18000f17d  mov     r8, r14
0x18000f180  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000f187  mov     rcx, r9
0x18000f18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f18f  mov     esi, eax
0x18000f191  test    rdi, rdi
0x18000f194  jz      short loc_18000F1A0
0x18000f196  mov     rcx, rdi; SRWLock
0x18000f199  call    cs:__imp_ReleaseSRWLockShared
0x18000f19f  nop
0x18000f1a0  mov     eax, esi
0x18000f1a2  mov     rcx, [rsp+98h+var_30]
0x18000f1a7  xor     rcx, rsp; StackCookie
0x18000f1aa  call    __security_check_cookie
0x18000f1af  mov     rbx, [rsp+98h+arg_10]
0x18000f1b7  add     rsp, 70h
0x18000f1bb  pop     r15
0x18000f1bd  pop     r14
0x18000f1bf  pop     rdi
0x18000f1c0  pop     rsi
0x18000f1c1  pop     rbp
0x18000f1c2  retn
0x18000f1c3  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18000f1ca  movups  [rsp+98h+var_58], xmm0
0x18000f1cf  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000f1d6  movups  xmmword ptr [rsp+98h+var_48], xmm1
0x18000f1db  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18000f1e3  movsd   qword ptr [rsp+98h+var_48+0Eh], xmm0
0x18000f1e9  lea     r8, [rsp+98h+var_58]
0x18000f1ee  mov     edx, 12h
0x18000f1f3  mov     ecx, 80070057h
0x18000f1f8  call    cs:__imp_RoOriginateErrorW
0x18000f1fe  nop
0x18000f1ff  mov     eax, 80070057h
0x18000f204  jmp     short loc_18000F1A2
0x18000f206  lea     r9, [rsp+98h+Ptr]
0x18000f20b  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x18000f212  mov     rdx, rbx
0x18000f215  lea     rcx, [rsp+98h+var_5C]
0x18000f21a  mov     rax, [rbx]
0x18000f21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f222  mov     esi, eax
0x18000f224  test    eax, eax
0x18000f226  js      loc_18000F1A0
0x18000f22c  test    byte ptr [rsp+98h+var_5C], 4
0x18000f231  jnz     short loc_18000F281
0x18000f233  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f23a  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000f241  mov     rax, [rax+38h]
0x18000f245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f24a  mov     rsi, rax
0x18000f24d  mov     rcx, rax; SRWLock
0x18000f250  call    cs:__imp_AcquireSRWLockExclusive
0x18000f256  mov     rcx, [rbx+18h]
0x18000f25a  mov     rcx, [rcx]; Ptr
0x18000f25d  test    rcx, rcx
0x18000f260  jnz     short loc_18000F2B3
0x18000f262  mov     rdi, r15
0x18000f265  mov     rcx, [rsp+98h+Ptr]; Ptr
0x18000f26a  call    cs:__imp_EncodePointer
0x18000f270  mov     rcx, [rbx+18h]
0x18000f274  mov     [rcx], rax
0x18000f277  test    rsi, rsi
0x18000f27a  jnz     short loc_18000F2A8
0x18000f27c  test    rdi, rdi
0x18000f27f  jnz     short loc_18000F2CD
0x18000f281  mov     rdi, [rsp+98h+Ptr]
0x18000f286  mov     [r14], rdi
0x18000f289  mov     esi, r15d
0x18000f28c  jmp     loc_18000F1A0
0x18000f291  test    rdi, rdi
0x18000f294  jz      loc_18000F206
0x18000f29a  mov     rcx, rdi; SRWLock
0x18000f29d  call    cs:__imp_ReleaseSRWLockShared
0x18000f2a3  jmp     loc_18000F206
0x18000f2a8  mov     rcx, rsi; SRWLock
0x18000f2ab  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f2b1  jmp     short loc_18000F27C
0x18000f2b3  call    cs:__imp_DecodePointer
0x18000f2b9  mov     rdi, rax
0x18000f2bc  mov     rcx, [rax]
0x18000f2bf  mov     rax, [rcx+8]
0x18000f2c3  mov     rcx, rdi
0x18000f2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2cb  jmp     short loc_18000F277
0x18000f2cd  mov     rcx, [rsp+98h+Ptr]
0x18000f2d2  mov     rax, [rcx]
0x18000f2d5  mov     rax, [rax+10h]
0x18000f2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2de  mov     rcx, [rsp+98h+Ptr]
0x18000f2e3  mov     rax, [rcx]
0x18000f2e6  mov     rax, [rax+10h]
0x18000f2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2ef  jmp     short loc_18000F286
0x18000f2f1  mov     rdx, rbp
0x18000f2f4  mov     ecx, 80040111h
0x18000f2f9  call    cs:__imp_RoOriginateError
0x18000f2ff  nop
0x18000f300  mov     eax, 80040111h
0x18000f305  jmp     loc_18000F1A2
```
