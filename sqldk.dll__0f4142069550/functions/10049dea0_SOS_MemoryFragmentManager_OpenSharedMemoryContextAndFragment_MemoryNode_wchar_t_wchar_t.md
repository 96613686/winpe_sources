# SOS_MemoryFragmentManager::OpenSharedMemoryContextAndFragment(MemoryNode *,wchar_t *,wchar_t *)

- ea: `0x10049dea0`
- end: `0x10049e23b`
- name: `?OpenSharedMemoryContextAndFragment@SOS_MemoryFragmentManager@@AEAAPEAXPEAVMemoryNode@@PEA_W1@Z`
- size: `923`
- prototype: `void *(SOS_MemoryFragmentManager *__hidden this, struct MemoryNode *, wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x10049e250`

## callees

- `0x10049dea0`
- `0x1004a22c0`
- `0x1004a2520`

## import_xrefs

- `KERNEL32!CreateFileMappingNumaW` at `0x10049df9e`
- `KERNEL32!CreateFileMappingNumaW` at `0x10049df9e`
- `KERNEL32!OpenFileMappingW` at `0x10049def3`
- `KERNEL32!OpenFileMappingW` at `0x10049e153`
- `KERNEL32!OpenFileMappingW` at `0x10049def3`
- `KERNEL32!OpenFileMappingW` at `0x10049e153`
- `KERNEL32!CloseHandle` at `0x10049df65`
- `KERNEL32!CloseHandle` at `0x10049e018`
- `KERNEL32!CloseHandle` at `0x10049e091`
- `KERNEL32!CloseHandle` at `0x10049e1c8`
- `KERNEL32!CloseHandle` at `0x10049df65`
- `KERNEL32!CloseHandle` at `0x10049e018`
- `KERNEL32!CloseHandle` at `0x10049e091`
- `KERNEL32!CloseHandle` at `0x10049e1c8`

## pseudocode

