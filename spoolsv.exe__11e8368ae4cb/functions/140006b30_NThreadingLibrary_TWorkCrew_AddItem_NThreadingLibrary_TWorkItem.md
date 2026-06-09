# NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)

- ea: `0x140006b30`
- end: `0x140006d77`
- name: `?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z`
- size: `583`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, struct NThreadingLibrary::TWorkItem *)`
- caller_count: `76`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400068a0`
- `0x140006a40`
- `0x140006d80`
- `0x140007250`
- `0x1400074b0`
- `0x1400077e0`
- `0x140007f90`
- `0x14000a2c0`
- `0x14000c970`
- `0x140014934`
- `0x1400417f0`
- `0x140041890`
- `0x140041920`
- `0x1400419f0`
- `0x140041af0`
- `0x140041c20`
- `0x140041d50`
- `0x140041eb0`
- `0x140041fb0`
- `0x1400420d0`
- `0x1400421a0`
- `0x140042230`
- `0x140042340`
- `0x140042480`
- `0x140042590`
- `0x1400426d0`
- `0x140042770`
- `0x140042840`
- `0x140042920`
- `0x140042a60`
- `0x140042bb0`
- `0x140042ca0`
- `0x140042d30`
- `0x140042e00`
- `0x140042ea0`
- `0x140042f40`
- `0x140043040`
- `0x140043110`
- `0x140043210`
- `0x140043310`
- `0x140043410`
- `0x140043530`
- `0x140043650`
- `0x140043730`
- `0x140043820`
- `0x140043940`
- `0x140043a20`
- `0x140043af0`
- `0x140043be0`
- `0x140043ce0`

## callees

- `0x140006b30`
- `0x140006f90`
- `0x14005142c`
- `0x1400514ac`
- `0x140051510`
- `0x14005159c`
- `0x140051630`
- `0x14007a010`

## import_xrefs

- `ntdll!TpSimpleTryPost` at `0x140006d1a`
- `ntdll!TpSimpleTryPost` at `0x140006d1a`
- `ntdll!RtlNtStatusToDosError` at `0x140006d22`
- `ntdll!RtlNtStatusToDosError` at `0x140006d22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006c86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006c86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006b80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006b80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006b89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006b89`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::AddItem(
        struct _RTL_CRITICAL_SECTION *this,
        struct NThreadingLibrary::TWorkItem *a2)
{
  unsigned int v4; // edi
  int v5; // r14d
  char *v6; // rdx
  __int64 v7; // rax
  char *v8; // r8
  __int64 v9; // r9
  signed __int32 i; // eax
  struct _TP_CALLBACK_ENVIRON_V3 *LockSemaphore; // r8
  int v13; // ecx
  NThreadingLibrary::TWorkCrew *v14; // rcx
  NThreadingLibrary::TWorkCrew *v15; // rcx
  NThreadingLibrary::TWorkCrew *v16; // rcx
  NThreadingLibrary::TWorkCrew *v17; // rcx
  NTSTATUS v18; // eax
  signed int v19; // eax

