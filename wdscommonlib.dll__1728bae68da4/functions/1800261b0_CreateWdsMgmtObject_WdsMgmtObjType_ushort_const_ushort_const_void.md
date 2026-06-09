# CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)

- ea: `0x1800261b0`
- end: `0x180026715`
- name: `?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z`
- size: `1381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800261b0`

## callees

- `0x1800261b0`
- `0x180030390`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002620c`
- `OLEAUT32!__imp_SysAllocString` at `0x180026230`
- `OLEAUT32!__imp_SysAllocString` at `0x180026253`
- `OLEAUT32!__imp_SysAllocString` at `0x18002620c`
- `OLEAUT32!__imp_SysAllocString` at `0x180026230`
- `OLEAUT32!__imp_SysAllocString` at `0x180026253`
- `OLEAUT32!__imp_SysFreeString` at `0x180026657`
- `OLEAUT32!__imp_SysFreeString` at `0x18002666b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002667f`
- `OLEAUT32!__imp_SysFreeString` at `0x180026657`
- `OLEAUT32!__imp_SysFreeString` at `0x18002666b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002667f`
- `OLE32!CLSIDFromProgID` at `0x180026418`
- `OLE32!CLSIDFromProgID` at `0x180026460`
- `OLE32!CLSIDFromProgID` at `0x18002658d`
- `OLE32!CLSIDFromProgID` at `0x180026418`
- `OLE32!CLSIDFromProgID` at `0x180026460`
- `OLE32!CLSIDFromProgID` at `0x18002658d`
- `OLE32!CoCreateInstance` at `0x180026444`
- `OLE32!CoCreateInstance` at `0x180026444`

## string_xrefs

- `0x180026411`: `WdsMgmt.WdsDirectoryServicesManager`

## pseudocode

```c
__int64 __fastcall CreateWdsMgmtObject(int a1, const OLECHAR *a2, const OLECHAR *a3, LPVOID *a4)
{
  OLECHAR *v4; // r15
  OLECHAR *v5; // r13
  OLECHAR *v6; // r12
  unsigned int v11; // ebx
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  int v16; // edi
  int v17; // edi
  LPVOID v18; // rcx
  HRESULT v19; // eax
  void *v20; // rcx
  int v21; // eax
  GUID *v22; // r9
  int v23; // edi
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi
  int v28; // edi
  LPVOID v30; // [rsp+30h] [rbp-40h] BYREF
  void *v31; // [rsp+38h] [rbp-38h] BYREF
  __int64 v32; // [rsp+40h] [rbp-30h] BYREF
  void *v33; // [rsp+48h] [rbp-28h] BYREF
  GUID clsid; // [rsp+50h] [rbp-20h] BYREF

  v31 = 0;
  v4 = 0;
  v32 = 0;
  v5 = 0;
  v30 = 0;
  v6 = 0;
  v33 = 0;
  clsid = 0;
  if ( a2 )
  {
    v4 = SysAllocString(a2);
    if ( !v4 )
    {
      v11 = 8;
      goto LABEL_83;
    }
  }
  if ( a3 )
  {
    v5 = SysAllocString(a3);
    if ( !v5 )
    {
      v11 = 8;
      goto LABEL_77;
    }
  }
  v6 = SysAllocString(&psz);
  v11 = 8;
  if ( v6 )
  {
    if ( a1 > 8 )
    {
      v23 = a1 - 9;
      if ( !v23 )
      {
        if ( !a2 )
          goto LABEL_58;
        v11 = CreateWdsMgmtObject(3, a2, 0, &v30);
        if ( v11 )
          goto LABEL_77;
        v19 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v30 + 88LL))(v30, a4);
        goto LABEL_74;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        if ( !a2 )
          goto LABEL_58;
        v11 = CreateWdsMgmtObject(3, a2, 0, &v30);
        if ( v11 )
          goto LABEL_77;
        v19 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v30 + 96LL))(v30, a4);
        goto LABEL_74;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v11 = CreateWdsMgmtObject(0, 0, 0, &v31);
        if ( v11 )
          goto LABEL_77;
        v19 = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v31 + 64LL))(v31, a4);
        goto LABEL_74;
      }
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 )
          {
            if ( v28 != 1 || !a2 )
              goto LABEL_58;
            v11 = CreateWdsMgmtObject(3, a2, 0, &v30);
            if ( v11 )
              goto LABEL_77;
            v19 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v30 + 112LL))(v30, a4);
          }
          else
          {
            if ( !a2 )
              goto LABEL_58;
            v11 = CreateWdsMgmtObject(3, a2, 0, &v30);
            if ( v11 )
              goto LABEL_77;
            v19 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v30 + 104LL))(v30, a4);
          }
          goto LABEL_74;
        }
        if ( !v4 )
          goto LABEL_31;
        v11 = CreateWdsMgmtObject(12, 0, 0, &v33);
        if ( !v11 )
        {
          v20 = v33;
          goto LABEL_34;
        }
