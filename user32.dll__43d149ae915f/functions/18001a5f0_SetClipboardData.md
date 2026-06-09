# SetClipboardData

- ea: `0x18001a5f0`
- end: `0x18001a83e`
- name: `SetClipboardData`
- size: `590`
- prototype: `HANDLE __stdcall(UINT uFormat, HANDLE hMem)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18007a624`
- `0x1800889f8`

## callees

- `0x18001a5f0`
- `0x18001a844`
- `0x18001bd44`
- `0x180053540`
- `0x180072ec4`

## import_xrefs

- `win32u!NtUserSetClipboardData` at `0x18001a63d`
- `win32u!NtUserSetClipboardData` at `0x18001a63d`
- `ntdll!RtlNtStatusToDosError` at `0x18001a768`
- `ntdll!RtlNtStatusToDosError` at `0x18001a768`
- `ntdll!RtlEnterCriticalSection` at `0x18001a625`
- `ntdll!RtlEnterCriticalSection` at `0x18001a625`
- `ntdll!RtlLeaveCriticalSection` at `0x18001a6b0`
- `ntdll!RtlLeaveCriticalSection` at `0x18001a792`
- `ntdll!RtlLeaveCriticalSection` at `0x18001a6b0`
- `ntdll!RtlLeaveCriticalSection` at `0x18001a792`
- `ntdll!RtlAllocateHeap` at `0x18001a676`
- `ntdll!RtlAllocateHeap` at `0x18001a676`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180099c58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180099c58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099c8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099c8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099c7c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalFlags` at `0x18001a731`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalFlags` at `0x18001a731`
- `GDI32!GdiConvertEnhMetaFile` at `0x18001a7d8`
- `GDI32!GdiConvertEnhMetaFile` at `0x18001a7d8`
- `GDI32!GdiConvertMetaFilePict` at `0x18001a82a`
- `GDI32!GdiConvertMetaFilePict` at `0x18001a82a`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x180099ca6`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x180099ca6`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsUIPolicyEvaluationEnabledForThread` at `0x180099c0a`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsUIPolicyEvaluationEnabledForThread` at `0x180099c0a`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180099c26`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForWindow` at `0x180099c26`
- `ext-ms-win-edputil-policy-l1-1-0!EdpClearClipboardMetaData` at `0x180099c34`
- `ext-ms-win-edputil-policy-l1-1-0!EdpClearClipboardMetaData` at `0x180099c34`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetEnterpriseIdForClipboard` at `0x180099c46`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetEnterpriseIdForClipboard` at `0x180099c46`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x180099c64`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x180099c64`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceAppIdForClipboard` at `0x180099c72`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceAppIdForClipboard` at `0x180099c72`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceIsEnlightenedForClipboard` at `0x180099c9c`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceIsEnlightenedForClipboard` at `0x180099c9c`

## pseudocode

