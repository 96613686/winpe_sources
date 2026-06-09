# EcbFileExtentsLoadFx

- ea: `0x180020370`
- end: `0x1800209e4`
- name: `EcbFileExtentsLoadFx`
- size: `1652`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001b1b8`

## callees

- `0x18001bfcc`
- `0x18001c020`
- `0x18001ccac`
- `0x18001e950`
- `0x18001eeb0`
- `0x180020370`
- `0x180020a8c`
- `0x180020ee8`
- `0x180020f00`
- `0x18002104c`
- `0x180069b60`
- `0x180071d64`
- `0x1800786c8`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180020917`
- `ntdll!RtlCompareMemory` at `0x180020917`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800209d9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800209d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800207b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002099a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800209b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800207b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002099a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800209b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020420`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020510`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800205b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020640`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020420`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020510`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800205b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020640`

## pseudocode

```c
__int64 __fastcall EcbFileExtentsLoadFx(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        __int64 a6)
{
  void *v7; // r12
  unsigned int v8; // r15d
  _DWORD *v9; // rdi
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  int v12; // r14d
  unsigned int File; // eax
  unsigned int FileNameString; // ebx
  unsigned int v15; // r15d
  unsigned int v16; // r12d
  unsigned int i; // r13d
  _DWORD *v18; // rax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // r13
  unsigned int j; // r15d
  int v23; // ecx
  _DWORD *v24; // rax
  int v25; // eax
  __int64 v26; // rax
  LPVOID v27; // rax
  __int64 v28; // r8
  __int64 v29; // rdx
  int v30; // r9d
  __int64 v31; // r10
  unsigned int v32; // r8d
  __int64 v33; // r13
  __int64 v34; // rcx
  _DWORD *v35; // rdi
  __int64 k; // rax
  __int64 v37; // rax
  int v38; // ecx
  wchar_t **v40; // r8
  __int64 v41; // rbx
  __int64 v42; // r12
  wchar_t *v43; // r15
  int v44; // eax
  wchar_t **v45; // r8
  unsigned int v46; // r15d
  __int64 v47; // rax
  LPCWSTR v48; // r8
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v52; // [rsp+48h] [rbp-B8h]
  int v53; // [rsp+4Ch] [rbp-B4h]
  unsigned int v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h] BYREF
  __int64 v58; // [rsp+70h] [rbp-90h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  _OWORD v61[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h]
  char v63[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-48h]
  wchar_t String[264]; // [rsp+100h] [rbp+0h] BYREF

  v60 = a5;
  v56 = a6;
  v51 = a3;
  v55 = a2;
  v59 = a1;
  v62 = 0;
  memset(v61, 0, sizeof(v61));
  memset_0(v63, 0, 0x48u);
  v64 = -1;
  EcbFileNameSpaceInitialize(v61);
  v7 = 0;
  v8 = *a4 + 22;
  v9 = 0;
  v10 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v8);
  v11 = v10;
  if ( !v10 )
  {
    FileNameString = 8;
    goto LABEL_78;
  }
  v12 = 1;
  memset_0(v10, 0, v8);
  v49 = 0;
  File = PfsBcCreateFile(v63, v59, 0);
  FileNameString = File;
  if ( File )
  {
    if ( File != 8 && File != 1450 )
      goto LABEL_49;
LABEL_78:
    v12 = 0;
    goto LABEL_49;
  }
  FileNameString = PfsBcReadFile(v63, v11, v8);
  if ( FileNameString )
    goto LABEL_49;
  v15 = (unsigned int)(v11[2] + 1023) >> 10;
  if ( v15 > 0x400 )
  {
    FileNameString = 1006;
    goto LABEL_49;
  }
  v16 = (unsigned int)(v11[3] + 1023) >> 10;
  if ( v16 > 0x400 || v11[4] > 0x40000000u || *v11 != 1164134008 || v11[1] != 44 )
  {
LABEL_47:
    FileNameString = 1006;
    goto LABEL_48;
  }
  if ( a4 && (*a4 != *((_WORD *)v11 + 10) || RtlCompareMemory(a4 + 1, (char *)v11 + 22, *a4) != *a4) )
  {
    FileNameString = 17;
    goto LABEL_48;
  }
  for ( i = 0; i < v15; ++i )
  {
    if ( **(_DWORD **)(v51 + 632) )
      goto LABEL_89;
    v18 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0xA008u);
    v9 = v18;
    if ( !v18 )
    {
LABEL_88:
      v12 = 0;
      FileNameString = 8;
      v7 = 0;
      goto LABEL_49;
    }
    FileNameString = PfsBcReadFile(v63, v18, 40968);
    if ( FileNameString )
      goto LABEL_87;
    if ( i + 1 == v15 )
      v19 = v11[2] & 0x3FF;
    else
      v19 = 1024;
    if ( *v9 != v19 || v9[1] != 1024 )
    {
LABEL_86:
      FileNameString = 1006;
LABEL_87:
      v7 = 0;
      goto LABEL_49;
    }
    v20 = i;
    *(_QWORD *)(v55 + 8 * v20) = v9;
  }
  v21 = v55;
  for ( j = 0; ; ++j )
  {
    v23 = **(_DWORD **)(v51 + 632);
    if ( j >= v16 )
      break;
    if ( v23 )
      goto LABEL_89;
    v24 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0xA008u);
    v9 = v24;
    if ( !v24 )
      goto LABEL_88;
    FileNameString = PfsBcReadFile(v63, v24, 40968);
    if ( FileNameString )
      goto LABEL_87;
    if ( j + 1 == v16 )
      v25 = v11[3] & 0x3FF;
    else
      v25 = 1024;
    if ( *v9 != v25 || v9[1] != 1024 )
      goto LABEL_86;
    v26 = j;
    *(_QWORD *)(v21 + 8 * v26 + 0x2000) = v9;
  }
  if ( v23 )
  {
LABEL_89:
    FileNameString = 995;
    v12 = 0;
    goto LABEL_76;
  }
  v27 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, (unsigned int)v11[4]);
  v7 = v27;
  if ( !v27 )
  {
    v12 = 0;
    FileNameString = 8;
    v9 = 0;
    goto LABEL_49;
  }
  v9 = 0;
  FileNameString = PfsBcReadFile(v63, v27, (unsigned int)v11[4]);
  if ( FileNameString )
    goto LABEL_49;
  v28 = (unsigned int)v11[4];
  v52 = 0;
  EcbFileNameSpaceReplaceBuffer(v61, v7, v28);
  v29 = 0;
  HIDWORD(v62) += v11[4];
  v12 = 0;
  v30 = -1;
  *(_DWORD *)(v21 + 57376) = v11[3];
  v31 = v21;
  v32 = 0;
  *(_DWORD *)(v21 + 57372) = v11[2];
  v57 = 0;
  while ( 1 )
  {
    v54 = v32;
    if ( v32 >= 2 )
    {
      FileNameString = 0;
      v9 = 0;
      v7 = 0;
      goto LABEL_49;
    }
    v33 = 0;
LABEL_38:
    if ( (unsigned int)v33 < 0x400 )
    {
      v34 = (unsigned int)v33;
      if ( v32 )
        v34 = v33 + 1024;
      v35 = *(_DWORD **)(v31 + 8 * v34);
      if ( v35 )
        break;
    }
    ++v32;
  }
  for ( k = 0; ; k = (unsigned int)(v53 + 1) )
  {
    v53 = k;
    if ( (unsigned int)k >= *v35 )
    {
      v32 = v54;
      v33 = (unsigned int)(v33 + 1);
      v31 = v55;
      goto LABEL_38;
    }
    v37 = 5 * k;
    v38 = v35[2 * v37 + 4];
    v58 = v37;
    if ( v38 == -1 || (v35[2 * v37 + 10] & 0x700u) >= 0x700 )
    {
      v9 = 0;
      goto LABEL_47;
    }
    if ( v38 != v30 )
      break;
    v47 = v58;
LABEL_73:
    *(_QWORD *)&v35[2 * v47 + 4] = v29;
  }
  v50 = 0;
  FileNameString = EcbMakeFileNameString((unsigned int)v61, v38, 0, (unsigned int)String, v49, (__int64)&v50);
  if ( FileNameString )
  {
    v9 = 0;
    v12 = 1;
    goto LABEL_48;
  }
  v41 = 0;
  v42 = 0;
  v51 = 0;
  v50 = 0;
  v43 = wcstok_mvcrt_legacy_two_parameter_form(String, L"\\\n", v40);
  v44 = 0;
  while ( v43 )
  {
    if ( v44 )
    {
      FileNameString = EcbFileNameSpaceInsert(v56, v43, v42, &v51);
      if ( FileNameString )
        goto LABEL_76;
LABEL_66:
      v41 = v51;
      v42 = v51;
      v43 = wcstok_mvcrt_legacy_two_parameter_form(0, L"\\\n", v45);
      v44 = v50;
    }
    else
    {
      if ( !(unsigned int)EcbFileNameSpaceFind(v56, v43, v42, &v51) )
        goto LABEL_66;
      v41 = v51;
      v44 = 1;
      v50 = 1;
    }
  }
  if ( v41 )
  {
    v46 = v41 - *(_DWORD *)(v56 + 24);
    v52 = v46;
  }
  else
  {
    v46 = v52;
  }
  FileNameString = RdBtFxFileNameHashInsert(v60, v46, &v57);
  if ( !FileNameString )
  {
    v47 = v58;
    v29 = v57;
    v30 = v35[2 * v58 + 4];
    goto LABEL_73;
  }
LABEL_76:
  v9 = 0;
LABEL_48:
  v7 = 0;
LABEL_49:
  EcbFileNameSpaceCleanup(v61);
  PfsBcClose(v63);
  if ( v9 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v9);
  if ( v7 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v7);
  if ( v11 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v11);
  if ( v12 )
  {
    EcbUtilsOut(16, "FxFileCorrupt: Deleting %ws...\n", v59);
    DeleteFileW(v48);
  }
  return FileNameString;
}

```

