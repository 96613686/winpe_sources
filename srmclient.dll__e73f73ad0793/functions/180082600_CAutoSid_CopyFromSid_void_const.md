# CAutoSid::CopyFromSid(void * const)

- ea: `0x180082600`
- end: `0x1800827dc`
- name: `?CopyFromSid@CAutoSid@@QEAAXQEAX@Z`
- size: `476`
- prototype: `void(CAutoSid *__hidden this, void *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800a9e40`

## callees

- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180075034`
- `0x180082388`
- `0x180082600`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180082729`
- `KERNEL32!LocalFree` at `0x180082729`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800826aa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800826aa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008270d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008270d`

## string_xrefs

- `0x180082642`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x1800827b6`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x18008264e`: `CAutoSid::CopyFromSid`
- `0x1800827a8`: `CAutoSid::CopyFromSid`
- `0x1800827c8`: `CopySid`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CAutoSid::CopyFromSid(CAutoSid *this, void *const a2)
{
  __int64 LengthSid; // rbx
  PSID v5; // r14
  void *v6; // rcx
  __int64 v7; // rax
  void **v8; // [rsp+40h] [rbp-C0h] BYREF
  PSID pDestinationSid; // [rsp+48h] [rbp-B8h]
  _QWORD *v10; // [rsp+50h] [rbp-B0h]
  _QWORD v11[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v12; // [rsp+70h] [rbp-90h]
  int v13; // [rsp+74h] [rbp-8Ch]
  int v14; // [rsp+78h] [rbp-88h]
  _BYTE v15[96]; // [rsp+80h] [rbp-80h] BYREF
  int v16; // [rsp+E0h] [rbp-20h]
  _QWORD v17[22]; // [rsp+F0h] [rbp-10h] BYREF

  v10 = v11;
  v11[0] = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
  v11[1] = L"CAutoSid::CopyFromSid";
  v11[2] = L"SECSECRC";
  v12 = 1392;
  v13 = 17;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v17, (const struct CSrmDebugInfo *)v11, 0);
  LengthSid = GetLengthSid(a2);
  pDestinationSid = 0;
  v8 = &CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable';
  CSrmAutoLocalPtr_Storage<_SID *>::AllocateBytes(&v8, LengthSid);
  v5 = pDestinationSid;
  if ( !CopySid(LengthSid, pDestinationSid, a2) )
  {
    v10 = v11;
    v7 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v11,
           (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
           (__int64)L"SECSECRC",
           (__int64)L"CAutoSid::CopyFromSid",
           1405,
           10);
    CSrmFunctionTracer::TranslateWin32Error(v17, v7, L"CopySid");
  }
  pDestinationSid = 0;
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
    LocalFree(v6);
  *((_QWORD *)this + 1) = v5;
  v8 = &CSrmAutoLocalPtr_Storage<void *>::`vftable';
  pDestinationSid = 0;
  v17[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v17);
}

