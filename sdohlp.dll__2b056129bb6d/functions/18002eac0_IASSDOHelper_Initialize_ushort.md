# IASSDOHelper::Initialize(ushort *)

- ea: `0x18002eac0`
- end: `0x18002eda4`
- name: `?Initialize@IASSDOHelper@@UEAAJPEAG@Z`
- size: `740`
- prototype: `__int64 __fastcall(IASSDOHelper *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002eac0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002eb05`
- `ole32!CoCreateInstance` at `0x18002ec15`
- `ole32!CoCreateInstance` at `0x18002eb05`
- `ole32!CoCreateInstance` at `0x18002ec15`

## string_xrefs

- `0x18002eb52`: `CoCreateInstance(CLSID_GlobalOptions) failed with hr %!hresult! `
- `0x18002ebbc`: `Setting COMGLB_EXCEPTION_HANDLING failed with hr %!hresult! `
- `0x18002ec47`: `CoCi(CLSID_SdoMachine) failed with %!hresult!`

## pseudocode

```c
__int64 __fastcall IASSDOHelper::Initialize(IASSDOHelper *this, unsigned __int16 *a2)
{
  HRESULT v4; // eax
  char v5; // di
  int v6; // eax
  char v7; // di
  LPVOID *v8; // rsi
  HRESULT Instance; // edi
  int v10; // edx
  __int64 (__fastcall ***v11)(LPVOID, GUID *, __int64 *); // rcx
  int v12; // edx
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+18h] BYREF

  ppv = 0;
  v4 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 1);
    v7 = v6;
    if ( v6 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Setting COMGLB_EXCEPTION_HANDLING failed with hr %!hresult! ");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
        (unsigned int)"NPSSDO",
        v7);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("CoCreateInstance(CLSID_GlobalOptions) failed with hr %!hresult! ");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
      (unsigned int)"NPSSDO",
      v5);
  }
  v8 = (LPVOID *)((char *)this + 72);
  Instance = CoCreateInstance(&CLSID_SdoMachine, 0, 1u, &IID_ISdoMachine, v8);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("CoCi(CLSID_SdoMachine) failed with %!hresult!");
      v10 = 12;
LABEL_17:
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
        (unsigned int)"NPSSDO",
        Instance);
      return (unsigned int)Instance;
    }
    return (unsigned int)Instance;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)*v8 + 56LL))(*v8, a2);
  if ( Instance >= 0 )
  {
    v11 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))*v8;
    v14 = 0;
    Instance = (**v11)(v11, &GUID_518e5ffe_d8ce_4f7e_a5db_b40a35419d3b, &v14);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14);
      if ( Instance >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_34;
      }
      WppDbgPrint("pSdoMachine2->Reload failed with %!hresult!");
      v12 = 15;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_34;
      }
      WppDbgPrint("m_pMachine->QueryInterface(ISdoMachine2) failed with %!hresult!");
      v12 = 14;
    }
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
      (unsigned int)"NPSSDO",
      Instance);
LABEL_34:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
    return (unsigned int)Instance;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("m_pMachine->Attach failed with %!hresult!");
    v10 = 13;
    goto LABEL_17;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002eac0  mov     r11, rsp
0x18002eac3  mov     [r11+10h], rbx
0x18002eac7  mov     [r11+20h], rbp
0x18002eacb  push    rsi
0x18002eacc  push    rdi
0x18002eacd  push    r12
0x18002eacf  push    r13
0x18002ead1  push    r15
0x18002ead3  sub     rsp, 30h
0x18002ead7  mov     rbp, rdx
0x18002eada  mov     qword ptr [r11+18h], 0
0x18002eae2  mov     rsi, rcx
0x18002eae5  lea     rax, [r11+18h]
0x18002eae9  mov     ebx, 1
0x18002eaee  mov     [r11-38h], rax
0x18002eaf2  mov     r8d, ebx; dwClsContext
0x18002eaf5  lea     r9, IID_IGlobalOptions; riid
0x18002eafc  xor     edx, edx; pUnkOuter
0x18002eafe  lea     rcx, CLSID_GlobalOptions; rclsid
0x18002eb05  call    cs:__imp_CoCreateInstance
0x18002eb0b  mov     r15d, 400h
0x18002eb11  lea     r12, aNpssdo; "NPSSDO"
0x18002eb18  lea     r13, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002eb1f  mov     edi, eax
0x18002eb21  test    eax, eax
0x18002eb23  jns     short loc_18002EB7F
0x18002eb25  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb2c  lea     rbx, WPP_GLOBAL_Control
0x18002eb33  cmp     rcx, rbx
0x18002eb36  jz      loc_18002EBF8
0x18002eb3c  cmp     byte ptr [rcx+19h], 2
0x18002eb40  jb      loc_18002EBF8
0x18002eb46  test    [rcx+1Ch], r15d
0x18002eb4a  jz      loc_18002EBF8
0x18002eb50  mov     edx, eax
0x18002eb52  lea     rcx, aCocreateinstan; "CoCreateInstance(CLSID_GlobalOptions) f"...
0x18002eb59  call    WppDbgPrint
0x18002eb5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb65  mov     edx, 0Ah
0x18002eb6a  mov     r9, r12
0x18002eb6d  mov     dword ptr [rsp+58h+ppv], edi
0x18002eb71  mov     r8, r13
0x18002eb74  mov     rcx, [rcx+10h]
0x18002eb78  call    WPP_SF_sd
0x18002eb7d  jmp     short loc_18002EBF8
0x18002eb7f  mov     rcx, [rsp+58h+arg_10]
0x18002eb84  mov     r8, rbx
0x18002eb87  mov     edx, ebx
0x18002eb89  mov     rax, [rcx]
0x18002eb8c  mov     rax, [rax+18h]
0x18002eb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb95  lea     rbx, WPP_GLOBAL_Control
0x18002eb9c  mov     edi, eax
0x18002eb9e  test    eax, eax
0x18002eba0  jns     short loc_18002EBE7
0x18002eba2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eba9  cmp     rcx, rbx
0x18002ebac  jz      short loc_18002EBE7
0x18002ebae  cmp     byte ptr [rcx+19h], 2
0x18002ebb2  jb      short loc_18002EBE7
0x18002ebb4  test    [rcx+1Ch], r15d
0x18002ebb8  jz      short loc_18002EBE7
0x18002ebba  mov     edx, eax
0x18002ebbc  lea     rcx, aSettingComglbE; "Setting COMGLB_EXCEPTION_HANDLING faile"...
0x18002ebc3  call    WppDbgPrint
0x18002ebc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebcf  mov     edx, 0Bh
0x18002ebd4  mov     r9, r12
0x18002ebd7  mov     dword ptr [rsp+58h+ppv], edi
0x18002ebdb  mov     r8, r13
0x18002ebde  mov     rcx, [rcx+10h]
0x18002ebe2  call    WPP_SF_sd
0x18002ebe7  mov     rcx, [rsp+58h+arg_10]
0x18002ebec  mov     rax, [rcx]
0x18002ebef  mov     rax, [rax+10h]
0x18002ebf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebf8  xor     edx, edx; pUnkOuter
0x18002ebfa  lea     r9, IID_ISdoMachine; riid
0x18002ec01  add     rsi, 48h ; 'H'
0x18002ec05  lea     rcx, CLSID_SdoMachine; rclsid
0x18002ec0c  mov     [rsp+58h+ppv], rsi; ppv
0x18002ec11  lea     r8d, [rdx+1]; dwClsContext
0x18002ec15  call    cs:__imp_CoCreateInstance
0x18002ec1b  mov     edi, eax
0x18002ec1d  test    eax, eax
0x18002ec1f  jns     short loc_18002EC77
0x18002ec21  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec28  cmp     rcx, rbx
0x18002ec2b  jz      loc_18002ED8B
0x18002ec31  cmp     byte ptr [rcx+19h], 2
0x18002ec35  jb      loc_18002ED8B
0x18002ec3b  test    [rcx+1Ch], r15d
0x18002ec3f  jz      loc_18002ED8B
0x18002ec45  mov     edx, eax
0x18002ec47  lea     rcx, aCociClsidSdoma; "CoCi(CLSID_SdoMachine) failed with %!hr"...
0x18002ec4e  call    WppDbgPrint
0x18002ec53  mov     edx, 0Ch
0x18002ec58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec5f  mov     r9, r12
0x18002ec62  mov     r8, r13
0x18002ec65  mov     dword ptr [rsp+58h+ppv], edi
0x18002ec69  mov     rcx, [rcx+10h]
0x18002ec6d  call    WPP_SF_sd
0x18002ec72  jmp     loc_18002ED8B
0x18002ec77  mov     rcx, [rsi]
0x18002ec7a  mov     rdx, rbp
0x18002ec7d  mov     rax, [rcx]
0x18002ec80  mov     rax, [rax+38h]
0x18002ec84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec89  mov     edi, eax
0x18002ec8b  test    eax, eax
0x18002ec8d  jns     short loc_18002ECC8
0x18002ec8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec96  cmp     rcx, rbx
0x18002ec99  jz      loc_18002ED8B
0x18002ec9f  cmp     byte ptr [rcx+19h], 2
0x18002eca3  jb      loc_18002ED8B
0x18002eca9  test    [rcx+1Ch], r15d
0x18002ecad  jz      loc_18002ED8B
0x18002ecb3  mov     edx, eax
0x18002ecb5  lea     rcx, aMPmachineAttac; "m_pMachine->Attach failed with %!hresul"...
0x18002ecbc  call    WppDbgPrint
0x18002ecc1  mov     edx, 0Dh
0x18002ecc6  jmp     short loc_18002EC58
0x18002ecc8  mov     rcx, [rsi]
0x18002eccb  lea     r8, [rsp+58h+arg_0]
0x18002ecd0  mov     [rsp+58h+arg_0], 0
0x18002ecd9  lea     rdx, _GUID_518e5ffe_d8ce_4f7e_a5db_b40a35419d3b
0x18002ece0  mov     rax, [rcx]
0x18002ece3  mov     rax, [rax]
0x18002ece6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eceb  mov     edi, eax
0x18002eced  test    eax, eax
0x18002ecef  jns     short loc_18002ED22
0x18002ecf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecf8  cmp     rcx, rbx
0x18002ecfb  jz      loc_18002ED81
0x18002ed01  cmp     byte ptr [rcx+19h], 2
0x18002ed05  jb      short loc_18002ED81
0x18002ed07  test    [rcx+1Ch], r15d
0x18002ed0b  jz      short loc_18002ED81
0x18002ed0d  mov     edx, eax
0x18002ed0f  lea     rcx, aMPmachineQuery; "m_pMachine->QueryInterface(ISdoMachine2"...
0x18002ed16  call    WppDbgPrint
0x18002ed1b  mov     edx, 0Eh
0x18002ed20  jmp     short loc_18002ED67
0x18002ed22  mov     rcx, [rsp+58h+arg_0]
0x18002ed27  mov     rax, [rcx]
0x18002ed2a  mov     rax, [rax+0A0h]
0x18002ed31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed36  mov     edi, eax
0x18002ed38  test    eax, eax
0x18002ed3a  jns     short loc_18002ED81
0x18002ed3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed43  cmp     rcx, rbx
0x18002ed46  jz      short loc_18002ED81
0x18002ed48  cmp     byte ptr [rcx+19h], 2
0x18002ed4c  jb      short loc_18002ED81
0x18002ed4e  test    [rcx+1Ch], r15d
0x18002ed52  jz      short loc_18002ED81
0x18002ed54  mov     edx, eax
0x18002ed56  lea     rcx, aPsdomachine2Re; "pSdoMachine2->Reload failed with %!hres"...
0x18002ed5d  call    WppDbgPrint
0x18002ed62  mov     edx, 0Fh
0x18002ed67  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed6e  mov     r9, r12
0x18002ed71  mov     r8, r13
0x18002ed74  mov     dword ptr [rsp+58h+ppv], edi
0x18002ed78  mov     rcx, [rcx+10h]
0x18002ed7c  call    WPP_SF_sd
0x18002ed81  lea     rcx, [rsp+58h+arg_0]
0x18002ed86  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ed8b  mov     rbx, [rsp+58h+arg_8]
0x18002ed90  mov     eax, edi
0x18002ed92  mov     rbp, [rsp+58h+arg_18]
0x18002ed97  add     rsp, 30h
0x18002ed9b  pop     r15
0x18002ed9d  pop     r13
0x18002ed9f  pop     r12
0x18002eda1  pop     rdi
0x18002eda2  pop     rsi
0x18002eda3  retn
```
