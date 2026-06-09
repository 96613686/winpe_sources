# CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::GetDataFromCache(_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *)

- ea: `0x180003360`
- end: `0x180003549`
- name: `?GetDataFromCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _BYTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18000c468`

## callees

- `0x180003360`
- `0x180003968`
- `0x180003ce0`
- `0x180003e5c`
- `0x180005e30`
- `0x18000d348`
- `0x18000d43c`
- `0x18000f154`
- `0x180015760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180003518`
- `KERNEL32!CloseHandle` at `0x180003518`
- `KERNEL32!CreateFileW` at `0x180003463`
- `KERNEL32!CreateFileW` at `0x180003463`

## string_xrefs

- `0x1800033b8`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *)>::GetDataFromCache`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::GetDataFromCache(
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
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,stru"
    "ct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_O"
    "NDISK_DRIVER_INFO *)>::GetDataFromCache",
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
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(
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
    CacheFileName = DeserializeFromFile<_DRVWUHELPER_ONDISK_DRIVER_INFO>(
                      FileW,
                      (__int64)&DRVWUHELPER_ONDISK_DRIVER_INFO_Decode,
                      (__int64)&rguid,
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
0x180003360  mov     [rsp-8+arg_18], rbx
0x180003365  push    rbp
0x180003366  push    rsi
0x180003367  push    rdi
0x180003368  push    r12
0x18000336a  push    r14
0x18000336c  lea     rbp, [rsp-37h]
0x180003371  sub     rsp, 90h
0x180003378  mov     rsi, r8
0x18000337b  mov     rdi, rdx
0x18000337e  mov     rbx, rcx
0x180003381  mov     rcx, cs:WPP_GLOBAL_Control
0x180003388  lea     r12, WPP_GLOBAL_Control
0x18000338f  cmp     rcx, r12
0x180003392  jz      short loc_1800033B2
0x180003394  test    dword ptr [rcx+1Ch], 20000000h
0x18000339b  jz      short loc_1800033B2
0x18000339d  mov     rcx, [rcx+10h]
0x1800033a1  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x1800033a8  mov     edx, 0Eh
0x1800033ad  call    WPP_SF_
0x1800033b2  mov     r8d, 7Eh ; '~'; unsigned __int16
0x1800033b8  lea     rdx, aCsxondiskcache_2; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x1800033bf  lea     rcx, [rbp+57h+var_60]; this
0x1800033c3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800033c8  mov     [rbp+57h+var_68], 0
0x1800033d0  lea     rax, qword_18001A620
0x1800033d7  mov     [rbp+57h+lpFileName], rax
0x1800033db  mov     eax, 82h
0x1800033e0  test    rsi, rsi
0x1800033e3  jnz     short loc_1800033F6
0x1800033e5  mov     ebx, 80070057h
0x1800033ea  mov     [rbp+57h+var_60], ebx
0x1800033ed  mov     [rbp+57h+var_5A], ax
0x1800033f1  jmp     loc_18000351E
0x1800033f6  mov     [rbp+57h+var_5C], ax
0x1800033fa  mov     r8d, 10h
0x180003400  mov     rax, rsi
0x180003403  mov     [rbp+57h+var_60], 0
0x18000340a  mov     byte ptr [rax], 0
0x18000340d  inc     rax
0x180003410  sub     r8, 1
0x180003414  jnz     short loc_18000340A
0x180003416  lea     r9, [rbp+57h+lpFileName]
0x18000341a  mov     rdx, rdi
0x18000341d  mov     rcx, rbx
0x180003420  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x180003425  mov     ebx, eax
0x180003427  mov     [rbp+57h+var_60], eax
0x18000342a  test    eax, eax
0x18000342c  mov     eax, 85h
0x180003431  js      short loc_1800033ED
0x180003433  mov     r14, [rbp+57h+lpFileName]
0x180003437  xor     r9d, r9d; lpSecurityAttributes
0x18000343a  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x180003443  mov     edx, 80000000h; dwDesiredAccess
0x180003448  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000006h; dwFlagsAndAttributes
0x180003450  mov     rcx, r14; lpFileName
0x180003453  mov     [rbp+57h+var_5C], ax
0x180003457  lea     r8d, [r9+1]; dwShareMode
0x18000345b  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180003463  call    cs:__imp_CreateFileW
0x180003469  mov     rdi, rax
0x18000346c  inc     rax
0x18000346f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003475  jnz     short loc_1800034D4
0x180003477  call    GetLastFailureAsHRESULT
0x18000347c  mov     ebx, eax
0x18000347e  mov     [rbp+57h+var_60], eax
0x180003481  mov     eax, 93h
0x180003486  mov     [rbp+57h+var_5A], ax
0x18000348a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003491  cmp     rcx, r12
0x180003494  jz      short loc_1800034C7
0x180003496  test    dword ptr [rcx+1Ch], 2000000h
0x18000349d  jz      short loc_1800034C7
0x18000349f  mov     rcx, [rcx+10h]
0x1800034a3  lea     r9, aShfileIsvalid; "shFile.IsValid()"
0x1800034aa  mov     edx, 0Fh
0x1800034af  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx
0x1800034b3  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x1800034ba  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x1800034bf  call    WPP_SF_sSd
0x1800034c4  mov     ebx, [rbp+57h+var_60]
0x1800034c7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800034cb  jz      short loc_18000351E
0x1800034cd  test    rdi, rdi
0x1800034d0  jz      short loc_18000351E
0x1800034d2  jmp     short loc_180003515
0x1800034d4  mov     eax, 93h
0x1800034d9  mov     [rbp+57h+var_60], 0
0x1800034e0  mov     r9, rsi
0x1800034e3  mov     [rbp+57h+var_5C], ax
0x1800034e7  lea     r8, rguid
0x1800034ee  mov     rcx, rdi; hFile
0x1800034f1  lea     rdx, DRVWUHELPER_ONDISK_DRIVER_INFO_Decode
0x1800034f8  call    ??$DeserializeFromFile@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@ZPEBU_GUID@@1@Z; DeserializeFromFile<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_GUID const *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)
0x1800034fd  mov     ebx, eax
0x1800034ff  mov     [rbp+57h+var_60], eax
0x180003502  test    eax, eax
0x180003504  mov     eax, 95h
0x180003509  jns     short loc_180003511
0x18000350b  mov     [rbp+57h+var_5A], ax
0x18000350f  jmp     short loc_180003515
0x180003511  mov     [rbp+57h+var_5C], ax
0x180003515  mov     rcx, rdi; hObject
0x180003518  call    cs:__imp_CloseHandle
0x18000351e  lea     rcx, [rbp+57h+lpFileName]; this
0x180003522  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180003527  lea     rcx, [rbp+57h+var_60]; this
0x18000352b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180003530  mov     eax, ebx
0x180003532  mov     rbx, [rsp+0B0h+arg_18]
0x18000353a  add     rsp, 90h
0x180003541  pop     r14
0x180003543  pop     r12
0x180003545  pop     rdi
0x180003546  pop     rsi
0x180003547  pop     rbp
0x180003548  retn
```
