# GetWcnInterfaceForDevice(_GUID const *,IFunctionInstance * *,IWCNDevice * *)

- ea: `0x18001e244`
- end: `0x18001e55f`
- name: `?GetWcnInterfaceForDevice@@YAJPEBU_GUID@@PEAPEAUIFunctionInstance@@PEAPEAUIWCNDevice@@@Z`
- size: `795`
- prototype: `__int64 __fastcall(GUID *rguid, struct IFunctionInstance **, struct IWCNDevice **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017a20`

## callees

- `0x180001820`
- `0x18000d630`
- `0x18000e19c`
- `0x180015d28`
- `0x18001e244`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e33d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e33d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e3ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e3ad`

## pseudocode

```c
__int64 __fastcall GetWcnInterfaceForDevice(GUID *rguid, struct IFunctionInstance **a2, struct IWCNDevice **a3)
{
  _BYTE *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  __int64 v9; // rdx
  const char *v10; // r9
  HRESULT v12; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[72]; // [rsp+52h] [rbp-AEh] BYREF
  __int16 v21; // [rsp+9Ah] [rbp-66h]
  unsigned __int16 v22[128]; // [rsp+D0h] [rbp-30h] BYREF

  ppv = 0;
  v17 = 0;
  v16 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 10, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !rguid )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 11;
    v10 = "pDeviceUuid";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v6 + 2), v9, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids, v10);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 12;
    v10 = "ppWcnDevice";
    goto LABEL_12;
  }
  *a3 = 0;
  StringFromGUID2(rguid, &sz, 64);
  v21 = 0;
  v12 = StringCchPrintfW(v22, 0x80u, L"Provider\\Microsoft.Networking.WCN//%s", v20);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v12 = CoCreateInstance(&CLSID_FunctionDiscovery, 0, 0x401u, &IID_IFunctionDiscovery, &ppv);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              v22,
              0,
              0,
              &v17);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL))(v17, &v16);
        v13 = v12;
        if ( v12 >= 0 )
        {
          if ( a2
            && (v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IFunctionInstance **))v16)(
                        v16,
                        &GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9,
                        a2),
                v13 = v12,
                v12 < 0) )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_40;
            v15 = 17;
          }
          else
          {
            v12 = (*(__int64 (__fastcall **)(__int64, SID *, GUID *, struct IWCNDevice **))(*(_QWORD *)v16 + 24LL))(
                    v16,
                    &SID_WcnProvider,
                    &GUID_c100be9c_d33a_4a4b_bf23_bbef4663d017,
                    a3);
            v13 = v12;
            if ( v12 >= 0 )
              goto LABEL_40;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_40;
            v15 = 18;
          }
        }
        else
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_40;
          v15 = 16;
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_40;
        v15 = 15;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_40;
      v15 = 14;
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_40;
    v15 = 13;
  }
  WPP_SF_d(v14[2], v15, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids, (unsigned int)v12);
LABEL_40:
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v13;
}

