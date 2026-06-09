# UbpmpGetConsumerSids

- ea: `0x180027a2c`
- end: `0x180027ce8`
- name: `UbpmpGetConsumerSids`
- size: `700`
- prototype: `__int64 __usercall@<rax>(PSID pSid1@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019480`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x180027a2c`
- `0x18003c650`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027b3c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027c45`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027b3c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180027c45`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180027b4e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180027b4e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180027aad`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180027bd1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180027bfc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180027aad`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180027bd1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180027bfc`
- `ntdll!RtlReleaseSRWLockShared` at `0x180027b06`
- `ntdll!RtlReleaseSRWLockShared` at `0x180027c67`
- `ntdll!RtlReleaseSRWLockShared` at `0x180027caa`
- `ntdll!RtlReleaseSRWLockShared` at `0x180027b06`
- `ntdll!RtlReleaseSRWLockShared` at `0x180027c67`
- `ntdll!RtlReleaseSRWLockShared` at `0x180027caa`
- `ntdll!RtlAcquireSRWLockShared` at `0x180027a72`
- `ntdll!RtlAcquireSRWLockShared` at `0x180027ae9`
- `ntdll!RtlAcquireSRWLockShared` at `0x180027a72`
- `ntdll!RtlAcquireSRWLockShared` at `0x180027ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c58`

## pseudocode

```c
__int64 __fastcall UbpmpGetConsumerSids(PSID pSid1, int a2, _DWORD *a3, _QWORD *a4, _QWORD *a5)
{
  PSID v5; // rbx
  int v6; // r14d
  int v7; // ebp
  __int64 v8; // r15
  char *v9; // rsi
  unsigned int i; // r12d
  struct _LIST_ENTRY *j; // rdi
  _QWORD *v12; // rbx
  char v13; // r13
  DWORD LengthSid; // eax
  void *v15; // rdx
  __int64 v16; // rbp
  char *v17; // r14
  void *v18; // rcx
  __int64 k; // rbp
  char *v20; // rax
  DWORD LastError; // ebx
  int v23; // [rsp+30h] [rbp-58h]
  int v24; // [rsp+34h] [rbp-54h]
  char *v25; // [rsp+38h] [rbp-50h]

  v5 = pSid1;
  v6 = 0;
  v25 = 0;
  v7 = 0;
  v23 = 0;
  v24 = 0;
  v8 = 0;
  v9 = 0;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
      *a4 = v9;
      v9 = 0;
      LastError = 0;
      *a3 = v8;
      goto LABEL_36;
    }
    if ( i == 1 )
      break;
LABEL_4:
    for ( j = g_leTaskHostHardeningListHead.Flink; j != &g_leTaskHostHardeningListHead; j = j->Flink )
    {
      if ( EqualSid(v5, j[1].Blink) && j[3].Flink )
      {
        v12 = g_leTaskHostContextListHead;
        v13 = 0;
        if ( g_leTaskHostContextListHead != (_UNKNOWN *)&g_leTaskHostContextListHead )
        {
          while ( 1 )
          {
            if ( (v12[12] & 0x54) == 0x10 )
            {
              RtlAcquireSRWLockShared(v12 + 7);
              if ( *((unsigned __int8 *)v12 + 424) == a2
                && *((char *)v12 + 96) >= 0
                && (v18 = (void *)v12[22]) != 0
                && EqualSid(v18, pSid1) )
              {
                for ( k = 0; (unsigned int)k < *((_DWORD *)v12 + 96); k = (unsigned int)(k + 1) )
                {
                  if ( EqualSid(*(PSID *)(v12[49] + 8 * k), j[3].Flink) )
                  {
                    v13 = 1;
                    break;
                  }
                }
                RtlReleaseSRWLockShared(v12 + 7);
                if ( v13 )
                {
                  v7 = v24;
                  goto LABEL_21;
                }
              }
              else
              {
                RtlReleaseSRWLockShared(v12 + 7);
              }
            }
            v12 = (_QWORD *)*v12;
            if ( v12 == &g_leTaskHostContextListHead )
            {
              v6 = v23;
              v7 = v24;
              break;
            }
          }
        }
        if ( i )
        {
          *(_QWORD *)&v9[8 * v7] = v25;
          LengthSid = GetLengthSid(j[3].Flink);
          v15 = *(void **)&v9[8 * v7];
          v16 = LengthSid;
          if ( !CopySid(LengthSid, v15, j[3].Flink) )
            goto LABEL_35;
          *a5 |= (unsigned __int64)j[2].Flink;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_Si(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, *a5, j[1].Flink, *a5);
          v17 = &v25[v16];
          v7 = v24 + 1;
          v25 = v17;
          ++v24;
LABEL_21:
          v6 = v23;
        }
        else
        {
          v8 = (unsigned int)(v8 + 1);
          v6 += GetLengthSid(j[3].Flink);
          v23 = v6;
        }
        v5 = pSid1;
      }
    }
  }
  if ( (_DWORD)v8 )
  {
    v20 = (char *)UbpmAlloc((unsigned int)(v6 + 8 * v8));
    v9 = v20;
    if ( !v20 )
    {
LABEL_35:
      LastError = GetLastError();
      goto LABEL_36;
    }
    v25 = &v20[8 * v8];
    goto LABEL_4;
  }
  LastError = 13;
LABEL_36:
  RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  UBPM_MIDL_user_free(v9);
  return LastError;
}

```

