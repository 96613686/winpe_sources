# UbpmpRunConsumerAction(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)

- ea: `0x18001a8a8`
- end: `0x18001acaa`
- name: `?UbpmpRunConsumerAction@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z`
- size: `1026`
- prototype: `__int64 __fastcall(struct _UBPM_INPUT_ACTION_PARAMS *, struct _UBPM_CONSTRAINT_PRECHECK_INFO *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019fb0`

## callees

- `0x180001e14`
- `0x180006650`
- `0x1800096e0`
- `0x1800189f4`
- `0x180019d90`
- `0x18001a8a8`
- `0x18001b190`
- `0x18001e9f4`
- `0x180035000`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001aad7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001aad7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a98e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a98e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa24`

## pseudocode

```c
__int64 __fastcall UbpmpRunConsumerAction(
        struct _UBPM_INPUT_ACTION_PARAMS *a1,
        struct _UBPM_CONSTRAINT_PRECHECK_INFO *a2,
        unsigned __int8 *a3)
{
  unsigned int v3; // edi
  struct _UBPM_INPUT_ACTION_PARAMS *v4; // r13
  __int64 v5; // rax
  const unsigned __int16 *ConsumerFriendlyName; // rbx
  void *v7; // rcx
  unsigned int InteractiveUserSidAndToken; // ebx
  unsigned int v9; // eax
  char *v10; // rcx
  unsigned int i; // edi
  __int64 v12; // rsi
  PSID v13; // rdi
  void *v15; // rcx
  const unsigned __int16 **v16; // rdx
  unsigned __int8 v17; // r8
  unsigned int v18; // r10d
  unsigned __int8 *v19; // r11
  unsigned int v20; // ebx
  char v21; // si
  unsigned __int64 v22; // r14
  unsigned int v23; // r15d
  unsigned __int64 v24; // r12
  unsigned int v25; // [rsp+48h] [rbp-89h]
  unsigned __int16 **v26; // [rsp+70h] [rbp-61h]
  unsigned int v27; // [rsp+B8h] [rbp-19h]
  PSID pSid; // [rsp+C0h] [rbp-11h]
  char *v29; // [rsp+C8h] [rbp-9h] BYREF
  HANDLE hObject; // [rsp+D0h] [rbp-1h] BYREF
  HLOCAL hMem[10]; // [rsp+D8h] [rbp+7h] BYREF
  __int64 v35; // [rsp+150h] [rbp+7Fh] BYREF

  v3 = *((_DWORD *)a1 + 9);
  hObject = 0;
  v4 = a1;
  hMem[0] = 0;
  pSid = 0;
  v29 = 0;
  v5 = *(_QWORD *)a1;
  v27 = v3;
  LODWORD(v35) = v3;
  ConsumerFriendlyName = UbpmpGetConsumerFriendlyName(*(PCNZWCH *)(*(_QWORD *)(v5 + 24) + 8LL));
  if ( (*((_BYTE *)v4 + 56) & 2) != 0 )
  {
    v7 = (void *)*((_QWORD *)v4 + 5);
    v29 = 0;
    LODWORD(v35) = 0;
    InteractiveUserSidAndToken = UbpmGetInteractiveUserSidAndToken(v7, 0, (__int64)&v35);
    if ( !InteractiveUserSidAndToken )
    {
      if ( (_DWORD)v35 )
      {
        hObject = (HANDLE)*((_QWORD *)v29 + 1);
        pSid = *(PSID *)v29;
        v9 = *((_DWORD *)v29 + 4);
        *((_QWORD *)v29 + 1) = 0;
        v27 = v9;
        *(_QWORD *)v29 = 0;
      }
      else
      {
        InteractiveUserSidAndToken = 1168;
      }
    }
    v10 = v29;
    if ( v29 )
    {
      for ( i = 0; i < (unsigned int)v35; ++i )
      {
        v12 = 32LL * i;
        if ( *(_QWORD *)&v10[v12 + 8] )
        {
          CloseHandle(*(HANDLE *)&v10[v12 + 8]);
          v10 = v29;
        }
        UBPM_MIDL_user_free(*(_QWORD *)&v10[v12]);
        v10 = v29;
      }
      UBPM_MIDL_user_free(v10);
    }
    if ( InteractiveUserSidAndToken )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v4 + 24LL) + 8LL),
          *((_DWORD *)v4 + 9),
          InteractiveUserSidAndToken);
