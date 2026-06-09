# UbpmHardeningListInsert

- ea: `0x180018ef0`
- end: `0x180019478`
- name: `UbpmHardeningListInsert`
- size: `1416`
- prototype: `__int64 __fastcall(wchar_t *String2, const WCHAR *, unsigned int, void *, struct _LIST_ENTRY *, char, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d5c0`

## callees

- `0x18000f9a0`
- `0x180017610`
- `0x180018ef0`
- `0x180019d90`
- `0x18001e9f4`
- `0x1800208bc`
- `0x18003c6d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800191f6`
- `msvcrt!_wcsicmp` at `0x1800191f6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018f6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018f6b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018fdd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001922c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018fdd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001922c`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180019185`
- `ntdll!RtlCreateVirtualAccountSid` at `0x1800191ba`
- `ntdll!RtlCreateVirtualAccountSid` at `0x180019185`
- `ntdll!RtlCreateVirtualAccountSid` at `0x1800191ba`
- `ntdll!RtlInitUnicodeString` at `0x180019170`
- `ntdll!RtlInitUnicodeString` at `0x180019170`
- `ntdll!RtlNtStatusToDosError` at `0x1800193e6`
- `ntdll!RtlNtStatusToDosError` at `0x1800193e6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001906e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001906e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800190eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019386`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800190eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180019386`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019074`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001923a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001923a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019404`

## pseudocode

