# CUmRdpPrn::ConfigureAndSavePrinter(ulong,void *,int,ushort const *,ushort *,uchar *,ulong,int,int,void *)

- ea: `0x180004680`
- end: `0x180004a88`
- name: `?ConfigureAndSavePrinter@CUmRdpPrn@@AEAAKKPEAXHPEBGPEAGPEAEKHH0@Z`
- size: `1032`
- prototype: `__int64 __fastcall(struct tagDRDEVLST **this, const unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 *, LPWSTR pPrinterName, unsigned __int8 *, DWORD, int, int, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800032f0`

## callees

- `0x180004680`
- `0x180008fbc`
- `0x18000a3ac`
- `0x18000a41c`
- `0x18000b8f8`
- `0x18001294c`
- `0x1800140a4`
- `0x180014370`
- `0x180016e70`
- `0x180017494`
- `0x180017a34`
- `0x180017d14`
- `0x180017dc8`
- `0x180018200`
- `0x1800197e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004858`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004858`
- `WINSPOOL!OpenPrinterW` at `0x1800048aa`
- `WINSPOOL!OpenPrinterW` at `0x1800048aa`
- `WINSPOOL!ClosePrinter` at `0x180004a79`
- `WINSPOOL!ClosePrinter` at `0x180004a79`
- `WINSPOOL!SetPrinterDataW` at `0x180004926`
- `WINSPOOL!SetPrinterDataW` at `0x180004926`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::ConfigureAndSavePrinter(
        struct tagDRDEVLST **this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        LPWSTR pPrinterName,
        unsigned __int8 *a7,
        DWORD a8,
        int a9,
        int a10,
        void *a11)
{
  unsigned int v11; // r12d
  unsigned __int16 *v13; // r14
  CUmRdpDr *v14; // rcx
  DWORD LastError; // ebx
  unsigned int v16; // r15d
  unsigned int v17; // r9d
  unsigned int v18; // eax
  __int64 v19; // r8
  unsigned int v20; // eax
  __int64 v21; // r8
  DWORD v22; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v24; // r8
  unsigned int v25; // r9d
  int v26; // r15d
  unsigned int v27; // eax
  int v28; // edx
  int v29; // r8d
  unsigned int v30; // eax
  struct tagDRDEVLST *v31; // rdi
  struct tagDRDEVLST *v32; // rdi
  HANDLE phPrinter; // [rsp+40h] [rbp-38h] BYREF
  _PRINTER_DEFAULTSW pDefault; // [rsp+48h] [rbp-30h] BYREF
  CUmRdpRpc *pData; // [rsp+A0h] [rbp+28h] BYREF
  unsigned int v37; // [rsp+A8h] [rbp+30h] BYREF

  pData = (CUmRdpRpc *)a3;
  v11 = (unsigned int)a2;
  v13 = pPrinterName;
  phPrinter = (HANDLE)-1LL;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v37 = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  if ( !a4 || !*((_DWORD *)*this + 494) && *((_DWORD *)this + 212) )
  {
LABEL_11:
    if ( *((_DWORD *)*this + 542) )
    {
      LastError = 1115;
    }
    else
    {
      if ( a8 && !a10 && (v22 = CUmRdpPrn::SetPrinterConfigInfo((CUmRdpPrn *)this, v13, a7, a8)) != 0 )
      {
        pData = (CUmRdpRpc *)v13;
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 65, v24, CurrentThreadActivityIdPrefix);
        }
        SetLastError(v22);
        TsLogError(&EVENT_NOTIFY_RESTORE_PRINTER_CONFIG_FAILED, 1, (unsigned __int16 **const)&pData, v25);
        v26 = 1;
      }
      else
      {
        v26 = a9;
      }
      if ( *((_DWORD *)*this + 542) )
      {
        LastError = 1115;
      }
      else
      {
        if ( OpenPrinterW(v13, &phPrinter, &pDefault) )
          goto LABEL_35;
        phPrinter = (HANDLE)-1LL;
        LastError = GetLastError();
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), v28, v29, v27, (__int64)v13, LastError);
        }
        if ( !LastError )
        {
LABEL_35:
          LODWORD(pData) = *(_DWORD *)*this;
          LastError = SetPrinterDataW(phPrinter, (LPWSTR)L"TSSessionID", 4u, (LPBYTE)&pData, 4u);
          if ( LastError
            && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v30 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
              67,
              (unsigned int)WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids,
              v30,
              (__int64)v13);
          }
        }
        if ( *((_DWORD *)*this + 542) )
        {
          LastError = 1115;
        }
        else
        {
          v31 = this[5];
          if ( (!(unsigned int)DRDEVLST_FindByServerDeviceName(v31, v13, &v37)
             || *(_DWORD *)(*(_QWORD *)v31 + 80LL * v37 + 8) != 4)
            && !LastError )
          {
            if ( (unsigned int)DRDEVLST_Add(v31, v11, 0xFFFFFFFF, 4u, v13, a5, "UNKNOWN") )
            {
              v32 = this[5];
              if ( (unsigned int)DRDEVLST_FindByClientDeviceID(v32, v11, &v37) )
              {
                if ( a10 )
                {
                  *(_DWORD *)(80LL * v37 + *(_QWORD *)v32 + 16) |= 1u;
                }
                else if ( v26 )
                {
                  *(_DWORD *)(*(_QWORD *)v32 + 80LL * v37 + 12) = 1;
                  CUmRdpPrn::TriggerConfigChangeTimer((CUmRdpPrn *)this);
                }
              }
            }
            else
            {
              LastError = 14;
            }
          }
        }
      }
    }
    goto LABEL_52;
  }
  CUmRdpPrn::SaveDefaultPrinter((CUmRdpPrn *)this, a2);
  v14 = *this;
  pData = 0;
  LastError = CUmRdpDr::CreateUmRdpRpc(v14, &pData);
  if ( !LastError )
  {
    v16 = CUmRdpRpc::SetDefaultPrinterW(pData, v13, a11);
    CUmRdpRpc::Release(pData);
    if ( v16 )
    {
      pData = (CUmRdpRpc *)v13;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 64, v19, v18);
      }
      TsLogError(&EVENT_NOTIFY_SETDEFAULTPRINTER_FAILED, 1, (unsigned __int16 **const)&pData, v17);
    }
    goto LABEL_11;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 63, v21, v20);
  }
LABEL_52:
  if ( phPrinter != (HANDLE)-1LL )
    ClosePrinter(phPrinter);
  return LastError;
}

```

