# CNtSid::CNtSid(void *)

- ea: `0x18001c340`
- end: `0x18001c4c6`
- name: `??0CNtSid@@QEAA@PEAX@Z`
- size: `390`
- prototype: `CNtSid *__fastcall(CNtSid *this, void *)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001be80`
- `0x18001c2d0`
- `0x180030cd0`
- `0x18003cef0`
- `0x18003d1d0`
- `0x18003dfa8`
- `0x18003eff4`
- `0x18003f730`

## callees

- `0x18000ab30`
- `0x18001c340`
- `0x18001d19c`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c3b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c3b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c414`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c4a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c414`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c4a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c44c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c477`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c44c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c477`
- `ntdll!RtlLengthSid` at `0x18001c394`
- `ntdll!RtlLengthSid` at `0x18001c394`

## string_xrefs

- `0x18001c445`: `CopySid`
- `0x18001c470`: `IsValidSid`

## pseudocode

```c
CNtSid *__fastcall CNtSid::CNtSid(CNtSid *this, void *a2)
{
  FARPROC ProcAddress; // rax
  ULONG v5; // eax
  ULONG v6; // ebp
  void *v7; // rax
  FARPROC v8; // rax
  __int64 v9; // rsi
  CNtSid *result; // rax
  DWORD v11; // eax
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_1800702F8;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = 8;
  if ( !ProcAddress )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      goto LABEL_9;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "IsValidSid");
    qword_1800702F8 = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_9;
  }
  if ( ((unsigned int (__fastcall *)(void *))ProcAddress)(a2) )
  {
    v5 = RtlLengthSid(a2);
    v6 = v5;
    if ( hHeap )
    {
      v7 = HeapAlloc(hHeap, 0, v5);
      *(_QWORD *)this = v7;
      if ( v7 )
      {
        memset_0(v7, 0, v6);
        v8 = (FARPROC)qword_180070338;
        v9 = *(_QWORD *)this;
        if ( !qword_180070338 )
        {
          v11 = DLpLoadSecurityDll();
          if ( v11 )
          {
            SetLastError(v11);
            goto LABEL_19;
          }
          v8 = GetProcAddress(g_hInstSecurityDLL, "CopySid");
          qword_180070338 = (__int64)v8;
          if ( !v8 )
            goto LABEL_19;
        }
        if ( ((unsigned int (__fastcall *)(_QWORD, __int64, void *))v8)(v6, v9, a2) )
          return this;
LABEL_19:
        CMUILocale::_Free(*(void **)this);
        *(_QWORD *)this = 0;
        *((_DWORD *)this + 2) = GetLastError();
        *((_DWORD *)this + 3) = 8;
        return this;
      }
    }
    else
    {
      *(_QWORD *)this = 0;
    }
    *((_DWORD *)this + 2) = 14;
    return this;
  }
LABEL_9:
  result = this;
  *((_DWORD *)this + 2) = 13;
  return result;
}

```

## disassembly

