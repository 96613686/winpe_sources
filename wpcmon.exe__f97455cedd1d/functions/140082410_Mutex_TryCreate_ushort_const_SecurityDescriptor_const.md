# Mutex::TryCreate(ushort const *,SecurityDescriptor const *)

- ea: `0x140082410`
- end: `0x14008259f`
- name: `?TryCreate@Mutex@@SA?AVAutoRelease@1@PEBGPEBVSecurityDescriptor@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e4ac`
- `0x14000edf0`

## callees

- `0x1400057f0`
- `0x140006338`
- `0x14001f6b4`
- `0x140060f58`
- `0x1400822d4`
- `0x140082410`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x14008249e`
- `KERNEL32!CreateMutexW` at `0x14008249e`
- `KERNEL32!CloseHandle` at `0x1400824b6`
- `KERNEL32!CloseHandle` at `0x1400824b6`
- `KERNEL32!GetLastError` at `0x1400824c3`
- `KERNEL32!GetLastError` at `0x14008253a`
- `KERNEL32!GetLastError` at `0x1400824c3`
- `KERNEL32!GetLastError` at `0x14008253a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mutex::TryCreate(__int64 a1, const WCHAR *a2)
{
  _QWORD *v4; // r14
  void *v5; // rdi
  HANDLE MutexW; // rax
  char *v7; // rcx
  signed int LastError; // eax
  unsigned int v10; // ebx
  _QWORD v11[2]; // [rsp+28h] [rbp-70h] BYREF
  __int128 v12; // [rsp+38h] [rbp-60h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+48h] [rbp-50h] BYREF

  v4 = operator new(0x10u);
  *v4 = &Mutex::`vftable';
  v4[1] = 0;
  v5 = operator new(0x18u);
  *(_OWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 1;
  *((_DWORD *)v5 + 3) = 1;
  *(_QWORD *)v5 = &std::_Ref_count<Mutex>::`vftable';
  *((_QWORD *)v5 + 2) = v4;
  v11[0] = v4;
  v11[1] = v5;
  MutexW = CreateMutexW(0, 1, a2);
  v7 = (char *)v4[1];
  v4[1] = MutexW;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  if ( !v4[1] )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_334811bc4f5a3e630305732fc2139df2_Traceguids, v10);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v10);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( GetLastError() == 183 )
  {
    v12 = 0;
    Mutex::AutoRelease::AutoRelease(a1, &v12);
  }
  else
  {
    Mutex::AutoRelease::AutoRelease(a1, v11);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v5)(v5);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 8LL))(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x140082410  mov     [rsp+arg_10], r8
0x140082415  push    rbx
0x140082416  push    rsi
0x140082417  push    rdi
0x140082418  push    r14
0x14008241a  sub     rsp, 78h
0x14008241e  mov     rbx, rdx
0x140082421  mov     rsi, rcx
0x140082424  mov     ecx, 10h; Size
0x140082429  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008242e  mov     r14, rax
0x140082431  mov     [rsp+98h+arg_10], rax
0x140082439  lea     rax, ??_7Mutex@@6B@; const Mutex::`vftable'
0x140082440  mov     [r14], rax
0x140082443  mov     qword ptr [r14+8], 0
0x14008244b  mov     [rsp+98h+arg_10], r14
0x140082453  mov     ecx, 18h; Size
0x140082458  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008245d  mov     rdi, rax
0x140082460  mov     [rsp+98h+arg_10], rax
0x140082468  xorps   xmm0, xmm0
0x14008246b  movups  xmmword ptr [rax], xmm0
0x14008246e  mov     dword ptr [rax+8], 1
0x140082475  mov     dword ptr [rax+0Ch], 1
0x14008247c  lea     rax, ??_7?$_Ref_count@VMutex@@@std@@6B@; const std::_Ref_count<Mutex>::`vftable'
0x140082483  mov     [rdi], rax
0x140082486  mov     [rdi+10h], r14
0x14008248a  mov     [rsp+98h+var_70], r14
0x14008248f  mov     [rsp+98h+var_68], rdi
0x140082494  mov     r8, rbx; lpName
0x140082497  mov     edx, 1; bInitialOwner
0x14008249c  xor     ecx, ecx; lpMutexAttributes
0x14008249e  call    cs:__imp_CreateMutexW
0x1400824a4  mov     rcx, [r14+8]; hObject
0x1400824a8  mov     [r14+8], rax
0x1400824ac  lea     rax, [rcx-1]
0x1400824b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400824b4  ja      short loc_1400824BC
0x1400824b6  call    cs:__imp_CloseHandle
0x1400824bc  cmp     qword ptr [r14+8], 0
0x1400824c1  jz      short loc_14008253A
0x1400824c3  call    cs:__imp_GetLastError
0x1400824c9  cmp     eax, 0B7h
0x1400824ce  jnz     short loc_1400824E9
0x1400824d0  xorps   xmm0, xmm0
0x1400824d3  movdqu  [rsp+98h+var_60], xmm0
0x1400824d9  lea     rdx, [rsp+98h+var_60]
0x1400824de  mov     rcx, rsi
0x1400824e1  call    ??0AutoRelease@Mutex@@AEAA@AEBV?$shared_ptr@VMutex@@@std@@@Z; Mutex::AutoRelease::AutoRelease(std::shared_ptr<Mutex> const &)
0x1400824e6  nop
0x1400824e7  jmp     short loc_1400824F7
0x1400824e9  lea     rdx, [rsp+98h+var_70]
0x1400824ee  mov     rcx, rsi
0x1400824f1  call    ??0AutoRelease@Mutex@@AEAA@AEBV?$shared_ptr@VMutex@@@std@@@Z; Mutex::AutoRelease::AutoRelease(std::shared_ptr<Mutex> const &)
0x1400824f6  nop
0x1400824f7  or      ebx, 0FFFFFFFFh
0x1400824fa  mov     eax, ebx
0x1400824fc  lock xadd [rdi+8], eax
0x140082501  add     eax, ebx
0x140082503  jnz     short loc_14008252D
0x140082505  mov     rax, [rdi]
0x140082508  mov     rcx, rdi
0x14008250b  mov     rax, [rax]
0x14008250e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082513  mov     eax, ebx
0x140082515  lock xadd [rdi+0Ch], eax
0x14008251a  add     eax, ebx
0x14008251c  jnz     short loc_14008252D
0x14008251e  mov     rax, [rdi]
0x140082521  mov     rcx, rdi
0x140082524  mov     rax, [rax+8]
0x140082528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008252d  mov     rax, rsi
0x140082530  add     rsp, 78h
0x140082534  pop     r14
0x140082536  pop     rdi
0x140082537  pop     rsi
0x140082538  pop     rbx
0x140082539  retn
0x14008253a  call    cs:__imp_GetLastError
0x140082540  nop
0x140082541  mov     ebx, eax
0x140082543  test    eax, eax
0x140082545  jle     short loc_140082550
0x140082547  movzx   ebx, ax
0x14008254a  or      ebx, 80070000h
0x140082550  lea     rax, WPP_GLOBAL_Control
0x140082557  mov     rcx, cs:WPP_GLOBAL_Control
0x14008255e  cmp     rcx, rax
0x140082561  jz      short loc_140082581
0x140082563  test    byte ptr [rcx+1Ch], 1
0x140082567  jz      short loc_140082581
0x140082569  mov     edx, 0Ch
0x14008256e  mov     r9d, ebx
0x140082571  lea     r8, WPP_334811bc4f5a3e630305732fc2139df2_Traceguids
0x140082578  mov     rcx, [rcx+10h]
0x14008257c  call    WPP_SF_d
0x140082581  mov     edx, ebx; int
0x140082583  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140082588  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14008258d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140082594  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140082599  call    _CxxThrowException_0
```
