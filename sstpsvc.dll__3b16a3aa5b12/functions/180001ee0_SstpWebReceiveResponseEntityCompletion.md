# SstpWebReceiveResponseEntityCompletion

- ea: `0x180001ee0`
- end: `0x1800021dd`
- name: `SstpWebReceiveResponseEntityCompletion`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001ee0`
- `0x1800021f0`
- `0x180002908`
- `0x180002d70`
- `0x180006b64`
- `0x1800077bc`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001bd80`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002073`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001fa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002073`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000200a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000200a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001f4d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180001f4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001f67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180001f67`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001ffd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001ffd`

## pseudocode

```c
__int64 __fastcall SstpWebReceiveResponseEntityCompletion(__int64 a1, unsigned int a2, int a3)
{
  __int64 v3; // rdi
  RTL_SRWLOCK *v7; // rcx
  int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 result; // rax
  _QWORD *v13; // rsi
  char *v14; // rbx
  __int64 v15; // rax
  int v16; // [rsp+20h] [rbp-1028h] BYREF
  _BYTE v17[2044]; // [rsp+24h] [rbp-1024h] BYREF
  int v18; // [rsp+820h] [rbp-828h] BYREF
  _BYTE v19[2044]; // [rsp+824h] [rbp-824h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( a2 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"CoId=%hs:ReceiveResponseEntity fails with %d", v3 + 552, a2);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v16);
    }
    v13 = (_QWORD *)(a1 - 24);
    v14 = (char *)SstpSvcGlobals + 424;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 488));
    if ( (_QWORD *)*v13 == v13 )
    {
      v15 = *((_QWORD *)v14 + 5);
      *v13 = v15;
      v13[1] = v14 + 40;
      *(_QWORD *)(v15 + 8) = v13;
      *((_QWORD *)v14 + 5) = v13;
      ++*(_DWORD *)(v13[2] + 28LL);
      if ( ++*((_DWORD *)v14 + 5) >= *((_DWORD *)v14 + 4) )
      {
        FreeUnusedBufferPoolBlocks(v14);
        *((_DWORD *)v14 + 5) = 0;
      }
    }
    else
    {
      ++g_ulDoubleBufferFrees;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 64));
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 288));
    InitiateCallContextCleanup(v3, 1u);
  }
  else
  {
    v7 = (RTL_SRWLOCK *)SstpSvcGlobals;
    *(_DWORD *)(a1 + 92) = a3;
    *(_DWORD *)(a1 + 88) = *(_DWORD *)(v3 + 240);
    AcquireSRWLockShared(v7 + 96);
    v8 = *((_DWORD *)SstpSvcGlobals + 194);
    ReleaseSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
    if ( (v8 & 1) != 0 && v3 && *(_QWORD *)(v3 + 624) )
    {
      ProxySendToRelatedCtx((LPOVERLAPPED)a1);
    }
    else
    {
      v18 = 0;
      memset_0(v19, 0, sizeof(v19));
      v9 = *(_QWORD *)(a1 + 56);
      *(_QWORD *)(a1 + 56) = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 288));
      if ( *(_BYTE *)(v9 + 435) )
      {
        if ( (byte_18002D803 & 8) != 0 )
        {
          LOWORD(v18) = 0;
          FormatRRASErrorString(&v18, L"CoId=%hs:Dropping packet since disconnect in progress", v9 + 552);
          if ( (byte_18002D803 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v18);
        }
        LOBYTE(v10) = 1;
        FreeBufferToPool((char *)SstpSvcGlobals + 424, a1, v10);
      }
      else
      {
        *(_QWORD *)(a1 + 48) = a1 + 40;
        *(_QWORD *)(a1 + 40) = a1 + 40;
        v11 = *(_QWORD **)(v9 + 424);
        *(_QWORD *)(a1 + 40) = v9 + 416;
        *(_QWORD *)(a1 + 48) = v11;
        *v11 = a1 + 40;
        *(_QWORD *)(v9 + 424) = a1 + 40;
        if ( !*(_BYTE *)(v9 + 432) )
        {
          *(_BYTE *)(v9 + 432) = 1;
          _InterlockedIncrement((volatile signed __int32 *)(v9 + 208));
          SubmitThreadpoolWork(*(PTP_WORK *)(v9 + 336));
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 288));
    }
    PostReceiveOnCall(v3);
  }
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 208), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return (*(__int64 (**)(void))(v3 + 216))();
  return result;
}

```

