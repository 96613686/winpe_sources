# CFsrmClusterUtil::GetSrmClusterRegistryKey(CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<_HCLUSTER *,0,int (*)(_HCLUSTER *),&CloseCluster(_HCLUSTER *),_HCLUSTER * & (*)(_HCLUSTER * &),&DTyper<_HCLUSTER *>::Identity(_HCLUSTER * &)>> &)

- ea: `0x18001eb94`
- end: `0x18001ed61`
- name: `?GetSrmClusterRegistryKey@CFsrmClusterUtil@@SAPEAUHKEY__@@AEAV?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAU_HCLUSTER@@$0A@P6AHPEAU1@@Z$1?CloseCluster@@YAH0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAU_HCLUSTER@@@@SAAEAPEAU1@1@Z@@@@@Z`
- size: `461`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x1800209ac`
- `0x180020b08`
- `0x180020d48`
- `0x180020f84`
- `0x180021148`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18001e69c`
- `0x18001eb94`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `CLUSAPI!OpenCluster` at `0x18001ec46`
- `CLUSAPI!OpenCluster` at `0x18001ec46`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001ecbf`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001ecbf`
- `CLUSAPI!GetClusterKey` at `0x18001ec6c`
- `CLUSAPI!GetClusterKey` at `0x18001ec6c`
- `CLUSAPI!CloseCluster` at `0x18001ecb2`
- `CLUSAPI!CloseCluster` at `0x18001ecb2`

## string_xrefs

- `0x18001ebc5`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001ebd1`: `CFsrmClusterUtil::GetSrmClusterRegistryKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HKEY __fastcall CFsrmClusterUtil::GetSrmClusterRegistryKey(__int64 a1)
{
  struct _HCLUSTER *v2; // rcx
  HCLUSTER v3; // rbx
  HCLUSTER v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  HKEY ClusterKey; // rdi
  HKEY ClusterKeyForPath; // r14
  struct _HCLUSTER *v11; // rcx
  int v13; // eax
  char v14; // al
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  HCLUSTER v17; // [rsp+28h] [rbp-D8h]
  const wchar_t *v18; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v19; // [rsp+48h] [rbp-B8h]
  const wchar_t *v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+58h] [rbp-A8h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  _BYTE v23[96]; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+C8h] [rbp-38h]
  void **v25; // [rsp+D0h] [rbp-30h] BYREF
  int v26; // [rsp+D8h] [rbp-28h]

  v18 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v19 = L"CFsrmClusterUtil::GetSrmClusterRegistryKey";
  v20 = L"CLUSUTLC";
  v21 = 0x16000000F4LL;
  LODWORD(v22) = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v25, (const struct CSrmDebugInfo *)&v18, 0);
  v2 = *(struct _HCLUSTER **)(a1 + 8);
  v3 = 0;
  v17 = 0;
  if ( !v2 )
  {
    v4 = OpenCluster(0);
    v3 = v4;
    v17 = v4;
    if ( !v4 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6, v5);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v25, LastFailureAsHRESULT);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v25);
      CSrmFunctionTracer::Throw(
        (CSrmFunctionTracer *)&v25,
        0xFDu,
        Hr,
        0,
        &CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<_HCLUSTER *,0,int (*)(_HCLUSTER *),&int CloseCluster(_HCLUSTER *),_HCLUSTER * & (*)(_HCLUSTER * &),&public: static _HCLUSTER * & DTyper<_HCLUSTER *>::Identity(_HCLUSTER * &)>>::`vftable',
        0);
    }
    v26 = 0;
    v2 = v4;
  }
  ClusterKey = GetClusterKey(v2, 0xF003Fu);
  if ( !ClusterKey )
  {
    v13 = GetLastFailureAsHRESULT(v8, v7);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v25, v13);
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v25);
    CSrmFunctionTracer::Throw(
      (CSrmFunctionTracer *)&v25,
      0x103u,
      v14,
      0,
      &CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<_HCLUSTER *,0,int (*)(_HCLUSTER *),&int CloseCluster(_HCLUSTER *),_HCLUSTER * & (*)(_HCLUSTER * &),&public: static _HCLUSTER * & DTyper<_HCLUSTER *>::Identity(_HCLUSTER * &)>>::`vftable',
      v17,
      &CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable',
      0,
      v18,
      v19,
      v20,
      v21,
      v22);
  }
  v26 = 0;
  ClusterKeyForPath = CFsrmClusterUtil::GetClusterKeyForPath(ClusterKey, L"SRM");
  if ( v3 )
  {
    v11 = *(struct _HCLUSTER **)(a1 + 8);
    if ( v11 )
      CloseCluster(v11);
    *(_QWORD *)(a1 + 8) = v3;
  }
  ClusterRegCloseKey(ClusterKey);
  v25 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v25);
  return ClusterKeyForPath;
}

