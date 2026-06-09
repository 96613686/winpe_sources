# CZipBackupFile::AddFileStreamFromDisk(ushort const *,ushort const *,_MSD_FILE_INFO *,ISdReadObj *,unsigned __int64 *)

- ea: `0x180003d30`
- end: `0x180003ffd`
- name: `?AddFileStreamFromDisk@CZipBackupFile@@UEAAJPEBG0PEAU_MSD_FILE_INFO@@PEAUISdReadObj@@PEA_K@Z`
- size: `717`
- prototype: `__int64 __usercall@<rax>(CZipBackupFile *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct _MSD_FILE_INFO *@<r9>, struct ISdReadObj *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003c80`
- `0x180003d30`
- `0x180006924`
- `0x180006bc8`
- `0x180072e08`
- `0x180072f14`
- `0x180073344`
- `0x18009df24`
- `0x18009e904`

## import_xrefs

- `KERNEL32!GetACP` at `0x180003eb6`
- `KERNEL32!GetACP` at `0x180003f2d`
- `KERNEL32!GetACP` at `0x180003eb6`
- `KERNEL32!GetACP` at `0x180003f2d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003e08`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003f92`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003e08`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003f92`
- `ole32!CoTaskMemFree` at `0x180003e1d`
- `ole32!CoTaskMemFree` at `0x180003f19`
- `ole32!CoTaskMemFree` at `0x180003fc6`
- `ole32!CoTaskMemFree` at `0x180003e1d`
- `ole32!CoTaskMemFree` at `0x180003f19`
- `ole32!CoTaskMemFree` at `0x180003fc6`

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
  struct ISdReadObj *v12; // rbx
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
    0x531u,
    1u);
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
  if ( !a3 || (v24 = 1340, v11 = 1341, !a4) || (v24 = 1341, v12 = a5, v11 = 1342, !a5) || (v24 = 1342, v11 = 1343, !v10) )
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
  ATL::CComPtr<ISdBackupSetRecord>::operator=((char *)this + 56, v12);
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
0x180003d30  mov     [rsp-28h+arg_0], rbx
0x180003d35  mov     [rsp-28h+arg_10], rsi
0x180003d3a  push    rbp
0x180003d3b  push    rdi
0x180003d3c  push    r12
0x180003d3e  push    r14
0x180003d40  push    r15
0x180003d42  mov     rbp, rsp
0x180003d45  sub     rsp, 80h
0x180003d4c  mov     r12, r9
0x180003d4f  mov     r15, r8
0x180003d52  mov     r14, rdx
0x180003d55  mov     rdi, rcx
0x180003d58  mov     r9d, 1; unsigned __int16
0x180003d5e  mov     r8d, 531h; unsigned __int16
0x180003d64  lea     rdx, aCzipbackupfile_11; "CZipBackupFile::AddFileStreamFromDisk"
0x180003d6b  lea     rcx, [rbp+var_38]; this
0x180003d6f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180003d74  mov     [rbp+pv], 0
0x180003d7c  mov     [rbp+arg_8], 0
0x180003d83  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180003d8b  mov     qword ptr [rbp+var_48.dwLowDateTime], 0
0x180003d93  mov     rsi, [rbp+arg_28]
0x180003d97  test    rsi, rsi
0x180003d9a  jz      short loc_180003DA3
0x180003d9c  mov     qword ptr [rsi], 0
0x180003da3  mov     eax, 53Bh
0x180003da8  test    r14, r14
0x180003dab  jnz     short loc_180003DBD
0x180003dad  mov     [rbp+var_38], 80070057h
0x180003db4  mov     [rbp+var_32], ax
0x180003db8  jmp     loc_180003FD2
0x180003dbd  mov     [rbp+var_34], ax
0x180003dc1  mov     eax, 53Ch
0x180003dc6  test    r15, r15
0x180003dc9  jz      short loc_180003DAD
0x180003dcb  mov     [rbp+var_34], ax
0x180003dcf  mov     eax, 53Dh
0x180003dd4  test    r12, r12
0x180003dd7  jz      short loc_180003DAD
0x180003dd9  mov     [rbp+var_34], ax
0x180003ddd  mov     rbx, [rbp+arg_20]
0x180003de1  mov     eax, 53Eh
0x180003de6  test    rbx, rbx
0x180003de9  jz      short loc_180003DAD
0x180003deb  mov     [rbp+var_34], ax
0x180003def  mov     eax, 53Fh
0x180003df4  test    rsi, rsi
0x180003df7  jz      short loc_180003DAD
0x180003df9  mov     [rbp+var_38], 0
0x180003e00  mov     [rbp+var_34], ax
0x180003e04  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003e08  call    cs:__imp_GetSystemTimeAsFileTime
0x180003e0f  nop     dword ptr [rax+rax+00h]
0x180003e14  mov     rcx, [rdi+78h]; pv
0x180003e18  test    rcx, rcx
0x180003e1b  jz      short loc_180003E31
0x180003e1d  call    cs:__imp_CoTaskMemFree
0x180003e24  nop     dword ptr [rax+rax+00h]
0x180003e29  mov     qword ptr [rdi+78h], 0
0x180003e31  lea     rcx, [rdi+38h]
0x180003e35  mov     rdx, rbx
0x180003e38  call    ??4?$CComPtr@UISdBackupSetRecord@@@ATL@@QEAAPEAUISdBackupSetRecord@@PEAU2@@Z; ATL::CComPtr<ISdBackupSetRecord>::operator=(ISdBackupSetRecord *)
0x180003e3d  lea     rcx, [rdi+58h]; this
0x180003e41  mov     rdx, r14; unsigned __int16 *
0x180003e44  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180003e49  mov     [rbp+var_38], eax
0x180003e4c  test    eax, eax
0x180003e4e  mov     eax, 54Bh
0x180003e53  js      loc_180003DB4
0x180003e59  mov     [rbp+var_34], ax
0x180003e5d  lea     rbx, [rdi+68h]
0x180003e61  mov     rdx, r15; unsigned __int16 *
0x180003e64  mov     rcx, rbx; this
0x180003e67  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180003e6c  mov     [rbp+var_38], eax
0x180003e6f  test    eax, eax
0x180003e71  mov     eax, 54Dh
0x180003e76  js      loc_180003DB4
0x180003e7c  mov     [rbp+var_34], ax
0x180003e80  mov     rax, [rdi+48h]
0x180003e84  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x180003e89  mov     r9, r14; unsigned __int16 *
0x180003e8c  mov     r8d, 4E2Bh; unsigned int
0x180003e92  mov     rdx, cs:hInstance; HINSTANCE
0x180003e99  lea     rcx, [rbp+var_38]; this
0x180003e9d  call    ?SetContext@CSxFunctionTracer@@QEAAJPEAUHINSTANCE__@@KPEBG1@Z; CSxFunctionTracer::SetContext(HINSTANCE__ *,ulong,ushort const *,ushort const *)
0x180003ea2  mov     [rbp+var_38], eax
0x180003ea5  test    eax, eax
0x180003ea7  mov     eax, 54Fh
0x180003eac  js      loc_180003DB4
0x180003eb2  mov     [rbp+var_34], ax
0x180003eb6  call    cs:__imp_GetACP
0x180003ebd  nop     dword ptr [rax+rax+00h]
0x180003ec2  mov     edx, eax; unsigned int
0x180003ec4  lea     r9, [rbp+arg_8]; unsigned int *
0x180003ec8  lea     r8, [rbp+pv]; char **
0x180003ecc  mov     rcx, rbx; this
0x180003ecf  call    ?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z; CBsString::ConvertMBS(uint,char * *,ulong *)
0x180003ed4  mov     [rbp+var_38], eax
0x180003ed7  test    eax, eax
0x180003ed9  mov     eax, 551h
0x180003ede  jns     short loc_180003EED
0x180003ee0  mov     [rbp+var_32], ax
0x180003ee4  mov     rbx, [rbp+pv]
0x180003ee8  jmp     loc_180003FBE
0x180003eed  mov     [rbp+var_34], ax
0x180003ef1  cmp     [rbp+arg_8], 103h
0x180003ef8  jbe     short loc_180003F5B
0x180003efa  mov     rdx, rbx; struct CBsString *
0x180003efd  mov     rcx, rdi; this
0x180003f00  call    ?_GenerateFriendlyNameInZip@CZipBackupFile@@AEAAJPEAVCBsString@@@Z; CZipBackupFile::_GenerateFriendlyNameInZip(CBsString *)
0x180003f05  mov     [rbp+var_38], eax
0x180003f08  test    eax, eax
0x180003f0a  mov     eax, 555h
0x180003f0f  js      short loc_180003EE0
0x180003f11  mov     [rbp+var_34], ax
0x180003f15  mov     rcx, [rbp+pv]; pv
0x180003f19  call    cs:__imp_CoTaskMemFree
0x180003f20  nop     dword ptr [rax+rax+00h]
0x180003f25  mov     [rbp+pv], 0
0x180003f2d  call    cs:__imp_GetACP
0x180003f34  nop     dword ptr [rax+rax+00h]
0x180003f39  mov     edx, eax; unsigned int
0x180003f3b  lea     r9, [rbp+arg_8]; unsigned int *
0x180003f3f  lea     r8, [rbp+pv]; char **
0x180003f43  mov     rcx, rbx; this
0x180003f46  call    ?ConvertMBS@CBsString@@QEAAJIPEAPEADPEAK@Z; CBsString::ConvertMBS(uint,char * *,ulong *)
0x180003f4b  mov     [rbp+var_38], eax
0x180003f4e  test    eax, eax
0x180003f50  mov     eax, 559h
0x180003f55  js      short loc_180003EE0
0x180003f57  mov     [rbp+var_34], ax
0x180003f5b  mov     rax, [rbp+pv]
0x180003f5f  mov     [rdi+78h], rax
0x180003f63  xor     ebx, ebx
0x180003f65  mov     rdx, r12; struct _MSD_FILE_INFO *
0x180003f68  mov     rcx, rdi; this
0x180003f6b  call    ?_ProcessStream@CZipBackupFile@@AEAAJPEAU_MSD_FILE_INFO@@@Z; CZipBackupFile::_ProcessStream(_MSD_FILE_INFO *)
0x180003f70  mov     [rbp+var_38], eax
0x180003f73  test    eax, eax
0x180003f75  mov     eax, 55Fh
0x180003f7a  js      loc_180003DB4
0x180003f80  mov     [rbp+var_34], ax
0x180003f84  mov     rax, [rdi+0B8h]
0x180003f8b  mov     [rsi], rax
0x180003f8e  lea     rcx, [rbp+var_48]; lpSystemTimeAsFileTime
0x180003f92  call    cs:__imp_GetSystemTimeAsFileTime
0x180003f99  nop     dword ptr [rax+rax+00h]
0x180003f9e  mov     rdx, qword ptr [rbp+var_48.dwLowDateTime]
0x180003fa2  sub     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003fa6  mov     rax, 346DC5D63886594Bh
0x180003fb0  mul     rdx
0x180003fb3  shr     rdx, 0Bh
0x180003fb7  add     [rdi+0C8h], rdx
0x180003fbe  test    rbx, rbx
0x180003fc1  jz      short loc_180003FD2
0x180003fc3  mov     rcx, rbx; pv
0x180003fc6  call    cs:__imp_CoTaskMemFree
0x180003fcd  nop     dword ptr [rax+rax+00h]
0x180003fd2  mov     ebx, [rbp+var_38]
0x180003fd5  lea     rcx, [rbp+var_38]; this
0x180003fd9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180003fde  mov     eax, ebx
0x180003fe0  lea     r11, [rsp+80h+var_s0]
0x180003fe8  mov     rbx, [r11+30h]
0x180003fec  mov     rsi, [r11+40h]
0x180003ff0  mov     rsp, r11
0x180003ff3  pop     r15
0x180003ff5  pop     r14
0x180003ff7  pop     r12
0x180003ff9  pop     rdi
0x180003ffa  pop     rbp
0x180003ffb  retn
```
