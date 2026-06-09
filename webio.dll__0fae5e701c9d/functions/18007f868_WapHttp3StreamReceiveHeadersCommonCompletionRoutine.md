# WapHttp3StreamReceiveHeadersCommonCompletionRoutine

- ea: `0x18007f868`
- end: `0x18007fc70`
- name: `WapHttp3StreamReceiveHeadersCommonCompletionRoutine`
- size: `1032`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180079c10`
- `0x18007fc80`

## callees

- `0x180013820`
- `0x1800391c0`
- `0x180043f00`
- `0x18005fd88`
- `0x1800722f0`
- `0x18007b2ac`
- `0x18007ec98`
- `0x18007edb8`
- `0x18007ee9c`
- `0x18007f260`
- `0x18007f868`
- `0x18008033c`
- `0x180080830`
- `0x180091678`
- `0x180092564`
- `0x180093944`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fb25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fbad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fb25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fbad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fbe5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fbe5`

## pseudocode

```c
__int64 __fastcall WapHttp3StreamReceiveHeadersCommonCompletionRoutine(
        __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        _QWORD *a4)
{
  __int64 v4; // rbx
  unsigned int *v5; // r13
  __int64 v9; // rcx
  __int64 v10; // r8
  _QWORD *v11; // r15
  unsigned int **v12; // r12
  unsigned __int64 v13; // rdi
  unsigned int Error; // edi
  _QWORD *v15; // r14
  struct _RTL_CRITICAL_SECTION *v16; // r14
  unsigned __int64 v17; // rcx
  void *v18; // rdx
  unsigned __int64 v19; // rax
  unsigned int v20; // r15d
  _QWORD *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  void (__fastcall *v25)(__int64, __int64, __int64); // rax
  size_t Size; // [rsp+70h] [rbp-29h] BYREF
  unsigned int *Heap; // [rsp+78h] [rbp-21h] BYREF
  void *Src; // [rsp+80h] [rbp-19h] BYREF
  __int64 v30; // [rsp+88h] [rbp-11h] BYREF
  _QWORD *v31; // [rsp+90h] [rbp-9h]
  int v32; // [rsp+98h] [rbp-1h] BYREF

  v4 = *(_QWORD *)(a1 + 8);
  v5 = 0;
  v31 = a4;
  Src = 0;
  LODWORD(Size) = 0;
  v32 = 0;
  WapHttp3StreamUpdateTimerOnCompletion(v4, v4 + 104);
  v11 = (_QWORD *)(v4 + 24);
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_iD(1050, 229, v10, *v11, a2);
  v12 = (unsigned int **)(v4 + 312);
  if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
    McTemplateU0ppxppqxxxtt_EventWriteTransfer(
      a1 + 24,
      (unsigned int)NetSocketRecvEntityComplete,
      *(_QWORD *)(v4 + 8),
      0,
      0,
      (char)*v12,
      a1 + 24,
      a2,
      a3,
      *v11,
      *(_DWORD *)(v4 + 320),
      0,
      1);
  if ( a2 == 234 )
  {
    v13 = *(unsigned int *)(v4 + 320);
    if ( v13 >= a3 )
    {
      v15 = (_QWORD *)(v4 + 312);
    }
    else
    {
      if ( a3 > 0xFFFFFFFF )
      {
        Error = 1359;
LABEL_29:
        v16 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
        v20 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
        goto LABEL_30;
      }
      LODWORD(v13) = a3;
      Heap = (unsigned int *)WxAllocateHeapEx(v9, (unsigned int)a3);
      if ( !Heap )
      {
        Error = 8;
        goto LABEL_29;
      }
      v15 = (_QWORD *)(v4 + 312);
      v30 = *(_QWORD *)(v4 + 312);
      WxFreeHeapEx(&v30);
      *(_QWORD *)(v4 + 312) = Heap;
      *(_DWORD *)(v4 + 320) = v13;
    }
    if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
    {
      v15 = (_QWORD *)(v4 + 312);
      McTemplateU0ppxppqxxxtt_EventWriteTransfer(
        a1 + 24,
        (unsigned int)NetSocketRecvEntity,
        *(_QWORD *)(v4 + 8),
        0,
        0,
        *(_QWORD *)(v4 + 312),
        a1 + 24,
        0,
        0,
        *(_QWORD *)(v4 + 24),
        v13,
        0,
        1);
    }
    a2 = WaHttpApiStreamReceiveHeaders(**(_QWORD **)(v4 + 40), *v11, 1, *v15, *(_DWORD *)(v4 + 320), 0, (__int64)&v32);
    if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
      McTemplateU0ppxppqxxxtt_EventWriteTransfer(
        v32,
        (unsigned int)NetSocketRecvEntityComplete,
        *(_QWORD *)(v4 + 8),
        0,
        0,
        *v15,
        a1 + 24,
        a2,
        v32,
        *v11,
        *(_DWORD *)(v4 + 320),
        0,
        1);
    if ( a2 == 234 )
    {
      if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
        WPP_SF_(538, 230, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
      a2 = 1359;
      goto LABEL_22;
    }
  }
  if ( a2 )
  {
LABEL_22:
    Error = WapHttp3StreamGetError(a2, v4);
    goto LABEL_29;
  }
  Error = WaHttp2ConvertHPackToHttp11(*((_QWORD *)*v12 + 1), **v12, (__int64 *)&Src, &Size);
  Heap = *v12;
  WxFreeHeapEx(&Heap);
  *v12 = 0;
  *(_DWORD *)(v4 + 320) = 0;
  if ( Error )
  {
    v5 = (unsigned int *)Src;
    goto LABEL_29;
  }
  v16 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
  v17 = (unsigned int)Size;
  v18 = Src;
  *(_QWORD *)(v4 + 328) = Src;
  *(_QWORD *)(v4 + 336) = (unsigned int)v17;
  v19 = *(_QWORD *)(a1 + 144);
  if ( v19 >= v17 )
    LODWORD(v19) = v17;
  v20 = v19;
  memcpy_0(*(void **)(a1 + 136), v18, (unsigned int)v19);
  *(_DWORD *)(v4 + 340) += v20;
  if ( *(_DWORD *)(v4 + 336) == *(_DWORD *)(v4 + 340) )
  {
    v5 = *(unsigned int **)(v4 + 328);
    *(_QWORD *)(v4 + 328) = 0;
    *(_QWORD *)(v4 + 336) = 0;
  }
LABEL_30:
  *(_QWORD *)(v4 + 304) = 0;
  WapHttp3StreamCheckForGoawayResend(v4, Error);
  WapHttp3StreamCheckForDowngrade(v4, Error);
  WapHttp3StreamCheckForReset(v4, Error);
  LeaveCriticalSection(v16);
  if ( v5 )
  {
    Heap = v5;
    WxFreeHeapEx(&Heap);
  }
  v21 = v31;
  *(_DWORD *)(a1 + 112) = Error;
  *(_QWORD *)(a1 + 120) = v20;
  *v21 = v20;
  if ( !*(_BYTE *)(a1 + 132) )
  {
    v22 = *(_QWORD *)(a1 + 120);
    v23 = *(unsigned int *)(a1 + 112);
    v24 = *(_QWORD *)(a1 + 104);
    v25 = *(void (__fastcall **)(__int64, __int64, __int64))(a1 + 96);
    *(_BYTE *)(a1 + 132) = 1;
    v25(v24, v23, v22);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF) == 1 )
    WapHttpApiFreeIoContext(a1);
  return Error;
}

```

