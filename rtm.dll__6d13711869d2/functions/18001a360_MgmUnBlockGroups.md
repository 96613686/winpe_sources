# MgmUnBlockGroups

- ea: `0x18001a360`
- end: `0x18001aa43`
- name: `MgmUnBlockGroups`
- size: `1763`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180014bfc`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015100`
- `0x180015178`
- `0x18001765c`
- `0x180018d1c`
- `0x180019094`
- `0x18001958c`
- `0x180019c94`
- `0x18001a360`
- `0x18001ad04`
- `0x18001bc4c`
- `0x18001c790`
- `0x18001dc28`
- `0x18001dcbc`
- `0x18001dd8c`
- `0x18001e374`
- `0x18001e4b0`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `ntdll!RtlUpdateTimer` at `0x18001a80b`
- `ntdll!RtlUpdateTimer` at `0x18001a80b`

## string_xrefs

- `0x18001a4e7`: `Ne protocol on interface (%lx-%lx)`

## pseudocode

```c
__int64 __fastcall MgmUnBlockGroups(unsigned int a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  _DWORD *v4; // rdi
  unsigned int v5; // r15d
  unsigned int v7; // r13d
  unsigned int v8; // esi
  int v10; // r12d
  __int64 v11; // r14
  char *v12; // rbx
  const wchar_t *v13; // rdx
  int v14; // r8d
  int v15; // ebx
  int v16; // r8d
  __int16 v17; // bx
  __int64 v18; // rsi
  unsigned int v19; // r8d
  int v20; // r9d
  int v21; // edx
  int v22; // ecx
  __int16 v23; // r15
  __int16 v24; // r12
  int v25; // r8d
  __int64 *v26; // rbx
  __int16 v27; // r14
  __int16 v28; // r13
  int v29; // r9d
  int v30; // ecx
  int v31; // eax
  int v32; // r8d
  int v33; // ecx
  int v34; // r9d
  int v35; // r8d
  int v36; // eax
  _WORD *v37; // rax
  int v38; // [rsp+28h] [rbp-D8h]
  int v39; // [rsp+40h] [rbp-C0h]
  __int16 v40; // [rsp+44h] [rbp-BCh]
  __int16 v41; // [rsp+48h] [rbp-B8h]
  _WORD *v42; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+58h] [rbp-A8h]
  int v44; // [rsp+5Ch] [rbp-A4h]
  int v45; // [rsp+60h] [rbp-A0h]
  int v46; // [rsp+64h] [rbp-9Ch]
  _DWORD *v47; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v48; // [rsp+70h] [rbp-90h]
  int v49; // [rsp+74h] [rbp-8Ch]
  __int64 v50; // [rsp+78h] [rbp-88h] BYREF
  __int128 v51; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v52; // [rsp+90h] [rbp-70h]
  unsigned int v53; // [rsp+94h] [rbp-6Ch]
  unsigned int v54; // [rsp+98h] [rbp-68h]
  __int64 v55; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v56; // [rsp+A8h] [rbp-58h]
  int v57; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v58[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v4 = 0;
  v48 = a3;
  v5 = a3;
  v52 = a2;
  v53 = a1;
  v7 = a1;
  v55 = 0;
  v50 = 0;
  v42 = 0;
  v57 = 0;
  v54 = a4;
  v51 = 0;
  v8 = a4;
  memset_0(v58, 0, sizeof(v58));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    LOWORD(v57) = 0;
    FormatRRASErrorString(&v57, L"ENTERED MgmUnblockGroups : (%lx - %lx) on %lx", v7, a2, v5);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v57);
  }
  v49 = 0;
  v10 = 0;
  v39 = 0;
  v41 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  AcquireReadLock(&qword_18002B9B8);
  *((_QWORD *)&v51 + 1) = &v51;
  *(_QWORD *)&v51 = &v51;
  while ( 1 )
  {
    v11 = 32LL * (v5 % dword_18002B92C);
    v56 = v11;
    AcquireReadLock((char *)qword_18002B9E8 + v11 + 16);
    v12 = (char *)qword_18002B9E8;
    v47 = 0;
    if ( !(unsigned int)FindIfEntry((char *)qword_18002B9E8 + v11, v5, v8, &v47) )
      break;
    v4 = v47;
    if ( !v47 )
      break;
    if ( v10 )
    {
      if ( v47[6] != v45 || v47[7] != v44 )
      {
        LOWORD(v4) = 0;
        if ( !qword_18002B8A8 )
          goto LABEL_67;
        v13 = L"Ne protocol on interface (%lx-%lx)";
        goto LABEL_66;
      }
    }
    else
    {
      v45 = v47[6];
      v44 = v47[7];
    }
    AcquireWriteLock(&qword_18002BA10);
    MergeTempAndMasterGroupLists(&qword_18002BA00);
    ReleaseWriteLock(&qword_18002BA10);
    AcquireReadLock(&qword_18002BA30);
    if ( (unsigned int)FindGroupEntry((unsigned int)&qword_18002BA20, 0, v14, (unsigned int)&v55, 0)
      && (v15 = v55,
          AcquireReadLock(v55 + 40),
          v49 = 1,
          (unsigned int)FindSourceEntry(v15 + 88, 0, v16, (unsigned int)&v50, 1))
      && (unsigned int)FindOutInterfaceEntry((int)v50 + 48, v4[4], v4[5], v4[6], v4[7], (__int64)&v47, (__int64)&v42) )
    {
      v17 = v42[17];
      v46 = (unsigned __int16)v42[19];
      v41 = v17;
    }
    else
    {
      v17 = v41;
    }
    v18 = qword_18002BA20;
    if ( (__int64 *)qword_18002BA20 != &qword_18002BA20 )
    {
      while ( 1 )
      {
        v19 = *(_DWORD *)(v18 + 32);
        if ( v19 )
        {
          v20 = *(_DWORD *)(v18 + 32) & 0xFF00;
          v21 = (unsigned __int8)v19 - (unsigned __int8)v52;
          if ( (unsigned __int8)v19 == (unsigned __int8)v52 )
          {
            v21 = v20 - (v52 & 0xFF00);
            if ( v20 == (v52 & 0xFF00) )
            {
              v21 = (v19 & 0xFF0000) - (v52 & 0xFF0000);
              if ( (v19 & 0xFF0000) == (v52 & 0xFF0000) )
                v21 = ((v19 >> 8) & 0xFF0000) - ((v52 >> 8) & 0xFF0000);
            }
          }
          if ( v21 > 0 )
          {
LABEL_58:
            v11 = v56;
            v5 = v48;
            v10 = v39;
            break;
          }
          v22 = (unsigned __int8)v19 - (unsigned __int8)v7;
          if ( !v22 )
          {
            v22 = v20 - (v7 & 0xFF00);
            if ( v20 == (v7 & 0xFF00) )
            {
              v22 = (v19 & 0xFF0000) - (v7 & 0xFF0000);
              if ( (v19 & 0xFF0000) == (v7 & 0xFF0000) )
                v22 = ((v19 >> 8) & 0xFF0000) - ((v7 >> 8) & 0xFF0000);
            }
          }
          if ( v22 >= 0 )
          {
            AcquireWriteLock(v18 + 40);
            v43 = 0;
            v23 = v17;
            v24 = v46;
            if ( (unsigned int)FindSourceEntry((int)v18 + 88, 0, v25, (unsigned int)&v50, 1)
              && (unsigned int)FindOutInterfaceEntry(
                                 (int)v50 + 64,
                                 v4[4],
                                 v4[5],
                                 v4[6],
                                 v4[7],
                                 (__int64)&v47,
                                 (__int64)&v42) )
            {
              v23 = v42[17] | v17;
              v24 += v42[19];
              v43 = (unsigned __int16)v42[18];
            }
            MergeTempAndMasterSourceLists(v18);
            v26 = *(__int64 **)(v18 + 72);
            if ( v26 != (__int64 *)(v18 + 72) )
            {
              while ( 1 )
              {
                v27 = v23;
                v28 = v24;
                v40 = v43;
                if ( (unsigned int)FindOutInterfaceEntry(
                                     (int)v26 + 64,
                                     v4[4],
                                     v4[5],
                                     v4[6],
                                     v4[7],
                                     (__int64)&v47,
                                     (__int64)&v42) )
                {
                  if ( *((_DWORD *)v26 + 26) )
                  {
                    v27 = v42[17] | v23;
                    v28 = v42[19] + v24;
                    v40 = v42[18] + v43;
                  }
                  v30 = v39;
                  if ( !v39 )
                    goto LABEL_41;
                  UnScopeIfAndInvokeCallbacks(v18, v26, v42);
                }
                v30 = v39;
LABEL_41:
                v31 = *((_DWORD *)v26 + 28);
                if ( v31 )
                {
                  if ( v31 == v4[4] && *((_DWORD *)v26 + 29) == v4[5] )
                  {
                    if ( v30 )
                      RtlUpdateTimer(
                        *((HANDLE *)qword_18002BA48 + *(_DWORD *)(v18 + 32) % (unsigned int)dword_18002B95C),
                        (HANDLE)v26[19],
                        0x7D0u,
                        0);
                  }
                  else if ( v27
                         && (!qword_18002B950 || !(unsigned int)qword_18002B950(v48, *(unsigned int *)(v18 + 32))) )
                  {
                    v32 = *((_DWORD *)v26 + 26);
                    v33 = *(_DWORD *)(v18 + 32);
                    if ( v39 )
                    {
                      if ( (unsigned int)IsForwardingEnabled(v33, 0, v32, v29, (__int64)&v51) )
                      {
                        v34 = v4[5];
                        v35 = v4[4];
                        v38 = v4[7];
                        v36 = v4[6];
                        v42 = 0;
                        AddInterfaceToSourceMfe(v18, (_DWORD)v26, v35, v34, v36, v38, 0, (__int64)&v42);
                        v37 = v42;
                        if ( v42 )
                        {
                          v42[17] = v27;
                          v37[19] = v28;
                          v37[18] = v40;
                        }
                      }
                    }
                    else
                    {
                      AddToCheckForCreationAlertList(
                        v33,
                        *(_DWORD *)(v18 + 36),
                        v32,
                        *((_DWORD *)v26 + 27),
                        *((_DWORD *)v26 + 28),
                        *((_DWORD *)v26 + 29),
                        (__int64)&v51);
                    }
                  }
                }
                v26 = (__int64 *)*v26;
                if ( v26 == (__int64 *)(v18 + 72) )
                {
                  v7 = v53;
                  break;
                }
              }
            }
            ReleaseWriteLock(v18 + 40);
          }
        }
        v18 = *(_QWORD *)v18;
        v17 = v41;
        if ( (__int64 *)v18 == &qword_18002BA20 )
          goto LABEL_58;
      }
    }
    v4 = 0;
    if ( v49 )
      ReleaseReadLock(v55 + 40);
    ReleaseReadLock(&qword_18002BA30);
    ReleaseReadLock((char *)qword_18002B9E8 + v11 + 16);
    if ( v10 )
      goto LABEL_68;
    v8 = v54;
    if ( (unsigned int)InvokeCreationAlertForList((unsigned int)&v51, v45, v44, v5, v54) )
      goto LABEL_68;
    v10 = 1;
    v39 = 1;
  }
  if ( (_DWORD *)qword_18002B8A8 == v4 )
    goto LABEL_67;
  v13 = L"Interface (%lx-%lx) not found";
LABEL_66:
  LOWORD(v57) = (_WORD)v4;
  FormatRRASErrorString(&v57, v13, v5, v8);
  ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v57);
  v12 = (char *)qword_18002B9E8;
LABEL_67:
  ReleaseReadLock(&v12[v11 + 16]);
LABEL_68:
  InvokeOutstandingCallbacks();
  ReleaseReadLock(&qword_18002B9B8);
  FreeList(&v51);
  LeaveMgmWorker();
  if ( qword_18002B8A8 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"LEAVING MgmUnblockGroups");
  return 0;
}

```

