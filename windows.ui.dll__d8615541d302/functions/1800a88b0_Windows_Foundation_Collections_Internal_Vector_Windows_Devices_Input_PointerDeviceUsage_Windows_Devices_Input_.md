# Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Input::PointerDeviceUsage,Windows::Devices::Input::PointerDeviceUsageEqualityPredicate,Windows::Devices::Input::PointerDeviceUsageLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Input::PointerDeviceUsage>>::RemoveAtInternal(uint,bool)

- ea: `0x1800a88b0`
- end: `0x1800a8a04`
- name: `?RemoveAtInternal@?$Vector@UPointerDeviceUsage@Input@Devices@Windows@@UPointerDeviceUsageEqualityPredicate@234@UPointerDeviceUsageLifetimeTraits@234@U?$DefaultVectorOptions@UPointerDeviceUsage@Input@Devices@Windows@@@Internal@Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800a8890`
- `0x1800a88a0`

## callees

- `0x18002e7e0`
- `0x18002e7fc`
- `0x18003b690`
- `0x18003bc44`
- `0x1800a88b0`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800a8956`
- `msvcrt!memmove_s` at `0x1800a8956`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a89c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a89c8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800a8909`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800a8969`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800a8909`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800a8969`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Input::PointerDeviceUsage,Windows::Devices::Input::PointerDeviceUsageEqualityPredicate,Windows::Devices::Input::PointerDeviceUsageLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Input::PointerDeviceUsage>>::RemoveAtInternal(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  int v6; // ebx
  unsigned int *v7; // rsi
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  RTL_SRWLOCK *v10; // rcx
  int v12; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v13; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  XWinRT::SerializingLockPolicy::Write(&v13, a1 + 80, &v12);
  v6 = v12;
  if ( v12 >= 0 )
  {
    v7 = (unsigned int *)(a1 + 48);
    if ( a3 )
      a2 = *v7 - 1;
    if ( a2 >= *v7 )
    {
      v6 = -2147483637;
      RoOriginateError(2147483659LL, 0);
    }
    if ( v6 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v12, *(unsigned __int8 *)(a1 + 101), a1 + 104);
      v6 = 0;
      if ( a2 < *v7 - 1
        && memmove_s(
             (void *const)(*(_QWORD *)(a1 + 64) + 32LL * a2),
             32LL * (*v7 - a2 - 1),
             (const void *const)(*(_QWORD *)(a1 + 64) + 32LL * (a2 + 1)),
             32LL * (*v7 - a2 - 1)) )
      {
        v6 = -2147418113;
        RoOriginateError(2147549183LL, 0);
      }
      else
      {
        v8 = *(_DWORD *)(a1 + 52);
        ++*(_DWORD *)(a1 + 96);
        if ( --*v7 < v8 / 3 )
        {
          v9 = 1;
          if ( v8 - 1 >= v8 - v8 / 3 )
            v9 = v8 / 3;
          v6 = Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Input::PointerDeviceUsage,Windows::Devices::Input::PointerDeviceUsageEqualityPredicate,Windows::Devices::Input::PointerDeviceUsageLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Input::PointerDeviceUsage>>::ResizeStorage(
                 a1,
                 v8 - v9);
        }
      }
    }
  }
  if ( v13 )
  {
    v10 = v13 + 1;
    if ( LODWORD(v13->Ptr) == 1 )
      LODWORD(v10->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v10);
  }
  if ( v6 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,unsigned __int64,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>::RaiseEvent(
                           (unsigned __int8)v12,
                           *(unsigned __int8 *)(a1 + 100),
                           a1,
                           2,
                           a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a88b0  mov     rax, rsp
0x1800a88b3  mov     [rax+10h], rbx
0x1800a88b7  mov     [rax+18h], rbp
0x1800a88bb  push    rsi
0x1800a88bc  push    rdi
0x1800a88bd  push    r14
0x1800a88bf  sub     rsp, 30h
0x1800a88c3  mov     ebp, edx
0x1800a88c5  mov     dword ptr [rax+8], 0
0x1800a88cc  lea     rdx, [rcx+50h]
0x1800a88d0  mov     r14b, r8b
0x1800a88d3  mov     rdi, rcx
0x1800a88d6  lea     r8, [rax+8]
0x1800a88da  lea     rcx, [rax+20h]
0x1800a88de  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800a88e3  mov     ebx, [rsp+48h+arg_0]
0x1800a88e7  test    ebx, ebx
0x1800a88e9  js      loc_1800A89AD
0x1800a88ef  lea     rsi, [rdi+30h]
0x1800a88f3  test    r14b, r14b
0x1800a88f6  jz      short loc_1800A88FC
0x1800a88f8  mov     ebp, [rsi]
0x1800a88fa  dec     ebp
0x1800a88fc  cmp     ebp, [rsi]
0x1800a88fe  jb      short loc_1800A890F
0x1800a8900  mov     ebx, 8000000Bh
0x1800a8905  xor     edx, edx
0x1800a8907  mov     ecx, ebx
0x1800a8909  call    cs:__imp_RoOriginateError
0x1800a890f  test    ebx, ebx
0x1800a8911  js      loc_1800A89AD
0x1800a8917  movzx   edx, byte ptr [rdi+65h]
0x1800a891b  lea     r8, [rdi+68h]
0x1800a891f  lea     rcx, [rsp+48h+arg_0]
0x1800a8924  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800a8929  mov     ecx, [rsi]
0x1800a892b  xor     ebx, ebx
0x1800a892d  lea     eax, [rcx-1]
0x1800a8930  cmp     ebp, eax
0x1800a8932  jnb     short loc_1800A8971
0x1800a8934  sub     ecx, ebp
0x1800a8936  lea     r8d, [rbp+1]
0x1800a893a  shl     r8, 5
0x1800a893e  add     r8, [rdi+40h]; Source
0x1800a8942  lea     edx, [rcx-1]
0x1800a8945  mov     ecx, ebp
0x1800a8947  shl     rcx, 5
0x1800a894b  add     rcx, [rdi+40h]; Destination
0x1800a894f  shl     rdx, 5; DestinationSize
0x1800a8953  mov     r9, rdx; SourceSize
0x1800a8956  call    cs:__imp_memmove_s
0x1800a895c  test    eax, eax
0x1800a895e  jz      short loc_1800A8971
0x1800a8960  mov     ebx, 8000FFFFh
0x1800a8965  xor     edx, edx
0x1800a8967  mov     ecx, ebx
0x1800a8969  call    cs:__imp_RoOriginateError
0x1800a896f  jmp     short loc_1800A89AD
0x1800a8971  mov     r9d, [rdi+34h]
0x1800a8975  mov     eax, 0AAAAAAABh
0x1800a897a  inc     dword ptr [rdi+60h]
0x1800a897d  dec     dword ptr [rsi]
0x1800a897f  mul     r9d
0x1800a8982  shr     edx, 1
0x1800a8984  cmp     [rsi], edx
0x1800a8986  jnb     short loc_1800A89AD
0x1800a8988  mov     ecx, r9d
0x1800a898b  lea     eax, [r9-1]
0x1800a898f  sub     ecx, edx
0x1800a8991  mov     r8d, 1
0x1800a8997  cmp     eax, ecx
0x1800a8999  mov     rcx, rdi
0x1800a899c  cmovnb  r8d, edx
0x1800a89a0  sub     r9d, r8d
0x1800a89a3  mov     edx, r9d
0x1800a89a6  call    ?ResizeStorage@?$Vector@UPointerDeviceUsage@Input@Devices@Windows@@UPointerDeviceUsageEqualityPredicate@234@UPointerDeviceUsageLifetimeTraits@234@U?$DefaultVectorOptions@UPointerDeviceUsage@Input@Devices@Windows@@@Internal@Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Input::PointerDeviceUsage,Windows::Devices::Input::PointerDeviceUsageEqualityPredicate,Windows::Devices::Input::PointerDeviceUsageLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Input::PointerDeviceUsage>>::ResizeStorage(uint)
0x1800a89ab  mov     ebx, eax
0x1800a89ad  mov     rax, [rsp+48h+arg_18]
0x1800a89b2  test    rax, rax
0x1800a89b5  jz      short loc_1800A89CE
0x1800a89b7  cmp     dword ptr [rax], 1
0x1800a89ba  lea     rcx, [rax+8]; SRWLock
0x1800a89be  jnz     short loc_1800A89C8
0x1800a89c0  add     dword ptr [rcx], 10000000h
0x1800a89c6  jmp     short loc_1800A89CE
0x1800a89c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a89ce  test    ebx, ebx
0x1800a89d0  js      short loc_1800A89EF
0x1800a89d2  movzx   edx, byte ptr [rdi+64h]
0x1800a89d6  mov     r9d, 2
0x1800a89dc  movzx   ecx, byte ptr [rsp+48h+arg_0]
0x1800a89e1  mov     r8, rdi
0x1800a89e4  mov     [rsp+48h+var_28], ebp
0x1800a89e8  call    ?RaiseEvent@?$HashMapOptions@I_KU?$DefaultLifetimeTraits@I@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<uint,unsigned __int64,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>::RaiseEvent(...)
0x1800a89ed  mov     ebx, eax
0x1800a89ef  mov     rbp, [rsp+48h+arg_10]
0x1800a89f4  mov     eax, ebx
0x1800a89f6  mov     rbx, [rsp+48h+arg_8]
0x1800a89fb  add     rsp, 30h
0x1800a89ff  pop     r14
0x1800a8a01  pop     rdi
0x1800a8a02  pop     rsi
0x1800a8a03  retn
```