```c
__int64 __fastcall UbpmHardeningListInsert(
        wchar_t *String2,
        const WCHAR *a2,
        unsigned int a3,
        void *a4,
        struct _LIST_ENTRY *a5,
        char a6,
        char a7)
{
  DWORD v7; // ebx
  unsigned int v9; // ebp
  struct _LIST_ENTRY *v11; // r13
  DWORD v12; // r14d
  __int64 LengthSid; // r15
  __int64 v14; // rbx
  unsigned int v16; // ebx
  struct _LIST_ENTRY *v17; // rax
  char v18; // bp
  unsigned __int64 v19; // r8
  struct _LIST_ENTRY *Flink; // r9
  __int64 v21; // rcx
  wchar_t *v22; // rdx
  struct _LIST_ENTRY *v23; // rcx
  DWORD CurrentThreadId; // eax
  struct _LIST_ENTRY *v25; // rbx
  struct _LIST_ENTRY *v26; // rdi
  unsigned __int8 i; // si
  struct _LIST_ENTRY *v28; // rax
  int v29; // r8d
  void *v31; // rax
  void *v32; // rsi
  NTSTATUS v33; // eax
  PSID v34; // r8
  struct _LIST_ENTRY *v35; // rdx
  struct _LIST_ENTRY *v36; // rax
  ULONG LastError; // eax
  ULONG v38; // ebp
  SIZE_T Size; // [rsp+30h] [rbp-58h] BYREF
  PSID pSourceSid; // [rsp+38h] [rbp-50h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF

  v7 = 0;
  v9 = a3;
  pSourceSid = 0;
  v11 = 0;
  if ( !a4 || !a5 && !a6 )
    goto LABEL_30;
  if ( !UbpmUtilsSidSupportsHardening(a4) || !String2 )
  {
    v7 = 87;
    goto LABEL_30;
  }
  v12 = 0;
  LengthSid = GetLengthSid(a4);
  v14 = -1;
  while ( String2[++v14] != 0 )
    ;
  if ( a6 == 1 )
  {
    LODWORD(Size) = 0;
    DestinationString = 0;
    if ( v9 - 80 > 0x1F )
    {
      v7 = 87;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, String2);
      if ( (unsigned int)RtlCreateVirtualAccountSid(&DestinationString, v9, 0, &Size) == -1073741789 )
      {
        v31 = UbpmAlloc((unsigned int)Size);
        v32 = v31;
        if ( v31 )
        {
          v33 = RtlCreateVirtualAccountSid(&DestinationString, v9, v31, &Size);
          if ( v33 >= 0 )
          {
            v12 = Size;
            pSourceSid = v32;
            UBPM_MIDL_user_free(0);
            goto LABEL_9;
          }
          LastError = RtlNtStatusToDosError(v33);
        }
        else
        {
          LastError = GetLastError();
        }
        v38 = LastError;
        UBPM_MIDL_user_free(v32);
        if ( !v38 )
        {
          v9 = a3;
          goto LABEL_9;
        }
        v7 = v38;
LABEL_58:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
            (_DWORD)String2,
            v38);
        goto LABEL_30;
      }
      v7 = 13;
    }
    LOBYTE(v38) = v7;
    UBPM_MIDL_user_free(0);
    goto LABEL_58;
  }
LABEL_9:
  v16 = 2 * v14 + 2;
  v17 = (struct _LIST_ENTRY *)UbpmAlloc(v12 + v16 + (_DWORD)LengthSid + 64);
  v11 = v17;
  if ( v17 )
  {
    HIDWORD(v17[3].Blink) = v9;
    v17[1].Blink = v17 + 4;
    v17[1].Flink = (struct _LIST_ENTRY *)((char *)v17 + LengthSid + v12 + 64);
    if ( CopySid(LengthSid, &v17[4], a4) )
    {
      if ( a6 == 1 )
      {
        v34 = pSourceSid;
        v35 = (struct _LIST_ENTRY *)((char *)v11[1].Blink + LengthSid);
        v11[3].Flink = v35;
        if ( !CopySid(v12, v35, v34) )
        {
          v7 = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
              (_DWORD)String2,
              v7);
          goto LABEL_30;
        }
      }
      v18 = 0;
      v19 = (unsigned __int64)v16 >> 1;
      if ( v19 )
      {
        Flink = v11[1].Flink;
        v21 = 2147483646;
        v22 = String2;
        do
        {
          if ( !v21 )
            break;
          if ( !*v22 )
            break;
          LOWORD(Flink->Flink) = *v22++;
          Flink = (struct _LIST_ENTRY *)((char *)Flink + 2);
          --v21;
          --v19;
        }
        while ( v19 );
        v23 = (struct _LIST_ENTRY *)((char *)Flink - 2);
        if ( v19 )
          v23 = Flink;
        LOWORD(v23->Flink) = 0;
      }
      v11->Blink = v11;
      v11->Flink = v11;
      v11[2].Flink = a5;
      LOBYTE(v11[2].Blink) = a6;
      LODWORD(v11[3].Blink) = -1;
      RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
      CurrentThreadId = GetCurrentThreadId();
      v25 = g_leTaskHostHardeningListHead.Flink;
      v26 = &g_leTaskHostHardeningListHead;
      dword_18004CF18 = CurrentThreadId;
      for ( i = 0; i < 2u; ++i )
      {
        while ( v25 != v26 )
        {
          if ( !_wcsicmp((const wchar_t *)v25[1].Flink, String2) )
          {
            dword_18004CF18 = 0;
            RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
            v7 = 183;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                62,
                (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                (_DWORD)String2,
                183);
            goto LABEL_30;
          }
          v25 = v25->Flink;
          if ( a3 == HIDWORD(v11[3].Blink) )
            v18 = 1;
        }
        v25 = g_leNonHostHardeningListHead.Flink;
        v26 = &g_leNonHostHardeningListHead;
      }
      if ( a7 )
      {
        v36 = off_18004C140[0];
        if ( off_18004C140[0]->Flink == &g_leTaskHostHardeningListHead )
        {
          v11->Flink = &g_leTaskHostHardeningListHead;
          v11->Blink = v36;
          v36->Flink = v11;
          off_18004C140[0] = v11;
          goto LABEL_25;
        }
      }
      else
      {
        v28 = off_18004C160[0];
        if ( off_18004C160[0]->Flink == &g_leNonHostHardeningListHead )
        {
          v11->Flink = &g_leNonHostHardeningListHead;
          v11->Blink = v28;
          v28->Flink = v11;
          off_18004C160[0] = v11;
LABEL_25:
          dword_18004CF18 = 0;
          RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
          if ( a6 )
          {
            if ( !v18 )
              UbpmUpdateConsumerSidCache(a2);
            UbpmUpdateConsumerSidCache(a2);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_Sid(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, v29, (_DWORD)String2, (char)a5, a6);
          v7 = 0;
          v11 = 0;
          goto LABEL_30;
        }
      }
      __fastfail(3u);
    }
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
        (_DWORD)String2,
        v7);
  }
  else
  {
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
        (_DWORD)String2,
        v7);
  }
LABEL_30:
  UBPM_MIDL_user_free(v11);
  UBPM_MIDL_user_free(pSourceSid);
  return v7;
}

```

