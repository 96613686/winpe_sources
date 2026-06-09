# GetClipboardData

- ea: `0x18001af90`
- end: `0x18001b566`
- name: `GetClipboardData`
- size: `1494`
- prototype: `HANDLE __stdcall(UINT uFormat)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18006bef0`
- `0x18007d2a0`

## callees

- `0x18001a844`
- `0x18001af90`
- `0x18001b56c`
- `0x18001b5fc`
- `0x18001bd44`
- `0x18001bdf0`
- `0x18001c260`
- `0x18001c2b0`
- `0x18006e618`
- `0x180072ec4`

## import_xrefs

- `win32u!NtUserSetClipboardData` at `0x18001b2ac`
- `win32u!NtUserSetClipboardData` at `0x18001b2ac`
- `win32u!NtUserGetClipboardData` at `0x18001afc5`
- `win32u!NtUserGetClipboardData` at `0x18001afc5`
- `ntdll!RtlNtStatusToDosError` at `0x18001b083`
- `ntdll!RtlNtStatusToDosError` at `0x18001b083`
- `ntdll!RtlEnterCriticalSection` at `0x18001afea`
- `ntdll!RtlEnterCriticalSection` at `0x18001b28f`
- `ntdll!RtlEnterCriticalSection` at `0x18001afea`
- `ntdll!RtlEnterCriticalSection` at `0x18001b28f`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b025`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b2c1`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b025`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b2c1`
- `ntdll!RtlFreeHeap` at `0x18001b515`
- `ntdll!RtlFreeHeap` at `0x18001b515`
- `ntdll!RtlAllocateHeap` at `0x18001b00c`
- `ntdll!RtlAllocateHeap` at `0x18001b00c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b2cf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b2dd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b3e0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b3e9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b478`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b2cf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b2dd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b3e0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b3e9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001b478`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001b486`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001b486`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b377`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b3b6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b377`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001b3b6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001b215`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001b26b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180099dab`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180099e01`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001b215`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001b26b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180099dab`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180099e01`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18001b181`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18001b181`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18001b232`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18001b393`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180099dc8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18001b232`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18001b393`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180099dc8`
- `GDI32!GdiConvertBitmapV5` at `0x18001b4b7`
- `GDI32!GdiConvertBitmapV5` at `0x18001b54f`
- `GDI32!GdiConvertBitmapV5` at `0x18001b4b7`
- `GDI32!GdiConvertBitmapV5` at `0x18001b54f`
- `GDI32!GdiCreateLocalEnhMetaFile` at `0x18001b4f0`
- `GDI32!GdiCreateLocalEnhMetaFile` at `0x18001b4f0`
- `GDI32!GdiCreateLocalMetaFilePict` at `0x18001b4fe`
- `GDI32!GdiCreateLocalMetaFilePict` at `0x18001b4fe`
- `ext-ms-win-edputil-policy-l1-1-0!EdpCanCallerAccessWin32Clipboard` at `0x18001b0ac`
- `ext-ms-win-edputil-policy-l1-1-0!EdpCanCallerAccessWin32Clipboard` at `0x18001b0ac`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetClipboardAccessDeniedData` at `0x18001b0d3`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetClipboardAccessDeniedData` at `0x18001b0d3`

## pseudocode