## disassembly

```asm
0x180001ee0  mov     [rsp+arg_10], rbx
0x180001ee5  push    rbp
0x180001ee6  push    rsi
0x180001ee7  push    rdi
0x180001ee8  mov     eax, 1030h
0x180001eed  call    _alloca_probe
0x180001ef2  sub     rsp, rax
0x180001ef5  mov     rax, cs:__security_cookie
0x180001efc  xor     rax, rsp
0x180001eff  mov     [rsp+1048h+var_28], rax
0x180001f07  mov     rdi, [rcx+38h]
0x180001f0b  mov     rbp, r8
0x180001f0e  mov     ebx, edx
0x180001f10  mov     rsi, rcx
0x180001f13  xor     eax, eax
0x180001f15  lea     rcx, [rsp+1048h+var_1024]; void *
0x180001f1a  xor     edx, edx; Val
0x180001f1c  mov     [rsp+1048h+var_1028], eax
0x180001f20  mov     r8d, 7FCh; Size
0x180001f26  call    memset_0
0x180001f2b  test    ebx, ebx
0x180001f2d  jnz     loc_180002054
0x180001f33  mov     rcx, cs:SstpSvcGlobals
0x180001f3a  mov     [rsi+5Ch], ebp
0x180001f3d  add     rcx, 300h; SRWLock
0x180001f44  mov     eax, [rdi+0F0h]
0x180001f4a  mov     [rsi+58h], eax
0x180001f4d  call    cs:__imp_AcquireSRWLockShared
0x180001f53  mov     rcx, cs:SstpSvcGlobals
0x180001f5a  mov     ebx, [rcx+308h]
0x180001f60  add     rcx, 300h; SRWLock
0x180001f67  call    cs:__imp_ReleaseSRWLockShared
0x180001f6d  bt      ebx, 0
0x180001f71  jb      loc_18000213B
0x180001f77  xor     eax, eax
0x180001f79  lea     rcx, [rsp+1048h+var_824]; void *
0x180001f81  xor     edx, edx; Val
0x180001f83  mov     [rsp+1048h+var_828], eax
0x180001f8a  mov     r8d, 7FCh; Size
0x180001f90  call    memset_0
0x180001f95  mov     rbx, [rsi+38h]
0x180001f99  mov     qword ptr [rsi+38h], 0
0x180001fa1  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001fa8  call    cs:__imp_EnterCriticalSection
0x180001fae  cmp     byte ptr [rbx+1B3h], 0
0x180001fb5  jnz     loc_18000215F
0x180001fbb  lea     r8, [rsi+28h]
0x180001fbf  mov     [rsi+30h], r8
0x180001fc3  lea     rdx, [rbx+1A0h]
0x180001fca  mov     [r8], r8
0x180001fcd  mov     rax, [rdx+8]
0x180001fd1  mov     [r8], rdx
0x180001fd4  mov     [rsi+30h], rax
0x180001fd8  mov     [rax], r8
0x180001fdb  mov     [rdx+8], r8
0x180001fdf  cmp     byte ptr [rbx+1B0h], 0
0x180001fe6  jnz     short loc_180002003
0x180001fe8  mov     byte ptr [rbx+1B0h], 1
0x180001fef  lock inc dword ptr [rbx+0D0h]
0x180001ff6  mov     rcx, [rbx+150h]; pwk
0x180001ffd  call    cs:__imp_SubmitThreadpoolWork
0x180002003  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000200a  call    cs:__imp_LeaveCriticalSection
0x180002010  mov     rcx, rdi
0x180002013  call    PostReceiveOnCall
0x180002018  lea     rcx, [rdi+0D0h]
0x18000201f  mov     eax, 0FFFFFFFFh
0x180002024  lock xadd [rcx], eax
0x180002028  cmp     eax, 1
0x18000202b  jz      loc_1800021CF
0x180002031  mov     rcx, [rsp+1048h+var_28]
0x180002039  xor     rcx, rsp; StackCookie
0x18000203c  call    __security_check_cookie
0x180002041  mov     rbx, [rsp+1048h+arg_10]
0x180002049  add     rsp, 1030h
0x180002050  pop     rdi
0x180002051  pop     rsi
0x180002052  pop     rbp
0x180002053  retn
0x180002054  test    cs:byte_18002D803, 8
0x18000205b  jnz     short loc_1800020D3
0x18000205d  mov     rbx, cs:SstpSvcGlobals
0x180002064  add     rsi, 0FFFFFFFFFFFFFFE8h
0x180002068  add     rbx, 1A8h
0x18000206f  lea     rcx, [rbx+40h]; lpCriticalSection
0x180002073  call    cs:__imp_EnterCriticalSection
0x180002079  cmp     [rsi], rsi
0x18000207c  jnz     loc_18000211F
0x180002082  mov     rax, [rbx+28h]
0x180002086  lea     rcx, [rbx+28h]
0x18000208a  mov     [rsi], rax
0x18000208d  mov     [rsi+8], rcx
0x180002091  mov     [rax+8], rsi
0x180002095  mov     [rcx], rsi
0x180002098  mov     rax, [rsi+10h]
0x18000209c  inc     dword ptr [rax+1Ch]
0x18000209f  inc     dword ptr [rbx+14h]
0x1800020a2  mov     eax, [rbx+14h]
0x1800020a5  cmp     eax, [rbx+10h]
0x1800020a8  jnb     short loc_180002127
0x1800020aa  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800020ae  call    cs:__imp_LeaveCriticalSection
0x1800020b4  lea     rcx, [rdi+120h]; lpCriticalSection
0x1800020bb  call    cs:__imp_EnterCriticalSection
0x1800020c1  mov     edx, 1
0x1800020c6  mov     rcx, rdi
0x1800020c9  call    InitiateCallContextCleanup
0x1800020ce  jmp     loc_180002018
0x1800020d3  xor     eax, eax
0x1800020d5  lea     r8, [rdi+228h]
0x1800020dc  mov     r9d, ebx
0x1800020df  mov     word ptr [rsp+1048h+var_1028], ax
0x1800020e4  lea     rdx, aCoidHsReceiver; "CoId=%hs:ReceiveResponseEntity fails wi"...
0x1800020eb  lea     rcx, [rsp+1048h+var_1028]
0x1800020f0  call    FormatRRASErrorString
0x1800020f5  test    cs:byte_18002D803, 8
0x1800020fc  jz      loc_18000205D
0x180002102  lea     r8, [rsp+1048h+var_1028]
0x180002107  lea     rdx, RasSSTPSvcTraceError
0x18000210e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002115  call    McTemplateU0z_EventWriteTransfer
0x18000211a  jmp     loc_18000205D
0x18000211f  inc     cs:g_ulDoubleBufferFrees
0x180002125  jmp     short loc_1800020AA
0x180002127  mov     rcx, rbx
0x18000212a  call    FreeUnusedBufferPoolBlocks
0x18000212f  mov     dword ptr [rbx+14h], 0
0x180002136  jmp     loc_1800020AA
0x18000213b  test    rdi, rdi
0x18000213e  jz      loc_180001F77
0x180002144  cmp     qword ptr [rdi+270h], 0
0x18000214c  jz      loc_180001F77
0x180002152  mov     rcx, rsi; Overlapped
0x180002155  call    ProxySendToRelatedCtx
0x18000215a  jmp     loc_180002010
0x18000215f  test    cs:byte_18002D803, 8
0x180002166  jz      short loc_1800021B1
0x180002168  xor     eax, eax
0x18000216a  lea     r8, [rbx+228h]
0x180002171  lea     rdx, aCoidHsDropping; "CoId=%hs:Dropping packet since disconne"...
0x180002178  mov     word ptr [rsp+1048h+var_828], ax
0x180002180  lea     rcx, [rsp+1048h+var_828]
0x180002188  call    FormatRRASErrorString
0x18000218d  test    cs:byte_18002D803, 8
0x180002194  jz      short loc_1800021B1
0x180002196  lea     r8, [rsp+1048h+var_828]
0x18000219e  lea     rdx, RasSSTPSvcTraceError
0x1800021a5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800021ac  call    McTemplateU0z_EventWriteTransfer
0x1800021b1  mov     rcx, cs:SstpSvcGlobals
0x1800021b8  mov     r8b, 1
0x1800021bb  add     rcx, 1A8h
0x1800021c2  mov     rdx, rsi
0x1800021c5  call    FreeBufferToPool
0x1800021ca  jmp     loc_180002003
0x1800021cf  mov     rax, [rcx+8]
0x1800021d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021d8  jmp     loc_180002031
```
