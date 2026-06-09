# VsmmNtSlatExtensionSetup

- ea: `0x1400cd4d0`
- end: `0x1400cd78f`
- name: `VsmmNtSlatExtensionSetup`
- size: `703`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140083714`

## callees

- `0x140021db0`
- `0x14002f724`
- `0x140076000`
- `0x140092250`
- `0x1400cd4d0`
- `0x1400cd798`
- `0x1400fd28c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400cd5e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd5e4`
- `ntoskrnl!RtlSetBit` at `0x1400cd68a`
- `ntoskrnl!RtlSetBit` at `0x1400cd68a`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400cd657`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400cd657`
- `ntoskrnl!ExRegisterExtension` at `0x1400cd58e`
- `ntoskrnl!ExRegisterExtension` at `0x1400cd58e`

## string_xrefs

- `0x1400cd5c0`: `VsmmNtSlatExtensionSetup`
- `0x1400cd611`: `VsmmNtSlatExtensionSetup`
- `0x1400cd639`: `VsmmNtSlatExtensionSetup`
- `0x1400cd6c3`: `VsmmNtSlatExtensionSetup`

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
  int v8; // eax
  _OWORD *v9; // rcx
  _OWORD *v10; // rax
  __int128 v11; // xmm1
  _BYTE v13[16]; // [rsp+20h] [rbp-30h] BYREF
  __int16 v14; // [rsp+30h] [rbp-20h] BYREF
  int v15; // [rsp+32h] [rbp-1Eh]
  __int16 v16; // [rsp+36h] [rbp-1Ah]
  __int64 (__fastcall **v17)(); // [rsp+38h] [rbp-18h]
  __int64 *v18; // [rsp+40h] [rbp-10h]
  __int64 v19; // [rsp+48h] [rbp-8h]
  int v20; // [rsp+80h] [rbp+30h]
  int v21; // [rsp+84h] [rbp+34h]
  __int64 v22; // [rsp+88h] [rbp+38h] BYREF
  __int64 v23; // [rsp+90h] [rbp+40h] BYREF

  v1 = (char *)VidDeviceExtension;
  v19 = a1;
  v22 = 0;
  v20 = 65537;
  v21 = 1;
  v14 = 8;
  v2 = 2;
  v23 = 0;
  v17 = VsmmNtSlatDriverFunctionTable;
  v18 = &v22;
  v15 = 0;
  v16 = 2;
  if ( (int)VidRegistryOpenParametersKey(&v23) < 0 )
    UINT32WithDefault = 0;
  else
    UINT32WithDefault = VidRegistryQueryUINT32WithDefault(v23, L"SimulateDownlevelKernel", 0);
  for ( i = UINT32WithDefault != 0; i < 2; ++i )
  {
    v15 = *(&v20 + i);
    v5 = ExRegisterExtension(v1 + 1896, 65537, &v14);
    v6 = v5;
    if ( v5 != -1073741275 )
    {
      if ( v5 < 0 )
      {
        VidTraceErrorStatusInternal0(
          "VsmmNtSlatExtensionSetup",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat.c",
          912,
          (unsigned int)v5);
        goto LABEL_24;
      }
      goto LABEL_10;
    }
  }
  if ( i == 2 )
  {
    v6 = -1073741637;
    VidTraceErrorStatusInternal0(
      "VsmmNtSlatExtensionSetup",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat.c",
      931,
      3221225659LL);
    goto LABEL_24;
  }
LABEL_10:
  Pool2 = (struct _RTL_BITMAP *)ExAllocatePool2(64, 20, 1833788502);
  *((_QWORD *)v1 + 274) = Pool2;
  if ( Pool2 )
  {
    RtlInitializeBitMap(Pool2, &Pool2[1].SizeOfBitMap, 4u);
    v20 = *(&v20 + i);
    if ( !HIWORD(v20) )
      goto LABEL_19;
    if ( (*(_BYTE *)(VidQueryVmmCapabilities(v13) + 8) & 1) != 0 )
      RtlSetBit(*((PRTL_BITMAP *)v1 + 274), 1u);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(v22 + 256))(*((_QWORD *)v1 + 274));
    v6 = v8;
    if ( v8 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmNtSlatExtensionSetup",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat.c",
        985,
        (unsigned int)v8);
    }
    else
    {
LABEL_19:
      v9 = (_OWORD *)v22;
      v10 = v1 + 1904;
      do
      {
        *v10 = *v9;
        v10[1] = v9[1];
        v10[2] = v9[2];
        v10[3] = v9[3];
        v10[4] = v9[4];
        v10[5] = v9[5];
        v10[6] = v9[6];
        v11 = v9[7];
        v9 += 8;
        v10[7] = v11;
        v10 += 8;
        --v2;
      }
      while ( v2 );
      if ( HIWORD(v20) )
        *((_QWORD *)v1 + 270) = *(_QWORD *)(v22 + 256);
      v6 = 0;
    }
  }
  else
  {
    v6 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmNtSlatExtensionSetup",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat.c",
      952,
      3221225626LL);
  }
LABEL_24:
  if ( v23 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v23);
  if ( v6 < 0 )
    VsmmNtSlatExtensionTeardown();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400cd4d0  mov     [rsp-28h+arg_18], rbx
0x1400cd4d5  push    rbp
0x1400cd4d6  push    rsi
0x1400cd4d7  push    rdi
0x1400cd4d8  push    r14
0x1400cd4da  push    r15
0x1400cd4dc  mov     rbp, rsp
0x1400cd4df  sub     rsp, 50h
0x1400cd4e3  mov     rsi, cs:VidDeviceExtension
0x1400cd4ea  mov     ebx, 1
0x1400cd4ef  mov     [rbp+var_8], rcx
0x1400cd4f3  lea     rcx, [rbp+arg_10]
0x1400cd4f7  mov     [rbp+arg_8], 0
0x1400cd4ff  mov     [rbp+arg_0], 10001h
0x1400cd506  lea     eax, [rbx+7]
0x1400cd509  mov     [rbp+arg_4], ebx
0x1400cd50c  mov     [rbp+var_20], ax
0x1400cd510  lea     r15d, [rbx+1]
0x1400cd514  lea     rax, VsmmNtSlatDriverFunctionTable
0x1400cd51b  mov     [rbp+arg_10], 0
0x1400cd523  mov     [rbp+var_18], rax
0x1400cd527  lea     rax, [rbp+arg_8]
0x1400cd52b  mov     [rbp+var_10], rax
0x1400cd52f  mov     [rbp+var_1E], 0
0x1400cd536  mov     [rbp+var_1A], r15w
0x1400cd53b  call    VidRegistryOpenParametersKey
0x1400cd540  test    eax, eax
0x1400cd542  js      short loc_1400CD559
0x1400cd544  mov     rcx, [rbp+arg_10]
0x1400cd548  lea     rdx, aSimulatedownle; "SimulateDownlevelKernel"
0x1400cd54f  xor     r8d, r8d
0x1400cd552  call    VidRegistryQueryUINT32WithDefault
0x1400cd557  jmp     short loc_1400CD55B
0x1400cd559  xor     eax, eax
0x1400cd55b  xor     edi, edi
0x1400cd55d  test    eax, eax
0x1400cd55f  setnz   dil
0x1400cd563  mov     eax, edi
0x1400cd565  lea     r14, ds:0[rax*4]
0x1400cd56d  cmp     edi, r15d
0x1400cd570  jnb     loc_1400CD622
0x1400cd576  mov     eax, [rbp+r14+arg_0]
0x1400cd57b  lea     rcx, [rsi+768h]
0x1400cd582  lea     r8, [rbp+var_20]
0x1400cd586  mov     [rbp+var_1E], eax
0x1400cd589  mov     edx, 10001h
0x1400cd58e  call    cs:__imp_ExRegisterExtension
0x1400cd595  nop     dword ptr [rax+rax+00h]
0x1400cd59a  mov     ebx, eax
0x1400cd59c  cmp     eax, 0C0000225h
0x1400cd5a1  jnz     short loc_1400CD5AC
0x1400cd5a3  mov     ebx, 1
0x1400cd5a8  add     edi, ebx
0x1400cd5aa  jmp     short loc_1400CD563
0x1400cd5ac  test    eax, eax
0x1400cd5ae  jns     short loc_1400CD5D1
0x1400cd5b0  mov     r9d, eax
0x1400cd5b3  lea     rdx, aOnecoreVmVidSy_46; "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat"...
0x1400cd5ba  mov     r8d, 390h
0x1400cd5c0  lea     rcx, aVsmmntslatexte; "VsmmNtSlatExtensionSetup"
0x1400cd5c7  call    VidTraceErrorStatusInternal0
0x1400cd5cc  jmp     loc_1400CD74A
0x1400cd5d1  mov     ebx, 1
0x1400cd5d6  mov     edx, 14h
0x1400cd5db  mov     r8d, 6D4D6456h
0x1400cd5e1  lea     ecx, [rdx+2Ch]
0x1400cd5e4  call    cs:__imp_ExAllocatePool2
0x1400cd5eb  nop     dword ptr [rax+rax+00h]
0x1400cd5f0  mov     [rsi+890h], rax
0x1400cd5f7  test    rax, rax
0x1400cd5fa  jnz     short loc_1400CD64A
0x1400cd5fc  mov     ebx, 0C000009Ah
0x1400cd601  mov     r9d, ebx
0x1400cd604  lea     rdx, aOnecoreVmVidSy_46; "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat"...
0x1400cd60b  mov     r8d, 3B8h
0x1400cd611  lea     rcx, aVsmmntslatexte; "VsmmNtSlatExtensionSetup"
0x1400cd618  call    VidTraceErrorStatusInternal0
0x1400cd61d  jmp     loc_1400CD74A
0x1400cd622  jnz     short loc_1400CD5D6
0x1400cd624  mov     ebx, 0C00000BBh
0x1400cd629  mov     r9d, ebx
0x1400cd62c  lea     rdx, aOnecoreVmVidSy_46; "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat"...
0x1400cd633  mov     r8d, 3A3h
0x1400cd639  lea     rcx, aVsmmntslatexte; "VsmmNtSlatExtensionSetup"
0x1400cd640  call    VidTraceErrorStatusInternal0
0x1400cd645  jmp     loc_1400CD74A
0x1400cd64a  lea     rdx, [rax+10h]; BitMapBuffer
0x1400cd64e  mov     r8d, 4; SizeOfBitMap
0x1400cd654  mov     rcx, rax; BitMapHeader
0x1400cd657  call    cs:__imp_RtlInitializeBitMap
0x1400cd65e  nop     dword ptr [rax+rax+00h]
0x1400cd663  mov     eax, [rbp+r14+arg_0]
0x1400cd668  mov     [rbp+arg_0], eax
0x1400cd66b  shr     eax, 10h
0x1400cd66e  cmp     ax, bx
0x1400cd671  jb      short loc_1400CD6D6
0x1400cd673  lea     rcx, [rbp+var_30]
0x1400cd677  call    VidQueryVmmCapabilities
0x1400cd67c  test    [rax+8], bl
0x1400cd67f  jz      short loc_1400CD696
0x1400cd681  mov     rcx, [rsi+890h]; BitMapHeader
0x1400cd688  mov     edx, ebx; BitNumber
0x1400cd68a  call    cs:__imp_RtlSetBit
0x1400cd691  nop     dword ptr [rax+rax+00h]
0x1400cd696  mov     rax, [rbp+arg_8]
0x1400cd69a  mov     rcx, [rsi+890h]
0x1400cd6a1  mov     rax, [rax+100h]
0x1400cd6a8  call    _guard_dispatch_icall
0x1400cd6ad  mov     ebx, eax
0x1400cd6af  test    eax, eax
0x1400cd6b1  jns     short loc_1400CD6D1
0x1400cd6b3  mov     r9d, eax
0x1400cd6b6  lea     rdx, aOnecoreVmVidSy_46; "onecore\\vm\\vid\\sys\\vsmm\\vsmmntslat"...
0x1400cd6bd  mov     r8d, 3D9h
0x1400cd6c3  lea     rcx, aVsmmntslatexte; "VsmmNtSlatExtensionSetup"
0x1400cd6ca  call    VidTraceErrorStatusInternal0
0x1400cd6cf  jmp     short loc_1400CD74A
0x1400cd6d1  mov     ebx, 1
0x1400cd6d6  mov     rcx, [rbp+arg_8]
0x1400cd6da  lea     rax, [rsi+770h]
0x1400cd6e1  mov     edx, 80h
0x1400cd6e6  movups  xmm0, xmmword ptr [rcx]
0x1400cd6e9  movups  xmmword ptr [rax], xmm0
0x1400cd6ec  movups  xmm1, xmmword ptr [rcx+10h]
0x1400cd6f0  movups  xmmword ptr [rax+10h], xmm1
0x1400cd6f4  movups  xmm0, xmmword ptr [rcx+20h]
0x1400cd6f8  movups  xmmword ptr [rax+20h], xmm0
0x1400cd6fc  movups  xmm1, xmmword ptr [rcx+30h]
0x1400cd700  movups  xmmword ptr [rax+30h], xmm1
0x1400cd704  movups  xmm0, xmmword ptr [rcx+40h]
0x1400cd708  movups  xmmword ptr [rax+40h], xmm0
0x1400cd70c  movups  xmm1, xmmword ptr [rcx+50h]
0x1400cd710  movups  xmmword ptr [rax+50h], xmm1
0x1400cd714  movups  xmm0, xmmword ptr [rcx+60h]
0x1400cd718  movups  xmmword ptr [rax+60h], xmm0
0x1400cd71c  movups  xmm1, xmmword ptr [rcx+70h]
0x1400cd720  add     rcx, rdx
0x1400cd723  movups  xmmword ptr [rax+70h], xmm1
0x1400cd727  add     rax, rdx
0x1400cd72a  sub     r15, 1
0x1400cd72e  jnz     short loc_1400CD6E6
0x1400cd730  cmp     word ptr [rbp+arg_0+2], bx
0x1400cd734  jb      short loc_1400CD748
0x1400cd736  mov     rax, [rbp+arg_8]
0x1400cd73a  mov     rcx, [rax+100h]
0x1400cd741  mov     [rsi+870h], rcx
0x1400cd748  xor     ebx, ebx
0x1400cd74a  cmp     [rbp+arg_10], 0
0x1400cd74f  jz      short loc_1400CD76F
0x1400cd751  mov     rax, cs:WdfFunctions_01015
0x1400cd758  mov     rdx, [rbp+arg_10]
0x1400cd75c  mov     rcx, cs:WdfDriverGlobals
0x1400cd763  mov     rax, [rax+738h]
0x1400cd76a  call    _guard_dispatch_icall
0x1400cd76f  test    ebx, ebx
0x1400cd771  jns     short loc_1400CD778
0x1400cd773  call    VsmmNtSlatExtensionTeardown
0x1400cd778  mov     eax, ebx
0x1400cd77a  mov     rbx, [rsp+50h+arg_18]
0x1400cd782  add     rsp, 50h
0x1400cd786  pop     r15
0x1400cd788  pop     r14
0x1400cd78a  pop     rdi
0x1400cd78b  pop     rsi
0x1400cd78c  pop     rbp
0x1400cd78d  retn
```