```c
HANDLE __stdcall GetClipboardData(UINT uFormat)
{
  __int64 ClipboardData; // rbx
  _QWORD *i; // rax
  void *v4; // rsi
  _DWORD *Heap; // rax
  _DWORD *v6; // rdi
  __int64 v7; // rdx
  NTSTATUS EdpEnforcementLevel2; // eax
  signed int v10; // eax
  bool v11; // sf
  void *LocalEnhMetaFile; // rax
  CHAR *v13; // rdi
  int v14; // ecx
  void *LocalMemHandle; // rax
  void *v16; // rsi
  int v17; // r15d
  int v18; // ecx
  unsigned int v19; // r12d
  unsigned int v20; // r13d
  UINT v21; // r13d
  unsigned __int64 v22; // r12
  int v23; // eax
  int cbMultiByte; // r15d
  CHAR *lpMultiByteStr; // rax
  unsigned int v26; // edx
  UINT v27; // r12d
  int v28; // eax
  int v29; // ebx
  WCHAR *v30; // rax
  unsigned int *v31; // rax
  UINT ClipboardCodePage; // eax
  unsigned __int64 v33; // r12
  int v34; // eax
  int v35; // r15d
  CHAR *v36; // rax
  void *v37[2]; // [rsp+40h] [rbp-10h] BYREF
  UINT CodePage; // [rsp+98h] [rbp+48h] BYREF
  void *v39; // [rsp+A0h] [rbp+50h] BYREF

  *(_OWORD *)v37 = 0;
  if ( (unsigned __int8)IsEdpUtilGetEnterpriseContextByProcessPresent() )
  {
    CodePage = 0;
    EdpEnforcementLevel2 = EdpGetEdpEnforcementLevel2(&CodePage);
    v10 = RtlNtStatusToDosError(EdpEnforcementLevel2);
    v11 = v10 < 0;
    if ( v10 > 0 )
      v11 = 1;
    if ( !v11 )
    {
      if ( CodePage )
      {
        CodePage = 1;
        if ( (int)EdpCanCallerAccessWin32Clipboard(&CodePage) >= 0 && CodePage != 1 )
        {
          v39 = 0;
          EdpGetClipboardAccessDeniedData(uFormat, &v39);
          return v39;
        }
      }
    }
  }
  ClipboardData = NtUserGetClipboardData(uFormat, v37);
  if ( !ClipboardData )
    return 0;
  if ( uFormat != LODWORD(v37[0]) )
  {
    v13 = 0;
    v39 = 0;
    if ( LODWORD(v37[0]) > 0xD || (v14 = 8578, !_bittest(&v14, (unsigned int)v37[0])) )
    {
      v16 = 0;
      if ( LODWORD(v37[0]) != 17 )
        goto LABEL_42;
    }
    LocalMemHandle = CreateLocalMemHandle((void *)ClipboardData);
    v16 = LocalMemHandle;
    if ( !LocalMemHandle )
      return 0;
    v17 = GlobalSize(LocalMemHandle);
    if ( !v17 )
    {
LABEL_64:
      GlobalFree(v16);
      return 0;
    }
    v18 = (int)v37[0];
    if ( LODWORD(v37[0]) == 1 || LODWORD(v37[0]) == 7 || (v19 = 0, LODWORD(v37[0]) == 13) )
    {
      v31 = (unsigned int *)CreateLocalMemHandle(v37[1]);
      if ( v31 )
      {
        v19 = *v31;
        GlobalFree(v31);
      }
      else
      {
        v19 = 0;
      }
      v13 = (CHAR *)GlobalAlloc(0x40u, v17);
      if ( !v13 )
        goto LABEL_64;
      v18 = (int)v37[0];
    }
    v20 = 0;
    switch ( uFormat )
    {
      case 1u:
        v20 = 1;
        if ( v18 == 7 )
        {
          OemToCharA((LPCSTR)v16, v13);
        }
        else
        {
          ClipboardCodePage = GetClipboardCodePage(v19, 0x1004u);
          v33 = (unsigned __int64)v17 >> 1;
          CodePage = ClipboardCodePage;
          v34 = WideCharToMultiByte(ClipboardCodePage, 0, (LPCWCH)v16, v33, 0, 0, 0, 0);
          v35 = v34;
          if ( !v34 )
            goto LABEL_63;
          v36 = (CHAR *)GlobalReAlloc(v13, v34, 0x42u);
          if ( !v36 )
            goto LABEL_63;
          v13 = v36;
          if ( !WideCharToMultiByte(CodePage, 0, (LPCWCH)v16, v33, v36, v35, 0, 0) )
            goto LABEL_63;
        }
        break;
      case 2u:
        if ( v18 != 17 )
          goto LABEL_64;
        ClipboardData = GdiConvertBitmapV5(v16, (unsigned int)v17, v37[1], 2);
        if ( !ClipboardData )
          goto LABEL_64;
        break;
      case 7u:
        if ( v18 == 1 )
        {
          CharToOemA((LPCSTR)v16, v13);
        }
        else
        {
          v21 = GetClipboardCodePage(v19, 0xBu);
          v22 = (unsigned __int64)v17 >> 1;
          v23 = WideCharToMultiByte(v21, 0, (LPCWCH)v16, v22, 0, 0, 0, 0);
          cbMultiByte = v23;
          if ( !v23 )
            goto LABEL_63;
          lpMultiByteStr = (CHAR *)GlobalReAlloc(v13, v23, 0x42u);
          if ( !lpMultiByteStr )
            goto LABEL_63;
          v13 = lpMultiByteStr;
          if ( !WideCharToMultiByte(v21, 0, (LPCWCH)v16, v22, lpMultiByteStr, cbMultiByte, 0, 0) )
            goto LABEL_63;
        }
        v20 = 1;
        break;
      case 8u:
        if ( v18 != 17 )
          goto LABEL_64;
        v13 = (CHAR *)GdiConvertBitmapV5(v16, (unsigned int)v17, v37[1], 8);
        if ( !v13 )
          goto LABEL_64;
        goto LABEL_62;
      case 0xDu:
        v26 = 4100;
        if ( v18 != 1 )
          v26 = 11;
        v27 = GetClipboardCodePage(v19, v26);
        v28 = MultiByteToWideChar(v27, 1u, (LPCCH)v16, v17, 0, 0);
        v29 = v28;
        if ( !v28 )
          goto LABEL_63;
        v30 = (WCHAR *)GlobalReAlloc(v13, 2LL * v28, 0x42u);
        if ( !v30 )
          goto LABEL_63;
        v13 = (CHAR *)v30;
        if ( !MultiByteToWideChar(v27, 1u, (LPCCH)v16, v17, v30, v29) )
          goto LABEL_63;
        v20 = 2;
LABEL_62:
        ClipboardData = (__int64)ConvertMemHandle(v13, v20);
        if ( !ClipboardData )
        {
LABEL_63:
          GlobalFree(v13);
          goto LABEL_64;
        }
LABEL_42:
        RtlEnterCriticalSection(&gcsClipboard);
        v39 = (void *)HIDWORD(v37[0]);
        ClipboardData &= -(__int64)((unsigned int)NtUserSetClipboardData(uFormat, ClipboardData, &v39) != 0);
        RtlLeaveCriticalSection(&gcsClipboard);
        if ( v13 )
          GlobalFree(v13);
        if ( v16 )
          GlobalFree(v16);
        if ( ClipboardData )
          goto LABEL_4;
        return 0;
    }
    if ( !v13 )
      goto LABEL_42;
    goto LABEL_62;
  }
LABEL_4:
  RtlEnterCriticalSection(&gcsClipboard);
  for ( i = gphn; i; i = (_QWORD *)*i )
  {
    if ( i[2] == ClipboardData && *((_DWORD *)i + 2) == uFormat )
    {
      v4 = (void *)i[3];
      goto LABEL_7;
    }
  }
  v4 = 0;
  Heap = RtlAllocateHeap(pUserHeap, 8u, 0x28u);
  v6 = Heap;
  if ( !Heap )
    goto LABEL_7;
  *((_QWORD *)Heap + 2) = ClipboardData;
  Heap[2] = v37[0];
  Heap[8] = HIDWORD(v37[0]);
  if ( uFormat <= 0xE )
  {
    if ( uFormat == 14 )
    {
LABEL_84:
      LocalEnhMetaFile = (void *)GdiCreateLocalEnhMetaFile(ClipboardData);
      goto LABEL_23;
    }
    if ( uFormat != 1 )
    {
      if ( uFormat == 2 )
        goto LABEL_24;
      if ( uFormat == 3 )
        goto LABEL_85;
      if ( uFormat != 7 && uFormat != 8 )
      {
        if ( uFormat == 9 )
          goto LABEL_24;
        if ( uFormat != 13 )
          goto LABEL_52;
      }
    }
  }
  else if ( uFormat != 16 && uFormat != 17 && uFormat != 129 )
  {
    if ( uFormat == 130 )
      goto LABEL_24;
    if ( uFormat != 131 )
    {
      if ( uFormat != 142 )
      {
LABEL_52:
        if ( !HIDWORD(v37[0]) )
          goto LABEL_24;
        LocalEnhMetaFile = CreateLocalMemHandle((void *)ClipboardData);
        goto LABEL_23;
      }
      goto LABEL_84;
    }
LABEL_85:
    LocalEnhMetaFile = (void *)GdiCreateLocalMetaFilePict(ClipboardData);
    goto LABEL_23;
  }
  LocalEnhMetaFile = CreateLocalMemHandle((void *)ClipboardData);
  v6[8] = 1;
LABEL_23:
  ClipboardData = (__int64)LocalEnhMetaFile;
LABEL_24:
  *((_QWORD *)v6 + 3) = ClipboardData;
  if ( ClipboardData )
  {
    v4 = (void *)ClipboardData;
    *(_QWORD *)v6 = gphn;
    gphn = v6;
  }
  else
  {
    RtlFreeHeap(pUserHeap, 0, v6);
  }
LABEL_7:
  RtlLeaveCriticalSection(&gcsClipboard);
  LOBYTE(v7) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipboardCredentialMonitor>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ClipboardCredentialMonitor>::GetImpl'::`2'::impl,
    v7);
  OnPastingData(v4, uFormat);
  return v4;
}

