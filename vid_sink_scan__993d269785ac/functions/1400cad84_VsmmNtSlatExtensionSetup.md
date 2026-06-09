# VsmmNtSlatExtensionSetup

- ea: `0x1400cad84`
- end: `0x1400cb043`
- name: `VsmmNtSlatExtensionSetup`
- size: `703`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14008279c`

## callees

- `0x1400217a0`
- `0x14002f524`
- `0x140075140`
- `0x140090c48`
- `0x1400cad84`
- `0x1400cb04c`
- `0x1400faa18`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400cae98`
- `ntoskrnl!ExAllocatePool2` at `0x1400cae98`
- `ntoskrnl!RtlSetBit` at `0x1400caf3e`
- `ntoskrnl!RtlSetBit` at `0x1400caf3e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400caf0b`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400caf0b`
- `ntoskrnl!ExRegisterExtension` at `0x1400cae42`
- `ntoskrnl!ExRegisterExtension` at `0x1400cae42`

## string_xrefs

- `0x1400cae74`: `VsmmNtSlatExtensionSetup`
- `0x1400caec5`: `VsmmNtSlatExtensionSetup`
- `0x1400caeed`: `VsmmNtSlatExtensionSetup`
- `0x1400caf77`: `VsmmNtSlatExtensionSetup`

## pseudocode

```c
__int64 __fastcall VsmmNtSlatExtensionSetup(__int64 a1)
{
  char *v1; // rsi
  __int64 v2; // r15
  int UINT32WithDefault; // eax
  unsigned int i; // edi
  int v5; // eax
  int v6; // ebx
  struct _RTL_BITMAP *Pool2; // rax
  _OWORD *v8; // rcx
  _OWORD *v9; // rax
  __int128 v10; // xmm1
  _BYTE v12[16]; // [rsp+20h] [rbp-30h] BYREF
  __int16 v13; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+32h] [rbp-1Eh]
  __int16 v15; // [rsp+36h] [rbp-1Ah]
  __int64 (__fastcall **v16)(); // [rsp+38h] [rbp-18h]
  __int64 *v17; // [rsp+40h] [rbp-10h]
  __int64 v18; // [rsp+48h] [rbp-8h]
  int v19; // [rsp+80h] [rbp+30h]
  int v20; // [rsp+84h] [rbp+34h]
  __int64 v21; // [rsp+88h] [rbp+38h] BYREF
  __int64 v22; // [rsp+90h] [rbp+40h] BYREF

  v1 = (char *)VidDeviceExtension;
  v18 = a1;
  v21 = 0;
  v19 = 65537;
  v20 = 1;
  v13 = 8;
  v2 = 2;
  v22 = 0;
  v16 = VsmmNtSlatDriverFunctionTable;
  v17 = &v21;
  v14 = 0;
  v15 = 2;
  if ( (int)VidRegistryOpenParametersKey(&v22) < 0 )
    UINT32WithDefault = 0;
  else
    UINT32WithDefault = VidRegistryQueryUINT32WithDefault(v22, L"SimulateDownlevelKernel", 0);
  for ( i = UINT32WithDefault != 0; i < 2; ++i )
  {
    v14 = *(&v19 + i);
    v5 = ExRegisterExtension(v1 + 1896, 65537, &v13);
    v6 = v5;
    if ( v5 != -1073741275 )
    {
      if ( v5 < 0 )
      {
        VidTraceErrorStatusInternal0("VsmmNtSlatExtensionSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat.c", 912);
        goto LABEL_24;
      }
      goto LABEL_10;
    }
  }
  if ( i == 2 )
  {
    v6 = -1073741637;
    VidTraceErrorStatusInternal0("VsmmNtSlatExtensionSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat.c", 931);
    goto LABEL_24;
  }
