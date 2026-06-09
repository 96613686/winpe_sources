# CXxxJobImpl::EnqueueCallback(void *)

- ea: `0x1800806c8`
- end: `0x1800808db`
- name: `?EnqueueCallback@CXxxJobImpl@@IEAAJPEAX@Z`
- size: `531`
- prototype: `__int64 __fastcall(CXxxJobImpl *__hidden this, void *)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000da3c`
- `0x18001d254`
- `0x18001f420`
- `0x180024fac`
- `0x18003f920`
- `0x1800808f0`

## callees

- `0x1800806c8`
- `0x18008dff0`
- `0x18009b050`
- `0x18009b24c`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080802`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800808af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080802`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800808af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008070a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008070a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180080755`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180080755`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800807ad`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800807ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080766`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008075e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008075e`

## string_xrefs

- `0x180080784`: `create callback thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXxxJobImpl::EnqueueCallback(CXxxJobImpl *this, void *a2)
{
  unsigned __int64 v3; // rbx
  HANDLE *v4; // r14
  signed int LastError; // eax
  signed int v6; // esi
  HANDLE Thread; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  void *v14; // [rsp+30h] [rbp-38h] BYREF
  DWORD dwindex[2]; // [rsp+38h] [rbp-30h] BYREF

  v14 = a2;
  v3 = ((unsigned __int64)this + 184) & -(__int64)(this != 0);
  if ( v3 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  *(_QWORD *)dwindex = v3;
  if ( *((_DWORD *)this + 72) )
  {
    (*(void (__fastcall **)(CXxxJobImpl *, void **))(*(_QWORD *)this + 32LL))(this, &v14);
    goto LABEL_28;
  }
  if ( *((_DWORD *)this + 80) )
  {
LABEL_14:
    v6 = -2147024882;
    while ( 1 )
    {
      v8 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( v8 )
        break;
      if ( !(unsigned int)NeedToRetryAfterWait(-2147024882, L"enqueue callback") )
        goto LABEL_17;
    }
    v8[2] = 0;
    *v8 = 0;
    v8[1] = 0;
    v8[2] = v14;
    v10 = *((_QWORD *)this + 45);
    *((_QWORD *)this + 47) = v10;
    ++*((_DWORD *)this + 92);
    *v8 = v10;
    if ( v10 )
    {
      v8[1] = *(_QWORD *)(v10 + 8);
      *(_QWORD *)(v10 + 8) = v8;
      v12 = (_QWORD *)v8[1];
      if ( v12 )
      {
        *v12 = v9;
        goto LABEL_24;
      }
    }
    else
    {
      v11 = (_QWORD *)*((_QWORD *)this + 44);
      if ( v11 )
        *v11 = v9;
      v9[1] = *((_QWORD *)this + 44);
      *((_QWORD *)this + 44) = v9;
      if ( *((_QWORD *)this + 45) )
        goto LABEL_24;
    }
    *((_QWORD *)this + 45) = v9;
LABEL_24:
    *((_QWORD *)this + 47) = v9;
LABEL_28:
    if ( v3 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
    return 0;
  }
  v4 = (HANDLE *)((char *)this + 272);
  if ( *((_QWORD *)this + 34) )
  {
    dwindex[0] = 0;
    CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)this + 34, dwindex);
    CloseHandle(*v4);
  }
  do
  {
    Thread = CreateThread(0, 0, CXxxJobImpl::CallbackWorker, this, 0, 0);
    *v4 = Thread;
    if ( Thread )
    {
      *((_DWORD *)this + 80) = 1;
      goto LABEL_14;
    }
    LastError = GetLastError();
    v6 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v6 = LastError;
    if ( v6 >= 0 )
      v6 = -2147418113;
  }
  while ( (unsigned int)NeedToRetryAfterWait(v6, L"create callback thread") );
LABEL_17:
  if ( v3 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800806c8  mov     [rsp+arg_10], rbx
0x1800806cd  mov     [rsp+arg_18], rbp
0x1800806d2  push    rsi
0x1800806d3  push    rdi
0x1800806d4  push    r14
0x1800806d6  sub     rsp, 50h
0x1800806da  mov     rax, cs:__security_cookie
0x1800806e1  xor     rax, rsp
0x1800806e4  mov     [rsp+68h+var_28], rax
0x1800806e9  mov     rdi, rcx
0x1800806ec  mov     [rsp+68h+var_38], rdx
0x1800806f1  mov     rax, rcx
0x1800806f4  add     rcx, 0B8h
0x1800806fb  neg     rax
0x1800806fe  sbb     rbx, rbx
0x180080701  and     rbx, rcx
0x180080704  jz      short loc_180080710
0x180080706  lea     rcx, [rbx+8]; lpCriticalSection
0x18008070a  call    cs:__imp_EnterCriticalSection
0x180080710  mov     qword ptr [rsp+68h+dwindex], rbx
0x180080715  xor     ebp, ebp
0x180080717  cmp     [rdi+120h], ebp
0x18008071d  jnz     loc_180080891
0x180080723  cmp     [rdi+140h], ebp
0x180080729  jnz     loc_1800807C5
0x18008072f  lea     r14, [rdi+110h]
0x180080736  cmp     [r14], rbp
0x180080739  jz      short loc_180080796
0x18008073b  mov     [rsp+68h+dwindex], ebp
0x18008073f  lea     rax, [rsp+68h+dwindex]
0x180080744  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180080749  mov     r9, r14; pHandles
0x18008074c  lea     r8d, [rbp+1]; cHandles
0x180080750  or      edx, 0FFFFFFFFh; dwTimeout
0x180080753  xor     ecx, ecx; dwFlags
0x180080755  call    cs:__imp_CoWaitForMultipleHandles
0x18008075b  mov     rcx, [r14]; hObject
0x18008075e  call    cs:__imp_CloseHandle
0x180080764  jmp     short loc_180080796
0x180080766  call    cs:__imp_GetLastError
0x18008076c  movzx   esi, ax
0x18008076f  or      esi, 80070000h
0x180080775  test    eax, eax
0x180080777  cmovle  esi, eax
0x18008077a  mov     eax, 8000FFFFh
0x18008077f  test    esi, esi
0x180080781  cmovns  esi, eax
0x180080784  lea     rdx, aCreateCallback; "create callback thread"
0x18008078b  mov     ecx, esi; int
0x18008078d  call    ?NeedToRetryAfterWait@@YAHJPEB_W@Z; NeedToRetryAfterWait(long,wchar_t const *)
0x180080792  test    eax, eax
0x180080794  jz      short loc_1800807F5
0x180080796  mov     [rsp+68h+lpThreadId], rbp; lpThreadId
0x18008079b  mov     dword ptr [rsp+68h+lpdwindex], ebp; dwCreationFlags
0x18008079f  mov     r9, rdi; lpParameter
0x1800807a2  lea     r8, ?CallbackWorker@CXxxJobImpl@@CAKPEAX@Z; lpStartAddress
0x1800807a9  xor     edx, edx; dwStackSize
0x1800807ab  xor     ecx, ecx; lpThreadAttributes
0x1800807ad  call    cs:__imp_CreateThread
0x1800807b3  test    rax, rax
0x1800807b6  mov     [r14], rax
0x1800807b9  jz      short loc_180080766
0x1800807bb  mov     dword ptr [rdi+140h], 1
0x1800807c5  mov     esi, 8007000Eh
0x1800807ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800807d1  mov     ecx, 18h; unsigned __int64
0x1800807d6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800807db  mov     rcx, rax
0x1800807de  test    rax, rax
0x1800807e1  jnz     short loc_18008080D
0x1800807e3  lea     rdx, aEnqueueCallbac; "enqueue callback"
0x1800807ea  mov     ecx, esi; int
0x1800807ec  call    ?NeedToRetryAfterWait@@YAHJPEB_W@Z; NeedToRetryAfterWait(long,wchar_t const *)
0x1800807f1  test    eax, eax
0x1800807f3  jnz     short loc_1800807CA
0x1800807f5  test    rbx, rbx
0x1800807f8  jz      loc_1800808B7
0x1800807fe  lea     rcx, [rbx+8]; lpCriticalSection
0x180080802  call    cs:__imp_LeaveCriticalSection
0x180080808  jmp     loc_1800808B7
0x18008080d  mov     [rax+10h], rbp
0x180080811  mov     [rax], rbp
0x180080814  mov     [rax+8], rbp
0x180080818  mov     rax, [rsp+68h+var_38]
0x18008081d  mov     [rcx+10h], rax
0x180080821  mov     rdx, [rdi+168h]
0x180080828  mov     [rdi+178h], rdx
0x18008082f  inc     dword ptr [rdi+170h]
0x180080835  mov     [rcx], rdx
0x180080838  test    rdx, rdx
0x18008083b  jnz     short loc_180080877
0x18008083d  mov     rax, [rdi+160h]
0x180080844  test    rax, rax
0x180080847  jz      short loc_18008084C
0x180080849  mov     [rax], rcx
0x18008084c  mov     rax, [rdi+160h]
0x180080853  mov     [rcx+8], rax
0x180080857  mov     [rdi+160h], rcx
0x18008085e  cmp     [rdi+168h], rbp
0x180080865  jnz     short loc_18008086E
0x180080867  mov     [rdi+168h], rcx
0x18008086e  mov     [rdi+178h], rcx
0x180080875  jmp     short loc_1800808A6
0x180080877  mov     rax, [rdx+8]
0x18008087b  mov     [rcx+8], rax
0x18008087f  mov     [rdx+8], rcx
0x180080883  mov     rax, [rcx+8]
0x180080887  test    rax, rax
0x18008088a  jz      short loc_180080867
0x18008088c  mov     [rax], rcx
0x18008088f  jmp     short loc_18008086E
0x180080891  mov     rax, [rdi]
0x180080894  lea     rdx, [rsp+68h+var_38]
0x180080899  mov     rcx, rdi
0x18008089c  mov     rax, [rax+20h]
0x1800808a0  call    _guard_dispatch_icall
0x1800808a5  nop
0x1800808a6  test    rbx, rbx
0x1800808a9  jz      short loc_1800808B5
0x1800808ab  lea     rcx, [rbx+8]; lpCriticalSection
0x1800808af  call    cs:__imp_LeaveCriticalSection
0x1800808b5  mov     esi, ebp
0x1800808b7  mov     eax, esi
0x1800808b9  mov     rcx, [rsp+68h+var_28]
0x1800808be  xor     rcx, rsp; StackCookie
0x1800808c1  call    __security_check_cookie
0x1800808c6  lea     r11, [rsp+68h+var_18]
0x1800808cb  mov     rbx, [r11+30h]
0x1800808cf  mov     rbp, [r11+38h]
0x1800808d3  mov     rsp, r11
0x1800808d6  pop     r14
0x1800808d8  pop     rdi
0x1800808d9  pop     rsi
0x1800808da  retn
```
