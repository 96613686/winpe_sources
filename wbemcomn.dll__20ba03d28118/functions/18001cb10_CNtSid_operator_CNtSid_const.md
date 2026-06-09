# CNtSid::operator=(CNtSid const &)

- ea: `0x18001cb10`
- end: `0x18001ccbc`
- name: `??4CNtSid@@QEAAAEAV0@AEBV0@@Z`
- size: `428`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b850`
- `0x180023160`
- `0x1800307b0`
- `0x180030cd0`

## callees

- `0x18001cb10`
- `0x18001d19c`
- `0x1800298f0`
- `0x18002a1f0`
- `0x18002c98c`
- `0x180033f0c`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cc35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cc35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cb79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cb79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cca5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cca5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cc77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cc77`
- `ntdll!RtlLengthSid` at `0x18001cb5b`
- `ntdll!RtlLengthSid` at `0x18001cb5b`

## string_xrefs

- `0x18001cc69`: `CopySid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CNtSid::operator=(__int64 a1, __int64 a2)
{
  __int64 v4; // r14
  DWORD LastError; // ebx
  ULONG v6; // eax
  size_t v7; // r12
  LPVOID v8; // rax
  void *v9; // rbx
  PSID v10; // rsi
  FARPROC ProcAddress; // rax
  void *v12; // r8
  DWORD SecurityDll; // eax
  void *v15; // [rsp+60h] [rbp+30h] BYREF
  void *v16; // [rsp+68h] [rbp+38h] BYREF

  v4 = 0;
  LastError = *(_DWORD *)(a2 + 8);
  if ( !LastError )
  {
    if ( !*(_QWORD *)a2 )
    {
      LastError = 6;
      goto LABEL_10;
    }
    v6 = RtlLengthSid(*(PSID *)a2);
    v7 = v6;
    if ( hHeap )
      v8 = HeapAlloc(hHeap, 0, v6);
    else
      v8 = 0;
    std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&v15, (__int64)v8);
    v9 = v15;
    if ( !v15 )
    {
      LastError = 14;
      goto LABEL_9;
    }
    memset_0(v15, 0, v7);
    v10 = *(PSID *)a2;
    ProcAddress = (FARPROC)qword_180070338;
    if ( !qword_180070338 )
    {
      SecurityDll = DLpLoadSecurityDll();
      if ( SecurityDll )
      {
        SetLastError(SecurityDll);
        goto LABEL_22;
      }
      ProcAddress = GetProcAddress(g_hInstSecurityDLL, "CopySid");
      qword_180070338 = (__int64)ProcAddress;
      if ( !ProcAddress )
        goto LABEL_22;
    }
    if ( ((unsigned int (__fastcall *)(_QWORD, void *, PSID))ProcAddress)((unsigned int)v7, v9, v10) )
    {
      CWbemTime::CWbemTime((CWbemTime *)&v16);
      v4 = std::unique_ptr<CExecQueue::CThreadRecord>::release(&v15);
      LastError = 0;
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v16);
LABEL_9:
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v15);
      goto LABEL_10;
    }
LABEL_22:
    LastError = GetLastError();
    goto LABEL_9;
  }
LABEL_10:
  *(_DWORD *)(a1 + 8) = LastError;
  v12 = *(void **)a1;
  *(_QWORD *)a1 = v4;
  *(_DWORD *)(a1 + 12) = 8;
  if ( hHeap && v12 )
    HeapFree(hHeap, 0, v12);
  return a1;
}

```

## disassembly

