# ProfileInfo::CreateProfile(void)

- ea: `0x180023550`
- end: `0x1800236c4`
- name: `?CreateProfile@ProfileInfo@@QEAAJXZ`
- size: `372`
- prototype: `__int64 __fastcall(GUID *pInterfaceGuid)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800236d0`

## callees

- `0x180003458`
- `0x1800077dc`
- `0x18000b888`
- `0x18000cdcc`
- `0x180020bac`
- `0x180023550`
- `0x180025a00`
- `0x1800262e4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023621`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023621`
- `OLEAUT32!__imp_SysFreeString` at `0x180023655`
- `OLEAUT32!__imp_SysFreeString` at `0x180023655`

## pseudocode

```c
__int64 __fastcall ProfileInfo::CreateProfile(GUID *pInterfaceGuid)
{
  const OLECHAR **v2; // r14
  WTL::CString *Data4; // rsi
  int Profile; // ebx
  unsigned __int16 v5; // bx
  const unsigned __int16 *v6; // rax
  unsigned __int16 *Buffer; // rax
  __int64 i; // rdx
  bool v10; // [rsp+38h] [rbp-28h]
  bool v11; // [rsp+40h] [rbp-20h]
  BSTR bstrString; // [rsp+80h] [rbp+20h] BYREF
  __int64 v13; // [rsp+88h] [rbp+28h] BYREF

  v13 = 0;
  v2 = (const OLECHAR **)&pInterfaceGuid[2];
  Data4 = (WTL::CString *)pInterfaceGuid[1].Data4;
  Profile = CreateProfile(
              pInterfaceGuid,
              (const struct WTL::CString *)&pInterfaceGuid[1],
              (const struct WTL::CString *)pInterfaceGuid[1].Data4,
              *(_DWORD *)pInterfaceGuid[2].Data4,
              (enum _DOT11_CIPHER_ALGORITHM)*(_DWORD *)&pInterfaceGuid[2].Data4[4],
              pInterfaceGuid[3].Data1,
              BYTE1(pInterfaceGuid[3].Data1),
              v10,
              v11,
              pInterfaceGuid[3].Data3,
              (struct WTL::CString *)&pInterfaceGuid[2]);
  if ( Profile >= 0 && HIBYTE(pInterfaceGuid[3].Data1) )
  {
    if ( pInterfaceGuid[3].Data4[0] )
    {
      bstrString = 0;
      Profile = ATL::AtlGetGITPtr((LPVOID *)&bstrString);
      if ( Profile >= 0 )
        Profile = (*(__int64 (__fastcall **)(BSTR, _QWORD, GUID *, __int64 *))(*(_QWORD *)bstrString + 40LL))(
                    bstrString,
                    pInterfaceGuid[4].Data1,
                    &GUID_f9f55e6b_65cc_43b3_9e39_f62bd18b0b9a,
                    &v13);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&bstrString);
      if ( Profile >= 0 && v13 )
      {
        v5 = -(BYTE2(pInterfaceGuid[3].Data1) != 0);
        v6 = SysAllocStringLen(*v2, *((_DWORD *)*v2 - 2));
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v6);
        Profile = (*(__int64 (__fastcall **)(__int64, GUID *, BSTR, _QWORD))(*(_QWORD *)v13 + 64LL))(
                    v13,
                    pInterfaceGuid,
                    bstrString,
                    v5);
        SysFreeString(bstrString);
      }
    }
    else
    {
      Profile = SaveProfile(pInterfaceGuid, v2, BYTE2(pInterfaceGuid[3].Data1));
    }
  }
  Buffer = WTL::CString::GetBuffer(Data4, 0);
  if ( Buffer )
  {
    if ( *(_DWORD *)(*(_QWORD *)Data4 - 8LL) )
    {
      for ( i = 2LL * *(int *)(*(_QWORD *)Data4 - 8LL); i; --i )
      {
        *(_BYTE *)Buffer = 0;
        Buffer = (unsigned __int16 *)((char *)Buffer + 1);
      }
    }
  }
  WTL::CString::ReleaseBuffer(Data4, i);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  return (unsigned int)Profile;
}