## disassembly

```asm
0x180018ef0  mov     [rsp+arg_0], rbx
0x180018ef5  mov     [rsp+arg_10], r8d
0x180018efa  mov     [rsp+SourceString], rdx
0x180018eff  push    rbp
0x180018f00  push    rsi
0x180018f01  push    rdi
0x180018f02  push    r12
0x180018f04  push    r13
0x180018f06  push    r14
0x180018f08  push    r15
0x180018f0a  sub     rsp, 50h
0x180018f0e  xor     ebx, ebx
0x180018f10  mov     rdi, r9
0x180018f13  mov     [rsp+88h+arg_18], ebx
0x180018f1a  mov     ebp, r8d
0x180018f1d  mov     [rsp+88h+pSourceSid], rbx
0x180018f22  mov     r12, rcx
0x180018f25  mov     r13d, ebx
0x180018f28  test    r9, r9
0x180018f2b  jz      loc_18001914D
0x180018f31  movzx   esi, [rsp+88h+arg_28]
0x180018f39  cmp     [rsp+88h+arg_20], rbx
0x180018f41  jnz     short loc_180018F4C
0x180018f43  test    sil, sil
0x180018f46  jz      loc_18001914D
0x180018f4c  mov     rcx, rdi; pSid1
0x180018f4f  call    ?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z; UbpmUtilsSidSupportsHardening(void *)
0x180018f54  test    al, al
0x180018f56  jz      loc_1800193D3
0x180018f5c  test    r12, r12
0x180018f5f  jz      loc_1800193D3
0x180018f65  mov     rcx, rdi; pSid
0x180018f68  mov     r14d, ebx
0x180018f6b  call    cs:__imp_GetLengthSid
0x180018f71  mov     r15d, eax
0x180018f74  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180018f7b  nop     dword ptr [rax+rax+00h]
0x180018f80  cmp     [r12+rbx*2+2], r13w
0x180018f86  lea     rbx, [rbx+1]
0x180018f8a  jnz     short loc_180018F80
0x180018f8c  cmp     sil, 1
0x180018f90  jz      loc_18001914F
0x180018f96  lea     ecx, [r15+40h]
0x180018f9a  lea     ebx, ds:2[rbx*2]
0x180018fa1  add     ecx, ebx
0x180018fa3  add     ecx, r14d; Size
0x180018fa6  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180018fab  mov     r13, rax
0x180018fae  test    rax, rax
0x180018fb1  jz      loc_1800192E2
0x180018fb7  lea     rdx, [rax+40h]; pDestinationSid
0x180018fbb  mov     [r13+3Ch], ebp
0x180018fbf  mov     [rax+18h], rdx
0x180018fc3  mov     r8, rdi; pSourceSid
0x180018fc6  mov     eax, r14d
0x180018fc9  mov     ecx, r15d; nDestinationSidLength
0x180018fcc  add     rax, 40h ; '@'
0x180018fd0  mov     rsi, r15
0x180018fd3  add     rax, r15
0x180018fd6  add     rax, r13
0x180018fd9  mov     [r13+10h], rax
0x180018fdd  call    cs:__imp_CopySid
0x180018fe3  test    eax, eax
0x180018fe5  jz      loc_180019404
0x180018feb  movzx   r15d, [rsp+88h+arg_28]
0x180018ff4  cmp     r15b, 1
0x180018ff8  jz      loc_180019219
0x180018ffe  xor     bpl, bpl
0x180019001  mov     r8d, ebx
0x180019004  shr     r8, 1
0x180019007  jz      short loc_180019047
0x180019009  mov     r9, [r13+10h]
0x18001900d  mov     ecx, 7FFFFFFEh
0x180019012  mov     rdx, r12
0x180019015  test    rcx, rcx
0x180019018  jz      short loc_180019037
0x18001901a  movzx   eax, word ptr [rdx]
0x18001901d  test    ax, ax
0x180019020  jz      short loc_180019037
0x180019022  mov     [r9], ax
0x180019026  add     rdx, 2
0x18001902a  add     r9, 2
0x18001902e  dec     rcx
0x180019031  sub     r8, 1
0x180019035  jnz     short loc_180019015
0x180019037  test    r8, r8
0x18001903a  lea     rcx, [r9-2]
0x18001903e  cmovnz  rcx, r9
0x180019042  xor     eax, eax
0x180019044  mov     [rcx], ax
0x180019047  mov     rax, [rsp+88h+arg_20]
0x18001904f  lea     rcx, g_TaskHostContextListLock
0x180019056  mov     [r13+8], r13
0x18001905a  mov     [r13+0], r13
0x18001905e  mov     [r13+20h], rax
0x180019062  mov     [r13+28h], r15b
0x180019066  mov     dword ptr [r13+38h], 0FFFFFFFFh
0x18001906e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180019074  call    cs:__imp_GetCurrentThreadId
0x18001907a  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180019081  lea     rdi, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180019088  mov     r14d, [rsp+88h+arg_10]
0x180019090  lea     rcx, ?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x180019097  mov     cs:dword_18004CF18, eax
0x18001909d  xor     sil, sil
0x1800190a0  cmp     sil, 2
0x1800190a4  jb      loc_1800191E6
0x1800190aa  cmp     [rsp+88h+arg_30], 0
0x1800190b2  jnz     loc_1800192B4
0x1800190b8  mov     rax, cs:off_18004C160
0x1800190bf  cmp     [rax], rcx
0x1800190c2  jnz     loc_18001936E
0x1800190c8  mov     [r13+0], rcx
0x1800190cc  mov     [r13+8], rax
0x1800190d0  mov     [rax], r13
0x1800190d3  mov     cs:off_18004C160, r13
0x1800190da  lea     rcx, g_TaskHostContextListLock
0x1800190e1  mov     cs:dword_18004CF18, 0
0x1800190eb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800190f1  test    r15b, r15b
0x1800190f4  jnz     loc_18001928A
0x1800190fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180019101  lea     rax, WPP_GLOBAL_Control
0x180019108  cmp     rcx, rax
0x18001910b  jz      short loc_180019117
0x18001910d  test    byte ptr [rcx+1Ch], 80h
0x180019111  jnz     loc_180019450
0x180019117  mov     ebx, [rsp+88h+arg_18]
0x18001911e  xor     r13d, r13d
0x180019121  mov     rcx, r13
0x180019124  call    UBPM_MIDL_user_free
0x180019129  mov     rcx, [rsp+88h+pSourceSid]
0x18001912e  call    UBPM_MIDL_user_free
0x180019133  mov     eax, ebx
0x180019135  mov     rbx, [rsp+88h+arg_0]
0x18001913d  add     rsp, 50h
0x180019141  pop     r15
0x180019143  pop     r14
0x180019145  pop     r13
0x180019147  pop     r12
0x180019149  pop     rdi
0x18001914a  pop     rsi
0x18001914b  pop     rbp
0x18001914c  retn
0x18001914d  jmp     short loc_180019121
0x18001914f  lea     eax, [rbp-50h]
0x180019152  mov     dword ptr [rsp+88h+Size], r13d
0x180019157  xorps   xmm0, xmm0
0x18001915a  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x18001915f  cmp     eax, 1Fh
0x180019162  ja      loc_1800193F1
0x180019168  mov     rdx, r12; SourceString
0x18001916b  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180019170  call    cs:__imp_RtlInitUnicodeString
0x180019176  lea     r9, [rsp+88h+Size]
0x18001917b  xor     r8d, r8d
0x18001917e  mov     edx, ebp
0x180019180  lea     rcx, [rsp+88h+DestinationString]
0x180019185  call    cs:__imp_RtlCreateVirtualAccountSid
0x18001918b  cmp     eax, 0C0000023h
0x180019190  jnz     loc_1800193DD
0x180019196  mov     ecx, dword ptr [rsp+88h+Size]; Size
0x18001919a  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001919f  mov     rsi, rax
0x1800191a2  test    rax, rax
0x1800191a5  jz      loc_180019319
0x1800191ab  lea     r9, [rsp+88h+Size]
0x1800191b0  mov     r8, rax
0x1800191b3  mov     edx, ebp
0x1800191b5  lea     rcx, [rsp+88h+DestinationString]
0x1800191ba  call    cs:__imp_RtlCreateVirtualAccountSid
0x1800191c0  test    eax, eax
0x1800191c2  js      loc_1800193E4
0x1800191c8  mov     r14d, dword ptr [rsp+88h+Size]
0x1800191cd  xor     ecx, ecx
0x1800191cf  mov     [rsp+88h+pSourceSid], rsi
0x1800191d4  call    UBPM_MIDL_user_free
0x1800191d9  mov     [rsp+88h+arg_18], r13d
0x1800191e1  jmp     loc_180018F96
0x1800191e6  cmp     rbx, rdi
0x1800191e9  jz      loc_180019271
0x1800191ef  mov     rcx, [rbx+10h]; String1
0x1800191f3  mov     rdx, r12; String2
0x1800191f6  call    cs:__imp__wcsicmp
0x1800191fc  test    eax, eax
0x1800191fe  jz      loc_180019375
0x180019204  cmp     r14d, [r13+3Ch]
0x180019208  mov     eax, 1
0x18001920d  mov     rbx, [rbx]
0x180019210  movzx   ebp, bpl
0x180019214  cmovz   ebp, eax
0x180019217  jmp     short loc_1800191E6
0x180019219  mov     rdx, [r13+18h]
0x18001921d  mov     ecx, r14d; nDestinationSidLength
0x180019220  mov     r8, [rsp+88h+pSourceSid]; pSourceSid
0x180019225  add     rdx, rsi; pDestinationSid
0x180019228  mov     [r13+30h], rdx
0x18001922c  call    cs:__imp_CopySid
0x180019232  test    eax, eax
0x180019234  jnz     loc_180018FFE
0x18001923a  call    cs:__imp_GetLastError
0x180019240  mov     ebx, eax
0x180019242  mov     rcx, cs:WPP_GLOBAL_Control
0x180019249  lea     rax, WPP_GLOBAL_Control
0x180019250  cmp     rcx, rax
0x180019253  jz      loc_180019121
0x180019259  test    byte ptr [rcx+1Ch], 1
0x18001925d  jz      loc_180019121
0x180019263  mov     edx, 3Dh ; '='
0x180019268  mov     dword ptr [rsp+88h+var_68], ebx
0x18001926c  jmp     loc_1800193BB
0x180019271  mov     rbx, cs:?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x180019278  lea     rcx, ?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x18001927f  mov     rdi, rcx
0x180019282  inc     sil
0x180019285  jmp     loc_1800190A0
0x18001928a  mov     rbx, [rsp+88h+SourceString]
0x180019292  test    bpl, bpl
0x180019295  jz      loc_180019438
0x18001929b  mov     r9d, 1
0x1800192a1  mov     r8d, r14d
0x1800192a4  mov     rdx, r12
0x1800192a7  mov     rcx, rbx; SourceString
0x1800192aa  call    UbpmUpdateConsumerSidCache
0x1800192af  jmp     loc_1800190FA
0x1800192b4  mov     rax, cs:off_18004C140
0x1800192bb  lea     rcx, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x1800192c2  cmp     [rax], rcx
0x1800192c5  jnz     loc_18001936E
0x1800192cb  mov     [r13+0], rcx
0x1800192cf  mov     [r13+8], rax
0x1800192d3  mov     [rax], r13
0x1800192d6  mov     cs:off_18004C140, r13
0x1800192dd  jmp     loc_1800190DA
0x1800192e2  call    cs:__imp_GetLastError
0x1800192e8  mov     ebx, eax
0x1800192ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192f1  lea     rax, WPP_GLOBAL_Control
0x1800192f8  cmp     rcx, rax
0x1800192fb  jz      loc_180019121
0x180019301  test    byte ptr [rcx+1Ch], 1
0x180019305  jz      loc_180019121
0x18001930b  mov     edx, 3Bh ; ';'
0x180019310  mov     dword ptr [rsp+88h+var_68], ebx
0x180019314  jmp     loc_1800193BB
0x180019319  call    cs:__imp_GetLastError
0x18001931f  mov     ebp, eax
0x180019321  mov     rcx, rsi
0x180019324  call    UBPM_MIDL_user_free
0x180019329  mov     [rsp+88h+arg_18], ebp
0x180019330  test    ebp, ebp
0x180019332  jz      short loc_180019362
0x180019334  mov     ebx, ebp
0x180019336  mov     rcx, cs:WPP_GLOBAL_Control
0x18001933d  lea     rax, WPP_GLOBAL_Control
0x180019344  cmp     rcx, rax
0x180019347  jz      loc_180019121
0x18001934d  test    byte ptr [rcx+1Ch], 1
0x180019351  jz      loc_180019121
0x180019357  mov     edx, 3Ah ; ':'
0x18001935c  mov     dword ptr [rsp+88h+var_68], ebp
0x180019360  jmp     short loc_1800193BB
0x180019362  mov     ebp, [rsp+88h+arg_10]
0x180019369  jmp     loc_180018F96
0x18001936e  mov     ecx, 3
0x180019373  int     29h; Win8: RtlFailFast(ecx)
0x180019375  lea     rcx, g_TaskHostContextListLock
0x18001937c  mov     cs:dword_18004CF18, 0
0x180019386  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001938c  mov     ebx, 0B7h
0x180019391  mov     rcx, cs:WPP_GLOBAL_Control
0x180019398  lea     rax, WPP_GLOBAL_Control
0x18001939f  cmp     rcx, rax
0x1800193a2  jz      loc_180019121
0x1800193a8  test    byte ptr [rcx+1Ch], 1
0x1800193ac  jz      loc_180019121
0x1800193b2  mov     edx, 3Eh ; '>'
0x1800193b7  mov     dword ptr [rsp+88h+var_68], ebx
0x1800193bb  mov     rcx, [rcx+10h]
0x1800193bf  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800193c6  mov     r9, r12
0x1800193c9  call    WPP_SF_Sd
0x1800193ce  jmp     loc_180019121
0x1800193d3  mov     ebx, 57h ; 'W'
0x1800193d8  jmp     loc_180019121
0x1800193dd  mov     ebx, 0Dh
0x1800193e2  jmp     short loc_1800193F6
0x1800193e4  mov     ecx, eax; Status
0x1800193e6  call    cs:__imp_RtlNtStatusToDosError
0x1800193ec  jmp     loc_18001931F
0x1800193f1  mov     ebx, 57h ; 'W'
0x1800193f6  xor     ecx, ecx
0x1800193f8  mov     ebp, ebx
0x1800193fa  call    UBPM_MIDL_user_free
0x1800193ff  jmp     loc_180019336
0x180019404  call    cs:__imp_GetLastError
0x18001940a  mov     ebx, eax
0x18001940c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019413  lea     rax, WPP_GLOBAL_Control
0x18001941a  cmp     rcx, rax
  ... truncated ...
```