  if ( !a2
    || (*(int (__fastcall **)(struct NThreadingLibrary::TWorkItem *))(*(_QWORD *)a2 + 16LL))(a2) < 0
    || *((_DWORD *)a2 + 16) != 1953063799 )
  {
    return 2147942487LL;
  }
  EnterCriticalSection(this + 1);
  ++HIDWORD(this[2].DebugInfo);
  LODWORD(this[2].DebugInfo) = GetCurrentThreadId();
  v4 = -2147024809;
  if ( LODWORD(this[4].OwningThread) )
  {
    v5 = -2147467259;
  }
  else if ( *((_QWORD *)a2 + 10) )
  {
    v5 = 0;
    if ( *((_DWORD *)a2 + 18) )
      v5 = -2147024846;
  }
  else
  {
    v6 = (char *)a2 + 32;
    if ( a2 == (struct NThreadingLibrary::TWorkItem *)-32LL )
    {
      v5 = -2147024809;
    }
    else
    {
      v7 = *((_QWORD *)a2 + 6);
      v8 = (char *)a2 + 56;
      if ( v7 && *(_QWORD *)v8 )
        v5 = 0;
      else
        v5 = -2147467259;
      if ( v5 >= 0 )
      {
        v9 = *(_QWORD *)&this[3].LockCount;
        if ( (char *)v7 != v6 && *(char **)v8 != v6 )
        {
          *(_QWORD *)(v7 + 24) = *(_QWORD *)v8;
          *(_QWORD *)(*(_QWORD *)v8 + 16LL) = *((_QWORD *)a2 + 6);
          *((_QWORD *)a2 + 6) = v6;
          *(_QWORD *)v8 = v6;
        }
        v5 = 0;
        *(_QWORD *)(*(_QWORD *)(v9 + 16) + 24LL) = v6;
        *((_QWORD *)a2 + 6) = *(_QWORD *)(v9 + 16);
        *(_QWORD *)v8 = v9;
        *(_QWORD *)(v9 + 16) = v6;
        *((_QWORD *)a2 + 10) = this;
        *(_QWORD *)((char *)a2 + 68) = 0;
        ++LODWORD(this[5].DebugInfo);
        for ( i = *((_DWORD *)a2 + 2); i != 0x7FFFFFFF; i = *((_DWORD *)a2 + 2) )
        {
          if ( i == _InterlockedCompareExchange((volatile signed __int32 *)a2 + 2, i + 1, i) )
            break;
        }
      }
    }
  }
  if ( HIDWORD(this[2].DebugInfo)-- == 1 )
    LODWORD(this[2].DebugInfo) = 0;
  LeaveCriticalSection(this + 1);
  if ( v5 >= 0 )
  {
    LockSemaphore = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)a2 + 3);
    if ( LockSemaphore )
      LockSemaphore->Pool = (PTP_POOL)this[5].LockSemaphore;
    else
      LockSemaphore = (struct _TP_CALLBACK_ENVIRON_V3 *)this->LockSemaphore;
    v13 = *((_DWORD *)a2 + 22);
    if ( v13 )
    {
      v14 = (NThreadingLibrary::TWorkCrew *)(unsigned int)(v13 - 1);
      if ( (_DWORD)v14 )
      {
        v15 = (NThreadingLibrary::TWorkCrew *)(unsigned int)((_DWORD)v14 - 1);
        if ( (_DWORD)v15 )
        {
          v16 = (NThreadingLibrary::TWorkCrew *)(unsigned int)((_DWORD)v15 - 1);
          if ( (_DWORD)v16 )
          {
            v17 = (NThreadingLibrary::TWorkCrew *)(unsigned int)((_DWORD)v16 - 1);
            if ( (_DWORD)v17 )
            {
              if ( (_DWORD)v17 != 1 )
                goto LABEL_43;
              v4 = NThreadingLibrary::TWorkCrew::AddLpcItem(v17, a2, LockSemaphore);
            }
            else
            {
              v4 = NThreadingLibrary::TWorkCrew::AddIOItem(v17, a2, LockSemaphore);
            }
          }
          else
          {
            v4 = NThreadingLibrary::TWorkCrew::AddTimerItem(v16, a2, LockSemaphore);
          }
        }
        else
        {
          v4 = NThreadingLibrary::TWorkCrew::AddWaitItem(v15, a2, LockSemaphore);
        }
      }
      else
      {
        v4 = NThreadingLibrary::TWorkCrew::AddWorkItem(v14, a2, LockSemaphore);
      }
    }
    else
    {
      v18 = TpSimpleTryPost(NThreadingLibrary::TWorkCrew::tpSimpleCallback, a2, LockSemaphore);
      v19 = RtlNtStatusToDosError(v18);
      v4 = v19;
      if ( v19 > 0 )
        v4 = (unsigned __int16)v19 | 0x80070000;
    }
    if ( (v4 & 0x80000000) == 0 )
      return v4;
LABEL_43:
    NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue((NThreadingLibrary::TWorkCrew *)this, a2);
    return v4;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006b30  mov     [rsp+arg_10], rbp
