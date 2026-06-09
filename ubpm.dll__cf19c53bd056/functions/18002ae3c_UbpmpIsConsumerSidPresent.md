# UbpmpIsConsumerSidPresent

- ea: `0x18002ae3c`
- end: `0x18002af47`
- name: `UbpmpIsConsumerSidPresent`
- size: `267`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020900`

## callees

- `0x180019d90`
- `0x18001e9f4`
- `0x180029398`
- `0x18002ae3c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002aef8`
- `msvcrt!_wcsicmp` at `0x18002aef8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002aec9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002af20`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002aec9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002af20`

## pseudocode

```c
char __fastcall UbpmpIsConsumerSidPresent(wchar_t *String2, unsigned int a2, __int64 a3, char a4)
{
  char v4; // si
  int ConsumerSid; // eax
  __int64 k; // rbx
  struct _LIST_ENTRY *i; // rbx
  __int64 j; // rdi
  PSID pSid2; // [rsp+30h] [rbp-38h] BYREF

  v4 = 0;
  pSid2 = 0;
  if ( a4 )
  {
    for ( i = g_leTaskHostHardeningListHead.Flink; i != &g_leTaskHostHardeningListHead; i = i->Flink )
    {
      if ( i[3].Flink && !_wcsicmp((const wchar_t *)i[1].Flink, String2) )
      {
        for ( j = 0; (unsigned int)j < *(_DWORD *)(a3 + 392); j = (unsigned int)(j + 1) )
        {
          if ( EqualSid(*(PSID *)(*(_QWORD *)(a3 + 400) + 8 * j), i[3].Flink) )
          {
LABEL_19:
            v4 = 1;
            goto LABEL_20;
          }
        }
        break;
      }
    }
  }
  else
  {
    ConsumerSid = UbpmUtilsGetConsumerSid(String2, a2, &pSid2, 0);
    if ( ConsumerSid )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          225,
          (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          (_DWORD)String2,
          ConsumerSid);
    }
    else
    {
      for ( k = 0; (unsigned int)k < *(_DWORD *)(a3 + 392); k = (unsigned int)(k + 1) )
      {
        if ( EqualSid(*(PSID *)(*(_QWORD *)(a3 + 400) + 8 * k), pSid2) )
          goto LABEL_19;
      }
    }
  }
LABEL_20:
  UBPM_MIDL_user_free(pSid2);
  return v4;
}

```

## disassembly

```asm
0x18002ae3c  push    rbx
0x18002ae3e  push    rbp
0x18002ae3f  push    rsi
0x18002ae40  push    rdi
0x18002ae41  sub     rsp, 48h
0x18002ae45  xor     sil, sil
0x18002ae48  mov     [rsp+68h+pSid2], 0
0x18002ae51  mov     rbp, r8
0x18002ae54  mov     rdi, rcx
0x18002ae57  test    r9b, r9b
0x18002ae5a  jnz     short loc_18002AED7
0x18002ae5c  xor     r9d, r9d; unsigned int *
0x18002ae5f  lea     r8, [rsp+68h+pSid2]; void **
0x18002ae64  call    ?UbpmUtilsGetConsumerSid@@YAKPEBGKPEAPEAXPEAK@Z; UbpmUtilsGetConsumerSid(ushort const *,ulong,void * *,ulong *)
0x18002ae69  test    eax, eax
0x18002ae6b  jz      short loc_18002AEAF
0x18002ae6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae74  lea     rdx, WPP_GLOBAL_Control
0x18002ae7b  cmp     rcx, rdx
0x18002ae7e  jz      loc_18002AF31
0x18002ae84  test    byte ptr [rcx+1Ch], 1
0x18002ae88  jz      loc_18002AF31
0x18002ae8e  mov     rcx, [rcx+10h]
0x18002ae92  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002ae99  mov     edx, 0E1h
0x18002ae9e  mov     [rsp+68h+var_48], eax
0x18002aea2  mov     r9, rdi
0x18002aea5  call    WPP_SF_Sd
0x18002aeaa  jmp     loc_18002AF31
0x18002aeaf  xor     ebx, ebx
0x18002aeb1  cmp     ebx, [rbp+188h]
0x18002aeb7  jnb     short loc_18002AF31
0x18002aeb9  mov     rcx, [rbp+190h]
0x18002aec0  mov     rdx, [rsp+68h+pSid2]; pSid2
0x18002aec5  mov     rcx, [rcx+rbx*8]; pSid1
0x18002aec9  call    cs:__imp_EqualSid
0x18002aecf  test    eax, eax
0x18002aed1  jnz     short loc_18002AF2E
0x18002aed3  inc     ebx
0x18002aed5  jmp     short loc_18002AEB1
0x18002aed7  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18002aede  lea     rax, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18002aee5  cmp     rbx, rax
0x18002aee8  jz      short loc_18002AF31
0x18002aeea  cmp     qword ptr [rbx+30h], 0
0x18002aeef  jz      short loc_18002AF02
0x18002aef1  mov     rcx, [rbx+10h]; String1
0x18002aef5  mov     rdx, rdi; String2
0x18002aef8  call    cs:__imp__wcsicmp
0x18002aefe  test    eax, eax
0x18002af00  jz      short loc_18002AF07
0x18002af02  mov     rbx, [rbx]
0x18002af05  jmp     short loc_18002AEDE
0x18002af07  xor     edi, edi
0x18002af09  cmp     edi, [rbp+188h]
0x18002af0f  jnb     short loc_18002AF31
0x18002af11  mov     rcx, [rbp+190h]
0x18002af18  mov     rdx, [rbx+30h]; pSid2
0x18002af1c  mov     rcx, [rcx+rdi*8]; pSid1
0x18002af20  call    cs:__imp_EqualSid
0x18002af26  test    eax, eax
0x18002af28  jnz     short loc_18002AF2E
0x18002af2a  inc     edi
0x18002af2c  jmp     short loc_18002AF09
0x18002af2e  mov     sil, 1
0x18002af31  mov     rcx, [rsp+68h+pSid2]
0x18002af36  call    UBPM_MIDL_user_free
0x18002af3b  mov     al, sil
0x18002af3e  add     rsp, 48h
0x18002af42  pop     rdi
0x18002af43  pop     rsi
0x18002af44  pop     rbp
0x18002af45  pop     rbx
0x18002af46  retn
```