## disassembly

```asm
0x180020370  mov     [rsp-8+arg_10], rbx
0x180020375  push    rbp
0x180020376  push    rsi
0x180020377  push    rdi
0x180020378  push    r12
0x18002037a  push    r13
0x18002037c  push    r14
0x18002037e  push    r15
0x180020380  lea     rbp, [rsp-220h]
0x180020388  sub     rsp, 320h
0x18002038f  mov     rax, cs:__security_cookie
0x180020396  xor     rax, rsp
0x180020399  mov     [rbp+250h+var_40], rax
0x1800203a0  mov     rax, [rbp+250h+arg_20]
0x1800203a7  xorps   xmm0, xmm0
0x1800203aa  mov     [rbp+250h+var_2D0], rax
0x1800203ae  mov     r13, r9
0x1800203b1  mov     rax, [rbp+250h+arg_28]
0x1800203b8  mov     [rsp+350h+var_2F0], rax
0x1800203bd  xor     eax, eax
0x1800203bf  mov     [rsp+350h+var_310], r8
0x1800203c4  mov     [rsp+350h+var_2F8], rdx
0x1800203c9  xor     edx, edx; Val
0x1800203cb  mov     [rsp+350h+var_2D8], rcx
0x1800203d0  lea     rcx, [rbp+250h+var_2A0]; void *
0x1800203d4  lea     r8d, [rax+48h]; Size
0x1800203d8  mov     [rbp+250h+var_2A8], rax
0x1800203dc  movups  [rbp+250h+var_2C8], xmm0
0x1800203e0  movups  [rbp+250h+var_2B8], xmm0
0x1800203e4  call    memset_0
0x1800203e9  lea     rcx, [rbp+250h+var_2C8]
0x1800203ed  mov     [rbp+250h+var_298], 0FFFFFFFFFFFFFFFFh
0x1800203f5  call    EcbFileNameSpaceInitialize
0x1800203fa  mov     rcx, cs:PfSvcGlobals
0x180020401  xor     r12d, r12d
0x180020404  movzx   r15d, word ptr [r13+0]
0x180020409  xor     edx, edx; dwFlags
0x18002040b  add     r15d, 16h
0x18002040f  mov     [rsp+350h+var_320], r12
0x180020414  mov     r8d, r15d; dwBytes
0x180020417  xor     edi, edi
0x180020419  mov     rcx, [rcx+58h]; hHeap
0x18002041d  mov     ebx, r15d
0x180020420  call    cs:__imp_HeapAlloc
0x180020426  mov     rsi, rax
0x180020429  test    rax, rax
0x18002042c  jz      loc_1800208D8
0x180020432  mov     r8d, ebx; Size
0x180020435  lea     r14d, [rdi+1]
0x180020439  xor     edx, edx; Val
0x18002043b  mov     rcx, rax; void *
0x18002043e  call    memset_0
0x180020443  mov     rdx, [rsp+350h+var_2D8]
0x180020448  lea     rcx, [rbp+250h+var_2A0]
0x18002044c  xor     r8d, r8d
0x18002044f  mov     [rsp+350h+var_330], edi
0x180020453  call    PfsBcCreateFile
0x180020458  mov     ebx, eax
0x18002045a  test    eax, eax
0x18002045c  jnz     loc_1800208E5
0x180020462  mov     r8d, r15d
0x180020465  lea     rcx, [rbp+250h+var_2A0]
0x180020469  mov     rdx, rsi
0x18002046c  call    PfsBcReadFile
0x180020471  mov     ebx, eax
0x180020473  test    eax, eax
0x180020475  jnz     loc_18002072B
0x18002047b  mov     r15d, [rsi+8]
0x18002047f  mov     eax, 3FFh
0x180020484  add     r15d, eax
0x180020487  shr     r15d, 0Ah
0x18002048b  cmp     r15d, 400h
0x180020492  ja      loc_1800208F7
0x180020498  mov     r12d, [rsi+0Ch]
0x18002049c  add     r12d, eax
0x18002049f  shr     r12d, 0Ah
0x1800204a3  cmp     r12d, 400h
0x1800204aa  ja      loc_180020723
0x1800204b0  cmp     dword ptr [rsi+10h], 40000000h
0x1800204b7  ja      loc_180020723
0x1800204bd  cmp     dword ptr [rsi], 45634678h
0x1800204c3  jnz     loc_180020723
0x1800204c9  cmp     dword ptr [rsi+4], 2Ch ; ','
0x1800204cd  jnz     loc_180020723
0x1800204d3  test    r13, r13
0x1800204d6  jnz     loc_180020901
0x1800204dc  xor     r13d, r13d
0x1800204df  cmp     r13d, r15d
0x1800204e2  jnb     loc_18002057F
0x1800204e8  mov     rax, [rsp+350h+var_310]
0x1800204ed  mov     rax, [rax+278h]
0x1800204f4  cmp     dword ptr [rax], 0
0x1800204f7  jnz     loc_180020957
0x1800204fd  mov     rcx, cs:PfSvcGlobals
0x180020504  xor     edx, edx; dwFlags
0x180020506  mov     r8d, 0A008h; dwBytes
0x18002050c  mov     rcx, [rcx+58h]; hHeap
0x180020510  call    cs:__imp_HeapAlloc
0x180020516  mov     rdi, rax
0x180020519  test    rax, rax
0x18002051c  jz      loc_180020947
0x180020522  mov     r8d, 0A008h
0x180020528  lea     rcx, [rbp+250h+var_2A0]
0x18002052c  mov     rdx, rax
0x18002052f  call    PfsBcReadFile
0x180020534  mov     ebx, eax
0x180020536  test    eax, eax
0x180020538  jnz     loc_18002093D
0x18002053e  lea     ecx, [r13+1]
0x180020542  cmp     ecx, r15d
0x180020545  jnz     short loc_180020578
0x180020547  mov     eax, [rsi+8]
0x18002054a  and     eax, 3FFh
0x18002054f  cmp     [rdi], eax
0x180020551  jnz     loc_180020938
0x180020557  cmp     dword ptr [rdi+4], 400h
0x18002055e  jnz     loc_180020938
0x180020564  mov     rdx, [rsp+350h+var_2F8]
0x180020569  mov     eax, r13d
0x18002056c  mov     r13d, ecx
0x18002056f  mov     [rdx+rax*8], rdi
0x180020573  jmp     loc_1800204DF
0x180020578  mov     eax, 400h
0x18002057d  jmp     short loc_18002054F
0x18002057f  mov     r13, [rsp+350h+var_2F8]
0x180020584  xor     r15d, r15d
0x180020587  mov     rax, [rsp+350h+var_310]
0x18002058c  mov     rax, [rax+278h]
0x180020593  mov     ecx, [rax]
0x180020595  cmp     r15d, r12d
0x180020598  jnb     loc_180020627
0x18002059e  test    ecx, ecx
0x1800205a0  jnz     loc_180020957
0x1800205a6  mov     rcx, cs:PfSvcGlobals
0x1800205ad  xor     edx, edx; dwFlags
0x1800205af  mov     r8d, 0A008h; dwBytes
0x1800205b5  mov     rcx, [rcx+58h]; hHeap
0x1800205b9  call    cs:__imp_HeapAlloc
0x1800205bf  mov     rdi, rax
0x1800205c2  test    rax, rax
0x1800205c5  jz      loc_180020947
0x1800205cb  mov     r8d, 0A008h
0x1800205d1  lea     rcx, [rbp+250h+var_2A0]
0x1800205d5  mov     rdx, rax
0x1800205d8  call    PfsBcReadFile
0x1800205dd  mov     ebx, eax
0x1800205df  test    eax, eax
0x1800205e1  jnz     loc_18002093D
0x1800205e7  lea     ecx, [r15+1]
0x1800205eb  cmp     ecx, r12d
0x1800205ee  jnz     short loc_180020620
0x1800205f0  mov     eax, [rsi+0Ch]
0x1800205f3  and     eax, 3FFh
0x1800205f8  cmp     [rdi], eax
0x1800205fa  jnz     loc_180020938
0x180020600  cmp     dword ptr [rdi+4], 400h
0x180020607  jnz     loc_180020938
0x18002060d  mov     eax, r15d
0x180020610  mov     r15d, ecx
0x180020613  mov     [r13+rax*8+2000h], rdi
0x18002061b  jmp     loc_180020587
0x180020620  mov     eax, 400h
0x180020625  jmp     short loc_1800205F8
0x180020627  test    ecx, ecx
0x180020629  jnz     loc_180020957
0x18002062f  mov     rcx, cs:PfSvcGlobals
0x180020636  xor     edx, edx; dwFlags
0x180020638  mov     r8d, [rsi+10h]; dwBytes
0x18002063c  mov     rcx, [rcx+58h]; hHeap
0x180020640  call    cs:__imp_HeapAlloc
0x180020646  mov     r12, rax
0x180020649  test    rax, rax
0x18002064c  jz      loc_180020964
0x180020652  mov     r8d, [rsi+10h]
0x180020656  lea     rcx, [rbp+250h+var_2A0]
0x18002065a  mov     rdx, rax
0x18002065d  call    PfsBcReadFile
0x180020662  xor     edi, edi
0x180020664  mov     ebx, eax
0x180020666  test    eax, eax
0x180020668  jnz     loc_18002072B
0x18002066e  mov     r8d, [rsi+10h]
0x180020672  lea     rcx, [rbp+250h+var_2C8]
0x180020676  mov     rdx, r12
0x180020679  mov     [rsp+350h+var_308], edi
0x18002067d  call    EcbFileNameSpaceReplaceBuffer
0x180020682  mov     eax, [rsi+10h]
0x180020685  xor     edx, edx
0x180020687  add     dword ptr [rbp+250h+var_2A8+4], eax
0x18002068a  xor     r14d, r14d
0x18002068d  mov     eax, [rsi+0Ch]
0x180020690  or      r9d, 0FFFFFFFFh
0x180020694  mov     [r13+0E020h], eax
0x18002069b  mov     r10, r13
0x18002069e  mov     eax, [rsi+8]
0x1800206a1  xor     r8d, r8d
0x1800206a4  mov     [r13+0E01Ch], eax
0x1800206ab  mov     [rsp+350h+var_2E8], rdx
0x1800206b0  mov     [rsp+350h+var_300], r8d
0x1800206b5  cmp     r8d, 2
0x1800206b9  jnb     loc_18002097E
0x1800206bf  xor     r13d, r13d
0x1800206c2  cmp     r13d, 400h
0x1800206c9  jnb     loc_18002079B
0x1800206cf  test    r8d, r8d
0x1800206d2  mov     ecx, r13d
0x1800206d5  lea     rax, [r13+400h]
0x1800206dc  cmovnz  rcx, rax
0x1800206e0  mov     rdi, [r10+rcx*8]
0x1800206e4  test    rdi, rdi
0x1800206e7  jz      loc_18002079B
0x1800206ed  xor     eax, eax
0x1800206ef  mov     [rsp+350h+var_304], eax
0x1800206f3  cmp     eax, [rdi]
0x1800206f5  jnb     loc_180020789
0x1800206fb  lea     rax, [rax+rax*4]
0x1800206ff  mov     ecx, [rdi+rax*8+10h]
0x180020703  mov     [rsp+350h+var_2E0], rax
0x180020708  cmp     ecx, 0FFFFFFFFh
0x18002070b  jz      short loc_180020721
0x18002070d  mov     eax, [rdi+rax*8+28h]
0x180020711  and     eax, 700h
0x180020716  cmp     eax, 700h
0x18002071b  jb      loc_180020891
0x180020721  xor     edi, edi
0x180020723  mov     ebx, 3EEh
0x180020728  mov     r12, rdi
0x18002072b  lea     rcx, [rbp+250h+var_2C8]
0x18002072f  call    EcbFileNameSpaceCleanup
0x180020734  lea     rcx, [rbp+250h+var_2A0]
0x180020738  call    PfsBcClose
0x18002073d  test    rdi, rdi
0x180020740  jnz     loc_18002098A
0x180020746  test    r12, r12
0x180020749  jnz     loc_1800209A5
0x18002074f  test    rsi, rsi
0x180020752  jnz     short loc_1800207A3
0x180020754  test    r14d, r14d
0x180020757  jnz     loc_1800209C0
0x18002075d  mov     eax, ebx
0x18002075f  mov     rcx, [rbp+250h+var_40]
0x180020766  xor     rcx, rsp; StackCookie
0x180020769  call    __security_check_cookie
0x18002076e  mov     rbx, [rsp+350h+arg_10]
0x180020776  add     rsp, 320h
0x18002077d  pop     r15
0x18002077f  pop     r14
0x180020781  pop     r13
0x180020783  pop     r12
0x180020785  pop     rdi
0x180020786  pop     rsi
0x180020787  pop     rbp
0x180020788  retn
0x180020789  mov     r8d, [rsp+350h+var_300]
0x18002078e  inc     r13d
0x180020791  mov     r10, [rsp+350h+var_2F8]
0x180020796  jmp     loc_1800206C2
0x18002079b  inc     r8d
0x18002079e  jmp     loc_1800206B0
0x1800207a3  mov     rcx, cs:PfSvcGlobals
0x1800207aa  mov     r8, rsi; lpMem
0x1800207ad  xor     edx, edx; dwFlags
0x1800207af  mov     rcx, [rcx+58h]; hHeap
0x1800207b3  call    cs:__imp_HeapFree
0x1800207b9  jmp     short loc_180020754
0x1800207bb  mov     rdx, rcx
0x1800207be  mov     [rsp+350h+var_318], r14d
0x1800207c3  lea     rax, [rsp+350h+var_318]
0x1800207c8  xor     r8d, r8d
0x1800207cb  lea     rcx, [rbp+250h+var_2C8]
0x1800207cf  mov     [rsp+350h+var_328], rax
0x1800207d4  lea     r9, [rbp+250h+String]
0x1800207d8  call    EcbMakeFileNameString
0x1800207dd  mov     ebx, eax
0x1800207df  test    eax, eax
0x1800207e1  jnz     loc_180020973
0x1800207e7  xor     ebx, ebx
0x1800207e9  lea     rdx, Delimiter; "\\\n"
0x1800207f0  xor     r12d, r12d
0x1800207f3  mov     [rsp+350h+var_310], rbx
0x1800207f8  lea     rcx, [rbp+250h+String]; String
0x1800207fc  mov     [rsp+350h+var_318], ebx
0x180020800  call    wcstok_mvcrt_legacy_two_parameter_form
0x180020805  mov     r15, rax
0x180020808  mov     eax, ebx
0x18002080a  test    r15, r15
0x18002080d  jz      short loc_18002085F
0x18002080f  mov     rcx, [rsp+350h+var_2F0]
0x180020814  lea     r9, [rsp+350h+var_310]
0x180020819  mov     r8, r12
0x18002081c  mov     rdx, r15
0x18002081f  test    eax, eax
0x180020821  jnz     loc_1800208C2
0x180020827  call    EcbFileNameSpaceFind
0x18002082c  test    eax, eax
0x18002082e  jz      short loc_180020840
0x180020830  mov     rbx, [rsp+350h+var_310]
0x180020835  mov     eax, 1
0x18002083a  mov     [rsp+350h+var_318], eax
0x18002083e  jmp     short loc_18002080A
  ... truncated ...
```
