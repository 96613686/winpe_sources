# CWMSMPTEIndexer::DumpSMPTEIndexToFile(void *,CASFMMStream *,ulong *)

- ea: `0x18000dfe0`
- end: `0x18000e33a`
- name: `?DumpSMPTEIndexToFile@CWMSMPTEIndexer@@UEAAJPEAXPEAVCASFMMStream@@PEAK@Z`
- size: `858`
- prototype: `__int64 __fastcall(CWMSMPTEIndexer *__hidden this, void *, struct CASFMMStream *, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x1800015f0`
- `0x180007e38`
- `0x18000dfe0`
- `0x1800279e8`
- `0x180027a24`
- `0x180028e40`
- `0x180028ee0`
- `0x180028f60`
- `0x180028fa0`
- `0x180029060`
- `0x1800290a0`
- `0x18002b010`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000e292`
- `KERNEL32!WriteFile` at `0x18000e292`

## pseudocode

```c
__int64 __fastcall CWMSMPTEIndexer::DumpSMPTEIndexToFile(
        CWMSMPTEIndexer *this,
        void *a2,
        struct CASFMMStream *a3,
        unsigned int *a4)
{
  void *v6; // r14
  unsigned int v7; // eax
  int v8; // ebx
  unsigned __int16 v9; // si
  unsigned int i; // ebx
  __int64 v11; // rax
  unsigned __int16 v12; // cx
  unsigned __int16 v13; // r13
  unsigned int j; // r12d
  __int64 v15; // rax
  unsigned int k; // esi
  __int64 v17; // rax
  unsigned __int16 *v18; // r12
  unsigned __int16 v19; // r13
  unsigned int v20; // r12d
  char *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  __int64 v24; // rax
  unsigned __int64 v25; // rsi
  char *v26; // rax
  struct CASFMMStream *v27; // r13
  HANDLE v28; // rbx
  __int64 v29; // rax
  unsigned __int64 v30; // rdx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-A9h] BYREF
  int v33; // [rsp+34h] [rbp-A5h] BYREF
  unsigned int v34; // [rsp+38h] [rbp-A1h]
  unsigned __int64 v35; // [rsp+40h] [rbp-99h] BYREF
  struct CASFMMStream *v36; // [rsp+48h] [rbp-91h]
  HANDLE hFile; // [rsp+50h] [rbp-89h]
  _QWORD v38[3]; // [rsp+58h] [rbp-81h] BYREF
  int v39; // [rsp+70h] [rbp-69h]
  int v40; // [rsp+74h] [rbp-65h]
  _QWORD v41[7]; // [rsp+80h] [rbp-59h] BYREF
  unsigned __int16 v42; // [rsp+BCh] [rbp-1Dh]

  v36 = a3;
  hFile = a2;
  if ( !a3 || a2 == (void *)-1LL )
    return 2147942487LL;
  v6 = 0;
  CASFSMPTEIndexObjectV1::CASFSMPTEIndexObjectV1((CASFSMPTEIndexObjectV1 *)v41);
  v7 = *((_DWORD *)this + 180);
  v41[0] = &CASFSkeletonSMPTEIndexObject::`vftable';
  v34 = v7;
  v8 = CASFSMPTEIndexObjectV1::SetBlockCount((CASFSMPTEIndexObjectV1 *)v41, v7);
  if ( v8 >= 0 )
  {
    v9 = 0;
    for ( i = 0; i < *((_DWORD *)this + 58); v9 = v12 )
    {
      v11 = CTPtrArray<unsigned char,20>::operator[]((char *)this + 16, i);
      v12 = v9 + 1;
      if ( !v11 )
        v12 = v9;
      ++i;
    }
    v8 = CASFBaseIndexObjectEx::SetSpecifierCount((CASFBaseIndexObjectEx *)v41, v9);
    if ( v8 >= 0 )
    {
      v13 = 0;
      for ( j = 0; j < v9; ++j )
      {
        v15 = CTPtrArray<unsigned char,20>::operator[]((char *)this + 16, j);
        if ( v15 )
        {
          v8 = CASFBaseIndexObjectEx::SetSpecifier((CASFBaseIndexObjectEx *)v41, v13, *(_WORD *)(v15 + 12), 2u);
          if ( v8 < 0 )
            goto LABEL_39;
          ++v13;
        }
      }
      for ( k = 0; k < v34; ++k )
      {
        v17 = CTPtrArray<unsigned char,20>::operator[]((char *)this + 504, k);
        v18 = (unsigned __int16 *)v17;
        if ( !v17 )
        {
          v8 = -2147418113;
          goto LABEL_39;
        }
        v8 = CASFSkeletonSMPTEIndexObject::SetBlock((CASFSkeletonSMPTEIndexObject *)v41, k, *(_DWORD *)(v17 + 16));
        if ( v8 < 0 )
          goto LABEL_39;
        v8 = CASFSMPTEIndexObjectV1::SetBlockSMPTERange((CASFSMPTEIndexObjectV1 *)v41, k, *v18);
        if ( v8 < 0 )
          goto LABEL_39;
        v19 = 0;
        v20 = 0;
        if ( *((_DWORD *)this + 58) )
        {
          v21 = (char *)this + 16;
          do
          {
            v22 = (_QWORD *)CTPtrArray<unsigned char,20>::operator[](v21, v20);
            v23 = v22;
            if ( v22 )
            {
              v24 = *v22;
              v35 = 0;
              v8 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, unsigned __int64 *))(v24 + 48))(v23, k, &v35);
              if ( v8 < 0 )
                goto LABEL_39;
              v8 = CASFBaseIndexObjectEx::SetBlockOffset((CASFBaseIndexObjectEx *)v41, k, v19, v35);
              if ( v8 < 0 )
                goto LABEL_39;
              ++v19;
            }
            ++v20;
            v21 = (char *)this + 16;
          }
          while ( v20 < *((_DWORD *)this + 58) );
        }
      }
      v25 = 4 * (unsigned int)v42 + 34;
      v26 = (char *)operator new[](v25);
      v6 = v26;
      if ( v26 )
      {
        v27 = v36;
        v38[0] = v26;
        v38[1] = v26;
        v39 = 1;
        v40 = *((_DWORD *)v36 + 166);
        v38[2] = &v26[v25];
        v8 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(v41[0] + 168LL))(v41, v38);
        if ( v8 >= 0 )
        {
          v28 = hFile;
          NumberOfBytesWritten = 0;
          if ( WriteFile(hFile, v6, v25, &NumberOfBytesWritten, 0) && NumberOfBytesWritten >= (unsigned int)v25 )
          {
            if ( a4 )
              *a4 = NumberOfBytesWritten;
            v29 = *(_QWORD *)this;
            v33 = 0;
            v8 = (*(__int64 (__fastcall **)(CWMSMPTEIndexer *, HANDLE, struct CASFMMStream *, _QWORD *, int *))(v29 + 72))(
                   this,
                   v28,
                   v27,
                   v41,
                   &v33);
            if ( v8 >= 0 && a4 )
              *a4 += v33;
          }
          else
          {
            v8 = -2147467259;
          }
        }
      }
      else
      {
        v8 = -2147024882;
      }
    }
  }
LABEL_39:
  v41[0] = &CASFSMPTEIndexObjectV1::`vftable';
  CASFBaseIndexObjectEx::~CASFBaseIndexObjectEx((CASFBaseIndexObjectEx *)v41);
  if ( v6 )
    operator delete(v6, v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000dfe0  push    rbp
0x18000dfe2  push    rbx
0x18000dfe3  push    rsi
0x18000dfe4  push    rdi
0x18000dfe5  push    r12
0x18000dfe7  push    r13
0x18000dfe9  push    r14
0x18000dfeb  push    r15
0x18000dfed  lea     rbp, [rsp-1Fh]
0x18000dff2  sub     rsp, 0F8h
0x18000dff9  mov     rax, cs:__security_cookie
0x18000e000  xor     rax, rsp
0x18000e003  mov     [rbp+57h+var_50], rax
0x18000e007  mov     [rsp+130h+var_E8], r8
0x18000e00c  mov     r15, r9
0x18000e00f  mov     [rsp+130h+hFile], rdx
0x18000e014  mov     rax, rdx
0x18000e017  mov     rdi, rcx
0x18000e01a  test    r8, r8
0x18000e01d  jz      loc_18000E315
0x18000e023  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e027  jz      loc_18000E315
0x18000e02d  lea     rcx, [rbp+57h+var_B0]; this
0x18000e031  xor     r14d, r14d
0x18000e034  call    ??0CASFSMPTEIndexObjectV1@@QEAA@XZ; CASFSMPTEIndexObjectV1::CASFSMPTEIndexObjectV1(void)
0x18000e039  mov     eax, [rdi+2D0h]
0x18000e03f  lea     rcx, ??_7CASFSkeletonSMPTEIndexObject@@6B@; const CASFSkeletonSMPTEIndexObject::`vftable'
0x18000e046  mov     [rbp+57h+var_B0], rcx
0x18000e04a  mov     edx, eax; unsigned int
0x18000e04c  lea     rcx, [rbp+57h+var_B0]; this
0x18000e050  mov     [rsp+130h+var_F8], eax
0x18000e054  call    ?SetBlockCount@CASFSMPTEIndexObjectV1@@UEAAJK@Z; CASFSMPTEIndexObjectV1::SetBlockCount(ulong)
0x18000e059  mov     ebx, eax
0x18000e05b  test    eax, eax
0x18000e05d  js      loc_18000E2F0
0x18000e063  xor     esi, esi
0x18000e065  lea     r13d, [r14+1]
0x18000e069  xor     ebx, ebx
0x18000e06b  cmp     [rdi+0E8h], ebx
0x18000e071  jbe     short loc_18000E097
0x18000e073  mov     edx, ebx
0x18000e075  lea     rcx, [rdi+10h]
0x18000e079  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000e07e  test    rax, rax
0x18000e081  lea     ecx, [rsi+r13]
0x18000e085  cmovz   cx, si
0x18000e089  add     ebx, r13d
0x18000e08c  movzx   esi, cx
0x18000e08f  cmp     ebx, [rdi+0E8h]
0x18000e095  jb      short loc_18000E073
0x18000e097  movzx   edx, si; unsigned __int16
0x18000e09a  lea     rcx, [rbp+57h+var_B0]; this
0x18000e09e  call    ?SetSpecifierCount@CASFBaseIndexObjectEx@@UEAAJG@Z; CASFBaseIndexObjectEx::SetSpecifierCount(ushort)
0x18000e0a3  mov     ebx, eax
0x18000e0a5  test    eax, eax
0x18000e0a7  js      loc_18000E2F0
0x18000e0ad  xor     r13d, r13d
0x18000e0b0  movzx   esi, si
0x18000e0b3  xor     r12d, r12d
0x18000e0b6  test    esi, esi
0x18000e0b8  jz      short loc_18000E108
0x18000e0ba  lea     rax, [rdi+10h]
0x18000e0be  mov     edx, r12d
0x18000e0c1  mov     rcx, rax
0x18000e0c4  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000e0c9  test    rax, rax
0x18000e0cc  jz      short loc_18000E0FB
0x18000e0ce  movzx   r8d, word ptr [rax+0Ch]; unsigned __int16
0x18000e0d3  lea     rcx, [rbp+57h+var_B0]; this
0x18000e0d7  mov     r9d, 2; unsigned __int16
0x18000e0dd  movzx   edx, r13w; unsigned __int16
0x18000e0e1  call    ?SetSpecifier@CASFBaseIndexObjectEx@@UEAAJGGG@Z; CASFBaseIndexObjectEx::SetSpecifier(ushort,ushort,ushort)
0x18000e0e6  mov     ebx, eax
0x18000e0e8  test    eax, eax
0x18000e0ea  js      loc_18000E2F0
0x18000e0f0  mov     eax, 1
0x18000e0f5  add     r13w, ax
0x18000e0f9  jmp     short loc_18000E100
0x18000e0fb  mov     eax, 1
0x18000e100  add     r12d, eax
0x18000e103  cmp     r12d, esi
0x18000e106  jb      short loc_18000E0BA
0x18000e108  xor     esi, esi
0x18000e10a  cmp     esi, [rsp+130h+var_F8]
0x18000e10e  jnb     loc_18000E1F8
0x18000e114  lea     rcx, [rdi+1F8h]
0x18000e11b  mov     edx, esi
0x18000e11d  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000e122  mov     r12, rax
0x18000e125  test    rax, rax
0x18000e128  jz      loc_18000E1EE
0x18000e12e  mov     r8d, [rax+10h]; unsigned int
0x18000e132  lea     rcx, [rbp+57h+var_B0]; this
0x18000e136  mov     edx, esi; unsigned int
0x18000e138  call    ?SetBlock@CASFSkeletonSMPTEIndexObject@@UEAAJKK@Z; CASFSkeletonSMPTEIndexObject::SetBlock(ulong,ulong)
0x18000e13d  mov     ebx, eax
0x18000e13f  test    eax, eax
0x18000e141  js      loc_18000E2F0
0x18000e147  movzx   r8d, word ptr [r12]; unsigned __int16
0x18000e14c  lea     rcx, [rbp+57h+var_B0]; this
0x18000e150  mov     edx, esi; unsigned int
0x18000e152  call    ?SetBlockSMPTERange@CASFSMPTEIndexObjectV1@@UEAAJKG@Z; CASFSMPTEIndexObjectV1::SetBlockSMPTERange(ulong,ushort)
0x18000e157  mov     ebx, eax
0x18000e159  test    eax, eax
0x18000e15b  js      loc_18000E2F0
0x18000e161  xor     r13d, r13d
0x18000e164  xor     r12d, r12d
0x18000e167  cmp     [rdi+0E8h], r12d
0x18000e16e  jbe     short loc_18000E1E7
0x18000e170  lea     rax, [rdi+10h]
0x18000e174  mov     edx, r12d
0x18000e177  mov     rcx, rax
0x18000e17a  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000e17f  mov     rcx, rax
0x18000e182  test    rax, rax
0x18000e185  jz      short loc_18000E1D2
0x18000e187  mov     rax, [rax]
0x18000e18a  lea     r8, [rsp+130h+var_F0]
0x18000e18f  mov     edx, esi
0x18000e191  mov     [rsp+130h+var_F0], r14
0x18000e196  mov     rax, [rax+30h]
0x18000e19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e19f  mov     ebx, eax
0x18000e1a1  test    eax, eax
0x18000e1a3  js      loc_18000E2F0
0x18000e1a9  mov     r9, [rsp+130h+var_F0]; unsigned __int64
0x18000e1ae  lea     rcx, [rbp+57h+var_B0]; this
0x18000e1b2  movzx   r8d, r13w; unsigned __int16
0x18000e1b6  mov     edx, esi; unsigned int
0x18000e1b8  call    ?SetBlockOffset@CASFBaseIndexObjectEx@@UEAAJKG_K@Z; CASFBaseIndexObjectEx::SetBlockOffset(ulong,ushort,unsigned __int64)
0x18000e1bd  mov     ebx, eax
0x18000e1bf  test    eax, eax
0x18000e1c1  js      loc_18000E2F0
0x18000e1c7  mov     eax, 1
0x18000e1cc  add     r13w, ax
0x18000e1d0  jmp     short loc_18000E1D7
0x18000e1d2  mov     eax, 1
0x18000e1d7  add     r12d, eax
0x18000e1da  lea     rax, [rdi+10h]
0x18000e1de  cmp     r12d, [rdi+0E8h]
0x18000e1e5  jb      short loc_18000E174
0x18000e1e7  inc     esi
0x18000e1e9  jmp     loc_18000E10A
0x18000e1ee  mov     ebx, 8000FFFFh
0x18000e1f3  jmp     loc_18000E2F0
0x18000e1f8  test    ebx, ebx
0x18000e1fa  js      loc_18000E2F0
0x18000e200  movzx   eax, [rbp+57h+var_74]
0x18000e204  lea     esi, ds:22h[rax*4]
0x18000e20b  mov     ecx, esi; unsigned __int64
0x18000e20d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000e212  mov     r14, rax
0x18000e215  test    rax, rax
0x18000e218  jnz     short loc_18000E224
0x18000e21a  mov     ebx, 8007000Eh
0x18000e21f  jmp     loc_18000E2F0
0x18000e224  mov     r13, [rsp+130h+var_E8]
0x18000e229  lea     rdx, [rsp+130h+var_D8]
0x18000e22e  lea     rcx, [rbp+57h+var_B0]
0x18000e232  mov     [rsp+130h+var_D8], r14
0x18000e237  mov     [rbp+57h+var_D0], r14
0x18000e23b  mov     [rbp+57h+var_C0], 1
0x18000e242  mov     eax, [r13+298h]
0x18000e249  mov     [rbp+57h+var_BC], eax
0x18000e24c  lea     rax, [rsi+r14]
0x18000e250  mov     [rbp+57h+var_C8], rax
0x18000e254  mov     rax, [rbp+57h+var_B0]
0x18000e258  mov     rax, [rax+0A8h]
0x18000e25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e264  mov     ebx, eax
0x18000e266  test    eax, eax
0x18000e268  js      loc_18000E2F0
0x18000e26e  mov     rbx, [rsp+130h+hFile]
0x18000e273  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000e278  mov     rcx, rbx; hFile
0x18000e27b  mov     [rsp+130h+NumberOfBytesWritten], 0
0x18000e283  mov     r8d, esi; nNumberOfBytesToWrite
0x18000e286  mov     [rsp+130h+lpOverlapped], 0; lpOverlapped
0x18000e28f  mov     rdx, r14; lpBuffer
0x18000e292  call    cs:__imp_WriteFile
0x18000e298  test    eax, eax
0x18000e29a  jz      short loc_18000E2EB
0x18000e29c  mov     eax, [rsp+130h+NumberOfBytesWritten]
0x18000e2a0  cmp     eax, esi
0x18000e2a2  jb      short loc_18000E2EB
0x18000e2a4  test    r15, r15
0x18000e2a7  jz      short loc_18000E2AC
0x18000e2a9  mov     [r15], eax
0x18000e2ac  mov     rax, [rdi]
0x18000e2af  lea     rcx, [rsp+130h+var_FC]
0x18000e2b4  mov     [rsp+130h+lpOverlapped], rcx
0x18000e2b9  lea     r9, [rbp+57h+var_B0]
0x18000e2bd  mov     r8, r13
0x18000e2c0  mov     [rsp+130h+var_FC], 0
0x18000e2c8  mov     rdx, rbx
0x18000e2cb  mov     rcx, rdi
0x18000e2ce  mov     rax, [rax+48h]
0x18000e2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2d7  mov     ebx, eax
0x18000e2d9  test    eax, eax
0x18000e2db  js      short loc_18000E2F0
0x18000e2dd  test    r15, r15
0x18000e2e0  jz      short loc_18000E2F0
0x18000e2e2  mov     eax, [rsp+130h+var_FC]
0x18000e2e6  add     [r15], eax
0x18000e2e9  jmp     short loc_18000E2F0
0x18000e2eb  mov     ebx, 80004005h
0x18000e2f0  lea     rax, ??_7CASFSMPTEIndexObjectV1@@6B@; const CASFSMPTEIndexObjectV1::`vftable'
0x18000e2f7  lea     rcx, [rbp+57h+var_B0]; this
0x18000e2fb  mov     [rbp+57h+var_B0], rax
0x18000e2ff  call    ??1CASFBaseIndexObjectEx@@UEAA@XZ; CASFBaseIndexObjectEx::~CASFBaseIndexObjectEx(void)
0x18000e304  test    r14, r14
0x18000e307  jz      short loc_18000E311
0x18000e309  mov     rcx, r14; void *
0x18000e30c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e311  mov     eax, ebx
0x18000e313  jmp     short loc_18000E31A
0x18000e315  mov     eax, 80070057h
0x18000e31a  mov     rcx, [rbp+57h+var_50]
0x18000e31e  xor     rcx, rsp; StackCookie
0x18000e321  call    __security_check_cookie
0x18000e326  add     rsp, 0F8h
0x18000e32d  pop     r15
0x18000e32f  pop     r14
0x18000e331  pop     r13
0x18000e333  pop     r12
0x18000e335  pop     rdi
0x18000e336  pop     rsi
0x18000e337  pop     rbx
0x18000e338  pop     rbp
0x18000e339  retn
```
