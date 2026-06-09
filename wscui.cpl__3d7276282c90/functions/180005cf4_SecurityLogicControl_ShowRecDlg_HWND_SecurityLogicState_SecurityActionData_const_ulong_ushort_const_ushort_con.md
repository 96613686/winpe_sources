# SecurityLogicControl::ShowRecDlg(HWND__ *,SecurityLogicState *,SecurityActionData const *,ulong,ushort const *,ushort const *,int,ushort const *,int *)

- ea: `0x180005cf4`
- end: `0x1800061de`
- name: `?ShowRecDlg@SecurityLogicControl@@SAHPEAUHWND__@@PEAVSecurityLogicState@@PEBUSecurityActionData@@KPEBG3H3PEAH@Z`
- size: `1258`
- prototype: `static int(HWND, struct SecurityLogicState *, const struct SecurityActionData *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006520`
- `0x18000774c`

## callees

- `0x180001b90`
- `0x180001cc8`
- `0x180002228`
- `0x180002638`
- `0x180002644`
- `0x180004838`
- `0x180004c48`
- `0x180004f20`
- `0x1800052cc`
- `0x1800055b0`
- `0x180005cf4`
- `0x180006340`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180005d73`
- `ntdll!EtwEventWrite` at `0x180005d73`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005dd4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005dd4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180005ea2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180005ea2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SecurityLogicControl::ShowRecDlg(
        HWND a1,
        struct SecurityLogicState *a2,
        const struct SecurityActionData *a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  unsigned __int64 v6; // r14
  struct SecurityLogicState *v8; // r12
  __int64 v10; // rax
  bool v11; // cf
  unsigned __int64 v12; // rax
  unsigned __int64 *v13; // rax
  char *v14; // rdi
  unsigned __int64 v15; // rax
  char *v16; // rsi
  __int64 v17; // r8
  unsigned __int8 v18; // r15
  __int64 v19; // r14
  _QWORD *v20; // r13
  const struct SecurityActionData *v21; // rbx
  __int64 v22; // rdx
  char *v23; // r13
  int *v24; // r12
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rdx
  char *v28; // r13
  int *v29; // r12
  __int64 v30; // rbx
  __int64 v31; // rdx
  char *v32; // r13
  int *v33; // r12
  __int64 v34; // rbx
  int v35; // eax
  char *v36; // r12
  __int64 v37; // rdx
  int *v38; // rax
  __int64 v39; // rbx
  unsigned int v40; // [rsp+30h] [rbp-D0h]
  int v42; // [rsp+38h] [rbp-C8h] BYREF
  char *v43; // [rsp+40h] [rbp-C0h]
  const struct SecurityActionData *v44; // [rsp+48h] [rbp-B8h]
  struct SecurityLogicState *v45; // [rsp+50h] [rbp-B0h]
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  ATL::CStringData *v49; // [rsp+70h] [rbp-90h]
  __int64 v50; // [rsp+78h] [rbp-88h] BYREF
  HWND v51; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v52; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v53; // [rsp+90h] [rbp-70h]
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v55[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v56; // [rsp+B0h] [rbp-50h]
  int v57; // [rsp+B4h] [rbp-4Ch]
  int v58; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v59[2]; // [rsp+C4h] [rbp-3Ch] BYREF
  int v60; // [rsp+D4h] [rbp-2Ch]
  int v61; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+DCh] [rbp-24h]
  __int64 v63; // [rsp+E4h] [rbp-1Ch]
  const unsigned __int16 *v64; // [rsp+ECh] [rbp-14h]
  const unsigned __int16 *v65; // [rsp+F4h] [rbp-Ch]
  int v66; // [rsp+FCh] [rbp-4h]
  char *v67; // [rsp+100h] [rbp+0h]
  __int64 v68; // [rsp+11Ch] [rbp+1Ch]
  __int64 (__usercall *v69)@<rax>(HWND@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64); // [rsp+14Ch] [rbp+4Ch]
  _QWORD *v70; // [rsp+154h] [rbp+54h]
  WCHAR Dst[264]; // [rsp+160h] [rbp+60h] BYREF

  v6 = a4;
  v44 = a3;
  v8 = a2;
  v45 = a2;
  v51 = a1;
  v52 = a5;
  v53 = a6;
  if ( !a2 )
    return 0;
  EtwEventWrite(g_Provider, "p", 0, 0);
  v42 = 100;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v54);
  v58 = 160;
  memset_0(v59, 0, 0x9Cu);
  v55[0] = v8;
  v55[1] = a3;
  v56 = v6;
  v57 = 0;
  memset_0(Dst, 0, 0x208u);
  ExpandEnvironmentStringsW(*((LPCWSTR *)v8 + 9), Dst, 0x104u);
  v10 = 8 * v6;
  if ( !is_mul_ok(v6, 8u) )
    v10 = -1;
  v11 = __CFADD__(v10, 8);
  v12 = v10 + 8;
  if ( v11 )
    v12 = -1;
  v13 = (unsigned __int64 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  if ( v13 )
  {
    *v13 = v6;
    v14 = (char *)(v13 + 1);
    `eh vector constructor iterator'(
      v13 + 1,
      8u,
      v6,
      SecurityLogicControl::ShowRecDlg_::_2_::WscString::WscString,
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>);
    if ( v14 )
    {
      v15 = 12 * v6;
      if ( !is_mul_ok(v6, 0xCu) )
        v15 = -1;
      v16 = (char *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v16 )
      {
        v18 = 0;
LABEL_50:
        `eh vector destructor iterator'(
          v14,
          8u,
          *((_QWORD *)v14 - 1),
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>);
        operator delete(v14 - 8);
        if ( v16 )
          operator delete(v16);
        goto LABEL_53;
      }
      v43 = v14;
      v40 = 0;
      v18 = 1;
      if ( !(_DWORD)v6 )
      {
LABEL_48:
        v59[1] = hInstance;
        v59[0] = v51;
        v62 = 1181;
        v64 = v52;
        v65 = v53;
        v68 = 0;
        v63 = 5000;
        v66 = v6;
        v67 = v16;
        v61 = 8;
        v60 = 25;
        v70 = v55;
        v69 = ShowRecDialogCallbackProc;
        if ( (int)IsolationAwareTaskDialogIndirect(&v58, &v42, v17, 0) < 0 )
          v18 = 0;
        goto LABEL_50;
      }
      v19 = 0;
      v20 = (_QWORD *)((char *)v8 + 64);
      while ( 1 )
      {
        v21 = v44;
        if ( *((_DWORD *)v44 + 2 * v19) != 121 || PathFileExistsW(Dst) )
        {
          v36 = &v14[8 * v19];
          v37 = *(_QWORD *)SecurityLogicControl::GetString(&v50, *((unsigned int *)v44 + 2 * v19 + 1), *v20);
          v38 = (int *)(*(_QWORD *)v36 - 24LL);
          v49 = (ATL::CStringData *)v38;
          if ( (int *)(v37 - 24) != v38 )
          {
            if ( v38[4] >= 0 && *(_QWORD *)(v37 - 24) == *(_QWORD *)v38 )
            {
              v39 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
              ATL::CStringData::Release(v49);
              *(_QWORD *)v36 = v39 + 24;
              v21 = v44;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v14[8 * v19], v37, *(unsigned int *)(v37 - 16));
            }
          }
          ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
          v35 = *((_DWORD *)v21 + 2 * v19);
          goto LABEL_46;
        }
        if ( *((_DWORD *)v8 + 2) == 1 )
        {
          v31 = *(_QWORD *)SecurityLogicControl::GetString(&v48, 1254, *v20);
          v32 = &v43[8 * v19];
          v33 = (int *)(*(_QWORD *)v32 - 24LL);
          if ( (int *)(v31 - 24) != v33 )
          {
            if ( v33[4] >= 0 && *(_QWORD *)(v31 - 24) == *(_QWORD *)v33 )
            {
              v34 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
              ATL::CStringData::Release((ATL::CStringData *)v33);
              *(_QWORD *)v32 = v34 + 24;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v43[8 * v19], v31, *(unsigned int *)(v31 - 16));
            }
          }
          v26 = v48;
          goto LABEL_38;
        }
        if ( *((_DWORD *)v8 + 2) == 3 )
          break;
        if ( *((_DWORD *)v8 + 2) == 4 )
        {
          v22 = *(_QWORD *)SecurityLogicControl::GetString(&v46, 1279, *((_QWORD *)v8 + 8));
          v23 = &v43[8 * v19];
          v24 = (int *)(*(_QWORD *)v23 - 24LL);
          if ( (int *)(v22 - 24) != v24 )
          {
            if ( v24[4] >= 0 && *(_QWORD *)(v22 - 24) == *(_QWORD *)v24 )
            {
              v25 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
              ATL::CStringData::Release((ATL::CStringData *)v24);
              *(_QWORD *)v23 = v25 + 24;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v43[8 * v19], v22, *(unsigned int *)(v22 - 16));
            }
          }
          v26 = v46;
LABEL_38:
          ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
        }
        v35 = 101;
        v36 = &v14[8 * v19];
        v20 = (_QWORD *)((char *)v45 + 64);
LABEL_46:
        *(_DWORD *)&v16[12 * v19] = v35;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Remove(v36);
        *(_QWORD *)&v16[12 * v19 + 4] = *(_QWORD *)v36;
        ++v40;
        ++v19;
        v8 = v45;
        if ( v40 >= a4 )
        {
          LODWORD(v6) = a4;
          goto LABEL_48;
        }
      }
      v27 = *(_QWORD *)SecurityLogicControl::GetString(&v47, 1264, *v20);
      v28 = &v43[8 * v19];
      v29 = (int *)(*(_QWORD *)v28 - 24LL);
      if ( (int *)(v27 - 24) != v29 )
      {
        if ( v29[4] >= 0 && *(_QWORD *)(v27 - 24) == *(_QWORD *)v29 )
        {
          v30 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v29);
          *(_QWORD *)v28 = v30 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v43[8 * v19], v27, *(unsigned int *)(v27 - 16));
        }
      }
      v26 = v47;
      goto LABEL_38;
    }
  }
  v18 = 0;
LABEL_53:
  ATL::CStringData::Release((ATL::CStringData *)(v54 - 24));
  return v18;
}

```

## disassembly

```asm
0x180005cf4  push    rbp
0x180005cf6  push    rbx
0x180005cf7  push    rsi
0x180005cf8  push    rdi
0x180005cf9  push    r12
0x180005cfb  push    r13
0x180005cfd  push    r14
0x180005cff  push    r15
0x180005d01  lea     rbp, [rsp-288h]
0x180005d09  sub     rsp, 388h
0x180005d10  mov     rax, cs:__security_cookie
0x180005d17  xor     rax, rsp
0x180005d1a  mov     [rbp+2C0h+var_50], rax
0x180005d21  mov     r14d, r9d
0x180005d24  mov     [rsp+3C0h+var_38C], r14d
0x180005d29  mov     rbx, r8
0x180005d2c  mov     [rsp+3C0h+var_378], rbx
0x180005d31  mov     r12, rdx
0x180005d34  mov     [rsp+3C0h+var_370], rdx
0x180005d39  mov     [rbp+2C0h+var_340], rcx
0x180005d3d  mov     rax, [rbp+2C0h+arg_20]
0x180005d44  mov     [rbp+2C0h+var_338], rax
0x180005d48  mov     rax, [rbp+2C0h+arg_28]
0x180005d4f  mov     [rbp+2C0h+var_330], rax
0x180005d53  test    rdx, rdx
0x180005d56  jnz     short loc_180005D5F
0x180005d58  xor     eax, eax
0x180005d5a  jmp     loc_1800061BB
0x180005d5f  xor     r9d, r9d
0x180005d62  xor     r8d, r8d
0x180005d65  lea     rdx, WSC_UI_LaunchDialog_Begin; "p"
0x180005d6c  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x180005d73  call    cs:__imp_EtwEventWrite
0x180005d79  mov     [rsp+3C0h+var_388], 64h ; 'd'
0x180005d81  lea     rcx, [rbp+2C0h+var_328]
0x180005d85  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180005d8a  nop
0x180005d8b  mov     [rbp+2C0h+var_300], 0A0h
0x180005d92  xor     edx, edx; Val
0x180005d94  mov     r8d, 9Ch; Size
0x180005d9a  lea     rcx, [rbp+2C0h+var_2FC]; void *
0x180005d9e  call    memset_0
0x180005da3  mov     [rbp+2C0h+var_320], r12
0x180005da7  mov     [rbp+2C0h+var_318], rbx
0x180005dab  mov     [rbp+2C0h+var_310], r14d
0x180005daf  xor     eax, eax
0x180005db1  mov     [rbp+2C0h+var_30C], eax
0x180005db4  xor     edx, edx; Val
0x180005db6  mov     r8d, 208h; Size
0x180005dbc  lea     rcx, [rbp+2C0h+Dst]; void *
0x180005dc0  call    memset_0
0x180005dc5  mov     r8d, 104h; nSize
0x180005dcb  lea     rdx, [rbp+2C0h+Dst]; lpDst
0x180005dcf  mov     rcx, [r12+48h]; lpSrc
0x180005dd4  call    cs:__imp_ExpandEnvironmentStringsW
0x180005dda  mov     rbx, r14
0x180005ddd  mov     r13d, 8
0x180005de3  mov     eax, r13d
0x180005de6  mul     r14
0x180005de9  lea     rsi, [r13-9]
0x180005ded  cmovb   rax, rsi
0x180005df1  add     rax, r13
0x180005df4  cmovb   rax, rsi
0x180005df8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005dff  mov     rcx, rax; unsigned __int64
0x180005e02  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005e07  test    rax, rax
0x180005e0a  jz      loc_1800061A7
0x180005e10  mov     [rax], rbx
0x180005e13  lea     rdi, [rax+8]
0x180005e17  lea     rax, ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180005e1e  mov     [rsp+3C0h+var_3A0], rax; void (*)(void *)
0x180005e23  lea     r9, _SecurityLogicControl__ShowRecDlg____2___WscString__WscString; void (*)(void *)
0x180005e2a  mov     r8, rbx; unsigned __int64
0x180005e2d  mov     edx, r13d; unsigned __int64
0x180005e30  mov     rcx, rdi; void *
0x180005e33  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180005e38  test    rdi, rdi
0x180005e3b  jz      loc_1800061A7
0x180005e41  lea     eax, [rsi+0Dh]
0x180005e44  mul     rbx
0x180005e47  cmovb   rax, rsi
0x180005e4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005e52  mov     rcx, rax; unsigned __int64
0x180005e55  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005e5a  mov     rsi, rax
0x180005e5d  test    rax, rax
0x180005e60  jnz     short loc_180005E6A
0x180005e62  xor     r15b, r15b
0x180005e65  jmp     loc_180006178
0x180005e6a  mov     [rsp+3C0h+var_380], rdi
0x180005e6f  mov     [rsp+3C0h+var_390], 0
0x180005e77  mov     r15d, 1
0x180005e7d  test    r14d, r14d
0x180005e80  jz      loc_1800060FA
0x180005e86  xor     r14d, r14d
0x180005e89  lea     r13, [r12+40h]
0x180005e8e  mov     rbx, [rsp+3C0h+var_378]
0x180005e93  cmp     dword ptr [rbx+r14*8], 79h ; 'y'
0x180005e98  jnz     loc_18000603B
0x180005e9e  lea     rcx, [rbp+2C0h+Dst]; pszPath
0x180005ea2  call    cs:__imp_PathFileExistsW
0x180005ea8  test    eax, eax
0x180005eaa  jnz     loc_18000603B
0x180005eb0  mov     ecx, [r12+8]
0x180005eb5  sub     ecx, 1
0x180005eb8  jz      loc_180005FB0
0x180005ebe  sub     ecx, 2
0x180005ec1  jz      short loc_180005F40
0x180005ec3  cmp     ecx, 1
0x180005ec6  jnz     loc_180006027
0x180005ecc  mov     r8, [r12+40h]
0x180005ed1  mov     edx, 4FFh
0x180005ed6  lea     rcx, [rsp+3C0h+var_368]
0x180005edb  call    ?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z; SecurityLogicControl::GetString(int,ushort const *)
0x180005ee0  nop
0x180005ee1  mov     rdx, [rax]
0x180005ee4  lea     rcx, [rdx-18h]
0x180005ee8  mov     rax, [rsp+3C0h+var_380]
0x180005eed  lea     r13, [rax+r14*8]
0x180005ef1  mov     r12, [r13+0]
0x180005ef5  add     r12, 0FFFFFFFFFFFFFFE8h
0x180005ef9  cmp     rcx, r12
0x180005efc  jz      short loc_180005F36
0x180005efe  cmp     dword ptr [r12+10h], 0
0x180005f04  jl      short loc_180005F29
0x180005f06  mov     rax, [r12]
0x180005f0a  cmp     [rcx], rax
0x180005f0d  jnz     short loc_180005F29
0x180005f0f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180005f14  mov     rbx, rax
0x180005f17  mov     rcx, r12; this
0x180005f1a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005f1f  lea     rax, [rbx+18h]
0x180005f23  mov     [r13+0], rax
0x180005f27  jmp     short loc_180005F36
0x180005f29  mov     r8d, [rdx-10h]
0x180005f2d  mov     rcx, r13
0x180005f30  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180005f35  nop
0x180005f36  mov     rcx, [rsp+3C0h+var_368]
0x180005f3b  jmp     loc_18000601E
0x180005f40  mov     r8, [r13+0]
0x180005f44  mov     edx, 4F0h
0x180005f49  lea     rcx, [rsp+3C0h+var_360]
0x180005f4e  call    ?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z; SecurityLogicControl::GetString(int,ushort const *)
0x180005f53  nop
0x180005f54  mov     rdx, [rax]
0x180005f57  lea     rcx, [rdx-18h]
0x180005f5b  mov     rax, [rsp+3C0h+var_380]
0x180005f60  lea     r13, [rax+r14*8]
0x180005f64  mov     r12, [r13+0]
0x180005f68  add     r12, 0FFFFFFFFFFFFFFE8h
0x180005f6c  cmp     rcx, r12
0x180005f6f  jz      short loc_180005FA9
0x180005f71  cmp     dword ptr [r12+10h], 0
0x180005f77  jl      short loc_180005F9C
0x180005f79  mov     rax, [r12]
0x180005f7d  cmp     [rcx], rax
0x180005f80  jnz     short loc_180005F9C
0x180005f82  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180005f87  mov     rbx, rax
0x180005f8a  mov     rcx, r12; this
0x180005f8d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005f92  lea     rax, [rbx+18h]
0x180005f96  mov     [r13+0], rax
0x180005f9a  jmp     short loc_180005FA9
0x180005f9c  mov     r8d, [rdx-10h]
0x180005fa0  mov     rcx, r13
0x180005fa3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180005fa8  nop
0x180005fa9  mov     rcx, [rsp+3C0h+var_360]
0x180005fae  jmp     short loc_18000601E
0x180005fb0  mov     r8, [r13+0]
0x180005fb4  mov     edx, 4E6h
0x180005fb9  lea     rcx, [rsp+3C0h+var_358]
0x180005fbe  call    ?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z; SecurityLogicControl::GetString(int,ushort const *)
0x180005fc3  nop
0x180005fc4  mov     rdx, [rax]
0x180005fc7  lea     rcx, [rdx-18h]
0x180005fcb  mov     rax, [rsp+3C0h+var_380]
0x180005fd0  lea     r13, [rax+r14*8]
0x180005fd4  mov     r12, [r13+0]
0x180005fd8  add     r12, 0FFFFFFFFFFFFFFE8h
0x180005fdc  cmp     rcx, r12
0x180005fdf  jz      short loc_180006019
0x180005fe1  cmp     dword ptr [r12+10h], 0
0x180005fe7  jl      short loc_18000600C
0x180005fe9  mov     rax, [r12]
0x180005fed  cmp     [rcx], rax
0x180005ff0  jnz     short loc_18000600C
0x180005ff2  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180005ff7  mov     rbx, rax
0x180005ffa  mov     rcx, r12; this
0x180005ffd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006002  lea     rax, [rbx+18h]
0x180006006  mov     [r13+0], rax
0x18000600a  jmp     short loc_180006019
0x18000600c  mov     r8d, [rdx-10h]
0x180006010  mov     rcx, r13
0x180006013  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006018  nop
0x180006019  mov     rcx, [rsp+3C0h+var_358]
0x18000601e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180006022  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006027  mov     eax, 65h ; 'e'
0x18000602c  lea     r12, [rdi+r14*8]
0x180006030  mov     r13, [rsp+3C0h+var_370]
0x180006035  add     r13, 40h ; '@'
0x180006039  jmp     short loc_1800060BA
0x18000603b  mov     r8, [r13+0]
0x18000603f  mov     edx, [rbx+r14*8+4]
0x180006044  lea     rcx, [rsp+3C0h+var_348]
0x180006049  call    ?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z; SecurityLogicControl::GetString(int,ushort const *)
0x18000604e  nop
0x18000604f  lea     r12, [rdi+r14*8]
0x180006053  mov     rdx, [rax]
0x180006056  lea     rcx, [rdx-18h]
0x18000605a  mov     rax, [r12]
0x18000605e  add     rax, 0FFFFFFFFFFFFFFE8h
0x180006062  mov     [rsp+3C0h+var_350], rax
0x180006067  cmp     rcx, rax
0x18000606a  jz      short loc_1800060A8
0x18000606c  cmp     dword ptr [rax+10h], 0
0x180006070  jl      short loc_18000609B
0x180006072  mov     rax, [rax]
0x180006075  cmp     [rcx], rax
0x180006078  jnz     short loc_18000609B
0x18000607a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000607f  mov     rbx, rax
0x180006082  mov     rcx, [rsp+3C0h+var_350]; this
0x180006087  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000608c  lea     rax, [rbx+18h]
0x180006090  mov     [r12], rax
0x180006094  mov     rbx, [rsp+3C0h+var_378]
0x180006099  jmp     short loc_1800060A8
0x18000609b  mov     r8d, [rdx-10h]
0x18000609f  mov     rcx, r12
0x1800060a2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800060a7  nop
0x1800060a8  mov     rcx, [rsp+3C0h+var_348]
0x1800060ad  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800060b1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800060b6  mov     eax, [rbx+r14*8]
0x1800060ba  lea     rbx, [r14+r14*2]
0x1800060be  mov     [rsi+rbx*4], eax
0x1800060c1  mov     rcx, r12
0x1800060c4  call    ?Remove@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Remove(ushort)
0x1800060c9  mov     rax, [r12]
0x1800060cd  mov     [rsi+rbx*4+4], rax
0x1800060d2  mov     eax, [rsp+3C0h+var_390]
0x1800060d6  add     eax, r15d
0x1800060d9  mov     [rsp+3C0h+var_390], eax
0x1800060dd  add     r14, r15
0x1800060e0  cmp     eax, [rsp+3C0h+var_38C]
0x1800060e4  mov     r12, [rsp+3C0h+var_370]
0x1800060e9  jb      loc_180005E8E
0x1800060ef  mov     r14d, [rsp+3C0h+var_38C]
0x1800060f4  mov     r13d, 8
0x1800060fa  mov     rax, cs:hInstance
0x180006101  mov     [rbp+2C0h+var_2F4], rax
0x180006105  mov     rax, [rbp+2C0h+var_340]
0x180006109  mov     [rbp+2C0h+var_2FC], rax
0x18000610d  mov     [rbp+2C0h+var_2E4], 49Dh
0x180006115  mov     rax, [rbp+2C0h+var_338]
0x180006119  mov     [rbp+2C0h+var_2D4], rax
0x18000611d  mov     rax, [rbp+2C0h+var_330]
0x180006121  mov     [rbp+2C0h+var_2CC], rax
0x180006125  mov     [rbp+2C0h+var_2A4], 0
0x18000612d  mov     [rbp+2C0h+var_2DC], 1388h
0x180006135  mov     [rbp+2C0h+var_2C4], r14d
0x180006139  mov     [rbp+2C0h+var_2C0], rsi
0x18000613d  mov     [rbp+2C0h+var_2E8], r13d
0x180006141  mov     [rbp+2C0h+var_2EC], 19h
0x180006148  lea     rax, [rbp+2C0h+var_320]
0x18000614c  mov     [rbp+2C0h+var_26C], rax
0x180006150  lea     rax, ?ShowRecDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; ShowRecDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180006157  mov     [rbp+2C0h+var_274], rax
0x18000615b  xor     r9d, r9d
0x18000615e  lea     rdx, [rsp+3C0h+var_388]
0x180006163  lea     rcx, [rbp+2C0h+var_300]
0x180006167  call    IsolationAwareTaskDialogIndirect
0x18000616c  test    eax, eax
0x18000616e  jns     short loc_180006173
0x180006170  xor     r15b, r15b
0x180006173  test    rdi, rdi
0x180006176  jz      short loc_18000619D
0x180006178  lea     r9, ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; void (*)(void *)
0x18000617f  mov     r8, [rdi-8]; unsigned __int64
0x180006183  mov     rdx, r13; unsigned __int64
0x180006186  mov     rcx, rdi; void *
0x180006189  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000618e  lea     rcx, [rdi-8]; Block
0x180006192  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006197  nop
0x180006198  test    rsi, rsi
0x18000619b  jz      short loc_1800061AA
0x18000619d  mov     rcx, rsi; Block
0x1800061a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800061a5  jmp     short loc_1800061AA
  ... truncated ...
```
