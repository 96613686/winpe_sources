# ScheduledToasts::UnpackPersistedEvent(_GUID,void *,ScheduledToasts::_PERSISTEDTOAST * *,int *)

- ea: `0x18002ff5c`
- end: `0x1800303f7`
- name: `?UnpackPersistedEvent@ScheduledToasts@@CAJU_GUID@@PEAXPEAPEAU_PERSISTEDTOAST@1@PEAH@Z`
- size: `1179`
- prototype: `static int(struct _GUID *__struct_ptr, void *, struct ScheduledToasts::_PERSISTEDTOAST **, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f2ac`
- `0x1800730b4`
- `0x18008e000`

## callees

- `0x18002ee38`
- `0x18002ff5c`
- `0x1800af0a4`
- `0x1800ba574`
- `0x1800bc541`
- `0x1800d7400`
- `0x1800d78a8`
- `0x1800d794c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030044`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030044`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fff3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030036`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fff3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030036`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030001`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030001`
- `ntdll!RtlNtStatusToDosError` at `0x18003008a`
- `ntdll!RtlNtStatusToDosError` at `0x18003008a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003010c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003010c`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x18002ff94`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x18002ff94`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x18002ffe0`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x18002ffe0`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x180030179`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x180030179`

## string_xrefs

- `0x18002ffac`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800300ac`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180030183`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`

## pseudocode