## disassembly

```asm
0x18007f868  push    rbp
0x18007f86a  push    rbx
0x18007f86b  push    rsi
0x18007f86c  push    rdi
0x18007f86d  push    r12
0x18007f86f  push    r13
0x18007f871  push    r14
0x18007f873  push    r15
0x18007f875  lea     rbp, [rsp-1Fh]
0x18007f87a  sub     rsp, 0B8h
0x18007f881  mov     rax, cs:__security_cookie
0x18007f888  xor     rax, rsp
0x18007f88b  mov     [rbp+57h+var_50], rax
0x18007f88f  mov     rbx, [rcx+8]
0x18007f893  xor     r13d, r13d
0x18007f896  mov     edi, edx
0x18007f898  mov     [rbp+57h+var_60], r9
0x18007f89c  mov     rsi, rcx
0x18007f89f  mov     [rbp+57h+Src], r13
0x18007f8a3  mov     rcx, rbx
0x18007f8a6  mov     dword ptr [rbp+57h+Size], r13d
0x18007f8aa  lea     rdx, [rbx+68h]
0x18007f8ae  mov     [rbp+57h+var_58], r13d
0x18007f8b2  mov     r14, r8
0x18007f8b5  call    WapHttp3StreamUpdateTimerOnCompletion
0x18007f8ba  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007f8c1  lea     r15, [rbx+18h]
0x18007f8c5  jz      short loc_18007F8DD
0x18007f8c7  mov     r9, [r15]
0x18007f8ca  mov     edx, 0E5h
0x18007f8cf  mov     ecx, 41Ah
0x18007f8d4  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18007f8d8  call    WPP_SF_iD
0x18007f8dd  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 20h
0x18007f8e4  lea     r12, [rbx+138h]
0x18007f8eb  jz      short loc_18007F940
0x18007f8ed  mov     eax, [rbx+140h]
0x18007f8f3  lea     rcx, [rsi+18h]
0x18007f8f7  mov     r8, [rbx+8]
0x18007f8fb  lea     rdx, NetSocketRecvEntityComplete
0x18007f902  mov     [rsp+0F0h+var_90], 1
0x18007f90a  xor     r9d, r9d
0x18007f90d  mov     [rsp+0F0h+var_98], r13d
0x18007f912  mov     [rsp+0F0h+var_A0], rax
0x18007f917  mov     rax, [r15]
0x18007f91a  mov     [rsp+0F0h+var_A8], rax
0x18007f91f  mov     rax, [r12]
0x18007f923  mov     [rsp+0F0h+var_B0], r14
0x18007f928  mov     [rsp+0F0h+var_B8], edi
0x18007f92c  mov     [rsp+0F0h+var_C0], rcx
0x18007f931  mov     [rsp+0F0h+var_C8], rax
0x18007f936  mov     [rsp+0F0h+var_D0], r13
0x18007f93b  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x18007f940  cmp     edi, 0EAh
0x18007f946  jnz     loc_18007FACC
0x18007f94c  mov     edi, [rbx+140h]
0x18007f952  cmp     rdi, r14
0x18007f955  jnb     short loc_18007F9AD
0x18007f957  mov     eax, 0FFFFFFFFh
0x18007f95c  cmp     r14, rax
0x18007f95f  jbe     short loc_18007F96B
0x18007f961  mov     edi, 54Fh
0x18007f966  jmp     loc_18007FBA3
0x18007f96b  mov     edx, r14d
0x18007f96e  mov     edi, r14d
0x18007f971  call    WxAllocateHeapEx
0x18007f976  mov     [rbp+57h+var_78], rax
0x18007f97a  test    rax, rax
0x18007f97d  jnz     short loc_18007F987
0x18007f97f  lea     edi, [rax+8]
0x18007f982  jmp     loc_18007FBA3
0x18007f987  lea     r14, [rbx+138h]
0x18007f98e  mov     rax, [r14]
0x18007f991  lea     rcx, [rbp+57h+var_68]
0x18007f995  mov     [rbp+57h+var_68], rax
0x18007f999  call    WxFreeHeapEx
0x18007f99e  mov     rax, [rbp+57h+var_78]
0x18007f9a2  mov     [r14], rax
0x18007f9a5  mov     [rbx+140h], edi
0x18007f9ab  jmp     short loc_18007F9B0
0x18007f9ad  mov     r14, r12
0x18007f9b0  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 20h
0x18007f9b7  jz      short loc_18007FA10
0x18007f9b9  mov     r8, [rbx+8]
0x18007f9bd  lea     rcx, [rsi+18h]
0x18007f9c1  mov     [rsp+0F0h+var_90], 1
0x18007f9c9  lea     r14, [rbx+138h]
0x18007f9d0  xor     edx, edx
0x18007f9d2  mov     eax, edi
0x18007f9d4  mov     [rsp+0F0h+var_98], edx
0x18007f9d8  xor     r9d, r9d
0x18007f9db  mov     [rsp+0F0h+var_A0], rax
0x18007f9e0  mov     rax, [rbx+18h]
0x18007f9e4  mov     [rsp+0F0h+var_A8], rax
0x18007f9e9  mov     rax, [r14]
0x18007f9ec  mov     [rsp+0F0h+var_B0], rdx
0x18007f9f1  mov     [rsp+0F0h+var_B8], edx
0x18007f9f5  mov     [rsp+0F0h+var_C0], rcx
0x18007f9fa  mov     [rsp+0F0h+var_C8], rax
0x18007f9ff  mov     [rsp+0F0h+var_D0], rdx
0x18007fa04  lea     rdx, NetSocketRecvEntity
0x18007fa0b  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x18007fa10  mov     rcx, [rbx+28h]
0x18007fa14  lea     rax, [rbp+57h+var_58]
0x18007fa18  mov     r9, [r14]
0x18007fa1b  mov     r8d, 1
0x18007fa21  mov     rdx, [r15]
0x18007fa24  mov     [rsp+0F0h+var_C0], rax
0x18007fa29  mov     eax, [rbx+140h]
0x18007fa2f  mov     rcx, [rcx]
0x18007fa32  mov     [rsp+0F0h+var_C8], r13
0x18007fa37  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18007fa3b  call    WaHttpApiStreamReceiveHeaders
0x18007fa40  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 20h
0x18007fa47  mov     edi, eax
0x18007fa49  jz      short loc_18007FAA0
0x18007fa4b  mov     eax, [rbx+140h]
0x18007fa51  lea     r8, [rsi+18h]
0x18007fa55  mov     ecx, [rbp+57h+var_58]
0x18007fa58  lea     rdx, NetSocketRecvEntityComplete
0x18007fa5f  mov     [rsp+0F0h+var_90], 1
0x18007fa67  xor     r9d, r9d
0x18007fa6a  mov     [rsp+0F0h+var_98], r13d
0x18007fa6f  mov     [rsp+0F0h+var_A0], rax
0x18007fa74  mov     rax, [r15]
0x18007fa77  mov     [rsp+0F0h+var_A8], rax
0x18007fa7c  mov     rax, [r14]
0x18007fa7f  mov     [rsp+0F0h+var_B0], rcx
0x18007fa84  mov     [rsp+0F0h+var_B8], edi
0x18007fa88  mov     [rsp+0F0h+var_C0], r8
0x18007fa8d  mov     r8, [rbx+8]
0x18007fa91  mov     [rsp+0F0h+var_C8], rax
0x18007fa96  mov     [rsp+0F0h+var_D0], r13
0x18007fa9b  call    McTemplateU0ppxppqxxxtt_EventWriteTransfer
0x18007faa0  cmp     edi, 0EAh
0x18007faa6  jnz     short loc_18007FACC
0x18007faa8  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007faaf  jz      short loc_18007FAC5
0x18007fab1  lea     edx, [rdi-4]
0x18007fab4  mov     ecx, 21Ah
0x18007fab9  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007fac0  call    WPP_SF_
0x18007fac5  mov     edi, 54Fh
0x18007faca  jmp     short loc_18007FAD0
0x18007facc  test    edi, edi
0x18007face  jz      short loc_18007FAE1
0x18007fad0  mov     rdx, rbx
0x18007fad3  mov     ecx, edi
0x18007fad5  call    WapHttp3StreamGetError
0x18007fada  mov     edi, eax
0x18007fadc  jmp     loc_18007FBA3
0x18007fae1  mov     rcx, [r12]
0x18007fae5  lea     r9, [rbp+57h+Size]
0x18007fae9  lea     r8, [rbp+57h+Src]
0x18007faed  mov     edx, [rcx]
0x18007faef  mov     rcx, [rcx+8]
0x18007faf3  call    WaHttp2ConvertHPackToHttp11
0x18007faf8  mov     edi, eax
0x18007fafa  lea     rcx, [rbp+57h+var_78]
0x18007fafe  mov     rax, [r12]
0x18007fb02  mov     [rbp+57h+var_78], rax
0x18007fb06  call    WxFreeHeapEx
0x18007fb0b  mov     [r12], r13
0x18007fb0f  mov     [rbx+140h], r13d
0x18007fb16  test    edi, edi
0x18007fb18  jnz     loc_18007FB9F
0x18007fb1e  lea     r14, [rbx+30h]
0x18007fb22  mov     rcx, r14; lpCriticalSection
0x18007fb25  call    cs:__imp_EnterCriticalSection
0x18007fb2c  nop     dword ptr [rax+rax+00h]
0x18007fb31  mov     ecx, dword ptr [rbp+57h+Size]
0x18007fb34  mov     rdx, [rbp+57h+Src]; Src
0x18007fb38  mov     [rbx+148h], rdx
0x18007fb3f  mov     [rbx+150h], ecx
0x18007fb45  mov     [rbx+154h], r13d
0x18007fb4c  mov     rax, [rsi+90h]
0x18007fb53  cmp     rax, rcx
0x18007fb56  cmovnb  eax, ecx
0x18007fb59  mov     rcx, [rsi+88h]; void *
0x18007fb60  mov     r8d, eax; Size
0x18007fb63  mov     r15d, eax
0x18007fb66  call    memcpy_0
0x18007fb6b  add     [rbx+154h], r15d
0x18007fb72  mov     eax, [rbx+150h]
0x18007fb78  cmp     eax, [rbx+154h]
0x18007fb7e  jnz     short loc_18007FBB9
0x18007fb80  mov     r13, [rbx+148h]
0x18007fb87  mov     qword ptr [rbx+148h], 0
0x18007fb92  mov     qword ptr [rbx+150h], 0
0x18007fb9d  jmp     short loc_18007FBB9
0x18007fb9f  mov     r13, [rbp+57h+Src]
0x18007fba3  lea     r14, [rbx+30h]
0x18007fba7  xor     r15d, r15d
0x18007fbaa  mov     rcx, r14; lpCriticalSection
0x18007fbad  call    cs:__imp_EnterCriticalSection
0x18007fbb4  nop     dword ptr [rax+rax+00h]
0x18007fbb9  mov     edx, edi
0x18007fbbb  mov     qword ptr [rbx+130h], 0
0x18007fbc6  mov     rcx, rbx
0x18007fbc9  call    WapHttp3StreamCheckForGoawayResend
0x18007fbce  mov     edx, edi
0x18007fbd0  mov     rcx, rbx
0x18007fbd3  call    WapHttp3StreamCheckForDowngrade
0x18007fbd8  mov     edx, edi
0x18007fbda  mov     rcx, rbx
0x18007fbdd  call    WapHttp3StreamCheckForReset
0x18007fbe2  mov     rcx, r14; lpCriticalSection
0x18007fbe5  call    cs:__imp_LeaveCriticalSection
0x18007fbec  nop     dword ptr [rax+rax+00h]
0x18007fbf1  test    r13, r13
0x18007fbf4  jz      short loc_18007FC03
0x18007fbf6  lea     rcx, [rbp+57h+var_78]
0x18007fbfa  mov     [rbp+57h+var_78], r13
0x18007fbfe  call    WxFreeHeapEx
0x18007fc03  mov     rcx, [rbp+57h+var_60]
0x18007fc07  mov     eax, r15d
0x18007fc0a  mov     [rsi+70h], edi
0x18007fc0d  mov     [rsi+78h], rax
0x18007fc11  mov     [rcx], rax
0x18007fc14  cmp     byte ptr [rsi+84h], 0
0x18007fc1b  jnz     short loc_18007FC38
0x18007fc1d  mov     r8, [rsi+78h]
0x18007fc21  mov     edx, [rsi+70h]
0x18007fc24  mov     rcx, [rsi+68h]
0x18007fc28  mov     rax, [rsi+60h]
0x18007fc2c  mov     byte ptr [rsi+84h], 1
0x18007fc33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc38  or      eax, 0FFFFFFFFh
0x18007fc3b  lock xadd [rsi+4], eax
0x18007fc40  cmp     eax, 1
0x18007fc43  jnz     short loc_18007FC4D
0x18007fc45  mov     rcx, rsi
0x18007fc48  call    WapHttpApiFreeIoContext
0x18007fc4d  mov     eax, edi
0x18007fc4f  mov     rcx, [rbp+57h+var_50]
0x18007fc53  xor     rcx, rsp; StackCookie
0x18007fc56  call    __security_check_cookie
0x18007fc5b  add     rsp, 0B8h
0x18007fc62  pop     r15
0x18007fc64  pop     r14
0x18007fc66  pop     r13
0x18007fc68  pop     r12
0x18007fc6a  pop     rdi
0x18007fc6b  pop     rsi
0x18007fc6c  pop     rbx
0x18007fc6d  pop     rbp
0x18007fc6e  retn
```
