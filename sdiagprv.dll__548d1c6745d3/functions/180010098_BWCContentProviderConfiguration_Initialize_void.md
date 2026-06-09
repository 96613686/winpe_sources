# BWCContentProviderConfiguration::Initialize(void)

- ea: `0x180010098`
- end: `0x1800102a2`
- name: `?Initialize@BWCContentProviderConfiguration@@AEAAJXZ`
- size: `522`
- prototype: `__int64 __fastcall(BWCContentProviderConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fac8`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x18000fc2c`
- `0x18000fe60`
- `0x180010098`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001014f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010194`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800101d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001014f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010194`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800101d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010186`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800101c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010186`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800101c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800100d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001028a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001028a`

## string_xrefs

- `0x180010103`: `BWCContentProviderConfiguration::GetConfigurationKey`
- `0x180010122`: `BWCContentProviderConfiguration::GetConfigurationKey`
- `0x18001025c`: `BWCContentProviderConfiguration::GetConfigurationKey`
- `0x18001023b`: `BWCContentProviderConfiguration::Initialize`
- `0x180010274`: `BWCContentProviderConfiguration::Initialize`

## pseudocode

```c
__int64 __fastcall BWCContentProviderConfiguration::Initialize(BWCContentProviderConfiguration *this)
{
  LSTATUS v2; // eax
  __int64 v3; // rdx
  BWCContentProviderConfiguration *v4; // rcx
  int SzValue; // ebx
  void *v6; // rsi
  HANDLE ProcessHeap; // rax
  void *v8; // rsi
  HANDLE v9; // rax
  void *v10; // rsi
  HANDLE v11; // rax
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
      goto LABEL_29;
    McTemplateU0sq_EventWriteTransfer(v4, v3, "BWCContentProviderConfiguration::GetConfigurationKey", 2147942487LL);
    goto LABEL_27;
  }
  if ( SzValue )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(
        v4,
        v3,
        "BWCContentProviderConfiguration::GetConfigurationKey",
        (unsigned int)SzValue);
    if ( SzValue < 0 )
      goto LABEL_27;
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
  {
    McTemplateU0s_EventWriteTransfer(
      v4,
      SDIAGPRV_EVENT_DEBUG_SUCCESS,
      "BWCContentProviderConfiguration::GetConfigurationKey");
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
    *((_QWORD *)this + 1) = 0;
  }
  SzValue = BWCContentProviderConfiguration::GetSzValue(v4, hKey, L"RemoteServer", (unsigned __int16 **)this + 1);
  if ( SzValue >= 0 )
  {
    v8 = (void *)*((_QWORD *)this + 2);
    if ( v8 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v8);
      *((_QWORD *)this + 2) = 0;
    }
    SzValue = BWCContentProviderConfiguration::GetSzValue(
                v4,
                hKey,
                L"RemoteServerPartnerParameter",
                (unsigned __int16 **)this + 2);
    if ( SzValue >= 0 )
    {
      v10 = (void *)*((_QWORD *)this + 3);
      if ( v10 )
      {
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v10);
        *((_QWORD *)this + 3) = 0;
      }
      SzValue = BWCContentProviderConfiguration::GetSzValue(
                  v4,
                  hKey,
                  L"RemoteServerVersion",
                  (unsigned __int16 **)this + 3);
      if ( SzValue >= 0 )
      {
        SzValue = BWCContentProviderConfiguration::GetDWORDValue(v4, hKey, L"RemoteServerResponseId", (BYTE *)this + 32);
        if ( SzValue >= 0 )
          SzValue = BWCContentProviderConfiguration::GetDWORDValue(v4, hKey, L"RemoteServerTimeout", (BYTE *)this + 36);
      }
    }
  }
  if ( !SzValue )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(v4, SDIAGPRV_EVENT_DEBUG_SUCCESS, "BWCContentProviderConfiguration::Initialize");
    goto LABEL_29;
  }
LABEL_27:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(v4, v3, "BWCContentProviderConfiguration::Initialize", (unsigned int)SzValue);
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)SzValue;
}

```

