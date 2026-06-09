# wiasUpdateValidFormat

- ea: `0x180030980`
- end: `0x180030eed`
- name: `wiasUpdateValidFormat`
- size: `1389`
- prototype: `__int64 __fastcall(struct IWiaItem *this)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update`

## callees

- `0x180004380`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800189cc`
- `0x1800284dc`
- `0x18002de18`
- `0x18002def8`
- `0x180030980`
- `0x18003de6c`
- `0x1800405b0`
- `0x180040750`
- `0x180042ef0`
- `0x180044a20`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180030da0`
- `KERNEL32!LocalFree` at `0x180030da0`
- `KERNEL32!LocalAlloc` at `0x180030bc9`
- `KERNEL32!LocalAlloc` at `0x180030bc9`

## string_xrefs

- `0x1800309b7`: `wiasUpdateValidFormat`
- `0x180030b11`: `wiasUpdateValidFormat`
- `0x180030b9c`: `wiasUpdateValidFormat`
- `0x180030be6`: `wiasUpdateValidFormat`
- `0x180030c11`: `wiasUpdateValidFormat`
- `0x180030d64`: `wiasUpdateValidFormat`
- `0x180030d91`: `wiasUpdateValidFormat`
- `0x180030db9`: `wiasUpdateValidFormat`
- `0x180030de6`: `wiasUpdateValidFormat`
- `0x180030e4b`: `wiasUpdateValidFormat`
- `0x180030e73`: `wiasUpdateValidFormat`
- `0x180030e3c`: `wiasWritePropGuid failed. (0x%X)`
- `0x180030e62`: `wiasWritePropGuid failed. (0x%X)`

## pseudocode

