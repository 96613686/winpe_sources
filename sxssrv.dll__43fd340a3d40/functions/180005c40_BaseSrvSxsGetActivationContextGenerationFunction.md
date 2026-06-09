# BaseSrvSxsGetActivationContextGenerationFunction

- ea: `0x180005c40`
- end: `0x180005ea5`
- name: `BaseSrvSxsGetActivationContextGenerationFunction`
- size: `613`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003310`

## callees

- `0x180005c40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180005d89`
- `ntdll!RtlFreeHeap` at `0x180005d89`
- `ntdll!DbgPrintEx` at `0x180005d14`
- `ntdll!DbgPrintEx` at `0x180005d6b`
- `ntdll!DbgPrintEx` at `0x180005e48`
- `ntdll!DbgPrintEx` at `0x180005d14`
- `ntdll!DbgPrintEx` at `0x180005d6b`
- `ntdll!DbgPrintEx` at `0x180005e48`
- `ntdll!LdrLoadDll` at `0x180005c98`
- `ntdll!LdrLoadDll` at `0x180005c98`
- `ntdll!LdrGetProcedureAddress` at `0x180005dc7`
- `ntdll!LdrGetProcedureAddress` at `0x180005dc7`
- `ntdll!LdrUnloadDll` at `0x180005e64`
- `ntdll!LdrUnloadDll` at `0x180005e64`
- `ntdll!RtlAllocateHeap` at `0x180005d3d`
- `ntdll!RtlAllocateHeap` at `0x180005d3d`

## string_xrefs

- `0x180005d03`: `SXS: %s: LdrLoadDll(%wZ) failed 0x%08lx\n`
- `0x180005d5d`: `SXS: %s: LdrLoadDll(%wZ) actually probably out of memory in RtlSearchPath (RtlAllocateHeap failure)\n`
- `0x180005e37`: `SXS: %s: LdrGetProcedureAddress(%wZ:%Z) failed 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsGetActivationContextGenerationFunction(PULONG *a1, _QWORD *a2)
{
  PULONG v4; // rdx
  NTSTATUS v5; // eax
  unsigned int v6; // esi
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  ULONG v10; // edx
  PVOID Heap; // rbx
  NTSTATUS ProcedureAddress; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  ULONG v17; // edx
  __int64 v18; // rcx
  PVOID BaseAddress; // [rsp+60h] [rbp+8h] BYREF

  BaseAddress = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  v4 = SxsActivationContextGenerationFunction;
  if ( SxsActivationContextGenerationFunction )
    goto LABEL_30;
  v5 = LdrLoadDll(0, 0, &BaseSrvSxsDllPath, &BaseAddress);
  v6 = v5;
  if ( v5 >= 0 )
  {
    ProcedureAddress = LdrGetProcedureAddress(BaseAddress, &Name, 0, (PVOID *)&SxsActivationContextGenerationFunction);
    v6 = ProcedureAddress;
    if ( ProcedureAddress < 0 )
    {
      if ( ProcedureAddress == -1073741308
        || (unsigned int)(ProcedureAddress + 1073741687) <= 2
        || (v14 = (unsigned int)(ProcedureAddress + 1073741809), (unsigned int)v14 <= 0x2B)
        && (v15 = 0x82000000001LL, _bittest64(&v15, v14))
        || v6 + 1072365566 <= 0x10 && (v16 = 65541, _bittest(&v16, v6 + 1072365566)) )
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
        v6);
      SxsActivationContextGenerationFunction = 0;
      LdrUnloadDll(BaseAddress);
      return v6;
    }
    v4 = SxsActivationContextGenerationFunction;
LABEL_30:
    v18 = BaseSrvSxsGetActCtxGenCount;
    *a1 = v4;
    *a2 = v18;
    BaseSrvSxsGetActCtxGenCount = v18 + 1;
    return 0;
  }
  if ( v5 == -1073741308
    || (unsigned int)(v5 + 1073741687) <= 2
    || (v7 = (unsigned int)(v5 + 1073741809), (unsigned int)v7 <= 0x2B) && (v8 = 0x82000000001LL, _bittest64(&v8, v7))
    || v6 + 1072365566 <= 0x10 && (v9 = 65541, _bittest(&v9, v6 + 1072365566)) )
  {
    v10 = 2;
  }
  else
  {
    v10 = 0;
  }
  DbgPrintEx(
    0x33u,
    v10,
    "SXS: %s: LdrLoadDll(%wZ) failed 0x%08lx\n",
    "BaseSrvSxsGetActivationContextGenerationFunction",
    &BaseSrvSxsDllPath,
    v6);
  if ( v6 == -1073741515 )
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
  return v6;
}