## disassembly

```asm
0x180010098  mov     r11, rsp
0x18001009b  mov     [r11+8], rbx
0x18001009f  mov     [r11+18h], rsi
0x1800100a3  push    rdi
0x1800100a4  sub     rsp, 30h
0x1800100a8  mov     rdi, rcx
0x1800100ab  mov     qword ptr [r11+10h], 0
0x1800100b3  lea     rax, [r11+10h]
0x1800100b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800100be  mov     r9d, 20019h; samDesired
0x1800100c4  mov     [r11-18h], rax
0x1800100c8  xor     r8d, r8d; ulOptions
0x1800100cb  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\ScriptedD"...
0x1800100d2  call    cs:__imp_RegOpenKeyExW
0x1800100d8  mov     ebx, eax
0x1800100da  test    eax, eax
0x1800100dc  jle     short loc_1800100E7
0x1800100de  movzx   ebx, ax
0x1800100e1  or      ebx, 80070000h
0x1800100e7  cmp     ebx, 80070057h
0x1800100ed  jz      loc_180010250
0x1800100f3  test    ebx, ebx
0x1800100f5  jz      short loc_180010119
0x1800100f7  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800100fe  jz      short loc_18001010F
0x180010100  mov     r9d, ebx
0x180010103  lea     r8, aBwccontentprov_0; "BWCContentProviderConfiguration::GetCon"...
0x18001010a  call    McTemplateU0sq_EventWriteTransfer
0x18001010f  test    ebx, ebx
0x180010111  js      loc_180010268
0x180010117  jmp     short loc_180010135
0x180010119  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180010120  jz      short loc_180010135
0x180010122  lea     r8, aBwccontentprov_0; "BWCContentProviderConfiguration::GetCon"...
0x180010129  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180010130  call    McTemplateU0s_EventWriteTransfer
0x180010135  lea     rbx, [rdi+8]
0x180010139  mov     rsi, [rbx]
0x18001013c  test    rsi, rsi
0x18001013f  jz      short loc_18001015C
0x180010141  call    cs:__imp_GetProcessHeap
0x180010147  mov     r8, rsi; lpMem
0x18001014a  xor     edx, edx; dwFlags
0x18001014c  mov     rcx, rax; hHeap
0x18001014f  call    cs:__imp_HeapFree
0x180010155  mov     qword ptr [rbx], 0
0x18001015c  mov     rdx, [rsp+38h+hKey]; HKEY
0x180010161  lea     r8, aRemoteserver_0; "RemoteServer"
0x180010168  mov     r9, rbx; unsigned __int16 **
0x18001016b  call    ?GetSzValue@BWCContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAPEAG@Z; BWCContentProviderConfiguration::GetSzValue(HKEY__ * const,ushort const *,ushort * *)
0x180010170  mov     ebx, eax
0x180010172  test    eax, eax
0x180010174  js      loc_18001022E
0x18001017a  lea     rbx, [rdi+10h]
0x18001017e  mov     rsi, [rbx]
0x180010181  test    rsi, rsi
0x180010184  jz      short loc_1800101A1
0x180010186  call    cs:__imp_GetProcessHeap
0x18001018c  mov     r8, rsi; lpMem
0x18001018f  xor     edx, edx; dwFlags
0x180010191  mov     rcx, rax; hHeap
0x180010194  call    cs:__imp_HeapFree
0x18001019a  mov     qword ptr [rbx], 0
0x1800101a1  mov     rdx, [rsp+38h+hKey]; HKEY
0x1800101a6  lea     r8, aRemoteserverpa; "RemoteServerPartnerParameter"
0x1800101ad  mov     r9, rbx; unsigned __int16 **
0x1800101b0  call    ?GetSzValue@BWCContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAPEAG@Z; BWCContentProviderConfiguration::GetSzValue(HKEY__ * const,ushort const *,ushort * *)
0x1800101b5  mov     ebx, eax
0x1800101b7  test    eax, eax
0x1800101b9  js      short loc_18001022E
0x1800101bb  lea     rbx, [rdi+18h]
0x1800101bf  mov     rsi, [rbx]
0x1800101c2  test    rsi, rsi
0x1800101c5  jz      short loc_1800101E2
0x1800101c7  call    cs:__imp_GetProcessHeap
0x1800101cd  mov     r8, rsi; lpMem
0x1800101d0  xor     edx, edx; dwFlags
0x1800101d2  mov     rcx, rax; hHeap
0x1800101d5  call    cs:__imp_HeapFree
0x1800101db  mov     qword ptr [rbx], 0
0x1800101e2  mov     rdx, [rsp+38h+hKey]; HKEY
0x1800101e7  lea     r8, aRemoteserverve; "RemoteServerVersion"
0x1800101ee  mov     r9, rbx; unsigned __int16 **
0x1800101f1  call    ?GetSzValue@BWCContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAPEAG@Z; BWCContentProviderConfiguration::GetSzValue(HKEY__ * const,ushort const *,ushort * *)
0x1800101f6  mov     ebx, eax
0x1800101f8  test    eax, eax
0x1800101fa  js      short loc_18001022E
0x1800101fc  mov     rdx, [rsp+38h+hKey]; HKEY
0x180010201  lea     r9, [rdi+20h]; unsigned int *
0x180010205  lea     r8, aRemoteserverre; "RemoteServerResponseId"
0x18001020c  call    ?GetDWORDValue@BWCContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAK@Z; BWCContentProviderConfiguration::GetDWORDValue(HKEY__ * const,ushort const *,ulong *)
0x180010211  mov     ebx, eax
0x180010213  test    eax, eax
0x180010215  js      short loc_18001022E
0x180010217  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001021c  lea     r9, [rdi+24h]; unsigned int *
0x180010220  lea     r8, aRemoteserverti; "RemoteServerTimeout"
0x180010227  call    ?GetDWORDValue@BWCContentProviderConfiguration@@AEAAJQEAUHKEY__@@PEBGPEAK@Z; BWCContentProviderConfiguration::GetDWORDValue(HKEY__ * const,ushort const *,ulong *)
0x18001022c  mov     ebx, eax
0x18001022e  test    ebx, ebx
0x180010230  jnz     short loc_180010268
0x180010232  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180010239  jz      short loc_180010280
0x18001023b  lea     r8, aBwccontentprov_5; "BWCContentProviderConfiguration::Initia"...
0x180010242  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180010249  call    McTemplateU0s_EventWriteTransfer
0x18001024e  jmp     short loc_180010280
0x180010250  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180010257  jz      short loc_180010280
0x180010259  mov     r9d, ebx
0x18001025c  lea     r8, aBwccontentprov_0; "BWCContentProviderConfiguration::GetCon"...
0x180010263  call    McTemplateU0sq_EventWriteTransfer
0x180010268  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001026f  jz      short loc_180010280
0x180010271  mov     r9d, ebx
0x180010274  lea     r8, aBwccontentprov_5; "BWCContentProviderConfiguration::Initia"...
0x18001027b  call    McTemplateU0sq_EventWriteTransfer
0x180010280  mov     rcx, [rsp+38h+hKey]; hKey
0x180010285  test    rcx, rcx
0x180010288  jz      short loc_180010290
0x18001028a  call    cs:__imp_RegCloseKey
0x180010290  mov     rsi, [rsp+38h+arg_10]
0x180010295  mov     eax, ebx
0x180010297  mov     rbx, [rsp+38h+arg_0]
0x18001029c  add     rsp, 30h
0x1800102a0  pop     rdi
0x1800102a1  retn
```
