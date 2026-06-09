# AsrRegWriteXmlToFile(ushort * *)

- ea: `0x140060ba4`
- end: `0x140060e38`
- name: `?AsrRegWriteXmlToFile@@YAHPEAPEAG@Z`
- size: `660`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140079a50`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x140060ba4`
- `0x1400d257c`
- `0x1400d25f8`
- `0x1400d8e24`
- `0x1400d910c`
- `0x1400d9254`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140060e1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140060e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060cee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060cee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060d4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140060e01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140060e01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140060e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140060e0a`

## string_xrefs

- `0x140060bb8`: `AsrRegWriteXmlToFile`
- `0x140060e10`: `AsrRegWriteXmlToFile`
- `0x140060c0d`: `ppwszOutXmlFilename`
- `0x140060cf4`: `WriteXmlToFile`
- `0x140060d52`: `WriteXmlToFile`

## pseudocode

```c
__int64 __fastcall AsrRegWriteXmlToFile(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rbx
  unsigned int v3; // edi
  DWORD LastError; // esi
  const unsigned __int16 *v5; // rdx
  DWORD v6; // eax
  const unsigned __int16 *v7; // rdx
  DWORD v8; // eax
  DWORD v9; // eax
  unsigned int v11; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v13; // [rsp+70h] [rbp+18h] BYREF

  TraceFunctionEnter(L"AsrRegWriteXmlToFile");
  hKey = 0;
  v2 = 0;
  v13 = 0;
  v11 = 0;
  if ( !a1 )
  {
    v3 = 0;
    LastError = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        23,
        (unsigned int)WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids,
        87,
        "ppwszOutXmlFilename");
    }
    goto LABEL_28;
  }
  if ( (unsigned int)AsrRegpOpenHandle(L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\BackupSession", 0, &hKey) )
  {
    if ( (unsigned int)AsrRegpQueryValueDword(hKey, v5, &v11) )
    {
      if ( v11 )
      {
        if ( !(unsigned int)AsrRegpQueryValueSz(hKey, v7, &v13) )
        {
          v3 = 0;
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v9 = GetLastError();
            WPP_SF_DsS(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              26,
              (unsigned int)WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids,
              v9,
              (__int64)"GetLastError()",
              (__int64)L"WriteXmlToFile");
          }
          v2 = v13;
          goto LABEL_26;
        }
        v2 = v13;
        if ( !v13 || !*v13 )
        {
          v3 = 0;
          LastError = 87;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              27,
              (unsigned int)WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids,
              87,
              "ERROR_INVALID_PARAMETER");
          }
          goto LABEL_26;
        }
      }
      *a1 = v2;
      LastError = 0;
      v2 = 0;
      v3 = 1;
    }
    else
    {
      v3 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v8 = GetLastError();
        WPP_SF_DsS(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          25,
          (unsigned int)WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids,
          v8,
          (__int64)"GetLastError()",
          (__int64)L"WriteXmlToFile");
      }
    }
  }
  else
  {
    v3 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v6 = GetLastError();
      WPP_SF_DsS(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        24,
        (unsigned int)WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids,
        v6,
        (__int64)"GetLastError()",
        (__int64)L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\BackupSession");
    }
  }
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_28:
  CoTaskMemFree(v2);
  TraceFunctionExit(L"AsrRegWriteXmlToFile");
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x140060ba4  mov     [rsp+arg_18], rbx
0x140060ba9  push    rsi
0x140060baa  push    rdi
0x140060bab  push    r12
0x140060bad  push    r14
0x140060baf  push    r15
0x140060bb1  sub     rsp, 30h
0x140060bb5  mov     r14, rcx
0x140060bb8  lea     rcx, aAsrregwritexml; "AsrRegWriteXmlToFile"
0x140060bbf  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x140060bc4  xor     r15d, r15d
0x140060bc7  mov     [rsp+58h+hKey], r15
0x140060bcc  mov     ebx, r15d
0x140060bcf  mov     [rsp+58h+arg_10], rbx
0x140060bd4  mov     [rsp+58h+arg_0], r15d
0x140060bd9  test    r14, r14
0x140060bdc  jnz     short loc_140060C2E
0x140060bde  lea     r9d, [r15+57h]
0x140060be2  mov     edi, r15d
0x140060be5  mov     esi, r9d
0x140060be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140060bef  lea     rax, WPP_GLOBAL_Control
0x140060bf6  cmp     rcx, rax
0x140060bf9  jz      loc_140060E07
0x140060bff  test    byte ptr [rcx+1Ch], 8
0x140060c03  jz      loc_140060E07
0x140060c09  mov     rcx, [rcx+10h]
0x140060c0d  lea     rax, aPpwszoutxmlfil; "ppwszOutXmlFilename"
0x140060c14  lea     edx, [r15+17h]
0x140060c18  mov     [rsp+58h+var_38], rax
0x140060c1d  lea     r8, WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids
0x140060c24  call    WPP_SF_Ds
0x140060c29  jmp     loc_140060E07
0x140060c2e  lea     r12, aSoftwareMicros; "SOFTWARE\\MICROSOFT\\WINDOWS NT\\Curren"...
0x140060c35  xor     edx, edx; int
0x140060c37  mov     rcx, r12; lpSubKey
0x140060c3a  lea     r8, [rsp+58h+hKey]; HKEY *
0x140060c3f  call    ?AsrRegpOpenHandle@@YAHPEBGHPEAPEAUHKEY__@@@Z; AsrRegpOpenHandle(ushort const *,int,HKEY__ * *)
0x140060c44  test    eax, eax
0x140060c46  jnz     short loc_140060CAF
0x140060c48  mov     edi, r15d
0x140060c4b  call    cs:__imp_GetLastError
0x140060c51  mov     esi, eax
0x140060c53  mov     rcx, cs:WPP_GLOBAL_Control
0x140060c5a  lea     rax, WPP_GLOBAL_Control
0x140060c61  cmp     rcx, rax
0x140060c64  jz      loc_140060DF5
0x140060c6a  test    byte ptr [rcx+1Ch], 8
0x140060c6e  jz      loc_140060DF5
0x140060c74  call    cs:__imp_GetLastError
0x140060c7a  mov     edx, 18h
0x140060c7f  mov     [rsp+58h+var_30], r12
0x140060c84  lea     rcx, aGetlasterror_1; "GetLastError()"
0x140060c8b  mov     r9d, eax
0x140060c8e  mov     [rsp+58h+var_38], rcx
0x140060c93  lea     r8, WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids
0x140060c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140060ca1  mov     rcx, [rcx+10h]
0x140060ca5  call    WPP_SF_DsS
0x140060caa  jmp     loc_140060DF5
0x140060caf  mov     rcx, [rsp+58h+hKey]; HKEY
0x140060cb4  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x140060cb9  call    ?AsrRegpQueryValueDword@@YAHPEAUHKEY__@@PEBGPEAK@Z; AsrRegpQueryValueDword(HKEY__ *,ushort const *,ulong *)
0x140060cbe  test    eax, eax
0x140060cc0  jnz     short loc_140060D0A
0x140060cc2  mov     edi, r15d
0x140060cc5  call    cs:__imp_GetLastError
0x140060ccb  mov     esi, eax
0x140060ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x140060cd4  lea     rax, WPP_GLOBAL_Control
0x140060cdb  cmp     rcx, rax
0x140060cde  jz      loc_140060DF5
0x140060ce4  test    byte ptr [rcx+1Ch], 8
0x140060ce8  jz      loc_140060DF5
0x140060cee  call    cs:__imp_GetLastError
0x140060cf4  lea     rcx, aWritexmltofile; "WriteXmlToFile"
0x140060cfb  mov     edx, 19h
0x140060d00  mov     [rsp+58h+var_30], rcx
0x140060d05  jmp     loc_140060C84
0x140060d0a  cmp     [rsp+58h+arg_0], r15d
0x140060d0f  jz      loc_140060DE7
0x140060d15  mov     rcx, [rsp+58h+hKey]; HKEY
0x140060d1a  lea     r8, [rsp+58h+arg_10]; unsigned __int16 **
0x140060d1f  call    ?AsrRegpQueryValueSz@@YAHPEAUHKEY__@@PEBGPEAPEAG@Z; AsrRegpQueryValueSz(HKEY__ *,ushort const *,ushort * *)
0x140060d24  test    eax, eax
0x140060d26  jnz     short loc_140060D90
0x140060d28  mov     edi, r15d
0x140060d2b  call    cs:__imp_GetLastError
0x140060d31  mov     esi, eax
0x140060d33  mov     rcx, cs:WPP_GLOBAL_Control
0x140060d3a  lea     rax, WPP_GLOBAL_Control
0x140060d41  cmp     rcx, rax
0x140060d44  jz      short loc_140060D89
0x140060d46  test    byte ptr [rcx+1Ch], 8
0x140060d4a  jz      short loc_140060D89
0x140060d4c  call    cs:__imp_GetLastError
0x140060d52  lea     rcx, aWritexmltofile; "WriteXmlToFile"
0x140060d59  mov     edx, 1Ah
0x140060d5e  mov     [rsp+58h+var_30], rcx
0x140060d63  lea     r8, WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids
0x140060d6a  lea     rcx, aGetlasterror_1; "GetLastError()"
0x140060d71  mov     r9d, eax
0x140060d74  mov     [rsp+58h+var_38], rcx
0x140060d79  mov     rcx, cs:WPP_GLOBAL_Control
0x140060d80  mov     rcx, [rcx+10h]
0x140060d84  call    WPP_SF_DsS
0x140060d89  mov     rbx, [rsp+58h+arg_10]
0x140060d8e  jmp     short loc_140060DF5
0x140060d90  mov     rbx, [rsp+58h+arg_10]
0x140060d95  test    rbx, rbx
0x140060d98  jz      short loc_140060DA0
0x140060d9a  cmp     [rbx], r15w
0x140060d9e  jnz     short loc_140060DE7
0x140060da0  mov     r9d, 57h ; 'W'
0x140060da6  mov     edi, r15d
0x140060da9  mov     esi, r9d
0x140060dac  mov     rcx, cs:WPP_GLOBAL_Control
0x140060db3  lea     rax, WPP_GLOBAL_Control
0x140060dba  cmp     rcx, rax
0x140060dbd  jz      short loc_140060DF5
0x140060dbf  test    byte ptr [rcx+1Ch], 8
0x140060dc3  jz      short loc_140060DF5
0x140060dc5  mov     rcx, [rcx+10h]
0x140060dc9  lea     rax, aErrorInvalidPa; "ERROR_INVALID_PARAMETER"
0x140060dd0  lea     edx, [r9-3Ch]
0x140060dd4  mov     [rsp+58h+var_38], rax
0x140060dd9  lea     r8, WPP_e89c33f4c80635d2dae56cdb46d879e1_Traceguids
0x140060de0  call    WPP_SF_Ds
0x140060de5  jmp     short loc_140060DF5
0x140060de7  mov     [r14], rbx
0x140060dea  mov     esi, r15d
0x140060ded  mov     rbx, r15
0x140060df0  mov     edi, 1
0x140060df5  cmp     [rsp+58h+hKey], r15
0x140060dfa  jz      short loc_140060E07
0x140060dfc  mov     rcx, [rsp+58h+hKey]; hKey
0x140060e01  call    cs:__imp_RegCloseKey
0x140060e07  mov     rcx, rbx; pv
0x140060e0a  call    cs:__imp_CoTaskMemFree
0x140060e10  lea     rcx, aAsrregwritexml; "AsrRegWriteXmlToFile"
0x140060e17  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x140060e1c  mov     ecx, esi; dwErrCode
0x140060e1e  call    cs:__imp_SetLastError
0x140060e24  mov     rbx, [rsp+58h+arg_18]
0x140060e29  mov     eax, edi
0x140060e2b  add     rsp, 30h
0x140060e2f  pop     r15
0x140060e31  pop     r14
0x140060e33  pop     r12
0x140060e35  pop     rdi
0x140060e36  pop     rsi
0x140060e37  retn
```
