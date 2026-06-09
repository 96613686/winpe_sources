# CContentFolder::_BindToStream(CONTENTITEM const *,ulong,int,IStream * *)

- ea: `0x180005b90`
- end: `0x180006199`
- name: `?_BindToStream@CContentFolder@@AEAAJPEFBUCONTENTITEM@@KHPEAPEAUIStream@@@Z`
- size: `1545`
- prototype: `__int64 __usercall@<rax>(CContentFolder *__hidden this@<rcx>, const struct CONTENTITEM *@<rdx>, unsigned int@<r8d>, int@<r9d>, struct IStream **)`
- caller_count: `3`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006cd0`
- `0x180044370`
- `0x180064bbc`

## callees

- `0x180003ddc`
- `0x180004110`
- `0x180004190`
- `0x180005b90`
- `0x1800082e0`
- `0x18000d610`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x180039e80`
- `0x180041ab0`
- `0x180041e78`
- `0x180042274`
- `0x1800487bc`
- `0x18005c024`
- `0x18005f190`
- `0x18006323c`
- `0x1800643a8`
- `0x18006478c`
- `0x180064cd4`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006105`
- `ole32!CoTaskMemFree` at `0x180006167`
- `ole32!CoTaskMemFree` at `0x180006105`
- `ole32!CoTaskMemFree` at `0x180006167`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CContentFolder::_BindToStream(
        CContentFolder *this,
        const struct CONTENTITEM *a2,
        int a3,
        unsigned int a4,
        struct IStream **a5)
{
  const struct CONTENTITEM *v6; // r14
  int v8; // edi
  unsigned int v9; // r15d
  const struct std::nothrow_t *v10; // rdx
  unsigned __int16 v11; // si
  int v12; // eax
  struct IStream *v13; // rax
  CStgCreationStream *v14; // rax
  CPortableMediaReader *v15; // rbx
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  struct IStream *v20; // rax
  CStgDualStream *v21; // rsi
  int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  CPortableMediaReader *v25; // rax
  CPortableMediaReader *v26; // rax
  CPortableMediaReader *v27; // rbx
  CContentFolder *v28; // rcx
  const struct std::nothrow_t *v29; // rdx
  CSeekableStreamOverLimitedSeekStream *v30; // rax
  CSeekableStreamOverLimitedSeekStream *v31; // rcx
  struct IStream *v32; // rcx
  struct IStream *v33; // rax
  CPortableMediaReader *v35; // [rsp+40h] [rbp-C0h] BYREF
  struct IStream *v36; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  CPortableMediaReader *v38; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v39[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v40[264]; // [rsp+270h] [rbp+170h] BYREF

  v6 = a2;
  if ( a5 )
  {
    if ( !a2 )
    {
      v8 = -2147024809;
      goto LABEL_78;
    }
    *a5 = 0;
    v9 = a3 & 0xFFFEFF8F;
    if ( (a3 & 0xFFFEFF8C) != 0 )
    {
      v8 = -2147287039;
      goto LABEL_78;
    }
    CContentFolder::_Name(this, a2, v39, a4);
    StringCchCopyW(
      v40,
      0x104u,
      (const unsigned __int16 *)v6 + *(unsigned int *)((char *)v6 + 62) + *(unsigned int *)((char *)v6 + 66) + 37);
    v11 = v40[0];
    if ( !v40[0] )
    {
      if ( a4 )
        goto LABEL_14;
      v12 = CContentFolder::_RemoveVirtualFile(this, v39);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            266,
            (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)v39,
            v12);
        goto LABEL_78;
      }
      if ( v12 != 1 )
      {
LABEL_14:
        v35 = 0;
        v13 = (struct IStream *)operator new(0x278u, v10);
        v36 = v13;
        if ( v13 )
          v14 = CStgCreationStream::CStgCreationStream((CStgCreationStream *)v13);
        else
          v14 = 0;
        ATL::CComPtrBase<CStgCreationStream>::Attach(&v35, v14);
        v15 = v35;
        if ( !v35 )
        {
          v8 = -2147024882;
LABEL_19:
          ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(&v35);
          goto LABEL_78;
        }
        v16 = CStgCreationStream::_Initialize(v35, this, v39, v9, v6);
        v8 = v16;
        if ( v16 < 0 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_19;
          v19 = 271;
          goto LABEL_24;
        }
        if ( (v9 & 3) != 0 )
        {
          v16 = (**((__int64 (__fastcall ***)(__int64, GUID *, struct IStream **))v15 + 2))(
                  (__int64)v15 + 16,
                  &GUID_0000000c_0000_0000_c000_000000000046,
                  a5);
          v8 = v16;
          if ( v16 < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_19;
            v19 = 272;
LABEL_24:
            WPP_SF_d(v18[2], v19, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v16);
            goto LABEL_19;
          }
LABEL_47:
          ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(&v35);
          return (unsigned int)v8;
        }
        v20 = (struct IStream *)operator new(0x48u, v17);
        v36 = v20;
        if ( v20 )
          v21 = CStgDualStream::CStgDualStream((CStgDualStream *)v20);
        else
          v21 = 0;
        v36 = (struct IStream *)v21;
        if ( !v21 )
        {
          v8 = -2147024882;
          ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(&v36);
          goto LABEL_19;
        }
        v22 = CStgDualStream::_Initialize(
                v21,
                this,
                v9,
                v6,
                (struct IStream *)(((unsigned __int64)v15 + 16) & -(__int64)(v15 != 0)));
        v8 = v22;
        if ( v22 >= 0 )
        {
          v22 = (**((__int64 (__fastcall ***)(__int64, GUID *, struct IStream **))v21 + 2))(
                  (__int64)v21 + 16,
                  &GUID_0000000c_0000_0000_c000_000000000046,
                  a5);
          v8 = v22;
          if ( v22 >= 0 )
          {
            ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(&v36);
            goto LABEL_47;
          }
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          {
LABEL_41:
            ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(&v36);
            goto LABEL_19;
          }
          v24 = 274;
        }
        else
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_41;
          v24 = 273;
        }
        WPP_SF_d(v23[2], v24, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v22);
        goto LABEL_41;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, WPP_953c7f1870f230da5c3777fec273291e_Traceguids);
    pv = 0;
    v35 = 0;
    v25 = (CPortableMediaReader *)operator new(0x698u, v10);
    v38 = v25;
    if ( v25 )
      v26 = CPortableMediaReader::CPortableMediaReader(v25);
    else
      v26 = 0;
    ATL::CComPtrBase<CStgCreationStream>::Attach(&v35, v26);
    v27 = v35;
    if ( !v35 )
    {
      v8 = -2147024882;
LABEL_77:
      ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(&v35);
      CoTaskMemFree(pv);
      goto LABEL_78;
    }
    if ( !v11 )
    {
      *((_DWORD *)this + 36) = 1;
      v8 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, unsigned __int16 *, _QWORD, LPVOID *, _QWORD))(*((_QWORD *)this + 2) + 24LL))(
             (char *)this + 16,
             0,
             0,
             v39,
             0,
             &pv,
             0);
      *((_DWORD *)this + 36) = 0;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            268,
            (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)v39,
            v8);
        goto LABEL_77;
      }
      v6 = CContentFolder::_IsValid(v28, (const struct _ITEMIDLIST *)pv);
    }
    v8 = CPortableMediaReader::_Initialize(v27, this, v6, v9);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          269,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)v8);
      goto LABEL_77;
    }
    v36 = 0;
    v8 = (**((__int64 (__fastcall ***)(__int64, GUID *, struct IStream **))v27 + 2))(
           (__int64)v27 + 16,
           &GUID_0000000c_0000_0000_c000_000000000046,
           &v36);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          270,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)v8);
      goto LABEL_76;
    }
    if ( (*(unsigned int (__fastcall **)(CContentFolder *, _QWORD, const PROPERTYKEY *))(*(_QWORD *)this + 72LL))(
           this,
           *((_QWORD *)this + 8),
           &WPD_COMMAND_OBJECT_RESOURCES_SEEK) )
    {
      v33 = v36;
      v36 = 0;
      *a5 = v33;
    }
    else
    {
      v30 = (CSeekableStreamOverLimitedSeekStream *)operator new(0x40u, v29);
      v38 = v30;
      if ( v30 )
        v31 = CSeekableStreamOverLimitedSeekStream::CSeekableStreamOverLimitedSeekStream(v30, v36);
      else
        v31 = 0;
      v32 = (struct IStream *)(((unsigned __int64)v31 + 24) & -(__int64)(v31 != 0));
      *a5 = v32;
      if ( !v32 )
      {
        v8 = -2147024882;
LABEL_76:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
        goto LABEL_77;
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(&v35);
    CoTaskMemFree(pv);
    return (unsigned int)v8;
  }
  v8 = -2147467261;
LABEL_78:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      275,
      WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005b90  mov     [rsp-8+arg_18], rbx
0x180005b95  push    rbp
0x180005b96  push    rsi
0x180005b97  push    rdi
0x180005b98  push    r12
0x180005b9a  push    r13
0x180005b9c  push    r14
0x180005b9e  push    r15
0x180005ba0  lea     rbp, [rsp-390h]
0x180005ba8  sub     rsp, 490h
0x180005baf  mov     rax, cs:__security_cookie
0x180005bb6  xor     rax, rsp
0x180005bb9  mov     [rbp+3C0h+var_40], rax
0x180005bc0  mov     ebx, r9d
0x180005bc3  mov     r15d, r8d
0x180005bc6  mov     r14, rdx
0x180005bc9  mov     r12, rcx
0x180005bcc  mov     r13, [rbp+3C0h+arg_20]
0x180005bd3  xor     edi, edi
0x180005bd5  test    r13, r13
0x180005bd8  jnz     short loc_180005BE4
0x180005bda  mov     edi, 80004003h
0x180005bdf  jmp     loc_18000610B
0x180005be4  test    r14, r14
0x180005be7  jnz     short loc_180005BF3
0x180005be9  mov     edi, 80070057h
0x180005bee  jmp     loc_18000610B
0x180005bf3  mov     [r13+0], rdi
0x180005bf7  and     r15d, 0FFFEFF8Fh
0x180005bfe  test    r15d, 0FFFFFFFCh
0x180005c05  jz      short loc_180005C11
0x180005c07  mov     edi, 80030001h
0x180005c0c  jmp     loc_18000610B
0x180005c11  lea     r8, [rsp+4C0h+var_460]; unsigned __int16 *
0x180005c16  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x180005c1b  mov     ecx, [r14+42h]
0x180005c1f  mov     eax, [r14+3Eh]
0x180005c23  add     rax, 25h ; '%'
0x180005c27  add     rcx, rax
0x180005c2a  lea     r8, [r14+rcx*2]; unsigned __int16 *
0x180005c2e  mov     edx, 104h; unsigned __int64
0x180005c33  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x180005c3a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005c3f  movzx   esi, [rbp+3C0h+var_250]
0x180005c46  test    si, si
0x180005c49  jnz     loc_180005EB2
0x180005c4f  test    ebx, ebx
0x180005c51  jnz     short loc_180005CB5
0x180005c53  lea     rdx, [rsp+4C0h+var_460]; unsigned __int16 *
0x180005c58  mov     rcx, r12; this
0x180005c5b  call    ?_RemoveVirtualFile@CContentFolder@@AEAAJPEBG@Z; CContentFolder::_RemoveVirtualFile(ushort const *)
0x180005c60  mov     edi, eax
0x180005c62  test    eax, eax
0x180005c64  jns     short loc_180005CAA
0x180005c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c6d  lea     rbx, WPP_GLOBAL_Control
0x180005c74  cmp     rcx, rbx
0x180005c77  jz      loc_180006112
0x180005c7d  test    byte ptr [rcx+1Ch], 2
0x180005c81  jz      loc_180006112
0x180005c87  mov     edx, 10Ah
0x180005c8c  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x180005c90  lea     r9, [rsp+4C0h+var_460]
0x180005c95  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180005c9c  mov     rcx, [rcx+10h]
0x180005ca0  call    WPP_SF_Sd
0x180005ca5  jmp     loc_180006112
0x180005caa  xor     edi, edi
0x180005cac  cmp     eax, 1
0x180005caf  jz      loc_180005EB2
0x180005cb5  mov     [rsp+4C0h+var_480], rdi
0x180005cba  mov     ecx, 278h; unsigned __int64
0x180005cbf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005cc4  mov     [rsp+4C0h+var_478], rax
0x180005cc9  test    rax, rax
0x180005ccc  jz      short loc_180005CD8
0x180005cce  mov     rcx, rax; this
0x180005cd1  call    ??0CStgCreationStream@@QEAA@XZ; CStgCreationStream::CStgCreationStream(void)
0x180005cd6  jmp     short loc_180005CDB
0x180005cd8  mov     rax, rdi
0x180005cdb  mov     rdx, rax
0x180005cde  lea     rcx, [rsp+4C0h+var_480]
0x180005ce3  call    ?Attach@?$CComPtrBase@VCStgCreationStream@@@ATL@@QEAAXPEAVCStgCreationStream@@@Z; ATL::CComPtrBase<CStgCreationStream>::Attach(CStgCreationStream *)
0x180005ce8  mov     rbx, [rsp+4C0h+var_480]
0x180005ced  test    rbx, rbx
0x180005cf0  jnz     short loc_180005D06
0x180005cf2  mov     edi, 8007000Eh
0x180005cf7  lea     rcx, [rsp+4C0h+var_480]
0x180005cfc  call    ??1?$CComPtrBase@VCStgCreationStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(void)
0x180005d01  jmp     loc_18000610B
0x180005d06  mov     [rsp+4C0h+var_4A0], r14; struct CONTENTITEM *
0x180005d0b  mov     r9d, r15d; unsigned int
0x180005d0e  lea     r8, [rsp+4C0h+var_460]; unsigned __int16 *
0x180005d13  mov     rdx, r12; struct CContentFolder *
0x180005d16  mov     rcx, rbx; this
0x180005d19  call    ?_Initialize@CStgCreationStream@@QEAAJPEAVCContentFolder@@PEBGKPEFBUCONTENTITEM@@@Z; CStgCreationStream::_Initialize(CContentFolder *,ushort const *,ulong,CONTENTITEM const *)
0x180005d1e  mov     edi, eax
0x180005d20  test    eax, eax
0x180005d22  jns     short loc_180005D65
0x180005d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d2b  lea     rbx, WPP_GLOBAL_Control
0x180005d32  cmp     rcx, rbx
0x180005d35  jz      short loc_180005D56
0x180005d37  test    byte ptr [rcx+1Ch], 2
0x180005d3b  jz      short loc_180005D56
0x180005d3d  mov     edx, 10Fh
0x180005d42  mov     r9d, eax
0x180005d45  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180005d4c  mov     rcx, [rcx+10h]
0x180005d50  call    WPP_SF_d
0x180005d55  nop
0x180005d56  lea     rcx, [rsp+4C0h+var_480]
0x180005d5b  call    ??1?$CComPtrBase@VCStgCreationStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(void)
0x180005d60  jmp     loc_180006112
0x180005d65  test    r15b, 3
0x180005d69  jz      short loc_180005DAE
0x180005d6b  lea     rcx, [rbx+10h]
0x180005d6f  mov     rax, [rcx]
0x180005d72  mov     r8, r13
0x180005d75  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180005d7c  mov     rax, [rax]
0x180005d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d84  mov     edi, eax
0x180005d86  test    eax, eax
0x180005d88  jns     loc_180005EA3
0x180005d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d95  lea     rbx, WPP_GLOBAL_Control
0x180005d9c  cmp     rcx, rbx
0x180005d9f  jz      short loc_180005D56
0x180005da1  test    byte ptr [rcx+1Ch], 2
0x180005da5  jz      short loc_180005D56
0x180005da7  mov     edx, 110h
0x180005dac  jmp     short loc_180005D42
0x180005dae  mov     ecx, 48h ; 'H'; unsigned __int64
0x180005db3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005db8  mov     [rsp+4C0h+var_478], rax
0x180005dbd  test    rax, rax
0x180005dc0  jz      short loc_180005DCF
0x180005dc2  mov     rcx, rax; this
0x180005dc5  call    ??0CStgDualStream@@QEAA@XZ; CStgDualStream::CStgDualStream(void)
0x180005dca  mov     rsi, rax
0x180005dcd  jmp     short loc_180005DD1
0x180005dcf  xor     esi, esi
0x180005dd1  mov     [rsp+4C0h+var_478], rsi
0x180005dd6  test    rsi, rsi
0x180005dd9  jnz     short loc_180005DEF
0x180005ddb  mov     edi, 8007000Eh
0x180005de0  lea     rcx, [rsp+4C0h+var_478]
0x180005de5  call    ??1?$CComPtrBase@VCStgCreationStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(void)
0x180005dea  jmp     loc_180005CF7
0x180005def  lea     rcx, [rbx+10h]
0x180005df3  neg     rbx
0x180005df6  sbb     rax, rax
0x180005df9  and     rax, rcx
0x180005dfc  mov     [rsp+4C0h+var_4A0], rax; struct IStream *
0x180005e01  mov     r9, r14; struct CONTENTITEM *
0x180005e04  mov     r8d, r15d; unsigned int
0x180005e07  mov     rdx, r12; struct CContentFolder *
0x180005e0a  mov     rcx, rsi; this
0x180005e0d  call    ?_Initialize@CStgDualStream@@QEAAJPEAVCContentFolder@@KPEFBUCONTENTITEM@@PEAUIStream@@@Z; CStgDualStream::_Initialize(CContentFolder *,ulong,CONTENTITEM const *,IStream *)
0x180005e12  mov     edi, eax
0x180005e14  test    eax, eax
0x180005e16  jns     short loc_180005E59
0x180005e18  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e1f  lea     rbx, WPP_GLOBAL_Control
0x180005e26  cmp     rcx, rbx
0x180005e29  jz      short loc_180005E4A
0x180005e2b  test    byte ptr [rcx+1Ch], 2
0x180005e2f  jz      short loc_180005E4A
0x180005e31  mov     edx, 111h
0x180005e36  mov     r9d, eax
0x180005e39  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180005e40  mov     rcx, [rcx+10h]
0x180005e44  call    WPP_SF_d
0x180005e49  nop
0x180005e4a  lea     rcx, [rsp+4C0h+var_478]
0x180005e4f  call    ??1?$CComPtrBase@VCStgCreationStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(void)
0x180005e54  jmp     loc_180005D56
0x180005e59  lea     rcx, [rsi+10h]
0x180005e5d  mov     rax, [rcx]
0x180005e60  mov     r8, r13
0x180005e63  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180005e6a  mov     rax, [rax]
0x180005e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e72  mov     edi, eax
0x180005e74  test    eax, eax
0x180005e76  jns     short loc_180005E98
0x180005e78  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e7f  lea     rbx, WPP_GLOBAL_Control
0x180005e86  cmp     rcx, rbx
0x180005e89  jz      short loc_180005E4A
0x180005e8b  test    byte ptr [rcx+1Ch], 2
0x180005e8f  jz      short loc_180005E4A
0x180005e91  mov     edx, 112h
0x180005e96  jmp     short loc_180005E36
0x180005e98  lea     rcx, [rsp+4C0h+var_478]
0x180005e9d  call    ??1?$CComPtrBase@VCStgCreationStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(void)
0x180005ea2  nop
0x180005ea3  lea     rcx, [rsp+4C0h+var_480]
0x180005ea8  call    ??1?$CComPtrBase@VCStgCreationStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CStgCreationStream>::~CComPtrBase<CStgCreationStream>(void)
0x180005ead  jmp     loc_18000616D
0x180005eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005eb9  lea     rax, WPP_GLOBAL_Control
0x180005ec0  cmp     rcx, rax
0x180005ec3  jz      short loc_180005EE0
0x180005ec5  test    byte ptr [rcx+1Ch], 40h
0x180005ec9  jz      short loc_180005EE0
0x180005ecb  mov     edx, 10Bh
0x180005ed0  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180005ed7  mov     rcx, [rcx+10h]
0x180005edb  call    WPP_SF_
0x180005ee0  mov     [rsp+4C0h+pv], rdi
0x180005ee5  mov     [rsp+4C0h+var_480], rdi
0x180005eea  mov     ecx, 698h; unsigned __int64
0x180005eef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005ef4  mov     [rsp+4C0h+var_468], rax
0x180005ef9  test    rax, rax
0x180005efc  jz      short loc_180005F08
0x180005efe  mov     rcx, rax; this
0x180005f01  call    ??0CPortableMediaReader@@QEAA@XZ; CPortableMediaReader::CPortableMediaReader(void)
0x180005f06  jmp     short loc_180005F0B
0x180005f08  mov     rax, rdi
0x180005f0b  mov     rdx, rax
0x180005f0e  lea     rcx, [rsp+4C0h+var_480]
0x180005f13  call    ?Attach@?$CComPtrBase@VCStgCreationStream@@@ATL@@QEAAXPEAVCStgCreationStream@@@Z; ATL::CComPtrBase<CStgCreationStream>::Attach(CStgCreationStream *)
0x180005f18  mov     rbx, [rsp+4C0h+var_480]
0x180005f1d  test    rbx, rbx
0x180005f20  jnz     short loc_180005F2C
0x180005f22  mov     edi, 8007000Eh
0x180005f27  jmp     loc_1800060F5
0x180005f2c  test    si, si
0x180005f2f  jnz     loc_180005FD3
0x180005f35  mov     dword ptr [r12+90h], 1
0x180005f41  lea     rcx, [r12+10h]
0x180005f46  mov     rax, [rcx]
0x180005f49  mov     [rsp+4C0h+var_490], rdi
0x180005f4e  lea     rdx, [rsp+4C0h+pv]
0x180005f53  mov     [rsp+4C0h+var_498], rdx
0x180005f58  mov     [rsp+4C0h+var_4A0], rdi
0x180005f5d  lea     r9, [rsp+4C0h+var_460]
0x180005f62  xor     r8d, r8d
0x180005f65  xor     edx, edx
0x180005f67  mov     rax, [rax+18h]
0x180005f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f70  mov     edi, eax
0x180005f72  xor     esi, esi
0x180005f74  mov     [r12+90h], esi
0x180005f7c  test    eax, eax
0x180005f7e  jns     short loc_180005FC4
0x180005f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f87  lea     rax, WPP_GLOBAL_Control
0x180005f8e  cmp     rcx, rax
0x180005f91  jz      loc_1800060F5
0x180005f97  test    byte ptr [rcx+1Ch], 2
0x180005f9b  jz      loc_1800060F5
0x180005fa1  mov     edx, 10Ch
0x180005fa6  mov     dword ptr [rsp+4C0h+var_4A0], edi
0x180005faa  lea     r9, [rsp+4C0h+var_460]
0x180005faf  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180005fb6  mov     rcx, [rcx+10h]
0x180005fba  call    WPP_SF_Sd
0x180005fbf  jmp     loc_1800060F5
0x180005fc4  mov     rdx, [rsp+4C0h+pv]; struct _ITEMIDLIST *
0x180005fc9  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180005fce  mov     r14, rax
0x180005fd1  jmp     short loc_180005FD5
0x180005fd3  xor     esi, esi
0x180005fd5  mov     r9d, r15d; unsigned int
0x180005fd8  mov     r8, r14; struct CONTENTITEM *
0x180005fdb  mov     rdx, r12; struct CContentFolder *
0x180005fde  mov     rcx, rbx; this
0x180005fe1  call    ?_Initialize@CPortableMediaReader@@QEAAJPEAVCContentFolder@@PEFBUCONTENTITEM@@K@Z; CPortableMediaReader::_Initialize(CContentFolder *,CONTENTITEM const *,ulong)
0x180005fe6  mov     edi, eax
0x180005fe8  test    eax, eax
0x180005fea  jns     short loc_18000602A
0x180005fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ff3  lea     rax, WPP_GLOBAL_Control
0x180005ffa  cmp     rcx, rax
0x180005ffd  jz      loc_1800060F5
0x180006003  test    byte ptr [rcx+1Ch], 2
0x180006007  jz      loc_1800060F5
0x18000600d  mov     edx, 10Dh
0x180006012  mov     r9d, edi
0x180006015  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000601c  mov     rcx, [rcx+10h]
0x180006020  call    WPP_SF_d
0x180006025  jmp     loc_1800060F5
0x18000602a  mov     [rsp+4C0h+var_478], rsi
0x18000602f  lea     rcx, [rbx+10h]
0x180006033  mov     rax, [rcx]
0x180006036  lea     r8, [rsp+4C0h+var_478]
0x18000603b  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180006042  mov     rax, [rax]
0x180006045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000604a  mov     edi, eax
0x18000604c  test    eax, eax
0x18000604e  jns     short loc_180006087
0x180006050  mov     rcx, cs:WPP_GLOBAL_Control
0x180006057  lea     rax, WPP_GLOBAL_Control
0x18000605e  cmp     rcx, rax
  ... truncated ...
```
