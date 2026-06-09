# CSIsUserInAdministratorGroup

- ea: `0x180008f80`
- end: `0x1800090d3`
- name: `CSIsUserInAdministratorGroup`
- size: `339`
- prototype: `__int64 __fastcall(PSID pSid2, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006890`
- `0x180006b00`

## callees

- `0x180008b48`
- `0x180008e4c`
- `0x180008f80`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000906b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000906b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090b3`
- `SAMLIB!SamFreeMemory` at `0x18000908b`
- `SAMLIB!SamFreeMemory` at `0x18000908b`
- `SAMLIB!SamGetMembersInAlias` at `0x18000903f`
- `SAMLIB!SamGetMembersInAlias` at `0x18000903f`
- `SAMLIB!SamOpenAlias` at `0x180009019`
- `SAMLIB!SamOpenAlias` at `0x180009019`
- `SAMLIB!SamCloseHandle` at `0x180009095`
- `SAMLIB!SamCloseHandle` at `0x18000909f`
- `SAMLIB!SamCloseHandle` at `0x1800090a9`
- `SAMLIB!SamCloseHandle` at `0x180009095`
- `SAMLIB!SamCloseHandle` at `0x18000909f`
- `SAMLIB!SamCloseHandle` at `0x1800090a9`

## pseudocode

```c
__int64 __fastcall CSIsUserInAdministratorGroup(PSID pSid2, int *a2)
{
  unsigned int v2; // esi
  int v5; // ebx
  int v6; // eax
  int MembersInAlias; // eax
  unsigned int v8; // r14d
  __int64 v9; // r13
  int v10; // r15d
  void *v11; // rcx
  __int64 v12; // rcx
  void *v14; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  void *v16; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v17; // [rsp+90h] [rbp+40h] BYREF
  __int64 v18; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  v5 = -2147024809;
  if ( pSid2 )
  {
    if ( a2 )
    {
      *a2 = 0;
      pv = 0;
      v5 = CSGetBuiltInDomainSid(&pv);
      if ( v5 >= 0 )
      {
        v16 = 0;
        v14 = 0;
        v5 = SamHandleForDomain(pv, 0x20021u, 0x20385u, &v16, &v14);
        if ( v5 >= 0 )
        {
          v19 = 0;
          v6 = SamOpenAlias(v14, 131084, 544, &v19);
          v5 = v6 | 0x10000000;
          if ( v6 >= 0 )
          {
            v17 = 0;
            v18 = 0;
            MembersInAlias = SamGetMembersInAlias(v19, &v18, &v17);
            v5 = MembersInAlias | 0x10000000;
            if ( MembersInAlias >= 0 )
            {
              v8 = v17;
              if ( v17 )
              {
                v9 = v18;
                v10 = 0;
                while ( 1 )
                {
                  v11 = *(void **)(v9 + 8LL * v2);
                  if ( v11 )
                  {
                    if ( EqualSid(v11, pSid2) )
                      break;
                  }
                  if ( ++v2 >= v8 )
                    goto LABEL_14;
                }
                v10 = 1;
LABEL_14:
                v12 = v18;
                *a2 = v10;
                SamFreeMemory(v12);
              }
            }
            SamCloseHandle(v19);
          }
          SamCloseHandle(v14);
          SamCloseHandle(v16);
        }
        CoTaskMemFree(pv);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008f80  mov     [rsp-38h+arg_8], rbx
0x180008f85  push    rbp
0x180008f86  push    rsi
0x180008f87  push    rdi
0x180008f88  push    r12
0x180008f8a  push    r13
0x180008f8c  push    r14
0x180008f8e  push    r15
0x180008f90  mov     rbp, rsp
0x180008f93  sub     rsp, 50h
0x180008f97  xor     esi, esi
0x180008f99  mov     rdi, rdx
0x180008f9c  mov     r12, rcx
0x180008f9f  mov     ebx, 80070057h
0x180008fa4  test    rcx, rcx
0x180008fa7  jz      loc_1800090B9
0x180008fad  test    rdx, rdx
0x180008fb0  jz      loc_1800090B9
0x180008fb6  lea     rcx, [rbp+pv]
0x180008fba  mov     [rdx], esi
0x180008fbc  mov     [rbp+pv], rsi
0x180008fc0  call    CSGetBuiltInDomainSid
0x180008fc5  mov     ebx, eax
0x180008fc7  test    eax, eax
0x180008fc9  js      loc_1800090B9
0x180008fcf  mov     rcx, [rbp+pv]; void *
0x180008fd3  lea     rax, [rbp+var_20]
0x180008fd7  lea     r9, [rbp+var_10]; void **
0x180008fdb  mov     [rsp+50h+var_30], rax; void **
0x180008fe0  mov     edx, 20021h; unsigned int
0x180008fe5  mov     [rbp+var_10], rsi
0x180008fe9  mov     r8d, 20385h; unsigned int
0x180008fef  mov     [rbp+var_20], rsi
0x180008ff3  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x180008ff8  mov     ebx, eax
0x180008ffa  test    eax, eax
0x180008ffc  js      loc_1800090AF
0x180009002  mov     rcx, [rbp+var_20]
0x180009006  lea     r9, [rbp+arg_18]
0x18000900a  mov     edx, 2000Ch
0x18000900f  mov     [rbp+arg_18], rsi
0x180009013  mov     r8d, 220h
0x180009019  call    cs:__imp_SamOpenAlias
0x18000901f  mov     ebx, eax
0x180009021  mov     r14d, 10000000h
0x180009027  or      ebx, r14d
0x18000902a  jl      short loc_18000909B
0x18000902c  mov     rcx, [rbp+arg_18]
0x180009030  lea     r8, [rbp+arg_0]
0x180009034  lea     rdx, [rbp+arg_10]
0x180009038  mov     [rbp+arg_0], esi
0x18000903b  mov     [rbp+arg_10], rsi
0x18000903f  call    cs:__imp_SamGetMembersInAlias
0x180009045  mov     ebx, eax
0x180009047  or      ebx, r14d
0x18000904a  jl      short loc_180009091
0x18000904c  mov     r14d, [rbp+arg_0]
0x180009050  test    r14d, r14d
0x180009053  jz      short loc_180009091
0x180009055  mov     r13, [rbp+arg_10]
0x180009059  mov     r15d, esi
0x18000905c  mov     eax, esi
0x18000905e  mov     rcx, [r13+rax*8+0]; pSid1
0x180009063  test    rcx, rcx
0x180009066  jz      short loc_180009075
0x180009068  mov     rdx, r12; pSid2
0x18000906b  call    cs:__imp_EqualSid
0x180009071  test    eax, eax
0x180009073  jnz     short loc_18000907E
0x180009075  inc     esi
0x180009077  cmp     esi, r14d
0x18000907a  jb      short loc_18000905C
0x18000907c  jmp     short loc_180009084
0x18000907e  mov     r15d, 1
0x180009084  mov     rcx, [rbp+arg_10]
0x180009088  mov     [rdi], r15d
0x18000908b  call    cs:__imp_SamFreeMemory
0x180009091  mov     rcx, [rbp+arg_18]
0x180009095  call    cs:__imp_SamCloseHandle
0x18000909b  mov     rcx, [rbp+var_20]
0x18000909f  call    cs:__imp_SamCloseHandle
0x1800090a5  mov     rcx, [rbp+var_10]
0x1800090a9  call    cs:__imp_SamCloseHandle
0x1800090af  mov     rcx, [rbp+pv]; pv
0x1800090b3  call    cs:__imp_CoTaskMemFree
0x1800090b9  mov     eax, ebx
0x1800090bb  mov     rbx, [rsp+50h+arg_8]
0x1800090c3  add     rsp, 50h
0x1800090c7  pop     r15
0x1800090c9  pop     r14
0x1800090cb  pop     r13
0x1800090cd  pop     r12
0x1800090cf  pop     rdi
0x1800090d0  pop     rsi
0x1800090d1  pop     rbp
0x1800090d2  retn
```
