# DestroytLineClient

- ea: `0x180005378`
- end: `0x180005b1d`
- name: `DestroytLineClient`
- size: `1957`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180004cd0`
- `0x180004fcc`
- `0x1800081d0`
- `0x1800330a8`

## callees

- `0x180001600`
- `0x180004a94`
- `0x180004cd0`
- `0x180005378`
- `0x18001bd10`
- `0x18001f5ac`
- `0x1800281f0`
- `0x18002c8d4`
- `0x18003ce2c`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e3b4`
- `0x180040010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800057dd`
- `KERNEL32!Sleep` at `0x1800057dd`
- `KERNEL32!ReleaseMutex` at `0x1800055e8`
- `KERNEL32!ReleaseMutex` at `0x18000569a`
- `KERNEL32!ReleaseMutex` at `0x180005782`
- `KERNEL32!ReleaseMutex` at `0x1800057c4`
- `KERNEL32!ReleaseMutex` at `0x1800057d2`
- `KERNEL32!ReleaseMutex` at `0x1800058e8`
- `KERNEL32!ReleaseMutex` at `0x18000592d`
- `KERNEL32!ReleaseMutex` at `0x1800059c3`
- `KERNEL32!ReleaseMutex` at `0x1800059d6`
- `KERNEL32!ReleaseMutex` at `0x1800059fe`
- `KERNEL32!ReleaseMutex` at `0x180005a0c`
- `KERNEL32!ReleaseMutex` at `0x1800055e8`
- `KERNEL32!ReleaseMutex` at `0x18000569a`
- `KERNEL32!ReleaseMutex` at `0x180005782`
- `KERNEL32!ReleaseMutex` at `0x1800057c4`
- `KERNEL32!ReleaseMutex` at `0x1800057d2`
- `KERNEL32!ReleaseMutex` at `0x1800058e8`
- `KERNEL32!ReleaseMutex` at `0x18000592d`
- `KERNEL32!ReleaseMutex` at `0x1800059c3`
- `KERNEL32!ReleaseMutex` at `0x1800059d6`
- `KERNEL32!ReleaseMutex` at `0x1800059fe`
- `KERNEL32!ReleaseMutex` at `0x180005a0c`
- `KERNEL32!WaitForSingleObject` at `0x180005522`
- `KERNEL32!WaitForSingleObject` at `0x180005553`
- `KERNEL32!WaitForSingleObject` at `0x1800055b3`
- `KERNEL32!WaitForSingleObject` at `0x18000566b`
- `KERNEL32!WaitForSingleObject` at `0x180005752`
- `KERNEL32!WaitForSingleObject` at `0x1800057ee`
- `KERNEL32!WaitForSingleObject` at `0x1800057fc`
- `KERNEL32!WaitForSingleObject` at `0x1800058f9`
- `KERNEL32!WaitForSingleObject` at `0x18000593b`
- `KERNEL32!WaitForSingleObject` at `0x180005522`
- `KERNEL32!WaitForSingleObject` at `0x180005553`
- `KERNEL32!WaitForSingleObject` at `0x1800055b3`
- `KERNEL32!WaitForSingleObject` at `0x18000566b`
- `KERNEL32!WaitForSingleObject` at `0x180005752`
- `KERNEL32!WaitForSingleObject` at `0x1800057ee`
- `KERNEL32!WaitForSingleObject` at `0x1800057fc`
- `KERNEL32!WaitForSingleObject` at `0x1800058f9`
- `KERNEL32!WaitForSingleObject` at `0x18000593b`
- `KERNEL32!LeaveCriticalSection` at `0x180005490`
- `KERNEL32!LeaveCriticalSection` at `0x18000550d`
- `KERNEL32!LeaveCriticalSection` at `0x180005490`
- `KERNEL32!LeaveCriticalSection` at `0x18000550d`
- `KERNEL32!EnterCriticalSection` at `0x18000546e`
- `KERNEL32!EnterCriticalSection` at `0x1800054be`
- `KERNEL32!EnterCriticalSection` at `0x18000546e`
- `KERNEL32!EnterCriticalSection` at `0x1800054be`