## disassembly

```asm
0x180027a2c  mov     rax, rsp
0x180027a2f  mov     [rax+20h], r9
0x180027a33  mov     [rax+18h], r8
0x180027a37  mov     [rax+10h], edx
0x180027a3a  mov     [rax+8], rcx
0x180027a3e  push    rbx
0x180027a3f  push    rbp
0x180027a40  push    rsi
0x180027a41  push    rdi
0x180027a42  push    r12
0x180027a44  push    r13
0x180027a46  push    r14
0x180027a48  push    r15
0x180027a4a  sub     rsp, 48h
0x180027a4e  mov     rbx, rcx
0x180027a51  xor     eax, eax
0x180027a53  xor     r14d, r14d
0x180027a56  mov     [rsp+88h+var_50], rax
0x180027a5b  xor     ebp, ebp
0x180027a5d  mov     [rsp+88h+var_58], r14d
0x180027a62  lea     rcx, g_TaskHostContextListLock
0x180027a69  mov     [rsp+88h+var_54], ebp
0x180027a6d  xor     r15d, r15d
0x180027a70  xor     esi, esi
0x180027a72  call    cs:__imp_RtlAcquireSRWLockShared
0x180027a78  xor     r12d, r12d
0x180027a7b  cmp     r12d, 2
0x180027a7f  jnb     loc_180027C88
0x180027a85  cmp     r12d, 1
0x180027a89  jz      loc_180027C16
0x180027a8f  mov     rdi, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180027a96  lea     rax, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180027a9d  cmp     rdi, rax
0x180027aa0  jz      loc_180027C0E
0x180027aa6  mov     rdx, [rdi+18h]; pSid2
0x180027aaa  mov     rcx, rbx; pSid1
0x180027aad  call    cs:__imp_EqualSid
0x180027ab3  test    eax, eax
0x180027ab5  jnz     short loc_180027ABC
0x180027ab7  mov     rdi, [rdi]
0x180027aba  jmp     short loc_180027A96
0x180027abc  cmp     qword ptr [rdi+30h], 0
0x180027ac1  jz      short loc_180027AB7
0x180027ac3  mov     rbx, cs:g_leTaskHostContextListHead
0x180027aca  lea     rax, g_leTaskHostContextListHead
0x180027ad1  xor     r13b, r13b
0x180027ad4  cmp     rbx, rax
0x180027ad7  jz      short loc_180027B24
0x180027ad9  mov     al, [rbx+60h]
0x180027adc  and     al, 54h
0x180027ade  cmp     al, 10h
0x180027ae0  jnz     short loc_180027B0C
0x180027ae2  lea     r14, [rbx+38h]
0x180027ae6  mov     rcx, r14
0x180027ae9  call    cs:__imp_RtlAcquireSRWLockShared
0x180027aef  movzx   eax, byte ptr [rbx+1A8h]
0x180027af6  cmp     eax, [rsp+88h+arg_8]
0x180027afd  jz      loc_180027BAF
0x180027b03  mov     rcx, r14
0x180027b06  call    cs:__imp_RtlReleaseSRWLockShared
0x180027b0c  mov     rbx, [rbx]
0x180027b0f  lea     rax, g_leTaskHostContextListHead
0x180027b16  cmp     rbx, rax
0x180027b19  jnz     short loc_180027AD9
0x180027b1b  mov     r14d, [rsp+88h+var_58]
0x180027b20  mov     ebp, [rsp+88h+var_54]
0x180027b24  test    r12d, r12d
0x180027b27  jz      loc_180027C3E
0x180027b2d  mov     r14, [rsp+88h+var_50]
0x180027b32  mov     ebx, ebp
0x180027b34  mov     [rsi+rbx*8], r14
0x180027b38  mov     rcx, [rdi+30h]; pSid
0x180027b3c  call    cs:__imp_GetLengthSid
0x180027b42  mov     r8, [rdi+30h]; pSourceSid
0x180027b46  mov     ecx, eax; nDestinationSidLength
0x180027b48  mov     rdx, [rsi+rbx*8]; pDestinationSid
0x180027b4c  mov     ebp, eax
0x180027b4e  call    cs:__imp_CopySid
0x180027b54  test    eax, eax
0x180027b56  jz      loc_180027C58
0x180027b5c  mov     rax, [rsp+88h+arg_20]
0x180027b64  mov     rcx, [rdi+20h]
0x180027b68  or      [rax], rcx
0x180027b6b  mov     r8, [rax]
0x180027b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b75  lea     rax, WPP_GLOBAL_Control
0x180027b7c  cmp     rcx, rax
0x180027b7f  jz      short loc_180027B8B
0x180027b81  test    byte ptr [rcx+1Ch], 80h
0x180027b85  jnz     loc_180027CC2
0x180027b8b  add     r14, rbp
0x180027b8e  mov     ebp, [rsp+88h+var_54]
0x180027b92  inc     ebp
0x180027b94  mov     [rsp+88h+var_50], r14
0x180027b99  mov     [rsp+88h+var_54], ebp
0x180027b9d  mov     r14d, [rsp+88h+var_58]
0x180027ba2  mov     rbx, [rsp+88h+pSid2]
0x180027baa  jmp     loc_180027AB7
0x180027baf  cmp     byte ptr [rbx+60h], 0
0x180027bb3  jl      loc_180027B03
0x180027bb9  mov     rcx, [rbx+0B0h]; pSid1
0x180027bc0  test    rcx, rcx
0x180027bc3  jz      loc_180027B03
0x180027bc9  mov     rdx, [rsp+88h+pSid2]; pSid2
0x180027bd1  call    cs:__imp_EqualSid
0x180027bd7  test    eax, eax
0x180027bd9  jz      loc_180027B03
0x180027bdf  xor     ebp, ebp
0x180027be1  cmp     ebp, [rbx+180h]
0x180027be7  jnb     loc_180027CA7
0x180027bed  mov     rcx, [rbx+188h]
0x180027bf4  mov     rdx, [rdi+30h]; pSid2
0x180027bf8  mov     rcx, [rcx+rbp*8]; pSid1
0x180027bfc  call    cs:__imp_EqualSid
0x180027c02  test    eax, eax
0x180027c04  jnz     loc_180027CA4
0x180027c0a  inc     ebp
0x180027c0c  jmp     short loc_180027BE1
0x180027c0e  inc     r12d
0x180027c11  jmp     loc_180027A7B
0x180027c16  test    r15d, r15d
0x180027c19  jz      loc_180027CDE
0x180027c1f  lea     ecx, [r14+r15*8]; Size
0x180027c23  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180027c28  mov     rsi, rax
0x180027c2b  test    rax, rax
0x180027c2e  jz      short loc_180027C58
0x180027c30  lea     rax, [rax+r15*8]
0x180027c34  mov     [rsp+88h+var_50], rax
0x180027c39  jmp     loc_180027A8F
0x180027c3e  mov     rcx, [rdi+30h]; pSid
0x180027c42  inc     r15d
0x180027c45  call    cs:__imp_GetLengthSid
0x180027c4b  add     r14d, eax
0x180027c4e  mov     [rsp+88h+var_58], r14d
0x180027c53  jmp     loc_180027BA2
0x180027c58  call    cs:__imp_GetLastError
0x180027c5e  mov     ebx, eax
0x180027c60  lea     rcx, g_TaskHostContextListLock
0x180027c67  call    cs:__imp_RtlReleaseSRWLockShared
0x180027c6d  mov     rcx, rsi
0x180027c70  call    UBPM_MIDL_user_free
0x180027c75  mov     eax, ebx
0x180027c77  add     rsp, 48h
0x180027c7b  pop     r15
0x180027c7d  pop     r14
0x180027c7f  pop     r13
0x180027c81  pop     r12
0x180027c83  pop     rdi
0x180027c84  pop     rsi
0x180027c85  pop     rbp
0x180027c86  pop     rbx
0x180027c87  retn
0x180027c88  mov     rax, [rsp+88h+arg_18]
0x180027c90  mov     [rax], rsi
0x180027c93  xor     esi, esi
0x180027c95  mov     rax, [rsp+88h+arg_10]
0x180027c9d  xor     ebx, ebx
0x180027c9f  mov     [rax], r15d
0x180027ca2  jmp     short loc_180027C60
0x180027ca4  mov     r13b, 1
0x180027ca7  mov     rcx, r14
0x180027caa  call    cs:__imp_RtlReleaseSRWLockShared
0x180027cb0  test    r13b, r13b
0x180027cb3  jz      loc_180027B0C
0x180027cb9  mov     ebp, [rsp+88h+var_54]
0x180027cbd  jmp     loc_180027B9D
0x180027cc2  mov     r9, [rdi+10h]
0x180027cc6  mov     edx, 0E0h
0x180027ccb  mov     rcx, [rcx+10h]
0x180027ccf  mov     [rsp+88h+var_68], r8
0x180027cd4  call    WPP_SF_Si
0x180027cd9  jmp     loc_180027B8B
0x180027cde  mov     ebx, 0Dh
0x180027ce3  jmp     loc_180027C60
```
