# CWMSMPTEIndexer::DumpSMPTEIndexBlocks(void *,CASFMMStream *,CASFSkeletonSMPTEIndexObject *,ulong *)

- ea: `0x18000dbb0`
- end: `0x18000dfd4`
- name: `?DumpSMPTEIndexBlocks@CWMSMPTEIndexer@@MEAAJPEAXPEAVCASFMMStream@@PEAVCASFSkeletonSMPTEIndexObject@@PEAK@Z`
- size: `1060`
- prototype: `__int64 __fastcall(CWMSMPTEIndexer *__hidden this, void *, struct CASFMMStream *, struct CASFSkeletonSMPTEIndexObject *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x1800015f0`
- `0x180007e38`
- `0x18000dbb0`
- `0x18002b010`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000dde7`
- `KERNEL32!WriteFile` at `0x18000df3f`
- `KERNEL32!WriteFile` at `0x18000dde7`
- `KERNEL32!WriteFile` at `0x18000df3f`

## pseudocode

```c
__int64 __fastcall CWMSMPTEIndexer::DumpSMPTEIndexBlocks(
        CWMSMPTEIndexer *this,
        void *a2,
        struct CASFMMStream *a3,
        struct CASFSkeletonSMPTEIndexObject *a4,
        unsigned int *a5)
{
  unsigned int v8; // r15d
  char *v9; // rax
  char *v10; // rcx
  int v11; // ebx
  void *v12; // r13
  __int64 v13; // rax
  char *v14; // rax
  unsigned __int64 v15; // rdx
  char *v16; // r12
  __int64 v17; // rax
  unsigned int i; // esi
  __int64 v19; // rax
  unsigned int j; // esi
  DWORD v21; // ebx
  __int64 v22; // rax
  unsigned int k; // r13d
  int v24; // ebx
  char *v25; // rcx
  unsigned __int16 v26; // r13
  unsigned int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned __int64 v30; // rdx
  unsigned __int16 v32; // [rsp+40h] [rbp-91h] BYREF
  void *v33; // [rsp+48h] [rbp-89h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-7Dh] BYREF
  int v36; // [rsp+58h] [rbp-79h]
  DWORD v37; // [rsp+5Ch] [rbp-75h]
  DWORD v38; // [rsp+60h] [rbp-71h] BYREF
  unsigned int v39; // [rsp+64h] [rbp-6Dh]
  DWORD nNumberOfBytesToWrite; // [rsp+68h] [rbp-69h]
  LPCVOID lpBuffer; // [rsp+70h] [rbp-61h]
  HANDLE hFile; // [rsp+78h] [rbp-59h]
  LPCVOID v43; // [rsp+80h] [rbp-51h] BYREF
  LPCVOID v44; // [rsp+88h] [rbp-49h]
  char *v45; // [rsp+90h] [rbp-41h]
  int v46; // [rsp+98h] [rbp-39h]
  int v47; // [rsp+9Ch] [rbp-35h]
  char *v48; // [rsp+A0h] [rbp-31h] BYREF
  void *v49; // [rsp+A8h] [rbp-29h]
  char *v50; // [rsp+B0h] [rbp-21h]
  int v51; // [rsp+B8h] [rbp-19h]
  int v52; // [rsp+BCh] [rbp-15h]
  char *v53; // [rsp+C0h] [rbp-11h]
  char *v54; // [rsp+C8h] [rbp-9h]
  unsigned int *v55; // [rsp+D0h] [rbp-1h]
  __int64 v56; // [rsp+D8h] [rbp+7h] BYREF
  int v57; // [rsp+E0h] [rbp+Fh]
  __int16 v58; // [rsp+E4h] [rbp+13h]

  v55 = a5;
  hFile = a2;
  if ( a2 == (void *)-1LL || !a3 || !a4 )
    return 2147942487LL;
  v56 = 0;
  v8 = 0;
  v57 = 0;
  v58 = 0;
  nNumberOfBytesToWrite = (*(__int64 (__fastcall **)(struct CASFSkeletonSMPTEIndexObject *))(*(_QWORD *)a4 + 216LL))(a4);
  v9 = (char *)operator new[](nNumberOfBytesToWrite);
  lpBuffer = v9;
  v10 = v9;
  if ( v9 )
  {
    v12 = 0;
    v47 = *((_DWORD *)a3 + 166);
    v53 = &v9[nNumberOfBytesToWrite];
    v45 = v53;
    v13 = *(_QWORD *)a4;
    v43 = v10;
    v44 = v10;
    v46 = 1;
    v37 = (*(__int64 (__fastcall **)(struct CASFSkeletonSMPTEIndexObject *))(v13 + 224))(a4);
    v14 = (char *)operator new[](v37);
    v16 = v14;
    if ( v14 )
    {
      v52 = *((_DWORD *)a3 + 166);
      v48 = v14;
      v54 = &v14[v37];
      v50 = v54;
      v32 = 0;
      v17 = *(_QWORD *)a4;
      v49 = v16;
      v51 = 1;
      v11 = (*(__int64 (__fastcall **)(struct CASFSkeletonSMPTEIndexObject *, unsigned __int16 *))(v17 + 128))(a4, &v32);
      if ( v11 < 0 )
        goto LABEL_38;
      v33 = operator new[](saturated_mul(v32, 4u));
      v12 = v33;
      if ( v33 )
      {
        v11 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 91) + 40LL))((char *)this + 728);
        if ( v11 >= 0 )
        {
          for ( i = 0; i < *((_DWORD *)this + 58); ++i )
          {
            v19 = CTPtrArray<unsigned char,20>::operator[]((char *)this + 16, i);
            v15 = v19;
            if ( v19 )
            {
              v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 56LL))(v19);
              if ( v11 < 0 )
                break;
            }
          }
          for ( j = 0; j < *((_DWORD *)this + 180); ++j )
          {
            v43 = lpBuffer;
            v44 = lpBuffer;
            v45 = v53;
            v11 = (*(__int64 (__fastcall **)(struct CASFSkeletonSMPTEIndexObject *, _QWORD, LPCVOID *))(*(_QWORD *)a4 + 312LL))(
                    a4,
                    j,
                    &v43);
            if ( v11 < 0 )
              break;
            v21 = nNumberOfBytesToWrite;
            NumberOfBytesWritten = 0;
            if ( !WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
              || NumberOfBytesWritten < v21 )
            {
LABEL_36:
              v11 = -2147467259;
              break;
            }
            v22 = *(_QWORD *)a4;
            v35 = 0;
            v8 += v21;
            v11 = (*(__int64 (__fastcall **)(struct CASFSkeletonSMPTEIndexObject *, _QWORD, _QWORD, unsigned int *))(v22 + 152))(
                    a4,
                    j,
                    0,
                    &v35);
            if ( v11 < 0 )
              break;
            for ( k = 0; ; ++k )
            {
              v39 = k;
              if ( k >= v35 )
                break;
              v11 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 91) + 48LL))(
                      (char *)this + 728,
                      &v56);
              if ( v11 < 0 )
                goto LABEL_37;
              if ( *((_DWORD *)this + 58) )
              {
                LOWORD(v24) = 0;
                v25 = (char *)this + 16;
                v26 = 0;
                v36 = 0;
                v27 = 0;
                do
                {
                  v28 = CTPtrArray<unsigned char,20>::operator[](v25, v27);
                  if ( v28 )
                  {
                    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v28 + 64LL))(
                            v28,
                            j,
                            (__int64)v33 + 4 * (unsigned __int16)v24);
                    if ( v11 < 0 )
                      goto LABEL_37;
                    HIWORD(v24) = HIWORD(v36);
                    LOWORD(v24) = v36 + 1;
                    v36 = v24;
                  }
                  ++v26;
                  v25 = (char *)this + 16;
                  v27 = v26;
                }
                while ( (unsigned int)v26 < *((_DWORD *)this + 58) );
                k = v39;
              }
              v50 = v54;
              v29 = *(_QWORD *)a4;
              v48 = v16;
              v49 = v16;
              v11 = (*(__int64 (__fastcall **)(struct CASFSkeletonSMPTEIndexObject *, _QWORD, _QWORD, char *, void *, char **))(v29 + 320))(
                      a4,
                      j,
                      k,
                      (char *)&v56 + 2,
                      v33,
                      &v48);
              if ( v11 < 0 )
                goto LABEL_37;
              v38 = 0;
              if ( !WriteFile(hFile, v16, v37, &v38, 0) || v38 < v37 )
                goto LABEL_36;
              v8 += v37;
            }
          }
