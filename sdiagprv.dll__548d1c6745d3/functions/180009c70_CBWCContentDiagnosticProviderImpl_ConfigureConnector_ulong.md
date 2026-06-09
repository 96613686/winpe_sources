# CBWCContentDiagnosticProviderImpl::ConfigureConnector(ulong)

- ea: `0x180009c70`
- end: `0x180009d9a`
- name: `?ConfigureConnector@CBWCContentDiagnosticProviderImpl@@AEAAJK@Z`
- size: `298`
- prototype: `__int64 __fastcall(CBWCContentDiagnosticProviderImpl *this, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009e60`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x180003400`
- `0x180009c70`
- `0x18000ce50`
- `0x18000cee0`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009cc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009cc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d74`

## string_xrefs

- `0x180009d45`: `CBWCContentDiagnosticProviderImpl::ConfigureConnector`
- `0x180009d5c`: `CBWCContentDiagnosticProviderImpl::ConfigureConnector`

## pseudocode

```c
__int64 __fastcall CBWCContentDiagnosticProviderImpl::ConfigureConnector(
        CBWCContentDiagnosticProviderImpl *this,
        __int64 a2)
{
  unsigned __int16 *v2; // rdi
  CBWCContentDiagnosticProviderImpl *v3; // rsi
  int v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rax
  HANDLE v7; // rax

  v2 = 0;
  v3 = this;
  if ( !*((_QWORD *)this + 2) || (this = (CBWCContentDiagnosticProviderImpl *)*((_QWORD *)this + 1)) == 0 )
  {
    v4 = -2147019873;
    goto LABEL_10;
  }
  v4 = CHttpConnector::put_Timeout(this, a2);
  if ( v4 >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x800u);
    v2 = v6;
    if ( !v6 )
    {
      v4 = -2147024882;
      goto LABEL_10;
    }
    memset_0(v6, 0, 0x800u);
    v4 = StringCchPrintfW(
           v2,
           0x400u,
           L"Windows Scripted Diagnostic Provider Client (Version %d.%d.%d.%d Build %d)",
           **((unsigned int **)v3 + 2),
           *(_DWORD *)(*((_QWORD *)v3 + 2) + 4LL),
           *(unsigned __int16 *)(*((_QWORD *)v3 + 2) + 8LL),
           *(unsigned __int16 *)(*((_QWORD *)v3 + 2) + 10LL),
           *(_DWORD *)(*((_QWORD *)v3 + 2) + 12LL));
    if ( v4 >= 0 )
      v4 = CHttpConnector::put_UserAgent(*((CHttpConnector **)v3 + 1), v2);
  }
  if ( v4 )
  {
LABEL_10:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(
        this,
        a2,
        "CBWCContentDiagnosticProviderImpl::ConfigureConnector",
        (unsigned int)v4);
    goto LABEL_14;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_DEBUG_SUCCESS,
      "CBWCContentDiagnosticProviderImpl::ConfigureConnector");
LABEL_14:
  if ( v2 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009c70  mov     [rsp+arg_0], rbx
0x180009c75  mov     [rsp+arg_8], rsi
0x180009c7a  push    rdi
0x180009c7b  sub     rsp, 40h
0x180009c7f  xor     edi, edi
0x180009c81  mov     rsi, rcx
0x180009c84  cmp     [rcx+10h], rdi
0x180009c88  jnz     short loc_180009C94
0x180009c8a  mov     ebx, 8007139Fh
0x180009c8f  jmp     loc_180009D39
0x180009c94  mov     rcx, [rcx+8]; this
0x180009c98  test    rcx, rcx
0x180009c9b  jz      short loc_180009C8A
0x180009c9d  call    ?put_Timeout@CHttpConnector@@QEAAJK@Z; CHttpConnector::put_Timeout(ulong)
0x180009ca2  mov     ebx, eax
0x180009ca4  test    eax, eax
0x180009ca6  js      loc_180009D35
0x180009cac  call    cs:__imp_GetProcessHeap
0x180009cb2  mov     ebx, 800h
0x180009cb7  mov     edx, 8; dwFlags
0x180009cbc  mov     rcx, rax; hHeap
0x180009cbf  mov     r8d, ebx; dwBytes
0x180009cc2  call    cs:__imp_HeapAlloc
0x180009cc8  mov     rdi, rax
0x180009ccb  test    rax, rax
0x180009cce  jnz     short loc_180009CD7
0x180009cd0  mov     ebx, 8007000Eh
0x180009cd5  jmp     short loc_180009D39
0x180009cd7  mov     r8, rbx; Size
0x180009cda  xor     edx, edx; Val
0x180009cdc  mov     rcx, rdi; void *
0x180009cdf  call    memset_0
0x180009ce4  mov     r9, [rsi+10h]
0x180009ce8  lea     r8, aWindowsScripte; "Windows Scripted Diagnostic Provider Cl"...
0x180009cef  movzx   ecx, word ptr [r9+0Ah]
0x180009cf4  mov     eax, [r9+0Ch]
0x180009cf8  movzx   edx, word ptr [r9+8]
0x180009cfd  mov     [rsp+48h+var_10], eax
0x180009d01  mov     eax, [r9+4]
0x180009d05  mov     r9d, [r9]
0x180009d08  mov     [rsp+48h+var_18], ecx
0x180009d0c  mov     rcx, rdi; unsigned __int16 *
0x180009d0f  mov     [rsp+48h+var_20], edx
0x180009d13  mov     edx, 400h; unsigned __int64
0x180009d18  mov     [rsp+48h+var_28], eax
0x180009d1c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009d21  mov     ebx, eax
0x180009d23  test    eax, eax
0x180009d25  js      short loc_180009D35
0x180009d27  mov     rcx, [rsi+8]; this
0x180009d2b  mov     rdx, rdi; unsigned __int16 *
0x180009d2e  call    ?put_UserAgent@CHttpConnector@@QEAAJPEBG@Z; CHttpConnector::put_UserAgent(ushort const *)
0x180009d33  mov     ebx, eax
0x180009d35  test    ebx, ebx
0x180009d37  jz      short loc_180009D53
0x180009d39  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180009d40  jz      short loc_180009D6F
0x180009d42  mov     r9d, ebx
0x180009d45  lea     r8, aCbwccontentdia; "CBWCContentDiagnosticProviderImpl::Conf"...
0x180009d4c  call    McTemplateU0sq_EventWriteTransfer
0x180009d51  jmp     short loc_180009D6F
0x180009d53  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180009d5a  jz      short loc_180009D6F
0x180009d5c  lea     r8, aCbwccontentdia; "CBWCContentDiagnosticProviderImpl::Conf"...
0x180009d63  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180009d6a  call    McTemplateU0s_EventWriteTransfer
0x180009d6f  test    rdi, rdi
0x180009d72  jz      short loc_180009D88
0x180009d74  call    cs:__imp_GetProcessHeap
0x180009d7a  mov     r8, rdi; lpMem
0x180009d7d  xor     edx, edx; dwFlags
0x180009d7f  mov     rcx, rax; hHeap
0x180009d82  call    cs:__imp_HeapFree
0x180009d88  mov     rsi, [rsp+48h+arg_8]
0x180009d8d  mov     eax, ebx
0x180009d8f  mov     rbx, [rsp+48h+arg_0]
0x180009d94  add     rsp, 40h
0x180009d98  pop     rdi
0x180009d99  retn
```
