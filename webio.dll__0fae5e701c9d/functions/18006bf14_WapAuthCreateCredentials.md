# WapAuthCreateCredentials

- ea: `0x18006bf14`
- end: `0x18006c0da`
- name: `WapAuthCreateCredentials`
- size: `454`
- prototype: `__int64 __fastcall(int, int, int, int, char, __int64, PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18006be4c`

## callees

- `0x180013820`
- `0x18002e460`
- `0x1800391c0`
- `0x18006bf14`
- `0x1800722f0`
- `0x180072c70`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c03f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c03f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18006bfd2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18006bfd2`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006c084`
- `SspiCli!SspiZeroAuthIdentity` at `0x18006c084`
- `SspiCli!SspiCopyAuthIdentity` at `0x18006bfb3`
- `SspiCli!SspiCopyAuthIdentity` at `0x18006bfb3`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006c094`
- `SspiCli!SspiFreeAuthIdentity` at `0x18006c094`

## pseudocode

```c
__int64 __fastcall WapAuthCreateCredentials(
        __int64 a1,
        char a2,
        char a3,
        char a4,
        char a5,
        volatile signed __int32 *a6,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData,
        __int64 a8,
        __int64 a9,
        struct _RTL_CRITICAL_SECTION **a10)
{
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  unsigned int LastError; // edi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v21; // [rsp+58h] [rbp-20h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+60h] [rbp-18h] BYREF

  *a10 = 0;
  v21 = a8;
  AuthDataCopy = 0;
  Heap = (struct _RTL_CRITICAL_SECTION *)WxAllocateHeapEx(a1, 104);
  v13 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0x68u);
    v13[2].OwningThread = (HANDLE)-1LL;
    *(_QWORD *)&v13[2].LockCount = -1;
    v13->SpinCount = -1;
    v13->LockSemaphore = (HANDLE)-1LL;
    LastError = SspiCopyAuthIdentity(AuthData, &AuthDataCopy);
    if ( !LastError )
    {
      if ( InitializeCriticalSectionAndSpinCount(v13 + 1, 0xFA0u) )
      {
        LOBYTE(v15) = a2;
        LOBYTE(v17) = a4;
        LOBYTE(v16) = a3;
        LastError = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, char, PSEC_WINNT_AUTH_IDENTITY_OPAQUE, __int64, __int64, struct _RTL_CRITICAL_SECTION *))(*(_QWORD *)(a1 + 8) + 32LL))(
                      a1,
                      v15,
                      v16,
                      v17,
                      a5,
                      AuthDataCopy,
                      v21,
                      a9,
                      v13);
        if ( LastError )
        {
          DeleteCriticalSection(v13 + 1);
        }
        else
        {
          v13[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)AuthDataCopy;
          AuthDataCopy = 0;
          if ( a6 )
          {
            _InterlockedIncrement(a6);
            v13->OwningThread = (HANDLE)a6;
          }
          LODWORD(v13->DebugInfo) = 1145393731;
          HIDWORD(v13->DebugInfo) = 1;
          *a10 = v13;
          v13 = 0;
        }
      }
      else
      {
        LastError = WaGetLastError();
      }
    }
  }
  else
  {
    LastError = 8;
  }
  if ( AuthDataCopy )
  {
    SspiZeroAuthIdentity(AuthDataCopy);
    SspiFreeAuthIdentity(AuthDataCopy);
    AuthDataCopy = 0;
  }
  if ( v13 )
  {
    v21 = (__int64)v13;
    WxFreeHeapEx(&v21);
  }
  return LastError;
}

