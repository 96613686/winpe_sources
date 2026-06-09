# p9fs::util::storvsp::OpenRelativeFileEx(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_IO_STATUS_BLOCK *,ulong,ulong *,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,ulong,void *,void *,ulong,void *,ushort,void * *,_REPARSE_DATA_BUFFER * *)

- ea: `0x18002a16c`
- end: `0x18002a5d1`
- name: `?OpenRelativeFileEx@storvsp@util@p9fs@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_IO_STATUS_BLOCK@@KPEAKPEAT_LARGE_INTEGER@@KKKKKPEAX4K4GPEAPEAXPEAPEAU_REPARSE_DATA_BUFFER@@@Z`
- size: `1125`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18002a024`

## callees

- `0x180004c68`
- `0x180004c80`
- `0x18000d498`
- `0x18000e23c`
- `0x180029ee0`
- `0x18002a16c`
- `0x18002a6b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a47b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a47b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a48c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a48c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall p9fs::util::storvsp::OpenRelativeFileEx(
        unsigned int *a1,
        struct _IO_STATUS_BLOCK *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        void *a11,
        void *a12,
        unsigned int Size,
        void *a14,
        unsigned __int16 a15,
        _QWORD *a16,
        _QWORD *a17)
{
  struct _IO_STATUS_BLOCK *v17; // r13
  ULONG_PTR *v18; // rdi
  int v19; // ebx
  unsigned __int64 v20; // rbx
  ULONG v21; // r14d
  ULONG v22; // r12d
  ULONG v23; // eax
  size_t v24; // rdi
  _DWORD *v25; // r15
  void *v26; // rax
  ULONG v27; // r14d
  char *v28; // rdi
  signed __int64 v29; // rcx
  char *v30; // rax
  signed __int64 v31; // rbx
  unsigned int v32; // r12d
  HANDLE ProcessHeap; // rax
  void *v34; // rax
  void *v35; // r14
  __int64 v36; // rax
  char *v37; // r12
  char *v38; // rax
  size_t v39; // rdi
  int v42; // [rsp+40h] [rbp-B8h]
  char v43[4]; // [rsp+44h] [rbp-B4h] BYREF
  PVOID v44[2]; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A0h]
  PVOID v46; // [rsp+60h] [rbp-98h]
  ULONG v47; // [rsp+68h] [rbp-90h]
  struct _IO_STATUS_BLOCK *v48; // [rsp+70h] [rbp-88h]
  int *v49; // [rsp+78h] [rbp-80h]
  PVOID InputBuffer[3]; // [rsp+80h] [rbp-78h] BYREF
  void *Src; // [rsp+98h] [rbp-60h]
  void *v52; // [rsp+A0h] [rbp-58h]
  void *v53; // [rsp+A8h] [rbp-50h]
  HANDLE FileHandle; // [rsp+B0h] [rbp-48h]
  _QWORD *v55; // [rsp+B8h] [rbp-40h]
  _QWORD *v56; // [rsp+C0h] [rbp-38h]

  v17 = a2;
  Src = a1;
  v49 = (int *)&a2->0;
  v48 = a2;
  FileHandle = a11;
  v52 = a12;
  v53 = a14;
  v56 = a16;
  v55 = a17;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  memset(InputBuffer, 0, sizeof(InputBuffer));
  v18 = 0;
  *a17 = 0;
  if ( (a3 & 0x2000000) == 0 )
  {
    v20 = 2LL * a1[4];
    if ( v20 > 0xFFFFFFFF
      || (unsigned int)v20 > 0xFFFF
      || (v21 = v20 + 68,
          (v22 = v21 + ((Size + 7) & 0xFFFFFFF8), v22 < v21)
       || (v23 = v22 + ((a15 + 7) & 0xFFFFFFF8), v47 = v23, v23 < v22)) )
    {
LABEL_46:
      v19 = -1073741675;
      goto LABEL_47;
    }
    v43[0] = 0;
    v24 = v23;
    if ( v23 )
    {
      try
      {
        std::vector<unsigned char>::_Resize_reallocate<unsigned char>(InputBuffer, v23, v43);
      }
      catch ( ... )
      {
        v18 = 0;
        v19 = -1073741670;
        v17 = v48;
        goto LABEL_47;
      }
    }
    try
    {
      v25 = InputBuffer[0];
      memset_0(InputBuffer[0], 0, v24);
      *v25 = 1;
      v25[4] = a6;
      v25[8] = a9;
      v25[9] = a10;
      v25[5] = a3;
      v25[6] = a7;
      v25[7] = a8;
      *((_WORD *)v25 + 32) = v20;
      v26 = Src;
      if ( *((_QWORD *)Src + 3) > 7u )
        v26 = *(void **)Src;
      memcpy_0(v25 + 17, v26, (unsigned __int16)v20);
      if ( Size )
      {
        v25[11] = Size;
        v25[10] = v21;
        memcpy_0((char *)v25 + v21, v52, Size);
      }
      else
      {
        v22 = v20 + 68;
      }
      if ( a15 )
      {
        v25[15] = a15;
        v25[14] = v22;
        memcpy_0((char *)v25 + v22, v53, a15);
      }
      *((_QWORD *)v25 + 6) = 0;
      v42 = 0;
      v27 = 1160;
      v28 = (char *)v44[1];
      v29 = (char *)v44[1] - (char *)v44[0];
      if ( (PVOID)((char *)v44[1] - (char *)v44[0]) > (PVOID)0x488 )
      {
        v30 = (char *)v44[0] + 1160;
LABEL_23:
        v44[1] = v30;
        goto LABEL_60;
      }
      if ( (PVOID)((char *)v44[1] - (char *)v44[0]) < (PVOID)0x488 )
      {
        if ( v45 - (unsigned __int64)v44[0] >= 0x488 )
        {
          v31 = 1160 - v29;
          memset_0(v44[1], 0, 1160 - v29);
          v30 = &v28[v31];
          goto LABEL_23;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v44, 1160);
      }
    }
    catch ( ... )
    {
      v18 = 0;
      v19 = -1073741670;
      v17 = v48;
      goto LABEL_47;
    }
LABEL_60:
    v18 = (ULONG_PTR *)v44[0];
    v46 = v44[0];
    while ( 1 )
    {
      v19 = p9fs::util::storvsp::VstorIoControl(FileHandle, v17, 0x240320u, v25, v47, v18, v27);
      if ( v19 < 0 )
        goto LABEL_47;
      v19 = *v49;
      if ( *v49 < 0 )
        goto LABEL_47;
      if ( v17->Information < 0x70 || *(_DWORD *)v18 != 2 )
        goto LABEL_2;
      v19 = *((_DWORD *)v18 + 1);
      if ( v19 != -2147483603 )
        goto LABEL_47;
      v32 = *((_DWORD *)v18 + 7);
      if ( v32 )
        break;
LABEL_44:
      if ( (unsigned int)++v42 > 3 )
        goto LABEL_47;
    }
    if ( *((_DWORD *)v18 + 6) )
    {
      ProcessHeap = GetProcessHeap();
      v34 = HeapAlloc(ProcessHeap, 8u, v32);
      v35 = v34;
      if ( v34 )
      {
        memcpy_0(v34, (char *)v18 + *((unsigned int *)v18 + 6), *((unsigned int *)v18 + 7));
        *v55 = v35;
      }
      else
      {
        v19 = -1073741670;
      }
      goto LABEL_47;
    }
    v36 = v32 + v27;
    if ( (unsigned int)v36 < v27 )
      goto LABEL_46;
    v27 += v32;
    v19 = 0;
    v37 = (char *)v44[1];
    if ( (PVOID)(unsigned int)v36 < (PVOID)((char *)v44[1] - (char *)v44[0]) )
    {
      v38 = (char *)v44[0] + v36;
LABEL_42:
      v44[1] = v38;
      goto LABEL_43;
    }
    if ( (PVOID)(unsigned int)v36 > (PVOID)((char *)v44[1] - (char *)v44[0]) )
    {
      if ( (unsigned int)v36 <= v45 - (unsigned __int64)v44[0] )
      {
        v39 = (unsigned int)v36 - (unsigned __int64)((char *)v44[1] - (char *)v44[0]);
        memset_0(v44[1], 0, v39);
        v38 = &v37[v39];
        goto LABEL_42;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v44, (unsigned int)v36);
    }
LABEL_43:
    v18 = (ULONG_PTR *)v44[0];
    v46 = v44[0];
    goto LABEL_44;
  }
