# CHttpConnector::CreateInstance(CHttpConnector * *)

- ea: `0x18000c018`
- end: `0x18000c1cb`
- name: `?CreateInstance@CHttpConnector@@SAJPEAPEAV1@@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct _PROXY_LIST ***, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ab30`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180009b98`
- `0x18000c018`
- `0x18000c1d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0fc`
- `WINHTTP!WinHttpOpen` at `0x18000c0d6`
- `WINHTTP!WinHttpOpen` at `0x18000c0d6`

## string_xrefs

- `0x18000c04e`: `CHttpConnector::CreateInstance`
- `0x18000c13c`: `CHttpConnector::CreateInstance`
- `0x18000c153`: `CHttpConnector::CreateInstance`
- `0x18000c177`: `CHttpConnector::CreateInstance`
- `0x18000c195`: `CHttpConnector::CreateInstance`

## pseudocode

```c
__int64 __fastcall CHttpConnector::CreateInstance(struct _PROXY_LIST ***a1, int a2)
{
  unsigned int v3; // edi
  struct _PROXY_LIST **v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  struct _PROXY_LIST **v7; // rbx
  struct _PROXY_LIST *v8; // rax
  CHttpConnector *v9; // rcx
  signed int LastError; // eax

  if ( !a1 )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        0,
        a2,
        (unsigned int)"CHttpConnector::CreateInstance",
        -2147024809,
        (__int64)"HttpConnector");
    return v3;
  }
  *a1 = 0;
  v4 = (struct _PROXY_LIST **)operator new(0x40u);
  v7 = v4;
  if ( !v4 )
  {
    v3 = -2147024882;
    v7 = 0;
    goto LABEL_22;
  }
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  v4[3] = 0;
  v4[4] = 0;
  v4[5] = 0;
  v4[6] = 0;
  *((_DWORD *)v4 + 14) = 0;
  v8 = (struct _PROXY_LIST *)WinHttpOpen(L"CHttpConnector", 0, 0, 0, 0);
  *v7 = v8;
  if ( (unsigned __int64)v8 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
    {
      v3 = -2147467259;
      goto LABEL_15;
    }
  }
  else
  {
    v3 = CHttpConnector::InitializeProxyList(v9, v7 + 6);
    if ( (v3 & 0x80000000) == 0 )
    {
      *a1 = v7;
      goto LABEL_14;
    }
  }
  if ( v3 == -2147024882 )
  {
LABEL_22:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    {
LABEL_25:
      if ( !v7 )
        return v3;
LABEL_26:
      CHttpConnector::`scalar deleting destructor'((CHttpConnector *)v7, v5);
      return v3;
    }
    McTemplateU0s_EventWriteTransfer(v6, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY, "CHttpConnector::CreateInstance");
LABEL_24:
    if ( (v3 & 0x80000000) == 0 )
      return v3;
    goto LABEL_25;
  }
  if ( v3 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v6, v5, "CHttpConnector::CreateInstance", 2147942487LL);
    goto LABEL_26;
  }
LABEL_14:
  if ( v3 )
  {
LABEL_15:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v6, v5, "CHttpConnector::CreateInstance", v3);
    goto LABEL_24;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(v6, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CHttpConnector::CreateInstance");
  return v3;
}

```

## disassembly

```asm
0x18000c018  mov     [rsp+arg_0], rbx
0x18000c01d  mov     [rsp+arg_8], rsi
0x18000c022  push    rdi
0x18000c023  sub     rsp, 30h
0x18000c027  mov     rsi, rcx
0x18000c02a  test    rcx, rcx
0x18000c02d  jnz     short loc_18000C064
0x18000c02f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c036  mov     edi, 80070057h
0x18000c03b  jz      loc_18000C1B9
0x18000c041  lea     rax, aHttpconnector; "HttpConnector"
0x18000c048  mov     r9d, 80070057h
0x18000c04e  lea     r8, aChttpconnector_2; "CHttpConnector::CreateInstance"
0x18000c055  mov     qword ptr [rsp+38h+dwFlags], rax
0x18000c05a  call    McTemplateU0sqs_EventWriteTransfer
0x18000c05f  jmp     loc_18000C1B9
0x18000c064  mov     qword ptr [rcx], 0
0x18000c06b  mov     ecx, 40h ; '@'; Size
0x18000c070  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c075  mov     rbx, rax
0x18000c078  test    rax, rax
0x18000c07b  jz      loc_18000C185
0x18000c081  xor     r9d, r9d; pszProxyBypassW
0x18000c084  mov     qword ptr [rax], 0
0x18000c08b  xor     r8d, r8d; pszProxyW
0x18000c08e  mov     qword ptr [rax+8], 0
0x18000c096  xor     edx, edx; dwAccessType
0x18000c098  mov     qword ptr [rax+10h], 0
0x18000c0a0  lea     rcx, pszAgentW; "CHttpConnector"
0x18000c0a7  mov     qword ptr [rax+18h], 0
0x18000c0af  mov     qword ptr [rax+20h], 0
0x18000c0b7  mov     qword ptr [rax+28h], 0
0x18000c0bf  mov     qword ptr [rax+30h], 0
0x18000c0c7  mov     dword ptr [rax+38h], 0
0x18000c0ce  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000c0d6  call    cs:__imp_WinHttpOpen
0x18000c0dc  mov     [rbx], rax
0x18000c0df  dec     rax
0x18000c0e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c0e6  ja      short loc_18000C0FC
0x18000c0e8  lea     rdx, [rbx+30h]; struct _PROXY_LIST **
0x18000c0ec  call    ?InitializeProxyList@CHttpConnector@@AEAAJPEAPEAU_PROXY_LIST@@@Z; CHttpConnector::InitializeProxyList(_PROXY_LIST * *)
0x18000c0f1  mov     edi, eax
0x18000c0f3  test    eax, eax
0x18000c0f5  js      short loc_18000C11C
0x18000c0f7  mov     [rsi], rbx
0x18000c0fa  jmp     short loc_18000C12C
0x18000c0fc  call    cs:__imp_GetLastError
0x18000c102  mov     edi, eax
0x18000c104  test    eax, eax
0x18000c106  jle     short loc_18000C111
0x18000c108  movzx   edi, ax
0x18000c10b  or      edi, 80070000h
0x18000c111  test    edi, edi
0x18000c113  js      short loc_18000C11C
0x18000c115  mov     edi, 80004005h
0x18000c11a  jmp     short loc_18000C130
0x18000c11c  cmp     edi, 8007000Eh
0x18000c122  jz      short loc_18000C18C
0x18000c124  cmp     edi, 80070057h
0x18000c12a  jz      short loc_18000C168
0x18000c12c  test    edi, edi
0x18000c12e  jz      short loc_18000C14A
0x18000c130  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c137  jz      short loc_18000C1A8
0x18000c139  mov     r9d, edi
0x18000c13c  lea     r8, aChttpconnector_2; "CHttpConnector::CreateInstance"
0x18000c143  call    McTemplateU0sq_EventWriteTransfer
0x18000c148  jmp     short loc_18000C1A8
0x18000c14a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000c151  jz      short loc_18000C1B9
0x18000c153  lea     r8, aChttpconnector_2; "CHttpConnector::CreateInstance"
0x18000c15a  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000c161  call    McTemplateU0s_EventWriteTransfer
0x18000c166  jmp     short loc_18000C1B9
0x18000c168  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c16f  jz      short loc_18000C1B1
0x18000c171  mov     r9d, 80070057h
0x18000c177  lea     r8, aChttpconnector_2; "CHttpConnector::CreateInstance"
0x18000c17e  call    McTemplateU0sq_EventWriteTransfer
0x18000c183  jmp     short loc_18000C1B1
0x18000c185  mov     edi, 8007000Eh
0x18000c18a  xor     ebx, ebx
0x18000c18c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c193  jz      short loc_18000C1AC
0x18000c195  lea     r8, aChttpconnector_2; "CHttpConnector::CreateInstance"
0x18000c19c  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000c1a3  call    McTemplateU0s_EventWriteTransfer
0x18000c1a8  test    edi, edi
0x18000c1aa  jns     short loc_18000C1B9
0x18000c1ac  test    rbx, rbx
0x18000c1af  jz      short loc_18000C1B9
0x18000c1b1  mov     rcx, rbx; this
0x18000c1b4  call    ??_GCHttpConnector@@QEAAPEAXI@Z; CHttpConnector::`scalar deleting destructor'(uint)
0x18000c1b9  mov     rbx, [rsp+38h+arg_0]
0x18000c1be  mov     eax, edi
0x18000c1c0  mov     rsi, [rsp+38h+arg_8]
0x18000c1c5  add     rsp, 30h
0x18000c1c9  pop     rdi
0x18000c1ca  retn
```
