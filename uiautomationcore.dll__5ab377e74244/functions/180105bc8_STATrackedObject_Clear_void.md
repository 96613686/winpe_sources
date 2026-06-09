# STATrackedObject::Clear(void)

- ea: `0x180105bc8`
- end: `0x180105dfe`
- name: `?Clear@STATrackedObject@@QEAAXXZ`
- size: `566`
- prototype: `void __fastcall(STATrackedObject *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18010547c`

## callees

- `0x180105bc8`
- `0x180105e04`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180105bf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180105bf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105c89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105c89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180105bfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180105cbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180105bfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180105cbf`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180105dc7`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180105dc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall STATrackedObject::Clear(STATrackedObject *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v5; // rdx
  unsigned __int64 i; // r8
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // edi
  char *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rax
  HRESULT ClassObject; // eax
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF
  __int64 v17; // [rsp+60h] [rbp+18h]

  v2 = 0;
  v17 = 0;
  if ( !g_ComMitigationDone && !`CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress )
  {
    `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 1;
    ppv = 0;
    ClassObject = CoGetClassObject(&CLSID_CUIAutomation, 1u, 0, &GUID_00000001_0000_0000_c000_000000000046, &ppv);
    `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 0;
    if ( ClassObject < 0 )
      goto LABEL_25;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    g_ComMitigationDone = 1;
  }
  v3 = 0;
  EnterCriticalSection(&CApartmentTracker::_classLock);
  CurrentThreadId = GetCurrentThreadId();
  LODWORD(ppv) = CurrentThreadId;
  v5 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v5 = 0x100000001B3LL * (*((unsigned __int8 *)&ppv + i) ^ (unsigned __int64)v5);
  v7 = 2 * (qword_18039F790 & v5);
  v8 = *((_QWORD *)Block + v7 + 1);
  if ( v8 == qword_18039F768 )
  {
LABEL_8:
    v8 = 0;
  }
  else
  {
    while ( CurrentThreadId != *(_DWORD *)(v8 + 16) )
    {
      if ( v8 == *((_QWORD *)Block + v7) )
        goto LABEL_8;
      v8 = *(_QWORD *)(v8 + 8);
    }
  }
  v9 = qword_18039F768;
  if ( v8 )
    v9 = v8;
  if ( v9 != qword_18039F768 )
    v3 = *(_QWORD *)(v9 + 24);
  LeaveCriticalSection(&CApartmentTracker::_classLock);
  if ( v3 )
  {
    if ( *(_DWORD *)(v3 + 24) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
      v2 = v3;
      v17 = v3;
      STATrackedObject::ReleaseContainedInterfaceIfValid(this);
      if ( *(_DWORD *)(v3 + 24) )
      {
        v10 = *((_DWORD *)this + 10);
        if ( GetCurrentThreadId() == v10 )
        {
          v11 = (char *)this + 16;
          v12 = *((_QWORD *)this + 3);
          if ( v12
            || *(_QWORD *)v11
            || v11 == (char *)((*(_QWORD *)(v2 + 40) + 16LL) & -(__int64)(*(_QWORD *)(v2 + 40) != 0)) )
          {
            if ( *(_QWORD *)v11 )
              *(_QWORD *)(*(_QWORD *)v11 + 24LL) = v12;
            v13 = *((_QWORD *)this + 3);
            v14 = *(_QWORD *)v11;
            if ( v13 )
              *(_QWORD *)(v13 + 16) = v14;
            else
              *(_QWORD *)(v2 + 40) = v14;
            *((_QWORD *)this + 3) = 0;
            *(_QWORD *)v11 = 0;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
              (**(void (__fastcall ***)(STATrackedObject *, __int64))this)(this, 1);
          }
        }
      }
    }
  }
LABEL_25:
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
  }
}

```

## disassembly

```asm
0x180105bc8  mov     [rsp+arg_0], rbx
0x180105bcd  mov     [rsp+arg_18], rsi
0x180105bd2  push    rdi
0x180105bd3  sub     rsp, 40h
0x180105bd7  mov     rsi, rcx
0x180105bda  xor     ebx, ebx
0x180105bdc  mov     [rsp+48h+arg_10], rbx
0x180105be1  cmp     cs:?g_ComMitigationDone@@3_NA, bl; bool g_ComMitigationDone
0x180105be7  jz      loc_180105D90
0x180105bed  xor     edi, edi
0x180105bef  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180105bf6  call    cs:__imp_EnterCriticalSection
0x180105bfc  call    cs:__imp_GetCurrentThreadId
0x180105c02  mov     r9d, eax
0x180105c05  mov     dword ptr [rsp+48h+arg_8], eax
0x180105c09  mov     rdx, 0CBF29CE484222325h
0x180105c13  xor     r8d, r8d
0x180105c16  movzx   ecx, byte ptr [rsp+r8+48h+arg_8]
0x180105c1c  xor     rdx, rcx
0x180105c1f  mov     rax, 100000001B3h
0x180105c29  imul    rdx, rax
0x180105c2d  inc     r8
0x180105c30  cmp     r8, 4
0x180105c34  jb      short loc_180105C16
0x180105c36  and     rdx, cs:qword_18039F790
0x180105c3d  add     rdx, rdx
0x180105c40  mov     rcx, cs:Block
0x180105c47  mov     rax, [rcx+rdx*8+8]
0x180105c4c  mov     r10, cs:qword_18039F768
0x180105c53  cmp     rax, r10
0x180105c56  jz      short loc_180105C6D
0x180105c58  mov     r8, [rcx+rdx*8]
0x180105c5c  cmp     r9d, [rax+10h]
0x180105c60  jz      short loc_180105C6F
0x180105c62  cmp     rax, r8
0x180105c65  jz      short loc_180105C6D
0x180105c67  mov     rax, [rax+8]
0x180105c6b  jmp     short loc_180105C5C
0x180105c6d  xor     eax, eax
0x180105c6f  mov     rdx, r10
0x180105c72  test    rax, rax
0x180105c75  cmovnz  rdx, rax
0x180105c79  cmp     rdx, r10
0x180105c7c  jnz     loc_180105D39
0x180105c82  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180105c89  call    cs:__imp_LeaveCriticalSection
0x180105c8f  test    rdi, rdi
0x180105c92  jz      loc_180105D42
0x180105c98  cmp     dword ptr [rdi+18h], 0
0x180105c9c  jz      loc_180105D42
0x180105ca2  lock inc dword ptr [rdi+8]
0x180105ca6  mov     rbx, rdi
0x180105ca9  mov     [rsp+48h+arg_10], rbx
0x180105cae  mov     rcx, rsi; this
0x180105cb1  call    ?ReleaseContainedInterfaceIfValid@STATrackedObject@@QEAAXXZ; STATrackedObject::ReleaseContainedInterfaceIfValid(void)
0x180105cb6  cmp     dword ptr [rdi+18h], 0
0x180105cba  jz      short loc_180105D17
0x180105cbc  mov     edi, [rsi+28h]
0x180105cbf  call    cs:__imp_GetCurrentThreadId
0x180105cc5  cmp     eax, edi
0x180105cc7  jnz     short loc_180105D17
0x180105cc9  lea     rdx, [rsi+10h]
0x180105ccd  mov     r8, [rdx+8]
0x180105cd1  test    r8, r8
0x180105cd4  jnz     short loc_180105CDF
0x180105cd6  cmp     [rdx], r8
0x180105cd9  jz      loc_180105D74
0x180105cdf  mov     rax, [rdx]
0x180105ce2  test    rax, rax
0x180105ce5  jz      short loc_180105CEB
0x180105ce7  mov     [rax+18h], r8
0x180105ceb  mov     rcx, [rdx+8]
0x180105cef  mov     rax, [rdx]
0x180105cf2  test    rcx, rcx
0x180105cf5  jz      short loc_180105D59
0x180105cf7  mov     [rcx+10h], rax
0x180105cfb  mov     qword ptr [rdx+8], 0
0x180105d03  mov     qword ptr [rdx], 0
0x180105d0a  or      eax, 0FFFFFFFFh
0x180105d0d  lock xadd [rsi+8], eax
0x180105d12  cmp     eax, 1
0x180105d15  jz      short loc_180105D5F
0x180105d17  test    rbx, rbx
0x180105d1a  jz      short loc_180105D29
0x180105d1c  or      eax, 0FFFFFFFFh
0x180105d1f  lock xadd [rbx+8], eax
0x180105d24  cmp     eax, 1
0x180105d27  jz      short loc_180105D44
0x180105d29  mov     rbx, [rsp+48h+arg_0]
0x180105d2e  mov     rsi, [rsp+48h+arg_18]
0x180105d33  add     rsp, 40h
0x180105d37  pop     rdi
0x180105d38  retn
0x180105d39  mov     rdi, [rdx+18h]
0x180105d3d  jmp     loc_180105C82
0x180105d42  jmp     short loc_180105D17
0x180105d44  mov     rax, [rbx]
0x180105d47  mov     edx, 1
0x180105d4c  mov     rcx, rbx
0x180105d4f  mov     rax, [rax]
0x180105d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105d57  jmp     short loc_180105D29
0x180105d59  mov     [rbx+28h], rax
0x180105d5d  jmp     short loc_180105CFB
0x180105d5f  mov     rax, [rsi]
0x180105d62  mov     edx, 1
0x180105d67  mov     rcx, rsi
0x180105d6a  mov     rax, [rax]
0x180105d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105d72  jmp     short loc_180105D17
0x180105d74  mov     rax, [rbx+28h]
0x180105d78  lea     rcx, [rax+10h]
0x180105d7c  neg     rax
0x180105d7f  sbb     rax, rax
0x180105d82  and     rax, rcx
0x180105d85  cmp     rdx, rax
0x180105d88  jz      loc_180105CDF
0x180105d8e  jmp     short loc_180105D17
0x180105d90  cmp     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, bl; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180105d96  jnz     loc_180105BED
0x180105d9c  mov     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, 1; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180105da3  mov     [rsp+48h+arg_8], rbx
0x180105da8  lea     rax, [rsp+48h+arg_8]
0x180105dad  mov     [rsp+48h+ppv], rax; ppv
0x180105db2  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180105db9  xor     r8d, r8d; pvReserved
0x180105dbc  lea     edx, [r8+1]; dwClsContext
0x180105dc0  lea     rcx, CLSID_CUIAutomation; rclsid
0x180105dc7  call    cs:__imp_CoGetClassObject
0x180105dcd  mov     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, bl; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180105dd3  test    eax, eax
0x180105dd5  js      loc_180105D17
0x180105ddb  mov     rcx, [rsp+48h+arg_8]
0x180105de0  test    rcx, rcx
0x180105de3  jz      short loc_180105DF1
0x180105de5  mov     rax, [rcx]
0x180105de8  mov     rax, [rax+10h]
0x180105dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105df1  mov     cs:?g_ComMitigationDone@@3_NA, 1; bool g_ComMitigationDone
0x180105df8  jmp     loc_180105BED
```