LABEL_10:
  Pool2 = (struct _RTL_BITMAP *)ExAllocatePool2(64, 20, 1833788502);
  *((_QWORD *)v1 + 274) = Pool2;
  if ( Pool2 )
  {
    RtlInitializeBitMap(Pool2, &Pool2[1].SizeOfBitMap, 4u);
    v19 = *(&v19 + i);
    if ( !HIWORD(v19) )
      goto LABEL_19;
    if ( (*(_BYTE *)(VidQueryVmmCapabilities(v12) + 8) & 1) != 0 )
      RtlSetBit(*((PRTL_BITMAP *)v1 + 274), 1u);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(v21 + 256))(*((_QWORD *)v1 + 274));
    if ( v6 < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmNtSlatExtensionSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat.c", 985);
    }
    else
    {
LABEL_19:
      v8 = (_OWORD *)v21;
      v9 = v1 + 1904;
      do
      {
        *v9 = *v8;
        v9[1] = v8[1];
        v9[2] = v8[2];
        v9[3] = v8[3];
        v9[4] = v8[4];
        v9[5] = v8[5];
        v9[6] = v8[6];
        v10 = v8[7];
        v8 += 8;
        v9[7] = v10;
        v9 += 8;
        --v2;
      }
      while ( v2 );
      if ( HIWORD(v19) )
        *((_QWORD *)v1 + 270) = *(_QWORD *)(v21 + 256);
      v6 = 0;
    }
  }
  else
  {
    v6 = -1073741670;
    VidTraceErrorStatusInternal0("VsmmNtSlatExtensionSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat.c", 952);
  }
LABEL_24:
  if ( v22 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v22);
  if ( v6 < 0 )
    VsmmNtSlatExtensionTeardown();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400cad84  mov     [rsp-28h+arg_18], rbx
