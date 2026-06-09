# AgileInterface<IEnumVARIANT>::Clear(IGlobalInterfaceTable *)

- ea: `0x18010517c`
- end: `0x18010542c`
- name: `?Clear@?$AgileInterface@UIEnumVARIANT@@@@QEAAXPEAUIGlobalInterfaceTable@@@Z`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800baaa4`

## callees

- `0x18010517c`
- `0x180105e04`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801051f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801051f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105288`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105288`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801051fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801052bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801051fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801052bd`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1801053f4`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1801053f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AgileInterface<IEnumVARIANT>::Clear(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v9; // rdx
  unsigned __int64 i; // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  int v14; // edi
  __int64 *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  HRESULT ClassObject; // eax
  LPVOID ppv; // [rsp+60h] [rbp+8h] BYREF
  __int64 v22; // [rsp+70h] [rbp+18h]

  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *(_QWORD *)(a1 + 8) = 0;
  }
  if ( *(_DWORD *)(a1 + 24) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 32LL))(a2);
    *(_DWORD *)(a1 + 24) = 0;
  }
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 )
  {
    v6 = 0;
    v22 = 0;
    if ( !g_ComMitigationDone && !`CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress )
    {
      `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 1;
      ppv = 0;
      ClassObject = CoGetClassObject(&CLSID_CUIAutomation, 1u, 0, &GUID_00000001_0000_0000_c000_000000000046, &ppv);
      `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 0;
      if ( ClassObject < 0 )
      {
LABEL_30:
        if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 8), 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(__int64, __int64))v6)(v6, 1);
        v19 = *(_QWORD *)(a1 + 16);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 8), 0xFFFFFFFF) == 1 && v19 )
          (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
        *(_QWORD *)(a1 + 16) = 0;
        goto LABEL_35;
      }
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      g_ComMitigationDone = 1;
    }
    v7 = 0;
    EnterCriticalSection(&CApartmentTracker::_classLock);
    CurrentThreadId = GetCurrentThreadId();
    LODWORD(ppv) = CurrentThreadId;
    v9 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 4; ++i )
      v9 = 0x100000001B3LL * (*((unsigned __int8 *)&ppv + i) ^ (unsigned __int64)v9);
    v11 = 2 * (qword_18039F790 & v9);
    v12 = *((_QWORD *)Block + v11 + 1);
    if ( v12 == qword_18039F768 )
    {
LABEL_13:
      v12 = 0;
    }
    else
    {
      while ( CurrentThreadId != *(_DWORD *)(v12 + 16) )
      {
        if ( v12 == *((_QWORD *)Block + v11) )
          goto LABEL_13;
        v12 = *(_QWORD *)(v12 + 8);
      }
    }
    v13 = qword_18039F768;
    if ( v12 )
      v13 = v12;
    if ( v13 != qword_18039F768 )
      v7 = *(_QWORD *)(v13 + 24);
    LeaveCriticalSection(&CApartmentTracker::_classLock);
    if ( v7 )
    {
      if ( *(_DWORD *)(v7 + 24) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
        v6 = v7;
        v22 = v7;
        STATrackedObject::ReleaseContainedInterfaceIfValid((STATrackedObject *)v5);
        if ( *(_DWORD *)(v7 + 24) )
        {
          v14 = *(_DWORD *)(v5 + 40);
          if ( GetCurrentThreadId() == v14 )
          {
            v15 = (__int64 *)(v5 + 16);
            v16 = *(_QWORD *)(v5 + 24);
            if ( v16
              || *v15
              || v15 == (__int64 *)((*(_QWORD *)(v6 + 40) + 16LL) & -(__int64)(*(_QWORD *)(v6 + 40) != 0)) )
            {
              if ( *v15 )
                *(_QWORD *)(*v15 + 24) = v16;
              v17 = *(_QWORD *)(v5 + 24);
              v18 = *v15;
              if ( v17 )
                *(_QWORD *)(v17 + 16) = v18;
              else
                *(_QWORD *)(v6 + 40) = v18;
              *(_QWORD *)(v5 + 24) = 0;
              *v15 = 0;
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 8), 0xFFFFFFFF) == 1 )
                (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
            }
          }
        }
      }
    }
    goto LABEL_30;
  }
LABEL_35:
  *(_DWORD *)a1 = 0;
}

