# CBWCContentDiagnosticProviderImpl::GetPreferredUILanguages(void)

- ea: `0x18000a964`
- end: `0x18000ab1c`
- name: `?GetPreferredUILanguages@CBWCContentDiagnosticProviderImpl@@AEAAJXZ`
- size: `440`
- prototype: `__int64 __fastcall(CBWCContentDiagnosticProviderImpl *this, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009e60`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800034e4`
- `0x18000a964`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aa24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aa24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9d0`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000a9c6`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000aa99`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000a9c6`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000aa99`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000aaad`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000aaad`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a9a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a9a2`

## pseudocode

```c
__int64 __fastcall CBWCContentDiagnosticProviderImpl::GetPreferredUILanguages(
        CBWCContentDiagnosticProviderImpl *this,
        __int64 a2)
{
  WCHAR *v2; // rsi
  __int64 v4; // rcx
  signed int v5; // ebx
  OLECHAR *v6; // rcx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rax
  __int64 *v10; // rdx
  HANDLE v11; // rax
  ULONG pcchLanguagesBuffer; // [rsp+40h] [rbp+20h] BYREF
  ULONG pulNumLanguages; // [rsp+48h] [rbp+28h] BYREF
  SIZE_T dwBytes; // [rsp+50h] [rbp+30h] BYREF

  v2 = 0;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  v4 = *((_QWORD *)this + 2);
  dwBytes = 0;
  if ( !v4 )
  {
    v5 = -2147019873;
    goto LABEL_26;
  }
  v6 = *(OLECHAR **)(v4 + 24);
  if ( v6 )
  {
    SysFreeString(v6);
    *(_QWORD *)(*((_QWORD *)this + 2) + 24LL) = 0;
  }
  *(_DWORD *)(*((_QWORD *)this + 2) + 32LL) = 0;
  if ( GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
  {
    v5 = ULongLongMult(pcchLanguagesBuffer, 2u, &dwBytes);
    if ( v5 < 0 )
      goto LABEL_24;
    ProcessHeap = GetProcessHeap();
    v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, dwBytes);
    v2 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, dwBytes);
      if ( !GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, v2, &pcchLanguagesBuffer) )
        goto LABEL_6;
      *(_QWORD *)(*((_QWORD *)this + 2) + 24LL) = SysAllocStringLen(v2, pcchLanguagesBuffer);
      v4 = *((_QWORD *)this + 2);
      if ( *(_QWORD *)(v4 + 24) )
      {
        v5 = 0;
        *(_DWORD *)(v4 + 32) = pulNumLanguages;
LABEL_22:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
          goto LABEL_16;
        v10 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_15:
        McTemplateU0s_EventWriteTransfer(v4, v10, "CBWCContentDiagnosticProviderImpl::GetPreferredUILanguages");
        goto LABEL_16;
      }
    }
    v5 = -2147024882;
LABEL_13:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_16;
    v10 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_15;
  }
LABEL_6:
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
    v5 = -2147467259;
    goto LABEL_26;
  }
LABEL_24:
  if ( v5 == -2147024882 )
    goto LABEL_13;
  if ( !v5 )
    goto LABEL_22;
LABEL_26:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(
      v4,
      a2,
      "CBWCContentDiagnosticProviderImpl::GetPreferredUILanguages",
      (unsigned int)v5);
LABEL_16:
  if ( v2 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v2);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a964  mov     [rsp-18h+arg_18], rbx
