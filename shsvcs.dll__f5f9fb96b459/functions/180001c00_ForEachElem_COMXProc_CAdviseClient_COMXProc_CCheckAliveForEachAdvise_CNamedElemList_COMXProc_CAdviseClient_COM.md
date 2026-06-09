# ForEachElem<COMXProc::CAdviseClient,COMXProc::CCheckAliveForEachAdvise>(CNamedElemList<COMXProc::CAdviseClient> *,COMXProc::CCheckAliveForEachAdvise *,int)

- ea: `0x180001c00`
- end: `0x180001e78`
- name: `??$ForEachElem@VCAdviseClient@COMXProc@@VCCheckAliveForEachAdvise@2@@@YAJPEAV?$CNamedElemList@VCAdviseClient@COMXProc@@@@PEAVCCheckAliveForEachAdvise@COMXProc@@H@Z`
- size: `632`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001bb0`

## callees

- `0x180001480`
- `0x1800014b0`
- `0x180001c00`
- `0x180003570`
- `0x18001b404`
- `0x180028cf8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001db3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001cc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001cc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ce4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ce4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e4d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001da2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001da2`

## pseudocode

```c
__int64 ForEachElem<COMXProc::CAdviseClient,COMXProc::CCheckAliveForEachAdvise>()
{
  CRefCounted *v0; // rdi
  _DWORD *v1; // rax
  _DWORD *v2; // rbx
  __int64 v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  __int64 ValidHead; // rax
  volatile signed __int32 *v6; // rsi
  __int64 i; // rbp
  __int64 v8; // rdx
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  __int64 v10; // rdx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  __int64 v12; // rdx
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  __int64 v14; // rdx
  int v15; // ebp
  __int64 v16; // rsi
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rdx
  struct _RTL_CRITICAL_SECTION *v20; // rcx
  DWORD v21; // eax
  __int64 v22; // rcx
  __int64 v24; // rdx
  struct _RTL_CRITICAL_SECTION *v25; // rcx

  v0 = COMXProc::g_pnelAdviseClient;
  v1 = operator new(0x28u);
  v2 = v1;
  if ( !v1 )
    return 2147942414LL;
  v1[2] = 1;
  *((_QWORD *)v1 + 2) = 0;
  *(_QWORD *)v1 = &CNamedElemEnum<COMXProc::CAdviseClient>::`vftable';
  *((_QWORD *)v1 + 4) = 0;
  v3 = *((_QWORD *)v0 + 3);
  v4 = (struct _RTL_CRITICAL_SECTION *)(v3 + 8);
  if ( !v3 )
    v4 = 0;
  EnterCriticalSection(v4);
  ValidHead = CNamedElemList<COMXProc::CAdviseClient>::_GetValidHead(v0);
  v6 = (volatile signed __int32 *)ValidHead;
  if ( ValidHead )
  {
    for ( i = CElemSlot<Storage::CDisk>::GetNextValid(ValidHead); i; i = CElemSlot<Storage::CDisk>::GetNextValid(i) )
    {
      CRefCounted::Release((CRefCounted *)v6);
      v6 = (volatile signed __int32 *)i;
    }
    v8 = *((_QWORD *)v0 + 3);
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 64));
    *((_QWORD *)v2 + 4) = v8;
    v9 = (struct _RTL_CRITICAL_SECTION *)(v8 + 8);
    v2[6] = 1;
    if ( !v8 )
      v9 = 0;
    EnterCriticalSection(v9);
    *((_QWORD *)v2 + 2) = v6;
    if ( v6 )
      _InterlockedIncrement(v6 + 2);
    v10 = *((_QWORD *)v2 + 4);
    v11 = (struct _RTL_CRITICAL_SECTION *)(v10 + 8);
    if ( !v10 )
      v11 = 0;
    LeaveCriticalSection(v11);
    CRefCounted::Release((CRefCounted *)v6);
    v12 = *((_QWORD *)v0 + 3);
    v13 = (struct _RTL_CRITICAL_SECTION *)(v12 + 8);
    if ( !v12 )
      v13 = 0;
    LeaveCriticalSection(v13);
    while ( 1 )
    {
      v14 = *((_QWORD *)v2 + 4);
      v15 = 1;
      v16 = 0;
      v17 = (struct _RTL_CRITICAL_SECTION *)(v14 + 8);
      if ( !v14 )
        v17 = 0;
      EnterCriticalSection(v17);
      v18 = *((_QWORD *)v2 + 2);
      if ( v18 )
      {
        if ( v2[6] && *(_QWORD *)(v18 + 16) )
          goto LABEL_27;
        v18 = *(_QWORD *)(v18 + 24);
        if ( v18 )
        {
          while ( !*(_QWORD *)(v18 + 16) )
          {
            v18 = *(_QWORD *)(v18 + 24);
            if ( !v18 )
              goto LABEL_26;
          }
          _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
        }
LABEL_26:
        CRefCounted::Release(*((CRefCounted **)v2 + 2));
        *((_QWORD *)v2 + 2) = v18;
        if ( v18 )
        {
LABEL_27:
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v18 + 16) + 8LL));
          v16 = *(_QWORD *)(v18 + 16);
          v15 = 0;
        }
        v2[6] = 0;
      }
      v19 = *((_QWORD *)v2 + 4);
      v20 = (struct _RTL_CRITICAL_SECTION *)(v19 + 8);
      if ( !v19 )
        v20 = 0;
      LeaveCriticalSection(v20);
      if ( v15 == 1 )
      {
        if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(_DWORD *, __int64))v2)(v2, 1);
        return 1;
      }
      v21 = WaitForSingleObject(*(HANDLE *)(v16 + 32), 0);
      if ( !v21 )
        goto LABEL_35;
      if ( v21 != 258 )
        break;
LABEL_36:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 8), 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(__int64, __int64))v16)(v16, 1);
    }
    GetLastError();
LABEL_35:
    CNamedElemList<COMXProc::CAdviseClient>::Remove<unsigned long>(v22, *(unsigned int *)(v16 + 16));
    goto LABEL_36;
  }
  (**(void (__fastcall ***)(_DWORD *, __int64))v2)(v2, 1);
  v24 = *((_QWORD *)v0 + 3);
  v25 = (struct _RTL_CRITICAL_SECTION *)(v24 + 8);
  if ( !v24 )
    v25 = 0;
  LeaveCriticalSection(v25);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180001c00  mov     [rsp+arg_18], rbx
0x180001c05  push    rsi
0x180001c06  push    rdi
0x180001c07  push    r15
0x180001c09  sub     rsp, 20h
0x180001c0d  mov     rdi, cs:?g_pnelAdviseClient@COMXProc@@3PEAV?$CNamedElemList@VCAdviseClient@COMXProc@@@@EA; CNamedElemList<COMXProc::CAdviseClient> * COMXProc::g_pnelAdviseClient
0x180001c14  mov     ecx, 28h ; '('; Size
0x180001c19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c1e  mov     rbx, rax
0x180001c21  test    rax, rax
0x180001c24  jz      loc_180001E63
0x180001c2a  xor     r15d, r15d
0x180001c2d  mov     dword ptr [rax+8], 1
0x180001c34  lea     rax, ??_7?$CNamedElemEnum@VCAdviseClient@COMXProc@@@@6B@; const CNamedElemEnum<COMXProc::CAdviseClient>::`vftable'
0x180001c3b  mov     [rbx+10h], r15
0x180001c3f  mov     [rbx], rax
0x180001c42  mov     [rbx+20h], r15
0x180001c46  mov     rdx, [rdi+18h]
0x180001c4a  test    rdx, rdx
0x180001c4d  lea     rcx, [rdx+8]
0x180001c51  cmovz   rcx, r15; lpCriticalSection
0x180001c55  call    cs:__imp_EnterCriticalSection
0x180001c5b  mov     rcx, rdi
0x180001c5e  call    ?_GetValidHead@?$CNamedElemList@VCAdviseClient@COMXProc@@@@AEBAPEAV?$CElemSlot@VCAdviseClient@COMXProc@@@@XZ; CNamedElemList<COMXProc::CAdviseClient>::_GetValidHead(void)
0x180001c63  mov     rsi, rax
0x180001c66  test    rax, rax
0x180001c69  jz      loc_180001E26
0x180001c6f  mov     [rsp+38h+arg_0], rbp
0x180001c74  mov     rcx, rax
0x180001c77  mov     [rsp+38h+arg_8], r14
0x180001c7c  call    ?GetNextValid@?$CElemSlot@VCDisk@Storage@@@@QEBAPEAV1@XZ; CElemSlot<Storage::CDisk>::GetNextValid(void)
0x180001c81  mov     rbp, rax
0x180001c84  test    rax, rax
0x180001c87  jz      short loc_180001CA4
0x180001c89  mov     rcx, rsi; this
0x180001c8c  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180001c91  mov     rcx, rbp
0x180001c94  mov     rsi, rbp
0x180001c97  call    ?GetNextValid@?$CElemSlot@VCDisk@Storage@@@@QEBAPEAV1@XZ; CElemSlot<Storage::CDisk>::GetNextValid(void)
0x180001c9c  mov     rbp, rax
0x180001c9f  test    rax, rax
0x180001ca2  jnz     short loc_180001C89
0x180001ca4  mov     rdx, [rdi+18h]
0x180001ca8  lock inc dword ptr [rdx+40h]
0x180001cac  test    rdx, rdx
0x180001caf  mov     [rbx+20h], rdx
0x180001cb3  lea     rcx, [rdx+8]
0x180001cb7  mov     dword ptr [rbx+18h], 1
0x180001cbe  cmovz   rcx, r15; lpCriticalSection
0x180001cc2  call    cs:__imp_EnterCriticalSection
0x180001cc8  mov     [rbx+10h], rsi
0x180001ccc  test    rsi, rsi
0x180001ccf  jz      short loc_180001CD5
0x180001cd1  lock inc dword ptr [rsi+8]
0x180001cd5  mov     rdx, [rbx+20h]
0x180001cd9  test    rdx, rdx
0x180001cdc  lea     rcx, [rdx+8]
0x180001ce0  cmovz   rcx, r15; lpCriticalSection
0x180001ce4  call    cs:__imp_LeaveCriticalSection
0x180001cea  mov     rcx, rsi; this
0x180001ced  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180001cf2  mov     rdx, [rdi+18h]
0x180001cf6  test    rdx, rdx
0x180001cf9  lea     rcx, [rdx+8]
0x180001cfd  cmovz   rcx, r15; lpCriticalSection
0x180001d01  call    cs:__imp_LeaveCriticalSection
0x180001d07  mov     r14d, 0FFFFFFFFh
0x180001d0d  mov     rdx, [rbx+20h]
0x180001d11  mov     ebp, 1
0x180001d16  test    rdx, rdx
0x180001d19  mov     rsi, r15
0x180001d1c  lea     rcx, [rdx+8]
0x180001d20  cmovz   rcx, r15; lpCriticalSection
0x180001d24  call    cs:__imp_EnterCriticalSection
0x180001d2a  mov     rdi, [rbx+10h]
0x180001d2e  test    rdi, rdi
0x180001d31  jz      short loc_180001D82
0x180001d33  cmp     [rbx+18h], r15d
0x180001d37  jz      short loc_180001D3F
0x180001d39  cmp     [rdi+10h], r15
0x180001d3d  jnz     short loc_180001D6F
0x180001d3f  mov     rdi, [rdi+18h]
0x180001d43  test    rdi, rdi
0x180001d46  jz      short loc_180001D5D
0x180001d48  cmp     [rdi+10h], r15
0x180001d4c  jnz     short loc_180001D59
0x180001d4e  mov     rdi, [rdi+18h]
0x180001d52  test    rdi, rdi
0x180001d55  jnz     short loc_180001D48
0x180001d57  jmp     short loc_180001D5D
0x180001d59  lock inc dword ptr [rdi+8]
0x180001d5d  mov     rcx, [rbx+10h]; this
0x180001d61  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180001d66  mov     [rbx+10h], rdi
0x180001d6a  test    rdi, rdi
0x180001d6d  jz      short loc_180001D7E
0x180001d6f  mov     rax, [rdi+10h]
0x180001d73  lock inc dword ptr [rax+8]
0x180001d77  mov     rsi, [rdi+10h]
0x180001d7b  mov     ebp, r15d
0x180001d7e  mov     [rbx+18h], r15d
0x180001d82  mov     rdx, [rbx+20h]
0x180001d86  test    rdx, rdx
0x180001d89  lea     rcx, [rdx+8]
0x180001d8d  cmovz   rcx, r15; lpCriticalSection
0x180001d91  call    cs:__imp_LeaveCriticalSection
0x180001d97  cmp     ebp, 1
0x180001d9a  jz      short loc_180001DED
0x180001d9c  mov     rcx, [rsi+20h]; hHandle
0x180001da0  xor     edx, edx; dwMilliseconds
0x180001da2  call    cs:__imp_WaitForSingleObject
0x180001da8  test    eax, eax
0x180001daa  jz      short loc_180001DB9
0x180001dac  cmp     eax, 102h
0x180001db1  jz      short loc_180001DC1
0x180001db3  call    cs:__imp_GetLastError
0x180001db9  mov     edx, [rsi+10h]
0x180001dbc  call    ??$Remove@K@?$CNamedElemList@VCAdviseClient@COMXProc@@@@QEAAJK@Z; CNamedElemList<COMXProc::CAdviseClient>::Remove<ulong>(ulong)
0x180001dc1  mov     ebp, r15d
0x180001dc4  mov     eax, r14d
0x180001dc7  lock xadd [rsi+8], eax
0x180001dcc  cmp     eax, 1
0x180001dcf  jnz     short loc_180001DE4
0x180001dd1  mov     rax, [rsi]
0x180001dd4  mov     edx, 1
0x180001dd9  mov     rcx, rsi
0x180001ddc  mov     rax, [rax]
0x180001ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001de4  cmp     ebp, 1
0x180001de7  jnz     loc_180001D0D
0x180001ded  lock xadd [rbx+8], r14d
0x180001df3  cmp     r14d, 1
0x180001df7  mov     r14, [rsp+38h+arg_8]
0x180001dfc  jnz     short loc_180001E11
0x180001dfe  mov     rcx, [rbx]
0x180001e01  mov     edx, 1
0x180001e06  mov     rax, [rcx]
0x180001e09  mov     rcx, rbx
0x180001e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e11  mov     eax, ebp
0x180001e13  mov     rbp, [rsp+38h+arg_0]
0x180001e18  mov     rbx, [rsp+38h+arg_18]
0x180001e1d  add     rsp, 20h
0x180001e21  pop     r15
0x180001e23  pop     rdi
0x180001e24  pop     rsi
0x180001e25  retn
0x180001e26  mov     rax, [rbx]
0x180001e29  mov     edx, 1
0x180001e2e  mov     rcx, rbx
0x180001e31  mov     esi, 80004005h
0x180001e36  mov     rax, [rax]
0x180001e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e3e  mov     rdx, [rdi+18h]
0x180001e42  test    rdx, rdx
0x180001e45  lea     rcx, [rdx+8]
0x180001e49  cmovz   rcx, r15; lpCriticalSection
0x180001e4d  call    cs:__imp_LeaveCriticalSection
0x180001e53  mov     eax, esi
0x180001e55  mov     rbx, [rsp+38h+arg_18]
0x180001e5a  add     rsp, 20h
0x180001e5e  pop     r15
0x180001e60  pop     rdi
0x180001e61  pop     rsi
0x180001e62  retn
0x180001e63  mov     rbx, [rsp+38h+arg_18]
0x180001e68  mov     esi, 8007000Eh
0x180001e6d  mov     eax, esi
0x180001e6f  add     rsp, 20h
0x180001e73  pop     r15
0x180001e75  pop     rdi
0x180001e76  pop     rsi
0x180001e77  retn
```