```

## disassembly

```asm
0x180023550  mov     [rsp-18h+arg_10], rbx
0x180023555  mov     [rsp-18h+arg_18], rsi
0x18002355a  push    rbp
0x18002355b  push    rdi
0x18002355c  push    r14
0x18002355e  mov     rbp, rsp
0x180023561  sub     rsp, 60h
0x180023565  mov     rdi, rcx
0x180023568  mov     [rbp+arg_8], 0
0x180023570  lea     r14, [rcx+20h]
0x180023574  lea     rsi, [rcx+18h]
0x180023578  lea     rdx, [rcx+10h]; struct WTL::CString *
0x18002357c  mov     [rsp+60h+var_10], r14; struct WTL::CString *
0x180023581  mov     al, [rcx+36h]
0x180023584  mov     [rsp+60h+var_18], al; bool
0x180023588  mov     al, [rcx+31h]
0x18002358b  mov     [rsp+60h+var_30], al; bool
0x18002358f  mov     al, [rcx+30h]
0x180023592  mov     [rsp+60h+var_38], al; bool
0x180023596  mov     eax, [rcx+2Ch]
0x180023599  mov     [rsp+60h+var_40], eax; enum _DOT11_CIPHER_ALGORITHM
0x18002359d  mov     r9d, [rcx+28h]; enum _DOT11_AUTH_ALGORITHM
0x1800235a1  mov     r8, rsi; struct WTL::CString *
0x1800235a4  call    ?CreateProfile@@YAJAEAU_GUID@@AEBVCString@WTL@@1W4_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@_N4444AEAV23@@Z; CreateProfile(_GUID &,WTL::CString const &,WTL::CString const &,_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,bool,bool,bool,bool,bool,WTL::CString &)
0x1800235a9  mov     ebx, eax
0x1800235ab  test    eax, eax
0x1800235ad  js      loc_18002366E
0x1800235b3  cmp     byte ptr [rdi+33h], 0
0x1800235b7  jz      loc_18002366E
0x1800235bd  cmp     byte ptr [rdi+38h], 0
0x1800235c1  jz      loc_18002365D
0x1800235c7  mov     [rbp+bstrString], 0
0x1800235cf  lea     rcx, [rbp+bstrString]; ppv
0x1800235d3  call    ?AtlGetGITPtr@ATL@@YAJPEAPEAUIGlobalInterfaceTable@@@Z; ATL::AtlGetGITPtr(IGlobalInterfaceTable * *)
0x1800235d8  mov     ebx, eax
0x1800235da  test    eax, eax
0x1800235dc  js      short loc_1800235FE
0x1800235de  mov     rcx, [rbp+bstrString]
0x1800235e2  mov     rax, [rcx]
0x1800235e5  lea     r9, [rbp+arg_8]
0x1800235e9  lea     r8, _GUID_f9f55e6b_65cc_43b3_9e39_f62bd18b0b9a
0x1800235f0  mov     edx, [rdi+40h]
0x1800235f3  mov     rax, [rax+28h]
0x1800235f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235fc  mov     ebx, eax
0x1800235fe  lea     rcx, [rbp+bstrString]
0x180023602  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023607  nop
0x180023608  test    ebx, ebx
0x18002360a  js      short loc_18002366E
0x18002360c  cmp     [rbp+arg_8], 0
0x180023611  jz      short loc_18002366E
0x180023613  mov     al, [rdi+32h]
0x180023616  neg     al
0x180023618  sbb     bx, bx
0x18002361b  mov     rcx, [r14]; strIn
0x18002361e  mov     edx, [rcx-8]; ui
0x180023621  call    cs:__imp_SysAllocStringLen
0x180023627  mov     rdx, rax; unsigned __int16 *
0x18002362a  lea     rcx, [rbp+bstrString]; this
0x18002362e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180023633  nop
0x180023634  mov     rcx, [rbp+arg_8]
0x180023638  mov     rax, [rcx]
0x18002363b  movzx   r9d, bx
0x18002363f  mov     r8, [rbp+bstrString]
0x180023643  mov     rdx, rdi
0x180023646  mov     rax, [rax+40h]
0x18002364a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002364f  mov     ebx, eax
0x180023651  mov     rcx, [rbp+bstrString]; bstrString
0x180023655  call    cs:__imp_SysFreeString
0x18002365b  jmp     short loc_18002366E
0x18002365d  mov     r8b, [rdi+32h]; bool
0x180023661  mov     rdx, r14; struct WTL::CString *
0x180023664  mov     rcx, rdi; pInterfaceGuid
0x180023667  call    ?SaveProfile@@YAJAEAU_GUID@@AEAVCString@WTL@@_N@Z; SaveProfile(_GUID &,WTL::CString &,bool)
0x18002366c  mov     ebx, eax
0x18002366e  xor     edx, edx; int
0x180023670  mov     rcx, rsi; this
0x180023673  call    ?GetBuffer@CString@WTL@@QEAAPEAGH@Z; WTL::CString::GetBuffer(int)
0x180023678  test    rax, rax
0x18002367b  jz      short loc_18002369B
0x18002367d  mov     rcx, [rsi]
0x180023680  cmp     dword ptr [rcx-8], 0
0x180023684  jz      short loc_18002369B
0x180023686  movsxd  rdx, dword ptr [rcx-8]
0x18002368a  add     rdx, rdx
0x18002368d  jz      short loc_18002369B
0x18002368f  mov     byte ptr [rax], 0
0x180023692  inc     rax
0x180023695  sub     rdx, 1; int
0x180023699  jnz     short loc_18002368F
0x18002369b  mov     rcx, rsi; this
0x18002369e  call    ?ReleaseBuffer@CString@WTL@@QEAAXH@Z; WTL::CString::ReleaseBuffer(int)
0x1800236a3  nop
0x1800236a4  lea     rcx, [rbp+arg_8]
0x1800236a8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800236ad  mov     eax, ebx
0x1800236af  lea     r11, [rsp+60h+var_s0]
0x1800236b4  mov     rbx, [r11+30h]
0x1800236b8  mov     rsi, [r11+38h]
0x1800236bc  mov     rsp, r11
0x1800236bf  pop     r14
0x1800236c1  pop     rdi
0x1800236c2  pop     rbp
0x1800236c3  retn
```
