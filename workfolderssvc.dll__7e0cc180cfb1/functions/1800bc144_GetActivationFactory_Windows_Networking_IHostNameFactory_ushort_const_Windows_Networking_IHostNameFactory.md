# GetActivationFactory<Windows::Networking::IHostNameFactory>(ushort const *,Windows::Networking::IHostNameFactory * *)

- ea: `0x1800bc144`
- end: `0x1800bc264`
- name: `??$GetActivationFactory@UIHostNameFactory@Networking@Windows@@@@YAJPEBGPEAPEAUIHostNameFactory@Networking@Windows@@@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800bc894`

## callees

- `0x180007e10`
- `0x180011314`
- `0x1800bc144`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bc219`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bc219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bc1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bc1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bc245`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bc245`

## pseudocode

```c
__int64 __fastcall GetActivationFactory<Windows::Networking::IHostNameFactory>(HSTRING a1, _QWORD *a2)
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
  ActivationFactory = WindowsCreateString(L"Windows.Networking.HostName", 0x1Bu, &string);
  v5 = 49;
  if ( ActivationFactory < 0 )
    goto LABEL_14;
  LOWORD(v9) = 49;
  ActivationFactory = RoGetActivationFactory(string, &GUID_458c23ed_712f_4576_adf1_c20b2c643558, a2);
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
0x1800bc144  mov     [rsp-8+arg_8], rbx
0x1800bc149  mov     [rsp-8+string], rcx
0x1800bc14e  push    rbp
0x1800bc14f  mov     rbp, rsp
0x1800bc152  sub     rsp, 40h
0x1800bc156  mov     rbx, rdx
0x1800bc159  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc160  lea     rcx, WPP_GLOBAL_Control
0x1800bc167  cmp     rax, rcx
0x1800bc16a  jz      short loc_1800BC194
0x1800bc16c  test    byte ptr [rax+44h], 20h
0x1800bc170  jz      short loc_1800BC1A4
0x1800bc172  cmp     byte ptr [rax+41h], 6
0x1800bc176  jb      short loc_1800BC194
0x1800bc178  mov     rcx, [rax+38h]
0x1800bc17c  lea     r8, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids
0x1800bc183  mov     edx, 0Ah
0x1800bc188  call    WPP_SF_
0x1800bc18d  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc194  test    byte ptr [rax+44h], 20h
0x1800bc198  jz      short loc_1800BC1A4
0x1800bc19a  cmp     byte ptr [rax+41h], 6
0x1800bc19e  jb      short loc_1800BC1A4
0x1800bc1a0  mov     cl, 1
0x1800bc1a2  jmp     short loc_1800BC1A6
0x1800bc1a4  xor     cl, cl
0x1800bc1a6  mov     [rbp+var_1C], 26h ; '&'
0x1800bc1ad  lea     rax, aGetactivationf; "GetActivationFactory"
0x1800bc1b4  mov     [rbp+var_10], rax
0x1800bc1b8  mov     [rbp+var_18], cl
0x1800bc1bb  mov     [rbp+var_8], 0
0x1800bc1c3  mov     [rbp+string], 0
0x1800bc1cb  test    rbx, rbx
0x1800bc1ce  jz      short loc_1800BC231
0x1800bc1d0  mov     eax, 2Ch ; ','
0x1800bc1d5  mov     qword ptr [rbx], 0
0x1800bc1dc  lea     r8, [rbp+string]; string
0x1800bc1e0  mov     [rbp+var_20], 0
0x1800bc1e7  lea     rcx, ?RuntimeClass_Windows_Networking_HostName@@3QBGB; "Windows.Networking.HostName"
0x1800bc1ee  mov     word ptr [rbp+var_1C], ax
0x1800bc1f2  lea     edx, [rax-11h]; length
0x1800bc1f5  call    cs:__imp_WindowsCreateString
0x1800bc1fb  mov     [rbp+var_20], eax
0x1800bc1fe  test    eax, eax
0x1800bc200  mov     eax, 31h ; '1'
0x1800bc205  js      short loc_1800BC23D
0x1800bc207  mov     rcx, [rbp+string]
0x1800bc20b  lea     rdx, _GUID_458c23ed_712f_4576_adf1_c20b2c643558
0x1800bc212  mov     r8, rbx
0x1800bc215  mov     word ptr [rbp+var_1C], ax
0x1800bc219  call    cs:__imp_RoGetActivationFactory
0x1800bc21f  mov     [rbp+var_20], eax
0x1800bc222  test    eax, eax
0x1800bc224  mov     eax, 32h ; '2'
0x1800bc229  js      short loc_1800BC23D
0x1800bc22b  mov     word ptr [rbp+var_1C], ax
0x1800bc22f  jmp     short loc_1800BC241
0x1800bc231  mov     [rbp+var_20], 80070057h
0x1800bc238  mov     eax, 2Bh ; '+'
0x1800bc23d  mov     word ptr [rbp+var_1C+2], ax
0x1800bc241  mov     rcx, [rbp+string]; string
0x1800bc245  call    cs:__imp_WindowsDeleteString
0x1800bc24b  mov     ebx, [rbp+var_20]
0x1800bc24e  lea     rcx, [rbp+var_20]; this
0x1800bc252  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800bc257  mov     eax, ebx
0x1800bc259  mov     rbx, [rsp+40h+arg_8]
0x1800bc25e  add     rsp, 40h
0x1800bc262  pop     rbp
0x1800bc263  retn
```