```asm
0x18001c340  mov     [rsp+arg_10], rbx
0x18001c345  mov     [rsp+arg_18], rdi
0x18001c34a  push    r14
0x18001c34c  sub     rsp, 20h
0x18001c350  mov     rax, cs:qword_1800702F8
0x18001c357  xor     r14d, r14d
0x18001c35a  mov     [rcx], r14
0x18001c35d  mov     rdi, rdx
0x18001c360  mov     [rcx+8], r14d
0x18001c364  mov     rbx, rcx
0x18001c367  mov     dword ptr [rcx+0Ch], 8
0x18001c36e  test    rax, rax
0x18001c371  jz      loc_18001C460
0x18001c377  mov     rcx, rdi
0x18001c37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c37f  test    eax, eax
0x18001c381  jz      loc_18001C41A
0x18001c387  mov     [rsp+28h+arg_0], rbp
0x18001c38c  mov     rcx, rdi; Sid
0x18001c38f  mov     [rsp+28h+arg_8], rsi
0x18001c394  call    cs:__imp_RtlLengthSid
0x18001c39a  mov     rcx, cs:hHeap; hHeap
0x18001c3a1  mov     ebp, eax
0x18001c3a3  test    rcx, rcx
0x18001c3a6  jz      loc_18001C48F
0x18001c3ac  mov     r8d, ebp; dwBytes
0x18001c3af  xor     edx, edx; dwFlags
0x18001c3b1  call    cs:__imp_HeapAlloc
0x18001c3b7  mov     [rbx], rax
0x18001c3ba  test    rax, rax
0x18001c3bd  jz      loc_18001C492
0x18001c3c3  mov     r8d, ebp; Size
0x18001c3c6  xor     edx, edx; Val
0x18001c3c8  mov     rcx, rax; void *
0x18001c3cb  call    memset_0
0x18001c3d0  mov     rax, cs:qword_180070338
0x18001c3d7  mov     rsi, [rbx]
0x18001c3da  test    rax, rax
0x18001c3dd  jz      short loc_18001C435
0x18001c3df  mov     r8, rdi
0x18001c3e2  mov     rdx, rsi
0x18001c3e5  mov     ecx, ebp
0x18001c3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3ec  test    eax, eax
0x18001c3ee  jz      loc_18001C4A6
0x18001c3f4  mov     rbp, [rsp+28h+arg_0]
0x18001c3f9  mov     rax, rbx
0x18001c3fc  mov     rsi, [rsp+28h+arg_8]
0x18001c401  mov     rbx, [rsp+28h+arg_10]
0x18001c406  mov     rdi, [rsp+28h+arg_18]
0x18001c40b  add     rsp, 20h
0x18001c40f  pop     r14
0x18001c411  retn
0x18001c412  mov     ecx, eax; dwErrCode
0x18001c414  call    cs:__imp_SetLastError
0x18001c41a  mov     rdi, [rsp+28h+arg_18]
0x18001c41f  mov     rax, rbx
0x18001c422  mov     dword ptr [rbx+8], 0Dh
0x18001c429  mov     rbx, [rsp+28h+arg_10]
0x18001c42e  add     rsp, 20h
0x18001c432  pop     r14
0x18001c434  retn
0x18001c435  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001c43a  test    eax, eax
0x18001c43c  jnz     short loc_18001C49E
0x18001c43e  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001c445  lea     rdx, aCopysid; "CopySid"
0x18001c44c  call    cs:__imp_GetProcAddress
0x18001c452  mov     cs:qword_180070338, rax
0x18001c459  test    rax, rax
0x18001c45c  jnz     short loc_18001C3DF
0x18001c45e  jmp     short loc_18001C4A6
0x18001c460  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001c465  test    eax, eax
0x18001c467  jnz     short loc_18001C412
0x18001c469  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001c470  lea     rdx, aIsvalidsid; "IsValidSid"
0x18001c477  call    cs:__imp_GetProcAddress
0x18001c47d  mov     cs:qword_1800702F8, rax
0x18001c484  test    rax, rax
0x18001c487  jnz     loc_18001C377
0x18001c48d  jmp     short loc_18001C41A
0x18001c48f  mov     [rbx], r14
0x18001c492  mov     dword ptr [rbx+8], 0Eh
0x18001c499  jmp     loc_18001C3F4
0x18001c49e  mov     ecx, eax; dwErrCode
0x18001c4a0  call    cs:__imp_SetLastError
0x18001c4a6  mov     rcx, [rbx]; void *
0x18001c4a9  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001c4ae  mov     [rbx], r14
0x18001c4b1  call    cs:__imp_GetLastError
0x18001c4b7  mov     [rbx+8], eax
0x18001c4ba  mov     dword ptr [rbx+0Ch], 8
0x18001c4c1  jmp     loc_18001C3F4
```
