# GetActivationFactory<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>(ushort const *,Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics * *)

- ea: `0x1800bc26c`
- end: `0x1800bc38c`
- name: `??$GetActivationFactory@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@@YAJPEBGPEAPEAUIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bcee0`

## callees

- `0x180007e10`
- `0x180011314`
- `0x1800bc26c`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bc341`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bc341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bc31d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bc31d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bc36d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bc36d`

## string_xrefs

- `0x1800bc30f`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`

## pseudocode

```c
__int64 __fastcall GetActivationFactory<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>(
        HSTRING a1,
        _QWORD *a2)
{
  _BYTE *v3; // rax
  char v4; // cl
  __int16 v5; // ax
  unsigned int v6; // ebx
  HRESULT ActivationFactory; // [rsp+20h] [rbp-20h] BYREF
  int v9; // [rsp+24h] [rbp-1Ch]
  char v10; // [rsp+28h] [rbp-18h]
  const char *v11; // [rsp+30h] [rbp-10h]
  __int64 v12; // [rsp+38h] [rbp-8h]
  HSTRING string; // [rsp+50h] [rbp+10h] BYREF

  string = a1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( (v3[68] & 0x20) != 0 && v3[65] >= 6u )
  {
    v4 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v4 = 0;
LABEL_9:
  v9 = 38;
  v11 = "GetActivationFactory";
  v10 = v4;
  v12 = 0;
  string = 0;
  if ( !a2 )
  {
    ActivationFactory = -2147024809;
    v5 = 43;
LABEL_14:
    HIWORD(v9) = v5;
    goto LABEL_15;
  }
  *a2 = 0;
  LOWORD(v9) = 44;
  ActivationFactory = WindowsCreateString(L"Windows.Security.EnterpriseData.ProtectionPolicyManager", 0x37u, &string);
  v5 = 49;
  if ( ActivationFactory < 0 )
    goto LABEL_14;
  LOWORD(v9) = 49;
  ActivationFactory = RoGetActivationFactory(string, &GUID_c0bffc66_8c3d_4d56_8804_c68f0ad32ec5, a2);
  v5 = 50;
  if ( ActivationFactory < 0 )
    goto LABEL_14;
  LOWORD(v9) = 50;
LABEL_15:
  WindowsDeleteString(string);
  v6 = ActivationFactory;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&ActivationFactory);
  return v6;
}

```

## disassembly

```asm
0x1800bc26c  mov     [rsp-8+arg_8], rbx
0x1800bc271  mov     [rsp-8+string], rcx
0x1800bc276  push    rbp
0x1800bc277  mov     rbp, rsp
0x1800bc27a  sub     rsp, 40h
0x1800bc27e  mov     rbx, rdx
0x1800bc281  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc288  lea     rcx, WPP_GLOBAL_Control
0x1800bc28f  cmp     rax, rcx
0x1800bc292  jz      short loc_1800BC2BC
0x1800bc294  test    byte ptr [rax+44h], 20h
0x1800bc298  jz      short loc_1800BC2CC
0x1800bc29a  cmp     byte ptr [rax+41h], 6
0x1800bc29e  jb      short loc_1800BC2BC
0x1800bc2a0  mov     rcx, [rax+38h]
0x1800bc2a4  lea     r8, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids
0x1800bc2ab  mov     edx, 0Ah
0x1800bc2b0  call    WPP_SF_
0x1800bc2b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc2bc  test    byte ptr [rax+44h], 20h
0x1800bc2c0  jz      short loc_1800BC2CC
0x1800bc2c2  cmp     byte ptr [rax+41h], 6
0x1800bc2c6  jb      short loc_1800BC2CC
0x1800bc2c8  mov     cl, 1
0x1800bc2ca  jmp     short loc_1800BC2CE
0x1800bc2cc  xor     cl, cl
0x1800bc2ce  mov     [rbp+var_1C], 26h ; '&'
0x1800bc2d5  lea     rax, aGetactivationf; "GetActivationFactory"
0x1800bc2dc  mov     [rbp+var_10], rax
0x1800bc2e0  mov     [rbp+var_18], cl
0x1800bc2e3  mov     [rbp+var_8], 0
0x1800bc2eb  mov     [rbp+string], 0
0x1800bc2f3  test    rbx, rbx
0x1800bc2f6  jz      short loc_1800BC359
0x1800bc2f8  mov     eax, 2Ch ; ','
0x1800bc2fd  mov     qword ptr [rbx], 0
0x1800bc304  lea     r8, [rbp+string]; string
0x1800bc308  mov     [rbp+var_20], 0
0x1800bc30f  lea     rcx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyManager@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x1800bc316  mov     word ptr [rbp+var_1C], ax
0x1800bc31a  lea     edx, [rax+0Bh]; length
0x1800bc31d  call    cs:__imp_WindowsCreateString
0x1800bc323  mov     [rbp+var_20], eax
0x1800bc326  test    eax, eax
0x1800bc328  mov     eax, 31h ; '1'
0x1800bc32d  js      short loc_1800BC365
0x1800bc32f  mov     rcx, [rbp+string]
0x1800bc333  lea     rdx, _GUID_c0bffc66_8c3d_4d56_8804_c68f0ad32ec5
0x1800bc33a  mov     r8, rbx
0x1800bc33d  mov     word ptr [rbp+var_1C], ax
0x1800bc341  call    cs:__imp_RoGetActivationFactory
0x1800bc347  mov     [rbp+var_20], eax
0x1800bc34a  test    eax, eax
0x1800bc34c  mov     eax, 32h ; '2'
0x1800bc351  js      short loc_1800BC365
0x1800bc353  mov     word ptr [rbp+var_1C], ax
0x1800bc357  jmp     short loc_1800BC369
0x1800bc359  mov     [rbp+var_20], 80070057h
0x1800bc360  mov     eax, 2Bh ; '+'
0x1800bc365  mov     word ptr [rbp+var_1C+2], ax
0x1800bc369  mov     rcx, [rbp+string]; string
0x1800bc36d  call    cs:__imp_WindowsDeleteString
0x1800bc373  mov     ebx, [rbp+var_20]
0x1800bc376  lea     rcx, [rbp+var_20]; this
0x1800bc37a  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800bc37f  mov     eax, ebx
0x1800bc381  mov     rbx, [rsp+40h+arg_8]
0x1800bc386  add     rsp, 40h
0x1800bc38a  pop     rbp
0x1800bc38b  retn
```
