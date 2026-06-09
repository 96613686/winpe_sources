# InternalSxsCreateProcess

- ea: `0x180001d80`
- end: `0x1800026d0`
- name: `InternalSxsCreateProcess`
- size: `2384`
- prototype: `__int64 __fastcall(void *, void *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180001cd0`

## callees

- `0x180001d80`
- `0x1800026e0`
- `0x180002800`
- `0x180003170`
- `0x180006580`
- `0x180006598`
- `0x180006c13`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800022f9`
- `ntdll!RtlFreeHeap` at `0x18000247b`
- `ntdll!RtlFreeHeap` at `0x180002697`
- `ntdll!RtlFreeHeap` at `0x1800022f9`
- `ntdll!RtlFreeHeap` at `0x18000247b`
- `ntdll!RtlFreeHeap` at `0x180002697`
- `ntdll!NtClose` at `0x180001f4c`
- `ntdll!NtClose` at `0x180001f4c`
- `ntdll!NtQueryInformationFile` at `0x180002276`
- `ntdll!NtQueryInformationFile` at `0x1800022b9`
- `ntdll!NtQueryInformationFile` at `0x180002276`
- `ntdll!NtQueryInformationFile` at `0x1800022b9`
- `ntdll!NtDuplicateObject` at `0x180002056`
- `ntdll!NtDuplicateObject` at `0x180002056`
- `ntdll!NtReadVirtualMemory` at `0x1800020b0`
- `ntdll!NtReadVirtualMemory` at `0x1800020b0`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000257e`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000257e`

## pseudocode

```c
__int64 __fastcall InternalSxsCreateProcess(void *a1, void *a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v7; // esi
  __int16 v8; // r14
  int v9; // ebx
  __int64 result; // rax
  __int64 v11; // rdx
  void *v12; // rdx
  __int64 v13; // rcx
  __int128 *v14; // rdx
  __int64 v15; // rcx
  NTSTATUS v16; // eax
  _OWORD *v17; // r10
  _OWORD *v18; // rcx
  __int128 v19; // xmm2
  bool v20; // zf
  HANDLE v21; // r15
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm0
  __int128 v28; // xmm0
  int v29; // eax
  _DWORD *v30; // rcx
  __int64 v31; // rdx
  __int128 *v32; // rax
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  _WORD *v41; // rax
  __int128 v42; // xmm0
  __int64 v43; // rax
  __int128 v44; // xmm0
  __int64 v45; // rax
  __int64 Buffer; // [rsp+78h] [rbp-90h] BYREF
  void *v47; // [rsp+80h] [rbp-88h]
  HANDLE SourceProcessHandle; // [rsp+88h] [rbp-80h]
  PVOID v49[2]; // [rsp+90h] [rbp-78h] BYREF
  HANDLE Handle[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v51; // [rsp+B0h] [rbp-58h]
  __int64 v52; // [rsp+C0h] [rbp-48h]
  _OWORD v53[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v54; // [rsp+E8h] [rbp-20h]
  __int64 v55; // [rsp+F8h] [rbp-10h]
  _OWORD v56[2]; // [rsp+100h] [rbp-8h] BYREF
  __int128 v57; // [rsp+120h] [rbp+18h]
  __int64 v58; // [rsp+130h] [rbp+28h]
  HANDLE v59[2]; // [rsp+138h] [rbp+30h] BYREF
  HANDLE BaseAddress[2]; // [rsp+148h] [rbp+40h]
  __int128 v61; // [rsp+158h] [rbp+50h] BYREF
  PVOID P[2]; // [rsp+168h] [rbp+60h]
  __int128 v63; // [rsp+178h] [rbp+70h]
  __int64 v64; // [rsp+188h] [rbp+80h]
  __int128 v65; // [rsp+190h] [rbp+88h] BYREF
  PVOID v66[2]; // [rsp+1A0h] [rbp+98h]
  __int128 v67; // [rsp+1B0h] [rbp+A8h]
  __int64 v68; // [rsp+1C0h] [rbp+B8h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1C8h] [rbp+C0h] BYREF
  HANDLE v70[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  HANDLE v71[2]; // [rsp+1E8h] [rbp+E0h]
  unsigned int v72; // [rsp+1F8h] [rbp+F0h] BYREF
  __int16 v73; // [rsp+1FCh] [rbp+F4h]
  __int128 v74; // [rsp+200h] [rbp+F8h]
  __int128 v75; // [rsp+210h] [rbp+108h]
  __int128 v76; // [rsp+220h] [rbp+118h]
  __int128 v77; // [rsp+230h] [rbp+128h]
  __int64 v78; // [rsp+240h] [rbp+138h]
  __int128 v79; // [rsp+248h] [rbp+140h]
  __int128 v80; // [rsp+258h] [rbp+150h]
  __int128 v81; // [rsp+268h] [rbp+160h]
  __int64 v82; // [rsp+278h] [rbp+170h]
  __int128 v83; // [rsp+280h] [rbp+178h]
  __int64 v84; // [rsp+2A0h] [rbp+198h]
  __int64 v85; // [rsp+2A8h] [rbp+1A0h]
  __int64 v86; // [rsp+2B0h] [rbp+1A8h]
  __int64 v87; // [rsp+2B8h] [rbp+1B0h]
  __int64 v88; // [rsp+2C0h] [rbp+1B8h]
  int v89; // [rsp+2C8h] [rbp+1C0h]
  int v90; // [rsp+2CCh] [rbp+1C4h]
  __int128 v91; // [rsp+2D0h] [rbp+1C8h]
  __int64 v92; // [rsp+2E0h] [rbp+1D8h]
  char v93; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int128 v94; // [rsp+3F8h] [rbp+2F0h] BYREF
  __int128 v95; // [rsp+408h] [rbp+300h]
  __int128 v96; // [rsp+418h] [rbp+310h] BYREF
  __int64 v97; // [rsp+428h] [rbp+320h]
  __int128 FileInformation; // [rsp+430h] [rbp+328h] BYREF
  __int128 v99; // [rsp+440h] [rbp+338h]
  __int64 v100; // [rsp+450h] [rbp+348h]
  __int64 v101; // [rsp+458h] [rbp+350h] BYREF
  __int64 v102; // [rsp+460h] [rbp+358h]
  __int64 v103; // [rsp+468h] [rbp+360h]
  __int64 v104; // [rsp+470h] [rbp+368h]
  __int64 v105; // [rsp+478h] [rbp+370h]

  v47 = a2;
  SourceProcessHandle = a1;
  v52 = a5;
  memset_0(&v72, 0, 0x1F8u);
  v7 = *(_DWORD *)(a3 + 120);
  v64 = 0;
  v105 = 0;
  v8 = 0;
  v68 = 0;
  v58 = 0;
  v55 = 0;
  v100 = 0;
  v97 = 0;
  v94 = 0;
  v95 = 0;
  v61 = 0;
  *(_OWORD *)P = 0;
  v63 = 0;
  v65 = 0;
  *(_OWORD *)v66 = 0;
  v67 = 0;
  *(_OWORD *)v49 = 0;
  memset(v56, 0, sizeof(v56));
  v57 = 0;
  memset(v53, 0, sizeof(v53));
  v54 = 0;
  *(_OWORD *)Handle = 0;
  v51 = 0;
  *(_OWORD *)v59 = 0;
  *(_OWORD *)BaseAddress = 0;
  *(_OWORD *)v70 = 0;
  *(_OWORD *)v71 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v99 = 0;
  v96 = 0;
  if ( (v7 & 0x20) != 0 )
  {
    v9 = 0;
    goto LABEL_3;
  }
  if ( (v7 & 0x41) == 0 )
  {
    v9 = 0;
    goto LABEL_3;
  }
  v101 = a3 + 136;
  if ( (v7 & 0x40) != 0 )
  {
    v103 = a3 + 256;
    v102 = a3 + 152;
    v11 = 4;
    v104 = a3 + 288;
  }
  else
  {
    v104 = a3 + 256;
    v102 = a3 + 192;
    v11 = 5;
    v105 = a3 + 288;
    v103 = a3 + 240;
  }
  v9 = BaseSrvSxsValidateMessageStrings(a3, v11, &v101);
  if ( v9 < 0 )
    goto LABEL_3;
  if ( *(_WORD *)(a3 + 290)
    && !(unsigned __int8)CsrValidateMessageBuffer(a3, a3 + 296, *(unsigned __int16 *)(a3 + 290), 1) )
  {
    v8 = *(_WORD *)(a3 + 290);
    *(_WORD *)(a3 + 290) = *(_WORD *)(a3 + 288) + 2;
  }
  if ( *(_WORD *)(a3 + 290) )
  {
    v41 = *(_WORD **)(a3 + 296);
    if ( v41 )
    {
      *v41 = 0;
      *(_WORD *)(a3 + 288) = 0;
    }
  }
  if ( (v7 & 0x40) != 0 )
  {
    v12 = *(void **)(a3 + 128);
    Handle[1] = v47;
    v9 = NtDuplicateObject(SourceProcessHandle, v12, (HANDLE)0xFFFFFFFFFFFFFFFFLL, Handle, 0, 0, 2u);
    if ( v9 < 0 )
      goto LABEL_3;
    v13 = *(_QWORD *)(a3 + 176);
    v14 = (__int128 *)(a3 + 136);
    if ( v13 )
    {
      v42 = *v14;
      v43 = *(_QWORD *)(a3 + 168);
      v7 |= 0x100u;
      LOWORD(v56[0]) = 769;
      *(_OWORD *)((char *)v56 + 8) = v42;
      *((_QWORD *)&v56[1] + 1) = 0;
      BYTE2(v56[0]) = 2;
      *(_QWORD *)&v57 = 0;
      *((_QWORD *)&v57 + 1) = v43;
      v58 = v13;
    }
    v15 = *(_QWORD *)(a3 + 192);
    if ( v15 )
    {
      v44 = *v14;
      v45 = *(_QWORD *)(a3 + 184);
      LOWORD(v53[0]) = 769;
      *(_OWORD *)((char *)v53 + 8) = v44;
      *((_QWORD *)&v53[1] + 1) = 0;
      BYTE2(v53[0]) = 2;
      *(_QWORD *)&v54 = 0;
      *((_QWORD *)&v54 + 1) = v45;
      v55 = v15;
    }
    Buffer = 0;
    v16 = NtReadVirtualMemory(Handle[1], (PVOID)(a4 + 16), &Buffer, 8u, 0);
    if ( v16 >= 0 )
      *((_QWORD *)&v51 + 1) = Buffer;
    v9 = 0;
    if ( v16 < 0 )
      v9 = v16;
    if ( v9 < 0 )
      goto LABEL_3;
    v17 = v53;
    v18 = v56;
    if ( !*(_QWORD *)(a3 + 192) )
      v17 = 0;
    if ( !*(_QWORD *)(a3 + 176) )
      v18 = 0;
    v9 = BaseSrvSxsProbeManifestAndPolicyAndDotLocal(
           (__int64)v18,
           (__int64)v17,
           *(_QWORD *)(a3 + 200),
           *(_DWORD *)(a3 + 208),
           (__int64)Handle,
           (unsigned __int16 *)(a3 + 136),
           (unsigned __int16 *)(a3 + 152),
           (*(_DWORD *)(a3 + 120) & 0x200) == 0,
           (__int64)v59,
           (__int64)&v61,
           (__int64)v70,
           (__int64)&v65,
           v49,
           (_DWORD *)(a3 + 124));
    if ( v9 < 0 )
      goto LABEL_3;
    if ( (*(_DWORD *)(a3 + 124) & 0x2000) == 0 )
    {
      v9 = 0;
      goto LABEL_3;
    }
    v19 = v61;
    v7 |= 1u;
    if ( v68 )
      v7 |= 2u;
  }
  else
  {
    v19 = 0;
  }
  v72 = v7;
  v74 = *(_OWORD *)(a3 + 256);
  if ( (v7 & 0x40) == 0 )
  {
    v22 = *(_OWORD *)(a3 + 144);
    v75 = *(_OWORD *)(a3 + 128);
    v23 = *(_OWORD *)(a3 + 160);
    v76 = v22;
    *(_QWORD *)&v22 = *(_QWORD *)(a3 + 176);
    v77 = v23;
    v24 = *(_OWORD *)(a3 + 184);
    v78 = v22;
    v25 = *(_OWORD *)(a3 + 200);
    v79 = v24;
    v26 = *(_OWORD *)(a3 + 216);
    v80 = v25;
    *(_QWORD *)&v25 = *(_QWORD *)(a3 + 232);
    v81 = v26;
    v27 = *(_OWORD *)(a3 + 240);
    v82 = v25;
    v83 = v27;
    goto LABEL_60;
  }
  v20 = *(_QWORD *)(a3 + 176) == 0;
  v77 = v63;
  v76 = *(_OWORD *)P;
  v79 = v65;
  v78 = v64;
  v81 = v67;
  v80 = *(_OWORD *)v66;
  v83 = *(_OWORD *)v49;
  v75 = v19;
  v82 = v68;
  if ( !v20 )
  {
LABEL_60:
    v86 = a4 + 760;
    v73 = *(_WORD *)(a3 + 592);
    if ( v52 )
      v87 = v52 + 504;
    v28 = *(_OWORD *)(a3 + 288);
    v85 = 1;
    v91 = v28;
    v9 = BaseSrvSxsCreateActivationContextFromStructEx(SourceProcessHandle, v47, &v72, (union _LARGE_INTEGER)&v94, 0);
    if ( v9 >= 0 )
    {
      v29 = v89;
      v30 = (_DWORD *)(a3 + 312);
      v31 = 2;
      *(_QWORD *)(a3 + 272) = v88;
      *(_DWORD *)(a3 + 280) = v29;
      *(_DWORD *)(a3 + 284) = v90;
      *(_QWORD *)(a3 + 304) = v92;
      v32 = (__int128 *)&v93;
      do
      {
        v30 += 32;
        v33 = *v32;
        v34 = v32[1];
        v32 += 8;
        *((_OWORD *)v30 - 8) = v33;
        v35 = *(v32 - 6);
        *((_OWORD *)v30 - 7) = v34;
        v36 = *(v32 - 5);
        *((_OWORD *)v30 - 6) = v35;
        v37 = *(v32 - 4);
        *((_OWORD *)v30 - 5) = v36;
        v38 = *(v32 - 3);
        *((_OWORD *)v30 - 4) = v37;
        v39 = *(v32 - 2);
        *((_OWORD *)v30 - 3) = v38;
        v40 = *(v32 - 1);
        *((_OWORD *)v30 - 2) = v39;
        *((_OWORD *)v30 - 1) = v40;
        --v31;
      }
      while ( v31 );
      v9 = 0;
      *v30 = *(_DWORD *)v32;
      *(_WORD *)(a3 + 288) = v91;
    }
    goto LABEL_3;
  }
  v21 = v59[0];
  if ( BYTE2(v19) == 4 )
    v21 = Handle[0];
  v9 = NtQueryInformationFile(v21, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
  if ( v9 >= 0 )
  {
    v84 = v99;
    if ( NtQueryInformationFile(v21, &IoStatusBlock, &v96, 0x18u, FileMaximumInformation|FileBothDirectoryInformation) >= 0 )
    {
      v94 = v96;
      *(_QWORD *)&v95 = v97;
    }
    else
    {
      DWORD2(v95) |= 1u;
    }
    goto LABEL_60;
  }
LABEL_3:
  if ( (v7 & 0x40) != 0 )
  {
    if ( v59[0] )
      NtClose_0(v59[0]);
    if ( BaseAddress[0] )
      NtClose_0(BaseAddress[0]);
    if ( BaseAddress[1] )
      NtUnmapViewOfSection_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress[1]);
    if ( P[0] && P[0] != *(PVOID *)(a3 + 144) )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    if ( v66[0] && v66[0] != *(PVOID *)(a3 + 144) )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v66[0]);
    if ( v70[0] )
      NtClose_0(v70[0]);
    if ( v71[0] )
      NtClose_0(v71[0]);
    if ( v71[1] )
      NtUnmapViewOfSection_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, v71[1]);
    if ( v49[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v49[1]);
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
0x180001d80  mov     r11, rsp
0x180001d83  push    rbp
0x180001d84  push    rbx
0x180001d85  push    rdi
0x180001d86  push    r14
0x180001d88  lea     rbp, [r11-3C8h]
0x180001d8f  sub     rsp, 4A8h
0x180001d96  mov     rax, cs:__security_cookie
0x180001d9d  xor     rax, rsp
0x180001da0  mov     [rbp+3C0h+var_48], rax
0x180001da7  mov     rax, [rbp+3C0h+arg_20]
0x180001dae  mov     rdi, r8
0x180001db1  mov     [r11-28h], rsi
0x180001db5  mov     r8d, 1F8h; Size
0x180001dbb  mov     [rsp+4C0h+var_448], rdx
0x180001dc0  xor     edx, edx; Val
0x180001dc2  mov     [rbp+3C0h+SourceProcessHandle], rcx
0x180001dc6  lea     rcx, [rbp+3C0h+var_2D0]; void *
0x180001dcd  mov     [r11-38h], r13
0x180001dd1  mov     r13, r9
0x180001dd4  mov     [rbp+3C0h+var_408], rax
0x180001dd8  call    memset_0
0x180001ddd  mov     esi, [rdi+78h]
0x180001de0  xorps   xmm0, xmm0
0x180001de3  xor     eax, eax
0x180001de5  xorps   xmm1, xmm1
0x180001de8  xor     ecx, ecx
0x180001dea  mov     [rbp+3C0h+var_340], rax
0x180001df1  mov     [rbp+3C0h+var_50], rcx
0x180001df8  movzx   r14d, cx
0x180001dfc  mov     [rbp+3C0h+var_308], rax
0x180001e03  mov     [rbp+3C0h+var_398], rax
0x180001e07  mov     [rbp+3C0h+var_3D0], rax
0x180001e0b  mov     [rbp+3C0h+var_78], rax
0x180001e12  mov     [rbp+3C0h+var_A0], rax
0x180001e19  movups  [rbp+3C0h+var_D0], xmm0
0x180001e20  movups  [rbp+3C0h+var_C0], xmm0
0x180001e27  movups  [rbp+3C0h+var_370], xmm0
0x180001e2b  movups  xmmword ptr [rbp+3C0h+P], xmm0
0x180001e2f  movups  [rbp+3C0h+var_350], xmm0
0x180001e33  movups  [rbp+3C0h+var_338], xmm0
0x180001e3a  movups  xmmword ptr [rbp+3C0h+var_328], xmm0
0x180001e41  movups  [rbp+3C0h+var_318], xmm0
0x180001e48  movups  xmmword ptr [rbp+3C0h+var_438], xmm0
0x180001e4c  movups  [rbp+3C0h+var_3C8], xmm1
0x180001e50  movups  [rbp+3C0h+var_3B8], xmm1
0x180001e54  movups  [rbp+3C0h+var_3A8], xmm1
0x180001e58  movups  [rbp+3C0h+var_400], xmm0
0x180001e5c  movups  [rbp+3C0h+var_3F0], xmm0
0x180001e60  movups  [rbp+3C0h+var_3E0], xmm0
0x180001e64  movups  xmmword ptr [rbp+3C0h+Handle], xmm0
0x180001e68  movups  [rbp+3C0h+var_418], xmm0
0x180001e6c  movups  xmmword ptr [rbp+3C0h+var_390], xmm1
0x180001e70  movups  xmmword ptr [rbp+3C0h+BaseAddress], xmm1
0x180001e74  movups  xmmword ptr [rbp+3C0h+var_2F0], xmm0
0x180001e7b  movups  xmmword ptr [rbp+3C0h+var_2E0], xmm0
0x180001e82  movups  xmmword ptr [rbp+3C0h+IoStatusBlock], xmm0
0x180001e89  movups  [rbp+3C0h+FileInformation], xmm1
0x180001e90  movups  [rbp+3C0h+var_88], xmm1
0x180001e97  movups  [rbp+3C0h+var_B0], xmm0
0x180001e9e  test    sil, 20h
0x180001ea2  jz      loc_180001F81
0x180001ea8  mov     ebx, ecx
0x180001eaa  mov     r13, [rsp+4C0h+var_30]
0x180001eb2  test    sil, 40h
0x180001eb6  mov     rsi, qword ptr [rsp+4C0h+var_20]
0x180001ebe  jz      loc_180001F58
0x180001ec4  mov     rcx, [rbp+3C0h+var_390]; Handle
0x180001ec8  test    rcx, rcx
0x180001ecb  jnz     loc_180002550
0x180001ed1  mov     rcx, [rbp+3C0h+BaseAddress]; Handle
0x180001ed5  test    rcx, rcx
0x180001ed8  jnz     loc_180002659
0x180001ede  mov     rdx, [rbp+3C0h+BaseAddress+8]; BaseAddress
0x180001ee2  test    rdx, rdx
0x180001ee5  jnz     loc_180002663
0x180001eeb  mov     rax, [rbp+3C0h+P]
0x180001eef  test    rax, rax
0x180001ef2  jnz     loc_1800022D9
0x180001ef8  mov     rax, [rbp+3C0h+var_328]
0x180001eff  test    rax, rax
0x180001f02  jnz     loc_180002674
0x180001f08  mov     rcx, [rbp+3C0h+var_2F0]; Handle
0x180001f0f  test    rcx, rcx
0x180001f12  jnz     loc_18000255A
0x180001f18  mov     rcx, [rbp+3C0h+var_2E0]; Handle
0x180001f1f  test    rcx, rcx
0x180001f22  jnz     loc_1800026A8
0x180001f28  mov     rdx, [rbp+3C0h+var_2E0+8]; BaseAddress
0x180001f2f  test    rdx, rdx
0x180001f32  jnz     loc_1800026B2
0x180001f38  cmp     [rbp+3C0h+var_438+8], 0
0x180001f3d  jnz     loc_180002468
0x180001f43  mov     rcx, [rbp+3C0h+Handle]; Handle
0x180001f47  test    rcx, rcx
0x180001f4a  jz      short loc_180001F58
0x180001f4c  call    cs:__imp_NtClose
0x180001f53  nop     dword ptr [rax+rax+00h]
0x180001f58  mov     eax, ebx
0x180001f5a  test    r14w, r14w
0x180001f5e  jnz     loc_1800026C3
0x180001f64  mov     rcx, [rbp+3C0h+var_48]
0x180001f6b  xor     rcx, rsp; StackCookie
0x180001f6e  call    __security_check_cookie
0x180001f73  add     rsp, 4A8h
0x180001f7a  pop     r14
0x180001f7c  pop     rdi
0x180001f7d  pop     rbx
0x180001f7e  pop     rbp
0x180001f7f  retn
0x180001f81  test    sil, 41h
0x180001f85  jz      loc_180002564
0x180001f8b  mov     [rsp+4C0h+var_28], r12
0x180001f93  lea     rax, [rdi+88h]
0x180001f9a  mov     [rsp+4C0h+var_38], r15
0x180001fa2  lea     r12, [rdi+100h]
0x180001fa9  mov     r15d, esi
0x180001fac  mov     [rbp+3C0h+var_70], rax
0x180001fb3  lea     rcx, [rdi+120h]
0x180001fba  and     r15d, 40h
0x180001fbe  jz      loc_180002411
0x180001fc4  lea     rax, [rdi+98h]
0x180001fcb  mov     [rbp+3C0h+var_60], r12
0x180001fd2  mov     [rbp+3C0h+var_68], rax
0x180001fd9  mov     edx, 4
0x180001fde  mov     [rbp+3C0h+var_58], rcx
0x180001fe5  lea     r8, [rbp+3C0h+var_70]
0x180001fec  mov     rcx, rdi
0x180001fef  call    BaseSrvSxsValidateMessageStrings
0x180001ff4  mov     ebx, eax
0x180001ff6  test    eax, eax
0x180001ff8  js      loc_1800023FC
0x180001ffe  movzx   eax, word ptr [rdi+122h]
0x180002005  test    ax, ax
0x180002008  jnz     loc_18000256B
0x18000200e  cmp     word ptr [rdi+122h], 0
0x180002016  jnz     loc_1800025B1
0x18000201c  test    r15d, r15d
0x18000201f  jz      loc_18000263F
0x180002025  mov     rax, [rsp+4C0h+var_448]
0x18000202a  lea     r9, [rbp+3C0h+Handle]; TargetHandle
0x18000202e  mov     rdx, [rdi+80h]; SourceHandle
0x180002035  xor     r15d, r15d
0x180002038  mov     rcx, [rbp+3C0h+SourceProcessHandle]; SourceProcessHandle
0x18000203c  mov     [rsp+4C0h+Options], 2; Options
0x180002044  mov     [rsp+4C0h+HandleAttributes], r15d; HandleAttributes
0x180002049  lea     r8, [r15-1]; TargetProcessHandle
0x18000204d  mov     [rbp+3C0h+Handle+8], rax
0x180002051  mov     [rsp+4C0h+DesiredAccess], r15d; DesiredAccess
0x180002056  call    cs:__imp_NtDuplicateObject
0x18000205d  nop     dword ptr [rax+rax+00h]
0x180002062  mov     ebx, eax
0x180002064  test    eax, eax
0x180002066  js      loc_1800023FC
0x18000206c  mov     rcx, [rdi+0B0h]
0x180002073  lea     rdx, [rdi+88h]
0x18000207a  test    rcx, rcx
0x18000207d  jnz     loc_1800025D2
0x180002083  mov     rcx, [rdi+0C0h]
0x18000208a  test    rcx, rcx
0x18000208d  jnz     loc_180002603
0x180002093  mov     rcx, [rbp+3C0h+Handle+8]; ProcessHandle
0x180002097  lea     rdx, [r13+10h]; BaseAddress
0x18000209b  mov     r9d, 8; NumberOfBytesToRead
0x1800020a1  mov     [rsp+4C0h+Buffer], r15
0x1800020a6  lea     r8, [rsp+4C0h+Buffer]; Buffer
0x1800020ab  mov     qword ptr [rsp+4C0h+DesiredAccess], r15; NumberOfBytesRead
0x1800020b0  call    cs:__imp_NtReadVirtualMemory
0x1800020b7  nop     dword ptr [rax+rax+00h]
0x1800020bc  test    eax, eax
0x1800020be  jns     loc_180002542
0x1800020c4  test    eax, eax
0x1800020c6  mov     ebx, r15d
0x1800020c9  cmovs   ebx, eax
0x1800020cc  test    ebx, ebx
0x1800020ce  js      loc_1800023FC
0x1800020d4  mov     edx, [rdi+78h]
0x1800020d7  lea     rax, [rdi+98h]
0x1800020de  mov     r9d, [rdi+0D0h]
0x1800020e5  lea     r10, [rbp+3C0h+var_400]
0x1800020e9  shr     edx, 9
0x1800020ec  lea     rcx, [rbp+3C0h+var_3C8]
0x1800020f0  mov     r8d, 0
0x1800020f6  lea     r15, [rdi+7Ch]
0x1800020fa  mov     [rsp+4C0h+var_458], r15
0x1800020ff  not     edx
0x180002101  and     edx, 1
0x180002104  cmp     qword ptr [rdi+0C0h], 0
0x18000210c  cmovz   r10, r8
0x180002110  cmp     [rdi+0B0h], r8
0x180002117  cmovz   rcx, r8
0x18000211b  lea     r8, [rbp+3C0h+var_438]
0x18000211f  mov     [rsp+4C0h+var_460], r8
0x180002124  lea     r8, [rbp+3C0h+var_338]
0x18000212b  mov     [rsp+4C0h+var_468], r8
0x180002130  lea     r8, [rbp+3C0h+var_2F0]
0x180002137  mov     [rsp+4C0h+var_470], r8
0x18000213c  lea     r8, [rbp+3C0h+var_370]
0x180002140  mov     [rsp+4C0h+var_478], r8
0x180002145  lea     r8, [rbp+3C0h+var_390]
0x180002149  mov     [rsp+4C0h+var_480], r8
0x18000214e  mov     r8, [rdi+0C8h]
0x180002155  mov     dword ptr [rsp+4C0h+var_488], edx
0x180002159  mov     rdx, r10
0x18000215c  mov     qword ptr [rsp+4C0h+Options], rax
0x180002161  lea     rax, [rdi+88h]
0x180002168  mov     qword ptr [rsp+4C0h+HandleAttributes], rax
0x18000216d  lea     rax, [rbp+3C0h+Handle]
0x180002171  mov     qword ptr [rsp+4C0h+DesiredAccess], rax
0x180002176  call    BaseSrvSxsProbeManifestAndPolicyAndDotLocal
0x18000217b  mov     ebx, eax
0x18000217d  test    eax, eax
0x18000217f  js      loc_1800023FC
0x180002185  test    dword ptr [r15], 2000h
0x18000218c  jz      loc_180002630
0x180002192  movups  xmm2, [rbp+3C0h+var_370]
0x180002196  or      esi, 1
0x180002199  cmp     [rbp+3C0h+var_308], 0
0x1800021a1  jnz     loc_180002637
0x1800021a7  mov     [rbp+3C0h+var_2D0], esi
0x1800021ad  movups  xmm0, xmmword ptr [r12]
0x1800021b2  movups  [rbp+3C0h+var_2C8], xmm0
0x1800021b9  test    sil, 40h
0x1800021bd  jz      loc_18000230A
0x1800021c3  cmp     qword ptr [rdi+0B0h], 0
0x1800021cb  movups  xmm1, [rbp+3C0h+var_350]
0x1800021cf  movups  xmm0, xmmword ptr [rbp+3C0h+P]
0x1800021d3  movups  [rbp+3C0h+var_298], xmm1
0x1800021da  movups  xmm1, [rbp+3C0h+var_338]
0x1800021e1  movups  [rbp+3C0h+var_2A8], xmm0
0x1800021e8  movsd   xmm0, [rbp+3C0h+var_340]
0x1800021f0  movaps  [rbp+3C0h+var_280], xmm1
0x1800021f7  movups  xmm1, [rbp+3C0h+var_318]
0x1800021fe  movsd   [rbp+3C0h+var_288], xmm0
0x180002206  movups  xmm0, xmmword ptr [rbp+3C0h+var_328]
0x18000220d  movaps  [rbp+3C0h+var_260], xmm1
0x180002214  movups  xmm1, xmmword ptr [rbp+3C0h+var_438]
0x180002218  movaps  [rbp+3C0h+var_270], xmm0
0x18000221f  movsd   xmm0, [rbp+3C0h+var_308]
0x180002227  movups  [rbp+3C0h+var_248], xmm1
0x18000222e  movups  [rbp+3C0h+var_2B8], xmm2
0x180002235  movsd   [rbp+3C0h+var_250], xmm0
0x18000223d  jnz     loc_18000238C
0x180002243  mov     r15, [rbp+3C0h+var_390]
0x180002247  lea     r8, [rbp+3C0h+FileInformation]; FileInformation
0x18000224e  movq    rax, xmm2
0x180002253  mov     [rsp+4C0h+DesiredAccess], 4; FileInformationClass
0x18000225b  shr     rax, 10h
0x18000225f  lea     rdx, [rbp+3C0h+IoStatusBlock]; IoStatusBlock
0x180002266  cmp     al, 4
0x180002268  mov     r9d, 28h ; '('; Length
0x18000226e  cmovz   r15, [rbp+3C0h+Handle]
0x180002273  mov     rcx, r15; FileHandle
0x180002276  call    cs:__imp_NtQueryInformationFile
0x18000227d  nop     dword ptr [rax+rax+00h]
0x180002282  mov     ebx, eax
0x180002284  test    eax, eax
0x180002286  js      loc_1800023FC
0x18000228c  mov     rax, qword ptr [rbp+3C0h+var_88]
0x180002293  lea     r8, [rbp+3C0h+var_B0]; FileInformation
0x18000229a  mov     r9d, 18h; Length
0x1800022a0  mov     [rbp+3C0h+var_228], rax
0x1800022a7  lea     rdx, [rbp+3C0h+IoStatusBlock]; IoStatusBlock
0x1800022ae  mov     [rsp+4C0h+DesiredAccess], 3Bh ; ';'; FileInformationClass
0x1800022b6  mov     rcx, r15; FileHandle
0x1800022b9  call    cs:__imp_NtQueryInformationFile
0x1800022c0  nop     dword ptr [rax+rax+00h]
0x1800022c5  test    eax, eax
0x1800022c7  jns     loc_180002445
0x1800022cd  or      dword ptr [rbp+3C0h+var_C0+8], 1
0x1800022d4  jmp     loc_18000238C
0x1800022d9  cmp     rax, [rdi+90h]
0x1800022e0  jz      loc_180001EF8
0x1800022e6  mov     rcx, gs:60h
0x1800022ef  xor     edx, edx; Flags
0x1800022f1  mov     r8, [rbp+3C0h+P]; P
0x1800022f5  mov     rcx, [rcx+30h]; HeapHandle
0x1800022f9  call    cs:__imp_RtlFreeHeap
0x180002300  nop     dword ptr [rax+rax+00h]
0x180002305  jmp     loc_180001EF8
0x18000230a  movups  xmm0, xmmword ptr [rdi+80h]
0x180002311  movups  xmm1, xmmword ptr [rdi+90h]
0x180002318  movups  [rbp+3C0h+var_2B8], xmm0
0x18000231f  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180002326  movups  [rbp+3C0h+var_2A8], xmm1
0x18000232d  movsd   xmm1, qword ptr [rdi+0B0h]
0x180002335  movups  [rbp+3C0h+var_298], xmm0
0x18000233c  movups  xmm0, xmmword ptr [rdi+0B8h]
0x180002343  movsd   [rbp+3C0h+var_288], xmm1
0x18000234b  movups  xmm1, xmmword ptr [rdi+0C8h]
0x180002352  movaps  [rbp+3C0h+var_280], xmm0
0x180002359  movups  xmm0, xmmword ptr [rdi+0D8h]
0x180002360  movaps  [rbp+3C0h+var_270], xmm1
0x180002367  movsd   xmm1, qword ptr [rdi+0E8h]
0x18000236f  movaps  [rbp+3C0h+var_260], xmm0
0x180002376  movups  xmm0, xmmword ptr [rdi+0F0h]
0x18000237d  movsd   [rbp+3C0h+var_250], xmm1
0x180002385  movups  [rbp+3C0h+var_248], xmm0
0x18000238c  lea     rax, [r13+2F8h]
0x180002393  mov     [rbp+3C0h+var_218], rax
  ... truncated ...
```
