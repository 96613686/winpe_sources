# CScanInformation::GetNamespaceVolumePaths(ushort const *,CSrmVssUtil *,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &,CSrmAutoPWSZ &,bool &)

- ea: `0x180050fd0`
- end: `0x180051270`
- name: `?GetNamespaceVolumePaths@CScanInformation@@SAXPEBGPEAVCSrmVssUtil@@AEAVCSrmAutoPWSZ@@222AEA_N@Z`
- size: `672`
- prototype: `void __usercall(const unsigned __int16 *@<rcx>, struct CSrmVssUtil *@<rdx>, struct CSrmAutoPWSZ *@<r8>, struct CSrmAutoPWSZ *@<r9>, struct CSrmAutoPWSZ *, struct CSrmAutoPWSZ *, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180096d3c`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x18000af40`
- `0x180050fd0`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180074d00`
- `0x18007c45c`
- `0x18007fbd8`
- `0x180080580`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800510fc`
- `KERNEL32!GetLastError` at `0x1800510fc`
- `KERNEL32!GetVolumePathNameW` at `0x1800510f0`
- `KERNEL32!GetVolumePathNameW` at `0x1800510f0`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18005109c`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18005109c`

## string_xrefs

- `0x180051028`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x180051248`: `base\fs\fsrm\service\pipeline\namespace.cpp`
- `0x180051259`: `GetVolumePathName`
- `0x180051034`: `CScanInformation::GetNamespaceVolumePaths`
- `0x18005123a`: `CScanInformation::GetNamespaceVolumePaths`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CScanInformation::GetNamespaceVolumePaths(
        const unsigned __int16 *a1,
        struct CSrmVssUtil *a2,
        struct CSrmAutoPWSZ *a3,
        struct CSrmAutoPWSZ *a4,
        struct CSrmAutoPWSZ *a5,
        struct CSrmAutoPWSZ *a6,
        bool *a7)
{
  __int64 v11; // rbx
  signed int LastError; // edx
  bool v13; // dl
  char v14; // al
  char v15; // al
  char Hr; // al
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned int v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v20[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+64h] [rbp-9Ch]
  int v23; // [rsp+68h] [rbp-98h]
  _BYTE v24[96]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+D0h] [rbp-30h]
  _BYTE v26[152]; // [rsp+D8h] [rbp-28h] BYREF
  void **v27; // [rsp+170h] [rbp+70h] BYREF
  int v28; // [rsp+178h] [rbp+78h]

  *(_QWORD *)v19 = v20;
  v20[0] = L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp";
  v20[1] = L"CScanInformation::GetNamespaceVolumePaths";
  v20[2] = L"NAMESPCC";
  v21 = 652;
  v22 = 22;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v27, (const struct CSrmDebugInfo *)v20, 0);
  CSrmAutoPWSZ::CopyFrom(a3, a1);
  PathRemoveFileSpecW(*(LPWSTR *)a3);
  v19[0] = 0;
  if ( !SrmDoesPathExist(a1, v19) )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v27, -2147200252);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v27);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v27, 0x295u, Hr, 0);
  }
  v28 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(*(_QWORD *)a3 + 2 * v11) );
  CSrmAutoPWSZ::Allocate(a4, v11 + 1);
  if ( !GetVolumePathNameW(*(LPCWSTR *)a3, *(LPWSTR *)a4, v11 + 2) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v28 = 0;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v27, LastError);
      v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v27);
      *(_QWORD *)v19 = v26;
      v18 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v26,
              (__int64)L"base\\fs\\fsrm\\service\\pipeline\\namespace.cpp",
              (__int64)L"NAMESPCC",
              (__int64)L"CScanInformation::GetNamespaceVolumePaths",
              683,
              22);
      CSrmFunctionTracer::TranslatePathError(&v27, v18, v17, L"GetVolumePathName");
    }
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v27, -2147024809);
    v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v27);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v27, 0x2A5u, v15, 0);
  }
  CSrmVssUtil::GetAccessAndLiveVolumes(a2, *(const unsigned __int16 **)a4, a5, a6, a7);
  if ( !SrmIsVolumeValid(*(const unsigned __int16 **)a6, v13) )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v27, -2147200250);
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v27);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v27, 0x2BDu, v14, 0);
  }
  v28 = 0;
  v27 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v27);
}

