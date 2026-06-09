# CAccountManager::GetAccountPolicy(_WINBIO_IDENTITY *,uint,_WINBIO_ACCOUNT_POLICY *,_WINBIO_POLICY_SOURCE *)

- ea: `0x18002adf4`
- end: `0x18002b015`
- name: `?GetAccountPolicy@CAccountManager@@SAJPEAU_WINBIO_IDENTITY@@IPEAU_WINBIO_ACCOUNT_POLICY@@PEAW4_WINBIO_POLICY_SOURCE@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(struct _WINBIO_IDENTITY *, winbio *this, struct _WINBIO_ACCOUNT_POLICY *, enum _WINBIO_POLICY_SOURCE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f7c0`
- `0x1800b3dd0`

## callees

- `0x180008dd0`
- `0x18000986c`
- `0x18002adf4`
- `0x18002b2f8`
- `0x18002b368`
- `0x18002b408`
- `0x180068f60`
- `0x180069cc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002afe4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002afe4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aeb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aeb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002aec9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002aec9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002ae40`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002ae40`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAccountManager::GetAccountPolicy(
        struct _WINBIO_IDENTITY *a1,
        winbio *this,
        struct _WINBIO_ACCOUNT_POLICY *a3,
        enum _WINBIO_POLICY_SOURCE *a4)
{
  unsigned int v6; // ebp
  __int64 result; // rax
  RTL_SRWLOCK *v9; // rsi
  CAccountManager *v10; // rax
  RTL_SRWLOCK *v11; // r15
  CAccountManager *v12; // rax
  int ManagementPolicy; // esi
  CAccountManager *v14; // rax
  int Policy; // eax
  CAccountManager *v16; // rax
  struct _WINBIO_IDENTITY v17; // [rsp+30h] [rbp-98h] BYREF

  v6 = (unsigned int)this;
  if ( !a1 )
    return 2147500035LL;
  if ( a1->Type != 1 && (a1->Type != 3 || !IsValidSid(a1->Value.AccountSid.Data)) )
    return 2147942487LL;
  result = winbio::ValidateFactor((winbio *)v6, (unsigned int)this);
  if ( (int)result >= 0 )
  {
    if ( a3 && a4 )
    {
      memset_0(a3, 0, sizeof(struct _WINBIO_ACCOUNT_POLICY));
      *a4 = WINBIO_POLICY_UNKNOWN;
      v9 = (RTL_SRWLOCK *)((char *)CAccountManager::Instance() + 8);
      AcquireSRWLockExclusive(v9);
      v10 = CAccountManager::Instance();
      CAccountManager::LoadManagementPolicy(v10);
      if ( v9 )
        ReleaseSRWLockExclusive(v9);
      v11 = (RTL_SRWLOCK *)((char *)CAccountManager::Instance() + 8);
      AcquireSRWLockShared(v11);
      v12 = CAccountManager::Instance();
      ManagementPolicy = CAccountManager::GetManagementPolicy(v12, v6, a3);
      if ( ManagementPolicy < 0 )
      {
        v14 = CAccountManager::Instance();
        Policy = CAccountManager::FindPolicy(v14, a1, v6, a3);
        ManagementPolicy = Policy;
        if ( Policy < 0 )
        {
          if ( Policy == -2147023728 )
          {
            memset_0(&v17, 0, sizeof(v17));
            v17.Type = 1;
            v16 = CAccountManager::Instance();
            ManagementPolicy = CAccountManager::FindPolicy(v16, &v17, v6, a3);
            if ( ManagementPolicy == -2147023728 )
            {
              CAccountManager::Instance();
              ManagementPolicy = 0;
              if ( v6 == 4 || v6 == 8 || v6 == 2 || v6 == 16 )
              {
                a3->AntiSpoofBehavior = WINBIO_ANTI_SPOOF_DISABLE;
                a3->Identity.Type = 1;
              }
              else
              {
                ManagementPolicy = -2147023728;
              }
            }
            if ( ManagementPolicy >= 0 )
            {
              *(_OWORD *)&a3->Identity.Type = *(_OWORD *)&a1->Type;
              *(_OWORD *)&a3->Identity.Value.AccountSid.Data[8] = *(_OWORD *)&a1->Value.AccountSid.Data[8];
              *(_OWORD *)&a3->Identity.Value.AccountSid.Data[24] = *(_OWORD *)&a1->Value.AccountSid.Data[24];
              *(_OWORD *)&a3->Identity.Value.AccountSid.Data[40] = *(_OWORD *)&a1->Value.AccountSid.Data[40];
              *(_OWORD *)&a3->Identity.Value.AccountSid.Data[52] = *(_OWORD *)&a1->Value.AccountSid.Data[52];
              *a4 = WINBIO_POLICY_DEFAULT;
            }
          }
        }
        else
        {
          *a4 = WINBIO_POLICY_LOCAL;
        }
      }
      else
      {
        *(_OWORD *)&a3->Identity.Type = *(_OWORD *)&a1->Type;
        *(_OWORD *)&a3->Identity.Value.AccountSid.Data[8] = *(_OWORD *)&a1->Value.AccountSid.Data[8];
        *(_OWORD *)&a3->Identity.Value.AccountSid.Data[24] = *(_OWORD *)&a1->Value.AccountSid.Data[24];
        *(_OWORD *)&a3->Identity.Value.AccountSid.Data[40] = *(_OWORD *)&a1->Value.AccountSid.Data[40];
        *(_OWORD *)&a3->Identity.Value.AccountSid.Data[52] = *(_OWORD *)&a1->Value.AccountSid.Data[52];
        *a4 = WINBIO_POLICY_ADMIN;
      }
      if ( v11 )
        ReleaseSRWLockShared(v11);
      return (unsigned int)ManagementPolicy;
    }
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002adf4  push    rbx
0x18002adf6  push    rbp
0x18002adf7  push    rsi
0x18002adf8  push    rdi
0x18002adf9  push    r13
0x18002adfb  push    r14
0x18002adfd  push    r15
0x18002adff  sub     rsp, 90h
0x18002ae06  mov     rax, cs:__security_cookie
0x18002ae0d  xor     rax, rsp
0x18002ae10  mov     [rsp+0C8h+var_48], rax
0x18002ae18  mov     r14, r9
0x18002ae1b  mov     rbx, r8
0x18002ae1e  mov     ebp, edx
0x18002ae20  mov     rdi, rcx
0x18002ae23  test    rcx, rcx
0x18002ae26  jz      loc_18002AFEE
0x18002ae2c  mov     r13d, 1
0x18002ae32  cmp     [rcx], r13d
0x18002ae35  jz      short loc_18002AE54
0x18002ae37  cmp     dword ptr [rcx], 3
0x18002ae3a  jnz     short loc_18002AE4A
0x18002ae3c  add     rcx, 8; pSid
0x18002ae40  call    cs:__imp_IsValidSid
0x18002ae46  test    eax, eax
0x18002ae48  jnz     short loc_18002AE54
0x18002ae4a  mov     eax, 80070057h
0x18002ae4f  jmp     loc_18002AFF3
0x18002ae54  mov     ecx, ebp; this
0x18002ae56  call    ?ValidateFactor@winbio@@YAJI@Z; winbio::ValidateFactor(uint)
0x18002ae5b  test    eax, eax
0x18002ae5d  js      loc_18002AFF3
0x18002ae63  test    rbx, rbx
0x18002ae66  jz      loc_18002AFEE
0x18002ae6c  test    r14, r14
0x18002ae6f  jz      loc_18002AFEE
0x18002ae75  xor     edx, edx; Val
0x18002ae77  lea     r8d, [rdx+50h]; Size
0x18002ae7b  mov     rcx, rbx; void *
0x18002ae7e  call    memset_0
0x18002ae83  mov     dword ptr [r14], 0
0x18002ae8a  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x18002ae8f  lea     rsi, [rax+8]
0x18002ae93  mov     rcx, rsi; SRWLock
0x18002ae96  call    cs:__imp_AcquireSRWLockExclusive
0x18002ae9c  mov     [rsp+0C8h+var_A8], rsi
0x18002aea1  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x18002aea6  mov     rcx, rax; this
0x18002aea9  call    ?LoadManagementPolicy@CAccountManager@@AEAAJXZ; CAccountManager::LoadManagementPolicy(void)
0x18002aeae  nop
0x18002aeaf  test    rsi, rsi
0x18002aeb2  jz      short loc_18002AEBD
0x18002aeb4  mov     rcx, rsi; SRWLock
0x18002aeb7  call    cs:__imp_ReleaseSRWLockExclusive
0x18002aebd  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x18002aec2  lea     r15, [rax+8]
0x18002aec6  mov     rcx, r15; SRWLock
0x18002aec9  call    cs:__imp_AcquireSRWLockShared
0x18002aecf  mov     [rsp+0C8h+var_A8], r15
0x18002aed4  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x18002aed9  mov     r8, rbx; struct _WINBIO_ACCOUNT_POLICY *
0x18002aedc  mov     edx, ebp; unsigned int
0x18002aede  mov     rcx, rax; this
0x18002aee1  call    ?GetManagementPolicy@CAccountManager@@AEAAJIPEAU_WINBIO_ACCOUNT_POLICY@@@Z; CAccountManager::GetManagementPolicy(uint,_WINBIO_ACCOUNT_POLICY *)
0x18002aee6  mov     esi, eax
0x18002aee8  test    eax, eax
0x18002aeea  js      short loc_18002AF1E
0x18002aeec  movups  xmm0, xmmword ptr [rdi]
0x18002aeef  movups  xmmword ptr [rbx], xmm0
0x18002aef2  movups  xmm1, xmmword ptr [rdi+10h]
0x18002aef6  movups  xmmword ptr [rbx+10h], xmm1
0x18002aefa  movups  xmm0, xmmword ptr [rdi+20h]
0x18002aefe  movups  xmmword ptr [rbx+20h], xmm0
0x18002af02  movups  xmm1, xmmword ptr [rdi+30h]
0x18002af06  movups  xmmword ptr [rbx+30h], xmm1
0x18002af0a  movups  xmm0, xmmword ptr [rdi+3Ch]
0x18002af0e  movups  xmmword ptr [rbx+3Ch], xmm0
0x18002af12  mov     dword ptr [r14], 3
0x18002af19  jmp     loc_18002AFDC
0x18002af1e  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x18002af23  mov     r9, rbx; struct _WINBIO_ACCOUNT_POLICY *
0x18002af26  mov     r8d, ebp; unsigned int
0x18002af29  mov     rdx, rdi; struct _WINBIO_IDENTITY *
0x18002af2c  mov     rcx, rax; this
0x18002af2f  call    ?FindPolicy@CAccountManager@@AEAAJPEAU_WINBIO_IDENTITY@@IPEAU_WINBIO_ACCOUNT_POLICY@@@Z; CAccountManager::FindPolicy(_WINBIO_IDENTITY *,uint,_WINBIO_ACCOUNT_POLICY *)
0x18002af34  mov     esi, eax
0x18002af36  test    eax, eax
0x18002af38  js      short loc_18002AF46
0x18002af3a  mov     dword ptr [r14], 2
0x18002af41  jmp     loc_18002AFDC
0x18002af46  cmp     eax, 80070490h
0x18002af4b  jnz     loc_18002AFDC
0x18002af51  xor     edx, edx; Val
0x18002af53  lea     r8d, [rdx+4Ch]; Size
0x18002af57  lea     rcx, [rsp+0C8h+var_98]; void *
0x18002af5c  call    memset_0
0x18002af61  mov     [rsp+0C8h+var_98.Type], r13d
0x18002af66  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x18002af6b  mov     r9, rbx; struct _WINBIO_ACCOUNT_POLICY *
0x18002af6e  mov     r8d, ebp; unsigned int
0x18002af71  lea     rdx, [rsp+0C8h+var_98]; struct _WINBIO_IDENTITY *
0x18002af76  mov     rcx, rax; this
0x18002af79  call    ?FindPolicy@CAccountManager@@AEAAJPEAU_WINBIO_IDENTITY@@IPEAU_WINBIO_ACCOUNT_POLICY@@@Z; CAccountManager::FindPolicy(_WINBIO_IDENTITY *,uint,_WINBIO_ACCOUNT_POLICY *)
0x18002af7e  mov     esi, eax
0x18002af80  cmp     eax, 80070490h
0x18002af85  jnz     short loc_18002AFAF
0x18002af87  call    ?Instance@CAccountManager@@CAAEAV1@XZ; CAccountManager::Instance(void)
0x18002af8c  xor     esi, esi
0x18002af8e  cmp     ebp, 4
0x18002af91  jz      short loc_18002AFA9
0x18002af93  cmp     ebp, 8
0x18002af96  jz      short loc_18002AFA9
0x18002af98  cmp     ebp, 2
0x18002af9b  jz      short loc_18002AFA9
0x18002af9d  cmp     ebp, 10h
0x18002afa0  jz      short loc_18002AFA9
0x18002afa2  mov     esi, 80070490h
0x18002afa7  jmp     short loc_18002AFAF
0x18002afa9  mov     [rbx+4Ch], esi
0x18002afac  mov     [rbx], r13d
0x18002afaf  test    esi, esi
0x18002afb1  js      short loc_18002AFDC
0x18002afb3  movups  xmm0, xmmword ptr [rdi]
0x18002afb6  movups  xmmword ptr [rbx], xmm0
0x18002afb9  movups  xmm1, xmmword ptr [rdi+10h]
0x18002afbd  movups  xmmword ptr [rbx+10h], xmm1
0x18002afc1  movups  xmm0, xmmword ptr [rdi+20h]
0x18002afc5  movups  xmmword ptr [rbx+20h], xmm0
0x18002afc9  movups  xmm1, xmmword ptr [rdi+30h]
0x18002afcd  movups  xmmword ptr [rbx+30h], xmm1
0x18002afd1  movups  xmm0, xmmword ptr [rdi+3Ch]
0x18002afd5  movups  xmmword ptr [rbx+3Ch], xmm0
0x18002afd9  mov     [r14], r13d
0x18002afdc  test    r15, r15
0x18002afdf  jz      short loc_18002AFEA
0x18002afe1  mov     rcx, r15; SRWLock
0x18002afe4  call    cs:__imp_ReleaseSRWLockShared
0x18002afea  mov     eax, esi
0x18002afec  jmp     short loc_18002AFF3
0x18002afee  mov     eax, 80004003h
0x18002aff3  mov     rcx, [rsp+0C8h+var_48]
0x18002affb  xor     rcx, rsp; StackCookie
0x18002affe  call    __security_check_cookie
0x18002b003  add     rsp, 90h
0x18002b00a  pop     r15
0x18002b00c  pop     r14
0x18002b00e  pop     r13
0x18002b010  pop     rdi
0x18002b011  pop     rsi
0x18002b012  pop     rbp
0x18002b013  pop     rbx
0x18002b014  retn
```