0x140006b35  mov     [rsp+arg_18], rsi
0x140006b3a  push    rdi
0x140006b3b  sub     rsp, 20h
0x140006b3f  mov     rsi, rdx
0x140006b42  mov     rbp, rcx
0x140006b45  test    rdx, rdx
0x140006b48  jz      loc_140006D62
0x140006b4e  mov     rax, [rdx]
0x140006b51  mov     rcx, rdx
0x140006b54  mov     rax, [rax+10h]
0x140006b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b5d  test    eax, eax
0x140006b5f  js      loc_140006D62
0x140006b65  cmp     dword ptr [rsi+40h], 74696377h
0x140006b6c  jnz     loc_140006D62
0x140006b72  mov     [rsp+28h+arg_0], rbx
0x140006b77  lea     rcx, [rbp+28h]; lpCriticalSection
0x140006b7b  mov     [rsp+28h+arg_8], r14
0x140006b80  call    cs:__imp_EnterCriticalSection
0x140006b86  inc     dword ptr [rbp+54h]
0x140006b89  call    cs:__imp_GetCurrentThreadId
0x140006b8f  mov     [rbp+50h], eax
0x140006b92  mov     edi, 80070057h
0x140006b97  cmp     dword ptr [rbp+0B0h], 0
0x140006b9e  jnz     loc_140006C6C
0x140006ba4  cmp     qword ptr [rsi+50h], 0
0x140006ba9  jz      short loc_140006BC3
0x140006bab  xor     r14d, r14d
0x140006bae  cmp     [rsi+48h], r14d
0x140006bb2  jz      loc_140006C72
0x140006bb8  mov     r14d, 80070032h
0x140006bbe  jmp     loc_140006C72
0x140006bc3  lea     rdx, [rsi+20h]
0x140006bc7  test    rdx, rdx
0x140006bca  jz      loc_140006C67
0x140006bd0  mov     rax, [rsi+30h]
0x140006bd4  lea     r8, [rsi+38h]
0x140006bd8  test    rax, rax
0x140006bdb  jz      short loc_140006BE8
0x140006bdd  cmp     qword ptr [r8], 0
0x140006be1  jz      short loc_140006BE8
0x140006be3  xor     r14d, r14d
0x140006be6  jmp     short loc_140006BEE
0x140006be8  mov     r14d, 80004005h
0x140006bee  test    r14d, r14d
0x140006bf1  js      short loc_140006C72
0x140006bf3  mov     r9, [rbp+80h]
0x140006bfa  cmp     rax, rdx
0x140006bfd  jz      short loc_140006C1D
0x140006bff  mov     rcx, [r8]
0x140006c02  cmp     rcx, rdx
0x140006c05  jz      short loc_140006C1D
0x140006c07  mov     [rax+18h], rcx
0x140006c0b  mov     rcx, [r8]
0x140006c0e  mov     rax, [rsi+30h]
0x140006c12  mov     [rcx+10h], rax
0x140006c16  mov     [rsi+30h], rdx
0x140006c1a  mov     [r8], rdx
0x140006c1d  mov     rax, [r9+10h]
0x140006c21  xor     ecx, ecx
0x140006c23  xor     r14d, r14d
0x140006c26  mov     [rax+18h], rdx
0x140006c2a  mov     rax, [r9+10h]
0x140006c2e  mov     [rsi+30h], rax
0x140006c32  mov     [r8], r9
0x140006c35  mov     [r9+10h], rdx
0x140006c39  mov     [rsi+50h], rbp
0x140006c3d  mov     [rsi+44h], rcx
0x140006c41  inc     dword ptr [rbp+0C8h]
0x140006c47  mov     eax, [rsi+8]
0x140006c4a  cmp     eax, 7FFFFFFFh
0x140006c4f  jz      short loc_140006C72
0x140006c51  lea     ecx, [rax+1]
0x140006c54  lock cmpxchg [rsi+8], ecx
0x140006c59  jz      short loc_140006C72
0x140006c5b  mov     eax, [rsi+8]
0x140006c5e  cmp     eax, 7FFFFFFFh
0x140006c63  jnz     short loc_140006C51
0x140006c65  jmp     short loc_140006C72
0x140006c67  mov     r14d, edi
0x140006c6a  jmp     short loc_140006C72
0x140006c6c  mov     r14d, 80004005h
0x140006c72  add     dword ptr [rbp+54h], 0FFFFFFFFh
0x140006c76  mov     eax, [rbp+54h]
0x140006c79  jnz     short loc_140006C82
0x140006c7b  mov     dword ptr [rbp+50h], 0
0x140006c82  lea     rcx, [rbp+28h]; lpCriticalSection
0x140006c86  call    cs:__imp_LeaveCriticalSection
0x140006c8c  mov     rbx, [rsp+28h+arg_0]
0x140006c91  test    r14d, r14d
0x140006c94  js      loc_140006D5D
0x140006c9a  mov     r8, [rsi+18h]
0x140006c9e  test    r8, r8
0x140006ca1  jz      short loc_140006CB0
0x140006ca3  mov     rax, [rbp+0E0h]
0x140006caa  mov     [r8+8], rax
0x140006cae  jmp     short loc_140006CB4
0x140006cb0  mov     r8, [rbp+18h]; struct _TP_CALLBACK_ENVIRON_V3 *
0x140006cb4  mov     ecx, [rsi+58h]
0x140006cb7  test    ecx, ecx
0x140006cb9  jz      short loc_140006D10
0x140006cbb  sub     ecx, 1; this
0x140006cbe  jz      short loc_140006D04
0x140006cc0  sub     ecx, 1; this
0x140006cc3  jz      short loc_140006CF8
0x140006cc5  sub     ecx, 1; this
0x140006cc8  jz      short loc_140006CEC
0x140006cca  sub     ecx, 1; this
0x140006ccd  jz      short loc_140006CE0
0x140006ccf  cmp     ecx, 1
0x140006cd2  jnz     short loc_140006D3B
0x140006cd4  mov     rdx, rsi; struct NThreadingLibrary::TLpcItem *
0x140006cd7  call    ?AddLpcItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTLpcItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddLpcItem(NThreadingLibrary::TLpcItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x140006cdc  mov     edi, eax
0x140006cde  jmp     short loc_140006D37
0x140006ce0  mov     rdx, rsi; struct NThreadingLibrary::TIOItem *
0x140006ce3  call    ?AddIOItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTIOItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddIOItem(NThreadingLibrary::TIOItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x140006ce8  mov     edi, eax
0x140006cea  jmp     short loc_140006D37
0x140006cec  mov     rdx, rsi; struct NThreadingLibrary::TTimerItem *
0x140006cef  call    ?AddTimerItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTTimerItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddTimerItem(NThreadingLibrary::TTimerItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x140006cf4  mov     edi, eax
0x140006cf6  jmp     short loc_140006D37
0x140006cf8  mov     rdx, rsi; struct NThreadingLibrary::TWaitItem *
0x140006cfb  call    ?AddWaitItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWaitItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddWaitItem(NThreadingLibrary::TWaitItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x140006d00  mov     edi, eax
0x140006d02  jmp     short loc_140006D37
0x140006d04  mov     rdx, rsi; struct NThreadingLibrary::TQueuedItem *
0x140006d07  call    ?AddWorkItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTQueuedItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddWorkItem(NThreadingLibrary::TQueuedItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x140006d0c  mov     edi, eax
0x140006d0e  jmp     short loc_140006D37
0x140006d10  mov     rdx, rsi
0x140006d13  lea     rcx, ?tpSimpleCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; NThreadingLibrary::TWorkCrew::tpSimpleCallback(_TP_CALLBACK_INSTANCE *,void *)
0x140006d1a  call    cs:__imp_TpSimpleTryPost
0x140006d20  mov     ecx, eax; Status
0x140006d22  call    cs:__imp_RtlNtStatusToDosError
0x140006d28  mov     edi, eax
0x140006d2a  test    eax, eax
0x140006d2c  jle     short loc_140006D37
0x140006d2e  movzx   edi, ax
0x140006d31  or      edi, 80070000h
0x140006d37  test    edi, edi
0x140006d39  jns     short loc_140006D46
0x140006d3b  mov     rdx, rsi; struct NThreadingLibrary::TWorkItem *
0x140006d3e  mov     rcx, rbp; this
0x140006d41  call    ?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)
0x140006d46  mov     eax, edi
0x140006d48  mov     r14, [rsp+28h+arg_8]
0x140006d4d  mov     rbp, [rsp+28h+arg_10]
0x140006d52  mov     rsi, [rsp+28h+arg_18]
0x140006d57  add     rsp, 20h
0x140006d5b  pop     rdi
0x140006d5c  retn
0x140006d5d  mov     eax, r14d
0x140006d60  jmp     short loc_140006D48
0x140006d62  mov     rbp, [rsp+28h+arg_10]
0x140006d67  mov     eax, 80070057h
0x140006d6c  mov     rsi, [rsp+28h+arg_18]
0x140006d71  add     rsp, 20h
0x140006d75  pop     rdi
0x140006d76  retn
```
