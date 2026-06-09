# CVssAsrAPIBackup::GetAsrMetadata(ulong,ulong const *,ulong,ushort const * const *,ushort * *)

- ea: `0x140079a50`
- end: `0x140079cf2`
- name: `?GetAsrMetadata@CVssAsrAPIBackup@@UEAAJKPEBKKPEBQEBGPEAPEAG@Z`
- size: `674`
- prototype: `int(CVssAsrAPIBackup *__hidden this, unsigned int, const unsigned int *, unsigned int, const unsigned __int16 *const *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x14005cd48`
- `0x140060ba4`
- `0x14006168c`
- `0x140079a50`
- `0x1400d2194`
- `0x1400d257c`
- `0x1400d25f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140079cd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140079cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079bfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079bfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140079c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140079ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140079cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140079c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140079ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140079cb4`

## string_xrefs

- `0x140079b9f`: `_GetCriticalVolumesFromSelectedComponents( cVolumes, rgpwszVolumes, &pmwszCriticalVolumes)`
- `0x140079c05`: `AsrPerformBackup(&pwszXmlDoc, &pmwszCriticalVolumes, rgDisks, cDisks )`

## pseudocode

```c
__int64 __fastcall CVssAsrAPIBackup::GetAsrMetadata(
        CVssAsrAPIBackup *this,
        unsigned int a2,
        const unsigned int *a3,
        unsigned int a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  CVssAsrAPIBackup *v9; // rcx
  WCHAR *v10; // rsi
  unsigned __int16 **v11; // rdi
  int LastError; // ebx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v13; // rcx
  int v14; // edx
  const char *v15; // rax
  DWORD v16; // eax
  int v17; // edx
  const char *v18; // rcx
  int v19; // eax
  DWORD v20; // eax
  unsigned __int16 *v22; // [rsp+30h] [rbp-18h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+48h] BYREF

  TraceFunctionEnter(L"CVssAsrAPIBackup::GetAsrMetadata");
  v10 = 0;
  lpFileName = 0;
  pv = 0;
  v22 = 0;
  v11 = a6;
  if ( a6 )
    *a6 = 0;
  if ( a3 )
  {
    if ( a5 )
    {
      if ( v11 )
      {
        if ( (unsigned int)CVssAsrAPIBackup::_GetCriticalVolumesFromSelectedComponents(
                             v9,
                             a4,
                             (const unsigned __int16 *const *)a5,
                             &v22) )
        {
          if ( AsrPerformBackup((unsigned __int16 **)&pv, &v22, a3, a2) )
          {
            v19 = AsrRegWriteXmlToFile((unsigned __int16 **)&lpFileName);
            v10 = (WCHAR *)lpFileName;
            if ( !v19 || (unsigned int)AsrWriteXmlToSifFile(lpFileName, pv) )
            {
              LastError = 0;
              *v11 = (unsigned __int16 *)pv;
              pv = 0;
            }
            else
            {
              LastError = GetLastError();
              if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
              {
                v20 = GetLastError();
                WPP_SF_DsS(
                  *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
                  79,
                  (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
                  v20,
                  (__int64)"GetLastError()",
                  (__int64)v10);
              }
            }
            goto LABEL_32;
          }
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
          {
            goto LABEL_32;
          }
          v16 = GetLastError();
          v17 = 78;
          v18 = "AsrPerformBackup(&pwszXmlDoc, &pmwszCriticalVolumes, rgDisks, cDisks )";
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
          {
            goto LABEL_32;
          }
          v16 = GetLastError();
          v17 = 77;
          v18 = "_GetCriticalVolumesFromSelectedComponents( cVolumes, rgpwszVolumes, &pmwszCriticalVolumes)";
        }
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          v17,
          (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
          v16,
          v18);
        goto LABEL_32;
      }
      LastError = 87;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v14 = 76;
        v15 = "ppwszMetadata";
        goto LABEL_7;
      }
    }
    else
    {
      LastError = 87;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v14 = (_DWORD)a5 + 75;
        v15 = "rgpwszVolumes";
        goto LABEL_7;
      }
    }
  }
  else
  {
    LastError = 87;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v14 = 74;
      v15 = "rgDisks";
LABEL_7:
      WPP_SF_Ds(
        *(_QWORD *)v13->Gpt.DiskId.Data4,
        v14,
        (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
        87,
        v15);
    }
  }
LABEL_32:
  CoTaskMemFree(v10);
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v22);
  v22 = 0;
  TraceFunctionExit(L"CVssAsrAPIBackup::GetAsrMetadata");
  SetLastError(LastError);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140079a50  push    rbp
0x140079a52  push    rbx
0x140079a53  push    rsi
0x140079a54  push    rdi
0x140079a55  push    r14
0x140079a57  push    r15
0x140079a59  mov     rbp, rsp
0x140079a5c  sub     rsp, 48h
0x140079a60  mov     r14d, r9d
0x140079a63  mov     rbx, r8
0x140079a66  mov     r15d, edx
0x140079a69  lea     rcx, aCvssasrapiback; "CVssAsrAPIBackup::GetAsrMetadata"
0x140079a70  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x140079a75  xor     esi, esi
0x140079a77  mov     [rbp+lpFileName], rsi
0x140079a7b  mov     [rbp+pv], rsi
0x140079a7f  mov     [rbp+var_18], rsi
0x140079a83  mov     rdi, [rbp+arg_28]
0x140079a87  test    rdi, rdi
0x140079a8a  jz      short loc_140079A8F
0x140079a8c  mov     [rdi], rsi
0x140079a8f  test    rbx, rbx
0x140079a92  jnz     short loc_140079AE1
0x140079a94  lea     r9d, [rbx+57h]
0x140079a98  mov     ebx, r9d
0x140079a9b  lea     rax, WPP_GLOBAL_Control
0x140079aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140079aa9  cmp     rcx, rax
0x140079aac  jz      loc_140079C95
0x140079ab2  test    byte ptr [rcx+1Ch], 8
0x140079ab6  jz      loc_140079C95
0x140079abc  lea     edx, [r9-0Dh]
0x140079ac0  lea     rax, aRgdisks; "rgDisks"
0x140079ac7  mov     [rsp+48h+var_28], rax
0x140079acc  lea     r8, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x140079ad3  mov     rcx, [rcx+10h]
0x140079ad7  call    WPP_SF_Ds
0x140079adc  jmp     loc_140079C95
0x140079ae1  mov     r8, [rbp+arg_20]; unsigned __int16 **
0x140079ae5  test    r8, r8
0x140079ae8  jnz     short loc_140079B1F
0x140079aea  lea     r9d, [r8+57h]
0x140079aee  mov     ebx, r9d
0x140079af1  lea     rax, WPP_GLOBAL_Control
0x140079af8  mov     rcx, cs:WPP_GLOBAL_Control
0x140079aff  cmp     rcx, rax
0x140079b02  jz      loc_140079C95
0x140079b08  test    byte ptr [rcx+1Ch], 8
0x140079b0c  jz      loc_140079C95
0x140079b12  lea     edx, [r8+4Bh]
0x140079b16  lea     rax, aRgpwszvolumes; "rgpwszVolumes"
0x140079b1d  jmp     short loc_140079AC7
0x140079b1f  test    rdi, rdi
0x140079b22  jnz     short loc_140079B5B
0x140079b24  lea     r9d, [rdi+57h]
0x140079b28  mov     ebx, r9d
0x140079b2b  lea     rax, WPP_GLOBAL_Control
0x140079b32  mov     rcx, cs:WPP_GLOBAL_Control
0x140079b39  cmp     rcx, rax
0x140079b3c  jz      loc_140079C95
0x140079b42  test    byte ptr [rcx+1Ch], 8
0x140079b46  jz      loc_140079C95
0x140079b4c  lea     edx, [rdi+4Ch]
0x140079b4f  lea     rax, aPpwszmetadata; "ppwszMetadata"
0x140079b56  jmp     loc_140079AC7
0x140079b5b  lea     r9, [rbp+var_18]; unsigned __int16 **
0x140079b5f  mov     edx, r14d; unsigned int
0x140079b62  call    ?_GetCriticalVolumesFromSelectedComponents@CVssAsrAPIBackup@@AEAAHKPEBQEBGPEAPEAG@Z; CVssAsrAPIBackup::_GetCriticalVolumesFromSelectedComponents(ulong,ushort const * const *,ushort * *)
0x140079b67  test    eax, eax
0x140079b69  jnz     short loc_140079BBA
0x140079b6b  call    cs:__imp_GetLastError
0x140079b71  mov     ebx, eax
0x140079b73  lea     rax, WPP_GLOBAL_Control
0x140079b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140079b81  cmp     rcx, rax
0x140079b84  jz      loc_140079C95
0x140079b8a  test    byte ptr [rcx+1Ch], 8
0x140079b8e  jz      loc_140079C95
0x140079b94  call    cs:__imp_GetLastError
0x140079b9a  mov     edx, 4Dh ; 'M'
0x140079b9f  lea     rcx, aGetcriticalvol; "_GetCriticalVolumesFromSelectedComponen"...
0x140079ba6  mov     [rsp+48h+var_28], rcx
0x140079bab  mov     r9d, eax
0x140079bae  mov     rcx, cs:WPP_GLOBAL_Control
0x140079bb5  jmp     loc_140079ACC
0x140079bba  mov     r9d, r15d; unsigned int
0x140079bbd  mov     r8, rbx; unsigned int *
0x140079bc0  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x140079bc4  lea     rcx, [rbp+pv]; unsigned __int16 **
0x140079bc8  call    ?AsrPerformBackup@@YAHPEAPEAG0PEBKK@Z; AsrPerformBackup(ushort * *,ushort * *,ulong const *,ulong)
0x140079bcd  test    eax, eax
0x140079bcf  jnz     short loc_140079C0E
0x140079bd1  call    cs:__imp_GetLastError
0x140079bd7  mov     ebx, eax
0x140079bd9  lea     rax, WPP_GLOBAL_Control
0x140079be0  mov     rcx, cs:WPP_GLOBAL_Control
0x140079be7  cmp     rcx, rax
0x140079bea  jz      loc_140079C95
0x140079bf0  test    byte ptr [rcx+1Ch], 8
0x140079bf4  jz      loc_140079C95
0x140079bfa  call    cs:__imp_GetLastError
0x140079c00  mov     edx, 4Eh ; 'N'
0x140079c05  lea     rcx, aAsrperformback; "AsrPerformBackup(&pwszXmlDoc, &pmwszCri"...
0x140079c0c  jmp     short loc_140079BA6
0x140079c0e  lea     rcx, [rbp+lpFileName]; unsigned __int16 **
0x140079c12  call    ?AsrRegWriteXmlToFile@@YAHPEAPEAG@Z; AsrRegWriteXmlToFile(ushort * *)
0x140079c17  mov     rsi, [rbp+lpFileName]
0x140079c1b  test    eax, eax
0x140079c1d  jz      short loc_140079C88
0x140079c1f  mov     rdx, [rbp+pv]; lpBuffer
0x140079c23  mov     rcx, rsi; lpFileName
0x140079c26  call    ?AsrWriteXmlToSifFile@@YAHPEAG0@Z; AsrWriteXmlToSifFile(ushort *,ushort *)
0x140079c2b  test    eax, eax
0x140079c2d  jnz     short loc_140079C88
0x140079c2f  call    cs:__imp_GetLastError
0x140079c35  mov     ebx, eax
0x140079c37  lea     rax, WPP_GLOBAL_Control
0x140079c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140079c45  cmp     rcx, rax
0x140079c48  jz      short loc_140079C95
0x140079c4a  test    byte ptr [rcx+1Ch], 8
0x140079c4e  jz      short loc_140079C95
0x140079c50  call    cs:__imp_GetLastError
0x140079c56  mov     edx, 4Fh ; 'O'
0x140079c5b  mov     [rsp+48h+var_20], rsi
0x140079c60  lea     rcx, aGetlasterror_1; "GetLastError()"
0x140079c67  mov     [rsp+48h+var_28], rcx
0x140079c6c  mov     r9d, eax
0x140079c6f  lea     r8, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x140079c76  mov     rcx, cs:WPP_GLOBAL_Control
0x140079c7d  mov     rcx, [rcx+10h]
0x140079c81  call    WPP_SF_DsS
0x140079c86  jmp     short loc_140079C95
0x140079c88  xor     ebx, ebx
0x140079c8a  mov     rax, [rbp+pv]
0x140079c8e  mov     [rdi], rax
0x140079c91  mov     [rbp+pv], rbx
0x140079c95  mov     rcx, rsi; pv
0x140079c98  call    cs:__imp_CoTaskMemFree
0x140079c9e  mov     rcx, [rbp+pv]; pv
0x140079ca2  call    cs:__imp_CoTaskMemFree
0x140079ca8  mov     [rbp+pv], 0
0x140079cb0  mov     rcx, [rbp+var_18]; pv
0x140079cb4  call    cs:__imp_CoTaskMemFree
0x140079cba  mov     [rbp+var_18], 0
0x140079cc2  lea     rcx, aCvssasrapiback; "CVssAsrAPIBackup::GetAsrMetadata"
0x140079cc9  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x140079cce  mov     ecx, ebx; dwErrCode
0x140079cd0  call    cs:__imp_SetLastError
0x140079cd6  test    ebx, ebx
0x140079cd8  jle     short loc_140079CE3
0x140079cda  movzx   ebx, bx
0x140079cdd  or      ebx, 80070000h
0x140079ce3  mov     eax, ebx
0x140079ce5  add     rsp, 48h
0x140079ce9  pop     r15
0x140079ceb  pop     r14
0x140079ced  pop     rdi
0x140079cee  pop     rsi
0x140079cef  pop     rbx
0x140079cf0  pop     rbp
0x140079cf1  retn
```
