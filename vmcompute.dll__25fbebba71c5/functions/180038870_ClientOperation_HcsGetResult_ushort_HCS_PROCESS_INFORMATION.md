# ClientOperation::HcsGetResult(ushort * *,HCS_PROCESS_INFORMATION *)

- ea: `0x180038870`
- end: `0x180038a42`
- name: `?HcsGetResult@ClientOperation@@QEAAJPEAPEAGPEAUHCS_PROCESS_INFORMATION@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, unsigned __int16 **, struct HCS_PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038a48`

## callees

- `0x180003440`
- `0x18000c294`
- `0x180038870`
- `0x180039050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038889`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038889`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038a1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038a10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038a10`

## string_xrefs

- `0x18003890d`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClientOperation::HcsGetResult(
        PSRWLOCK SRWLock,
        unsigned __int16 **a2,
        struct HCS_PROCESS_INFORMATION *a3)
{
  __int64 v6; // r8
  const char *v7; // r9
  unsigned int Ptr; // ebp
  int v9; // ebp
  char *v10; // rdx
  unsigned __int16 *v11; // rdi
  LPVOID v12; // rax
  unsigned __int16 *v13; // rbx
  __int64 v14; // rdx
  PVOID v15; // rax
  PVOID v16; // rax
  PVOID v17; // rax
  unsigned __int16 *v18; // rax
  int v20[2]; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[8]; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  AcquireSRWLockExclusive(SRWLock);
  Ptr = (unsigned int)SRWLock[12].Ptr;
  if ( ((Ptr + 2143878891) & 0xFFFFFFFD) == 0 )
    goto LABEL_29;
  v20[1] = 0;
  v9 = (__int64)SRWLock[13].Ptr & 1;
  v20[0] = v9;
  *(_OWORD *)pv = 0;
  if ( !a2 || (v10 = (char *)SRWLock[11].Ptr) == 0 )
  {
    v11 = (unsigned __int16 *)pv[1];
    v13 = (unsigned __int16 *)pv[0];
    goto LABEL_11;
  }
  Details::ClientStringAllocator::make_string_nothrow((Details::ClientStringAllocator *)v20, v10, v6, v7);
  v11 = (unsigned __int16 *)pv[1];
  v12 = pv[1];
  v13 = (unsigned __int16 *)pv[0];
  v9 = v20[0];
  if ( !v20[0] )
    v12 = pv[0];
  if ( v12 || SLODWORD(SRWLock[12].Ptr) < 0 )
  {
LABEL_11:
    if ( a3 )
    {
      if ( ((HIDWORD(SRWLock[12].Ptr) - 10) & 0xFFFFFFFD) != 0 )
      {
        Ptr = -2147024809;
        v14 = 109;
        goto LABEL_9;
      }
      *(_OWORD *)&a3->ProcessId = 0;
      *(_OWORD *)&a3->StdOutput = 0;
      if ( SLODWORD(SRWLock[12].Ptr) >= 0 )
      {
        if ( !LOBYTE(SRWLock[23].Ptr) )
        {
          Ptr = -2143878883;
          v14 = 116;
          goto LABEL_9;
        }
        a3->ProcessId = (DWORD)SRWLock[19].Ptr;
        v15 = SRWLock[20].Ptr;
        SRWLock[20].Ptr = (PVOID)-1LL;
        a3->StdInput = v15;
        v16 = SRWLock[21].Ptr;
        SRWLock[21].Ptr = (PVOID)-1LL;
        a3->StdOutput = v16;
        v17 = SRWLock[22].Ptr;
        SRWLock[22].Ptr = (PVOID)-1LL;
        a3->StdError = v17;
        if ( LOBYTE(SRWLock[23].Ptr) )
        {
          `eh vector destructor iterator'(
            &SRWLock[20],
            8u,
            3u,
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
          LOBYTE(SRWLock[23].Ptr) = 0;
        }
      }
    }
    if ( a2 )
    {
      if ( v9 )
      {
        v18 = v11;
        v11 = 0;
      }
      else
      {
        v18 = v13;
        v13 = 0;
      }
      *a2 = v18;
    }
    Ptr = (unsigned int)SRWLock[12].Ptr;
    goto LABEL_25;
  }
  Ptr = -2143878886;
  v14 = 103;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\clientoperation.cpp",
    (const char *)Ptr,
    v20[0]);
LABEL_25:
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v13 )
    LocalFree(v13);
LABEL_29:
  ReleaseSRWLockExclusive(SRWLock);
  return Ptr;
}

```

## disassembly

```asm
0x180038870  mov     [rsp+arg_18], rbx
0x180038875  push    rbp
0x180038876  push    rsi
0x180038877  push    rdi
0x180038878  push    r14
0x18003887a  push    r15
0x18003887c  sub     rsp, 40h
0x180038880  mov     r14, r8
0x180038883  mov     r15, rdx
0x180038886  mov     rsi, rcx
0x180038889  call    cs:__imp_AcquireSRWLockExclusive
0x180038890  nop     dword ptr [rax+rax+00h]
0x180038895  mov     ebp, [rsi+60h]
0x180038898  lea     eax, [rbp+7FC8FEEBh]
0x18003889e  test    eax, 0FFFFFFFDh
0x1800388a3  jz      loc_180038A1C
0x1800388a9  mov     [rsp+68h+var_44], 0
0x1800388b1  mov     ebp, [rsi+68h]
0x1800388b4  and     ebp, 1
0x1800388b7  mov     [rsp+68h+var_48], ebp; int
0x1800388bb  xorps   xmm0, xmm0
0x1800388be  movdqu  xmmword ptr [rsp+68h+pv], xmm0
0x1800388c4  test    r15, r15
0x1800388c7  jz      short loc_18003891E
0x1800388c9  mov     rdx, [rsi+58h]; unsigned __int16 *
0x1800388cd  test    rdx, rdx
0x1800388d0  jz      short loc_18003891E
0x1800388d2  lea     rcx, [rsp+68h+var_48]; this
0x1800388d7  call    ?make_string_nothrow@ClientStringAllocator@Details@@QEAAXPEBG@Z; Details::ClientStringAllocator::make_string_nothrow(ushort const *)
0x1800388dc  mov     rdi, [rsp+68h+pv+8]
0x1800388e1  mov     rax, rdi
0x1800388e4  mov     rbx, [rsp+68h+pv]
0x1800388e9  mov     ebp, [rsp+68h+var_48]
0x1800388ed  test    ebp, ebp
0x1800388ef  cmovz   rax, rbx
0x1800388f3  test    rax, rax
0x1800388f6  jnz     short loc_180038928
0x1800388f8  cmp     [rsi+60h], eax
0x1800388fb  jl      short loc_180038928
0x1800388fd  mov     ebp, 8037011Ah
0x180038902  lea     edx, [rax+67h]; void *
0x180038905  mov     rcx, [rsp+68h]; this
0x18003890a  mov     r9d, ebp; char *
0x18003890d  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\dll\\lib\\core\\c"...
0x180038914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038919  jmp     loc_1800389F4
0x18003891e  mov     rdi, [rsp+68h+pv+8]
0x180038923  mov     rbx, [rsp+68h+pv]
0x180038928  test    r14, r14
0x18003892b  jz      loc_1800389D9
0x180038931  mov     eax, [rsi+64h]
0x180038934  sub     eax, 0Ah
0x180038937  test    eax, 0FFFFFFFDh
0x18003893c  jz      short loc_18003894A
0x18003893e  mov     ebp, 80070057h
0x180038943  mov     edx, 6Dh ; 'm'
0x180038948  jmp     short loc_180038905
0x18003894a  xorps   xmm0, xmm0
0x18003894d  movups  xmmword ptr [r14], xmm0
0x180038951  movups  xmmword ptr [r14+10h], xmm0
0x180038956  cmp     dword ptr [rsi+60h], 0
0x18003895a  jl      short loc_1800389D9
0x18003895c  cmp     byte ptr [rsi+0B8h], 0
0x180038963  jnz     short loc_180038971
0x180038965  mov     ebp, 8037011Dh
0x18003896a  mov     edx, 74h ; 't'
0x18003896f  jmp     short loc_180038905
0x180038971  mov     eax, [rsi+98h]
0x180038977  mov     [r14], eax
0x18003897a  lea     rcx, [rsi+0A0h]; void *
0x180038981  mov     rax, [rcx]
0x180038984  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180038988  mov     [rcx], rdx
0x18003898b  mov     [r14+8], rax
0x18003898f  mov     rax, [rsi+0A8h]
0x180038996  mov     [rsi+0A8h], rdx
0x18003899d  mov     [r14+10h], rax
0x1800389a1  mov     rax, [rsi+0B0h]
0x1800389a8  mov     [rsi+0B0h], rdx
0x1800389af  mov     [r14+18h], rax
0x1800389b3  cmp     byte ptr [rsi+0B8h], 0
0x1800389ba  jz      short loc_1800389D9
0x1800389bc  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1800389c3  mov     edx, 8; unsigned __int64
0x1800389c8  lea     r8d, [rdx-5]; unsigned __int64
0x1800389cc  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800389d1  nop
0x1800389d2  mov     byte ptr [rsi+0B8h], 0
0x1800389d9  test    r15, r15
0x1800389dc  jz      short loc_1800389F1
0x1800389de  test    ebp, ebp
0x1800389e0  jnz     short loc_1800389E9
0x1800389e2  mov     rax, rbx
0x1800389e5  xor     ebx, ebx
0x1800389e7  jmp     short loc_1800389EE
0x1800389e9  mov     rax, rdi
0x1800389ec  xor     edi, edi
0x1800389ee  mov     [r15], rax
0x1800389f1  mov     ebp, [rsi+60h]
0x1800389f4  test    rdi, rdi
0x1800389f7  jz      short loc_180038A08
0x1800389f9  mov     rcx, rdi; pv
0x1800389fc  call    cs:__imp_CoTaskMemFree
0x180038a03  nop     dword ptr [rax+rax+00h]
0x180038a08  test    rbx, rbx
0x180038a0b  jz      short loc_180038A1C
0x180038a0d  mov     rcx, rbx; hMem
0x180038a10  call    cs:__imp_LocalFree
0x180038a17  nop     dword ptr [rax+rax+00h]
0x180038a1c  mov     rcx, rsi; SRWLock
0x180038a1f  call    cs:__imp_ReleaseSRWLockExclusive
0x180038a26  nop     dword ptr [rax+rax+00h]
0x180038a2b  mov     eax, ebp
0x180038a2d  mov     rbx, [rsp+68h+arg_18]
0x180038a35  add     rsp, 40h
0x180038a39  pop     r15
0x180038a3b  pop     r14
0x180038a3d  pop     rdi
0x180038a3e  pop     rsi
0x180038a3f  pop     rbp
0x180038a40  retn
```
