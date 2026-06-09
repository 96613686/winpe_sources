# TryOpenSinkSession(ulong,_GUID const *,ulong,CSbSafeBuffer *,CWcnMessageSinkSession * *)

- ea: `0x18003b400`
- end: `0x18003b732`
- name: `?TryOpenSinkSession@@YAJKPEBU_GUID@@KPEAVCSbSafeBuffer@@PEAPEAVCWcnMessageSinkSession@@@Z`
- size: `818`
- prototype: `__int64 __fastcall(unsigned int, const struct _GUID *, unsigned int, struct CSbSafeBuffer *, struct CWcnMessageSinkSession **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18003bb60`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18003b1ec`
- `0x18003b400`
- `0x18003dbb4`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003b603`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003b603`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TryOpenSinkSession(
        unsigned int a1,
        const struct _GUID *a2,
        unsigned int a3,
        struct CSbSafeBuffer *a4,
        struct CWcnMessageSinkSession **a5)
{
  __int64 v6; // rbp
  __int64 v8; // rbx
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // rdi
  const char *v13; // rax
  __int64 v14; // r10
  __int64 (__fastcall ***v15)(_QWORD, const struct _GUID *, _QWORD *, struct CSbSafeBuffer *, _QWORD *); // rsi
  int v16; // edi
  unsigned int v17; // eax
  __int64 v18; // r10
  int v19; // edx
  __int64 (__fastcall ***v20)(_QWORD, const struct _GUID *, _QWORD *, struct CSbSafeBuffer *, _QWORD *); // rcx
  unsigned int v21; // eax
  __int64 v22; // r10
  __int64 v23; // rdx
  _QWORD *v24; // rax
  CWcnMessageSinkManager *v25; // rcx
  _QWORD *v26; // rbx
  int active; // eax
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // r10
  _QWORD v33[11]; // [rsp+30h] [rbp-58h] BYREF

  v6 = a3;
  v8 = a1;
  v33[0] = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 25, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  v12 = qword_1800759B0;
  if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && v9[25] >= 6u )
  {
    v13 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v14 + 16), 10, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids, v13);
    v9 = WPP_GLOBAL_Control;
  }
  v15 = 0;
  if ( (unsigned int)v8 < 7 )
  {
    _mm_lfence();
    v20 = *(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, _QWORD *, struct CSbSafeBuffer *, _QWORD *))(v12 + 8 * v8 + 16);
    if ( v20 )
    {
      v16 = 0;
      v15 = v20;
      goto LABEL_17;
    }
    v16 = -2147024809;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v16;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = (unsigned int)GetIndent(0);
      v19 = 13;
      goto LABEL_11;
    }
  }
  else
  {
    v16 = -2147024809;
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control )
      return (unsigned int)v16;
    if ( v9[25] >= 2u )
    {
      v17 = (unsigned int)GetIndent(0);
      v19 = 12;
LABEL_11:
      WPP_SF_sd(*(_QWORD *)(v18 + 16), v19, (unsigned int)WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids, v17, v8);
LABEL_17:
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( v9 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( v16 >= 0 && v9[25] < 6u )
      goto LABEL_27;
    v21 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v22 + 16), 14, (unsigned int)WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids, v21, v16);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v16 >= 0 )
  {
LABEL_27:
    v24 = operator new(0xF8u, (const struct std::nothrow_t *)&std::nothrow);
    v26 = v24;
    v33[1] = v24;
    if ( v24 )
    {
      v24[2] = 0;
      v24[3] = 0;
      *((_BYTE *)v24 + 32) = 0;
      v24[10] = 0;
      v24[15] = 0;
      *((_BYTE *)v24 + 128) = 0;
      *((_BYTE *)v24 + 168) = 0;
      CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)(v24 + 22));
      *((_BYTE *)v26 + 240) = 0;
      *((_DWORD *)v26 + 61) = 1;
      InitializeCriticalSection((LPCRITICAL_SECTION)v26 + 1);
    }
    else
    {
      v26 = 0;
    }
    if ( !v26 )
    {
      v16 = -2147024882;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)v16;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_46;
      v23 = 27;
      goto LABEL_26;
    }
    v26[2] = qword_1800759B0;
    v26[15] = v6;
    active = CWcnMessageSinkManager::RegisterActiveSession(v25, (struct CWcnMessageSinkSession *)v26);
    v16 = active;
    if ( active >= 0 )
    {
      active = (**v15)(v15, a2, v26, a4, v33);
      v16 = active;
      if ( active >= 0 )
      {
        v26[3] = v33[0];
        *a5 = (struct CWcnMessageSinkSession *)v26;
        _InterlockedIncrement((volatile signed __int32 *)v26 + 61);
        goto LABEL_44;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_44;
      v29 = 29;
    }
    else
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_44;
      v29 = 28;
    }
    WPP_SF_d(v28[2], v29, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids, (unsigned int)active);
LABEL_44:
    CWcnMessageSinkSession::Release((CWcnMessageSinkSession *)v26);
    goto LABEL_45;
  }
  if ( v9 == (_BYTE *)&WPP_GLOBAL_Control )
    return (unsigned int)v16;
  if ( v9[25] < 2u )
    goto LABEL_46;
  v23 = 26;
LABEL_26:
  WPP_SF_d(*((_QWORD *)v9 + 2), v23, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids, (unsigned int)v16);
LABEL_45:
  v9 = WPP_GLOBAL_Control;
LABEL_46:
  if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && (v16 < 0 || v9[25] >= 6u) )
  {
    v30 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v31 + 16), 30, (unsigned int)WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids, v30, v16);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18003b400  push    rbx
0x18003b402  push    rbp
0x18003b403  push    rsi
0x18003b404  push    rdi
0x18003b405  push    r13
0x18003b407  push    r14
0x18003b409  push    r15
0x18003b40b  sub     rsp, 50h
0x18003b40f  mov     r14, r9
0x18003b412  mov     ebp, r8d
0x18003b415  mov     r15, rdx
0x18003b418  mov     ebx, ecx
0x18003b41a  mov     [rsp+88h+var_58], 0
0x18003b423  lea     r13, WPP_GLOBAL_Control
0x18003b42a  mov     r10, cs:WPP_GLOBAL_Control
0x18003b431  cmp     r10, r13
0x18003b434  jz      short loc_18003B466
0x18003b436  cmp     byte ptr [r10+19h], 6
0x18003b43b  jb      short loc_18003B466
0x18003b43d  mov     ecx, 1; int
0x18003b442  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003b447  mov     edx, 19h
0x18003b44c  mov     r9, rax
0x18003b44f  lea     r8, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids
0x18003b456  mov     rcx, [r10+10h]
0x18003b45a  call    WPP_SF_s
0x18003b45f  mov     r10, cs:WPP_GLOBAL_Control
0x18003b466  mov     rdi, cs:qword_1800759B0
0x18003b46d  cmp     r10, r13
0x18003b470  jz      short loc_18003B4A2
0x18003b472  cmp     byte ptr [r10+19h], 6
0x18003b477  jb      short loc_18003B4A2
0x18003b479  mov     ecx, 1; int
0x18003b47e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003b483  mov     edx, 0Ah
0x18003b488  mov     r9, rax
0x18003b48b  lea     r8, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids
0x18003b492  mov     rcx, [r10+10h]
0x18003b496  call    WPP_SF_s
0x18003b49b  mov     r10, cs:WPP_GLOBAL_Control
0x18003b4a2  xor     esi, esi
0x18003b4a4  cmp     ebx, 7
0x18003b4a7  jb      short loc_18003B4E1
0x18003b4a9  mov     edi, 80070057h
0x18003b4ae  cmp     r10, r13
0x18003b4b1  jz      loc_18003B721
0x18003b4b7  cmp     byte ptr [r10+19h], 2
0x18003b4bc  jb      short loc_18003B522
0x18003b4be  xor     ecx, ecx; int
0x18003b4c0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003b4c5  lea     edx, [rsi+0Ch]
0x18003b4c8  mov     dword ptr [rsp+88h+var_68], ebx
0x18003b4cc  mov     r9, rax
0x18003b4cf  lea     r8, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids
0x18003b4d6  mov     rcx, [r10+10h]
0x18003b4da  call    WPP_SF_sd
0x18003b4df  jmp     short loc_18003B51B
0x18003b4e1  lfence
0x18003b4e4  mov     rcx, [rdi+rbx*8+10h]; int
0x18003b4e9  test    rcx, rcx
0x18003b4ec  jnz     short loc_18003B516
0x18003b4ee  mov     edi, 80070057h
0x18003b4f3  mov     r10, cs:WPP_GLOBAL_Control
0x18003b4fa  cmp     r10, r13
0x18003b4fd  jz      loc_18003B721
0x18003b503  cmp     byte ptr [r10+19h], 2
0x18003b508  jb      short loc_18003B522
0x18003b50a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003b50f  mov     edx, 0Dh
0x18003b514  jmp     short loc_18003B4C8
0x18003b516  xor     edi, edi
0x18003b518  mov     rsi, rcx
0x18003b51b  mov     r10, cs:WPP_GLOBAL_Control
0x18003b522  cmp     r10, r13
0x18003b525  jz      short loc_18003B55D
0x18003b527  test    edi, edi
0x18003b529  js      short loc_18003B532
0x18003b52b  cmp     byte ptr [r10+19h], 6
0x18003b530  jb      short loc_18003B592
0x18003b532  or      ecx, 0FFFFFFFFh; int
0x18003b535  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003b53a  mov     edx, 0Eh
0x18003b53f  mov     dword ptr [rsp+88h+var_68], edi
0x18003b543  mov     r9, rax
0x18003b546  lea     r8, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids
0x18003b54d  mov     rcx, [r10+10h]
0x18003b551  call    WPP_SF_sd
0x18003b556  mov     r10, cs:WPP_GLOBAL_Control
0x18003b55d  test    edi, edi
0x18003b55f  jns     short loc_18003B592
0x18003b561  cmp     r10, r13
0x18003b564  jz      loc_18003B721
0x18003b56a  cmp     byte ptr [r10+19h], 2
0x18003b56f  jb      loc_18003B6ED
0x18003b575  mov     edx, 1Ah
0x18003b57a  mov     r9d, edi
0x18003b57d  lea     r8, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids
0x18003b584  mov     rcx, [r10+10h]
0x18003b588  call    WPP_SF_d
0x18003b58d  jmp     loc_18003B6E6
0x18003b592  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b599  mov     ecx, 0F8h; unsigned __int64
0x18003b59e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003b5a3  mov     rbx, rax
0x18003b5a6  mov     [rsp+88h+var_50], rax
0x18003b5ab  test    rax, rax
0x18003b5ae  jz      short loc_18003B60B
0x18003b5b0  mov     qword ptr [rax+10h], 0
0x18003b5b8  mov     qword ptr [rax+18h], 0
0x18003b5c0  mov     byte ptr [rax+20h], 0
0x18003b5c4  mov     qword ptr [rax+50h], 0
0x18003b5cc  mov     qword ptr [rax+78h], 0
0x18003b5d4  mov     byte ptr [rax+80h], 0
0x18003b5db  mov     byte ptr [rax+0A8h], 0
0x18003b5e2  lea     rcx, [rax+0B0h]; this
0x18003b5e9  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18003b5ee  mov     byte ptr [rbx+0F0h], 0
0x18003b5f5  mov     dword ptr [rbx+0F4h], 1
0x18003b5ff  lea     rcx, [rbx+28h]; lpCriticalSection
0x18003b603  call    cs:__imp_InitializeCriticalSection
0x18003b609  jmp     short loc_18003B60D
0x18003b60b  xor     ebx, ebx
0x18003b60d  test    rbx, rbx
0x18003b610  jnz     short loc_18003B63A
0x18003b612  mov     edi, 8007000Eh
0x18003b617  mov     r10, cs:WPP_GLOBAL_Control
0x18003b61e  cmp     r10, r13
0x18003b621  jz      loc_18003B721
0x18003b627  cmp     byte ptr [r10+19h], 2
0x18003b62c  jb      loc_18003B6ED
0x18003b632  lea     edx, [rbx+1Bh]
0x18003b635  jmp     loc_18003B57A
0x18003b63a  mov     rax, cs:qword_1800759B0
0x18003b641  mov     [rbx+10h], rax
0x18003b645  mov     [rbx+78h], rbp
0x18003b649  mov     rdx, rbx; struct CWcnMessageSinkSession *
0x18003b64c  call    ?RegisterActiveSession@CWcnMessageSinkManager@@QEAAJPEAVCWcnMessageSinkSession@@@Z; CWcnMessageSinkManager::RegisterActiveSession(CWcnMessageSinkSession *)
0x18003b651  mov     edi, eax
0x18003b653  test    eax, eax
0x18003b655  jns     short loc_18003B683
0x18003b657  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b65e  cmp     rcx, r13
0x18003b661  jz      short loc_18003B6DE
0x18003b663  cmp     byte ptr [rcx+19h], 2
0x18003b667  jb      short loc_18003B6DE
0x18003b669  mov     edx, 1Ch
0x18003b66e  mov     r9d, eax
0x18003b671  lea     r8, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids
0x18003b678  mov     rcx, [rcx+10h]
0x18003b67c  call    WPP_SF_d
0x18003b681  jmp     short loc_18003B6DE
0x18003b683  mov     rax, [rsi]
0x18003b686  lea     rcx, [rsp+88h+var_58]
0x18003b68b  mov     [rsp+88h+var_68], rcx
0x18003b690  mov     r9, r14
0x18003b693  mov     r8, rbx
0x18003b696  mov     rdx, r15
0x18003b699  mov     rcx, rsi
0x18003b69c  mov     rax, [rax]
0x18003b69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6a4  mov     edi, eax
0x18003b6a6  test    eax, eax
0x18003b6a8  jns     short loc_18003B6C3
0x18003b6aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6b1  cmp     rcx, r13
0x18003b6b4  jz      short loc_18003B6DE
0x18003b6b6  cmp     byte ptr [rcx+19h], 2
0x18003b6ba  jb      short loc_18003B6DE
0x18003b6bc  mov     edx, 1Dh
0x18003b6c1  jmp     short loc_18003B66E
0x18003b6c3  mov     rax, [rsp+88h+var_58]
0x18003b6c8  mov     [rbx+18h], rax
0x18003b6cc  mov     rax, [rsp+88h+arg_20]
0x18003b6d4  mov     [rax], rbx
0x18003b6d7  lock inc dword ptr [rbx+0F4h]
0x18003b6de  mov     rcx, rbx; this
0x18003b6e1  call    ?Release@CWcnMessageSinkSession@@QEAAXXZ; CWcnMessageSinkSession::Release(void)
0x18003b6e6  mov     r10, cs:WPP_GLOBAL_Control
0x18003b6ed  cmp     r10, r13
0x18003b6f0  jz      short loc_18003B721
0x18003b6f2  test    edi, edi
0x18003b6f4  js      short loc_18003B6FD
0x18003b6f6  cmp     byte ptr [r10+19h], 6
0x18003b6fb  jb      short loc_18003B721
0x18003b6fd  or      ecx, 0FFFFFFFFh; int
0x18003b700  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003b705  mov     edx, 1Eh
0x18003b70a  mov     dword ptr [rsp+88h+var_68], edi
0x18003b70e  mov     r9, rax
0x18003b711  lea     r8, WPP_fa1ae5c186c03fa225e4fdcfa6dec201_Traceguids
0x18003b718  mov     rcx, [r10+10h]
0x18003b71c  call    WPP_SF_sd
0x18003b721  mov     eax, edi
0x18003b723  add     rsp, 50h
0x18003b727  pop     r15
0x18003b729  pop     r14
0x18003b72b  pop     r13
0x18003b72d  pop     rdi
0x18003b72e  pop     rsi
0x18003b72f  pop     rbp
0x18003b730  pop     rbx
0x18003b731  retn
```
