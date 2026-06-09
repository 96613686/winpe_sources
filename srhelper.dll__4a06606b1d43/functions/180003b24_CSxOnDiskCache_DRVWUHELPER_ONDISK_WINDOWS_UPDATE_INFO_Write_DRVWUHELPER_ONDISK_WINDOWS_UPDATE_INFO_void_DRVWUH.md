# CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(_GUID const *,int,CBsString *)

- ea: `0x180003b24`
- end: `0x180003cd8`
- name: `?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, int, CBsString *)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800022e4`
- `0x180002818`
- `0x180002e9c`
- `0x180003550`

## callees

- `0x180003b24`
- `0x180003ce0`
- `0x18000d348`
- `0x18000d43c`
- `0x180014f38`
- `0x180015150`
- `0x18001528c`
- `0x180015390`
- `0x180015760`

## string_xrefs

- `0x180003c10`: `Temp_%s_%s`
- `0x180003b7a`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(
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
  __int64 v17; // rdx
  __int64 v18; // r8
  const unsigned __int16 *v20; // [rsp+20h] [rbp-79h]
  const unsigned __int16 *v21; // [rsp+28h] [rbp-71h]
  const unsigned __int16 *v22; // [rsp+30h] [rbp-69h]
  const unsigned __int16 *v23; // [rsp+38h] [rbp-61h]
  const unsigned __int16 *v24; // [rsp+40h] [rbp-59h]
  const unsigned __int16 *v25; // [rsp+48h] [rbp-51h]
  const unsigned __int16 *v26; // [rsp+50h] [rbp-49h]
  _QWORD v27[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 *v28[2]; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v29[2]; // [rsp+80h] [rbp-19h] BYREF
  int v30; // [rsp+90h] [rbp-9h] BYREF
  __int16 v31; // [rsp+94h] [rbp-5h]
  __int16 v32; // [rsp+96h] [rbp-3h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v30,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_"
    "INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_I"
    "NFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName",
    216);
  v28[1] = 0;
  v28[0] = (unsigned __int16 *)qword_18001A620;
  v29[0] = (unsigned __int16 *)qword_18001A620;
  v27[0] = qword_18001A620;
  v29[1] = 0;
  v27[1] = 0;
  if ( a2 )
  {
    v8 = CBsString::Set((CBsString *)v27, a2);
    v30 = v8;
    v9 = v8 < 0;
    v10 = 223;
  }
  else
  {
    v8 = CBsString::Append((CBsString *)v27, L"*");
    v30 = v8;
    v9 = v8 < 0;
    v10 = 227;
  }
  if ( v9 )
    goto LABEL_7;
  v11 = *(_QWORD *)(a1 + 16);
  v31 = v10;
  if ( a3 )
  {
    v8 = CBsString::Format((CBsString *)v28, L"Temp_%s_%s", v27[0], v11);
    v30 = v8;
    v13 = v8 < 0;
    v10 = 233;
  }
  else
  {
    v8 = CBsString::Format((CBsString *)v28, L"%s_%s", v27[0], v11);
    v30 = v8;
    v13 = v8 < 0;
    v10 = 238;
  }
  if ( v13 )
    goto LABEL_7;
  v14 = *(const unsigned __int16 **)a1;
  v31 = v10;
  v8 = CBsString::SetPath((CBsString *)v29, v14, v28[0], v12, v20, v21, v22, v23, v24, v25, v26);
  v30 = v8;
  v10 = 241;
  if ( v8 < 0 )
    goto LABEL_7;
  v15 = *((_DWORD *)a4 + 2) == 0;
  v31 = 241;
  if ( !v15 )
  {
    v16 = *(_WORD **)a4;
    *((_DWORD *)a4 + 2) = 0;
    *v16 = 0;
  }
  v8 = CBsString::Append(a4, v29[0]);
  v30 = v8;
  v10 = 243;
  if ( v8 < 0 )
LABEL_7:
    v32 = v10;
  else
    v31 = 243;
  CBsString::_Release((CBsString *)v27);
  CBsString::_Release((CBsString *)v29);
  CBsString::_Release((CBsString *)v28);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v30, v17, v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003b24  push    rbp
0x180003b26  push    rbx
0x180003b27  push    rsi
0x180003b28  push    rdi
0x180003b29  push    r14
0x180003b2b  lea     rbp, [rsp-37h]
0x180003b30  sub     rsp, 0D0h
0x180003b37  mov     rdi, r9
0x180003b3a  mov     r14d, r8d
0x180003b3d  mov     rbx, rdx
0x180003b40  mov     rsi, rcx
0x180003b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b4a  lea     rax, WPP_GLOBAL_Control
0x180003b51  cmp     rcx, rax
0x180003b54  jz      short loc_180003B74
0x180003b56  test    dword ptr [rcx+1Ch], 20000000h
0x180003b5d  jz      short loc_180003B74
0x180003b5f  mov     rcx, [rcx+10h]
0x180003b63  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180003b6a  mov     edx, 13h
0x180003b6f  call    WPP_SF_
0x180003b74  mov     r8d, 0D8h; unsigned __int16
0x180003b7a  lea     rdx, aCsxondiskcache_6; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x180003b81  lea     rcx, [rbp+57h+var_60]; this
0x180003b85  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180003b8a  mov     [rbp+57h+var_78], 0
0x180003b92  lea     rax, qword_18001A620
0x180003b99  mov     [rbp+57h+var_80], rax
0x180003b9d  lea     rcx, [rbp+57h+var_90]; this
0x180003ba1  mov     [rbp+57h+var_70], rax
0x180003ba5  mov     [rbp+57h+var_90], rax
0x180003ba9  mov     [rbp+57h+var_68], 0
0x180003bb1  mov     [rbp+57h+var_88], 0
0x180003bb9  test    rbx, rbx
0x180003bbc  jz      short loc_180003BDD
0x180003bbe  mov     rdx, rbx; struct _GUID *
0x180003bc1  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x180003bc6  mov     ebx, eax
0x180003bc8  mov     [rbp+57h+var_60], eax
0x180003bcb  test    eax, eax
0x180003bcd  mov     eax, 0DFh
0x180003bd2  jns     short loc_180003BF7
0x180003bd4  mov     [rbp+57h+var_5A], ax
0x180003bd8  jmp     loc_180003C87
0x180003bdd  lea     rdx, asc_180018904; "*"
0x180003be4  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180003be9  mov     ebx, eax
0x180003beb  mov     [rbp+57h+var_60], eax
0x180003bee  test    eax, eax
0x180003bf0  mov     eax, 0E3h
0x180003bf5  jmp     short loc_180003BD2
0x180003bf7  mov     r9, [rsi+10h]
0x180003bfb  lea     rcx, [rbp+57h+var_80]; this
0x180003bff  mov     r8, [rbp+57h+var_90]
0x180003c03  mov     [rbp+57h+var_5C], ax
0x180003c07  test    r14d, r14d
0x180003c0a  jz      loc_180003CBB
0x180003c10  lea     rdx, aTempSS; "Temp_%s_%s"
0x180003c17  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180003c1c  mov     ebx, eax
0x180003c1e  mov     [rbp+57h+var_60], eax
0x180003c21  test    eax, eax
0x180003c23  mov     eax, 0E9h
0x180003c28  js      short loc_180003BD4
0x180003c2a  mov     r8, [rbp+57h+var_80]; unsigned __int16 *
0x180003c2e  lea     rcx, [rbp+57h+var_70]; this
0x180003c32  mov     rdx, [rsi]; unsigned __int16 *
0x180003c35  mov     [rbp+57h+var_5C], ax
0x180003c39  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180003c3e  mov     ebx, eax
0x180003c40  mov     [rbp+57h+var_60], eax
0x180003c43  test    eax, eax
0x180003c45  mov     eax, 0F1h
0x180003c4a  js      short loc_180003BD4
0x180003c4c  cmp     dword ptr [rdi+8], 0
0x180003c50  mov     [rbp+57h+var_5C], ax
0x180003c54  jz      short loc_180003C65
0x180003c56  mov     rcx, [rdi]
0x180003c59  xor     eax, eax
0x180003c5b  mov     dword ptr [rdi+8], 0
0x180003c62  mov     [rcx], ax
0x180003c65  mov     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180003c69  mov     rcx, rdi; this
0x180003c6c  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180003c71  mov     ebx, eax
0x180003c73  mov     [rbp+57h+var_60], eax
0x180003c76  test    eax, eax
0x180003c78  mov     eax, 0F3h
0x180003c7d  js      loc_180003BD4
0x180003c83  mov     [rbp+57h+var_5C], ax
0x180003c87  lea     rcx, [rbp+57h+var_90]; this
0x180003c8b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180003c90  lea     rcx, [rbp+57h+var_70]; this
0x180003c94  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180003c99  lea     rcx, [rbp+57h+var_80]; this
0x180003c9d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180003ca2  lea     rcx, [rbp+57h+var_60]; this
0x180003ca6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180003cab  mov     eax, ebx
0x180003cad  add     rsp, 0D0h
0x180003cb4  pop     r14
0x180003cb6  pop     rdi
0x180003cb7  pop     rsi
0x180003cb8  pop     rbx
0x180003cb9  pop     rbp
0x180003cba  retn
0x180003cbb  lea     rdx, aSS; "%s_%s"
0x180003cc2  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180003cc7  mov     ebx, eax
0x180003cc9  mov     [rbp+57h+var_60], eax
0x180003ccc  test    eax, eax
0x180003cce  mov     eax, 0EEh
0x180003cd3  jmp     loc_180003C28
```
