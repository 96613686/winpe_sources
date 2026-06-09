# CResourceLoader::LoadLocalizedResource(ushort *,ushort * *)

- ea: `0x180011d2c`
- end: `0x18001206a`
- name: `?LoadLocalizedResource@CResourceLoader@@QEAAJPEAGPEAPEAG@Z`
- size: `830`
- prototype: `__int64 __fastcall(CResourceLoader *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180012ef0`
- `0x1800131ac`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002840`
- `0x180007ce0`
- `0x180011d2c`
- `0x180012070`
- `0x1800122b8`
- `0x1800124a8`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180011efd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180011efd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011ec8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011ec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012020`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012039`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012052`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012020`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012039`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012052`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011eb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012012`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001202b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012044`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011eb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012012`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001202b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011e04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011e04`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180011e11`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180011e11`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180011f48`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180011f48`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180011e4e`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180011e4e`
- `OLEAUT32!__imp_SysAllocString` at `0x180011f2a`
- `OLEAUT32!__imp_SysAllocString` at `0x180011f2a`

## pseudocode

```c
__int64 __fastcall CResourceLoader::LoadLocalizedResource(
        CResourceLoader *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rsi
  wchar_t *v4; // r12
  int v6; // ebx
  OLECHAR *v7; // r15
  int v8; // eax
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *v10; // rdx
  signed int v11; // eax
  int v12; // r14d
  int v13; // eax
  HANDLE ProcessHeap; // rax
  OLECHAR *v15; // rax
  signed int LastError; // eax
  unsigned __int16 *v17; // rax
  signed int v18; // eax
  bool v19; // sf
  __int64 *v20; // rdx
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  WINBOOL Wow64Process; // [rsp+30h] [rbp-30h] BYREF
  STRSAFE_PCNZWCH pszSrc; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v27; // [rsp+40h] [rbp-20h] BYREF
  HINSTANCE hInstance; // [rsp+48h] [rbp-18h] BYREF
  PVOID OldValue; // [rsp+50h] [rbp-10h] BYREF
  int v31; // [rsp+A8h] [rbp+48h]
  UINT uID; // [rsp+B8h] [rbp+58h] BYREF

  v31 = (int)a2;
  v3 = 0;
  v4 = 0;
  pszSrc = 0;
  v27 = 0;
  uID = 0;
  hInstance = 0;
  Wow64Process = 0;
  OldValue = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CResourceLoader::LoadLocalizedResource",
        -2147024809,
        (__int64)"Value");
    return (unsigned int)v6;
  }
  v7 = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    goto LABEL_6;
  }
  *a3 = 0;
  v8 = CResourceLoader::ParseLocalizedResource(this, a2, (unsigned __int16 **)&pszSrc, (int *)&uID);
  v4 = (wchar_t *)pszSrc;
  v6 = v8;
  if ( v8 < 0 )
    goto LABEL_41;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) )
  {
    v12 = 0;
    if ( Wow64Process )
    {
      if ( !Wow64DisableWow64FsRedirection(&OldValue) )
        goto LABEL_11;
      v12 = 1;
    }
    LODWORD(pszSrc) = 0;
    v13 = SDiagPrviBuildPath(v4, v10, &v27);
    v3 = v27;
    v6 = v13;
    if ( v13 >= 0 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
        McTemplateU0z_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_LOAD_RESOURCE_START, v27);
      LODWORD(pszSrc) = 1;
      v6 = CResourceLoader::LoadModule(this, v3, &hInstance);
      if ( v6 >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v15 = (OLECHAR *)HeapAlloc(ProcessHeap, 8u, 0x800u);
        v7 = v15;
        if ( v15 )
        {
          memset_0(v15, 0, 0x800u);
          if ( LoadStringW(hInstance, uID, v7, 1024) )
          {
            v17 = SysAllocString(v7);
            *a3 = v17;
            if ( !v17 )
              v6 = -2147024882;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            if ( LastError >= 0 )
              LastError = -2147467259;
            v6 = LastError;
          }
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    if ( v12 && !Wow64RevertWow64FsRedirection(OldValue) )
    {
      v18 = GetLastError();
      v19 = v18 < 0;
      if ( v18 > 0 )
      {
        v18 = (unsigned __int16)v18 | 0x80070000;
        v19 = v18 < 0;
      }
      if ( v19 )
        v6 = v18;
    }
    if ( (_DWORD)pszSrc && (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
      McTemplateU0z_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_LOAD_RESOURCE_END, v3);
    goto LABEL_41;
  }
LABEL_11:
  v11 = GetLastError();
  v6 = v11;
  if ( v11 > 0 )
    v6 = (unsigned __int16)v11 | 0x80070000;
  if ( v6 >= 0 )
  {
    v6 = -2147467259;
    goto LABEL_44;
  }
LABEL_41:
  if ( v6 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v20 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
      goto LABEL_53;
    }
  }
  else
  {
    if ( v6 == -2147024809 )
    {
LABEL_6:
      if ( a3 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          McTemplateU0sq_EventWriteTransfer(this, a2, "CResourceLoader::LoadLocalizedResource", 2147942487LL);
      }
      else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        McTemplateU0sqs_EventWriteTransfer(
          (_DWORD)this,
          (_DWORD)a2,
          (unsigned int)"CResourceLoader::LoadLocalizedResource",
          -2147024809,
          (__int64)"LocalizedValue");
      }
      goto LABEL_54;
    }
    if ( v6 )
    {
LABEL_44:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 2) != 0 )
        McTemplateU0qzd_EventWriteTransfer((_DWORD)this, (_DWORD)a2, v6, v31, uID);
      v6 = -2147446780;
      goto LABEL_54;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    {
      v20 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_53:
      McTemplateU0s_EventWriteTransfer(this, v20, "CResourceLoader::LoadLocalizedResource");
    }
  }