```c
HANDLE __stdcall SetClipboardData(UINT uFormat, HANDLE hMem)
{
  HANDLE v2; // rdi
  unsigned int v3; // r15d
  HENHMETAFILE i; // rbx
  _QWORD *Heap; // rax
  void *v9; // rax
  NTSTATUS EdpEnforcementLevel2; // eax
  signed int v11; // eax
  bool v12; // sf
  unsigned int v13; // edx
  DWORD CurrentProcessId; // eax
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v17; // [rsp+68h] [rbp+48h] BYREF
  __int64 v18; // [rsp+70h] [rbp+50h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+58h] BYREF

  v2 = 0;
  v3 = 0;
  v18 = 0;
  if ( !hMem )
    goto LABEL_2;
  if ( uFormat > 0xE )
  {
    switch ( uFormat )
    {
      case 0x10u:
        goto LABEL_46;
      case 0x11u:
LABEL_45:
        v13 = 0;
LABEL_42:
        v9 = ConvertMemHandle(hMem, v13);
        v3 = 1;
        goto LABEL_22;
      case 0x80u:
        goto LABEL_20;
      case 0x81u:
        goto LABEL_46;
      case 0x82u:
        goto LABEL_43;
      case 0x83u:
        goto LABEL_44;
    }
    if ( uFormat != 142 )
    {
LABEL_20:
      if ( GlobalFlags(hMem) != 0x8000 )
      {
        v3 = 1;
        v9 = ConvertMemHandle(hMem, 0);
        goto LABEL_22;
      }
LABEL_43:
      v2 = hMem;
      goto LABEL_2;
    }
LABEL_38:
    v9 = (void *)GdiConvertEnhMetaFile(hMem);
    goto LABEL_22;
  }
  switch ( uFormat )
  {
    case 0xEu:
      goto LABEL_38;
    case 1u:
      goto LABEL_46;
    case 2u:
      goto LABEL_43;
  }
  if ( uFormat != 3 )
  {
    if ( uFormat != 7 )
    {
      if ( uFormat != 8 )
      {
        if ( uFormat == 9 )
          goto LABEL_43;
        if ( uFormat != 13 )
          goto LABEL_20;
        v13 = 2;
        goto LABEL_42;
      }
      goto LABEL_45;
    }
LABEL_46:
    v13 = 1;
    goto LABEL_42;
  }
LABEL_44:
  v9 = (void *)GdiConvertMetaFilePict(hMem);
LABEL_22:
  v2 = v9;
  if ( !v9 )
    return 0;
LABEL_2:
  RtlEnterCriticalSection(&gcsClipboard);
  v18 = v3 | 0x100000000LL;
  if ( !(unsigned int)NtUserSetClipboardData(uFormat, v2, &v18) )
  {
LABEL_29:
    RtlLeaveCriticalSection(&gcsClipboard);
    return 0;
  }
  for ( i = (HENHMETAFILE)gphn; i; i = *(HENHMETAFILE *)i )
  {
    if ( *((_DWORD *)i + 2) == uFormat )
    {
      if ( *((_QWORD *)i + 3) )
        DeleteClientClipboardHandle((HENHMETAFILE *)i);
      goto LABEL_9;
    }
  }
  Heap = RtlAllocateHeap(pUserHeap, 8u, 0x28u);
  i = (HENHMETAFILE)Heap;
  if ( !Heap )
    goto LABEL_29;
  *Heap = gphn;
  gphn = Heap;
LABEL_9:
  *((_QWORD *)i + 2) = v2;
  *((_QWORD *)i + 3) = hMem;
  *((_DWORD *)i + 2) = uFormat;
  *((_DWORD *)i + 8) = v3;
  RtlLeaveCriticalSection(&gcsClipboard);
  LODWORD(v17) = 0;
  if ( (unsigned __int8)IsEdpUtilGetEnterpriseContextByProcessPresent() )
  {
    EdpEnforcementLevel2 = EdpGetEdpEnforcementLevel2(&v17);
    v11 = RtlNtStatusToDosError(EdpEnforcementLevel2);
    v12 = v11 < 0;
    if ( v11 > 0 )
      v12 = 1;
    if ( !v12 )
    {
      if ( (_DWORD)v17 )
      {
        if ( (unsigned int)EdpIsUIPolicyEvaluationEnabledForThread() )
        {
          v17 = 0;
          if ( (int)EdpGetContextForWindow(0, &v17) >= 0 )
          {
            if ( (int)EdpClearClipboardMetaData() >= 0 && (int)EdpSetEnterpriseIdForClipboard(*(_QWORD *)(v17 + 8)) >= 0 )
            {
              lpMem = 0;
              CurrentProcessId = GetCurrentProcessId();
              if ( (int)EdpGetAppLockerUniqueAppIdentifier(CurrentProcessId, &lpMem) >= 0 )
              {
                EdpSetSourceAppIdForClipboard(lpMem);
                v15 = lpMem;
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v15);
              }
              if ( (*(_BYTE *)v17 & 3) != 0 )
                EdpSetSourceIsEnlightenedForClipboard(1);
            }
            EdpFreeContext(v17);
          }
        }
      }
    }
  }
  return hMem;
}

```

## disassembly

