# CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::AddDataToCache(_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *)

- ea: `0x180002054`
- end: `0x1800022db`
- name: `?AddDataToCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000bbe0`

## callees

- `0x180002054`
- `0x180003968`
- `0x180003ce0`
- `0x180003d80`
- `0x180003e5c`
- `0x180006840`
- `0x18000d348`
- `0x18000d43c`
- `0x18000dd64`
- `0x18000f154`
- `0x180015760`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x180002241`
- `KERNEL32!MoveFileExW` at `0x180002241`
- `KERNEL32!CloseHandle` at `0x180002229`
- `KERNEL32!CloseHandle` at `0x1800022b8`
- `KERNEL32!CloseHandle` at `0x180002229`
- `KERNEL32!CloseHandle` at `0x1800022b8`
- `KERNEL32!CreateFileW` at `0x180002186`
- `KERNEL32!CreateFileW` at `0x180002186`

## string_xrefs

- `0x1800020ab`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *)>::AddDataToCache`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::AddDataToCache(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  __int64 FileW; // rbx
  int CacheFileName; // edi
  __int16 v9; // ax
  const WCHAR *v10; // rsi
  LPCWSTR v11; // r14
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v16; // [rsp+40h] [rbp-39h] BYREF
  __int16 v17; // [rsp+44h] [rbp-35h]
  __int16 v18; // [rsp+46h] [rbp-33h]
  LPCWSTR lpFileName[2]; // [rsp+78h] [rbp-1h] BYREF
  LPCWSTR lpNewFileName[9]; // [rsp+88h] [rbp+Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v16,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,stru"
    "ct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_O"
    "NDISK_DRIVER_INFO *)>::AddDataToCache",
    0x44u,
    a4);
  lpNewFileName[1] = 0;
  FileW = -1;
  lpNewFileName[0] = (LPCWSTR)qword_18001A620;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  lpFileName[1] = 0;
  if ( !a3 )
  {
    CacheFileName = -2147024809;
    v18 = 74;
LABEL_20:
    v16 = CacheFileName;
    goto LABEL_21;
  }
  v16 = 0;
  v17 = 74;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(
                    a1,
                    a2,
                    0,
                    lpNewFileName);
  v16 = CacheFileName;
  v9 = 76;
  if ( CacheFileName < 0 )
    goto LABEL_7;
  v17 = 76;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(
                    a1,
                    a2,
                    1,
                    lpFileName);
  v16 = CacheFileName;
  v9 = 77;
  if ( CacheFileName < 0 )
    goto LABEL_7;
  v10 = lpFileName[0];
  v17 = 77;
  SxDeleteFile(lpFileName[0]);
  FileW = (__int64)CreateFileW(v10, 0x40000000u, 0, 0, 2u, 0x2000006u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    CacheFileName = GetLastFailureAsHRESULT();
    v16 = CacheFileName;
    v18 = 94;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids,
        (unsigned int)"shFile.IsValid()",
        (__int64)v10,
        CacheFileName);
LABEL_13:
      CacheFileName = v16;
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  v16 = 0;
  v17 = 94;
  CacheFileName = SerializeToFile<_DRVWUHELPER_ONDISK_DRIVER_INFO>((HANDLE)FileW);
  v16 = CacheFileName;
  v9 = 95;
  if ( CacheFileName < 0 )
  {
LABEL_7:
    v18 = v9;
    goto LABEL_21;
  }
  v17 = 95;
  CloseHandle((HANDLE)FileW);
  v11 = lpNewFileName[0];
  FileW = -1;
  if ( MoveFileExW(v10, lpNewFileName[0], 9u) )
  {
    CacheFileName = 0;
    v17 = 101;
    goto LABEL_20;
  }
  CacheFileName = GetLastFailureAsHRESULT();
  v16 = CacheFileName;
  v18 = 101;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_sSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v14, (__int64)v10, (__int64)v11, CacheFileName);
    goto LABEL_13;
  }
LABEL_21:
  CBsString::_Release((CBsString *)lpFileName);
  CBsString::_Release((CBsString *)lpNewFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)CacheFileName;
}