0x18000a969  push    rbp
0x18000a96a  push    rsi
0x18000a96b  push    rdi
0x18000a96c  mov     rbp, rsp
0x18000a96f  sub     rsp, 20h
0x18000a973  xor     esi, esi
0x18000a975  mov     [rbp+pulNumLanguages], 0
0x18000a97c  mov     rdi, rcx
0x18000a97f  mov     [rbp+pcchLanguagesBuffer], esi
0x18000a982  mov     rcx, [rcx+10h]
0x18000a986  mov     [rbp+dwBytes], rsi
0x18000a98a  test    rcx, rcx
0x18000a98d  jnz     short loc_18000A999
0x18000a98f  mov     ebx, 8007139Fh
0x18000a994  jmp     loc_18000AAFB
0x18000a999  mov     rcx, [rcx+18h]; bstrString
0x18000a99d  test    rcx, rcx
0x18000a9a0  jz      short loc_18000A9B0
0x18000a9a2  call    cs:__imp_SysFreeString
0x18000a9a8  mov     rax, [rdi+10h]
0x18000a9ac  mov     [rax+18h], rsi
0x18000a9b0  mov     rax, [rdi+10h]
0x18000a9b4  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18000a9b8  xor     r8d, r8d; pwszLanguagesBuffer
0x18000a9bb  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x18000a9bf  mov     [rax+20h], esi
0x18000a9c2  lea     ecx, [r8+28h]; dwFlags
0x18000a9c6  call    cs:__imp_GetThreadPreferredUILanguages
0x18000a9cc  test    eax, eax
0x18000a9ce  jnz     short loc_18000A9F7
0x18000a9d0  call    cs:__imp_GetLastError
0x18000a9d6  mov     ebx, eax
0x18000a9d8  test    eax, eax
0x18000a9da  jle     short loc_18000A9E5
0x18000a9dc  movzx   ebx, ax
0x18000a9df  or      ebx, 80070000h
0x18000a9e5  test    ebx, ebx
0x18000a9e7  js      loc_18000AAEB
0x18000a9ed  mov     ebx, 80004005h
0x18000a9f2  jmp     loc_18000AAFB
0x18000a9f7  mov     ecx, [rbp+pcchLanguagesBuffer]; unsigned __int64
0x18000a9fa  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18000a9fe  mov     edx, 2; unsigned __int64
0x18000aa03  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000aa08  mov     ebx, eax
0x18000aa0a  test    eax, eax
0x18000aa0c  js      loc_18000AAEB
0x18000aa12  call    cs:__imp_GetProcessHeap
0x18000aa18  mov     r8, [rbp+dwBytes]; dwBytes
0x18000aa1c  mov     edx, 8; dwFlags
0x18000aa21  mov     rcx, rax; hHeap
0x18000aa24  call    cs:__imp_HeapAlloc
0x18000aa2a  mov     rsi, rax
0x18000aa2d  test    rax, rax
0x18000aa30  jnz     short loc_18000AA7B
0x18000aa32  mov     ebx, 8007000Eh
0x18000aa37  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000aa3e  jz      short loc_18000AA53
0x18000aa40  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000aa47  lea     r8, aCbwccontentdia_1; "CBWCContentDiagnosticProviderImpl::GetP"...
0x18000aa4e  call    McTemplateU0s_EventWriteTransfer
0x18000aa53  test    rsi, rsi
0x18000aa56  jz      short loc_18000AA6C
0x18000aa58  call    cs:__imp_GetProcessHeap
0x18000aa5e  mov     r8, rsi; lpMem
0x18000aa61  xor     edx, edx; dwFlags
0x18000aa63  mov     rcx, rax; hHeap
0x18000aa66  call    cs:__imp_HeapFree
0x18000aa6c  mov     eax, ebx
0x18000aa6e  mov     rbx, [rsp+20h+arg_18]
0x18000aa73  add     rsp, 20h
0x18000aa77  pop     rdi
0x18000aa78  pop     rsi
0x18000aa79  pop     rbp
0x18000aa7a  retn
0x18000aa7b  mov     r8, [rbp+dwBytes]; Size
0x18000aa7f  xor     edx, edx; Val
0x18000aa81  mov     rcx, rsi; void *
0x18000aa84  call    memset_0
0x18000aa89  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18000aa8d  mov     r8, rsi; pwszLanguagesBuffer
0x18000aa90  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x18000aa94  mov     ecx, 28h ; '('; dwFlags
0x18000aa99  call    cs:__imp_GetThreadPreferredUILanguages
0x18000aa9f  test    eax, eax
0x18000aaa1  jz      loc_18000A9D0
0x18000aaa7  mov     edx, [rbp+pcchLanguagesBuffer]; ui
0x18000aaaa  mov     rcx, rsi; strIn
0x18000aaad  call    cs:__imp_SysAllocStringLen
0x18000aab3  mov     rcx, [rdi+10h]
0x18000aab7  mov     [rcx+18h], rax
0x18000aabb  mov     rcx, [rdi+10h]
0x18000aabf  cmp     qword ptr [rcx+18h], 0
0x18000aac4  jz      loc_18000AA32
0x18000aaca  mov     eax, [rbp+pulNumLanguages]
0x18000aacd  xor     ebx, ebx
0x18000aacf  mov     [rcx+20h], eax
0x18000aad2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000aad9  jz      loc_18000AA53
0x18000aadf  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000aae6  jmp     loc_18000AA47
0x18000aaeb  cmp     ebx, 8007000Eh
0x18000aaf1  jz      loc_18000AA37
0x18000aaf7  test    ebx, ebx
0x18000aaf9  jz      short loc_18000AAD2
0x18000aafb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000ab02  jz      loc_18000AA53
0x18000ab08  mov     r9d, ebx
0x18000ab0b  lea     r8, aCbwccontentdia_1; "CBWCContentDiagnosticProviderImpl::GetP"...
0x18000ab12  call    McTemplateU0sq_EventWriteTransfer
0x18000ab17  jmp     loc_18000AA53
```
