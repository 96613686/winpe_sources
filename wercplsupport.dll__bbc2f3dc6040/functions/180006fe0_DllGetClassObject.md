# DllGetClassObject

- ea: `0x180006fe0`
- end: `0x1800071bd`
- name: `DllGetClassObject`
- size: `477`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x180006fe0`
- `0x1800073d4`
- `0x180013010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180007023`
- `RPCRT4!NdrDllGetClassObject` at `0x180007023`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  int ClassObject; // ebx
  CManagedObj *v8; // rax
  CManagedObj *v9; // rdi

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  ClassObject = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( ClassObject < 0 )
  {
    if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_WerComSupport.Data1
      && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_WerComSupport.Data4 )
    {
      v8 = (CManagedObj *)operator new(0x20u);
      v9 = v8;
      if ( v8 )
      {
        CManagedObj::CManagedObj(v8);
        *(_QWORD *)v9 = &CWerComSupportClassFactory::`vftable'{for `CManagedObj'};
        *((_QWORD *)v9 + 3) = &CWerComSupportClassFactory::`vftable'{for `IClassFactory'};
        _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
        ClassObject = (**(__int64 (__fastcall ***)(CManagedObj *, const IID *const, LPVOID *))v9)(v9, riid, ppv);
        if ( ClassObject >= 0 )
        {
          ClassObject = 0;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids,
            (unsigned int)ClassObject);
        }
        (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids);
      }
    }
    else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_ErcLUAElevationHelper.Data1
           && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_ErcLUAElevationHelper.Data4
           || *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_CEIPLUAElevationHelper.Data1
           && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_CEIPLUAElevationHelper.Data4 )
    {
      ClassObject = ((__int64 (__fastcall *)(void ***, const IID *const, LPVOID *))*CErcLuaElevationHelperClassFactory::ms_instance)(
                      &CErcLuaElevationHelperClassFactory::ms_instance,
                      riid,
                      ppv);
      if ( ClassObject >= 0 )
      {
        return 0;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids,
          (unsigned int)ClassObject);
      }
    }
  }
  return ClassObject;
}