## string_xrefs

- `0x180005adf`: `DestroytLineClient: WaitForExclLineClientAccess failed!`

## pseudocode

```c
void __fastcall DestroytLineClient(unsigned int a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  unsigned __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rcx
  void *v7; // rsi
  unsigned __int64 i; // rbx
  __int64 v9; // r15
  unsigned __int64 v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  void (__fastcall *v15)(_QWORD, _DWORD *); // rax
  unsigned int v16; // r13d
  int v17; // r15d
  void (__fastcall *v18)(_QWORD, _QWORD); // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 *v22; // r13
  int v23; // ecx
  unsigned int v24; // r13d
  __int64 j; // rax
  void (__fastcall *v26)(_QWORD, _QWORD); // rax
  int v27; // r15d
  unsigned int v28; // ecx
  unsigned int v29; // edx
  __int64 v30; // rax
  unsigned int v31; // r13d
  int v32; // r13d
  int v33; // r15d
  int v34; // esi
  __int64 v35; // rsi
  __int64 v36; // rbx
  __int64 v37; // rcx
  void *v38; // rcx
  int v39; // [rsp+30h] [rbp-C8h]
  HANDLE hMutex; // [rsp+40h] [rbp-B8h]
  unsigned int v42; // [rsp+50h] [rbp-A8h]
  int v43; // [rsp+50h] [rbp-A8h]
  unsigned int v44; // [rsp+58h] [rbp-A0h]
  __int64 v45; // [rsp+70h] [rbp-88h]
  __int64 v46; // [rsp+98h] [rbp-60h]
  __int64 (__fastcall *v47)(__int64, _QWORD, _QWORD); // [rsp+A0h] [rbp-58h]
  _DWORD v48[2]; // [rsp+B0h] [rbp-48h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-40h]
  int v50; // [rsp+C0h] [rbp-38h]

  TRACELogPrint(524290, "DestroytLineClient: enter, hLine=x%x", a1);
  v3 = ReferenceObject(v2, a1, 0);
  v4 = v3;
  if ( !v3 )
    return;
  if ( !(unsigned int)WaitForExclusiveLineClientAccess(v3) )
  {
    DereferenceObject(v5, a1, 1);
    TRACELogPrint(65538, "DestroytLineClient: WaitForExclLineClientAccess failed!");
    return;
  }
  v39 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 192LL);
  v7 = 0;
  if ( (*(_BYTE *)(v6 + 24) & 1) != 0 )
    v7 = *(void **)(v6 + 8);
  *(_DWORD *)v4 = 1280724553;
  if ( *(_QWORD *)(v4 + 160) )
  {
    OnProxyLineClose();
    ServerFree(*(LPVOID *)(v4 + 160));
  }
  for ( i = v4 >> 4;
        ;
        EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)i & gdwPointerToLockTableIndexBits)) )
  {
    v9 = *(_QWORD *)(v4 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)i & gdwPointerToLockTableIndexBits));
    if ( !v9 )
      break;
    DestroytCallClient(v9);
  }
  v10 = *(_QWORD *)(v4 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v10 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  v11 = *(_QWORD *)(v4 + 128);
  if ( v11 )
    *(_QWORD *)(v11 + 120) = *(_QWORD *)(v4 + 120);
  v12 = *(_QWORD *)(v4 + 120);
  v13 = *(_QWORD *)(v4 + 128);
  if ( v12 )
    *(_QWORD *)(v12 + 128) = v13;
  else
    *(_QWORD *)(v10 + 16) = v13;
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v10 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  if ( v7 )
    WaitForSingleObject(v7, 0xFFFFFFFF);
  v45 = *(_QWORD *)(v4 + 32);
  hMutex = *(HANDLE *)(v45 + 8);
  WaitForSingleObject(hMutex, 0xFFFFFFFF);
  if ( *(_DWORD *)(v4 + 144) )
  {
    --*(_DWORD *)(v45 + 256);
    if ( (*(_BYTE *)(v4 + 144) & 1) != 0 )
    {
      v14 = (*(_DWORD *)(v45 + 260))-- == 1;
      if ( v14 )
      {
        v48[0] = 20;
        v48[1] = 20;
        v49 = 20;
        v50 = 0;
        if ( v7 )
          WaitForSingleObject(v7, 0xFFFFFFFF);
        v15 = *(void (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)(v45 + 192) + 1048LL);
        if ( v15 )
          v15(*(_QWORD *)(v45 + 200), v48);
        if ( v7 )
          ReleaseMutex(v7);
      }
    }
  }
  if ( (*(_DWORD *)(v4 + 64) & 0x40000000) != 0 )
  {
    v16 = 1;
    v17 = 0;
    do
    {
      if ( *(_QWORD *)(v45 + 8LL * v16 + 24) == v4 )
      {
        TRACELogPrint(262146, "tell clients proxy %02X closed", v16);
        v17 |= 1 << (v16 - 1);
        *(_QWORD *)(v45 + 8LL * v16 + 24) = 0;
      }
      ++v16;
    }
    while ( v16 <= 0x14 );
    v39 = v17;
  }
  if ( *(_DWORD *)(v4 + 96) )
  {
    v14 = (*(_DWORD *)(v45 + 224))-- == 1;
    if ( v14 )
    {
      if ( v7 )
        WaitForSingleObject(v7, 0xFFFFFFFF);
      v18 = *(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(v45 + 192) + 528LL);
      if ( v18 )
        v18(*(_QWORD *)(v45 + 200), 0);
      if ( v7 )
        ReleaseMutex(v7);
      *(_DWORD *)(v45 + 220) = 0;
    }
  }
  v19 = *(_QWORD *)(v4 + 112);
  if ( v19 )
    *(_QWORD *)(v19 + 104) = *(_QWORD *)(v4 + 104);
  v20 = *(_QWORD *)(v4 + 104);
  v21 = *(_QWORD *)(v4 + 112);
  v22 = (__int64 *)(v45 + 16);
  if ( v20 )
    *(_QWORD *)(v20 + 112) = v21;
  else
    *v22 = v21;
  --*(_DWORD *)(v45 + 236);
  if ( *(_DWORD *)v45 != 1162758476 )
    goto LABEL_90;
  TRACELogPrint(262146, "It's a line_key");
  if ( !*v22 )
  {
    TRACELogPrint(262146, "...and it's the last one out");
    ReleaseMutex(hMutex);
    hMutex = 0;
    if ( v7 )
    {
      ReleaseMutex(v7);
      v7 = 0;
    }
    DestroytLine((_DWORD *)v45, 0);
LABEL_90:
    v27 = 0;
    goto LABEL_91;
  }
  TRACELogPrint(262146, "...and there are still clients");
  v23 = *(_DWORD *)(v45 + 232);
  if ( v23 && *(_DWORD *)(v4 + 68) )
  {
    v24 = 0;
    for ( j = *(_QWORD *)(v45 + 16); j; j = *(_QWORD *)(j + 112) )
    {
      if ( (*(_BYTE *)(j + 64) & 4) != 0 )
        v24 |= *(_DWORD *)(j + 68);
    }
    if ( v24 != v23 )
    {
      if ( v7 )
        WaitForSingleObject(v7, 0xFFFFFFFF);
      v26 = *(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(v45 + 192) + 616LL);
      if ( v26 )
        v26(*(_QWORD *)(v45 + 200), v24);
      if ( v7 )
        ReleaseMutex(v7);
      *(_DWORD *)(v45 + 232) = v24;
    }
    v22 = (__int64 *)(v45 + 16);
  }
  if ( (*(_DWORD *)(v4 + 76) & 0xFFFBFFFF) != 0 || *(_DWORD *)(v4 + 80) )
  {
    while ( *(_DWORD *)(v45 + 264) )
    {
      ReleaseMutex(hMutex);
      if ( v7 )
        ReleaseMutex(v7);
      Sleep(0x32u);
      if ( v7 )
        WaitForSingleObject(v7, 0xFFFFFFFF);
      WaitForSingleObject(hMutex, 0xFFFFFFFF);
      if ( *(_DWORD *)v45 != 1162758476 )
        goto LABEL_72;
    }
    v28 = 0;
    v42 = 0;
    v29 = 0;
    v44 = 0;
    v30 = *v22;
    if ( *v22 )
    {
      do
      {
        v28 |= *(_DWORD *)(v30 + 76);
        v29 |= *(_DWORD *)(v30 + 80);
        v30 = *(_QWORD *)(v30 + 112);
      }
      while ( v30 );
      v44 = v29;
      v42 = v28;
    }
    if ( v28 == *(_DWORD *)(v45 + 240) && v29 == *(_DWORD *)(v45 + 244)
      || (v47 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(v45 + 192) + 656LL)) == 0 )
    {
LABEL_72:
      v27 = 1;
      goto LABEL_91;
    }
    v46 = *(_QWORD *)(v45 + 200);
    *(_DWORD *)(v45 + 264) = 1;
    ReleaseMutex(hMutex);
    if ( v7 )
      WaitForSingleObject(v7, 0xFFFFFFFF);
    v31 = v42;
    v43 = v47(v46, v42, v44);
    if ( v7 )
      ReleaseMutex(v7);
    WaitForSingleObject(hMutex, 0xFFFFFFFF);
    if ( *(_DWORD *)v45 == 1162758476 )
    {
      *(_DWORD *)(v45 + 264) = 0;
      if ( !v43 )
      {
        *(_DWORD *)(v45 + 240) = v31;
        *(_DWORD *)(v45 + 244) = v44;
      }
    }
    v32 = v39;
    v27 = 1;
    goto LABEL_92;
  }
  v27 = 1;
LABEL_91:
  v32 = v39;
LABEL_92:
  if ( hMutex )
    ReleaseMutex(hMutex);
  if ( v7 )
    ReleaseMutex(v7);
  if ( v27 )
  {
    SendMsgToLineClients(v45, 0, 8, 1024, 0, 0);
    v33 = 1;
    v34 = 1;
    while ( v32 )
    {
      if ( (v34 & v32) != 0 )
      {
        SendMsgToLineClients(v45, 0, 31, 2, v33, 0);
        v32 ^= v34;
      }
      ++v33;
      v34 *= 2;
    }
  }
  if ( (*(_DWORD *)(v4 + 64) & 0x40000000) != 0 )
  {
    v35 = *(_QWORD *)(v4 + 136);
    if ( v35 )
    {
      do
      {
        v36 = *(_QWORD *)(v35 + 112);
        *(_DWORD *)v35 = 1129927489;
        CompletionProc(v35, 0x80000049);
        DereferenceObject(v37, *(_DWORD *)(v35 + 72), 1);
        v35 = v36;
      }
      while ( v36 );
    }
  }
  v38 = *(void **)(v4 + 88);
  if ( v38 )
    ServerFree(v38);
  DereferenceObject((__int64)v38, a1, 2);
}

```

