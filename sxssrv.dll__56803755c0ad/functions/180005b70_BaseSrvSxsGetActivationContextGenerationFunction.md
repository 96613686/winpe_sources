# BaseSrvSxsGetActivationContextGenerationFunction

- ea: `0x180005b70`
- end: `0x180005dcb`
- name: `BaseSrvSxsGetActivationContextGenerationFunction`
- size: `603`
- prototype: `__int64 __fastcall(PULONG *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003170`

## callees

- `0x180005b70`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180005cb2`
- `ntdll!RtlFreeHeap` at `0x180005cb2`
- `ntdll!DbgPrintEx` at `0x180005c41`
- `ntdll!DbgPrintEx` at `0x180005c94`
- `ntdll!DbgPrintEx` at `0x180005d72`
- `ntdll!DbgPrintEx` at `0x180005c41`
- `ntdll!DbgPrintEx` at `0x180005c94`
- `ntdll!DbgPrintEx` at `0x180005d72`
- `ntdll!LdrLoadDll` at `0x180005bc7`
- `ntdll!LdrLoadDll` at `0x180005bc7`
- `ntdll!LdrGetProcedureAddress` at `0x180005cf1`
- `ntdll!LdrGetProcedureAddress` at `0x180005cf1`
- `ntdll!LdrUnloadDll` at `0x180005d8a`
- `ntdll!LdrUnloadDll` at `0x180005d8a`
- `ntdll!RtlAllocateHeap` at `0x180005c68`
- `ntdll!RtlAllocateHeap` at `0x180005c68`

## string_xrefs

- `0x180005c2e`: `SXS: %s: LdrLoadDll(%wZ) failed 0x%08lx\n`
- `0x180005c88`: `SXS: %s: LdrLoadDll(%wZ) actually probably out of memory in RtlSearchPath (RtlAllocateHeap failure)\n`
- `0x180005d61`: `SXS: %s: LdrGetProcedureAddress(%wZ:%Z) failed 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsGetActivationContextGenerationFunction(PULONG *a1, _QWORD *a2)
{
  ULONG v2; // edi
  PULONG v5; // rdx
  NTSTATUS v6; // eax
  unsigned int v7; // ebp
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // eax
  PVOID Heap; // rbx
  NTSTATUS ProcedureAddress; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  ULONG v17; // edx
  __int64 v18; // rcx
  PVOID BaseAddress; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  BaseAddress = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  v5 = SxsActivationContextGenerationFunction;
  if ( SxsActivationContextGenerationFunction )
  {
LABEL_29:
    v18 = BaseSrvSxsGetActCtxGenCount;
    *a1 = v5;
    *a2 = v18;
    BaseSrvSxsGetActCtxGenCount = v18 + 1;
    return 0;
  }
  v6 = LdrLoadDll(0, 0, &BaseSrvSxsDllPath, &BaseAddress);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( v6 == -1073741308
      || (unsigned int)(v6 + 1073741687) <= 2
      || (v8 = (unsigned int)(v6 + 1073741809), (unsigned int)v8 <= 0x2B) && (v9 = 0x82000000001LL, _bittest64(&v9, v8))
      || v7 + 1072365566 <= 0x10 && (v10 = 65541, _bittest(&v10, v7 + 1072365566)) )
    {
      v2 = 2;
    }
    DbgPrintEx(
      0x33u,
      v2,
      "SXS: %s: LdrLoadDll(%wZ) failed 0x%08lx\n",
      "BaseSrvSxsGetActivationContextGenerationFunction",
      &BaseSrvSxsDllPath,
      v7);
    if ( v7 == -1073741515 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x38u);
      if ( !Heap )
        DbgPrintEx(
          0x33u,
          0,
          "SXS: %s: LdrLoadDll(%wZ) actually probably out of memory in RtlSearchPath (RtlAllocateHeap failure)\n",
          "BaseSrvSxsGetActivationContextGenerationFunction",
          &BaseSrvSxsDllPath);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    }
    return v7;
  }
  ProcedureAddress = LdrGetProcedureAddress(BaseAddress, &Name, 0, (PVOID *)&SxsActivationContextGenerationFunction);
  v7 = ProcedureAddress;
  if ( ProcedureAddress >= 0 )
  {
    v5 = SxsActivationContextGenerationFunction;
    goto LABEL_29;
  }
  if ( ProcedureAddress == -1073741308
    || (unsigned int)(ProcedureAddress + 1073741687) <= 2
    || (v14 = (unsigned int)(ProcedureAddress + 1073741809), (unsigned int)v14 <= 0x2B)
    && (v15 = 0x82000000001LL, _bittest64(&v15, v14))
    || v7 + 1072365566 <= 0x10 && (v16 = 65541, _bittest(&v16, v7 + 1072365566)) )
  {
    v17 = 2;
  }
  else
  {
    v17 = 0;
  }
  DbgPrintEx(
    0x33u,
    v17,
    "SXS: %s: LdrGetProcedureAddress(%wZ:%Z) failed 0x%08lx\n",
    "BaseSrvSxsGetActivationContextGenerationFunction",
    &BaseSrvSxsDllPath,
    &Name,
    v7);
  SxsActivationContextGenerationFunction = 0;
  LdrUnloadDll(BaseAddress);
  return v7;
}

