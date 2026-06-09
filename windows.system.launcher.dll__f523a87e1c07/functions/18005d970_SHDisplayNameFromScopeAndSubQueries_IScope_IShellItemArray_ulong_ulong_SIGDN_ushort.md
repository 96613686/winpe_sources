# SHDisplayNameFromScopeAndSubQueries(IScope *,IShellItemArray *,ulong,ulong,_SIGDN,ushort * *)

- ea: `0x18005d970`
- end: `0x18005dd06`
- name: `?SHDisplayNameFromScopeAndSubQueries@@YAJPEAUIScope@@PEAUIShellItemArray@@KKW4_SIGDN@@PEAPEAG@Z`
- size: `918`
- prototype: `__int64 __fastcall(struct IScope *, struct IShellItemArray *, unsigned int, unsigned int, enum _SIGDN, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005d85c`

## callees

- `0x18005d970`
- `0x18006f278`
- `0x180072074`
- `0x180072e74`
- `0x1800fd44c`
- `0x1800fda34`
- `0x1800fdb44`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005dcb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005dcb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005da9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dc0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005da9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dc0d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18005dcaa`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18005dcaa`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_DestroyCallback` at `0x18005dccb`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_DestroyCallback` at `0x18005dccb`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_Create` at `0x18005d9a0`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_Create` at `0x18005d9a0`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_GetPtr` at `0x18005dc52`
- `ext-ms-win-shell-comctl32-da-l1-1-0!DPA_GetPtr` at `0x18005dc52`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SHDisplayNameFromScopeAndSubQueries(
        struct IScope *a1,
        struct IShellItemArray *a2,
        unsigned int a3,
        unsigned int a4,
        enum _SIGDN a5,
        LPWSTR *ppwsz)
{
  __int64 v8; // rcx
  struct _DPA *v9; // rbx
  unsigned __int64 v10; // r13
  int appended; // edi
  WCHAR *v12; // r12
  unsigned int v13; // r14d
  struct IUnknown *v14; // rdx
  __int64 v15; // r8
  unsigned int i; // esi
  enum _SIGDN v17; // edx
  int v18; // esi
  int v19; // r14d
  const WCHAR *Ptr; // rax
  const unsigned __int16 *v21; // rdx
  HRESULT v22; // eax
  unsigned int v24; // [rsp+30h] [rbp-51h]
  LPVOID pv; // [rsp+48h] [rbp-39h] BYREF
  struct IScopeItem *v26; // [rsp+50h] [rbp-31h] BYREF
  struct _DPA *v27; // [rsp+58h] [rbp-29h] BYREF
  LPCWSTR psz; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int16 *v29; // [rsp+68h] [rbp-19h] BYREF
  unsigned __int64 v30; // [rsp+70h] [rbp-11h] BYREF
  struct _tagpropertykey v31; // [rsp+78h] [rbp-9h] BYREF
  unsigned int v32; // [rsp+E8h] [rbp+67h] BYREF
  unsigned int v33; // [rsp+F0h] [rbp+6Fh] BYREF

  v33 = a4;
  v32 = a3;
  v9 = DPA_Create(5);
  v27 = v9;
  if ( !v9 )
  {
    appended = -2147024882;
    goto LABEL_42;
  }
  psz = 0;
  v10 = 260;
  appended = _AllocArray<unsigned short,CTLocalAllocPolicy>(v8, 64, 260, &psz);
  if ( appended >= 0 )
  {
    v12 = (WCHAR *)psz;
    v29 = (unsigned __int16 *)psz;
    v30 = 260;
    if ( a2 )
    {
      v33 = 0;
      appended = ((__int64 (__fastcall *)(struct IShellItemArray *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v33);
      v13 = 0;
      if ( v33 )
      {
        while ( appended >= 0 )
        {
          v26 = 0;
          appended = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IScopeItem **))a2->lpVtbl->GetItemAt)(
                       a2,
                       v13,
                       &v26);
          if ( appended >= 0 )
          {
            pv = 0;
            appended = (*(__int64 (__fastcall **)(struct IScopeItem *, __int64, LPVOID *))(*(_QWORD *)v26 + 40LL))(
                         v26,
                         2147844096LL,
                         &pv);
            if ( appended >= 0 )
            {
              v32 = 4;
              if ( (int)SHMapUrlToZone((const unsigned __int16 *)pv, v14, v15, &v32) < 0
                || v32
                || (CoTaskMemFree(pv),
                    appended = (*(__int64 (__fastcall **)(struct IScopeItem *, _QWORD, LPVOID *))(*(_QWORD *)v26 + 40LL))(
                                 v26,
                                 0,
                                 &pv),
                    appended >= 0) )
              {
                appended = CDPA_Base<IFilterCondition,CTContainer_PolicyUnOwned<IFilterCondition>>::AppendPtr(&v27, pv);
                if ( appended < 0 )
                  CoTaskMemFree(pv);
              }
            }
            (*(void (__fastcall **)(struct IScopeItem *))(*(_QWORD *)v26 + 16LL))(v26);
          }
          if ( ++v13 >= v33 )
            goto LABEL_15;
        }
LABEL_29:
        v18 = 0;
        v19 = 0;
        while ( v18 < *(_DWORD *)v9 )
        {
          Ptr = (const WCHAR *)DPA_GetPtr(v9, v18);
          appended = _AppendNext(Ptr, v21, v29, v10, v19, v24, &v29, &v30);
          if ( appended >= 0 )
            v19 = 1;
          ++v18;
          v10 = v30;
        }
        if ( appended == -2147024774 )
        {
          appended = 1;
        }
        else if ( appended < 0 )
        {
LABEL_39:
          LocalFree(v12);
          goto LABEL_40;
        }
        v22 = SHStrDupW(v12, ppwsz);
        if ( v22 < 0 )
          appended = v22;
        goto LABEL_39;
      }
LABEL_15:
      if ( appended < 0 )
        goto LABEL_29;
    }
    if ( a1 )
    {
      pv = 0;
      appended = (*(__int64 (__fastcall **)(struct IScope *, _QWORD, GUID *, LPVOID *))(*(_QWORD *)a1 + 64LL))(
                   a1,
                   0,
                   &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                   &pv);
      if ( appended >= 0 )
      {
        v33 = 0;
        appended = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)pv + 24LL))(pv, &v33);
        for ( i = 0; appended >= 0; ++i )
        {
          if ( i >= v33 )
            break;
          v26 = 0;
          appended = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IScopeItem **))(*(_QWORD *)pv + 32LL))(
                       pv,
                       i,
                       &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                       &v26);
          if ( appended >= 0 )
          {
            v32 = 0;
            appended = (*(__int64 (__fastcall **)(struct IScopeItem *, unsigned int *))(*(_QWORD *)v26 + 32LL))(
                         v26,
                         &v32);
            if ( appended >= 0 && v32 == 1 )
            {
              psz = 0;
              memset(&v31, 0, sizeof(v31));
              appended = _GetScopeItemName(v26, v17, &v31, (unsigned __int16 **)&psz);
              if ( appended >= 0 )
              {
                appended = CDPA_Base<IFilterCondition,CTContainer_PolicyUnOwned<IFilterCondition>>::AppendPtr(&v27, psz);
                if ( appended < 0 )
                  CoTaskMemFree((LPVOID)psz);
              }
            }
            (*(void (__fastcall **)(struct IScopeItem *))(*(_QWORD *)v26 + 16LL))(v26);
          }
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      }
    }
    goto LABEL_29;
  }
LABEL_40:
  DPA_DestroyCallback(v9, (PFNDAENUMCALLBACK)DPA_CoTaskMemFreeCB<unsigned short>, 0);
  v27 = 0;
LABEL_42:
  CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::~CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>(&v27);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18005d970  mov     rax, rsp
0x18005d973  mov     [rax+8], rbx
0x18005d977  mov     [rax+20h], r9d
0x18005d97b  mov     [rax+18h], r8d
0x18005d97f  push    rbp
0x18005d980  push    rsi
0x18005d981  push    rdi
0x18005d982  push    r12
0x18005d984  push    r13
0x18005d986  push    r14
0x18005d988  push    r15
0x18005d98a  lea     rbp, [rax-4Fh]
0x18005d98e  sub     rsp, 90h
0x18005d995  mov     rsi, rdx
0x18005d998  mov     r15, rcx
0x18005d99b  mov     ecx, 5; cItemGrow
0x18005d9a0  call    cs:__imp_DPA_Create
0x18005d9a6  mov     rbx, rax
0x18005d9a9  mov     [rbp+47h+var_70], rax
0x18005d9ad  test    rax, rax
0x18005d9b0  jz      loc_18005DCDB
0x18005d9b6  mov     [rbp+47h+psz], 0
0x18005d9be  lea     r9, [rbp+47h+psz]
0x18005d9c2  mov     r13d, 104h
0x18005d9c8  mov     r8d, r13d
0x18005d9cb  mov     edx, 40h ; '@'
0x18005d9d0  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18005d9d5  mov     edi, eax
0x18005d9d7  test    eax, eax
0x18005d9d9  js      loc_18005DCBE
0x18005d9df  mov     r12, [rbp+47h+psz]
0x18005d9e3  mov     [rbp+47h+var_60], r12
0x18005d9e7  mov     [rbp+47h+var_58], r13
0x18005d9eb  mov     r14d, 1
0x18005d9f1  test    rsi, rsi
0x18005d9f4  jz      loc_18005DB06
0x18005d9fa  mov     [rbp+47h+arg_18], 0
0x18005da01  mov     rax, [rsi]
0x18005da04  lea     rdx, [rbp+47h+arg_18]
0x18005da08  mov     rcx, rsi
0x18005da0b  mov     rax, [rax+38h]
0x18005da0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da14  mov     edi, eax
0x18005da16  xor     r14d, r14d
0x18005da19  cmp     [rbp+47h+arg_18], r14d
0x18005da1d  jbe     loc_18005DAF8
0x18005da23  test    edi, edi
0x18005da25  js      loc_18005DC3E
0x18005da2b  mov     [rbp+47h+var_78], 0
0x18005da33  mov     rax, [rsi]
0x18005da36  lea     r8, [rbp+47h+var_78]
0x18005da3a  mov     edx, r14d
0x18005da3d  mov     rcx, rsi
0x18005da40  mov     rax, [rax+40h]
0x18005da44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da49  mov     edi, eax
0x18005da4b  test    eax, eax
0x18005da4d  js      loc_18005DAEB
0x18005da53  mov     [rbp+47h+pv], 0
0x18005da5b  mov     rcx, [rbp+47h+var_78]
0x18005da5f  mov     rax, [rcx]
0x18005da62  lea     r8, [rbp+47h+pv]
0x18005da66  mov     edx, 80058000h
0x18005da6b  mov     rax, [rax+28h]
0x18005da6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da74  mov     edi, eax
0x18005da76  test    eax, eax
0x18005da78  js      short loc_18005DADB
0x18005da7a  mov     [rbp+47h+arg_10], 4
0x18005da81  lea     r9, [rbp+47h+arg_10]; unsigned int *
0x18005da85  mov     rcx, [rbp+47h+pv]; unsigned __int16 *
0x18005da89  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x18005da8e  test    eax, eax
0x18005da90  js      short loc_18005DABE
0x18005da92  cmp     [rbp+47h+arg_10], 0
0x18005da96  jnz     short loc_18005DABE
0x18005da98  mov     rcx, [rbp+47h+pv]; pv
0x18005da9c  call    cs:__imp_CoTaskMemFree
0x18005daa2  mov     rcx, [rbp+47h+var_78]
0x18005daa6  mov     rax, [rcx]
0x18005daa9  lea     r8, [rbp+47h+pv]
0x18005daad  xor     edx, edx
0x18005daaf  mov     rax, [rax+28h]
0x18005dab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dab8  mov     edi, eax
0x18005daba  test    eax, eax
0x18005dabc  js      short loc_18005DADB
0x18005dabe  mov     rdx, [rbp+47h+pv]
0x18005dac2  lea     rcx, [rbp+47h+var_70]
0x18005dac6  call    ?AppendPtr@?$CDPA_Base@UIFilterCondition@@V?$CTContainer_PolicyUnOwned@UIFilterCondition@@@@@@QEAAJPEAUIFilterCondition@@PEAH@Z; CDPA_Base<IFilterCondition,CTContainer_PolicyUnOwned<IFilterCondition>>::AppendPtr(IFilterCondition *,int *)
0x18005dacb  mov     edi, eax
0x18005dacd  test    eax, eax
0x18005dacf  jns     short loc_18005DADB
0x18005dad1  mov     rcx, [rbp+47h+pv]; pv
0x18005dad5  call    cs:__imp_CoTaskMemFree
0x18005dadb  mov     rcx, [rbp+47h+var_78]
0x18005dadf  mov     rax, [rcx]
0x18005dae2  mov     rax, [rax+10h]
0x18005dae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005daeb  inc     r14d
0x18005daee  cmp     r14d, [rbp+47h+arg_18]
0x18005daf2  jb      loc_18005DA23
0x18005daf8  test    edi, edi
0x18005dafa  js      loc_18005DC3E
0x18005db00  mov     r14d, 1
0x18005db06  test    r15, r15
0x18005db09  jz      loc_18005DC3E
0x18005db0f  mov     [rbp+47h+pv], 0
0x18005db17  mov     rax, [r15]
0x18005db1a  lea     r9, [rbp+47h+pv]
0x18005db1e  lea     r8, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x18005db25  xor     edx, edx
0x18005db27  mov     rcx, r15
0x18005db2a  mov     rax, [rax+40h]
0x18005db2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db33  mov     edi, eax
0x18005db35  test    eax, eax
0x18005db37  js      loc_18005DC3E
0x18005db3d  mov     [rbp+47h+arg_18], 0
0x18005db44  mov     rcx, [rbp+47h+pv]
0x18005db48  mov     rax, [rcx]
0x18005db4b  lea     rdx, [rbp+47h+arg_18]
0x18005db4f  mov     rax, [rax+18h]
0x18005db53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db58  mov     edi, eax
0x18005db5a  xor     esi, esi
0x18005db5c  test    eax, eax
0x18005db5e  js      loc_18005DC2E
0x18005db64  cmp     esi, [rbp+47h+arg_18]
0x18005db67  jnb     loc_18005DC2E
0x18005db6d  mov     [rbp+47h+var_78], 0
0x18005db75  mov     rcx, [rbp+47h+pv]
0x18005db79  mov     rax, [rcx]
0x18005db7c  lea     r9, [rbp+47h+var_78]
0x18005db80  lea     r8, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18005db87  mov     edx, esi
0x18005db89  mov     rax, [rax+20h]
0x18005db8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db92  mov     edi, eax
0x18005db94  test    eax, eax
0x18005db96  js      loc_18005DC23
0x18005db9c  mov     [rbp+47h+arg_10], 0
0x18005dba3  mov     rcx, [rbp+47h+var_78]
0x18005dba7  mov     rax, [rcx]
0x18005dbaa  lea     rdx, [rbp+47h+arg_10]
0x18005dbae  mov     rax, [rax+20h]
0x18005dbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dbb7  mov     edi, eax
0x18005dbb9  test    eax, eax
0x18005dbbb  js      short loc_18005DC13
0x18005dbbd  cmp     [rbp+47h+arg_10], r14d
0x18005dbc1  jnz     short loc_18005DC13
0x18005dbc3  mov     [rbp+47h+psz], 0
0x18005dbcb  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x18005dbd2  movaps  xmmword ptr [rbp+47h+var_50.fmtid.Data1], xmm0
0x18005dbd6  mov     eax, cs:PKEY_Null.pid
0x18005dbdc  mov     [rbp+47h+var_50.pid], eax
0x18005dbdf  lea     r9, [rbp+47h+psz]; unsigned __int16 **
0x18005dbe3  lea     r8, [rbp+47h+var_50]; struct _tagpropertykey
0x18005dbe7  mov     rcx, [rbp+47h+var_78]; struct IScopeItem *
0x18005dbeb  call    ?_GetScopeItemName@@YAJPEAUIScopeItem@@W4_SIGDN@@U_tagpropertykey@@PEAPEAG@Z; _GetScopeItemName(IScopeItem *,_SIGDN,_tagpropertykey,ushort * *)
0x18005dbf0  mov     edi, eax
0x18005dbf2  test    eax, eax
0x18005dbf4  js      short loc_18005DC13
0x18005dbf6  mov     rdx, [rbp+47h+psz]
0x18005dbfa  lea     rcx, [rbp+47h+var_70]
0x18005dbfe  call    ?AppendPtr@?$CDPA_Base@UIFilterCondition@@V?$CTContainer_PolicyUnOwned@UIFilterCondition@@@@@@QEAAJPEAUIFilterCondition@@PEAH@Z; CDPA_Base<IFilterCondition,CTContainer_PolicyUnOwned<IFilterCondition>>::AppendPtr(IFilterCondition *,int *)
0x18005dc03  mov     edi, eax
0x18005dc05  test    eax, eax
0x18005dc07  jns     short loc_18005DC13
0x18005dc09  mov     rcx, [rbp+47h+psz]; pv
0x18005dc0d  call    cs:__imp_CoTaskMemFree
0x18005dc13  mov     rcx, [rbp+47h+var_78]
0x18005dc17  mov     rax, [rcx]
0x18005dc1a  mov     rax, [rax+10h]
0x18005dc1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc23  add     esi, r14d
0x18005dc26  test    edi, edi
0x18005dc28  jns     loc_18005DB64
0x18005dc2e  mov     rcx, [rbp+47h+pv]
0x18005dc32  mov     rax, [rcx]
0x18005dc35  mov     rax, [rax+10h]
0x18005dc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc3e  xor     esi, esi
0x18005dc40  mov     r14d, esi
0x18005dc43  lea     ecx, [rsi+1]
0x18005dc46  mov     eax, edi
0x18005dc48  cmp     esi, [rbx]
0x18005dc4a  jge     short loc_18005DC93
0x18005dc4c  movsxd  rdx, esi; i
0x18005dc4f  mov     rcx, rbx; hdpa
0x18005dc52  call    cs:__imp_DPA_GetPtr
0x18005dc58  lea     rcx, [rbp+47h+var_58]
0x18005dc5c  mov     [rsp+38h], rcx; unsigned __int64 *
0x18005dc61  lea     rcx, [rbp+47h+var_60]
0x18005dc65  mov     [rsp+0C0h+var_90], rcx; unsigned __int16 **
0x18005dc6a  mov     [rsp+20h], r14d; int
0x18005dc6f  mov     r9, r13; unsigned __int64
0x18005dc72  mov     r8, [rbp+47h+var_60]; unsigned __int16 *
0x18005dc76  mov     rcx, rax; pszSrc
0x18005dc79  call    ?_AppendNext@@YAJPEBG0PEAG_KHKPEAPEAGPEA_K@Z; _AppendNext(ushort const *,ushort const *,ushort *,unsigned __int64,int,ulong,ushort * *,unsigned __int64 *)
0x18005dc7e  mov     edi, eax
0x18005dc80  test    eax, eax
0x18005dc82  mov     ecx, 1
0x18005dc87  cmovns  r14d, ecx
0x18005dc8b  add     esi, ecx
0x18005dc8d  mov     r13, [rbp+47h+var_58]
0x18005dc91  jmp     short loc_18005DC46
0x18005dc93  cmp     edi, 8007007Ah
0x18005dc99  jnz     short loc_18005DC9F
0x18005dc9b  mov     edi, ecx
0x18005dc9d  jmp     short loc_18005DCA3
0x18005dc9f  test    eax, eax
0x18005dca1  js      short loc_18005DCB5
0x18005dca3  mov     rdx, [rbp+47h+ppwsz]; ppwsz
0x18005dca7  mov     rcx, r12; psz
0x18005dcaa  call    cs:__imp_SHStrDupW
0x18005dcb0  test    eax, eax
0x18005dcb2  cmovs   edi, eax
0x18005dcb5  mov     rcx, r12; hMem
0x18005dcb8  call    cs:__imp_LocalFree
0x18005dcbe  xor     r8d, r8d; pData
0x18005dcc1  lea     rdx, ??$DPA_CoTaskMemFreeCB@G@@YAHPEAGPEAX@Z; pfnCB
0x18005dcc8  mov     rcx, rbx; hdpa
0x18005dccb  call    cs:__imp_DPA_DestroyCallback
0x18005dcd1  mov     [rbp+47h+var_70], 0
0x18005dcd9  jmp     short loc_18005DCE0
0x18005dcdb  mov     edi, 8007000Eh
0x18005dce0  lea     rcx, [rbp+47h+var_70]
0x18005dce4  call    ??1?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAA@XZ; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::~CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>(void)
0x18005dce9  mov     eax, edi
0x18005dceb  mov     rbx, [rsp+0C0h+arg_0]
0x18005dcf3  add     rsp, 90h
0x18005dcfa  pop     r15
0x18005dcfc  pop     r14
0x18005dcfe  pop     r13
0x18005dd00  pop     r12
0x18005dd02  pop     rdi
0x18005dd03  pop     rsi
0x18005dd04  pop     rbp
0x18005dd05  retn
```