LABEL_16:
      v13 = pSid;
      goto LABEL_17;
    }
    goto LABEL_37;
  }
  if ( (*((_BYTE *)v4 + 56) & 4) == 0 )
  {
LABEL_37:
    v16 = (const unsigned __int16 **)*((_QWORD *)v4 + 14);
    v17 = *((_BYTE *)v4 + 108);
    v18 = *((_DWORD *)v4 + 26);
    v19 = (unsigned __int8 *)*((_QWORD *)v4 + 3);
    v20 = *((_DWORD *)v4 + 8);
    v21 = *((_BYTE *)v4 + 88);
    v22 = *((_QWORD *)v4 + 10);
    v23 = *((_DWORD *)v4 + 18);
    v24 = *((_QWORD *)v4 + 8);
    v26 = (unsigned __int16 **)*((_QWORD *)v4 + 12);
    v13 = pSid;
    v25 = *((_DWORD *)v4 + 14);
    v4 = a1;
    InteractiveUserSidAndToken = UbpmpLaunchOneTask(
                                   *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)a1,
                                   a2,
                                   *((struct _UBPM_ACTION_PARAMS **)a1 + 1),
                                   v27,
                                   pSid,
                                   (void **)((unsigned __int64)&hObject & -(__int64)(hObject != 0)),
                                   hMem[0],
                                   *((struct _GUID **)a1 + 6),
                                   v25,
                                   v24,
                                   v23,
                                   v22,
                                   v21,
                                   (const unsigned __int16 **)v26,
                                   v20,
                                   v19,
                                   v18,
                                   0,
                                   v17,
                                   v16,
                                   a3);
    if ( InteractiveUserSidAndToken
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
        *((_DWORD *)a1 + 9),
        InteractiveUserSidAndToken);
    }
    goto LABEL_17;
  }
  v15 = (void *)*((_QWORD *)v4 + 5);
  if ( (*((_BYTE *)v4 + 56) & 8) != 0 )
  {
    if ( !EqualSid(v15, ::pSid) )
    {
      InteractiveUserSidAndToken = UbpmTokenGetTokenForTask(
                                     *(_QWORD *)(*((_QWORD *)v4 + 1) + 24LL),
                                     *((_QWORD *)v4 + 5),
                                     *((_DWORD *)v4 + 9),
                                     0,
                                     (__int64)ConsumerFriendlyName,
                                     (__int64)&hObject,
                                     hMem,
                                     (__int64)&v35);
      if ( InteractiveUserSidAndToken )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v4 + 24LL) + 8LL),
            InteractiveUserSidAndToken);
        goto LABEL_16;
      }
      v27 = v35;
    }
    goto LABEL_36;
  }
  InteractiveUserSidAndToken = UbpmTokenGetInteractiveToken(
                                 (_DWORD)v15,
                                 -1,
                                 (unsigned int)&hObject,
                                 (unsigned int)&v35,
                                 (__int64)&v29);
  if ( !InteractiveUserSidAndToken )
  {
    UBPM_MIDL_user_free(v29);
    v27 = v35;
LABEL_36:
    pSid = (PSID)*((_QWORD *)v4 + 5);
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v4 + 24LL) + 8LL),
      InteractiveUserSidAndToken);
  v13 = v29;
LABEL_17:
  if ( hObject )
    CloseHandle(hObject);
  if ( v13 != *((PSID *)v4 + 5) )
    UBPM_MIDL_user_free(v13);
  LocalFree(hMem[0]);
  return InteractiveUserSidAndToken;
}

