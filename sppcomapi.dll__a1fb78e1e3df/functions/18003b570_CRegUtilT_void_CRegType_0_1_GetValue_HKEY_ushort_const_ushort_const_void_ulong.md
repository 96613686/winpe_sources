# CRegUtilT<void *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,void * *,ulong *)

- ea: `0x18003b570`
- end: `0x18003b70e`
- name: `?GetValue@?$CRegUtilT@PEAXUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAXPEAK@Z`
- size: `414`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003b294`
- `0x18003b714`

## callees

- `0x180003520`
- `0x180004288`
- `0x18003b570`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b6ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b6ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b6de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b6de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b65d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b65d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b629`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b629`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b5f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b6f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b5f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b6f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b5b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b5b1`

## pseudocode

```c
__int64 __fastcall CRegUtilT<void *,CRegType,0,1>::GetValue(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        BYTE **a4,
        DWORD *a5)
{
  BYTE *v5; // rdi
  int v8; // ebx
  HKEY v9; // rsi
  DWORD v10; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v12; // rax
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+38h] BYREF
  int v17; // [rsp+84h] [rbp+3Ch]

  v17 = HIDWORD(a1);
  v5 = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey);
  if ( v8 )
  {
    v9 = 0;
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
  }
  else
  {
    v9 = hKey;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v8 < 0 )
  {
LABEL_22:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
  }
  else
  {
    cbData = 0;
    while ( 1 )
    {
      v8 = RegQueryValueExW(v9, a3, 0, &Type, v5, &cbData);
      if ( v8 )
      {
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        goto LABEL_22;
      }
      if ( v5 )
        break;
      if ( !cbData )
      {
        v8 = -2147418113;
        goto LABEL_22;
      }
      v10 = cbData;
      ProcessHeap = GetProcessHeap();
      v5 = (BYTE *)HeapAlloc(ProcessHeap, 0, v10);
      if ( !v5 )
      {
        v8 = -2147024882;
        goto LABEL_22;
      }
    }
    if ( Type != 3 )
    {
      v8 = -2147024883;
      goto LABEL_22;
    }
    *a4 = v5;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v8 = 0;
    v5 = 0;
    if ( a5 )
      *a5 = cbData;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v5 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v5);
  }
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003b570  mov     qword ptr [rsp-30h+cbData], rcx
0x18003b575  push    rbp
0x18003b576  push    rbx
0x18003b577  push    rsi
0x18003b578  push    rdi
0x18003b579  push    r14
0x18003b57b  push    r15
0x18003b57d  mov     rbp, rsp
0x18003b580  sub     rsp, 48h
0x18003b584  xor     edi, edi
0x18003b586  mov     [rbp+Type], 0
0x18003b58d  mov     r14, r9
0x18003b590  mov     [rbp+cbData], edi
0x18003b593  mov     r15, r8
0x18003b596  mov     [rbp+hKey], rdi
0x18003b59a  lea     rax, [rbp+hKey]
0x18003b59e  xor     r8d, r8d; ulOptions
0x18003b5a1  lea     r9d, [rdi+1]; samDesired
0x18003b5a5  mov     [rsp+48h+phkResult], rax; phkResult
0x18003b5aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b5b1  call    cs:__imp_RegOpenKeyExW
0x18003b5b8  nop     dword ptr [rax+rax+00h]
0x18003b5bd  mov     ebx, eax
0x18003b5bf  test    eax, eax
0x18003b5c1  jnz     short loc_18003B5CD
0x18003b5c3  mov     rsi, [rbp+hKey]
0x18003b5c7  mov     [rbp+hKey], rdi
0x18003b5cb  jmp     short loc_18003B5E3
0x18003b5cd  xor     esi, esi
0x18003b5cf  test    ebx, ebx
0x18003b5d1  jle     short loc_18003B5DC
0x18003b5d3  movzx   ebx, bx
0x18003b5d6  or      ebx, 80070000h
0x18003b5dc  mov     ecx, ebx
0x18003b5de  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b5e3  mov     ecx, ebx
0x18003b5e5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b5ea  mov     rcx, [rbp+hKey]; hKey
0x18003b5ee  test    rcx, rcx
0x18003b5f1  jz      short loc_18003B603
0x18003b5f3  call    cs:__imp_RegCloseKey
0x18003b5fa  nop     dword ptr [rax+rax+00h]
0x18003b5ff  mov     [rbp+hKey], rdi
0x18003b603  test    ebx, ebx
0x18003b605  js      loc_18003B6B7
0x18003b60b  mov     [rbp+cbData], edi
0x18003b60e  lea     rax, [rbp+cbData]
0x18003b612  xor     r8d, r8d; lpReserved
0x18003b615  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18003b61a  lea     r9, [rbp+Type]; lpType
0x18003b61e  mov     rdx, r15; lpValueName
0x18003b621  mov     [rsp+48h+phkResult], rdi; lpData
0x18003b626  mov     rcx, rsi; hKey
0x18003b629  call    cs:__imp_RegQueryValueExW
0x18003b630  nop     dword ptr [rax+rax+00h]
0x18003b635  mov     ebx, eax
0x18003b637  test    eax, eax
0x18003b639  jnz     short loc_18003B6AA
0x18003b63b  test    rdi, rdi
0x18003b63e  jnz     short loc_18003B67F
0x18003b640  mov     eax, [rbp+cbData]
0x18003b643  test    eax, eax
0x18003b645  jz      short loc_18003B678
0x18003b647  mov     ebx, eax
0x18003b649  call    cs:__imp_GetProcessHeap
0x18003b650  nop     dword ptr [rax+rax+00h]
0x18003b655  mov     r8d, ebx; dwBytes
0x18003b658  xor     edx, edx; dwFlags
0x18003b65a  mov     rcx, rax; hHeap
0x18003b65d  call    cs:__imp_HeapAlloc
0x18003b664  nop     dword ptr [rax+rax+00h]
0x18003b669  mov     rdi, rax
0x18003b66c  test    rax, rax
0x18003b66f  jnz     short loc_18003B60E
0x18003b671  mov     ebx, 8007000Eh
0x18003b676  jmp     short loc_18003B6B7
0x18003b678  mov     ebx, 8000FFFFh
0x18003b67d  jmp     short loc_18003B6B7
0x18003b67f  cmp     [rbp+Type], 3
0x18003b683  jz      short loc_18003B68C
0x18003b685  mov     ebx, 8007000Dh
0x18003b68a  jmp     short loc_18003B6B7
0x18003b68c  mov     [r14], rdi
0x18003b68f  xor     ecx, ecx
0x18003b691  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b696  mov     rcx, [rbp+arg_20]
0x18003b69a  xor     ebx, ebx
0x18003b69c  xor     edi, edi
0x18003b69e  test    rcx, rcx
0x18003b6a1  jz      short loc_18003B6BE
0x18003b6a3  mov     eax, [rbp+cbData]
0x18003b6a6  mov     [rcx], eax
0x18003b6a8  jmp     short loc_18003B6BE
0x18003b6aa  test    ebx, ebx
0x18003b6ac  jle     short loc_18003B6B7
0x18003b6ae  movzx   ebx, bx
0x18003b6b1  or      ebx, 80070000h
0x18003b6b7  mov     ecx, ebx
0x18003b6b9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b6be  mov     ecx, ebx
0x18003b6c0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b6c5  test    rdi, rdi
0x18003b6c8  jz      short loc_18003B6EA
0x18003b6ca  call    cs:__imp_GetProcessHeap
0x18003b6d1  nop     dword ptr [rax+rax+00h]
0x18003b6d6  mov     r8, rdi; lpMem
0x18003b6d9  xor     edx, edx; dwFlags
0x18003b6db  mov     rcx, rax; hHeap
0x18003b6de  call    cs:__imp_HeapFree
0x18003b6e5  nop     dword ptr [rax+rax+00h]
0x18003b6ea  test    rsi, rsi
0x18003b6ed  jz      short loc_18003B6FE
0x18003b6ef  mov     rcx, rsi; hKey
0x18003b6f2  call    cs:__imp_RegCloseKey
0x18003b6f9  nop     dword ptr [rax+rax+00h]
0x18003b6fe  mov     eax, ebx
0x18003b700  add     rsp, 48h
0x18003b704  pop     r15
0x18003b706  pop     r14
0x18003b708  pop     rdi
0x18003b709  pop     rsi
0x18003b70a  pop     rbx
0x18003b70b  pop     rbp
0x18003b70c  retn
```