```

## disassembly

```asm
0x180005b70  push    rbx
0x180005b72  push    rsi
0x180005b73  push    rdi
0x180005b74  sub     rsp, 40h
0x180005b78  xor     edi, edi
0x180005b7a  mov     rbx, rdx
0x180005b7d  mov     [rsp+58h+BaseAddress], rdi
0x180005b82  mov     rsi, rcx
0x180005b85  test    rcx, rcx
0x180005b88  jz      loc_180005DC1
0x180005b8e  test    rdx, rdx
0x180005b91  jz      loc_180005DC1
0x180005b97  mov     rdx, cs:SxsActivationContextGenerationFunction; LoadFlags
0x180005b9e  mov     [rsp+58h+arg_8], rbp
0x180005ba3  mov     [rsp+58h+arg_10], r14
0x180005ba8  mov     [rsp+58h+arg_18], r15
0x180005bad  test    rdx, rdx
0x180005bb0  jnz     loc_180005DA2
0x180005bb6  lea     r14, BaseSrvSxsDllPath
0x180005bbd  xor     ecx, ecx; SearchPath
0x180005bbf  mov     r8, r14; Name
0x180005bc2  lea     r9, [rsp+58h+BaseAddress]; BaseAddress
0x180005bc7  call    cs:__imp_LdrLoadDll
0x180005bce  nop     dword ptr [rax+rax+00h]
0x180005bd3  mov     ebp, eax
0x180005bd5  test    eax, eax
0x180005bd7  jns     loc_180005CD8
0x180005bdd  cmp     eax, 0C0000204h
0x180005be2  jz      short loc_180005C1E
0x180005be4  lea     ecx, [rax+3FFFFF77h]
0x180005bea  cmp     ecx, 2
0x180005bed  jbe     short loc_180005C1E
0x180005bef  add     eax, 3FFFFFF1h
0x180005bf4  cmp     eax, 2Bh ; '+'
0x180005bf7  ja      short loc_180005C09
0x180005bf9  mov     rcx, 82000000001h
0x180005c03  bt      rcx, rax
0x180005c07  jb      short loc_180005C1E
0x180005c09  lea     ecx, [rbp+3FEAFFFEh]
0x180005c0f  cmp     ecx, 10h
0x180005c12  ja      short loc_180005C23
0x180005c14  mov     eax, 10005h
0x180005c19  bt      eax, ecx
0x180005c1c  jnb     short loc_180005C23
0x180005c1e  mov     edi, 2
0x180005c23  mov     dword ptr [rsp+58h+var_30], ebp
0x180005c27  lea     r9, aBasesrvsxsgeta; "BaseSrvSxsGetActivationContextGeneratio"...
0x180005c2e  lea     r8, aSxsSLdrloaddll_0; "SXS: %s: LdrLoadDll(%wZ) failed 0x%08lx"...
0x180005c35  mov     [rsp+58h+var_38], r14
0x180005c3a  mov     edx, edi; Level
0x180005c3c  mov     ecx, 33h ; '3'; ComponentId
0x180005c41  call    cs:__imp_DbgPrintEx
0x180005c48  nop     dword ptr [rax+rax+00h]
0x180005c4d  cmp     ebp, 0C0000135h
0x180005c53  jnz     short loc_180005CBE
0x180005c55  mov     rcx, gs:60h
0x180005c5e  xor     edx, edx; Flags
0x180005c60  mov     rcx, [rcx+30h]; HeapHandle
0x180005c64  lea     r8d, [rdx+38h]; Size
0x180005c68  call    cs:__imp_RtlAllocateHeap
0x180005c6f  nop     dword ptr [rax+rax+00h]
0x180005c74  mov     rbx, rax
0x180005c77  test    rax, rax
0x180005c7a  jnz     short loc_180005CA0
0x180005c7c  lea     r9, aBasesrvsxsgeta; "BaseSrvSxsGetActivationContextGeneratio"...
0x180005c83  mov     [rsp+58h+var_38], r14
0x180005c88  lea     r8, aSxsSLdrloaddll; "SXS: %s: LdrLoadDll(%wZ) actually proba"...
0x180005c8f  xor     edx, edx; Level
0x180005c91  lea     ecx, [rax+33h]; ComponentId
0x180005c94  call    cs:__imp_DbgPrintEx
0x180005c9b  nop     dword ptr [rax+rax+00h]
0x180005ca0  mov     rcx, gs:60h
0x180005ca9  mov     r8, rbx; P
0x180005cac  xor     edx, edx; Flags
0x180005cae  mov     rcx, [rcx+30h]; HeapHandle
0x180005cb2  call    cs:__imp_RtlFreeHeap
0x180005cb9  nop     dword ptr [rax+rax+00h]
0x180005cbe  mov     eax, ebp
0x180005cc0  mov     r14, [rsp+58h+arg_10]
0x180005cc5  mov     rbp, [rsp+58h+arg_8]
0x180005cca  mov     r15, [rsp+58h+arg_18]
0x180005ccf  add     rsp, 40h
0x180005cd3  pop     rdi
0x180005cd4  pop     rsi
0x180005cd5  pop     rbx
0x180005cd6  retn
0x180005cd8  mov     rcx, [rsp+58h+BaseAddress]; BaseAddress
0x180005cdd  lea     r15, Name
0x180005ce4  mov     rdx, r15; Name
0x180005ce7  lea     r9, SxsActivationContextGenerationFunction; ProcedureAddress
0x180005cee  xor     r8d, r8d; Ordinal
0x180005cf1  call    cs:__imp_LdrGetProcedureAddress
0x180005cf8  nop     dword ptr [rax+rax+00h]
0x180005cfd  mov     ebp, eax
0x180005cff  test    eax, eax
0x180005d01  jns     loc_180005D9B
0x180005d07  cmp     eax, 0C0000204h
0x180005d0c  jz      short loc_180005D4C
0x180005d0e  lea     ecx, [rax+3FFFFF77h]
0x180005d14  cmp     ecx, 2
0x180005d17  jbe     short loc_180005D4C
0x180005d19  add     eax, 3FFFFFF1h
0x180005d1e  cmp     eax, 2Bh ; '+'
0x180005d21  ja      short loc_180005D33
0x180005d23  mov     rcx, 82000000001h
0x180005d2d  bt      rcx, rax
0x180005d31  jb      short loc_180005D4C
0x180005d33  lea     ecx, [rbp+3FEAFFFEh]
0x180005d39  cmp     ecx, 10h
0x180005d3c  ja      short loc_180005D48
0x180005d3e  mov     eax, 10005h
0x180005d43  bt      eax, ecx
0x180005d46  jb      short loc_180005D4C
0x180005d48  mov     edx, edi
0x180005d4a  jmp     short loc_180005D51
0x180005d4c  mov     edx, 2; Level
0x180005d51  mov     [rsp+58h+var_28], ebp
0x180005d55  lea     r9, aBasesrvsxsgeta; "BaseSrvSxsGetActivationContextGeneratio"...
0x180005d5c  mov     [rsp+58h+var_30], r15
0x180005d61  lea     r8, aSxsSLdrgetproc; "SXS: %s: LdrGetProcedureAddress(%wZ:%Z)"...
0x180005d68  mov     ecx, 33h ; '3'; ComponentId
0x180005d6d  mov     [rsp+58h+var_38], r14
0x180005d72  call    cs:__imp_DbgPrintEx
0x180005d79  nop     dword ptr [rax+rax+00h]
0x180005d7e  mov     rcx, [rsp+58h+BaseAddress]; BaseAddress
0x180005d83  mov     cs:SxsActivationContextGenerationFunction, rdi
0x180005d8a  call    cs:__imp_LdrUnloadDll
0x180005d91  nop     dword ptr [rax+rax+00h]
0x180005d96  jmp     loc_180005CBE
0x180005d9b  mov     rdx, cs:SxsActivationContextGenerationFunction
0x180005da2  movsxd  rax, cs:BaseSrvSxsGetActCtxGenCount
0x180005da9  mov     rcx, rax
0x180005dac  mov     [rsi], rdx
0x180005daf  inc     eax
0x180005db1  mov     [rbx], rcx
0x180005db4  mov     cs:BaseSrvSxsGetActCtxGenCount, eax
0x180005dba  mov     eax, edi
0x180005dbc  jmp     loc_180005CC0
0x180005dc1  mov     eax, 0C000000Dh
0x180005dc6  jmp     loc_180005CCF
```
