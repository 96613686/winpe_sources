# HrCanWrapCOMComponent(_GUID const *,_GUID const *,ushort *,_XW_WRAPPED_COM_COMPONENT_INFO * *)

- ea: `0x18001bb24`
- end: `0x18001bf3c`
- name: `?HrCanWrapCOMComponent@@YAJPEBU_GUID@@0PEAGPEAPEAU_XW_WRAPPED_COM_COMPONENT_INFO@@@Z`
- size: `1048`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, unsigned __int16 *, struct _XW_WRAPPED_COM_COMPONENT_INFO **)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180015df0`
- `0x18001c220`
- `0x18001d200`
- `0x18002841c`

## callees

- `0x18000ae04`
- `0x18000ae44`
- `0x18000d8b8`
- `0x18001bb24`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd4d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001bd24`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001bd24`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bb8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bc90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bb8e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bc90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bdac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bdb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bed5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bdac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bdb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bed5`

## pseudocode

```c
__int64 __fastcall HrCanWrapCOMComponent(
        struct _GUID *a1,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        struct _XW_WRAPPED_COM_COMPONENT_INFO **a4)
{
  HRESULT v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned __int16 *v7; // r12
  char *v8; // rdi
  __int64 v9; // r13
  __int64 v10; // rdx
  HRESULT v11; // eax
  LPVOID *p_pv; // r8
  unsigned __int16 *v13; // r12
  char *v14; // rax
  __int128 v15; // xmm0
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  LPVOID *v18; // r12
  struct _XW_WRAPPED_COM_COMPONENT_INFO *i; // rdi
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v23; // [rsp+50h] [rbp-B0h]
  LPVOID v24; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  GUID *rguid; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v27; // [rsp+70h] [rbp-90h] BYREF
  struct _XW_WRAPPED_COM_COMPONENT_INFO **v28; // [rsp+78h] [rbp-88h]
  const struct _GUID *v29; // [rsp+80h] [rbp-80h]
  IID rclsid; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF

  v28 = a4;
  v23 = a3;
  v29 = a2;
  rguid = a1;
  *a4 = 0;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_CPXWizardRegistryInfo, 0, 0x401u, &IID_IPXWizardRegistryInfo, &ppv);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 12;
      goto LABEL_54;
    }
    return (unsigned int)v4;
  }
  v7 = v23;
  v8 = 0;
  v9 = 0;
LABEL_6:
  v4 = 1;
  while ( 1 )
  {
    v10 = *((unsigned int *)qword_18003D0A0 + v9);
    if ( !(_DWORD)v10 )
      break;
    v24 = 0;
    rclsid = 0;
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, IID *, _QWORD))(*(_QWORD *)ppv + 88LL))(ppv, v10, &rclsid, 0);
    v4 = v11;
    if ( v11 == -2147467263 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids,
          *((unsigned int *)qword_18003D0A0 + v9),
          -2147467263);
      v9 = (unsigned int)(v9 + 1);
      goto LABEL_6;
    }
    if ( v11 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v17 = 14;
LABEL_46:
        WPP_SF_DD(
          v16[2],
          v17,
          WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids,
          *((unsigned int *)qword_18003D0A0 + v9),
          v11);
      }
LABEL_47:
      v18 = (LPVOID *)v28;
      for ( i = *v28; i; i = (struct _XW_WRAPPED_COM_COMPONENT_INFO *)((char *)i + 48) )
      {
        if ( !*(_DWORD *)i )
          break;
        CoTaskMemFree(*((LPVOID *)i + 5));
      }
      CoTaskMemFree(*v18);
      *v18 = 0;
      break;
    }
    v11 = CoCreateInstance(&rclsid, 0, 0x401u, &IID_IPXWizardTypeCOMWrapper, &v24);
    v4 = v11;
    if ( v11 >= 0 )
    {
      p_pv = &pv;
      pv = 0;
      v22 = 0;
      if ( v8 )
        p_pv = 0;
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, const struct _GUID *, unsigned __int16 *, LPVOID *, LPVOID *))(*(_QWORD *)v24 + 24LL))(
             v24,
             *((unsigned int *)qword_18003D0A0 + v9),
             rguid,
             v29,
             v7,
             p_pv,
             &v22);
      if ( !v4 )
      {
        v13 = 0;
        v27 = 0;
        if ( v23 )
          goto LABEL_22;
        if ( v8 )
          goto LABEL_25;
        StringFromGUID2(rguid, sz, 40);
        v4 = HrVerifyCOMRegistration(sz, &v27);
        if ( v4 < 0 )
          goto LABEL_28;
        v13 = v27;
LABEL_22:
        if ( v8 )
        {
LABEL_25:
          *(_DWORD *)v8 = *((_DWORD *)qword_18003D0A0 + v9);
          if ( pv )
            *(_OWORD *)(v8 + 4) = *(_OWORD *)pv;
          v15 = *(_OWORD *)v22;
          *((_QWORD *)v8 + 5) = v13;
          *(_OWORD *)(v8 + 20) = v15;
          v8 += 48;
        }
        else
        {
          v14 = (char *)CoTaskMemAlloc(0x150u);
          v8 = v14;
          if ( v14 )
          {
            memset_0(v14, 0, 0x150u);
            *v28 = (struct _XW_WRAPPED_COM_COMPONENT_INFO *)v8;
            goto LABEL_25;
          }
          CoTaskMemFree(v13);
          v4 = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids,
              2147942414LL);
        }
LABEL_28:
        CoTaskMemFree(pv);
        CoTaskMemFree(v22);
        v7 = v23;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
      goto LABEL_40;
    }
    if ( v11 == -2147467262 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids,
          *((unsigned int *)qword_18003D0A0 + v9),
          -2147467262);
      v9 = (unsigned int)(v9 + 1);
      goto LABEL_6;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v17 = 17;
      goto LABEL_46;
    }
LABEL_40:
    v9 = (unsigned int)(v9 + 1);
    if ( v4 < 0 )
      goto LABEL_47;
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v6 = 18;
LABEL_54:
    WPP_SF_d(v5[2], v6, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids, (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001bb24  push    rbp
0x18001bb26  push    rbx
0x18001bb27  push    rsi
0x18001bb28  push    rdi
0x18001bb29  push    r12
0x18001bb2b  push    r13
0x18001bb2d  push    r14
0x18001bb2f  push    r15
0x18001bb31  lea     rbp, [rsp-8]
0x18001bb36  sub     rsp, 108h
0x18001bb3d  mov     rax, cs:__security_cookie
0x18001bb44  xor     rax, rsp
0x18001bb47  mov     [rbp+40h+var_50], rax
0x18001bb4b  mov     [rsp+140h+var_C8], r9
0x18001bb50  lea     rax, [rsp+140h+var_E0]
0x18001bb55  mov     [rsp+140h+var_F0], r8
0x18001bb5a  mov     r8d, 401h; dwClsContext
0x18001bb60  mov     [rbp+40h+var_C0], rdx
0x18001bb64  xor     edx, edx; pUnkOuter
0x18001bb66  mov     [rsp+140h+rguid], rcx
0x18001bb6b  lea     rcx, CLSID_CPXWizardRegistryInfo; rclsid
0x18001bb72  mov     qword ptr [r9], 0
0x18001bb79  lea     r9, IID_IPXWizardRegistryInfo; riid
0x18001bb80  mov     [rsp+140h+ppv], rax; ppv
0x18001bb85  mov     [rsp+140h+var_E0], 0
0x18001bb8e  call    cs:__imp_CoCreateInstance
0x18001bb94  mov     ebx, eax
0x18001bb96  test    eax, eax
0x18001bb98  jns     short loc_18001BBCC
0x18001bb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bba1  lea     rsi, WPP_GLOBAL_Control
0x18001bba8  cmp     rcx, rsi
0x18001bbab  jz      loc_18001BF1A
0x18001bbb1  test    byte ptr [rcx+1Ch], 4
0x18001bbb5  jz      loc_18001BF1A
0x18001bbbb  mov     edx, 0Ch
0x18001bbc0  lea     r8, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids
0x18001bbc7  jmp     loc_18001BF0E
0x18001bbcc  mov     r12, [rsp+140h+var_F0]
0x18001bbd1  lea     rsi, WPP_GLOBAL_Control
0x18001bbd8  xor     edi, edi
0x18001bbda  lea     r14, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids
0x18001bbe1  xor     r13d, r13d
0x18001bbe4  mov     ebx, 1
0x18001bbe9  lea     rax, qword_18003D0A0
0x18001bbf0  mov     edx, [rax+r13*4]
0x18001bbf4  test    edx, edx
0x18001bbf6  jz      loc_18001BEE3
0x18001bbfc  mov     rcx, [rsp+140h+var_E0]
0x18001bc01  lea     r8, [rbp+40h+rclsid]
0x18001bc05  xorps   xmm0, xmm0
0x18001bc08  mov     [rsp+140h+var_E8], 0
0x18001bc11  movups  xmmword ptr [rbp+40h+rclsid.Data1], xmm0
0x18001bc15  xor     r9d, r9d
0x18001bc18  mov     rax, [rcx]
0x18001bc1b  mov     rax, [rax+58h]
0x18001bc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc24  mov     ebx, eax
0x18001bc26  cmp     eax, 80004001h
0x18001bc2b  jnz     short loc_18001BC6B
0x18001bc2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc34  cmp     rcx, rsi
0x18001bc37  jz      short loc_18001BC63
0x18001bc39  test    byte ptr [rcx+1Ch], 10h
0x18001bc3d  jz      short loc_18001BC63
0x18001bc3f  mov     rcx, [rcx+10h]
0x18001bc43  lea     r10, qword_18003D0A0
0x18001bc4a  mov     r9d, [r10+r13*4]
0x18001bc4e  mov     edx, 0Dh
0x18001bc53  mov     r8, r14
0x18001bc56  mov     dword ptr [rsp+140h+ppv], 80004001h
0x18001bc5e  call    WPP_SF_DD
0x18001bc63  inc     r13d
0x18001bc66  jmp     loc_18001BBE4
0x18001bc6b  test    eax, eax
0x18001bc6d  js      loc_18001BE7C
0x18001bc73  lea     rax, [rsp+140h+var_E8]
0x18001bc78  xor     edx, edx; pUnkOuter
0x18001bc7a  lea     r9, IID_IPXWizardTypeCOMWrapper; riid
0x18001bc81  mov     [rsp+140h+ppv], rax; ppv
0x18001bc86  mov     r8d, 401h; dwClsContext
0x18001bc8c  lea     rcx, [rbp+40h+rclsid]; rclsid
0x18001bc90  call    cs:__imp_CoCreateInstance
0x18001bc96  mov     ebx, eax
0x18001bc98  test    eax, eax
0x18001bc9a  js      loc_18001BE11
0x18001bca0  mov     rcx, [rsp+140h+var_E8]
0x18001bca5  lea     r10, qword_18003D0A0
0x18001bcac  mov     r9, [rbp+40h+var_C0]
0x18001bcb0  lea     r8, [rsp+140h+pv]
0x18001bcb5  xor     eax, eax
0x18001bcb7  mov     [rsp+140h+pv], 0
0x18001bcc0  mov     [rsp+140h+var_F8], 0
0x18001bcc9  test    rdi, rdi
0x18001bccc  mov     rdx, [rcx]
0x18001bccf  cmovnz  r8, rax
0x18001bcd3  mov     rax, [rdx+18h]
0x18001bcd7  lea     rdx, [rsp+140h+var_F8]
0x18001bcdc  mov     [rsp+140h+var_110], rdx
0x18001bce1  mov     edx, [r10+r13*4]
0x18001bce5  mov     [rsp+140h+var_118], r8
0x18001bcea  mov     r8, [rsp+140h+rguid]
0x18001bcef  mov     [rsp+140h+ppv], r12
0x18001bcf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcf9  mov     ebx, eax
0x18001bcfb  test    eax, eax
0x18001bcfd  jnz     loc_18001BDC2
0x18001bd03  xor     r12d, r12d
0x18001bd06  mov     [rsp+140h+var_D0], r12
0x18001bd0b  cmp     [rsp+140h+var_F0], r12
0x18001bd10  jnz     short loc_18001BD43
0x18001bd12  test    rdi, rdi
0x18001bd15  jnz     short loc_18001BD73
0x18001bd17  mov     rcx, [rsp+140h+rguid]; rguid
0x18001bd1c  lea     r8d, [rax+28h]; cchMax
0x18001bd20  lea     rdx, [rbp+40h+sz]; lpsz
0x18001bd24  call    cs:__imp_StringFromGUID2
0x18001bd2a  lea     rdx, [rsp+140h+var_D0]; unsigned __int16 **
0x18001bd2f  lea     rcx, [rbp+40h+sz]; unsigned __int16 *
0x18001bd33  call    ?HrVerifyCOMRegistration@@YAJQEAGQEAPEAG@Z; HrVerifyCOMRegistration(ushort * const,ushort * * const)
0x18001bd38  mov     ebx, eax
0x18001bd3a  test    eax, eax
0x18001bd3c  js      short loc_18001BDA7
0x18001bd3e  mov     r12, [rsp+140h+var_D0]
0x18001bd43  test    rdi, rdi
0x18001bd46  jnz     short loc_18001BD73
0x18001bd48  mov     ecx, 150h; cb
0x18001bd4d  call    cs:__imp_CoTaskMemAlloc
0x18001bd53  mov     rdi, rax
0x18001bd56  test    rax, rax
0x18001bd59  jz      short loc_18001BDD8
0x18001bd5b  xor     edx, edx; Val
0x18001bd5d  mov     r8d, 150h; Size
0x18001bd63  mov     rcx, rax; void *
0x18001bd66  call    memset_0
0x18001bd6b  mov     rax, [rsp+140h+var_C8]
0x18001bd70  mov     [rax], rdi
0x18001bd73  lea     rax, qword_18003D0A0
0x18001bd7a  mov     eax, [rax+r13*4]
0x18001bd7e  mov     [rdi], eax
0x18001bd80  mov     rax, [rsp+140h+pv]
0x18001bd85  test    rax, rax
0x18001bd88  jz      short loc_18001BD92
0x18001bd8a  movups  xmm0, xmmword ptr [rax]
0x18001bd8d  movdqu  xmmword ptr [rdi+4], xmm0
0x18001bd92  mov     rax, [rsp+140h+var_F8]
0x18001bd97  movups  xmm0, xmmword ptr [rax]
0x18001bd9a  mov     [rdi+28h], r12
0x18001bd9e  movdqu  xmmword ptr [rdi+14h], xmm0
0x18001bda3  add     rdi, 30h ; '0'
0x18001bda7  mov     rcx, [rsp+140h+pv]; pv
0x18001bdac  call    cs:__imp_CoTaskMemFree
0x18001bdb2  mov     rcx, [rsp+140h+var_F8]; pv
0x18001bdb7  call    cs:__imp_CoTaskMemFree
0x18001bdbd  mov     r12, [rsp+140h+var_F0]
0x18001bdc2  mov     rcx, [rsp+140h+var_E8]
0x18001bdc7  mov     rax, [rcx]
0x18001bdca  mov     rax, [rax+10h]
0x18001bdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdd3  jmp     loc_18001BE68
0x18001bdd8  mov     rcx, r12; pv
0x18001bddb  call    cs:__imp_CoTaskMemFree
0x18001bde1  mov     ebx, 8007000Eh
0x18001bde6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bded  cmp     rcx, rsi
0x18001bdf0  jz      short loc_18001BDA7
0x18001bdf2  test    byte ptr [rcx+1Ch], 4
0x18001bdf6  jz      short loc_18001BDA7
0x18001bdf8  mov     rcx, [rcx+10h]
0x18001bdfc  mov     edx, 0Fh
0x18001be01  mov     r9d, 8007000Eh
0x18001be07  mov     r8, r14
0x18001be0a  call    WPP_SF_d
0x18001be0f  jmp     short loc_18001BDA7
0x18001be11  cmp     eax, 80004002h
0x18001be16  jnz     short loc_18001BE56
0x18001be18  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be1f  cmp     rcx, rsi
0x18001be22  jz      short loc_18001BE4E
0x18001be24  test    byte ptr [rcx+1Ch], 10h
0x18001be28  jz      short loc_18001BE4E
0x18001be2a  mov     rcx, [rcx+10h]
0x18001be2e  lea     rax, qword_18003D0A0
0x18001be35  mov     r9d, [rax+r13*4]
0x18001be39  mov     edx, 10h
0x18001be3e  mov     r8, r14
0x18001be41  mov     dword ptr [rsp+140h+ppv], 80004002h
0x18001be49  call    WPP_SF_DD
0x18001be4e  inc     r13d
0x18001be51  jmp     loc_18001BBE4
0x18001be56  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be5d  cmp     rcx, rsi
0x18001be60  jz      short loc_18001BE68
0x18001be62  test    byte ptr [rcx+1Ch], 4
0x18001be66  jnz     short loc_18001BE75
0x18001be68  inc     r13d
0x18001be6b  test    ebx, ebx
0x18001be6d  jns     loc_18001BBE9
0x18001be73  jmp     short loc_18001BEAE
0x18001be75  mov     edx, 11h
0x18001be7a  jmp     short loc_18001BE93
0x18001be7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be83  cmp     rcx, rsi
0x18001be86  jz      short loc_18001BEAE
0x18001be88  test    byte ptr [rcx+1Ch], 4
0x18001be8c  jz      short loc_18001BEAE
0x18001be8e  mov     edx, 0Eh
0x18001be93  mov     rcx, [rcx+10h]
0x18001be97  mov     r8, r14
0x18001be9a  mov     dword ptr [rsp+140h+ppv], eax
0x18001be9e  lea     rax, qword_18003D0A0
0x18001bea5  mov     r9d, [rax+r13*4]
0x18001bea9  call    WPP_SF_DD
0x18001beae  mov     r12, [rsp+140h+var_C8]
0x18001beb3  mov     rdi, [r12]
0x18001beb7  test    rdi, rdi
0x18001beba  jz      short loc_18001BED1
0x18001bebc  cmp     dword ptr [rdi], 0
0x18001bebf  jz      short loc_18001BED1
0x18001bec1  mov     rcx, [rdi+28h]; pv
0x18001bec5  call    cs:__imp_CoTaskMemFree
0x18001becb  add     rdi, 30h ; '0'
0x18001becf  jnz     short loc_18001BEBC
0x18001bed1  mov     rcx, [r12]; pv
0x18001bed5  call    cs:__imp_CoTaskMemFree
0x18001bedb  mov     qword ptr [r12], 0
0x18001bee3  mov     rcx, [rsp+140h+var_E0]
0x18001bee8  mov     rax, [rcx]
0x18001beeb  mov     rax, [rax+10h]
0x18001beef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bef4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001befb  cmp     rcx, rsi
0x18001befe  jz      short loc_18001BF1A
0x18001bf00  test    byte ptr [rcx+1Ch], 10h
0x18001bf04  jz      short loc_18001BF1A
0x18001bf06  mov     edx, 12h
0x18001bf0b  mov     r8, r14
0x18001bf0e  mov     rcx, [rcx+10h]
0x18001bf12  mov     r9d, ebx
0x18001bf15  call    WPP_SF_d
0x18001bf1a  mov     eax, ebx
0x18001bf1c  mov     rcx, [rbp+40h+var_50]
0x18001bf20  xor     rcx, rsp; StackCookie
0x18001bf23  call    __security_check_cookie
0x18001bf28  add     rsp, 108h
0x18001bf2f  pop     r15
0x18001bf31  pop     r14
0x18001bf33  pop     r13
0x18001bf35  pop     r12
0x18001bf37  pop     rdi
0x18001bf38  pop     rsi
0x18001bf39  pop     rbx
0x18001bf3a  pop     rbp
0x18001bf3b  retn
```
