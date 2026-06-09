# CMDEContentServer::ProfileMatchesMIME(MDEProfile const *,ushort const *)

- ea: `0x14001d520`
- end: `0x14001df93`
- name: `?ProfileMatchesMIME@CMDEContentServer@@CAHPEBUMDEProfile@@PEBG@Z`
- size: `2675`
- prototype: `__int64 __fastcall(const struct MDEProfile *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140004160`
- `0x14001b850`
- `0x14001d020`

## callees

- `0x140014f90`
- `0x140019540`
- `0x14001d520`
- `0x140027620`
- `0x1400395c0`
- `0x1400396dc`
- `0x14003e5f4`
- `0x14003f17c`
- `0x140046c32`
- `0x140046d00`
- `0x140047798`
- `0x1400549e0`
- `0x14009ad10`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14001d97a`
- `KERNEL32!CompareStringW` at `0x14001d9a2`
- `KERNEL32!CompareStringW` at `0x14001d9d3`
- `KERNEL32!CompareStringW` at `0x14001d9fd`
- `KERNEL32!CompareStringW` at `0x14001d97a`
- `KERNEL32!CompareStringW` at `0x14001d9a2`
- `KERNEL32!CompareStringW` at `0x14001d9d3`
- `KERNEL32!CompareStringW` at `0x14001d9fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001dcc8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001ddeb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001de84`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001deae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001df20`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001dcc8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001ddeb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001de84`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001deae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001df20`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::ProfileMatchesMIME(const struct MDEProfile *a1, const unsigned __int16 *a2)
{
  const WCHAR *lpString2; // r14
  PVOID *v4; // rcx
  __int64 v5; // r9
  _WORD **v6; // rdi
  bool v7; // zf
  _WORD *v8; // r15
  unsigned int v9; // r12d
  __int64 v10; // r10
  unsigned __int64 v11; // r9
  __int16 v12; // dx
  int v13; // ebp
  _WORD *i; // r8
  const wchar_t *j; // rax
  unsigned __int16 *v16; // r8
  __int64 v17; // rdx
  int jj; // ebx
  const wchar_t *kk; // rcx
  int v20; // edi
  int v21; // ecx
  int v22; // r14d
  _WORD *v23; // rsi
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, __int64); // rax
  WCHAR *v25; // rsi
  __int64 v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, __int64); // rcx
  const void *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  size_t v32; // r8
  int v33; // r13d
  PVOID *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, __int64); // rcx
  unsigned __int16 *v38; // r8
  __int64 k; // r9
  const void *v40; // rbp
  __int64 v41; // rax
  char *v42; // rbx
  size_t v43; // r8
  volatile signed __int32 *v44; // r14
  volatile signed __int32 *v45; // r15
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, __int64); // rax
  _WORD *v47; // rbp
  __int64 v48; // r11
  __int16 *v49; // r8
  unsigned __int64 v50; // r10
  __int16 v51; // dx
  int v52; // ebx
  const wchar_t *m; // rcx
  int n; // r15d
  const wchar_t *ii; // rcx
  int v56; // r14d
  int v57; // ecx
  int v58; // ebx
  int v59; // edi
  char *v60; // rbx
  __int64 (__fastcall ***v61)(_QWORD, _QWORD, __int64); // rax
  size_t v63; // r8
  void *v64; // rcx
  size_t v65; // r8
  void *v66; // rcx
  size_t v67; // r8
  void *v68; // rcx
  _DWORD *v69; // rdi
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 Manager; // rax
  _DWORD *v73; // rdi
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 v79; // rax
  _DWORD *v80; // rsi
  __int64 v81; // rax
  __int64 v82; // rdx
  WCHAR *v83; // [rsp+80h] [rbp+8h] BYREF
  PCNZWCH v84; // [rsp+88h] [rbp+10h]
  _QWORD *v85; // [rsp+90h] [rbp+18h]
  char *v86; // [rsp+98h] [rbp+20h] BYREF

  v84 = a2;
  lpString2 = a2;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      92,
      (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (_DWORD)a1,
      (__int64)a2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *((_QWORD *)a1 + 3);
  v6 = (_WORD **)((char *)a1 + 24);
  v7 = *(_DWORD *)(v5 - 16) == 0;
  v85 = (_QWORD *)((char *)a1 + 24);
  if ( !v7 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      WPP_SF_S(v4[2], 93, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, v5);
    v8 = *v6;
    v9 = 0;
    v10 = *((int *)*v6 - 4);
    v11 = (unsigned __int64)&(*v6)[v10];
    if ( (unsigned __int64)*v6 >= v11 )
      goto LABEL_153;
    v12 = *v8;
    v13 = 0;
    for ( i = *v6; v12; ++v13 )
    {
      for ( j = L";"; *j; ++j )
      {
        if ( *j == v12 )
          goto LABEL_34;
      }
      if ( v12 )
        break;
LABEL_34:
      v12 = i[1];
      ++i;
    }
    v16 = &v8[v13];
    if ( (unsigned __int64)v16 >= v11 )
    {
LABEL_153:
      v33 = -1;
      Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::GetManager((char *)a1 + 24);
      ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v83, Manager);
      v25 = v83;
LABEL_47:
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_74;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids);
      while ( 1 )
      {
        v34 = (PVOID *)WPP_GLOBAL_Control;
LABEL_74:
        if ( !*((_DWORD *)v25 - 4) )
        {
LABEL_112:
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v25 - 3) + 8LL))(*((_QWORD *)v25 - 3));
          v4 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_115;
        }
        if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 2) != 0 && *((_BYTE *)v34 + 25) >= 5u )
          WPP_SF_S(v34[2], 95, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, v25);
        if ( CompareStringW(0x7Fu, 1u, v25, -1, L"application/octet-stream", -1) == 2
          || CompareStringW(0x7Fu, 1u, v25, -1, lpString2, -1) == 2
          || CompareStringW(0x7Fu, 1u, &v25[*((int *)v25 - 4) - 2], -1, L"/*", -1) == 2
          && CompareStringW(0x7Fu, 1u, v25, *((_DWORD *)v25 - 4) - 2, lpString2, *((_DWORD *)v25 - 4) - 2) == 2 )
        {
          v9 = 1;
          goto LABEL_112;
        }
        if ( v33 < 0 )
          goto LABEL_119;
        v47 = *v6;
        v48 = *((int *)*v6 - 4);
        v49 = &(*v6)[v33];
        v50 = (unsigned __int64)&(*v6)[v48];
        if ( (unsigned __int64)v49 < v50 )
        {
          v51 = *v49;
          v52 = 0;
          for ( k = (__int64)&(*v6)[v33]; v51; ++v52 )
          {
            for ( m = L";"; *m; ++m )
            {
              if ( *m == v51 )
                goto LABEL_117;
            }
            if ( v51 )
              break;
LABEL_117:
            v51 = *(_WORD *)(k + 2);
            k += 2;
          }
          v38 = (unsigned __int16 *)&v49[v52];
          if ( (unsigned __int64)v38 < v50 )
            break;
        }
        v33 = -1;
        v79 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::GetManager(v6);
        ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v86, v79);
        v42 = v86;