LABEL_54:
  if ( v4 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v4);
  }
  if ( v3 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v3);
  }
  if ( v7 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011d2c  mov     [rsp-38h+arg_8], rdx
0x180011d31  mov     [rsp-38h+arg_0], rcx
0x180011d36  push    rbp
0x180011d37  push    rbx
0x180011d38  push    rsi
0x180011d39  push    r12
0x180011d3b  push    r13
0x180011d3d  push    r14
0x180011d3f  push    r15
0x180011d41  mov     rbp, rsp
0x180011d44  sub     rsp, 60h
0x180011d48  xor     esi, esi
0x180011d4a  xor     r12d, r12d
0x180011d4d  mov     [rbp+pszSrc], r12
0x180011d51  mov     r13, r8
0x180011d54  mov     [rbp+var_20], rsi
0x180011d58  mov     [rbp+uID], esi
0x180011d5b  mov     [rbp+hInstance], rsi
0x180011d5f  mov     [rbp+Wow64Process], esi
0x180011d62  mov     [rbp+OldValue], rsi
0x180011d66  test    rdx, rdx
0x180011d69  jnz     short loc_180011DA0
0x180011d6b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180011d72  mov     ebx, 80070057h
0x180011d77  jz      loc_180012058
0x180011d7d  lea     rax, aValue; "Value"
0x180011d84  mov     r9d, 80070057h
0x180011d8a  lea     r8, aCresourceloade_1; "CResourceLoader::LoadLocalizedResource"
0x180011d91  mov     [rsp+60h+var_40], rax
0x180011d96  call    McTemplateU0sqs_EventWriteTransfer
0x180011d9b  jmp     loc_180012058
0x180011da0  xor     r15d, r15d
0x180011da3  test    r13, r13
0x180011da6  jnz     short loc_180011DE6
0x180011da8  mov     ebx, 80070057h
0x180011dad  test    r13, r13
0x180011db0  jnz     loc_180011FD4
0x180011db6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180011dbd  jz      loc_18001200D
0x180011dc3  lea     rax, aLocalizedvalue; "LocalizedValue"
0x180011dca  mov     r9d, 80070057h
0x180011dd0  lea     r8, aCresourceloade_1; "CResourceLoader::LoadLocalizedResource"
0x180011dd7  mov     [rsp+60h+var_40], rax
0x180011ddc  call    McTemplateU0sqs_EventWriteTransfer
0x180011de1  jmp     loc_18001200D
0x180011de6  mov     [r8], rsi
0x180011de9  lea     r9, [rbp+uID]; int *
0x180011ded  lea     r8, [rbp+pszSrc]; unsigned __int16 **
0x180011df1  call    ?ParseLocalizedResource@CResourceLoader@@AEAAJPEAGPEAPEAGPEAJ@Z; CResourceLoader::ParseLocalizedResource(ushort *,ushort * *,long *)
0x180011df6  mov     r12, [rbp+pszSrc]
0x180011dfa  mov     ebx, eax
0x180011dfc  test    eax, eax
0x180011dfe  js      loc_180011F87
0x180011e04  call    cs:__imp_GetCurrentProcess
0x180011e0a  mov     rcx, rax; hProcess
0x180011e0d  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x180011e11  call    cs:__imp_IsWow64Process
0x180011e17  test    eax, eax
0x180011e19  jnz     short loc_180011E42
0x180011e1b  call    cs:__imp_GetLastError
0x180011e21  mov     ebx, eax
0x180011e23  test    eax, eax
0x180011e25  jle     short loc_180011E30
0x180011e27  movzx   ebx, ax
0x180011e2a  or      ebx, 80070000h
0x180011e30  test    ebx, ebx
0x180011e32  js      loc_180011F87
0x180011e38  mov     ebx, 80004005h
0x180011e3d  jmp     loc_180011F9F
0x180011e42  xor     r14d, r14d
0x180011e45  cmp     [rbp+Wow64Process], esi
0x180011e48  jz      short loc_180011E5E
0x180011e4a  lea     rcx, [rbp+OldValue]; OldValue
0x180011e4e  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180011e54  test    eax, eax
0x180011e56  jz      short loc_180011E1B
0x180011e58  mov     r14d, 1
0x180011e5e  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180011e62  mov     dword ptr [rbp+pszSrc], esi
0x180011e65  mov     rcx, r12; pszSrc
0x180011e68  call    ?SDiagPrviBuildPath@@YAJPEBG0PEAPEAG@Z; SDiagPrviBuildPath(ushort const *,ushort const *,ushort * *)
0x180011e6d  mov     rsi, [rbp+var_20]
0x180011e71  mov     ebx, eax
0x180011e73  test    eax, eax
0x180011e75  js      loc_180011F3F
0x180011e7b  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, r15b
0x180011e82  jge     short loc_180011E93
0x180011e84  mov     r8, rsi
0x180011e87  lea     rdx, SDIAGPRV_EVENT_PERF_LOAD_RESOURCE_START
0x180011e8e  call    McTemplateU0z_EventWriteTransfer
0x180011e93  mov     rcx, [rbp+arg_0]; this
0x180011e97  lea     r8, [rbp+hInstance]; HINSTANCE *
0x180011e9b  mov     rdx, rsi; unsigned __int16 *
0x180011e9e  mov     dword ptr [rbp+pszSrc], 1
0x180011ea5  call    ?LoadModule@CResourceLoader@@AEAAJPEBGPEAPEAUHINSTANCE__@@@Z; CResourceLoader::LoadModule(ushort const *,HINSTANCE__ * *)
0x180011eaa  mov     ebx, eax
0x180011eac  test    eax, eax
0x180011eae  js      loc_180011F3F
0x180011eb4  call    cs:__imp_GetProcessHeap
0x180011eba  mov     edx, 8; dwFlags
0x180011ebf  mov     r8d, 800h; dwBytes
0x180011ec5  mov     rcx, rax; hHeap
0x180011ec8  call    cs:__imp_HeapAlloc
0x180011ece  mov     r15, rax
0x180011ed1  test    rax, rax
0x180011ed4  jnz     short loc_180011EDD
0x180011ed6  mov     ebx, 8007000Eh
0x180011edb  jmp     short loc_180011F3F
0x180011edd  xor     edx, edx; Val
0x180011edf  mov     r8d, 800h; Size
0x180011ee5  mov     rcx, r15; void *
0x180011ee8  call    memset_0
0x180011eed  mov     edx, [rbp+uID]; uID
0x180011ef0  mov     r9d, 400h; cchBufferMax
0x180011ef6  mov     rcx, [rbp+hInstance]; hInstance
0x180011efa  mov     r8, r15; lpBuffer
0x180011efd  call    cs:__imp_LoadStringW
0x180011f03  test    eax, eax
0x180011f05  jnz     short loc_180011F27
0x180011f07  call    cs:__imp_GetLastError
0x180011f0d  test    eax, eax
0x180011f0f  jle     short loc_180011F19
0x180011f11  movzx   eax, ax
0x180011f14  or      eax, 80070000h
0x180011f19  mov     ebx, 80004005h
0x180011f1e  test    eax, eax
0x180011f20  cmovns  eax, ebx
0x180011f23  mov     ebx, eax
0x180011f25  jmp     short loc_180011F3F
0x180011f27  mov     rcx, r15; psz
0x180011f2a  call    cs:__imp_SysAllocString
0x180011f30  test    rax, rax
0x180011f33  mov     [r13+0], rax
0x180011f37  mov     eax, 8007000Eh
0x180011f3c  cmovz   ebx, eax
0x180011f3f  test    r14d, r14d
0x180011f42  jz      short loc_180011F69
0x180011f44  mov     rcx, [rbp+OldValue]; OlValue
0x180011f48  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180011f4e  test    eax, eax
0x180011f50  jnz     short loc_180011F69
0x180011f52  call    cs:__imp_GetLastError
0x180011f58  test    eax, eax
0x180011f5a  jle     short loc_180011F66
0x180011f5c  movzx   eax, ax
0x180011f5f  or      eax, 80070000h
0x180011f64  test    eax, eax
0x180011f66  cmovs   ebx, eax
0x180011f69  cmp     dword ptr [rbp+pszSrc], 0
0x180011f6d  jz      short loc_180011F87
0x180011f6f  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180011f76  jge     short loc_180011F87
0x180011f78  mov     r8, rsi
0x180011f7b  lea     rdx, SDIAGPRV_EVENT_PERF_LOAD_RESOURCE_END
0x180011f82  call    McTemplateU0z_EventWriteTransfer
0x180011f87  cmp     ebx, 8007000Eh
0x180011f8d  jz      short loc_180011FF1
0x180011f8f  cmp     ebx, 80070057h
0x180011f95  jz      loc_180011DAD
0x180011f9b  test    ebx, ebx
0x180011f9d  jz      short loc_180011FC2
0x180011f9f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 2
0x180011fa6  jz      short loc_180011FBB
0x180011fa8  mov     eax, [rbp+uID]
0x180011fab  mov     r8d, ebx
0x180011fae  mov     r9, [rbp+arg_8]
0x180011fb2  mov     dword ptr [rsp+60h+var_40], eax
0x180011fb6  call    McTemplateU0qzd_EventWriteTransfer
0x180011fbb  mov     ebx, 80009004h
0x180011fc0  jmp     short loc_18001200D
0x180011fc2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180011fc9  jz      short loc_18001200D
0x180011fcb  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180011fd2  jmp     short loc_180012001
0x180011fd4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180011fdb  jz      short loc_18001200D
0x180011fdd  mov     r9d, 80070057h
0x180011fe3  lea     r8, aCresourceloade_1; "CResourceLoader::LoadLocalizedResource"
0x180011fea  call    McTemplateU0sq_EventWriteTransfer
0x180011fef  jmp     short loc_18001200D
0x180011ff1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180011ff8  jz      short loc_18001200D
0x180011ffa  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180012001  lea     r8, aCresourceloade_1; "CResourceLoader::LoadLocalizedResource"
0x180012008  call    McTemplateU0s_EventWriteTransfer
0x18001200d  test    r12, r12
0x180012010  jz      short loc_180012026
0x180012012  call    cs:__imp_GetProcessHeap
0x180012018  mov     r8, r12; lpMem
0x18001201b  xor     edx, edx; dwFlags
0x18001201d  mov     rcx, rax; hHeap
0x180012020  call    cs:__imp_HeapFree
0x180012026  test    rsi, rsi
0x180012029  jz      short loc_18001203F
0x18001202b  call    cs:__imp_GetProcessHeap
0x180012031  mov     r8, rsi; lpMem
0x180012034  xor     edx, edx; dwFlags
0x180012036  mov     rcx, rax; hHeap
0x180012039  call    cs:__imp_HeapFree
0x18001203f  test    r15, r15
0x180012042  jz      short loc_180012058
0x180012044  call    cs:__imp_GetProcessHeap
0x18001204a  mov     r8, r15; lpMem
0x18001204d  xor     edx, edx; dwFlags
0x18001204f  mov     rcx, rax; hHeap
0x180012052  call    cs:__imp_HeapFree
0x180012058  mov     eax, ebx
0x18001205a  add     rsp, 60h
0x18001205e  pop     r15
0x180012060  pop     r14
0x180012062  pop     r13
0x180012064  pop     r12
0x180012066  pop     rsi
0x180012067  pop     rbx
0x180012068  pop     rbp
0x180012069  retn
```
