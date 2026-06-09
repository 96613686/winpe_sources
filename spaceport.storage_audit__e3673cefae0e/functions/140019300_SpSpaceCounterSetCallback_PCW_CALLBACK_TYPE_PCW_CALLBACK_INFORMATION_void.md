# SpSpaceCounterSetCallback(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *)

- ea: `0x140019300`
- end: `0x1400194f3`
- name: `?SpSpaceCounterSetCallback@@YAJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z`
- size: `499`
- prototype: `__int64 __fastcall(enum _PCW_CALLBACK_TYPE, union _PCW_CALLBACK_INFORMATION *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140019300`
- `0x140019500`
- `0x1400420d8`
- `0x140067fc0`
- `0x1400684c0`
- `0x1400b6030`
- `0x1400b6ac0`
- `0x1400b6fc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140019413`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006a8e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006a9df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006aaf3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019413`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006a8e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006a9df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006aaf3`
- `ntoskrnl!PcwAddInstance` at `0x140019443`
- `ntoskrnl!PcwAddInstance` at `0x14006a919`
- `ntoskrnl!PcwAddInstance` at `0x14006aa0f`
- `ntoskrnl!PcwAddInstance` at `0x14006ab27`
- `ntoskrnl!PcwAddInstance` at `0x140019443`
- `ntoskrnl!PcwAddInstance` at `0x14006a919`
- `ntoskrnl!PcwAddInstance` at `0x14006aa0f`
- `ntoskrnl!PcwAddInstance` at `0x14006ab27`

## string_xrefs

- `0x14006a974`: `Cache Lines`
- `0x14006a97d`: `Cache Log`

## pseudocode