LABEL_78:
        SysFreeString(v4);
        goto LABEL_79;
      }
      v19 = CLSIDFromProgID(L"WdsTptMgmt.WdsTransportManager", &clsid);
      v11 = v19;
      if ( v19 >= 0 )
      {
        v22 = &GUID_5b0d35f5_1b13_4afd_b878_6526dc340b5d;
        goto LABEL_41;
      }
    }
    else
    {
      if ( a1 == 8 )
      {
        if ( !a2 )
          goto LABEL_58;
        v11 = CreateWdsMgmtObject(3, a2, 0, &v30);
        if ( v11 )
          goto LABEL_77;
        v19 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v30 + 80LL))(v30, a4);
        goto LABEL_74;
      }
      if ( a1 )
      {
        v12 = a1 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( !v13 )
          {
            v11 = CreateWdsMgmtObject(0, 0, 0, &v31);
            if ( v11 )
              goto LABEL_77;
            v18 = v31;
            goto LABEL_21;
          }
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                v17 = v16 - 1;
                if ( v17 )
                {
                  if ( v17 == 1 && a2 )
                  {
                    v11 = CreateWdsMgmtObject(3, a2, 0, &v30);
                    if ( v11 )
                      goto LABEL_77;
                    v18 = v30;
LABEL_21:
                    v19 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v18 + 72LL))(v18, a4);
                    goto LABEL_74;
                  }
LABEL_58:
                  v11 = 87;
                  goto LABEL_77;
                }
                v11 = CreateWdsMgmtObject(1, 0, 0, &v32);
                if ( v11 )
                  goto LABEL_77;
                v19 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, LPVOID *))(*(_QWORD *)v32 + 96LL))(v32, v6, a4);
              }
              else
              {
                v11 = CreateWdsMgmtObject(1, 0, 0, &v32);
                if ( v11 )
                  goto LABEL_77;
                v19 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, LPVOID *))(*(_QWORD *)v32 + 120LL))(v32, v4, a4);
              }
            }
            else
            {
              if ( !a2 )
                goto LABEL_58;
              v11 = CreateWdsMgmtObject(3, a2, 0, &v30);
              if ( v11 )
                goto LABEL_77;
              v19 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v30 + 120LL))(v30, a4);
            }
