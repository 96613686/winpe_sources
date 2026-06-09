# CBWCRequest::get_RequestUrlPath(ushort * *)

- ea: `0x18000f654`
- end: `0x18000f9e9`
- name: `?get_RequestUrlPath@CBWCRequest@@QEBAJPEAPEAG@Z`
- size: `917`
- prototype: `__int64 __fastcall(CBWCRequest *this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009e60`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002ac4`
- `0x180003400`
- `0x1800034e4`
- `0x18000f654`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f7ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f897`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f7ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f897`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f7f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f80c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f825`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f7f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f80c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f825`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f797`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f7e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f7fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f817`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f797`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f7e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f7fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f817`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f881`
- `SHLWAPI!UrlEscapeW` at `0x18000f871`
- `SHLWAPI!UrlEscapeW` at `0x18000f871`

## string_xrefs

- `0x18000f6aa`: `CBWCRequest::get_RequestUrlPath`
- `0x18000f7d4`: `CBWCRequest::get_RequestUrlPath`
- `0x18000f9aa`: `CBWCRequest::get_RequestUrlPath`
- `0x18000f69d`: `RequestUrlPath`
- `0x18000f744`: `BWCContentProviderConfiguration::GetRemoteServerVersion`
- `0x18000f763`: `BWCContentProviderConfiguration::GetRemoteServerVersion`
- `0x18000f958`: `BWCContentProviderConfiguration::GetRemoteServerVersion`
- `0x18000f96f`: `BWCContentProviderConfiguration::GetRemoteServerVersion`
- `0x18000f6ec`: `BWCContentProviderConfiguration::GetRemoteServerResponseId`

## pseudocode