```

## disassembly

```asm
0x180082600  mov     [rsp-8+arg_10], rbx
0x180082605  mov     [rsp-8+arg_18], rsi
0x18008260a  push    rbp
0x18008260b  push    rdi
0x18008260c  push    r12
0x18008260e  push    r13
0x180082610  push    r14
0x180082612  lea     rbp, [rsp-0B0h]
0x18008261a  sub     rsp, 1B0h
0x180082621  mov     rax, cs:__security_cookie
0x180082628  xor     rax, rsp
0x18008262b  mov     [rbp+0D0h+var_30], rax
0x180082632  mov     rdi, rdx
0x180082635  mov     rsi, rcx
0x180082638  lea     rax, [rsp+1D0h+var_178]
0x18008263d  mov     [rsp+1D0h+var_180], rax
0x180082642  lea     rax, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x180082649  mov     [rsp+1D0h+var_178], rax
0x18008264e  lea     rax, aCautosidCopyfr; "CAutoSid::CopyFromSid"
0x180082655  mov     [rsp+1D0h+var_170], rax
0x18008265a  lea     rax, aSecsecrc; "SECSECRC"
0x180082661  mov     [rsp+1D0h+var_168], rax
0x180082666  mov     [rsp+1D0h+var_160], 570h
0x18008266e  mov     [rsp+1D0h+var_15C], 11h
0x180082676  mov     [rsp+1D0h+var_158], 0FFh
0x18008267e  mov     [rbp+0D0h+var_F0], 1000000h
0x180082685  xor     edx, edx; Val
0x180082687  lea     r8d, [rdx+60h]; Size
0x18008268b  lea     rcx, [rbp+0D0h+var_150]; void *
0x18008268f  call    memset_0
0x180082694  nop
0x180082695  xor     r8d, r8d
0x180082698  lea     rdx, [rsp+1D0h+var_178]
0x18008269d  lea     rcx, [rbp+0D0h+var_E0]
0x1800826a1  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800826a6  nop
0x1800826a7  mov     rcx, rdi; pSid
0x1800826aa  call    cs:__imp_GetLengthSid
0x1800826b0  mov     ebx, eax
0x1800826b2  lea     r12, ??_7?$CSrmAutoLocalPtr_Storage@PEAX@@6B@; const CSrmAutoLocalPtr_Storage<void *>::`vftable'
0x1800826b9  mov     [rsp+1D0h+var_190], r12
0x1800826be  mov     [rsp+1D0h+pDestinationSid], 0
0x1800826c7  lea     rax, ??_7?$CSrmAutoLocalPtr_Storage@PEAE@@6B@; const CSrmAutoLocalPtr_Storage<uchar *>::`vftable'
0x1800826ce  mov     [rsp+1D0h+var_190], rax
0x1800826d3  lea     r13, ??_7?$CSrmAuto@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@V?$CSrmAutoLocalPtr_Storage@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@@@6B@; const CSrmAuto<_FCI_ADS_NON_SECURE_PROPERTY *,CSrmAutoLocalPtr_Storage<_FCI_ADS_NON_SECURE_PROPERTY *>>::`vftable'
0x1800826da  mov     [rsp+1D0h+var_190], r13
0x1800826df  mov     [rsp+1D0h+pDestinationSid], 0
0x1800826e8  lea     rax, ??_7?$CSrmAutoLocalPtr@PEAU_FCI_ADS_NON_SECURE_PROPERTY@@@@6B@; const CSrmAutoLocalPtr<_FCI_ADS_NON_SECURE_PROPERTY *>::`vftable'
0x1800826ef  mov     [rsp+1D0h+var_190], rax
0x1800826f4  mov     edx, ebx
0x1800826f6  lea     rcx, [rsp+1D0h+var_190]
0x1800826fb  call    ?AllocateBytes@?$CSrmAutoLocalPtr_Storage@PEAU_SID@@@@QEAAX_K@Z; CSrmAutoLocalPtr_Storage<_SID *>::AllocateBytes(unsigned __int64)
0x180082700  mov     r14, [rsp+1D0h+pDestinationSid]
0x180082705  mov     r8, rdi; pSourceSid
0x180082708  mov     rdx, r14; pDestinationSid
0x18008270b  mov     ecx, ebx; nDestinationSidLength
0x18008270d  call    cs:__imp_CopySid
0x180082713  test    eax, eax
0x180082715  jz      short loc_18008278E
0x180082717  mov     [rsp+1D0h+pDestinationSid], 0
0x180082720  mov     rcx, [rsi+8]; hMem
0x180082724  test    rcx, rcx
0x180082727  jz      short loc_18008272F
0x180082729  call    cs:__imp_LocalFree
0x18008272f  mov     [rsi+8], r14
0x180082733  mov     [rsp+1D0h+var_190], r13
0x180082738  mov     [rsp+1D0h+pDestinationSid], 0
0x180082741  mov     [rsp+1D0h+var_190], r12
0x180082746  mov     [rsp+1D0h+pDestinationSid], 0
0x18008274f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180082756  mov     [rbp+0D0h+var_E0], rax
0x18008275a  lea     rcx, [rbp+0D0h+var_E0]; this
0x18008275e  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180082763  mov     rcx, [rbp+0D0h+var_30]
0x18008276a  xor     rcx, rsp; StackCookie
0x18008276d  call    __security_check_cookie
0x180082772  lea     r11, [rsp+1D0h+var_20]
0x18008277a  mov     rbx, [r11+40h]
0x18008277e  mov     rsi, [r11+48h]
0x180082782  mov     rsp, r11
0x180082785  pop     r14
0x180082787  pop     r13
0x180082789  pop     r12
0x18008278b  pop     rdi
0x18008278c  pop     rbp
0x18008278d  retn
0x18008278e  lea     rax, [rsp+1D0h+var_178]
0x180082793  mov     [rsp+1D0h+var_180], rax
0x180082798  mov     [rsp+1D0h+var_1A8], 0Ah
0x1800827a0  mov     [rsp+1D0h+var_1B0], 57Dh
0x1800827a8  lea     r9, aCautosidCopyfr; "CAutoSid::CopyFromSid"
0x1800827af  lea     r8, aSecsecrc; "SECSECRC"
0x1800827b6  lea     rdx, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x1800827bd  lea     rcx, [rsp+1D0h+var_178]
0x1800827c2  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800827c7  nop
0x1800827c8  lea     r8, aCopysid; "CopySid"
0x1800827cf  mov     rdx, rax
0x1800827d2  lea     rcx, [rbp+0D0h+var_E0]
0x1800827d6  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
```