LABEL_74:
            v11 = v19;
            if ( v19 >= 0 )
              goto LABEL_77;
            goto LABEL_75;
          }
          if ( !v4 )
          {
LABEL_31:
            v11 = 87;
            goto LABEL_79;
          }
          v11 = CreateWdsMgmtObject(0, 0, 0, &v31);
          if ( !v11 )
          {
            v20 = v31;
LABEL_34:
            v21 = (*(__int64 (__fastcall **)(void *, OLECHAR *, LPVOID *))(*(_QWORD *)v20 + 56LL))(v20, v4, a4);
            v11 = v21;
            if ( v21 < 0 && (v21 & 0x1FFF0000) == 0x70000 )
              v11 = (unsigned __int16)v21;
            goto LABEL_78;
          }
          goto LABEL_78;
        }
        v19 = CLSIDFromProgID(L"WdsMgmt.WdsDirectoryServicesManager", &clsid);
        v11 = v19;
        if ( v19 >= 0 )
        {
          v22 = &GUID_56320c0b_a60a_4dcd_96eb_23527ae351e0;
LABEL_41:
          v19 = CoCreateInstance(&clsid, 0, 1u, v22, a4);
          goto LABEL_74;
        }
      }
      else
      {
        v19 = CLSIDFromProgID(L"WdsMgmt.WdsManager", &clsid);
        v11 = v19;
        if ( v19 >= 0 )
        {
          v22 = &GUID_f5c420af_ced9_4b92_809b_9debd7e32b03;
          goto LABEL_41;
        }
      }
    }
