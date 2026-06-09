# CImpPerf::RefreshProperty(long,IWbemClassObject *,ushort *,CProvObj &,CObject *,CVariant *,int)

- ea: `0x180011300`
- end: `0x18001169a`
- name: `?RefreshProperty@CImpPerf@@UEAAJJPEAUIWbemClassObject@@PEAGAEAVCProvObj@@PEAVCObject@@PEAVCVariant@@H@Z`
- size: `922`
- prototype: `__int64 __fastcall(CImpPerf *this, int, struct IWbemClassObject *, unsigned __int16 *, struct CProvObj *, struct CObject *, struct CVariant *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004260`
- `0x1800087c0`
- `0x180008a80`
- `0x180008c30`
- `0x1800091e0`
- `0x18000cb10`
- `0x18000f364`
- `0x1800101d4`
- `0x180010dc8`
- `0x180011300`
- `0x180015646`
- `0x180015652`
- `0x180015680`

## import_xrefs

- `msvcrt!mbstowcs` at `0x1800115e5`
- `msvcrt!mbstowcs` at `0x1800115e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800115ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800115ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011658`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011658`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800113a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800113a3`
- `OLEAUT32!__imp_SysAllocString` at `0x180011608`
- `OLEAUT32!__imp_SysAllocString` at `0x180011608`
- `OLEAUT32!__imp_VariantClear` at `0x1800115f6`
- `OLEAUT32!__imp_VariantClear` at `0x1800115f6`

## pseudocode

```c
__int64 __fastcall CImpPerf::RefreshProperty(
        CImpPerf *this,
        int a2,
        struct IWbemClassObject *a3,
        unsigned __int16 *a4,
        struct CProvObj *a5,
        struct CObject *a6,
        struct CVariant *a7)
{
  void *v10; // rcx
  unsigned int Data; // ebx
  int v12; // r15d
  int v13; // esi
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  size_t v16; // rsi
  SIZE_T v17; // r15
  wchar_t *v18; // rax
  wchar_t *v19; // rdi
  int v20; // ecx
  void *v21; // rcx
  unsigned int v23; // [rsp+60h] [rbp-A0h] BYREF
  float v24; // [rsp+64h] [rbp-9Ch] BYREF
  size_t MaxCount; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v27; // [rsp+74h] [rbp-8Ch] BYREF
  struct _PERF_DATA_BLOCK *v28; // [rsp+78h] [rbp-88h] BYREF
  char *Source; // [rsp+80h] [rbp-80h] BYREF
  struct _PERF_DATA_BLOCK *v30; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[8]; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-68h] BYREF
  void *v33; // [rsp+B0h] [rbp-50h] BYREF
  struct CVariant *v34; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v35; // [rsp+C0h] [rbp-40h]
  _BYTE v36[64]; // [rsp+D0h] [rbp-30h] BYREF
  int v37; // [rsp+110h] [rbp+10h]

  v35 = a4;
  v34 = a7;
  v24 = 0.0;
  v26 = 0;
  v28 = 0;
  v30 = 0;
  v23 = 0;
  v27 = 0;
  MaxCount = 0;
  memset_0(v36, 0, 0x68u);
  Source = 0;
  v33 = 0;
  CVariant::CVariant((CVariant *)v31);
  v10 = (void *)*((_QWORD *)this + 16);
  if ( !v10 || (WaitForSingleObject(v10, 0x1388u) & 0xFFFFFF7F) != 0 )
    goto LABEL_26;
  Data = CImpPerf::LoadData((PCNZWCH *)this, a5, (struct _LINESTRUCT *)v36, &v26, (int *)&MaxCount + 1, &v28, &v23, 0);
  if ( Data )
    goto LABEL_23;
  v12 = HIDWORD(MaxCount);
  v13 = v26;
  Data = CImpPerf::FindData(
           this,
           v28,
           v23,
           v26,
           SHIDWORD(MaxCount),
           a5,
           (unsigned int *)&MaxCount,
           (void **)&Source,
           (struct _LINESTRUCT *)v36,
           1,
           0);
  if ( Data )
    goto LABEL_23;
  v14 = v37 & 0xC00;
  if ( v14 != 1024 )
  {
    if ( (v37 & 0xC00) == 0 )
    {
LABEL_11:
      v24 = CounterEntry((struct _LINESTRUCT *)v36);
      CVariant::SetData((CVariant *)v31, &v24, 4u, -1);
LABEL_22:
      Data = CVariant::DoPut((CVariant *)v31, a2, a3, v35, v34);
      goto LABEL_23;
    }
    if ( v14 != 2048 )
      goto LABEL_22;
    v16 = (unsigned int)MaxCount;
    if ( (unsigned int)MaxCount <= 0xFFFFFFFD )
    {
      v17 = (unsigned int)(MaxCount + 2);
      v18 = (wchar_t *)CoTaskMemAlloc(v17);
      v19 = v18;
      if ( v18 )
      {
        memset_0(v18, 0, v17);
        if ( (v37 & 0x10000) != 0 )
          mbstowcs(v19, Source, v16);
        else
          memcpy_0(v19, Source, v16);
        VariantClear(&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(v19);
        v20 = 0;
        if ( !pvarg.llVal )
          v20 = -2147217402;
        Data = v20;
        CoTaskMemFree(v19);
        if ( Data )
          goto LABEL_23;
        goto LABEL_22;
      }
      Data = -2147217402;
      goto LABEL_23;
    }
LABEL_26:
    CVariant::~CVariant((CVariant *)v31);
    return 2147749889LL;
  }
  CProvObj::sGetToken(a5, 0);
  Data = PerfCache::dwGetPair(
           (CImpPerf *)((char *)this + 136),
           v15,
           v13,
           (unsigned __int8 **)&v30,
           &v27,
           (unsigned __int8 **)&v28,
           &v23,
           (struct _LINESTRUCT *)v36);
  if ( !Data )
  {
    Data = CImpPerf::FindData(
             this,
             v28,
             v23,
             v13,
             v12,
             a5,
             (unsigned int *)&MaxCount,
             (void **)&Source,
             (struct _LINESTRUCT *)v36,
             1,
             0);
    if ( !Data )
    {
      Data = CImpPerf::FindData(
               this,
               v30,
               v27,
               v13,
               v12,
               a5,
               (unsigned int *)&MaxCount,
               &v33,
               (struct _LINESTRUCT *)v36,
               0,
               0);
      if ( !Data )
        goto LABEL_11;
    }
  }
LABEL_23:
  v21 = (void *)*((_QWORD *)this + 16);
  if ( v21 )
    ReleaseMutex(v21);
  CVariant::~CVariant((CVariant *)v31);
  return Data;
}

```