LABEL_61:
        v44 = (volatile signed __int32 *)(v42 - 24);
        v45 = (volatile signed __int32 *)(v25 - 12);
        if ( v42 - 24 == (char *)(v25 - 12) )
          goto LABEL_70;
        if ( *((int *)v45 + 4) < 0 || *(_QWORD *)v44 != *(_QWORD *)v45 )
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v83, v42, *((unsigned int *)v42 - 4));
          v25 = v83;
          goto LABEL_70;
        }
        v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 32LL))(*(_QWORD *)v44);
        if ( *((int *)v44 + 4) >= 0 && v46 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v44 )
        {
          _InterlockedIncrement(v44 + 4);
        }
        else
        {
          v80 = v44 + 2;
          v81 = (**v46)(v46, *((unsigned int *)v44 + 2), 2);
          v44 = (volatile signed __int32 *)v81;
          if ( !v81 )
            goto LABEL_148;
          *(_DWORD *)(v81 + 8) = *v80;
          v67 = 2LL * (*v80 + 1);
          if ( !v67 )
            goto LABEL_67;
          v68 = (void *)(v81 + 24);
          if ( v81 == -24 )
            goto LABEL_167;
          if ( !v42 )
          {
            memset_0(v68, 0, v67);
LABEL_167:
            *(_DWORD *)_o__errno(v68, v82, v67) = 22;
            invalid_parameter_noinfo();
            goto LABEL_67;
          }
          memcpy_0(v68, v42, v67);
        }