```c
char *__fastcall SOS_MemoryFragmentManager::OpenSharedMemoryContextAndFragment(
        SOS_MemoryFragmentManager *this,
        struct MemoryNode *a2,
        wchar_t *a3,
        wchar_t *a4)
{
  int v4; // r12d
  __int64 dwMaximumSizeLow; // r15
  char *v8; // rbp
  char v9; // r13
  char *v10; // rdi
  HANDLE v11; // rax
  void *v12; // rbx
  HANDLE FileMappingNumaW; // rax
  void (*v14)(const wchar_t *, ...); // rax
  void *v15; // rbx
  __int64 v16; // r9
  _WORD *v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rdx
  char *v21; // rsi
  __int16 v22; // ax
  _WORD *v23; // rax
  _QWORD *v24; // rsi
  char *v25; // rdi
  unsigned __int64 v26; // rbp
  HANDLE v27; // rax
  void *v28; // r15
  _WORD *v29; // rdx
  char *v30; // r14
  __int16 v31; // ax
  _WORD *v32; // rcx
  __int64 v33; // rcx
  char *v34; // [rsp+70h] [rbp-58h]
  __int64 v35; // [rsp+78h] [rbp-50h] BYREF
  __int64 v36[9]; // [rsp+80h] [rbp-48h] BYREF

  v4 = SOS_OS_SharedMemoryContextExternalFragmentCount;
  v34 = 0;
  dwMaximumSizeLow = 560LL * SOS_OS_SharedMemoryContextExternalFragmentCount + 1104;
  v8 = 0;
  v9 = 1;
  v10 = 0;
  v11 = OpenFileMappingW(0xF001Fu, 0, a3);
  v12 = v11;
  if ( !v11
    || (v10 = (char *)MemoryNode::MapViewOfFileEx(
                        a2,
                        v11,
                        0xF001Fu,
                        0,
                        0,
                        dwMaximumSizeLow,
                        0,
                        4u,
                        v36,
                        &v35,
                        0xFFFFFFFF,
                        0,
                        0)) != 0 )
  {
    if ( v10 )
      goto LABEL_15;
  }
  else
  {
    CloseHandle(v12);
  }
  v10 = 0;
  v9 = 0;
  FileMappingNumaW = CreateFileMappingNumaW(
                       (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                       0,
                       4u,
                       HIDWORD(dwMaximumSizeLow),
                       dwMaximumSizeLow,
                       a3,
                       0xFFFFFFFF);
  v12 = FileMappingNumaW;
  if ( FileMappingNumaW )
  {
    v10 = (char *)MemoryNode::MapViewOfFileEx(
                    a2,
                    FileMappingNumaW,
                    0xF001Fu,
                    0,
                    0,
                    dwMaximumSizeLow,
                    0,
                    4u,
                    &v35,
                    v36,
                    0xFFFFFFFF,
                    0,
                    0);
    if ( !v10 )
    {
      CloseHandle(v12);
LABEL_8:
      v14 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
      if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
        v14 = SOS_OS_LogUnlocalizedRoutine;
      v14(L"Unable to allocate shared memory. Reverting to conventional memory.");
      *((_DWORD *)this + 6) = 3;
      if ( v34 && SOS_OS_SharedMemoryContext )
      {
        v15 = *(void **)SOS_OS_SharedMemoryContext;
        v16 = 560LL * *((int *)SOS_OS_SharedMemoryContext + 4) + 1104;
        MemoryNode::UnmapViewOfFile(a2, SOS_OS_SharedMemoryContext, v16, v16, 0, 0);
        CloseHandle(v15);
        SOS_OS_SharedMemoryContext = 0;
      }
      return v8;
    }
  }
  if ( !v10 )
    goto LABEL_8;
LABEL_15:
  *(_QWORD *)v10 = v12;
  v18 = v10 + 20;
  v19 = 260;
  *((_DWORD *)v10 + 3) = 1;
  v20 = 260;
  v34 = v10;
  v10[8] = v9;
  v21 = (char *)((char *)a3 - (v10 + 20));
  *((_DWORD *)v10 + 4) = v4;
  do
  {
    if ( v20 == -2147483386 )
      break;
    v22 = *(_WORD *)((char *)v18 + (_QWORD)v21);
    if ( !v22 )
      break;
    *v18++ = v22;
    --v20;
  }
  while ( v20 );
  v23 = v18 - 1;
  if ( v20 )
    v23 = v18;
  *v23 = 0;
  SOS_OS_SharedMemoryContext = (struct SOS_SharedMemoryContext *)v10;
  if ( v9 )
  {
    v24 = v10 + 544;
    if ( *((int *)v10 + 3) <= 0 )
      v24 = 0;
    v25 = 0;
    v26 = v24[3];
    v27 = OpenFileMappingW(0xF001Fu, 0, a4);
    v28 = v27;
    if ( v27 )
    {
      v25 = (char *)MemoryNode::MapViewOfFileEx(
                      a2,
                      v27,
                      0xF001Fu,
                      0,
                      0,
                      v26,
                      0,
                      0x4000004u,
                      &v35,
                      v36,
                      0xFFFFFFFF,
                      0,
                      0);
      v8 = v25;
      if ( !v25 )
      {
        CloseHandle(v28);
        goto LABEL_8;
      }
    }
    v8 = v25;
    if ( !v25 )
      goto LABEL_8;
    v29 = v24 + 5;
    *v24 = v28;
    v30 = (char *)((char *)a4 - (char *)(v24 + 5));
    do
    {
      if ( v19 == -2147483386 )
        break;
      v31 = *(_WORD *)((char *)v29 + (_QWORD)v30);
      if ( !v31 )
        break;
      *v29++ = v31;
      --v19;
    }
    while ( v19 );
    v32 = v29 - 1;
    if ( v19 )
      v32 = v29;
    *v32 = 0;
    v33 = v24[2];
    v24[2] = v25;
    v24[4] = &v25[-v33];
    v24[1] = v33;
  }
  return v8;
}

```

## disassembly

