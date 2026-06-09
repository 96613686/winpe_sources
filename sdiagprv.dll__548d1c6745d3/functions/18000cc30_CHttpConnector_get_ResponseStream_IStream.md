# CHttpConnector::get_ResponseStream(IStream * *)

- ea: `0x18000cc30`
- end: `0x18000ce49`
- name: `?get_ResponseStream@CHttpConnector@@QEAAJPEAPEAUIStream@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(HINTERNET *this, struct IStream **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000ac18`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18000cc30`
- `0x1800180be`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ccd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ccd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdad`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000ccad`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000ccad`
- `WINHTTP!WinHttpReadData` at `0x18000cd0c`
- `WINHTTP!WinHttpReadData` at `0x18000cd0c`

## pseudocode

```c
__int64 __fastcall CHttpConnector::get_ResponseStream(HINTERNET *this, struct IStream **a2)
{
  void *v2; // rdi
  int v5; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  int v8; // ebx
  __int64 v9; // r9
  signed int LastError; // eax
  HANDLE v11; // rax
  DWORD dwNumberOfBytesRead; // [rsp+78h] [rbp+38h] BYREF
  int v14; // [rsp+80h] [rbp+40h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  ppstm = 0;
  dwNumberOfBytesRead = 0;
  v14 = 0;
  if ( a2 )
  {
    if ( this[2] )
    {
      v5 = CreateStreamOnHGlobal(0, 1, &ppstm);
      if ( v5 >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v7 = HeapAlloc(ProcessHeap, 8u, 0x1000u);
        v2 = v7;
        if ( !v7 )
        {
          v5 = -2147024882;
          goto LABEL_21;
        }
        v8 = 0;
        memset_0(v7, 0, 0x1000u);
        while ( WinHttpReadData(this[2], v2, 0x1000u, &dwNumberOfBytesRead) )
        {
          if ( !dwNumberOfBytesRead )
          {
            if ( !v8 )
            {
              v5 = -2147024637;
              goto LABEL_21;
            }
LABEL_17:
            v5 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
            if ( v5 >= 0 )
              v5 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, struct IStream **))ppstm)(ppstm, &IID_IStream, a2);
            goto LABEL_19;
          }
          v5 = (*(__int64 (__fastcall **)(LPSTREAM, void *, _QWORD, int *))(*(_QWORD *)ppstm + 32LL))(
                 ppstm,
                 v2,
                 dwNumberOfBytesRead,
                 &v14);
          if ( v5 < 0 )
            goto LABEL_19;
          if ( !dwNumberOfBytesRead )
            goto LABEL_17;
          v8 = 1;
        }
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 >= 0 )
        {
          v5 = -2147467259;
          goto LABEL_21;
        }
      }
LABEL_19:
      if ( v5 == -2147024809 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_32;
        v9 = 2147942487LL;
        goto LABEL_31;
      }
      if ( !v5 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
          McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CHttpConnector::get_ResponseStream");
        goto LABEL_32;
      }
    }
    else
    {
      v5 = -2147019873;
    }
LABEL_21:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_32;
    v9 = (unsigned int)v5;
LABEL_31:
    McTemplateU0sq_EventWriteTransfer(this, a2, "CHttpConnector::get_ResponseStream", v9);
    goto LABEL_32;
  }
  v5 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    return (unsigned int)v5;
  McTemplateU0sqs_EventWriteTransfer(
    (_DWORD)this,
    0,
    (unsigned int)"CHttpConnector::get_ResponseStream",
    -2147024809,
    (__int64)"Stream");
LABEL_32:
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
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
0x18000cc30  push    rbp
0x18000cc32  push    rbx
0x18000cc33  push    rsi
0x18000cc34  push    rdi
0x18000cc35  push    r14
0x18000cc37  mov     rbp, rsp
0x18000cc3a  sub     rsp, 40h
0x18000cc3e  xor     edi, edi
0x18000cc40  mov     [rbp+ppstm], 0
0x18000cc48  mov     [rbp+dwNumberOfBytesRead], edi
0x18000cc4b  mov     r14, rdx
0x18000cc4e  mov     [rbp+arg_10], edi
0x18000cc51  mov     rsi, rcx
0x18000cc54  mov     [rbp+var_10], rdi
0x18000cc58  test    rdx, rdx
0x18000cc5b  jnz     short loc_18000CC92
0x18000cc5d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000cc64  mov     ebx, 80070057h
0x18000cc69  jz      loc_18000CE3C
0x18000cc6f  lea     rax, aStream; "Stream"
0x18000cc76  mov     r9d, 80070057h
0x18000cc7c  lea     r8, aChttpconnector_8; "CHttpConnector::get_ResponseStream"
0x18000cc83  mov     [rsp+40h+var_20], rax
0x18000cc88  call    McTemplateU0sqs_EventWriteTransfer
0x18000cc8d  jmp     loc_18000CE06
0x18000cc92  cmp     [rcx+10h], rdi
0x18000cc96  jnz     short loc_18000CCA2
0x18000cc98  mov     ebx, 8007139Fh
0x18000cc9d  jmp     loc_18000CD9F
0x18000cca2  lea     r8, [rbp+ppstm]; ppstm
0x18000cca6  mov     edx, 1; fDeleteOnRelease
0x18000ccab  xor     ecx, ecx; hGlobal
0x18000ccad  call    cs:__imp_CreateStreamOnHGlobal
0x18000ccb3  mov     ebx, eax
0x18000ccb5  test    eax, eax
0x18000ccb7  js      loc_18000CD93
0x18000ccbd  call    cs:__imp_GetProcessHeap
0x18000ccc3  mov     edx, 8; dwFlags
0x18000ccc8  mov     r8d, 1000h; dwBytes
0x18000ccce  mov     rcx, rax; hHeap
0x18000ccd1  call    cs:__imp_HeapAlloc
0x18000ccd7  mov     rdi, rax
0x18000ccda  test    rax, rax
0x18000ccdd  jnz     short loc_18000CCE9
0x18000ccdf  mov     ebx, 8007000Eh
0x18000cce4  jmp     loc_18000CD9F
0x18000cce9  xor     ebx, ebx
0x18000cceb  xor     edx, edx; Val
0x18000cced  mov     r8d, 1000h; Size
0x18000ccf3  mov     rcx, rdi; void *
0x18000ccf6  call    memset_0
0x18000ccfb  mov     rcx, [rsi+10h]; hRequest
0x18000ccff  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18000cd03  mov     r8d, 1000h; dwNumberOfBytesToRead
0x18000cd09  mov     rdx, rdi; lpBuffer
0x18000cd0c  call    cs:__imp_WinHttpReadData
0x18000cd12  test    eax, eax
0x18000cd14  jz      loc_18000CDAD
0x18000cd1a  mov     r8d, [rbp+dwNumberOfBytesRead]
0x18000cd1e  test    r8d, r8d
0x18000cd21  jz      short loc_18000CD4D
0x18000cd23  mov     rcx, [rbp+ppstm]
0x18000cd27  lea     r9, [rbp+arg_10]
0x18000cd2b  mov     rdx, rdi
0x18000cd2e  mov     rax, [rcx]
0x18000cd31  mov     rax, [rax+20h]
0x18000cd35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd3a  mov     ebx, eax
0x18000cd3c  test    eax, eax
0x18000cd3e  js      short loc_18000CD93
0x18000cd40  cmp     [rbp+dwNumberOfBytesRead], 0
0x18000cd44  jbe     short loc_18000CD58
0x18000cd46  mov     ebx, 1
0x18000cd4b  jmp     short loc_18000CCFB
0x18000cd4d  test    ebx, ebx
0x18000cd4f  jnz     short loc_18000CD58
0x18000cd51  mov     ebx, 80070103h
0x18000cd56  jmp     short loc_18000CD9F
0x18000cd58  mov     rcx, [rbp+ppstm]
0x18000cd5c  xor     r9d, r9d
0x18000cd5f  mov     rdx, [rbp+var_10]
0x18000cd63  xor     r8d, r8d
0x18000cd66  mov     rax, [rcx]
0x18000cd69  mov     rax, [rax+28h]
0x18000cd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd72  mov     ebx, eax
0x18000cd74  test    eax, eax
0x18000cd76  js      short loc_18000CD93
0x18000cd78  mov     rcx, [rbp+ppstm]
0x18000cd7c  lea     rdx, IID_IStream
0x18000cd83  mov     r8, r14
0x18000cd86  mov     rax, [rcx]
0x18000cd89  mov     rax, [rax]
0x18000cd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd91  mov     ebx, eax
0x18000cd93  cmp     ebx, 80070057h
0x18000cd99  jz      short loc_18000CDEB
0x18000cd9b  test    ebx, ebx
0x18000cd9d  jz      short loc_18000CDCD
0x18000cd9f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000cda6  jz      short loc_18000CE06
0x18000cda8  mov     r9d, ebx
0x18000cdab  jmp     short loc_18000CDFA
0x18000cdad  call    cs:__imp_GetLastError
0x18000cdb3  mov     ebx, eax
0x18000cdb5  test    eax, eax
0x18000cdb7  jle     short loc_18000CDC2
0x18000cdb9  movzx   ebx, ax
0x18000cdbc  or      ebx, 80070000h
0x18000cdc2  test    ebx, ebx
0x18000cdc4  js      short loc_18000CD93
0x18000cdc6  mov     ebx, 80004005h
0x18000cdcb  jmp     short loc_18000CD9F
0x18000cdcd  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000cdd4  jz      short loc_18000CE06
0x18000cdd6  lea     r8, aChttpconnector_8; "CHttpConnector::get_ResponseStream"
0x18000cddd  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000cde4  call    McTemplateU0s_EventWriteTransfer
0x18000cde9  jmp     short loc_18000CE06
0x18000cdeb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000cdf2  jz      short loc_18000CE06
0x18000cdf4  mov     r9d, 80070057h
0x18000cdfa  lea     r8, aChttpconnector_8; "CHttpConnector::get_ResponseStream"
0x18000ce01  call    McTemplateU0sq_EventWriteTransfer
0x18000ce06  mov     rcx, [rbp+ppstm]
0x18000ce0a  test    rcx, rcx
0x18000ce0d  jz      short loc_18000CE23
0x18000ce0f  mov     rax, [rcx]
0x18000ce12  mov     rax, [rax+10h]
0x18000ce16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce1b  mov     [rbp+ppstm], 0
0x18000ce23  test    rdi, rdi
0x18000ce26  jz      short loc_18000CE3C
0x18000ce28  call    cs:__imp_GetProcessHeap
0x18000ce2e  mov     r8, rdi; lpMem
0x18000ce31  xor     edx, edx; dwFlags
0x18000ce33  mov     rcx, rax; hHeap
0x18000ce36  call    cs:__imp_HeapFree
0x18000ce3c  mov     eax, ebx
0x18000ce3e  add     rsp, 40h
0x18000ce42  pop     r14
0x18000ce44  pop     rdi
0x18000ce45  pop     rsi
0x18000ce46  pop     rbx
0x18000ce47  pop     rbp
0x18000ce48  retn
```