LABEL_37:
          v12 = v33;
        }
        goto LABEL_38;
      }
    }
    v11 = -2147024882;
LABEL_38:
    operator delete((void *)lpBuffer, v15);
    if ( v16 )
      operator delete(v16, v30);
    if ( v12 )
      operator delete(v12, v30);
    goto LABEL_42;
  }
  v11 = -2147024882;
LABEL_42:
  if ( v55 )
  {
    if ( v11 < 0 )
      v8 = 0;
    *v55 = v8;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000dbb0  mov     [rsp-8+arg_10], rbx
0x18000dbb5  push    rbp
0x18000dbb6  push    rsi
0x18000dbb7  push    rdi
0x18000dbb8  push    r12
0x18000dbba  push    r13
0x18000dbbc  push    r14
0x18000dbbe  push    r15
0x18000dbc0  lea     rbp, [rsp-1Fh]
0x18000dbc5  sub     rsp, 0F0h
0x18000dbcc  mov     rax, cs:__security_cookie
0x18000dbd3  xor     rax, rsp
0x18000dbd6  mov     [rbp+4Fh+var_38], rax
0x18000dbda  mov     rax, [rbp+4Fh+arg_20]
0x18000dbde  mov     rdi, r9
0x18000dbe1  mov     [rbp+4Fh+var_50], rax
0x18000dbe5  mov     rbx, r8
0x18000dbe8  mov     [rbp+4Fh+hFile], rdx
0x18000dbec  mov     r14, rcx
0x18000dbef  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000dbf3  jz      loc_18000DFA8
0x18000dbf9  test    rbx, rbx
0x18000dbfc  jz      loc_18000DFA8
0x18000dc02  test    r9, r9
0x18000dc05  jz      loc_18000DFA8
0x18000dc0b  xor     eax, eax
0x18000dc0d  mov     rcx, r9
0x18000dc10  mov     [rbp+4Fh+var_48], rax
0x18000dc14  xor     r15d, r15d
0x18000dc17  mov     [rbp+4Fh+var_40], eax
0x18000dc1a  mov     [rbp+4Fh+var_3C], ax
0x18000dc1e  mov     rax, [r9]
0x18000dc21  mov     rax, [rax+0D8h]
0x18000dc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc2d  mov     ecx, eax; unsigned __int64
0x18000dc2f  mov     [rbp+4Fh+nNumberOfBytesToWrite], eax
0x18000dc32  mov     esi, eax
0x18000dc34  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000dc39  mov     [rbp+4Fh+lpBuffer], rax
0x18000dc3d  mov     rcx, rax
0x18000dc40  test    rax, rax
0x18000dc43  jnz     short loc_18000DC4F
0x18000dc45  mov     ebx, 8007000Eh
0x18000dc4a  jmp     loc_18000DF90
0x18000dc4f  mov     eax, [rbx+298h]
0x18000dc55  xor     r13d, r13d
0x18000dc58  mov     [rbp+4Fh+var_84], eax
0x18000dc5b  lea     rax, [rsi+rcx]
0x18000dc5f  mov     [rbp+4Fh+var_60], rax
0x18000dc63  mov     [rbp+4Fh+var_90], rax
0x18000dc67  mov     rax, [rdi]
0x18000dc6a  mov     [rbp+4Fh+var_A0], rcx
0x18000dc6e  mov     [rbp+4Fh+var_98], rcx
0x18000dc72  mov     rcx, rdi
0x18000dc75  mov     [rbp+4Fh+var_88], 1
0x18000dc7c  mov     rax, [rax+0E0h]
0x18000dc83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc88  mov     ecx, eax; unsigned __int64
0x18000dc8a  mov     [rbp+4Fh+var_C4], eax
0x18000dc8d  mov     esi, eax
0x18000dc8f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000dc94  mov     r12, rax
0x18000dc97  test    rax, rax
0x18000dc9a  jnz     short loc_18000DCA6
0x18000dc9c  mov     ebx, 8007000Eh
0x18000dca1  jmp     loc_18000DF6D
0x18000dca6  mov     eax, [rbx+298h]
0x18000dcac  lea     rdx, [rsp+120h+var_E0]
0x18000dcb1  mov     [rbp+4Fh+var_64], eax
0x18000dcb4  mov     rcx, rdi
0x18000dcb7  lea     rax, [rsi+r12]
0x18000dcbb  mov     [rbp+4Fh+var_80], r12
0x18000dcbf  mov     [rbp+4Fh+var_58], rax
0x18000dcc3  mov     [rbp+4Fh+var_70], rax
0x18000dcc7  xor     eax, eax
0x18000dcc9  mov     [rsp+120h+var_E0], ax
0x18000dcce  mov     rax, [rdi]
0x18000dcd1  mov     [rbp+4Fh+var_78], r12
0x18000dcd5  mov     [rbp+4Fh+var_68], 1
0x18000dcdc  mov     rax, [rax+80h]
0x18000dce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce8  mov     ebx, eax
0x18000dcea  test    eax, eax
0x18000dcec  js      loc_18000DF6D
0x18000dcf2  movzx   ecx, [rsp+120h+var_E0]
0x18000dcf7  mov     eax, 4
0x18000dcfc  mul     rcx
0x18000dcff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000dd06  cmovb   rax, rcx
0x18000dd0a  mov     rcx, rax; unsigned __int64
0x18000dd0d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000dd12  mov     [rsp+120h+var_D8], rax
0x18000dd17  mov     r13, rax
0x18000dd1a  test    rax, rax
0x18000dd1d  jz      loc_18000DC9C
0x18000dd23  lea     rcx, [r14+2D8h]
0x18000dd2a  mov     rax, [rcx]
0x18000dd2d  mov     rax, [rax+28h]
0x18000dd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd36  mov     ebx, eax
0x18000dd38  test    eax, eax
0x18000dd3a  js      loc_18000DF6D
0x18000dd40  xor     esi, esi
0x18000dd42  cmp     [r14+0E8h], esi
0x18000dd49  jbe     short loc_18000DD7E
0x18000dd4b  mov     edx, esi
0x18000dd4d  lea     rcx, [r14+10h]
0x18000dd51  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000dd56  mov     rdx, rax
0x18000dd59  test    rax, rax
0x18000dd5c  jz      short loc_18000DD73
0x18000dd5e  mov     rcx, [rax]
0x18000dd61  mov     rax, [rcx+38h]
0x18000dd65  mov     rcx, rdx
0x18000dd68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd6d  mov     ebx, eax
0x18000dd6f  test    eax, eax
0x18000dd71  js      short loc_18000DD7E
0x18000dd73  inc     esi
0x18000dd75  cmp     esi, [r14+0E8h]
0x18000dd7c  jb      short loc_18000DD4B
0x18000dd7e  xor     esi, esi
0x18000dd80  cmp     esi, [r14+2D0h]
0x18000dd87  jnb     loc_18000DF68
0x18000dd8d  mov     rax, [rbp+4Fh+lpBuffer]
0x18000dd91  lea     r8, [rbp+4Fh+var_A0]
0x18000dd95  mov     [rbp+4Fh+var_A0], rax
0x18000dd99  mov     edx, esi
0x18000dd9b  mov     [rbp+4Fh+var_98], rax
0x18000dd9f  mov     rcx, rdi
0x18000dda2  mov     rax, [rbp+4Fh+var_60]
0x18000dda6  mov     [rbp+4Fh+var_90], rax
0x18000ddaa  mov     rax, [rdi]
0x18000ddad  mov     rax, [rax+138h]
0x18000ddb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddb9  mov     ebx, eax
0x18000ddbb  test    eax, eax
0x18000ddbd  js      loc_18000DF68
0x18000ddc3  mov     ebx, [rbp+4Fh+nNumberOfBytesToWrite]
0x18000ddc6  lea     r9, [rsp+120h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000ddcb  mov     rdx, [rbp+4Fh+lpBuffer]; lpBuffer
0x18000ddcf  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000ddd2  mov     rcx, [rbp+4Fh+hFile]; hFile
0x18000ddd6  mov     [rsp+120h+NumberOfBytesWritten], 0
0x18000ddde  mov     [rsp+120h+lpOverlapped], 0; lpOverlapped
0x18000dde7  call    cs:__imp_WriteFile
0x18000dded  test    eax, eax
0x18000ddef  jz      loc_18000DF63
0x18000ddf5  cmp     [rsp+120h+NumberOfBytesWritten], ebx
0x18000ddf9  jb      loc_18000DF63
0x18000ddff  mov     rax, [rdi]
0x18000de02  lea     r9, [rbp+4Fh+var_CC]
0x18000de06  xor     r8d, r8d
0x18000de09  mov     [rbp+4Fh+var_CC], 0
0x18000de10  mov     edx, esi
0x18000de12  mov     rcx, rdi
0x18000de15  add     r15d, ebx
0x18000de18  mov     rax, [rax+98h]
0x18000de1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de24  mov     ebx, eax
0x18000de26  test    eax, eax
0x18000de28  js      loc_18000DF68
0x18000de2e  xor     r13d, r13d
0x18000de31  mov     [rbp+4Fh+var_BC], r13d
0x18000de35  cmp     r13d, [rbp+4Fh+var_CC]
0x18000de39  jnb     loc_18000DF5C
0x18000de3f  lea     rcx, [r14+2D8h]
0x18000de46  mov     rax, [rcx]
0x18000de49  lea     rdx, [rbp+4Fh+var_48]
0x18000de4d  mov     rax, [rax+30h]
0x18000de51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de56  mov     ebx, eax
0x18000de58  test    eax, eax
0x18000de5a  js      loc_18000DF68
0x18000de60  cmp     dword ptr [r14+0E8h], 0
0x18000de68  jbe     short loc_18000DEDC
0x18000de6a  xor     ebx, ebx
0x18000de6c  lea     rcx, [r14+10h]
0x18000de70  xor     r13d, r13d
0x18000de73  mov     [rbp+4Fh+var_C8], ebx
0x18000de76  xor     eax, eax
0x18000de78  mov     edx, eax
0x18000de7a  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000de7f  mov     r9, rax
0x18000de82  test    rax, rax
0x18000de85  jz      short loc_18000DEBE
0x18000de87  mov     rdx, [rax]
0x18000de8a  mov     rax, [rsp+120h+var_D8]
0x18000de8f  movzx   ecx, bx
0x18000de92  lea     r8, [rax+rcx*4]
0x18000de96  mov     rax, [rdx+40h]
0x18000de9a  mov     edx, esi
0x18000de9c  mov     rcx, r9
0x18000de9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dea4  mov     ebx, eax
0x18000dea6  test    eax, eax
0x18000dea8  js      loc_18000DF68
0x18000deae  mov     ebx, [rbp+4Fh+var_C8]
0x18000deb1  mov     eax, 1
0x18000deb6  add     bx, ax
0x18000deb9  mov     [rbp+4Fh+var_C8], ebx
0x18000debc  jmp     short loc_18000DEC3
0x18000debe  mov     eax, 1
0x18000dec3  add     r13w, ax
0x18000dec7  lea     rcx, [r14+10h]
0x18000decb  movzx   eax, r13w
0x18000decf  cmp     eax, [r14+0E8h]
0x18000ded6  jb      short loc_18000DE78
0x18000ded8  mov     r13d, [rbp+4Fh+var_BC]
0x18000dedc  mov     rax, [rbp+4Fh+var_58]
0x18000dee0  lea     rcx, [rbp+4Fh+var_80]
0x18000dee4  mov     [rsp+120h+var_F8], rcx
0x18000dee9  lea     r9, [rbp+4Fh+var_48+2]
0x18000deed  mov     rcx, [rsp+120h+var_D8]
0x18000def2  mov     r8d, r13d
0x18000def5  mov     [rbp+4Fh+var_70], rax
0x18000def9  mov     edx, esi
0x18000defb  mov     rax, [rdi]
0x18000defe  mov     [rsp+120h+lpOverlapped], rcx
0x18000df03  mov     rcx, rdi
0x18000df06  mov     [rbp+4Fh+var_80], r12
0x18000df0a  mov     [rbp+4Fh+var_78], r12
0x18000df0e  mov     rax, [rax+140h]
0x18000df15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df1a  mov     ebx, eax
0x18000df1c  test    eax, eax
0x18000df1e  js      short loc_18000DF68
0x18000df20  mov     r8d, [rbp+4Fh+var_C4]; nNumberOfBytesToWrite
0x18000df24  lea     r9, [rbp+4Fh+var_C0]; lpNumberOfBytesWritten
0x18000df28  mov     rcx, [rbp+4Fh+hFile]; hFile
0x18000df2c  mov     rdx, r12; lpBuffer
0x18000df2f  mov     [rbp+4Fh+var_C0], 0
0x18000df36  mov     [rsp+120h+lpOverlapped], 0; lpOverlapped
0x18000df3f  call    cs:__imp_WriteFile
0x18000df45  test    eax, eax
0x18000df47  jz      short loc_18000DF63
0x18000df49  mov     eax, [rbp+4Fh+var_C4]
0x18000df4c  cmp     [rbp+4Fh+var_C0], eax
0x18000df4f  jb      short loc_18000DF63
0x18000df51  add     r15d, eax
0x18000df54  inc     r13d
0x18000df57  jmp     loc_18000DE31
0x18000df5c  inc     esi
0x18000df5e  jmp     loc_18000DD80
0x18000df63  mov     ebx, 80004005h
0x18000df68  mov     r13, [rsp+120h+var_D8]
0x18000df6d  mov     rcx, [rbp+4Fh+lpBuffer]; void *
0x18000df71  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df76  test    r12, r12
0x18000df79  jz      short loc_18000DF83
0x18000df7b  mov     rcx, r12; void *
0x18000df7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df83  test    r13, r13
0x18000df86  jz      short loc_18000DF90
0x18000df88  mov     rcx, r13; void *
0x18000df8b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df90  mov     rcx, [rbp+4Fh+var_50]
0x18000df94  test    rcx, rcx
0x18000df97  jz      short loc_18000DFA4
0x18000df99  xor     eax, eax
0x18000df9b  test    ebx, ebx
0x18000df9d  cmovs   r15d, eax
0x18000dfa1  mov     [rcx], r15d
0x18000dfa4  mov     eax, ebx
0x18000dfa6  jmp     short loc_18000DFAD
0x18000dfa8  mov     eax, 80070057h
0x18000dfad  mov     rcx, [rbp+4Fh+var_38]
0x18000dfb1  xor     rcx, rsp; StackCookie
0x18000dfb4  call    __security_check_cookie
0x18000dfb9  mov     rbx, [rsp+120h+arg_10]
0x18000dfc1  add     rsp, 0F0h
0x18000dfc8  pop     r15
0x18000dfca  pop     r14
0x18000dfcc  pop     r13
0x18000dfce  pop     r12
0x18000dfd0  pop     rdi
0x18000dfd1  pop     rsi
0x18000dfd2  pop     rbp
0x18000dfd3  retn
```
