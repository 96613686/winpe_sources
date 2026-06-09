# ClientOperationCompleter::Complete(long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)

- ea: `0x1800470c0`
- end: `0x1800471b4`
- name: `?Complete@ClientOperationCompleter@@QEAA_NJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047aac`

## callees

- `0x18003816c`
- `0x1800470c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047100`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004711f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004711f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180047139`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180047139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047111`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004715d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047194`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047111`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004715d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047194`

## pseudocode

```c
char __fastcall ClientOperationCompleter::Complete(__int64 a1, int a2, HLOCAL *a3)
{
  void **v5; // r14
  void *v6; // rbp
  HLOCAL v7; // r15
  DWORD LastError; // ebx
  RTL_SRWLOCK *v10; // rcx

  if ( *(_QWORD *)(a1 + 16) )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 16LL) = a2;
    v5 = (void **)(*(_QWORD *)(a1 + 24) + 24LL);
    if ( v5 != a3 )
    {
      v6 = *v5;
      v7 = *a3;
      if ( *v5 )
      {
        LastError = GetLastError();
        LocalFree(v6);
        SetLastError(LastError);
      }
      *v5 = v7;
      *a3 = 0;
    }
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 16));
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 16) = 0;
    if ( *a3 )
      LocalFree(*a3);
    return 0;
  }
  else
  {
    v10 = *(RTL_SRWLOCK **)a1;
    *a3 = 0;
    ClientOperation::Complete(v10);
    if ( *a3 )
      LocalFree(*a3);
    return 1;
  }
}

```

## disassembly

```asm
0x1800470c0  mov     [rsp+arg_18], rbx
0x1800470c5  push    rbp
0x1800470c6  push    rsi
0x1800470c7  push    rdi
0x1800470c8  push    r14
0x1800470ca  push    r15
0x1800470cc  sub     rsp, 30h
0x1800470d0  cmp     qword ptr [rcx+10h], 0
0x1800470d5  mov     rdi, r8
0x1800470d8  mov     rsi, rcx
0x1800470db  jz      loc_18004716D
0x1800470e1  mov     rax, [rcx+18h]
0x1800470e5  mov     [rax+10h], edx
0x1800470e8  mov     r14, [rcx+18h]
0x1800470ec  add     r14, 18h
0x1800470f0  cmp     r14, r8
0x1800470f3  jz      short loc_180047135
0x1800470f5  mov     rbp, [r14]
0x1800470f8  mov     r15, [r8]
0x1800470fb  test    rbp, rbp
0x1800470fe  jz      short loc_18004712B
0x180047100  call    cs:__imp_GetLastError
0x180047107  nop     dword ptr [rax+rax+00h]
0x18004710c  mov     rcx, rbp; hMem
0x18004710f  mov     ebx, eax
0x180047111  call    cs:__imp_LocalFree
0x180047118  nop     dword ptr [rax+rax+00h]
0x18004711d  mov     ecx, ebx; dwErrCode
0x18004711f  call    cs:__imp_SetLastError
0x180047126  nop     dword ptr [rax+rax+00h]
0x18004712b  mov     [r14], r15
0x18004712e  mov     qword ptr [rdi], 0
0x180047135  mov     rcx, [rsi+10h]; pwk
0x180047139  call    cs:__imp_SubmitThreadpoolWork
0x180047140  nop     dword ptr [rax+rax+00h]
0x180047145  mov     qword ptr [rsi+18h], 0
0x18004714d  mov     qword ptr [rsi+10h], 0
0x180047155  mov     rcx, [rdi]; hMem
0x180047158  test    rcx, rcx
0x18004715b  jz      short loc_180047169
0x18004715d  call    cs:__imp_LocalFree
0x180047164  nop     dword ptr [rax+rax+00h]
0x180047169  xor     al, al
0x18004716b  jmp     short loc_1800471A2
0x18004716d  mov     rax, [r8]
0x180047170  xor     r9d, r9d
0x180047173  mov     rcx, [rcx]; SRWLock
0x180047176  mov     qword ptr [r8], 0
0x18004717d  lea     r8, [rsp+58h+var_38]
0x180047182  mov     [rsp+58h+var_38], rax
0x180047187  call    ?Complete@ClientOperation@@QEAA_NJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z; ClientOperation::Complete(long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)
0x18004718c  mov     rcx, [rdi]; hMem
0x18004718f  test    rcx, rcx
0x180047192  jz      short loc_1800471A0
0x180047194  call    cs:__imp_LocalFree
0x18004719b  nop     dword ptr [rax+rax+00h]
0x1800471a0  mov     al, 1
0x1800471a2  mov     rbx, [rsp+58h+arg_18]
0x1800471a7  add     rsp, 30h
0x1800471ab  pop     r15
0x1800471ad  pop     r14
0x1800471af  pop     rdi
0x1800471b0  pop     rsi
0x1800471b1  pop     rbp
0x1800471b2  retn
```
