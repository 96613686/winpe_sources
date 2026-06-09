# CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::DeleteDataFromCache(_GUID)

- ea: `0x180002658`
- end: `0x180002812`
- name: `?DeleteDataFromCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJU_GUID@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000b3b0`

## callees

- `0x180002658`
- `0x180003968`
- `0x180003ce0`
- `0x180003d08`
- `0x18000d348`
- `0x18000d43c`
- `0x18000dd64`
- `0x180015760`

## string_xrefs

- `0x1800026ad`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *)>::DeleteDataFromCache`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::DeleteDataFromCache(
        __int64 a1,
        const struct _GUID *a2)
{
  int CacheFileName; // ebx
  __int16 v5; // ax
  __int64 v6; // rdx
  __int64 v7; // r8
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-50h] BYREF
  int v10; // [rsp+40h] [rbp-40h] BYREF
  __int16 v11; // [rsp+44h] [rbp-3Ch]
  __int16 v12; // [rsp+46h] [rbp-3Ah]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v10,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,stru"
    "ct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_O"
    "NDISK_DRIVER_INFO *)>::DeleteDataFromCache",
    168);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(
                    a1,
                    a2,
                    0,
                    (CBsString *)lpFileName);
  v10 = CacheFileName;
  v5 = 173;
  if ( CacheFileName < 0 )
    goto LABEL_5;
  v11 = 173;
  v10 = SxDeleteFile(lpFileName[0]);
  if ( (int)(v10 + 0x80000000) >= 0
    && v10 != -2147024894
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids,
      lpFileName[0],
      v10);
  }
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(
                    a1,
                    a2,
                    1,
                    (CBsString *)lpFileName);
  v10 = CacheFileName;
  v5 = 181;
  if ( CacheFileName < 0 )
  {
LABEL_5:
    v12 = v5;
  }
  else
  {
    v11 = 181;
    v10 = SxDeleteFile(lpFileName[0]);
    if ( (int)(v10 + 0x80000000) >= 0
      && v10 != -2147024894
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids,
        lpFileName[0],
        v10);
    }
    v10 = 0;
    v11 = 189;
    CacheFileName = 0;
  }
  CBsString::_Release((LPVOID *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10, v6, v7);
  return (unsigned int)CacheFileName;
}

```

## disassembly

```asm
0x180002658  mov     [rsp-18h+arg_10], rbx
0x18000265d  mov     [rsp-18h+arg_18], rsi
0x180002662  push    rbp
0x180002663  push    rdi
0x180002664  push    r14
0x180002666  mov     rbp, rsp
0x180002669  sub     rsp, 80h
0x180002670  mov     rsi, rdx
0x180002673  mov     rdi, rcx
0x180002676  mov     rcx, cs:WPP_GLOBAL_Control
0x18000267d  lea     r14, WPP_GLOBAL_Control
0x180002684  cmp     rcx, r14
0x180002687  jz      short loc_1800026A7
0x180002689  test    dword ptr [rcx+1Ch], 20000000h
0x180002690  jz      short loc_1800026A7
0x180002692  mov     rcx, [rcx+10h]
0x180002696  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x18000269d  mov     edx, 10h
0x1800026a2  call    WPP_SF_
0x1800026a7  mov     r8d, 0A8h; unsigned __int16
0x1800026ad  lea     rdx, aCsxondiskcache_1; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x1800026b4  lea     rcx, [rbp+var_40]; this
0x1800026b8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800026bd  lea     rax, qword_18001A620
0x1800026c4  mov     [rbp+var_48], 0
0x1800026cc  lea     r9, [rbp+lpFileName]
0x1800026d0  mov     [rbp+lpFileName], rax
0x1800026d4  xor     r8d, r8d
0x1800026d7  mov     rdx, rsi
0x1800026da  mov     rcx, rdi
0x1800026dd  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x1800026e2  mov     ebx, eax
0x1800026e4  mov     [rbp+var_40], eax
0x1800026e7  test    eax, eax
0x1800026e9  mov     eax, 0ADh
0x1800026ee  jns     short loc_1800026F9
0x1800026f0  mov     [rbp+var_3A], ax
0x1800026f4  jmp     loc_1800027E6
0x1800026f9  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800026fd  mov     [rbp+var_3C], ax
0x180002701  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x180002706  mov     ecx, 80000000h
0x18000270b  mov     [rbp+var_40], eax
0x18000270e  mov     r8d, eax
0x180002711  add     eax, ecx
0x180002713  test    ecx, eax
0x180002715  jnz     short loc_180002753
0x180002717  cmp     r8d, 80070002h
0x18000271e  jz      short loc_180002753
0x180002720  mov     rcx, cs:WPP_GLOBAL_Control
0x180002727  cmp     rcx, r14
0x18000272a  jz      short loc_180002753
0x18000272c  test    dword ptr [rcx+1Ch], 4000000h
0x180002733  jz      short loc_180002753
0x180002735  mov     r9, [rbp+lpFileName]
0x180002739  mov     edx, 11h
0x18000273e  mov     rcx, [rcx+10h]
0x180002742  mov     [rsp+80h+var_60], r8d
0x180002747  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x18000274e  call    WPP_SF_SD
0x180002753  lea     r9, [rbp+lpFileName]
0x180002757  mov     r8d, 1
0x18000275d  mov     rdx, rsi
0x180002760  mov     rcx, rdi
0x180002763  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x180002768  mov     ebx, eax
0x18000276a  mov     [rbp+var_40], eax
0x18000276d  test    eax, eax
0x18000276f  mov     eax, 0B5h
0x180002774  js      loc_1800026F0
0x18000277a  mov     rcx, [rbp+lpFileName]; lpFileName
0x18000277e  mov     [rbp+var_3C], ax
0x180002782  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x180002787  mov     ecx, 80000000h
0x18000278c  mov     [rbp+var_40], eax
0x18000278f  mov     r10d, eax
0x180002792  add     eax, ecx
0x180002794  test    ecx, eax
0x180002796  jnz     short loc_1800027D4
0x180002798  cmp     r10d, 80070002h
0x18000279f  jz      short loc_1800027D4
0x1800027a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027a8  cmp     rcx, r14
0x1800027ab  jz      short loc_1800027D4
0x1800027ad  test    dword ptr [rcx+1Ch], 4000000h
0x1800027b4  jz      short loc_1800027D4
0x1800027b6  mov     r9, [rbp+lpFileName]
0x1800027ba  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x1800027c1  mov     rcx, [rcx+10h]
0x1800027c5  mov     edx, 12h
0x1800027ca  mov     [rsp+80h+var_60], r10d
0x1800027cf  call    WPP_SF_SD
0x1800027d4  mov     eax, 0BDh
0x1800027d9  mov     [rbp+var_40], 0
0x1800027e0  mov     [rbp+var_3C], ax
0x1800027e4  xor     ebx, ebx
0x1800027e6  lea     rcx, [rbp+lpFileName]; this
0x1800027ea  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800027ef  lea     rcx, [rbp+var_40]; this
0x1800027f3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800027f8  lea     r11, [rsp+80h+var_s0]
0x180002800  mov     eax, ebx
0x180002802  mov     rbx, [r11+30h]
0x180002806  mov     rsi, [r11+38h]
0x18000280a  mov     rsp, r11
0x18000280d  pop     r14
0x18000280f  pop     rdi
0x180002810  pop     rbp
0x180002811  retn
```
