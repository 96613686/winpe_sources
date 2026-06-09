# SetServiceStartTypeViaWMI(void)

- ea: `0x18004d178`
- end: `0x18004d581`
- name: `?SetServiceStartTypeViaWMI@@YAXXZ`
- size: `1033`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004c024`

## callees

- `0x180038ce4`
- `0x180039a84`
- `0x18004d178`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d1ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d1ee`
- `OLEAUT32!__imp_SysAllocString` at `0x18004d2bc`
- `OLEAUT32!__imp_SysAllocString` at `0x18004d340`
- `OLEAUT32!__imp_SysAllocString` at `0x18004d3c4`
- `OLEAUT32!__imp_SysAllocString` at `0x18004d2bc`
- `OLEAUT32!__imp_SysAllocString` at `0x18004d340`
- `OLEAUT32!__imp_SysAllocString` at `0x18004d3c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d551`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d55f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d56d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d551`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d55f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d56d`
- `OLEAUT32!__imp_VariantInit` at `0x18004d1cb`
- `OLEAUT32!__imp_VariantInit` at `0x18004d1cb`

## string_xrefs

- `0x18004d3bd`: `UPnPHostConfig`

## pseudocode

```c
void SetServiceStartTypeViaWMI(void)
{
  OLECHAR *v0; // r14
  OLECHAR *v1; // rsi
  OLECHAR *v2; // rdi
  HRESULT v3; // eax
  STRSAFE_PCNZWCH v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 (__fastcall *v7)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  BSTR v8; // rax
  STRSAFE_PCNZWCH v9; // rcx
  __int64 v10; // rdx
  BSTR v11; // rax
  BSTR v12; // rax
  __int64 v13; // rax
  __int64 v14; // [rsp+30h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-61h] BYREF
  VARIANTARG v16; // [rsp+50h] [rbp-49h] BYREF
  __int128 v17; // [rsp+70h] [rbp-29h] BYREF
  IRecordInfo *pRecInfo; // [rsp+80h] [rbp-19h]
  VARIANTARG v19; // [rsp+90h] [rbp-9h] BYREF
  VARIANTARG v20; // [rsp+B0h] [rbp+17h] BYREF
  LPVOID ppv; // [rsp+100h] [rbp+67h] BYREF
  __int64 v22; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+110h] [rbp+77h] BYREF
  __int64 *v24; // [rsp+118h] [rbp+7Fh] BYREF

  ppv = 0;
  v22 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v23 = 0;
  v0 = 0;
  v24 = 0;
  v1 = 0;
  v14 = 0;
  v2 = 0;
  VariantInit(&pvarg);
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v3 >= 0 )
  {
    v17 = *(_OWORD *)&pvarg.vt;
    v6 = *(_QWORD *)ppv;
    pRecInfo = pvarg.pRecInfo;
    v19 = pvarg;
    v7 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v6 + 80);
    v20 = pvarg;
    v16 = pvarg;
    v3 = v7(ppv, &v16, &v20, &v19, &v17);
    if ( v3 >= 0 )
    {
      v8 = SysAllocString(L"\\");
      v0 = v8;
      if ( v8 )
      {
        v3 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v8, &v22);
        if ( v3 < 0 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
          {
            v5 = 80;
            goto LABEL_5;
          }
          goto LABEL_45;
        }
        v11 = SysAllocString(L"\\Microsoft\\Windows\\UPnP");
        v1 = v11;
        if ( v11 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v22 + 72LL))(v22, v11, &v23);
          if ( v3 < 0 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
            {
              v5 = 82;
              goto LABEL_5;
            }
            goto LABEL_45;
          }
          v12 = SysAllocString(L"UPnPHostConfig");
          v2 = v12;
          if ( v12 )
          {
            v3 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 **))(*(_QWORD *)v23 + 104LL))(v23, v12, &v24);
            if ( v3 < 0 )
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
              {
                v5 = 84;
                goto LABEL_5;
              }
              goto LABEL_45;
            }
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
            v13 = *v24;
            v16 = pvarg;
            v3 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v13 + 96))(v24, &v16, &v14);
            if ( v3 < 0 )
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
              {
                v5 = 86;
                goto LABEL_5;
              }
              goto LABEL_45;
            }
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 0x40) == 0 )
              goto LABEL_45;
            v10 = 87;
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 0x40) == 0 )
              goto LABEL_45;
            v10 = 83;
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 0x40) == 0 )
            goto LABEL_45;
          v10 = 81;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 0x40) == 0 )
          goto LABEL_45;
        v10 = 79;
      }
      WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids);
      goto LABEL_45;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    {
      v5 = 78;
      goto LABEL_5;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    {
      v5 = 77;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids, (unsigned int)v3);
    }
  }
LABEL_45:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v0 )
    SysFreeString(v0);
  if ( v1 )
    SysFreeString(v1);
  if ( v2 )
    SysFreeString(v2);
}

```