LABEL_2:
  v19 = -1073741595;
LABEL_47:
  v17->Information = 0;
  *v49 = v19;
  if ( v19 >= 0 && v18 )
  {
    *v56 = v18[1];
    v18[1] = 0;
    v17->Information = v18[2];
  }
  std::vector<unsigned char>::~vector<unsigned char>(InputBuffer);
  return std::vector<unsigned char>::~vector<unsigned char>(v44);
}

```

## disassembly

```asm
0x18002a16c  mov     r11, rsp
0x18002a16f  mov     [r11+18h], rbx
0x18002a173  mov     [r11+20h], rsi
0x18002a177  push    rdi
0x18002a178  push    r12
0x18002a17a  push    r13
0x18002a17c  push    r14
0x18002a17e  push    r15
0x18002a180  sub     rsp, 0D0h
0x18002a187  mov     [rsp+0F8h+var_B8], r8d
0x18002a18c  mov     r13, rdx
0x18002a18f  mov     [rsp+0F8h+Src], rcx
0x18002a197  mov     [rsp+0F8h+var_80], rdx
0x18002a19c  mov     [rsp+0F8h+var_88], rdx
0x18002a1a1  mov     rax, [rsp+0F8h+arg_50]
0x18002a1a9  mov     [rsp+0F8h+FileHandle], rax
0x18002a1b1  mov     rax, [rsp+0F8h+arg_58]
0x18002a1b9  mov     [rsp+0F8h+var_58], rax
0x18002a1c1  mov     rax, [rsp+0F8h+arg_68]
0x18002a1c9  mov     [rsp+0F8h+var_50], rax
0x18002a1d1  mov     rax, [rsp+0F8h+arg_78]
0x18002a1d9  mov     [rsp+0F8h+var_38], rax
0x18002a1e1  mov     rax, [rsp+0F8h+arg_80]
0x18002a1e9  mov     [rsp+0F8h+var_40], rax
0x18002a1f1  xorps   xmm1, xmm1
0x18002a1f4  movdqu  xmmword ptr [rsp+0F8h+var_B0], xmm1
0x18002a1fa  xor     esi, esi
0x18002a1fc  mov     [rsp+0F8h+var_A0], rsi
0x18002a201  movdqu  xmmword ptr [r11-78h], xmm1
0x18002a207  mov     [r11-68h], rsi
0x18002a20b  mov     edi, esi
0x18002a20d  mov     [rax], rsi
0x18002a210  bt      r8d, 19h
0x18002a215  jnb     short loc_18002A221
0x18002a217  mov     ebx, 0C00000E5h
0x18002a21c  jmp     loc_18002A56D
0x18002a221  mov     ebx, [rcx+10h]
0x18002a224  add     rbx, rbx
0x18002a227  mov     eax, 0FFFFFFFFh
0x18002a22c  cmp     rbx, rax
0x18002a22f  ja      loc_18002A568
0x18002a235  cmp     ebx, 0FFFFh
0x18002a23b  ja      loc_18002A568
0x18002a241  lea     r14d, [rbx+44h]
0x18002a245  cmp     r14d, 44h ; 'D'
0x18002a249  jb      loc_18002A568
0x18002a24f  mov     r12d, dword ptr [rsp+0F8h+Size]
0x18002a257  add     r12d, 7
0x18002a25b  mov     ecx, 0FFFFFFF8h
0x18002a260  and     r12d, ecx
0x18002a263  add     r12d, r14d
0x18002a266  cmp     r12d, r14d
0x18002a269  jb      loc_18002A568
0x18002a26f  movzx   eax, [rsp+0F8h+arg_70]
0x18002a277  add     eax, 7
0x18002a27a  and     eax, ecx
0x18002a27c  add     eax, r12d
0x18002a27f  mov     [rsp+0F8h+var_90], eax
0x18002a283  cmp     eax, r12d
0x18002a286  jb      loc_18002A568
0x18002a28c  mov     [rsp+0F8h+var_B4], sil
0x18002a291  mov     edi, eax
0x18002a293  test    eax, eax
0x18002a295  jz      short loc_18002A2AC
0x18002a297  lea     r8, [rsp+0F8h+var_B4]
0x18002a29c  mov     edx, edi
0x18002a29e  lea     rcx, [rsp+0F8h+InputBuffer]
0x18002a2a6  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x18002a2ab  nop
0x18002a2ac  mov     r15, [rsp+0F8h+InputBuffer]
0x18002a2b4  mov     r8, rdi; Size
0x18002a2b7  xor     edx, edx; Val
0x18002a2b9  mov     rcx, r15; void *
0x18002a2bc  call    memset_0
0x18002a2c1  mov     dword ptr [r15], 1
0x18002a2c8  mov     eax, [rsp+0F8h+arg_28]
0x18002a2cf  mov     [r15+10h], eax
0x18002a2d3  mov     eax, [rsp+0F8h+arg_40]
0x18002a2da  mov     [r15+20h], eax
0x18002a2de  mov     eax, [rsp+0F8h+arg_48]
0x18002a2e5  mov     [r15+24h], eax
0x18002a2e9  mov     eax, [rsp+0F8h+var_B8]
0x18002a2ed  mov     [r15+14h], eax
0x18002a2f1  mov     eax, [rsp+0F8h+arg_30]
0x18002a2f8  mov     [r15+18h], eax
0x18002a2fc  mov     eax, [rsp+0F8h+arg_38]
0x18002a303  mov     [r15+1Ch], eax
0x18002a307  mov     [r15+40h], bx
0x18002a30c  mov     rax, [rsp+0F8h+Src]
0x18002a314  cmp     qword ptr [rax+18h], 7
0x18002a319  jbe     short loc_18002A31E
0x18002a31b  mov     rax, [rax]
0x18002a31e  movzx   r8d, bx; Size
0x18002a322  lea     rcx, [r15+44h]; void *
0x18002a326  mov     rdx, rax; Src
0x18002a329  call    memcpy_0
0x18002a32e  mov     eax, dword ptr [rsp+0F8h+Size]
0x18002a335  test    eax, eax
0x18002a337  jz      short loc_18002A359
0x18002a339  mov     [r15+2Ch], eax
0x18002a33d  mov     [r15+28h], r14d
0x18002a341  mov     r8d, eax; Size
0x18002a344  mov     ecx, r14d
0x18002a347  add     rcx, r15; void *
0x18002a34a  mov     rdx, [rsp+0F8h+var_58]; Src
0x18002a352  call    memcpy_0
0x18002a357  jmp     short loc_18002A35C
0x18002a359  mov     r12d, r14d
0x18002a35c  cmp     [rsp+0F8h+arg_70], si
0x18002a364  jbe     short loc_18002A392
0x18002a366  movzx   eax, [rsp+0F8h+arg_70]
0x18002a36e  mov     [r15+3Ch], eax
0x18002a372  mov     [r15+38h], r12d
0x18002a376  movzx   r8d, [rsp+0F8h+arg_70]; Size
0x18002a37f  mov     ecx, r12d
0x18002a382  add     rcx, r15; void *
0x18002a385  mov     rdx, [rsp+0F8h+var_50]; Src
0x18002a38d  call    memcpy_0
0x18002a392  mov     [r15+30h], rsi
0x18002a396  mov     [rsp+0F8h+var_B8], esi
0x18002a39a  mov     r14d, 488h
0x18002a3a0  mov     rdx, [rsp+0F8h+var_B0]
0x18002a3a5  mov     rdi, [rsp+0F8h+var_B0+8]
0x18002a3aa  mov     rcx, rdi
0x18002a3ad  sub     rcx, rdx
0x18002a3b0  cmp     rcx, r14
0x18002a3b3  jbe     short loc_18002A3BE
0x18002a3b5  lea     rax, [rdx+488h]
0x18002a3bc  jmp     short loc_18002A3F3
0x18002a3be  jnb     short loc_18002A3F8
0x18002a3c0  mov     rax, [rsp+0F8h+var_A0]
0x18002a3c5  sub     rax, rdx
0x18002a3c8  cmp     rax, r14
0x18002a3cb  jnb     short loc_18002A3DC
0x18002a3cd  mov     rdx, r14
0x18002a3d0  lea     rcx, [rsp+0F8h+var_B0]
0x18002a3d5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002a3da  jmp     short loc_18002A3F8
0x18002a3dc  mov     rbx, r14
0x18002a3df  sub     rbx, rcx
0x18002a3e2  mov     r8, rbx; Size
0x18002a3e5  xor     edx, edx; Val
0x18002a3e7  mov     rcx, rdi; void *
0x18002a3ea  call    memset_0
0x18002a3ef  lea     rax, [rdi+rbx]
0x18002a3f3  mov     [rsp+0F8h+var_B0+8], rax
0x18002a3f8  mov     rdi, [rsp+0F8h+var_B0]
0x18002a3fd  mov     [rsp+0F8h+var_98], rdi
0x18002a402  mov     [rsp+0F8h+var_C8], r14d; ULONG
0x18002a407  mov     [rsp+0F8h+var_D0], rdi; PVOID
0x18002a40c  mov     eax, [rsp+0F8h+var_90]
0x18002a410  mov     [rsp+0F8h+var_D8], eax; ULONG
0x18002a414  mov     r9, r15; InputBuffer
0x18002a417  mov     r8d, 240320h; IoControlCode
0x18002a41d  mov     rdx, r13; IoStatusBlock
0x18002a420  mov     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x18002a428  call    ?VstorIoControl@storvsp@util@p9fs@@YAJPEAXPEAU_IO_STATUS_BLOCK@@K0K0K@Z; p9fs::util::storvsp::VstorIoControl(void *,_IO_STATUS_BLOCK *,ulong,void *,ulong,void *,ulong)
0x18002a42d  mov     ebx, eax
0x18002a42f  test    eax, eax
0x18002a431  js      loc_18002A56D
0x18002a437  mov     rax, [rsp+0F8h+var_80]
0x18002a43c  mov     ebx, [rax]
0x18002a43e  test    ebx, ebx
0x18002a440  js      loc_18002A56D
0x18002a446  cmp     qword ptr [r13+8], 70h ; 'p'
0x18002a44b  jb      loc_18002A217
0x18002a451  cmp     dword ptr [rdi], 2
0x18002a454  jnz     loc_18002A217
0x18002a45a  mov     ebx, [rdi+4]
0x18002a45d  cmp     ebx, 8000002Dh
0x18002a463  jnz     loc_18002A56D
0x18002a469  mov     r12d, [rdi+1Ch]
0x18002a46d  test    r12d, r12d
0x18002a470  jz      loc_18002A537
0x18002a476  cmp     [rdi+18h], esi
0x18002a479  jz      short loc_18002A4C6
0x18002a47b  call    cs:__imp_GetProcessHeap
0x18002a481  mov     r8d, r12d; dwBytes
0x18002a484  mov     edx, 8; dwFlags
0x18002a489  mov     rcx, rax; hHeap
0x18002a48c  call    cs:__imp_HeapAlloc
0x18002a492  mov     r14, rax
0x18002a495  test    rax, rax
0x18002a498  jnz     short loc_18002A4A4
0x18002a49a  mov     ebx, 0C000009Ah
0x18002a49f  jmp     loc_18002A56D
0x18002a4a4  mov     r8d, [rdi+1Ch]; Size
0x18002a4a8  mov     edx, [rdi+18h]
0x18002a4ab  add     rdx, rdi; Src
0x18002a4ae  mov     rcx, r14; void *
0x18002a4b1  call    memcpy_0
0x18002a4b6  mov     rax, [rsp+0F8h+var_40]
0x18002a4be  mov     [rax], r14
0x18002a4c1  jmp     loc_18002A56D
0x18002a4c6  lea     eax, [r12+r14]
0x18002a4ca  cmp     eax, r14d
0x18002a4cd  jb      loc_18002A568
0x18002a4d3  mov     r14d, eax
0x18002a4d6  mov     ebx, esi
0x18002a4d8  mov     rdx, [rsp+0F8h+var_B0]
0x18002a4dd  mov     r12, [rsp+0F8h+var_B0+8]
0x18002a4e2  mov     rcx, r12
0x18002a4e5  sub     rcx, rdx
0x18002a4e8  mov     edi, r14d
0x18002a4eb  cmp     r14, rcx
0x18002a4ee  jnb     short loc_18002A4F6
0x18002a4f0  lea     rax, [rax+rdx]
0x18002a4f4  jmp     short loc_18002A528
0x18002a4f6  jbe     short loc_18002A52D
0x18002a4f8  mov     rax, [rsp+0F8h+var_A0]
0x18002a4fd  sub     rax, rdx
0x18002a500  cmp     rdi, rax
0x18002a503  jbe     short loc_18002A514
0x18002a505  mov     rdx, rdi
0x18002a508  lea     rcx, [rsp+0F8h+var_B0]
0x18002a50d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002a512  jmp     short loc_18002A52D
0x18002a514  sub     rdi, rcx
0x18002a517  mov     r8, rdi; Size
0x18002a51a  xor     edx, edx; Val
0x18002a51c  mov     rcx, r12; void *
0x18002a51f  call    memset_0
0x18002a524  lea     rax, [r12+rdi]
0x18002a528  mov     [rsp+0F8h+var_B0+8], rax
0x18002a52d  mov     rdi, [rsp+0F8h+var_B0]
0x18002a532  mov     [rsp+0F8h+var_98], rdi
0x18002a537  mov     r12d, [rsp+0F8h+var_B8]
0x18002a53c  inc     r12d
0x18002a53f  mov     [rsp+0F8h+var_B8], r12d
0x18002a544  cmp     r12d, 3
0x18002a548  jbe     loc_18002A402
0x18002a54e  jmp     short loc_18002A56D
0x18002a550  xor     esi, esi
0x18002a552  mov     rdi, [rsp+0F8h+var_98]
0x18002a557  jmp     short loc_18002A55D
0x18002a559  xor     esi, esi
0x18002a55b  mov     edi, esi
0x18002a55d  mov     ebx, [rsp+0F8h+var_B8]
0x18002a561  mov     r13, [rsp+0F8h+var_88]
0x18002a566  jmp     short loc_18002A56D
0x18002a568  mov     ebx, 0C0000095h
0x18002a56d  mov     [r13+8], rsi
0x18002a571  mov     rax, [rsp+0F8h+var_80]
0x18002a576  mov     [rax], ebx
0x18002a578  test    ebx, ebx
0x18002a57a  js      short loc_18002A59C
0x18002a57c  test    rdi, rdi
0x18002a57f  jz      short loc_18002A59C
0x18002a581  mov     rcx, [rdi+8]
0x18002a585  mov     rax, [rsp+0F8h+var_38]
0x18002a58d  mov     [rax], rcx
0x18002a590  mov     [rdi+8], rsi
0x18002a594  mov     rax, [rdi+10h]
0x18002a598  mov     [r13+8], rax
0x18002a59c  lea     rcx, [rsp+0F8h+InputBuffer]
0x18002a5a4  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002a5a9  nop
0x18002a5aa  lea     rcx, [rsp+0F8h+var_B0]
0x18002a5af  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002a5b4  lea     r11, [rsp+0F8h+var_28]
0x18002a5bc  mov     rbx, [r11+40h]
0x18002a5c0  mov     rsi, [r11+48h]
0x18002a5c4  mov     rsp, r11
0x18002a5c7  pop     r15
0x18002a5c9  pop     r14
0x18002a5cb  pop     r13
0x18002a5cd  pop     r12
0x18002a5cf  pop     rdi
0x18002a5d0  retn
```