```asm
0x10049dea0  mov     [rsp+arg_10], rbx
0x10049dea5  mov     [rsp+arg_8], rdx
0x10049deaa  mov     [rsp+arg_0], rcx
0x10049deaf  push    rbp
0x10049deb0  push    rsi
0x10049deb1  push    rdi
0x10049deb2  push    r12
0x10049deb4  push    r13
0x10049deb6  push    r14
0x10049deb8  push    r15
0x10049deba  sub     rsp, 90h
0x10049dec1  movsxd  r12, cs:?SOS_OS_SharedMemoryContextExternalFragmentCount@@3HA; int SOS_OS_SharedMemoryContextExternalFragmentCount
0x10049dec8  xor     edx, edx; bInheritHandle
0x10049deca  imul    r15, r12, 230h
0x10049ded1  mov     ecx, 0F001Fh; dwDesiredAccess
0x10049ded6  mov     [rsp+0C8h+var_58], 0
0x10049dedf  add     r15, 450h
0x10049dee6  mov     r14, r9
0x10049dee9  mov     rsi, r8
0x10049deec  xor     ebp, ebp
0x10049deee  mov     r13b, 1
0x10049def1  xor     edi, edi
0x10049def3  call    cs:__imp_OpenFileMappingW
0x10049def9  mov     rbx, rax
0x10049defc  test    rax, rax
0x10049deff  jz      short loc_10049DF6D
0x10049df01  xor     ecx, ecx
0x10049df03  lea     rax, [rsp+0C8h+var_50]
0x10049df08  mov     [rsp+0C8h+var_68], rcx; unsigned int *
0x10049df0d  xor     r9d, r9d; unsigned int
0x10049df10  mov     [rsp+0C8h+var_70], cl; bool
0x10049df14  mov     r8d, 0F001Fh; unsigned int
0x10049df1a  mov     [rsp+0C8h+var_78], 0FFFFFFFFh; unsigned int
0x10049df22  mov     rdx, rbx; void *
0x10049df25  mov     [rsp+0C8h+var_80], rax; __int64 *
0x10049df2a  lea     rax, [rsp+0C8h+var_48]
0x10049df32  mov     [rsp+0C8h+var_88], rax; __int64 *
0x10049df37  mov     [rsp+0C8h+var_90], 4; unsigned int
0x10049df3f  mov     qword ptr [rsp+0C8h+nndPreferred], rcx; void *
0x10049df44  mov     [rsp+0C8h+lpName], r15; unsigned __int64
0x10049df49  mov     [rsp+0C8h+dwMaximumSizeLow], ecx; unsigned int
0x10049df4d  mov     rcx, [rsp+0C8h+arg_8]; this
0x10049df55  call    ?MapViewOfFileEx@MemoryNode@@AEAAPEAXPEAXKKK_K0KPEA_J2K_NPEAI@Z; MemoryNode::MapViewOfFileEx(void *,ulong,ulong,ulong,unsigned __int64,void *,ulong,__int64 *,__int64 *,ulong,bool,uint *)
0x10049df5a  mov     rdi, rax
0x10049df5d  test    rax, rax
0x10049df60  jnz     short loc_10049DF6D
0x10049df62  mov     rcx, rbx; hObject
0x10049df65  call    cs:__imp_CloseHandle
0x10049df6b  jmp     short loc_10049DF76
0x10049df6d  test    rdi, rdi
0x10049df70  jnz     loc_10049E0C5
0x10049df76  xor     edi, edi
0x10049df78  mov     [rsp+0C8h+nndPreferred], 0FFFFFFFFh; nndPreferred
0x10049df80  mov     r9, r15
0x10049df83  mov     [rsp+0C8h+lpName], rsi; lpName
0x10049df88  shr     r9, 20h; dwMaximumSizeHigh
0x10049df8c  xor     edx, edx; lpFileMappingAttributes
0x10049df8e  xor     r13b, r13b
0x10049df91  mov     [rsp+0C8h+dwMaximumSizeLow], r15d; dwMaximumSizeLow
0x10049df96  lea     rcx, [rdi-1]; hFile
0x10049df9a  lea     r8d, [rdi+4]; flProtect
0x10049df9e  call    cs:__imp_CreateFileMappingNumaW
0x10049dfa4  mov     rbx, rax
0x10049dfa7  test    rax, rax
0x10049dfaa  jz      loc_10049E0BC
0x10049dfb0  xor     ecx, ecx
0x10049dfb2  lea     rax, [rsp+0C8h+var_48]
0x10049dfba  mov     [rsp+0C8h+var_68], rcx; unsigned int *
0x10049dfbf  xor     r9d, r9d; unsigned int
0x10049dfc2  mov     [rsp+0C8h+var_70], cl; bool
0x10049dfc6  mov     r8d, 0F001Fh; unsigned int
0x10049dfcc  mov     [rsp+0C8h+var_78], 0FFFFFFFFh; unsigned int
0x10049dfd4  mov     rdx, rbx; void *
0x10049dfd7  mov     [rsp+0C8h+var_80], rax; __int64 *
0x10049dfdc  lea     rax, [rsp+0C8h+var_50]
0x10049dfe1  mov     [rsp+0C8h+var_88], rax; __int64 *
0x10049dfe6  mov     [rsp+0C8h+var_90], 4; unsigned int
0x10049dfee  mov     qword ptr [rsp+0C8h+nndPreferred], rcx; void *
0x10049dff3  mov     [rsp+0C8h+lpName], r15; unsigned __int64
0x10049dff8  mov     [rsp+0C8h+dwMaximumSizeLow], ecx; unsigned int
0x10049dffc  mov     rcx, [rsp+0C8h+arg_8]; this
0x10049e004  call    ?MapViewOfFileEx@MemoryNode@@AEAAPEAXPEAXKKK_K0KPEA_J2K_NPEAI@Z; MemoryNode::MapViewOfFileEx(void *,ulong,ulong,ulong,unsigned __int64,void *,ulong,__int64 *,__int64 *,ulong,bool,uint *)
0x10049e009  mov     rdi, rax
0x10049e00c  test    rax, rax
0x10049e00f  jnz     loc_10049E0BC
0x10049e015  mov     rcx, rbx; hObject
0x10049e018  call    cs:__imp_CloseHandle
0x10049e01e  xor     r12d, r12d
0x10049e021  mov     rax, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x10049e028  lea     rcx, aUnableToAlloca; "Unable to allocate shared memory. Rever"...
0x10049e02f  test    rax, rax
0x10049e032  cmovz   rax, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x10049e03a  call    rax
0x10049e03c  cmp     [rsp+0C8h+var_58], 0
0x10049e042  mov     rax, [rsp+0C8h+arg_0]
0x10049e04a  mov     dword ptr [rax+18h], 3
0x10049e051  jz      short loc_10049E09E
0x10049e053  mov     rdx, cs:?SOS_OS_SharedMemoryContext@@3PEAVSOS_SharedMemoryContext@@EA; SOS_SharedMemoryContext * SOS_OS_SharedMemoryContext
0x10049e05a  test    rdx, rdx
0x10049e05d  jz      short loc_10049E09E
0x10049e05f  movsxd  rax, dword ptr [rdx+10h]
0x10049e063  mov     rcx, [rsp+0C8h+arg_8]
0x10049e06b  mov     rbx, [rdx]
0x10049e06e  imul    r8, rax, 230h
0x10049e075  mov     [rsp+0C8h+lpName], r12
0x10049e07a  add     r8, 450h
0x10049e081  mov     qword ptr [rsp+0C8h+dwMaximumSizeLow], r12
0x10049e086  mov     r9, r8
0x10049e089  call    ?UnmapViewOfFile@MemoryNode@@AEAA?AW4SOS_RESULT@@QEAX_K1PEA_J2_N@Z; MemoryNode::UnmapViewOfFile(void * const,unsigned __int64,unsigned __int64,__int64 *,__int64 *,bool)
0x10049e08e  mov     rcx, rbx; hObject
0x10049e091  call    cs:__imp_CloseHandle
0x10049e097  mov     cs:?SOS_OS_SharedMemoryContext@@3PEAVSOS_SharedMemoryContext@@EA, r12; SOS_SharedMemoryContext * SOS_OS_SharedMemoryContext
0x10049e09e  mov     rbx, [rsp+0C8h+arg_10]
0x10049e0a6  mov     rax, rbp
0x10049e0a9  add     rsp, 90h
0x10049e0b0  pop     r15
0x10049e0b2  pop     r14
0x10049e0b4  pop     r13
0x10049e0b6  pop     r12
0x10049e0b8  pop     rdi
0x10049e0b9  pop     rsi
0x10049e0ba  pop     rbp
0x10049e0bb  retn
0x10049e0bc  test    rdi, rdi
0x10049e0bf  jz      loc_10049E01E
0x10049e0c5  mov     [rdi], rbx
0x10049e0c8  lea     rcx, [rdi+14h]
0x10049e0cc  mov     ebx, 104h
0x10049e0d1  mov     dword ptr [rdi+0Ch], 1
0x10049e0d8  mov     edx, ebx
0x10049e0da  mov     [rsp+0C8h+var_58], rdi
0x10049e0df  mov     [rdi+8], r13b
0x10049e0e3  sub     rsi, rcx
0x10049e0e6  mov     [rdi+10h], r12d
0x10049e0ea  nop     word ptr [rax+rax+00h]
0x10049e0f0  lea     rax, [rdx+7FFFFEFAh]
0x10049e0f7  test    rax, rax
0x10049e0fa  jz      short loc_10049E112
0x10049e0fc  movzx   eax, word ptr [rsi+rcx]
0x10049e100  test    ax, ax
0x10049e103  jz      short loc_10049E112
0x10049e105  mov     [rcx], ax
0x10049e108  add     rcx, 2
0x10049e10c  sub     rdx, 1
0x10049e110  jnz     short loc_10049E0F0
0x10049e112  test    rdx, rdx
0x10049e115  lea     rax, [rcx-2]
0x10049e119  cmovnz  rax, rcx
0x10049e11d  xor     r12d, r12d
0x10049e120  mov     [rax], r12w
0x10049e124  mov     cs:?SOS_OS_SharedMemoryContext@@3PEAVSOS_SharedMemoryContext@@EA, rdi; SOS_SharedMemoryContext * SOS_OS_SharedMemoryContext
0x10049e12b  test    r13b, r13b
0x10049e12e  jz      loc_10049E09E
0x10049e134  cmp     [rdi+0Ch], ebp
0x10049e137  lea     rsi, [rdi+220h]
0x10049e13e  mov     r8, r14; lpName
0x10049e141  mov     ecx, 0F001Fh; dwDesiredAccess
0x10049e146  cmovle  rsi, r12
0x10049e14a  mov     edi, r12d
0x10049e14d  xor     edx, edx; bInheritHandle
0x10049e14f  mov     rbp, [rsi+18h]
0x10049e153  call    cs:__imp_OpenFileMappingW
0x10049e159  mov     r15, rax
0x10049e15c  test    rax, rax
0x10049e15f  jz      short loc_10049E1D3
0x10049e161  mov     rcx, [rsp+0C8h+arg_8]; this
0x10049e169  lea     rax, [rsp+0C8h+var_48]
0x10049e171  mov     [rsp+0C8h+var_68], r12; unsigned int *
0x10049e176  xor     r9d, r9d; unsigned int
0x10049e179  mov     [rsp+0C8h+var_70], dil; bool
0x10049e17e  mov     r8d, 0F001Fh; unsigned int
0x10049e184  mov     [rsp+0C8h+var_78], 0FFFFFFFFh; unsigned int
0x10049e18c  mov     rdx, r15; void *
0x10049e18f  mov     [rsp+0C8h+var_80], rax; __int64 *
0x10049e194  lea     rax, [rsp+0C8h+var_50]
0x10049e199  mov     [rsp+0C8h+var_88], rax; __int64 *
0x10049e19e  mov     [rsp+0C8h+var_90], 4000004h; unsigned int
0x10049e1a6  mov     qword ptr [rsp+0C8h+nndPreferred], r12; void *
0x10049e1ab  mov     [rsp+0C8h+lpName], rbp; unsigned __int64
0x10049e1b0  mov     [rsp+0C8h+dwMaximumSizeLow], r12d; unsigned int
0x10049e1b5  call    ?MapViewOfFileEx@MemoryNode@@AEAAPEAXPEAXKKK_K0KPEA_J2K_NPEAI@Z; MemoryNode::MapViewOfFileEx(void *,ulong,ulong,ulong,unsigned __int64,void *,ulong,__int64 *,__int64 *,ulong,bool,uint *)
0x10049e1ba  mov     rdi, rax
0x10049e1bd  mov     rbp, rax
0x10049e1c0  test    rax, rax
0x10049e1c3  jnz     short loc_10049E1D3
0x10049e1c5  mov     rcx, r15; hObject
0x10049e1c8  call    cs:__imp_CloseHandle
0x10049e1ce  jmp     loc_10049E021
0x10049e1d3  mov     rbp, rdi
0x10049e1d6  test    rdi, rdi
0x10049e1d9  jz      loc_10049E021
0x10049e1df  lea     rdx, [rsi+28h]
0x10049e1e3  mov     [rsi], r15
0x10049e1e6  sub     r14, rdx
0x10049e1e9  nop     dword ptr [rax+00000000h]
0x10049e1f0  lea     rax, [rbx+7FFFFEFAh]
0x10049e1f7  test    rax, rax
0x10049e1fa  jz      short loc_10049E213
0x10049e1fc  movzx   eax, word ptr [r14+rdx]
0x10049e201  test    ax, ax
0x10049e204  jz      short loc_10049E213
0x10049e206  mov     [rdx], ax
0x10049e209  add     rdx, 2
0x10049e20d  sub     rbx, 1
0x10049e211  jnz     short loc_10049E1F0
0x10049e213  test    rbx, rbx
0x10049e216  lea     rcx, [rdx-2]
0x10049e21a  cmovnz  rcx, rdx
0x10049e21e  mov     [rcx], r12w
0x10049e222  mov     rcx, [rsi+10h]
0x10049e226  mov     [rsi+10h], rdi
0x10049e22a  sub     rdi, rcx
0x10049e22d  mov     [rsi+20h], rdi
0x10049e231  mov     [rsi+8], rcx
0x10049e235  jmp     loc_10049E09E
```
