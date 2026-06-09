# SchEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)

- ea: `0x18005f1e4`
- end: `0x18005f8b2`
- name: `?SchEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ`
- size: `1742`
- prototype: `unsigned int(const struct _EVENT_DESCRIPTOR *, unsigned __int16 *, ...)`
- caller_count: `36`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b620`
- `0x1800106e0`
- `0x1800112c0`
- `0x180014d70`
- `0x1800154b0`
- `0x180015c60`
- `0x1800160a0`
- `0x180016300`
- `0x1800166b0`
- `0x180017f00`
- `0x18001aecc`
- `0x18001c060`
- `0x180020450`
- `0x1800214f0`
- `0x180022aa0`
- `0x180025c38`
- `0x18002d780`
- `0x18003dbe0`
- `0x180042a50`
- `0x18004a4fc`
- `0x18004a994`
- `0x180056c68`
- `0x1800580e8`
- `0x18005d974`
- `0x18005ecb0`
- `0x18005ed20`
- `0x18005edb8`
- `0x18005ee58`
- `0x18005eea4`
- `0x18005eef0`
- `0x18005ef44`
- `0x18005eff0`
- `0x180062de8`
- `0x180072580`
- `0x18007ce4c`
- `0x180084668`

## callees

- `0x18001db60`
- `0x180021e64`
- `0x1800597b0`
- `0x18005a160`
- `0x18005f160`
- `0x18005f1e4`
- `0x18005f91c`
- `0x1800889d0`
- `0x180091010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005f5ba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005f5ba`
- `ntdll!EtwEventWrite` at `0x18005f7e0`
- `ntdll!EtwEventWrite` at `0x18005f7e0`

## pseudocode

```c
__int64 SchEventWrite(const struct _EVENT_DESCRIPTOR *a1, unsigned __int16 *a2, ...)
{
  unsigned int v2; // r15d
  const struct _EVENT_DESCRIPTOR *v3; // r12
  int *v4; // rdi
  int *v5; // rsi
  unsigned __int64 i; // r14
  unsigned int v7; // ebx
  __int64 v8; // rax
  unsigned __int64 v9; // r12
  va_list v10; // r13
  unsigned int v11; // r8d
  __int64 v12; // rbx
  __int64 v13; // rsi
  size_t v14; // rbx
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  int *v19; // rax
  size_t v20; // rbx
  __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  int *v25; // rax
  unsigned int v26; // eax
  const unsigned __int16 **v27; // r12
  int *v28; // rbx
  unsigned __int64 v29; // r15
  unsigned __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  void *v33; // rsp
  void *v34; // rsp
  int *v35; // rax
  unsigned int v36; // ecx
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rcx
  void *v40; // rbx
  DWORD LengthSid; // eax
  __int64 v42; // rcx
  __int64 v43; // rbx
  __int64 *v44; // rax
  int v45; // ebx
  int *v46; // rax
  int v47; // ebx
  int *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rcx
  unsigned int v51; // eax
  __int64 v52; // rcx
  _BYTE v54[16]; // [rsp-10h] [rbp-40h] BYREF
  _DWORD v55[8]; // [rsp+0h] [rbp-30h] BYREF
  int v56; // [rsp+20h] [rbp-10h] BYREF
  __int64 v57; // [rsp+28h] [rbp-8h] BYREF
  int v58; // [rsp+30h] [rbp+0h] BYREF
  unsigned int v59; // [rsp+38h] [rbp+8h] BYREF
  unsigned __int64 v60; // [rsp+40h] [rbp+10h]
  const struct _EVENT_DESCRIPTOR *v61; // [rsp+48h] [rbp+18h]
  unsigned __int16 *v62; // [rsp+B8h] [rbp+88h]
  va_list va; // [rsp+C0h] [rbp+90h] BYREF

  va_start(va, a2);
  v62 = a2;
  v2 = 0;
  v61 = a1;
  v3 = a1;
  v60 = 0;
  v4 = 0;
  v5 = 0;
  i = 0;
  if ( !g_RegistrationHandle )
  {
    v7 = SchInitializeEvents();
    if ( v7 )
      goto LABEL_106;
    a2 = v62;
  }
  v58 = 0;
  if ( !a2 )
    goto LABEL_102;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = (unsigned int)v8;
  va_copy(v10, va);
  v11 = 0;
  if ( (unsigned int)v8 > 0x7FuLL )
    v9 = 127;
  v60 = v9;
  while ( v11 < v9 )
  {
    if ( a2[v11] == 98 )
    {
      v2 += 2;
    }
    else
    {
      if ( a2[v11] != 100 && a2[v11] != 112 && a2[v11] != 115 && (unsigned int)a2[v11] - 116 > 1 )
        return 87;
      ++v2;
    }
    v58 = v2;
    ++v11;
  }
  v12 = v2;
  v13 = v2;
  v2 = 0;
  v14 = 16 * v12;
  if ( !v14
    || v14 > g_ulMaxStackAllocSize
    || v14 + g_ulAdditionalProbeSize + 8 < v14
    || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)() )
  {
    goto LABEL_120;
  }
  v15 = v14 + 23;
  if ( v14 + 23 <= v14 + 8 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
  v17 = alloca(v16);
  v18 = alloca(v16);
  v4 = &v58;
  if ( v55 == (_DWORD *)-48LL || (v58 = 1801679955, (v4 = (int *)&v59) == 0) )
  {
LABEL_120:
    if ( v14 + 8 >= v14 )
    {
      v19 = (int *)((__int64 (*)(void))g_pfnAllocate)();
      v4 = v19;
      if ( v19 )
      {
        *v19 = 1885431112;
        v4 = v19 + 2;
      }
    }
  }
  if ( !v4 )
    return 8;
  memset_0(v4, 0, v14);
  v20 = 8 * v13;
  v5 = 0;
  if ( !v20
    || v20 > g_ulMaxStackAllocSize
    || v20 + g_ulAdditionalProbeSize + 8 < v20
    || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)() )
  {
    goto LABEL_121;
  }
  v21 = v20 + 23;
  if ( v20 + 23 <= v20 + 8 )
    v21 = 0xFFFFFFFFFFFFFF0LL;
  v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
  v23 = alloca(v22);
  v24 = alloca(v22);
  v5 = &v58;
  if ( v55 == (_DWORD *)-48LL || (v58 = 1801679955, (v5 = (int *)&v59) == 0) )
  {
LABEL_121:
    if ( v20 + 8 >= v20 )
    {
      v25 = (int *)((__int64 (*)(void))g_pfnAllocate)();
      v5 = v25;
      if ( v25 )
      {
        *v25 = 1885431112;
        v5 = v25 + 2;
      }
    }
  }
  if ( !v5 )
  {
    v7 = 8;
    goto LABEL_115;
  }
  memset_0(v5, 0, v20);
  v26 = 0;
  for ( i = 0; ; ++i )
  {
    v59 = v26;
    if ( v26 >= v9 )
      break;
    switch ( v62[v26] )
    {
      case 'b':
        v47 = *(_DWORD *)v10;
        if ( (unsigned __int64)g_ulMaxStackAllocSize < 4
          || (unsigned __int64)(g_ulAdditionalProbeSize + 12) < 4
          || !(unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 12)
          || v54 == (_BYTE *)-48LL
          || (v48 = (int *)&v57, v56 = 1801679955, &v56 == (int *)-8LL) )
        {
          v48 = (int *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(12);
          if ( v48 )
          {
            *v48 = 1885431112;
            v48 += 2;
          }
        }
        *(_QWORD *)&v5[2 * i] = v48;
        if ( !v48 )
        {
LABEL_99:
          v7 = 8;
          goto LABEL_106;
        }
        *v48 = v47;
        v49 = *(_QWORD *)&v5[2 * i];
        v50 = 2 * i++;
        v10 += 16;
        *(_QWORD *)&v4[2 * v50] = v49;
        *(_QWORD *)&v4[2 * v50 + 2] = 4;
        v38 = *((_QWORD *)v10 - 1);
        v39 = 2 * i;
        v4[2 * v39 + 2] = v47;
        v4[2 * v39 + 3] = 0;
        goto LABEL_97;
      case 'd':
        v45 = *(_DWORD *)v10;
        v10 += 8;
        if ( (unsigned __int64)g_ulMaxStackAllocSize < 4
          || (unsigned __int64)(g_ulAdditionalProbeSize + 12) < 4
          || !(unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 12)
          || v54 == (_BYTE *)-48LL
          || (v46 = (int *)&v57, v56 = 1801679955, &v56 == (int *)-8LL) )
        {
          v46 = (int *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(12);
          if ( v46 )
          {
            *v46 = 1885431112;
            v46 += 2;
          }
        }
        *(_QWORD *)&v5[2 * i] = v46;
        if ( !v46 )
          goto LABEL_99;
        *v46 = v45;
        v38 = *(_QWORD *)&v5[2 * i];
        v39 = 2 * i;
        *(_QWORD *)&v4[4 * i + 2] = 4;
        goto LABEL_97;
      case 'p':
        v43 = *(_QWORD *)v10;
        v10 += 8;
        if ( (unsigned __int64)g_ulMaxStackAllocSize < 8
          || (unsigned __int64)(g_ulAdditionalProbeSize + 16) < 8
          || !(unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 16)
          || v54 == (_BYTE *)-48LL
          || (v44 = &v57, v56 = 1801679955, &v56 == (int *)-8LL) )
        {
          v44 = (__int64 *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(16);
          if ( v44 )
            *(_DWORD *)v44++ = 1885431112;
        }
        *(_QWORD *)&v5[2 * i] = v44;
        if ( !v44 )
          goto LABEL_99;
        *v44 = v43;
        v38 = *(_QWORD *)&v5[2 * i];
        v39 = 2 * i;
        *(_QWORD *)&v4[4 * i + 2] = 8;
        goto LABEL_97;
      case 's':
        v40 = *(void **)v10;
        v10 += 8;
        LengthSid = GetLengthSid(v40);
        v42 = 2 * i;
        *(_QWORD *)&v4[2 * v42] = v40;
        v4[2 * v42 + 2] = LengthSid;
        v4[2 * v42 + 3] = 0;
        goto LABEL_98;
      case 't':
        v38 = *(_QWORD *)v10;
        v10 += 8;
        v39 = 2 * i;
        *(_QWORD *)&v4[4 * i + 2] = 16;
LABEL_97:
        *(_QWORD *)&v4[2 * v39] = v38;
        goto LABEL_98;
    }
    if ( v62[v26] != 117 )
    {
      v7 = 87;
      goto LABEL_106;
    }
    v27 = *(const unsigned __int16 ***)v10;
    v10 += 8;
    v28 = 0;
    v29 = *(unsigned __int16 *)v27 + 2LL;
    if ( v29 <= g_ulMaxStackAllocSize )
    {
      v30 = v29 + g_ulAdditionalProbeSize + 8;
      if ( v30 >= v29 )
      {
        if ( (unsigned int)VerifyStackAvailable(v30) )
        {
          v31 = v29 + 23;
          if ( v29 + 23 <= v29 + 8 )
            v31 = 0xFFFFFFFFFFFFFF0LL;
          v32 = v31 & 0xFFFFFFFFFFFFFFF0uLL;
          v33 = alloca(v32);
          v34 = alloca(v32);
          v28 = &v58;
          if ( v55 != (_DWORD *)-48LL )
          {
            v58 = 1801679955;
            v28 = (int *)&v59;
            if ( &v59 )
              goto LABEL_64;
          }
        }
      }
    }
    if ( v29 + 8 < v29 )
    {
LABEL_64:
      v2 = 0;
    }
    else
    {
      v35 = (int *)((__int64 (__fastcall *)(unsigned __int64))g_pfnAllocate)(v29 + 8);
      v2 = 0;
      v28 = v35;
      if ( v35 )
      {
        *v35 = 1885431112;
        v28 = v35 + 2;
      }
    }
    *(_QWORD *)&v5[2 * i] = v28;
    if ( !v28 )
      goto LABEL_99;
    memset_0(v28, 0, *(unsigned __int16 *)v27 + 2LL);
    v7 = RtlStringCchCopyNW(
           *(unsigned __int16 **)&v5[2 * i],
           ((unsigned __int64)*(unsigned __int16 *)v27 >> 1) + 1,
           v27[1],
           (unsigned __int64)*(unsigned __int16 *)v27 >> 1);
    if ( v7 )
      goto LABEL_106;
    v36 = *(unsigned __int16 *)v27 + 2;
    v9 = v60;
    v37 = 2 * i;
    *(_QWORD *)&v4[2 * v37] = *(_QWORD *)&v5[2 * i];
    *(_QWORD *)&v4[2 * v37 + 2] = v36;
LABEL_98:
    v26 = v59 + 1;
  }
  v2 = v58;
  v3 = v61;
LABEL_102:
  v51 = EtwEventWrite(g_RegistrationHandle, v3, v2, v4, v56);
  v2 = 0;
  v7 = v51;
  if ( v51 && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9cc880ee923835bef0ce0974c4127801_Traceguids, v3->Id, v51);
LABEL_106:
  if ( i )
  {
    do
    {
      v52 = *(_QWORD *)&v5[2 * v2];
      if ( v52 && *(_DWORD *)(v52 - 8) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      ++v2;
    }
    while ( v2 < i );
  }
  if ( v5 && *(v5 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v4 )
  {
LABEL_115:
    if ( *(v4 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v7;
}

```

## disassembly

```asm
0x18005f1e4  mov     [rsp-8+arg_8], rdx
0x18005f1e9  mov     [rsp-8+arg_10], r8
0x18005f1ee  mov     [rsp-8+arg_18], r9
0x18005f1f3  push    rbp
0x18005f1f4  push    rbx
0x18005f1f5  push    rsi
0x18005f1f6  push    rdi
0x18005f1f7  push    r12
0x18005f1f9  push    r13
0x18005f1fb  push    r14
0x18005f1fd  push    r15
0x18005f1ff  sub     rsp, 68h
0x18005f203  lea     rbp, [rsp+30h]
0x18005f208  mov     rax, cs:__security_cookie
0x18005f20f  xor     rax, rbp
0x18005f212  mov     [rbp+70h+var_48], rax
0x18005f216  xor     r15d, r15d
0x18005f219  mov     [rbp+70h+var_58], rcx
0x18005f21d  cmp     cs:?g_RegistrationHandle@@3_KA, r15; unsigned __int64 g_RegistrationHandle
0x18005f224  mov     r12, rcx
0x18005f227  mov     [rbp+70h+var_60], r15
0x18005f22b  mov     edi, r15d
0x18005f22e  mov     esi, r15d
0x18005f231  mov     r14d, r15d
0x18005f234  jnz     short loc_18005F24C
0x18005f236  call    ?SchInitializeEvents@@YAKXZ; SchInitializeEvents(void)
0x18005f23b  mov     ebx, eax
0x18005f23d  test    eax, eax
0x18005f23f  jnz     loc_18005F825
0x18005f245  mov     rdx, [rbp+70h+arg_8]
0x18005f24c  xor     ecx, ecx
0x18005f24e  mov     [rbp+70h+var_70], r15d
0x18005f252  test    rdx, rdx
0x18005f255  jz      loc_18005F7D0
0x18005f25b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005f25f  inc     rax
0x18005f262  cmp     [rdx+rax*2], cx
0x18005f266  jnz     short loc_18005F25F
0x18005f268  mov     r12d, eax
0x18005f26b  lea     r13, [rbp+70h+arg_10]
0x18005f272  mov     eax, 7Fh
0x18005f277  mov     r8d, ecx
0x18005f27a  cmp     r12, rax
0x18005f27d  cmova   r12d, eax
0x18005f281  mov     [rbp+70h+var_60], r12
0x18005f285  mov     eax, r8d
0x18005f288  cmp     rax, r12
0x18005f28b  jnb     short loc_18005F2CB
0x18005f28d  movzx   ecx, word ptr [rdx+rax*2]
0x18005f291  sub     ecx, 62h ; 'b'
0x18005f294  jz      short loc_18005F2B4
0x18005f296  sub     ecx, 2
0x18005f299  jz      short loc_18005F2AF
0x18005f29b  sub     ecx, 0Ch
0x18005f29e  jz      short loc_18005F2AF
0x18005f2a0  sub     ecx, 3
0x18005f2a3  jz      short loc_18005F2AF
0x18005f2a5  sub     ecx, 1
0x18005f2a8  jz      short loc_18005F2AF
0x18005f2aa  cmp     ecx, 1
0x18005f2ad  jnz     short loc_18005F2C1
0x18005f2af  inc     r15d
0x18005f2b2  jmp     short loc_18005F2B8
0x18005f2b4  add     r15d, 2
0x18005f2b8  mov     [rbp+70h+var_70], r15d
0x18005f2bc  inc     r8d
0x18005f2bf  jmp     short loc_18005F285
0x18005f2c1  mov     ebx, 57h ; 'W'
0x18005f2c6  jmp     loc_18005F893
0x18005f2cb  mov     ebx, r15d
0x18005f2ce  mov     esi, r15d
0x18005f2d1  xor     r15d, r15d
0x18005f2d4  shl     rbx, 4
0x18005f2d8  lea     r14d, [r15+8]
0x18005f2dc  test    rbx, rbx
0x18005f2df  jz      short loc_18005F340
0x18005f2e1  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005f2e8  ja      short loc_18005F340
0x18005f2ea  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005f2f1  add     rcx, r14
0x18005f2f4  add     rcx, rbx
0x18005f2f7  cmp     rcx, rbx
0x18005f2fa  jb      short loc_18005F340
0x18005f2fc  call    VerifyStackAvailable
0x18005f301  test    eax, eax
0x18005f303  jz      short loc_18005F340
0x18005f305  lea     rax, [rbx+8]
0x18005f309  lea     rcx, [rax+0Fh]
0x18005f30d  cmp     rcx, rax
0x18005f310  ja      short loc_18005F31C
0x18005f312  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005f31c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005f320  mov     rax, rcx
0x18005f323  call    _alloca_probe
0x18005f328  sub     rsp, rcx
0x18005f32b  lea     rdi, [rsp+0A0h+var_70]
0x18005f330  test    rdi, rdi
0x18005f333  jz      short loc_18005F340
0x18005f335  mov     dword ptr [rdi], 6B637453h
0x18005f33b  add     rdi, r14
0x18005f33e  jnz     short loc_18005F366
0x18005f340  lea     rcx, [rbx+8]
0x18005f344  cmp     rcx, rbx
0x18005f347  jb      short loc_18005F366
0x18005f349  mov     rax, cs:g_pfnAllocate
0x18005f350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f355  mov     rdi, rax
0x18005f358  test    rax, rax
0x18005f35b  jz      short loc_18005F366
0x18005f35d  mov     dword ptr [rax], 70616548h
0x18005f363  add     rdi, r14
0x18005f366  test    rdi, rdi
0x18005f369  jnz     short loc_18005F373
0x18005f36b  mov     ebx, r14d
0x18005f36e  jmp     loc_18005F893
0x18005f373  mov     r8, rbx; Size
0x18005f376  xor     edx, edx; Val
0x18005f378  mov     rcx, rdi; void *
0x18005f37b  call    memset_0
0x18005f380  lea     rbx, ds:0[rsi*8]
0x18005f388  mov     rsi, r15
0x18005f38b  test    rbx, rbx
0x18005f38e  jz      short loc_18005F3EF
0x18005f390  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005f397  ja      short loc_18005F3EF
0x18005f399  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005f3a0  add     rcx, r14
0x18005f3a3  add     rcx, rbx
0x18005f3a6  cmp     rcx, rbx
0x18005f3a9  jb      short loc_18005F3EF
0x18005f3ab  call    VerifyStackAvailable
0x18005f3b0  test    eax, eax
0x18005f3b2  jz      short loc_18005F3EF
0x18005f3b4  lea     rax, [rbx+8]
0x18005f3b8  lea     rcx, [rax+0Fh]
0x18005f3bc  cmp     rcx, rax
0x18005f3bf  ja      short loc_18005F3CB
0x18005f3c1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005f3cb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005f3cf  mov     rax, rcx
0x18005f3d2  call    _alloca_probe
0x18005f3d7  sub     rsp, rcx
0x18005f3da  lea     rsi, [rsp+0A0h+var_70]
0x18005f3df  test    rsi, rsi
0x18005f3e2  jz      short loc_18005F3EF
0x18005f3e4  mov     dword ptr [rsi], 6B637453h
0x18005f3ea  add     rsi, r14
0x18005f3ed  jnz     short loc_18005F415
0x18005f3ef  lea     rcx, [rbx+8]
0x18005f3f3  cmp     rcx, rbx
0x18005f3f6  jb      short loc_18005F415
0x18005f3f8  mov     rax, cs:g_pfnAllocate
0x18005f3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f404  mov     rsi, rax
0x18005f407  test    rax, rax
0x18005f40a  jz      short loc_18005F415
0x18005f40c  mov     dword ptr [rax], 70616548h
0x18005f412  add     rsi, r14
0x18005f415  test    rsi, rsi
0x18005f418  jnz     short loc_18005F422
0x18005f41a  mov     ebx, r14d
0x18005f41d  jmp     loc_18005F87B
0x18005f422  mov     r8, rbx; Size
0x18005f425  xor     edx, edx; Val
0x18005f427  mov     rcx, rsi; void *
0x18005f42a  call    memset_0
0x18005f42f  mov     eax, r15d
0x18005f432  mov     r14, r15
0x18005f435  mov     ecx, eax
0x18005f437  mov     [rbp+70h+var_68], eax
0x18005f43a  cmp     rcx, r12
0x18005f43d  jnb     loc_18005F7C8
0x18005f443  mov     rax, [rbp+70h+arg_8]
0x18005f44a  movzx   ecx, word ptr [rax+rcx*2]
0x18005f44e  sub     ecx, 62h ; 'b'
0x18005f451  jz      loc_18005F703
0x18005f457  sub     ecx, 2
0x18005f45a  jz      loc_18005F66E
0x18005f460  sub     ecx, 0Ch
0x18005f463  jz      loc_18005F5D8
0x18005f469  sub     ecx, 3
0x18005f46c  jz      loc_18005F5AF
0x18005f472  sub     ecx, 1
0x18005f475  jz      loc_18005F593
0x18005f47b  cmp     ecx, 1
0x18005f47e  jnz     loc_18005F7C1
0x18005f484  mov     r12, [r13+0]
0x18005f488  add     r13, 8
0x18005f48c  xor     ebx, ebx
0x18005f48e  movzx   r15d, word ptr [r12]
0x18005f493  add     r15, 2
0x18005f497  cmp     r15, cs:g_ulMaxStackAllocSize
0x18005f49e  ja      short loc_18005F4F8
0x18005f4a0  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005f4a7  add     rcx, 8
0x18005f4ab  add     rcx, r15
0x18005f4ae  cmp     rcx, r15
0x18005f4b1  jb      short loc_18005F4F8
0x18005f4b3  call    VerifyStackAvailable
0x18005f4b8  test    eax, eax
0x18005f4ba  jz      short loc_18005F4F8
0x18005f4bc  lea     rax, [r15+8]
0x18005f4c0  lea     rcx, [rax+0Fh]
0x18005f4c4  cmp     rcx, rax
0x18005f4c7  ja      short loc_18005F4D3
0x18005f4c9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005f4d3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005f4d7  mov     rax, rcx
0x18005f4da  call    _alloca_probe
0x18005f4df  sub     rsp, rcx
0x18005f4e2  lea     rbx, [rsp+0A0h+var_70]
0x18005f4e7  test    rbx, rbx
0x18005f4ea  jz      short loc_18005F4F8
0x18005f4ec  mov     dword ptr [rbx], 6B637453h
0x18005f4f2  add     rbx, 8
0x18005f4f6  jnz     short loc_18005F524
0x18005f4f8  lea     rcx, [r15+8]
0x18005f4fc  cmp     rcx, r15
0x18005f4ff  jb      short loc_18005F524
0x18005f501  mov     rax, cs:g_pfnAllocate
0x18005f508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f50d  xor     r15d, r15d
0x18005f510  mov     rbx, rax
0x18005f513  test    rax, rax
0x18005f516  jz      short loc_18005F527
0x18005f518  mov     dword ptr [rax], 70616548h
0x18005f51e  add     rbx, 8
0x18005f522  jmp     short loc_18005F527
0x18005f524  xor     r15d, r15d
0x18005f527  mov     [rsi+r14*8], rbx
0x18005f52b  test    rbx, rbx
0x18005f52e  jz      loc_18005F7BA
0x18005f534  movzx   r8d, word ptr [r12]
0x18005f539  xor     edx, edx; Val
0x18005f53b  add     r8, 2; Size
0x18005f53f  mov     rcx, rbx; void *
0x18005f542  call    memset_0
0x18005f547  movzx   r9d, word ptr [r12]
0x18005f54c  mov     r8, [r12+8]; unsigned __int16 *
0x18005f551  mov     rcx, [rsi+r14*8]; unsigned __int16 *
0x18005f555  shr     r9, 1; unsigned __int64
0x18005f558  lea     rdx, [r9+1]; unsigned __int64
0x18005f55c  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18005f561  mov     ebx, eax
0x18005f563  test    eax, eax
0x18005f565  jnz     loc_18005F825
0x18005f56b  movzx   ecx, word ptr [r12]
0x18005f570  mov     rdx, r14
0x18005f573  mov     rax, [rsi+r14*8]
0x18005f577  add     ecx, 2
0x18005f57a  mov     r12, [rbp+70h+var_60]
0x18005f57e  add     rdx, rdx
0x18005f581  mov     [rdi+rdx*8], rax
0x18005f585  mov     [rdi+rdx*8+8], ecx
0x18005f589  mov     [rdi+rdx*8+0Ch], r15d
0x18005f58e  jmp     loc_18005F7AD
0x18005f593  mov     rax, [r13+0]
0x18005f597  add     r13, 8
0x18005f59b  mov     rcx, r14
0x18005f59e  add     rcx, rcx
0x18005f5a1  mov     qword ptr [rdi+rcx*8+8], 10h
0x18005f5aa  jmp     loc_18005F7A9
0x18005f5af  mov     rbx, [r13+0]
0x18005f5b3  add     r13, 8
0x18005f5b7  mov     rcx, rbx; pSid
0x18005f5ba  call    cs:__imp_GetLengthSid
0x18005f5c0  mov     rcx, r14
0x18005f5c3  add     rcx, rcx
0x18005f5c6  mov     [rdi+rcx*8], rbx
0x18005f5ca  mov     [rdi+rcx*8+8], eax
0x18005f5ce  mov     [rdi+rcx*8+0Ch], r15d
0x18005f5d3  jmp     loc_18005F7AD
0x18005f5d8  mov     rbx, [r13+0]
0x18005f5dc  add     r13, 8
0x18005f5e0  cmp     cs:g_ulMaxStackAllocSize, 8
0x18005f5e8  jb      short loc_18005F626
0x18005f5ea  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005f5f1  add     rcx, 10h
0x18005f5f5  cmp     rcx, 8
0x18005f5f9  jb      short loc_18005F626
0x18005f5fb  call    VerifyStackAvailable
0x18005f600  test    eax, eax
0x18005f602  jz      short loc_18005F626
0x18005f604  mov     eax, [rsp+0A0h+var_A0]
0x18005f607  sub     rsp, 10h
0x18005f60b  lea     rcx, [rsp+0B0h+var_80]
0x18005f610  mov     eax, [rcx]
0x18005f612  test    rcx, rcx
0x18005f615  jz      short loc_18005F626
0x18005f617  lea     rax, [rcx+8]
0x18005f61b  mov     dword ptr [rcx], 6B637453h
0x18005f621  test    rax, rax
0x18005f624  jnz     short loc_18005F646
0x18005f626  mov     rax, cs:g_pfnAllocate
0x18005f62d  mov     ecx, 10h
0x18005f632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f637  test    rax, rax
0x18005f63a  jz      short loc_18005F646
0x18005f63c  mov     dword ptr [rax], 70616548h
0x18005f642  add     rax, 8
  ... truncated ...
```