```c
__int64 __fastcall ScheduledToasts::UnpackPersistedEvent(
        struct _GUID *a1,
        void *a2,
        struct ScheduledToasts::_PERSISTEDTOAST **a3,
        int *a4)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  unsigned int v12; // eax
  char *v13; // r14
  HANDLE ProcessHeap; // rax
  _DWORD *v15; // rdi
  signed int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  char *v19; // rbx
  int v20; // eax
  char *v21; // rbx
  size_t Size; // [rsp+20h] [rbp-10h] BYREF
  unsigned int *v23; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]

  v23 = 0;
  LODWORD(Size) = 0;
  if ( a4 )
    *a4 = 1;
  v8 = BiPtQueryBrokeredEvent(a1, &Size, &v23);
  if ( v8 < 0 )
  {
    v16 = RtlNtStatusToDosError(v8);
    v9 = v16;
    if ( v16 > 0 )
      v9 = (unsigned __int16)v16 | 0x80070000;
  }
  else
  {
    v9 = 0;
  }
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x42B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)v9,
      Size);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v17 = 56;
      v18 = v9;
      goto LABEL_21;
    }
    goto LABEL_7;
  }
  v12 = v23[12];
  LODWORD(Size) = v12;
  if ( v12 != 6144 && v12 != 6128 && v12 != 5936 && v12 != 5792 && v12 != 5720 )
  {
    BiPtDeleteEvent(a1);
    v9 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x43A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)0x80070057LL,
      Size);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v17 = 57;
      v18 = 2147942487LL;
      goto LABEL_21;
    }
    goto LABEL_7;
  }
  v13 = (char *)v23 + v23[10];
  ProcessHeap = GetProcessHeap();
  v15 = HeapAlloc(ProcessHeap, 0, 0x1800u);
  if ( v15 )
  {
    if ( (_DWORD)Size == 6144 )
    {
      memcpy_0(v15, (char *)v23 + v23[11], 0x1800u);
      goto LABEL_14;
    }
    if ( (_DWORD)Size != 6128 && (_DWORD)Size != 5936 && (_DWORD)Size != 5792 && (_DWORD)Size != 5720 )
      goto LABEL_14;
    memset_0(v15, 0, 0x1800u);
    if ( (_DWORD)Size == 5720 || (_DWORD)Size == 5792 )
    {
      ScheduledToasts::MigrateFromV1V2ToCurrentVersion(
        (struct ScheduledToasts::_PERSISTEDTOAST *)v15,
        (unsigned __int8 *)v23 + v23[11],
        Size);
    }
    else
    {
      if ( (_DWORD)Size == 5936 )
      {
        v19 = (char *)v23 + v23[11];
        ScheduledToasts::MigrateToCurrentVersion<ScheduledToasts::_PERSISTEDTOAST_V3 *>(v19, v15);
        *(_OWORD *)(v15 + 1467) = *((_OWORD *)v19 + 358);
        *(_OWORD *)(v15 + 1471) = *((_OWORD *)v19 + 359);
        *((_WORD *)v15 + 2950) = *((_WORD *)v19 + 2880);
        *(_OWORD *)((char *)v15 + 5998) = *(_OWORD *)(v19 + 5762);
        *(_OWORD *)((char *)v15 + 6014) = *(_OWORD *)(v19 + 5778);
        *((_WORD *)v15 + 3015) = *((_WORD *)v19 + 2897);
        v20 = *((_DWORD *)v19 + 1449);
      }
      else
      {
        if ( (_DWORD)Size != 6128 )
        {
          if ( (_DWORD)Size == 6144 )
            ScheduledToasts::MigrateFromV5ToCurrentVersion(
              (struct ScheduledToasts::_PERSISTEDTOAST *)v15,
              (struct ScheduledToasts::_PERSISTEDTOAST_V5 *)((char *)v23 + v23[11]));
          goto LABEL_48;
        }
        v21 = (char *)v23 + v23[11];
        ScheduledToasts::MigrateToCurrentVersion<ScheduledToasts::_PERSISTEDTOAST_V3 *>(v21, v15);
        *(_OWORD *)(v15 + 1467) = *(_OWORD *)(v21 + 5868);
        *(_OWORD *)(v15 + 1471) = *(_OWORD *)(v21 + 5884);
        *(_OWORD *)(v15 + 1475) = *(_OWORD *)(v21 + 5900);
        *(_OWORD *)(v15 + 1479) = *(_OWORD *)(v21 + 5916);
        *(_OWORD *)(v15 + 1483) = *(_OWORD *)(v21 + 5932);
        *(_OWORD *)(v15 + 1487) = *(_OWORD *)(v21 + 5948);
        *(_OWORD *)(v15 + 1491) = *(_OWORD *)(v21 + 5964);
        *(_OWORD *)(v15 + 1495) = *(_OWORD *)(v21 + 5980);
        *((_WORD *)v15 + 2998) = *((_WORD *)v21 + 2998);
        *(_OWORD *)((char *)v15 + 5998) = *(_OWORD *)(v21 + 5998);
        *(_OWORD *)((char *)v15 + 6014) = *(_OWORD *)(v21 + 6014);
        *(_OWORD *)((char *)v15 + 6030) = *(_OWORD *)(v21 + 6030);
        *(_OWORD *)((char *)v15 + 6046) = *(_OWORD *)(v21 + 6046);
        *(_OWORD *)((char *)v15 + 6062) = *(_OWORD *)(v21 + 6062);
        *(_OWORD *)((char *)v15 + 6078) = *(_OWORD *)(v21 + 6078);
        *(_OWORD *)((char *)v15 + 6094) = *(_OWORD *)(v21 + 6094);
        *(_OWORD *)((char *)v15 + 6110) = *(_OWORD *)(v21 + 6110);
        *((_WORD *)v15 + 3063) = *((_WORD *)v21 + 3063);
        v20 = *((_DWORD *)v21 + 1432);
      }
      v15[1432] = v20;
    }
LABEL_48:
    *v15 = 6;
LABEL_14:
    if ( a2 && !EqualSid(a2, v13) && a4 )
      *a4 = 0;
    *a3 = (struct ScheduledToasts::_PERSISTEDTOAST *)v15;
    v9 = 0;
    goto LABEL_7;
  }
  v9 = -2147024882;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x440,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
    (const char *)0x8007000ELL,
    Size);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v17 = 58;
    v18 = 2147942414LL;
LABEL_21:
    WPP_SF_d(v10[2], v17, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids, v18);
  }
LABEL_7:
  if ( v23 )
  {
    BiPtFreeMemory();
    v23 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18002ff5c  push    rbp
0x18002ff5e  push    rbx
0x18002ff5f  push    rsi
0x18002ff60  push    rdi
0x18002ff61  push    r12
0x18002ff63  push    r14
0x18002ff65  push    r15
0x18002ff67  mov     rbp, rsp
0x18002ff6a  sub     rsp, 30h
0x18002ff6e  xor     edi, edi
0x18002ff70  mov     rsi, r9
0x18002ff73  mov     [rbp+var_8], rdi
0x18002ff77  mov     r12, r8
0x18002ff7a  mov     dword ptr [rbp+Size], edi
0x18002ff7d  mov     r15, rdx
0x18002ff80  mov     r14, rcx
0x18002ff83  test    r9, r9
0x18002ff86  jnz     loc_18003012A
0x18002ff8c  lea     r8, [rbp+var_8]
0x18002ff90  lea     rdx, [rbp+Size]
0x18002ff94  call    cs:__imp_BiPtQueryBrokeredEvent
0x18002ff9a  test    eax, eax
0x18002ff9c  js      loc_180030088
0x18002ffa2  xor     ebx, ebx
0x18002ffa4  test    ebx, ebx
0x18002ffa6  jns     short loc_180030018
0x18002ffa8  mov     rcx, [rbp+38h]; this
0x18002ffac  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002ffb3  mov     r9d, ebx; char *
0x18002ffb6  mov     edx, 42Bh; void *
0x18002ffbb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ffc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffc7  lea     rax, WPP_GLOBAL_Control
0x18002ffce  cmp     rcx, rax
0x18002ffd1  jnz     loc_180030136
0x18002ffd7  mov     rcx, [rbp+var_8]
0x18002ffdb  test    rcx, rcx
0x18002ffde  jz      short loc_18002FFEE
0x18002ffe0  call    cs:__imp_BiPtFreeMemory
0x18002ffe6  mov     [rbp+var_8], 0
0x18002ffee  test    rdi, rdi
0x18002fff1  jz      short loc_180030007
0x18002fff3  call    cs:__imp_GetProcessHeap
0x18002fff9  mov     r8, rdi; lpMem
0x18002fffc  xor     edx, edx; dwFlags
0x18002fffe  mov     rcx, rax; hHeap
0x180030001  call    cs:__imp_HeapFree
0x180030007  mov     eax, ebx
0x180030009  add     rsp, 30h
0x18003000d  pop     r15
0x18003000f  pop     r14
0x180030011  pop     r12
0x180030013  pop     rdi
0x180030014  pop     rsi
0x180030015  pop     rbx
0x180030016  pop     rbp
0x180030017  retn
0x180030018  mov     rdx, [rbp+var_8]
0x18003001c  mov     ebx, 1800h
0x180030021  mov     eax, [rdx+30h]
0x180030024  mov     dword ptr [rbp+Size], eax
0x180030027  cmp     eax, ebx
0x180030029  jnz     loc_18003014A
0x18003002f  mov     r14d, [rdx+28h]
0x180030033  add     r14, rdx
0x180030036  call    cs:__imp_GetProcessHeap
0x18003003c  mov     r8, rbx; dwBytes
0x18003003f  xor     edx, edx; dwFlags
0x180030041  mov     rcx, rax; hHeap
0x180030044  call    cs:__imp_HeapAlloc
0x18003004a  mov     rdi, rax
0x18003004d  test    rax, rax
0x180030050  jz      short loc_1800300A8
0x180030052  mov     eax, dword ptr [rbp+Size]
0x180030055  cmp     eax, ebx
0x180030057  jnz     loc_1800301CD
0x18003005d  mov     r8d, eax; Size
0x180030060  mov     rcx, rdi; void *
0x180030063  mov     rax, [rbp+var_8]
0x180030067  mov     edx, [rax+2Ch]
0x18003006a  add     rdx, rax; Src
0x18003006d  call    memcpy_0
0x180030072  test    r15, r15
0x180030075  jnz     loc_180030106
0x18003007b  mov     [r12], rdi
0x18003007f  xor     edi, edi
0x180030081  xor     ebx, ebx
0x180030083  jmp     loc_18002FFD7
0x180030088  mov     ecx, eax; Status
0x18003008a  call    cs:__imp_RtlNtStatusToDosError
0x180030090  mov     ebx, eax
0x180030092  test    eax, eax
0x180030094  jle     loc_18002FFA4
0x18003009a  movzx   ebx, ax
0x18003009d  or      ebx, 80070000h
0x1800300a3  jmp     loc_18002FFA4
0x1800300a8  mov     rcx, [rbp+38h]; this
0x1800300ac  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800300b3  mov     ebx, 8007000Eh
0x1800300b8  mov     edx, 440h; void *
0x1800300bd  mov     r9d, ebx; char *
0x1800300c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800300c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300cc  lea     rax, WPP_GLOBAL_Control
0x1800300d3  cmp     rcx, rax
0x1800300d6  jz      loc_18002FFD7
0x1800300dc  test    byte ptr [rcx+1Ch], 80h
0x1800300e0  jz      loc_18002FFD7
0x1800300e6  mov     edx, 3Ah ; ':'
0x1800300eb  mov     r9d, 8007000Eh
0x1800300f1  mov     rcx, [rcx+10h]
0x1800300f5  lea     r8, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids
0x1800300fc  call    WPP_SF_d
0x180030101  jmp     loc_18002FFD7
0x180030106  mov     rdx, r14; pSid2
0x180030109  mov     rcx, r15; pSid1
0x18003010c  call    cs:__imp_EqualSid
0x180030112  test    eax, eax
0x180030114  jnz     loc_18003007B
0x18003011a  test    rsi, rsi
0x18003011d  jz      loc_18003007B
0x180030123  mov     [rsi], eax
0x180030125  jmp     loc_18003007B
0x18003012a  mov     dword ptr [r9], 1
0x180030131  jmp     loc_18002FF8C
0x180030136  test    byte ptr [rcx+1Ch], 80h
0x18003013a  jz      loc_18002FFD7
0x180030140  mov     edx, 38h ; '8'
0x180030145  mov     r9d, ebx
0x180030148  jmp     short loc_1800300F1
0x18003014a  cmp     eax, 17F0h
0x18003014f  jz      loc_18003002F
0x180030155  cmp     eax, 1730h
0x18003015a  jz      loc_18003002F
0x180030160  cmp     eax, 16A0h
0x180030165  jz      loc_18003002F
0x18003016b  cmp     eax, 1658h
0x180030170  jz      loc_18003002F
0x180030176  mov     rcx, r14
0x180030179  call    cs:__imp_BiPtDeleteEvent
0x18003017f  mov     rcx, [rbp+38h]; this
0x180030183  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003018a  mov     ebx, 80070057h
0x18003018f  mov     edx, 43Ah; void *
0x180030194  mov     r9d, ebx; char *
0x180030197  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003019c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800301a3  lea     rax, WPP_GLOBAL_Control
0x1800301aa  cmp     rcx, rax
0x1800301ad  jz      loc_18002FFD7
0x1800301b3  test    byte ptr [rcx+1Ch], 80h
0x1800301b7  jz      loc_18002FFD7
0x1800301bd  mov     edx, 39h ; '9'
0x1800301c2  mov     r9d, 80070057h
0x1800301c8  jmp     loc_1800300F1
0x1800301cd  cmp     eax, 17F0h
0x1800301d2  jz      short loc_1800301ED
0x1800301d4  cmp     eax, 1730h
0x1800301d9  jz      short loc_1800301ED
0x1800301db  cmp     eax, 16A0h
0x1800301e0  jz      short loc_1800301ED
0x1800301e2  cmp     eax, 1658h
0x1800301e7  jnz     loc_180030072
0x1800301ed  mov     r8, rbx; Size
0x1800301f0  xor     edx, edx; Val
0x1800301f2  mov     rcx, rdi; void *
0x1800301f5  call    memset_0
0x1800301fa  mov     r8d, dword ptr [rbp+Size]; unsigned int
0x1800301fe  cmp     r8d, 1658h
0x180030205  jz      loc_1800303DA
0x18003020b  cmp     r8d, 16A0h
0x180030212  jz      loc_1800303DA
0x180030218  cmp     r8d, 1730h
0x18003021f  jnz     short loc_180030295
0x180030221  mov     rcx, [rbp+var_8]
0x180030225  mov     rdx, rdi
0x180030228  mov     ebx, [rcx+2Ch]
0x18003022b  add     rbx, rcx
0x18003022e  mov     rcx, rbx
0x180030231  call    ??$MigrateToCurrentVersion@PEAU_PERSISTEDTOAST_V3@ScheduledToasts@@@ScheduledToasts@@CAXPEAU_PERSISTEDTOAST_V3@0@PEAU_PERSISTEDTOAST@0@@Z; ScheduledToasts::MigrateToCurrentVersion<ScheduledToasts::_PERSISTEDTOAST_V3 *>(ScheduledToasts::_PERSISTEDTOAST_V3 *,ScheduledToasts::_PERSISTEDTOAST *)
0x180030236  movups  xmm0, xmmword ptr [rbx+1660h]
0x18003023d  movups  xmmword ptr [rdi+16ECh], xmm0
0x180030244  movups  xmm1, xmmword ptr [rbx+1670h]
0x18003024b  movups  xmmword ptr [rdi+16FCh], xmm1
0x180030252  movzx   eax, word ptr [rbx+1680h]
0x180030259  mov     [rdi+170Ch], ax
0x180030260  movups  xmm0, xmmword ptr [rbx+1682h]
0x180030267  movups  xmmword ptr [rdi+176Eh], xmm0
0x18003026e  movups  xmm1, xmmword ptr [rbx+1692h]
0x180030275  movups  xmmword ptr [rdi+177Eh], xmm1
0x18003027c  movzx   eax, word ptr [rbx+16A2h]
0x180030283  mov     [rdi+178Eh], ax
0x18003028a  mov     eax, [rbx+16A4h]
0x180030290  jmp     loc_1800303B9
0x180030295  cmp     r8d, 17F0h
0x18003029c  jnz     loc_1800303C1
0x1800302a2  mov     rcx, [rbp+var_8]
0x1800302a6  mov     rdx, rdi
0x1800302a9  mov     ebx, [rcx+2Ch]
0x1800302ac  add     rbx, rcx
0x1800302af  mov     rcx, rbx
0x1800302b2  call    ??$MigrateToCurrentVersion@PEAU_PERSISTEDTOAST_V3@ScheduledToasts@@@ScheduledToasts@@CAXPEAU_PERSISTEDTOAST_V3@0@PEAU_PERSISTEDTOAST@0@@Z; ScheduledToasts::MigrateToCurrentVersion<ScheduledToasts::_PERSISTEDTOAST_V3 *>(ScheduledToasts::_PERSISTEDTOAST_V3 *,ScheduledToasts::_PERSISTEDTOAST *)
0x1800302b7  movups  xmm0, xmmword ptr [rbx+16ECh]
0x1800302be  movups  xmmword ptr [rdi+16ECh], xmm0
0x1800302c5  movups  xmm1, xmmword ptr [rbx+16FCh]
0x1800302cc  movups  xmmword ptr [rdi+16FCh], xmm1
0x1800302d3  movups  xmm0, xmmword ptr [rbx+170Ch]
0x1800302da  movups  xmmword ptr [rdi+170Ch], xmm0
0x1800302e1  movups  xmm1, xmmword ptr [rbx+171Ch]
0x1800302e8  movups  xmmword ptr [rdi+171Ch], xmm1
0x1800302ef  movups  xmm0, xmmword ptr [rbx+172Ch]
0x1800302f6  movups  xmmword ptr [rdi+172Ch], xmm0
0x1800302fd  movups  xmm1, xmmword ptr [rbx+173Ch]
0x180030304  movups  xmmword ptr [rdi+173Ch], xmm1
0x18003030b  movups  xmm0, xmmword ptr [rbx+174Ch]
0x180030312  movups  xmmword ptr [rdi+174Ch], xmm0
0x180030319  movups  xmm1, xmmword ptr [rbx+175Ch]
0x180030320  movups  xmmword ptr [rdi+175Ch], xmm1
0x180030327  movzx   eax, word ptr [rbx+176Ch]
0x18003032e  mov     [rdi+176Ch], ax
0x180030335  movups  xmm0, xmmword ptr [rbx+176Eh]
0x18003033c  movups  xmmword ptr [rdi+176Eh], xmm0
0x180030343  movups  xmm1, xmmword ptr [rbx+177Eh]
0x18003034a  movups  xmmword ptr [rdi+177Eh], xmm1
0x180030351  movups  xmm0, xmmword ptr [rbx+178Eh]
0x180030358  movups  xmmword ptr [rdi+178Eh], xmm0
0x18003035f  movups  xmm1, xmmword ptr [rbx+179Eh]
0x180030366  movups  xmmword ptr [rdi+179Eh], xmm1
0x18003036d  movups  xmm0, xmmword ptr [rbx+17AEh]
0x180030374  movups  xmmword ptr [rdi+17AEh], xmm0
0x18003037b  movups  xmm1, xmmword ptr [rbx+17BEh]
0x180030382  movups  xmmword ptr [rdi+17BEh], xmm1
0x180030389  movups  xmm0, xmmword ptr [rbx+17CEh]
0x180030390  movups  xmmword ptr [rdi+17CEh], xmm0
0x180030397  movups  xmm1, xmmword ptr [rbx+17DEh]
0x18003039e  movups  xmmword ptr [rdi+17DEh], xmm1
0x1800303a5  movzx   eax, word ptr [rbx+17EEh]
0x1800303ac  mov     [rdi+17EEh], ax
0x1800303b3  mov     eax, [rbx+1660h]
0x1800303b9  mov     [rdi+1660h], eax
0x1800303bf  jmp     short loc_1800303EC
0x1800303c1  cmp     r8d, ebx
0x1800303c4  jnz     short loc_1800303EC
0x1800303c6  mov     rax, [rbp+var_8]
0x1800303ca  mov     rcx, rdi; struct ScheduledToasts::_PERSISTEDTOAST *
0x1800303cd  mov     edx, [rax+2Ch]
0x1800303d0  add     rdx, rax; struct ScheduledToasts::_PERSISTEDTOAST_V5 *
0x1800303d3  call    ?MigrateFromV5ToCurrentVersion@ScheduledToasts@@CAXPEAU_PERSISTEDTOAST@1@PEAU_PERSISTEDTOAST_V5@1@@Z; ScheduledToasts::MigrateFromV5ToCurrentVersion(ScheduledToasts::_PERSISTEDTOAST *,ScheduledToasts::_PERSISTEDTOAST_V5 *)
0x1800303d8  jmp     short loc_1800303EC
0x1800303da  mov     rax, [rbp+var_8]
0x1800303de  mov     rcx, rdi; struct ScheduledToasts::_PERSISTEDTOAST *
0x1800303e1  mov     edx, [rax+2Ch]
0x1800303e4  add     rdx, rax; unsigned __int8 *
0x1800303e7  call    ?MigrateFromV1V2ToCurrentVersion@ScheduledToasts@@CAXPEAU_PERSISTEDTOAST@1@PEAEK@Z; ScheduledToasts::MigrateFromV1V2ToCurrentVersion(ScheduledToasts::_PERSISTEDTOAST *,uchar *,ulong)
0x1800303ec  mov     dword ptr [rdi], 6
0x1800303f2  jmp     loc_180030072
```
