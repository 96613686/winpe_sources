# AddInterfaceToSourceEntry

- ea: `0x18001c1a8`
- end: `0x18001c788`
- name: `AddInterfaceToSourceEntry`
- size: `1504`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180011850`

## callees

- `0x180014d2c`
- `0x180015178`
- `0x18001928c`
- `0x18001c0c8`
- `0x18001c1a8`
- `0x18001c790`
- `0x18001ca9c`
- `0x18001cd94`
- `0x18001cf18`
- `0x18001d1ec`
- `0x18001dbd0`
- `0x18001dc28`
- `0x18001dcbc`
- `0x18001dd8c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## string_xrefs

- `0x18001c63b`: `Invoked Local Join Alert for protocol %x, %x`

## pseudocode

```c
__int64 __fastcall AddInterfaceToSourceEntry(
        __int64 a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        _DWORD *a9,
        __int64 a10)
{
  unsigned int v13; // edx
  __int64 v14; // r13
  char *v15; // rbx
  int v16; // r8d
  int v17; // edx
  unsigned int v18; // ebx
  __int64 v19; // r14
  __int64 v20; // rbx
  int v21; // r8d
  unsigned int v22; // edx
  __int64 v23; // rdi
  __int64 v24; // rdx
  _DWORD *v25; // r15
  __int64 v26; // rdx
  unsigned int v27; // r12d
  unsigned int v28; // ebx
  int *v29; // rsi
  int *v30; // rdi
  unsigned int v31; // r8d
  _DWORD *v32; // rcx
  int v33; // r12d
  _DWORD *v34; // rax
  int OutInterfaceEntry; // eax
  _DWORD *v36; // rcx
  _DWORD *v37; // rdx
  __int16 v38; // ax
  __int64 v39; // rax
  __int64 v40; // r8
  _DWORD *v41; // r8
  __int16 v42; // dx
  _DWORD *v44; // [rsp+40h] [rbp-C0h] BYREF
  int v45; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  int v47; // [rsp+58h] [rbp-A8h]
  unsigned int v48; // [rsp+5Ch] [rbp-A4h]
  unsigned int v49; // [rsp+60h] [rbp-A0h]
  __int64 v50; // [rsp+68h] [rbp-98h]
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+78h] [rbp-88h]
  _DWORD *v53; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v54; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v55; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+98h] [rbp-68h]
  int v57; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v58[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v52 = a3;
  v48 = a2;
  v50 = a1;
  v55 = a9;
  v56 = a10;
  v47 = 0;
  v45 = 0;
  v46 = 0;
  v51 = 0;
  v54 = 0;
  v53 = 0;
  v44 = 0;
  v57 = 0;
  v49 = a4;
  memset_0(v58, 0, sizeof(v58));
  *a9 = 0;
  if ( a2 )
    v13 = a2 % (dword_18002B930 - 1) + 1;
  else
    v13 = 0;
  v14 = 32LL * v13;
  AcquireWriteLock((char *)qword_18002BA40 + v14 + 16);
  v15 = (char *)qword_18002BA40 + v14;
  if ( (unsigned int)FindGroupEntry((int)v14 + (int)qword_18002BA40, a2, v16, (unsigned int)&v46, 1) )
  {
    v19 = v46;
  }
  else
  {
    if ( v46 )
      v15 = (char *)(v46 + 16);
    v18 = CreateGroupEntry((__int64)v15, v17, a3, &v51);
    if ( v18 )
      goto LABEL_57;
    v19 = v51;
    v47 = 1;
  }
  v20 = v19 + 40;
  LODWORD(v46) = 0;
  v51 = v19 + 40;
  AcquireWriteLock(v19 + 40);
  if ( a4 )
    v22 = a4 % (dword_18002B934 - 1) + 1;
  else
    v22 = 0;
  v23 = 16LL * v22;
  if ( (unsigned int)FindSourceEntry((int)v19 + (int)v23 + 88, a4, v21, (unsigned int)&v54, 1) )
  {
    v25 = v54;
  }
  else
  {
    if ( v54 )
      v24 = (__int64)(v54 + 4);
    else
      v24 = v23 + v19 + 88;
    v18 = CreateSourceEntry(v19, v24, a4, a5, &v53);
    if ( v18 )
    {
LABEL_45:
      ReleaseWriteLock(v19 + 40);
      if ( v47 )
        DeleteGroupEntry(v19);
      goto LABEL_57;
    }
    v25 = v53;
    ++*(_DWORD *)(v19 + 48);
    v20 = v19 + 40;
    LODWORD(v46) = 1;
  }
  if ( qword_18002B950 )
  {
    v26 = a2;
    v27 = a6;
    if ( (unsigned int)qword_18002B950(a6, v26) )
    {
      v28 = a6;
      v29 = (int *)(v50 + 20);
      v30 = (int *)(v50 + 16);
      if ( (unsigned int)FindOutInterfaceEntry(
                           (int)v25 + 64,
                           a6,
                           a7,
                           *(_DWORD *)(v50 + 16),
                           *(_DWORD *)(v50 + 20),
                           (__int64)&v45,
                           (__int64)&v44) )
      {
        v33 = a8;
        v34 = v44;
        if ( a8 )
        {
          *((_WORD *)v44 + 17) |= 0x8000u;
          *((_WORD *)v34 + 18) = 1;
        }
        else
        {
          *((_WORD *)v44 + 17) |= 0x4000u;
          *((_WORD *)v34 + 19) = 1;
        }
        goto LABEL_29;
      }
      v32 = v44;
      if ( !v44 )
        v32 = v25 + 16;
      v33 = a8;
      v18 = CreateOutInterfaceEntry((__int64)v32, a6, v31, *v30, *v29, a8, &v44);
      if ( !v18 )
      {
        ++v25[9];
LABEL_27:
        v28 = a6;
        goto LABEL_28;
      }
      goto LABEL_43;
    }
  }
  else
  {
    v27 = a6;
  }
  v29 = (int *)(v50 + 20);
  v30 = (int *)(v50 + 16);
  OutInterfaceEntry = FindOutInterfaceEntry(
                        (int)v25 + 48,
                        v27,
                        a7,
                        *(_DWORD *)(v50 + 16),
                        *(_DWORD *)(v50 + 20),
                        (__int64)&v45,
                        (__int64)&v44);
  v33 = a8;
  if ( !OutInterfaceEntry )
  {
    v36 = v44;
    if ( !v44 )
      v36 = v25 + 12;
    v18 = CreateOutInterfaceEntry((__int64)v36, a6, v31, *v30, *v29, a8, &v44);
    if ( !v18 )
    {
      ++v25[9];
      if ( v45 )
      {
        ++v25[10];
        InvokeJoinAlertCallbacks(v19, (__int64)v25, v44, a8, v50);
      }
      goto LABEL_27;
    }
LABEL_43:
    if ( (_DWORD)v46 )
      DeleteSourceEntry(v25);
    goto LABEL_45;
  }
  if ( !a8 )
  {
    v41 = v44;
    v42 = *((_WORD *)v44 + 17);
    *((_WORD *)v44 + 17) = v42 | 0x4000;
    *((_WORD *)v41 + 19) = 1;
    if ( (v42 & 0x4000) == 0 )
      goto LABEL_27;
    goto LABEL_56;
  }
  v37 = v44;
  v38 = *((_WORD *)v44 + 17);
  if ( v38 < 0 )
  {
LABEL_56:
    ReleaseWriteLock(v20);
    v18 = 0;
LABEL_57:
    ReleaseWriteLock((char *)qword_18002BA40 + v14 + 16);
    return v18;
  }
  *((_WORD *)v44 + 17) = v38 | 0x8000;
  *((_WORD *)v37 + 18) = 1;
  if ( *v30 == 10 || (v39 = v50, !*(_QWORD *)(v50 + 80)) )
  {
    v28 = a6;
    goto LABEL_29;
  }
  if ( qword_18002B8A8 )
  {
    v40 = (unsigned int)*v30;
    LOWORD(v57) = 0;
    FormatRRASErrorString(&v57, L"Invoked Local Join Alert for protocol %x, %x", v40, (unsigned int)*v29);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v57);
    v31 = a7;
    v39 = v50;
  }
  v28 = a6;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int))(v39 + 80))(
    v49,
    a5,
    v48,
    v52,
    a6,
    v31);
LABEL_28:
  v31 = a7;
LABEL_29:
  if ( v25[28] )
    AddInterfaceToSourceMfe(v19, (__int64)v25, v28, v31, *v30, *v29, v33, 0);
  if ( v48 )
  {
    if ( !v49 )
    {
      *v55 = 1;
      AddInterfaceToGroupMfe(v19, v28, a7, *v30, *v29, v33, 0, v56);
    }
    ReleaseWriteLock(v19 + 40);
    ReleaseWriteLock((char *)qword_18002BA40 + v14 + 16);
  }
  else
  {
    ReleaseWriteLock(v51);
    ReleaseWriteLock((char *)qword_18002BA40 + v14 + 16);
    *v55 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c1a8  push    rbp
0x18001c1aa  push    rbx
0x18001c1ab  push    rsi
0x18001c1ac  push    rdi
0x18001c1ad  push    r12
0x18001c1af  push    r13
0x18001c1b1  push    r14
0x18001c1b3  push    r15
0x18001c1b5  lea     rbp, [rsp-7B8h]
0x18001c1bd  sub     rsp, 8B8h
0x18001c1c4  mov     rax, cs:__security_cookie
0x18001c1cb  xor     rax, rsp
0x18001c1ce  mov     [rbp+7F0h+var_50], rax
0x18001c1d5  mov     rax, [rbp+7F0h+arg_48]
0x18001c1dc  xor     r15d, r15d
0x18001c1df  mov     rbx, [rbp+7F0h+arg_40]
0x18001c1e6  mov     edi, r8d
0x18001c1e9  mov     [rsp+8F0h+var_878], r8d
0x18001c1ee  mov     r12d, edx
0x18001c1f1  mov     [rsp+8F0h+var_894], edx
0x18001c1f5  mov     r8d, 7FCh; Size
0x18001c1fb  mov     [rsp+8F0h+var_888], rcx
0x18001c200  xor     edx, edx; Val
0x18001c202  lea     rcx, [rbp+7F0h+var_84C]; void *
0x18001c206  mov     [rbp+7F0h+var_860], rbx
0x18001c20a  mov     [rbp+7F0h+var_858], rax
0x18001c20e  mov     esi, r9d
0x18001c211  mov     [rsp+8F0h+var_898], r15d
0x18001c216  mov     [rsp+8F0h+var_8A8], r15d
0x18001c21b  mov     [rsp+8F0h+var_8A0], r15
0x18001c220  mov     [rsp+8F0h+var_880], r15
0x18001c225  mov     [rbp+7F0h+var_868], r15
0x18001c229  mov     [rbp+7F0h+var_870], r15
0x18001c22d  mov     [rsp+8F0h+var_8B0], r15
0x18001c232  mov     [rbp+7F0h+var_850], r15d
0x18001c236  mov     [rsp+8F0h+var_890], r9d
0x18001c23b  call    memset_0
0x18001c240  mov     [rbx], r15d
0x18001c243  lea     r14d, [r15+1]
0x18001c247  test    r12d, r12d
0x18001c24a  jz      short loc_18001C260
0x18001c24c  mov     ecx, cs:dword_18002B930
0x18001c252  xor     edx, edx
0x18001c254  dec     ecx
0x18001c256  mov     eax, r12d
0x18001c259  div     ecx
0x18001c25b  add     edx, r14d
0x18001c25e  jmp     short loc_18001C263
0x18001c260  mov     edx, r15d
0x18001c263  mov     rcx, cs:qword_18002BA40
0x18001c26a  mov     r13d, edx
0x18001c26d  add     rcx, 10h
0x18001c271  shl     r13, 5
0x18001c275  add     rcx, r13
0x18001c278  call    AcquireWriteLock
0x18001c27d  mov     rbx, cs:qword_18002BA40
0x18001c284  lea     r9, [rsp+8F0h+var_8A0]
0x18001c289  add     rbx, r13
0x18001c28c  mov     dword ptr [rsp+8F0h+var_8D0], r14d
0x18001c291  mov     rcx, rbx
0x18001c294  mov     edx, r12d
0x18001c297  call    FindGroupEntry
0x18001c29c  test    eax, eax
0x18001c29e  jnz     short loc_18001C2D7
0x18001c2a0  mov     rax, [rsp+8F0h+var_8A0]
0x18001c2a5  test    rax, rax
0x18001c2a8  jz      short loc_18001C2AE
0x18001c2aa  lea     rbx, [rax+10h]
0x18001c2ae  lea     r9, [rsp+8F0h+var_880]
0x18001c2b3  mov     r8d, edi
0x18001c2b6  mov     rcx, rbx
0x18001c2b9  call    CreateGroupEntry
0x18001c2be  mov     ebx, eax
0x18001c2c0  test    eax, eax
0x18001c2c2  jnz     loc_18001C6F2
0x18001c2c8  mov     r14, [rsp+8F0h+var_880]
0x18001c2cd  mov     [rsp+8F0h+var_898], 1
0x18001c2d5  jmp     short loc_18001C2DC
0x18001c2d7  mov     r14, [rsp+8F0h+var_8A0]
0x18001c2dc  lea     rbx, [r14+28h]
0x18001c2e0  mov     dword ptr [rsp+8F0h+var_8A0], r15d
0x18001c2e5  mov     rcx, rbx
0x18001c2e8  mov     [rsp+8F0h+var_880], rbx
0x18001c2ed  call    AcquireWriteLock
0x18001c2f2  test    esi, esi
0x18001c2f4  jz      short loc_18001C308
0x18001c2f6  mov     ecx, cs:dword_18002B934
0x18001c2fc  xor     edx, edx
0x18001c2fe  dec     ecx
0x18001c300  mov     eax, esi
0x18001c302  div     ecx
0x18001c304  inc     edx
0x18001c306  jmp     short loc_18001C30B
0x18001c308  mov     edx, r15d
0x18001c30b  mov     edi, edx
0x18001c30d  lea     r9, [rbp+7F0h+var_868]
0x18001c311  shl     rdi, 4
0x18001c315  mov     edx, esi
0x18001c317  mov     dword ptr [rsp+8F0h+var_8D0], 1
0x18001c31f  lea     rcx, [rdi+58h]
0x18001c323  add     rcx, r14
0x18001c326  call    FindSourceEntry
0x18001c32b  test    eax, eax
0x18001c32d  jnz     short loc_18001C37F
0x18001c32f  mov     rdx, [rbp+7F0h+var_868]
0x18001c333  lea     rax, [rbp+7F0h+var_870]
0x18001c337  mov     r9d, [rbp+7F0h+arg_20]
0x18001c33e  mov     r8d, esi
0x18001c341  mov     [rsp+8F0h+var_8D0], rax
0x18001c346  mov     rcx, r14
0x18001c349  test    rdx, rdx
0x18001c34c  jnz     short loc_18001C357
0x18001c34e  lea     rdx, [r14+58h]
0x18001c352  add     rdx, rdi
0x18001c355  jmp     short loc_18001C35B
0x18001c357  add     rdx, 10h
0x18001c35b  call    CreateSourceEntry
0x18001c360  mov     ebx, eax
0x18001c362  test    eax, eax
0x18001c364  jnz     loc_18001C5CD
0x18001c36a  mov     r15, [rbp+7F0h+var_870]
0x18001c36e  lea     eax, [rbx+1]
0x18001c371  add     [r14+30h], eax
0x18001c375  lea     rbx, [r14+28h]
0x18001c379  mov     dword ptr [rsp+8F0h+var_8A0], eax
0x18001c37d  jmp     short loc_18001C383
0x18001c37f  mov     r15, [rbp+7F0h+var_868]
0x18001c383  mov     rax, cs:qword_18002B950
0x18001c38a  test    rax, rax
0x18001c38d  jz      loc_18001C4F0
0x18001c393  mov     edx, r12d
0x18001c396  mov     r12d, [rbp+7F0h+arg_28]
0x18001c39d  mov     ecx, r12d
0x18001c3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3a5  test    eax, eax
0x18001c3a7  jz      loc_18001C4F7
0x18001c3ad  mov     rcx, [rsp+8F0h+var_888]
0x18001c3b2  lea     r12, [r15+40h]
0x18001c3b6  mov     ebx, [rbp+7F0h+arg_28]
0x18001c3bc  mov     edx, ebx
0x18001c3be  mov     r8d, [rbp+7F0h+arg_30]
0x18001c3c5  lea     rsi, [rcx+14h]
0x18001c3c9  mov     eax, [rsi]
0x18001c3cb  lea     rdi, [rcx+10h]
0x18001c3cf  mov     r9d, [rdi]
0x18001c3d2  lea     rcx, [rsp+8F0h+var_8B0]
0x18001c3d7  mov     [rsp+8F0h+var_8C0], rcx
0x18001c3dc  lea     rcx, [rsp+8F0h+var_8A8]
0x18001c3e1  mov     [rsp+8F0h+var_8C8], rcx
0x18001c3e6  mov     rcx, r12
0x18001c3e9  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x18001c3ed  call    FindOutInterfaceEntry
0x18001c3f2  xor     r9d, r9d
0x18001c3f5  test    eax, eax
0x18001c3f7  jnz     loc_18001C4B7
0x18001c3fd  mov     rcx, [rsp+8F0h+var_8B0]
0x18001c402  lea     rax, [rsp+8F0h+var_8B0]
0x18001c407  mov     r9d, [rdi]
0x18001c40a  test    rcx, rcx
0x18001c40d  mov     [rsp+8F0h+var_8C0], rax
0x18001c412  mov     edx, ebx
0x18001c414  mov     eax, [rsi]
0x18001c416  cmovz   rcx, r12
0x18001c41a  mov     r12d, [rbp+7F0h+arg_38]
0x18001c421  mov     dword ptr [rsp+8F0h+var_8C8], r12d
0x18001c426  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x18001c42a  call    CreateOutInterfaceEntry
0x18001c42f  xor     r9d, r9d
0x18001c432  mov     ebx, eax
0x18001c434  test    eax, eax
0x18001c436  jnz     loc_18001C5BB
0x18001c43c  lea     eax, [rbx+1]
0x18001c43f  add     [r15+24h], eax
0x18001c443  mov     ebx, [rbp+7F0h+arg_28]
0x18001c449  mov     r8d, [rbp+7F0h+arg_30]
0x18001c450  cmp     [r15+70h], r9d
0x18001c454  jz      short loc_18001C480
0x18001c456  mov     eax, [rsi]
0x18001c458  mov     rdx, r15
0x18001c45b  mov     [rsp+8F0h+var_8B8], r9
0x18001c460  mov     rcx, r14
0x18001c463  mov     dword ptr [rsp+8F0h+var_8C0], r12d
0x18001c468  mov     r9d, r8d
0x18001c46b  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x18001c46f  mov     r8d, ebx
0x18001c472  mov     eax, [rdi]
0x18001c474  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x18001c478  call    AddInterfaceToSourceMfe
0x18001c47d  xor     r9d, r9d
0x18001c480  cmp     [rsp+8F0h+var_894], r9d
0x18001c485  jnz     loc_18001C709
0x18001c48b  mov     rcx, [rsp+8F0h+var_880]
0x18001c490  call    ReleaseWriteLock
0x18001c495  mov     rcx, cs:qword_18002BA40
0x18001c49c  add     rcx, 10h
0x18001c4a0  add     rcx, r13
0x18001c4a3  call    ReleaseWriteLock
0x18001c4a8  mov     rax, [rbp+7F0h+var_860]
0x18001c4ac  mov     dword ptr [rax], 1
0x18001c4b2  jmp     loc_18001C763
0x18001c4b7  mov     r12d, [rbp+7F0h+arg_38]
0x18001c4be  mov     rax, [rsp+8F0h+var_8B0]
0x18001c4c3  test    r12d, r12d
0x18001c4c6  jz      short loc_18001C4DC
0x18001c4c8  mov     ecx, 8000h
0x18001c4cd  or      [rax+22h], cx
0x18001c4d1  mov     word ptr [rax+24h], 1
0x18001c4d7  jmp     loc_18001C450
0x18001c4dc  mov     ecx, 4000h
0x18001c4e1  or      [rax+22h], cx
0x18001c4e5  mov     word ptr [rax+26h], 1
0x18001c4eb  jmp     loc_18001C450
0x18001c4f0  mov     r12d, [rbp+7F0h+arg_28]
0x18001c4f7  mov     rcx, [rsp+8F0h+var_888]
0x18001c4fc  lea     rdx, [rsp+8F0h+var_8B0]
0x18001c501  mov     r8d, [rbp+7F0h+arg_30]
0x18001c508  mov     [rsp+8F0h+var_8C0], rdx
0x18001c50d  lea     rdx, [rsp+8F0h+var_8A8]
0x18001c512  mov     [rsp+8F0h+var_8C8], rdx
0x18001c517  mov     edx, r12d
0x18001c51a  lea     rsi, [rcx+14h]
0x18001c51e  mov     eax, [rsi]
0x18001c520  lea     rdi, [rcx+10h]
0x18001c524  mov     r9d, [rdi]
0x18001c527  lea     rcx, [r15+30h]
0x18001c52b  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x18001c52f  call    FindOutInterfaceEntry
0x18001c534  mov     r12d, [rbp+7F0h+arg_38]
0x18001c53b  xor     r9d, r9d
0x18001c53e  test    eax, eax
0x18001c540  jnz     loc_18001C5EE
0x18001c546  mov     rcx, [rsp+8F0h+var_8B0]
0x18001c54b  lea     rax, [rsp+8F0h+var_8B0]
0x18001c550  mov     r9d, [rdi]
0x18001c553  mov     edx, [rbp+7F0h+arg_28]
0x18001c559  mov     [rsp+8F0h+var_8C0], rax
0x18001c55e  mov     eax, [rsi]
0x18001c560  mov     dword ptr [rsp+8F0h+var_8C8], r12d
0x18001c565  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x18001c569  test    rcx, rcx
0x18001c56c  jnz     short loc_18001C572
0x18001c56e  lea     rcx, [r15+30h]
0x18001c572  call    CreateOutInterfaceEntry
0x18001c577  xor     r9d, r9d
0x18001c57a  mov     ebx, eax
0x18001c57c  test    eax, eax
0x18001c57e  jnz     short loc_18001C5BB
0x18001c580  lea     eax, [rbx+1]
0x18001c583  add     [r15+24h], eax
0x18001c587  cmp     [rsp+8F0h+var_8A8], r9d
0x18001c58c  jz      loc_18001C443
0x18001c592  add     [r15+28h], eax
0x18001c596  mov     r9d, r12d
0x18001c599  mov     rax, [rsp+8F0h+var_888]
0x18001c59e  mov     rdx, r15
0x18001c5a1  mov     r8, [rsp+8F0h+var_8B0]
0x18001c5a6  mov     rcx, r14
0x18001c5a9  mov     [rsp+8F0h+var_8D0], rax
0x18001c5ae  call    InvokeJoinAlertCallbacks
0x18001c5b3  xor     r9d, r9d
0x18001c5b6  jmp     loc_18001C443
0x18001c5bb  cmp     dword ptr [rsp+8F0h+var_8A0], r9d
0x18001c5c0  jz      short loc_18001C5CA
0x18001c5c2  mov     rcx, r15
0x18001c5c5  call    DeleteSourceEntry
0x18001c5ca  xor     r15d, r15d
0x18001c5cd  lea     rcx, [r14+28h]
0x18001c5d1  call    ReleaseWriteLock
0x18001c5d6  cmp     [rsp+8F0h+var_898], r15d
0x18001c5db  jz      loc_18001C6F2
0x18001c5e1  mov     rcx, r14
0x18001c5e4  call    DeleteGroupEntry
0x18001c5e9  jmp     loc_18001C6F2
0x18001c5ee  test    r12d, r12d
0x18001c5f1  jz      loc_18001C6BC
0x18001c5f7  mov     rdx, [rsp+8F0h+var_8B0]
0x18001c5fc  movzx   eax, word ptr [rdx+22h]
0x18001c600  test    ax, ax
0x18001c603  js      loc_18001C6E6
0x18001c609  or      ax, 8000h
0x18001c60d  mov     [rdx+22h], ax
0x18001c611  mov     word ptr [rdx+24h], 1
0x18001c617  cmp     dword ptr [rdi], 0Ah
0x18001c61a  jz      loc_18001C6B1
0x18001c620  mov     rax, [rsp+8F0h+var_888]
0x18001c625  cmp     [rax+50h], r9
0x18001c629  jz      loc_18001C6B1
0x18001c62f  cmp     cs:qword_18002B8A8, r9
0x18001c636  jz      short loc_18001C67D
0x18001c638  mov     r8d, [rdi]
0x18001c63b  lea     rdx, aInvokedLocalJo; "Invoked Local Join Alert for protocol %"...
0x18001c642  mov     word ptr [rbp+7F0h+var_850], r9w
0x18001c647  lea     rcx, [rbp+7F0h+var_850]
0x18001c64b  mov     r9d, [rsi]
0x18001c64e  call    FormatRRASErrorString
0x18001c653  mov     rdx, cs:qword_18002B8A8
0x18001c65a  lea     r8, [rbp+7F0h+var_850]
0x18001c65e  mov     rcx, cs:gMgmEtwContext
0x18001c665  mov     rax, cs:gMgmTemplateFunc
0x18001c66c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