```

## disassembly

```asm
0x18010517c  mov     [rsp+arg_8], rbx
0x180105181  mov     [rsp+arg_18], rbp
0x180105186  push    rsi
0x180105187  push    rdi
0x180105188  push    r14
0x18010518a  sub     rsp, 40h
0x18010518e  mov     rbx, rdx
0x180105191  mov     rsi, rcx
0x180105194  mov     rcx, [rcx+8]
0x180105198  xor     ebp, ebp
0x18010519a  test    rcx, rcx
0x18010519d  jz      short loc_1801051AF
0x18010519f  mov     rax, [rcx]
0x1801051a2  mov     rax, [rax+10h]
0x1801051a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801051ab  mov     [rsi+8], rbp
0x1801051af  mov     edx, [rsi+18h]
0x1801051b2  test    edx, edx
0x1801051b4  jz      short loc_1801051C8
0x1801051b6  mov     rax, [rbx]
0x1801051b9  mov     rcx, rbx
0x1801051bc  mov     rax, [rax+20h]
0x1801051c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801051c5  mov     [rsi+18h], ebp
0x1801051c8  mov     r14, [rsi+10h]
0x1801051cc  test    r14, r14
0x1801051cf  jz      loc_180105339
0x1801051d5  mov     rbx, rbp
0x1801051d8  mov     [rsp+58h+arg_10], rbx
0x1801051dd  cmp     cs:?g_ComMitigationDone@@3_NA, bpl; bool g_ComMitigationDone
0x1801051e4  jz      loc_1801053BC
0x1801051ea  mov     rdi, rbp
0x1801051ed  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801051f4  call    cs:__imp_EnterCriticalSection
0x1801051fa  call    cs:__imp_GetCurrentThreadId
0x180105200  mov     r9d, eax
0x180105203  mov     dword ptr [rsp+58h+arg_0], eax
0x180105207  mov     rdx, 0CBF29CE484222325h
0x180105211  mov     r8, rbp
0x180105214  movzx   ecx, byte ptr [rsp+r8+58h+arg_0]
0x18010521a  xor     rdx, rcx
0x18010521d  mov     rax, 100000001B3h
0x180105227  imul    rdx, rax
0x18010522b  inc     r8
0x18010522e  cmp     r8, 4
0x180105232  jb      short loc_180105214
0x180105234  and     rdx, cs:qword_18039F790
0x18010523b  add     rdx, rdx
0x18010523e  mov     rcx, cs:Block
0x180105245  mov     rax, [rcx+rdx*8+8]
0x18010524a  mov     r10, cs:qword_18039F768
0x180105251  cmp     rax, r10
0x180105254  jz      short loc_18010526B
0x180105256  mov     r8, [rcx+rdx*8]
0x18010525a  cmp     r9d, [rax+10h]
0x18010525e  jz      short loc_18010526E
0x180105260  cmp     rax, r8
0x180105263  jz      short loc_18010526B
0x180105265  mov     rax, [rax+8]
0x180105269  jmp     short loc_18010525A
0x18010526b  mov     rax, rbp
0x18010526e  mov     rdx, r10
0x180105271  test    rax, rax
0x180105274  cmovnz  rdx, rax
0x180105278  cmp     rdx, r10
0x18010527b  jz      short loc_180105281
0x18010527d  mov     rdi, [rdx+18h]
0x180105281  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180105288  call    cs:__imp_LeaveCriticalSection
0x18010528e  test    rdi, rdi
0x180105291  jz      loc_18010534E
0x180105297  cmp     [rdi+18h], ebp
0x18010529a  jz      loc_18010534E
0x1801052a0  lock inc dword ptr [rdi+8]
0x1801052a4  mov     rbx, rdi
0x1801052a7  mov     [rsp+58h+arg_10], rbx
0x1801052ac  mov     rcx, r14; this
0x1801052af  call    ?ReleaseContainedInterfaceIfValid@STATrackedObject@@QEAAXXZ; STATrackedObject::ReleaseContainedInterfaceIfValid(void)
0x1801052b4  cmp     [rdi+18h], ebp
0x1801052b7  jz      short loc_180105312
0x1801052b9  mov     edi, [r14+28h]
0x1801052bd  call    cs:__imp_GetCurrentThreadId
0x1801052c3  cmp     eax, edi
0x1801052c5  jnz     short loc_180105312
0x1801052c7  lea     rdx, [r14+10h]
0x1801052cb  mov     r8, [rdx+8]
0x1801052cf  test    r8, r8
0x1801052d2  jnz     short loc_1801052DD
0x1801052d4  cmp     [rdx], rbp
0x1801052d7  jz      loc_18010539D
0x1801052dd  mov     rax, [rdx]
0x1801052e0  test    rax, rax
0x1801052e3  jz      short loc_1801052E9
0x1801052e5  mov     [rax+18h], r8
0x1801052e9  mov     rcx, [rdx+8]
0x1801052ed  mov     rax, [rdx]
0x1801052f0  test    rcx, rcx
0x1801052f3  jz      loc_18010537C
0x1801052f9  mov     [rcx+10h], rax
0x1801052fd  mov     [rdx+8], rbp
0x180105301  mov     [rdx], rbp
0x180105304  or      eax, 0FFFFFFFFh
0x180105307  lock xadd [r14+8], eax
0x18010530d  cmp     eax, 1
0x180105310  jz      short loc_180105385
0x180105312  test    rbx, rbx
0x180105315  jz      short loc_180105324
0x180105317  or      eax, 0FFFFFFFFh
0x18010531a  lock xadd [rbx+8], eax
0x18010531f  cmp     eax, 1
0x180105322  jz      short loc_180105350
0x180105324  mov     rcx, [rsi+10h]
0x180105328  or      eax, 0FFFFFFFFh
0x18010532b  lock xadd [rcx+8], eax
0x180105330  cmp     eax, 1
0x180105333  jz      short loc_180105365
0x180105335  mov     [rsi+10h], rbp
0x180105339  mov     [rsi], ebp
0x18010533b  mov     rbx, [rsp+58h+arg_8]
0x180105340  mov     rbp, [rsp+58h+arg_18]
0x180105345  add     rsp, 40h
0x180105349  pop     r14
0x18010534b  pop     rdi
0x18010534c  pop     rsi
0x18010534d  retn
0x18010534e  jmp     short loc_180105312
0x180105350  mov     rax, [rbx]
0x180105353  mov     edx, 1
0x180105358  mov     rcx, rbx
0x18010535b  mov     rax, [rax]
0x18010535e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105363  jmp     short loc_180105324
0x180105365  test    rcx, rcx
0x180105368  jz      short loc_180105335
0x18010536a  mov     rax, [rcx]
0x18010536d  mov     edx, 1
0x180105372  mov     rax, [rax]
0x180105375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010537a  jmp     short loc_180105335
0x18010537c  mov     [rbx+28h], rax
0x180105380  jmp     loc_1801052FD
0x180105385  mov     rax, [r14]
0x180105388  mov     edx, 1
0x18010538d  mov     rcx, r14
0x180105390  mov     rax, [rax]
0x180105393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105398  jmp     loc_180105312
0x18010539d  mov     rax, [rbx+28h]
0x1801053a1  lea     rcx, [rax+10h]
0x1801053a5  neg     rax
0x1801053a8  sbb     rax, rax
0x1801053ab  and     rax, rcx
0x1801053ae  cmp     rdx, rax
0x1801053b1  jz      loc_1801052DD
0x1801053b7  jmp     loc_180105312
0x1801053bc  cmp     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, bpl; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x1801053c3  jnz     loc_1801051EA
0x1801053c9  mov     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, 1; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x1801053d0  mov     [rsp+58h+arg_0], rbp
0x1801053d5  lea     rax, [rsp+58h+arg_0]
0x1801053da  mov     [rsp+58h+ppv], rax; ppv
0x1801053df  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x1801053e6  xor     r8d, r8d; pvReserved
0x1801053e9  lea     edx, [r8+1]; dwClsContext
0x1801053ed  lea     rcx, CLSID_CUIAutomation; rclsid
0x1801053f4  call    cs:__imp_CoGetClassObject
0x1801053fa  mov     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, bpl; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180105401  test    eax, eax
0x180105403  js      loc_180105312
0x180105409  mov     rcx, [rsp+58h+arg_0]
0x18010540e  test    rcx, rcx
0x180105411  jz      short loc_18010541F
0x180105413  mov     rax, [rcx]
0x180105416  mov     rax, [rax+10h]
0x18010541a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010541f  mov     cs:?g_ComMitigationDone@@3_NA, 1; bool g_ComMitigationDone
0x180105426  jmp     loc_1801051EA
```
