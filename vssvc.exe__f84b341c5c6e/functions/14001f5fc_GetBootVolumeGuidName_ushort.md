# GetBootVolumeGuidName(ushort * *)

- ea: `0x14001f5fc`
- end: `0x14001f7ab`
- name: `?GetBootVolumeGuidName@@YAHPEAPEAG@Z`
- size: `431`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1400205d0`
- `0x1400235e0`
- `0x14006168c`

## callees

- `0x14001f5fc`
- `0x1400227a0`
- `0x140091560`
- `0x1400d257c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001f77e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001f77e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f6b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f6b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f754`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14001f727`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14001f727`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14001f682`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14001f682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f776`

## pseudocode

```c
__int64 __fastcall GetBootVolumeGuidName(unsigned __int16 **a1)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v4; // rcx
  int v5; // edx
  const char *v6; // rax
  UINT SystemWindowsDirectoryW; // eax
  DWORD v8; // eax
  int v9; // edx
  WCHAR szVolumeName[56]; // [rsp+30h] [rbp-298h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-228h] BYREF

  if ( !a1 )
  {
    v2 = 0;
    LastError = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v5 = 14;
      v6 = "ppwszVolumeGuidOut";
LABEL_5:
      WPP_SF_Ds(
        *(_QWORD *)v4->Gpt.DiskId.Data4,
        v5,
        (unsigned int)WPP_214f6c84b4d4323947ecaa518c1defb8_Traceguids,
        LastError,
        v6);
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x105u);
  if ( !SystemWindowsDirectoryW )
  {
    v2 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_21;
    }
    v8 = GetLastError();
    v9 = 15;
LABEL_11:
    WPP_SF_Ds(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      v9,
      (unsigned int)WPP_214f6c84b4d4323947ecaa518c1defb8_Traceguids,
      v8,
      "GetLastError( )");
    goto LABEL_21;
  }
  if ( SystemWindowsDirectoryW <= 0x104 )
  {
    Buffer[3] = 0;
    if ( GetVolumeNameForVolumeMountPointW(Buffer, szVolumeName, 0x32u) )
    {
      LastError = 0;
      v2 = 1;
      *a1 = SafeStrClone(szVolumeName);
      goto LABEL_21;
    }
    v2 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v8 = GetLastError();
      v9 = 17;
      goto LABEL_11;
    }
  }
  else
  {
    v2 = 0;
    LastError = 122;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v5 = 16;
      v6 = "ERROR_INSUFFICIENT_BUFFER";
      goto LABEL_5;
    }
  }
LABEL_21:
  CoTaskMemFree(0);
  SetLastError(LastError);
  return v2;
}