```asm
0x18001cb10  mov     [rsp-28h+arg_10], rbx
0x18001cb15  mov     [rsp-28h+arg_18], rsi
0x18001cb1a  push    rbp
0x18001cb1b  push    rdi
0x18001cb1c  push    r12
0x18001cb1e  push    r14
0x18001cb20  push    r15
0x18001cb22  mov     rbp, rsp
0x18001cb25  sub     rsp, 30h
0x18001cb29  mov     rsi, rdx
0x18001cb2c  mov     rdi, rcx
0x18001cb2f  xor     r14d, r14d
0x18001cb32  mov     [rbp+var_10], r14
0x18001cb36  mov     [rbp+var_4], 8
0x18001cb3d  mov     ebx, [rdx+8]
0x18001cb40  test    ebx, ebx
0x18001cb42  jnz     loc_18001CC5A
0x18001cb48  mov     [rbp+var_8], 1
0x18001cb4f  mov     rcx, [rdx]; Sid
0x18001cb52  test    rcx, rcx
0x18001cb55  jz      loc_18001CC55
0x18001cb5b  call    cs:__imp_RtlLengthSid
0x18001cb61  mov     r12d, eax
0x18001cb64  mov     rcx, cs:hHeap; hHeap
0x18001cb6b  test    rcx, rcx
0x18001cb6e  jz      loc_18001CC8F
0x18001cb74  mov     r8d, r12d; dwBytes
0x18001cb77  xor     edx, edx; dwFlags
0x18001cb79  call    cs:__imp_HeapAlloc
0x18001cb7f  mov     rdx, rax
0x18001cb82  lea     rcx, [rbp+arg_0]
0x18001cb86  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18001cb8b  nop
0x18001cb8c  mov     rbx, [rbp+arg_0]
0x18001cb90  test    rbx, rbx
0x18001cb93  jz      loc_18001CC96
0x18001cb99  mov     r8, r12; Size
0x18001cb9c  xor     edx, edx; Val
0x18001cb9e  mov     rcx, rbx; void *
0x18001cba1  call    memset_0
0x18001cba6  mov     rsi, [rsi]
0x18001cba9  mov     rax, cs:qword_180070338
0x18001cbb0  test    rax, rax
0x18001cbb3  jz      loc_18001CC5F
0x18001cbb9  mov     r8, rsi
0x18001cbbc  mov     rdx, rbx
0x18001cbbf  mov     ecx, r12d
0x18001cbc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc7  test    eax, eax
0x18001cbc9  jz      loc_18001CCAB
0x18001cbcf  lea     rcx, [rbp+arg_8]; this
0x18001cbd3  call    ??0CWbemTime@@QEAA@XZ; CWbemTime::CWbemTime(void)
0x18001cbd8  nop
0x18001cbd9  lea     rcx, [rbp+arg_0]
0x18001cbdd  call    ?release@?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAAPEAVCThreadRecord@CExecQueue@@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::release(void)
0x18001cbe2  mov     r14, rax
0x18001cbe5  mov     [rbp+var_10], rax
0x18001cbe9  xor     ebx, ebx
0x18001cbeb  mov     [rbp+var_8], ebx
0x18001cbee  lea     rcx, [rbp+arg_8]
0x18001cbf2  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001cbf7  nop
0x18001cbf8  lea     rcx, [rbp+arg_0]
0x18001cbfc  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001cc01  nop
0x18001cc02  mov     eax, [rdi+8]
0x18001cc05  mov     [rdi+8], ebx
0x18001cc08  mov     [rbp+var_8], eax
0x18001cc0b  mov     r8, [rdi]; lpMem
0x18001cc0e  mov     [rdi], r14
0x18001cc11  mov     [rbp+var_10], r8
0x18001cc15  mov     eax, [rdi+0Ch]
0x18001cc18  mov     dword ptr [rdi+0Ch], 8
0x18001cc1f  mov     [rbp+var_4], eax
0x18001cc22  mov     rcx, cs:hHeap; hHeap
0x18001cc29  test    rcx, rcx
0x18001cc2c  jz      short loc_18001CC3B
0x18001cc2e  test    r8, r8
0x18001cc31  jz      short loc_18001CC3B
0x18001cc33  xor     edx, edx; dwFlags
0x18001cc35  call    cs:__imp_HeapFree
0x18001cc3b  mov     rax, rdi
0x18001cc3e  mov     rbx, [rsp+30h+arg_10]
0x18001cc43  mov     rsi, [rsp+30h+arg_18]
0x18001cc48  add     rsp, 30h
0x18001cc4c  pop     r15
0x18001cc4e  pop     r14
0x18001cc50  pop     r12
0x18001cc52  pop     rdi
0x18001cc53  pop     rbp
0x18001cc54  retn
0x18001cc55  mov     ebx, 6
0x18001cc5a  mov     [rbp+var_8], ebx
0x18001cc5d  jmp     short loc_18001CC02
0x18001cc5f  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001cc64  nop
0x18001cc65  test    eax, eax
0x18001cc67  jnz     short loc_18001CCA3
0x18001cc69  lea     rdx, aCopysid; "CopySid"
0x18001cc70  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001cc77  call    cs:__imp_GetProcAddress
0x18001cc7d  mov     cs:qword_180070338, rax
0x18001cc84  test    rax, rax
0x18001cc87  jnz     loc_18001CBB9
0x18001cc8d  jmp     short loc_18001CCAB
0x18001cc8f  xor     eax, eax
0x18001cc91  jmp     loc_18001CB7F
0x18001cc96  mov     ebx, 0Eh
0x18001cc9b  mov     [rbp+var_8], ebx
0x18001cc9e  jmp     loc_18001CBF8
0x18001cca3  mov     ecx, eax; dwErrCode
0x18001cca5  call    cs:__imp_SetLastError
0x18001ccab  call    cs:__imp_GetLastError
0x18001ccb1  mov     ebx, eax
0x18001ccb3  mov     [rbp+var_8], eax
0x18001ccb6  jmp     loc_18001CBF8
```
