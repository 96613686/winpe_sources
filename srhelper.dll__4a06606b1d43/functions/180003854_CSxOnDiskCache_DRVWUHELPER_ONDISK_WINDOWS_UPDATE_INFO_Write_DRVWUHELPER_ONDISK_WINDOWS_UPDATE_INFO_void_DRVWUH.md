# CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize(ushort const *,ushort const *)

- ea: `0x180003854`
- end: `0x18000395f`
- name: `?Initialize@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJPEBG0@Z`
- size: `267`
- prototype: `__int64 __fastcall(CBsString *this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000b3b0`
- `0x18000bbe0`
- `0x18000c468`

## callees

- `0x180003854`
- `0x180003ce0`
- `0x18000d348`
- `0x18000d43c`
- `0x180014f38`

## string_xrefs

- `0x1800038a3`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize`
- `0x180003926`: `WindowsUpdateInfo`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize(
        CBsString *this,
        unsigned __int16 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // ebx
  __int16 v7; // ax
  bool v8; // zf
  _WORD *v9; // rcx
  CBsString *v10; // rcx
  _WORD *v11; // rdx
  int v13; // [rsp+20h] [rbp-40h] BYREF
  __int16 v14; // [rsp+24h] [rbp-3Ch]
  __int16 v15; // [rsp+26h] [rbp-3Ah]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v13,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_"
    "INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_I"
    "NFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize",
    42);
  if ( a2 )
  {
    v8 = *((_DWORD *)this + 2) == 0;
    v14 = 45;
    v13 = 0;
    if ( !v8 )
    {
      v9 = *(_WORD **)this;
      *((_DWORD *)this + 2) = 0;
      *v9 = 0;
    }
    v6 = CBsString::Append(this, a2);
    v13 = v6;
    v7 = 46;
    if ( v6 >= 0 )
    {
      v10 = (CBsString *)((char *)this + 16);
      v14 = 46;
      if ( *((_DWORD *)this + 6) )
      {
        v11 = *(_WORD **)v10;
        *((_DWORD *)this + 6) = 0;
        *v11 = 0;
      }
      v6 = CBsString::Append(v10, L"WindowsUpdateInfo");
      v13 = v6;
      v7 = 47;
      if ( v6 >= 0 )
      {
        v14 = 47;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v6 = -2147024809;
    v7 = 44;
    v13 = -2147024809;
  }
  v15 = v7;
LABEL_14:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v4, v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003854  mov     [rsp-8+arg_0], rbx
0x180003859  mov     [rsp-8+arg_8], rdi
0x18000385e  push    rbp
0x18000385f  mov     rbp, rsp
0x180003862  sub     rsp, 60h
0x180003866  mov     rbx, rdx
0x180003869  mov     rdi, rcx
0x18000386c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003873  lea     rax, WPP_GLOBAL_Control
0x18000387a  cmp     rcx, rax
0x18000387d  jz      short loc_18000389D
0x18000387f  test    dword ptr [rcx+1Ch], 20000000h
0x180003886  jz      short loc_18000389D
0x180003888  mov     rcx, [rcx+10h]
0x18000388c  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180003893  mov     edx, 0Ah
0x180003898  call    WPP_SF_
0x18000389d  mov     r8d, 2Ah ; '*'; unsigned __int16
0x1800038a3  lea     rdx, aCsxondiskcache_0; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x1800038aa  lea     rcx, [rbp+var_40]; this
0x1800038ae  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800038b3  test    rbx, rbx
0x1800038b6  jnz     short loc_1800038CB
0x1800038b8  mov     ebx, 80070057h
0x1800038bd  mov     eax, 2Ch ; ','
0x1800038c2  mov     [rbp+var_40], ebx
0x1800038c5  mov     [rbp+var_3A], ax
0x1800038c9  jmp     short loc_180003944
0x1800038cb  cmp     dword ptr [rdi+8], 0
0x1800038cf  mov     eax, 2Dh ; '-'
0x1800038d4  mov     [rbp+var_3C], ax
0x1800038d8  mov     [rbp+var_40], 0
0x1800038df  jz      short loc_1800038F0
0x1800038e1  mov     rcx, [rdi]
0x1800038e4  xor     eax, eax
0x1800038e6  mov     dword ptr [rdi+8], 0
0x1800038ed  mov     [rcx], ax
0x1800038f0  mov     rdx, rbx; unsigned __int16 *
0x1800038f3  mov     rcx, rdi; this
0x1800038f6  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1800038fb  mov     ebx, eax
0x1800038fd  mov     [rbp+var_40], eax
0x180003900  test    eax, eax
0x180003902  mov     eax, 2Eh ; '.'
0x180003907  js      short loc_1800038C5
0x180003909  lea     rcx, [rdi+10h]; this
0x18000390d  mov     [rbp+var_3C], ax
0x180003911  cmp     dword ptr [rcx+8], 0
0x180003915  jz      short loc_180003926
0x180003917  mov     rdx, [rcx]
0x18000391a  xor     eax, eax
0x18000391c  mov     dword ptr [rcx+8], 0
0x180003923  mov     [rdx], ax
0x180003926  lea     rdx, aWindowsupdatei; "WindowsUpdateInfo"
0x18000392d  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180003932  mov     ebx, eax
0x180003934  mov     [rbp+var_40], eax
0x180003937  test    eax, eax
0x180003939  mov     eax, 2Fh ; '/'
0x18000393e  js      short loc_1800038C5
0x180003940  mov     [rbp+var_3C], ax
0x180003944  lea     rcx, [rbp+var_40]; this
0x180003948  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000394d  mov     rdi, [rsp+60h+arg_8]
0x180003952  mov     eax, ebx
0x180003954  mov     rbx, [rsp+60h+arg_0]
0x180003959  add     rsp, 60h
0x18000395d  pop     rbp
0x18000395e  retn
```
