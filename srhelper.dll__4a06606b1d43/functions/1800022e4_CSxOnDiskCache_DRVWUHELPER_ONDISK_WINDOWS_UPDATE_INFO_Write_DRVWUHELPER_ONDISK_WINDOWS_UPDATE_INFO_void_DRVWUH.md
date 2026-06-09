# CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::AddDataToCache(_GUID,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)

- ea: `0x1800022e4`
- end: `0x18000256b`
- name: `?AddDataToCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJU_GUID@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x18000bbe0`

## callees

- `0x1800022e4`
- `0x180003b24`
- `0x180003ce0`
- `0x180003d80`
- `0x180003e5c`
- `0x180006b50`
- `0x18000d348`
- `0x18000d43c`
- `0x18000dd64`
- `0x18000f154`
- `0x180015760`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x1800024d1`
- `KERNEL32!MoveFileExW` at `0x1800024d1`
- `KERNEL32!CloseHandle` at `0x1800024b9`
- `KERNEL32!CloseHandle` at `0x180002548`
- `KERNEL32!CloseHandle` at `0x1800024b9`
- `KERNEL32!CloseHandle` at `0x180002548`
- `KERNEL32!CreateFileW` at `0x180002416`
- `KERNEL32!CreateFileW` at `0x180002416`

## string_xrefs

- `0x18000233b`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::AddDataToCache`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::AddDataToCache(
        __int64 a1,
        const struct _GUID *a2,
        __int64 a3)
{
  __int64 FileW; // rbx
  int CacheFileName; // edi
  __int16 v8; // ax
  const WCHAR *v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r8
  LPCWSTR v12; // r14
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rdx
  __int64 v17; // r8
  int v19; // [rsp+40h] [rbp-39h] BYREF
  __int16 v20; // [rsp+44h] [rbp-35h]
  __int16 v21; // [rsp+46h] [rbp-33h]
  LPCWSTR lpFileName[2]; // [rsp+78h] [rbp-1h] BYREF
  LPCWSTR lpNewFileName[9]; // [rsp+88h] [rbp+Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v19,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_"
    "INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_I"
    "NFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::AddDataToCache",
    68);
  lpNewFileName[1] = 0;
  FileW = -1;
  lpNewFileName[0] = (LPCWSTR)qword_18001A620;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  lpFileName[1] = 0;
  if ( !a3 )
  {
    CacheFileName = -2147024809;
    v21 = 74;
LABEL_20:
    v19 = CacheFileName;
    goto LABEL_21;
  }
  v19 = 0;
  v20 = 74;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(
                    a1,
                    a2,
                    0,
                    (CBsString *)lpNewFileName);
  v19 = CacheFileName;
  v8 = 76;
  if ( CacheFileName < 0 )
    goto LABEL_7;
  v20 = 76;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(
                    a1,
                    a2,
                    1,
                    (CBsString *)lpFileName);
  v19 = CacheFileName;
  v8 = 77;
  if ( CacheFileName < 0 )
    goto LABEL_7;
  v9 = lpFileName[0];
  v20 = 77;
  SxDeleteFile(lpFileName[0]);
  FileW = (__int64)CreateFileW(v9, 0x40000000u, 0, 0, 2u, 0x2000006u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    CacheFileName = GetLastFailureAsHRESULT();
    v19 = CacheFileName;
    v21 = 94;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids,
        (unsigned int)"shFile.IsValid()",
        (__int64)v9,
        CacheFileName);
LABEL_13:
      CacheFileName = v19;
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  v19 = 0;
  v20 = 94;
  CacheFileName = SerializeToFile<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO>((HANDLE)FileW, v10, v11, a3);
  v19 = CacheFileName;
  v8 = 95;
  if ( CacheFileName < 0 )
  {
LABEL_7:
    v21 = v8;
    goto LABEL_21;
  }
  v20 = 95;
  CloseHandle((HANDLE)FileW);
  v12 = lpNewFileName[0];
  FileW = -1;
  if ( MoveFileExW(v9, lpNewFileName[0], 9u) )
  {
    CacheFileName = 0;
    v20 = 101;
    goto LABEL_20;
  }
  CacheFileName = GetLastFailureAsHRESULT();
  v19 = CacheFileName;
  v21 = 101;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_sSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v15, (__int64)v9, (__int64)v12, CacheFileName);
    goto LABEL_13;
  }
