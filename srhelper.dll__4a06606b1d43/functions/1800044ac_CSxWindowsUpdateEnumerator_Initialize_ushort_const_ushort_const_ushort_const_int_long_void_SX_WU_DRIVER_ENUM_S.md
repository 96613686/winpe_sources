# CSxWindowsUpdateEnumerator::Initialize(ushort const *,ushort const *,ushort const *,int,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)

- ea: `0x1800044ac`
- end: `0x180004656`
- name: `?Initialize@CSxWindowsUpdateEnumerator@@QEAAJPEBG00HP6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z`
- size: `426`
- prototype: `__int64 __fastcall(unsigned __int16 **this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int (__high *)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *), unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18000cc20`

## callees

- `0x1800012d4`
- `0x1800012f8`
- `0x180003ce0`
- `0x180003f1c`
- `0x1800044ac`
- `0x18000d348`
- `0x18000d43c`
- `0x18000e330`

## string_xrefs

- `0x1800044fa`: `CSxWindowsUpdateEnumerator::Initialize`

## pseudocode

```c
__int64 __fastcall CSxWindowsUpdateEnumerator::Initialize(
        unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        int (__high *a6)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *),
        unsigned __int16 *a7)
{
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // ebx
  __int16 v13; // ax
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rax
  int v17; // [rsp+20h] [rbp-40h] BYREF
  __int16 v18; // [rsp+24h] [rbp-3Ch]
  __int16 v19; // [rsp+26h] [rbp-3Ah]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSxWindowsUpdateEnumerator::Initialize", 551);
  v18 = 553;
  if ( a5 && (!a4 || !a2) )
  {
    v12 = -2147024809;
    v13 = 555;
LABEL_17:
    v17 = v12;
LABEL_18:
    v19 = v13;
    goto LABEL_19;
  }
  v17 = 0;
  v18 = 555;
  v12 = SxCopyString(a2, this + 2);
  v17 = v12;
  v13 = 557;
  if ( v12 < 0 )
    goto LABEL_18;
  v18 = 557;
  v12 = SxCopyString(0, this + 3);
  v17 = v12;
  v13 = 558;
  if ( v12 < 0 )
    goto LABEL_18;
  v18 = 558;
  v12 = SxCopyString(a4, this + 1);
  v17 = v12;
  v13 = 559;
  if ( v12 < 0 )
    goto LABEL_18;
  v14 = *this;
  v18 = 559;
  if ( v14 )
  {
    *this = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14, 0xFFFFFFFF) == 1 )
    {
      CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&public: static void CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::~CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&public: static void CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>((__int64)v14);
      operator delete(v14);
    }
  }
  *this = 0;
  v15 = (unsigned __int16 *)operator new(0x18u);
  if ( !v15 )
  {
    v12 = -2147024882;
    v13 = 561;
    goto LABEL_17;
  }
  *(_DWORD *)v15 = 1;
  *((_QWORD *)v15 + 1) = 0;
  *((_QWORD *)v15 + 2) = 0;
  *this = v15;
  v17 = 0;
  v18 = 561;
  v12 = 0;
  *((_DWORD *)this + 8) = a5;
  this[5] = (unsigned __int16 *)CSrDrvWuHelper::_EnumDriverWUNameCollector;
  this[6] = a7;
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17, v10, v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800044ac  push    rbp
0x1800044ae  push    rbx
0x1800044af  push    rsi
0x1800044b0  push    rdi
0x1800044b1  push    r14
0x1800044b3  mov     rbp, rsp
0x1800044b6  sub     rsp, 60h
0x1800044ba  mov     rsi, r9
0x1800044bd  mov     rbx, rdx
0x1800044c0  mov     rdi, rcx
0x1800044c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044ca  lea     rax, WPP_GLOBAL_Control
0x1800044d1  cmp     rcx, rax
0x1800044d4  jz      short loc_1800044F4
0x1800044d6  test    dword ptr [rcx+1Ch], 20000000h
0x1800044dd  jz      short loc_1800044F4
0x1800044df  mov     rcx, [rcx+10h]
0x1800044e3  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x1800044ea  mov     edx, 12h
0x1800044ef  call    WPP_SF_
0x1800044f4  mov     r8d, 227h; unsigned __int16
0x1800044fa  lea     rdx, aCsxwindowsupda_2; "CSxWindowsUpdateEnumerator::Initialize"
0x180004501  lea     rcx, [rbp+var_40]; this
0x180004505  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000450a  mov     r14d, [rbp+arg_20]
0x18000450e  mov     eax, 229h
0x180004513  mov     [rbp+var_3C], ax
0x180004517  test    r14d, r14d
0x18000451a  jz      short loc_180004535
0x18000451c  test    rsi, rsi
0x18000451f  jz      short loc_180004526
0x180004521  test    rbx, rbx
0x180004524  jnz     short loc_180004535
0x180004526  mov     ebx, 80070057h
0x18000452b  mov     eax, 22Bh
0x180004530  jmp     loc_180004639
0x180004535  mov     eax, 22Bh
0x18000453a  mov     [rbp+var_40], 0
0x180004541  lea     rdx, [rdi+10h]; unsigned __int16 **
0x180004545  mov     [rbp+var_3C], ax
0x180004549  mov     rcx, rbx; Src
0x18000454c  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180004551  mov     ebx, eax
0x180004553  mov     [rbp+var_40], eax
0x180004556  test    eax, eax
0x180004558  mov     eax, 22Dh
0x18000455d  js      loc_18000463C
0x180004563  lea     rdx, [rdi+18h]; unsigned __int16 **
0x180004567  mov     [rbp+var_3C], ax
0x18000456b  xor     ecx, ecx; Src
0x18000456d  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180004572  mov     ebx, eax
0x180004574  mov     [rbp+var_40], eax
0x180004577  test    eax, eax
0x180004579  mov     eax, 22Eh
0x18000457e  js      loc_18000463C
0x180004584  lea     rdx, [rdi+8]; unsigned __int16 **
0x180004588  mov     [rbp+var_3C], ax
0x18000458c  mov     rcx, rsi; Src
0x18000458f  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180004594  mov     ebx, eax
0x180004596  mov     [rbp+var_40], eax
0x180004599  test    eax, eax
0x18000459b  mov     eax, 22Fh
0x1800045a0  js      loc_18000463C
0x1800045a6  mov     rbx, [rdi]
0x1800045a9  mov     [rbp+var_3C], ax
0x1800045ad  test    rbx, rbx
0x1800045b0  jz      short loc_1800045D5
0x1800045b2  mov     qword ptr [rdi], 0
0x1800045b9  or      eax, 0FFFFFFFFh
0x1800045bc  lock xadd [rbx], eax
0x1800045c0  cmp     eax, 1
0x1800045c3  jnz     short loc_1800045D5
0x1800045c5  mov     rcx, rbx
0x1800045c8  call    ??1?$CSxArrayBuilder@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@$1?_FreeCbsHiveLoadInformation@2@SAXPEAU12@@Z$1??$SxDefaultInit@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX0@Z$1??$SxDefaultTransfer@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX00@Z@@AEAA@XZ; CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::~CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>(void)
0x1800045cd  mov     rcx, rbx; Block
0x1800045d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045d5  mov     ecx, 18h; Size
0x1800045da  mov     qword ptr [rdi], 0
0x1800045e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045e6  test    rax, rax
0x1800045e9  jz      short loc_18000462F
0x1800045eb  mov     dword ptr [rax], 1
0x1800045f1  mov     qword ptr [rax+8], 0
0x1800045f9  mov     qword ptr [rax+10h], 0
0x180004601  mov     [rdi], rax
0x180004604  mov     eax, 231h
0x180004609  mov     [rbp+var_40], 0
0x180004610  mov     [rbp+var_3C], ax
0x180004614  xor     ebx, ebx
0x180004616  lea     rax, ?_EnumDriverWUNameCollector@CSrDrvWuHelper@@CAJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z; CSrDrvWuHelper::_EnumDriverWUNameCollector(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *)
0x18000461d  mov     [rdi+20h], r14d
0x180004621  mov     [rdi+28h], rax
0x180004625  mov     rax, [rbp+arg_30]
0x180004629  mov     [rdi+30h], rax
0x18000462d  jmp     short loc_180004640
0x18000462f  mov     ebx, 8007000Eh
0x180004634  mov     eax, 231h
0x180004639  mov     [rbp+var_40], ebx
0x18000463c  mov     [rbp+var_3A], ax
0x180004640  lea     rcx, [rbp+var_40]; this
0x180004644  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180004649  mov     eax, ebx
0x18000464b  add     rsp, 60h
0x18000464f  pop     r14
0x180004651  pop     rdi
0x180004652  pop     rsi
0x180004653  pop     rbx
0x180004654  pop     rbp
0x180004655  retn
```