```

## disassembly

```asm
0x18001a8a8  mov     rax, rsp
0x18001a8ab  mov     [rax+18h], r8
0x18001a8af  mov     [rax+10h], rdx
0x18001a8b3  mov     [rax+8], rcx
0x18001a8b7  push    rbp
0x18001a8b8  push    rbx
0x18001a8b9  push    rsi
0x18001a8ba  push    rdi
0x18001a8bb  push    r12
0x18001a8bd  push    r13
0x18001a8bf  push    r14
0x18001a8c1  push    r15
0x18001a8c3  lea     rbp, [rax-5Fh]
0x18001a8c7  sub     rsp, 0E8h
0x18001a8ce  mov     edi, [rcx+24h]
0x18001a8d1  xor     r14d, r14d
0x18001a8d4  mov     eax, r14d
0x18001a8d7  mov     [rbp+57h+hObject], r14
0x18001a8db  mov     r13, rcx
0x18001a8de  mov     [rbp+57h+hMem], r14
0x18001a8e2  mov     [rbp+57h+var_68], rax
0x18001a8e6  mov     [rbp+57h+var_60], rax
0x18001a8ea  mov     rax, [rcx]
0x18001a8ed  mov     [rbp+57h+var_70], edi
0x18001a8f0  mov     dword ptr [rbp+57h+arg_18], edi
0x18001a8f3  mov     rcx, [rax+18h]
0x18001a8f7  mov     rcx, [rcx+8]; lpString1
0x18001a8fb  call    ?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z; UbpmpGetConsumerFriendlyName(ushort const *)
0x18001a900  test    byte ptr [r13+38h], 2
0x18001a905  mov     rbx, rax
0x18001a908  jz      loc_18001AA40
0x18001a90e  mov     r8d, [r13+24h]
0x18001a912  lea     rax, [rbp+57h+arg_18]
0x18001a916  mov     rcx, [r13+28h]; pSid2
0x18001a91a  lea     r9, [rbp+57h+var_60]
0x18001a91e  xor     edx, edx; SidToCheck
0x18001a920  mov     [rsp+120h+pSid], rax; __int64
0x18001a925  mov     [rbp+57h+var_60], r14
0x18001a929  mov     dword ptr [rbp+57h+arg_18], r14d
0x18001a92d  call    UbpmGetInteractiveUserSidAndToken
0x18001a932  mov     ebx, eax
0x18001a934  test    eax, eax
0x18001a936  jnz     short loc_18001A969
0x18001a938  cmp     dword ptr [rbp+57h+arg_18], r14d
0x18001a93c  jnz     short loc_18001A945
0x18001a93e  mov     ebx, 490h
0x18001a943  jmp     short loc_18001A969
0x18001a945  mov     rcx, [rbp+57h+var_60]
0x18001a949  mov     rax, [rcx+8]
0x18001a94d  mov     [rbp+57h+hObject], rax
0x18001a951  mov     rax, [rcx]
0x18001a954  mov     [rbp+57h+var_68], rax
0x18001a958  mov     eax, [rcx+10h]
0x18001a95b  mov     [rcx+8], r14
0x18001a95f  mov     [rbp+57h+var_70], eax
0x18001a962  mov     rax, [rbp+57h+var_60]
0x18001a966  mov     [rax], r14
0x18001a969  mov     rcx, [rbp+57h+var_60]
0x18001a96d  test    rcx, rcx
0x18001a970  jz      short loc_18001A9B1
0x18001a972  mov     edi, r14d
0x18001a975  cmp     dword ptr [rbp+57h+arg_18], r14d
0x18001a979  jbe     short loc_18001A9AC
0x18001a97b  mov     esi, edi
0x18001a97d  shl     rsi, 5
0x18001a981  mov     rax, [rsi+rcx+8]
0x18001a986  test    rax, rax
0x18001a989  jz      short loc_18001A998
0x18001a98b  mov     rcx, rax; hObject
0x18001a98e  call    cs:__imp_CloseHandle
0x18001a994  mov     rcx, [rbp+57h+var_60]
0x18001a998  mov     rcx, [rsi+rcx]
0x18001a99c  call    UBPM_MIDL_user_free
0x18001a9a1  mov     rcx, [rbp+57h+var_60]
0x18001a9a5  inc     edi
0x18001a9a7  cmp     edi, dword ptr [rbp+57h+arg_18]
0x18001a9aa  jb      short loc_18001A97B
0x18001a9ac  call    UBPM_MIDL_user_free
0x18001a9b1  test    ebx, ebx
0x18001a9b3  jz      loc_18001AB7C
0x18001a9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9c0  lea     rax, WPP_GLOBAL_Control
0x18001a9c7  cmp     rcx, rax
0x18001a9ca  jz      short loc_18001A9FF
0x18001a9cc  test    byte ptr [rcx+1Ch], 1
0x18001a9d0  jz      short loc_18001A9FF
0x18001a9d2  mov     rax, [r13+0]
0x18001a9d6  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001a9dd  mov     rcx, [rcx+10h]
0x18001a9e1  mov     edx, 4Dh ; 'M'
0x18001a9e6  mov     dword ptr [rsp+120h+var_F8], ebx
0x18001a9ea  mov     r9, [rax+18h]
0x18001a9ee  mov     eax, [r13+24h]
0x18001a9f2  mov     dword ptr [rsp+120h+pSid], eax
0x18001a9f6  mov     r9, [r9+8]
0x18001a9fa  call    WPP_SF_Sdd
0x18001a9ff  mov     rdi, [rbp+57h+var_68]
0x18001aa03  mov     rcx, [rbp+57h+hObject]; hObject
0x18001aa07  test    rcx, rcx
0x18001aa0a  jz      short loc_18001AA12
0x18001aa0c  call    cs:__imp_CloseHandle
0x18001aa12  cmp     rdi, [r13+28h]
0x18001aa16  jz      short loc_18001AA20
0x18001aa18  mov     rcx, rdi
0x18001aa1b  call    UBPM_MIDL_user_free
0x18001aa20  mov     rcx, [rbp+57h+hMem]; hMem
0x18001aa24  call    cs:__imp_LocalFree
0x18001aa2a  mov     eax, ebx
0x18001aa2c  add     rsp, 0E8h
0x18001aa33  pop     r15
0x18001aa35  pop     r14
0x18001aa37  pop     r13
0x18001aa39  pop     r12
0x18001aa3b  pop     rdi
0x18001aa3c  pop     rsi
0x18001aa3d  pop     rbx
0x18001aa3e  pop     rbp
0x18001aa3f  retn
0x18001aa40  test    byte ptr [r13+38h], 4
0x18001aa45  jz      loc_18001AB7C
0x18001aa4b  test    byte ptr [r13+38h], 8
0x18001aa50  mov     rcx, [r13+28h]; pSid1
0x18001aa54  jnz     short loc_18001AAD0
0x18001aa56  lea     rax, [rbp+57h+var_60]
0x18001aa5a  or      edx, 0FFFFFFFFh
0x18001aa5d  lea     r9, [rbp+57h+arg_18]
0x18001aa61  mov     [rsp+120h+pSid], rax
0x18001aa66  lea     r8, [rbp+57h+hObject]
0x18001aa6a  call    UbpmTokenGetInteractiveToken
0x18001aa6f  mov     ebx, eax
0x18001aa71  test    eax, eax
0x18001aa73  jz      short loc_18001AABC
0x18001aa75  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa7c  lea     rax, WPP_GLOBAL_Control
0x18001aa83  cmp     rcx, rax
0x18001aa86  jz      short loc_18001AAB3
0x18001aa88  test    byte ptr [rcx+1Ch], 1
0x18001aa8c  jz      short loc_18001AAB3
0x18001aa8e  mov     rax, [r13+0]
0x18001aa92  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001aa99  mov     rcx, [rcx+10h]
0x18001aa9d  mov     edx, 4Eh ; 'N'
0x18001aaa2  mov     dword ptr [rsp+120h+pSid], ebx
0x18001aaa6  mov     r9, [rax+18h]
0x18001aaaa  mov     r9, [r9+8]
0x18001aaae  call    WPP_SF_Sd
0x18001aab3  mov     rdi, [rbp+57h+var_60]
0x18001aab7  jmp     loc_18001AA03
0x18001aabc  mov     rcx, [rbp+57h+var_60]
0x18001aac0  call    UBPM_MIDL_user_free
0x18001aac5  mov     ecx, dword ptr [rbp+57h+arg_18]
0x18001aac8  mov     [rbp+57h+var_70], ecx
0x18001aacb  jmp     loc_18001AB74
0x18001aad0  mov     rdx, cs:pSid; pSid2
0x18001aad7  call    cs:__imp_EqualSid
0x18001aadd  test    eax, eax
0x18001aadf  jnz     loc_18001AB74
0x18001aae5  mov     rcx, [r13+8]
0x18001aae9  lea     rax, [rbp+57h+arg_18]
0x18001aaed  mov     r8d, [r13+24h]
0x18001aaf1  xor     r9d, r9d
0x18001aaf4  mov     rdx, [r13+28h]
0x18001aaf8  mov     [rsp+120h+var_E8], rax
0x18001aafd  lea     rax, [rbp+57h+hMem]
0x18001ab01  mov     rcx, [rcx+18h]
0x18001ab05  mov     [rsp+120h+var_F0], rax
0x18001ab0a  lea     rax, [rbp+57h+hObject]
0x18001ab0e  mov     [rsp+120h+var_F8], rax
0x18001ab13  mov     [rsp+120h+pSid], rbx
0x18001ab18  call    UbpmTokenGetTokenForTask
0x18001ab1d  mov     ebx, eax
0x18001ab1f  test    eax, eax
0x18001ab21  jz      short loc_18001AB6E
0x18001ab23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab2a  lea     rax, WPP_GLOBAL_Control
0x18001ab31  cmp     rcx, rax
0x18001ab34  jz      loc_18001A9FF
0x18001ab3a  test    byte ptr [rcx+1Ch], 1
0x18001ab3e  jz      loc_18001A9FF
0x18001ab44  mov     rax, [r13+0]
0x18001ab48  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001ab4f  mov     rcx, [rcx+10h]
0x18001ab53  mov     edx, 4Fh ; 'O'
0x18001ab58  mov     dword ptr [rsp+120h+pSid], ebx
0x18001ab5c  mov     r9, [rax+18h]
0x18001ab60  mov     r9, [r9+8]
0x18001ab64  call    WPP_SF_Sd
0x18001ab69  jmp     loc_18001A9FF
0x18001ab6e  mov     eax, dword ptr [rbp+57h+arg_18]
0x18001ab71  mov     [rbp+57h+var_70], eax
0x18001ab74  mov     rax, [r13+28h]
0x18001ab78  mov     [rbp+57h+var_68], rax
0x18001ab7c  mov     rdx, [r13+70h]
0x18001ab80  mov     r8b, [r13+6Ch]
0x18001ab84  mov     rdi, [r13+60h]
0x18001ab88  mov     r10d, [r13+68h]
0x18001ab8c  mov     r11, [r13+18h]
0x18001ab90  mov     ebx, [r13+20h]
0x18001ab94  mov     sil, [r13+58h]
0x18001ab98  mov     r14, [r13+50h]
0x18001ab9c  mov     r15d, [r13+48h]
0x18001aba0  mov     r12, [r13+40h]
0x18001aba4  mov     r13d, [r13+38h]
0x18001aba8  mov     rax, [rbp+57h+hObject]
0x18001abac  mov     r9, [rbp+57h+arg_0]
0x18001abb0  neg     rax
0x18001abb3  lea     rax, [rbp+57h+hObject]
0x18001abb7  sbb     rcx, rcx
0x18001abba  and     rcx, rax
0x18001abbd  mov     rax, [rbp+57h+arg_10]
0x18001abc1  mov     r9, [r9+30h]
0x18001abc5  mov     [rsp+0A0h], rax; unsigned __int8 *
0x18001abcd  mov     rax, [rbp+57h+hMem]
0x18001abd1  mov     [rsp+120h+var_88], rdx; unsigned __int16 **
0x18001abd9  mov     rdx, [rbp+57h+arg_8]; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18001abdd  mov     [rsp+120h+var_90], r8b; unsigned __int8
0x18001abe5  mov     [rsp+120h+var_98], 0; void *
0x18001abf1  mov     [rsp+120h+var_A0], r10d; unsigned int
0x18001abf9  mov     [rsp+120h+var_A8], r11; unsigned __int8 *
0x18001abfe  mov     [rsp+120h+var_B0], ebx; unsigned int
0x18001ac02  mov     [rsp+120h+var_B8], rdi; unsigned __int16 **
0x18001ac07  mov     rdi, [rbp+57h+var_68]
0x18001ac0b  mov     [rsp+120h+var_C0], sil; char
0x18001ac10  mov     [rsp+120h+var_C8], r14; unsigned __int64
0x18001ac15  mov     [rsp+120h+var_D0], r15d; unsigned int
0x18001ac1a  mov     [rsp+120h+var_D8], r12; unsigned __int64
0x18001ac1f  mov     [rsp+120h+var_E0], r13d; unsigned int
0x18001ac24  mov     r13, [rbp+57h+arg_0]
0x18001ac28  mov     [rsp+120h+var_E8], r9; struct _GUID *
0x18001ac2d  mov     r9d, [rbp+57h+var_70]; unsigned int
0x18001ac31  mov     [rsp+120h+var_F0], rax; void *
0x18001ac36  mov     r8, [r13+8]; struct _UBPM_ACTION_PARAMS *
0x18001ac3a  mov     [rsp+120h+var_F8], rcx; void **
0x18001ac3f  mov     rcx, [r13+0]; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18001ac43  mov     [rsp+120h+pSid], rdi; pSid
0x18001ac48  call    ?UbpmpLaunchOneTask@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAU_UBPM_ACTION_PARAMS@@KPEAXPEAPEAX3PEAU_GUID@@K_KK6EPEAPEBGKPEAEK3E78@Z; UbpmpLaunchOneTask(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_ACTION_PARAMS *,ulong,void *,void * *,void *,_GUID *,ulong,unsigned __int64,ulong,unsigned __int64,uchar,ushort const * *,ulong,uchar *,ulong,void *,uchar,ushort const * *,uchar *)
0x18001ac4d  mov     ebx, eax
0x18001ac4f  test    eax, eax
0x18001ac51  jz      loc_18001AA03
0x18001ac57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac5e  lea     rax, WPP_GLOBAL_Control
0x18001ac65  cmp     rcx, rax
0x18001ac68  jz      loc_18001AA03
0x18001ac6e  test    byte ptr [rcx+1Ch], 1
0x18001ac72  jz      loc_18001AA03
0x18001ac78  mov     rax, [r13+0]
0x18001ac7c  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18001ac83  mov     rcx, [rcx+10h]
0x18001ac87  mov     edx, 50h ; 'P'
0x18001ac8c  mov     dword ptr [rsp+120h+var_F8], ebx
0x18001ac90  mov     r9, [rax+18h]
0x18001ac94  mov     eax, [r13+24h]
0x18001ac98  mov     dword ptr [rsp+120h+pSid], eax
0x18001ac9c  mov     r9, [r9+8]
0x18001aca0  call    WPP_SF_Sdd
0x18001aca5  jmp     loc_18001AA03
```
