# CDVRSource::Read(void *,ulong,ulong *)

- ea: `0x1800067e0`
- end: `0x180006ea0`
- name: `?Read@CDVRSource@@UEAAJPEAXKPEAK@Z`
- size: `1728`
- prototype: `__int64 __fastcall(CDVRSource *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1800015f0`
- `0x1800067e0`
- `0x180006ea8`
- `0x18002a070`
- `0x18002b010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180006975`
- `KERNEL32!ResetEvent` at `0x180006975`
- `KERNEL32!WaitForMultipleObjects` at `0x180006a3c`
- `KERNEL32!WaitForMultipleObjects` at `0x180006a3c`
- `KERNEL32!SetFilePointerEx` at `0x180006dec`
- `KERNEL32!SetFilePointerEx` at `0x180006dec`
- `KERNEL32!GetLastError` at `0x180006a49`
- `KERNEL32!GetLastError` at `0x180006a49`
- `KERNEL32!ReleaseMutex` at `0x1800069e4`
- `KERNEL32!ReleaseMutex` at `0x180006acc`
- `KERNEL32!ReleaseMutex` at `0x180006dc8`
- `KERNEL32!ReleaseMutex` at `0x180006e8a`
- `KERNEL32!ReleaseMutex` at `0x18002a640`
- `KERNEL32!ReleaseMutex` at `0x1800069e4`
- `KERNEL32!ReleaseMutex` at `0x180006acc`
- `KERNEL32!ReleaseMutex` at `0x180006dc8`
- `KERNEL32!ReleaseMutex` at `0x180006e8a`
- `KERNEL32!ReleaseMutex` at `0x18002a640`
- `KERNEL32!LeaveCriticalSection` at `0x180006e93`
- `KERNEL32!LeaveCriticalSection` at `0x18002a652`
- `KERNEL32!LeaveCriticalSection` at `0x180006e93`
- `KERNEL32!LeaveCriticalSection` at `0x18002a652`
- `KERNEL32!EnterCriticalSection` at `0x180006877`
- `KERNEL32!EnterCriticalSection` at `0x180006877`
- `KERNEL32!ReadFile` at `0x180006e1a`
- `KERNEL32!ReadFile` at `0x180006e1a`

## pseudocode