```

## disassembly

```asm
0x180006fe0  push    rbx
0x180006fe2  push    rbp
0x180006fe3  push    rsi
0x180006fe4  push    rdi
0x180006fe5  sub     rsp, 38h
0x180006fe9  mov     rax, cs:aProxyFileList
0x180006ff0  mov     rsi, r8
0x180006ff3  mov     rbp, rdx
0x180006ff6  mov     rdi, rcx
0x180006ff9  mov     r9, [rax+8]
0x180006ffd  mov     rax, [r9]
0x180007000  test    rax, rax
0x180007003  jz      short loc_180007008
0x180007005  mov     rax, [rax]
0x180007008  lea     rcx, gPFactory
0x18000700f  mov     [rsp+58h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180007014  lea     r9, aProxyFileList; pProxyFileList
0x18000701b  mov     rcx, rdi; rclsid
0x18000701e  mov     [rsp+58h+pclsid], rax; pclsid
0x180007023  call    cs:__imp_NdrDllGetClassObject
0x180007029  mov     ebx, eax
0x18000702b  test    eax, eax
0x18000702d  jns     loc_1800071B2
0x180007033  mov     rcx, [rdi]
0x180007036  cmp     rcx, qword ptr cs:CLSID_WerComSupport.Data1
0x18000703d  jnz     loc_180007129
0x180007043  mov     rcx, [rdi+8]
0x180007047  cmp     rcx, qword ptr cs:CLSID_WerComSupport.Data4
0x18000704e  jnz     loc_180007129
0x180007054  mov     ecx, 20h ; ' '; Size
0x180007059  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000705e  mov     rdi, rax
0x180007061  test    rax, rax
0x180007064  jz      loc_1800070EE
0x18000706a  mov     rcx, rax; this
0x18000706d  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x180007072  lea     rax, ??_7CWerComSupportClassFactory@@6BCManagedObj@@@; const CWerComSupportClassFactory::`vftable'{for `CManagedObj'}
0x180007079  mov     [rdi], rax
0x18000707c  lea     rax, ??_7CWerComSupportClassFactory@@6BIClassFactory@@@; const CWerComSupportClassFactory::`vftable'{for `IClassFactory'}
0x180007083  mov     [rdi+18h], rax
0x180007087  lock inc dword ptr [rdi+8]
0x18000708b  mov     rax, [rdi]
0x18000708e  mov     r8, rsi
0x180007091  mov     rdx, rbp
0x180007094  mov     rcx, rdi
0x180007097  mov     rax, [rax]
0x18000709a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000709f  mov     ebx, eax
0x1800070a1  test    eax, eax
0x1800070a3  jns     short loc_1800070D8
0x1800070a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070ac  lea     rax, WPP_GLOBAL_Control
0x1800070b3  cmp     rcx, rax
0x1800070b6  jz      short loc_1800070DA
0x1800070b8  test    byte ptr [rcx+1Ch], 1
0x1800070bc  jz      short loc_1800070DA
0x1800070be  mov     rcx, [rcx+10h]
0x1800070c2  lea     r8, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids
0x1800070c9  mov     edx, 12h
0x1800070ce  mov     r9d, ebx
0x1800070d1  call    WPP_SF_d
0x1800070d6  jmp     short loc_1800070DA
0x1800070d8  xor     ebx, ebx
0x1800070da  mov     rax, [rdi]
0x1800070dd  mov     rcx, rdi
0x1800070e0  mov     rax, [rax+10h]
0x1800070e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070e9  jmp     loc_1800071B2
0x1800070ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070f5  lea     rax, WPP_GLOBAL_Control
0x1800070fc  cmp     rcx, rax
0x1800070ff  jz      loc_1800071B2
0x180007105  test    byte ptr [rcx+1Ch], 1
0x180007109  jz      loc_1800071B2
0x18000710f  mov     rcx, [rcx+10h]
0x180007113  lea     r8, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids
0x18000711a  mov     edx, 11h
0x18000711f  call    WPP_SF_
0x180007124  jmp     loc_1800071B2
0x180007129  mov     rax, [rdi]
0x18000712c  cmp     rax, qword ptr cs:CLSID_ErcLUAElevationHelper.Data1
0x180007133  jnz     short loc_180007142
0x180007135  mov     rax, [rdi+8]
0x180007139  cmp     rax, qword ptr cs:CLSID_ErcLUAElevationHelper.Data4
0x180007140  jz      short loc_18000715B
0x180007142  mov     rax, [rdi]
0x180007145  cmp     rax, qword ptr cs:CLSID_CEIPLUAElevationHelper.Data1
0x18000714c  jnz     short loc_1800071B2
0x18000714e  mov     rax, [rdi+8]
0x180007152  cmp     rax, qword ptr cs:CLSID_CEIPLUAElevationHelper.Data4
0x180007159  jnz     short loc_1800071B2
0x18000715b  mov     rax, cs:?ms_instance@CErcLuaElevationHelperClassFactory@@0V1@A; CErcLuaElevationHelperClassFactory CErcLuaElevationHelperClassFactory::ms_instance
0x180007162  lea     rcx, ?ms_instance@CErcLuaElevationHelperClassFactory@@0V1@A; CErcLuaElevationHelperClassFactory CErcLuaElevationHelperClassFactory::ms_instance
0x180007169  mov     r8, rsi
0x18000716c  mov     rdx, rbp
0x18000716f  mov     rax, [rax]
0x180007172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007177  mov     ebx, eax
0x180007179  test    eax, eax
0x18000717b  jns     short loc_1800071B0
0x18000717d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007184  lea     rax, WPP_GLOBAL_Control
0x18000718b  cmp     rcx, rax
0x18000718e  jz      short loc_1800071B2
0x180007190  test    byte ptr [rcx+1Ch], 1
0x180007194  jz      short loc_1800071B2
0x180007196  mov     rcx, [rcx+10h]
0x18000719a  lea     r8, WPP_42a1f46a1ffc3dae14aad533fcb30511_Traceguids
0x1800071a1  mov     edx, 13h
0x1800071a6  mov     r9d, ebx
0x1800071a9  call    WPP_SF_d
0x1800071ae  jmp     short loc_1800071B2
0x1800071b0  xor     ebx, ebx
0x1800071b2  mov     eax, ebx
0x1800071b4  add     rsp, 38h
0x1800071b8  pop     rdi
0x1800071b9  pop     rsi
0x1800071ba  pop     rbp
0x1800071bb  pop     rbx
0x1800071bc  retn
```
