# CSLLUAComInstance::SLLUAActivateProduct(_GUID const *,tagSAFEARRAY *,tagVARIANT)

- ea: `0x18001d490`
- end: `0x18001d588`
- name: `?SLLUAActivateProduct@CSLLUAComInstance@@UEAAJPEBU_GUID@@PEAUtagSAFEARRAY@@UtagVARIANT@@@Z`
- size: `248`
- prototype: `int(CSLLUAComInstance *__hidden this, const struct _GUID *, struct tagSAFEARRAY *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001c0b0`
- `0x18001d490`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d547`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d55b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d55b`
- `SLC!SLOpen` at `0x18001d4ed`
- `SLC!SLOpen` at `0x18001d4ed`
- `SLC!SLClose` at `0x18001d570`
- `SLC!SLClose` at `0x18001d570`
- `sppcext!SLActivateProduct` at `0x18001d522`
- `sppcext!SLActivateProduct` at `0x18001d522`

## pseudocode

```c
__int64 __fastcall CSLLUAComInstance::SLLUAActivateProduct(
        CSLLUAComInstance *this,
        const struct _GUID *a2,
        struct tagSAFEARRAY *a3,
        struct tagVARIANT *a4)
{
  PVOID v4; // rdi
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v8; // eax
  HRESULT v9; // eax
  HANDLE ProcessHeap; // rax
  PVOID pvAppSpecificData; // [rsp+40h] [rbp-18h] BYREF
  HSLC phSLC; // [rsp+48h] [rbp-10h] BYREF
  UINT cbAppSpecificData; // [rsp+88h] [rbp+30h] BYREF

  v4 = 0;
  phSLC = 0;
  pvAppSpecificData = 0;
  cbAppSpecificData = 0;
  if ( !a2 || !a3 )
  {
    v6 = 2147942487LL;
    v7 = -2147024809;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_10;
  }
  v8 = CSafeArrayHelperT<CEmptyType>::ExtractFromSafeArray(a3, (__int64 *)&pvAppSpecificData, &cbAppSpecificData);
  v7 = v8;
  if ( v8 < 0 || (v8 = SLOpen(&phSLC), v7 = v8, v8 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
    v4 = pvAppSpecificData;
    goto LABEL_10;
  }
  v4 = pvAppSpecificData;
  v9 = SLActivateProduct(phSLC, a2, cbAppSpecificData, pvAppSpecificData, 0, 0, 0);
  v7 = v9;
  if ( v9 < 0 )
  {
    v6 = (unsigned int)v9;
    goto LABEL_9;
  }
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( phSLC )
    SLClose(phSLC);
  return v7;
}

```

## disassembly

```asm
0x18001d490  push    rbp
0x18001d492  push    rbx
0x18001d493  push    rsi
0x18001d494  push    rdi
0x18001d495  mov     rbp, rsp
0x18001d498  sub     rsp, 58h
0x18001d49c  xor     edi, edi
0x18001d49e  mov     [rbp+phSLC], 0
0x18001d4a6  mov     [rbp+pvAppSpecificData], rdi
0x18001d4aa  mov     rax, r8
0x18001d4ad  mov     [rbp+cbAppSpecificData], edi
0x18001d4b0  mov     rsi, rdx
0x18001d4b3  test    rdx, rdx
0x18001d4b6  jnz     short loc_18001D4C1
0x18001d4b8  mov     ecx, 80070057h
0x18001d4bd  mov     ebx, ecx
0x18001d4bf  jmp     short loc_18001D536
0x18001d4c1  test    rax, rax
0x18001d4c4  jz      short loc_18001D4B8
0x18001d4c6  lea     r8, [rbp+cbAppSpecificData]
0x18001d4ca  mov     rcx, rax; psa
0x18001d4cd  lea     rdx, [rbp+pvAppSpecificData]
0x18001d4d1  call    ?ExtractFromSafeArray@?$CSafeArrayHelperT@VCEmptyType@@@@SAJPEAUtagSAFEARRAY@@PEAPEAEPEAK@Z; CSafeArrayHelperT<CEmptyType>::ExtractFromSafeArray(tagSAFEARRAY *,uchar * *,ulong *)
0x18001d4d6  mov     ebx, eax
0x18001d4d8  test    eax, eax
0x18001d4da  jns     short loc_18001D4E9
0x18001d4dc  mov     ecx, eax
0x18001d4de  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d4e3  mov     rdi, [rbp+pvAppSpecificData]
0x18001d4e7  jmp     short loc_18001D53B
0x18001d4e9  lea     rcx, [rbp+phSLC]; phSLC
0x18001d4ed  call    cs:__imp_SLOpen
0x18001d4f4  nop     dword ptr [rax+rax+00h]
0x18001d4f9  mov     ebx, eax
0x18001d4fb  test    eax, eax
0x18001d4fd  js      short loc_18001D4DC
0x18001d4ff  mov     rdi, [rbp+pvAppSpecificData]
0x18001d503  xor     eax, eax
0x18001d505  mov     r8d, [rbp+cbAppSpecificData]; cbAppSpecificData
0x18001d509  mov     r9, rdi; pvAppSpecificData
0x18001d50c  mov     rcx, [rbp+phSLC]; hSLC
0x18001d510  mov     rdx, rsi; pProductSkuId
0x18001d513  mov     [rsp+58h+wProxyPort], ax; wProxyPort
0x18001d518  mov     [rsp+58h+pwszProxyServer], rax; pwszProxyServer
0x18001d51d  mov     [rsp+58h+pActivationInfo], rax; pActivationInfo
0x18001d522  call    cs:__imp_SLActivateProduct
0x18001d529  nop     dword ptr [rax+rax+00h]
0x18001d52e  mov     ebx, eax
0x18001d530  test    eax, eax
0x18001d532  jns     short loc_18001D53B
0x18001d534  mov     ecx, eax
0x18001d536  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d53b  mov     ecx, ebx
0x18001d53d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d542  test    rdi, rdi
0x18001d545  jz      short loc_18001D567
0x18001d547  call    cs:__imp_GetProcessHeap
0x18001d54e  nop     dword ptr [rax+rax+00h]
0x18001d553  mov     r8, rdi; lpMem
0x18001d556  xor     edx, edx; dwFlags
0x18001d558  mov     rcx, rax; hHeap
0x18001d55b  call    cs:__imp_HeapFree
0x18001d562  nop     dword ptr [rax+rax+00h]
0x18001d567  mov     rcx, [rbp+phSLC]; hSLC
0x18001d56b  test    rcx, rcx
0x18001d56e  jz      short loc_18001D57C
0x18001d570  call    cs:__imp_SLClose
0x18001d577  nop     dword ptr [rax+rax+00h]
0x18001d57c  mov     eax, ebx
0x18001d57e  add     rsp, 58h
0x18001d582  pop     rdi
0x18001d583  pop     rsi
0x18001d584  pop     rbx
0x18001d585  pop     rbp
0x18001d586  retn
```
