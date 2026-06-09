# LocalContentProviderConfiguration::GetSzValue(HKEY__ * const,ushort const *,ushort * *)

- ea: `0x180009728`
- end: `0x18000993f`
- name: `?GetSzValue@LocalContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `535`
- prototype: `__int64 __fastcall(LocalContentProviderConfiguration *this, HKEY, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009948`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180009728`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009816`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009816`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000985c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000985c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000984e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000984e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800097e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000989b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800097e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000989b`

## string_xrefs

- `0x18000975a`: `ConfigurationKey`
- `0x180009767`: `LocalContentProviderConfiguration::GetSzValue`
- `0x1800097ac`: `LocalContentProviderConfiguration::GetSzValue`
- `0x180009832`: `LocalContentProviderConfiguration::GetSzValue`
- `0x1800098e5`: `LocalContentProviderConfiguration::GetSzValue`
- `0x180009903`: `LocalContentProviderConfiguration::GetSzValue`
- `0x18000992e`: `LocalContentProviderConfiguration::GetSzValue`

## pseudocode

```c
__int64 __fastcall LocalContentProviderConfiguration::GetSzValue(
        LocalContentProviderConfiguration *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  signed int v6; // ebx
  void *lpData; // rdi
  LSTATUS v8; // eax
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  void *v11; // rax
  HANDLE v12; // rax
  LSTATUS v14; // eax
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  int v16; // [rsp+74h] [rbp+1Ch]

  v16 = HIDWORD(a3);
  cbData = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"LocalContentProviderConfiguration::GetSzValue",
        -2147024809,
        (__int64)"ConfigurationKey");
    return (unsigned int)v6;
  }
  lpData = 0;
  if ( !a4 )
  {
    v6 = -2147024809;
    goto LABEL_6;
  }
  *a4 = 0;
  v8 = RegQueryValueExW(a2, L"LocalSystemIndex", 0, 0, 0, &cbData);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_24;
  v9 = cbData;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v9);
  lpData = v11;
  if ( !v11 )
  {
    v6 = -2147024882;
LABEL_14:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    {
LABEL_17:
      if ( lpData )
      {
        v12 = GetProcessHeap();
        HeapFree(v12, 0, lpData);
      }
      return (unsigned int)v6;
    }
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
      "LocalContentProviderConfiguration::GetSzValue");
LABEL_16:
    if ( v6 >= 0 )
      return (unsigned int)v6;
    goto LABEL_17;
  }
  memset_0(v11, 0, cbData);
  v14 = RegQueryValueExW(a2, L"LocalSystemIndex", 0, 0, (LPBYTE)lpData, &cbData);
  v6 = v14;
  if ( v14 > 0 )
    v6 = (unsigned __int16)v14 | 0x80070000;
  if ( v6 < 0 )
  {
LABEL_24:
    if ( v6 == -2147024882 )
      goto LABEL_14;
    if ( v6 == -2147024809 )
    {
LABEL_6:
      if ( a4 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          McTemplateU0sq_EventWriteTransfer(this, a2, "LocalContentProviderConfiguration::GetSzValue", 2147942487LL);
      }
      else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        McTemplateU0sqs_EventWriteTransfer(
          (_DWORD)this,
          (_DWORD)a2,
          (unsigned int)"LocalContentProviderConfiguration::GetSzValue",
          -2147024809,
          (__int64)"Value");
      }
      goto LABEL_17;
    }
  }
  else
  {
    *a4 = (unsigned __int16 *)lpData;
  }
  if ( v6 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(this, a2, "LocalContentProviderConfiguration::GetSzValue", (unsigned int)v6);
    goto LABEL_16;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_DEBUG_SUCCESS,
      "LocalContentProviderConfiguration::GetSzValue");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009728  mov     qword ptr [rsp+cbData], r8
