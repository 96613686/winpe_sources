# CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::GetDataFromCache(_GUID,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)

- ea: `0x180003550`
- end: `0x180003739`
- name: `?GetDataFromCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJU_GUID@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _BYTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000c468`

## callees

- `0x180003550`
- `0x180003b24`
- `0x180003ce0`
- `0x180003e5c`
- `0x1800062e8`
- `0x18000d348`
- `0x18000d43c`
- `0x18000f154`
- `0x180015760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180003708`
- `KERNEL32!CloseHandle` at `0x180003708`
- `KERNEL32!CreateFileW` at `0x180003653`
- `KERNEL32!CreateFileW` at `0x180003653`

## string_xrefs

- `0x1800035a8`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::GetDataFromCache`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::GetDataFromCache(
        __int64 a1,
        const struct _GUID *a2,
        _BYTE *a3)
{
  __int16 v6; // ax
  int CacheFileName; // ebx
  __int64 v8; // r8
  _BYTE *v9; // rax
  LPCWSTR v10; // r14
  HANDLE FileW; // rdi
  __int64 v12; // rdx
  __int64 v13; // r8
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-19h] BYREF
  int v16; // [rsp+50h] [rbp-9h] BYREF
  __int16 v17; // [rsp+54h] [rbp-5h]
  __int16 v18; // [rsp+56h] [rbp-3h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v16,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_"
    "INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_I"
    "NFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::GetDataFromCache",
    126);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  v6 = 130;
  if ( !a3 )
  {
    CacheFileName = -2147024809;
    v16 = -2147024809;
LABEL_6:
    v18 = v6;
    goto LABEL_21;
  }
  v17 = 130;
  v8 = 16;
  v9 = a3;
  v16 = 0;
  do
  {
    *v9++ = 0;
    --v8;
  }
  while ( v8 );
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(
                    a1,
                    a2,
                    0,
                    (CBsString *)lpFileName);
  v16 = CacheFileName;
  v6 = 133;
  if ( CacheFileName < 0 )
    goto LABEL_6;
  v10 = lpFileName[0];
  v17 = 133;
  FileW = CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, 0x2000006u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v16 = 0;
    v17 = 147;
    CacheFileName = DeserializeFromFile<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO>(
                      FileW,
                      (__int64)&DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Decode,
                      (__int64)&stru_180019528,
                      a3);
    v16 = CacheFileName;
    if ( CacheFileName >= 0 )
      v17 = 149;
    else
      v18 = 149;
LABEL_20:
    CloseHandle(FileW);
    goto LABEL_21;
  }
  CacheFileName = GetLastFailureAsHRESULT();
  v16 = CacheFileName;
  v18 = 147;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids,
      (unsigned int)"shFile.IsValid()",
      (__int64)v10,
      CacheFileName);
    CacheFileName = v16;
  }
  if ( FileW != (HANDLE)-1LL && FileW )
    goto LABEL_20;
LABEL_21:
  CBsString::_Release((LPVOID *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16, v12, v13);
  return (unsigned int)CacheFileName;
}

```

## disassembly

