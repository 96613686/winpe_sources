# CLogonEnumUsers::remove(tagVARIANT,tagVARIANT,short *)

- ea: `0x1800343b0`
- end: `0x1800345f0`
- name: `?remove@CLogonEnumUsers@@UEAAJUtagVARIANT@@0PEAF@Z`
- size: `576`
- prototype: `__int64 __fastcall(CLogonEnumUsers *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *__struct_ptr, __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180003614`
- `0x180032374`
- `0x180032ac4`
- `0x180032c64`
- `0x1800332b0`
- `0x1800343b0`
- `0x180063880`
- `0x1800639c0`
- `0x180063a50`
- `0x180078010`

## import_xrefs

- `SHELL32!__imp_IsUserAnAdmin` at `0x1800343db`
- `SHELL32!__imp_IsUserAnAdmin` at `0x1800343db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003456a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003456a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003450e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003450e`
- `OLEAUT32!__imp_VariantClear` at `0x18003459f`
- `OLEAUT32!__imp_VariantClear` at `0x1800345a9`
- `OLEAUT32!__imp_VariantClear` at `0x18003459f`
- `OLEAUT32!__imp_VariantClear` at `0x1800345a9`
- `samcli!NetUserDel` at `0x1800344e1`
- `samcli!NetUserDel` at `0x1800344e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800344b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800344b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003449c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003449c`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x1800345c8`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x1800345c8`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalRemoveCredential` at `0x1800344cb`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalRemoveCredential` at `0x1800344cb`
- `ext-ms-win-advapi32-lsa-l1-1-3!LsaProfileDeleted` at `0x1800344d5`
- `ext-ms-win-advapi32-lsa-l1-1-3!LsaProfileDeleted` at `0x1800344d5`

## pseudocode

```c
// AFR coverage: remove path gates on IsUserAnAdmin before NetUserDel/DeleteUserData.
__int64 __fastcall CLogonEnumUsers::remove(
        CLogonEnumUsers *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        __int16 *a4)
{
  __int128 v8; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 (__fastcall *v10)(CLogonEnumUsers *, VARIANTARG *, void **); // rax
  signed int LogonUserSetting; // ebx
  signed int v12; // eax
  int PtrIndex; // esi
  struct _DPA *v14; // rcx
  BSTR bstrVal; // r9
  PSID Sid; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG StringSid; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG username; // [rsp+40h] [rbp-20h] BYREF
  void *p; // [rsp+A8h] [rbp+48h] BYREF

  *a4 = 0;
  if ( IsUserAnAdmin() )
  {
    v8 = *(_OWORD *)&a2->vt;
    pRecInfo = a2->pRecInfo;
    v10 = *(__int64 (__fastcall **)(CLogonEnumUsers *, VARIANTARG *, void **))(*(_QWORD *)this + 48LL);
    p = 0;
    *(_OWORD *)&username.vt = v8;
    username.pRecInfo = pRecInfo;
    LogonUserSetting = v10(this, &username, &p);
    if ( LogonUserSetting >= 0 )
    {
      memset(&username, 0, sizeof(username));
      LogonUserSetting = GetLogonUserSetting(p, L"LoginName", &username);
      if ( LogonUserSetting >= 0 )
      {
        memset(&StringSid, 0, sizeof(StringSid));
        LogonUserSetting = GetLogonUserSetting(p, L"SID", &StringSid);
        if ( LogonUserSetting >= 0 )
        {
          LogonUserSetting = DeleteUserGroupMemberships(StringSid.llVal);
          if ( LogonUserSetting >= 0 )
          {
            Sid = 0;
            if ( ConvertStringSidToSidW(StringSid.bstrVal, &Sid) )
            {
              BiometricHelpers::RemovePii(Sid);
              LocalFree(Sid);
            }
            if ( (unsigned __int8)IsNgcLocalRemoveCredentialPresent() )
              NgcLocalRemoveCredential(StringSid.llVal, 3);
            LsaProfileDeleted(StringSid.llVal);
            v12 = NetUserDel(0, username.bstrVal);
            LogonUserSetting = v12;
            if ( !v12 || v12 == 2221 )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
              PtrIndex = g_pfn_DPA_GetPtrIndex(*((HDPA *)this + 5), p);
              if ( PtrIndex == -1 )
              {
                v14 = (struct _DPA *)_InterlockedExchange64((volatile __int64 *)this + 5, 0);
                if ( v14 )
                  g_pfn_DPA_DestroyCallback(v14, ReleaseLogonUserCallback, 0);
              }
              else
              {
                (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
                g_pfn_DPA_DeletePtr(*((HDPA *)this + 5), PtrIndex);
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
              if ( a3->vt == 8 )
                bstrVal = a3->bstrVal;
              else
                bstrVal = 0;
              DeleteUserData((__int64)p, username.llVal, StringSid.bstrVal, bstrVal);
              LogonUserSetting = 0;
              *a4 = -1;
            }
            else if ( v12 > 0 )
            {
              LogonUserSetting = (unsigned __int16)v12 | 0x80070000;
            }
          }
          VariantClear(&StringSid);
        }
        VariantClear(&username);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
      if ( LogonUserSetting >= 0 )
        SHGlobalCounterIncrement(GLOBALCOUNTER_INTERNETTOOLBAR_LAYOUT|GLOBALCOUNTER_OVERLAYMANAGER);
    }
  }
  else
  {
    return (unsigned int)-2147024891;
  }
  return (unsigned int)LogonUserSetting;
}

```