LABEL_21:
  CBsString::_Release((LPVOID *)lpFileName);
  CBsString::_Release((LPVOID *)lpNewFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v19, v16, v17);
  return (unsigned int)CacheFileName;
}

```

## disassembly

```asm
0x1800022e4  push    rbp
0x1800022e6  push    rbx
0x1800022e7  push    rsi
0x1800022e8  push    rdi
0x1800022e9  push    r13
0x1800022eb  push    r14
0x1800022ed  push    r15
0x1800022ef  lea     rbp, [rsp-27h]
0x1800022f4  sub     rsp, 0A0h
0x1800022fb  mov     r14, r8
0x1800022fe  mov     r15, rdx
0x180002301  mov     rsi, rcx
0x180002304  mov     rcx, cs:WPP_GLOBAL_Control
0x18000230b  lea     r13, WPP_GLOBAL_Control
0x180002312  cmp     rcx, r13
0x180002315  jz      short loc_180002335
0x180002317  test    dword ptr [rcx+1Ch], 20000000h
0x18000231e  jz      short loc_180002335
0x180002320  mov     rcx, [rcx+10h]
0x180002324  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x18000232b  mov     edx, 0Bh
0x180002330  call    WPP_SF_
0x180002335  mov     r8d, 44h ; 'D'; unsigned __int16
0x18000233b  lea     rdx, aCsxondiskcache_7; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x180002342  lea     rcx, [rbp+57h+var_90]; this
0x180002346  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000234b  lea     rax, qword_18001A620
0x180002352  mov     [rbp+57h+var_40], 0
0x18000235a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000235e  mov     [rbp+57h+lpNewFileName], rax
0x180002362  mov     [rbp+57h+lpFileName], rax
0x180002366  mov     [rbp+57h+var_50], 0
0x18000236e  lea     eax, [rbx+4Bh]
0x180002371  test    r14, r14
0x180002374  jnz     short loc_180002384
0x180002376  mov     edi, 80070057h
0x18000237b  mov     [rbp+57h+var_8A], ax
0x18000237f  jmp     loc_180002526
0x180002384  lea     r9, [rbp+57h+lpNewFileName]
0x180002388  mov     [rbp+57h+var_90], 0
0x18000238f  xor     r8d, r8d
0x180002392  mov     [rbp+57h+var_8C], ax
0x180002396  mov     rdx, r15
0x180002399  mov     rcx, rsi
0x18000239c  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x1800023a1  mov     edi, eax
0x1800023a3  mov     [rbp+57h+var_90], eax
0x1800023a6  test    eax, eax
0x1800023a8  mov     eax, 4Ch ; 'L'
0x1800023ad  jns     short loc_1800023B8
0x1800023af  mov     [rbp+57h+var_8A], ax
0x1800023b3  jmp     loc_180002529
0x1800023b8  lea     r9, [rbp+57h+lpFileName]
0x1800023bc  mov     [rbp+57h+var_8C], ax
0x1800023c0  mov     r8d, 1
0x1800023c6  mov     rdx, r15
0x1800023c9  mov     rcx, rsi
0x1800023cc  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x1800023d1  mov     edi, eax
0x1800023d3  mov     [rbp+57h+var_90], eax
0x1800023d6  test    eax, eax
0x1800023d8  mov     eax, 4Dh ; 'M'
0x1800023dd  js      short loc_1800023AF
0x1800023df  mov     rsi, [rbp+57h+lpFileName]
0x1800023e3  mov     rcx, rsi; lpFileName
0x1800023e6  mov     [rbp+57h+var_8C], ax
0x1800023ea  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x1800023ef  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x1800023f8  xor     r9d, r9d; lpSecurityAttributes
0x1800023fb  mov     [rsp+0D0h+dwFlagsAndAttributes], 2000006h; dwFlagsAndAttributes
0x180002403  xor     r8d, r8d; dwShareMode
0x180002406  mov     edx, 40000000h; dwDesiredAccess
0x18000240b  mov     [rsp+0D0h+dwCreationDisposition], 2; dwCreationDisposition
0x180002413  mov     rcx, rsi; lpFileName
0x180002416  call    cs:__imp_CreateFileW
0x18000241c  mov     rbx, rax
0x18000241f  inc     rax
0x180002422  test    rax, 0FFFFFFFFFFFFFFFEh
0x180002428  jnz     short loc_180002485
0x18000242a  call    GetLastFailureAsHRESULT
0x18000242f  mov     edi, eax
0x180002431  mov     [rbp+57h+var_90], eax
0x180002434  mov     eax, 5Eh ; '^'
0x180002439  mov     [rbp+57h+var_8A], ax
0x18000243d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002444  cmp     rcx, r13
0x180002447  jz      loc_180002529
0x18000244d  test    dword ptr [rcx+1Ch], 2000000h
0x180002454  jz      loc_180002529
0x18000245a  mov     rcx, [rcx+10h]
0x18000245e  lea     edx, [rax-52h]
0x180002461  mov     [rsp+0D0h+dwFlagsAndAttributes], edi
0x180002465  lea     r9, aShfileIsvalid; "shFile.IsValid()"
0x18000246c  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180002473  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rsi
0x180002478  call    WPP_SF_sSd
0x18000247d  mov     edi, [rbp+57h+var_90]
0x180002480  jmp     loc_180002529
0x180002485  mov     eax, 5Eh ; '^'
0x18000248a  mov     [rbp+57h+var_90], 0
0x180002491  mov     r9, r14
0x180002494  mov     [rbp+57h+var_8C], ax
0x180002498  mov     rcx, rbx; hFile
0x18000249b  call    ??$SerializeToFile@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@ZPEBU_GUID@@1@Z; SerializeToFile<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),_GUID const *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)
0x1800024a0  mov     edi, eax
0x1800024a2  mov     [rbp+57h+var_90], eax
0x1800024a5  test    eax, eax
0x1800024a7  mov     eax, 5Fh ; '_'
0x1800024ac  js      loc_1800023AF
0x1800024b2  mov     rcx, rbx; hObject
0x1800024b5  mov     [rbp+57h+var_8C], ax
0x1800024b9  call    cs:__imp_CloseHandle
0x1800024bf  mov     r14, [rbp+57h+lpNewFileName]
0x1800024c3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800024c7  mov     rdx, r14; lpNewFileName
0x1800024ca  mov     rcx, rsi; lpExistingFileName
0x1800024cd  lea     r8d, [rbx+0Ah]; dwFlags
0x1800024d1  call    cs:__imp_MoveFileExW
0x1800024d7  test    eax, eax
0x1800024d9  jnz     short loc_18000251D
0x1800024db  call    GetLastFailureAsHRESULT
0x1800024e0  mov     edi, eax
0x1800024e2  mov     [rbp+57h+var_90], eax
0x1800024e5  lea     eax, [rbx+66h]
0x1800024e8  mov     [rbp+57h+var_8A], ax
0x1800024ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024f3  cmp     rcx, r13
0x1800024f6  jz      short loc_180002529
0x1800024f8  test    dword ptr [rcx+1Ch], 2000000h
0x1800024ff  jz      short loc_180002529
0x180002501  mov     rcx, [rcx+10h]
0x180002505  mov     dword ptr [rsp+0D0h+hTemplateFile], edi
0x180002509  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], r14
0x18000250e  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rsi
0x180002513  call    WPP_SF_sSSd
0x180002518  jmp     loc_18000247D
0x18000251d  xor     edi, edi
0x18000251f  lea     eax, [rdi+65h]
0x180002522  mov     [rbp+57h+var_8C], ax
0x180002526  mov     [rbp+57h+var_90], edi
0x180002529  lea     rcx, [rbp+57h+lpFileName]; this
0x18000252d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180002532  lea     rcx, [rbp+57h+lpNewFileName]; this
0x180002536  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000253b  lea     rcx, [rbx-1]
0x18000253f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180002543  ja      short loc_18000254E
0x180002545  mov     rcx, rbx; hObject
0x180002548  call    cs:__imp_CloseHandle
0x18000254e  lea     rcx, [rbp+57h+var_90]; this
0x180002552  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180002557  mov     eax, edi
0x180002559  add     rsp, 0A0h
0x180002560  pop     r15
0x180002562  pop     r14
0x180002564  pop     r13
0x180002566  pop     rdi
0x180002567  pop     rsi
0x180002568  pop     rbx
0x180002569  pop     rbp
0x18000256a  retn
```
