# CSdController::_VerifyUncDeviceAccess(ushort const *,_SID *,ulong *)

- ea: `0x1800148dc`
- end: `0x180014d14`
- name: `?_VerifyUncDeviceAccess@CSdController@@CAJPEBGPEAU_SID@@PEAK@Z`
- size: `1080`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SID *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001445c`

## callees

- `0x1800148dc`
- `0x18001586c`
- `0x180015974`
- `0x180016a78`
- `0x180017454`
- `0x18001c58c`
- `0x18001cfc8`
- `0x18001d154`
- `0x18001e2dc`
- `0x18001fc5c`
- `0x18001fcc0`
- `0x180020488`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014cdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014cdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c9c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014aff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014aff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014b60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014b60`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014bb6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014bb6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800149ba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180014a82`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800149ba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180014a82`

## string_xrefs

- `0x180014909`: `CSdController::_VerifyUncDeviceAccess`

## pseudocode

```c
__int64 __fastcall CSdController::_VerifyUncDeviceAccess(const unsigned __int16 *a1, struct _SID *a2, unsigned int *a3)
{
  __int64 FileW; // rbx
  __int16 v6; // ax
  HRESULT LastFailureAsHRESULT; // edi
  const unsigned __int16 *v8; // r9
  int v9; // edx
  HRESULT v10; // eax
  bool v11; // zf
  const unsigned __int16 *v12; // r9
  __int16 v13; // ax
  int v14; // esi
  const unsigned __int16 *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v22; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v23; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v24; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v25; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v26; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v27; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v28; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v29; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v31; // [rsp+64h] [rbp-9Ch]
  __int16 v32; // [rsp+66h] [rbp-9Ah]
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp-68h] BYREF
  int v34; // [rsp+9Ch] [rbp-64h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp-60h] BYREF
  int v36; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v37[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v39[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 Buffer; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v41; // [rsp+F0h] [rbp-10h]
  _QWORD v42[2]; // [rsp+F8h] [rbp-8h] BYREF
  GUID pguid; // [rsp+108h] [rbp+8h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v30, "CSdController::_VerifyUncDeviceAccess", 0x118u, 1u);
  v39[0] = (unsigned __int16 *)qword_180028260;
  v41 = 0;
  Buffer = 0;
  FileW = -1;
  v39[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_180028260;
  v6 = 296;
  lpFileName[1] = 0;
  v42[0] = qword_180028260;
  v42[1] = 0;
  SecurityDescriptor = 0;
  NumberOfBytesWritten = 0;
  v37[0] = (unsigned __int16 *)qword_180028260;
  v37[1] = 0;
  v36 = 0;
  v34 = 0;
  pguid = GUID_NULL;
  if ( !a1 || (v31 = 296, v6 = 297, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
    v30 = -2147024809;
LABEL_3:
    v32 = v6;
    goto LABEL_39;
  }
  v30 = 0;
  v31 = 297;
  LastFailureAsHRESULT = CoCreateGuid(&pguid);
  v30 = LastFailureAsHRESULT;
  v6 = 303;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v31 = 303;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)v37, &pguid);
  v30 = LastFailureAsHRESULT;
  v6 = 304;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v31 = 304;
  LastFailureAsHRESULT = CBsString::SetPath(
                           (CBsString *)v39,
                           a1,
                           v37[0],
                           v8,
                           dwCreationDisposition,
                           dwFlagsAndAttributes,
                           hTemplateFile,
                           v22,
                           v24,
                           v26,
                           v28);
  v30 = LastFailureAsHRESULT;
  v6 = 305;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v31 = 305;
  LastFailureAsHRESULT = EnsureDirectoryExists(v39[0], 0, 0, 0);
  v6 = 314;
  if ( LastFailureAsHRESULT == -2147024891 )
    LastFailureAsHRESULT = -2130706390;
  v30 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v31 = 314;
  v10 = SxDeleteDirectory(v39[0], v9);
  v11 = v10 == -2147024891;
  LastFailureAsHRESULT = v10;
  v6 = 322;
  if ( v11 )
    LastFailureAsHRESULT = -2130706390;
  v30 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v31 = 322;
  LastFailureAsHRESULT = CoCreateGuid(&pguid);
  v30 = LastFailureAsHRESULT;
  v6 = 325;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v31 = 325;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)v37, &pguid);
  v30 = LastFailureAsHRESULT;
  v6 = 326;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v31 = 326;
  LastFailureAsHRESULT = CBsString::SetPath(
                           (CBsString *)lpFileName,
                           a1,
                           v37[0],
                           v12,
                           dwCreationDispositiona,
                           dwFlagsAndAttributesa,
                           hTemplateFilea,
                           v23,
                           v25,
                           v27,
                           v29);
  v30 = LastFailureAsHRESULT;
  v6 = 327;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v31 = 327;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:AR(A;;FR;;;AU)(A;OICI;FA;;;CO)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v30 = LastFailureAsHRESULT;
    v6 = 330;
    goto LABEL_3;
  }
  v31 = 330;
  *((_QWORD *)&Buffer + 1) = SecurityDescriptor;
  v30 = 0;
  LODWORD(v41) = 0;
  LODWORD(Buffer) = 24;
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 2u, 2u, 0);
  if ( FileW == -1 )
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
  else
    LastFailureAsHRESULT = v30;
  if ( LastFailureAsHRESULT == -2147024891 )
    LastFailureAsHRESULT = -2130706390;
  v13 = 352;
  v30 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_25;
  v31 = 352;
  if ( WriteFile((HANDLE)FileW, &Buffer, 0x18u, &NumberOfBytesWritten, 0) )
    LastFailureAsHRESULT = v30;
  else
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
  if ( LastFailureAsHRESULT == -2147024891 )
    LastFailureAsHRESULT = -2130706390;
  v13 = 363;
  v30 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_25;
  v31 = 363;
  v13 = 365;
  if ( NumberOfBytesWritten != 24 )
  {
    LastFailureAsHRESULT = -2130706430;
    v30 = -2130706430;
LABEL_25:
    v32 = v13;
    goto LABEL_37;
  }
  v30 = 0;
  v31 = 365;
  v14 = IsNTFS(a1);
  v30 = v14;
  LastFailureAsHRESULT = v14;
  v13 = 367;
  if ( v14 < 0 )
    goto LABEL_25;
  v31 = 367;
  LastFailureAsHRESULT = SxCheckVolumeCompressedEncrypted(a1, &v36, &v34);
  v30 = LastFailureAsHRESULT;
  v13 = 370;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_25;
  v31 = 370;
  *a3 |= (v14 == 0 ? 4 : 0) | (v34 != 0 ? 2 : 0);
LABEL_37:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle((HANDLE)FileW);
    FileW = -1;
    SxDeleteFile(lpFileName[0]);
    LastFailureAsHRESULT = v30;
  }
LABEL_39:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    LastFailureAsHRESULT = v30;
    SecurityDescriptor = 0;
  }
  CBsString::_Release((CBsString *)v37);
  CBsString::_Release((CBsString *)v42);
  CBsString::_Release((CBsString *)lpFileName);
  CBsString::_Release((CBsString *)v39);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v30);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800148dc  mov     [rsp-8+arg_8], rbx
0x1800148e1  push    rbp
0x1800148e2  push    rsi
0x1800148e3  push    rdi
0x1800148e4  push    r12
0x1800148e6  push    r13
0x1800148e8  push    r14
0x1800148ea  push    r15
0x1800148ec  lea     rbp, [rsp-20h]
0x1800148f1  sub     rsp, 120h
0x1800148f8  mov     rax, cs:__security_cookie
0x1800148ff  xor     rax, rsp
0x180014902  mov     [rbp+50h+var_38], rax
0x180014906  mov     r15, r8
0x180014909  lea     rdx, aCsdcontrollerV_1; "CSdController::_VerifyUncDeviceAccess"
0x180014910  mov     r14, rcx
0x180014913  mov     r8d, 118h; unsigned __int16
0x180014919  lea     rcx, [rsp+150h+var_F0]; this
0x18001491e  mov     r9d, 1; unsigned __int16
0x180014924  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014929  xor     r12d, r12d
0x18001492c  lea     rcx, qword_180028260
0x180014933  xor     eax, eax
0x180014935  mov     [rbp+50h+var_80], rcx
0x180014939  xorps   xmm0, xmm0
0x18001493c  mov     [rbp+50h+var_60], rax
0x180014940  movups  [rbp+50h+Buffer], xmm0
0x180014944  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014948  mov     [rbp+50h+var_78], r12
0x18001494c  mov     [rbp+50h+lpFileName], rcx
0x180014950  mov     eax, 128h
0x180014955  mov     [rbp+50h+var_88], r12
0x180014959  mov     [rbp+50h+var_58], rcx
0x18001495d  mov     [rbp+50h+var_50], r12
0x180014961  mov     [rbp+50h+SecurityDescriptor], r12
0x180014965  mov     [rbp+50h+NumberOfBytesWritten], r12d
0x180014969  mov     [rbp+50h+var_A0], rcx
0x18001496d  mov     [rbp+50h+var_98], r12
0x180014971  mov     [rbp+50h+var_A8], r12d
0x180014975  mov     [rbp+50h+var_B4], r12d
0x180014979  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180014980  movdqu  xmmword ptr [rbp+50h+pguid.Data1], xmm0
0x180014985  test    r14, r14
0x180014988  jnz     short loc_18001499D
0x18001498a  mov     edi, 80070057h
0x18001498f  mov     [rsp+150h+var_F0], edi
0x180014993  mov     [rsp+150h+var_EA], ax
0x180014998  jmp     loc_180014C93
0x18001499d  mov     [rsp+150h+var_EC], ax
0x1800149a2  mov     eax, 129h
0x1800149a7  test    r15, r15
0x1800149aa  jz      short loc_18001498A
0x1800149ac  lea     rcx, [rbp+50h+pguid]; pguid
0x1800149b0  mov     [rsp+150h+var_F0], r12d
0x1800149b5  mov     [rsp+150h+var_EC], ax
0x1800149ba  call    cs:__imp_CoCreateGuid
0x1800149c0  mov     edi, eax
0x1800149c2  mov     [rsp+150h+var_F0], eax
0x1800149c6  test    eax, eax
0x1800149c8  mov     eax, 12Fh
0x1800149cd  js      short loc_180014993
0x1800149cf  lea     rdx, [rbp+50h+pguid]; struct _GUID *
0x1800149d3  mov     [rsp+150h+var_EC], ax
0x1800149d8  lea     rcx, [rbp+50h+var_A0]; this
0x1800149dc  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x1800149e1  mov     edi, eax
0x1800149e3  mov     [rsp+150h+var_F0], eax
0x1800149e7  test    eax, eax
0x1800149e9  mov     eax, 130h
0x1800149ee  js      short loc_180014993
0x1800149f0  mov     r8, [rbp+50h+var_A0]; unsigned __int16 *
0x1800149f4  lea     rcx, [rbp+50h+var_80]; this
0x1800149f8  mov     rdx, r14; unsigned __int16 *
0x1800149fb  mov     [rsp+150h+var_EC], ax
0x180014a00  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180014a05  mov     edi, eax
0x180014a07  mov     [rsp+150h+var_F0], eax
0x180014a0b  test    eax, eax
0x180014a0d  mov     eax, 131h
0x180014a12  js      loc_180014993
0x180014a18  mov     rcx, [rbp+50h+var_80]; unsigned __int16 *
0x180014a1c  xor     r9d, r9d; int
0x180014a1f  xor     r8d, r8d; int
0x180014a22  mov     [rsp+150h+var_EC], ax
0x180014a27  xor     edx, edx; struct _SECURITY_ATTRIBUTES *
0x180014a29  call    ?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z; EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)
0x180014a2e  mov     edi, eax
0x180014a30  mov     r13d, 80070005h
0x180014a36  cmp     eax, r13d
0x180014a39  mov     esi, 8100002Ah
0x180014a3e  mov     eax, 13Ah
0x180014a43  cmovz   edi, esi
0x180014a46  mov     [rsp+150h+var_F0], edi
0x180014a4a  test    edi, edi
0x180014a4c  js      loc_180014993
0x180014a52  mov     rcx, [rbp+50h+var_80]; unsigned __int16 *
0x180014a56  mov     [rsp+150h+var_EC], ax
0x180014a5b  call    ?SxDeleteDirectory@@YAJPEBGH@Z; SxDeleteDirectory(ushort const *,int)
0x180014a60  cmp     eax, r13d
0x180014a63  mov     edi, eax
0x180014a65  mov     eax, 142h
0x180014a6a  cmovz   edi, esi
0x180014a6d  mov     [rsp+150h+var_F0], edi
0x180014a71  test    edi, edi
0x180014a73  js      loc_180014993
0x180014a79  lea     rcx, [rbp+50h+pguid]; pguid
0x180014a7d  mov     [rsp+150h+var_EC], ax
0x180014a82  call    cs:__imp_CoCreateGuid
0x180014a88  mov     edi, eax
0x180014a8a  mov     [rsp+150h+var_F0], eax
0x180014a8e  test    eax, eax
0x180014a90  mov     eax, 145h
0x180014a95  js      loc_180014993
0x180014a9b  lea     rdx, [rbp+50h+pguid]; struct _GUID *
0x180014a9f  mov     [rsp+150h+var_EC], ax
0x180014aa4  lea     rcx, [rbp+50h+var_A0]; this
0x180014aa8  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x180014aad  mov     edi, eax
0x180014aaf  mov     [rsp+150h+var_F0], eax
0x180014ab3  test    eax, eax
0x180014ab5  mov     eax, 146h
0x180014aba  js      loc_180014993
0x180014ac0  mov     r8, [rbp+50h+var_A0]; unsigned __int16 *
0x180014ac4  lea     rcx, [rbp+50h+lpFileName]; this
0x180014ac8  mov     rdx, r14; unsigned __int16 *
0x180014acb  mov     [rsp+150h+var_EC], ax
0x180014ad0  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180014ad5  mov     edi, eax
0x180014ad7  mov     [rsp+150h+var_F0], eax
0x180014adb  test    eax, eax
0x180014add  mov     eax, 147h
0x180014ae2  js      loc_180014993
0x180014ae8  xor     r9d, r9d; SecurityDescriptorSize
0x180014aeb  mov     [rsp+150h+var_EC], ax
0x180014af0  lea     r8, [rbp+50h+SecurityDescriptor]; SecurityDescriptor
0x180014af4  lea     rcx, StringSecurityDescriptor; "D:AR(A;;FR;;;AU)(A;OICI;FA;;;CO)(A;OICI"...
0x180014afb  lea     edx, [r9+1]; StringSDRevision
0x180014aff  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180014b05  test    eax, eax
0x180014b07  jnz     short loc_180014B1E
0x180014b09  call    GetLastFailureAsHRESULT
0x180014b0e  mov     edi, eax
0x180014b10  mov     [rsp+150h+var_F0], eax
0x180014b14  mov     eax, 14Ah
0x180014b19  jmp     loc_180014993
0x180014b1e  mov     rcx, [rbp+50h+lpFileName]; lpFileName
0x180014b22  mov     eax, 14Ah
0x180014b27  mov     [rsp+150h+var_EC], ax
0x180014b2c  mov     esi, 18h
0x180014b31  mov     rax, [rbp+50h+SecurityDescriptor]
0x180014b35  xor     r9d, r9d; lpSecurityAttributes
0x180014b38  mov     qword ptr [rbp+50h+Buffer+8], rax
0x180014b3c  xor     r8d, r8d; dwShareMode
0x180014b3f  mov     [rsp+150h+hTemplateFile], r12; hTemplateFile
0x180014b44  mov     edx, 0C0000000h; dwDesiredAccess
0x180014b49  lea     eax, [rsi-16h]
0x180014b4c  mov     [rsp+150h+var_F0], r12d
0x180014b51  mov     dword ptr [rsp+150h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180014b55  mov     [rsp+150h+dwCreationDisposition], eax; dwCreationDisposition
0x180014b59  mov     dword ptr [rbp+50h+var_60], r12d
0x180014b5d  mov     dword ptr [rbp+50h+Buffer], esi
0x180014b60  call    cs:__imp_CreateFileW
0x180014b66  mov     rbx, rax
0x180014b69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014b6d  jnz     short loc_180014B78
0x180014b6f  call    GetLastFailureAsHRESULT
0x180014b74  mov     edi, eax
0x180014b76  jmp     short loc_180014B7C
0x180014b78  mov     edi, [rsp+150h+var_F0]
0x180014b7c  cmp     edi, r13d
0x180014b7f  mov     eax, 8100002Ah
0x180014b84  cmovz   edi, eax
0x180014b87  mov     eax, 160h
0x180014b8c  mov     [rsp+150h+var_F0], edi
0x180014b90  test    edi, edi
0x180014b92  jns     short loc_180014B9E
0x180014b94  mov     [rsp+150h+var_EA], ax
0x180014b99  jmp     loc_180014C6F
0x180014b9e  lea     r9, [rbp+50h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180014ba2  mov     [rsp+150h+var_EC], ax
0x180014ba7  mov     r8d, esi; nNumberOfBytesToWrite
0x180014baa  mov     qword ptr [rsp+150h+dwCreationDisposition], r12; lpOverlapped
0x180014baf  lea     rdx, [rbp+50h+Buffer]; lpBuffer
0x180014bb3  mov     rcx, rbx; hFile
0x180014bb6  call    cs:__imp_WriteFile
0x180014bbc  test    eax, eax
0x180014bbe  jnz     short loc_180014BC9
0x180014bc0  call    GetLastFailureAsHRESULT
0x180014bc5  mov     edi, eax
0x180014bc7  jmp     short loc_180014BCD
0x180014bc9  mov     edi, [rsp+150h+var_F0]
0x180014bcd  cmp     edi, r13d
0x180014bd0  mov     eax, 8100002Ah
0x180014bd5  cmovz   edi, eax
0x180014bd8  mov     eax, 16Bh
0x180014bdd  mov     [rsp+150h+var_F0], edi
0x180014be1  test    edi, edi
0x180014be3  js      short loc_180014B94
0x180014be5  mov     [rsp+150h+var_EC], ax
0x180014bea  mov     eax, 16Dh
0x180014bef  cmp     [rbp+50h+NumberOfBytesWritten], esi
0x180014bf2  jz      short loc_180014BFF
0x180014bf4  mov     edi, 81000002h
0x180014bf9  mov     [rsp+150h+var_F0], edi
0x180014bfd  jmp     short loc_180014B94
0x180014bff  mov     rcx, r14; lpFileName
0x180014c02  mov     [rsp+150h+var_F0], r12d
0x180014c07  mov     [rsp+150h+var_EC], ax
0x180014c0c  call    ?IsNTFS@@YAJPEBG@Z; IsNTFS(ushort const *)
0x180014c11  mov     esi, eax
0x180014c13  mov     [rsp+150h+var_F0], eax
0x180014c17  mov     edi, eax
0x180014c19  test    eax, eax
0x180014c1b  mov     eax, 16Fh
0x180014c20  js      loc_180014B94
0x180014c26  lea     r8, [rbp+50h+var_B4]; int *
0x180014c2a  mov     [rsp+150h+var_EC], ax
0x180014c2f  lea     rdx, [rbp+50h+var_A8]; int *
0x180014c33  mov     rcx, r14; unsigned __int16 *
0x180014c36  call    ?SxCheckVolumeCompressedEncrypted@@YAJPEBGPEAH1@Z; SxCheckVolumeCompressedEncrypted(ushort const *,int *,int *)
0x180014c3b  mov     edi, eax
0x180014c3d  mov     [rsp+150h+var_F0], eax
0x180014c41  test    eax, eax
0x180014c43  mov     eax, 172h
0x180014c48  js      loc_180014B94
0x180014c4e  neg     esi
0x180014c50  mov     [rsp+150h+var_EC], ax
0x180014c55  mov     eax, [rbp+50h+var_B4]
0x180014c58  sbb     r8d, r8d
0x180014c5b  not     r8d
0x180014c5e  and     r8d, 4
0x180014c62  neg     eax
0x180014c64  sbb     edx, edx
0x180014c66  and     edx, 2
0x180014c69  or      edx, r8d
0x180014c6c  or      [r15], edx
0x180014c6f  lea     rax, [rbx-1]
0x180014c73  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014c77  ja      short loc_180014C93
0x180014c79  mov     rcx, rbx; hObject
0x180014c7c  call    cs:__imp_CloseHandle
0x180014c82  mov     rcx, [rbp+50h+lpFileName]; lpFileName
0x180014c86  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014c8a  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x180014c8f  mov     edi, [rsp+150h+var_F0]
0x180014c93  mov     rcx, [rbp+50h+SecurityDescriptor]; hMem
0x180014c97  test    rcx, rcx
0x180014c9a  jz      short loc_180014CAA
0x180014c9c  call    cs:__imp_LocalFree
0x180014ca2  mov     edi, [rsp+150h+var_F0]
0x180014ca6  mov     [rbp+50h+SecurityDescriptor], r12
0x180014caa  lea     rcx, [rbp+50h+var_A0]; this
0x180014cae  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180014cb3  lea     rcx, [rbp+50h+var_58]; this
0x180014cb7  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180014cbc  lea     rcx, [rbp+50h+lpFileName]; this
0x180014cc0  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180014cc5  lea     rcx, [rbp+50h+var_80]; this
0x180014cc9  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180014cce  lea     rcx, [rbx-1]
0x180014cd2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180014cd6  ja      short loc_180014CE1
0x180014cd8  mov     rcx, rbx; hObject
0x180014cdb  call    cs:__imp_CloseHandle
0x180014ce1  lea     rcx, [rsp+150h+var_F0]; this
0x180014ce6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180014ceb  mov     eax, edi
0x180014ced  mov     rcx, [rbp+50h+var_38]
0x180014cf1  xor     rcx, rsp; StackCookie
0x180014cf4  call    __security_check_cookie
0x180014cf9  mov     rbx, [rsp+150h+arg_8]
0x180014d01  add     rsp, 120h
0x180014d08  pop     r15
0x180014d0a  pop     r14
0x180014d0c  pop     r13
0x180014d0e  pop     r12
0x180014d10  pop     rdi
0x180014d11  pop     rsi
0x180014d12  pop     rbp
0x180014d13  retn
```
