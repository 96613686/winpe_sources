# SetServiceStartTypeViaWMI(void)

- ea: `0x180050578`
- end: `0x1800509b2`
- name: `?SetServiceStartTypeViaWMI@@YAXXZ`
- size: `1082`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004f368`

## callees

- `0x18003b1cc`
- `0x18003c018`
- `0x180050578`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800505f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800505f4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800506c8`
- `OLEAUT32!__imp_SysAllocString` at `0x180050752`
- `OLEAUT32!__imp_SysAllocString` at `0x1800507dc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800506c8`
- `OLEAUT32!__imp_SysAllocString` at `0x180050752`
- `OLEAUT32!__imp_SysAllocString` at `0x1800507dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18005096f`
- `OLEAUT32!__imp_SysFreeString` at `0x180050983`
- `OLEAUT32!__imp_SysFreeString` at `0x180050997`
- `OLEAUT32!__imp_SysFreeString` at `0x18005096f`
- `OLEAUT32!__imp_SysFreeString` at `0x180050983`
- `OLEAUT32!__imp_SysFreeString` at `0x180050997`
- `OLEAUT32!__imp_VariantInit` at `0x1800505cb`
- `OLEAUT32!__imp_VariantInit` at `0x1800505cb`

## string_xrefs

- `0x1800507d5`: `UPnPHostConfig`

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
0x180050578  push    rbp
0x18005057a  push    rbx
0x18005057b  push    rsi
0x18005057c  push    rdi
0x18005057d  push    r14
0x18005057f  lea     rbp, [rsp-37h]
0x180050584  sub     rsp, 0D0h
0x18005058b  xorps   xmm0, xmm0
0x18005058e  mov     [rbp+57h+arg_0], 0
0x180050596  xor     eax, eax
0x180050598  mov     [rbp+57h+arg_8], 0
0x1800505a0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800505a4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800505a8  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800505ac  mov     [rbp+57h+arg_10], 0
0x1800505b4  xor     r14d, r14d
0x1800505b7  mov     [rbp+57h+arg_18], 0
0x1800505bf  xor     esi, esi
0x1800505c1  mov     [rbp+57h+var_C0], 0
0x1800505c9  xor     edi, edi
0x1800505cb  call    cs:__imp_VariantInit
0x1800505d2  nop     dword ptr [rax+rax+00h]
0x1800505d7  lea     rax, [rbp+57h+arg_0]
0x1800505db  xor     edx, edx; pUnkOuter
0x1800505dd  lea     r9, IID_ITaskService; riid
0x1800505e4  mov     [rsp+0F0h+ppv], rax; ppv
0x1800505e9  lea     r8d, [r14+1]; dwClsContext
0x1800505ed  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800505f4  call    cs:__imp_CoCreateInstance
0x1800505fb  nop     dword ptr [rax+rax+00h]
0x180050600  test    eax, eax
0x180050602  jns     short loc_180050640
0x180050604  mov     rcx, cs:WPP_GLOBAL_Control
0x18005060b  lea     rbx, WPP_GLOBAL_Control
0x180050612  cmp     rcx, rbx
0x180050615  jz      loc_1800508FE
0x18005061b  test    byte ptr [rcx+1Ch], 40h
0x18005061f  jz      loc_1800508FE
0x180050625  lea     edx, [rsi+4Dh]
0x180050628  mov     rcx, [rcx+10h]
0x18005062c  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180050633  mov     r9d, eax
0x180050636  call    WPP_SF_d
0x18005063b  jmp     loc_1800508FE
0x180050640  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x180050644  lea     rdx, [rbp+57h+var_80]
0x180050648  mov     rcx, [rbp+57h+arg_0]
0x18005064c  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180050651  lea     r9, [rbp+57h+var_60]
0x180050655  mov     [rsp+0F0h+ppv], rdx
0x18005065a  lea     r8, [rbp+57h+var_40]
0x18005065e  lea     rdx, [rbp+57h+var_A0]
0x180050662  movaps  [rbp+57h+var_80], xmm1
0x180050666  mov     rax, [rcx]
0x180050669  movsd   [rbp+57h+var_70], xmm0
0x18005066e  movaps  [rbp+57h+var_60], xmm1
0x180050672  movsd   [rbp+57h+var_50], xmm0
0x180050677  mov     rax, [rax+50h]
0x18005067b  movaps  [rbp+57h+var_40], xmm1
0x18005067f  movsd   [rbp+57h+var_30], xmm0
0x180050684  movaps  [rbp+57h+var_A0], xmm1
0x180050688  movsd   [rbp+57h+var_90], xmm0
0x18005068d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050692  test    eax, eax
0x180050694  jns     short loc_1800506C1
0x180050696  mov     rcx, cs:WPP_GLOBAL_Control
0x18005069d  lea     rbx, WPP_GLOBAL_Control
0x1800506a4  cmp     rcx, rbx
0x1800506a7  jz      loc_1800508FE
0x1800506ad  test    byte ptr [rcx+1Ch], 40h
0x1800506b1  jz      loc_1800508FE
0x1800506b7  mov     edx, 4Eh ; 'N'
0x1800506bc  jmp     loc_180050628
0x1800506c1  lea     rcx, asc_180063924; "\\"
0x1800506c8  call    cs:__imp_SysAllocString
0x1800506cf  nop     dword ptr [rax+rax+00h]
0x1800506d4  mov     r14, rax
0x1800506d7  test    rax, rax
0x1800506da  jnz     short loc_180050705
0x1800506dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800506e3  lea     rbx, WPP_GLOBAL_Control
0x1800506ea  cmp     rcx, rbx
0x1800506ed  jz      loc_1800508FE
0x1800506f3  test    byte ptr [rcx+1Ch], 40h
0x1800506f7  jz      loc_1800508FE
0x1800506fd  lea     edx, [rax+4Fh]
0x180050700  jmp     loc_1800508EE
0x180050705  mov     rcx, [rbp+57h+arg_0]
0x180050709  lea     r8, [rbp+57h+arg_8]
0x18005070d  mov     rdx, r14
0x180050710  mov     rax, [rcx]
0x180050713  mov     rax, [rax+38h]
0x180050717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005071c  test    eax, eax
0x18005071e  jns     short loc_18005074B
0x180050720  mov     rcx, cs:WPP_GLOBAL_Control
0x180050727  lea     rbx, WPP_GLOBAL_Control
0x18005072e  cmp     rcx, rbx
0x180050731  jz      loc_1800508FE
0x180050737  test    byte ptr [rcx+1Ch], 40h
0x18005073b  jz      loc_1800508FE
0x180050741  mov     edx, 50h ; 'P'
0x180050746  jmp     loc_180050628
0x18005074b  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\UPnP"
0x180050752  call    cs:__imp_SysAllocString
0x180050759  nop     dword ptr [rax+rax+00h]
0x18005075e  mov     rsi, rax
0x180050761  test    rax, rax
0x180050764  jnz     short loc_18005078F
0x180050766  mov     rcx, cs:WPP_GLOBAL_Control
0x18005076d  lea     rbx, WPP_GLOBAL_Control
0x180050774  cmp     rcx, rbx
0x180050777  jz      loc_1800508FE
0x18005077d  test    byte ptr [rcx+1Ch], 40h
0x180050781  jz      loc_1800508FE
0x180050787  lea     edx, [rax+51h]
0x18005078a  jmp     loc_1800508EE
0x18005078f  mov     rcx, [rbp+57h+arg_8]
0x180050793  lea     r8, [rbp+57h+arg_10]
0x180050797  mov     rdx, rsi
0x18005079a  mov     rax, [rcx]
0x18005079d  mov     rax, [rax+48h]
0x1800507a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507a6  test    eax, eax
0x1800507a8  jns     short loc_1800507D5
0x1800507aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800507b1  lea     rbx, WPP_GLOBAL_Control
0x1800507b8  cmp     rcx, rbx
0x1800507bb  jz      loc_1800508FE
0x1800507c1  test    byte ptr [rcx+1Ch], 40h
0x1800507c5  jz      loc_1800508FE
0x1800507cb  mov     edx, 52h ; 'R'
0x1800507d0  jmp     loc_180050628
0x1800507d5  lea     rcx, aUpnphostconfig; "UPnPHostConfig"
0x1800507dc  call    cs:__imp_SysAllocString
0x1800507e3  nop     dword ptr [rax+rax+00h]
0x1800507e8  mov     rdi, rax
0x1800507eb  test    rax, rax
0x1800507ee  jnz     short loc_180050819
0x1800507f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800507f7  lea     rbx, WPP_GLOBAL_Control
0x1800507fe  cmp     rcx, rbx
0x180050801  jz      loc_1800508FE
0x180050807  test    byte ptr [rcx+1Ch], 40h
0x18005080b  jz      loc_1800508FE
0x180050811  lea     edx, [rax+53h]
0x180050814  jmp     loc_1800508EE
0x180050819  mov     rcx, [rbp+57h+arg_10]
0x18005081d  lea     r8, [rbp+57h+arg_18]
0x180050821  mov     rdx, rdi
0x180050824  mov     rax, [rcx]
0x180050827  mov     rax, [rax+68h]
0x18005082b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050830  test    eax, eax
0x180050832  jns     short loc_18005085F
0x180050834  mov     rcx, cs:WPP_GLOBAL_Control
0x18005083b  lea     rbx, WPP_GLOBAL_Control
0x180050842  cmp     rcx, rbx
0x180050845  jz      loc_1800508FE
0x18005084b  test    byte ptr [rcx+1Ch], 40h
0x18005084f  jz      loc_1800508FE
0x180050855  mov     edx, 54h ; 'T'
0x18005085a  jmp     loc_180050628
0x18005085f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050866  lea     rbx, WPP_GLOBAL_Control
0x18005086d  cmp     rcx, rbx
0x180050870  jz      short loc_18005088D
0x180050872  test    byte ptr [rcx+1Ch], 40h
0x180050876  jz      short loc_18005088D
0x180050878  mov     rcx, [rcx+10h]
0x18005087c  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180050883  mov     edx, 55h ; 'U'
0x180050888  call    WPP_SF_
0x18005088d  mov     rcx, [rbp+57h+arg_18]
0x180050891  lea     r8, [rbp+57h+var_C0]
0x180050895  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180050899  lea     rdx, [rbp+57h+var_A0]
0x18005089d  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800508a2  mov     rax, [rcx]
0x1800508a5  movaps  [rbp+57h+var_A0], xmm0
0x1800508a9  movsd   [rbp+57h+var_90], xmm1
0x1800508ae  mov     rax, [rax+60h]
0x1800508b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508b7  test    eax, eax
0x1800508b9  jns     short loc_1800508D7
0x1800508bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800508c2  cmp     rcx, rbx
0x1800508c5  jz      short loc_1800508FE
0x1800508c7  test    byte ptr [rcx+1Ch], 40h
0x1800508cb  jz      short loc_1800508FE
0x1800508cd  mov     edx, 56h ; 'V'
0x1800508d2  jmp     loc_180050628
0x1800508d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800508de  cmp     rcx, rbx
0x1800508e1  jz      short loc_1800508FE
0x1800508e3  test    byte ptr [rcx+1Ch], 40h
0x1800508e7  jz      short loc_1800508FE
0x1800508e9  mov     edx, 57h ; 'W'
0x1800508ee  mov     rcx, [rcx+10h]
0x1800508f2  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x1800508f9  call    WPP_SF_
0x1800508fe  mov     rcx, [rbp+57h+arg_0]
0x180050902  test    rcx, rcx
0x180050905  jz      short loc_180050913
0x180050907  mov     rax, [rcx]
0x18005090a  mov     rax, [rax+10h]
0x18005090e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050913  mov     rcx, [rbp+57h+arg_8]
0x180050917  test    rcx, rcx
0x18005091a  jz      short loc_180050928
0x18005091c  mov     rax, [rcx]
0x18005091f  mov     rax, [rax+10h]
0x180050923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050928  mov     rcx, [rbp+57h+arg_10]
0x18005092c  test    rcx, rcx
0x18005092f  jz      short loc_18005093D
0x180050931  mov     rax, [rcx]
0x180050934  mov     rax, [rax+10h]
0x180050938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005093d  mov     rcx, [rbp+57h+arg_18]
0x180050941  test    rcx, rcx
0x180050944  jz      short loc_180050952
0x180050946  mov     rax, [rcx]
0x180050949  mov     rax, [rax+10h]
0x18005094d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050952  mov     rcx, [rbp+57h+var_C0]
0x180050956  test    rcx, rcx
0x180050959  jz      short loc_180050967
0x18005095b  mov     rax, [rcx]
0x18005095e  mov     rax, [rax+10h]
0x180050962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050967  test    r14, r14
0x18005096a  jz      short loc_18005097B
0x18005096c  mov     rcx, r14; bstrString
0x18005096f  call    cs:__imp_SysFreeString
0x180050976  nop     dword ptr [rax+rax+00h]
0x18005097b  test    rsi, rsi
0x18005097e  jz      short loc_18005098F
0x180050980  mov     rcx, rsi; bstrString
0x180050983  call    cs:__imp_SysFreeString
0x18005098a  nop     dword ptr [rax+rax+00h]
0x18005098f  test    rdi, rdi
0x180050992  jz      short loc_1800509A3
0x180050994  mov     rcx, rdi; bstrString
0x180050997  call    cs:__imp_SysFreeString
0x18005099e  nop     dword ptr [rax+rax+00h]
0x1800509a3  add     rsp, 0D0h
0x1800509aa  pop     r14
0x1800509ac  pop     rdi
0x1800509ad  pop     rsi
0x1800509ae  pop     rbx
0x1800509af  pop     rbp
0x1800509b0  retn
```
