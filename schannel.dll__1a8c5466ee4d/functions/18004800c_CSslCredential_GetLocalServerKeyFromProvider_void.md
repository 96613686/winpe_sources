# CSslCredential::GetLocalServerKeyFromProvider(void *)

- ea: `0x18004800c`
- end: `0x180048194`
- name: `?GetLocalServerKeyFromProvider@CSslCredential@@AEAAKPEAX@Z`
- size: `392`
- prototype: `unsigned int __fastcall(CSslCredential *__hidden this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b294`
- `0x18007305c`

## callees

- `0x18000ad58`
- `0x180014240`
- `0x180021eb0`
- `0x18004800c`
- `0x18004819c`
- `0x180091010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180048099`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180048099`
- `ntdll!NtSetInformationThread` at `0x180048063`
- `ntdll!NtSetInformationThread` at `0x180048063`
- `ntdll!RtlNtStatusToDosError` at `0x18004806d`
- `ntdll!RtlNtStatusToDosError` at `0x18004806d`
- `ncrypt!SslFreeObject` at `0x180090451`
- `ncrypt!SslFreeObject` at `0x180090451`

## pseudocode

```c
ULONG __fastcall CSslCredential::GetLocalServerKeyFromProvider(const struct _CERT_CONTEXT **this, void *a2)
{
  NTSTATUS v3; // eax
  NTSTATUS v4; // ebx
  ULONG result; // eax
  BOOL v6; // ebx
  unsigned int PrivateKeyFromProvider; // edi
  unsigned int v8; // r14d
  const struct _CERT_CONTEXT *v9; // rax
  struct ProviderToPrivateKey *v10; // r15
  __int64 v11; // rsi
  _QWORD *v12; // rax
  _QWORD *v13; // r9
  __int64 v14; // r8
  unsigned __int64 *v15; // rbx
  CCipherMill *v16; // rcx
  unsigned int v17; // [rsp+58h] [rbp+10h] BYREF
  struct ProviderToPrivateKey *v18; // [rsp+60h] [rbp+18h] BYREF
  void *ThreadInformation; // [rsp+68h] [rbp+20h] BYREF

  v18 = 0;
  v17 = 0;
  ThreadInformation = a2;
  if ( !LsaTable )
  {
    v6 = 0;
LABEL_6:
    PrivateKeyFromProvider = CCipherMill::GetPrivateKeyFromProvider((CCipherMill *)this, this[4], &v18, &v17);
    if ( v6 )
      RevertToSelf();
    if ( PrivateKeyFromProvider )
    {
      *((_DWORD *)this + 18) = 10001;
      return -2146893043;
    }
    v8 = v17;
    v9 = (const struct _CERT_CONTEXT *)SPExternalAlloc(8 * v17);
    v10 = v18;
    v11 = 0;
    this[11] = v9;
    if ( v9 )
    {
      while ( (unsigned int)v11 < v8 )
      {
        v12 = SPExternalAlloc(0x20u);
        v13 = v12;
        if ( v12 )
        {
          v14 = *((_QWORD *)v10 + 2 * (unsigned int)v11);
          v12[1] = *((_QWORD *)v10 + 2 * (unsigned int)v11 + 1);
          v12[2] = v14;
          *v12 = &CSslServerKey::`vftable';
          *((_DWORD *)v12 + 6) = 1;
        }
        else
        {
          v13 = 0;
        }
        *((_QWORD *)&this[11]->dwCertEncodingType + v11) = v13;
        if ( !*((_QWORD *)&this[11]->dwCertEncodingType + v11) )
        {
          PrivateKeyFromProvider = 14;
          break;
        }
        v11 = (unsigned int)(v11 + 1);
      }
      *((_DWORD *)this + 24) = v11;
      if ( !PrivateKeyFromProvider )
        goto LABEL_16;
    }
    else
    {
      PrivateKeyFromProvider = 14;
    }
    while ( v8 > (unsigned int)v11 )
    {
      v15 = (unsigned __int64 *)((char *)v10 + 16 * --v8);
      SslFreeObject(v15[1], 0);
      CCipherMill::DeferenceProvider(v16, v15);
    }
LABEL_16:
    if ( v10 )
      SPExternalFree(v10);
    return PrivateKeyFromProvider;
  }
  if ( a2 )
    v3 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  else
    v3 = (*(__int64 (**)(void))(LsaTable + 88))();
  v4 = v3;
  result = RtlNtStatusToDosError(v3);
  if ( !result )
  {
    v6 = v4 >= 0;
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x18004800c  mov     rax, rsp
0x18004800f  mov     [rax+8], rbx
0x180048013  push    rbp
0x180048014  push    rsi
0x180048015  push    rdi
0x180048016  push    r14
0x180048018  push    r15
0x18004801a  sub     rsp, 20h
0x18004801e  mov     qword ptr [rax+18h], 0
0x180048026  mov     rbp, rcx
0x180048029  mov     dword ptr [rax+10h], 0
0x180048030  mov     [rax+20h], rdx
0x180048034  mov     rax, cs:LsaTable
0x18004803b  test    rax, rax
0x18004803e  jz      loc_18004816A
0x180048044  test    rdx, rdx
0x180048047  jz      loc_180048171
0x18004804d  mov     r9d, 8; ThreadInformationLength
0x180048053  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x180048058  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18004805f  lea     edx, [r9-3]; ThreadInformationClass
0x180048063  call    cs:__imp_NtSetInformationThread
0x180048069  mov     ecx, eax; Status
0x18004806b  mov     ebx, eax
0x18004806d  call    cs:__imp_RtlNtStatusToDosError
0x180048073  test    eax, eax
0x180048075  jnz     loc_18004813A
0x18004807b  not     ebx
0x18004807d  shr     ebx, 1Fh
0x180048080  mov     rdx, [rbp+20h]; struct _CERT_CONTEXT *
0x180048084  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x180048089  lea     r8, [rsp+48h+arg_10]; struct ProviderToPrivateKey **
0x18004808e  call    ?GetPrivateKeyFromProvider@CCipherMill@@QEAAKPEBU_CERT_CONTEXT@@PEAPEAUProviderToPrivateKey@@PEAK@Z; CCipherMill::GetPrivateKeyFromProvider(_CERT_CONTEXT const *,ProviderToPrivateKey * *,ulong *)
0x180048093  mov     edi, eax
0x180048095  test    ebx, ebx
0x180048097  jz      short loc_18004809F
0x180048099  call    cs:__imp_RevertToSelf
0x18004809f  test    edi, edi
0x1800480a1  jnz     loc_18004815C
0x1800480a7  mov     r14d, [rsp+48h+arg_8]
0x1800480ac  lea     ecx, ds:0[r14*8]; uBytes
0x1800480b4  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x1800480b9  mov     r15, [rsp+48h+arg_10]
0x1800480be  xor     esi, esi
0x1800480c0  mov     [rbp+58h], rax
0x1800480c4  test    rax, rax
0x1800480c7  jz      loc_18004817F
0x1800480cd  cmp     esi, r14d
0x1800480d0  jnb     short loc_18004812C
0x1800480d2  mov     ecx, 20h ; ' '; uBytes
0x1800480d7  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x1800480dc  mov     r10d, esi
0x1800480df  mov     r9, rax
0x1800480e2  test    rax, rax
0x1800480e5  jz      loc_18004818F
0x1800480eb  mov     ecx, r10d
0x1800480ee  lea     rax, ??_7CSslServerKey@@6B@; const CSslServerKey::`vftable'
0x1800480f5  add     rcx, rcx
0x1800480f8  mov     rdx, [r15+rcx*8+8]
0x1800480fd  mov     r8, [r15+rcx*8]
0x180048101  mov     [r9+8], rdx
0x180048105  mov     [r9+10h], r8
0x180048109  mov     [r9], rax
0x18004810c  mov     dword ptr [r9+18h], 1
0x180048114  mov     rax, [rbp+58h]
0x180048118  mov     [rax+rsi*8], r9
0x18004811c  mov     rax, [rbp+58h]
0x180048120  cmp     qword ptr [rax+rsi*8], 0
0x180048125  jnz     short loc_18004814B
0x180048127  mov     edi, 0Eh
0x18004812c  mov     [rbp+60h], esi
0x18004812f  test    edi, edi
0x180048131  jnz     short loc_180048184
0x180048133  test    r15, r15
0x180048136  jnz     short loc_180048152
0x180048138  mov     eax, edi
0x18004813a  mov     rbx, [rsp+48h+arg_0]
0x18004813f  add     rsp, 20h
0x180048143  pop     r15
0x180048145  pop     r14
0x180048147  pop     rdi
0x180048148  pop     rsi
0x180048149  pop     rbp
0x18004814a  retn
0x18004814b  inc     esi
0x18004814d  jmp     loc_1800480CD
0x180048152  mov     rcx, r15; void *
0x180048155  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18004815a  jmp     short loc_180048138
0x18004815c  mov     dword ptr [rbp+48h], 2711h
0x180048163  mov     eax, 8009030Dh
0x180048168  jmp     short loc_18004813A
0x18004816a  xor     ebx, ebx
0x18004816c  jmp     loc_180048080
0x180048171  mov     rax, [rax+58h]
0x180048175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004817a  jmp     loc_180048069
0x18004817f  mov     edi, 0Eh
0x180048184  cmp     r14d, esi
0x180048187  ja      loc_18009043E
0x18004818d  jmp     short loc_180048133
0x18004818f  xor     r9d, r9d
0x180048192  jmp     short loc_180048114
0x18009043e  dec     r14d
0x180090441  xor     edx, edx
0x180090443  mov     ebx, r14d
0x180090446  shl     rbx, 4
0x18009044a  add     rbx, r15
0x18009044d  mov     rcx, [rbx+8]
0x180090451  call    cs:__imp_SslFreeObject
0x180090457  mov     rdx, rbx; unsigned __int64 *
0x18009045a  call    ?DeferenceProvider@CCipherMill@@QEAAXPEA_K@Z; CCipherMill::DeferenceProvider(unsigned __int64 *)
0x18009045f  nop
0x180090460  jmp     loc_180048184
```
