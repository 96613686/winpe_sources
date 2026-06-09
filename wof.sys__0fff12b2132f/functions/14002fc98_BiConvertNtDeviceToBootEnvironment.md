# BiConvertNtDeviceToBootEnvironment

- ea: `0x14002fc98`
- end: `0x140030434`
- name: `BiConvertNtDeviceToBootEnvironment`
- size: `1948`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002b43c`
- `0x14002fc98`
- `0x14003043c`
- `0x1400306fc`

## callees

- `0x14000da0d`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002fc98`
- `0x14003043c`
- `0x1400306fc`
- `0x1400314d0`
- `0x140031a40`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x140030364`
- `ntoskrnl!wcscpy_s` at `0x140030364`
- `ntoskrnl!ExAllocatePool2` at `0x14002fd32`
- `ntoskrnl!ExAllocatePool2` at `0x14002fdb4`
- `ntoskrnl!ExAllocatePool2` at `0x14002fe62`
- `ntoskrnl!ExAllocatePool2` at `0x14002ff17`
- `ntoskrnl!ExAllocatePool2` at `0x14002ff68`
- `ntoskrnl!ExAllocatePool2` at `0x14002ffeb`
- `ntoskrnl!ExAllocatePool2` at `0x140030044`
- `ntoskrnl!ExAllocatePool2` at `0x1400300c2`
- `ntoskrnl!ExAllocatePool2` at `0x140030137`
- `ntoskrnl!ExAllocatePool2` at `0x1400302ee`
- `ntoskrnl!ExAllocatePool2` at `0x14002fd32`
- `ntoskrnl!ExAllocatePool2` at `0x14002fdb4`
- `ntoskrnl!ExAllocatePool2` at `0x14002fe62`
- `ntoskrnl!ExAllocatePool2` at `0x14002ff17`
- `ntoskrnl!ExAllocatePool2` at `0x14002ff68`
- `ntoskrnl!ExAllocatePool2` at `0x14002ffeb`
- `ntoskrnl!ExAllocatePool2` at `0x140030044`
- `ntoskrnl!ExAllocatePool2` at `0x1400300c2`
- `ntoskrnl!ExAllocatePool2` at `0x140030137`
- `ntoskrnl!ExAllocatePool2` at `0x1400302ee`
- `ntoskrnl!strcpy_s` at `0x14003017d`
- `ntoskrnl!strcpy_s` at `0x14003017d`

## pseudocode

```c
__int64 BiConvertNtDeviceToBootEnvironment(__int64 a1, unsigned int a2, unsigned int a3, ...)
{
  unsigned int v3; // eax
  _QWORD *v4; // r12
  char *v7; // rdi
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  char *v13; // rax
  __int64 v14; // rax
  int v15; // ebx
  unsigned int *v16; // rbx
  unsigned int v17; // esi
  char *v18; // rax
  __int64 v19; // rax
  unsigned int v20; // esi
  char *v21; // rax
  int v22; // eax
  char *v23; // rax
  char *v24; // rax
  __int128 v25; // xmm0
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  char *v30; // rax
  char *v31; // rax
  char *Pool2; // rax
  __int64 v33; // rbx
  char *v34; // rax
  __int64 v35; // rax
  int v36; // ecx
  unsigned int v37; // r13d
  unsigned int v38; // ebx
  _DWORD *v39; // r15
  int v40; // eax
  __int64 v41; // rcx
  const WCHAR *v42; // rdx
  unsigned int v43; // eax
  int v44; // ecx
  ULONG *PartitionVhdFilePath; // rax
  unsigned int v46; // r15d
  unsigned int v47; // r14d
  int v48; // eax
  __int64 v49; // rbx
  __int64 v50; // rax
  char *v51; // rax
  int v52; // eax
  __int64 v53; // rdx
  char *v54; // rdx
  int v55; // eax
  __int64 result; // rax
  PVOID P; // [rsp+30h] [rbp-10h] BYREF
  char *v58; // [rsp+38h] [rbp-8h] BYREF
  int v59; // [rsp+80h] [rbp+40h] BYREF
  void *Src; // [rsp+98h] [rbp+58h] BYREF
  va_list Srca; // [rsp+98h] [rbp+58h]
  va_list va1; // [rsp+A0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(Srca, a3);
  Src = va_arg(va1, void *);
  v3 = *(_DWORD *)a1;
  v59 = 0;
  v4 = Src;
  P = 0;
  v58 = 0;
  v7 = 0;
  if ( v3 > 7 )
  {
    v26 = v3 - 8;
    if ( v26 )
    {
      v27 = v26 - 1;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( !v28 )
        {
          if ( a2 >= 0x28
            && *(_QWORD *)(a1 + 20) == CompositeDeviceSignature
            && *(_QWORD *)(a1 + 28) == 0x526C65784171869ELL )
          {
            Pool2 = (char *)ExAllocatePool2(258, 72, 1262764866);
            v7 = Pool2;
            if ( Pool2 )
            {
              memset(Pool2, 0, 0x48u);
              *(_DWORD *)v7 = 10;
              *((_DWORD *)v7 + 2) = 72;
              *((_DWORD *)v7 + 1) = 1;
              *((_OWORD *)v7 + 1) = *(_OWORD *)(a1 + 20);
              *((_DWORD *)v7 + 8) = *(_DWORD *)(a1 + 36);
              goto LABEL_108;
            }
            goto LABEL_30;
          }
          goto LABEL_111;
        }
        v29 = v28 - 1;
        if ( v29 )
        {
          if ( v29 == 2 && a2 >= 0x18 )
          {
            v30 = (char *)ExAllocatePool2(258, 72, 1262764866);
            v7 = v30;
            if ( v30 )
            {
              memset(v30, 0, 0x48u);
              *(_DWORD *)v7 = 0;
              *((_DWORD *)v7 + 2) = 72;
              *((_DWORD *)v7 + 4) = 0;
              *((_DWORD *)v7 + 5) = 2;
              *((_DWORD *)v7 + 6) = *(_DWORD *)(a1 + 20);
              goto LABEL_108;
            }
            goto LABEL_30;
          }
          goto LABEL_111;
        }
        if ( a2 < 0x28 )
          goto LABEL_111;
        v31 = (char *)ExAllocatePool2(258, 72, 1262764866);
        v7 = v31;
        if ( !v31 )
          goto LABEL_30;
        memset(v31, 0, 0x48u);
        *(_DWORD *)v7 = 11;
        *((_DWORD *)v7 + 2) = 72;
        *((_DWORD *)v7 + 1) = 1;
        *((_DWORD *)v7 + 4) = *(_DWORD *)(a1 + 20);
        v25 = *(_OWORD *)(a1 + 24);
LABEL_35:
        *((_OWORD *)v7 + 2) = v25;
        goto LABEL_108;
      }
      if ( a2 < 0x15 )
        goto LABEL_111;
      v33 = -1;
      do
        ++v33;
      while ( *(_BYTE *)(a1 + v33 + 20) );
      v34 = (char *)ExAllocatePool2(258, (unsigned int)(v33 + 21), 1262764866);
      v7 = v34;
      if ( v34 )
      {
        memset(v34, 0, (unsigned int)(v33 + 21));
        *(_DWORD *)v7 = 9;
        *((_DWORD *)v7 + 1) = 32;
        *((_DWORD *)v7 + 2) = v33 + 21;
        *((_DWORD *)v7 + 4) = v33 + 1;
        strcpy_s(v7 + 20, (unsigned int)(v33 + 1), (const char *)(a1 + 20));
        goto LABEL_108;
      }
    }
    else
    {
      if ( a2 < 0x22 )
        goto LABEL_111;
      v35 = *(unsigned int *)(a1 + 24);
      if ( a2 <= (unsigned int)v35 )
        goto LABEL_111;
      v36 = *(_DWORD *)(a1 + 20);
      if ( (v36 & 0xFFFFFFFC) != 0 || v36 == 2 )
        goto LABEL_111;
      v37 = 30;
      if ( (_DWORD)v35 )
      {
        v38 = a2 - v35;
        v39 = (_DWORD *)(a1 + v35);
        v40 = *(_DWORD *)(a1 + v35);
        if ( v40 == 3 && v38 >= 0x2E )
          goto LABEL_115;
        if ( v40 != 12 || v38 < 0x18 )
          goto LABEL_111;
        if ( v39[5] )
        {
LABEL_115:
          v41 = (unsigned int)v39[5];
          v42 = (const WCHAR *)((char *)v39 + v41);
          if ( (_DWORD *)((char *)v39 + v41) )
          {
            v43 = v38 - v41;
            v44 = *(_DWORD *)v42;
            if ( *(_DWORD *)v42 == 2 )
            {
              if ( v43 < 0x16 )
                goto LABEL_111;
              if ( (a3 & 0x40) == 0 )
              {
                PartitionVhdFilePath = BiGetPartitionVhdFilePath(v42 + 10);
                if ( PartitionVhdFilePath )
                {
                  ExFreePoolWithTag_0(PartitionVhdFilePath, 0x4B444342u);
                  goto LABEL_73;
                }
              }
            }
            else if ( v44 != 6 && (v44 != 8 || v43 < 0x22) && (v44 != 1 || v43 < 0x14) && (v44 != 9 || v43 < 0x15) )
            {
              goto LABEL_111;
            }
          }
        }
        v15 = BiConvertNtDeviceToBootEnvironment(v39, v38, a3 & 0x40, &P);
        if ( v15 < 0 )
          goto LABEL_109;
        v46 = *v39 != 12 ? 0x28 : 0;
        v47 = v46 + *((_DWORD *)P + 2) + 30;
      }
      else
      {
        v46 = 0;
        v47 = 30;
      }
      v48 = *(_DWORD *)(a1 + 20);
      v49 = -1;
      if ( v48 == 1 )
      {
        v50 = -1;
        do
          ++v50;
        while ( *(_WORD *)(a1 + 2 * v50 + 32) );
        v47 += 2 * v50;
      }
      else if ( v48 == 3 )
      {
        v47 += 14;
      }
      v51 = (char *)ExAllocatePool2(258, v47, 1262764866);
      v7 = v51;
      if ( v51 )
      {
        memset(v51, 0, v47);
        *(_DWORD *)v7 = 8;
        *((_DWORD *)v7 + 2) = v47;
        v52 = *(_DWORD *)(a1 + 20);
        if ( v52 )
        {
          if ( v52 == 1 )
          {
            *((_DWORD *)v7 + 4) = 1;
            v53 = -1;
            do
              ++v53;
            while ( *(_WORD *)(a1 + 2 * v53 + 32) );
            wcscpy_s((wchar_t *)v7 + 14, v53 + 1, (const wchar_t *)(a1 + 32));
            do
              ++v49;
            while ( *(_WORD *)(a1 + 2 * v49 + 32) );
            v37 = 2 * v49 + 30;
          }
          else
          {
            *((_DWORD *)v7 + 4) = 2;
            v37 = 44;
            *(_OWORD *)(v7 + 28) = *(_OWORD *)(a1 + 32);
          }
        }
        else
        {
          *((_DWORD *)v7 + 4) = 0;
          *((_DWORD *)v7 + 5) = *(_DWORD *)(a1 + 28);
        }
        if ( P )
        {
          v54 = &v7[v37];
          if ( v46 )
          {
            *(_DWORD *)v54 = 0;
            v55 = *((_DWORD *)P + 2);
            *((_DWORD *)v54 + 4) = 6;
            *((_DWORD *)v54 + 2) = v46 + v55;
          }
          memmove(&v54[v46], P, *((unsigned int *)P + 2));
          *((_DWORD *)v7 + 6) = v37;
          *((_DWORD *)v7 + 1) |= *((_DWORD *)P + 1) & 0x20;
        }
        v4 = Src;
        goto LABEL_108;
      }
      v4 = Src;
    }
    v15 = -1073741670;
    goto LABEL_109;
  }
  if ( v3 == 7 )
  {
    if ( a2 < 0x24 )
      goto LABEL_111;
    v24 = (char *)ExAllocatePool2(258, 72, 1262764866);
    v7 = v24;
    if ( !v24 )
      goto LABEL_30;
    memset(v24, 0, 0x48u);
    *(_DWORD *)v7 = 7;
    *((_DWORD *)v7 + 2) = 72;
    *((_OWORD *)v7 + 1) = VmbFsInterfaceTypeGuid;
    v25 = *(_OWORD *)(a1 + 20);
    goto LABEL_35;
  }
  v8 = v3 - 1;
  if ( !v8 )
  {
    if ( a2 >= 0x14 )
    {
      v23 = (char *)ExAllocatePool2(258, 72, 1262764866);
      v7 = v23;
      if ( v23 )
      {
        memset(v23, 0, 0x48u);
        *(_DWORD *)v7 = 5;
        *((_DWORD *)v7 + 2) = 72;
        goto LABEL_108;
      }
      goto LABEL_30;
    }
LABEL_111:
    v15 = -1073741811;
    goto LABEL_112;
  }
  v9 = v8 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 == 1 && a2 >= 0x20 )
        {
          v12 = *(_DWORD *)(a1 + 28);
          if ( v12 <= 0x100000 )
          {
            v13 = (char *)ExAllocatePool2(258, v12, 1262764866);
            v7 = v13;
            if ( v13 )
            {
              memmove(v13, (const void *)(a1 + 20), *(unsigned int *)(a1 + 28));
LABEL_108:
              v15 = 0;
              goto LABEL_109;
            }
LABEL_30:
            v15 = -1073741670;
            goto LABEL_109;
          }
        }
        goto LABEL_111;
      }
      if ( a2 < 0x2E )
        goto LABEL_111;
      v14 = *(unsigned int *)(a1 + 20);
      if ( !(_DWORD)v14 )
        goto LABEL_111;
      Src = 0;
      v15 = BiConvertNtFilePathToBootEnvironment(
              v14 + a1,
              a2 - (unsigned int)v14,
              (_WORD *)(a1 + 24),
              a3,
              (void **)Srca);
      if ( v15 < 0 )
        goto LABEL_109;
      v16 = (unsigned int *)Src;
      v17 = *((_DWORD *)Src + 1) + 40;
      v18 = (char *)ExAllocatePool2(258, v17, 1262764866);
      v7 = v18;
      if ( v18 )
      {
        memset(v18, 0, v17);
        *(_DWORD *)v7 = 0;
        *((_DWORD *)v7 + 1) = 1;
        *((_DWORD *)v7 + 2) = v17;
        *((_DWORD *)v7 + 4) = 3;
        memmove(v7 + 40, v16, v16[1]);
LABEL_17:
        ExFreePoolWithTag_0(v16, 0x4B444342u);
        goto LABEL_108;
      }
    }
    else
    {
      if ( a2 < 0x2E )
        goto LABEL_111;
      v19 = *(unsigned int *)(a1 + 20);
      if ( !(_DWORD)v19 )
        goto LABEL_111;
      Src = 0;
      v15 = BiConvertNtFilePathToBootEnvironment(
              v19 + a1,
              a2 - (unsigned int)v19,
              (_WORD *)(a1 + 24),
              a3,
              (void **)Srca);
      if ( v15 < 0 )
        goto LABEL_109;
      v16 = (unsigned int *)Src;
      v20 = *((_DWORD *)Src + 1) + 20;
      v21 = (char *)ExAllocatePool2(258, v20, 1262764866);
      v7 = v21;
      if ( v21 )
      {
        memset(v21, 0, v20);
        *(_DWORD *)v7 = 0;
        *((_DWORD *)v7 + 2) = v20;
        *((_DWORD *)v7 + 4) = 5;
        memmove(v7 + 20, v16, v16[1]);
        *((_DWORD *)v7 + 1) = v16[4] & 0x20;
        goto LABEL_17;
      }
    }
    ExFreePoolWithTag_0(v16, 0x4B444342u);
    goto LABEL_30;
  }
  if ( a2 < 0x16 )
    goto LABEL_111;
  if ( !(unsigned __int8)BiIsVolumePartitionInformationRetained((PCWSTR)(a1 + 20)) )
  {
LABEL_73:
    v15 = -1073741637;
    goto LABEL_109;
  }
  v22 = BiCreatePartitionDevice((PCWSTR)(a1 + 20), a3, &v58, &v59);
  v7 = v58;
  v15 = v22;
  if ( v22 >= 0 )
    goto LABEL_108;
