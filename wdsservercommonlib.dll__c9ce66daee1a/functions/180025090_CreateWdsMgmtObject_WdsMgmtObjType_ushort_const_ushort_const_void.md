# CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)

- ea: `0x180025090`
- end: `0x1800255f5`
- name: `?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z`
- size: `1381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025090`

## callees

- `0x180025090`
- `0x18002f3e0`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800250ec`
- `OLEAUT32!__imp_SysAllocString` at `0x180025110`
- `OLEAUT32!__imp_SysAllocString` at `0x180025133`
- `OLEAUT32!__imp_SysAllocString` at `0x1800250ec`
- `OLEAUT32!__imp_SysAllocString` at `0x180025110`
- `OLEAUT32!__imp_SysAllocString` at `0x180025133`
- `OLEAUT32!__imp_SysFreeString` at `0x180025537`
- `OLEAUT32!__imp_SysFreeString` at `0x18002554b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002555f`
- `OLEAUT32!__imp_SysFreeString` at `0x180025537`
- `OLEAUT32!__imp_SysFreeString` at `0x18002554b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002555f`
- `OLE32!CoCreateInstance` at `0x180025324`
- `OLE32!CoCreateInstance` at `0x180025324`
- `OLE32!CLSIDFromProgID` at `0x1800252f8`
- `OLE32!CLSIDFromProgID` at `0x180025340`
- `OLE32!CLSIDFromProgID` at `0x18002546d`
- `OLE32!CLSIDFromProgID` at `0x1800252f8`
- `OLE32!CLSIDFromProgID` at `0x180025340`
- `OLE32!CLSIDFromProgID` at `0x18002546d`

## string_xrefs

- `0x1800252f1`: `WdsMgmt.WdsDirectoryServicesManager`

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
0x180025090  mov     [rsp-38h+arg_0], rbx
0x180025095  push    rbp
0x180025096  push    rsi
0x180025097  push    rdi
0x180025098  push    r12
0x18002509a  push    r13
0x18002509c  push    r14
0x18002509e  push    r15
0x1800250a0  mov     rbp, rsp
0x1800250a3  sub     rsp, 70h
0x1800250a7  mov     rax, cs:__security_cookie
0x1800250ae  xor     rax, rsp
0x1800250b1  mov     [rbp+var_10], rax
0x1800250b5  and     [rbp+var_38], 0
0x1800250ba  xor     r15d, r15d
0x1800250bd  and     [rbp+var_30], 0
0x1800250c2  xor     r13d, r13d
0x1800250c5  and     [rbp+var_40], 0
0x1800250ca  xor     r12d, r12d
0x1800250cd  and     [rbp+var_28], 0
0x1800250d2  xorps   xmm0, xmm0
0x1800250d5  mov     r14, r9
0x1800250d8  mov     rbx, r8
0x1800250db  mov     rsi, rdx
0x1800250de  mov     edi, ecx
0x1800250e0  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x1800250e4  test    rdx, rdx
0x1800250e7  jz      short loc_180025108
0x1800250e9  mov     rcx, rdx; psz
0x1800250ec  call    cs:__imp_SysAllocString
0x1800250f3  nop     dword ptr [rax+rax+00h]
0x1800250f8  mov     r15, rax
0x1800250fb  test    rax, rax
0x1800250fe  jnz     short loc_180025108
0x180025100  lea     ebx, [rax+8]
0x180025103  jmp     loc_18002556B
0x180025108  test    rbx, rbx
0x18002510b  jz      short loc_18002512C
0x18002510d  mov     rcx, rbx; psz
0x180025110  call    cs:__imp_SysAllocString
0x180025117  nop     dword ptr [rax+rax+00h]
0x18002511c  mov     r13, rax
0x18002511f  test    rax, rax
0x180025122  jnz     short loc_18002512C
0x180025124  lea     ebx, [rax+8]
0x180025127  jmp     loc_18002552F
0x18002512c  lea     rcx, psz; psz
0x180025133  call    cs:__imp_SysAllocString
0x18002513a  nop     dword ptr [rax+rax+00h]
0x18002513f  mov     r12, rax
0x180025142  mov     ebx, 8
0x180025147  test    rax, rax
0x18002514a  jz      loc_18002552F
0x180025150  cmp     edi, ebx
0x180025152  jg      loc_180025395
0x180025158  jz      loc_18002535F
0x18002515e  test    edi, edi
0x180025160  jz      loc_180025335
0x180025166  sub     edi, 1
0x180025169  jz      loc_1800252ED
0x18002516f  sub     edi, 1
0x180025172  jz      loc_1800252CA
0x180025178  sub     edi, 1
0x18002517b  jz      loc_180025269
0x180025181  sub     edi, 1
0x180025184  jz      loc_180025233
0x18002518a  sub     edi, 1
0x18002518d  jz      short loc_180025208
0x18002518f  sub     edi, 1
0x180025192  jz      short loc_1800251D2
0x180025194  cmp     edi, 1
0x180025197  jnz     loc_1800253FE
0x18002519d  test    rsi, rsi
0x1800251a0  jz      loc_1800253FE
0x1800251a6  lea     r9, [rbp+var_40]
0x1800251aa  xor     r8d, r8d
0x1800251ad  mov     rdx, rsi
0x1800251b0  lea     ecx, [rbx-5]
0x1800251b3  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800251b8  mov     ebx, eax
0x1800251ba  test    eax, eax
0x1800251bc  jnz     loc_18002552F
0x1800251c2  mov     rcx, [rbp+var_40]
0x1800251c6  mov     rax, [rcx]
0x1800251c9  mov     rax, [rax+48h]
0x1800251cd  jmp     loc_180025512
0x1800251d2  xor     edx, edx
0x1800251d4  lea     r9, [rbp+var_30]
0x1800251d8  xor     r8d, r8d
0x1800251db  lea     ecx, [rdx+1]
0x1800251de  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800251e3  mov     ebx, eax
0x1800251e5  test    eax, eax
0x1800251e7  jnz     loc_18002552F
0x1800251ed  mov     rcx, [rbp+var_30]
0x1800251f1  mov     rdx, r12
0x1800251f4  mov     rax, [rcx]
0x1800251f7  mov     rax, [rax+60h]
0x1800251fb  mov     r8, r14
0x1800251fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025203  jmp     loc_18002551A
0x180025208  xor     edx, edx
0x18002520a  lea     r9, [rbp+var_30]
0x18002520e  xor     r8d, r8d
0x180025211  lea     ecx, [rdx+1]
0x180025214  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x180025219  mov     ebx, eax
0x18002521b  test    eax, eax
0x18002521d  jnz     loc_18002552F
0x180025223  mov     rcx, [rbp+var_30]
0x180025227  mov     rdx, r15
0x18002522a  mov     rax, [rcx]
0x18002522d  mov     rax, [rax+78h]
0x180025231  jmp     short loc_1800251FB
0x180025233  test    rsi, rsi
0x180025236  jz      loc_1800253FE
0x18002523c  xor     r8d, r8d
0x18002523f  lea     r9, [rbp+var_40]
0x180025243  mov     rdx, rsi
0x180025246  lea     ecx, [r8+3]
0x18002524a  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002524f  mov     ebx, eax
0x180025251  test    eax, eax
0x180025253  jnz     loc_18002552F
0x180025259  mov     rcx, [rbp+var_40]
0x18002525d  mov     rax, [rcx]
0x180025260  mov     rax, [rax+78h]
0x180025264  jmp     loc_180025512
0x180025269  test    r15, r15
0x18002526c  jnz     short loc_180025278
0x18002526e  mov     ebx, 57h ; 'W'
0x180025273  jmp     loc_180025543
0x180025278  lea     r9, [rbp+var_38]
0x18002527c  xor     r8d, r8d
0x18002527f  xor     edx, edx
0x180025281  xor     ecx, ecx
0x180025283  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x180025288  mov     ebx, eax
0x18002528a  test    eax, eax
0x18002528c  jnz     loc_180025534
0x180025292  mov     rcx, [rbp+var_38]
0x180025296  mov     rax, [rcx]
0x180025299  mov     r8, r14
0x18002529c  mov     rdx, r15
0x18002529f  mov     rax, [rax+38h]
0x1800252a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252a8  mov     ebx, eax
0x1800252aa  test    eax, eax
0x1800252ac  jns     loc_180025534
0x1800252b2  and     eax, 1FFF0000h
0x1800252b7  cmp     eax, 70000h
0x1800252bc  jnz     loc_180025534
0x1800252c2  movzx   ebx, bx
0x1800252c5  jmp     loc_180025534
0x1800252ca  lea     r9, [rbp+var_38]
0x1800252ce  xor     r8d, r8d
0x1800252d1  xor     edx, edx
0x1800252d3  xor     ecx, ecx
0x1800252d5  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800252da  mov     ebx, eax
0x1800252dc  test    eax, eax
0x1800252de  jnz     loc_18002552F
0x1800252e4  mov     rcx, [rbp+var_38]
0x1800252e8  jmp     loc_1800251C6
0x1800252ed  lea     rdx, [rbp+clsid]; lpclsid
0x1800252f1  lea     rcx, szProgID; "WdsMgmt.WdsDirectoryServicesManager"
0x1800252f8  call    cs:__imp_CLSIDFromProgID
0x1800252ff  nop     dword ptr [rax+rax+00h]
0x180025304  mov     ebx, eax
0x180025306  test    eax, eax
0x180025308  js      loc_180025520
0x18002530e  lea     r9, _GUID_56320c0b_a60a_4dcd_96eb_23527ae351e0; riid
0x180025315  xor     edx, edx; pUnkOuter
0x180025317  mov     [rsp+70h+ppv], r14; ppv
0x18002531c  lea     rcx, [rbp+clsid]; rclsid
0x180025320  lea     r8d, [rdx+1]; dwClsContext
0x180025324  call    cs:__imp_CoCreateInstance
0x18002532b  nop     dword ptr [rax+rax+00h]
0x180025330  jmp     loc_18002551A
0x180025335  lea     rdx, [rbp+clsid]; lpclsid
0x180025339  lea     rcx, aWdsmgmtWdsmana; "WdsMgmt.WdsManager"
0x180025340  call    cs:__imp_CLSIDFromProgID
0x180025347  nop     dword ptr [rax+rax+00h]
0x18002534c  mov     ebx, eax
0x18002534e  test    eax, eax
0x180025350  js      loc_180025520
0x180025356  lea     r9, _GUID_f5c420af_ced9_4b92_809b_9debd7e32b03
0x18002535d  jmp     short loc_180025315
0x18002535f  test    rsi, rsi
0x180025362  jz      loc_1800253FE
0x180025368  xor     r8d, r8d
0x18002536b  lea     r9, [rbp+var_40]
0x18002536f  mov     rdx, rsi
0x180025372  lea     ecx, [r8+3]
0x180025376  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002537b  mov     ebx, eax
0x18002537d  test    eax, eax
0x18002537f  jnz     loc_18002552F
0x180025385  mov     rcx, [rbp+var_40]
0x180025389  mov     rax, [rcx]
0x18002538c  mov     rax, [rax+50h]
0x180025390  jmp     loc_180025512
0x180025395  sub     edi, 9
0x180025398  jz      loc_1800254E5
0x18002539e  sub     edi, 1
0x1800253a1  jz      loc_1800254B6
0x1800253a7  sub     edi, 1
0x1800253aa  jz      loc_18002548F
0x1800253b0  sub     edi, 1
0x1800253b3  jz      loc_180025462
0x1800253b9  sub     edi, 1
0x1800253bc  jz      short loc_180025435
0x1800253be  sub     edi, 1
0x1800253c1  jz      short loc_1800253F9
0x1800253c3  cmp     edi, 1
0x1800253c6  jnz     short loc_1800253FE
0x1800253c8  test    rsi, rsi
0x1800253cb  jz      short loc_1800253FE
0x1800253cd  lea     r9, [rbp+var_40]
0x1800253d1  xor     r8d, r8d
0x1800253d4  mov     rdx, rsi
0x1800253d7  lea     ecx, [rdi+2]
0x1800253da  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800253df  mov     ebx, eax
0x1800253e1  test    eax, eax
0x1800253e3  jnz     loc_18002552F
0x1800253e9  mov     rcx, [rbp+var_40]
0x1800253ed  mov     rax, [rcx]
0x1800253f0  mov     rax, [rax+70h]
0x1800253f4  jmp     loc_180025512
0x1800253f9  test    rsi, rsi
0x1800253fc  jnz     short loc_180025408
0x1800253fe  mov     ebx, 57h ; 'W'
0x180025403  jmp     loc_18002552F
0x180025408  xor     r8d, r8d
0x18002540b  lea     r9, [rbp+var_40]
0x18002540f  mov     rdx, rsi
0x180025412  lea     ecx, [r8+3]
0x180025416  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002541b  mov     ebx, eax
0x18002541d  test    eax, eax
0x18002541f  jnz     loc_18002552F
0x180025425  mov     rcx, [rbp+var_40]
0x180025429  mov     rax, [rcx]
0x18002542c  mov     rax, [rax+68h]
0x180025430  jmp     loc_180025512
0x180025435  test    r15, r15
0x180025438  jz      loc_18002526E
0x18002543e  xor     edx, edx
0x180025440  lea     r9, [rbp+var_28]
0x180025444  xor     r8d, r8d
0x180025447  lea     ecx, [rdx+0Ch]
0x18002544a  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002544f  mov     ebx, eax
0x180025451  test    eax, eax
0x180025453  jnz     loc_180025534
0x180025459  mov     rcx, [rbp+var_28]
0x18002545d  jmp     loc_180025296
0x180025462  lea     rdx, [rbp+clsid]; lpclsid
0x180025466  lea     rcx, aWdstptmgmtWdst; "WdsTptMgmt.WdsTransportManager"
0x18002546d  call    cs:__imp_CLSIDFromProgID
0x180025474  nop     dword ptr [rax+rax+00h]
0x180025479  mov     ebx, eax
0x18002547b  test    eax, eax
0x18002547d  js      loc_180025520
0x180025483  lea     r9, _GUID_5b0d35f5_1b13_4afd_b878_6526dc340b5d
0x18002548a  jmp     loc_180025315
0x18002548f  lea     r9, [rbp+var_38]
0x180025493  xor     r8d, r8d
0x180025496  xor     edx, edx
0x180025498  xor     ecx, ecx
0x18002549a  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x18002549f  mov     ebx, eax
0x1800254a1  test    eax, eax
0x1800254a3  jnz     loc_18002552F
0x1800254a9  mov     rcx, [rbp+var_38]
0x1800254ad  mov     rax, [rcx]
0x1800254b0  mov     rax, [rax+40h]
0x1800254b4  jmp     short loc_180025512
0x1800254b6  test    rsi, rsi
0x1800254b9  jz      loc_1800253FE
0x1800254bf  xor     r8d, r8d
0x1800254c2  lea     r9, [rbp+var_40]
0x1800254c6  mov     rdx, rsi
0x1800254c9  lea     ecx, [r8+3]
0x1800254cd  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
0x1800254d2  mov     ebx, eax
0x1800254d4  test    eax, eax
0x1800254d6  jnz     short loc_18002552F
0x1800254d8  mov     rcx, [rbp+var_40]
0x1800254dc  mov     rax, [rcx]
0x1800254df  mov     rax, [rax+60h]
0x1800254e3  jmp     short loc_180025512
0x1800254e5  test    rsi, rsi
0x1800254e8  jz      loc_1800253FE
0x1800254ee  xor     r8d, r8d
0x1800254f1  lea     r9, [rbp+var_40]
0x1800254f5  mov     rdx, rsi
0x1800254f8  lea     ecx, [r8+3]
0x1800254fc  call    ?CreateWdsMgmtObject@@YAKW4WdsMgmtObjType@@PEBG1PEAPEAX@Z; CreateWdsMgmtObject(WdsMgmtObjType,ushort const *,ushort const *,void * *)
  ... truncated ...
```