```asm
0x18001a5f0  push    rbp
0x18001a5f2  push    rbx
0x18001a5f3  push    rsi
0x18001a5f4  push    rdi
0x18001a5f5  push    r13
0x18001a5f7  push    r14
0x18001a5f9  push    r15
0x18001a5fb  mov     rbp, rsp
0x18001a5fe  sub     rsp, 20h
0x18001a602  xor     edi, edi
0x18001a604  xor     r15d, r15d
0x18001a607  mov     [rbp+arg_10], rdi
0x18001a60b  mov     rsi, rdx
0x18001a60e  mov     r14d, ecx
0x18001a611  lea     r13d, [rdi+1]
0x18001a615  test    rdx, rdx
0x18001a618  jnz     loc_18001A6DC
0x18001a61e  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001a625  call    cs:__imp_RtlEnterCriticalSection
0x18001a62b  lea     r8, [rbp+arg_10]
0x18001a62f  mov     dword ptr [rbp+arg_10], r15d
0x18001a633  mov     rdx, rdi
0x18001a636  mov     dword ptr [rbp+arg_10+4], r13d
0x18001a63a  mov     ecx, r14d
0x18001a63d  call    cs:__imp_NtUserSetClipboardData
0x18001a643  test    eax, eax
0x18001a645  jz      loc_18001A78B
0x18001a64b  mov     rbx, cs:?gphn@@3PEAU_HANDLENODE@@EA; _HANDLENODE * gphn
0x18001a652  test    rbx, rbx
0x18001a655  jz      short loc_18001A666
0x18001a657  cmp     [rbx+8], r14d
0x18001a65b  jz      loc_18001A7E3
0x18001a661  mov     rbx, [rbx]
0x18001a664  jmp     short loc_18001A652
0x18001a666  mov     rcx, cs:pUserHeap; HeapHandle
0x18001a66d  mov     edx, 8; Flags
0x18001a672  lea     r8d, [rdx+20h]; Size
0x18001a676  call    cs:__imp_RtlAllocateHeap
0x18001a67c  mov     rbx, rax
0x18001a67f  test    rax, rax
0x18001a682  jz      loc_18001A78B
0x18001a688  mov     rdx, cs:?gphn@@3PEAU_HANDLENODE@@EA; _HANDLENODE * gphn
0x18001a68f  mov     [rax], rdx
0x18001a692  mov     cs:?gphn@@3PEAU_HANDLENODE@@EA, rax; _HANDLENODE * gphn
0x18001a699  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001a6a0  mov     [rbx+10h], rdi
0x18001a6a4  mov     [rbx+18h], rsi
0x18001a6a8  mov     [rbx+8], r14d
0x18001a6ac  mov     [rbx+20h], r15d
0x18001a6b0  call    cs:__imp_RtlLeaveCriticalSection
0x18001a6b6  mov     dword ptr [rbp+arg_8], 0
0x18001a6bd  call    IsEdpUtilGetEnterpriseContextByProcessPresent
0x18001a6c2  test    al, al
0x18001a6c4  jnz     loc_18001A75D
0x18001a6ca  mov     rax, rsi
0x18001a6cd  add     rsp, 20h
0x18001a6d1  pop     r15
0x18001a6d3  pop     r14
0x18001a6d5  pop     r13
0x18001a6d7  pop     rdi
0x18001a6d8  pop     rsi
0x18001a6d9  pop     rbx
0x18001a6da  pop     rbp
0x18001a6db  retn
0x18001a6dc  cmp     r14d, 0Eh
0x18001a6e0  ja      loc_18001A79F
0x18001a6e6  jz      loc_18001A7D5
0x18001a6ec  mov     eax, r14d
0x18001a6ef  sub     eax, r13d
0x18001a6f2  jz      loc_18001A839
0x18001a6f8  sub     eax, r13d
0x18001a6fb  jz      loc_18001A81F
0x18001a701  sub     eax, r13d
0x18001a704  jz      loc_18001A827
0x18001a70a  sub     eax, 4
0x18001a70d  jz      loc_18001A839
0x18001a713  sub     eax, r13d
0x18001a716  jz      loc_18001A835
0x18001a71c  sub     eax, r13d
0x18001a71f  jz      loc_18001A81F
0x18001a725  cmp     eax, 4
0x18001a728  jz      loc_18001A7FB
0x18001a72e  mov     rcx, rsi; hMem
0x18001a731  call    cs:__imp_GlobalFlags
0x18001a737  cmp     eax, 8000h
0x18001a73c  jz      loc_18001A81F
0x18001a742  xor     edx, edx; unsigned int
0x18001a744  mov     rcx, rsi; hMem
0x18001a747  mov     r15d, r13d
0x18001a74a  call    ?ConvertMemHandle@@YAPEAXPEAXI@Z; ConvertMemHandle(void *,uint)
0x18001a74f  mov     rdi, rax
0x18001a752  test    rax, rax
0x18001a755  jnz     loc_18001A61E
0x18001a75b  jmp     short loc_18001A798
0x18001a75d  lea     rcx, [rbp+arg_8]
0x18001a761  call    EdpGetEdpEnforcementLevel2
0x18001a766  mov     ecx, eax; Status
0x18001a768  call    cs:__imp_RtlNtStatusToDosError
0x18001a76e  test    eax, eax
0x18001a770  jg      loc_18001A810
0x18001a776  js      loc_18001A6CA
0x18001a77c  cmp     dword ptr [rbp+arg_8], 0
0x18001a780  jz      loc_18001A6CA
0x18001a786  jmp     loc_180099C0A
0x18001a78b  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001a792  call    cs:__imp_RtlLeaveCriticalSection
0x18001a798  xor     eax, eax
0x18001a79a  jmp     loc_18001A6CD
0x18001a79f  mov     eax, r14d
0x18001a7a2  sub     eax, 10h
0x18001a7a5  jz      loc_18001A839
0x18001a7ab  sub     eax, r13d
0x18001a7ae  jz      loc_18001A835
0x18001a7b4  sub     eax, 6Fh ; 'o'
0x18001a7b7  jz      loc_18001A72E
0x18001a7bd  sub     eax, r13d
0x18001a7c0  jz      short loc_18001A839
0x18001a7c2  sub     eax, r13d
0x18001a7c5  jz      short loc_18001A81F
0x18001a7c7  sub     eax, r13d
0x18001a7ca  jz      short loc_18001A827
0x18001a7cc  cmp     eax, 0Bh
0x18001a7cf  jnz     loc_18001A72E
0x18001a7d5  mov     rcx, rsi
0x18001a7d8  call    cs:__imp_GdiConvertEnhMetaFile
0x18001a7de  jmp     loc_18001A74F
0x18001a7e3  cmp     qword ptr [rbx+18h], 0
0x18001a7e8  jz      loc_18001A699
0x18001a7ee  mov     rcx, rbx; struct _HANDLENODE *
0x18001a7f1  call    ?DeleteClientClipboardHandle@@YAHPEAU_HANDLENODE@@@Z; DeleteClientClipboardHandle(_HANDLENODE *)
0x18001a7f6  jmp     loc_18001A699
0x18001a7fb  mov     edx, 2; unsigned int
0x18001a800  mov     rcx, rsi; hMem
0x18001a803  call    ?ConvertMemHandle@@YAPEAXPEAXI@Z; ConvertMemHandle(void *,uint)
0x18001a808  mov     r15d, r13d
0x18001a80b  jmp     loc_18001A74F
0x18001a810  movzx   eax, ax
0x18001a813  or      eax, 80070000h
0x18001a818  test    eax, eax
0x18001a81a  jmp     loc_18001A776
0x18001a81f  mov     rdi, rsi
0x18001a822  jmp     loc_18001A61E
0x18001a827  mov     rcx, rsi
0x18001a82a  call    cs:__imp_GdiConvertMetaFilePict
0x18001a830  jmp     loc_18001A74F
0x18001a835  xor     edx, edx
0x18001a837  jmp     short loc_18001A800
0x18001a839  mov     edx, r13d
0x18001a83c  jmp     short loc_18001A800
0x180099c0a  call    cs:__imp_EdpIsUIPolicyEvaluationEnabledForThread
0x180099c10  test    eax, eax
0x180099c12  jz      loc_18001A6CA
0x180099c18  lea     rdx, [rbp+arg_8]
0x180099c1c  mov     [rbp+arg_8], 0
0x180099c24  xor     ecx, ecx
0x180099c26  call    cs:__imp_EdpGetContextForWindow
0x180099c2c  test    eax, eax
0x180099c2e  js      loc_18001A6CA
0x180099c34  call    cs:__imp_EdpClearClipboardMetaData
0x180099c3a  test    eax, eax
0x180099c3c  js      short loc_180099CA2
0x180099c3e  mov     rcx, [rbp+arg_8]
0x180099c42  mov     rcx, [rcx+8]
0x180099c46  call    cs:__imp_EdpSetEnterpriseIdForClipboard
0x180099c4c  test    eax, eax
0x180099c4e  js      short loc_180099CA2
0x180099c50  mov     [rbp+lpMem], 0
0x180099c58  call    cs:__imp_GetCurrentProcessId
0x180099c5e  mov     ecx, eax
0x180099c60  lea     rdx, [rbp+lpMem]
0x180099c64  call    cs:__imp_EdpGetAppLockerUniqueAppIdentifier
0x180099c6a  test    eax, eax
0x180099c6c  js      short loc_180099C90
0x180099c6e  mov     rcx, [rbp+lpMem]
0x180099c72  call    cs:__imp_EdpSetSourceAppIdForClipboard
0x180099c78  mov     rbx, [rbp+lpMem]
0x180099c7c  call    cs:__imp_GetProcessHeap
0x180099c82  mov     r8, rbx; lpMem
0x180099c85  xor     edx, edx; dwFlags
0x180099c87  mov     rcx, rax; hHeap
0x180099c8a  call    cs:__imp_HeapFree
0x180099c90  mov     rax, [rbp+arg_8]
0x180099c94  test    byte ptr [rax], 3
0x180099c97  jbe     short loc_180099CA2
0x180099c99  mov     ecx, r13d
0x180099c9c  call    cs:__imp_EdpSetSourceIsEnlightenedForClipboard
0x180099ca2  mov     rcx, [rbp+arg_8]
0x180099ca6  call    cs:__imp_EdpFreeContext
0x180099cac  nop
0x180099cad  jmp     loc_18001A6CA
```