```

## disassembly

```asm
0x14001f5fc  mov     [rsp+arg_8], rbx
0x14001f601  mov     [rsp+arg_10], rsi
0x14001f606  push    rdi
0x14001f607  sub     rsp, 2C0h
0x14001f60e  mov     rax, cs:__security_cookie
0x14001f615  xor     rax, rsp
0x14001f618  mov     [rsp+2C8h+var_18], rax
0x14001f620  mov     rsi, rcx
0x14001f623  test    rcx, rcx
0x14001f626  jnz     short loc_14001F675
0x14001f628  xor     edi, edi
0x14001f62a  lea     ebx, [rcx+57h]
0x14001f62d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f634  lea     rax, WPP_GLOBAL_Control
0x14001f63b  cmp     rcx, rax
0x14001f63e  jz      loc_14001F774
0x14001f644  test    byte ptr [rcx+1Ch], 8
0x14001f648  jz      loc_14001F774
0x14001f64e  lea     edx, [rsi+0Eh]
0x14001f651  lea     rax, aPpwszvolumegui; "ppwszVolumeGuidOut"
0x14001f658  mov     [rsp+2C8h+var_2A8], rax
0x14001f65d  mov     r9d, ebx
0x14001f660  mov     rcx, [rcx+10h]
0x14001f664  lea     r8, WPP_214f6c84b4d4323947ecaa518c1defb8_Traceguids
0x14001f66b  call    WPP_SF_Ds
0x14001f670  jmp     loc_14001F774
0x14001f675  mov     edx, 105h; uSize
0x14001f67a  lea     rcx, [rsp+2C8h+Buffer]; lpBuffer
0x14001f682  call    cs:__imp_GetSystemWindowsDirectoryW
0x14001f688  test    eax, eax
0x14001f68a  jnz     short loc_14001F6D8
0x14001f68c  xor     edi, edi
0x14001f68e  call    cs:__imp_GetLastError
0x14001f694  mov     ebx, eax
0x14001f696  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f69d  lea     rax, WPP_GLOBAL_Control
0x14001f6a4  cmp     rcx, rax
0x14001f6a7  jz      loc_14001F774
0x14001f6ad  test    byte ptr [rcx+1Ch], 8
0x14001f6b1  jz      loc_14001F774
0x14001f6b7  call    cs:__imp_GetLastError
0x14001f6bd  lea     edx, [rdi+0Fh]
0x14001f6c0  lea     rcx, aGetlasterror; "GetLastError( )"
0x14001f6c7  mov     r9d, eax
0x14001f6ca  mov     [rsp+2C8h+var_2A8], rcx
0x14001f6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f6d6  jmp     short loc_14001F660
0x14001f6d8  cmp     eax, 104h
0x14001f6dd  jbe     short loc_14001F70C
0x14001f6df  xor     edi, edi
0x14001f6e1  lea     ebx, [rdi+7Ah]
0x14001f6e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f6eb  lea     rax, WPP_GLOBAL_Control
0x14001f6f2  cmp     rcx, rax
0x14001f6f5  jz      short loc_14001F774
0x14001f6f7  test    byte ptr [rcx+1Ch], 8
0x14001f6fb  jz      short loc_14001F774
0x14001f6fd  lea     edx, [rdi+10h]
0x14001f700  lea     rax, aErrorInsuffici; "ERROR_INSUFFICIENT_BUFFER"
0x14001f707  jmp     loc_14001F658
0x14001f70c  xor     eax, eax
0x14001f70e  lea     rdx, [rsp+2C8h+szVolumeName]; lpszVolumeName
0x14001f713  lea     rcx, [rsp+2C8h+Buffer]; lpszVolumeMountPoint
0x14001f71b  mov     [rsp+2C8h+var_222], ax
0x14001f723  lea     r8d, [rax+32h]; cchBufferLength
0x14001f727  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14001f72d  test    eax, eax
0x14001f72f  jnz     short loc_14001F762
0x14001f731  xor     edi, edi
0x14001f733  call    cs:__imp_GetLastError
0x14001f739  mov     ebx, eax
0x14001f73b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f742  lea     rax, WPP_GLOBAL_Control
0x14001f749  cmp     rcx, rax
0x14001f74c  jz      short loc_14001F774
0x14001f74e  test    byte ptr [rcx+1Ch], 8
0x14001f752  jz      short loc_14001F774
0x14001f754  call    cs:__imp_GetLastError
0x14001f75a  lea     edx, [rdi+11h]
0x14001f75d  jmp     loc_14001F6C0
0x14001f762  xor     ebx, ebx
0x14001f764  lea     rcx, [rsp+2C8h+szVolumeName]; unsigned __int16 *
0x14001f769  lea     edi, [rbx+1]
0x14001f76c  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x14001f771  mov     [rsi], rax
0x14001f774  xor     ecx, ecx; pv
0x14001f776  call    cs:__imp_CoTaskMemFree
0x14001f77c  mov     ecx, ebx; dwErrCode
0x14001f77e  call    cs:__imp_SetLastError
0x14001f784  mov     eax, edi
0x14001f786  mov     rcx, [rsp+2C8h+var_18]
0x14001f78e  xor     rcx, rsp; StackCookie
0x14001f791  call    __security_check_cookie
0x14001f796  lea     r11, [rsp+2C8h+var_8]
0x14001f79e  mov     rbx, [r11+18h]
0x14001f7a2  mov     rsi, [r11+20h]
0x14001f7a6  mov     rsp, r11
0x14001f7a9  pop     rdi
0x14001f7aa  retn
```