```

## disassembly

```asm
0x18001e244  mov     [rsp-8+arg_18], rbx
0x18001e249  push    rbp
0x18001e24a  push    rsi
0x18001e24b  push    rdi
0x18001e24c  push    r12
0x18001e24e  push    r15
0x18001e250  lea     rbp, [rsp-0E0h]
0x18001e258  sub     rsp, 1E0h
0x18001e25f  mov     rax, cs:__security_cookie
0x18001e266  xor     rax, rsp
0x18001e269  mov     [rbp+100h+var_30], rax
0x18001e270  mov     rdi, r8
0x18001e273  mov     [rsp+200h+var_1C0], 0
0x18001e27c  mov     rsi, rdx
0x18001e27f  mov     [rsp+200h+var_1C8], 0
0x18001e288  mov     rbx, rcx
0x18001e28b  mov     [rsp+200h+var_1D0], 0
0x18001e294  mov     r10, cs:WPP_GLOBAL_Control
0x18001e29b  lea     r15, WPP_GLOBAL_Control
0x18001e2a2  lea     r12, WPP_4e9bced2490c31cff62a1db6cd3d7a5a_Traceguids
0x18001e2a9  cmp     r10, r15
0x18001e2ac  jz      short loc_18001E2DA
0x18001e2ae  cmp     byte ptr [r10+19h], 6
0x18001e2b3  jb      short loc_18001E2DA
0x18001e2b5  mov     ecx, 1; int
0x18001e2ba  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001e2bf  mov     rcx, [r10+10h]
0x18001e2c3  mov     edx, 0Ah
0x18001e2c8  mov     r9, rax
0x18001e2cb  mov     r8, r12
0x18001e2ce  call    WPP_SF_s
0x18001e2d3  mov     r10, cs:WPP_GLOBAL_Control
0x18001e2da  test    rbx, rbx
0x18001e2dd  jnz     short loc_18001E2F7
0x18001e2df  cmp     r10, r15
0x18001e2e2  jz      short loc_18001E31E
0x18001e2e4  cmp     byte ptr [r10+19h], 2
0x18001e2e9  jb      short loc_18001E31E
0x18001e2eb  lea     edx, [rbx+0Bh]
0x18001e2ee  lea     r9, aPdeviceuuid; "pDeviceUuid"
0x18001e2f5  jmp     short loc_18001E312
0x18001e2f7  test    rdi, rdi
0x18001e2fa  jnz     short loc_18001E328
0x18001e2fc  cmp     r10, r15
0x18001e2ff  jz      short loc_18001E31E
0x18001e301  cmp     byte ptr [r10+19h], 2
0x18001e306  jb      short loc_18001E31E
0x18001e308  lea     edx, [rdi+0Ch]
0x18001e30b  lea     r9, aPpwcndevice; "ppWcnDevice"
0x18001e312  mov     rcx, [r10+10h]
0x18001e316  mov     r8, r12
0x18001e319  call    WPP_SF_s
0x18001e31e  mov     eax, 80004003h
0x18001e323  jmp     loc_18001E539
0x18001e328  mov     r8d, 40h ; '@'; cchMax
0x18001e32e  mov     qword ptr [rdi], 0
0x18001e335  lea     rdx, [rsp+200h+sz]; lpsz
0x18001e33a  mov     rcx, rbx; rguid
0x18001e33d  call    cs:__imp_StringFromGUID2
0x18001e343  xor     eax, eax
0x18001e345  lea     r9, [rsp+200h+var_1AE]
0x18001e34a  lea     r8, aProviderMicros; "Provider\\Microsoft.Networking.WCN//%s"
0x18001e351  mov     [rbp+100h+var_166], ax
0x18001e355  mov     edx, 80h; unsigned __int64
0x18001e35a  lea     rcx, [rbp+100h+var_130]; unsigned __int16 *
0x18001e35e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e363  mov     ebx, eax
0x18001e365  test    eax, eax
0x18001e367  jns     short loc_18001E38D
0x18001e369  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e370  cmp     rcx, r15
0x18001e373  jz      loc_18001E4F5
0x18001e379  cmp     byte ptr [rcx+19h], 2
0x18001e37d  jb      loc_18001E4F5
0x18001e383  mov     edx, 0Dh
0x18001e388  jmp     loc_18001E4E6
0x18001e38d  lea     rax, [rsp+200h+var_1C0]
0x18001e392  xor     edx, edx; pUnkOuter
0x18001e394  lea     r9, IID_IFunctionDiscovery; riid
0x18001e39b  mov     [rsp+200h+ppv], rax; ppv
0x18001e3a0  mov     r8d, 401h; dwClsContext
0x18001e3a6  lea     rcx, CLSID_FunctionDiscovery; rclsid
0x18001e3ad  call    cs:__imp_CoCreateInstance
0x18001e3b3  mov     ebx, eax
0x18001e3b5  test    eax, eax
0x18001e3b7  jns     short loc_18001E3DD
0x18001e3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3c0  cmp     rcx, r15
0x18001e3c3  jz      loc_18001E4F5
0x18001e3c9  cmp     byte ptr [rcx+19h], 2
0x18001e3cd  jb      loc_18001E4F5
0x18001e3d3  mov     edx, 0Eh
0x18001e3d8  jmp     loc_18001E4E6
0x18001e3dd  mov     rcx, [rsp+200h+var_1C0]
0x18001e3e2  lea     rdx, [rsp+200h+var_1C8]
0x18001e3e7  mov     [rsp+200h+ppv], rdx
0x18001e3ec  xor     r9d, r9d
0x18001e3ef  xor     r8d, r8d
0x18001e3f2  lea     rdx, [rbp+100h+var_130]
0x18001e3f6  mov     rax, [rcx]
0x18001e3f9  mov     rax, [rax+30h]
0x18001e3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e402  mov     ebx, eax
0x18001e404  test    eax, eax
0x18001e406  jns     short loc_18001E42C
0x18001e408  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e40f  cmp     rcx, r15
0x18001e412  jz      loc_18001E4F5
0x18001e418  cmp     byte ptr [rcx+19h], 2
0x18001e41c  jb      loc_18001E4F5
0x18001e422  mov     edx, 0Fh
0x18001e427  jmp     loc_18001E4E6
0x18001e42c  mov     rcx, [rsp+200h+var_1C8]
0x18001e431  lea     rdx, [rsp+200h+var_1D0]
0x18001e436  mov     rax, [rcx]
0x18001e439  mov     rax, [rax+18h]
0x18001e43d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e442  mov     ebx, eax
0x18001e444  test    eax, eax
0x18001e446  jns     short loc_18001E469
0x18001e448  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e44f  cmp     rcx, r15
0x18001e452  jz      loc_18001E4F5
0x18001e458  cmp     byte ptr [rcx+19h], 2
0x18001e45c  jb      loc_18001E4F5
0x18001e462  mov     edx, 10h
0x18001e467  jmp     short loc_18001E4E6
0x18001e469  test    rsi, rsi
0x18001e46c  jz      short loc_18001E4A7
0x18001e46e  mov     rcx, [rsp+200h+var_1D0]
0x18001e473  lea     rdx, _GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9
0x18001e47a  mov     r8, rsi
0x18001e47d  mov     rax, [rcx]
0x18001e480  mov     rax, [rax]
0x18001e483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e488  mov     ebx, eax
0x18001e48a  test    eax, eax
0x18001e48c  jns     short loc_18001E4A7
0x18001e48e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e495  cmp     rcx, r15
0x18001e498  jz      short loc_18001E4F5
0x18001e49a  cmp     byte ptr [rcx+19h], 2
0x18001e49e  jb      short loc_18001E4F5
0x18001e4a0  mov     edx, 11h
0x18001e4a5  jmp     short loc_18001E4E6
0x18001e4a7  mov     rcx, [rsp+200h+var_1D0]
0x18001e4ac  lea     r8, _GUID_c100be9c_d33a_4a4b_bf23_bbef4663d017
0x18001e4b3  mov     r9, rdi
0x18001e4b6  lea     rdx, SID_WcnProvider
0x18001e4bd  mov     rax, [rcx]
0x18001e4c0  mov     rax, [rax+18h]
0x18001e4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4c9  mov     ebx, eax
0x18001e4cb  test    eax, eax
0x18001e4cd  jns     short loc_18001E4F5
0x18001e4cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4d6  cmp     rcx, r15
0x18001e4d9  jz      short loc_18001E4F5
0x18001e4db  cmp     byte ptr [rcx+19h], 2
0x18001e4df  jb      short loc_18001E4F5
0x18001e4e1  mov     edx, 12h
0x18001e4e6  mov     rcx, [rcx+10h]
0x18001e4ea  mov     r9d, eax
0x18001e4ed  mov     r8, r12
0x18001e4f0  call    WPP_SF_d
0x18001e4f5  mov     rcx, [rsp+200h+var_1D0]
0x18001e4fa  test    rcx, rcx
0x18001e4fd  jz      short loc_18001E50B
0x18001e4ff  mov     rax, [rcx]
0x18001e502  mov     rax, [rax+10h]
0x18001e506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e50b  mov     rcx, [rsp+200h+var_1C8]
0x18001e510  test    rcx, rcx
0x18001e513  jz      short loc_18001E521
0x18001e515  mov     rax, [rcx]
0x18001e518  mov     rax, [rax+10h]
0x18001e51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e521  mov     rcx, [rsp+200h+var_1C0]
0x18001e526  test    rcx, rcx
0x18001e529  jz      short loc_18001E537
0x18001e52b  mov     rax, [rcx]
0x18001e52e  mov     rax, [rax+10h]
0x18001e532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e537  mov     eax, ebx
0x18001e539  mov     rcx, [rbp+100h+var_30]
0x18001e540  xor     rcx, rsp; StackCookie
0x18001e543  call    __security_check_cookie
0x18001e548  mov     rbx, [rsp+200h+arg_18]
0x18001e550  add     rsp, 1E0h
0x18001e557  pop     r15
0x18001e559  pop     r12
0x18001e55b  pop     rdi
0x18001e55c  pop     rsi
0x18001e55d  pop     rbp
0x18001e55e  retn
```