```

## disassembly

```asm
0x18001af90  mov     [rsp-38h+arg_0], rbx
0x18001af95  push    rbp
0x18001af96  push    rsi
0x18001af97  push    rdi
0x18001af98  push    r12
0x18001af9a  push    r13
0x18001af9c  push    r14
0x18001af9e  push    r15
0x18001afa0  mov     rbp, rsp
0x18001afa3  sub     rsp, 50h
0x18001afa7  xorps   xmm0, xmm0
0x18001afaa  mov     r14d, ecx
0x18001afad  movups  xmmword ptr [rbp+var_10], xmm0
0x18001afb1  call    IsEdpUtilGetEnterpriseContextByProcessPresent
0x18001afb6  test    al, al
0x18001afb8  jnz     loc_18001B071
0x18001afbe  lea     rdx, [rbp+var_10]
0x18001afc2  mov     ecx, r14d
0x18001afc5  call    cs:__imp_NtUserGetClipboardData
0x18001afcb  mov     rbx, rax
0x18001afce  test    rax, rax
0x18001afd1  jz      loc_18001B2EC
0x18001afd7  mov     eax, dword ptr [rbp+var_10]
0x18001afda  cmp     r14d, eax
0x18001afdd  jnz     loc_18001B14D
0x18001afe3  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001afea  call    cs:__imp_RtlEnterCriticalSection
0x18001aff0  mov     rax, cs:?gphn@@3PEAU_HANDLENODE@@EA; _HANDLENODE * gphn
0x18001aff7  test    rax, rax
0x18001affa  jnz     short loc_18001B05F
0x18001affc  mov     rcx, cs:pUserHeap; HeapHandle
0x18001b003  lea     edx, [rax+8]; Flags
0x18001b006  lea     r8d, [rax+28h]; Size
0x18001b00a  xor     esi, esi
0x18001b00c  call    cs:__imp_RtlAllocateHeap
0x18001b012  mov     rdi, rax
0x18001b015  test    rax, rax
0x18001b018  jnz     loc_18001B0EA
0x18001b01e  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001b025  call    cs:__imp_RtlLeaveCriticalSection
0x18001b02b  mov     dl, 1
0x18001b02d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ClipboardCredentialMonitor@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ClipboardCredentialMonitor@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipboardCredentialMonitor> `wil::Feature<__WilFeatureTraits_Feature_ClipboardCredentialMonitor>::GetImpl(void)'::`2'::impl
0x18001b034  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ClipboardCredentialMonitor@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipboardCredentialMonitor>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001b039  mov     edx, r14d; int
0x18001b03c  mov     rcx, rsi; hMem
0x18001b03f  call    ?OnPastingData@@YAXQEAXH@Z; OnPastingData(void * const,int)
0x18001b044  mov     rax, rsi
0x18001b047  mov     rbx, [rsp+50h+arg_0]
0x18001b04f  add     rsp, 50h
0x18001b053  pop     r15
0x18001b055  pop     r14
0x18001b057  pop     r13
0x18001b059  pop     r12
0x18001b05b  pop     rdi
0x18001b05c  pop     rsi
0x18001b05d  pop     rbp
0x18001b05e  retn
0x18001b05f  cmp     [rax+10h], rbx
0x18001b063  jnz     short loc_18001B0E2
0x18001b065  cmp     [rax+8], r14d
0x18001b069  jnz     short loc_18001B0E2
0x18001b06b  mov     rsi, [rax+18h]
0x18001b06f  jmp     short loc_18001B01E
0x18001b071  lea     rcx, [rbp+CodePage]
0x18001b075  mov     [rbp+CodePage], 0
0x18001b07c  call    EdpGetEdpEnforcementLevel2
0x18001b081  mov     ecx, eax; Status
0x18001b083  call    cs:__imp_RtlNtStatusToDosError
0x18001b089  test    eax, eax
0x18001b08b  jg      loc_18001B441
0x18001b091  js      loc_18001AFBE
0x18001b097  cmp     [rbp+CodePage], 0
0x18001b09b  jz      loc_18001AFBE
0x18001b0a1  lea     rcx, [rbp+CodePage]
0x18001b0a5  mov     [rbp+CodePage], 1
0x18001b0ac  call    cs:__imp_EdpCanCallerAccessWin32Clipboard
0x18001b0b2  test    eax, eax
0x18001b0b4  js      loc_18001AFBE
0x18001b0ba  cmp     [rbp+CodePage], 1
0x18001b0be  jz      loc_18001AFBE
0x18001b0c4  lea     rdx, [rbp+arg_10]
0x18001b0c8  mov     [rbp+arg_10], 0
0x18001b0d0  mov     ecx, r14d
0x18001b0d3  call    cs:__imp_EdpGetClipboardAccessDeniedData
0x18001b0d9  mov     rax, [rbp+arg_10]
0x18001b0dd  jmp     loc_18001B047
0x18001b0e2  mov     rax, [rax]
0x18001b0e5  jmp     loc_18001AFF7
0x18001b0ea  mov     [rax+10h], rbx
0x18001b0ee  mov     ecx, dword ptr [rbp+var_10]
0x18001b0f1  mov     [rax+8], ecx
0x18001b0f4  mov     ecx, dword ptr [rbp+var_10+4]
0x18001b0f7  mov     [rax+20h], ecx
0x18001b0fa  cmp     r14d, 0Eh
0x18001b0fe  jbe     loc_18001B3F4
0x18001b104  mov     eax, r14d
0x18001b107  sub     eax, 10h
0x18001b10a  jz      short loc_18001B115
0x18001b10c  sub     eax, 1
0x18001b10f  jnz     loc_18001B2F3
0x18001b115  mov     rcx, rbx; void *
0x18001b118  call    ?CreateLocalMemHandle@@YAPEAXPEAX@Z; CreateLocalMemHandle(void *)
0x18001b11d  mov     dword ptr [rdi+20h], 1
0x18001b124  mov     rbx, rax
0x18001b127  mov     [rdi+18h], rbx
0x18001b12b  test    rbx, rbx
0x18001b12e  jz      loc_18001B509
0x18001b134  mov     rax, cs:?gphn@@3PEAU_HANDLENODE@@EA; _HANDLENODE * gphn
0x18001b13b  mov     rsi, rbx
0x18001b13e  mov     [rdi], rax
0x18001b141  mov     cs:?gphn@@3PEAU_HANDLENODE@@EA, rdi; _HANDLENODE * gphn
0x18001b148  jmp     loc_18001B01E
0x18001b14d  xor     edi, edi
0x18001b14f  mov     [rbp+arg_10], rdi
0x18001b153  cmp     eax, 0Dh
0x18001b156  ja      loc_18001B520
0x18001b15c  mov     ecx, 2182h
0x18001b161  bt      ecx, eax
0x18001b164  jnb     loc_18001B520
0x18001b16a  mov     rcx, rbx; void *
0x18001b16d  call    ?CreateLocalMemHandle@@YAPEAXPEAX@Z; CreateLocalMemHandle(void *)
0x18001b172  mov     rsi, rax
0x18001b175  test    rax, rax
0x18001b178  jz      loc_18001B2EC
0x18001b17e  mov     rcx, rax; hMem
0x18001b181  call    cs:__imp_GlobalSize
0x18001b187  mov     r15, rax
0x18001b18a  test    eax, eax
0x18001b18c  jz      loc_18001B3E6
0x18001b192  mov     ecx, dword ptr [rbp+var_10]
0x18001b195  cmp     ecx, 1
0x18001b198  jz      loc_18001B460
0x18001b19e  cmp     ecx, 7
0x18001b1a1  jz      loc_18001B460
0x18001b1a7  xor     r12d, r12d
0x18001b1aa  cmp     ecx, 0Dh
0x18001b1ad  jz      loc_18001B460
0x18001b1b3  xor     r13d, r13d
0x18001b1b6  mov     eax, r14d
0x18001b1b9  sub     eax, 1
0x18001b1bc  jz      loc_18001B4CE
0x18001b1c2  sub     eax, 1
0x18001b1c5  jz      loc_18001B4A0
0x18001b1cb  sub     eax, 5
0x18001b1ce  jnz     loc_18001B32D
0x18001b1d4  lea     r13d, [rax+1]
0x18001b1d8  cmp     ecx, r13d
0x18001b1db  jz      loc_18001B450
0x18001b1e1  lea     edx, [rax+0Bh]; unsigned int
0x18001b1e4  mov     ecx, r12d; unsigned int
0x18001b1e7  call    ?GetClipboardCodePage@@YAIKK@Z; GetClipboardCodePage(ulong,ulong)
0x18001b1ec  mov     r13d, eax
0x18001b1ef  movsxd  r12, r15d
0x18001b1f2  xor     eax, eax
0x18001b1f4  shr     r12, 1
0x18001b1f7  mov     [rsp+50h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18001b1fc  mov     r9d, r12d; cchWideChar
0x18001b1ff  mov     [rsp+50h+lpDefaultChar], rax; lpDefaultChar
0x18001b204  mov     r8, rsi; lpWideCharStr
0x18001b207  mov     [rsp+50h+cbMultiByte], eax; cbMultiByte
0x18001b20b  xor     edx, edx; dwFlags
0x18001b20d  mov     ecx, r13d; CodePage
0x18001b210  mov     [rsp+50h+lpMultiByteStr], rax; lpMultiByteStr
0x18001b215  call    cs:__imp_WideCharToMultiByte
0x18001b21b  movsxd  r15, eax
0x18001b21e  test    eax, eax
0x18001b220  jz      loc_18001B3DD
0x18001b226  mov     rdx, r15; dwBytes
0x18001b229  mov     r8d, 42h ; 'B'; uFlags
0x18001b22f  mov     rcx, rdi; hMem
0x18001b232  call    cs:__imp_GlobalReAlloc
0x18001b238  test    rax, rax
0x18001b23b  jz      loc_18001B3DD
0x18001b241  mov     [rsp+50h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001b24a  mov     r9d, r12d; cchWideChar
0x18001b24d  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x18001b256  mov     r8, rsi; lpWideCharStr
0x18001b259  mov     [rsp+50h+cbMultiByte], r15d; cbMultiByte
0x18001b25e  xor     edx, edx; dwFlags
0x18001b260  mov     ecx, r13d; CodePage
0x18001b263  mov     [rsp+50h+lpMultiByteStr], rax; lpMultiByteStr
0x18001b268  mov     rdi, rax
0x18001b26b  call    cs:__imp_WideCharToMultiByte
0x18001b271  test    eax, eax
0x18001b273  jz      loc_18001B3DD
0x18001b279  mov     r13d, 1
0x18001b27f  test    rdi, rdi
0x18001b282  jnz     loc_18001B3C6
0x18001b288  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001b28f  call    cs:__imp_RtlEnterCriticalSection
0x18001b295  mov     eax, dword ptr [rbp+var_10+4]
0x18001b298  lea     r8, [rbp+arg_10]
0x18001b29c  mov     rdx, rbx
0x18001b29f  mov     dword ptr [rbp+arg_10], eax
0x18001b2a2  mov     ecx, r14d
0x18001b2a5  mov     dword ptr [rbp+arg_10+4], 0
0x18001b2ac  call    cs:__imp_NtUserSetClipboardData
0x18001b2b2  neg     eax
0x18001b2b4  sbb     rcx, rcx
0x18001b2b7  and     rbx, rcx
0x18001b2ba  lea     rcx, ?gcsClipboard@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001b2c1  call    cs:__imp_RtlLeaveCriticalSection
0x18001b2c7  test    rdi, rdi
0x18001b2ca  jz      short loc_18001B2D5
0x18001b2cc  mov     rcx, rdi; hMem
0x18001b2cf  call    cs:__imp_GlobalFree
0x18001b2d5  test    rsi, rsi
0x18001b2d8  jz      short loc_18001B2E3
0x18001b2da  mov     rcx, rsi; hMem
0x18001b2dd  call    cs:__imp_GlobalFree
0x18001b2e3  test    rbx, rbx
0x18001b2e6  jnz     loc_18001AFE3
0x18001b2ec  xor     eax, eax
0x18001b2ee  jmp     loc_18001B047
0x18001b2f3  sub     eax, 70h ; 'p'
0x18001b2f6  jz      loc_18001B115
0x18001b2fc  sub     eax, 1
0x18001b2ff  jz      loc_18001B127
0x18001b305  sub     eax, 1
0x18001b308  jz      loc_18001B4FB
0x18001b30e  cmp     eax, 0Bh
0x18001b311  jz      loc_18001B4ED
0x18001b317  cmp     dword ptr [rbp+var_10+4], esi
0x18001b31a  jz      loc_18001B127
0x18001b320  mov     rcx, rbx; void *
0x18001b323  call    ?CreateLocalMemHandle@@YAPEAXPEAX@Z; CreateLocalMemHandle(void *)
0x18001b328  jmp     loc_18001B124
0x18001b32d  sub     eax, 1
0x18001b330  jz      loc_18001B538
0x18001b336  cmp     eax, 5
0x18001b339  jnz     loc_18001B27F
0x18001b33f  lea     r13d, [rax-4]
0x18001b343  mov     edx, 1004h
0x18001b348  cmp     ecx, r13d
0x18001b34b  mov     ecx, r12d; unsigned int
0x18001b34e  jz      short loc_18001B353
0x18001b350  lea     edx, [rax+6]; unsigned int
0x18001b353  call    ?GetClipboardCodePage@@YAIKK@Z; GetClipboardCodePage(ulong,ulong)
0x18001b358  mov     r9d, r15d; cbMultiByte
0x18001b35b  mov     [rsp+50h+cbMultiByte], 0; cchWideChar
0x18001b363  mov     r8, rsi; lpMultiByteStr
0x18001b366  mov     [rsp+50h+lpMultiByteStr], 0; lpWideCharStr
0x18001b36f  mov     edx, r13d; dwFlags
0x18001b372  mov     ecx, eax; CodePage
0x18001b374  mov     r12d, eax
0x18001b377  call    cs:__imp_MultiByteToWideChar
0x18001b37d  movsxd  rbx, eax
0x18001b380  test    eax, eax
0x18001b382  jz      short loc_18001B3DD
0x18001b384  mov     rdx, rbx
0x18001b387  mov     r8d, 42h ; 'B'; uFlags
0x18001b38d  add     rdx, rdx; dwBytes
0x18001b390  mov     rcx, rdi; hMem
0x18001b393  call    cs:__imp_GlobalReAlloc
0x18001b399  test    rax, rax
0x18001b39c  jz      short loc_18001B3DD
0x18001b39e  mov     [rsp+50h+cbMultiByte], ebx; cchWideChar
0x18001b3a2  mov     r9d, r15d; cbMultiByte
0x18001b3a5  mov     r8, rsi; lpMultiByteStr
0x18001b3a8  mov     [rsp+50h+lpMultiByteStr], rax; lpWideCharStr
0x18001b3ad  mov     edx, r13d; dwFlags
0x18001b3b0  mov     ecx, r12d; CodePage
0x18001b3b3  mov     rdi, rax
0x18001b3b6  call    cs:__imp_MultiByteToWideChar
0x18001b3bc  test    eax, eax
0x18001b3be  jz      short loc_18001B3DD
0x18001b3c0  mov     r13d, 2
0x18001b3c6  mov     edx, r13d; unsigned int
0x18001b3c9  mov     rcx, rdi; hMem
0x18001b3cc  call    ?ConvertMemHandle@@YAPEAXPEAXI@Z; ConvertMemHandle(void *,uint)
0x18001b3d1  mov     rbx, rax
0x18001b3d4  test    rax, rax
0x18001b3d7  jnz     loc_18001B288
0x18001b3dd  mov     rcx, rdi; hMem
0x18001b3e0  call    cs:__imp_GlobalFree
0x18001b3e6  mov     rcx, rsi; hMem
0x18001b3e9  call    cs:__imp_GlobalFree
0x18001b3ef  jmp     loc_18001B2EC
0x18001b3f4  jz      loc_18001B4ED
0x18001b3fa  mov     eax, r14d
0x18001b3fd  sub     eax, 1
0x18001b400  jz      loc_18001B115
0x18001b406  sub     eax, 1
0x18001b409  jz      loc_18001B127
0x18001b40f  sub     eax, 1
0x18001b412  jz      loc_18001B4FB
0x18001b418  sub     eax, 4
0x18001b41b  jz      loc_18001B115
0x18001b421  sub     eax, 1
0x18001b424  jz      loc_18001B115
0x18001b42a  sub     eax, 1
0x18001b42d  jz      loc_18001B127
0x18001b433  cmp     eax, 4
0x18001b436  jnz     loc_18001B317
0x18001b43c  jmp     loc_18001B115
0x18001b441  movzx   eax, ax
0x18001b444  or      eax, 80070000h
0x18001b449  test    eax, eax
0x18001b44b  jmp     loc_18001B091
0x18001b450  mov     rdx, rdi; pDst
  ... truncated ...
```