```c
__int64 __fastcall wiasUpdateValidFormat(struct IWiaItem *this, __int64 a2, __int64 a3)
{
  struct tagWiaTraceData_Type *v5; // rax
  char *v6; // rdx
  unsigned int v7; // r8d
  GUID v8; // xmm6
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  int ChangedValueLong; // edi
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  int v20; // r12d
  char *v21; // rbx
  void *v22; // rdx
  char *v23; // rbx
  void *v24; // rdx
  GUID *v25; // r15
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  int v31; // r10d
  int v32; // r8d
  int v33; // r9d
  int v34; // r11d
  int v35; // ebx
  __int64 v36; // rdx
  __int64 v37; // rax
  bool v38; // zf
  const GUID *v39; // rcx
  __int64 v40; // rax
  GUID v41; // xmm0
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  char *v46; // rbx
  void *v47; // rdx
  void **v48; // rax
  void *v49; // rdx
  __int64 v50; // rcx
  char *v51; // rbx
  void *v52; // rdx
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  char *v56; // rbx
  void *v57; // rdx
  char *v58; // rbx
  void *v59; // rdx
  unsigned int lpMem; // [rsp+28h] [rbp-E0h]
  __int64 v62; // [rsp+48h] [rbp-C0h] BYREF
  int uBytes; // [rsp+50h] [rbp-B8h]
  int uBytes_4; // [rsp+54h] [rbp-B4h]
  GUID uBytes_8; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v66[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v67; // [rsp+78h] [rbp-90h]
  __int64 v68; // [rsp+88h] [rbp-80h]
  __int64 v69[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v70; // [rsp+A0h] [rbp-68h]
  _BYTE v71[96]; // [rsp+B8h] [rbp-50h] BYREF
  int v72; // [rsp+158h] [rbp+50h] BYREF
  int v73; // [rsp+160h] [rbp+58h] BYREF

  v5 = WiaTrace_Trace(&Class);
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v71, v6, v7, "wiasUpdateValidFormat", lpMem, v5);
  v68 = 0;
  v72 = 0;
  v62 = 0;
  v8 = 0;
  v73 = 0;
  *(_OWORD *)v69 = 0;
  v70 = 0;
  *(_OWORD *)v66 = 0;
  v67 = 0;
  if ( !a3 )
  {
    v9 = (char *)WiaTrace_TraceLog("Invalid pIMiniDrv pointer");
    WriteDbgTraceErrorWI("wiasUpdateValidFormat", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    v11 = (void **)WiaTrace_Trace("Invalid pIMiniDrv pointer");
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"wiasUpdateValidFormat", 1, v11);
    ChangedValueLong = -2147467261;
    goto LABEL_47;
  }
  ChangedValueLong = ValidateWiaItem(this);
  if ( ChangedValueLong < 0 )
  {
    v15 = (char *)WiaTrace_TraceLog("Invalid pWiasContext");
    WriteDbgTraceErrorWI("wiasUpdateValidFormat", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v17 = (void **)WiaTrace_Trace("Invalid pWiasContext");
LABEL_46:
    WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"wiasUpdateValidFormat", 1, v17);
    goto LABEL_47;
  }
  uBytes_4 = CWiaItem::IsLegacyDriver((CWiaItem *)this);
  uBytes = (int)this[28].lpVtbl;
  ChangedValueLong = wiasGetChangedValueLong(this, (__int64)v69);
  if ( ChangedValueLong < 0 )
  {
    v58 = (char *)WiaTrace_TraceLog("wiasGetChangedValue (tymed) failed (0x%X)");
    WriteDbgTraceErrorWI("wiasUpdateValidFormat", v58);
    WiaTrcLib::Free((WiaTrcLib *)v58, v59);
    v17 = (void **)WiaTrace_Trace("wiasGetChangedValue (tymed) failed (0x%X)", ChangedValueLong);
    goto LABEL_46;
  }
  v20 = 0;
  if ( LODWORD(v69[0]) )
  {
    ChangedValueLong = wiasGetChangedValueGuid(this, (__int64)v66);
    if ( ChangedValueLong < 0 )
    {
      v21 = (char *)WiaTrace_TraceLog("wiasGetChangedValue (format) failed (0x%X)");
      WriteDbgTraceErrorWI("wiasUpdateValidFormat", v21);
      WiaTrcLib::Free((WiaTrcLib *)v21, v22);
      v17 = (void **)WiaTrace_Trace("wiasGetChangedValue (format) failed (0x%X)", (unsigned int)ChangedValueLong);
      goto LABEL_46;
    }
    ChangedValueLong = (*(__int64 (__fastcall **)(__int64, struct IWiaItem *, _QWORD, int *, __int64 *, int *))(*(_QWORD *)a3 + 136LL))(
                         a3,
                         this,
                         0,
                         &v72,
                         &v62,
                         &v73);
    if ( ChangedValueLong < 0 )
    {
      v51 = (char *)WiaTrace_TraceLog("drvGetWiaFormatInfo failed. (0x%X)");
      WriteDbgTraceErrorWI("wiasUpdateValidFormat", v51);
      WiaTrcLib::Free((WiaTrcLib *)v51, v52);
      v53 = (void **)WiaTrace_Trace("drvGetWiaFormatInfo failed. (0x%X)", ChangedValueLong);
      WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"wiasUpdateValidFormat", 1, v53);
    }
    else
    {
      *(_QWORD *)&uBytes_8.Data1 = 0;
      ChangedValueLong = ULongLongMult(0x10u, v72, (unsigned __int64 *)&uBytes_8.Data1);
      if ( ChangedValueLong < 0 )
      {
        v23 = (char *)WiaTrace_TraceLog("Integer overflow (%#x)");
        WriteDbgTraceErrorWI("wiasUpdateValidFormat", v23);
        WiaTrcLib::Free((WiaTrcLib *)v23, v24);
        v17 = (void **)WiaTrace_Trace("Integer overflow (%#x)", (unsigned int)ChangedValueLong);
        goto LABEL_46;
      }
      v25 = (GUID *)LocalAlloc(0x40u, *(SIZE_T *)&uBytes_8.Data1);
      if ( !v25 )
      {
        v26 = (char *)WiaTrace_TraceLog("Out of memory");
        WriteDbgTraceErrorWI("wiasUpdateValidFormat", v26);
        WiaTrcLib::Free((WiaTrcLib *)v26, v27);
        v28 = (void **)WiaTrace_Trace("Out of memory");
        WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"wiasUpdateValidFormat", 1, v28);
        ChangedValueLong = -2147024882;
        goto LABEL_47;
      }
      v31 = 0;
      v32 = 0;
      if ( v72 > 0 )
      {
        v33 = DWORD2(v70);
        v34 = uBytes;
        v35 = uBytes_4;
        do
        {
          if ( v33 == 128 && !v35 && v34 == 1 )
          {
            v36 = v62 + 20LL * v32;
            if ( *(_DWORD *)(v36 + 16) == 2 )
            {
              v37 = *(_QWORD *)&WiaImgFmt_BMP.Data1 - *(_QWORD *)v36;
              if ( *(_QWORD *)&WiaImgFmt_BMP.Data1 == *(_QWORD *)v36 )
                v37 = *(_QWORD *)WiaImgFmt_BMP.Data4 - *(_QWORD *)(v36 + 8);
              v38 = v37 == 0;
              v39 = &WiaImgFmt_MEMORYBMP;
              v40 = v31;
              if ( !v38 )
                v39 = (const GUID *)(v62 + 20LL * v32);
              ++v31;
              v41 = *v39;
              v42 = v31;
              v25[v40] = v41;
              v43 = *((_QWORD *)&v67 + 1) - *(_QWORD *)&v25[v42].Data1;
              if ( *((_QWORD *)&v67 + 1) == *(_QWORD *)&v25[v42].Data1 )
                v43 = v68 - *(_QWORD *)v25[v42].Data4;
              if ( !v43 )
                v20 = 1;
            }
          }
          else if ( *(_DWORD *)(v62 + 20LL * v32 + 16) == v33 )
          {
            v44 = v31++;
            v25[v44] = *(GUID *)(v62 + 20LL * v32);
            v45 = *((_QWORD *)&v67 + 1) - *(_QWORD *)(v62 + 20LL * v32);
            if ( *((_QWORD *)&v67 + 1) == *(_QWORD *)(v62 + 20LL * v32) )
              v45 = v68 - *(_QWORD *)(v62 + 20LL * v32 + 8);
            if ( !v45 )
              v20 = 1;
          }
          ++v32;
        }
        while ( v32 < v72 );
        if ( v72 > 0 )
        {
          v8 = *v25;
          uBytes_8 = *v25;
          ChangedValueLong = wiasSetValidListGuid((CWiaItem *)this, (__int64)v25);
          if ( ChangedValueLong < 0 )
          {
            v46 = (char *)WiaTrace_TraceLog("wiasSetValidListGuid failed. (0x%X)");
            WriteDbgTraceErrorWI("wiasUpdateValidFormat", v46);
            WiaTrcLib::Free((WiaTrcLib *)v46, v47);
            v48 = (void **)WiaTrace_Trace("wiasSetValidListGuid failed. (0x%X)", ChangedValueLong);
            WiaTrace_ProcessTrace_Ex(v50, v49, (void *)"wiasUpdateValidFormat", 1, v48);
          }
          LocalFree(v25);
        }
      }
    }
  }
  if ( ChangedValueLong >= 0 )
  {
    if ( LODWORD(v69[0]) )
    {
      if ( !LODWORD(v66[0]) && !v20 )
      {
        uBytes_8 = v8;
        ChangedValueLong = wiasWritePropGuid(this, 0x100Au, &uBytes_8);
        if ( ChangedValueLong < 0 )
        {
          v56 = (char *)WiaTrace_TraceLog("wiasWritePropGuid failed. (0x%X)");
          WriteDbgTraceErrorWI("wiasUpdateValidFormat", v56);
          WiaTrcLib::Free((WiaTrcLib *)v56, v57);
          v17 = (void **)WiaTrace_Trace("wiasWritePropGuid failed. (0x%X)", (unsigned int)ChangedValueLong);
          goto LABEL_46;
        }
      }
    }
  }
LABEL_47:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v71);
  return (unsigned int)ChangedValueLong;
}

```

