# CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)

- ea: `0x180003968`
- end: `0x180003b1c`
- name: `?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, int, CBsString *)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180002054`
- `0x180002658`
- `0x1800029d8`
- `0x180003360`

## callees

- `0x180003968`
- `0x180003ce0`
- `0x18000d348`
- `0x18000d43c`
- `0x180014f38`
- `0x180015150`
- `0x18001528c`
- `0x180015390`
- `0x180015760`

## string_xrefs

- `0x1800039be`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName`
- `0x180003a54`: `Temp_%s_%s`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(
        __int64 a1,
        const struct _GUID *a2,
        int a3,
        CBsString *a4)
{
  int v8; // ebx
  bool v9; // sf
  __int16 v10; // ax
  __int64 v11; // r9
  const unsigned __int16 *v12; // r9
  bool v13; // sf
  const unsigned __int16 *v14; // rdx
  bool v15; // zf
  _WORD *v16; // rcx
  const unsigned __int16 *v18; // [rsp+20h] [rbp-79h]
  const unsigned __int16 *v19; // [rsp+28h] [rbp-71h]
  const unsigned __int16 *v20; // [rsp+30h] [rbp-69h]
  const unsigned __int16 *v21; // [rsp+38h] [rbp-61h]
  const unsigned __int16 *v22; // [rsp+40h] [rbp-59h]
  const unsigned __int16 *v23; // [rsp+48h] [rbp-51h]
  const unsigned __int16 *v24; // [rsp+50h] [rbp-49h]
  _QWORD v25[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 *v26[2]; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v27[2]; // [rsp+80h] [rbp-19h] BYREF
  int v28; // [rsp+90h] [rbp-9h] BYREF
  __int16 v29; // [rsp+94h] [rbp-5h]
  __int16 v30; // [rsp+96h] [rbp-3h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v28,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,stru"
    "ct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_O"
    "NDISK_DRIVER_INFO *)>::_CreateCacheFileName",
    0xD8u,
    (unsigned __int16)a4);
  v26[1] = 0;
  v26[0] = (unsigned __int16 *)qword_18001A620;
  v27[0] = (unsigned __int16 *)qword_18001A620;
  v25[0] = qword_18001A620;
  v27[1] = 0;
  v25[1] = 0;
  if ( a2 )
  {
    v8 = CBsString::Set((CBsString *)v25, a2);
    v28 = v8;
    v9 = v8 < 0;
    v10 = 223;
  }
  else
  {
    v8 = CBsString::Append((CBsString *)v25, L"*");
    v28 = v8;
    v9 = v8 < 0;
    v10 = 227;
  }
  if ( v9 )
    goto LABEL_7;
  v11 = *(_QWORD *)(a1 + 16);
  v29 = v10;
  if ( a3 )
  {
    v8 = CBsString::Format((CBsString *)v26, L"Temp_%s_%s", v25[0], v11);
    v28 = v8;
    v13 = v8 < 0;
    v10 = 233;
  }
  else
  {
    v8 = CBsString::Format((CBsString *)v26, L"%s_%s", v25[0], v11);
    v28 = v8;
    v13 = v8 < 0;
    v10 = 238;
  }
  if ( v13 )
    goto LABEL_7;
  v14 = *(const unsigned __int16 **)a1;
  v29 = v10;
  v8 = CBsString::SetPath((CBsString *)v27, v14, v26[0], v12, v18, v19, v20, v21, v22, v23, v24);
  v28 = v8;
  v10 = 241;
  if ( v8 < 0 )
    goto LABEL_7;
  v15 = *((_DWORD *)a4 + 2) == 0;
  v29 = 241;
  if ( !v15 )
  {
    v16 = *(_WORD **)a4;
    *((_DWORD *)a4 + 2) = 0;
    *v16 = 0;
  }
  v8 = CBsString::Append(a4, v27[0]);
  v28 = v8;
  v10 = 243;
  if ( v8 < 0 )
LABEL_7:
    v30 = v10;
  else
    v29 = 243;
  CBsString::_Release((CBsString *)v25);
  CBsString::_Release((CBsString *)v27);
  CBsString::_Release((CBsString *)v26);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003968  push    rbp
0x18000396a  push    rbx
0x18000396b  push    rsi
0x18000396c  push    rdi
0x18000396d  push    r14
0x18000396f  lea     rbp, [rsp-37h]
0x180003974  sub     rsp, 0D0h
0x18000397b  mov     rdi, r9
0x18000397e  mov     r14d, r8d
0x180003981  mov     rbx, rdx
0x180003984  mov     rsi, rcx
0x180003987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000398e  lea     rax, WPP_GLOBAL_Control
0x180003995  cmp     rcx, rax
0x180003998  jz      short loc_1800039B8
0x18000399a  test    dword ptr [rcx+1Ch], 20000000h
0x1800039a1  jz      short loc_1800039B8
0x1800039a3  mov     rcx, [rcx+10h]
0x1800039a7  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x1800039ae  mov     edx, 13h
0x1800039b3  call    WPP_SF_
0x1800039b8  mov     r8d, 0D8h; unsigned __int16
0x1800039be  lea     rdx, aCsxondiskcache_10; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x1800039c5  lea     rcx, [rbp+57h+var_60]; this
0x1800039c9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800039ce  mov     [rbp+57h+var_78], 0
0x1800039d6  lea     rax, qword_18001A620
0x1800039dd  mov     [rbp+57h+var_80], rax
0x1800039e1  lea     rcx, [rbp+57h+var_90]; this
0x1800039e5  mov     [rbp+57h+var_70], rax
0x1800039e9  mov     [rbp+57h+var_90], rax
0x1800039ed  mov     [rbp+57h+var_68], 0
0x1800039f5  mov     [rbp+57h+var_88], 0
0x1800039fd  test    rbx, rbx
0x180003a00  jz      short loc_180003A21
0x180003a02  mov     rdx, rbx; struct _GUID *
0x180003a05  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x180003a0a  mov     ebx, eax
0x180003a0c  mov     [rbp+57h+var_60], eax
0x180003a0f  test    eax, eax
0x180003a11  mov     eax, 0DFh
0x180003a16  jns     short loc_180003A3B
0x180003a18  mov     [rbp+57h+var_5A], ax
0x180003a1c  jmp     loc_180003ACB
0x180003a21  lea     rdx, asc_180018904; "*"
0x180003a28  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180003a2d  mov     ebx, eax
0x180003a2f  mov     [rbp+57h+var_60], eax
0x180003a32  test    eax, eax
0x180003a34  mov     eax, 0E3h
0x180003a39  jmp     short loc_180003A16
0x180003a3b  mov     r9, [rsi+10h]
0x180003a3f  lea     rcx, [rbp+57h+var_80]; this
0x180003a43  mov     r8, [rbp+57h+var_90]
0x180003a47  mov     [rbp+57h+var_5C], ax
0x180003a4b  test    r14d, r14d
0x180003a4e  jz      loc_180003AFF
0x180003a54  lea     rdx, aTempSS; "Temp_%s_%s"
0x180003a5b  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180003a60  mov     ebx, eax
0x180003a62  mov     [rbp+57h+var_60], eax
0x180003a65  test    eax, eax
0x180003a67  mov     eax, 0E9h
0x180003a6c  js      short loc_180003A18
0x180003a6e  mov     r8, [rbp+57h+var_80]; unsigned __int16 *
0x180003a72  lea     rcx, [rbp+57h+var_70]; this
0x180003a76  mov     rdx, [rsi]; unsigned __int16 *
0x180003a79  mov     [rbp+57h+var_5C], ax
0x180003a7d  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180003a82  mov     ebx, eax
0x180003a84  mov     [rbp+57h+var_60], eax
0x180003a87  test    eax, eax
0x180003a89  mov     eax, 0F1h
0x180003a8e  js      short loc_180003A18
0x180003a90  cmp     dword ptr [rdi+8], 0
0x180003a94  mov     [rbp+57h+var_5C], ax
0x180003a98  jz      short loc_180003AA9
0x180003a9a  mov     rcx, [rdi]
0x180003a9d  xor     eax, eax
0x180003a9f  mov     dword ptr [rdi+8], 0
0x180003aa6  mov     [rcx], ax
0x180003aa9  mov     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180003aad  mov     rcx, rdi; this
0x180003ab0  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180003ab5  mov     ebx, eax
0x180003ab7  mov     [rbp+57h+var_60], eax
0x180003aba  test    eax, eax
0x180003abc  mov     eax, 0F3h
0x180003ac1  js      loc_180003A18
0x180003ac7  mov     [rbp+57h+var_5C], ax
0x180003acb  lea     rcx, [rbp+57h+var_90]; this
0x180003acf  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180003ad4  lea     rcx, [rbp+57h+var_70]; this
0x180003ad8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180003add  lea     rcx, [rbp+57h+var_80]; this
0x180003ae1  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180003ae6  lea     rcx, [rbp+57h+var_60]; this
0x180003aea  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180003aef  mov     eax, ebx
0x180003af1  add     rsp, 0D0h
0x180003af8  pop     r14
0x180003afa  pop     rdi
0x180003afb  pop     rsi
0x180003afc  pop     rbx
0x180003afd  pop     rbp
0x180003afe  retn
0x180003aff  lea     rdx, aSS; "%s_%s"
0x180003b06  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180003b0b  mov     ebx, eax
0x180003b0d  mov     [rbp+57h+var_60], eax
0x180003b10  test    eax, eax
0x180003b12  mov     eax, 0EEh
0x180003b17  jmp     loc_180003A6C
```
