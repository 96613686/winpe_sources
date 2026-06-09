# CNamedElemList<PnP::CMiscDeviceInterface>::Remove<ushort const *>(ushort const * const)

- ea: `0x1800033f0`
- end: `0x18000355f`
- name: `??$Remove@PEBG@?$CNamedElemList@VCMiscDeviceInterface@PnP@@@@QEAAJQEBG@Z`
- size: `367`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800036e0`
- `0x180004790`

## callees

- `0x1800014b0`
- `0x1800033f0`
- `0x180003570`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000341e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000341e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000354e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000354e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003465`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003465`

## pseudocode

```c
__int64 __fastcall CNamedElemList<PnP::CMiscDeviceInterface>::Remove<unsigned short const *>(
        __int64 a1,
        const WCHAR *a2)
{
  CRefCounted *v2; // r13
  __int64 v4; // r8
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  __int64 ValidHead; // rsi
  __int64 v7; // rbx
  CRefCounted *v8; // rbp
  __int64 v9; // rdi
  int v10; // r14d
  unsigned int v11; // ebx
  __int64 v12; // r8
  struct _RTL_CRITICAL_SECTION *v13; // rcx

  v2 = PnP::g_pnelMiscDeviceInterface;
  v4 = *((_QWORD *)PnP::g_pnelMiscDeviceInterface + 3);
  v5 = (struct _RTL_CRITICAL_SECTION *)(v4 + 8);
  if ( !v4 )
    v5 = 0;
  EnterCriticalSection(v5);
  ValidHead = CNamedElemList<COMXProc::CAdviseClient>::_GetValidHead(v2);
  v7 = ValidHead;
  v8 = 0;
  while ( ValidHead && !v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(ValidHead + 16) + 24LL));
    v9 = *(_QWORD *)(ValidHead + 16);
    v10 = lstrcmpiW(a2, *(LPCWSTR *)(v9 + 8));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 24), 0xFFFFFFFF) == 1 && v9 != -16 )
      (**(void (__fastcall ***)(__int64, __int64))(v9 + 16))(v9 + 16, 1);
    if ( !v10 )
    {
      v8 = (CRefCounted *)ValidHead;
LABEL_11:
      _InterlockedIncrement((volatile signed __int32 *)(ValidHead + 8));
      goto LABEL_12;
    }
    ValidHead = *(_QWORD *)(ValidHead + 32);
    if ( ValidHead )
    {
      while ( !*(_QWORD *)(ValidHead + 16) )
      {
        ValidHead = *(_QWORD *)(ValidHead + 32);
        if ( !ValidHead )
          goto LABEL_12;
      }
      goto LABEL_11;
    }
LABEL_12:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) == 1 )
    {
      if ( v7 )
        (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
    }
    v7 = ValidHead;
  }
  if ( v8 )
  {
    CRefCounted::Release((CRefCounted *)(*((_QWORD *)v8 + 2) + 16LL));
    *((_QWORD *)v8 + 2) = 0;
    v11 = 0;
    CRefCounted::Release(v8);
    CRefCounted::Release(v8);
    --*((_DWORD *)v2 + 8);
  }
  else
  {
    v11 = -2147467259;
  }
  v12 = *((_QWORD *)v2 + 3);
  v13 = (struct _RTL_CRITICAL_SECTION *)(v12 + 8);
  if ( !v12 )
    v13 = 0;
  LeaveCriticalSection(v13);
  return v11;
}

