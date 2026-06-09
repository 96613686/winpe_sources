# CZipBackupFile::AddFileStreamFromDisk(ushort const *,ushort const *,_MSD_FILE_INFO *,ISdReadObj *,unsigned __int64 *)

- ea: `0x180003c10`
- end: `0x180003eb2`
- name: `?AddFileStreamFromDisk@CZipBackupFile@@UEAAJPEBG0PEAU_MSD_FILE_INFO@@PEAUISdReadObj@@PEA_K@Z`
- size: `674`
- prototype: `__int64 __usercall@<rax>(CZipBackupFile *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct _MSD_FILE_INFO *@<r9>, struct ISdReadObj *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003b60`
- `0x180003c10`
- `0x1800067f0`
- `0x180006a94`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18007038c`
- `0x180099904`
- `0x18009a24c`

## import_xrefs

- `KERNEL32!GetACP` at `0x180003d8a`
- `KERNEL32!GetACP` at `0x180003df5`
- `KERNEL32!GetACP` at `0x180003d8a`
- `KERNEL32!GetACP` at `0x180003df5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003ce8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003e54`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003ce8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003e54`
- `ole32!CoTaskMemFree` at `0x180003cf7`
- `ole32!CoTaskMemFree` at `0x180003de7`
- `ole32!CoTaskMemFree` at `0x180003e82`
- `ole32!CoTaskMemFree` at `0x180003cf7`
- `ole32!CoTaskMemFree` at `0x180003de7`
- `ole32!CoTaskMemFree` at `0x180003e82`

## pseudocode

```c
__int64 __fastcall CZipBackupFile::AddFileStreamFromDisk(
        CZipBackupFile *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _MSD_FILE_INFO *a4,
        struct ISdReadObj *a5,
        unsigned __int64 *a6)
{
  unsigned __int64 *v10; // rsi
  __int16 v11; // ax
  struct IUnknown *v12; // rbx
  void *v13; // rcx
  UINT ACP; // eax
  __int16 v15; // ax
  void *v16; // rbx
  UINT v17; // eax
  unsigned int v18; // ebx
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  struct _FILETIME v21; // [rsp+38h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-40h] BYREF
  int FriendlyNameInZip; // [rsp+48h] [rbp-38h] BYREF
  __int16 v24; // [rsp+4Ch] [rbp-34h]
  __int16 v25; // [rsp+4Eh] [rbp-32h]
  unsigned int v26; // [rsp+B8h] [rbp+38h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&FriendlyNameInZip,
    "CZipBackupFile::AddFileStreamFromDisk",
    1329,
    1);
  pv = 0;
  v26 = 0;
  SystemTimeAsFileTime = 0;
  v21 = 0;
  v10 = a6;
  if ( a6 )
    *a6 = 0;
  v11 = 1339;
  if ( !a2 )
    goto LABEL_4;
  v24 = 1339;
  v11 = 1340;
  if ( !a3
    || (v24 = 1340, v11 = 1341, !a4)
    || (v24 = 1341, v12 = (struct IUnknown *)a5, v11 = 1342, !a5)
    || (v24 = 1342, v11 = 1343, !v10) )
  {
LABEL_4:
    FriendlyNameInZip = -2147024809;
    goto LABEL_5;
  }
  FriendlyNameInZip = 0;
  v24 = 1343;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v13 = (void *)*((_QWORD *)this + 15);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)this + 15) = 0;
  }
  ATL::CComPtr<ISdBackupSetRecord>::operator=((struct IUnknown **)this + 7, v12);
  FriendlyNameInZip = CBsString::Set((CZipBackupFile *)((char *)this + 88), a2);
  v11 = 1355;
  if ( FriendlyNameInZip < 0 )
    goto LABEL_5;
  v24 = 1355;
  FriendlyNameInZip = CBsString::Set((CZipBackupFile *)((char *)this + 104), a3);
  v11 = 1357;
  if ( FriendlyNameInZip < 0 )
    goto LABEL_5;
  v24 = 1357;
  FriendlyNameInZip = CSxFunctionTracer::SetContext(
                        (CSxFunctionTracer *)&FriendlyNameInZip,
                        hInstance,
                        0x4E2Bu,
                        a2,
                        *((const unsigned __int16 **)this + 9));
  v11 = 1359;
  if ( FriendlyNameInZip < 0 )
    goto LABEL_5;
  v24 = 1359;
  ACP = GetACP();
  FriendlyNameInZip = CBsString::ConvertMBS((CZipBackupFile *)((char *)this + 104), ACP, (char **)&pv, &v26);
  v15 = 1361;
  if ( FriendlyNameInZip < 0 )
  {
LABEL_16:
    v25 = v15;
    v16 = pv;
    goto LABEL_23;
  }
  v24 = 1361;
  if ( v26 > 0x103 )
  {
    FriendlyNameInZip = CZipBackupFile::_GenerateFriendlyNameInZip(this, (CZipBackupFile *)((char *)this + 104));
    v15 = 1365;
    if ( FriendlyNameInZip < 0 )
      goto LABEL_16;
    v24 = 1365;
    CoTaskMemFree(pv);
    pv = 0;
    v17 = GetACP();
    FriendlyNameInZip = CBsString::ConvertMBS((CZipBackupFile *)((char *)this + 104), v17, (char **)&pv, &v26);
    v15 = 1369;
    if ( FriendlyNameInZip < 0 )
      goto LABEL_16;
    v24 = 1369;
  }
  *((_QWORD *)this + 15) = pv;
  v16 = 0;
  FriendlyNameInZip = CZipBackupFile::_ProcessStream(this, a4);
  v11 = 1375;
  if ( FriendlyNameInZip < 0 )
  {
LABEL_5:
    v25 = v11;
    goto LABEL_25;
  }
  v24 = 1375;
  *v10 = *((_QWORD *)this + 23);
  GetSystemTimeAsFileTime(&v21);
  *((_QWORD *)this + 25) += (*(_QWORD *)&v21 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL;
LABEL_23:
  if ( v16 )
    CoTaskMemFree(v16);
LABEL_25:
  v18 = FriendlyNameInZip;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&FriendlyNameInZip);
  return v18;
}

```