## disassembly

```asm
0x180004680  mov     rax, rsp
0x180004683  mov     [rax+18h], r8
0x180004687  push    rbp
0x180004688  push    rbx
0x180004689  mov     rbp, rsp
0x18000468c  sub     rsp, 78h
0x180004690  mov     [rax+8], rsi
0x180004694  xor     ebx, ebx
0x180004696  mov     [rax+10h], rdi
0x18000469a  xorps   xmm0, xmm0
0x18000469d  mov     [rax-18h], r12
0x1800046a1  mov     r12d, edx
0x1800046a4  mov     [rax-20h], r14
0x1800046a8  mov     rsi, rcx
0x1800046ab  mov     r14, [rbp+pPrinterName]
0x1800046af  lea     rdi, WPP_GLOBAL_Control
0x1800046b6  mov     [rax-28h], r15
0x1800046ba  mov     [rbp+phPrinter], 0FFFFFFFFFFFFFFFFh
0x1800046c2  mov     qword ptr [rbp+pDefault.DesiredAccess], 0F000Ch
0x1800046ca  mov     [rbp+arg_18], ebx
0x1800046cd  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x1800046d2  test    r9d, r9d
0x1800046d5  jz      loc_18000478C
0x1800046db  mov     rax, [rcx]
0x1800046de  cmp     [rax+7B8h], ebx
0x1800046e4  jnz     short loc_1800046F2
0x1800046e6  cmp     [rcx+350h], ebx
0x1800046ec  jnz     loc_18000478C
0x1800046f2  call    ?SaveDefaultPrinter@CUmRdpPrn@@AEAAHPEBG@Z; CUmRdpPrn::SaveDefaultPrinter(ushort const *)
0x1800046f7  mov     rcx, [rsi]; this
0x1800046fa  lea     rdx, [rbp+pData]; struct CUmRdpRpc **
0x1800046fe  mov     [rbp+pData], rbx
0x180004702  call    ?CreateUmRdpRpc@CUmRdpDr@@QEAAJAEAPEAVCUmRdpRpc@@@Z; CUmRdpDr::CreateUmRdpRpc(CUmRdpRpc * &)
0x180004707  mov     ebx, eax
0x180004709  test    eax, eax
0x18000470b  jnz     loc_1800047AB
0x180004711  mov     r8, [rbp+arg_50]; void *
0x180004715  mov     rdx, r14; unsigned __int16 *
0x180004718  mov     rcx, [rbp+pData]; this
0x18000471c  call    ?SetDefaultPrinterW@CUmRdpRpc@@QEAAIPEAGPEAX@Z; CUmRdpRpc::SetDefaultPrinterW(ushort *,void *)
0x180004721  mov     rcx, [rbp+pData]; this
0x180004725  mov     r15d, eax
0x180004728  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x18000472d  test    r15d, r15d
0x180004730  jz      short loc_1800047A2
0x180004732  mov     [rbp+pData], r14
0x180004736  mov     rcx, cs:WPP_GLOBAL_Control
0x18000473d  lea     rdi, WPP_GLOBAL_Control
0x180004744  cmp     rcx, rdi
0x180004747  jz      short loc_180004777
0x180004749  test    byte ptr [rcx+1Ch], 1
0x18000474d  jz      short loc_180004777
0x18000474f  cmp     byte ptr [rcx+19h], 2
0x180004753  jb      short loc_180004777
0x180004755  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000475a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004761  mov     edx, 40h ; '@'
0x180004766  mov     r9d, eax
0x180004769  mov     [rsp+78h+cbData], r15d
0x18000476e  mov     rcx, [rcx+10h]
0x180004772  call    WPP_SF_Dl
0x180004777  lea     r8, [rbp+pData]; unsigned __int16 **
0x18000477b  mov     edx, 1; int
0x180004780  lea     rcx, EVENT_NOTIFY_SETDEFAULTPRINTER_FAILED; struct _EVENT_DESCRIPTOR *
0x180004787  call    ?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z; TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)
0x18000478c  mov     rax, [rsi]
0x18000478f  cmp     dword ptr [rax+878h], 0
0x180004796  jz      short loc_1800047F5
0x180004798  mov     ebx, 45Bh
0x18000479d  jmp     loc_180004A50
0x1800047a2  lea     rdi, WPP_GLOBAL_Control
0x1800047a9  jmp     short loc_18000478C
0x1800047ab  mov     rax, cs:WPP_GLOBAL_Control
0x1800047b2  cmp     rax, rdi
0x1800047b5  jz      loc_180004A50
0x1800047bb  test    byte ptr [rax+1Ch], 1
0x1800047bf  jz      loc_180004A50
0x1800047c5  cmp     byte ptr [rax+19h], 2
0x1800047c9  jb      loc_180004A50
0x1800047cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800047d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047db  mov     edx, 3Fh ; '?'
0x1800047e0  mov     r9d, eax
0x1800047e3  mov     [rsp+78h+cbData], ebx
0x1800047e7  mov     rcx, [rcx+10h]
0x1800047eb  call    WPP_SF_Dl
0x1800047f0  jmp     loc_180004A50
0x1800047f5  mov     r9d, [rbp+arg_38]; unsigned int
0x1800047f9  test    r9d, r9d
0x1800047fc  jz      short loc_18000487D
0x1800047fe  cmp     [rbp+arg_48], 0
0x180004802  jnz     short loc_18000487D
0x180004804  mov     r8, [rbp+arg_30]; void *
0x180004808  mov     rdx, r14; unsigned __int16 *
0x18000480b  mov     rcx, rsi; this
0x18000480e  call    ?SetPrinterConfigInfo@CUmRdpPrn@@AEAAKPEBGPEAXK@Z; CUmRdpPrn::SetPrinterConfigInfo(ushort const *,void *,ulong)
0x180004813  mov     ebx, eax
0x180004815  test    eax, eax
0x180004817  jz      short loc_18000487D
0x180004819  mov     [rbp+pData], r14
0x18000481d  mov     rax, cs:WPP_GLOBAL_Control
0x180004824  cmp     rax, rdi
0x180004827  jz      short loc_180004856
0x180004829  test    byte ptr [rax+1Ch], 1
0x18000482d  jz      short loc_180004856
0x18000482f  cmp     byte ptr [rax+19h], 2
0x180004833  jb      short loc_180004856
0x180004835  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000483a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004841  mov     edx, 41h ; 'A'
0x180004846  mov     r9d, eax
0x180004849  mov     [rsp+78h+cbData], ebx
0x18000484d  mov     rcx, [rcx+10h]
0x180004851  call    WPP_SF_Dl
0x180004856  mov     ecx, ebx; dwErrCode
0x180004858  call    cs:__imp_SetLastError
0x18000485e  lea     r8, [rbp+pData]; unsigned __int16 **
0x180004862  mov     edx, 1; int
0x180004867  lea     rcx, EVENT_NOTIFY_RESTORE_PRINTER_CONFIG_FAILED; struct _EVENT_DESCRIPTOR *
0x18000486e  call    ?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z; TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)
0x180004873  xor     ebx, ebx
0x180004875  mov     r15d, 1
0x18000487b  jmp     short loc_180004881
0x18000487d  mov     r15d, [rbp+arg_40]
0x180004881  mov     rax, [rsi]
0x180004884  cmp     dword ptr [rax+878h], 0
0x18000488b  jz      short loc_180004897
0x18000488d  mov     ebx, 45Bh
0x180004892  jmp     loc_180004A50
0x180004897  test    ebx, ebx
0x180004899  jnz     loc_180004973
0x18000489f  lea     r8, [rbp+pDefault]; pDefault
0x1800048a3  mov     rcx, r14; pPrinterName
0x1800048a6  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800048aa  call    cs:__imp_OpenPrinterW
0x1800048b0  test    eax, eax
0x1800048b2  jnz     short loc_180004901
0x1800048b4  mov     [rbp+phPrinter], 0FFFFFFFFFFFFFFFFh
0x1800048bc  call    cs:__imp_GetLastError
0x1800048c2  mov     ebx, eax
0x1800048c4  mov     rax, cs:WPP_GLOBAL_Control
0x1800048cb  cmp     rax, rdi
0x1800048ce  jz      short loc_1800048FD
0x1800048d0  test    byte ptr [rax+1Ch], 1
0x1800048d4  jz      short loc_1800048FD
0x1800048d6  cmp     byte ptr [rax+19h], 2
0x1800048da  jb      short loc_1800048FD
0x1800048dc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800048e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048e8  mov     r9d, eax
0x1800048eb  mov     dword ptr [rsp+78h+var_50], ebx
0x1800048ef  mov     qword ptr [rsp+78h+cbData], r14
0x1800048f4  mov     rcx, [rcx+10h]
0x1800048f8  call    WPP_SF_DSl
0x1800048fd  test    ebx, ebx
0x1800048ff  jnz     short loc_180004973
0x180004901  mov     rax, [rsi]
0x180004904  lea     r9, [rbp+pData]; pData
0x180004908  mov     r8d, 4; Type
0x18000490e  mov     [rsp+78h+cbData], 4; cbData
0x180004916  lea     rdx, pValueName; "TSSessionID"
0x18000491d  mov     ecx, [rax]
0x18000491f  mov     dword ptr [rbp+pData], ecx
0x180004922  mov     rcx, [rbp+phPrinter]; hPrinter
0x180004926  call    cs:__imp_SetPrinterDataW
0x18000492c  mov     ebx, eax
0x18000492e  test    eax, eax
0x180004930  jz      short loc_180004973
0x180004932  mov     rax, cs:WPP_GLOBAL_Control
0x180004939  cmp     rax, rdi
0x18000493c  jz      short loc_180004973
0x18000493e  test    byte ptr [rax+1Ch], 1
0x180004942  jz      short loc_180004973
0x180004944  cmp     byte ptr [rax+19h], 2
0x180004948  jb      short loc_180004973
0x18000494a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000494f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004956  lea     r8, WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids
0x18000495d  mov     edx, 43h ; 'C'
0x180004962  mov     qword ptr [rsp+78h+cbData], r14
0x180004967  mov     r9d, eax
0x18000496a  mov     rcx, [rcx+10h]
0x18000496e  call    WPP_SF_DS
0x180004973  mov     rax, [rsi]
0x180004976  cmp     dword ptr [rax+878h], 0
0x18000497d  jz      short loc_180004989
0x18000497f  mov     ebx, 45Bh
0x180004984  jmp     loc_180004A50
0x180004989  mov     rdi, [rsi+28h]
0x18000498d  lea     r8, [rbp+arg_18]; unsigned int *
0x180004991  mov     rcx, rdi; struct tagDRDEVLST *
0x180004994  mov     rdx, r14; unsigned __int16 *
0x180004997  call    ?DRDEVLST_FindByServerDeviceName@@YAHPEAUtagDRDEVLST@@PEBGPEAK@Z; DRDEVLST_FindByServerDeviceName(tagDRDEVLST *,ushort const *,ulong *)
0x18000499c  test    eax, eax
0x18000499e  jz      short loc_1800049B8
0x1800049a0  mov     eax, [rbp+arg_18]
0x1800049a3  lea     rcx, [rax+rax*4]
0x1800049a7  mov     rax, [rdi]
0x1800049aa  add     rcx, rcx
0x1800049ad  cmp     dword ptr [rax+rcx*8+8], 4
0x1800049b2  jz      loc_180004A50
0x1800049b8  test    ebx, ebx
0x1800049ba  jnz     loc_180004A50
0x1800049c0  lea     rax, aUnknown; "UNKNOWN"
0x1800049c7  mov     r9d, 4; unsigned int
0x1800049cd  mov     [rsp+78h+var_48], rax; char *
0x1800049d2  mov     r8d, 0FFFFFFFFh; unsigned int
0x1800049d8  mov     rax, [rbp+arg_20]
0x1800049dc  mov     edx, r12d; unsigned int
0x1800049df  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x1800049e4  mov     rcx, rdi; struct tagDRDEVLST *
0x1800049e7  mov     qword ptr [rsp+78h+cbData], r14; unsigned __int16 *
0x1800049ec  call    ?DRDEVLST_Add@@YAHPEAUtagDRDEVLST@@KKKPEBG1PEBD@Z; DRDEVLST_Add(tagDRDEVLST *,ulong,ulong,ulong,ushort const *,ushort const *,char const *)
0x1800049f1  test    eax, eax
0x1800049f3  jnz     short loc_1800049FC
0x1800049f5  mov     ebx, 0Eh
0x1800049fa  jmp     short loc_180004A50
0x1800049fc  mov     rdi, [rsi+28h]
0x180004a00  lea     r8, [rbp+arg_18]; unsigned int *
0x180004a04  mov     rcx, rdi; struct tagDRDEVLST *
0x180004a07  mov     edx, r12d; unsigned int
0x180004a0a  call    ?DRDEVLST_FindByClientDeviceID@@YAHPEAUtagDRDEVLST@@KPEAK@Z; DRDEVLST_FindByClientDeviceID(tagDRDEVLST *,ulong,ulong *)
0x180004a0f  test    eax, eax
0x180004a11  jz      short loc_180004A50
0x180004a13  cmp     [rbp+arg_48], 0
0x180004a17  jz      short loc_180004A2E
0x180004a19  mov     eax, [rbp+arg_18]
0x180004a1c  lea     rcx, [rax+rax*4]
0x180004a20  mov     rax, [rdi]
0x180004a23  shl     rcx, 4
0x180004a27  or      dword ptr [rcx+rax+10h], 1
0x180004a2c  jmp     short loc_180004A50
0x180004a2e  test    r15d, r15d
0x180004a31  jz      short loc_180004A50
0x180004a33  mov     eax, [rbp+arg_18]
0x180004a36  lea     rcx, [rax+rax*4]
0x180004a3a  mov     rax, [rdi]
0x180004a3d  add     rcx, rcx
0x180004a40  mov     dword ptr [rax+rcx*8+0Ch], 1
0x180004a48  mov     rcx, rsi; this
0x180004a4b  call    ?TriggerConfigChangeTimer@CUmRdpPrn@@AEAAXXZ; CUmRdpPrn::TriggerConfigChangeTimer(void)
0x180004a50  mov     rcx, [rbp+phPrinter]; hPrinter
0x180004a54  mov     r15, [rsp+78h+var_18]
0x180004a59  mov     r14, [rsp+78h+var_10]
0x180004a5e  mov     r12, [rsp+78h+var_8]
0x180004a63  mov     rdi, [rsp+78h+arg_8]
0x180004a6b  mov     rsi, [rsp+78h+arg_0]
0x180004a73  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004a77  jz      short loc_180004A7F
0x180004a79  call    cs:__imp_ClosePrinter
0x180004a7f  mov     eax, ebx
0x180004a81  add     rsp, 78h
0x180004a85  pop     rbx
0x180004a86  pop     rbp
0x180004a87  retn
```