## disassembly

```asm
0x180005378  mov     [rsp+arg_8], rbx
0x18000537d  mov     [rsp+arg_10], rsi
0x180005382  push    rdi
0x180005383  push    r12
0x180005385  push    r13
0x180005387  push    r14
0x180005389  push    r15
0x18000538b  sub     rsp, 0D0h
0x180005392  mov     rax, cs:__security_cookie
0x180005399  xor     rax, rsp
0x18000539c  mov     [rsp+0F8h+var_30], rax
0x1800053a4  mov     ebx, ecx
0x1800053a6  mov     [rsp+0F8h+var_AC], ecx
0x1800053aa  mov     [rsp+0F8h+var_90], ecx
0x1800053ae  mov     r8d, ecx
0x1800053b1  lea     rdx, aDestroytlinecl; "DestroytLineClient: enter, hLine=x%x"
0x1800053b8  mov     ecx, 80002h
0x1800053bd  call    TRACELogPrint
0x1800053c2  xor     r8d, r8d
0x1800053c5  mov     edx, ebx
0x1800053c7  call    ReferenceObject
0x1800053cc  mov     r14, rax
0x1800053cf  mov     [rsp+0F8h+var_70], rax
0x1800053d7  xor     edi, edi
0x1800053d9  test    rax, rax
0x1800053dc  jz      loc_180005AF0
0x1800053e2  mov     rcx, rax
0x1800053e5  call    WaitForExclusiveLineClientAccess
0x1800053ea  test    eax, eax
0x1800053ec  jz      loc_180005AD2
0x1800053f2  mov     eax, edi
0x1800053f4  mov     [rsp+0F8h+var_C8], eax
0x1800053f8  mov     [rsp+0F8h+var_B0], eax
0x1800053fc  mov     rax, [r14+20h]
0x180005400  mov     rcx, [rax+0C0h]
0x180005407  mov     esi, edi
0x180005409  mov     [rsp+0F8h+var_80], rdi
0x18000540e  lea     r12d, [rdi+1]
0x180005412  test    [rcx+18h], r12b
0x180005416  jz      short loc_180005421
0x180005418  mov     rsi, [rcx+8]
0x18000541c  mov     [rsp+0F8h+var_80], rsi
0x180005421  mov     dword ptr [r14], 4C564E49h
0x180005428  mov     rcx, [r14+0A0h]
0x18000542f  test    rcx, rcx
0x180005432  jz      short loc_180005445
0x180005434  call    OnProxyLineClose
0x180005439  mov     rcx, [r14+0A0h]; lpMem
0x180005440  call    ServerFree
0x180005445  mov     rbx, r14
0x180005448  shr     rbx, 4
0x18000544c  jmp     short loc_180005474
0x18000544e  mov     rcx, r15
0x180005451  call    DestroytCallClient
0x180005456  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18000545c  and     rax, rbx
0x18000545f  lea     rcx, [rax+rax*4]
0x180005463  mov     rax, cs:gLockTable
0x18000546a  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000546e  call    cs:__imp_EnterCriticalSection
0x180005474  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18000547a  and     rax, rbx
0x18000547d  lea     rcx, [rax+rax*4]
0x180005481  mov     rax, cs:gLockTable
0x180005488  mov     r15, [r14+30h]
0x18000548c  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180005490  call    cs:__imp_LeaveCriticalSection
0x180005496  test    r15, r15
0x180005499  jnz     short loc_18000544E
0x18000549b  mov     r15, [r14+10h]
0x18000549f  mov     rbx, r15
0x1800054a2  shr     rbx, 4
0x1800054a6  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800054ac  and     rax, rbx
0x1800054af  lea     rcx, [rax+rax*4]
0x1800054b3  mov     rax, cs:gLockTable
0x1800054ba  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800054be  call    cs:__imp_EnterCriticalSection
0x1800054c4  mov     rcx, [r14+80h]
0x1800054cb  test    rcx, rcx
0x1800054ce  jz      short loc_1800054D8
0x1800054d0  mov     rax, [r14+78h]
0x1800054d4  mov     [rcx+78h], rax
0x1800054d8  mov     rcx, [r14+78h]
0x1800054dc  mov     rax, [r14+80h]
0x1800054e3  test    rcx, rcx
0x1800054e6  jz      short loc_1800054F1
0x1800054e8  mov     [rcx+80h], rax
0x1800054ef  jmp     short loc_1800054F5
0x1800054f1  mov     [r15+10h], rax
0x1800054f5  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800054fb  and     rax, rbx
0x1800054fe  lea     rcx, [rax+rax*4]
0x180005502  mov     rax, cs:gLockTable
0x180005509  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000550d  call    cs:__imp_LeaveCriticalSection
0x180005513  or      r15d, 0FFFFFFFFh
0x180005517  test    rsi, rsi
0x18000551a  jz      short loc_180005528
0x18000551c  mov     edx, r15d; dwMilliseconds
0x18000551f  mov     rcx, rsi; hHandle
0x180005522  call    cs:__imp_WaitForSingleObject
0x180005528  mov     rax, [r14+20h]
0x18000552c  mov     [rsp+0F8h+var_88], rax
0x180005531  mov     rbx, rax
0x180005534  mov     [rsp+0F8h+var_68], rax
0x18000553c  mov     rax, [rax+8]
0x180005540  mov     [rsp+0F8h+hMutex], rax
0x180005545  mov     [rsp+0F8h+var_78], rax
0x18000554d  mov     edx, r15d; dwMilliseconds
0x180005550  mov     rcx, rax; hHandle
0x180005553  call    cs:__imp_WaitForSingleObject
0x180005559  cmp     [r14+90h], edi
0x180005560  jz      loc_1800055EE
0x180005566  add     [rbx+100h], r15d
0x18000556d  test    [r14+90h], r12b
0x180005574  jz      short loc_1800055EE
0x180005576  add     [rbx+104h], r15d
0x18000557d  jnz     short loc_1800055EE
0x18000557f  mov     [rsp+0F8h+var_48], 14h
0x18000558a  mov     [rsp+0F8h+var_44], 14h
0x180005595  mov     [rsp+0F8h+var_40], 14h
0x1800055a1  mov     [rsp+0F8h+var_38], edi
0x1800055a8  test    rsi, rsi
0x1800055ab  jz      short loc_1800055B9
0x1800055ad  mov     edx, r15d; dwMilliseconds
0x1800055b0  mov     rcx, rsi; hHandle
0x1800055b3  call    cs:__imp_WaitForSingleObject
0x1800055b9  mov     rax, [rbx+0C0h]
0x1800055c0  mov     rax, [rax+418h]
0x1800055c7  test    rax, rax
0x1800055ca  jz      short loc_1800055E0
0x1800055cc  lea     rdx, [rsp+0F8h+var_48]
0x1800055d4  mov     rcx, [rbx+0C8h]
0x1800055db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055e0  test    rsi, rsi
0x1800055e3  jz      short loc_1800055EE
0x1800055e5  mov     rcx, rsi; hMutex
0x1800055e8  call    cs:__imp_ReleaseMutex
0x1800055ee  lea     rax, [r14+40h]
0x1800055f2  mov     [rsp+0F8h+var_50], rax
0x1800055fa  test    dword ptr [rax], 40000000h
0x180005600  jz      short loc_180005651
0x180005602  mov     r13d, r12d
0x180005605  mov     r15d, edi
0x180005608  mov     eax, r13d
0x18000560b  cmp     [rbx+rax*8+18h], r14
0x180005610  jnz     short loc_18000563F
0x180005612  mov     r8d, r13d
0x180005615  lea     rdx, aTellClientsPro; "tell clients proxy %02X closed"
0x18000561c  mov     ecx, 40002h
0x180005621  call    TRACELogPrint
0x180005626  lea     ecx, [r13-1]
0x18000562a  mov     eax, r12d
0x18000562d  shl     eax, cl
0x18000562f  or      r15d, eax
0x180005632  mov     [rsp+0F8h+var_B0], r15d
0x180005637  mov     eax, r13d
0x18000563a  mov     [rbx+rax*8+18h], rdi
0x18000563f  add     r13d, r12d
0x180005642  cmp     r13d, 14h
0x180005646  jbe     short loc_180005608
0x180005648  mov     [rsp+0F8h+var_C8], r15d
0x18000564d  or      r15d, 0FFFFFFFFh
0x180005651  cmp     [r14+60h], edi
0x180005655  jz      short loc_1800056A6
0x180005657  add     [rbx+0E0h], r15d
0x18000565e  jnz     short loc_1800056A6
0x180005660  test    rsi, rsi
0x180005663  jz      short loc_180005671
0x180005665  mov     edx, r15d; dwMilliseconds
0x180005668  mov     rcx, rsi; hHandle
0x18000566b  call    cs:__imp_WaitForSingleObject
0x180005671  mov     rax, [rbx+0C0h]
0x180005678  mov     rax, [rax+210h]
0x18000567f  test    rax, rax
0x180005682  jz      short loc_180005692
0x180005684  xor     edx, edx
0x180005686  mov     rcx, [rbx+0C8h]
0x18000568d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005692  test    rsi, rsi
0x180005695  jz      short loc_1800056A0
0x180005697  mov     rcx, rsi; hMutex
0x18000569a  call    cs:__imp_ReleaseMutex
0x1800056a0  mov     [rbx+0DCh], edi
0x1800056a6  mov     rcx, [r14+70h]
0x1800056aa  test    rcx, rcx
0x1800056ad  jz      short loc_1800056B7
0x1800056af  mov     rax, [r14+68h]
0x1800056b3  mov     [rcx+68h], rax
0x1800056b7  mov     rax, [r14+68h]
0x1800056bb  mov     rcx, [r14+70h]
0x1800056bf  lea     r13, [rbx+10h]
0x1800056c3  mov     [rsp+0F8h+var_A8], r13
0x1800056c8  test    rax, rax
0x1800056cb  jz      short loc_1800056D3
0x1800056cd  mov     [rax+70h], rcx
0x1800056d1  jmp     short loc_1800056D7
0x1800056d3  mov     [r13+0], rcx
0x1800056d7  add     [rbx+0ECh], r15d
0x1800056de  cmp     dword ptr [rbx], 454E494Ch
0x1800056e4  jnz     loc_1800059E9
0x1800056ea  lea     rdx, aItSALineKey; "It's a line_key"
0x1800056f1  mov     ecx, 40002h
0x1800056f6  call    TRACELogPrint
0x1800056fb  mov     ecx, 40002h
0x180005700  cmp     [r13+0], rdi
0x180005704  jz      loc_1800059B2
0x18000570a  lea     rdx, aAndThereAreSti; "...and there are still clients"
0x180005711  call    TRACELogPrint
0x180005716  mov     ecx, [rbx+0E8h]
0x18000571c  test    ecx, ecx
0x18000571e  jz      short loc_180005793
0x180005720  cmp     [r14+44h], edi
0x180005724  jz      short loc_180005793
0x180005726  mov     r13d, edi
0x180005729  mov     rax, [rbx+10h]
0x18000572d  jmp     short loc_18000573D
0x18000572f  test    byte ptr [rax+40h], 4
0x180005733  jz      short loc_180005739
0x180005735  or      r13d, [rax+44h]
0x180005739  mov     rax, [rax+70h]
0x18000573d  test    rax, rax
0x180005740  jnz     short loc_18000572F
0x180005742  cmp     r13d, ecx
0x180005745  jz      short loc_18000578F
0x180005747  test    rsi, rsi
0x18000574a  jz      short loc_180005758
0x18000574c  mov     edx, r15d; dwMilliseconds
0x18000574f  mov     rcx, rsi; hHandle
0x180005752  call    cs:__imp_WaitForSingleObject
0x180005758  mov     rax, [rbx+0C0h]
0x18000575f  mov     rax, [rax+268h]
0x180005766  test    rax, rax
0x180005769  jz      short loc_18000577A
0x18000576b  mov     edx, r13d
0x18000576e  mov     rcx, [rbx+0C8h]
0x180005775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000577a  test    rsi, rsi
0x18000577d  jz      short loc_180005788
0x18000577f  mov     rcx, rsi; hMutex
0x180005782  call    cs:__imp_ReleaseMutex
0x180005788  mov     [rbx+0E8h], r13d
0x18000578f  lea     r13, [rbx+10h]
0x180005793  mov     edx, r12d
0x180005796  mov     [rsp+0F8h+var_C4], edx
0x18000579a  test    dword ptr [r14+4Ch], 0FFFBFFFFh
0x1800057a2  jnz     short loc_1800057AE
0x1800057a4  cmp     [r14+50h], edi
0x1800057a8  jz      loc_180005A3B
0x1800057ae  cmp     [rbx+108h], edi
0x1800057b4  jz      loc_180005876
0x1800057ba  mov     [rsp+0F8h+var_98], r12d
0x1800057bf  mov     rcx, [rsp+0F8h+hMutex]; hMutex
0x1800057c4  call    cs:__imp_ReleaseMutex
0x1800057ca  test    rsi, rsi
0x1800057cd  jz      short loc_1800057D8
0x1800057cf  mov     rcx, rsi; hMutex
0x1800057d2  call    cs:__imp_ReleaseMutex
0x1800057d8  mov     ecx, 32h ; '2'; dwMilliseconds
0x1800057dd  call    cs:__imp_Sleep
0x1800057e3  test    rsi, rsi
0x1800057e6  jz      short loc_1800057F4
0x1800057e8  mov     edx, r15d; dwMilliseconds
0x1800057eb  mov     rcx, rsi; hHandle
0x1800057ee  call    cs:__imp_WaitForSingleObject
0x1800057f4  mov     edx, r15d; dwMilliseconds
0x1800057f7  mov     rcx, [rsp+0F8h+hMutex]; hHandle
0x1800057fc  call    cs:__imp_WaitForSingleObject
0x180005802  nop
0x180005803  mov     eax, r12d
0x180005806  cmp     dword ptr [rbx], 454E494Ch
0x18000580c  cmovz   eax, edi
0x18000580f  mov     [rsp+0F8h+var_98], eax
0x180005813  jmp     short loc_180005864
0x180005815  xor     edi, edi
0x180005817  lea     r12d, [rdi+1]
0x18000581b  or      r15d, 0FFFFFFFFh
0x18000581f  mov     rax, [rsp+0F8h+var_78]
0x180005827  mov     [rsp+0F8h+hMutex], rax
0x18000582c  mov     r14, [rsp+0F8h+var_70]
0x180005834  mov     [rsp+0F8h+var_C4], r12d
0x180005839  mov     eax, [rsp+0F8h+var_B0]
0x18000583d  mov     [rsp+0F8h+var_C8], eax
0x180005841  mov     rbx, [rsp+0F8h+var_68]
0x180005849  mov     rsi, [rsp+0F8h+var_80]
0x18000584e  mov     eax, [rsp+0F8h+var_98]
0x180005852  mov     r13, [rsp+0F8h+var_A8]
0x180005857  mov     ecx, [rsp+0F8h+var_90]
0x18000585b  mov     [rsp+0F8h+var_AC], ecx
0x18000585f  mov     [rsp+0F8h+var_88], rbx
0x180005864  test    eax, eax
0x180005866  jz      loc_1800057AE
0x18000586c  mov     r15d, [rsp+0F8h+var_C4]
0x180005871  jmp     loc_1800059EC
0x180005876  mov     ecx, edi
0x180005878  mov     dword ptr [rsp+0F8h+var_A8], ecx
0x18000587c  mov     edx, edi
0x18000587e  mov     [rsp+0F8h+var_A0], edx
0x180005882  mov     rax, [r13+0]
  ... truncated ...
```
