# CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize(ushort const *,ushort const *)

- ea: `0x180003740`
- end: `0x18000384b`
- name: `?Initialize@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJPEBG0@Z`
- size: `267`
- prototype: `__int64 __fastcall(CBsString *this, unsigned __int16 *, __int64, unsigned __int16)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b3b0`
- `0x18000bbe0`
- `0x18000c468`

## callees

- `0x180003740`
- `0x180003ce0`
- `0x18000d348`
- `0x18000d43c`
- `0x180014f38`

## string_xrefs

- `0x18000378f`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize(
        CBsString *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 a4)
{
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
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,stru"
    "ct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_O"
    "NDISK_DRIVER_INFO *)>::Initialize",
    0x2Au,
    a4);
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
      v6 = CBsString::Append(v10, L"DriverPackageInfo");
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
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003740  mov     [rsp-8+arg_0], rbx
0x180003745  mov     [rsp-8+arg_8], rdi
0x18000374a  push    rbp
0x18000374b  mov     rbp, rsp
0x18000374e  sub     rsp, 60h
0x180003752  mov     rbx, rdx
0x180003755  mov     rdi, rcx
0x180003758  mov     rcx, cs:WPP_GLOBAL_Control
0x18000375f  lea     rax, WPP_GLOBAL_Control
0x180003766  cmp     rcx, rax
0x180003769  jz      short loc_180003789
0x18000376b  test    dword ptr [rcx+1Ch], 20000000h
0x180003772  jz      short loc_180003789
0x180003774  mov     rcx, [rcx+10h]
0x180003778  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x18000377f  mov     edx, 0Ah
0x180003784  call    WPP_SF_
0x180003789  mov     r8d, 2Ah ; '*'; unsigned __int16
0x18000378f  lea     rdx, aCsxondiskcache_3; "CSxOnDiskCache<struct _DRVWUHELPER_ONDI"...
0x180003796  lea     rcx, [rbp+var_40]; this
0x18000379a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000379f  test    rbx, rbx
0x1800037a2  jnz     short loc_1800037B7
0x1800037a4  mov     ebx, 80070057h
0x1800037a9  mov     eax, 2Ch ; ','
0x1800037ae  mov     [rbp+var_40], ebx
0x1800037b1  mov     [rbp+var_3A], ax
0x1800037b5  jmp     short loc_180003830
0x1800037b7  cmp     dword ptr [rdi+8], 0
0x1800037bb  mov     eax, 2Dh ; '-'
0x1800037c0  mov     [rbp+var_3C], ax
0x1800037c4  mov     [rbp+var_40], 0
0x1800037cb  jz      short loc_1800037DC
0x1800037cd  mov     rcx, [rdi]
0x1800037d0  xor     eax, eax
0x1800037d2  mov     dword ptr [rdi+8], 0
0x1800037d9  mov     [rcx], ax
0x1800037dc  mov     rdx, rbx; unsigned __int16 *
0x1800037df  mov     rcx, rdi; this
0x1800037e2  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1800037e7  mov     ebx, eax
0x1800037e9  mov     [rbp+var_40], eax
0x1800037ec  test    eax, eax
0x1800037ee  mov     eax, 2Eh ; '.'
0x1800037f3  js      short loc_1800037B1
0x1800037f5  lea     rcx, [rdi+10h]; this
0x1800037f9  mov     [rbp+var_3C], ax
0x1800037fd  cmp     dword ptr [rcx+8], 0
0x180003801  jz      short loc_180003812
0x180003803  mov     rdx, [rcx]
0x180003806  xor     eax, eax
0x180003808  mov     dword ptr [rcx+8], 0
0x18000380f  mov     [rdx], ax
0x180003812  lea     rdx, aDriverpackagei; "DriverPackageInfo"
0x180003819  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000381e  mov     ebx, eax
0x180003820  mov     [rbp+var_40], eax
0x180003823  test    eax, eax
0x180003825  mov     eax, 2Fh ; '/'
0x18000382a  js      short loc_1800037B1
0x18000382c  mov     [rbp+var_3C], ax
0x180003830  lea     rcx, [rbp+var_40]; this
0x180003834  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180003839  mov     rdi, [rsp+60h+arg_8]
0x18000383e  mov     eax, ebx
0x180003840  mov     rbx, [rsp+60h+arg_0]
0x180003845  add     rsp, 60h
0x180003849  pop     rbp
0x18000384a  retn
```