## disassembly

```asm
0x180011300  push    rbp
0x180011302  push    rbx
0x180011303  push    rsi
0x180011304  push    rdi
0x180011305  push    r12
0x180011307  push    r13
0x180011309  push    r14
0x18001130b  push    r15
0x18001130d  lea     rbp, [rsp-58h]
0x180011312  sub     rsp, 158h
0x180011319  mov     rax, cs:__security_cookie
0x180011320  xor     rax, rsp
0x180011323  mov     [rbp+90h+var_50], rax
0x180011327  mov     [rbp+90h+var_D0], r9
0x18001132b  mov     r13, r8
0x18001132e  mov     r12d, edx
0x180011331  mov     r14, rcx
0x180011334  mov     rdi, [rbp+90h+arg_20]
0x18001133b  mov     rax, [rbp+90h+arg_30]
0x180011342  mov     [rbp+90h+var_D8], rax
0x180011346  mov     [rsp+190h+var_12C], 0
0x18001134e  xor     ebx, ebx
0x180011350  mov     [rsp+190h+var_120], ebx
0x180011354  mov     dword ptr [rsp+190h+MaxCount+4], ebx
0x180011358  mov     [rsp+190h+var_118], rbx
0x18001135d  mov     [rbp+90h+var_108], rbx
0x180011361  mov     [rsp+190h+var_130], ebx
0x180011365  mov     [rsp+190h+var_11C], ebx
0x180011369  mov     dword ptr [rsp+190h+MaxCount], ebx
0x18001136d  xor     edx, edx; Val
0x18001136f  lea     r8d, [rbx+68h]; Size
0x180011373  lea     rcx, [rbp+90h+var_C0]; void *
0x180011377  call    memset_0
0x18001137c  mov     [rbp+90h+Source], rbx
0x180011380  mov     [rbp+90h+var_E0], rbx
0x180011384  lea     rcx, [rbp+90h+var_100]; this
0x180011388  call    ??0CVariant@@QEAA@XZ; CVariant::CVariant(void)
0x18001138d  nop
0x18001138e  mov     rcx, [r14+80h]; hHandle
0x180011395  test    rcx, rcx
0x180011398  jz      loc_18001166C
0x18001139e  mov     edx, 1388h; dwMilliseconds
0x1800113a3  call    cs:__imp_WaitForSingleObject
0x1800113a9  test    eax, 0FFFFFF7Fh
0x1800113ae  jnz     loc_18001166C
0x1800113b4  mov     dword ptr [rsp+190h+var_158], ebx; int
0x1800113b8  lea     rax, [rsp+190h+var_130]
0x1800113bd  mov     [rsp+190h+var_160], rax; unsigned int *
0x1800113c2  lea     rax, [rsp+190h+var_118]
0x1800113c7  mov     [rsp+190h+var_168], rax; struct _PERF_DATA_BLOCK **
0x1800113cc  lea     rax, [rsp+190h+MaxCount+4]
0x1800113d1  mov     [rsp+190h+var_170], rax; int *
0x1800113d6  lea     r9, [rsp+190h+var_120]; int *
0x1800113db  lea     r8, [rbp+90h+var_C0]; struct _LINESTRUCT *
0x1800113df  mov     rdx, rdi; struct CProvObj *
0x1800113e2  mov     rcx, r14; this
0x1800113e5  call    ?LoadData@CImpPerf@@QEAAJAEAVCProvObj@@PEAU_LINESTRUCT@@PEAH2PEAPEAU_PERF_DATA_BLOCK@@PEAKH@Z; CImpPerf::LoadData(CProvObj &,_LINESTRUCT *,int *,int *,_PERF_DATA_BLOCK * *,ulong *,int)
0x1800113ea  mov     ebx, eax
0x1800113ec  test    eax, eax
0x1800113ee  jnz     loc_18001164C
0x1800113f4  mov     [rsp+190h+var_140], 0; struct CEnumPerfInfo *
0x1800113fd  mov     [rsp+190h+var_148], 1; int
0x180011405  lea     rax, [rbp+90h+var_C0]
0x180011409  mov     [rsp+190h+var_150], rax; struct _LINESTRUCT *
0x18001140e  lea     rax, [rbp+90h+Source]
0x180011412  mov     [rsp+190h+var_158], rax; void **
0x180011417  lea     rax, [rsp+190h+MaxCount]
0x18001141c  mov     [rsp+190h+var_160], rax; unsigned int *
0x180011421  mov     [rsp+190h+var_168], rdi; struct CProvObj *
0x180011426  mov     r15d, dword ptr [rsp+190h+MaxCount+4]
0x18001142b  mov     dword ptr [rsp+190h+var_170], r15d; int
0x180011430  mov     esi, [rsp+190h+var_120]
0x180011434  mov     r9d, esi; int
0x180011437  mov     r8d, [rsp+190h+var_130]; unsigned int
0x18001143c  mov     rdx, [rsp+190h+var_118]; struct _PERF_DATA_BLOCK *
0x180011441  mov     rcx, r14; this
0x180011444  call    ?FindData@CImpPerf@@QEAAJPEAU_PERF_DATA_BLOCK@@KHHAEAVCProvObj@@PEAKPEAPEAXPEAU_LINESTRUCT@@HPEAVCEnumPerfInfo@@@Z; CImpPerf::FindData(_PERF_DATA_BLOCK *,ulong,int,int,CProvObj &,ulong *,void * *,_LINESTRUCT *,int,CEnumPerfInfo *)
0x180011449  mov     ebx, eax
0x18001144b  test    eax, eax
0x18001144d  jnz     loc_18001164C
0x180011453  mov     eax, [rbp+90h+var_80]
0x180011456  and     eax, 0C00h
0x18001145b  cmp     eax, 400h
0x180011460  jnz     loc_18001155D
0x180011466  xor     edx, edx; int
0x180011468  mov     rcx, rdi; this
0x18001146b  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180011470  lea     rcx, [r14+88h]; this
0x180011477  lea     rax, [rbp+90h+var_C0]
0x18001147b  mov     [rsp+190h+var_158], rax; struct _LINESTRUCT *
0x180011480  lea     rax, [rsp+190h+var_130]
0x180011485  mov     [rsp+190h+var_160], rax; unsigned int *
0x18001148a  lea     rax, [rsp+190h+var_118]
0x18001148f  mov     [rsp+190h+var_168], rax; unsigned __int8 **
0x180011494  lea     rax, [rsp+190h+var_11C]
0x180011499  mov     [rsp+190h+var_170], rax; unsigned int *
0x18001149e  lea     r9, [rbp+90h+var_108]; unsigned __int8 **
0x1800114a2  mov     r8d, esi; int
0x1800114a5  call    ?dwGetPair@PerfCache@@QEAAKPEBGHPEAPEAEPEAK12PEAU_LINESTRUCT@@@Z; PerfCache::dwGetPair(ushort const *,int,uchar * *,ulong *,uchar * *,ulong *,_LINESTRUCT *)
0x1800114aa  mov     ebx, eax
0x1800114ac  test    eax, eax
0x1800114ae  jnz     loc_18001164C
0x1800114b4  mov     [rsp+190h+var_140], 0; struct CEnumPerfInfo *
0x1800114bd  mov     [rsp+190h+var_148], 1; int
0x1800114c5  lea     rax, [rbp+90h+var_C0]
0x1800114c9  mov     [rsp+190h+var_150], rax; struct _LINESTRUCT *
0x1800114ce  lea     rax, [rbp+90h+Source]
0x1800114d2  mov     [rsp+190h+var_158], rax; void **
0x1800114d7  lea     rax, [rsp+190h+MaxCount]
0x1800114dc  mov     [rsp+190h+var_160], rax; unsigned int *
0x1800114e1  mov     [rsp+190h+var_168], rdi; struct CProvObj *
0x1800114e6  mov     dword ptr [rsp+190h+var_170], r15d; int
0x1800114eb  mov     r9d, esi; int
0x1800114ee  mov     r8d, [rsp+190h+var_130]; unsigned int
0x1800114f3  mov     rdx, [rsp+190h+var_118]; struct _PERF_DATA_BLOCK *
0x1800114f8  mov     rcx, r14; this
0x1800114fb  call    ?FindData@CImpPerf@@QEAAJPEAU_PERF_DATA_BLOCK@@KHHAEAVCProvObj@@PEAKPEAPEAXPEAU_LINESTRUCT@@HPEAVCEnumPerfInfo@@@Z; CImpPerf::FindData(_PERF_DATA_BLOCK *,ulong,int,int,CProvObj &,ulong *,void * *,_LINESTRUCT *,int,CEnumPerfInfo *)
0x180011500  mov     ebx, eax
0x180011502  test    eax, eax
0x180011504  jnz     loc_18001164C
0x18001150a  mov     [rsp+190h+var_140], 0; struct CEnumPerfInfo *
0x180011513  mov     [rsp+190h+var_148], eax; int
0x180011517  lea     rax, [rbp+90h+var_C0]
0x18001151b  mov     [rsp+190h+var_150], rax; struct _LINESTRUCT *
0x180011520  lea     rax, [rbp+90h+var_E0]
0x180011524  mov     [rsp+190h+var_158], rax; void **
0x180011529  lea     rax, [rsp+190h+MaxCount]
0x18001152e  mov     [rsp+190h+var_160], rax; unsigned int *
0x180011533  mov     [rsp+190h+var_168], rdi; struct CProvObj *
0x180011538  mov     dword ptr [rsp+190h+var_170], r15d; int
0x18001153d  mov     r9d, esi; int
0x180011540  mov     r8d, [rsp+190h+var_11C]; unsigned int
0x180011545  mov     rdx, [rbp+90h+var_108]; struct _PERF_DATA_BLOCK *
0x180011549  mov     rcx, r14; this
0x18001154c  call    ?FindData@CImpPerf@@QEAAJPEAU_PERF_DATA_BLOCK@@KHHAEAVCProvObj@@PEAKPEAPEAXPEAU_LINESTRUCT@@HPEAVCEnumPerfInfo@@@Z; CImpPerf::FindData(_PERF_DATA_BLOCK *,ulong,int,int,CProvObj &,ulong *,void * *,_LINESTRUCT *,int,CEnumPerfInfo *)
0x180011551  mov     ebx, eax
0x180011553  test    eax, eax
0x180011555  jnz     loc_18001164C
0x18001155b  jmp     short loc_180011561
0x18001155d  test    eax, eax
0x18001155f  jnz     short loc_18001158D
0x180011561  lea     rcx, [rbp+90h+var_C0]; struct _LINESTRUCT *
0x180011565  call    ?CounterEntry@@YAMPEAU_LINESTRUCT@@@Z; CounterEntry(_LINESTRUCT *)
0x18001156a  movss   [rsp+190h+var_12C], xmm0
0x180011570  mov     r8d, 4; unsigned __int16
0x180011576  or      r9d, 0FFFFFFFFh; int
0x18001157a  lea     rdx, [rsp+190h+var_12C]; void *
0x18001157f  lea     rcx, [rbp+90h+var_100]; this
0x180011583  call    ?SetData@CVariant@@QEAAJPEAXGH@Z; CVariant::SetData(void *,ushort,int)
0x180011588  jmp     loc_18001162E
0x18001158d  cmp     eax, 800h
0x180011592  jnz     loc_18001162E
0x180011598  mov     esi, dword ptr [rsp+190h+MaxCount]
0x18001159c  cmp     esi, 0FFFFFFFDh
0x18001159f  ja      loc_18001166C
0x1800115a5  lea     eax, [rsi+2]
0x1800115a8  mov     r15d, eax
0x1800115ab  mov     ecx, eax; cb
0x1800115ad  call    cs:__imp_CoTaskMemAlloc
0x1800115b3  mov     rdi, rax
0x1800115b6  test    rax, rax
0x1800115b9  jnz     short loc_1800115C5
0x1800115bb  mov     ebx, 80041006h
0x1800115c0  jmp     loc_18001164C
0x1800115c5  mov     r8, r15; Size
0x1800115c8  xor     edx, edx; Val
0x1800115ca  mov     rcx, rdi; void *
0x1800115cd  call    memset_0
0x1800115d2  mov     r8, rsi; Size
0x1800115d5  mov     rdx, [rbp+90h+Source]; Src
0x1800115d9  mov     rcx, rdi; void *
0x1800115dc  test    [rbp+90h+var_80], 10000h
0x1800115e3  jz      short loc_1800115ED
0x1800115e5  call    cs:__imp_mbstowcs
0x1800115eb  jmp     short loc_1800115F2
0x1800115ed  call    memcpy_0
0x1800115f2  lea     rcx, [rbp+90h+pvarg]; pvarg
0x1800115f6  call    cs:__imp_VariantClear
0x1800115fc  mov     eax, 8
0x180011601  mov     word ptr [rbp+90h+pvarg], ax
0x180011605  mov     rcx, rdi; psz
0x180011608  call    cs:__imp_SysAllocString
0x18001160e  mov     qword ptr [rbp+90h+pvarg+8], rax
0x180011612  mov     ecx, ebx
0x180011614  mov     ebx, 80041006h
0x180011619  test    rax, rax
0x18001161c  cmovz   ecx, ebx
0x18001161f  mov     ebx, ecx
0x180011621  mov     rcx, rdi; pv
0x180011624  call    cs:__imp_CoTaskMemFree
0x18001162a  test    ebx, ebx
0x18001162c  jnz     short loc_18001164C
0x18001162e  mov     rax, [rbp+90h+var_D8]
0x180011632  mov     [rsp+190h+var_170], rax; struct CVariant *
0x180011637  mov     r9, [rbp+90h+var_D0]; unsigned __int16 *
0x18001163b  mov     r8, r13; struct IWbemClassObject *
0x18001163e  mov     edx, r12d; int
0x180011641  lea     rcx, [rbp+90h+var_100]; this
0x180011645  call    ?DoPut@CVariant@@QEAAJJPEAUIWbemClassObject@@PEAGPEAV1@@Z; CVariant::DoPut(long,IWbemClassObject *,ushort *,CVariant *)
0x18001164a  mov     ebx, eax
0x18001164c  mov     rcx, [r14+80h]; hMutex
0x180011653  test    rcx, rcx
0x180011656  jz      short loc_18001165F
0x180011658  call    cs:__imp_ReleaseMutex
0x18001165e  nop
0x18001165f  lea     rcx, [rbp+90h+var_100]; this
0x180011663  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x180011668  mov     eax, ebx
0x18001166a  jmp     short loc_18001167A
0x18001166c  lea     rcx, [rbp+90h+var_100]; this
0x180011670  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x180011675  mov     eax, 80041001h
0x18001167a  mov     rcx, [rbp+90h+var_50]
0x18001167e  xor     rcx, rsp; StackCookie
0x180011681  call    __security_check_cookie
0x180011686  add     rsp, 158h
0x18001168d  pop     r15
0x18001168f  pop     r14
0x180011691  pop     r13
0x180011693  pop     r12
0x180011695  pop     rdi
0x180011696  pop     rsi
0x180011697  pop     rbx
0x180011698  pop     rbp
0x180011699  retn
```