```

## disassembly

```asm
0x1800033f0  push    rbx
0x1800033f2  push    rbp
0x1800033f3  push    r13
0x1800033f5  sub     rsp, 30h
0x1800033f9  mov     r13, cs:?g_pnelMiscDeviceInterface@PnP@@3PEAV?$CNamedElemList@VCMiscDeviceInterface@PnP@@@@EA; CNamedElemList<PnP::CMiscDeviceInterface> * PnP::g_pnelMiscDeviceInterface
0x180003400  xor     eax, eax
0x180003402  mov     [rsp+48h+arg_8], rsi
0x180003407  mov     [rsp+48h+var_28], r15
0x18000340c  mov     r15, rdx
0x18000340f  mov     r8, [r13+18h]
0x180003413  test    r8, r8
0x180003416  lea     rcx, [r8+8]
0x18000341a  cmovz   rcx, rax; lpCriticalSection
0x18000341e  call    cs:__imp_EnterCriticalSection
0x180003424  mov     rcx, r13
0x180003427  call    ?_GetValidHead@?$CNamedElemList@VCAdviseClient@COMXProc@@@@AEBAPEAV?$CElemSlot@VCAdviseClient@COMXProc@@@@XZ; CNamedElemList<COMXProc::CAdviseClient>::_GetValidHead(void)
0x18000342c  mov     [rsp+48h+arg_10], rdi
0x180003431  mov     rsi, rax
0x180003434  mov     rbx, rax
0x180003437  mov     [rsp+48h+var_20], r14
0x18000343c  xor     ebp, ebp
0x18000343e  xchg    ax, ax
0x180003440  test    rsi, rsi
0x180003443  jz      loc_1800034F2
0x180003449  test    rbp, rbp
0x18000344c  jnz     loc_1800034F2
0x180003452  mov     rax, [rsi+10h]
0x180003456  lock inc dword ptr [rax+18h]
0x18000345a  mov     rdi, [rsi+10h]
0x18000345e  mov     rcx, r15; lpString1
0x180003461  mov     rdx, [rdi+8]; lpString2
0x180003465  call    cs:__imp_lstrcmpiW
0x18000346b  lea     rcx, [rdi+10h]
0x18000346f  mov     edx, 0FFFFFFFFh
0x180003474  mov     r14d, eax
0x180003477  lock xadd [rcx+8], edx
0x18000347c  cmp     edx, 1
0x18000347f  jnz     short loc_180003496
0x180003481  test    rcx, rcx
0x180003484  jz      short loc_180003496
0x180003486  mov     rdx, [rcx]
0x180003489  mov     rax, [rdx]
0x18000348c  mov     edx, 1
0x180003491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003496  test    r14d, r14d
0x180003499  jnz     short loc_1800034D1
0x18000349b  mov     rbp, rsi
0x18000349e  lock inc dword ptr [rsi+8]
0x1800034a2  mov     eax, 0FFFFFFFFh
0x1800034a7  lock xadd [rbx+8], eax
0x1800034ac  cmp     eax, 1
0x1800034af  jnz     short loc_1800034C9
0x1800034b1  test    rbx, rbx
0x1800034b4  jz      short loc_1800034C9
0x1800034b6  mov     rax, [rbx]
0x1800034b9  mov     edx, 1
0x1800034be  mov     rcx, rbx
0x1800034c1  mov     rax, [rax]
0x1800034c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c9  mov     rbx, rsi
0x1800034cc  jmp     loc_180003440
0x1800034d1  mov     rsi, [rsi+20h]
0x1800034d5  test    rsi, rsi
0x1800034d8  jz      short loc_1800034A2
0x1800034da  nop     word ptr [rax+rax+00h]
0x1800034e0  cmp     qword ptr [rsi+10h], 0
0x1800034e5  jnz     short loc_18000349E
0x1800034e7  mov     rsi, [rsi+20h]
0x1800034eb  test    rsi, rsi
0x1800034ee  jnz     short loc_1800034E0
0x1800034f0  jmp     short loc_1800034A2
0x1800034f2  mov     r15, [rsp+48h+var_28]
0x1800034f7  mov     r14, [rsp+48h+var_20]
0x1800034fc  mov     rdi, [rsp+48h+arg_10]
0x180003501  mov     rsi, [rsp+48h+arg_8]
0x180003506  test    rbp, rbp
0x180003509  jnz     short loc_180003512
0x18000350b  mov     ebx, 80004005h
0x180003510  jmp     short loc_18000353D
0x180003512  mov     rcx, [rbp+10h]
0x180003516  add     rcx, 10h; this
0x18000351a  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x18000351f  mov     rcx, rbp; this
0x180003522  mov     qword ptr [rbp+10h], 0
0x18000352a  xor     ebx, ebx
0x18000352c  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180003531  mov     rcx, rbp; this
0x180003534  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180003539  dec     dword ptr [r13+20h]
0x18000353d  mov     r8, [r13+18h]
0x180003541  xor     edx, edx
0x180003543  test    r8, r8
0x180003546  lea     rcx, [r8+8]
0x18000354a  cmovz   rcx, rdx; lpCriticalSection
0x18000354e  call    cs:__imp_LeaveCriticalSection
0x180003554  mov     eax, ebx
0x180003556  add     rsp, 30h
0x18000355a  pop     r13
0x18000355c  pop     rbp
0x18000355d  pop     rbx
0x18000355e  retn
```