```

## disassembly

```asm
0x18001eb94  mov     [rsp-8+arg_8], rbx
0x18001eb99  mov     [rsp-8+arg_10], rsi
0x18001eb9e  push    rbp
0x18001eb9f  push    rdi
0x18001eba0  push    r14
0x18001eba2  lea     rbp, [rsp-90h]
0x18001ebaa  sub     rsp, 190h
0x18001ebb1  mov     rax, cs:__security_cookie
0x18001ebb8  xor     rax, rsp
0x18001ebbb  mov     [rbp+0A0h+var_20], rax
0x18001ebc2  mov     rsi, rcx
0x18001ebc5  lea     rax, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001ebcc  mov     [rsp+1A0h+var_160], rax
0x18001ebd1  lea     rax, aCfsrmclusterut_1; "CFsrmClusterUtil::GetSrmClusterRegistry"...
0x18001ebd8  mov     [rsp+1A0h+var_158], rax
0x18001ebdd  lea     rax, aClusutlc; "CLUSUTLC"
0x18001ebe4  mov     [rsp+1A0h+var_150], rax
0x18001ebe9  mov     [rsp+1A0h+var_148], 0F4h
0x18001ebf1  mov     [rsp+1A0h+var_144], 16h
0x18001ebf9  mov     dword ptr [rsp+1A0h+var_140], 0FFh
0x18001ec01  mov     [rbp+0A0h+var_D8], 1000000h
0x18001ec08  xor     edx, edx; Val
0x18001ec0a  lea     r8d, [rdx+60h]; Size
0x18001ec0e  lea     rcx, [rsp+1A0h+var_138]; void *
0x18001ec13  call    memset_0
0x18001ec18  xor     r8d, r8d
0x18001ec1b  lea     rdx, [rsp+1A0h+var_160]
0x18001ec20  lea     rcx, [rbp+0A0h+var_D0]
0x18001ec24  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001ec29  nop
0x18001ec2a  mov     rcx, [rsi+8]; lpszClusterName
0x18001ec2e  xor     ebx, ebx
0x18001ec30  mov     [rsp+1A0h+var_178], rbx
0x18001ec35  lea     rax, ??_7?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAU_HCLUSTER@@$0A@P6AHPEAU1@@Z$1?CloseCluster@@YAH0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAU_HCLUSTER@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<_HCLUSTER *,0,int (*)(_HCLUSTER *),&CloseCluster(_HCLUSTER *),_HCLUSTER * & (*)(_HCLUSTER * &),&DTyper<_HCLUSTER *>::Identity(_HCLUSTER * &)>>::`vftable'
0x18001ec3c  mov     [rsp+1A0h+var_180], rax
0x18001ec41  test    rcx, rcx
0x18001ec44  jnz     short loc_18001EC67
0x18001ec46  call    cs:__imp_OpenCluster
0x18001ec4c  mov     rbx, rax
0x18001ec4f  mov     [rsp+1A0h+var_178], rax
0x18001ec54  test    rax, rax
0x18001ec57  jz      loc_18001ED33
0x18001ec5d  mov     [rbp+0A0h+var_C8], 0
0x18001ec64  mov     rcx, rax; hCluster
0x18001ec67  mov     edx, 0F003Fh; samDesired
0x18001ec6c  call    cs:__imp_GetClusterKey
0x18001ec72  mov     rdi, rax
0x18001ec75  lea     rax, ??_7?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?ClusterRegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&ClusterRegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x18001ec7c  mov     [rsp+1A0h+var_170], rax
0x18001ec81  mov     [rsp+1A0h+var_168], rdi
0x18001ec86  test    rdi, rdi
0x18001ec89  jz      short loc_18001ED04
0x18001ec8b  mov     [rbp+0A0h+var_C8], 0
0x18001ec92  lea     rdx, szSubKey; "SRM"
0x18001ec99  mov     rcx, rdi; hKey
0x18001ec9c  call    ?GetClusterKeyForPath@CFsrmClusterUtil@@SAPEAUHKEY__@@PEAU2@PEBG@Z; CFsrmClusterUtil::GetClusterKeyForPath(HKEY__ *,ushort const *)
0x18001eca1  mov     r14, rax
0x18001eca4  test    rbx, rbx
0x18001eca7  jz      short loc_18001ECBC
0x18001eca9  mov     rcx, [rsi+8]; hCluster
0x18001ecad  test    rcx, rcx
0x18001ecb0  jz      short loc_18001ECB8
0x18001ecb2  call    cs:__imp_CloseCluster
0x18001ecb8  mov     [rsi+8], rbx
0x18001ecbc  mov     rcx, rdi; hKey
0x18001ecbf  call    cs:__imp_ClusterRegCloseKey
0x18001ecc5  nop
0x18001ecc6  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001eccd  mov     [rbp+0A0h+var_D0], rax
0x18001ecd1  lea     rcx, [rbp+0A0h+var_D0]; this
0x18001ecd5  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001ecda  mov     rax, r14
0x18001ecdd  mov     rcx, [rbp+0A0h+var_20]
0x18001ece4  xor     rcx, rsp; StackCookie
0x18001ece7  call    __security_check_cookie
0x18001ecec  lea     r11, [rsp+1A0h+var_10]
0x18001ecf4  mov     rbx, [r11+28h]
0x18001ecf8  mov     rsi, [r11+30h]
0x18001ecfc  mov     rsp, r11
0x18001ecff  pop     r14
0x18001ed01  pop     rdi
0x18001ed02  pop     rbp
0x18001ed03  retn
0x18001ed04  call    GetLastFailureAsHRESULT
0x18001ed09  nop
0x18001ed0a  mov     edx, eax; int
0x18001ed0c  lea     rcx, [rbp+0A0h+var_D0]; this
0x18001ed10  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001ed15  lea     rcx, [rbp+0A0h+var_D0]; this
0x18001ed19  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001ed1e  mov     r8d, eax; char
0x18001ed21  xor     r9d, r9d; unsigned __int16 *
0x18001ed24  mov     edx, 103h; unsigned int
0x18001ed29  lea     rcx, [rbp+0A0h+var_D0]; this
0x18001ed2d  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18001ed33  call    GetLastFailureAsHRESULT
0x18001ed38  mov     edx, eax; int
0x18001ed3a  lea     rcx, [rbp+0A0h+var_D0]; this
0x18001ed3e  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001ed43  lea     rcx, [rbp+0A0h+var_D0]; this
0x18001ed47  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001ed4c  mov     r8d, eax; char
0x18001ed4f  xor     r9d, r9d; unsigned __int16 *
0x18001ed52  mov     edx, 0FDh; unsigned int
0x18001ed57  lea     rcx, [rbp+0A0h+var_D0]; this
0x18001ed5b  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
