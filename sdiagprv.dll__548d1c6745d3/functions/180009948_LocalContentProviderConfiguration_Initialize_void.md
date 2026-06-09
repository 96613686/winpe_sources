# LocalContentProviderConfiguration::Initialize(void)

- ea: `0x180009948`
- end: `0x180009a86`
- name: `?Initialize@LocalContentProviderConfiguration@@AEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(LocalContentProviderConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800087e0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x180009728`
- `0x180009948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800099fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800099fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800099ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800099ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000997e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000997e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009a73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009a73`

## string_xrefs

- `0x1800099af`: `LocalContentProviderConfiguration::GetConfigurationKey`
- `0x1800099ce`: `LocalContentProviderConfiguration::GetConfigurationKey`
- `0x180009a45`: `LocalContentProviderConfiguration::GetConfigurationKey`
- `0x180009a24`: `LocalContentProviderConfiguration::Initialize`
- `0x180009a5d`: `LocalContentProviderConfiguration::Initialize`

## pseudocode

```c
__int64 __fastcall LocalContentProviderConfiguration::Initialize(LocalContentProviderConfiguration *this)
{
  LSTATUS v2; // eax
  __int64 v3; // rdx
  LocalContentProviderConfiguration *v4; // rcx
  const unsigned __int16 *v5; // r8
  unsigned int SzValue; // ebx
  unsigned __int16 **v7; // rbx
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\ScriptedDiagnosticsProvider",
         0,
         0x20019u,
         &hKey);
  SzValue = v2;
  if ( v2 > 0 )
    SzValue = (unsigned __int16)v2 | 0x80070000;
  if ( SzValue == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_20;
    McTemplateU0sq_EventWriteTransfer(v4, v3, "LocalContentProviderConfiguration::GetConfigurationKey", 2147942487LL);
    goto LABEL_18;
  }
  if ( SzValue )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v4, v3, "LocalContentProviderConfiguration::GetConfigurationKey", SzValue);
    if ( (SzValue & 0x80000000) != 0 )
      goto LABEL_18;
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
  {
    McTemplateU0s_EventWriteTransfer(
      v4,
      SDIAGPRV_EVENT_DEBUG_SUCCESS,
      "LocalContentProviderConfiguration::GetConfigurationKey");
  }
  v7 = (unsigned __int16 **)((char *)this + 8);
  v8 = (void *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    *v7 = 0;
  }
  SzValue = LocalContentProviderConfiguration::GetSzValue(v4, hKey, v5, v7);
  if ( !SzValue )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(
        v4,
        SDIAGPRV_EVENT_DEBUG_SUCCESS,
        "LocalContentProviderConfiguration::Initialize");
    goto LABEL_20;
  }
LABEL_18:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(v4, v3, "LocalContentProviderConfiguration::Initialize", SzValue);
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  return SzValue;
}

```

## disassembly

```asm
0x180009948  mov     r11, rsp
0x18000994b  mov     [r11+8], rbx
0x18000994f  push    rdi
0x180009950  sub     rsp, 30h
0x180009954  mov     rdi, rcx
0x180009957  mov     qword ptr [r11+10h], 0
0x18000995f  lea     rax, [r11+10h]
0x180009963  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000996a  mov     r9d, 20019h; samDesired
0x180009970  mov     [r11-18h], rax
0x180009974  xor     r8d, r8d; ulOptions
0x180009977  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\ScriptedD"...
0x18000997e  call    cs:__imp_RegOpenKeyExW
0x180009984  mov     ebx, eax
0x180009986  test    eax, eax
0x180009988  jle     short loc_180009993
0x18000998a  movzx   ebx, ax
0x18000998d  or      ebx, 80070000h
0x180009993  cmp     ebx, 80070057h
0x180009999  jz      loc_180009A39
0x18000999f  test    ebx, ebx
0x1800099a1  jz      short loc_1800099C5
0x1800099a3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800099aa  jz      short loc_1800099BB
0x1800099ac  mov     r9d, ebx
0x1800099af  lea     r8, aLocalcontentpr_3; "LocalContentProviderConfiguration::GetC"...
0x1800099b6  call    McTemplateU0sq_EventWriteTransfer
0x1800099bb  test    ebx, ebx
0x1800099bd  js      loc_180009A51
0x1800099c3  jmp     short loc_1800099E1
0x1800099c5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800099cc  jz      short loc_1800099E1
0x1800099ce  lea     r8, aLocalcontentpr_3; "LocalContentProviderConfiguration::GetC"...
0x1800099d5  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800099dc  call    McTemplateU0s_EventWriteTransfer
0x1800099e1  lea     rbx, [rdi+8]
0x1800099e5  mov     rdi, [rbx]
0x1800099e8  test    rdi, rdi
0x1800099eb  jz      short loc_180009A08
0x1800099ed  call    cs:__imp_GetProcessHeap
0x1800099f3  mov     r8, rdi; lpMem
0x1800099f6  xor     edx, edx; dwFlags
0x1800099f8  mov     rcx, rax; hHeap
0x1800099fb  call    cs:__imp_HeapFree
0x180009a01  mov     qword ptr [rbx], 0
0x180009a08  mov     rdx, [rsp+38h+hKey]; HKEY
0x180009a0d  mov     r9, rbx; unsigned __int16 **
0x180009a10  call    ?GetSzValue@LocalContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAPEAG@Z; LocalContentProviderConfiguration::GetSzValue(HKEY__ * const,ushort const *,ushort * *)
0x180009a15  mov     ebx, eax
0x180009a17  test    eax, eax
0x180009a19  jnz     short loc_180009A51
0x180009a1b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180009a22  jz      short loc_180009A69
0x180009a24  lea     r8, aLocalcontentpr_2; "LocalContentProviderConfiguration::Init"...
0x180009a2b  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180009a32  call    McTemplateU0s_EventWriteTransfer
0x180009a37  jmp     short loc_180009A69
0x180009a39  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180009a40  jz      short loc_180009A69
0x180009a42  mov     r9d, ebx
0x180009a45  lea     r8, aLocalcontentpr_3; "LocalContentProviderConfiguration::GetC"...
0x180009a4c  call    McTemplateU0sq_EventWriteTransfer
0x180009a51  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180009a58  jz      short loc_180009A69
0x180009a5a  mov     r9d, ebx
0x180009a5d  lea     r8, aLocalcontentpr_2; "LocalContentProviderConfiguration::Init"...
0x180009a64  call    McTemplateU0sq_EventWriteTransfer
0x180009a69  mov     rcx, [rsp+38h+hKey]; hKey
0x180009a6e  test    rcx, rcx
0x180009a71  jz      short loc_180009A79
0x180009a73  call    cs:__imp_RegCloseKey
0x180009a79  mov     eax, ebx
0x180009a7b  mov     rbx, [rsp+38h+arg_0]
0x180009a80  add     rsp, 30h
0x180009a84  pop     rdi
0x180009a85  retn
```
