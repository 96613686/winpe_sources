# BiConvertNtDeviceToBootEnvironment

- ea: `0x14002fce8`
- end: `0x140030484`
- name: `BiConvertNtDeviceToBootEnvironment`
- size: `1948`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002b48c`
- `0x14002fce8`
- `0x14003048c`
- `0x14003074c`

## callees

- `0x14000da0d`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002fce8`
- `0x14003048c`
- `0x14003074c`
- `0x140031520`
- `0x140031a90`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x1400303b4`
- `ntoskrnl!wcscpy_s` at `0x1400303b4`
- `ntoskrnl!ExAllocatePool2` at `0x14002fd82`
- `ntoskrnl!ExAllocatePool2` at `0x14002fe04`
- `ntoskrnl!ExAllocatePool2` at `0x14002feb2`
- `ntoskrnl!ExAllocatePool2` at `0x14002ff67`
- `ntoskrnl!ExAllocatePool2` at `0x14002ffb8`
- `ntoskrnl!ExAllocatePool2` at `0x14003003b`
- `ntoskrnl!ExAllocatePool2` at `0x140030094`
- `ntoskrnl!ExAllocatePool2` at `0x140030112`
- `ntoskrnl!ExAllocatePool2` at `0x140030187`
- `ntoskrnl!ExAllocatePool2` at `0x14003033e`
- `ntoskrnl!ExAllocatePool2` at `0x14002fd82`
- `ntoskrnl!ExAllocatePool2` at `0x14002fe04`
- `ntoskrnl!ExAllocatePool2` at `0x14002feb2`
- `ntoskrnl!ExAllocatePool2` at `0x14002ff67`
- `ntoskrnl!ExAllocatePool2` at `0x14002ffb8`
- `ntoskrnl!ExAllocatePool2` at `0x14003003b`
- `ntoskrnl!ExAllocatePool2` at `0x140030094`
- `ntoskrnl!ExAllocatePool2` at `0x140030112`
- `ntoskrnl!ExAllocatePool2` at `0x140030187`
- `ntoskrnl!ExAllocatePool2` at `0x14003033e`
- `ntoskrnl!strcpy_s` at `0x1400301cd`
- `ntoskrnl!strcpy_s` at `0x1400301cd`

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
0x14002fce8  mov     [rsp-38h+arg_8], rbx
0x14002fced  mov     [rsp-38h+Src], r9
0x14002fcf2  push    rbp
0x14002fcf3  push    rsi
0x14002fcf4  push    rdi
0x14002fcf5  push    r12
0x14002fcf7  push    r13
0x14002fcf9  push    r14
0x14002fcfb  push    r15
0x14002fcfd  mov     rbp, rsp
0x14002fd00  sub     rsp, 40h
0x14002fd04  mov     eax, [rcx]
0x14002fd06  xor     r13d, r13d
0x14002fd09  mov     [rbp+arg_0], r13d
0x14002fd0d  mov     r12, r9
0x14002fd10  mov     [rbp+P], r13
0x14002fd14  mov     r14d, r8d
0x14002fd17  mov     [rbp+var_8], r13
0x14002fd1b  mov     ebx, edx
0x14002fd1d  mov     rsi, rcx
0x14002fd20  mov     edi, r13d
0x14002fd23  mov     r15d, 4B444342h
0x14002fd29  cmp     eax, 7
0x14002fd2c  ja      loc_14002FFFC
0x14002fd32  jz      loc_14002FFA0
0x14002fd38  sub     eax, 1
0x14002fd3b  jz      loc_14002FF4F
0x14002fd41  sub     eax, 1
0x14002fd44  jz      loc_14002FF0E
0x14002fd4a  sub     eax, 1
0x14002fd4d  jz      loc_14002FE5D
0x14002fd53  sub     eax, 1
0x14002fd56  jz      short loc_14002FDAF
0x14002fd58  cmp     eax, 1
0x14002fd5b  jnz     loc_140030460
0x14002fd61  cmp     edx, 20h ; ' '
0x14002fd64  jb      loc_140030460
0x14002fd6a  mov     eax, [rcx+1Ch]
0x14002fd6d  cmp     eax, 100000h
0x14002fd72  ja      loc_140030460
0x14002fd78  mov     edx, eax
0x14002fd7a  mov     r8d, r15d
0x14002fd7d  mov     ecx, 102h
0x14002fd82  call    cs:__imp_ExAllocatePool2
0x14002fd89  nop     dword ptr [rax+rax+00h]
0x14002fd8e  mov     rdi, rax
0x14002fd91  test    rax, rax
0x14002fd94  jz      loc_14002FF7B
0x14002fd9a  mov     r8d, [rsi+1Ch]; Size
0x14002fd9e  lea     rdx, [rsi+14h]; Src
0x14002fda2  mov     rcx, rax; void *
0x14002fda5  call    memmove
0x14002fdaa  jmp     loc_140030447
0x14002fdaf  cmp     ebx, 2Eh ; '.'
0x14002fdb2  jb      loc_140030460
0x14002fdb8  mov     eax, [rcx+14h]
0x14002fdbb  test    eax, eax
0x14002fdbd  jz      loc_140030460
0x14002fdc3  sub     ebx, eax
0x14002fdc5  mov     [rbp+Src], r13
0x14002fdc9  lea     r8, [rcx+18h]
0x14002fdcd  mov     r9d, r14d
0x14002fdd0  add     rcx, rax
0x14002fdd3  mov     edx, ebx
0x14002fdd5  lea     rax, [rbp+Src]
0x14002fdd9  mov     [rsp+40h+var_20], rax
0x14002fdde  call    BiConvertNtFilePathToBootEnvironment
0x14002fde3  mov     ebx, eax
0x14002fde5  test    eax, eax
0x14002fde7  js      loc_14003044A
0x14002fded  mov     rbx, [rbp+Src]
0x14002fdf1  mov     r8d, r15d
0x14002fdf4  mov     ecx, 102h
0x14002fdf9  mov     esi, [rbx+4]
0x14002fdfc  add     esi, 28h ; '('
0x14002fdff  mov     edx, esi
0x14002fe01  mov     r14d, esi
0x14002fe04  call    cs:__imp_ExAllocatePool2
0x14002fe0b  nop     dword ptr [rax+rax+00h]
0x14002fe10  mov     rdi, rax
0x14002fe13  test    rax, rax
0x14002fe16  jz      loc_14002FEC6
0x14002fe1c  mov     r8d, r14d; Size
0x14002fe1f  xor     edx, edx; Val
0x14002fe21  mov     rcx, rax; void *
0x14002fe24  call    memset
0x14002fe29  mov     [rdi], r13d
0x14002fe2c  lea     rcx, [rdi+28h]; void *
0x14002fe30  mov     dword ptr [rdi+4], 1
0x14002fe37  mov     rdx, rbx; Src
0x14002fe3a  mov     [rdi+8], esi
0x14002fe3d  mov     dword ptr [rdi+10h], 3
0x14002fe44  mov     r8d, [rbx+4]; Size
0x14002fe48  call    memmove
0x14002fe4d  mov     edx, r15d; Tag
0x14002fe50  mov     rcx, rbx; P
0x14002fe53  call    ExFreePoolWithTag_0
0x14002fe58  jmp     loc_140030447
0x14002fe5d  cmp     ebx, 2Eh ; '.'
0x14002fe60  jb      loc_140030460
0x14002fe66  mov     eax, [rcx+14h]
0x14002fe69  test    eax, eax
0x14002fe6b  jz      loc_140030460
0x14002fe71  sub     ebx, eax
0x14002fe73  mov     [rbp+Src], r13
0x14002fe77  lea     r8, [rcx+18h]
0x14002fe7b  mov     r9d, r14d
0x14002fe7e  add     rcx, rax
0x14002fe81  mov     edx, ebx
0x14002fe83  lea     rax, [rbp+Src]
0x14002fe87  mov     [rsp+40h+var_20], rax
0x14002fe8c  call    BiConvertNtFilePathToBootEnvironment
0x14002fe91  mov     ebx, eax
0x14002fe93  test    eax, eax
0x14002fe95  js      loc_14003044A
0x14002fe9b  mov     rbx, [rbp+Src]
0x14002fe9f  mov     r8d, r15d
0x14002fea2  mov     ecx, 102h
0x14002fea7  mov     esi, [rbx+4]
0x14002feaa  add     esi, 14h
0x14002fead  mov     edx, esi
0x14002feaf  mov     r14d, esi
0x14002feb2  call    cs:__imp_ExAllocatePool2
0x14002feb9  nop     dword ptr [rax+rax+00h]
0x14002febe  mov     rdi, rax
0x14002fec1  test    rax, rax
0x14002fec4  jnz     short loc_14002FED6
0x14002fec6  mov     edx, r15d; Tag
0x14002fec9  mov     rcx, rbx; P
0x14002fecc  call    ExFreePoolWithTag_0
0x14002fed1  jmp     loc_14002FF7B
0x14002fed6  mov     r8, r14; Size
0x14002fed9  xor     edx, edx; Val
0x14002fedb  mov     rcx, rdi; void *
0x14002fede  call    memset
0x14002fee3  mov     [rdi], r13d
0x14002fee6  lea     rcx, [rdi+14h]; void *
0x14002feea  mov     [rdi+8], esi
0x14002feed  mov     rdx, rbx; Src
0x14002fef0  mov     dword ptr [rdi+10h], 5
0x14002fef7  mov     r8d, [rbx+4]; Size
0x14002fefb  call    memmove
0x14002ff00  mov     eax, [rbx+10h]
0x14002ff03  and     eax, 20h
0x14002ff06  mov     [rdi+4], eax
0x14002ff09  jmp     loc_14002FE4D
0x14002ff0e  cmp     ebx, 16h
0x14002ff11  jb      loc_140030460
0x14002ff17  add     rcx, 14h; SourceString
0x14002ff1b  call    BiIsVolumePartitionInformationRetained
0x14002ff20  test    al, al
0x14002ff22  jz      loc_14003028C
0x14002ff28  lea     r9, [rbp+arg_0]
0x14002ff2c  mov     edx, r14d
0x14002ff2f  lea     r8, [rbp+var_8]
0x14002ff33  lea     rcx, [rsi+14h]; SourceString
0x14002ff37  call    BiCreatePartitionDevice
0x14002ff3c  mov     rdi, [rbp+var_8]
0x14002ff40  mov     ebx, eax
0x14002ff42  test    eax, eax
0x14002ff44  jns     loc_140030447
0x14002ff4a  jmp     loc_14003044A
0x14002ff4f  cmp     ebx, 14h
0x14002ff52  jb      loc_140030460
0x14002ff58  mov     ebx, 48h ; 'H'
0x14002ff5d  mov     r8d, r15d
0x14002ff60  mov     edx, ebx
0x14002ff62  mov     ecx, 102h
0x14002ff67  call    cs:__imp_ExAllocatePool2
0x14002ff6e  nop     dword ptr [rax+rax+00h]
0x14002ff73  mov     rdi, rax
0x14002ff76  test    rax, rax
0x14002ff79  jnz     short loc_14002FF85
0x14002ff7b  mov     ebx, 0C000009Ah
0x14002ff80  jmp     loc_14003044A
0x14002ff85  mov     r8, rbx; Size
0x14002ff88  xor     edx, edx; Val
0x14002ff8a  mov     rcx, rdi; void *
0x14002ff8d  call    memset
0x14002ff92  mov     dword ptr [rdi], 5
0x14002ff98  mov     [rdi+8], ebx
0x14002ff9b  jmp     loc_140030447
0x14002ffa0  cmp     ebx, 24h ; '$'
0x14002ffa3  jb      loc_140030460
0x14002ffa9  mov     ebx, 48h ; 'H'
0x14002ffae  mov     r8d, r15d
0x14002ffb1  mov     edx, ebx
0x14002ffb3  mov     ecx, 102h
0x14002ffb8  call    cs:__imp_ExAllocatePool2
0x14002ffbf  nop     dword ptr [rax+rax+00h]
0x14002ffc4  mov     rdi, rax
0x14002ffc7  test    rax, rax
0x14002ffca  jz      short loc_14002FF7B
0x14002ffcc  mov     r8d, ebx; Size
0x14002ffcf  xor     edx, edx; Val
0x14002ffd1  mov     rcx, rax; void *
0x14002ffd4  call    memset
0x14002ffd9  mov     dword ptr [rdi], 7
0x14002ffdf  mov     [rdi+8], ebx
0x14002ffe2  movups  xmm0, cs:VmbFsInterfaceTypeGuid
0x14002ffe9  movdqu  xmmword ptr [rdi+10h], xmm0
0x14002ffee  movups  xmm0, xmmword ptr [rsi+14h]
0x14002fff2  movdqu  xmmword ptr [rdi+20h], xmm0
0x14002fff7  jmp     loc_140030447
0x14002fffc  sub     eax, 8
0x14002ffff  jz      loc_1400301DE
0x140030005  sub     eax, 1
0x140030008  jz      loc_14003015B
0x14003000e  sub     eax, 1
0x140030011  jz      loc_1400300D8
0x140030017  sub     eax, 1
0x14003001a  jz      short loc_14003007C
0x14003001c  cmp     eax, 2
0x14003001f  jnz     loc_140030460
0x140030025  cmp     ebx, 18h
0x140030028  jb      loc_140030460
0x14003002e  lea     ebx, [rax+46h]
0x140030031  mov     r8d, r15d
0x140030034  mov     edx, ebx
0x140030036  mov     ecx, 102h
0x14003003b  call    cs:__imp_ExAllocatePool2
0x140030042  nop     dword ptr [rax+rax+00h]
0x140030047  mov     rdi, rax
0x14003004a  test    rax, rax
0x14003004d  jz      loc_14002FF7B
0x140030053  mov     r8d, ebx; Size
0x140030056  xor     edx, edx; Val
0x140030058  mov     rcx, rax; void *
0x14003005b  call    memset
0x140030060  mov     [rdi], r13d
0x140030063  mov     [rdi+8], ebx
0x140030066  mov     [rdi+10h], r13d
0x14003006a  mov     dword ptr [rdi+14h], 2
0x140030071  mov     eax, [rsi+14h]
0x140030074  mov     [rdi+18h], eax
0x140030077  jmp     loc_140030447
0x14003007c  cmp     ebx, 28h ; '('
0x14003007f  jb      loc_140030460
0x140030085  mov     ebx, 48h ; 'H'
0x14003008a  mov     r8d, r15d
0x14003008d  mov     edx, ebx
0x14003008f  mov     ecx, 102h
0x140030094  call    cs:__imp_ExAllocatePool2
0x14003009b  nop     dword ptr [rax+rax+00h]
0x1400300a0  mov     rdi, rax
0x1400300a3  test    rax, rax
0x1400300a6  jz      loc_14002FF7B
0x1400300ac  mov     r8d, ebx; Size
0x1400300af  xor     edx, edx; Val
0x1400300b1  mov     rcx, rax; void *
0x1400300b4  call    memset
0x1400300b9  mov     dword ptr [rdi], 0Bh
0x1400300bf  mov     [rdi+8], ebx
0x1400300c2  mov     dword ptr [rdi+4], 1
0x1400300c9  mov     eax, [rsi+14h]
0x1400300cc  mov     [rdi+10h], eax
0x1400300cf  movups  xmm0, xmmword ptr [rsi+18h]
0x1400300d3  jmp     loc_14002FFF2
0x1400300d8  cmp     ebx, 28h ; '('
0x1400300db  jb      loc_140030460
0x1400300e1  mov     rax, [rcx+14h]
0x1400300e5  cmp     rax, cs:CompositeDeviceSignature
0x1400300ec  jnz     loc_140030460
0x1400300f2  mov     rax, [rcx+1Ch]
0x1400300f6  cmp     rax, cs:qword_1400143D0
0x1400300fd  jnz     loc_140030460
0x140030103  mov     ebx, 48h ; 'H'
0x140030108  mov     r8d, r15d
0x14003010b  mov     edx, ebx
0x14003010d  mov     ecx, 102h
0x140030112  call    cs:__imp_ExAllocatePool2
0x140030119  nop     dword ptr [rax+rax+00h]
0x14003011e  mov     rdi, rax
0x140030121  test    rax, rax
0x140030124  jz      loc_14002FF7B
0x14003012a  mov     r8d, ebx; Size
0x14003012d  xor     edx, edx; Val
0x14003012f  mov     rcx, rax; void *
0x140030132  call    memset
0x140030137  mov     dword ptr [rdi], 0Ah
0x14003013d  mov     [rdi+8], ebx
0x140030140  mov     dword ptr [rdi+4], 1
0x140030147  movups  xmm0, xmmword ptr [rsi+14h]
0x14003014b  movdqu  xmmword ptr [rdi+10h], xmm0
0x140030150  mov     eax, [rsi+24h]
0x140030153  mov     [rdi+20h], eax
0x140030156  jmp     loc_140030447
0x14003015b  cmp     ebx, 15h
0x14003015e  jb      loc_140030460
0x140030164  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140030168  inc     rbx
0x14003016b  cmp     [rcx+rbx+14h], r13b
0x140030170  jnz     short loc_140030168
0x140030172  lea     r14d, [rbx+15h]
0x140030176  mov     r8d, 4B444342h
0x14003017c  mov     edx, r14d
0x14003017f  mov     ecx, 102h
0x140030184  mov     r15d, r14d
0x140030187  call    cs:__imp_ExAllocatePool2
0x14003018e  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