0x1400cad89  push    rbp
0x1400cad8a  push    rsi
0x1400cad8b  push    rdi
0x1400cad8c  push    r14
0x1400cad8e  push    r15
0x1400cad90  mov     rbp, rsp
0x1400cad93  sub     rsp, 50h
0x1400cad97  mov     rsi, cs:VidDeviceExtension
0x1400cad9e  mov     ebx, 1
0x1400cada3  mov     [rbp+var_8], rcx
0x1400cada7  lea     rcx, [rbp+arg_10]
0x1400cadab  mov     [rbp+arg_8], 0
0x1400cadb3  mov     [rbp+arg_0], 10001h
0x1400cadba  lea     eax, [rbx+7]
0x1400cadbd  mov     [rbp+arg_4], ebx
0x1400cadc0  mov     [rbp+var_20], ax
0x1400cadc4  lea     r15d, [rbx+1]
0x1400cadc8  lea     rax, VsmmNtSlatDriverFunctionTable
0x1400cadcf  mov     [rbp+arg_10], 0
0x1400cadd7  mov     [rbp+var_18], rax
0x1400caddb  lea     rax, [rbp+arg_8]
0x1400caddf  mov     [rbp+var_10], rax
0x1400cade3  mov     [rbp+var_1E], 0
0x1400cadea  mov     [rbp+var_1A], r15w
0x1400cadef  call    VidRegistryOpenParametersKey
0x1400cadf4  test    eax, eax
0x1400cadf6  js      short loc_1400CAE0D
0x1400cadf8  mov     rcx, [rbp+arg_10]
0x1400cadfc  lea     rdx, aSimulatedownle; "SimulateDownlevelKernel"
0x1400cae03  xor     r8d, r8d
0x1400cae06  call    VidRegistryQueryUINT32WithDefault
0x1400cae0b  jmp     short loc_1400CAE0F
0x1400cae0d  xor     eax, eax
0x1400cae0f  xor     edi, edi
0x1400cae11  test    eax, eax
0x1400cae13  setnz   dil
0x1400cae17  mov     eax, edi
0x1400cae19  lea     r14, ds:0[rax*4]
0x1400cae21  cmp     edi, r15d
0x1400cae24  jnb     loc_1400CAED6
0x1400cae2a  mov     eax, [rbp+r14+arg_0]
0x1400cae2f  lea     rcx, [rsi+768h]
0x1400cae36  lea     r8, [rbp+var_20]
0x1400cae3a  mov     [rbp+var_1E], eax
0x1400cae3d  mov     edx, 10001h
0x1400cae42  call    cs:__imp_ExRegisterExtension
0x1400cae49  nop     dword ptr [rax+rax+00h]
0x1400cae4e  mov     ebx, eax
0x1400cae50  cmp     eax, 0C0000225h
0x1400cae55  jnz     short loc_1400CAE60
0x1400cae57  mov     ebx, 1
0x1400cae5c  add     edi, ebx
0x1400cae5e  jmp     short loc_1400CAE17
0x1400cae60  test    eax, eax
0x1400cae62  jns     short loc_1400CAE85
0x1400cae64  mov     r9d, eax
0x1400cae67  lea     rdx, aOnecoreVmVidSy_46; "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat"...
0x1400cae6e  mov     r8d, 390h
0x1400cae74  lea     rcx, aVsmmntslatexte; "VsmmNtSlatExtensionSetup"
0x1400cae7b  call    VidTraceErrorStatusInternal0
0x1400cae80  jmp     loc_1400CAFFE
0x1400cae85  mov     ebx, 1
0x1400cae8a  mov     edx, 14h
0x1400cae8f  mov     r8d, 6D4D6456h
0x1400cae95  lea     ecx, [rdx+2Ch]
0x1400cae98  call    cs:__imp_ExAllocatePool2
0x1400cae9f  nop     dword ptr [rax+rax+00h]
0x1400caea4  mov     [rsi+890h], rax
0x1400caeab  test    rax, rax
0x1400caeae  jnz     short loc_1400CAEFE
0x1400caeb0  mov     ebx, 0C000009Ah
0x1400caeb5  mov     r9d, ebx
0x1400caeb8  lea     rdx, aOnecoreVmVidSy_46; "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat"...
0x1400caebf  mov     r8d, 3B8h
0x1400caec5  lea     rcx, aVsmmntslatexte; "VsmmNtSlatExtensionSetup"
0x1400caecc  call    VidTraceErrorStatusInternal0
0x1400caed1  jmp     loc_1400CAFFE
0x1400caed6  jnz     short loc_1400CAE8A
0x1400caed8  mov     ebx, 0C00000BBh
0x1400caedd  mov     r9d, ebx
0x1400caee0  lea     rdx, aOnecoreVmVidSy_46; "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat"...
0x1400caee7  mov     r8d, 3A3h
0x1400caeed  lea     rcx, aVsmmntslatexte; "VsmmNtSlatExtensionSetup"
0x1400caef4  call    VidTraceErrorStatusInternal0
0x1400caef9  jmp     loc_1400CAFFE
0x1400caefe  lea     rdx, [rax+10h]; BitMapBuffer
0x1400caf02  mov     r8d, 4; SizeOfBitMap
0x1400caf08  mov     rcx, rax; BitMapHeader
0x1400caf0b  call    cs:__imp_RtlInitializeBitMap
0x1400caf12  nop     dword ptr [rax+rax+00h]
0x1400caf17  mov     eax, [rbp+r14+arg_0]
0x1400caf1c  mov     [rbp+arg_0], eax
0x1400caf1f  shr     eax, 10h
0x1400caf22  cmp     ax, bx
0x1400caf25  jb      short loc_1400CAF8A
0x1400caf27  lea     rcx, [rbp+var_30]
0x1400caf2b  call    VidQueryVmmCapabilities
0x1400caf30  test    [rax+8], bl
0x1400caf33  jz      short loc_1400CAF4A
0x1400caf35  mov     rcx, [rsi+890h]; BitMapHeader
0x1400caf3c  mov     edx, ebx; BitNumber
0x1400caf3e  call    cs:__imp_RtlSetBit
0x1400caf45  nop     dword ptr [rax+rax+00h]
0x1400caf4a  mov     rax, [rbp+arg_8]
0x1400caf4e  mov     rcx, [rsi+890h]
0x1400caf55  mov     rax, [rax+100h]
0x1400caf5c  call    _guard_dispatch_icall
0x1400caf61  mov     ebx, eax
0x1400caf63  test    eax, eax
0x1400caf65  jns     short loc_1400CAF85
0x1400caf67  mov     r9d, eax
0x1400caf6a  lea     rdx, aOnecoreVmVidSy_46; "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat"...
0x1400caf71  mov     r8d, 3D9h
0x1400caf77  lea     rcx, aVsmmntslatexte; "VsmmNtSlatExtensionSetup"
0x1400caf7e  call    VidTraceErrorStatusInternal0
0x1400caf83  jmp     short loc_1400CAFFE
0x1400caf85  mov     ebx, 1
0x1400caf8a  mov     rcx, [rbp+arg_8]
0x1400caf8e  lea     rax, [rsi+770h]
0x1400caf95  mov     edx, 80h
0x1400caf9a  movups  xmm0, xmmword ptr [rcx]
0x1400caf9d  movups  xmmword ptr [rax], xmm0
0x1400cafa0  movups  xmm1, xmmword ptr [rcx+10h]
0x1400cafa4  movups  xmmword ptr [rax+10h], xmm1
0x1400cafa8  movups  xmm0, xmmword ptr [rcx+20h]
0x1400cafac  movups  xmmword ptr [rax+20h], xmm0
0x1400cafb0  movups  xmm1, xmmword ptr [rcx+30h]
0x1400cafb4  movups  xmmword ptr [rax+30h], xmm1
0x1400cafb8  movups  xmm0, xmmword ptr [rcx+40h]
0x1400cafbc  movups  xmmword ptr [rax+40h], xmm0
0x1400cafc0  movups  xmm1, xmmword ptr [rcx+50h]
0x1400cafc4  movups  xmmword ptr [rax+50h], xmm1
0x1400cafc8  movups  xmm0, xmmword ptr [rcx+60h]
0x1400cafcc  movups  xmmword ptr [rax+60h], xmm0
0x1400cafd0  movups  xmm1, xmmword ptr [rcx+70h]
0x1400cafd4  add     rcx, rdx
0x1400cafd7  movups  xmmword ptr [rax+70h], xmm1
0x1400cafdb  add     rax, rdx
0x1400cafde  sub     r15, 1
0x1400cafe2  jnz     short loc_1400CAF9A
0x1400cafe4  cmp     word ptr [rbp+arg_0+2], bx
0x1400cafe8  jb      short loc_1400CAFFC
0x1400cafea  mov     rax, [rbp+arg_8]
0x1400cafee  mov     rcx, [rax+100h]
0x1400caff5  mov     [rsi+870h], rcx
0x1400caffc  xor     ebx, ebx
0x1400caffe  cmp     [rbp+arg_10], 0
0x1400cb003  jz      short loc_1400CB023
0x1400cb005  mov     rax, cs:WdfFunctions_01015
0x1400cb00c  mov     rdx, [rbp+arg_10]
0x1400cb010  mov     rcx, cs:WdfDriverGlobals
0x1400cb017  mov     rax, [rax+738h]
0x1400cb01e  call    _guard_dispatch_icall
0x1400cb023  test    ebx, ebx
0x1400cb025  jns     short loc_1400CB02C
0x1400cb027  call    VsmmNtSlatExtensionTeardown
0x1400cb02c  mov     eax, ebx
0x1400cb02e  mov     rbx, [rsp+50h+arg_18]
0x1400cb036  add     rsp, 50h
0x1400cb03a  pop     r15
0x1400cb03c  pop     r14
0x1400cb03e  pop     rdi
0x1400cb03f  pop     rsi
0x1400cb040  pop     rbp
0x1400cb041  retn
```
