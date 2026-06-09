# CNtSid::CNtSid(CNtSid const &)

- ea: `0x18001b5c0`
- end: `0x18001b71b`
- name: `??0CNtSid@@QEAA@AEBV0@@Z`
- size: `347`
- prototype: `CNtSid *__fastcall(CNtSid *__hidden this, const struct CNtSid *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180030690`

## callees

- `0x18001b5c0`
- `0x18001d19c`
- `0x1800298f0`
- `0x18002a1f0`
- `0x18002c98c`
- `0x180033f0c`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b61f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b70f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b70f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b709`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b709`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b6de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b6de`
- `ntdll!RtlLengthSid` at `0x18001b601`
- `ntdll!RtlLengthSid` at `0x18001b601`

## string_xrefs

- `0x18001b6d0`: `CopySid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CNtSid *__fastcall CNtSid::CNtSid(CNtSid *this, const struct CNtSid *a2)
{
  int v4; // eax
  ULONG v5; // eax
  size_t v6; // r14
  LPVOID v7; // rax
  void *v8; // rbx
  __int64 v9; // rsi
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax
  void *v13; // [rsp+50h] [rbp+8h] BYREF
  char v14; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 3) = 8;
  v4 = *((_DWORD *)a2 + 2);
  if ( v4 )
  {
    *((_DWORD *)this + 2) = v4;
    return this;
  }
  *((_DWORD *)this + 2) = 1;
  if ( !*(_QWORD *)a2 )
  {
    *((_DWORD *)this + 2) = 6;
    return this;
  }
  v5 = RtlLengthSid(*(PSID *)a2);
  v6 = v5;
  if ( hHeap )
    v7 = HeapAlloc(hHeap, 0, v5);
  else
    v7 = 0;
  std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&v13, (__int64)v7);
  v8 = v13;
  if ( !v13 )
  {
    *((_DWORD *)this + 2) = 14;
    goto LABEL_9;
  }
  memset_0(v13, 0, v6);
  v9 = *(_QWORD *)a2;
  ProcAddress = (FARPROC)qword_180070338;
  if ( !qword_180070338 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      goto LABEL_19;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "CopySid");
    qword_180070338 = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_19;
  }
  if ( !((unsigned int (__fastcall *)(_QWORD, void *, __int64))ProcAddress)((unsigned int)v6, v8, v9) )
  {
LABEL_19:
    *((_DWORD *)this + 2) = GetLastError();
    goto LABEL_9;
  }
  CWbemTime::CWbemTime((CWbemTime *)&v14);
  *(_QWORD *)this = std::unique_ptr<CExecQueue::CThreadRecord>::release(&v13);
  *((_DWORD *)this + 2) = 0;
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v14);
LABEL_9:
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v13);
  return this;
}

```

## disassembly

```asm
0x18001b5c0  mov     [rsp+arg_10], rbx
0x18001b5c5  push    rbp
0x18001b5c6  push    rsi
0x18001b5c7  push    rdi
0x18001b5c8  push    r14
0x18001b5ca  push    r15
0x18001b5cc  sub     rsp, 20h
0x18001b5d0  mov     rsi, rdx
0x18001b5d3  mov     rdi, rcx
0x18001b5d6  xor     r15d, r15d
0x18001b5d9  mov     [rcx], r15
0x18001b5dc  mov     dword ptr [rcx+0Ch], 8
0x18001b5e3  mov     eax, [rdx+8]
0x18001b5e6  test    eax, eax
0x18001b5e8  jnz     loc_18001B6B8
0x18001b5ee  mov     dword ptr [rcx+8], 1
0x18001b5f5  mov     rcx, [rdx]; Sid
0x18001b5f8  test    rcx, rcx
0x18001b5fb  jz      loc_18001B6BD
0x18001b601  call    cs:__imp_RtlLengthSid
0x18001b607  mov     r14d, eax
0x18001b60a  mov     rcx, cs:hHeap; hHeap
0x18001b611  test    rcx, rcx
0x18001b614  jz      loc_18001B6F6
0x18001b61a  mov     r8d, r14d; dwBytes
0x18001b61d  xor     edx, edx; dwFlags
0x18001b61f  call    cs:__imp_HeapAlloc
0x18001b625  mov     rdx, rax
0x18001b628  lea     rcx, [rsp+48h+arg_0]
0x18001b62d  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18001b632  nop
0x18001b633  mov     rbx, [rsp+48h+arg_0]
0x18001b638  test    rbx, rbx
0x18001b63b  jz      loc_18001B6FE
0x18001b641  mov     r8, r14; Size
0x18001b644  xor     edx, edx; Val
0x18001b646  mov     rcx, rbx; void *
0x18001b649  call    memset_0
0x18001b64e  mov     rsi, [rsi]
0x18001b651  mov     rax, cs:qword_180070338
0x18001b658  test    rax, rax
0x18001b65b  jz      short loc_18001B6C6
0x18001b65d  mov     r8, rsi
0x18001b660  mov     rdx, rbx
0x18001b663  mov     ecx, r14d
0x18001b666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b66b  test    eax, eax
0x18001b66d  jz      loc_18001B70F
0x18001b673  lea     rcx, [rsp+48h+arg_8]; this
0x18001b678  call    ??0CWbemTime@@QEAA@XZ; CWbemTime::CWbemTime(void)
0x18001b67d  nop
0x18001b67e  lea     rcx, [rsp+48h+arg_0]
0x18001b683  call    ?release@?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAAPEAVCThreadRecord@CExecQueue@@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::release(void)
0x18001b688  mov     [rdi], rax
0x18001b68b  mov     [rdi+8], r15d
0x18001b68f  lea     rcx, [rsp+48h+arg_8]
0x18001b694  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001b699  nop
0x18001b69a  lea     rcx, [rsp+48h+arg_0]
0x18001b69f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001b6a4  mov     rax, rdi
0x18001b6a7  mov     rbx, [rsp+48h+arg_10]
0x18001b6ac  add     rsp, 20h
0x18001b6b0  pop     r15
0x18001b6b2  pop     r14
0x18001b6b4  pop     rdi
0x18001b6b5  pop     rsi
0x18001b6b6  pop     rbp
0x18001b6b7  retn
0x18001b6b8  mov     [rcx+8], eax
0x18001b6bb  jmp     short loc_18001B6A4
0x18001b6bd  mov     dword ptr [rdi+8], 6
0x18001b6c4  jmp     short loc_18001B6A4
0x18001b6c6  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001b6cb  nop
0x18001b6cc  test    eax, eax
0x18001b6ce  jnz     short loc_18001B707
0x18001b6d0  lea     rdx, aCopysid; "CopySid"
0x18001b6d7  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001b6de  call    cs:__imp_GetProcAddress
0x18001b6e4  mov     cs:qword_180070338, rax
0x18001b6eb  test    rax, rax
0x18001b6ee  jnz     loc_18001B65D
0x18001b6f4  jmp     short loc_18001B70F
0x18001b6f6  mov     rax, r15
0x18001b6f9  jmp     loc_18001B625
0x18001b6fe  mov     dword ptr [rdi+8], 0Eh
0x18001b705  jmp     short loc_18001B69A
0x18001b707  mov     ecx, eax; dwErrCode
0x18001b709  call    cs:__imp_SetLastError
0x18001b70f  call    cs:__imp_GetLastError
0x18001b715  mov     [rdi+8], eax
0x18001b718  jmp     short loc_18001B69A
```