LABEL_67:
        if ( _InterlockedExchangeAdd(v45 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v45 + 8LL))(*(_QWORD *)v45, v45);
        v25 = (WCHAR *)(v44 + 6);
        v83 = (WCHAR *)(v44 + 6);
LABEL_70:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v42 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v42 - 3) + 8LL))(*((_QWORD *)v42 - 3));
        v6 = (_WORD **)v85;
        lpString2 = v84;
      }
      v36 = *v38;
      for ( n = 0; (_WORD)v36; ++n )
      {
        for ( ii = L";"; *ii; ++ii )
        {
          if ( *ii == (_WORD)v36 )
            goto LABEL_96;
        }
        v36 = v38[1];
        ++v38;
      }
LABEL_96:
      v56 = v52 + v33;
      v57 = 0;
      v58 = 0;
      if ( v56 >= 0 )
        v58 = v56;
      if ( n >= 0 )
        v57 = n;
      if ( 0x7FFFFFFF - v58 < v57 )
        goto LABEL_119;
      if ( v57 + v58 > (int)v48 )
        v57 = v48 - v58;
      v59 = 0;
      if ( v58 <= (int)v48 )
        v59 = v57;
      if ( v58 || v59 != (_DWORD)v48 )
      {
        v35 = *((_QWORD *)v47 - 3);
        if ( !v35
          || (v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 32LL))(v35)) == 0 )
        {
          v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))((__int64 (__fastcall *)(void ***, __int64, unsigned __int16 *, __int64))ATL::g_strmgr[4])(
                                                                     &ATL::g_strmgr,
                                                                     v36,
                                                                     v38,
                                                                     k);
          if ( !v37 )
            goto LABEL_128;
        }
        v40 = (const void *)(*v85 + 2LL * v58);
        if ( !v40 && v59 )
          goto LABEL_119;
        v41 = (**v37)(v37, (unsigned int)v59, 2);
        if ( !v41 )
          goto LABEL_148;
        v42 = (char *)(v41 + 24);
        v86 = (char *)(v41 + 24);
        if ( v59 < 0 || v59 > *(_DWORD *)(v41 + 12) )
          goto LABEL_119;
        *(_DWORD *)(v41 + 8) = v59;
        v43 = 2LL * v59;
        *(_WORD *)&v42[v43] = 0;
        if ( v43 )
        {
          if ( v40 )
          {
            memcpy_0(v42, v40, v43);
          }
          else
          {
            memset_0(v42, 0, v43);
            *(_DWORD *)_o__errno(v77, v76, v78) = 22;
            invalid_parameter_noinfo();
          }
        }
        goto LABEL_60;
      }
      v60 = (char *)(v47 - 12);
      v61 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *, __int64))(**((_QWORD **)v47 - 3) + 32LL))(
                                                                 *((_QWORD *)v47 - 3),
                                                                 v36,
                                                                 v38,
                                                                 k);
      if ( *((int *)v47 - 2) >= 0 && v61 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v60 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v47 - 2);
      }
      else
      {
        v73 = v60 + 8;
        v74 = (**v61)(v61, *((unsigned int *)v60 + 2), 2);
        v60 = (char *)v74;
        if ( !v74 )
          goto LABEL_148;
        *(_DWORD *)(v74 + 8) = *v73;
        v65 = 2LL * (*v73 + 1);
        if ( v65 )
        {
          v66 = (void *)(v74 + 24);
          if ( v74 != -24 )
          {
            if ( v47 )
            {
              memcpy_0(v66, v47, v65);
              v42 = v60 + 24;
              v86 = v42;
              goto LABEL_60;
            }
            memset_0(v66, 0, v65);
          }
          *(_DWORD *)_o__errno(v66, v75, v65) = 22;
          invalid_parameter_noinfo();
        }
      }
      v42 = v60 + 24;
      v86 = v42;