```

## disassembly

```asm
0x180002054  push    rbp
0x180002056  push    rbx
0x180002057  push    rsi
0x180002058  push    rdi
0x180002059  push    r13
0x18000205b  push    r14
0x18000205d  push    r15
0x18000205f  lea     rbp, [rsp-27h]
0x180002064  sub     rsp, 0A0h
0x18000206b  mov     r14, r8
0x18000206e  mov     r15, rdx
0x180002071  mov     rsi, rcx
0x180002074  mov     rcx, cs:WPP_GLOBAL_Control
0x18000207b  lea     r13, WPP_GLOBAL_Control
0x180002082  cmp     rcx, r13
0x180002085  jz      short loc_1800020A5
0x180002087  test    dword ptr [rcx+1Ch], 20000000h
0x18000208e  jz      short loc_1800020A5
0x180002090  mov     rcx, [rcx+10h]
0x180002094  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x18000209b  mov     edx, 0Bh
0x1800020a0  call    WPP_SF_
0x1800020a5  mov     r8d, 44h ; 'D'; unsigned __int16
0x1800020ab  lea     rdx, aCsxondiskcache_5; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x1800020b2  lea     rcx, [rbp+57h+var_90]; this
0x1800020b6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800020bb  lea     rax, qword_18001A620
0x1800020c2  mov     [rbp+57h+var_40], 0
0x1800020ca  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800020ce  mov     [rbp+57h+lpNewFileName], rax
0x1800020d2  mov     [rbp+57h+lpFileName], rax
0x1800020d6  mov     [rbp+57h+var_50], 0
0x1800020de  lea     eax, [rbx+4Bh]
0x1800020e1  test    r14, r14
0x1800020e4  jnz     short loc_1800020F4
0x1800020e6  mov     edi, 80070057h
0x1800020eb  mov     [rbp+57h+var_8A], ax
0x1800020ef  jmp     loc_180002296
0x1800020f4  lea     r9, [rbp+57h+lpNewFileName]
0x1800020f8  mov     [rbp+57h+var_90], 0
0x1800020ff  xor     r8d, r8d
0x180002102  mov     [rbp+57h+var_8C], ax
0x180002106  mov     rdx, r15
0x180002109  mov     rcx, rsi
0x18000210c  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x180002111  mov     edi, eax
0x180002113  mov     [rbp+57h+var_90], eax
0x180002116  test    eax, eax
0x180002118  mov     eax, 4Ch ; 'L'
0x18000211d  jns     short loc_180002128
0x18000211f  mov     [rbp+57h+var_8A], ax
0x180002123  jmp     loc_180002299
0x180002128  lea     r9, [rbp+57h+lpFileName]
0x18000212c  mov     [rbp+57h+var_8C], ax
0x180002130  mov     r8d, 1
0x180002136  mov     rdx, r15
0x180002139  mov     rcx, rsi
0x18000213c  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x180002141  mov     edi, eax
0x180002143  mov     [rbp+57h+var_90], eax
0x180002146  test    eax, eax
0x180002148  mov     eax, 4Dh ; 'M'
0x18000214d  js      short loc_18000211F
0x18000214f  mov     rsi, [rbp+57h+lpFileName]
0x180002153  mov     rcx, rsi; lpFileName
0x180002156  mov     [rbp+57h+var_8C], ax
0x18000215a  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x18000215f  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180002168  xor     r9d, r9d; lpSecurityAttributes
0x18000216b  mov     [rsp+0D0h+dwFlagsAndAttributes], 2000006h; dwFlagsAndAttributes
0x180002173  xor     r8d, r8d; dwShareMode
0x180002176  mov     edx, 40000000h; dwDesiredAccess
0x18000217b  mov     [rsp+0D0h+dwCreationDisposition], 2; dwCreationDisposition
0x180002183  mov     rcx, rsi; lpFileName
0x180002186  call    cs:__imp_CreateFileW
0x18000218c  mov     rbx, rax
0x18000218f  inc     rax
0x180002192  test    rax, 0FFFFFFFFFFFFFFFEh
0x180002198  jnz     short loc_1800021F5
0x18000219a  call    GetLastFailureAsHRESULT
0x18000219f  mov     edi, eax
0x1800021a1  mov     [rbp+57h+var_90], eax
0x1800021a4  mov     eax, 5Eh ; '^'
0x1800021a9  mov     [rbp+57h+var_8A], ax
0x1800021ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021b4  cmp     rcx, r13
0x1800021b7  jz      loc_180002299
0x1800021bd  test    dword ptr [rcx+1Ch], 2000000h
0x1800021c4  jz      loc_180002299
0x1800021ca  mov     rcx, [rcx+10h]
0x1800021ce  lea     edx, [rax-52h]
0x1800021d1  mov     [rsp+0D0h+dwFlagsAndAttributes], edi
0x1800021d5  lea     r9, aShfileIsvalid; "shFile.IsValid()"
0x1800021dc  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x1800021e3  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rsi
0x1800021e8  call    WPP_SF_sSd
0x1800021ed  mov     edi, [rbp+57h+var_90]
0x1800021f0  jmp     loc_180002299
0x1800021f5  mov     eax, 5Eh ; '^'
0x1800021fa  mov     [rbp+57h+var_90], 0
0x180002201  mov     r9, r14
0x180002204  mov     [rbp+57h+var_8C], ax
0x180002208  mov     rcx, rbx; hFile
0x18000220b  call    ??$SerializeToFile@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@ZPEBU_GUID@@1@Z; SerializeToFile<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_GUID const *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)
0x180002210  mov     edi, eax
0x180002212  mov     [rbp+57h+var_90], eax
0x180002215  test    eax, eax
0x180002217  mov     eax, 5Fh ; '_'
0x18000221c  js      loc_18000211F
0x180002222  mov     rcx, rbx; hObject
0x180002225  mov     [rbp+57h+var_8C], ax
0x180002229  call    cs:__imp_CloseHandle
0x18000222f  mov     r14, [rbp+57h+lpNewFileName]
0x180002233  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002237  mov     rdx, r14; lpNewFileName
0x18000223a  mov     rcx, rsi; lpExistingFileName
0x18000223d  lea     r8d, [rbx+0Ah]; dwFlags
0x180002241  call    cs:__imp_MoveFileExW
0x180002247  test    eax, eax
0x180002249  jnz     short loc_18000228D
0x18000224b  call    GetLastFailureAsHRESULT
0x180002250  mov     edi, eax
0x180002252  mov     [rbp+57h+var_90], eax
0x180002255  lea     eax, [rbx+66h]
0x180002258  mov     [rbp+57h+var_8A], ax
0x18000225c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002263  cmp     rcx, r13
0x180002266  jz      short loc_180002299
0x180002268  test    dword ptr [rcx+1Ch], 2000000h
0x18000226f  jz      short loc_180002299
0x180002271  mov     rcx, [rcx+10h]
0x180002275  mov     dword ptr [rsp+0D0h+hTemplateFile], edi
0x180002279  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], r14
0x18000227e  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rsi
0x180002283  call    WPP_SF_sSSd
0x180002288  jmp     loc_1800021ED
0x18000228d  xor     edi, edi
0x18000228f  lea     eax, [rdi+65h]
0x180002292  mov     [rbp+57h+var_8C], ax
0x180002296  mov     [rbp+57h+var_90], edi
0x180002299  lea     rcx, [rbp+57h+lpFileName]; this
0x18000229d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800022a2  lea     rcx, [rbp+57h+lpNewFileName]; this
0x1800022a6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800022ab  lea     rcx, [rbx-1]
0x1800022af  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800022b3  ja      short loc_1800022BE
0x1800022b5  mov     rcx, rbx; hObject
0x1800022b8  call    cs:__imp_CloseHandle
0x1800022be  lea     rcx, [rbp+57h+var_90]; this
0x1800022c2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800022c7  mov     eax, edi
0x1800022c9  add     rsp, 0A0h
0x1800022d0  pop     r15
0x1800022d2  pop     r14
0x1800022d4  pop     r13
0x1800022d6  pop     rdi
0x1800022d7  pop     rsi
0x1800022d8  pop     rbx
0x1800022d9  pop     rbp
0x1800022da  retn
```