## disassembly

```asm
0x180003c10  mov     [rsp-28h+arg_0], rbx
0x180003c15  mov     [rsp-28h+arg_10], rsi
0x180003c1a  push    rbp
0x180003c1b  push    rdi
0x180003c1c  push    r12
0x180003c1e  push    r14
0x180003c20  push    r15
0x180003c22  mov     rbp, rsp
0x180003c25  sub     rsp, 80h
0x180003c2c  mov     r12, r9
0x180003c2f  mov     r15, r8
0x180003c32  mov     r14, rdx
0x180003c35  mov     rdi, rcx
0x180003c38  mov     r9d, 1; unsigned __int16
0x180003c3e  mov     r8d, 531h; unsigned __int16
0x180003c44  lea     rdx, aCzipbackupfile_11; "CZipBackupFile::AddFileStreamFromDisk"
0x180003c4b  lea     rcx, [rbp+var_38]; this
0x180003c4f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180003c54  mov     [rbp+pv], 0
0x180003c5c  mov     [rbp+arg_8], 0
0x180003c63  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180003c6b  mov     qword ptr [rbp+var_48.dwLowDateTime], 0
0x180003c73  mov     rsi, [rbp+arg_28]
0x180003c77  test    rsi, rsi
0x180003c7a  jz      short loc_180003C83
0x180003c7c  mov     qword ptr [rsi], 0
0x180003c83  mov     eax, 53Bh
0x180003c88  test    r14, r14
0x180003c8b  jnz     short loc_180003C9D
0x180003c8d  mov     [rbp+var_38], 80070057h
0x180003c94  mov     [rbp+var_32], ax
0x180003c98  jmp     loc_180003E88
0x180003c9d  mov     [rbp+var_34], ax
0x180003ca1  mov     eax, 53Ch
0x180003ca6  test    r15, r15
0x180003ca9  jz      short loc_180003C8D
0x180003cab  mov     [rbp+var_34], ax
0x180003caf  mov     eax, 53Dh
0x180003cb4  test    r12, r12
0x180003cb7  jz      short loc_180003C8D
0x180003cb9  mov     [rbp+var_34], ax
0x180003cbd  mov     rbx, [rbp+arg_20]
0x180003cc1  mov     eax, 53Eh
0x180003cc6  test    rbx, rbx
0x180003cc9  jz      short loc_180003C8D
0x180003ccb  mov     [rbp+var_34], ax
0x180003ccf  mov     eax, 53Fh
0x180003cd4  test    rsi, rsi
0x180003cd7  jz      short loc_180003C8D
0x180003cd9  mov     [rbp+var_38], 0
0x180003ce0  mov     [rbp+var_34], ax
0x180003ce4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003ce8  call    cs:__imp_GetSystemTimeAsFileTime
0x180003cee  mov     rcx, [rdi+78h]; pv
0x180003cf2  test    rcx, rcx
0x180003cf5  jz      short loc_180003D05
0x180003cf7  call    cs:__imp_CoTaskMemFree
0x180003cfd  mov     qword ptr [rdi+78h], 0
0x180003d05  lea     rcx, [rdi+38h]
0x180003d09  mov     rdx, rbx
0x180003d0c  call    ??4?$CComPtr@UISdBackupSetRecord@@@ATL@@QEAAPEAUISdBackupSetRecord@@PEAU2@@Z; ATL::CComPtr<ISdBackupSetRecord>::operator=(ISdBackupSetRecord *)
0x180003d11  lea     rcx, [rdi+58h]; this
0x180003d15  mov     rdx, r14; unsigned __int16 *
0x180003d18  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180003d1d  mov     [rbp+var_38], eax
0x180003d20  test    eax, eax
0x180003d22  mov     eax, 54Bh
0x180003d27  js      loc_180003C94
0x180003d2d  mov     [rbp+var_34], ax
0x180003d31  lea     rbx, [rdi+68h]
0x180003d35  mov     rdx, r15; unsigned __int16 *
0x180003d38  mov     rcx, rbx; this
0x180003d3b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180003d40  mov     [rbp+var_38], eax
0x180003d43  test    eax, eax
0x180003d45  mov     eax, 54Dh
0x180003d4a  js      loc_180003C94
0x180003d50  mov     [rbp+var_34], ax
0x180003d54  mov     rax, [rdi+48h]
0x180003d58  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x180003d5d  mov     r9, r14; unsigned __int16 *
0x180003d60  mov     r8d, 4E2Bh; unsigned int
0x180003d66  mov     rdx, cs:hInstance; HINSTANCE
0x180003d6d  lea     rcx, [rbp+var_38]; this
0x180003d71  call    ?SetContext@CSxFunctionTracer@@QEAAJPEAUHINSTANCE__@@KPEBG1@Z; CSxFunctionTracer::SetContext(HINSTANCE__ *,ulong,ushort const *,ushort const *)
0x180003d76  mov     [rbp+var_38], eax
0x180003d79  test    eax, eax
0x180003d7b  mov     eax, 54Fh
0x180003d80  js      loc_180003C94
0x180003d86  mov     [rbp+var_34], ax
0x180003d8a  call    cs:__imp_GetACP
0x180003d90  mov     edx, eax; unsigned int
0x180003d92  lea     r9, [rbp+arg_8]; unsigned int *
0x180003d96  lea     r8, [rbp+pv]; char **
0x180003d9a  mov     rcx, rbx; this
0x180003d9d  call    ?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z; CBsString::ConvertMBS(uint,char * *,ulong *)
0x180003da2  mov     [rbp+var_38], eax
0x180003da5  test    eax, eax
0x180003da7  mov     eax, 551h
0x180003dac  jns     short loc_180003DBB
0x180003dae  mov     [rbp+var_32], ax
0x180003db2  mov     rbx, [rbp+pv]
0x180003db6  jmp     loc_180003E7A
0x180003dbb  mov     [rbp+var_34], ax
0x180003dbf  cmp     [rbp+arg_8], 103h
0x180003dc6  jbe     short loc_180003E1D
0x180003dc8  mov     rdx, rbx; struct CBsString *
0x180003dcb  mov     rcx, rdi; this
0x180003dce  call    ?_GenerateFriendlyNameInZip@CZipBackupFile@@AEAAJPEAVCBsString@@@Z; CZipBackupFile::_GenerateFriendlyNameInZip(CBsString *)
0x180003dd3  mov     [rbp+var_38], eax
0x180003dd6  test    eax, eax
0x180003dd8  mov     eax, 555h
0x180003ddd  js      short loc_180003DAE
0x180003ddf  mov     [rbp+var_34], ax
0x180003de3  mov     rcx, [rbp+pv]; pv
0x180003de7  call    cs:__imp_CoTaskMemFree
0x180003ded  mov     [rbp+pv], 0
0x180003df5  call    cs:__imp_GetACP
0x180003dfb  mov     edx, eax; unsigned int
0x180003dfd  lea     r9, [rbp+arg_8]; unsigned int *
0x180003e01  lea     r8, [rbp+pv]; char **
0x180003e05  mov     rcx, rbx; this
0x180003e08  call    ?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z; CBsString::ConvertMBS(uint,char * *,ulong *)
0x180003e0d  mov     [rbp+var_38], eax
0x180003e10  test    eax, eax
0x180003e12  mov     eax, 559h
0x180003e17  js      short loc_180003DAE
0x180003e19  mov     [rbp+var_34], ax
0x180003e1d  mov     rax, [rbp+pv]
0x180003e21  mov     [rdi+78h], rax
0x180003e25  xor     ebx, ebx
0x180003e27  mov     rdx, r12; struct _MSD_FILE_INFO *
0x180003e2a  mov     rcx, rdi; this
0x180003e2d  call    ?_ProcessStream@CZipBackupFile@@AEAAJPEAU_MSD_FILE_INFO@@@Z; CZipBackupFile::_ProcessStream(_MSD_FILE_INFO *)
0x180003e32  mov     [rbp+var_38], eax
0x180003e35  test    eax, eax
0x180003e37  mov     eax, 55Fh
0x180003e3c  js      loc_180003C94
0x180003e42  mov     [rbp+var_34], ax
0x180003e46  mov     rax, [rdi+0B8h]
0x180003e4d  mov     [rsi], rax
0x180003e50  lea     rcx, [rbp+var_48]; lpSystemTimeAsFileTime
0x180003e54  call    cs:__imp_GetSystemTimeAsFileTime
0x180003e5a  mov     rdx, qword ptr [rbp+var_48.dwLowDateTime]
0x180003e5e  sub     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003e62  mov     rax, 346DC5D63886594Bh
0x180003e6c  mul     rdx
0x180003e6f  shr     rdx, 0Bh
0x180003e73  add     [rdi+0C8h], rdx
0x180003e7a  test    rbx, rbx
0x180003e7d  jz      short loc_180003E88
0x180003e7f  mov     rcx, rbx; pv
0x180003e82  call    cs:__imp_CoTaskMemFree
0x180003e88  mov     ebx, [rbp+var_38]
0x180003e8b  lea     rcx, [rbp+var_38]; this
0x180003e8f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180003e94  mov     eax, ebx
0x180003e96  lea     r11, [rsp+80h+var_s0]
0x180003e9e  mov     rbx, [r11+30h]
0x180003ea2  mov     rsi, [r11+40h]
0x180003ea6  mov     rsp, r11
0x180003ea9  pop     r15
0x180003eab  pop     r14
0x180003ead  pop     r12
0x180003eaf  pop     rdi
0x180003eb0  pop     rbp
0x180003eb1  retn
```