```

## disassembly

```asm
0x18006bf14  push    rbp
0x18006bf16  push    rbx
0x18006bf17  push    rsi
0x18006bf18  push    rdi
0x18006bf19  push    r12
0x18006bf1b  push    r13
0x18006bf1d  push    r14
0x18006bf1f  push    r15
0x18006bf21  mov     rbp, rsp
0x18006bf24  sub     rsp, 78h
0x18006bf28  mov     rax, cs:__security_cookie
0x18006bf2f  xor     rax, rsp
0x18006bf32  mov     [rbp+var_10], rax
0x18006bf36  mov     rax, [rbp+arg_38]
0x18006bf3d  mov     r12b, dl
0x18006bf40  mov     r15, [rbp+arg_48]
0x18006bf47  mov     r14d, 68h ; 'h'
0x18006bf4d  mov     rsi, [rbp+arg_28]
0x18006bf51  mov     edx, r14d
0x18006bf54  mov     rdi, [rbp+AuthData]
0x18006bf58  mov     r13, rcx
0x18006bf5b  mov     [rbp+var_28], r9b
0x18006bf5f  mov     qword ptr [r15], 0
0x18006bf66  mov     [rbp+var_27], r8b
0x18006bf6a  mov     [rbp+var_20], rax
0x18006bf6e  mov     [rbp+AuthDataCopy], 0
0x18006bf76  call    WxAllocateHeapEx
0x18006bf7b  mov     rbx, rax
0x18006bf7e  test    rax, rax
0x18006bf81  jnz     short loc_18006BF8B
0x18006bf83  lea     edi, [rax+8]
0x18006bf86  jmp     loc_18006C07B
0x18006bf8b  mov     r8, r14; Size
0x18006bf8e  xor     edx, edx; Val
0x18006bf90  mov     rcx, rbx; void *
0x18006bf93  call    memset_0
0x18006bf98  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006bf9c  lea     rdx, [rbp+AuthDataCopy]; AuthDataCopy
0x18006bfa0  mov     rcx, rdi; AuthData
0x18006bfa3  mov     [rbx+60h], rax
0x18006bfa7  mov     [rbx+58h], rax
0x18006bfab  mov     [rbx+20h], rax
0x18006bfaf  mov     [rbx+18h], rax
0x18006bfb3  call    cs:__imp_SspiCopyAuthIdentity
0x18006bfba  nop     dword ptr [rax+rax+00h]
0x18006bfbf  mov     edi, eax
0x18006bfc1  test    eax, eax
0x18006bfc3  jnz     loc_18006C07B
0x18006bfc9  mov     edx, 0FA0h; dwSpinCount
0x18006bfce  lea     rcx, [rbx+28h]; lpCriticalSection
0x18006bfd2  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18006bfd9  nop     dword ptr [rax+rax+00h]
0x18006bfde  test    eax, eax
0x18006bfe0  jnz     short loc_18006BFEE
0x18006bfe2  call    WaGetLastError
0x18006bfe7  mov     edi, eax
0x18006bfe9  jmp     loc_18006C07B
0x18006bfee  mov     r10, [rbp+arg_40]
0x18006bff5  mov     dl, r12b
0x18006bff8  mov     rax, [r13+8]
0x18006bffc  mov     rcx, [rbp+var_20]
0x18006c000  mov     r9b, [rbp+var_28]
0x18006c004  mov     r8b, [rbp+var_27]
0x18006c008  mov     rax, [rax+20h]
0x18006c00c  mov     [rsp+78h+var_38], rbx
0x18006c011  mov     [rsp+78h+var_40], r10
0x18006c016  mov     r10, [rbp+AuthDataCopy]
0x18006c01a  mov     [rsp+78h+var_48], rcx
0x18006c01f  mov     rcx, r13
0x18006c022  mov     [rsp+78h+var_50], r10
0x18006c027  mov     r10b, [rbp+arg_20]
0x18006c02b  mov     [rsp+78h+var_58], r10b
0x18006c030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c035  mov     edi, eax
0x18006c037  test    eax, eax
0x18006c039  jz      short loc_18006C04D
0x18006c03b  lea     rcx, [rbx+28h]; lpCriticalSection
0x18006c03f  call    cs:__imp_DeleteCriticalSection
0x18006c046  nop     dword ptr [rax+rax+00h]
0x18006c04b  jmp     short loc_18006C07B
0x18006c04d  mov     rax, [rbp+AuthDataCopy]
0x18006c051  mov     [rbx+50h], rax
0x18006c055  mov     [rbp+AuthDataCopy], 0
0x18006c05d  test    rsi, rsi
0x18006c060  jz      short loc_18006C069
0x18006c062  lock inc dword ptr [rsi]
0x18006c065  mov     [rbx+10h], rsi
0x18006c069  mov     dword ptr [rbx], 44455243h
0x18006c06f  mov     dword ptr [rbx+4], 1
0x18006c076  mov     [r15], rbx
0x18006c079  xor     ebx, ebx
0x18006c07b  mov     rcx, [rbp+AuthDataCopy]; AuthData
0x18006c07f  test    rcx, rcx
0x18006c082  jz      short loc_18006C0A8
0x18006c084  call    cs:__imp_SspiZeroAuthIdentity
0x18006c08b  nop     dword ptr [rax+rax+00h]
0x18006c090  mov     rcx, [rbp+AuthDataCopy]; AuthData
0x18006c094  call    cs:__imp_SspiFreeAuthIdentity
0x18006c09b  nop     dword ptr [rax+rax+00h]
0x18006c0a0  mov     [rbp+AuthDataCopy], 0
0x18006c0a8  test    rbx, rbx
0x18006c0ab  jz      short loc_18006C0BA
0x18006c0ad  lea     rcx, [rbp+var_20]
0x18006c0b1  mov     [rbp+var_20], rbx
0x18006c0b5  call    WxFreeHeapEx
0x18006c0ba  mov     eax, edi
0x18006c0bc  mov     rcx, [rbp+var_10]
0x18006c0c0  xor     rcx, rsp; StackCookie
0x18006c0c3  call    __security_check_cookie
0x18006c0c8  add     rsp, 78h
0x18006c0cc  pop     r15
0x18006c0ce  pop     r14
0x18006c0d0  pop     r13
0x18006c0d2  pop     r12
0x18006c0d4  pop     rdi
0x18006c0d5  pop     rsi
0x18006c0d6  pop     rbx
0x18006c0d7  pop     rbp
0x18006c0d8  retn
```