## disassembly

```asm
0x180030980  mov     rax, rsp
0x180030983  mov     [rax+8], rbx
0x180030987  mov     [rax+10h], rsi
0x18003098b  push    rbp
0x18003098c  push    rdi
0x18003098d  push    r12
0x18003098f  push    r14
0x180030991  push    r15
0x180030993  lea     rbp, [rax-38h]
0x180030997  sub     rsp, 110h
0x18003099e  mov     r14, rcx
0x1800309a1  movaps  xmmword ptr [rax-38h], xmm6
0x1800309a5  lea     rcx, Class; unsigned __int16 *
0x1800309ac  mov     rbx, r8
0x1800309af  mov     r15, rdx
0x1800309b2  call    ?WiaTrace_Trace@@YAPEAUtagWiaTraceData_Type@@PEBGZZ; WiaTrace_Trace(ushort const *,...)
0x1800309b7  lea     r12, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x1800309be  mov     [rsp+130h+var_108], rax; struct tagWiaTraceData_Type *
0x1800309c3  mov     r9, r12; char *
0x1800309c6  lea     rcx, [rbp+30h+var_80]; this
0x1800309ca  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800309cf  xor     esi, esi
0x1800309d1  xor     eax, eax
0x1800309d3  mov     [rbp+30h+var_B0], rax
0x1800309d7  xorps   xmm0, xmm0
0x1800309da  mov     [rbp+30h+arg_10], esi
0x1800309dd  xorps   xmm1, xmm1
0x1800309e0  mov     [rsp+130h+var_F0], rsi
0x1800309e5  xorps   xmm6, xmm6
0x1800309e8  mov     [rbp+30h+arg_18], esi
0x1800309eb  movups  xmmword ptr [rbp+30h+var_A8], xmm0
0x1800309ef  movups  [rbp+30h+var_98], xmm0
0x1800309f3  movups  xmmword ptr [rsp+130h+var_D8+8], xmm1
0x1800309f8  movups  [rsp+130h+var_C8+8], xmm1
0x1800309fd  test    rbx, rbx
0x180030a00  jnz     short loc_180030A4B
0x180030a02  lea     rcx, aInvalidPiminid; "Invalid pIMiniDrv pointer"
0x180030a09  call    WiaTrace_TraceLog
0x180030a0e  mov     rdx, rax; char *
0x180030a11  mov     rcx, r12; char *
0x180030a14  mov     rbx, rax
0x180030a17  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030a1c  mov     rcx, rbx; this
0x180030a1f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180030a24  lea     rcx, aInvalidPiminid; "Invalid pIMiniDrv pointer"
0x180030a2b  call    WiaTrace_Trace
0x180030a30  lea     r9d, [rsi+1]; int
0x180030a34  mov     [rsp+130h+lpMem], rax; lpMem
0x180030a39  mov     r8, r12; int
0x180030a3c  call    WiaTrace_ProcessTrace_Ex
0x180030a41  mov     edi, 80004003h
0x180030a46  jmp     loc_180030EC1
0x180030a4b  mov     rcx, r14; struct IWiaItem *
0x180030a4e  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180030a53  mov     edi, eax
0x180030a55  test    eax, eax
0x180030a57  jns     short loc_180030A8C
0x180030a59  lea     rcx, aInvalidPwiasco; "Invalid pWiasContext"
0x180030a60  call    WiaTrace_TraceLog
0x180030a65  mov     rdx, rax; char *
0x180030a68  mov     rcx, r12; char *
0x180030a6b  mov     rbx, rax
0x180030a6e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030a73  mov     rcx, rbx; this
0x180030a76  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180030a7b  lea     rcx, aInvalidPwiasco; "Invalid pWiasContext"
0x180030a82  call    WiaTrace_Trace
0x180030a87  jmp     loc_180030EAE
0x180030a8c  mov     rcx, r14; this
0x180030a8f  call    ?IsLegacyDriver@CWiaItem@@QEAAHXZ; CWiaItem::IsLegacyDriver(void)
0x180030a94  lea     rcx, [rbp+30h+var_A8]
0x180030a98  mov     dword ptr [rsp+130h+uBytes+4], eax
0x180030a9c  mov     eax, [r14+0E0h]
0x180030aa3  mov     r9d, 100Ch
0x180030aa9  mov     [rsp+130h+lpMem], rcx; __int64
0x180030aae  xor     r8d, r8d
0x180030ab1  mov     rcx, r14; this
0x180030ab4  mov     dword ptr [rsp+130h+uBytes], eax
0x180030ab8  mov     rdx, r15
0x180030abb  call    wiasGetChangedValueLong
0x180030ac0  mov     edi, eax
0x180030ac2  test    eax, eax
0x180030ac4  js      loc_180030E7C
0x180030aca  mov     r12d, esi
0x180030acd  mov     esi, 1
0x180030ad2  cmp     dword ptr [rbp+30h+var_A8], r12d
0x180030ad6  jz      loc_180030DF2
0x180030adc  lea     rax, [rsp+130h+var_D8+8]
0x180030ae1  mov     r9d, 100Ah
0x180030ae7  mov     r8d, esi
0x180030aea  mov     [rsp+130h+lpMem], rax; __int64
0x180030aef  mov     rdx, r15
0x180030af2  mov     rcx, r14; this
0x180030af5  call    wiasGetChangedValueGuid
0x180030afa  mov     edi, eax
0x180030afc  test    eax, eax
0x180030afe  jns     short loc_180030B34
0x180030b00  mov     edx, eax
0x180030b02  lea     rcx, aWiasgetchanged_8; "wiasGetChangedValue (format) failed (0x"...
0x180030b09  call    WiaTrace_TraceLog
0x180030b0e  mov     rdx, rax; char *
0x180030b11  lea     rcx, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030b18  mov     rbx, rax
0x180030b1b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030b20  mov     rcx, rbx; this
0x180030b23  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180030b28  lea     rcx, aWiasgetchanged_8; "wiasGetChangedValue (format) failed (0x"...
0x180030b2f  jmp     loc_180030E69
0x180030b34  mov     rax, [rbx]
0x180030b37  lea     rcx, [rbp+30h+arg_18]
0x180030b3b  mov     [rsp+130h+var_108], rcx
0x180030b40  lea     r9, [rbp+30h+arg_10]
0x180030b44  lea     rcx, [rsp+130h+var_F0]
0x180030b49  xor     r8d, r8d
0x180030b4c  mov     [rsp+130h+lpMem], rcx
0x180030b51  mov     rdx, r14
0x180030b54  mov     rax, [rax+88h]
0x180030b5b  mov     rcx, rbx
0x180030b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b63  mov     edi, eax
0x180030b65  test    eax, eax
0x180030b67  js      loc_180030DA8
0x180030b6d  movsxd  rdx, [rbp+30h+arg_10]; unsigned __int64
0x180030b71  lea     r8, [rsp+130h+uBytes+8]; unsigned __int64 *
0x180030b76  mov     ecx, 10h; unsigned __int64
0x180030b7b  mov     [rsp+130h+uBytes+8], r12
0x180030b80  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180030b85  mov     edi, eax
0x180030b87  test    eax, eax
0x180030b89  jns     short loc_180030BBF
0x180030b8b  mov     edx, eax
0x180030b8d  lea     rcx, aIntegerOverflo; "Integer overflow (%#x)"
0x180030b94  call    WiaTrace_TraceLog
0x180030b99  mov     rdx, rax; char *
0x180030b9c  lea     rcx, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030ba3  mov     rbx, rax
0x180030ba6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030bab  mov     rcx, rbx; this
0x180030bae  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180030bb3  lea     rcx, aIntegerOverflo; "Integer overflow (%#x)"
0x180030bba  jmp     loc_180030E69
0x180030bbf  mov     rdx, [rsp+130h+uBytes+8]; uBytes
0x180030bc4  mov     ecx, 40h ; '@'; uFlags
0x180030bc9  call    cs:__imp_LocalAlloc
0x180030bcf  mov     r15, rax
0x180030bd2  test    rax, rax
0x180030bd5  jnz     short loc_180030C27
0x180030bd7  lea     rcx, aOutOfMemory_3; "Out of memory"
0x180030bde  call    WiaTrace_TraceLog
0x180030be3  mov     rdx, rax; char *
0x180030be6  lea     rcx, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030bed  mov     rbx, rax
0x180030bf0  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030bf5  mov     rcx, rbx; this
0x180030bf8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180030bfd  lea     rcx, aOutOfMemory_3; "Out of memory"
0x180030c04  call    WiaTrace_Trace
0x180030c09  mov     r9d, esi; int
0x180030c0c  mov     [rsp+130h+lpMem], rax; lpMem
0x180030c11  lea     r8, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030c18  call    WiaTrace_ProcessTrace_Ex
0x180030c1d  mov     edi, 8007000Eh
0x180030c22  jmp     loc_180030EC1
0x180030c27  xor     r10d, r10d
0x180030c2a  xor     r8d, r8d
0x180030c2d  cmp     [rbp+30h+arg_10], r8d
0x180030c31  jle     loc_180030DF2
0x180030c37  mov     r9d, dword ptr [rbp+30h+var_98+8]
0x180030c3b  mov     r11d, dword ptr [rsp+130h+uBytes]
0x180030c40  mov     ebx, dword ptr [rsp+130h+uBytes+4]
0x180030c44  cmp     r9d, 80h
0x180030c4b  jnz     short loc_180030CCC
0x180030c4d  test    ebx, ebx
0x180030c4f  jnz     short loc_180030CCC
0x180030c51  cmp     r11d, esi
0x180030c54  jnz     short loc_180030CCC
0x180030c56  movsxd  rax, r8d
0x180030c59  lea     rcx, [rax+rax*4]
0x180030c5d  mov     rax, [rsp+130h+var_F0]
0x180030c62  lea     rdx, [rax+rcx*4]
0x180030c66  cmp     dword ptr [rdx+10h], 2
0x180030c6a  jnz     loc_180030D12
0x180030c70  mov     rax, qword ptr cs:WiaImgFmt_BMP.Data1
0x180030c77  sub     rax, [rdx]
0x180030c7a  jnz     short loc_180030C87
0x180030c7c  mov     rax, qword ptr cs:WiaImgFmt_BMP.Data4
0x180030c83  sub     rax, [rdx+8]
0x180030c87  test    rax, rax
0x180030c8a  lea     rcx, WiaImgFmt_MEMORYBMP
0x180030c91  movsxd  rax, r10d
0x180030c94  cmovnz  rcx, rdx
0x180030c98  add     rax, rax
0x180030c9b  add     r10d, esi
0x180030c9e  movups  xmm0, xmmword ptr [rcx]
0x180030ca1  movsxd  rcx, r10d
0x180030ca4  shl     rcx, 4
0x180030ca8  movdqu  xmmword ptr [r15+rax*8], xmm0
0x180030cae  mov     rax, [rsp+130h+var_B8]
0x180030cb3  sub     rax, [rcx+r15]
0x180030cb7  jnz     short loc_180030CC2
0x180030cb9  mov     rax, [rbp+30h+var_B0]
0x180030cbd  sub     rax, [rcx+r15+8]
0x180030cc2  test    rax, rax
0x180030cc5  jnz     short loc_180030D12
0x180030cc7  mov     r12d, esi
0x180030cca  jmp     short loc_180030D12
0x180030ccc  mov     rdx, [rsp+130h+var_F0]
0x180030cd1  movsxd  rax, r8d
0x180030cd4  lea     rcx, [rax+rax*4]
0x180030cd8  cmp     [rdx+rcx*4+10h], r9d
0x180030cdd  jnz     short loc_180030D12
0x180030cdf  movups  xmm0, xmmword ptr [rdx+rcx*4]
0x180030ce3  movsxd  rax, r10d
0x180030ce6  add     r10d, esi
0x180030ce9  add     rax, rax
0x180030cec  movdqu  xmmword ptr [r15+rax*8], xmm0
0x180030cf2  mov     rdx, [rsp+130h+var_F0]
0x180030cf7  mov     rax, [rsp+130h+var_B8]
0x180030cfc  sub     rax, [rdx+rcx*4]
0x180030d00  jnz     short loc_180030D0B
0x180030d02  mov     rax, [rbp+30h+var_B0]
0x180030d06  sub     rax, [rdx+rcx*4+8]
0x180030d0b  test    rax, rax
0x180030d0e  cmovz   r12d, esi
0x180030d12  mov     eax, [rbp+30h+arg_10]
0x180030d15  add     r8d, esi
0x180030d18  cmp     r8d, eax
0x180030d1b  jl      loc_180030C44
0x180030d21  test    eax, eax
0x180030d23  jle     loc_180030DF2
0x180030d29  movups  xmm6, xmmword ptr [r15]
0x180030d2d  lea     r9, [rsp+130h+uBytes+8]
0x180030d32  mov     [rsp+130h+lpMem], r15; __int64
0x180030d37  mov     r8d, r10d
0x180030d3a  mov     edx, 100Ah
0x180030d3f  mov     rcx, r14; this
0x180030d42  movdqu  xmmword ptr [rsp+130h+uBytes+8], xmm6
0x180030d48  call    wiasSetValidListGuid
0x180030d4d  mov     edi, eax
0x180030d4f  test    eax, eax
0x180030d51  jns     short loc_180030D9D
0x180030d53  mov     edx, eax
0x180030d55  lea     rcx, aWiassetvalidli_14; "wiasSetValidListGuid failed. (0x%X)"
0x180030d5c  call    WiaTrace_TraceLog
0x180030d61  mov     rdx, rax; char *
0x180030d64  lea     rcx, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030d6b  mov     rbx, rax
0x180030d6e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030d73  mov     rcx, rbx; this
0x180030d76  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180030d7b  mov     edx, edi
0x180030d7d  lea     rcx, aWiassetvalidli_14; "wiasSetValidListGuid failed. (0x%X)"
0x180030d84  call    WiaTrace_Trace
0x180030d89  mov     r9d, esi; int
0x180030d8c  mov     [rsp+130h+lpMem], rax; lpMem
0x180030d91  lea     r8, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030d98  call    WiaTrace_ProcessTrace_Ex
0x180030d9d  mov     rcx, r15; hMem
0x180030da0  call    cs:__imp_LocalFree
0x180030da6  jmp     short loc_180030DF2
0x180030da8  mov     edx, edi
0x180030daa  lea     rcx, aDrvgetwiaforma; "drvGetWiaFormatInfo failed. (0x%X)"
0x180030db1  call    WiaTrace_TraceLog
0x180030db6  mov     rdx, rax; char *
0x180030db9  lea     rcx, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030dc0  mov     rbx, rax
0x180030dc3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030dc8  mov     rcx, rbx; this
0x180030dcb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180030dd0  mov     edx, edi
0x180030dd2  lea     rcx, aDrvgetwiaforma; "drvGetWiaFormatInfo failed. (0x%X)"
0x180030dd9  call    WiaTrace_Trace
0x180030dde  mov     r9d, esi; int
0x180030de1  mov     [rsp+130h+lpMem], rax; lpMem
0x180030de6  lea     r8, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030ded  call    WiaTrace_ProcessTrace_Ex
0x180030df2  test    edi, edi
0x180030df4  js      loc_180030EC1
0x180030dfa  cmp     dword ptr [rbp+30h+var_A8], 0
0x180030dfe  jz      loc_180030EC1
0x180030e04  cmp     dword ptr [rsp+130h+var_D8+8], 0
0x180030e09  jnz     loc_180030EC1
0x180030e0f  test    r12d, r12d
0x180030e12  jnz     loc_180030EC1
0x180030e18  lea     r8, [rsp+130h+uBytes+8]
0x180030e1d  movdqa  xmmword ptr [rsp+130h+uBytes+8], xmm6
0x180030e23  mov     edx, 100Ah; unsigned int
0x180030e28  mov     rcx, r14; this
0x180030e2b  call    wiasWritePropGuid
0x180030e30  mov     edi, eax
0x180030e32  test    eax, eax
0x180030e34  jns     loc_180030EC1
0x180030e3a  mov     edx, eax
0x180030e3c  lea     rcx, aWiaswritepropg_4; "wiasWritePropGuid failed. (0x%X)"
0x180030e43  call    WiaTrace_TraceLog
0x180030e48  mov     rdx, rax; char *
0x180030e4b  lea     rcx, aWiasupdatevali_0; "wiasUpdateValidFormat"
0x180030e52  mov     rbx, rax
0x180030e55  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180030e5a  mov     rcx, rbx; this
  ... truncated ...
```
