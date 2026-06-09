# CLocalContentDiagnosticProviderImpl::GetPreferredUILanguage(ushort * *)

- ea: `0x180008cdc`
- end: `0x180008eae`
- name: `?GetPreferredUILanguage@CLocalContentDiagnosticProviderImpl@@AEAAJPEAPEAG@Z`
- size: `466`
- prototype: `__int64 __fastcall(CLocalContentDiagnosticProviderImpl *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800087e0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800034e4`
- `0x180008cdc`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008db3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008db3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008df5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008df5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008da0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008de7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008da0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d5c`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180008d52`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180008e26`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180008d52`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180008e26`
- `OLEAUT32!__imp_SysAllocString` at `0x180008e39`
- `OLEAUT32!__imp_SysAllocString` at `0x180008e39`

## pseudocode

```c
__int64 __fastcall CLocalContentDiagnosticProviderImpl::GetPreferredUILanguage(
        CLocalContentDiagnosticProviderImpl *this,
        unsigned __int16 **a2)
{
  signed int v3; // ebx
  WCHAR *v4; // rdi
  signed int LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rax
  __int64 *v10; // rdx
  HANDLE v11; // rax
  unsigned __int16 *v13; // rax
  __int64 v14; // r9
  ULONG pcchLanguagesBuffer; // [rsp+50h] [rbp+8h] BYREF
  int v16; // [rsp+54h] [rbp+Ch]
  ULONG pulNumLanguages; // [rsp+58h] [rbp+10h] BYREF
  SIZE_T dwBytes; // [rsp+60h] [rbp+18h] BYREF

  v16 = HIDWORD(this);
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  dwBytes = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CLocalContentDiagnosticProviderImpl::GetPreferredUILanguage",
        -2147024809,
        (__int64)"Language");
    return (unsigned int)v3;
  }
  v4 = 0;
  *a2 = 0;
  if ( GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
  {
    v3 = ULongLongMult(pcchLanguagesBuffer, 2u, &dwBytes);
    if ( v3 < 0 )
      goto LABEL_22;
    ProcessHeap = GetProcessHeap();
    v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, dwBytes);
    v4 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, dwBytes);
      if ( !GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, v4, &pcchLanguagesBuffer) )
        goto LABEL_5;
      v3 = 0;
      v13 = SysAllocString(v4);
      *a2 = v13;
      if ( v13 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
          goto LABEL_15;
        v10 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_14:
        McTemplateU0s_EventWriteTransfer(v7, v10, "CLocalContentDiagnosticProviderImpl::GetPreferredUILanguage");
        goto LABEL_15;
      }
    }
    v3 = -2147024882;
LABEL_12:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_15;
    v10 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_14;
  }
LABEL_5:
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
  {
    v3 = -2147467259;
LABEL_24:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_15;
    v14 = (unsigned int)v3;
    goto LABEL_26;
  }
LABEL_22:
  if ( v3 == -2147024882 )
    goto LABEL_12;
  if ( v3 != -2147024809 )
    goto LABEL_24;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v14 = 2147942487LL;
LABEL_26:
    McTemplateU0sq_EventWriteTransfer(v7, v6, "CLocalContentDiagnosticProviderImpl::GetPreferredUILanguage", v14);
  }
