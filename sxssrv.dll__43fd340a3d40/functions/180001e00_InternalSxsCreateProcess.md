# InternalSxsCreateProcess

- ea: `0x180001e00`
- end: `0x1800027b1`
- name: `InternalSxsCreateProcess`
- size: `2481`
- prototype: `__int64 __fastcall(HANDLE SourceProcessHandle, void *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180001d70`

## callees

- `0x180001e00`
- `0x1800027c0`
- `0x1800028d0`
- `0x180003310`
- `0x180006654`
- `0x18000666c`
- `0x180006ccd`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002183`
- `ntdll!RtlFreeHeap` at `0x1800021cb`
- `ntdll!RtlFreeHeap` at `0x180002778`
- `ntdll!RtlFreeHeap` at `0x180002183`
- `ntdll!RtlFreeHeap` at `0x1800021cb`
- `ntdll!RtlFreeHeap` at `0x180002778`
- `ntdll!NtClose` at `0x180001fe7`
- `ntdll!NtClose` at `0x180001fe7`
- `ntdll!NtQueryInformationFile` at `0x1800023b1`
- `ntdll!NtQueryInformationFile` at `0x1800023f4`
- `ntdll!NtQueryInformationFile` at `0x1800023b1`
- `ntdll!NtQueryInformationFile` at `0x1800023f4`
- `ntdll!NtDuplicateObject` at `0x1800020e1`
- `ntdll!NtDuplicateObject` at `0x1800020e1`
- `ntdll!NtReadVirtualMemory` at `0x18000213c`
- `ntdll!NtReadVirtualMemory` at `0x18000213c`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000264b`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000264b`

## pseudocode

```c
__int64 __fastcall InternalSxsCreateProcess(HANDLE SourceProcessHandle, void *a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v7; // edi
  __int16 v8; // r15
  int v9; // ebx
  __int64 result; // rax
  __int16 *v11; // r12
  __int64 v12; // rdx
  void **v13; // r14
  void *v14; // rdx
  _QWORD *v15; // r13
  __int64 v16; // rcx
  __int64 v17; // rcx
  _OWORD *v18; // r11
  _OWORD *v19; // r10
  __int64 v20; // rcx
  bool v21; // zf
  HANDLE v22; // r14
  __int64 v23; // xmm0_8
  __int128 v24; // xmm1
  char v25; // al
  __int128 v26; // xmm0
  int v27; // eax
  __int128 v28; // xmm0
  __int128 v29; // xmm0
  __int64 v30; // rax
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int64 v33; // xmm0_8
  int v34; // eax
  _DWORD *v35; // rcx
  __int128 *v36; // rdx
  __int64 v37; // rax
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  _WORD *v46; // rcx
  __int128 v47; // xmm0
  __int64 v48; // rax
  __int128 v49; // xmm0
  __int64 v50; // rax
  __int64 Buffer; // [rsp+78h] [rbp-90h] BYREF
  __int64 v52; // [rsp+80h] [rbp-88h]
  void *v53; // [rsp+88h] [rbp-80h]
  HANDLE Handle[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v55; // [rsp+A0h] [rbp-68h]
  __int64 v56; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-50h]
  __int64 v58; // [rsp+C0h] [rbp-48h]
  __int64 v59; // [rsp+C8h] [rbp-40h]
  __int64 v60; // [rsp+D0h] [rbp-38h]
  __int64 v61; // [rsp+D8h] [rbp-30h]
  HANDLE SourceProcessHandlea; // [rsp+E0h] [rbp-28h]
  PVOID v63[2]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v64[56]; // [rsp+F8h] [rbp-10h] BYREF
  _OWORD v65[2]; // [rsp+130h] [rbp+28h] BYREF
  __int128 v66; // [rsp+150h] [rbp+48h]
  __int64 v67; // [rsp+160h] [rbp+58h]
  _OWORD v68[2]; // [rsp+168h] [rbp+60h] BYREF
  __int128 v69; // [rsp+188h] [rbp+80h]
  __int64 v70; // [rsp+198h] [rbp+90h]
  HANDLE v71[2]; // [rsp+1A0h] [rbp+98h] BYREF
  HANDLE BaseAddress[2]; // [rsp+1B0h] [rbp+A8h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1C0h] [rbp+B8h] BYREF
  HANDLE v74[2]; // [rsp+1D0h] [rbp+C8h] BYREF
  HANDLE v75[2]; // [rsp+1E0h] [rbp+D8h]
  __int128 v76; // [rsp+1F0h] [rbp+E8h] BYREF
  PVOID v77[2]; // [rsp+200h] [rbp+F8h]
  __int128 v78; // [rsp+210h] [rbp+108h]
  __int64 v79; // [rsp+220h] [rbp+118h]
  unsigned int v80; // [rsp+228h] [rbp+120h] BYREF
  __int16 v81; // [rsp+22Ch] [rbp+124h]
  __int128 v82; // [rsp+230h] [rbp+128h]
  __int128 v83; // [rsp+240h] [rbp+138h]
  __int64 v84; // [rsp+250h] [rbp+148h]
  __int128 v85; // [rsp+258h] [rbp+150h]
  __int128 v86; // [rsp+268h] [rbp+160h]
  __int128 v87; // [rsp+278h] [rbp+170h]
  __int128 v88; // [rsp+288h] [rbp+180h]
  __int128 v89; // [rsp+298h] [rbp+190h]
  __int64 v90; // [rsp+2A8h] [rbp+1A0h]
  __int128 v91; // [rsp+2B0h] [rbp+1A8h]
  __int64 v92; // [rsp+2D0h] [rbp+1C8h]
  __int64 v93; // [rsp+2D8h] [rbp+1D0h]
  __int64 v94; // [rsp+2E0h] [rbp+1D8h]
  __int64 v95; // [rsp+2E8h] [rbp+1E0h]
  __int64 v96; // [rsp+2F0h] [rbp+1E8h]
  int v97; // [rsp+2F8h] [rbp+1F0h]
  int v98; // [rsp+2FCh] [rbp+1F4h]
  __int16 v99; // [rsp+300h] [rbp+1F8h]
  __int64 v100; // [rsp+302h] [rbp+1FAh]
  int v101; // [rsp+30Ah] [rbp+202h]
  __int16 v102; // [rsp+30Eh] [rbp+206h]
  __int64 v103; // [rsp+310h] [rbp+208h]
  char v104; // [rsp+318h] [rbp+210h] BYREF
  __int128 v105; // [rsp+428h] [rbp+320h] BYREF
  __int128 v106; // [rsp+438h] [rbp+330h]
  __int128 v107; // [rsp+448h] [rbp+340h] BYREF
  __int64 v108; // [rsp+458h] [rbp+350h]
  __int128 FileInformation; // [rsp+460h] [rbp+358h] BYREF
  __int128 v110; // [rsp+470h] [rbp+368h]
  __int64 v111; // [rsp+480h] [rbp+378h]

  v53 = a2;
  SourceProcessHandlea = SourceProcessHandle;
  v52 = a4;
  v61 = a5;
  memset_0(&v80, 0, 0x1F8u);
  v7 = *(_DWORD *)(a3 + 120);
  v60 = 0;
  v8 = 0;
  Buffer = 0;
  v79 = 0;
  v70 = 0;
  v67 = 0;
  v111 = 0;
  v108 = 0;
  v105 = 0;
  v106 = 0;
  memset(v64, 0, sizeof(v64));
  v76 = 0;
  *(_OWORD *)v77 = 0;
  v78 = 0;
  *(_OWORD *)v63 = 0;
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  memset(v65, 0, sizeof(v65));
  v66 = 0;
  *(_OWORD *)Handle = 0;
  v55 = 0;
  *(_OWORD *)v71 = 0;
  *(_OWORD *)BaseAddress = 0;
  *(_OWORD *)v74 = 0;
  *(_OWORD *)v75 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v110 = 0;
  v107 = 0;
  if ( (v7 & 0x20) != 0 )
  {
    v9 = 0;
    goto LABEL_3;
  }
  if ( (v7 & 0x40) == 0 && (v7 & 1) == 0 )
  {
    v9 = 0;
    goto LABEL_3;
  }
  v56 = a3 + 136;
  v11 = (__int16 *)(a3 + 288);
  if ( (v7 & 0x40) != 0 )
  {
    v58 = a3 + 256;
    v57 = a3 + 152;
    v12 = 4;
    v59 = a3 + 288;
  }
  else
  {
    v59 = a3 + 256;
    v57 = a3 + 192;
    v12 = 5;
    v60 = a3 + 288;
    v58 = a3 + 240;
  }
  v9 = BaseSrvSxsValidateMessageStrings(a3, v12, &v56);
  if ( v9 >= 0 )
  {
    if ( *(_WORD *)(a3 + 290)
      && !(unsigned __int8)CsrValidateMessageBuffer(a3, a3 + 296, *(unsigned __int16 *)(a3 + 290), 1) )
    {
      v8 = *(_WORD *)(a3 + 290);
      *(_WORD *)(a3 + 290) = *v11 + 2;
    }
    if ( *(_WORD *)(a3 + 290) )
    {
      v46 = *(_WORD **)(a3 + 296);
      if ( v46 )
      {
        *v46 = 0;
        *v11 = 0;
      }
    }
    v13 = (void **)(a3 + 128);
    if ( (v7 & 0x40) != 0 )
    {
      v14 = *v13;
      Handle[1] = v53;
      v9 = NtDuplicateObject(SourceProcessHandle, v14, (HANDLE)0xFFFFFFFFFFFFFFFFLL, Handle, 0, 0, 2u);
      if ( v9 < 0 )
        goto LABEL_3;
      v15 = (_QWORD *)(a3 + 176);
      v16 = *(_QWORD *)(a3 + 176);
      if ( v16 )
      {
        v47 = *(_OWORD *)(a3 + 136);
        v48 = *(_QWORD *)(a3 + 168);
        v7 |= 0x100u;
        LOWORD(v68[0]) = 769;
        *(_OWORD *)((char *)v68 + 8) = v47;
        *((_QWORD *)&v68[1] + 1) = 0;
        BYTE2(v68[0]) = 2;
        *(_QWORD *)&v69 = 0;
        *((_QWORD *)&v69 + 1) = v48;
        v70 = v16;
      }
      v17 = *(_QWORD *)(a3 + 192);
      if ( v17 )
      {
        v49 = *(_OWORD *)(a3 + 136);
        v50 = *(_QWORD *)(a3 + 184);
        LOWORD(v65[0]) = 769;
        *(_OWORD *)((char *)v65 + 8) = v49;
        *((_QWORD *)&v65[1] + 1) = 0;
        BYTE2(v65[0]) = 2;
        *(_QWORD *)&v66 = 0;
        *((_QWORD *)&v66 + 1) = v50;
        v67 = v17;
      }
      Buffer = 0;
      v9 = NtReadVirtualMemory(Handle[1], (PVOID)(v52 + 16), &Buffer, 8u, 0);
      if ( v9 < 0 )
        goto LABEL_3;
      *((_QWORD *)&v55 + 1) = Buffer;
      v18 = v65;
      v19 = v68;
      if ( !*(_QWORD *)(a3 + 192) )
        LODWORD(v18) = 0;
      if ( !*v15 )
        LODWORD(v19) = 0;
      v9 = BaseSrvSxsProbeManifestAndPolicyAndDotLocal(
             (_DWORD)v19,
             (_DWORD)v18,
             *(_QWORD *)(a3 + 200),
             *(_DWORD *)(a3 + 208),
             (__int64)Handle,
             a3 + 136,
             a3 + 152,
             (*(_DWORD *)(a3 + 120) & 0x200) == 0,
             (__int64)v71,
             (__int64)v64,
             (__int64)v74,
             (__int64)&v76,
             (__int64)v63,
             a3 + 124);
      if ( v9 < 0 )
        goto LABEL_3;
      if ( (*(_DWORD *)(a3 + 124) & 0x2000) == 0 )
      {
LABEL_64:
        v9 = 0;
        goto LABEL_3;
      }
      v20 = v79;
      v7 |= 1u;
      v82 = *(_OWORD *)(a3 + 256);
      if ( v79 )
        v7 |= 2u;
    }
    else
    {
      v20 = Buffer;
      v15 = (_QWORD *)(a3 + 176);
      v82 = *(_OWORD *)(a3 + 256);
    }
    v80 = v7;
    if ( (v7 & 0x40) != 0 )
    {
      v21 = *v15 == 0;
      v83 = *(_OWORD *)v64;
      v85 = *(_OWORD *)&v64[24];
      v87 = v76;
      v89 = v78;
      v86 = *(_OWORD *)&v64[40];
      v84 = *(_QWORD *)&v64[16];
      v91 = *(_OWORD *)v63;
      v90 = v20;
      v88 = *(_OWORD *)v77;
      if ( v21 )
      {
        v22 = v71[0];
        if ( v64[2] == 4 )
          v22 = Handle[0];
        v9 = NtQueryInformationFile(v22, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
        if ( v9 < 0 )
          goto LABEL_3;
        v92 = v110;
        if ( NtQueryInformationFile(
               v22,
               &IoStatusBlock,
               &v107,
               0x18u,
               FileMaximumInformation|FileBothDirectoryInformation) < 0 )
        {
          DWORD2(v106) |= 1u;
        }
        else
        {
          v105 = v107;
          *(_QWORD *)&v106 = v108;
        }
      }
    }
    else
    {
      v23 = *(_QWORD *)(a3 + 131);
      v24 = *(_OWORD *)(a3 + 168);
      LOWORD(v83) = *(_WORD *)v13;
      v25 = *(_BYTE *)(a3 + 130);
      *(_QWORD *)((char *)&v83 + 3) = v23;
      v26 = *(_OWORD *)(a3 + 152);
      BYTE2(v83) = v25;
      v27 = *(_DWORD *)(a3 + 139);
      v85 = v26;
      v28 = *(_OWORD *)(a3 + 184);
      *(_DWORD *)((char *)&v83 + 11) = v27;
      LOBYTE(v27) = *(_BYTE *)(a3 + 143);
      v87 = v28;
      v29 = *(_OWORD *)(a3 + 216);
      HIBYTE(v83) = v27;
      v30 = *(_QWORD *)(a3 + 144);
      v86 = v24;
      v31 = *(_OWORD *)(a3 + 200);
      v84 = v30;
      v89 = v29;
      v32 = *(_OWORD *)(a3 + 240);
      v88 = v31;
      *(_QWORD *)&v31 = *(_QWORD *)(a3 + 232);
      v91 = v32;
      v90 = v31;
    }
    v94 = v52 + 760;
    v81 = *(_WORD *)(a3 + 592);
    if ( v61 )
      v95 = v61 + 504;
    v33 = *(_QWORD *)(a3 + 290);
    v99 = *v11;
    v101 = *(_DWORD *)(a3 + 298);
    v102 = *(_WORD *)(a3 + 302);
    v93 = 1;
    v100 = v33;
    v9 = BaseSrvSxsCreateActivationContextFromStructEx(SourceProcessHandlea, v53, &v80, (union _LARGE_INTEGER)&v105, 0);
    if ( v9 >= 0 )
    {
      v34 = v97;
      v35 = (_DWORD *)(a3 + 312);
      v36 = (__int128 *)&v104;
      *(_QWORD *)(a3 + 272) = v96;
      *(_DWORD *)(a3 + 280) = v34;
      *(_DWORD *)(a3 + 284) = v98;
      *(_QWORD *)(a3 + 304) = v103;
      v37 = 2;
      do
      {
        v35 += 32;
        v38 = *v36;
        v39 = v36[1];
        v36 += 8;
        *((_OWORD *)v35 - 8) = v38;
        v40 = *(v36 - 6);
        *((_OWORD *)v35 - 7) = v39;
        v41 = *(v36 - 5);
        *((_OWORD *)v35 - 6) = v40;
        v42 = *(v36 - 4);
        *((_OWORD *)v35 - 5) = v41;
        v43 = *(v36 - 3);
        *((_OWORD *)v35 - 4) = v42;
        v44 = *(v36 - 2);
        *((_OWORD *)v35 - 3) = v43;
        v45 = *(v36 - 1);
        *((_OWORD *)v35 - 2) = v44;
        *((_OWORD *)v35 - 1) = v45;
        --v37;
      }
      while ( v37 );
      *v35 = *(_DWORD *)v36;
      *v11 = v99;
      goto LABEL_64;
    }
  }
LABEL_3:
  if ( (v7 & 0x40) != 0 )
  {
    if ( v71[0] )
      NtClose_0(v71[0]);
    if ( BaseAddress[0] )
      NtClose_0(BaseAddress[0]);
    if ( BaseAddress[1] )
      NtUnmapViewOfSection_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress[1]);
    if ( *(_QWORD *)&v64[16] && *(_QWORD *)&v64[16] != *(_QWORD *)(a3 + 144) )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&v64[16]);
    if ( v77[0] && v77[0] != *(PVOID *)(a3 + 144) )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v77[0]);
    if ( v74[0] )
      NtClose_0(v74[0]);
    if ( v75[0] )
      NtClose_0(v75[0]);
    if ( v75[1] )
      NtUnmapViewOfSection_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, v75[1]);
    if ( v63[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v63[1]);
    if ( Handle[0] )
      NtClose(Handle[0]);
  }
  result = (unsigned int)v9;
  if ( v8 )
    *(_WORD *)(a3 + 290) = v8;
  return result;
}