## disassembly

```asm
0x18004d178  push    rbp
0x18004d17a  push    rbx
0x18004d17b  push    rsi
0x18004d17c  push    rdi
0x18004d17d  push    r14
0x18004d17f  lea     rbp, [rsp-37h]
0x18004d184  sub     rsp, 0D0h
0x18004d18b  xorps   xmm0, xmm0
0x18004d18e  mov     [rbp+57h+arg_0], 0
0x18004d196  xor     eax, eax
0x18004d198  mov     [rbp+57h+arg_8], 0
0x18004d1a0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004d1a4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18004d1a8  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18004d1ac  mov     [rbp+57h+arg_10], 0
0x18004d1b4  xor     r14d, r14d
0x18004d1b7  mov     [rbp+57h+arg_18], 0
0x18004d1bf  xor     esi, esi
0x18004d1c1  mov     [rbp+57h+var_C0], 0
0x18004d1c9  xor     edi, edi
0x18004d1cb  call    cs:__imp_VariantInit
0x18004d1d1  lea     rax, [rbp+57h+arg_0]
0x18004d1d5  xor     edx, edx; pUnkOuter
0x18004d1d7  lea     r9, IID_ITaskService; riid
0x18004d1de  mov     [rsp+0F0h+ppv], rax; ppv
0x18004d1e3  lea     r8d, [r14+1]; dwClsContext
0x18004d1e7  lea     rcx, CLSID_TaskScheduler; rclsid
0x18004d1ee  call    cs:__imp_CoCreateInstance
0x18004d1f4  test    eax, eax
0x18004d1f6  jns     short loc_18004D234
0x18004d1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d1ff  lea     rbx, WPP_GLOBAL_Control
0x18004d206  cmp     rcx, rbx
0x18004d209  jz      loc_18004D4E0
0x18004d20f  test    byte ptr [rcx+1Ch], 40h
0x18004d213  jz      loc_18004D4E0
0x18004d219  lea     edx, [rsi+4Dh]
0x18004d21c  mov     rcx, [rcx+10h]
0x18004d220  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004d227  mov     r9d, eax
0x18004d22a  call    WPP_SF_d
0x18004d22f  jmp     loc_18004D4E0
0x18004d234  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18004d238  lea     rdx, [rbp+57h+var_80]
0x18004d23c  mov     rcx, [rbp+57h+arg_0]
0x18004d240  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18004d245  lea     r9, [rbp+57h+var_60]
0x18004d249  mov     [rsp+0F0h+ppv], rdx
0x18004d24e  lea     r8, [rbp+57h+var_40]
0x18004d252  lea     rdx, [rbp+57h+var_A0]
0x18004d256  movaps  [rbp+57h+var_80], xmm1
0x18004d25a  mov     rax, [rcx]
0x18004d25d  movsd   [rbp+57h+var_70], xmm0
0x18004d262  movaps  [rbp+57h+var_60], xmm1
0x18004d266  movsd   [rbp+57h+var_50], xmm0
0x18004d26b  mov     rax, [rax+50h]
0x18004d26f  movaps  [rbp+57h+var_40], xmm1
0x18004d273  movsd   [rbp+57h+var_30], xmm0
0x18004d278  movaps  [rbp+57h+var_A0], xmm1
0x18004d27c  movsd   [rbp+57h+var_90], xmm0
0x18004d281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d286  test    eax, eax
0x18004d288  jns     short loc_18004D2B5
0x18004d28a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d291  lea     rbx, WPP_GLOBAL_Control
0x18004d298  cmp     rcx, rbx
0x18004d29b  jz      loc_18004D4E0
0x18004d2a1  test    byte ptr [rcx+1Ch], 40h
0x18004d2a5  jz      loc_18004D4E0
0x18004d2ab  mov     edx, 4Eh ; 'N'
0x18004d2b0  jmp     loc_18004D21C
0x18004d2b5  lea     rcx, asc_180060164; "\\"
0x18004d2bc  call    cs:__imp_SysAllocString
0x18004d2c2  mov     r14, rax
0x18004d2c5  test    rax, rax
0x18004d2c8  jnz     short loc_18004D2F3
0x18004d2ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d2d1  lea     rbx, WPP_GLOBAL_Control
0x18004d2d8  cmp     rcx, rbx
0x18004d2db  jz      loc_18004D4E0
0x18004d2e1  test    byte ptr [rcx+1Ch], 40h
0x18004d2e5  jz      loc_18004D4E0
0x18004d2eb  lea     edx, [rax+4Fh]
0x18004d2ee  jmp     loc_18004D4D0
0x18004d2f3  mov     rcx, [rbp+57h+arg_0]
0x18004d2f7  lea     r8, [rbp+57h+arg_8]
0x18004d2fb  mov     rdx, r14
0x18004d2fe  mov     rax, [rcx]
0x18004d301  mov     rax, [rax+38h]
0x18004d305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d30a  test    eax, eax
0x18004d30c  jns     short loc_18004D339
0x18004d30e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d315  lea     rbx, WPP_GLOBAL_Control
0x18004d31c  cmp     rcx, rbx
0x18004d31f  jz      loc_18004D4E0
0x18004d325  test    byte ptr [rcx+1Ch], 40h
0x18004d329  jz      loc_18004D4E0
0x18004d32f  mov     edx, 50h ; 'P'
0x18004d334  jmp     loc_18004D21C
0x18004d339  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\UPnP"
0x18004d340  call    cs:__imp_SysAllocString
0x18004d346  mov     rsi, rax
0x18004d349  test    rax, rax
0x18004d34c  jnz     short loc_18004D377
0x18004d34e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d355  lea     rbx, WPP_GLOBAL_Control
0x18004d35c  cmp     rcx, rbx
0x18004d35f  jz      loc_18004D4E0
0x18004d365  test    byte ptr [rcx+1Ch], 40h
0x18004d369  jz      loc_18004D4E0
0x18004d36f  lea     edx, [rax+51h]
0x18004d372  jmp     loc_18004D4D0
0x18004d377  mov     rcx, [rbp+57h+arg_8]
0x18004d37b  lea     r8, [rbp+57h+arg_10]
0x18004d37f  mov     rdx, rsi
0x18004d382  mov     rax, [rcx]
0x18004d385  mov     rax, [rax+48h]
0x18004d389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d38e  test    eax, eax
0x18004d390  jns     short loc_18004D3BD
0x18004d392  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d399  lea     rbx, WPP_GLOBAL_Control
0x18004d3a0  cmp     rcx, rbx
0x18004d3a3  jz      loc_18004D4E0
0x18004d3a9  test    byte ptr [rcx+1Ch], 40h
0x18004d3ad  jz      loc_18004D4E0
0x18004d3b3  mov     edx, 52h ; 'R'
0x18004d3b8  jmp     loc_18004D21C
0x18004d3bd  lea     rcx, aUpnphostconfig; "UPnPHostConfig"
0x18004d3c4  call    cs:__imp_SysAllocString
0x18004d3ca  mov     rdi, rax
0x18004d3cd  test    rax, rax
0x18004d3d0  jnz     short loc_18004D3FB
0x18004d3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d3d9  lea     rbx, WPP_GLOBAL_Control
0x18004d3e0  cmp     rcx, rbx
0x18004d3e3  jz      loc_18004D4E0
0x18004d3e9  test    byte ptr [rcx+1Ch], 40h
0x18004d3ed  jz      loc_18004D4E0
0x18004d3f3  lea     edx, [rax+53h]
0x18004d3f6  jmp     loc_18004D4D0
0x18004d3fb  mov     rcx, [rbp+57h+arg_10]
0x18004d3ff  lea     r8, [rbp+57h+arg_18]
0x18004d403  mov     rdx, rdi
0x18004d406  mov     rax, [rcx]
0x18004d409  mov     rax, [rax+68h]
0x18004d40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d412  test    eax, eax
0x18004d414  jns     short loc_18004D441
0x18004d416  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d41d  lea     rbx, WPP_GLOBAL_Control
0x18004d424  cmp     rcx, rbx
0x18004d427  jz      loc_18004D4E0
0x18004d42d  test    byte ptr [rcx+1Ch], 40h
0x18004d431  jz      loc_18004D4E0
0x18004d437  mov     edx, 54h ; 'T'
0x18004d43c  jmp     loc_18004D21C
0x18004d441  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d448  lea     rbx, WPP_GLOBAL_Control
0x18004d44f  cmp     rcx, rbx
0x18004d452  jz      short loc_18004D46F
0x18004d454  test    byte ptr [rcx+1Ch], 40h
0x18004d458  jz      short loc_18004D46F
0x18004d45a  mov     rcx, [rcx+10h]
0x18004d45e  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004d465  mov     edx, 55h ; 'U'
0x18004d46a  call    WPP_SF_
0x18004d46f  mov     rcx, [rbp+57h+arg_18]
0x18004d473  lea     r8, [rbp+57h+var_C0]
0x18004d477  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18004d47b  lea     rdx, [rbp+57h+var_A0]
0x18004d47f  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18004d484  mov     rax, [rcx]
0x18004d487  movaps  [rbp+57h+var_A0], xmm0
0x18004d48b  movsd   [rbp+57h+var_90], xmm1
0x18004d490  mov     rax, [rax+60h]
0x18004d494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d499  test    eax, eax
0x18004d49b  jns     short loc_18004D4B9
0x18004d49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d4a4  cmp     rcx, rbx
0x18004d4a7  jz      short loc_18004D4E0
0x18004d4a9  test    byte ptr [rcx+1Ch], 40h
0x18004d4ad  jz      short loc_18004D4E0
0x18004d4af  mov     edx, 56h ; 'V'
0x18004d4b4  jmp     loc_18004D21C
0x18004d4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d4c0  cmp     rcx, rbx
0x18004d4c3  jz      short loc_18004D4E0
0x18004d4c5  test    byte ptr [rcx+1Ch], 40h
0x18004d4c9  jz      short loc_18004D4E0
0x18004d4cb  mov     edx, 57h ; 'W'
0x18004d4d0  mov     rcx, [rcx+10h]
0x18004d4d4  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18004d4db  call    WPP_SF_
0x18004d4e0  mov     rcx, [rbp+57h+arg_0]
0x18004d4e4  test    rcx, rcx
0x18004d4e7  jz      short loc_18004D4F5
0x18004d4e9  mov     rax, [rcx]
0x18004d4ec  mov     rax, [rax+10h]
0x18004d4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4f5  mov     rcx, [rbp+57h+arg_8]
0x18004d4f9  test    rcx, rcx
0x18004d4fc  jz      short loc_18004D50A
0x18004d4fe  mov     rax, [rcx]
0x18004d501  mov     rax, [rax+10h]
0x18004d505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d50a  mov     rcx, [rbp+57h+arg_10]
0x18004d50e  test    rcx, rcx
0x18004d511  jz      short loc_18004D51F
0x18004d513  mov     rax, [rcx]
0x18004d516  mov     rax, [rax+10h]
0x18004d51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d51f  mov     rcx, [rbp+57h+arg_18]
0x18004d523  test    rcx, rcx
0x18004d526  jz      short loc_18004D534
0x18004d528  mov     rax, [rcx]
0x18004d52b  mov     rax, [rax+10h]
0x18004d52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d534  mov     rcx, [rbp+57h+var_C0]
0x18004d538  test    rcx, rcx
0x18004d53b  jz      short loc_18004D549
0x18004d53d  mov     rax, [rcx]
0x18004d540  mov     rax, [rax+10h]
0x18004d544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d549  test    r14, r14
0x18004d54c  jz      short loc_18004D557
0x18004d54e  mov     rcx, r14; bstrString
0x18004d551  call    cs:__imp_SysFreeString
0x18004d557  test    rsi, rsi
0x18004d55a  jz      short loc_18004D565
0x18004d55c  mov     rcx, rsi; bstrString
0x18004d55f  call    cs:__imp_SysFreeString
0x18004d565  test    rdi, rdi
0x18004d568  jz      short loc_18004D573
0x18004d56a  mov     rcx, rdi; bstrString
0x18004d56d  call    cs:__imp_SysFreeString
0x18004d573  add     rsp, 0D0h
0x18004d57a  pop     r14
0x18004d57c  pop     rdi
0x18004d57d  pop     rsi
0x18004d57e  pop     rbx
0x18004d57f  pop     rbp
0x18004d580  retn
```