LABEL_15:
  if ( v4 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008cdc  mov     rax, rsp
0x180008cdf  mov     [rax+8], rcx
0x180008ce3  push    rbx
0x180008ce4  push    rsi
0x180008ce5  push    rdi
0x180008ce6  sub     rsp, 30h
0x180008cea  mov     dword ptr [rax+10h], 0
0x180008cf1  mov     rsi, rdx
0x180008cf4  mov     dword ptr [rax+8], 0
0x180008cfb  mov     qword ptr [rax+18h], 0
0x180008d03  test    rdx, rdx
0x180008d06  jnz     short loc_180008D3D
0x180008d08  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008d0f  mov     ebx, 80070057h
0x180008d14  jz      loc_180008DFB
0x180008d1a  lea     rax, aLanguage; "Language"
0x180008d21  mov     r9d, 80070057h
0x180008d27  lea     r8, aClocalcontentd_0; "CLocalContentDiagnosticProviderImpl::Ge"...
0x180008d2e  mov     [rsp+48h+var_28], rax
0x180008d33  call    McTemplateU0sqs_EventWriteTransfer
0x180008d38  jmp     loc_180008DFB
0x180008d3d  xor     edi, edi
0x180008d3f  lea     r9, [rsp+48h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180008d44  mov     [rdx], rdi
0x180008d47  xor     r8d, r8d; pwszLanguagesBuffer
0x180008d4a  lea     rdx, [rsp+48h+pulNumLanguages]; pulNumLanguages
0x180008d4f  lea     ecx, [rdi+28h]; dwFlags
0x180008d52  call    cs:__imp_GetThreadPreferredUILanguages
0x180008d58  test    eax, eax
0x180008d5a  jnz     short loc_180008D83
0x180008d5c  call    cs:__imp_GetLastError
0x180008d62  mov     ebx, eax
0x180008d64  test    eax, eax
0x180008d66  jle     short loc_180008D71
0x180008d68  movzx   ebx, ax
0x180008d6b  or      ebx, 80070000h
0x180008d71  test    ebx, ebx
0x180008d73  js      loc_180008E60
0x180008d79  mov     ebx, 80004005h
0x180008d7e  jmp     loc_180008E78
0x180008d83  mov     ecx, [rsp+48h+pcchLanguagesBuffer]; unsigned __int64
0x180008d87  lea     r8, [rsp+48h+dwBytes]; unsigned __int64 *
0x180008d8c  mov     edx, 2; unsigned __int64
0x180008d91  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180008d96  mov     ebx, eax
0x180008d98  test    eax, eax
0x180008d9a  js      loc_180008E60
0x180008da0  call    cs:__imp_GetProcessHeap
0x180008da6  mov     r8, [rsp+48h+dwBytes]; dwBytes
0x180008dab  mov     edx, 8; dwFlags
0x180008db0  mov     rcx, rax; hHeap
0x180008db3  call    cs:__imp_HeapAlloc
0x180008db9  mov     rdi, rax
0x180008dbc  test    rax, rax
0x180008dbf  jnz     short loc_180008E05
0x180008dc1  mov     ebx, 8007000Eh
0x180008dc6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008dcd  jz      short loc_180008DE2
0x180008dcf  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180008dd6  lea     r8, aClocalcontentd_0; "CLocalContentDiagnosticProviderImpl::Ge"...
0x180008ddd  call    McTemplateU0s_EventWriteTransfer
0x180008de2  test    rdi, rdi
0x180008de5  jz      short loc_180008DFB
0x180008de7  call    cs:__imp_GetProcessHeap
0x180008ded  mov     r8, rdi; lpMem
0x180008df0  xor     edx, edx; dwFlags
0x180008df2  mov     rcx, rax; hHeap
0x180008df5  call    cs:__imp_HeapFree
0x180008dfb  mov     eax, ebx
0x180008dfd  add     rsp, 30h
0x180008e01  pop     rdi
0x180008e02  pop     rsi
0x180008e03  pop     rbx
0x180008e04  retn
0x180008e05  mov     r8, [rsp+48h+dwBytes]; Size
0x180008e0a  xor     edx, edx; Val
0x180008e0c  mov     rcx, rdi; void *
0x180008e0f  call    memset_0
0x180008e14  lea     r9, [rsp+48h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180008e19  mov     r8, rdi; pwszLanguagesBuffer
0x180008e1c  lea     rdx, [rsp+48h+pulNumLanguages]; pulNumLanguages
0x180008e21  mov     ecx, 28h ; '('; dwFlags
0x180008e26  call    cs:__imp_GetThreadPreferredUILanguages
0x180008e2c  test    eax, eax
0x180008e2e  jz      loc_180008D5C
0x180008e34  mov     rcx, rdi; psz
0x180008e37  xor     ebx, ebx
0x180008e39  call    cs:__imp_SysAllocString
0x180008e3f  mov     [rsi], rax
0x180008e42  test    rax, rax
0x180008e45  jz      loc_180008DC1
0x180008e4b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180008e52  jz      short loc_180008DE2
0x180008e54  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180008e5b  jmp     loc_180008DD6
0x180008e60  cmp     ebx, 8007000Eh
0x180008e66  jz      loc_180008DC6
0x180008e6c  cmp     ebx, 80070057h
0x180008e72  jz      short loc_180008E99
0x180008e74  test    ebx, ebx
0x180008e76  jz      short loc_180008E4B
0x180008e78  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008e7f  jz      loc_180008DE2
0x180008e85  mov     r9d, ebx
0x180008e88  lea     r8, aClocalcontentd_0; "CLocalContentDiagnosticProviderImpl::Ge"...
0x180008e8f  call    McTemplateU0sq_EventWriteTransfer
0x180008e94  jmp     loc_180008DE2
0x180008e99  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008ea0  jz      loc_180008DE2
0x180008ea6  mov     r9d, 80070057h
0x180008eac  jmp     short loc_180008E88
```