```

## disassembly

```asm
0x180001e00  mov     r11, rsp
0x180001e03  push    rbp
0x180001e04  push    rbx
0x180001e05  push    rsi
0x180001e06  push    r15
0x180001e08  lea     rbp, [r11-3D8h]
0x180001e0f  sub     rsp, 4B8h
0x180001e16  mov     rax, cs:__security_cookie
0x180001e1d  xor     rax, rsp
0x180001e20  mov     [rbp+3D0h+var_50], rax
0x180001e27  mov     rax, [rbp+3D0h+arg_20]
0x180001e2e  mov     rsi, r8
0x180001e31  mov     [r11-28h], rdi
0x180001e35  mov     r8d, 1F8h; Size
0x180001e3b  mov     [r11-38h], r13
0x180001e3f  mov     r13, rcx
0x180001e42  mov     [rbp+3D0h+var_450], rdx
0x180001e46  xor     edx, edx; Val
0x180001e48  mov     [rbp+3D0h+SourceProcessHandle], rcx
0x180001e4c  lea     rcx, [rbp+3D0h+var_2B0]; void *
0x180001e53  mov     [rsp+4D0h+var_458], r9
0x180001e58  mov     [rbp+3D0h+var_400], rax
0x180001e5c  call    memset_0
0x180001e61  mov     edi, [rsi+78h]
0x180001e64  xorps   xmm0, xmm0
0x180001e67  xorps   xmm1, xmm1
0x180001e6a  mov     [rbp+3D0h+var_408], 0
0x180001e72  xor     eax, eax
0x180001e74  xor     r15d, r15d
0x180001e77  mov     [rbp+3D0h+var_3B0], rax
0x180001e7b  mov     [rsp+4D0h+Buffer], rax
0x180001e80  mov     [rbp+3D0h+var_2B8], rax
0x180001e87  mov     [rbp+3D0h+var_340], rax
0x180001e8e  mov     [rbp+3D0h+var_378], rax
0x180001e92  mov     [rbp+3D0h+var_58], rax
0x180001e99  mov     [rbp+3D0h+var_80], rax
0x180001ea0  movups  [rbp+3D0h+var_B0], xmm0
0x180001ea7  movups  [rbp+3D0h+var_A0], xmm0
0x180001eae  movups  [rbp+3D0h+var_3E0], xmm0
0x180001eb2  movups  xmmword ptr [rbp+3D0h+P], xmm0
0x180001eb6  movups  [rbp+3D0h+var_3C0], xmm0
0x180001eba  movups  [rbp+3D0h+var_2E8], xmm1
0x180001ec1  movups  xmmword ptr [rbp+3D0h+var_2D8], xmm1
0x180001ec8  movups  [rbp+3D0h+var_2C8], xmm1
0x180001ecf  movups  xmmword ptr [rbp+3D0h+var_3F0], xmm0
0x180001ed3  movups  [rbp+3D0h+var_370], xmm1
0x180001ed7  movups  [rbp+3D0h+var_360], xmm1
0x180001edb  movups  [rbp+3D0h+var_350], xmm1
0x180001ee2  movups  [rbp+3D0h+var_3A8], xmm0
0x180001ee6  movups  [rbp+3D0h+var_398], xmm0
0x180001eea  movups  [rbp+3D0h+var_388], xmm0
0x180001eee  movups  xmmword ptr [rbp+3D0h+Handle], xmm0
0x180001ef2  movups  [rbp+3D0h+var_438], xmm0
0x180001ef6  movups  xmmword ptr [rbp+3D0h+var_338], xmm1
0x180001efd  movups  xmmword ptr [rbp+3D0h+BaseAddress], xmm1
0x180001f04  movups  xmmword ptr [rbp+3D0h+var_308], xmm0
0x180001f0b  movups  xmmword ptr [rbp+3D0h+var_2F8], xmm0
0x180001f12  movups  xmmword ptr [rbp+3D0h+IoStatusBlock], xmm0
0x180001f19  movups  [rbp+3D0h+FileInformation], xmm1
0x180001f20  movups  [rbp+3D0h+var_68], xmm1
0x180001f27  movups  [rbp+3D0h+var_90], xmm0
0x180001f2e  test    dil, 20h
0x180001f32  jz      loc_18000201C
0x180001f38  xor     ebx, ebx
0x180001f3a  mov     r13, [rsp+4D0h+var_30]
0x180001f42  test    dil, 40h
0x180001f46  mov     rdi, qword ptr [rsp+4D0h+var_20]
0x180001f4e  jz      loc_180001FF3
0x180001f54  mov     rcx, [rbp+3D0h+var_338]; Handle
0x180001f5b  test    rcx, rcx
0x180001f5e  jnz     loc_1800021DC
0x180001f64  mov     rcx, [rbp+3D0h+BaseAddress]; Handle
0x180001f6b  test    rcx, rcx
0x180001f6e  jnz     loc_180002741
0x180001f74  mov     rdx, [rbp+3D0h+BaseAddress+8]; BaseAddress
0x180001f7b  test    rdx, rdx
0x180001f7e  jnz     loc_18000274B
0x180001f84  mov     r8, [rbp+3D0h+P]; P
0x180001f88  test    r8, r8
0x180001f8b  jnz     loc_180002167
0x180001f91  mov     r8, [rbp+3D0h+var_2D8]; P
0x180001f98  test    r8, r8
0x180001f9b  jnz     loc_18000275C
0x180001fa1  mov     rcx, [rbp+3D0h+var_308]; Handle
0x180001fa8  test    rcx, rcx
0x180001fab  jnz     loc_1800021E6
0x180001fb1  mov     rcx, [rbp+3D0h+var_2F8]; Handle
0x180001fb8  test    rcx, rcx
0x180001fbb  jnz     loc_180002789
0x180001fc1  mov     rdx, [rbp+3D0h+var_2F8+8]; BaseAddress
0x180001fc8  test    rdx, rdx
0x180001fcb  jnz     loc_180002793
0x180001fd1  mov     r8, [rbp+3D0h+var_3F0+8]; P
0x180001fd5  test    r8, r8
0x180001fd8  jnz     loc_1800021BC
0x180001fde  mov     rcx, [rbp+3D0h+Handle]; Handle
0x180001fe2  test    rcx, rcx
0x180001fe5  jz      short loc_180001FF3
0x180001fe7  call    cs:__imp_NtClose
0x180001fee  nop     dword ptr [rax+rax+00h]
0x180001ff3  mov     eax, ebx
0x180001ff5  test    r15w, r15w
0x180001ff9  jnz     loc_1800027A4
0x180001fff  mov     rcx, [rbp+3D0h+var_50]
0x180002006  xor     rcx, rsp; StackCookie
0x180002009  call    __security_check_cookie
0x18000200e  add     rsp, 4B8h
0x180002015  pop     r15
0x180002017  pop     rsi
0x180002018  pop     rbx
0x180002019  pop     rbp
0x18000201a  retn
0x18000201c  mov     [rsp+4D0h+var_38], r14
0x180002024  mov     r14d, edi
0x180002027  and     r14d, 40h
0x18000202b  jz      loc_180002627
0x180002031  mov     [rsp+4D0h+var_28], r12
0x180002039  lea     rax, [rsi+88h]
0x180002040  mov     [rbp+3D0h+var_428], rax
0x180002044  lea     rcx, [rsi+100h]
0x18000204b  lea     r12, [rsi+120h]
0x180002052  test    r14d, r14d
0x180002055  jz      loc_180002194
0x18000205b  lea     rax, [rsi+98h]
0x180002062  mov     [rbp+3D0h+var_418], rcx
0x180002066  mov     [rbp+3D0h+var_420], rax
0x18000206a  mov     edx, 4
0x18000206f  mov     [rbp+3D0h+var_410], r12
0x180002073  lea     r8, [rbp+3D0h+var_428]
0x180002077  mov     rcx, rsi
0x18000207a  call    BaseSrvSxsValidateMessageStrings
0x18000207f  mov     ebx, eax
0x180002081  test    eax, eax
0x180002083  js      loc_180002152
0x180002089  movzx   eax, word ptr [rsi+122h]
0x180002090  test    ax, ax
0x180002093  jnz     loc_180002638
0x180002099  xor     edx, edx
0x18000209b  cmp     [rsi+122h], dx
0x1800020a2  jnz     loc_18000267C
0x1800020a8  test    r14d, r14d
0x1800020ab  lea     r14, [rsi+80h]
0x1800020b2  jz      loc_180002710
0x1800020b8  mov     rax, [rbp+3D0h+var_450]
0x1800020bc  lea     r9, [rbp+3D0h+Handle]; TargetHandle
0x1800020c0  mov     [rsp+4D0h+Options], 2; Options
0x1800020c8  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800020cf  mov     [rsp+4D0h+HandleAttributes], edx; HandleAttributes
0x1800020d3  mov     rcx, r13; SourceProcessHandle
0x1800020d6  mov     [rsp+4D0h+DesiredAccess], edx; DesiredAccess
0x1800020da  mov     rdx, [r14]; SourceHandle
0x1800020dd  mov     [rbp+3D0h+Handle+8], rax
0x1800020e1  call    cs:__imp_NtDuplicateObject
0x1800020e8  nop     dword ptr [rax+rax+00h]
0x1800020ed  mov     ebx, eax
0x1800020ef  test    eax, eax
0x1800020f1  js      short loc_180002152
0x1800020f3  lea     r13, [rsi+0B0h]
0x1800020fa  xor     r8d, r8d
0x1800020fd  mov     rcx, [r13+0]
0x180002101  test    rcx, rcx
0x180002104  jnz     loc_180002699
0x18000210a  mov     rcx, [rsi+0C0h]
0x180002111  test    rcx, rcx
0x180002114  jnz     loc_1800026D7
0x18000211a  mov     rdx, [rsp+4D0h+var_458]
0x18000211f  mov     r9d, 8; NumberOfBytesToRead
0x180002125  mov     rcx, [rbp+3D0h+Handle+8]; ProcessHandle
0x180002129  add     rdx, 10h; BaseAddress
0x18000212d  mov     [rsp+4D0h+Buffer], r8
0x180002132  mov     qword ptr [rsp+4D0h+DesiredAccess], r8; NumberOfBytesRead
0x180002137  lea     r8, [rsp+4D0h+Buffer]; Buffer
0x18000213c  call    cs:__imp_NtReadVirtualMemory
0x180002143  nop     dword ptr [rax+rax+00h]
0x180002148  mov     ebx, eax
0x18000214a  test    eax, eax
0x18000214c  jns     loc_1800021F0
0x180002152  mov     r12, [rsp+4D0h+var_28]
0x18000215a  mov     r14, [rsp+4D0h+var_38]
0x180002162  jmp     loc_180001F3A
0x180002167  cmp     r8, [rsi+90h]
0x18000216e  jz      loc_180001F91
0x180002174  mov     rcx, gs:60h
0x18000217d  xor     edx, edx; Flags
0x18000217f  mov     rcx, [rcx+30h]; HeapHandle
0x180002183  call    cs:__imp_RtlFreeHeap
0x18000218a  nop     dword ptr [rax+rax+00h]
0x18000218f  jmp     loc_180001F91
0x180002194  lea     rax, [rsi+0C0h]
0x18000219b  mov     [rbp+3D0h+var_410], rcx
0x18000219f  mov     [rbp+3D0h+var_420], rax
0x1800021a3  mov     edx, 5
0x1800021a8  lea     rax, [rsi+0F0h]
0x1800021af  mov     [rbp+3D0h+var_408], r12
0x1800021b3  mov     [rbp+3D0h+var_418], rax
0x1800021b7  jmp     loc_180002073
0x1800021bc  mov     rcx, gs:60h
0x1800021c5  xor     edx, edx; Flags
0x1800021c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800021cb  call    cs:__imp_RtlFreeHeap
0x1800021d2  nop     dword ptr [rax+rax+00h]
0x1800021d7  jmp     loc_180001FDE
0x1800021dc  call    NtClose_0
0x1800021e1  jmp     loc_180001F64
0x1800021e6  call    NtClose_0
0x1800021eb  jmp     loc_180001FB1
0x1800021f0  mov     rax, [rsp+4D0h+Buffer]
0x1800021f5  mov     qword ptr [rbp+3D0h+var_438+8], rax
0x1800021f9  mov     edx, [rsi+78h]
0x1800021fc  lea     r8, [rsi+7Ch]
0x180002200  mov     r9d, [rsi+0D0h]
0x180002207  lea     rcx, [rsi+98h]
0x18000220e  xor     eax, eax
0x180002210  mov     [rsp+4D0h+var_468], r8
0x180002215  mov     r8, [rsi+0C8h]
0x18000221c  lea     r11, [rbp+3D0h+var_3A8]
0x180002220  shr     edx, 9
0x180002223  lea     r10, [rbp+3D0h+var_370]
0x180002227  not     edx
0x180002229  and     edx, 1
0x18000222c  cmp     [rsi+0C0h], rax
0x180002233  cmovz   r11, rax
0x180002237  cmp     [r13+0], rax
0x18000223b  cmovz   r10, rax
0x18000223f  lea     rax, [rbp+3D0h+var_3F0]
0x180002243  mov     [rsp+4D0h+var_470], rax
0x180002248  lea     rax, [rbp+3D0h+var_2E8]
0x18000224f  mov     [rsp+4D0h+var_478], rax
0x180002254  lea     rax, [rbp+3D0h+var_308]
0x18000225b  mov     [rsp+4D0h+var_480], rax
0x180002260  lea     rax, [rbp+3D0h+var_3E0]
0x180002264  mov     [rsp+4D0h+var_488], rax
0x180002269  lea     rax, [rbp+3D0h+var_338]
0x180002270  mov     [rsp+4D0h+var_490], rax
0x180002275  lea     rax, [rsi+88h]
0x18000227c  mov     dword ptr [rsp+4D0h+var_498], edx
0x180002280  mov     rdx, r11
0x180002283  mov     qword ptr [rsp+4D0h+Options], rcx
0x180002288  mov     rcx, r10
0x18000228b  mov     qword ptr [rsp+4D0h+HandleAttributes], rax
0x180002290  lea     rax, [rbp+3D0h+Handle]
0x180002294  mov     qword ptr [rsp+4D0h+DesiredAccess], rax
0x180002299  call    BaseSrvSxsProbeManifestAndPolicyAndDotLocal
0x18000229e  mov     ebx, eax
0x1800022a0  test    eax, eax
0x1800022a2  js      loc_180002152
0x1800022a8  test    dword ptr [rsi+7Ch], 2000h
0x1800022af  jz      loc_180002614
0x1800022b5  movups  xmm0, xmmword ptr [rsi+100h]
0x1800022bc  mov     rcx, [rbp+3D0h+var_2B8]
0x1800022c3  or      edi, 1
0x1800022c6  movups  [rbp+3D0h+var_2A8], xmm0
0x1800022cd  test    rcx, rcx
0x1800022d0  jnz     loc_180002708
0x1800022d6  mov     [rbp+3D0h+var_2B0], edi
0x1800022dc  test    dil, 40h
0x1800022e0  jz      loc_18000242B
0x1800022e6  cmp     qword ptr [r13+0], 0
0x1800022eb  movzx   eax, word ptr [rbp+3D0h+var_3E0]
0x1800022ef  movsd   xmm0, qword ptr [rbp+3D0h+var_3E0+3]
0x1800022f4  movups  xmm1, [rbp+3D0h+var_3C0+8]
0x1800022f8  movzx   edx, byte ptr [rbp+3D0h+var_3E0+2]
0x1800022fc  movsd   [rbp+3D0h+var_295], xmm0
0x180002304  movups  xmm0, xmmword ptr [rbp+3D0h+P+8]
0x180002308  mov     [rbp+3D0h+var_298], ax
0x18000230f  mov     eax, dword ptr [rbp+3D0h+var_3E0+0Bh]
0x180002312  movaps  [rbp+3D0h+var_280], xmm0
0x180002319  movups  xmm0, [rbp+3D0h+var_2E8]
0x180002320  mov     [rbp+3D0h+var_28D], eax
0x180002326  movzx   eax, byte ptr [rbp+3D0h+var_3E0+0Fh]
0x18000232a  movaps  [rbp+3D0h+var_260], xmm0
0x180002331  movups  xmm0, [rbp+3D0h+var_2C8]
0x180002338  mov     [rbp+3D0h+var_289], al
0x18000233e  mov     rax, [rbp+3D0h+P]
0x180002342  movaps  [rbp+3D0h+var_240], xmm0
0x180002349  movups  xmm0, xmmword ptr [rbp+3D0h+var_3F0]
0x18000234d  mov     [rbp+3D0h+var_296], dl
0x180002353  movaps  [rbp+3D0h+var_270], xmm1
0x18000235a  movups  xmm1, xmmword ptr [rbp+3D0h+var_2D8]
0x180002361  mov     [rbp+3D0h+var_288], rax
0x180002368  movups  [rbp+3D0h+var_228], xmm0
0x18000236f  mov     [rbp+3D0h+var_230], rcx
0x180002376  movaps  [rbp+3D0h+var_250], xmm1
0x18000237d  jnz     loc_1800024CF
0x180002383  mov     r14, [rbp+3D0h+var_338]
0x18000238a  lea     r8, [rbp+3D0h+FileInformation]; FileInformation
0x180002391  cmp     dl, 4
0x180002394  mov     [rsp+4D0h+DesiredAccess], 4; FileInformationClass
0x18000239c  mov     r9d, 28h ; '('; Length
0x1800023a2  lea     rdx, [rbp+3D0h+IoStatusBlock]; IoStatusBlock
0x1800023a9  cmovz   r14, [rbp+3D0h+Handle]
0x1800023ae  mov     rcx, r14; FileHandle
0x1800023b1  call    cs:__imp_NtQueryInformationFile
0x1800023b8  nop     dword ptr [rax+rax+00h]
0x1800023bd  mov     ebx, eax
0x1800023bf  test    eax, eax
0x1800023c1  js      loc_180002152
0x1800023c7  mov     rax, qword ptr [rbp+3D0h+var_68]
0x1800023ce  lea     r8, [rbp+3D0h+var_90]; FileInformation
0x1800023d5  mov     r9d, 18h; Length
  ... truncated ...
```
