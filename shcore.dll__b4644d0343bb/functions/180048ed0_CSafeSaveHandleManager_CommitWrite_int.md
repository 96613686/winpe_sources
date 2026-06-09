# CSafeSaveHandleManager::CommitWrite(int)

- ea: `0x180048ed0`
- end: `0x180049177`
- name: `?CommitWrite@CSafeSaveHandleManager@@UEAAJH@Z`
- size: `679`
- prototype: `__int64 __fastcall(CSafeSaveHandleManager *__hidden this, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ddd4`
- `0x18001b6f4`
- `0x18001b7dc`
- `0x18001c82c`
- `0x180048ed0`
- `0x180049180`
- `0x18006bc34`
- `0x180088764`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049120`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049120`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048f17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048f17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048fac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048fac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180048ff5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180048ff5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180048f82`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180048f82`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x18004905b`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x1800490d3`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x18004914b`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x18004905b`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x1800490d3`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x18004914b`

## string_xrefs

- `0x180049007`: `onecore\internal\shell\inc\impersonationutil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSafeSaveHandleManager::CommitWrite(CSafeSaveHandleManager *this, int a2)
{
  CSafeSaveHandleManagerBase *v4; // rcx
  int v5; // ebp
  __int64 v6; // rsi
  LPCWSTR *v7; // rbx
  __int64 *v9; // rcx
  __int64 v10; // rax
  const char *v11; // r9
  int Error; // eax
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  bool v15; // di
  int v16; // esi
  __int16 v17; // [rsp+30h] [rbp-58h] BYREF
  __int64 v18; // [rsp+38h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = (CSafeSaveHandleManager *)((char *)this - 8);
  if ( *((_BYTE *)v4 + 280) )
    return 2147483678LL;
  if ( !*((_BYTE *)this + 280) )
  {
    v5 = CSafeSaveHandleManagerBase::_TruncatePriorToCommit(v4);
    if ( v5 < 0 )
      return (unsigned int)v5;
    AcquireSRWLockExclusive((PSRWLOCK)this + 2);
    v6 = *((_QWORD *)this + 30);
    IUnknown_Close(*((struct IUnknown **)this + 29));
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease((char *)this + 232);
    IUnknown_Close(*((struct IUnknown **)this + 30));
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease((char *)this + 240);
    if ( !v6 )
    {
LABEL_11:
      v9 = (__int64 *)*((_QWORD *)this + 36);
      if ( v9 )
      {
        v10 = *v9;
        v17 = 0;
        (*(void (__fastcall **)(__int64 *, _QWORD, __int16 *))(v10 + 24))(v9, 0, &v17);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease((char *)this + 288);
      }
LABEL_9:
      ReleaseSRWLockExclusive((PSRWLOCK)this + 2);
      return (unsigned int)v5;
    }
    LOBYTE(v17) = 0;
    v18 = *((_QWORD *)this + 31);
    v5 = CImpersonateLoggedOnUser::Impersonate((CImpersonateLoggedOnUser *)&v17);
    if ( v5 < 0 )
      goto LABEL_6;
    v7 = (LPCWSTR *)((char *)this + 216);
    if ( ReplaceFileW(*((LPCWSTR *)this + 26), *((LPCWSTR *)this + 27), 0, 2u, 0, 0) )
      goto LABEL_19;
    Error = ResultFromKnownLastError();
    v5 = Error;
    if ( Error == -2147022976 )
    {
      if ( (*((_BYTE *)this + 264) & 2) == 0
        || SetPlaceholderReparsePointAndAttributes(*((const unsigned __int16 **)this + 26), 0, v13) < 0 )
      {
LABEL_6:
        v7 = (LPCWSTR *)((char *)this + 216);
        DeleteFileW(*((LPCWSTR *)this + 27));
LABEL_7:
        **v7 = 0;
        *((_BYTE *)this + 272) = a2 == 0;
        if ( (_BYTE)v17 && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x76,
            (unsigned int)"onecore\\internal\\shell\\inc\\impersonationutil.h",
            v11);
        if ( v5 < 0 )
          goto LABEL_9;
        goto LABEL_11;
      }
      if ( ReplaceFileW(*((LPCWSTR *)this + 26), *v7, 0, 2u, 0, 0) )
      {
LABEL_19:
        v5 = 0;
        goto LABEL_7;
      }
      v5 = ResultFromKnownLastError();
      if ( v5 >= 0 )
        goto LABEL_7;
      v15 = SetPlaceholderReparsePointAndAttributes(*((const unsigned __int16 **)this + 26), 1, v14) >= 0;
    }
    else
    {
      v15 = 1;
      if ( Error == -2147024864 )
      {
        v16 = 3;
        while ( 1 )
        {
          Sleep(0xAu);
          if ( ReplaceFileW(*((LPCWSTR *)this + 26), *v7, 0, 2u, 0, 0) )
            goto LABEL_19;
          v5 = ResultFromKnownLastError();
          if ( v5 == -2147024864 && --v16 > 0 )
            continue;
          break;
        }
      }
      if ( v5 >= 0 )
        goto LABEL_7;
    }
    if ( !v15 )
      goto LABEL_7;
    goto LABEL_6;
  }
  return 2147483667LL;
}

```