0x18000972d  push    rbx
0x18000972e  push    rbp
0x18000972f  push    rsi
0x180009730  push    rdi
0x180009731  sub     rsp, 38h
0x180009735  mov     [rsp+58h+cbData], 0
0x18000973d  mov     rsi, r9
0x180009740  mov     rbp, rdx
0x180009743  test    rdx, rdx
0x180009746  jnz     short loc_18000977D
0x180009748  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000974f  mov     ebx, 80070057h
0x180009754  jz      loc_180009862
0x18000975a  lea     rax, aConfigurationk; "ConfigurationKey"
0x180009761  mov     r9d, 80070057h
0x180009767  lea     r8, aLocalcontentpr_1; "LocalContentProviderConfiguration::GetS"...
0x18000976e  mov     [rsp+58h+lpData], rax
0x180009773  call    McTemplateU0sqs_EventWriteTransfer
0x180009778  jmp     loc_180009862
0x18000977d  xor     edi, edi
0x18000977f  test    rsi, rsi
0x180009782  jnz     short loc_1800097C2
0x180009784  mov     ebx, 80070057h
0x180009789  test    rsi, rsi
0x18000978c  jnz     loc_18000991B
0x180009792  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180009799  jz      loc_180009849
0x18000979f  lea     rax, aValue; "Value"
0x1800097a6  mov     r9d, 80070057h
0x1800097ac  lea     r8, aLocalcontentpr_1; "LocalContentProviderConfiguration::GetS"...
0x1800097b3  mov     [rsp+58h+lpData], rax
0x1800097b8  call    McTemplateU0sqs_EventWriteTransfer
0x1800097bd  jmp     loc_180009849
0x1800097c2  lea     rax, [rsp+58h+cbData]
0x1800097c7  mov     [r9], rdi
0x1800097ca  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800097cf  lea     rdx, aLocalsystemind; "LocalSystemIndex"
0x1800097d6  xor     r9d, r9d; lpType
0x1800097d9  mov     [rsp+58h+lpData], rdi; lpData
0x1800097de  xor     r8d, r8d; lpReserved
0x1800097e1  mov     rcx, rbp; hKey
0x1800097e4  call    cs:__imp_RegQueryValueExW
0x1800097ea  mov     ebx, eax
0x1800097ec  test    eax, eax
0x1800097ee  jle     short loc_1800097F9
0x1800097f0  movzx   ebx, ax
0x1800097f3  or      ebx, 80070000h
0x1800097f9  test    ebx, ebx
0x1800097fb  js      loc_1800098B9
0x180009801  mov     ebx, [rsp+58h+cbData]
0x180009805  call    cs:__imp_GetProcessHeap
0x18000980b  mov     r8d, ebx; dwBytes
0x18000980e  mov     edx, 8; dwFlags
0x180009813  mov     rcx, rax; hHeap
0x180009816  call    cs:__imp_HeapAlloc
0x18000981c  mov     rdi, rax
0x18000981f  test    rax, rax
0x180009822  jnz     short loc_18000986D
0x180009824  mov     ebx, 8007000Eh
0x180009829  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180009830  jz      short loc_180009849
0x180009832  lea     r8, aLocalcontentpr_1; "LocalContentProviderConfiguration::GetS"...
0x180009839  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180009840  call    McTemplateU0s_EventWriteTransfer
0x180009845  test    ebx, ebx
0x180009847  jns     short loc_180009862
0x180009849  test    rdi, rdi
0x18000984c  jz      short loc_180009862
0x18000984e  call    cs:__imp_GetProcessHeap
0x180009854  mov     r8, rdi; lpMem
0x180009857  xor     edx, edx; dwFlags
0x180009859  mov     rcx, rax; hHeap
0x18000985c  call    cs:__imp_HeapFree
0x180009862  mov     eax, ebx
0x180009864  add     rsp, 38h
0x180009868  pop     rdi
0x180009869  pop     rsi
0x18000986a  pop     rbp
0x18000986b  pop     rbx
0x18000986c  retn
0x18000986d  mov     r8d, [rsp+58h+cbData]; Size
0x180009872  xor     edx, edx; Val
0x180009874  mov     rcx, rdi; void *
0x180009877  call    memset_0
0x18000987c  lea     rax, [rsp+58h+cbData]
0x180009881  xor     r9d, r9d; lpType
0x180009884  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180009889  lea     rdx, aLocalsystemind; "LocalSystemIndex"
0x180009890  xor     r8d, r8d; lpReserved
0x180009893  mov     [rsp+58h+lpData], rdi; lpData
0x180009898  mov     rcx, rbp; hKey
0x18000989b  call    cs:__imp_RegQueryValueExW
0x1800098a1  mov     ebx, eax
0x1800098a3  test    eax, eax
0x1800098a5  jle     short loc_1800098B0
0x1800098a7  movzx   ebx, ax
0x1800098aa  or      ebx, 80070000h
0x1800098b0  test    ebx, ebx
0x1800098b2  js      short loc_1800098B9
0x1800098b4  mov     [rsi], rdi
0x1800098b7  jmp     short loc_1800098D1
0x1800098b9  cmp     ebx, 8007000Eh
0x1800098bf  jz      loc_180009829
0x1800098c5  cmp     ebx, 80070057h
0x1800098cb  jz      loc_180009789
0x1800098d1  test    ebx, ebx
0x1800098d3  jz      short loc_1800098F6
0x1800098d5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800098dc  jz      loc_180009845
0x1800098e2  mov     r9d, ebx
0x1800098e5  lea     r8, aLocalcontentpr_1; "LocalContentProviderConfiguration::GetS"...
0x1800098ec  call    McTemplateU0sq_EventWriteTransfer
0x1800098f1  jmp     loc_180009845
0x1800098f6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800098fd  jz      loc_180009862
0x180009903  lea     r8, aLocalcontentpr_1; "LocalContentProviderConfiguration::GetS"...
0x18000990a  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180009911  call    McTemplateU0s_EventWriteTransfer
0x180009916  jmp     loc_180009862
0x18000991b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180009922  jz      loc_180009849
0x180009928  mov     r9d, 80070057h
0x18000992e  lea     r8, aLocalcontentpr_1; "LocalContentProviderConfiguration::GetS"...
0x180009935  call    McTemplateU0sq_EventWriteTransfer
0x18000993a  jmp     loc_180009849
```