## disassembly

```asm
0x1800343b0  mov     [rsp-28h+arg_0], rbx; AFR coverage: remove path gates on IsUserAnAdmin before NetUserDel/DeleteUserData.
0x1800343b5  mov     [rsp-28h+arg_8], rsi
0x1800343ba  push    rbp
0x1800343bb  push    rdi
0x1800343bc  push    r12
0x1800343be  push    r14
0x1800343c0  push    r15
0x1800343c2  mov     rbp, rsp
0x1800343c5  sub     rsp, 60h
0x1800343c9  xor     eax, eax
0x1800343cb  mov     r15, r9
0x1800343ce  mov     [r9], ax
0x1800343d2  mov     r14, r8
0x1800343d5  mov     rbx, rdx
0x1800343d8  mov     rdi, rcx
0x1800343db  call    cs:__imp_IsUserAnAdmin
0x1800343e1  test    eax, eax
0x1800343e3  jz      loc_1800345D0
0x1800343e9  mov     rax, [rdi]
0x1800343ec  lea     r8, [rbp+p]
0x1800343f0  movups  xmm0, xmmword ptr [rbx]
0x1800343f3  lea     rdx, [rbp+username]
0x1800343f7  mov     rcx, rdi
0x1800343fa  movsd   xmm1, qword ptr [rbx+10h]
0x1800343ff  mov     rax, [rax+30h]
0x180034403  mov     [rbp+p], 0
0x18003440b  movaps  xmmword ptr [rbp+username], xmm0
0x18003440f  movsd   [rbp+var_10], xmm1
0x180034414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034419  mov     ebx, eax
0x18003441b  test    eax, eax
0x18003441d  js      loc_1800345D5
0x180034423  mov     rcx, [rbp+p]
0x180034427  lea     r8, [rbp+username]
0x18003442b  xorps   xmm0, xmm0
0x18003442e  lea     rdx, aLoginname_0; "LoginName"
0x180034435  xor     eax, eax
0x180034437  movups  xmmword ptr [rbp+username], xmm0
0x18003443b  mov     [rbp+var_10], rax
0x18003443f  call    _GetLogonUserSetting
0x180034444  mov     ebx, eax
0x180034446  test    eax, eax
0x180034448  js      loc_1800345AF
0x18003444e  mov     rcx, [rbp+p]
0x180034452  lea     r8, [rbp+StringSid]
0x180034456  xorps   xmm0, xmm0
0x180034459  lea     rdx, aSid_0; "SID"
0x180034460  xor     eax, eax
0x180034462  movups  xmmword ptr [rbp+StringSid], xmm0
0x180034466  mov     [rbp+var_28], rax
0x18003446a  call    _GetLogonUserSetting
0x18003446f  mov     ebx, eax
0x180034471  test    eax, eax
0x180034473  js      loc_1800345A5
0x180034479  mov     rcx, [rbp+StringSid+8]
0x18003447d  call    _DeleteUserGroupMemberships
0x180034482  mov     ebx, eax
0x180034484  test    eax, eax
0x180034486  js      loc_18003459B
0x18003448c  mov     rcx, [rbp+StringSid+8]; StringSid
0x180034490  lea     rdx, [rbp+Sid]; Sid
0x180034494  mov     [rbp+Sid], 0
0x18003449c  call    cs:__imp_ConvertStringSidToSidW
0x1800344a2  test    eax, eax
0x1800344a4  jz      short loc_1800344B9
0x1800344a6  mov     rcx, [rbp+Sid]; void *
0x1800344aa  call    ?RemovePii@BiometricHelpers@@SAXPEAX@Z; BiometricHelpers::RemovePii(void *)
0x1800344af  mov     rcx, [rbp+Sid]; hMem
0x1800344b3  call    cs:__imp_LocalFree
0x1800344b9  call    IsNgcLocalRemoveCredentialPresent
0x1800344be  test    al, al
0x1800344c0  jz      short loc_1800344D1
0x1800344c2  mov     rcx, [rbp+StringSid+8]
0x1800344c6  mov     edx, 3
0x1800344cb  call    cs:__imp_NgcLocalRemoveCredential
0x1800344d1  mov     rcx, [rbp+StringSid+8]
0x1800344d5  call    cs:__imp_LsaProfileDeleted
0x1800344db  mov     rdx, [rbp+username+8]; username
0x1800344df  xor     ecx, ecx; servername
0x1800344e1  call    cs:__imp_NetUserDel
0x1800344e7  mov     ebx, eax
0x1800344e9  test    eax, eax
0x1800344eb  jz      short loc_18003450A
0x1800344ed  cmp     eax, 8ADh
0x1800344f2  jz      short loc_18003450A
0x1800344f4  test    eax, eax
0x1800344f6  jle     loc_18003459B
0x1800344fc  movzx   ebx, ax
0x1800344ff  or      ebx, 80070000h
0x180034505  jmp     loc_18003459B
0x18003450a  lea     rcx, [rdi+30h]; lpCriticalSection
0x18003450e  call    cs:__imp_EnterCriticalSection
0x180034514  mov     rdx, [rbp+p]; p
0x180034518  mov     rcx, [rdi+28h]; hdpa
0x18003451c  call    cs:g_pfn_DPA_GetPtrIndex
0x180034522  or      r12d, 0FFFFFFFFh
0x180034526  mov     esi, eax
0x180034528  cmp     eax, r12d
0x18003452b  jz      short loc_18003454B
0x18003452d  mov     rcx, [rbp+p]
0x180034531  mov     rdx, [rcx]
0x180034534  mov     rax, [rdx+10h]
0x180034538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003453d  mov     rcx, [rdi+28h]; hdpa
0x180034541  mov     edx, esi; i
0x180034543  call    cs:g_pfn_DPA_DeletePtr
0x180034549  jmp     short loc_180034566
0x18003454b  xor     ecx, ecx
0x18003454d  xchg    rcx, [rdi+28h]; hdpa
0x180034551  test    rcx, rcx
0x180034554  jz      short loc_180034566
0x180034556  xor     r8d, r8d; pData
0x180034559  lea     rdx, ReleaseLogonUserCallback; pfnCB
0x180034560  call    cs:g_pfn_DPA_DestroyCallback
0x180034566  lea     rcx, [rdi+30h]; lpCriticalSection
0x18003456a  call    cs:__imp_LeaveCriticalSection
0x180034570  mov     eax, 8
0x180034575  cmp     ax, [r14]
0x180034579  jnz     short loc_180034581
0x18003457b  mov     r9, [r14+8]
0x18003457f  jmp     short loc_180034584
0x180034581  xor     r9d, r9d
0x180034584  mov     r8, [rbp+StringSid+8]
0x180034588  mov     rdx, [rbp+username+8]
0x18003458c  mov     rcx, [rbp+p]
0x180034590  call    _DeleteUserData
0x180034595  xor     ebx, ebx
0x180034597  mov     [r15], r12w
0x18003459b  lea     rcx, [rbp+StringSid]; pvarg
0x18003459f  call    cs:__imp_VariantClear
0x1800345a5  lea     rcx, [rbp+username]; pvarg
0x1800345a9  call    cs:__imp_VariantClear
0x1800345af  mov     rcx, [rbp+p]
0x1800345b3  mov     rax, [rcx]
0x1800345b6  mov     rax, [rax+10h]
0x1800345ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800345bf  test    ebx, ebx
0x1800345c1  js      short loc_1800345D5
0x1800345c3  mov     ecx, 38h ; '8'; id
0x1800345c8  call    cs:__imp_SHGlobalCounterIncrement
0x1800345ce  jmp     short loc_1800345D5
0x1800345d0  mov     ebx, 80070005h
0x1800345d5  lea     r11, [rsp+60h+var_s0]
0x1800345da  mov     eax, ebx
0x1800345dc  mov     rbx, [r11+30h]
0x1800345e0  mov     rsi, [r11+38h]
0x1800345e4  mov     rsp, r11
0x1800345e7  pop     r15
0x1800345e9  pop     r14
0x1800345eb  pop     r12
0x1800345ed  pop     rdi
0x1800345ee  pop     rbp
0x1800345ef  retn
```