```c
__int64 __fastcall CDVRSource::Read(HANDLE *this, char *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int *v4; // r14
  __int64 v5; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // r15
  signed int v10; // ebx
  char *v11; // rax
  char *v12; // r14
  char *v13; // r12
  int v14; // r13d
  unsigned __int64 v15; // r15
  _QWORD *v16; // rax
  int v17; // ebx
  HANDLE v18; // rcx
  DWORD v19; // r12d
  signed int LastError; // eax
  _QWORD *v21; // rax
  char *v22; // r14
  __int64 i; // rbx
  _DWORD *v24; // r11
  unsigned __int64 v25; // rcx
  _BYTE *v26; // r9
  unsigned __int64 v27; // r10
  unsigned __int64 v28; // r8
  int v29; // esi
  __int64 v30; // rdx
  _QWORD *v31; // r9
  unsigned __int64 v32; // rax
  HANDLE v33; // rcx
  HANDLE v34; // r10
  __int64 v35; // rdx
  unsigned __int64 v36; // rbx
  char *v37; // r15
  unsigned __int64 v38; // rbx
  unsigned int v39; // ecx
  _QWORD *v40; // r8
  unsigned __int64 v41; // rdx
  HANDLE v42; // rcx
  __int64 v43; // rbx
  __int64 v44; // rcx
  char *v45; // r13
  unsigned int v46; // r14d
  unsigned __int64 v47; // r9
  __int64 v48; // r10
  char *v49; // rdx
  DWORD v50; // esi
  unsigned int v51; // ecx
  unsigned int v52; // [rsp+34h] [rbp-C4h] BYREF
  int v53; // [rsp+38h] [rbp-C0h] BYREF
  unsigned int *v54; // [rsp+40h] [rbp-B8h]
  int v55; // [rsp+48h] [rbp-B0h]
  int v56; // [rsp+4Ch] [rbp-ACh]
  int v57; // [rsp+50h] [rbp-A8h]
  DWORD NumberOfBytesRead; // [rsp+54h] [rbp-A4h] BYREF
  int v59; // [rsp+58h] [rbp-A0h]
  unsigned int v60; // [rsp+5Ch] [rbp-9Ch]
  char *v61; // [rsp+60h] [rbp-98h]
  char *v62; // [rsp+68h] [rbp-90h]
  CDVRSource *v63; // [rsp+70h] [rbp-88h]
  void *v64; // [rsp+78h] [rbp-80h]
  unsigned __int64 v65; // [rsp+80h] [rbp-78h]
  char *v66; // [rsp+88h] [rbp-70h]
  unsigned int *v67; // [rsp+90h] [rbp-68h]
  char *v68; // [rsp+98h] [rbp-60h]
  HANDLE Handles[2]; // [rsp+A0h] [rbp-58h] BYREF
  HANDLE v70; // [rsp+B0h] [rbp-48h]

  v4 = a4;
  v54 = a4;
  v5 = a3;
  v64 = a2;
  v63 = (CDVRSource *)this;
  v67 = a4;
  if ( !a2 )
    return 2147500035LL;
  v53 = 0;
  v52 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)(this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 24));
  v61 = 0;
  if ( *((_DWORD *)this + 46) != 1 )
  {
    v10 = -2147418113;
    goto LABEL_89;
  }
  if ( !*((_DWORD *)this + 44) )
  {
    v10 = CDVRSource::ReadBytesLocked((CDVRSource *)this, a2, v5, &v52);
    goto LABEL_89;
  }
  v11 = (char *)this[3];
  v12 = &v11[v5];
  v61 = &v11[v5];
  v13 = (char *)this[4];
  if ( v11 < v13 )
  {
    v55 = v5;
    v66 = &v11[v5];
    v56 = 0;
    v14 = 0;
    v57 = 0;
    v15 = 0;
    v65 = 0;
    if ( v12 <= v13 )
    {
      v13 = &v11[v5];
    }
    else
    {
      LODWORD(v5) = (_DWORD)v13 - (_DWORD)v11;
      v55 = (_DWORD)v13 - (_DWORD)v11;
      v12 = v13;
      v66 = v13;
    }
    v10 = (*((__int64 (__fastcall **)(HANDLE *, int *))*this + 16))(this, &v53);
    if ( v10 < 0 )
      goto LABEL_12;
    v16 = this[8];
    if ( v16[3] < (unsigned __int64)v13 )
    {
      if ( *((_DWORD *)v16 + 102) )
      {
        v56 = 1;
        ResetEvent(this[14]);
        *((_QWORD *)this[8] + 5 * *((unsigned int *)this + 42) + 8) = v12;
        *((_DWORD *)this[8] + 10 * *((unsigned int *)this + 42) + 19) = 2;
      }
      else
      {
        v15 = v16[3];
        v65 = v15;
        v14 = 1;
        v57 = 1;
      }
    }
    v17 = v56;
    if ( v56 )
    {
      v18 = this[9];
      if ( v18 )
        (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v18 + 24LL))(v18);
    }
    if ( v53 )
    {
      ReleaseMutex(this[13]);
      v53 = 0;
    }
    if ( v17 )
    {
      Handles[0] = this[15];
      Handles[1] = this[14];
      v70 = this[16];
      v19 = WaitForMultipleObjects((v70 != 0) + 2, Handles, 0, 0xFFFFFFFF);
      if ( v19 == -1 )
      {
LABEL_24:
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_87;
      }
      if ( !v19 )
      {
        v10 = -2147023673;
LABEL_87:
        v9 = (struct _RTL_CRITICAL_SECTION *)(this + 24);
        goto LABEL_88;
      }
      v10 = (*((__int64 (__fastcall **)(HANDLE *, int *))*this + 16))(this, &v53);
      if ( v10 < 0 )
      {
LABEL_12:
        v4 = v54;
        v9 = (struct _RTL_CRITICAL_SECTION *)(this + 24);
        goto LABEL_89;
      }
      v21 = this[8];
      if ( !*((_DWORD *)v21 + 102) || v19 == 2 )
      {
        v15 = v21[3];
        v65 = v15;
        v14 = 1;
        v57 = 1;
      }
      if ( v53 )
      {
        ReleaseMutex(this[13]);
        v53 = 0;
      }
    }
    if ( v14 )
    {
      if ( (unsigned __int64)this[3] >= v15 )
      {
        v55 = 0;
LABEL_40:
        v52 = 0;
LABEL_42:
        v10 = -2147024858;
        goto LABEL_87;
      }
      if ( (unsigned __int64)v12 > v15 )
      {
        LODWORD(v5) = v15 - (_DWORD)v12 + v5;
        v55 = v5;
        v66 = (char *)v15;
      }
    }
    if ( !(_DWORD)v5 )
      goto LABEL_40;
    v22 = (char *)v64;
    CDVRSource::ReadBytesLocked((CDVRSource *)this, v64, v5, &v52);
    if ( !v52 )
      goto LABEL_42;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v59 = i;
      if ( (unsigned int)i >= 4 )
        break;
      v24 = this[8];
      v25 = (unsigned int)v24[3 * i + 107];
      v26 = this[3];
      if ( (unsigned __int64)v26 > v25 )
        break;
      v27 = (unsigned int)v24[3 * i + 106];
      v28 = (unsigned __int64)&v26[v52];
      if ( v28 > v27 )
      {
        v29 = v24[3 * i + 106];
        v64 = (void *)(unsigned int)v24[3 * i + 107];
        v30 = (unsigned int)v24[3 * i + 108];
        if ( (unsigned __int64)v26 > v27 )
        {
          v29 = (int)v26;
          v30 = (unsigned int)(*((_DWORD *)this + 6) + v30 - v27);
          v27 = (unsigned __int64)v26;
        }
        if ( v28 <= v25 )
        {
          LODWORD(v25) = v28 - 1;
          v64 = (void *)(v28 - 1);
        }
        memcpy_0((void *)(v27 + v22 - v26), (char *)v24 + v30 + 472, (unsigned int)(v25 - v29 + 1));
      }
    }
    goto LABEL_86;
  }
  if ( v12 >= v11 || (v12 = (char *)this[5], v5 = (unsigned int)((_DWORD)v12 - (_DWORD)v11), v61 = v12, (_DWORD)v5) )
  {
    v10 = (*((__int64 (__fastcall **)(HANDLE *, int *))*this + 16))(this, &v53);
    if ( v10 < 0 )
    {
      v4 = v54;
      goto LABEL_89;
    }
    v31 = this[8];
    v32 = v31[7];
    v33 = this[3];
    if ( (unsigned __int64)v33 < v32 )
    {
      if ( (unsigned __int64)v12 > v32 )
      {
        v5 = (unsigned int)(v32 - (_DWORD)v33);
        v61 = (char *)v31[7];
      }
      v34 = this[4];
      v35 = *((unsigned int *)v31 + 97);
      v36 = (unsigned __int64)v34 + (unsigned int)(*((_DWORD *)v31 + 98) - v35);
      if ( v36 != v31[6] )
      {
        v37 = a2;
        v68 = a2;
        if ( (unsigned __int64)v33 < v36 )
        {
          v38 = v36 - (_QWORD)v33;
          if ( (unsigned int)v5 <= v38 )
            LODWORD(v38) = v5;
          memcpy_0(&a2[v52], (char *)v31 + v35 - (_QWORD)v34 + (_QWORD)v33, (unsigned int)v38);
          v39 = v38 + v52;
          v52 = v39;
          if ( v39 == (_DWORD)v5 )
            goto LABEL_86;
          v37 = &a2[v39];
          v68 = v37;
        }
        v40 = this[8];
        v41 = v40[6];
        v42 = this[3];
        if ( (unsigned __int64)v42 + v5 <= v41 )
          goto LABEL_79;
        if ( (unsigned __int64)v42 < v41 )
        {
          v43 = (unsigned int)(v5 + (_DWORD)v42 - v41);
          v44 = 0;
        }
        else
        {
          v43 = (unsigned int)v5 - v52;
          v44 = (__int64)v42 - v41;
        }
        v45 = &a2[(unsigned int)v5 - (unsigned __int64)(unsigned int)v43];
        v46 = v43;
        v60 = v43;
        v62 = 0;
        v47 = *((unsigned int *)v40 + 100);
        v48 = *((unsigned int *)v40 + 99);
        if ( v48 + v44 < v47 )
        {
          v49 = (char *)v40 + v48 + v44;
          v62 = v49;
          if ( v44 + v48 + v43 > v47 )
          {
            v46 = v47 - v44 - v48;
            v60 = v46;
          }
        }
        else
        {
          v49 = (char *)v40 + v44 + *((unsigned int *)v40 + 98) - (unsigned __int64)(unsigned int)(v47 - v48);
          v62 = v49;
        }
        memcpy_0(v45, v49, v46);
        if ( v46 != (_DWORD)v43 )
        {
          v62 = (char *)this[8] + *((unsigned int *)this[8] + 98);
          memcpy_0(&v45[v46], v62, (unsigned int)v43 - v46);
        }
        v52 += v43;
        if ( v52 != (_DWORD)v5 )
        {
LABEL_79:
          if ( v53 )
          {
            ReleaseMutex(this[13]);
            v53 = 0;
          }
          v50 = v5 - v52;
          if ( !SetFilePointerEx(this[12], (LARGE_INTEGER)((_BYTE *)this[3] - (_BYTE *)this[4]), 0, 0) )
            goto LABEL_24;
          NumberOfBytesRead = 0;
          if ( !ReadFile(this[12], v37, v50, &NumberOfBytesRead, 0) )
            goto LABEL_24;
          if ( NumberOfBytesRead < v50 )
          {
            v10 = -2147467259;
            goto LABEL_87;
          }
          v52 += NumberOfBytesRead;
        }
LABEL_86:
        v10 = 0;
        goto LABEL_87;
      }
      memcpy_0(&a2[v52], (char *)v31 + v35 - (_QWORD)v34 + (_QWORD)v33, (unsigned int)v5);
      v52 += v5;
    }
  }
  v10 = 0;
LABEL_88:
  v4 = v54;
LABEL_89:
  if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024858 )
  {
    v51 = v52;
    this[3] = (char *)this[3] + v52;
    if ( v4 )
      *v4 = v51;
  }
  else if ( v4 )
  {
    *v4 = 0;
  }
  if ( v53 )
    ReleaseMutex(this[13]);
  LeaveCriticalSection(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800067e0  push    rbx
0x1800067e2  push    rsi
0x1800067e3  push    rdi
0x1800067e4  push    r12
0x1800067e6  push    r13
0x1800067e8  push    r14
0x1800067ea  push    r15
0x1800067ec  sub     rsp, 0C0h
0x1800067f3  mov     rax, cs:__security_cookie
0x1800067fa  xor     rax, rsp
0x1800067fd  mov     [rsp+0F8h+var_40], rax
0x180006805  mov     r14, r9
0x180006808  mov     [rsp+0F8h+var_B8], r9
0x18000680d  mov     esi, r8d
0x180006810  mov     r13, rdx
0x180006813  mov     [rsp+0F8h+var_80], rdx
0x180006818  mov     rdi, rcx
0x18000681b  mov     [rsp+0F8h+var_88], rcx
0x180006820  mov     [rsp+0F8h+var_68], r9
0x180006828  test    rdx, rdx
0x18000682b  jnz     short loc_180006855
0x18000682d  mov     eax, 80004003h
0x180006832  mov     rcx, [rsp+0F8h+var_40]
0x18000683a  xor     rcx, rsp; StackCookie
0x18000683d  call    __security_check_cookie
0x180006842  add     rsp, 0C0h
0x180006849  pop     r15
0x18000684b  pop     r14
0x18000684d  pop     r13
0x18000684f  pop     r12
0x180006851  pop     rdi
0x180006852  pop     rsi
0x180006853  pop     rbx
0x180006854  retn
0x180006855  mov     [rsp+0F8h+var_C0], 0
0x18000685d  mov     [rsp+0F8h+var_C8], 0
0x180006865  mov     [rsp+0F8h+var_C4], 0
0x18000686d  lea     r15, [rcx+0C0h]
0x180006874  mov     rcx, r15; lpCriticalSection
0x180006877  call    cs:__imp_EnterCriticalSection
0x18000687d  nop
0x18000687e  mov     [rsp+0F8h+var_98], 0
0x180006887  cmp     dword ptr [rdi+0B8h], 1
0x18000688e  jz      short loc_18000689A
0x180006890  mov     ebx, 8000FFFFh
0x180006895  jmp     loc_180006E49
0x18000689a  cmp     dword ptr [rdi+0B0h], 0
0x1800068a1  jnz     short loc_1800068C1
0x1800068a3  lea     r9, [rsp+0F8h+var_C4]; unsigned int *
0x1800068a8  mov     r8d, esi; unsigned int
0x1800068ab  mov     rdx, r13; void *
0x1800068ae  mov     rcx, rdi; this
0x1800068b1  call    ?ReadBytesLocked@CDVRSource@@IEAAJPEAXKPEAK@Z; CDVRSource::ReadBytesLocked(void *,ulong,ulong *)
0x1800068b6  mov     ebx, eax
0x1800068b8  mov     [rsp+0F8h+var_C8], eax
0x1800068bc  jmp     loc_180006E4D
0x1800068c1  mov     rax, [rdi+18h]
0x1800068c5  lea     r14, [rax+rsi]
0x1800068c9  mov     [rsp+0F8h+var_98], r14
0x1800068ce  mov     r12, [rdi+20h]
0x1800068d2  cmp     rax, r12
0x1800068d5  jnb     loc_180006BDE
0x1800068db  mov     [rsp+0F8h+var_B0], esi
0x1800068df  mov     [rsp+0F8h+var_70], r14
0x1800068e7  mov     [rsp+0F8h+var_AC], 0
0x1800068ef  xor     r13d, r13d
0x1800068f2  mov     [rsp+0F8h+var_A8], r13d
0x1800068f7  xor     r15d, r15d
0x1800068fa  mov     [rsp+0F8h+var_78], r15
0x180006902  cmp     r14, r12
0x180006905  jbe     short loc_18000691E
0x180006907  sub     esi, r14d
0x18000690a  add     esi, r12d
0x18000690d  mov     [rsp+0F8h+var_B0], esi
0x180006911  mov     r14, r12
0x180006914  mov     [rsp+0F8h+var_70], r12
0x18000691c  jmp     short loc_180006921
0x18000691e  mov     r12, r14
0x180006921  mov     rax, [rdi]
0x180006924  lea     rdx, [rsp+0F8h+var_C0]
0x180006929  mov     rcx, rdi
0x18000692c  mov     rax, [rax+80h]
0x180006933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006938  mov     ebx, eax
0x18000693a  test    eax, eax
0x18000693c  jns     short loc_180006953
0x18000693e  mov     [rsp+0F8h+var_C8], eax
0x180006942  mov     r14, [rsp+0F8h+var_B8]
0x180006947  lea     r15, [rdi+0C0h]
0x18000694e  jmp     loc_180006E4D
0x180006953  mov     rax, [rdi+40h]
0x180006957  mov     rcx, [rax+18h]
0x18000695b  cmp     rcx, r12
0x18000695e  jnb     short loc_1800069BC
0x180006960  cmp     [rax+198h], r13d
0x180006967  jz      short loc_1800069A6
0x180006969  mov     [rsp+0F8h+var_AC], 1
0x180006971  mov     rcx, [rdi+70h]; hEvent
0x180006975  call    cs:__imp_ResetEvent
0x18000697b  mov     eax, [rdi+0A8h]
0x180006981  lea     rcx, [rax+rax*4]
0x180006985  mov     rax, [rdi+40h]
0x180006989  mov     [rax+rcx*8+40h], r14
0x18000698e  mov     eax, [rdi+0A8h]
0x180006994  lea     rcx, [rax+rax*4]
0x180006998  mov     rax, [rdi+40h]
0x18000699c  mov     dword ptr [rax+rcx*8+4Ch], 2
0x1800069a4  jmp     short loc_1800069BC
0x1800069a6  mov     r15, rcx
0x1800069a9  mov     [rsp+0F8h+var_78], rcx
0x1800069b1  mov     r13d, 1
0x1800069b7  mov     [rsp+0F8h+var_A8], r13d
0x1800069bc  mov     ebx, [rsp+0F8h+var_AC]
0x1800069c0  test    ebx, ebx
0x1800069c2  jz      short loc_1800069D9
0x1800069c4  mov     rcx, [rdi+48h]
0x1800069c8  test    rcx, rcx
0x1800069cb  jz      short loc_1800069D9
0x1800069cd  mov     rax, [rcx]
0x1800069d0  mov     rax, [rax+18h]
0x1800069d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d9  cmp     [rsp+0F8h+var_C0], 0
0x1800069de  jz      short loc_1800069F2
0x1800069e0  mov     rcx, [rdi+68h]; hMutex
0x1800069e4  call    cs:__imp_ReleaseMutex
0x1800069ea  mov     [rsp+0F8h+var_C0], 0
0x1800069f2  test    ebx, ebx
0x1800069f4  jz      loc_180006ADA
0x1800069fa  mov     rax, [rdi+78h]
0x1800069fe  mov     [rsp+0F8h+Handles], rax
0x180006a06  mov     rax, [rdi+70h]
0x180006a0a  mov     [rsp+0F8h+var_50], rax
0x180006a12  mov     rax, [rdi+80h]
0x180006a19  mov     [rsp+0F8h+var_48], rax
0x180006a21  neg     rax
0x180006a24  sbb     ecx, ecx
0x180006a26  neg     ecx
0x180006a28  add     ecx, 2; nCount
0x180006a2b  or      ebx, 0FFFFFFFFh
0x180006a2e  mov     r9d, ebx; dwMilliseconds
0x180006a31  xor     r8d, r8d; bWaitAll
0x180006a34  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180006a3c  call    cs:__imp_WaitForMultipleObjects
0x180006a42  mov     r12d, eax
0x180006a45  cmp     eax, ebx
0x180006a47  jnz     short loc_180006A67
0x180006a49  call    cs:__imp_GetLastError
0x180006a4f  mov     ebx, eax
0x180006a51  test    eax, eax
0x180006a53  jle     loc_180006E3D
0x180006a59  movzx   ebx, ax
0x180006a5c  or      ebx, 80070000h
0x180006a62  jmp     loc_180006E3D
0x180006a67  test    r12d, r12d
0x180006a6a  jnz     short loc_180006A76
0x180006a6c  mov     ebx, 800704C7h
0x180006a71  jmp     loc_180006E3D
0x180006a76  mov     rax, [rdi]
0x180006a79  lea     rdx, [rsp+0F8h+var_C0]
0x180006a7e  mov     rcx, rdi
0x180006a81  mov     rax, [rax+80h]
0x180006a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a8d  mov     ebx, eax
0x180006a8f  test    eax, eax
0x180006a91  js      loc_18000693E
0x180006a97  mov     rax, [rdi+40h]
0x180006a9b  cmp     dword ptr [rax+198h], 0
0x180006aa2  jz      short loc_180006AAA
0x180006aa4  cmp     r12d, 2
0x180006aa8  jnz     short loc_180006AC1
0x180006aaa  mov     r15, [rax+18h]
0x180006aae  mov     [rsp+0F8h+var_78], r15
0x180006ab6  mov     r13d, 1
0x180006abc  mov     [rsp+0F8h+var_A8], r13d
0x180006ac1  cmp     [rsp+0F8h+var_C0], 0
0x180006ac6  jz      short loc_180006ADA
0x180006ac8  mov     rcx, [rdi+68h]; hMutex
0x180006acc  call    cs:__imp_ReleaseMutex
0x180006ad2  mov     [rsp+0F8h+var_C0], 0
0x180006ada  test    r13d, r13d
0x180006add  jz      short loc_180006B08
0x180006adf  cmp     [rdi+18h], r15
0x180006ae3  jb      short loc_180006AEF
0x180006ae5  mov     [rsp+0F8h+var_B0], 0
0x180006aed  jmp     short loc_180006B0C
0x180006aef  cmp     r14, r15
0x180006af2  jbe     short loc_180006B08
0x180006af4  mov     eax, r15d
0x180006af7  sub     eax, r14d
0x180006afa  add     esi, eax
0x180006afc  mov     [rsp+0F8h+var_B0], esi
0x180006b00  mov     [rsp+0F8h+var_70], r15
0x180006b08  test    esi, esi
0x180006b0a  jnz     short loc_180006B16
0x180006b0c  mov     [rsp+0F8h+var_C4], 0
0x180006b14  jmp     short loc_180006B39
0x180006b16  lea     r9, [rsp+0F8h+var_C4]; unsigned int *
0x180006b1b  mov     r8d, esi; unsigned int
0x180006b1e  mov     r14, [rsp+0F8h+var_80]
0x180006b23  mov     rdx, r14; void *
0x180006b26  mov     rcx, rdi; this
0x180006b29  call    ?ReadBytesLocked@CDVRSource@@IEAAJPEAXKPEAK@Z; CDVRSource::ReadBytesLocked(void *,ulong,ulong *)
0x180006b2e  mov     [rsp+0F8h+var_C8], eax
0x180006b32  cmp     [rsp+0F8h+var_C4], 0
0x180006b37  jnz     short loc_180006B43
0x180006b39  mov     ebx, 80070026h
0x180006b3e  jmp     loc_180006E3D
0x180006b43  xor     ebx, ebx
0x180006b45  mov     [rsp+0F8h+var_A0], ebx
0x180006b49  cmp     ebx, 4
0x180006b4c  jnb     loc_180006E3B
0x180006b52  mov     r11, [rdi+40h]
0x180006b56  lea     rax, [rbx+rbx*2]
0x180006b5a  mov     ecx, [r11+rax*4+1ACh]
0x180006b62  mov     r9, [rdi+18h]
0x180006b66  cmp     r9, rcx
0x180006b69  ja      loc_180006E3B
0x180006b6f  mov     r10d, [r11+rax*4+1A8h]
0x180006b77  mov     r8d, [rsp+0F8h+var_C4]
0x180006b7c  add     r8, r9
0x180006b7f  cmp     r8, r10
0x180006b82  ja      short loc_180006B86
0x180006b84  jmp     short loc_180006BD7
0x180006b86  mov     esi, r10d
0x180006b89  mov     [rsp+0F8h+var_80], rcx
0x180006b8e  lea     rax, [rbx+rbx*2]
0x180006b92  mov     edx, [r11+rax*4+1B0h]
0x180006b9a  cmp     r9, r10
0x180006b9d  jbe     short loc_180006BAB
0x180006b9f  mov     esi, r9d
0x180006ba2  sub     edx, r10d
0x180006ba5  add     edx, [rdi+18h]
0x180006ba8  mov     r10, r9
0x180006bab  cmp     r8, rcx
0x180006bae  ja      short loc_180006BB9
0x180006bb0  lea     rcx, [r8-1]
0x180006bb4  mov     [rsp+0F8h+var_80], rcx
0x180006bb9  sub     ecx, esi
0x180006bbb  lea     r8d, [rcx+1]; Size
0x180006bbf  add     r11, 1D8h
0x180006bc6  add     rdx, r11; Src
0x180006bc9  mov     rcx, r14
0x180006bcc  sub     rcx, r9
0x180006bcf  add     rcx, r10; void *
0x180006bd2  call    memcpy_0
0x180006bd7  inc     ebx
0x180006bd9  jmp     loc_180006B45
0x180006bde  cmp     r14, rax
0x180006be1  jnb     short loc_180006BFA
0x180006be3  mov     r14, [rdi+28h]
0x180006be7  mov     esi, r14d
0x180006bea  sub     esi, eax
0x180006bec  mov     [rsp+0F8h+var_98], r14
0x180006bf1  jnz     short loc_180006BFA
0x180006bf3  xor     ebx, ebx
0x180006bf5  jmp     loc_180006E44
0x180006bfa  mov     rax, [rdi]
0x180006bfd  lea     rdx, [rsp+0F8h+var_C0]
0x180006c02  mov     rcx, rdi
0x180006c05  mov     rax, [rax+80h]
0x180006c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c11  mov     ebx, eax
0x180006c13  test    eax, eax
0x180006c15  jns     short loc_180006C25
0x180006c17  mov     [rsp+0F8h+var_C8], eax
0x180006c1b  mov     r14, [rsp+0F8h+var_B8]
0x180006c20  jmp     loc_180006E4D
0x180006c25  mov     r9, [rdi+40h]
0x180006c29  mov     rax, [r9+38h]
0x180006c2d  mov     rcx, [rdi+18h]
0x180006c31  cmp     rcx, rax
0x180006c34  jnb     short loc_180006BF3
0x180006c36  cmp     r14, rax
0x180006c39  jbe     short loc_180006C44
0x180006c3b  mov     esi, eax
0x180006c3d  sub     esi, ecx
0x180006c3f  mov     [rsp+0F8h+var_98], rax
0x180006c44  mov     r10, [rdi+20h]
0x180006c48  mov     edx, [r9+184h]
0x180006c4f  mov     ebx, [r9+188h]
0x180006c56  sub     ebx, edx
0x180006c58  add     rbx, r10
0x180006c5b  mov     r14d, esi
0x180006c5e  cmp     rbx, [r9+30h]
0x180006c62  jnz     short loc_180006C85
0x180006c64  sub     rdx, r10
0x180006c67  add     rdx, r9
0x180006c6a  add     rdx, rcx; Src
0x180006c6d  mov     ecx, [rsp+0F8h+var_C4]
0x180006c71  add     rcx, r13; void *
0x180006c74  mov     r8d, r14d; Size
0x180006c77  call    memcpy_0
0x180006c7c  add     [rsp+0F8h+var_C4], esi
0x180006c80  jmp     loc_180006BF3
0x180006c85  mov     r15, r13
0x180006c88  mov     [rsp+0F8h+var_60], r13
0x180006c90  cmp     rcx, rbx
0x180006c93  jnb     short loc_180006CD7
0x180006c95  sub     rbx, rcx
0x180006c98  cmp     r14, rbx
  ... truncated ...
```