```

## disassembly

```asm
0x180050fd0  push    rbp
0x180050fd2  push    rbx
0x180050fd3  push    rsi
0x180050fd4  push    rdi
0x180050fd5  push    r12
0x180050fd7  push    r13
0x180050fd9  push    r14
0x180050fdb  push    r15
0x180050fdd  lea     rbp, [rsp-138h]
0x180050fe5  sub     rsp, 238h
0x180050fec  mov     rax, cs:__security_cookie
0x180050ff3  xor     rax, rsp
0x180050ff6  mov     [rbp+170h+var_50], rax
0x180050ffd  mov     rdi, r9
0x180051000  mov     rsi, r8
0x180051003  mov     r15, rdx
0x180051006  mov     rbx, rcx
0x180051009  mov     r12, [rbp+170h+arg_20]
0x180051010  mov     r14, [rbp+170h+arg_28]
0x180051017  mov     r13, [rbp+170h+arg_30]
0x18005101e  lea     rax, [rsp+270h+var_228]
0x180051023  mov     qword ptr [rsp+270h+var_230], rax
0x180051028  lea     rax, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x18005102f  mov     [rsp+270h+var_228], rax
0x180051034  lea     rax, aCscaninformati_3; "CScanInformation::GetNamespaceVolumePat"...
0x18005103b  mov     [rsp+270h+var_220], rax
0x180051040  lea     rax, aNamespcc; "NAMESPCC"
0x180051047  mov     [rsp+270h+var_218], rax
0x18005104c  mov     [rsp+270h+var_210], 28Ch
0x180051054  mov     [rsp+270h+var_20C], 16h
0x18005105c  mov     [rsp+270h+var_208], 0FFh
0x180051064  mov     [rbp+170h+var_1A0], 1000000h
0x18005106b  xor     edx, edx; Val
0x18005106d  lea     r8d, [rdx+60h]; Size
0x180051071  lea     rcx, [rsp+270h+var_200]; void *
0x180051076  call    memset_0
0x18005107b  nop
0x18005107c  xor     r8d, r8d
0x18005107f  lea     rdx, [rsp+270h+var_228]
0x180051084  lea     rcx, [rbp+170h+var_100]
0x180051088  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005108d  nop
0x18005108e  mov     rdx, rbx; unsigned __int16 *
0x180051091  mov     rcx, rsi; this
0x180051094  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180051099  mov     rcx, [rsi]; pszPath
0x18005109c  call    cs:__imp_PathRemoveFileSpecW
0x1800510a2  mov     [rsp+270h+var_230], 0
0x1800510aa  mov     eax, [rbp+170h+var_F8]
0x1800510ad  mov     [rbp+170h+var_F8], eax
0x1800510b0  lea     rdx, [rsp+270h+var_230]; unsigned int *
0x1800510b5  mov     rcx, rbx; unsigned __int16 *
0x1800510b8  call    ?SrmDoesPathExist@@YA_NPEBGPEAK@Z; SrmDoesPathExist(ushort const *,ulong *)
0x1800510bd  xor     ecx, ecx
0x1800510bf  test    al, al
0x1800510c1  jz      loc_1800511D1
0x1800510c7  mov     [rbp+170h+var_F8], ecx
0x1800510ca  mov     rax, [rsi]
0x1800510cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800510d1  inc     rbx
0x1800510d4  cmp     [rax+rbx*2], cx
0x1800510d8  jnz     short loc_1800510D1
0x1800510da  lea     rdx, [rbx+1]; unsigned __int64
0x1800510de  mov     rcx, rdi; this
0x1800510e1  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x1800510e6  lea     r8d, [rbx+2]; cchBufferLength
0x1800510ea  mov     rdx, [rdi]; lpszVolumePathName
0x1800510ed  mov     rcx, [rsi]; lpszFileName
0x1800510f0  call    cs:__imp_GetVolumePathNameW
0x1800510f6  xor     ebx, ebx
0x1800510f8  test    eax, eax
0x1800510fa  jnz     short loc_180051117
0x1800510fc  call    cs:__imp_GetLastError
0x180051102  mov     edx, eax
0x180051104  mov     eax, [rbp+170h+var_F8]
0x180051107  mov     [rbp+170h+var_F8], eax
0x18005110a  test    edx, edx
0x18005110c  jz      loc_1800511A5
0x180051112  jmp     loc_1800511FD
0x180051117  mov     [rsp+270h+var_250], r13; bool *
0x18005111c  mov     r9, r14; struct CSrmAutoPWSZ *
0x18005111f  mov     r8, r12; struct CSrmAutoPWSZ *
0x180051122  mov     rdx, [rdi]; unsigned __int16 *
0x180051125  mov     rcx, r15; this
0x180051128  call    ?GetAccessAndLiveVolumes@CSrmVssUtil@@QEAAXPEBGAEAVCSrmAutoPWSZ@@1AEA_N@Z; CSrmVssUtil::GetAccessAndLiveVolumes(ushort const *,CSrmAutoPWSZ &,CSrmAutoPWSZ &,bool &)
0x18005112d  mov     eax, [rbp+170h+var_F8]
0x180051130  mov     [rbp+170h+var_F8], eax
0x180051133  mov     rcx, [r14]; unsigned __int16 *
0x180051136  call    ?SrmIsVolumeValid@@YA_NPEBG_N@Z; SrmIsVolumeValid(ushort const *,bool)
0x18005113b  test    al, al
0x18005113d  jz      short loc_180051179
0x18005113f  mov     [rbp+170h+var_F8], ebx
0x180051142  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180051149  mov     [rbp+170h+var_100], rax
0x18005114d  lea     rcx, [rbp+170h+var_100]; this
0x180051151  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180051156  mov     rcx, [rbp+170h+var_50]
0x18005115d  xor     rcx, rsp; StackCookie
0x180051160  call    __security_check_cookie
0x180051165  add     rsp, 238h
0x18005116c  pop     r15
0x18005116e  pop     r14
0x180051170  pop     r13
0x180051172  pop     r12
0x180051174  pop     rdi
0x180051175  pop     rsi
0x180051176  pop     rbx
0x180051177  pop     rbp
0x180051178  retn
0x180051179  mov     edx, 80045306h; int
0x18005117e  lea     rcx, [rbp+170h+var_100]; this
0x180051182  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180051187  lea     rcx, [rbp+170h+var_100]; this
0x18005118b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180051190  mov     r8d, eax; char
0x180051193  xor     r9d, r9d; unsigned __int16 *
0x180051196  mov     edx, 2BDh; unsigned int
0x18005119b  lea     rcx, [rbp+170h+var_100]; this
0x18005119f  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800511a5  mov     edx, 80070057h; int
0x1800511aa  lea     rcx, [rbp+170h+var_100]; this
0x1800511ae  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800511b3  lea     rcx, [rbp+170h+var_100]; this
0x1800511b7  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800511bc  mov     r8d, eax; char
0x1800511bf  xor     r9d, r9d; unsigned __int16 *
0x1800511c2  mov     edx, 2A5h; unsigned int
0x1800511c7  lea     rcx, [rbp+170h+var_100]; this
0x1800511cb  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800511d1  mov     edx, 80045304h; int
0x1800511d6  lea     rcx, [rbp+170h+var_100]; this
0x1800511da  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800511df  lea     rcx, [rbp+170h+var_100]; this
0x1800511e3  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800511e8  mov     r8d, eax; char
0x1800511eb  xor     r9d, r9d; unsigned __int16 *
0x1800511ee  mov     edx, 295h; unsigned int
0x1800511f3  lea     rcx, [rbp+170h+var_100]; this
0x1800511f7  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800511fd  mov     [rbp+170h+var_F8], ebx
0x180051200  test    edx, edx
0x180051202  jle     short loc_18005120D
0x180051204  movzx   edx, dx
0x180051207  or      edx, 80070000h; int
0x18005120d  lea     rcx, [rbp+170h+var_100]; this
0x180051211  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180051216  lea     rcx, [rbp+170h+var_100]; this
0x18005121a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005121f  mov     ebx, eax
0x180051221  lea     rax, [rbp+170h+var_198]
0x180051225  mov     qword ptr [rsp+270h+var_230], rax
0x18005122a  mov     [rsp+270h+var_248], 16h
0x180051232  mov     dword ptr [rsp+270h+var_250], 2ABh
0x18005123a  lea     r9, aCscaninformati_3; "CScanInformation::GetNamespaceVolumePat"...
0x180051241  lea     r8, aNamespcc; "NAMESPCC"
0x180051248  lea     rdx, aBaseFsFsrmServ_34; "base\\fs\\fsrm\\service\\pipeline\\name"...
0x18005124f  lea     rcx, [rbp+170h+var_198]
0x180051253  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180051258  nop
0x180051259  lea     r9, aGetvolumepathn_1; "GetVolumePathName"
0x180051260  mov     r8d, ebx
0x180051263  mov     rdx, rax
0x180051266  lea     rcx, [rbp+170h+var_100]
0x18005126a  call    ?TranslatePathError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslatePathError(CSrmDebugInfo,long,ushort const *,...)
```