LABEL_60:
      v33 = v56 + n + 1;
      goto LABEL_61;
    }
    v17 = *v16;
    for ( jj = 0; (_WORD)v17; ++jj )
    {
      for ( kk = L";"; *kk; ++kk )
      {
        if ( *kk == (_WORD)v17 )
          goto LABEL_19;
      }
      v17 = v16[1];
      ++v16;
    }
LABEL_19:
    v20 = 0;
    v21 = 0;
    if ( v13 >= 0 )
      v20 = v13;
    if ( jj >= 0 )
      v21 = jj;
    if ( 0x7FFFFFFF - v20 >= v21 )
    {
      if ( v21 + v20 > (int)v10 )
        v21 = v10 - v20;
      v22 = 0;
      if ( v20 <= (int)v10 )
        v22 = v21;
      if ( !v20 && v22 == (_DWORD)v10 )
      {
        v23 = v8 - 12;
        v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**((_QWORD **)v8 - 3) + 32LL))(
                                                                   *((_QWORD *)v8 - 3),
                                                                   v17,
                                                                   v16);
        if ( *((int *)v8 - 2) >= 0 && v24 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v23 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v23 + 4);
LABEL_33:
          v25 = v23 + 12;
          v83 = v25;
          goto LABEL_46;
        }
        v69 = v23 + 4;
        v70 = (**v24)(v24, *((unsigned int *)v23 + 2), 2);
        v23 = (_WORD *)v70;
        if ( v70 )
        {
          *(_DWORD *)(v70 + 8) = *v69;
          v63 = 2LL * (*v69 + 1);
          if ( v63 )
          {
            v64 = (void *)(v70 + 24);
            if ( v70 == -24 )
            {
              *(_DWORD *)_o__errno(v64, v71, v63) = 22;
              invalid_parameter_noinfo();
              v25 = v23 + 12;
              v83 = v25;
              goto LABEL_46;
            }
            memcpy_0(v64, v8, v63);
          }
          goto LABEL_33;
        }
LABEL_148:
        ATL::CSimpleStringT<char,0>::ThrowMemoryException();
      }
      v26 = *((_QWORD *)v8 - 3);
      if ( !v26
        || (v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v26 + 32LL))(
                                                                       v26,
                                                                       v17,
                                                                       v16)) == 0 )
      {
        v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))((__int64 (__fastcall *)(void ***, __int64, unsigned __int16 *))ATL::g_strmgr[4])(
                                                                   &ATL::g_strmgr,
                                                                   v17,
                                                                   v16);
        if ( !v27 )
LABEL_128:
          ATL::AtlThrowImpl(-2147467259);
      }
      v28 = (const void *)(*v85 + 2LL * v20);
      if ( v28 || !v22 )
      {
        v29 = (**v27)(v27, (unsigned int)v22, 2);
        if ( !v29 )
          goto LABEL_148;
        v25 = (WCHAR *)(v29 + 24);
        v83 = (WCHAR *)(v29 + 24);
        if ( v22 >= 0 && v22 <= *(_DWORD *)(v29 + 12) )
        {
          *(_DWORD *)(v29 + 8) = v22;
          v32 = 2LL * v22;
          v25[v32 / 2] = 0;
          if ( v32 )
          {
            if ( v29 != -24 )
            {
              if ( v28 )
              {
                memcpy_0(v25, v28, v32);
                goto LABEL_46;
              }
              memset_0(v25, 0, v32);
            }
            *(_DWORD *)_o__errno(v31, v30, v32) = 22;
            invalid_parameter_noinfo();
          }
LABEL_46:
          v6 = (_WORD **)v85;
          lpString2 = v84;
          v33 = jj + v13 + 1;
          goto LABEL_47;
        }
      }
    }
