# CUserManager::_CreateAccount(ushort const *,ushort const *,ushort const *,bool,CUserData * *)

- ea: `0x18000d200`
- end: `0x18000d55a`
- name: `?_CreateAccount@CUserManager@@AEAAJPEBG00_NPEAPEAVCUserData@@@Z`
- size: `858`
- prototype: `__int64 __fastcall(struct CUserData ***this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool, struct CUserData **)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009874`
- `0x180009a50`
- `0x18000a8f0`

## callees

- `0x180009ec4`
- `0x18000a540`
- `0x18000d200`
- `0x18000d560`
- `0x180078010`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000d24e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000d24e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d514`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d28f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d2db`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d352`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d3ba`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d419`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d461`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d28f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d2db`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d352`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d3ba`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d419`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d461`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d319`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3f0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d495`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d319`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3f0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d495`
- `OLEAUT32!__imp_VariantInit` at `0x18000d278`
- `OLEAUT32!__imp_VariantInit` at `0x18000d2ab`
- `OLEAUT32!__imp_VariantInit` at `0x18000d377`
- `OLEAUT32!__imp_VariantInit` at `0x18000d42e`
- `OLEAUT32!__imp_VariantInit` at `0x18000d278`
- `OLEAUT32!__imp_VariantInit` at `0x18000d2ab`
- `OLEAUT32!__imp_VariantInit` at `0x18000d377`
- `OLEAUT32!__imp_VariantInit` at `0x18000d42e`
- `OLEAUT32!__imp_VariantClear` at `0x18000d4a0`
- `OLEAUT32!__imp_VariantClear` at `0x18000d4d4`
- `OLEAUT32!__imp_VariantClear` at `0x18000d4de`
- `OLEAUT32!__imp_VariantClear` at `0x18000d51e`
- `OLEAUT32!__imp_VariantClear` at `0x18000d4a0`
- `OLEAUT32!__imp_VariantClear` at `0x18000d4d4`
- `OLEAUT32!__imp_VariantClear` at `0x18000d4de`
- `OLEAUT32!__imp_VariantClear` at `0x18000d51e`

## pseudocode

```c
__int64 __fastcall CUserManager::_CreateAccount(
        struct CUserData ***this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        struct CUserData **a6)
{
  struct CUserData **v6; // r13
  HRESULT v11; // eax
  int v12; // edi
  struct CUserData **v13; // rdi
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v15; // xmm6
  struct CUserData *v16; // rax
  OLECHAR *v17; // rbx
  int v18; // ecx
  __int64 (__fastcall *v19)(struct CUserData **, OLECHAR *, ULONG *, struct CUserData ***); // rax
  struct CUserData **v20; // rcx
  struct CUserData *v21; // rdi
  __int128 v22; // xmm6
  IRecordInfo *v23; // xmm7_8
  BSTR v24; // rax
  int v25; // ecx
  OLECHAR *v26; // rbx
  BSTR v27; // rdx
  __int64 (__fastcall *v28)(struct CUserData **, BSTR, ULONG *); // rax
  __int128 v29; // xmm6
  IRecordInfo *v30; // xmm7_8
  struct CUserData *v31; // rdi
  BSTR v32; // rax
  int v33; // ecx
  OLECHAR *v34; // rbx
  BSTR v35; // rdx
  __int64 (__fastcall *v36)(struct CUserData **, BSTR, __int128 *); // rax
  struct CUserData **v37; // rcx
  struct CUserData *v39; // [rsp+38h] [rbp-99h] BYREF
  VARIANTARG v40; // [rsp+40h] [rbp-91h] BYREF
  IRecordInfo *v41; // [rsp+58h] [rbp-79h]
  VARIANTARG v42; // [rsp+68h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-51h] BYREF
  __int128 v44; // [rsp+98h] [rbp-39h] BYREF
  IRecordInfo *v45; // [rsp+A8h] [rbp-29h]
  LPWSTR ppwsz; // [rsp+130h] [rbp+5Fh] BYREF

