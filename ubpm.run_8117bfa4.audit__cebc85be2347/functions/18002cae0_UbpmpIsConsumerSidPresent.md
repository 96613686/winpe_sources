# UbpmpIsConsumerSidPresent

- ea: `0x18002cae0`
- end: `0x18002cc06`
- name: `UbpmpIsConsumerSidPresent`
- size: `294`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001d230`

## callees

- `0x18000fbf0`
- `0x18001af64`
- `0x18002b3a8`
- `0x18002cae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002cbaa`
- `msvcrt!_wcsicmp` at `0x18002cbaa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002cb75`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002cbd8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002cb75`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002cbd8`

## pseudocode

```c
char __fastcall UbpmpIsConsumerSidPresent(wchar_t *String2, PVOID *a2, __int64 a3, __int64 a4)
{
  char v4; // si
  unsigned int ConsumerSid; // eax
  __int64 k; // rbx
  struct _LIST_ENTRY *i; // rbx
  __int64 j; // rdi
  PSID pSid2; // [rsp+30h] [rbp-38h] BYREF

  v4 = 0;
  pSid2 = 0;
  if ( (_BYTE)a4 )
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
    ConsumerSid = UbpmUtilsGetConsumerSid(String2, (unsigned int)a2, &pSid2, 0);
    if ( ConsumerSid )
    {
      a2 = &WPP_GLOBAL_Control;
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
  UBPM_MIDL_user_free(pSid2, a2, a3, a4);
  return v4;
}

```

## disassembly

```asm
0x18002cae0  push    rbx
0x18002cae2  push    rbp
0x18002cae3  push    rsi
0x18002cae4  push    rdi
0x18002cae5  sub     rsp, 48h
0x18002cae9  xor     sil, sil
0x18002caec  mov     [rsp+68h+pSid2], 0
0x18002caf5  mov     rbp, r8
0x18002caf8  mov     rdi, rcx
0x18002cafb  test    r9b, r9b
0x18002cafe  jnz     loc_18002CB89
0x18002cb04  xor     r9d, r9d; unsigned int *
0x18002cb07  lea     r8, [rsp+68h+pSid2]; void **
0x18002cb0c  call    ?UbpmUtilsGetConsumerSid@@YAKPEBGKPEAPEAXPEAK@Z; UbpmUtilsGetConsumerSid(ushort const *,ulong,void * *,ulong *)
0x18002cb11  test    eax, eax
0x18002cb13  jz      short loc_18002CB57
0x18002cb15  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb1c  lea     rdx, WPP_GLOBAL_Control
0x18002cb23  cmp     rcx, rdx
0x18002cb26  jz      loc_18002CBEF
0x18002cb2c  test    byte ptr [rcx+1Ch], 1
0x18002cb30  jz      loc_18002CBEF
0x18002cb36  mov     rcx, [rcx+10h]
0x18002cb3a  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002cb41  mov     edx, 0E1h
0x18002cb46  mov     [rsp+68h+var_48], eax
0x18002cb4a  mov     r9, rdi
0x18002cb4d  call    WPP_SF_Sd
0x18002cb52  jmp     loc_18002CBEF
0x18002cb57  xor     ebx, ebx
0x18002cb59  cmp     ebx, [rbp+188h]
0x18002cb5f  jnb     loc_18002CBEF
0x18002cb65  mov     rcx, [rbp+190h]
0x18002cb6c  mov     rdx, [rsp+68h+pSid2]; pSid2
0x18002cb71  mov     rcx, [rcx+rbx*8]; pSid1
0x18002cb75  call    cs:__imp_EqualSid
0x18002cb7c  nop     dword ptr [rax+rax+00h]
0x18002cb81  test    eax, eax
0x18002cb83  jnz     short loc_18002CBEC
0x18002cb85  inc     ebx
0x18002cb87  jmp     short loc_18002CB59
0x18002cb89  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18002cb90  lea     rax, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18002cb97  cmp     rbx, rax
0x18002cb9a  jz      short loc_18002CBEF
0x18002cb9c  cmp     qword ptr [rbx+30h], 0
0x18002cba1  jz      short loc_18002CBBA
0x18002cba3  mov     rcx, [rbx+10h]; String1
0x18002cba7  mov     rdx, rdi; String2
0x18002cbaa  call    cs:__imp__wcsicmp
0x18002cbb1  nop     dword ptr [rax+rax+00h]
0x18002cbb6  test    eax, eax
0x18002cbb8  jz      short loc_18002CBBF
0x18002cbba  mov     rbx, [rbx]
0x18002cbbd  jmp     short loc_18002CB90
0x18002cbbf  xor     edi, edi
0x18002cbc1  cmp     edi, [rbp+188h]
0x18002cbc7  jnb     short loc_18002CBEF
0x18002cbc9  mov     rcx, [rbp+190h]
0x18002cbd0  mov     rdx, [rbx+30h]; pSid2
0x18002cbd4  mov     rcx, [rcx+rdi*8]; pSid1
0x18002cbd8  call    cs:__imp_EqualSid
0x18002cbdf  nop     dword ptr [rax+rax+00h]
0x18002cbe4  test    eax, eax
0x18002cbe6  jnz     short loc_18002CBEC
0x18002cbe8  inc     edi
0x18002cbea  jmp     short loc_18002CBC1
0x18002cbec  mov     sil, 1
0x18002cbef  mov     rcx, [rsp+68h+pSid2]
0x18002cbf4  call    UBPM_MIDL_user_free
0x18002cbf9  mov     al, sil
0x18002cbfc  add     rsp, 48h
0x18002cc00  pop     rdi
0x18002cc01  pop     rsi
0x18002cc02  pop     rbp
0x18002cc03  pop     rbx
0x18002cc04  retn
```