LABEL_119:
    ATL::AtlThrowImpl(-2147024809);
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    WPP_SF_(v4[2], 96, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = 1;
LABEL_115:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_d(v4[2], 97, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x14001d520  mov     [rsp+arg_8], rdx
0x14001d525  push    rbx
0x14001d526  push    rdi
0x14001d527  push    r14
0x14001d529  sub     rsp, 60h
0x14001d52d  mov     r14, rdx
0x14001d530  mov     rbx, rcx
0x14001d533  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d53a  lea     rax, WPP_GLOBAL_Control
0x14001d541  cmp     rcx, rax
0x14001d544  jz      short loc_14001D550
0x14001d546  test    byte ptr [rcx+1Ch], 1
0x14001d54a  jnz     loc_14001DD73
0x14001d550  mov     r9, [rbx+18h]
0x14001d554  lea     rdi, [rbx+18h]
0x14001d558  mov     [rsp+78h+var_20], rbp
0x14001d55d  mov     [rsp+78h+var_28], rsi
0x14001d562  mov     [rsp+78h+var_30], r12
0x14001d567  cmp     dword ptr [r9-10h], 0
0x14001d56c  mov     [rsp+78h+var_38], r13
0x14001d571  mov     [rsp+78h+var_40], r15
0x14001d576  mov     [rsp+78h+arg_10], rdi
0x14001d57e  jz      loc_14001DC96
0x14001d584  cmp     rcx, rax
0x14001d587  jnz     loc_14001DBDC
0x14001d58d  mov     r15, [rdi]
0x14001d590  xor     r12d, r12d
0x14001d593  mov     ebp, 0FFFFFFFFh
0x14001d598  movsxd  r10, dword ptr [r15-10h]
0x14001d59c  lea     r9, [r15+r10*2]
0x14001d5a0  cmp     r15, r9
0x14001d5a3  jnb     loc_14001DE06
0x14001d5a9  movzx   edx, word ptr [r15]
0x14001d5ad  mov     ebp, r12d
0x14001d5b0  mov     r8, r15
0x14001d5b3  test    dx, dx
0x14001d5b6  jz      short loc_14001D5E0
0x14001d5b8  lea     rax, asc_1400A3EB0; ";"
0x14001d5bf  movzx   ecx, word ptr [rax]
0x14001d5c2  test    cx, cx
0x14001d5c5  jz      short loc_14001D5D6
0x14001d5c7  cmp     cx, dx
0x14001d5ca  jz      loc_14001D6AE
0x14001d5d0  add     rax, 2
0x14001d5d4  jmp     short loc_14001D5BF
0x14001d5d6  cmp     r12w, dx
0x14001d5da  jz      loc_14001D6AE
0x14001d5e0  movsxd  rax, ebp
0x14001d5e3  lea     r8, [r15+rax*2]
0x14001d5e7  cmp     r8, r9
0x14001d5ea  jnb     loc_14001DE01
0x14001d5f0  movzx   edx, word ptr [r8]
0x14001d5f4  mov     ebx, r12d
0x14001d5f7  test    dx, dx
0x14001d5fa  jz      short loc_14001D62C
0x14001d5fc  lea     rcx, asc_1400A3EB0; ";"
0x14001d603  movzx   eax, word ptr [rcx]
0x14001d606  test    ax, ax
0x14001d609  jz      short loc_14001D616
0x14001d60b  cmp     ax, dx
0x14001d60e  jz      short loc_14001D62C
0x14001d610  add     rcx, 2
0x14001d614  jmp     short loc_14001D603
0x14001d616  cmp     r12w, dx
0x14001d61a  jz      short loc_14001D62C
0x14001d61c  movzx   edx, word ptr [r8+2]
0x14001d621  add     r8, 2
0x14001d625  inc     ebx
0x14001d627  test    dx, dx
0x14001d62a  jnz     short loc_14001D5FC
0x14001d62c  test    ebp, ebp
0x14001d62e  mov     edi, r12d
0x14001d631  mov     ecx, r12d
0x14001d634  mov     eax, 7FFFFFFFh
0x14001d639  cmovns  edi, ebp
0x14001d63c  test    ebx, ebx
0x14001d63e  cmovns  ecx, ebx
0x14001d641  sub     eax, edi
0x14001d643  cmp     eax, ecx
0x14001d645  jl      loc_14001DBD1
0x14001d64b  lea     eax, [rcx+rdi]
0x14001d64e  cmp     eax, r10d
0x14001d651  jle     short loc_14001D658
0x14001d653  mov     ecx, r10d
0x14001d656  sub     ecx, edi
0x14001d658  cmp     edi, r10d
0x14001d65b  mov     r14d, r12d
0x14001d65e  cmovle  r14d, ecx
0x14001d662  test    edi, edi
0x14001d664  jnz     short loc_14001D6C7
0x14001d666  lea     eax, [r14+rdi]
0x14001d66a  cmp     eax, r10d
0x14001d66d  jnz     short loc_14001D6C7
0x14001d66f  mov     rcx, [r15-18h]
0x14001d673  lea     rsi, [r15-18h]
0x14001d677  mov     rax, [rcx]
0x14001d67a  mov     rax, [rax+20h]
0x14001d67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d683  mov     rcx, rax
0x14001d686  cmp     [rsi+10h], r12d
0x14001d68a  jl      loc_14001DDAD
0x14001d690  cmp     rax, [rsi]
0x14001d693  jnz     loc_14001DDAD
0x14001d699  lock inc dword ptr [rsi+10h]
0x14001d69d  add     rsi, 18h
0x14001d6a1  mov     [rsp+78h+arg_0], rsi
0x14001d6a9  jmp     loc_14001D775
0x14001d6ae  movzx   edx, word ptr [r8+2]
0x14001d6b3  add     r8, 2
0x14001d6b7  inc     ebp
0x14001d6b9  test    dx, dx
0x14001d6bc  jz      loc_14001D5E0
0x14001d6c2  jmp     loc_14001D5B8
0x14001d6c7  mov     rcx, [r15-18h]
0x14001d6cb  test    rcx, rcx
0x14001d6ce  jz      loc_14001DC71
0x14001d6d4  mov     rax, [rcx]
0x14001d6d7  mov     rax, [rax+20h]
0x14001d6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d6e0  mov     rcx, rax
0x14001d6e3  test    rax, rax
0x14001d6e6  jz      loc_14001DC71
0x14001d6ec  mov     rax, [rsp+78h+arg_10]
0x14001d6f4  movsxd  rdx, edi
0x14001d6f7  mov     rax, [rax]
0x14001d6fa  lea     rdi, [rax+rdx*2]
0x14001d6fe  test    rdi, rdi
0x14001d701  jz      loc_14001DDD6
0x14001d707  mov     rax, [rcx]
0x14001d70a  mov     r8d, 2
0x14001d710  mov     edx, r14d
0x14001d713  mov     rax, [rax]
0x14001d716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d71b  test    rax, rax
0x14001d71e  jz      loc_14001DDD0
0x14001d724  lea     rsi, [rax+18h]
0x14001d728  mov     [rsp+78h+arg_0], rsi
0x14001d730  test    r14d, r14d
0x14001d733  js      loc_14001DBD1
0x14001d739  cmp     r14d, [rsi-0Ch]
0x14001d73d  jg      loc_14001DBD1
0x14001d743  movsxd  rax, r14d
0x14001d746  mov     [rsi-10h], r14d
0x14001d74a  lea     r8, [rax+rax]; Size
0x14001d74e  mov     [rsi+r8], r12w
0x14001d753  test    r8, r8
0x14001d756  jz      short loc_14001D775
0x14001d758  test    rsi, rsi
0x14001d75b  jz      loc_14001DDEB
0x14001d761  mov     rcx, rsi; void *
0x14001d764  test    rdi, rdi
0x14001d767  jz      loc_14001DDE4
0x14001d76d  mov     rdx, rdi; Src
0x14001d770  call    memcpy_0
0x14001d775  mov     rdi, [rsp+78h+arg_10]
0x14001d77d  lea     r13d, [rbp+1]
0x14001d781  mov     r14, [rsp+78h+arg_8]
0x14001d789  add     r13d, ebx
0x14001d78c  mov     ebp, 0FFFFFFFFh
0x14001d791  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d798  lea     rax, WPP_GLOBAL_Control
0x14001d79f  cmp     rcx, rax
0x14001d7a2  jz      loc_14001D93A
0x14001d7a8  test    byte ptr [rcx+1Ch], 2
0x14001d7ac  jz      loc_14001D93A
0x14001d7b2  cmp     byte ptr [rcx+19h], 5
0x14001d7b6  jb      loc_14001D93A
0x14001d7bc  mov     rcx, [rcx+10h]
0x14001d7c0  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14001d7c7  mov     edx, 5Eh ; '^'
0x14001d7cc  call    WPP_SF_
0x14001d7d1  jmp     loc_14001D92C
0x14001d7d6  mov     rcx, [rbp-18h]
0x14001d7da  test    rcx, rcx
0x14001d7dd  jz      loc_14001DC43
0x14001d7e3  mov     rax, [rcx]
0x14001d7e6  mov     rax, [rax+20h]
0x14001d7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d7ef  mov     rcx, rax
0x14001d7f2  test    rax, rax
0x14001d7f5  jz      loc_14001DC43
0x14001d7fb  mov     rax, [rsp+78h+arg_10]
0x14001d803  movsxd  rdx, ebx
0x14001d806  mov     rax, [rax]
0x14001d809  lea     rbp, [rax+rdx*2]
0x14001d80d  test    rbp, rbp
0x14001d810  jz      loc_14001DE9A
0x14001d816  mov     rax, [rcx]
0x14001d819  mov     r8d, 2
0x14001d81f  mov     edx, edi
0x14001d821  mov     rax, [rax]
0x14001d824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d829  test    rax, rax
0x14001d82c  jz      loc_14001DDD0
0x14001d832  lea     rbx, [rax+18h]
0x14001d836  mov     [rsp+78h+arg_18], rbx
0x14001d83e  test    edi, edi
0x14001d840  js      loc_14001DBD1
0x14001d846  cmp     edi, [rbx-0Ch]
0x14001d849  jg      loc_14001DBD1
0x14001d84f  movsxd  rax, edi
0x14001d852  mov     [rbx-10h], edi
0x14001d855  lea     r8, [rax+rax]; Size
0x14001d859  mov     [rbx+r8], r12w
0x14001d85e  test    r8, r8
0x14001d861  jz      short loc_14001D877
0x14001d863  mov     rcx, rbx; void *
0x14001d866  test    rbp, rbp
0x14001d869  jz      loc_14001DEA7
0x14001d86f  mov     rdx, rbp; Src
0x14001d872  call    memcpy_0
0x14001d877  lea     r13d, [r15+1]
0x14001d87b  mov     ebp, 0FFFFFFFFh
0x14001d880  add     r13d, r14d
0x14001d883  lea     r14, [rbx-18h]
0x14001d887  mov     rdi, rbx
0x14001d88a  lea     r15, [rsi-18h]
0x14001d88e  cmp     r14, r15
0x14001d891  jz      short loc_14001D8FD
0x14001d893  cmp     dword ptr [r15+10h], 0
0x14001d898  jl      loc_14001DF36
0x14001d89e  mov     rcx, [r14]
0x14001d8a1  cmp     rcx, [r15]
0x14001d8a4  jnz     loc_14001DF36
0x14001d8aa  mov     rax, [rcx]
0x14001d8ad  mov     rax, [rax+20h]
0x14001d8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d8b6  cmp     dword ptr [r14+10h], 0
0x14001d8bb  mov     rcx, rax
0x14001d8be  jl      loc_14001DEF1
0x14001d8c4  cmp     rax, [r14]
0x14001d8c7  jnz     loc_14001DEF1
0x14001d8cd  lock inc dword ptr [r14+10h]
0x14001d8d2  mov     eax, ebp
0x14001d8d4  lock xadd [r15+10h], eax
0x14001d8da  sub     eax, 1
0x14001d8dd  jg      short loc_14001D8F1
0x14001d8df  mov     rcx, [r15]
0x14001d8e2  mov     rdx, r15
0x14001d8e5  mov     rax, [rcx]
0x14001d8e8  mov     rax, [rax+8]
0x14001d8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d8f1  lea     rsi, [r14+18h]
0x14001d8f5  mov     [rsp+78h+arg_0], rsi
0x14001d8fd  lea     rdx, [rbx-18h]
0x14001d901  mov     eax, ebp
0x14001d903  lock xadd [rdx+10h], eax
0x14001d908  sub     eax, 1
0x14001d90b  jg      short loc_14001D91C
0x14001d90d  mov     rcx, [rdx]
0x14001d910  mov     rax, [rcx]
0x14001d913  mov     rax, [rax+8]
0x14001d917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d91c  mov     rdi, [rsp+78h+arg_10]
0x14001d924  mov     r14, [rsp+78h+arg_8]
0x14001d92c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d933  lea     rax, WPP_GLOBAL_Control
0x14001d93a  cmp     dword ptr [rsi-10h], 0
0x14001d93e  lea     r15, asc_1400A3EEC; "/*"
0x14001d945  lea     rbx, aApplicationOct; "application/octet-stream"
0x14001d94c  jz      loc_14001DB5F
0x14001d952  cmp     rcx, rax
0x14001d955  jz      short loc_14001D961
0x14001d957  test    byte ptr [rcx+1Ch], 2
0x14001d95b  jnz     loc_14001DE2E
0x14001d961  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x14001d965  mov     r9d, ebp; cchCount1
0x14001d968  mov     r8, rsi; lpString1
0x14001d96b  mov     [rsp+78h+lpString2], rbx; lpString2
0x14001d970  mov     edx, 1; dwCmpFlags
0x14001d975  mov     ecx, 7Fh; Locale
0x14001d97a  call    cs:__imp_CompareStringW
0x14001d980  cmp     eax, 2
0x14001d983  jz      loc_14001DB52
0x14001d989  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x14001d98d  mov     r9d, ebp; cchCount1
0x14001d990  mov     r8, rsi; lpString1
0x14001d993  mov     [rsp+78h+lpString2], r14; lpString2
0x14001d998  mov     edx, 1; dwCmpFlags
0x14001d99d  mov     ecx, 7Fh; Locale
0x14001d9a2  call    cs:__imp_CompareStringW
0x14001d9a8  cmp     eax, 2
0x14001d9ab  jz      loc_14001DB52
0x14001d9b1  movsxd  rax, dword ptr [rsi-10h]
0x14001d9b5  mov     r9d, ebp; cchCount1
0x14001d9b8  add     rax, 0FFFFFFFFFFFFFFFEh
0x14001d9bc  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x14001d9c0  mov     edx, 1; dwCmpFlags
0x14001d9c5  mov     [rsp+78h+lpString2], r15; lpString2
0x14001d9ca  mov     ecx, 7Fh; Locale
0x14001d9cf  lea     r8, [rsi+rax*2]; lpString1
0x14001d9d3  call    cs:__imp_CompareStringW
0x14001d9d9  cmp     eax, 2
0x14001d9dc  jnz     short loc_14001DA0C
0x14001d9de  mov     r9d, [rsi-10h]
0x14001d9e2  mov     r8, rsi; lpString1
0x14001d9e5  add     r9d, 0FFFFFFFEh; cchCount1
0x14001d9e9  mov     edx, 1; dwCmpFlags
0x14001d9ee  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x14001d9f3  mov     ecx, 7Fh; Locale
  ... truncated ...
```