LABEL_75:
    if ( (v19 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
  }
LABEL_77:
  if ( v4 )
    goto LABEL_78;
LABEL_79:
  if ( v5 )
    SysFreeString(v5);
  if ( v6 )
    SysFreeString(v6);
LABEL_83:
  if ( v31 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v33 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
  return v11;
}

```

## disassembly

```asm
0x1800261b0  mov     [rsp-38h+arg_0], rbx
0x1800261b5  push    rbp
0x1800261b6  push    rsi
0x1800261b7  push    rdi
0x1800261b8  push    r12
0x1800261ba  push    r13
0x1800261bc  push    r14
0x1800261be  push    r15
0x1800261c0  mov     rbp, rsp
0x1800261c3  sub     rsp, 70h
0x1800261c7  mov     rax, cs:__security_cookie
0x1800261ce  xor     rax, rsp
0x1800261d1  mov     [rbp+var_10], rax
0x1800261d5  and     [rbp+var_38], 0
0x1800261da  xor     r15d, r15d
0x1800261dd  and     [rbp+var_30], 0
0x1800261e2  xor     r13d, r13d
0x1800261e5  and     [rbp+var_40], 0
0x1800261ea  xor     r12d, r12d
0x1800261ed  and     [rbp+var_28], 0
0x1800261f2  xorps   xmm0, xmm0
0x1800261f5  mov     r14, r9
0x1800261f8  mov     rbx, r8
0x1800261fb  mov     rsi, rdx
0x1800261fe  mov     edi, ecx
0x180026200  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180026204  test    rdx, rdx
0x180026207  jz      short loc_180026228
0x180026209  mov     rcx, rdx; psz
0x18002620c  call    cs:__imp_SysAllocString
0x180026213  nop     dword ptr [rax+rax+00h]
0x180026218  mov     r15, rax
0x18002621b  test    rax, rax
0x18002621e  jnz     short loc_180026228
0x180026220  lea     ebx, [rax+8]
0x180026223  jmp     loc_18002668B
0x180026228  test    rbx, rbx
0x18002622b  jz      short loc_18002624C
0x18002622d  mov     rcx, rbx; psz
0x180026230  call    cs:__imp_SysAllocString
0x180026237  nop     dword ptr [rax+rax+00h]
0x18002623c  mov     r13, rax
0x18002623f  test    rax, rax
0x180026242  jnz     short loc_18002624C
0x180026244  lea     ebx, [rax+8]
0x180026247  jmp     loc_18002664F
0x18002624c  lea     rcx, psz; psz
0x180026253  call    cs:__imp_SysAllocString
0x18002625a  nop     dword ptr [rax+rax+00h]
0x18002625f  mov     r12, rax
0x180026262  mov     ebx, 8
0x180026267  test    rax, rax
0x18002626a  jz      loc_18002664F
0x180026270  cmp     edi, ebx
0x180026272  jg      loc_1800264B5
0x180026278  jz      loc_18002647F
0x18002627e  test    edi, edi
0x180026280  jz      loc_180026455
0x180026286  sub     edi, 1
0x180026289  jz      loc_18002640D
0x18002628f  sub     edi, 1
0x180026292  jz      loc_1800263EA
0x180026298  sub     edi, 1
0x18002629b  jz      loc_180026389
0x1800262a1  sub     edi, 1
0x1800262a4  jz      loc_180026353
0x1800262aa  sub     edi, 1
0x1800262ad  jz      short loc_180026328
0x1800262af  sub     edi, 1
0x1800262b2  jz      short loc_1800262F2
0x1800262b4  cmp     edi, 1
0x1800262b7  jnz     loc_18002651E
0x1800262bd  test    rsi, rsi
0x1800262c0  jz      loc_18002651E
0x1800262c6  lea     r9, [rbp+var_40]
0x1800262ca  xor     r8d, r8d
0x1800262cd  mov     rdx, rsi
0x1800262d0  lea     ecx, [rbx-5]
0x1800262d3  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800262d8  mov     ebx, eax
0x1800262da  test    eax, eax
0x1800262dc  jnz     loc_18002664F
0x1800262e2  mov     rcx, [rbp+var_40]
0x1800262e6  mov     rax, [rcx]
0x1800262e9  mov     rax, [rax+48h]
0x1800262ed  jmp     loc_180026632
0x1800262f2  xor     edx, edx
0x1800262f4  lea     r9, [rbp+var_30]
0x1800262f8  xor     r8d, r8d
0x1800262fb  lea     ecx, [rdx+1]
0x1800262fe  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x180026303  mov     ebx, eax
0x180026305  test    eax, eax
0x180026307  jnz     loc_18002664F
0x18002630d  mov     rcx, [rbp+var_30]
0x180026311  mov     rdx, r12
0x180026314  mov     rax, [rcx]
0x180026317  mov     rax, [rax+60h]
0x18002631b  mov     r8, r14
0x18002631e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026323  jmp     loc_18002663A
0x180026328  xor     edx, edx
0x18002632a  lea     r9, [rbp+var_30]
0x18002632e  xor     r8d, r8d
0x180026331  lea     ecx, [rdx+1]
0x180026334  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x180026339  mov     ebx, eax
0x18002633b  test    eax, eax
0x18002633d  jnz     loc_18002664F
0x180026343  mov     rcx, [rbp+var_30]
0x180026347  mov     rdx, r15
0x18002634a  mov     rax, [rcx]
0x18002634d  mov     rax, [rax+78h]
0x180026351  jmp     short loc_18002631B
0x180026353  test    rsi, rsi
0x180026356  jz      loc_18002651E
0x18002635c  xor     r8d, r8d
0x18002635f  lea     r9, [rbp+var_40]
0x180026363  mov     rdx, rsi
0x180026366  lea     ecx, [r8+3]
0x18002636a  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002636f  mov     ebx, eax
0x180026371  test    eax, eax
0x180026373  jnz     loc_18002664F
0x180026379  mov     rcx, [rbp+var_40]
0x18002637d  mov     rax, [rcx]
0x180026380  mov     rax, [rax+78h]
0x180026384  jmp     loc_180026632
0x180026389  test    r15, r15
0x18002638c  jnz     short loc_180026398
0x18002638e  mov     ebx, 57h ; 'W'
0x180026393  jmp     loc_180026663
0x180026398  lea     r9, [rbp+var_38]
0x18002639c  xor     r8d, r8d
0x18002639f  xor     edx, edx
0x1800263a1  xor     ecx, ecx
0x1800263a3  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800263a8  mov     ebx, eax
0x1800263aa  test    eax, eax
0x1800263ac  jnz     loc_180026654
0x1800263b2  mov     rcx, [rbp+var_38]
0x1800263b6  mov     rax, [rcx]
0x1800263b9  mov     r8, r14
0x1800263bc  mov     rdx, r15
0x1800263bf  mov     rax, [rax+38h]
0x1800263c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263c8  mov     ebx, eax
0x1800263ca  test    eax, eax
0x1800263cc  jns     loc_180026654
0x1800263d2  and     eax, 1FFF0000h
0x1800263d7  cmp     eax, 70000h
0x1800263dc  jnz     loc_180026654
0x1800263e2  movzx   ebx, bx
0x1800263e5  jmp     loc_180026654
0x1800263ea  lea     r9, [rbp+var_38]
0x1800263ee  xor     r8d, r8d
0x1800263f1  xor     edx, edx
0x1800263f3  xor     ecx, ecx
0x1800263f5  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800263fa  mov     ebx, eax
0x1800263fc  test    eax, eax
0x1800263fe  jnz     loc_18002664F
0x180026404  mov     rcx, [rbp+var_38]
0x180026408  jmp     loc_1800262E6
0x18002640d  lea     rdx, [rbp+clsid]; lpclsid
0x180026411  lea     rcx, szProgID; "WdsMgmt.WdsDirectoryServicesManager"
0x180026418  call    cs:__imp_CLSIDFromProgID
0x18002641f  nop     dword ptr [rax+rax+00h]
0x180026424  mov     ebx, eax
0x180026426  test    eax, eax
0x180026428  js      loc_180026640
0x18002642e  lea     r9, _GUID_56320c0b_a60a_4dcd_96eb_23527ae351e0; riid
0x180026435  xor     edx, edx; pUnkOuter
0x180026437  mov     [rsp+70h+ppv], r14; ppv
0x18002643c  lea     rcx, [rbp+clsid]; rclsid
0x180026440  lea     r8d, [rdx+1]; dwClsContext
0x180026444  call    cs:__imp_CoCreateInstance
0x18002644b  nop     dword ptr [rax+rax+00h]
0x180026450  jmp     loc_18002663A
0x180026455  lea     rdx, [rbp+clsid]; lpclsid
0x180026459  lea     rcx, aWdsmgmtWdsmana; "WdsMgmt.WdsManager"
0x180026460  call    cs:__imp_CLSIDFromProgID
0x180026467  nop     dword ptr [rax+rax+00h]
0x18002646c  mov     ebx, eax
0x18002646e  test    eax, eax
0x180026470  js      loc_180026640
0x180026476  lea     r9, _GUID_f5c420af_ced9_4b92_809b_9debd7e32b03
0x18002647d  jmp     short loc_180026435
0x18002647f  test    rsi, rsi
0x180026482  jz      loc_18002651E
0x180026488  xor     r8d, r8d
0x18002648b  lea     r9, [rbp+var_40]
0x18002648f  mov     rdx, rsi
0x180026492  lea     ecx, [r8+3]
0x180026496  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002649b  mov     ebx, eax
0x18002649d  test    eax, eax
0x18002649f  jnz     loc_18002664F
0x1800264a5  mov     rcx, [rbp+var_40]
0x1800264a9  mov     rax, [rcx]
0x1800264ac  mov     rax, [rax+50h]
0x1800264b0  jmp     loc_180026632
0x1800264b5  sub     edi, 9
0x1800264b8  jz      loc_180026605
0x1800264be  sub     edi, 1
0x1800264c1  jz      loc_1800265D6
0x1800264c7  sub     edi, 1
0x1800264ca  jz      loc_1800265AF
0x1800264d0  sub     edi, 1
0x1800264d3  jz      loc_180026582
0x1800264d9  sub     edi, 1
0x1800264dc  jz      short loc_180026555
0x1800264de  sub     edi, 1
0x1800264e1  jz      short loc_180026519
0x1800264e3  cmp     edi, 1
0x1800264e6  jnz     short loc_18002651E
0x1800264e8  test    rsi, rsi
0x1800264eb  jz      short loc_18002651E
0x1800264ed  lea     r9, [rbp+var_40]
0x1800264f1  xor     r8d, r8d
0x1800264f4  mov     rdx, rsi
0x1800264f7  lea     ecx, [rdi+2]
0x1800264fa  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800264ff  mov     ebx, eax
0x180026501  test    eax, eax
0x180026503  jnz     loc_18002664F
0x180026509  mov     rcx, [rbp+var_40]
0x18002650d  mov     rax, [rcx]
0x180026510  mov     rax, [rax+70h]
0x180026514  jmp     loc_180026632
0x180026519  test    rsi, rsi
0x18002651c  jnz     short loc_180026528
0x18002651e  mov     ebx, 57h ; 'W'
0x180026523  jmp     loc_18002664F
0x180026528  xor     r8d, r8d
0x18002652b  lea     r9, [rbp+var_40]
0x18002652f  mov     rdx, rsi
0x180026532  lea     ecx, [r8+3]
0x180026536  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002653b  mov     ebx, eax
0x18002653d  test    eax, eax
0x18002653f  jnz     loc_18002664F
0x180026545  mov     rcx, [rbp+var_40]
0x180026549  mov     rax, [rcx]
0x18002654c  mov     rax, [rax+68h]
0x180026550  jmp     loc_180026632
0x180026555  test    r15, r15
0x180026558  jz      loc_18002638E
0x18002655e  xor     edx, edx
0x180026560  lea     r9, [rbp+var_28]
0x180026564  xor     r8d, r8d
0x180026567  lea     ecx, [rdx+0Ch]
0x18002656a  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002656f  mov     ebx, eax
0x180026571  test    eax, eax
0x180026573  jnz     loc_180026654
0x180026579  mov     rcx, [rbp+var_28]
0x18002657d  jmp     loc_1800263B6
0x180026582  lea     rdx, [rbp+clsid]; lpclsid
0x180026586  lea     rcx, aWdstptmgmtWdst; "WdsTptMgmt.WdsTransportManager"
0x18002658d  call    cs:__imp_CLSIDFromProgID
0x180026594  nop     dword ptr [rax+rax+00h]
0x180026599  mov     ebx, eax
0x18002659b  test    eax, eax
0x18002659d  js      loc_180026640
0x1800265a3  lea     r9, _GUID_5b0d35f5_1b13_4afd_b878_6526dc340b5d
0x1800265aa  jmp     loc_180026435
0x1800265af  lea     r9, [rbp+var_38]
0x1800265b3  xor     r8d, r8d
0x1800265b6  xor     edx, edx
0x1800265b8  xor     ecx, ecx
0x1800265ba  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800265bf  mov     ebx, eax
0x1800265c1  test    eax, eax
0x1800265c3  jnz     loc_18002664F
0x1800265c9  mov     rcx, [rbp+var_38]
0x1800265cd  mov     rax, [rcx]
0x1800265d0  mov     rax, [rax+40h]
0x1800265d4  jmp     short loc_180026632
0x1800265d6  test    rsi, rsi
0x1800265d9  jz      loc_18002651E
0x1800265df  xor     r8d, r8d
0x1800265e2  lea     r9, [rbp+var_40]
0x1800265e6  mov     rdx, rsi
0x1800265e9  lea     ecx, [r8+3]
0x1800265ed  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800265f2  mov     ebx, eax
0x1800265f4  test    eax, eax
0x1800265f6  jnz     short loc_18002664F
0x1800265f8  mov     rcx, [rbp+var_40]
0x1800265fc  mov     rax, [rcx]
0x1800265ff  mov     rax, [rax+60h]
0x180026603  jmp     short loc_180026632
0x180026605  test    rsi, rsi
0x180026608  jz      loc_18002651E
0x18002660e  xor     r8d, r8d
0x180026611  lea     r9, [rbp+var_40]
0x180026615  mov     rdx, rsi
0x180026618  lea     ecx, [r8+3]
0x18002661c  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
  ... truncated ...
```