## disassembly

```asm
0x18001a360  push    rbp
0x18001a362  push    rbx
0x18001a363  push    rsi
0x18001a364  push    rdi
0x18001a365  push    r12
0x18001a367  push    r13
0x18001a369  push    r14
0x18001a36b  push    r15
0x18001a36d  lea     rbp, [rsp-7C8h]
0x18001a375  sub     rsp, 8C8h
0x18001a37c  mov     rax, cs:__security_cookie
0x18001a383  xor     rax, rsp
0x18001a386  mov     [rbp+800h+var_50], rax
0x18001a38d  xor     edi, edi
0x18001a38f  mov     [rsp+900h+var_890], r8d
0x18001a394  mov     r15d, r8d
0x18001a397  mov     [rbp+800h+var_870], edx
0x18001a39a  mov     ebx, edx
0x18001a39c  mov     [rbp+800h+var_86C], ecx
0x18001a39f  mov     r13d, ecx
0x18001a3a2  mov     [rbp+800h+var_860], rdi
0x18001a3a6  xorps   xmm0, xmm0
0x18001a3a9  mov     [rsp+900h+var_888], rdi
0x18001a3ae  xor     edx, edx; Val
0x18001a3b0  mov     [rsp+900h+var_8B0], rdi
0x18001a3b5  mov     r8d, 7FCh; Size
0x18001a3bb  mov     [rbp+800h+var_850], edi
0x18001a3be  lea     rcx, [rbp+800h+var_84C]; void *
0x18001a3c2  mov     [rbp+800h+var_868], r9d
0x18001a3c6  movups  [rbp+800h+var_880], xmm0
0x18001a3ca  mov     esi, r9d
0x18001a3cd  call    memset_0
0x18001a3d2  call    EnterMgmAPI
0x18001a3d7  test    eax, eax
0x18001a3d9  jnz     short loc_18001A3E5
0x18001a3db  mov     eax, 3EBh
0x18001a3e0  jmp     loc_18001AA20
0x18001a3e5  cmp     cs:qword_18002B8A8, rdi
0x18001a3ec  jz      short loc_18001A42B
0x18001a3ee  mov     r9d, ebx
0x18001a3f1  mov     word ptr [rbp+800h+var_850], di
0x18001a3f5  mov     r8d, r13d
0x18001a3f8  mov     dword ptr [rsp+900h+var_8E0], r15d
0x18001a3fd  lea     rdx, aEnteredMgmunbl; "ENTERED MgmUnblockGroups : (%lx - %lx) "...
0x18001a404  lea     rcx, [rbp+800h+var_850]
0x18001a408  call    FormatRRASErrorString
0x18001a40d  mov     rdx, cs:qword_18002B8A8
0x18001a414  lea     r8, [rbp+800h+var_850]
0x18001a418  mov     rcx, cs:gMgmEtwContext
0x18001a41f  mov     rax, cs:gMgmTemplateFunc
0x18001a426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a42b  lea     rcx, qword_18002B9B8
0x18001a432  mov     [rsp+900h+var_88C], edi
0x18001a436  mov     r12d, edi
0x18001a439  mov     [rsp+900h+var_8C0], edi
0x18001a43d  mov     dword ptr [rsp+900h+var_8B8], edi
0x18001a441  mov     [rsp+900h+var_89C], edi
0x18001a445  mov     [rsp+900h+var_8A0], edi
0x18001a449  mov     [rsp+900h+var_8A4], edi
0x18001a44d  call    AcquireReadLock
0x18001a452  lea     rax, [rbp+800h+var_880]
0x18001a456  mov     qword ptr [rbp+800h+var_880+8], rax
0x18001a45a  lea     rax, [rbp+800h+var_880]
0x18001a45e  mov     qword ptr [rbp+800h+var_880], rax
0x18001a462  mov     rcx, cs:qword_18002B9E8
0x18001a469  xor     edx, edx
0x18001a46b  mov     eax, r15d
0x18001a46e  add     rcx, 10h
0x18001a472  div     cs:dword_18002B92C
0x18001a478  mov     r14d, edx
0x18001a47b  shl     r14, 5
0x18001a47f  add     rcx, r14
0x18001a482  mov     [rbp+800h+var_858], r14
0x18001a486  call    AcquireReadLock
0x18001a48b  mov     rbx, cs:qword_18002B9E8
0x18001a492  lea     r9, [rsp+900h+var_898]
0x18001a497  mov     r8d, esi
0x18001a49a  mov     [rsp+900h+var_898], rdi
0x18001a49f  mov     edx, r15d
0x18001a4a2  lea     rcx, [r14+rbx]
0x18001a4a6  call    FindIfEntry
0x18001a4ab  test    eax, eax
0x18001a4ad  jz      loc_18001A985
0x18001a4b3  mov     rdi, [rsp+900h+var_898]
0x18001a4b8  test    rdi, rdi
0x18001a4bb  jz      loc_18001A985
0x18001a4c1  test    r12d, r12d
0x18001a4c4  jz      short loc_18001A4F3
0x18001a4c6  mov     eax, [rsp+900h+var_8A0]
0x18001a4ca  cmp     [rdi+18h], eax
0x18001a4cd  jnz     short loc_18001A4D8
0x18001a4cf  mov     eax, [rsp+900h+var_8A4]
0x18001a4d3  cmp     [rdi+1Ch], eax
0x18001a4d6  jz      short loc_18001A501
0x18001a4d8  xor     edi, edi
0x18001a4da  cmp     cs:qword_18002B8A8, rdi
0x18001a4e1  jz      loc_18001A9CD
0x18001a4e7  lea     rdx, aNeProtocolOnIn; "Ne protocol on interface (%lx-%lx)"
0x18001a4ee  jmp     loc_18001A995
0x18001a4f3  mov     eax, [rdi+18h]
0x18001a4f6  mov     [rsp+900h+var_8A0], eax
0x18001a4fa  mov     eax, [rdi+1Ch]
0x18001a4fd  mov     [rsp+900h+var_8A4], eax
0x18001a501  lea     rcx, qword_18002BA10
0x18001a508  call    AcquireWriteLock
0x18001a50d  lea     rcx, qword_18002BA00
0x18001a514  call    MergeTempAndMasterGroupLists
0x18001a519  lea     rcx, qword_18002BA10
0x18001a520  call    ReleaseWriteLock
0x18001a525  lea     rcx, qword_18002BA30
0x18001a52c  call    AcquireReadLock
0x18001a531  lea     r9, [rbp+800h+var_860]
0x18001a535  mov     dword ptr [rsp+900h+var_8E0], 0
0x18001a53d  xor     edx, edx
0x18001a53f  lea     rcx, qword_18002BA20
0x18001a546  call    FindGroupEntry
0x18001a54b  xor     r11d, r11d
0x18001a54e  test    eax, eax
0x18001a550  jz      loc_18001A5D9
0x18001a556  mov     rbx, [rbp+800h+var_860]
0x18001a55a  lea     rcx, [rbx+28h]
0x18001a55e  call    AcquireReadLock
0x18001a563  mov     eax, 1
0x18001a568  lea     rcx, [rbx+58h]
0x18001a56c  lea     r9, [rsp+900h+var_888]
0x18001a571  mov     [rsp+900h+var_88C], eax
0x18001a575  xor     edx, edx
0x18001a577  mov     dword ptr [rsp+900h+var_8E0], eax
0x18001a57b  call    FindSourceEntry
0x18001a580  xor     r11d, r11d
0x18001a583  test    eax, eax
0x18001a585  jz      short loc_18001A5D9
0x18001a587  mov     rcx, [rsp+900h+var_888]
0x18001a58c  lea     rax, [rsp+900h+var_8B0]
0x18001a591  mov     r9d, [rdi+18h]
0x18001a595  add     rcx, 30h ; '0'
0x18001a599  mov     edx, [rdi+10h]
0x18001a59c  mov     r8d, [rdi+14h]
0x18001a5a0  mov     [rsp+900h+var_8D0], rax
0x18001a5a5  lea     rax, [rsp+900h+var_898]
0x18001a5aa  mov     [rsp+900h+var_8D8], rax
0x18001a5af  mov     eax, [rdi+1Ch]
0x18001a5b2  mov     dword ptr [rsp+900h+var_8E0], eax
0x18001a5b6  call    FindOutInterfaceEntry
0x18001a5bb  xor     r11d, r11d
0x18001a5be  test    eax, eax
0x18001a5c0  jz      short loc_18001A5D9
0x18001a5c2  mov     rax, [rsp+900h+var_8B0]
0x18001a5c7  movzx   ebx, word ptr [rax+22h]
0x18001a5cb  movzx   eax, word ptr [rax+26h]
0x18001a5cf  mov     [rsp+900h+var_89C], eax
0x18001a5d3  mov     dword ptr [rsp+900h+var_8B8], ebx
0x18001a5d7  jmp     short loc_18001A5DD
0x18001a5d9  mov     ebx, dword ptr [rsp+900h+var_8B8]
0x18001a5dd  mov     rsi, cs:qword_18002BA20
0x18001a5e4  lea     rax, qword_18002BA20
0x18001a5eb  cmp     rsi, rax
0x18001a5ee  jz      loc_18001A91A
0x18001a5f4  mov     r8d, [rsi+20h]
0x18001a5f8  test    r8d, r8d
0x18001a5fb  jz      loc_18001A8F5
0x18001a601  mov     r10d, [rbp+800h+var_870]
0x18001a605  mov     r9d, r8d
0x18001a608  movzx   ecx, r8b
0x18001a60c  mov     r15d, 0FF00h
0x18001a612  mov     edx, ecx
0x18001a614  movzx   eax, r10b
0x18001a618  and     r9d, r15d
0x18001a61b  mov     r14d, 0FF0000h
0x18001a621  sub     edx, eax
0x18001a623  jnz     short loc_18001A656
0x18001a625  mov     eax, r10d
0x18001a628  mov     edx, r9d
0x18001a62b  and     eax, r15d
0x18001a62e  sub     edx, eax
0x18001a630  jnz     short loc_18001A656
0x18001a632  mov     eax, r10d
0x18001a635  mov     edx, r8d
0x18001a638  and     eax, r14d
0x18001a63b  and     edx, r14d
0x18001a63e  sub     edx, eax
0x18001a640  jnz     short loc_18001A656
0x18001a642  mov     eax, r10d
0x18001a645  mov     edx, r8d
0x18001a648  shr     eax, 8
0x18001a64b  shr     edx, 8
0x18001a64e  and     eax, r14d
0x18001a651  and     edx, r14d
0x18001a654  sub     edx, eax
0x18001a656  test    edx, edx
0x18001a658  jg      loc_18001A90C
0x18001a65e  movzx   eax, r13b
0x18001a662  sub     ecx, eax
0x18001a664  jnz     short loc_18001A697
0x18001a666  mov     eax, r13d
0x18001a669  mov     ecx, r9d
0x18001a66c  and     eax, r15d
0x18001a66f  sub     ecx, eax
0x18001a671  jnz     short loc_18001A697
0x18001a673  mov     eax, r13d
0x18001a676  mov     ecx, r8d
0x18001a679  and     eax, r14d
0x18001a67c  and     ecx, r14d
0x18001a67f  sub     ecx, eax
0x18001a681  jnz     short loc_18001A697
0x18001a683  mov     eax, r13d
0x18001a686  mov     ecx, r8d
0x18001a689  shr     eax, 8
0x18001a68c  shr     ecx, 8
0x18001a68f  and     eax, r14d
0x18001a692  and     ecx, r14d
0x18001a695  sub     ecx, eax
0x18001a697  test    ecx, ecx
0x18001a699  js      loc_18001A8F5
0x18001a69f  lea     rcx, [rsi+28h]
0x18001a6a3  call    AcquireWriteLock
0x18001a6a8  mov     r14d, [rsp+900h+var_89C]
0x18001a6ad  lea     rcx, [rsi+58h]
0x18001a6b1  lea     r9, [rsp+900h+var_888]
0x18001a6b6  mov     [rsp+900h+var_8A8], 0
0x18001a6be  xor     edx, edx
0x18001a6c0  mov     dword ptr [rsp+900h+var_8E0], 1
0x18001a6c8  movzx   r15d, bx
0x18001a6cc  movzx   r12d, r14w
0x18001a6d0  call    FindSourceEntry
0x18001a6d5  test    eax, eax
0x18001a6d7  jz      short loc_18001A728
0x18001a6d9  mov     rcx, [rsp+900h+var_888]
0x18001a6de  lea     rax, [rsp+900h+var_8B0]
0x18001a6e3  mov     r9d, [rdi+18h]
0x18001a6e7  add     rcx, 40h ; '@'
0x18001a6eb  mov     edx, [rdi+10h]
0x18001a6ee  mov     r8d, [rdi+14h]
0x18001a6f2  mov     [rsp+900h+var_8D0], rax
0x18001a6f7  lea     rax, [rsp+900h+var_898]
0x18001a6fc  mov     [rsp+900h+var_8D8], rax
0x18001a701  mov     eax, [rdi+1Ch]
0x18001a704  mov     dword ptr [rsp+900h+var_8E0], eax
0x18001a708  call    FindOutInterfaceEntry
0x18001a70d  test    eax, eax
0x18001a70f  jz      short loc_18001A728
0x18001a711  mov     rax, [rsp+900h+var_8B0]
0x18001a716  or      r15w, [rax+22h]
0x18001a71b  add     r12w, [rax+26h]
0x18001a720  movzx   eax, word ptr [rax+24h]
0x18001a724  mov     [rsp+900h+var_8A8], eax
0x18001a728  mov     rcx, rsi
0x18001a72b  call    MergeTempAndMasterSourceLists
0x18001a730  lea     rax, [rsi+48h]
0x18001a734  mov     rbx, [rax]
0x18001a737  cmp     rbx, rax
0x18001a73a  jz      loc_18001A8E9
0x18001a740  mov     eax, [rsp+900h+var_8A8]
0x18001a744  lea     rcx, [rbx+40h]
0x18001a748  mov     r9d, [rdi+18h]
0x18001a74c  movzx   r14d, r15w
0x18001a750  mov     edx, [rdi+10h]
0x18001a753  movzx   r13d, r12w
0x18001a757  mov     r8d, [rdi+14h]
0x18001a75b  mov     [rsp+900h+var_8BC], ax
0x18001a760  lea     rax, [rsp+900h+var_8B0]
0x18001a765  mov     [rsp+900h+var_8D0], rax
0x18001a76a  lea     rax, [rsp+900h+var_898]
0x18001a76f  mov     [rsp+900h+var_8D8], rax
0x18001a774  mov     eax, [rdi+1Ch]
0x18001a777  mov     dword ptr [rsp+900h+var_8E0], eax
0x18001a77b  call    FindOutInterfaceEntry
0x18001a780  xor     edx, edx
0x18001a782  test    eax, eax
0x18001a784  jz      short loc_18001A7BE
0x18001a786  mov     r8, [rsp+900h+var_8B0]
0x18001a78b  cmp     [rbx+68h], edx
0x18001a78e  jz      short loc_18001A7A9
0x18001a790  or      r14w, [r8+22h]
0x18001a795  add     r13w, [r8+26h]
0x18001a79a  movzx   eax, word ptr [rsp+900h+var_8A8]
0x18001a79f  add     ax, [r8+24h]
0x18001a7a4  mov     [rsp+900h+var_8BC], ax
0x18001a7a9  mov     ecx, [rsp+900h+var_8C0]
0x18001a7ad  test    ecx, ecx
0x18001a7af  jz      short loc_18001A7C2
0x18001a7b1  mov     rdx, rbx
0x18001a7b4  mov     rcx, rsi
0x18001a7b7  call    UnScopeIfAndInvokeCallbacks
0x18001a7bc  xor     edx, edx
0x18001a7be  mov     ecx, [rsp+900h+var_8C0]
0x18001a7c2  mov     eax, [rbx+70h]
0x18001a7c5  test    eax, eax
0x18001a7c7  jz      loc_18001A8D5
0x18001a7cd  cmp     eax, [rdi+10h]
0x18001a7d0  jnz     short loc_18001A816
0x18001a7d2  mov     eax, [rdi+14h]
0x18001a7d5  cmp     [rbx+74h], eax
0x18001a7d8  jnz     short loc_18001A816
0x18001a7da  test    ecx, ecx
0x18001a7dc  jz      loc_18001A8D5
0x18001a7e2  mov     eax, [rsi+20h]
0x18001a7e5  xor     edx, edx
0x18001a7e7  div     cs:dword_18002B95C
0x18001a7ed  mov     rcx, cs:qword_18002BA48
  ... truncated ...
```