```c
__int64 __fastcall CBWCRequest::get_RequestUrlPath(CBWCRequest *this, unsigned __int16 **a2)
{
  void *v2; // r14
  HRESULT v5; // ebx
  WCHAR *v6; // rsi
  unsigned __int16 *v7; // rdi
  unsigned int v8; // eax
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rax
  __int64 *v11; // rdx
  HANDLE v12; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  HANDLE v16; // rax
  unsigned __int16 *v17; // rax
  __int64 v18; // r9
  __int64 v19; // r9
  LPVOID lpMem; // [rsp+80h] [rbp-38h] BYREF
  DWORD pcchEscaped; // [rsp+C8h] [rbp+10h] BYREF
  int v22; // [rsp+D0h] [rbp+18h]
  SIZE_T dwBytes; // [rsp+D8h] [rbp+20h] BYREF

  v2 = 0;
  dwBytes = 0;
  pcchEscaped = 2048;
  lpMem = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CBWCRequest::get_RequestUrlPath",
        -2147024809,
        (__int64)"RequestUrlPath");
    return (unsigned int)v5;
  }
  v6 = 0;
  v7 = 0;
  *a2 = 0;
  if ( *(_QWORD *)this )
  {
    v22 = *(_DWORD *)(*(_QWORD *)this + 32LL);
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(
        this,
        SDIAGPRV_EVENT_DEBUG_SUCCESS,
        "BWCContentProviderConfiguration::GetRemoteServerResponseId");
    v8 = SDiagPrviCopyPWSTR(*(const unsigned __int16 **)(*(_QWORD *)this + 24LL), (unsigned __int16 **)&lpMem);
    v5 = v8;
    v2 = lpMem;
    if ( v8 == -2147024882 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0s_EventWriteTransfer(
          this,
          SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
          "BWCContentProviderConfiguration::GetRemoteServerVersion");
    }
    else if ( v8 == -2147024809 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(
          this,
          a2,
          "BWCContentProviderConfiguration::GetRemoteServerVersion",
          2147942487LL);
    }
    else
    {
      if ( v8 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          McTemplateU0sq_EventWriteTransfer(this, a2, "BWCContentProviderConfiguration::GetRemoteServerVersion", v8);
        if ( v5 < 0 )
          goto LABEL_38;
      }
      else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      {
        McTemplateU0s_EventWriteTransfer(
          this,
          SDIAGPRV_EVENT_DEBUG_SUCCESS,
          "BWCContentProviderConfiguration::GetRemoteServerVersion");
      }
      v5 = ULongLongMult(0x800u, 2u, &dwBytes);
      if ( v5 >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, dwBytes);
        v6 = v10;
        if ( !v10 )
        {
LABEL_19:
          v5 = -2147024882;
          goto LABEL_20;
        }
        memset_0(v10, 0, dwBytes);
        v5 = UrlEscapeW(*(PCWSTR *)(*((_QWORD *)this + 1) + 40LL), v6, &pcchEscaped, 0x3000u);
        if ( v5 >= 0 )
        {
          v16 = GetProcessHeap();
          v17 = (unsigned __int16 *)HeapAlloc(v16, 8u, dwBytes);
          v7 = v17;
          if ( !v17 )
            goto LABEL_19;
          memset_0(v17, 0, dwBytes);
          v18 = *((_QWORD *)this + 1);
          v5 = StringCchPrintfW(
                 v7,
                 0x800u,
                 L"%s/%d/%d.%d/%d.%d.%d.%d.0.%d.%d/%d/%s",
                 v2,
                 v22,
                 *((_DWORD *)this + 4),
                 *((_DWORD *)this + 5),
                 *(_DWORD *)v18,
                 *(_DWORD *)(v18 + 4),
                 *(_DWORD *)(v18 + 12),
                 *(unsigned __int8 *)(v18 + 22),
                 *(unsigned __int16 *)(v18 + 8),
                 *(unsigned __int16 *)(v18 + 10),
                 *(_DWORD *)(v18 + 16),
                 v6);
          if ( v5 >= 0 )
            v5 = SDiagPrviCopyPWSTR(v7, a2);
        }
      }
    }
LABEL_38:
    if ( v5 != -2147024882 )
    {
      if ( v5 == -2147024809 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_23;
        v19 = 2147942487LL;
        goto LABEL_43;
      }
      if ( v5 )
        goto LABEL_41;
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
        goto LABEL_23;
      v11 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_22:
      McTemplateU0s_EventWriteTransfer(this, v11, "CBWCRequest::get_RequestUrlPath");
      goto LABEL_23;
    }
LABEL_20:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_23;
    v11 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_22;
  }
  v5 = -2147019873;
LABEL_41:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v19 = (unsigned int)v5;
LABEL_43:
    McTemplateU0sq_EventWriteTransfer(this, a2, "CBWCRequest::get_RequestUrlPath", v19);
  }
LABEL_23:
  if ( v7 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v7);
  }
  if ( v6 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v6);
  }
  if ( v2 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v2);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f654  mov     rax, rsp
0x18000f657  mov     [rax+8], rbx
0x18000f65b  push    rsi
0x18000f65c  push    rdi
0x18000f65d  push    r12
0x18000f65f  push    r14
0x18000f661  push    r15
0x18000f663  sub     rsp, 90h
0x18000f66a  xor     r14d, r14d
0x18000f66d  mov     qword ptr [rax+20h], 0
0x18000f675  mov     dword ptr [rax+10h], 800h
0x18000f67c  mov     r15, rdx
0x18000f67f  mov     [rax-38h], r14
0x18000f683  mov     r12, rcx
0x18000f686  test    rdx, rdx
0x18000f689  jnz     short loc_18000F6C0
0x18000f68b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000f692  mov     ebx, 80070057h
0x18000f697  jz      loc_18000F82B
0x18000f69d  lea     rax, aRequesturlpath; "RequestUrlPath"
0x18000f6a4  mov     r9d, 80070057h
0x18000f6aa  lea     r8, aCbwcrequestGet_2; "CBWCRequest::get_RequestUrlPath"
0x18000f6b1  mov     [rsp+0B8h+var_98], rax
0x18000f6b6  call    McTemplateU0sqs_EventWriteTransfer
0x18000f6bb  jmp     loc_18000F82B
0x18000f6c0  xor     esi, esi
0x18000f6c2  xor     edi, edi
0x18000f6c4  mov     [rdx], rsi
0x18000f6c7  mov     rax, [rcx]
0x18000f6ca  test    rax, rax
0x18000f6cd  jnz     short loc_18000F6D9
0x18000f6cf  mov     ebx, 8007139Fh
0x18000f6d4  jmp     loc_18000F99A
0x18000f6d9  mov     eax, [rax+20h]
0x18000f6dc  mov     [rsp+0B8h+arg_10], eax
0x18000f6e3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000f6ea  jz      short loc_18000F6FF
0x18000f6ec  lea     r8, aBwccontentprov_3; "BWCContentProviderConfiguration::GetRem"...
0x18000f6f3  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000f6fa  call    McTemplateU0s_EventWriteTransfer
0x18000f6ff  mov     rcx, [r12]
0x18000f703  lea     rdx, [rsp+0B8h+lpMem]; unsigned __int16 **
0x18000f70b  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18000f70f  call    ?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z; SDiagPrviCopyPWSTR(ushort const *,ushort * *)
0x18000f714  mov     ebx, eax
0x18000f716  mov     r14, [rsp+0B8h+lpMem]
0x18000f71e  cmp     eax, 8007000Eh
0x18000f723  jz      loc_18000F966
0x18000f729  cmp     eax, 80070057h
0x18000f72e  jz      loc_18000F949
0x18000f734  test    eax, eax
0x18000f736  jz      short loc_18000F75A
0x18000f738  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000f73f  jz      short loc_18000F750
0x18000f741  mov     r9d, eax
0x18000f744  lea     r8, aBwccontentprov_2; "BWCContentProviderConfiguration::GetRem"...
0x18000f74b  call    McTemplateU0sq_EventWriteTransfer
0x18000f750  test    ebx, ebx
0x18000f752  js      loc_18000F982
0x18000f758  jmp     short loc_18000F776
0x18000f75a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000f761  jz      short loc_18000F776
0x18000f763  lea     r8, aBwccontentprov_2; "BWCContentProviderConfiguration::GetRem"...
0x18000f76a  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000f771  call    McTemplateU0s_EventWriteTransfer
0x18000f776  lea     r8, [rsp+0B8h+dwBytes]; unsigned __int64 *
0x18000f77e  mov     edx, 2; unsigned __int64
0x18000f783  mov     ecx, 800h; unsigned __int64
0x18000f788  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000f78d  mov     ebx, eax
0x18000f78f  test    eax, eax
0x18000f791  js      loc_18000F982
0x18000f797  call    cs:__imp_GetProcessHeap
0x18000f79d  mov     r8, [rsp+0B8h+dwBytes]; dwBytes
0x18000f7a5  mov     edx, 8; dwFlags
0x18000f7aa  mov     rcx, rax; hHeap
0x18000f7ad  call    cs:__imp_HeapAlloc
0x18000f7b3  mov     rsi, rax
0x18000f7b6  test    rax, rax
0x18000f7b9  jnz     loc_18000F845
0x18000f7bf  mov     ebx, 8007000Eh
0x18000f7c4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000f7cb  jz      short loc_18000F7E0
0x18000f7cd  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000f7d4  lea     r8, aCbwcrequestGet_2; "CBWCRequest::get_RequestUrlPath"
0x18000f7db  call    McTemplateU0s_EventWriteTransfer
0x18000f7e0  test    rdi, rdi
0x18000f7e3  jz      short loc_18000F7F9
0x18000f7e5  call    cs:__imp_GetProcessHeap
0x18000f7eb  mov     r8, rdi; lpMem
0x18000f7ee  xor     edx, edx; dwFlags
0x18000f7f0  mov     rcx, rax; hHeap
0x18000f7f3  call    cs:__imp_HeapFree
0x18000f7f9  test    rsi, rsi
0x18000f7fc  jz      short loc_18000F812
0x18000f7fe  call    cs:__imp_GetProcessHeap
0x18000f804  mov     r8, rsi; lpMem
0x18000f807  xor     edx, edx; dwFlags
0x18000f809  mov     rcx, rax; hHeap
0x18000f80c  call    cs:__imp_HeapFree
0x18000f812  test    r14, r14
0x18000f815  jz      short loc_18000F82B
0x18000f817  call    cs:__imp_GetProcessHeap
0x18000f81d  mov     r8, r14; lpMem
0x18000f820  xor     edx, edx; dwFlags
0x18000f822  mov     rcx, rax; hHeap
0x18000f825  call    cs:__imp_HeapFree
0x18000f82b  mov     eax, ebx
0x18000f82d  mov     rbx, [rsp+0B8h+arg_0]
0x18000f835  add     rsp, 90h
0x18000f83c  pop     r15
0x18000f83e  pop     r14
0x18000f840  pop     r12
0x18000f842  pop     rdi
0x18000f843  pop     rsi
0x18000f844  retn
0x18000f845  mov     r8, [rsp+0B8h+dwBytes]; Size
0x18000f84d  xor     edx, edx; Val
0x18000f84f  mov     rcx, rsi; void *
0x18000f852  call    memset_0
0x18000f857  mov     rcx, [r12+8]
0x18000f85c  lea     r8, [rsp+0B8h+pcchEscaped]; pcchEscaped
0x18000f864  mov     r9d, 3000h; dwFlags
0x18000f86a  mov     rdx, rsi; pszEscaped
0x18000f86d  mov     rcx, [rcx+28h]; pszUrl
0x18000f871  call    cs:__imp_UrlEscapeW
0x18000f877  mov     ebx, eax
0x18000f879  test    eax, eax
0x18000f87b  js      loc_18000F982
0x18000f881  call    cs:__imp_GetProcessHeap
0x18000f887  mov     r8, [rsp+0B8h+dwBytes]; dwBytes
0x18000f88f  mov     edx, 8; dwFlags
0x18000f894  mov     rcx, rax; hHeap
0x18000f897  call    cs:__imp_HeapAlloc
0x18000f89d  mov     rdi, rax
0x18000f8a0  test    rax, rax
0x18000f8a3  jz      loc_18000F7BF
0x18000f8a9  mov     r8, [rsp+0B8h+dwBytes]; Size
0x18000f8b1  xor     edx, edx; Val
0x18000f8b3  mov     rcx, rax; void *
0x18000f8b6  call    memset_0
0x18000f8bb  mov     r9, [r12+8]
0x18000f8c0  mov     [rsp+0B8h+var_48], rsi
0x18000f8c5  movzx   ecx, word ptr [r9+0Ah]
0x18000f8ca  mov     eax, [r9+10h]
0x18000f8ce  movzx   edx, word ptr [r9+8]
0x18000f8d3  movzx   r8d, byte ptr [r9+16h]
0x18000f8d8  mov     [rsp+0B8h+var_50], eax
0x18000f8dc  mov     eax, [r9+0Ch]
0x18000f8e0  mov     [rsp+0B8h+var_58], ecx
0x18000f8e4  mov     rcx, rdi; unsigned __int16 *
0x18000f8e7  mov     [rsp+0B8h+var_60], edx
0x18000f8eb  mov     edx, 800h; unsigned __int64
0x18000f8f0  mov     [rsp+0B8h+var_68], r8d
0x18000f8f5  lea     r8, aSDDDDDDD0DDDS; "%s/%d/%d.%d/%d.%d.%d.%d.0.%d.%d/%d/%s"
0x18000f8fc  mov     [rsp+0B8h+var_70], eax
0x18000f900  mov     eax, [r9+4]
0x18000f904  mov     [rsp+0B8h+var_78], eax
0x18000f908  mov     eax, [r9]
0x18000f90b  mov     r9, r14
0x18000f90e  mov     [rsp+0B8h+var_80], eax
0x18000f912  mov     eax, [r12+14h]
0x18000f917  mov     [rsp+0B8h+var_88], eax
0x18000f91b  mov     eax, [r12+10h]
0x18000f920  mov     [rsp+0B8h+var_90], eax
0x18000f924  mov     eax, [rsp+0B8h+arg_10]
0x18000f92b  mov     dword ptr [rsp+0B8h+var_98], eax
0x18000f92f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f934  mov     ebx, eax
0x18000f936  test    eax, eax
0x18000f938  js      short loc_18000F982
0x18000f93a  mov     rdx, r15; unsigned __int16 **
0x18000f93d  mov     rcx, rdi; unsigned __int16 *
0x18000f940  call    ?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z; SDiagPrviCopyPWSTR(ushort const *,ushort * *)
0x18000f945  mov     ebx, eax
0x18000f947  jmp     short loc_18000F982
0x18000f949  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000f950  jz      short loc_18000F982
0x18000f952  mov     r9d, 80070057h
0x18000f958  lea     r8, aBwccontentprov_2; "BWCContentProviderConfiguration::GetRem"...
0x18000f95f  call    McTemplateU0sq_EventWriteTransfer
0x18000f964  jmp     short loc_18000F982
0x18000f966  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000f96d  jz      short loc_18000F982
0x18000f96f  lea     r8, aBwccontentprov_2; "BWCContentProviderConfiguration::GetRem"...
0x18000f976  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000f97d  call    McTemplateU0s_EventWriteTransfer
0x18000f982  cmp     ebx, 8007000Eh
0x18000f988  jz      loc_18000F7C4
0x18000f98e  cmp     ebx, 80070057h
0x18000f994  jz      short loc_18000F9D4
0x18000f996  test    ebx, ebx
0x18000f998  jz      short loc_18000F9BB
0x18000f99a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000f9a1  jz      loc_18000F7E0
0x18000f9a7  mov     r9d, ebx
0x18000f9aa  lea     r8, aCbwcrequestGet_2; "CBWCRequest::get_RequestUrlPath"
0x18000f9b1  call    McTemplateU0sq_EventWriteTransfer
0x18000f9b6  jmp     loc_18000F7E0
0x18000f9bb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000f9c2  jz      loc_18000F7E0
0x18000f9c8  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000f9cf  jmp     loc_18000F7D4
0x18000f9d4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000f9db  jz      loc_18000F7E0
0x18000f9e1  mov     r9d, 80070057h
0x18000f9e7  jmp     short loc_18000F9AA
```