  v6 = a6;
  ppwsz = 0;
  *a6 = 0;
  if ( a2 )
    v11 = SHStrDupW(a3, &ppwsz);
  else
    v11 = CUserManager::_GenerateUniqueLoginName((CUserManager *)this, a3, &ppwsz);
  v12 = v11;
  if ( v11 < 0 )
    return (unsigned int)v12;
  a6 = 0;
  VariantInit(&pvarg);
  if ( a2 )
  {
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(a2);
    if ( pvarg.llVal )
    {
      v12 = 0;
    }
    else
    {
      v12 = -2147024882;
      VariantInit(&pvarg);
    }
  }
  if ( v12 >= 0 )
  {
    v13 = this[8];
    pRecInfo = pvarg.pRecInfo;
    v15 = *(_OWORD *)&pvarg.vt;
    v16 = *v13;
    v39 = *v13;
    if ( ppwsz )
    {
      v17 = SysAllocString(ppwsz);
      if ( !v17 )
        ATL::AtlThrowImpl(v18);
      v16 = v39;
    }
    else
    {
      v17 = 0;
    }
    v19 = (__int64 (__fastcall *)(struct CUserData **, OLECHAR *, ULONG *, struct CUserData ***))*((_QWORD *)v16 + 7);
    *(_OWORD *)&v40.decVal.Lo32 = v15;
    v41 = pRecInfo;
    v12 = v19(v13, v17, (ULONG *)&v40.cyVal, &a6);
    SysFreeString(v17);
    if ( v12 >= 0 )
    {
      v20 = a6;
      if ( a6 )
      {
        memset(&v42, 0, sizeof(v42));
        if ( a4 )
        {
          v42.vt = 8;
          v42.llVal = (LONGLONG)SysAllocString(a4);
          if ( v42.llVal )
          {
            v12 = 0;
          }
          else
          {
            v12 = -2147024882;
            VariantInit(&v42);
          }
          v20 = a6;
        }
        else
        {
          v42.vt = 3;
          v12 = 0;
          v42.lVal = 2 * !a5 + 1;
        }
        if ( v12 >= 0 )
        {
          v21 = *v20;
          v22 = *(_OWORD *)&v42.vt;
          v23 = v42.pRecInfo;
          v24 = SysAllocString(L"AccountType");
          v26 = v24;
          if ( !v24 )
            ATL::AtlThrowImpl(v25);
          v27 = v24;
          *(_OWORD *)&v40.decVal.Lo32 = v22;
          v28 = (__int64 (__fastcall *)(struct CUserData **, BSTR, ULONG *))*((_QWORD *)v21 + 4);
          v41 = v23;
          v12 = v28(a6, v27, (ULONG *)&v40.cyVal);
          SysFreeString(v26);
          if ( v12 < 0 )
            goto LABEL_33;
          v41 = 0;
          *(_OWORD *)&v40.decVal.Lo32 = 0;
          v40.iVal = 8;
          v40.pRecInfo = (IRecordInfo *)SysAllocString(a3);
          if ( v40.pRecInfo )
          {
            if ( a2 )
              goto LABEL_31;
            v29 = *(_OWORD *)&v40.decVal.Lo32;
            v30 = v41;
            v31 = *a6;
            v32 = SysAllocString(L"DisplayName");
            v34 = v32;
            if ( !v32 )
              ATL::AtlThrowImpl(v33);
            v35 = v32;
            v44 = v29;
            v36 = (__int64 (__fastcall *)(struct CUserData **, BSTR, __int128 *))*((_QWORD *)v31 + 4);
            v45 = v30;
            v12 = v36(a6, v35, &v44);
            SysFreeString(v34);
            VariantClear((VARIANTARG *)&v40.decVal.8);
          }
          else
          {
            VariantInit((VARIANTARG *)&v40.decVal.8);
            v12 = a3 != 0 ? -2147024882 : -2147024809;
          }
          if ( v12 < 0 )
          {
LABEL_33:
            VariantClear(&v42);
            goto LABEL_34;
          }
LABEL_31:
          v39 = 0;
          v12 = Microsoft::WRL::Details::MakeAndInitialize<CUserData,CUserData,ILogonUser * &>(&v39, &a6);
          if ( v12 >= 0 )
            *v6 = v39;
          goto LABEL_33;
        }
      }
    }
  }
LABEL_34:
  VariantClear(&pvarg);
  v37 = a6;
  a6 = 0;
  if ( v37 )
    (*((void (__fastcall **)(struct CUserData **))*v37 + 2))(v37);
  ((void (__fastcall *)(struct CUserData ***))(*this)[5])(this);
  CoTaskMemFree(ppwsz);
  VariantClear(&pvarg);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d200  mov     rax, rsp
0x18000d203  push    rbp
0x18000d204  push    rbx
0x18000d205  push    rsi
0x18000d206  push    rdi
0x18000d207  push    r12
0x18000d209  push    r13
0x18000d20b  push    r14
0x18000d20d  push    r15
0x18000d20f  lea     rbp, [rax-4Fh]
0x18000d213  sub     rsp, 0D8h
0x18000d21a  mov     r13, [rbp+47h+arg_28]
0x18000d21e  mov     r12, r9
0x18000d221  movaps  xmmword ptr [rax-58h], xmm6
0x18000d225  mov     rsi, r8
0x18000d228  movaps  xmmword ptr [rax-68h], xmm7
0x18000d22c  mov     r14, rdx
0x18000d22f  mov     [rbp+47h+ppwsz], 0
0x18000d237  mov     r15, rcx
0x18000d23a  mov     qword ptr [r13+0], 0
0x18000d242  test    rdx, rdx
0x18000d245  jz      short loc_18000D256
0x18000d247  lea     rdx, [rbp+47h+ppwsz]; ppwsz
0x18000d24b  mov     rcx, r8; psz
0x18000d24e  call    cs:__imp_SHStrDupW
0x18000d254  jmp     short loc_18000D262
0x18000d256  lea     r8, [rbp+47h+ppwsz]; unsigned __int16 **
0x18000d25a  mov     rdx, rsi; unsigned __int16 *
0x18000d25d  call    ?_GenerateUniqueLoginName@CUserManager@@AEAAJPEBGPEAPEAG@Z; CUserManager::_GenerateUniqueLoginName(ushort const *,ushort * *)
0x18000d262  mov     edi, eax
0x18000d264  test    eax, eax
0x18000d266  js      loc_18000D524
0x18000d26c  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000d270  mov     [rbp+47h+arg_28], 0
0x18000d278  call    cs:__imp_VariantInit
0x18000d27e  mov     eax, 8
0x18000d283  test    r14, r14
0x18000d286  jz      short loc_18000D2B1
0x18000d288  mov     rcx, r14; psz
0x18000d28b  mov     word ptr [rbp+47h+pvarg], ax
0x18000d28f  call    cs:__imp_SysAllocString
0x18000d295  mov     qword ptr [rbp+47h+pvarg+8], rax
0x18000d299  test    rax, rax
0x18000d29c  jz      short loc_18000D2A2
0x18000d29e  xor     edi, edi
0x18000d2a0  jmp     short loc_18000D2B1
0x18000d2a2  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000d2a6  mov     edi, 8007000Eh
0x18000d2ab  call    cs:__imp_VariantInit
0x18000d2b1  test    edi, edi
0x18000d2b3  js      loc_18000D4DA
0x18000d2b9  mov     rdi, [r15+40h]
0x18000d2bd  mov     rcx, [rbp+47h+ppwsz]; psz
0x18000d2c1  movsd   xmm7, qword ptr [rbp+47h+pvarg+10h]
0x18000d2c6  movups  xmm6, xmmword ptr [rbp+47h+pvarg]
0x18000d2ca  mov     rax, [rdi]
0x18000d2cd  mov     [rsp+110h+var_E0], rax
0x18000d2d2  test    rcx, rcx
0x18000d2d5  jnz     short loc_18000D2DB
0x18000d2d7  xor     ebx, ebx
0x18000d2d9  jmp     short loc_18000D2F2
0x18000d2db  call    cs:__imp_SysAllocString
0x18000d2e1  mov     rbx, rax
0x18000d2e4  test    rax, rax
0x18000d2e7  jz      loc_18000D54E
0x18000d2ed  mov     rax, [rsp+110h+var_E0]
0x18000d2f2  mov     rax, [rax+38h]
0x18000d2f6  lea     r9, [rbp+47h+arg_28]
0x18000d2fa  lea     r8, [rsp+110h+var_D8+8]
0x18000d2ff  movaps  xmmword ptr [rsp+110h+var_D8+8], xmm6
0x18000d304  mov     rdx, rbx
0x18000d307  movsd   [rbp+47h+var_C0], xmm7
0x18000d30c  mov     rcx, rdi
0x18000d30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d314  mov     rcx, rbx; bstrString
0x18000d317  mov     edi, eax
0x18000d319  call    cs:__imp_SysFreeString
0x18000d31f  test    edi, edi
0x18000d321  js      loc_18000D4DA
0x18000d327  mov     rcx, [rbp+47h+arg_28]
0x18000d32b  test    rcx, rcx
0x18000d32e  jz      loc_18000D4DA
0x18000d334  xor     eax, eax
0x18000d336  xorps   xmm0, xmm0
0x18000d339  mov     qword ptr [rbp+47h+var_B0+10h], rax
0x18000d33d  movups  xmmword ptr [rbp+47h+var_B0], xmm0
0x18000d341  test    r12, r12
0x18000d344  jz      short loc_18000D383
0x18000d346  mov     eax, 8
0x18000d34b  mov     rcx, r12; psz
0x18000d34e  mov     word ptr [rbp+47h+var_B0], ax
0x18000d352  call    cs:__imp_SysAllocString
0x18000d358  mov     rcx, rax
0x18000d35b  mov     dword ptr [rbp+47h+var_B0+8], eax
0x18000d35e  sar     rcx, 20h
0x18000d362  mov     dword ptr [rbp+47h+var_B0+0Ch], ecx
0x18000d365  test    rax, rax
0x18000d368  jz      short loc_18000D36E
0x18000d36a  xor     edi, edi
0x18000d36c  jmp     short loc_18000D37D
0x18000d36e  lea     rcx, [rbp+47h+var_B0]; pvarg
0x18000d372  mov     edi, 8007000Eh
0x18000d377  call    cs:__imp_VariantInit
0x18000d37d  mov     rcx, [rbp+47h+arg_28]
0x18000d381  jmp     short loc_18000D39F
0x18000d383  mov     eax, 3
0x18000d388  mov     word ptr [rbp+47h+var_B0], ax
0x18000d38c  movzx   eax, [rbp+47h+arg_20]
0x18000d390  xor     eax, 1
0x18000d393  xor     edi, edi
0x18000d395  lea     eax, ds:1[rax*2]
0x18000d39c  mov     dword ptr [rbp+47h+var_B0+8], eax
0x18000d39f  test    edi, edi
0x18000d3a1  js      loc_18000D4DA
0x18000d3a7  mov     rdi, [rcx]
0x18000d3aa  lea     rcx, aAccounttype; "AccountType"
0x18000d3b1  movups  xmm6, xmmword ptr [rbp+47h+var_B0]
0x18000d3b5  movsd   xmm7, qword ptr [rbp+47h+var_B0+10h]
0x18000d3ba  call    cs:__imp_SysAllocString
0x18000d3c0  mov     rbx, rax
0x18000d3c3  test    rax, rax
0x18000d3c6  jz      loc_18000D554
0x18000d3cc  mov     rcx, [rbp+47h+arg_28]
0x18000d3d0  lea     r8, [rsp+110h+var_D8+8]
0x18000d3d5  mov     rdx, rax
0x18000d3d8  movaps  xmmword ptr [rsp+110h+var_D8+8], xmm6
0x18000d3dd  mov     rax, [rdi+20h]
0x18000d3e1  movsd   [rbp+47h+var_C0], xmm7
0x18000d3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3eb  mov     rcx, rbx; bstrString
0x18000d3ee  mov     edi, eax
0x18000d3f0  call    cs:__imp_SysFreeString
0x18000d3f6  test    edi, edi
0x18000d3f8  js      loc_18000D4D0
0x18000d3fe  xor     eax, eax
0x18000d400  xorps   xmm0, xmm0
0x18000d403  mov     [rbp+47h+var_C0], rax
0x18000d407  mov     rcx, rsi; psz
0x18000d40a  mov     eax, 8
0x18000d40f  movups  xmmword ptr [rsp+110h+var_D8+8], xmm0
0x18000d414  mov     word ptr [rsp+110h+var_D8+8], ax
0x18000d419  call    cs:__imp_SysAllocString
0x18000d41f  mov     qword ptr [rsp+110h+var_D8+10h], rax
0x18000d424  test    rax, rax
0x18000d427  jnz     short loc_18000D444
0x18000d429  lea     rcx, [rsp+110h+var_D8+8]; pvarg
0x18000d42e  call    cs:__imp_VariantInit
0x18000d434  neg     rsi
0x18000d437  sbb     edi, edi
0x18000d439  and     edi, 0FFFFFFB7h
0x18000d43c  add     edi, 80070057h
0x18000d442  jmp     short loc_18000D4A6
0x18000d444  test    r14, r14
0x18000d447  jnz     short loc_18000D4AA
0x18000d449  mov     rax, [rbp+47h+arg_28]
0x18000d44d  lea     rcx, aDisplayname; "DisplayName"
0x18000d454  movups  xmm6, xmmword ptr [rsp+110h+var_D8+8]
0x18000d459  movsd   xmm7, [rbp+47h+var_C0]
0x18000d45e  mov     rdi, [rax]
0x18000d461  call    cs:__imp_SysAllocString
0x18000d467  mov     rbx, rax
0x18000d46a  test    rax, rax
0x18000d46d  jz      loc_18000D548
0x18000d473  mov     rcx, [rbp+47h+arg_28]
0x18000d477  lea     r8, [rbp+47h+var_80]
0x18000d47b  mov     rdx, rax
0x18000d47e  movaps  [rbp+47h+var_80], xmm6
0x18000d482  mov     rax, [rdi+20h]
0x18000d486  movsd   [rbp+47h+var_70], xmm7
0x18000d48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d490  mov     rcx, rbx; bstrString
0x18000d493  mov     edi, eax
0x18000d495  call    cs:__imp_SysFreeString
0x18000d49b  lea     rcx, [rsp+110h+var_D8+8]; pvarg
0x18000d4a0  call    cs:__imp_VariantClear
0x18000d4a6  test    edi, edi
0x18000d4a8  js      short loc_18000D4D0
0x18000d4aa  lea     rdx, [rbp+47h+arg_28]
0x18000d4ae  mov     [rsp+110h+var_E0], 0
0x18000d4b7  lea     rcx, [rsp+110h+var_E0]
0x18000d4bc  call    ??$MakeAndInitialize@VCUserData@@V1@AEAPEAUILogonUser@@@Details@WRL@Microsoft@@YAJPEAPEAVCUserData@@AEAPEAUILogonUser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CUserData,CUserData,ILogonUser * &>(CUserData * *,ILogonUser * &)
0x18000d4c1  mov     edi, eax
0x18000d4c3  test    eax, eax
0x18000d4c5  js      short loc_18000D4D0
0x18000d4c7  mov     rax, [rsp+110h+var_E0]
0x18000d4cc  mov     [r13+0], rax
0x18000d4d0  lea     rcx, [rbp+47h+var_B0]; pvarg
0x18000d4d4  call    cs:__imp_VariantClear
0x18000d4da  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000d4de  call    cs:__imp_VariantClear
0x18000d4e4  mov     rcx, [rbp+47h+arg_28]
0x18000d4e8  mov     [rbp+47h+arg_28], 0
0x18000d4f0  test    rcx, rcx
0x18000d4f3  jz      short loc_18000D501
0x18000d4f5  mov     rax, [rcx]
0x18000d4f8  mov     rax, [rax+10h]
0x18000d4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d501  mov     rax, [r15]
0x18000d504  mov     rcx, r15
0x18000d507  mov     rax, [rax+28h]
0x18000d50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d510  mov     rcx, [rbp+47h+ppwsz]; pv
0x18000d514  call    cs:__imp_CoTaskMemFree
0x18000d51a  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000d51e  call    cs:__imp_VariantClear
0x18000d524  lea     r11, [rsp+110h+var_38]
0x18000d52c  mov     eax, edi
0x18000d52e  movaps  xmm6, xmmword ptr [r11-18h]
0x18000d533  movaps  xmm7, xmmword ptr [r11-28h]
0x18000d538  mov     rsp, r11
0x18000d53b  pop     r15
0x18000d53d  pop     r14
0x18000d53f  pop     r13
0x18000d541  pop     r12
0x18000d543  pop     rdi
0x18000d544  pop     rsi
0x18000d545  pop     rbx
0x18000d546  pop     rbp
0x18000d547  retn
0x18000d548  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d54e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d554  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