```c
__int64 __fastcall SpSpaceCounterSetCallback(enum _PCW_CALLBACK_TYPE a1, union _PCW_CALLBACK_INFORMATION *a2, void *a3)
{
  NTSTATUS v5; // edi
  int v6; // edx
  int v7; // ebx
  SIO_SPACE_COUNTERS *v9; // r13
  const wchar_t *v10; // r12
  struct _PCW_BUFFER *v11; // rbx
  struct SP_SPACE *i; // r15
  __int64 *v13; // rsi
  __int64 *j; // r14
  char *v15; // rax
  char *k; // r14
  __int64 *m; // r14
  PPCW_DATA Data; // [rsp+20h] [rbp-F0h]
  __int64 v19; // [rsp+28h] [rbp-E8h]
  __int64 v20; // [rsp+30h] [rbp-E0h]
  __int64 v21; // [rsp+38h] [rbp-D8h]
  __int64 v22; // [rsp+40h] [rbp-D0h]
  __int64 v23; // [rsp+48h] [rbp-C8h]
  __int64 v24; // [rsp+50h] [rbp-C0h]
  __int64 v25; // [rsp+58h] [rbp-B8h]
  __int64 v26; // [rsp+60h] [rbp-B0h]
  __int64 v27; // [rsp+68h] [rbp-A8h]
  __int64 v28; // [rsp+70h] [rbp-A0h]
  __int64 v29; // [rsp+78h] [rbp-98h]
  __int64 v30; // [rsp+80h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-78h] BYREF
  PPCW_BUFFER Buffer; // [rsp+A8h] [rbp-68h]
  char **v33; // [rsp+B0h] [rbp-60h]
  _BYTE v34[16]; // [rsp+B8h] [rbp-58h] BYREF
  struct _PCW_DATA v35; // [rsp+C8h] [rbp-48h] BYREF
  struct _PCW_DATA v36; // [rsp+D8h] [rbp-38h] BYREF
  struct _PCW_DATA v37; // [rsp+E8h] [rbp-28h] BYREF
  struct _PCW_DATA v38; // [rsp+F8h] [rbp-18h] BYREF
  _BYTE v39[496]; // [rsp+110h] [rbp+0h] BYREF
  wchar_t pszDest[256]; // [rsp+300h] [rbp+1F0h] BYREF

  SP_ITERATOR_SPACE::SP_ITERATOR_SPACE((SP_ITERATOR_SPACE *)v34, 0);
  v5 = 0;
  DestinationString = 0;
  memset(v39, v6, 0x1E8u);
  v7 = a1 - 2;
  if ( v7 )
  {
    if ( v7 != 1 )
      goto LABEL_3;
    v9 = (SIO_SPACE_COUNTERS *)v39;
  }
  else
  {
    v9 = 0;
  }
  v10 = 0;
  v11 = a2->EnumerateInstances.Buffer;
  Buffer = v11;
  for ( i = SP_ITERATOR_SPACE::Next((SP_ITERATOR_SPACE *)v34); i; i = SP_ITERATOR_SPACE::Next((SP_ITERATOR_SPACE *)v34) )
  {
    if ( v9 )
      SIO_SPACE_COUNTERS::Format(v9, (struct SP_SPACE *)((char *)i + 160));
    LODWORD(Data) = *(_DWORD *)(*((_QWORD *)i + 144) + 3136LL);
    RtlStringCbPrintfW(pszDest, 0x200u, L"%s - Disk %d", *((_QWORD *)i + 142), Data);
    RtlInitUnicodeString(&DestinationString, pszDest);
    v35.Data = v9;
    v35.Size = 488;
    v5 = PcwAddInstance(v11, &DestinationString, 0, 1u, &v35);
    if ( v5 < 0 )
      break;
    v13 = (__int64 *)((char *)i + 240);
    for ( j = (__int64 *)*((_QWORD *)i + 30); j != v13; j = (__int64 *)*j )
    {
      if ( v9 )
        SIO_SPACE_COUNTERS::Format(v9, (struct SIO_COUNTERS *)(j + 4));
      LODWORD(v29) = *((unsigned __int8 *)j + 31);
      LODWORD(v28) = *((unsigned __int8 *)j + 30);
      LODWORD(v27) = *((unsigned __int8 *)j + 29);
      LODWORD(v26) = *((unsigned __int8 *)j + 28);
      LODWORD(v25) = *((unsigned __int8 *)j + 27);
      LODWORD(v24) = *((unsigned __int8 *)j + 26);
      LODWORD(v23) = *((unsigned __int8 *)j + 25);
      LODWORD(v22) = *((unsigned __int8 *)j + 24);
      LODWORD(v21) = *((unsigned __int16 *)j + 11);
      LODWORD(v20) = *((unsigned __int16 *)j + 10);
      LODWORD(v19) = *((_DWORD *)j + 4);
      LODWORD(Data) = *(_DWORD *)(*((_QWORD *)i + 144) + 3136LL);
      RtlStringCbPrintfW(
        pszDest,
        0x200u,
        L"%s - Disk %d - Node {%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
        *((_QWORD *)i + 142),
        Data,
        v19,
        v20,
        v21,
        v22,
        v23,
        v24,
        v25,
        v26,
        v27,
        v28,
        v29);
      RtlInitUnicodeString(&DestinationString, pszDest);
      v11 = Buffer;
      v36.Data = v9;
      v36.Size = 488;
      v5 = PcwAddInstance(Buffer, &DestinationString, 0, 1u, &v36);
      if ( v5 < 0 )
        goto LABEL_3;
      v13 = (__int64 *)((char *)i + 240);
    }
    v15 = (char *)i + 296;
    for ( k = (char *)*((_QWORD *)i + 37); ; k = *v33 )
    {
      v33 = (char **)k;
      if ( k == v15 )
        break;
      if ( v9 )
        SIO_SPACE_COUNTERS::Format(v9, (struct SIO_COUNTERS *)(k - 152));
      switch ( *(k - 272) )
      {
        case 3:
          v10 = L"Journal";
          break;
        case 5:
          v10 = L"Cache Log";
          break;
        case 6:
          v10 = L"Drt";
          break;
        case 7:
          v10 = L"Sst";
          break;
        case 10:
          v10 = L"Vdt";
          break;
        case 11:
          v10 = L"Cache Lines";
          break;
        default:
          break;
      }
      LODWORD(v19) = *(_DWORD *)(*((_QWORD *)i + 144) + 3136LL);
      RtlStringCbPrintfW(pszDest, 0x200u, L"%s (%s) - Disk %d", *((_QWORD *)i + 142), v10, v19);
      RtlInitUnicodeString(&DestinationString, pszDest);
      v37.Data = v9;
      v37.Size = 488;
      v5 = PcwAddInstance(v11, &DestinationString, 0, 1u, &v37);
      if ( v5 < 0 )
        goto LABEL_3;
      for ( m = (__int64 *)*v13; m != v13; m = (__int64 *)*m )
      {
        if ( v9 )
          SIO_SPACE_COUNTERS::Format(v9, (struct SIO_COUNTERS *)(m + 4));
        LODWORD(v30) = *((unsigned __int8 *)m + 31);
        LODWORD(v29) = *((unsigned __int8 *)m + 30);
        LODWORD(v28) = *((unsigned __int8 *)m + 29);
        LODWORD(v27) = *((unsigned __int8 *)m + 28);
        LODWORD(v26) = *((unsigned __int8 *)m + 27);
        LODWORD(v25) = *((unsigned __int8 *)m + 26);
        LODWORD(v24) = *((unsigned __int8 *)m + 25);
        LODWORD(v23) = *((unsigned __int8 *)m + 24);
        LODWORD(v22) = *((unsigned __int16 *)m + 11);
        LODWORD(v21) = *((unsigned __int16 *)m + 10);
        LODWORD(v20) = *((_DWORD *)m + 4);
        LODWORD(v19) = *(_DWORD *)(*((_QWORD *)i + 144) + 3136LL);
        RtlStringCbPrintfW(
          pszDest,
          0x200u,
          L"%s (%s) - Disk %d - Node {%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
          *((_QWORD *)i + 142),
          v10,
          v19,
          v20,
          v21,
          v22,
          v23,
          v24,
          v25,
          v26,
          v27,
          v28,
          v29,
          v30);
        RtlInitUnicodeString(&DestinationString, pszDest);
        v11 = Buffer;
        v38.Data = v9;
        v38.Size = 488;
        v5 = PcwAddInstance(Buffer, &DestinationString, 0, 1u, &v38);
        if ( v5 < 0 )
          goto LABEL_3;
        v13 = (__int64 *)((char *)i + 240);
      }
      v15 = (char *)i + 296;
    }
  }
LABEL_3:
  SP_ITERATOR_SPACE::~SP_ITERATOR_SPACE((SP_ITERATOR_SPACE *)v34);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140019300  push    rbp
0x140019302  push    rbx
0x140019303  push    rsi
0x140019304  push    rdi
0x140019305  push    r13
0x140019307  lea     rbp, [rsp-400h]
0x14001930f  sub     rsp, 510h
0x140019316  mov     rax, cs:__security_cookie
0x14001931d  xor     rax, rsp
0x140019320  mov     [rbp+420h+var_30], rax
0x140019327  mov     rsi, rdx
0x14001932a  mov     ebx, ecx
0x14001932c  xor     edx, edx; unsigned __int8
0x14001932e  lea     rcx, [rbp+420h+var_478]; this
0x140019332  call    ??0SP_ITERATOR_SPACE@@QEAA@E@Z; SP_ITERATOR_SPACE::SP_ITERATOR_SPACE(uchar)
0x140019337  xorps   xmm0, xmm0
0x14001933a  lea     rcx, [rbp+420h+var_420]; void *
0x14001933e  mov     r8d, 1E8h; Size
0x140019344  xor     edi, edi
0x140019346  movups  xmmword ptr [rbp+420h+DestinationString.Length], xmm0
0x14001934a  call    memset
0x14001934f  sub     ebx, 2
0x140019352  jz      short loc_140019386
0x140019354  cmp     ebx, 1
0x140019357  jz      loc_14001949D
0x14001935d  lea     rcx, [rbp+420h+var_478]; this
0x140019361  call    ??1SP_ITERATOR_SPACE@@QEAA@XZ; SP_ITERATOR_SPACE::~SP_ITERATOR_SPACE(void)
0x140019366  mov     eax, edi
0x140019368  mov     rcx, [rbp+420h+var_30]
0x14001936f  xor     rcx, rsp; StackCookie
0x140019372  call    __security_check_cookie
0x140019377  add     rsp, 510h
0x14001937e  pop     r13
0x140019380  pop     rdi
0x140019381  pop     rsi
0x140019382  pop     rbx
0x140019383  pop     rbp
0x140019384  retn
0x140019386  xor     r13d, r13d
0x140019389  mov     [rsp+530h+arg_0], r12
0x140019391  lea     rcx, [rbp+420h+var_478]; this
0x140019395  mov     [rsp+530h+arg_18], r15
0x14001939d  xor     r12d, r12d
0x1400193a0  mov     rbx, [rsi+18h]
0x1400193a4  mov     [rbp+420h+Buffer], rbx
0x1400193a8  call    ?Next@SP_ITERATOR_SPACE@@QEAAPEAVSP_SPACE@@XZ; SP_ITERATOR_SPACE::Next(void)
0x1400193ad  mov     r15, rax
0x1400193b0  test    rax, rax
0x1400193b3  jnz     short loc_1400193C7
0x1400193b5  mov     r12, [rsp+530h+arg_0]
0x1400193bd  mov     r15, [rsp+530h+arg_18]
0x1400193c5  jmp     short loc_14001935D
0x1400193c7  mov     [rsp+530h+arg_10], r14
0x1400193cf  test    r13, r13
0x1400193d2  jnz     loc_1400194A6
0x1400193d8  mov     rax, [r15+480h]
0x1400193df  lea     r8, aSDiskD; "%s - Disk %d"
0x1400193e6  mov     r9, [r15+470h]
0x1400193ed  mov     edx, 200h; cbDest
0x1400193f2  mov     ecx, [rax+0C40h]
0x1400193f8  mov     dword ptr [rsp+530h+Data], ecx
0x1400193fc  lea     rcx, [rbp+420h+pszDest]; pszDest
0x140019403  call    RtlStringCbPrintfW
0x140019408  lea     rdx, [rbp+420h+pszDest]; SourceString
0x14001940f  lea     rcx, [rbp+420h+DestinationString]; DestinationString
0x140019413  call    cs:__imp_RtlInitUnicodeString
0x14001941a  nop     dword ptr [rax+rax+00h]
0x14001941f  lea     rax, [rbp+420h+var_468]
0x140019423  mov     [rbp+420h+var_468.Data], r13
0x140019427  mov     r9d, 1; Count
0x14001942d  mov     [rsp+530h+Data], rax; Data
0x140019432  xor     r8d, r8d; Id
0x140019435  mov     [rbp+420h+var_468.Size], 1E8h
0x14001943c  lea     rdx, [rbp+420h+DestinationString]; Name
0x140019440  mov     rcx, rbx; Buffer
0x140019443  call    cs:__imp_PcwAddInstance
0x14001944a  nop     dword ptr [rax+rax+00h]
0x14001944f  mov     edi, eax
0x140019451  test    eax, eax
0x140019453  js      short loc_140019490
0x140019455  lea     rsi, [r15+0F0h]
0x14001945c  mov     r14, [rsi]
0x14001945f  mov     [rbp+420h+var_4A0], r14
0x140019463  cmp     r14, rsi
0x140019466  jnz     short loc_1400194BA
0x140019468  lea     rax, [r15+128h]
0x14001946f  mov     r14, [rax]
0x140019472  mov     [rbp+420h+var_480], r14
0x140019476  cmp     r14, rax
0x140019479  jnz     short loc_1400194D5
0x14001947b  lea     rcx, [rbp+420h+var_478]; this
0x14001947f  call    ?Next@SP_ITERATOR_SPACE@@QEAAPEAVSP_SPACE@@XZ; SP_ITERATOR_SPACE::Next(void)
0x140019484  mov     r15, rax
0x140019487  test    rax, rax
0x14001948a  jnz     loc_1400193CF
0x140019490  mov     r14, [rsp+530h+arg_10]
0x140019498  jmp     loc_1400193B5
0x14001949d  lea     r13, [rbp+420h+var_420]
0x1400194a1  jmp     loc_140019389
0x1400194a6  lea     rdx, [r15+0A0h]; struct SIO_COUNTERS *
0x1400194ad  mov     rcx, r13; this
0x1400194b0  call    ?Format@SIO_SPACE_COUNTERS@@QEAAXPEAVSIO_COUNTERS@@@Z; SIO_SPACE_COUNTERS::Format(SIO_COUNTERS *)
0x1400194b5  jmp     loc_1400193D8
0x1400194ba  test    r13, r13
0x1400194bd  jz      loc_14006A840
0x1400194c3  lea     rdx, [r14+20h]; struct SIO_COUNTERS *
0x1400194c7  mov     rcx, r13; this
0x1400194ca  call    ?Format@SIO_SPACE_COUNTERS@@QEAAXPEAVSIO_COUNTERS@@@Z; SIO_SPACE_COUNTERS::Format(SIO_COUNTERS *)
0x1400194cf  nop
0x1400194d0  jmp     loc_14006A840
0x1400194d5  test    r13, r13
0x1400194d8  jz      loc_14006A942
0x1400194de  lea     rdx, [r14-98h]; struct SIO_COUNTERS *
0x1400194e5  mov     rcx, r13; this
0x1400194e8  call    ?Format@SIO_SPACE_COUNTERS@@QEAAXPEAVSIO_COUNTERS@@@Z; SIO_SPACE_COUNTERS::Format(SIO_COUNTERS *)
0x1400194ed  nop
0x1400194ee  jmp     loc_14006A942
0x14006a840  movzx   eax, byte ptr [r14+1Fh]
0x14006a845  movzx   ecx, byte ptr [r14+1Eh]
0x14006a84a  movzx   edx, byte ptr [r14+1Dh]
0x14006a84f  movzx   r8d, byte ptr [r14+1Ch]
0x14006a854  movzx   r9d, byte ptr [r14+1Bh]
0x14006a859  movzx   r10d, byte ptr [r14+1Ah]
0x14006a85e  movzx   r11d, byte ptr [r14+19h]
0x14006a863  movzx   ebx, byte ptr [r14+18h]
0x14006a868  movzx   edi, word ptr [r14+16h]
0x14006a86d  movzx   esi, word ptr [r14+14h]
0x14006a872  mov     r14, [r15+480h]
0x14006a879  mov     dword ptr [rsp+530h+var_4B8], eax
0x14006a87d  mov     rax, [rbp+420h+var_4A0]
0x14006a881  mov     dword ptr [rsp+530h+var_4C0], ecx
0x14006a885  lea     rcx, [rbp+420h+pszDest]; pszDest
0x14006a88c  mov     dword ptr [rsp+530h+var_4C8], edx
0x14006a890  mov     edx, 200h; cbDest
0x14006a895  mov     dword ptr [rsp+530h+var_4D0], r8d
0x14006a89a  lea     r8, aSDiskDNode08lx; "%s - Disk %d - Node {%08lx-%04x-%04x-%0"...
0x14006a8a1  mov     eax, [rax+10h]
0x14006a8a4  mov     dword ptr [rsp+530h+var_4D8], r9d
0x14006a8a9  mov     r9, [r15+470h]
0x14006a8b0  mov     dword ptr [rsp+530h+var_4E0], r10d
0x14006a8b5  mov     dword ptr [rsp+530h+var_4E8], r11d
0x14006a8ba  mov     dword ptr [rsp+530h+var_4F0], ebx
0x14006a8be  mov     dword ptr [rsp+530h+var_4F8], edi
0x14006a8c2  mov     dword ptr [rsp+530h+var_500], esi
0x14006a8c6  mov     dword ptr [rsp+530h+var_508], eax
0x14006a8ca  mov     eax, [r14+0C40h]
0x14006a8d1  mov     dword ptr [rsp+530h+Data], eax
0x14006a8d5  call    RtlStringCbPrintfW
0x14006a8da  lea     rdx, [rbp+420h+pszDest]; SourceString
0x14006a8e1  lea     rcx, [rbp+420h+DestinationString]; DestinationString
0x14006a8e5  call    cs:__imp_RtlInitUnicodeString
0x14006a8ec  nop     dword ptr [rax+rax+00h]
0x14006a8f1  mov     rbx, [rbp+420h+Buffer]
0x14006a8f5  lea     rax, [rbp+420h+var_458]
0x14006a8f9  mov     rcx, rbx; Buffer
0x14006a8fc  mov     [rsp+530h+Data], rax; Data
0x14006a901  mov     r9d, 1; Count
0x14006a907  mov     [rbp+420h+var_458.Data], r13
0x14006a90b  xor     r8d, r8d; Id
0x14006a90e  mov     [rbp+420h+var_458.Size], 1E8h
0x14006a915  lea     rdx, [rbp+420h+DestinationString]; Name
0x14006a919  call    cs:__imp_PcwAddInstance
0x14006a920  nop     dword ptr [rax+rax+00h]
0x14006a925  mov     edi, eax
0x14006a927  test    eax, eax
0x14006a929  js      loc_140019490
0x14006a92f  mov     r14, [rbp+420h+var_4A0]
0x14006a933  lea     rsi, [r15+0F0h]
0x14006a93a  mov     r14, [r14]
0x14006a93d  jmp     loc_14001945F
0x14006a942  movzx   eax, byte ptr [r14-110h]
0x14006a94a  add     eax, 0FFFFFFFDh; switch 9 cases
0x14006a94d  cmp     eax, 8
0x14006a950  ja      short def_14006A965; jumptable 000000014006A965 default case, cases 4,8,9
0x14006a952  lea     rdx, cs:140000000h
0x14006a959  cdqe
0x14006a95b  mov     ecx, ds:(jpt_14006A965 - 140000000h)[rdx+rax*4]
0x14006a962  add     rcx, rdx
0x14006a965  jmp     rcx; switch jump
0x14006a96b  lea     r12, aJournal; jumptable 000000014006A965 case 3
0x14006a972  jmp     short def_14006A965; jumptable 000000014006A965 default case, cases 4,8,9
0x14006a974  lea     r12, aCacheLines; jumptable 000000014006A965 case 11
0x14006a97b  jmp     short def_14006A965; jumptable 000000014006A965 default case, cases 4,8,9
0x14006a97d  lea     r12, aCacheLog; jumptable 000000014006A965 case 5
0x14006a984  jmp     short def_14006A965; jumptable 000000014006A965 default case, cases 4,8,9
0x14006a986  lea     r12, aDrt; jumptable 000000014006A965 case 6
0x14006a98d  jmp     short def_14006A965; jumptable 000000014006A965 default case, cases 4,8,9
0x14006a98f  lea     r12, aSst; jumptable 000000014006A965 case 7
0x14006a996  jmp     short def_14006A965; jumptable 000000014006A965 default case, cases 4,8,9
0x14006a998  lea     r12, aVdt; jumptable 000000014006A965 case 10
0x14006a99f  mov     rax, [r15+480h]; jumptable 000000014006A965 default case, cases 4,8,9
0x14006a9a6  lea     r8, aSSDiskD; "%s (%s) - Disk %d"
0x14006a9ad  mov     r9, [r15+470h]
0x14006a9b4  mov     edx, 200h; cbDest
0x14006a9b9  mov     ecx, [rax+0C40h]
0x14006a9bf  mov     dword ptr [rsp+530h+var_508], ecx
0x14006a9c3  lea     rcx, [rbp+420h+pszDest]; pszDest
0x14006a9ca  mov     [rsp+530h+Data], r12
0x14006a9cf  call    RtlStringCbPrintfW
0x14006a9d4  lea     rdx, [rbp+420h+pszDest]; SourceString
0x14006a9db  lea     rcx, [rbp+420h+DestinationString]; DestinationString
0x14006a9df  call    cs:__imp_RtlInitUnicodeString
0x14006a9e6  nop     dword ptr [rax+rax+00h]
0x14006a9eb  lea     rax, [rbp+420h+var_448]
0x14006a9ef  mov     [rbp+420h+var_448.Data], r13
0x14006a9f3  mov     r9d, 1; Count
0x14006a9f9  mov     [rsp+530h+Data], rax; Data
0x14006a9fe  xor     r8d, r8d; Id
0x14006aa01  mov     [rbp+420h+var_448.Size], 1E8h
0x14006aa08  lea     rdx, [rbp+420h+DestinationString]; Name
0x14006aa0c  mov     rcx, rbx; Buffer
0x14006aa0f  call    cs:__imp_PcwAddInstance
0x14006aa16  nop     dword ptr [rax+rax+00h]
0x14006aa1b  mov     edi, eax
0x14006aa1d  test    eax, eax
0x14006aa1f  js      loc_140019490
0x14006aa25  mov     r14, [rsi]
0x14006aa28  mov     [rbp+420h+var_4A0], r14
0x14006aa2c  cmp     r14, rsi
0x14006aa2f  jz      loc_14006AB50
0x14006aa35  test    r13, r13
0x14006aa38  jz      short loc_14006AA46
0x14006aa3a  lea     rdx, [r14+20h]; struct SIO_COUNTERS *
0x14006aa3e  mov     rcx, r13; this
0x14006aa41  call    ?Format@SIO_SPACE_COUNTERS@@QEAAXPEAVSIO_COUNTERS@@@Z; SIO_SPACE_COUNTERS::Format(SIO_COUNTERS *)
0x14006aa46  movzx   eax, byte ptr [r14+1Fh]
0x14006aa4b  movzx   ecx, byte ptr [r14+1Eh]
0x14006aa50  movzx   edx, byte ptr [r14+1Dh]
0x14006aa55  movzx   r8d, byte ptr [r14+1Ch]
0x14006aa5a  movzx   r9d, byte ptr [r14+1Bh]
0x14006aa5f  movzx   r10d, byte ptr [r14+1Ah]
0x14006aa64  movzx   r11d, byte ptr [r14+19h]
0x14006aa69  movzx   ebx, byte ptr [r14+18h]
0x14006aa6e  movzx   edi, word ptr [r14+16h]
0x14006aa73  movzx   esi, word ptr [r14+14h]
0x14006aa78  mov     r14, [r15+480h]
0x14006aa7f  mov     [rsp+530h+var_4B0], eax
0x14006aa86  mov     rax, [rbp+420h+var_4A0]
0x14006aa8a  mov     dword ptr [rsp+530h+var_4B8], ecx
0x14006aa8e  lea     rcx, [rbp+420h+pszDest]; pszDest
0x14006aa95  mov     dword ptr [rsp+530h+var_4C0], edx
0x14006aa99  mov     edx, 200h; cbDest
0x14006aa9e  mov     dword ptr [rsp+530h+var_4C8], r8d
0x14006aaa3  lea     r8, aSSDiskDNode08l; "%s (%s) - Disk %d - Node {%08lx-%04x-%0"...
0x14006aaaa  mov     eax, [rax+10h]
0x14006aaad  mov     dword ptr [rsp+530h+var_4D0], r9d
0x14006aab2  mov     r9, [r15+470h]
0x14006aab9  mov     dword ptr [rsp+530h+var_4D8], r10d
0x14006aabe  mov     dword ptr [rsp+530h+var_4E0], r11d
0x14006aac3  mov     dword ptr [rsp+530h+var_4E8], ebx
0x14006aac7  mov     dword ptr [rsp+530h+var_4F0], edi
0x14006aacb  mov     dword ptr [rsp+530h+var_4F8], esi
0x14006aacf  mov     dword ptr [rsp+530h+var_500], eax
0x14006aad3  mov     eax, [r14+0C40h]
0x14006aada  mov     dword ptr [rsp+530h+var_508], eax
0x14006aade  mov     [rsp+530h+Data], r12
0x14006aae3  call    RtlStringCbPrintfW
0x14006aae8  lea     rdx, [rbp+420h+pszDest]; SourceString
0x14006aaef  lea     rcx, [rbp+420h+DestinationString]; DestinationString
0x14006aaf3  call    cs:__imp_RtlInitUnicodeString
0x14006aafa  nop     dword ptr [rax+rax+00h]
0x14006aaff  mov     rbx, [rbp+420h+Buffer]
0x14006ab03  lea     rax, [rbp+420h+var_438]
0x14006ab07  mov     rcx, rbx; Buffer
0x14006ab0a  mov     [rsp+530h+Data], rax; Data
0x14006ab0f  mov     r9d, 1; Count
0x14006ab15  mov     [rbp+420h+var_438.Data], r13
0x14006ab19  xor     r8d, r8d; Id
0x14006ab1c  mov     [rbp+420h+var_438.Size], 1E8h
0x14006ab23  lea     rdx, [rbp+420h+DestinationString]; Name
0x14006ab27  call    cs:__imp_PcwAddInstance
0x14006ab2e  nop     dword ptr [rax+rax+00h]
0x14006ab33  mov     edi, eax
0x14006ab35  test    eax, eax
0x14006ab37  js      loc_140019490
0x14006ab3d  mov     r14, [rbp+420h+var_4A0]
0x14006ab41  lea     rsi, [r15+0F0h]
0x14006ab48  mov     r14, [r14]
0x14006ab4b  jmp     loc_14006AA28
0x14006ab50  mov     r14, [rbp+420h+var_480]
0x14006ab54  lea     rax, [r15+128h]
0x14006ab5b  mov     r14, [r14]
0x14006ab5e  jmp     loc_140019472
```
