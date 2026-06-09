# CNamedElemList<COMXProc::CAdviseClient>::Remove<ulong>(ulong)

- ea: `0x180028cf8`
- end: `0x180028d9e`
- name: `??$Remove@K@?$CNamedElemList@VCAdviseClient@COMXProc@@@@QEAAJK@Z`
- size: `166`
- prototype: `__int64 __fastcall(CRefCounted *, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001c00`
- `0x180002890`
- `0x1800291e0`
- `0x180029c90`

## callees

- `0x180003570`
- `0x180028cf8`
- `0x180028ec4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028d26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028d86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028d86`

## pseudocode

```c
__int64 __fastcall CNamedElemList<COMXProc::CAdviseClient>::Remove<unsigned long>(CRefCounted *a1, int a2)
{
  CRefCounted *v2; // rdi
  int Elem; // esi
  CRefCounted *v5; // rbx
  CRefCounted *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = a1;
  v2 = COMXProc::g_pnelAdviseClient;
  EnterCriticalSection((LPCRITICAL_SECTION)((*((_QWORD *)COMXProc::g_pnelAdviseClient + 3) + 8LL)
                                          & -(__int64)(*((_QWORD *)COMXProc::g_pnelAdviseClient + 3) != 0)));
  v7 = 0;
  Elem = CNamedElemList<COMXProc::CAdviseClient>::_GetElemSlot<unsigned long>((__int64)v2, a2, (__int64 *)&v7);
  if ( Elem >= 0 )
  {
    v5 = v7;
    CRefCounted::Release(*((CRefCounted **)v7 + 2));
    *((_QWORD *)v5 + 2) = 0;
    Elem = 0;
    CRefCounted::Release(v5);
    CRefCounted::Release(v5);
    --*((_DWORD *)v2 + 8);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((*((_QWORD *)v2 + 3) + 8LL) & -(__int64)(*((_QWORD *)v2 + 3) != 0)));
  return (unsigned int)Elem;
}

```

## disassembly

```asm
0x180028cf8  mov     [rsp+arg_8], rbx
0x180028cfd  mov     [rsp+arg_10], rsi
0x180028d02  mov     [rsp+arg_0], rcx
0x180028d07  push    rdi
0x180028d08  sub     rsp, 20h
0x180028d0c  mov     rdi, cs:?g_pnelAdviseClient@COMXProc@@3PEAV?$CNamedElemList@VCAdviseClient@COMXProc@@@@EA; CNamedElemList<COMXProc::CAdviseClient> * COMXProc::g_pnelAdviseClient
0x180028d13  mov     ebx, edx
0x180028d15  mov     rax, [rdi+18h]
0x180028d19  lea     r8, [rax+8]
0x180028d1d  neg     rax
0x180028d20  sbb     rcx, rcx
0x180028d23  and     rcx, r8; lpCriticalSection
0x180028d26  call    cs:__imp_EnterCriticalSection
0x180028d2c  lea     r8, [rsp+28h+arg_0]
0x180028d31  mov     [rsp+28h+arg_0], 0
0x180028d3a  mov     edx, ebx
0x180028d3c  mov     rcx, rdi
0x180028d3f  call    ??$_GetElemSlot@K@?$CNamedElemList@VCAdviseClient@COMXProc@@@@AEAAJKPEAPEAV?$CElemSlot@VCAdviseClient@COMXProc@@@@@Z; CNamedElemList<COMXProc::CAdviseClient>::_GetElemSlot<ulong>(ulong,CElemSlot<COMXProc::CAdviseClient> * *)
0x180028d44  mov     esi, eax
0x180028d46  test    eax, eax
0x180028d48  js      short loc_180028D75
0x180028d4a  mov     rbx, [rsp+28h+arg_0]
0x180028d4f  mov     rcx, [rbx+10h]; this
0x180028d53  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180028d58  mov     rcx, rbx; this
0x180028d5b  mov     qword ptr [rbx+10h], 0
0x180028d63  xor     esi, esi
0x180028d65  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180028d6a  mov     rcx, rbx; this
0x180028d6d  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180028d72  dec     dword ptr [rdi+20h]
0x180028d75  mov     rax, [rdi+18h]
0x180028d79  lea     rdx, [rax+8]
0x180028d7d  neg     rax
0x180028d80  sbb     rcx, rcx
0x180028d83  and     rcx, rdx; lpCriticalSection
0x180028d86  call    cs:__imp_LeaveCriticalSection
0x180028d8c  mov     rbx, [rsp+28h+arg_8]
0x180028d91  mov     eax, esi
0x180028d93  mov     rsi, [rsp+28h+arg_10]
0x180028d98  add     rsp, 20h
0x180028d9c  pop     rdi
0x180028d9d  retn
```