LABEL_109:
  if ( P )
    ExFreePoolWithTag_0(P, 0x4B444342u);
LABEL_112:
  result = (unsigned int)v15;
  *v4 = v7;
  return result;
}

```

## disassembly

```asm
0x14002fc98  mov     [rsp-38h+arg_8], rbx
0x14002fc9d  mov     [rsp-38h+Src], r9
0x14002fca2  push    rbp
0x14002fca3  push    rsi
0x14002fca4  push    rdi
0x14002fca5  push    r12
0x14002fca7  push    r13
0x14002fca9  push    r14
0x14002fcab  push    r15
0x14002fcad  mov     rbp, rsp
0x14002fcb0  sub     rsp, 40h
0x14002fcb4  mov     eax, [rcx]
0x14002fcb6  xor     r13d, r13d
0x14002fcb9  mov     [rbp+arg_0], r13d
0x14002fcbd  mov     r12, r9
0x14002fcc0  mov     [rbp+P], r13
0x14002fcc4  mov     r14d, r8d
0x14002fcc7  mov     [rbp+var_8], r13
0x14002fccb  mov     ebx, edx
0x14002fccd  mov     rsi, rcx
0x14002fcd0  mov     edi, r13d
0x14002fcd3  mov     r15d, 4B444342h
0x14002fcd9  cmp     eax, 7
0x14002fcdc  ja      loc_14002FFAC
0x14002fce2  jz      loc_14002FF50
0x14002fce8  sub     eax, 1
0x14002fceb  jz      loc_14002FEFF
0x14002fcf1  sub     eax, 1
0x14002fcf4  jz      loc_14002FEBE
0x14002fcfa  sub     eax, 1
0x14002fcfd  jz      loc_14002FE0D
0x14002fd03  sub     eax, 1
0x14002fd06  jz      short loc_14002FD5F
0x14002fd08  cmp     eax, 1
0x14002fd0b  jnz     loc_140030410
0x14002fd11  cmp     edx, 20h ; ' '
0x14002fd14  jb      loc_140030410
0x14002fd1a  mov     eax, [rcx+1Ch]
0x14002fd1d  cmp     eax, 100000h
0x14002fd22  ja      loc_140030410
0x14002fd28  mov     edx, eax
0x14002fd2a  mov     r8d, r15d
0x14002fd2d  mov     ecx, 102h
0x14002fd32  call    cs:__imp_ExAllocatePool2
0x14002fd39  nop     dword ptr [rax+rax+00h]
0x14002fd3e  mov     rdi, rax
0x14002fd41  test    rax, rax
0x14002fd44  jz      loc_14002FF2B
0x14002fd4a  mov     r8d, [rsi+1Ch]; Size
0x14002fd4e  lea     rdx, [rsi+14h]; Src
0x14002fd52  mov     rcx, rax; void *
0x14002fd55  call    memmove
0x14002fd5a  jmp     loc_1400303F7
0x14002fd5f  cmp     ebx, 2Eh ; '.'
0x14002fd62  jb      loc_140030410
0x14002fd68  mov     eax, [rcx+14h]
0x14002fd6b  test    eax, eax
0x14002fd6d  jz      loc_140030410
0x14002fd73  sub     ebx, eax
0x14002fd75  mov     [rbp+Src], r13
0x14002fd79  lea     r8, [rcx+18h]
0x14002fd7d  mov     r9d, r14d
0x14002fd80  add     rcx, rax
0x14002fd83  mov     edx, ebx
0x14002fd85  lea     rax, [rbp+Src]
0x14002fd89  mov     [rsp+40h+var_20], rax
0x14002fd8e  call    BiConvertNtFilePathToBootEnvironment
0x14002fd93  mov     ebx, eax
0x14002fd95  test    eax, eax
0x14002fd97  js      loc_1400303FA
0x14002fd9d  mov     rbx, [rbp+Src]
0x14002fda1  mov     r8d, r15d
0x14002fda4  mov     ecx, 102h
0x14002fda9  mov     esi, [rbx+4]
0x14002fdac  add     esi, 28h ; '('
0x14002fdaf  mov     edx, esi
0x14002fdb1  mov     r14d, esi
0x14002fdb4  call    cs:__imp_ExAllocatePool2
0x14002fdbb  nop     dword ptr [rax+rax+00h]
0x14002fdc0  mov     rdi, rax
0x14002fdc3  test    rax, rax
0x14002fdc6  jz      loc_14002FE76
0x14002fdcc  mov     r8d, r14d; Size
0x14002fdcf  xor     edx, edx; Val
0x14002fdd1  mov     rcx, rax; void *
0x14002fdd4  call    memset
0x14002fdd9  mov     [rdi], r13d
0x14002fddc  lea     rcx, [rdi+28h]; void *
0x14002fde0  mov     dword ptr [rdi+4], 1
0x14002fde7  mov     rdx, rbx; Src
0x14002fdea  mov     [rdi+8], esi
0x14002fded  mov     dword ptr [rdi+10h], 3
0x14002fdf4  mov     r8d, [rbx+4]; Size
0x14002fdf8  call    memmove
0x14002fdfd  mov     edx, r15d; Tag
0x14002fe00  mov     rcx, rbx; P
0x14002fe03  call    ExFreePoolWithTag_0
0x14002fe08  jmp     loc_1400303F7
0x14002fe0d  cmp     ebx, 2Eh ; '.'
0x14002fe10  jb      loc_140030410
0x14002fe16  mov     eax, [rcx+14h]
0x14002fe19  test    eax, eax
0x14002fe1b  jz      loc_140030410
0x14002fe21  sub     ebx, eax
0x14002fe23  mov     [rbp+Src], r13
0x14002fe27  lea     r8, [rcx+18h]
0x14002fe2b  mov     r9d, r14d
0x14002fe2e  add     rcx, rax
0x14002fe31  mov     edx, ebx
0x14002fe33  lea     rax, [rbp+Src]
0x14002fe37  mov     [rsp+40h+var_20], rax
0x14002fe3c  call    BiConvertNtFilePathToBootEnvironment
0x14002fe41  mov     ebx, eax
0x14002fe43  test    eax, eax
0x14002fe45  js      loc_1400303FA
0x14002fe4b  mov     rbx, [rbp+Src]
0x14002fe4f  mov     r8d, r15d
0x14002fe52  mov     ecx, 102h
0x14002fe57  mov     esi, [rbx+4]
0x14002fe5a  add     esi, 14h
0x14002fe5d  mov     edx, esi
0x14002fe5f  mov     r14d, esi
0x14002fe62  call    cs:__imp_ExAllocatePool2
0x14002fe69  nop     dword ptr [rax+rax+00h]
0x14002fe6e  mov     rdi, rax
0x14002fe71  test    rax, rax
0x14002fe74  jnz     short loc_14002FE86
0x14002fe76  mov     edx, r15d; Tag
0x14002fe79  mov     rcx, rbx; P
0x14002fe7c  call    ExFreePoolWithTag_0
0x14002fe81  jmp     loc_14002FF2B
0x14002fe86  mov     r8, r14; Size
0x14002fe89  xor     edx, edx; Val
0x14002fe8b  mov     rcx, rdi; void *
0x14002fe8e  call    memset
0x14002fe93  mov     [rdi], r13d
0x14002fe96  lea     rcx, [rdi+14h]; void *
0x14002fe9a  mov     [rdi+8], esi
0x14002fe9d  mov     rdx, rbx; Src
0x14002fea0  mov     dword ptr [rdi+10h], 5
0x14002fea7  mov     r8d, [rbx+4]; Size
0x14002feab  call    memmove
0x14002feb0  mov     eax, [rbx+10h]
0x14002feb3  and     eax, 20h
0x14002feb6  mov     [rdi+4], eax
0x14002feb9  jmp     loc_14002FDFD
0x14002febe  cmp     ebx, 16h
0x14002fec1  jb      loc_140030410
0x14002fec7  add     rcx, 14h; SourceString
0x14002fecb  call    BiIsVolumePartitionInformationRetained
0x14002fed0  test    al, al
0x14002fed2  jz      loc_14003023C
0x14002fed8  lea     r9, [rbp+arg_0]
0x14002fedc  mov     edx, r14d
0x14002fedf  lea     r8, [rbp+var_8]
0x14002fee3  lea     rcx, [rsi+14h]; SourceString
0x14002fee7  call    BiCreatePartitionDevice
0x14002feec  mov     rdi, [rbp+var_8]
0x14002fef0  mov     ebx, eax
0x14002fef2  test    eax, eax
0x14002fef4  jns     loc_1400303F7
0x14002fefa  jmp     loc_1400303FA
0x14002feff  cmp     ebx, 14h
0x14002ff02  jb      loc_140030410
0x14002ff08  mov     ebx, 48h ; 'H'
0x14002ff0d  mov     r8d, r15d
0x14002ff10  mov     edx, ebx
0x14002ff12  mov     ecx, 102h
0x14002ff17  call    cs:__imp_ExAllocatePool2
0x14002ff1e  nop     dword ptr [rax+rax+00h]
0x14002ff23  mov     rdi, rax
0x14002ff26  test    rax, rax
0x14002ff29  jnz     short loc_14002FF35
0x14002ff2b  mov     ebx, 0C000009Ah
0x14002ff30  jmp     loc_1400303FA
0x14002ff35  mov     r8, rbx; Size
0x14002ff38  xor     edx, edx; Val
0x14002ff3a  mov     rcx, rdi; void *
0x14002ff3d  call    memset
0x14002ff42  mov     dword ptr [rdi], 5
0x14002ff48  mov     [rdi+8], ebx
0x14002ff4b  jmp     loc_1400303F7
0x14002ff50  cmp     ebx, 24h ; '$'
0x14002ff53  jb      loc_140030410
0x14002ff59  mov     ebx, 48h ; 'H'
0x14002ff5e  mov     r8d, r15d
0x14002ff61  mov     edx, ebx
0x14002ff63  mov     ecx, 102h
0x14002ff68  call    cs:__imp_ExAllocatePool2
0x14002ff6f  nop     dword ptr [rax+rax+00h]
0x14002ff74  mov     rdi, rax
0x14002ff77  test    rax, rax
0x14002ff7a  jz      short loc_14002FF2B
0x14002ff7c  mov     r8d, ebx; Size
0x14002ff7f  xor     edx, edx; Val
0x14002ff81  mov     rcx, rax; void *
0x14002ff84  call    memset
0x14002ff89  mov     dword ptr [rdi], 7
0x14002ff8f  mov     [rdi+8], ebx
0x14002ff92  movups  xmm0, cs:VmbFsInterfaceTypeGuid
0x14002ff99  movdqu  xmmword ptr [rdi+10h], xmm0
0x14002ff9e  movups  xmm0, xmmword ptr [rsi+14h]
0x14002ffa2  movdqu  xmmword ptr [rdi+20h], xmm0
0x14002ffa7  jmp     loc_1400303F7
0x14002ffac  sub     eax, 8
0x14002ffaf  jz      loc_14003018E
0x14002ffb5  sub     eax, 1
0x14002ffb8  jz      loc_14003010B
0x14002ffbe  sub     eax, 1
0x14002ffc1  jz      loc_140030088
0x14002ffc7  sub     eax, 1
0x14002ffca  jz      short loc_14003002C
0x14002ffcc  cmp     eax, 2
0x14002ffcf  jnz     loc_140030410
0x14002ffd5  cmp     ebx, 18h
0x14002ffd8  jb      loc_140030410
0x14002ffde  lea     ebx, [rax+46h]
0x14002ffe1  mov     r8d, r15d
0x14002ffe4  mov     edx, ebx
0x14002ffe6  mov     ecx, 102h
0x14002ffeb  call    cs:__imp_ExAllocatePool2
0x14002fff2  nop     dword ptr [rax+rax+00h]
0x14002fff7  mov     rdi, rax
0x14002fffa  test    rax, rax
0x14002fffd  jz      loc_14002FF2B
0x140030003  mov     r8d, ebx; Size
0x140030006  xor     edx, edx; Val
0x140030008  mov     rcx, rax; void *
0x14003000b  call    memset
0x140030010  mov     [rdi], r13d
0x140030013  mov     [rdi+8], ebx
0x140030016  mov     [rdi+10h], r13d
0x14003001a  mov     dword ptr [rdi+14h], 2
0x140030021  mov     eax, [rsi+14h]
0x140030024  mov     [rdi+18h], eax
0x140030027  jmp     loc_1400303F7
0x14003002c  cmp     ebx, 28h ; '('
0x14003002f  jb      loc_140030410
0x140030035  mov     ebx, 48h ; 'H'
0x14003003a  mov     r8d, r15d
0x14003003d  mov     edx, ebx
0x14003003f  mov     ecx, 102h
0x140030044  call    cs:__imp_ExAllocatePool2
0x14003004b  nop     dword ptr [rax+rax+00h]
0x140030050  mov     rdi, rax
0x140030053  test    rax, rax
0x140030056  jz      loc_14002FF2B
0x14003005c  mov     r8d, ebx; Size
0x14003005f  xor     edx, edx; Val
0x140030061  mov     rcx, rax; void *
0x140030064  call    memset
0x140030069  mov     dword ptr [rdi], 0Bh
0x14003006f  mov     [rdi+8], ebx
0x140030072  mov     dword ptr [rdi+4], 1
0x140030079  mov     eax, [rsi+14h]
0x14003007c  mov     [rdi+10h], eax
0x14003007f  movups  xmm0, xmmword ptr [rsi+18h]
0x140030083  jmp     loc_14002FFA2
0x140030088  cmp     ebx, 28h ; '('
0x14003008b  jb      loc_140030410
0x140030091  mov     rax, [rcx+14h]
0x140030095  cmp     rax, cs:CompositeDeviceSignature
0x14003009c  jnz     loc_140030410
0x1400300a2  mov     rax, [rcx+1Ch]
0x1400300a6  cmp     rax, cs:qword_1400143D0
0x1400300ad  jnz     loc_140030410
0x1400300b3  mov     ebx, 48h ; 'H'
0x1400300b8  mov     r8d, r15d
0x1400300bb  mov     edx, ebx
0x1400300bd  mov     ecx, 102h
0x1400300c2  call    cs:__imp_ExAllocatePool2
0x1400300c9  nop     dword ptr [rax+rax+00h]
0x1400300ce  mov     rdi, rax
0x1400300d1  test    rax, rax
0x1400300d4  jz      loc_14002FF2B
0x1400300da  mov     r8d, ebx; Size
0x1400300dd  xor     edx, edx; Val
0x1400300df  mov     rcx, rax; void *
0x1400300e2  call    memset
0x1400300e7  mov     dword ptr [rdi], 0Ah
0x1400300ed  mov     [rdi+8], ebx
0x1400300f0  mov     dword ptr [rdi+4], 1
0x1400300f7  movups  xmm0, xmmword ptr [rsi+14h]
0x1400300fb  movdqu  xmmword ptr [rdi+10h], xmm0
0x140030100  mov     eax, [rsi+24h]
0x140030103  mov     [rdi+20h], eax
0x140030106  jmp     loc_1400303F7
0x14003010b  cmp     ebx, 15h
0x14003010e  jb      loc_140030410
0x140030114  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140030118  inc     rbx
0x14003011b  cmp     [rcx+rbx+14h], r13b
0x140030120  jnz     short loc_140030118
0x140030122  lea     r14d, [rbx+15h]
0x140030126  mov     r8d, 4B444342h
0x14003012c  mov     edx, r14d
0x14003012f  mov     ecx, 102h
0x140030134  mov     r15d, r14d
0x140030137  call    cs:__imp_ExAllocatePool2
0x14003013e  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