```

## disassembly

```asm
0x180005c40  push    rbx
0x180005c42  push    rdi
0x180005c43  sub     rsp, 48h
0x180005c47  mov     [rsp+58h+BaseAddress], 0
0x180005c50  mov     rbx, rdx
0x180005c53  mov     rdi, rcx
0x180005c56  test    rcx, rcx
0x180005c59  jz      loc_180005E9B
0x180005c5f  test    rdx, rdx
0x180005c62  jz      loc_180005E9B
0x180005c68  mov     rdx, cs:SxsActivationContextGenerationFunction; LoadFlags
0x180005c6f  mov     [rsp+58h+arg_8], rsi
0x180005c74  mov     [rsp+58h+arg_10], r14
0x180005c79  mov     [rsp+58h+var_18], r15
0x180005c7e  test    rdx, rdx
0x180005c81  jnz     loc_180005E7C
0x180005c87  lea     r14, BaseSrvSxsDllPath
0x180005c8e  xor     ecx, ecx; SearchPath
0x180005c90  mov     r8, r14; Name
0x180005c93  lea     r9, [rsp+58h+BaseAddress]; BaseAddress
0x180005c98  call    cs:__imp_LdrLoadDll
0x180005c9f  nop     dword ptr [rax+rax+00h]
0x180005ca4  mov     esi, eax
0x180005ca6  test    eax, eax
0x180005ca8  jns     loc_180005DAE
0x180005cae  cmp     eax, 0C0000204h
0x180005cb3  jz      short loc_180005CF3
0x180005cb5  lea     ecx, [rax+3FFFFF77h]
0x180005cbb  cmp     ecx, 2
0x180005cbe  jbe     short loc_180005CF3
0x180005cc0  add     eax, 3FFFFFF1h
0x180005cc5  cmp     eax, 2Bh ; '+'
0x180005cc8  ja      short loc_180005CDA
0x180005cca  mov     rcx, 82000000001h
0x180005cd4  bt      rcx, rax
0x180005cd8  jb      short loc_180005CF3
0x180005cda  lea     ecx, [rsi+3FEAFFFEh]
0x180005ce0  cmp     ecx, 10h
0x180005ce3  ja      short loc_180005CEF
0x180005ce5  mov     eax, 10005h
0x180005cea  bt      eax, ecx
0x180005ced  jb      short loc_180005CF3
0x180005cef  xor     edx, edx
0x180005cf1  jmp     short loc_180005CF8
0x180005cf3  mov     edx, 2; Level
0x180005cf8  mov     dword ptr [rsp+58h+var_30], esi
0x180005cfc  lea     r9, aBasesrvsxsgeta; "BaseSrvSxsGetActivationContextGeneratio"...
0x180005d03  lea     r8, aSxsSLdrloaddll_0; "SXS: %s: LdrLoadDll(%wZ) failed 0x%08lx"...
0x180005d0a  mov     [rsp+58h+var_38], r14
0x180005d0f  mov     ecx, 33h ; '3'; ComponentId
0x180005d14  call    cs:__imp_DbgPrintEx
0x180005d1b  nop     dword ptr [rax+rax+00h]
0x180005d20  cmp     esi, 0C0000135h
0x180005d26  jnz     short loc_180005D95
0x180005d28  mov     rcx, gs:60h
0x180005d31  xor     edx, edx; Flags
0x180005d33  mov     r8d, 38h ; '8'; Size
0x180005d39  mov     rcx, [rcx+30h]; HeapHandle
0x180005d3d  call    cs:__imp_RtlAllocateHeap
0x180005d44  nop     dword ptr [rax+rax+00h]
0x180005d49  mov     rbx, rax
0x180005d4c  test    rax, rax
0x180005d4f  jnz     short loc_180005D77
0x180005d51  lea     r9, aBasesrvsxsgeta; "BaseSrvSxsGetActivationContextGeneratio"...
0x180005d58  mov     [rsp+58h+var_38], r14
0x180005d5d  lea     r8, aSxsSLdrloaddll; "SXS: %s: LdrLoadDll(%wZ) actually proba"...
0x180005d64  xor     edx, edx; Level
0x180005d66  mov     ecx, 33h ; '3'; ComponentId
0x180005d6b  call    cs:__imp_DbgPrintEx
0x180005d72  nop     dword ptr [rax+rax+00h]
0x180005d77  mov     rcx, gs:60h
0x180005d80  mov     r8, rbx; P
0x180005d83  xor     edx, edx; Flags
0x180005d85  mov     rcx, [rcx+30h]; HeapHandle
0x180005d89  call    cs:__imp_RtlFreeHeap
0x180005d90  nop     dword ptr [rax+rax+00h]
0x180005d95  mov     eax, esi
0x180005d97  mov     r14, [rsp+58h+arg_10]
0x180005d9c  mov     rsi, [rsp+58h+arg_8]
0x180005da1  mov     r15, [rsp+58h+var_18]
0x180005da6  add     rsp, 48h
0x180005daa  pop     rdi
0x180005dab  pop     rbx
0x180005dac  retn
0x180005dae  mov     rcx, [rsp+58h+BaseAddress]; BaseAddress
0x180005db3  lea     r15, Name
0x180005dba  mov     rdx, r15; Name
0x180005dbd  lea     r9, SxsActivationContextGenerationFunction; ProcedureAddress
0x180005dc4  xor     r8d, r8d; Ordinal
0x180005dc7  call    cs:__imp_LdrGetProcedureAddress
0x180005dce  nop     dword ptr [rax+rax+00h]
0x180005dd3  mov     esi, eax
0x180005dd5  test    eax, eax
0x180005dd7  jns     loc_180005E75
0x180005ddd  cmp     eax, 0C0000204h
0x180005de2  jz      short loc_180005E22
0x180005de4  lea     ecx, [rax+3FFFFF77h]
0x180005dea  cmp     ecx, 2
0x180005ded  jbe     short loc_180005E22
0x180005def  add     eax, 3FFFFFF1h
0x180005df4  cmp     eax, 2Bh ; '+'
0x180005df7  ja      short loc_180005E09
0x180005df9  mov     rcx, 82000000001h
0x180005e03  bt      rcx, rax
0x180005e07  jb      short loc_180005E22
0x180005e09  lea     ecx, [rsi+3FEAFFFEh]
0x180005e0f  cmp     ecx, 10h
0x180005e12  ja      short loc_180005E1E
0x180005e14  mov     eax, 10005h
0x180005e19  bt      eax, ecx
0x180005e1c  jb      short loc_180005E22
0x180005e1e  xor     edx, edx
0x180005e20  jmp     short loc_180005E27
0x180005e22  mov     edx, 2; Level
0x180005e27  mov     [rsp+58h+var_28], esi
0x180005e2b  lea     r9, aBasesrvsxsgeta; "BaseSrvSxsGetActivationContextGeneratio"...
0x180005e32  mov     [rsp+58h+var_30], r15
0x180005e37  lea     r8, aSxsSLdrgetproc; "SXS: %s: LdrGetProcedureAddress(%wZ:%Z)"...
0x180005e3e  mov     ecx, 33h ; '3'; ComponentId
0x180005e43  mov     [rsp+58h+var_38], r14
0x180005e48  call    cs:__imp_DbgPrintEx
0x180005e4f  nop     dword ptr [rax+rax+00h]
0x180005e54  mov     rcx, [rsp+58h+BaseAddress]; BaseAddress
0x180005e59  mov     cs:SxsActivationContextGenerationFunction, 0
0x180005e64  call    cs:__imp_LdrUnloadDll
0x180005e6b  nop     dword ptr [rax+rax+00h]
0x180005e70  jmp     loc_180005D95
0x180005e75  mov     rdx, cs:SxsActivationContextGenerationFunction
0x180005e7c  movsxd  rax, cs:BaseSrvSxsGetActCtxGenCount
0x180005e83  mov     rcx, rax
0x180005e86  mov     [rdi], rdx
0x180005e89  inc     eax
0x180005e8b  mov     [rbx], rcx
0x180005e8e  mov     cs:BaseSrvSxsGetActCtxGenCount, eax
0x180005e94  xor     eax, eax
0x180005e96  jmp     loc_180005D97
0x180005e9b  mov     eax, 0C000000Dh
0x180005ea0  jmp     loc_180005DA6
```