```asm
0x180003550  mov     [rsp-8+arg_18], rbx
0x180003555  push    rbp
0x180003556  push    rsi
0x180003557  push    rdi
0x180003558  push    r12
0x18000355a  push    r14
0x18000355c  lea     rbp, [rsp-37h]
0x180003561  sub     rsp, 90h
0x180003568  mov     rsi, r8
0x18000356b  mov     rdi, rdx
0x18000356e  mov     rbx, rcx
0x180003571  mov     rcx, cs:WPP_GLOBAL_Control
0x180003578  lea     r12, WPP_GLOBAL_Control
0x18000357f  cmp     rcx, r12
0x180003582  jz      short loc_1800035A2
0x180003584  test    dword ptr [rcx+1Ch], 20000000h
0x18000358b  jz      short loc_1800035A2
0x18000358d  mov     rcx, [rcx+10h]
0x180003591  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180003598  mov     edx, 0Eh
0x18000359d  call    WPP_SF_
0x1800035a2  mov     r8d, 7Eh ; '~'; unsigned __int16
0x1800035a8  lea     rdx, aCsxondiskcache_4; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x1800035af  lea     rcx, [rbp+57h+var_60]; this
0x1800035b3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800035b8  mov     [rbp+57h+var_68], 0
0x1800035c0  lea     rax, qword_18001A620
0x1800035c7  mov     [rbp+57h+lpFileName], rax
0x1800035cb  mov     eax, 82h
0x1800035d0  test    rsi, rsi
0x1800035d3  jnz     short loc_1800035E6
0x1800035d5  mov     ebx, 80070057h
0x1800035da  mov     [rbp+57h+var_60], ebx
0x1800035dd  mov     [rbp+57h+var_5A], ax
0x1800035e1  jmp     loc_18000370E
0x1800035e6  mov     [rbp+57h+var_5C], ax
0x1800035ea  mov     r8d, 10h
0x1800035f0  mov     rax, rsi
0x1800035f3  mov     [rbp+57h+var_60], 0
0x1800035fa  mov     byte ptr [rax], 0
0x1800035fd  inc     rax
0x180003600  sub     r8, 1
0x180003604  jnz     short loc_1800035FA
0x180003606  lea     r9, [rbp+57h+lpFileName]
0x18000360a  mov     rdx, rdi
0x18000360d  mov     rcx, rbx
0x180003610  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x180003615  mov     ebx, eax
0x180003617  mov     [rbp+57h+var_60], eax
0x18000361a  test    eax, eax
0x18000361c  mov     eax, 85h
0x180003621  js      short loc_1800035DD
0x180003623  mov     r14, [rbp+57h+lpFileName]
0x180003627  xor     r9d, r9d; lpSecurityAttributes
0x18000362a  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x180003633  mov     edx, 80000000h; dwDesiredAccess
0x180003638  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000006h; dwFlagsAndAttributes
0x180003640  mov     rcx, r14; lpFileName
0x180003643  mov     [rbp+57h+var_5C], ax
0x180003647  lea     r8d, [r9+1]; dwShareMode
0x18000364b  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180003653  call    cs:__imp_CreateFileW
0x180003659  mov     rdi, rax
0x18000365c  inc     rax
0x18000365f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003665  jnz     short loc_1800036C4
0x180003667  call    GetLastFailureAsHRESULT
0x18000366c  mov     ebx, eax
0x18000366e  mov     [rbp+57h+var_60], eax
0x180003671  mov     eax, 93h
0x180003676  mov     [rbp+57h+var_5A], ax
0x18000367a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003681  cmp     rcx, r12
0x180003684  jz      short loc_1800036B7
0x180003686  test    dword ptr [rcx+1Ch], 2000000h
0x18000368d  jz      short loc_1800036B7
0x18000368f  mov     rcx, [rcx+10h]
0x180003693  lea     r9, aShfileIsvalid; "shFile.IsValid()"
0x18000369a  mov     edx, 0Fh
0x18000369f  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx
0x1800036a3  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x1800036aa  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x1800036af  call    WPP_SF_sSd
0x1800036b4  mov     ebx, [rbp+57h+var_60]
0x1800036b7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800036bb  jz      short loc_18000370E
0x1800036bd  test    rdi, rdi
0x1800036c0  jz      short loc_18000370E
0x1800036c2  jmp     short loc_180003705
0x1800036c4  mov     eax, 93h
0x1800036c9  mov     [rbp+57h+var_60], 0
0x1800036d0  mov     r9, rsi
0x1800036d3  mov     [rbp+57h+var_5C], ax
0x1800036d7  lea     r8, stru_180019528
0x1800036de  mov     rcx, rdi; hFile
0x1800036e1  lea     rdx, DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Decode
0x1800036e8  call    ??$DeserializeFromFile@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@ZPEBU_GUID@@1@Z; DeserializeFromFile<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),_GUID const *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)
0x1800036ed  mov     ebx, eax
0x1800036ef  mov     [rbp+57h+var_60], eax
0x1800036f2  test    eax, eax
0x1800036f4  mov     eax, 95h
0x1800036f9  jns     short loc_180003701
0x1800036fb  mov     [rbp+57h+var_5A], ax
0x1800036ff  jmp     short loc_180003705
0x180003701  mov     [rbp+57h+var_5C], ax
0x180003705  mov     rcx, rdi; hObject
0x180003708  call    cs:__imp_CloseHandle
0x18000370e  lea     rcx, [rbp+57h+lpFileName]; this
0x180003712  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180003717  lea     rcx, [rbp+57h+var_60]; this
0x18000371b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180003720  mov     eax, ebx
0x180003722  mov     rbx, [rsp+0B0h+arg_18]
0x18000372a  add     rsp, 90h
0x180003731  pop     r14
0x180003733  pop     r12
0x180003735  pop     rdi
0x180003736  pop     rsi
0x180003737  pop     rbp
0x180003738  retn
```