## disassembly

```asm
0x180048ed0  push    rbx
0x180048ed2  push    rbp
0x180048ed3  push    rsi
0x180048ed4  push    rdi
0x180048ed5  push    r12
0x180048ed7  push    r14
0x180048ed9  push    r15
0x180048edb  sub     rsp, 50h
0x180048edf  mov     r12d, edx
0x180048ee2  mov     r14, rcx
0x180048ee5  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180048ee9  cmp     byte ptr [rcx+118h], 0
0x180048ef0  jnz     loc_18004906C
0x180048ef6  cmp     byte ptr [r14+118h], 0
0x180048efe  jnz     loc_180049076
0x180048f04  call    ?_TruncatePriorToCommit@CSafeSaveHandleManagerBase@@IEAAJXZ; CSafeSaveHandleManagerBase::_TruncatePriorToCommit(void)
0x180048f09  mov     ebp, eax
0x180048f0b  test    eax, eax
0x180048f0d  js      loc_180048FB2
0x180048f13  lea     rcx, [r14+10h]; SRWLock
0x180048f17  call    cs:__imp_AcquireSRWLockExclusive
0x180048f1d  lea     rdi, [r14+0F0h]
0x180048f24  mov     rsi, [rdi]
0x180048f27  lea     rbx, [r14+0E8h]
0x180048f2e  mov     rcx, [rbx]; struct IUnknown *
0x180048f31  call    ?IUnknown_Close@@YAXPEAUIUnknown@@@Z; IUnknown_Close(IUnknown *)
0x180048f36  mov     rcx, rbx
0x180048f39  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180048f3e  mov     rcx, [rdi]; struct IUnknown *
0x180048f41  call    ?IUnknown_Close@@YAXPEAUIUnknown@@@Z; IUnknown_Close(IUnknown *)
0x180048f46  mov     rcx, rdi
0x180048f49  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180048f4e  test    rsi, rsi
0x180048f51  jz      short loc_180048FC3
0x180048f53  mov     byte ptr [rsp+88h+var_58], 0
0x180048f58  mov     rax, [r14+0F8h]
0x180048f5f  mov     [rsp+88h+var_50], rax
0x180048f64  lea     rcx, [rsp+88h+var_58]; this
0x180048f69  call    ?Impersonate@CImpersonateLoggedOnUser@@QEAAJXZ; CImpersonateLoggedOnUser::Impersonate(void)
0x180048f6e  mov     ebp, eax
0x180048f70  test    eax, eax
0x180048f72  jns     loc_18004902D
0x180048f78  lea     rbx, [r14+0D8h]
0x180048f7f  mov     rcx, [rbx]; lpFileName
0x180048f82  call    cs:__imp_DeleteFileW
0x180048f88  mov     rcx, [rbx]
0x180048f8b  xor     eax, eax
0x180048f8d  mov     [rcx], ax
0x180048f90  test    r12d, r12d
0x180048f93  setz    al
0x180048f96  mov     [r14+110h], al
0x180048f9d  cmp     byte ptr [rsp+88h+var_58], 0
0x180048fa2  jnz     short loc_180048FF5
0x180048fa4  test    ebp, ebp
0x180048fa6  jns     short loc_180048FC3
0x180048fa8  lea     rcx, [r14+10h]; SRWLock
0x180048fac  call    cs:__imp_ReleaseSRWLockExclusive
0x180048fb2  mov     eax, ebp
0x180048fb4  add     rsp, 50h
0x180048fb8  pop     r15
0x180048fba  pop     r14
0x180048fbc  pop     r12
0x180048fbe  pop     rdi
0x180048fbf  pop     rsi
0x180048fc0  pop     rbp
0x180048fc1  pop     rbx
0x180048fc2  retn
0x180048fc3  mov     rcx, [r14+120h]
0x180048fca  test    rcx, rcx
0x180048fcd  jz      short loc_180048FA8
0x180048fcf  mov     rax, [rcx]
0x180048fd2  xor     edx, edx
0x180048fd4  mov     [rsp+88h+var_58], dx
0x180048fd9  lea     r8, [rsp+88h+var_58]
0x180048fde  mov     rax, [rax+18h]
0x180048fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fe7  lea     rcx, [r14+120h]
0x180048fee  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180048ff3  jmp     short loc_180048FA8
0x180048ff5  call    cs:__imp_RevertToSelf
0x180048ffb  test    eax, eax
0x180048ffd  jnz     short loc_180048FA4
0x180048fff  mov     rcx, [rsp+88h]; this
0x180049007  lea     r8, aOnecoreInterna_1; "onecore\\internal\\shell\\inc\\imperson"...
0x18004900e  lea     edx, [rax+76h]; void *
0x180049011  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180049017  test    ebp, ebp
0x180049019  jns     loc_180048F88
0x18004901f  test    dil, dil
0x180049022  jz      loc_180048F88
0x180049028  jmp     loc_180048F78
0x18004902d  lea     rbx, [r14+0D8h]
0x180049034  mov     [rsp+88h+lpReserved], 0; lpReserved
0x18004903d  mov     [rsp+88h+lpExclude], 0; lpExclude
0x180049046  mov     edi, 2
0x18004904b  mov     r9d, edi; dwReplaceFlags
0x18004904e  xor     r8d, r8d; lpBackupFileName
0x180049051  mov     rdx, [rbx]; lpReplacementFileName
0x180049054  mov     rcx, [r14+0D0h]; lpReplacedFileName
0x18004905b  call    cs:__imp_ReplaceFileW
0x180049061  test    eax, eax
0x180049063  jz      short loc_180049080
0x180049065  xor     ebp, ebp
0x180049067  jmp     loc_180048F88
0x18004906c  mov     eax, 8000001Eh
0x180049071  jmp     loc_180048FB4
0x180049076  mov     eax, 80000013h
0x18004907b  jmp     loc_180048FB4
0x180049080  call    ResultFromKnownLastError
0x180049085  mov     ebp, eax
0x180049087  cmp     eax, 80070780h
0x18004908c  jnz     short loc_180049108
0x18004908e  test    [r14+108h], dil
0x180049095  jz      loc_180048F78
0x18004909b  xor     edx, edx; bool
0x18004909d  mov     rcx, [r14+0D0h]; unsigned __int16 *
0x1800490a4  call    ?SetPlaceholderReparsePointAndAttributes@@YAJPEBG_NK@Z; SetPlaceholderReparsePointAndAttributes(ushort const *,bool,ulong)
0x1800490a9  test    eax, eax
0x1800490ab  js      loc_180048F78
0x1800490b1  mov     [rsp+88h+lpReserved], 0; lpReserved
0x1800490ba  mov     [rsp+88h+lpExclude], 0; lpExclude
0x1800490c3  mov     r9d, edi; dwReplaceFlags
0x1800490c6  xor     r8d, r8d; lpBackupFileName
0x1800490c9  mov     rdx, [rbx]; lpReplacementFileName
0x1800490cc  mov     rcx, [r14+0D0h]; lpReplacedFileName
0x1800490d3  call    cs:__imp_ReplaceFileW
0x1800490d9  test    eax, eax
0x1800490db  jnz     short loc_180049065
0x1800490dd  call    ResultFromKnownLastError
0x1800490e2  mov     ebp, eax
0x1800490e4  test    eax, eax
0x1800490e6  jns     loc_180048F88
0x1800490ec  mov     dl, 1; bool
0x1800490ee  mov     rcx, [r14+0D0h]; unsigned __int16 *
0x1800490f5  call    ?SetPlaceholderReparsePointAndAttributes@@YAJPEBG_NK@Z; SetPlaceholderReparsePointAndAttributes(ushort const *,bool,ulong)
0x1800490fa  mov     edi, eax
0x1800490fc  shr     edi, 1Fh
0x1800490ff  xor     dil, 1
0x180049103  jmp     loc_18004901F
0x180049108  mov     dil, 1
0x18004910b  cmp     eax, 80070020h
0x180049110  jnz     loc_180049017
0x180049116  mov     esi, 3
0x18004911b  mov     ecx, 0Ah; dwMilliseconds
0x180049120  call    cs:__imp_Sleep
0x180049126  mov     [rsp+88h+lpReserved], 0; lpReserved
0x18004912f  mov     [rsp+88h+lpExclude], 0; lpExclude
0x180049138  mov     r9d, 2; dwReplaceFlags
0x18004913e  xor     r8d, r8d; lpBackupFileName
0x180049141  mov     rdx, [rbx]; lpReplacementFileName
0x180049144  mov     rcx, [r14+0D0h]; lpReplacedFileName
0x18004914b  call    cs:__imp_ReplaceFileW
0x180049151  test    eax, eax
0x180049153  jnz     loc_180049065
0x180049159  call    ResultFromKnownLastError
0x18004915e  mov     ebp, eax
0x180049160  cmp     eax, 80070020h
0x180049165  jnz     loc_180049017
0x18004916b  dec     esi
0x18004916d  test    esi, esi
0x18004916f  jg      short loc_18004911B
0x180049171  jmp     loc_180049017
```
