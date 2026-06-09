# CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::DeleteDataFromCache(_GUID)

- ea: `0x180002818`
- end: `0x1800029d2`
- name: `?DeleteDataFromCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJU_GUID@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18000b3b0`

## callees

- `0x180002818`
- `0x180003b24`
- `0x180003ce0`
- `0x180003d08`
- `0x18000d348`
- `0x18000d43c`
- `0x18000dd64`
- `0x180015760`

## string_xrefs

- `0x18000286d`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::DeleteDataFromCache`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::DeleteDataFromCache(
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
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_"
    "INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_I"
    "NFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::DeleteDataFromCache",
    168);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(
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
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(
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
0x180002818  mov     [rsp-18h+arg_10], rbx
0x18000281d  mov     [rsp-18h+arg_18], rsi
0x180002822  push    rbp
0x180002823  push    rdi
0x180002824  push    r14
0x180002826  mov     rbp, rsp
0x180002829  sub     rsp, 80h
0x180002830  mov     rsi, rdx
0x180002833  mov     rdi, rcx
0x180002836  mov     rcx, cs:WPP_GLOBAL_Control
0x18000283d  lea     r14, WPP_GLOBAL_Control
0x180002844  cmp     rcx, r14
0x180002847  jz      short loc_180002867
0x180002849  test    dword ptr [rcx+1Ch], 20000000h
0x180002850  jz      short loc_180002867
0x180002852  mov     rcx, [rcx+10h]
0x180002856  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x18000285d  mov     edx, 10h
0x180002862  call    WPP_SF_
0x180002867  mov     r8d, 0A8h; unsigned __int16
0x18000286d  lea     rdx, aCsxondiskcache_9; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x180002874  lea     rcx, [rbp+var_40]; this
0x180002878  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000287d  lea     rax, qword_18001A620
0x180002884  mov     [rbp+var_48], 0
0x18000288c  lea     r9, [rbp+lpFileName]
0x180002890  mov     [rbp+lpFileName], rax
0x180002894  xor     r8d, r8d
0x180002897  mov     rdx, rsi
0x18000289a  mov     rcx, rdi
0x18000289d  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x1800028a2  mov     ebx, eax
0x1800028a4  mov     [rbp+var_40], eax
0x1800028a7  test    eax, eax
0x1800028a9  mov     eax, 0ADh
0x1800028ae  jns     short loc_1800028B9
0x1800028b0  mov     [rbp+var_3A], ax
0x1800028b4  jmp     loc_1800029A6
0x1800028b9  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800028bd  mov     [rbp+var_3C], ax
0x1800028c1  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x1800028c6  mov     ecx, 80000000h
0x1800028cb  mov     [rbp+var_40], eax
0x1800028ce  mov     r8d, eax
0x1800028d1  add     eax, ecx
0x1800028d3  test    ecx, eax
0x1800028d5  jnz     short loc_180002913
0x1800028d7  cmp     r8d, 80070002h
0x1800028de  jz      short loc_180002913
0x1800028e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028e7  cmp     rcx, r14
0x1800028ea  jz      short loc_180002913
0x1800028ec  test    dword ptr [rcx+1Ch], 4000000h
0x1800028f3  jz      short loc_180002913
0x1800028f5  mov     r9, [rbp+lpFileName]
0x1800028f9  mov     edx, 11h
0x1800028fe  mov     rcx, [rcx+10h]
0x180002902  mov     [rsp+80h+var_60], r8d
0x180002907  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x18000290e  call    WPP_SF_SD
0x180002913  lea     r9, [rbp+lpFileName]
0x180002917  mov     r8d, 1
0x18000291d  mov     rdx, rsi
0x180002920  mov     rcx, rdi
0x180002923  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)
0x180002928  mov     ebx, eax
0x18000292a  mov     [rbp+var_40], eax
0x18000292d  test    eax, eax
0x18000292f  mov     eax, 0B5h
0x180002934  js      loc_1800028B0
0x18000293a  mov     rcx, [rbp+lpFileName]; lpFileName
0x18000293e  mov     [rbp+var_3C], ax
0x180002942  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x180002947  mov     ecx, 80000000h
0x18000294c  mov     [rbp+var_40], eax
0x18000294f  mov     r10d, eax
0x180002952  add     eax, ecx
0x180002954  test    ecx, eax
0x180002956  jnz     short loc_180002994
0x180002958  cmp     r10d, 80070002h
0x18000295f  jz      short loc_180002994
0x180002961  mov     rcx, cs:WPP_GLOBAL_Control
0x180002968  cmp     rcx, r14
0x18000296b  jz      short loc_180002994
0x18000296d  test    dword ptr [rcx+1Ch], 4000000h
0x180002974  jz      short loc_180002994
0x180002976  mov     r9, [rbp+lpFileName]
0x18000297a  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180002981  mov     rcx, [rcx+10h]
0x180002985  mov     edx, 12h
0x18000298a  mov     [rsp+80h+var_60], r10d
0x18000298f  call    WPP_SF_SD
0x180002994  mov     eax, 0BDh
0x180002999  mov     [rbp+var_40], 0
0x1800029a0  mov     [rbp+var_3C], ax
0x1800029a4  xor     ebx, ebx
0x1800029a6  lea     rcx, [rbp+lpFileName]; this
0x1800029aa  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800029af  lea     rcx, [rbp+var_40]; this
0x1800029b3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800029b8  lea     r11, [rsp+80h+var_s0]
0x1800029c0  mov     eax, ebx
0x1800029c2  mov     rbx, [r11+30h]
0x1800029c6  mov     rsi, [r11+38h]
0x1800029ca  mov     rsp, r11
0x1800029cd  pop     r14
0x1800029cf  pop     rdi
0x1800029d0  pop     rbp
0x1800029d1  retn
```
