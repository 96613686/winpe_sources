# OncRpcSeEstablishOutboundGssContext

- ea: `0x1400090f4`
- end: `0x140009538`
- name: `OncRpcSeEstablishOutboundGssContext`
- size: `1092`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140006d50`

## callees

- `0x1400020c0`
- `0x1400090f4`
- `0x140012838`
- `0x140015640`
- `0x140015840`
- `0x140015b40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140009437`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009437`
- `ntoskrnl!ZwSetInformationThread` at `0x140009282`
- `ntoskrnl!ZwSetInformationThread` at `0x140009498`
- `ntoskrnl!ZwSetInformationThread` at `0x140009282`
- `ntoskrnl!ZwSetInformationThread` at `0x140009498`
- `ntoskrnl!ZwDuplicateToken` at `0x140009347`
- `ntoskrnl!ZwDuplicateToken` at `0x140009347`
- `ntoskrnl!KeReleaseMutex` at `0x14000945f`
- `ntoskrnl!KeReleaseMutex` at `0x14000945f`
- `ntoskrnl!ZwClose` at `0x1400094ae`
- `ntoskrnl!ZwClose` at `0x1400094ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094de`
- `ksecdd!MapSecurityError` at `0x1400093da`
- `ksecdd!MapSecurityError` at `0x1400093da`
- `ksecdd!AcquireCredentialsHandleW` at `0x1400093cc`
- `ksecdd!AcquireCredentialsHandleW` at `0x1400093cc`

## pseudocode

```c
__int64 __fastcall OncRpcSeEstablishOutboundGssContext(
        __int64 a1,
        void **a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  char *v5; // rsi
  char v6; // bl
  unsigned int v9; // r14d
  int v10; // eax
  NTSTATUS v11; // edi
  unsigned __int16 *dwLower; // rdx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rbx
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  void *v19; // rcx
  SECURITY_STATUS v20; // eax
  struct _SecHandle v21; // xmm0
  void *v22; // rax
  __int64 v23; // rcx
  _BYTE *v24; // rax
  char v26; // [rsp+50h] [rbp-61h]
  void *pAuthData; // [rsp+58h] [rbp-59h] BYREF
  __int64 ThreadInformation; // [rsp+60h] [rbp-51h] BYREF
  UNICODE_STRING pPackage; // [rsp+68h] [rbp-49h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-39h] BYREF
  struct _SecHandle phCredential; // [rsp+A8h] [rbp-9h] BYREF

  v5 = 0;
  v6 = 0;
  phCredential.dwLower = (ULONG_PTR)a3;
  pAuthData = 0;
  ThreadInformation = -1;
  v26 = 0;
  *(_QWORD *)&pPackage.Length = 1179664;
  pPackage.Buffer = L"Kerberos";
  if ( a3 && a4 && a5 )
  {
    v9 = *a4 + *a3 + *a5 + 78;
    v10 = NfsMemMgrBufferAllocate(512, 1347241300, v9, &pAuthData);
    v5 = (char *)pAuthData;
    v11 = v10;
    if ( v10 < 0 )
      goto LABEL_27;
    memset(pAuthData, 0, v9);
    dwLower = (unsigned __int16 *)phCredential.dwLower;
    *(_DWORD *)v5 = 512;
    *((_DWORD *)v5 + 1) = 72;
    *((_DWORD *)v5 + 13) = 6;
    *((_QWORD *)v5 + 3) = v5 + 72;
    *((_DWORD *)v5 + 8) = *dwLower >> 1;
    memmove(*((void **)v5 + 3), *((const void **)dwLower + 1), *dwLower);
    v13 = *((unsigned int *)v5 + 8);
    *(_WORD *)&v5[2 * v13 + 72] = 0;
    v14 = (__int64)&v5[2 * v13 + 74];
    *((_QWORD *)v5 + 1) = v14;
    *((_DWORD *)v5 + 4) = *a4 >> 1;
    memmove(*((void **)v5 + 1), *((const void **)a4 + 1), *a4);
    v15 = *((unsigned int *)v5 + 4);
    *(_WORD *)(v14 + 2 * v15) = 0;
    v16 = v14 + 2 * v15 + 2;
    *((_QWORD *)v5 + 5) = v16;
    *((_DWORD *)v5 + 12) = *a5 >> 1;
    memmove(*((void **)v5 + 5), *((const void **)a5 + 1), *a5);
    *(_WORD *)(v16 + 2LL * *((unsigned int *)v5 + 12)) = 0;
    v6 = 0;
    goto LABEL_6;
  }
  v9 = 0;
  if ( !a2 )
    goto LABEL_19;
  v19 = *a2;
  ObjectAttributes.SecurityQualityOfService = &phCredential;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  LODWORD(phCredential.dwUpper) = 1;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  ObjectAttributes.SecurityDescriptor = 0;
  phCredential.dwLower = 0x20000000CLL;
  v11 = ZwDuplicateToken(v19, 4u, &ObjectAttributes, 0, TokenImpersonation, (PHANDLE)&ThreadInformation);
  if ( v11 >= 0 )
  {
LABEL_6:
    if ( ThreadInformation != -1 )
    {
      v11 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      if ( v11 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          v18 = 70;
LABEL_11:
          WPP_SF_d(v17->AttachedDevice, v18, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v11);
          goto LABEL_27;
        }
        goto LABEL_27;
      }
      v6 = 1;
      v26 = 1;
    }
LABEL_19:
    pAuthData = 0;
    phCredential = 0;
    v20 = AcquireCredentialsHandleW(
            0,
            &pPackage,
            2u,
            (void *)(a1 + 184),
            v5,
            0,
            0,
            &phCredential,
            (PTimeStamp)&pAuthData);
    v11 = MapSecurityError(v20);
    if ( v11 >= 0 )
    {
      KeWaitForSingleObject((PVOID)(a1 + 128), Executive, 0, 0, 0);
      v21 = phCredential;
      v22 = pAuthData;
      *(_DWORD *)(a1 + 60) |= 1u;
      *(struct _SecHandle *)(a1 + 80) = v21;
      *(_QWORD *)(a1 + 112) = v22;
      KeReleaseMutex((PRKMUTEX)(a1 + 128), 0);
      v6 = v26;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        71,
        WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
        (unsigned int)v11);
    }
    if ( v6 )
    {
      phCredential.dwLower = 0;
      if ( ThreadInformation )
        ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &phCredential, 8u);
    }
    goto LABEL_27;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    v18 = 69;
    goto LABEL_11;
  }
LABEL_27:
  if ( ThreadInformation != -1 )
    ZwClose((HANDLE)ThreadInformation);
  if ( v5 )
  {
    v23 = v9;
    v24 = v5;
    if ( v9 )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    ExFreePoolWithTag(v5, 0x504D4554u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400090f4  push    rbp
0x1400090f6  push    rbx
0x1400090f7  push    rsi
0x1400090f8  push    rdi
0x1400090f9  push    r12
0x1400090fb  push    r13
0x1400090fd  push    r14
0x1400090ff  push    r15
0x140009101  lea     rbp, [rsp-17h]
0x140009106  sub     rsp, 0C8h
0x14000910d  mov     rax, cs:__security_cookie
0x140009114  xor     rax, rsp
0x140009117  mov     [rbp+4Fh+var_48], rax
0x14000911b  mov     r12, [rbp+4Fh+arg_20]
0x14000911f  xor     esi, esi
0x140009121  xor     bl, bl
0x140009123  mov     [rbp+4Fh+var_58.dwLower], r8
0x140009127  mov     [rbp+4Fh+pAuthData], rsi
0x14000912b  mov     r15, rcx
0x14000912e  mov     [rbp+4Fh+ThreadInformation], 0FFFFFFFFFFFFFFFFh
0x140009136  lea     rcx, aKerberos; "Kerberos"
0x14000913d  mov     [rbp+4Fh+var_B0], bl
0x140009140  mov     r13, r9
0x140009143  mov     qword ptr [rbp+4Fh+pPackage.Length], 120010h
0x14000914b  lea     r9d, [rsi+2]
0x14000914f  mov     [rbp+4Fh+pPackage.Buffer], rcx
0x140009153  mov     r10, rdx
0x140009156  test    r8, r8
0x140009159  jz      loc_1400092E6
0x14000915f  test    r13, r13
0x140009162  jz      loc_1400092E6
0x140009168  test    r12, r12
0x14000916b  jz      loc_1400092E6
0x140009171  movzx   ecx, word ptr [r8]
0x140009175  lea     r9, [rbp+4Fh+pAuthData]
0x140009179  movzx   eax, word ptr [r13+0]
0x14000917e  mov     edx, 504D4554h
0x140009183  movzx   r14d, word ptr [r12]
0x140009188  add     ecx, eax
0x14000918a  add     r14d, 4Eh ; 'N'
0x14000918e  add     r14d, ecx
0x140009191  mov     ecx, 200h
0x140009196  mov     r8d, r14d
0x140009199  call    NfsMemMgrBufferAllocate
0x14000919e  mov     rsi, [rbp+4Fh+pAuthData]
0x1400091a2  mov     edi, eax
0x1400091a4  test    eax, eax
0x1400091a6  js      loc_1400092D7
0x1400091ac  mov     r8d, r14d; Size
0x1400091af  xor     edx, edx; Val
0x1400091b1  mov     rcx, rsi; void *
0x1400091b4  call    memset
0x1400091b9  mov     rdx, [rbp+4Fh+var_58.dwLower]
0x1400091bd  lea     rbx, [rsi+48h]
0x1400091c1  mov     dword ptr [rsi], 200h
0x1400091c7  mov     dword ptr [rsi+4], 48h ; 'H'
0x1400091ce  mov     dword ptr [rsi+34h], 6
0x1400091d5  mov     [rsi+18h], rbx
0x1400091d9  movzx   eax, word ptr [rdx]
0x1400091dc  shr     eax, 1
0x1400091de  mov     [rsi+20h], eax
0x1400091e1  movzx   r8d, word ptr [rdx]; Size
0x1400091e5  mov     rdx, [rdx+8]; Src
0x1400091e9  mov     rcx, [rsi+18h]; void *
0x1400091ed  call    memmove
0x1400091f2  mov     ecx, [rsi+20h]
0x1400091f5  xor     eax, eax
0x1400091f7  mov     [rbx+rcx*2], ax
0x1400091fb  lea     rbx, [rbx+rcx*2]
0x1400091ff  add     rbx, 2
0x140009203  mov     [rsi+8], rbx
0x140009207  movzx   eax, word ptr [r13+0]
0x14000920c  shr     eax, 1
0x14000920e  mov     [rsi+10h], eax
0x140009211  movzx   r8d, word ptr [r13+0]; Size
0x140009216  mov     rdx, [r13+8]; Src
0x14000921a  mov     rcx, [rsi+8]; void *
0x14000921e  call    memmove
0x140009223  mov     ecx, [rsi+10h]
0x140009226  xor     r13d, r13d
0x140009229  mov     [rbx+rcx*2], r13w
0x14000922e  lea     rbx, [rbx+rcx*2]
0x140009232  add     rbx, 2
0x140009236  mov     [rsi+28h], rbx
0x14000923a  movzx   eax, word ptr [r12]
0x14000923f  shr     eax, 1
0x140009241  mov     [rsi+30h], eax
0x140009244  movzx   r8d, word ptr [r12]; Size
0x140009249  mov     rdx, [r12+8]; Src
0x14000924e  mov     rcx, [rsi+28h]; void *
0x140009252  call    memmove
0x140009257  mov     ecx, [rsi+30h]
0x14000925a  mov     [rbx+rcx*2], r13w
0x14000925f  mov     bl, r13b
0x140009262  cmp     [rbp+4Fh+ThreadInformation], 0FFFFFFFFFFFFFFFFh
0x140009267  jz      loc_14000938D
0x14000926d  mov     r9d, 8; ThreadInformationLength
0x140009273  lea     r8, [rbp+4Fh+ThreadInformation]; ThreadInformation
0x140009277  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14000927e  lea     edx, [r9-3]; ThreadInformationClass
0x140009282  call    cs:__imp_ZwSetInformationThread
0x140009289  nop     dword ptr [rax+rax+00h]
0x14000928e  mov     edi, eax
0x140009290  test    eax, eax
0x140009292  jns     loc_140009388
0x140009298  mov     rcx, cs:WPP_GLOBAL_Control
0x14000929f  lea     r15, WPP_GLOBAL_Control
0x1400092a6  cmp     rcx, r15
0x1400092a9  jz      loc_1400094A4
0x1400092af  mov     eax, [rcx+2Ch]
0x1400092b2  test    al, 40h
0x1400092b4  jz      loc_1400094A4
0x1400092ba  mov     edx, 46h ; 'F'
0x1400092bf  mov     rcx, [rcx+18h]
0x1400092c3  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x1400092ca  mov     r9d, edi
0x1400092cd  call    WPP_SF_d
0x1400092d2  jmp     loc_1400094A4
0x1400092d7  xor     r13d, r13d
0x1400092da  lea     r15, WPP_GLOBAL_Control
0x1400092e1  jmp     loc_1400094A4
0x1400092e6  xor     r13d, r13d
0x1400092e9  mov     r14d, r13d
0x1400092ec  test    r10, r10
0x1400092ef  jz      loc_14000938D
0x1400092f5  mov     rcx, [r10]; ExistingTokenHandle
0x1400092f8  lea     rax, [rbp+4Fh+var_58]
0x1400092fc  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], rax
0x140009300  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x140009304  lea     rax, [rbp+4Fh+ThreadInformation]
0x140009308  mov     dword ptr [rbp+4Fh+var_58.dwLower+4], r9d
0x14000930c  mov     [rsp+100h+NewTokenHandle], rax; NewTokenHandle
0x140009311  lea     edx, [r13+4]; DesiredAccess
0x140009315  mov     [rsp+100h+TokenType], r9d; TokenType
0x14000931a  xor     r9d, r9d; EffectiveOnly
0x14000931d  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x140009325  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x14000932d  mov     dword ptr [rbp+4Fh+var_58.dwUpper], 1
0x140009334  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r13
0x140009338  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r13
0x14000933c  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], r13
0x140009340  mov     dword ptr [rbp+4Fh+var_58.dwLower], 0Ch
0x140009347  call    cs:__imp_ZwDuplicateToken
0x14000934e  nop     dword ptr [rax+rax+00h]
0x140009353  mov     edi, eax
0x140009355  test    eax, eax
0x140009357  jns     loc_140009262
0x14000935d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009364  lea     r15, WPP_GLOBAL_Control
0x14000936b  cmp     rcx, r15
0x14000936e  jz      loc_1400094A4
0x140009374  mov     eax, [rcx+2Ch]
0x140009377  test    al, 40h
0x140009379  jz      loc_1400094A4
0x14000937f  lea     edx, [r13+45h]
0x140009383  jmp     loc_1400092BF
0x140009388  mov     bl, 1
0x14000938a  mov     [rbp+4Fh+var_B0], bl
0x14000938d  lea     rax, [rbp+4Fh+pAuthData]
0x140009391  mov     [rbp+4Fh+pAuthData], r13
0x140009395  mov     [rsp+100h+ptsExpiry], rax; ptsExpiry
0x14000939a  lea     r9, [r15+0B8h]; pvLogonId
0x1400093a1  lea     rax, [rbp+4Fh+var_58]
0x1400093a5  xorps   xmm0, xmm0
0x1400093a8  mov     [rsp+100h+phCredential], rax; phCredential
0x1400093ad  lea     rdx, [rbp+4Fh+pPackage]; pPackage
0x1400093b1  mov     [rsp+100h+pvGetKeyArgument], r13; pvGetKeyArgument
0x1400093b6  mov     r8d, 2; fCredentialUse
0x1400093bc  mov     [rsp+100h+NewTokenHandle], r13; pGetKeyFn
0x1400093c1  xor     ecx, ecx; pPrincipal
0x1400093c3  mov     qword ptr [rsp+100h+TokenType], rsi; pAuthData
0x1400093c8  movups  xmmword ptr [rbp+4Fh+var_58.dwLower], xmm0
0x1400093cc  call    cs:__imp_AcquireCredentialsHandleW
0x1400093d3  nop     dword ptr [rax+rax+00h]
0x1400093d8  mov     ecx, eax; SecStatus
0x1400093da  call    cs:__imp_MapSecurityError
0x1400093e1  nop     dword ptr [rax+rax+00h]
0x1400093e6  mov     edi, eax
0x1400093e8  test    eax, eax
0x1400093ea  jns     short loc_140009420
0x1400093ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400093f3  lea     r15, WPP_GLOBAL_Control
0x1400093fa  cmp     rcx, r15
0x1400093fd  jz      short loc_140009475
0x1400093ff  mov     eax, [rcx+2Ch]
0x140009402  test    al, 40h
0x140009404  jz      short loc_140009475
0x140009406  mov     rcx, [rcx+18h]
0x14000940a  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140009411  mov     edx, 47h ; 'G'
0x140009416  mov     r9d, edi
0x140009419  call    WPP_SF_d
0x14000941e  jmp     short loc_140009475
0x140009420  lea     rbx, [r15+80h]
0x140009427  mov     qword ptr [rsp+100h+TokenType], r13; Timeout
0x14000942c  mov     rcx, rbx; Object
0x14000942f  xor     r9d, r9d; Alertable
0x140009432  xor     r8d, r8d; WaitMode
0x140009435  xor     edx, edx; WaitReason
0x140009437  call    cs:__imp_KeWaitForSingleObject
0x14000943e  nop     dword ptr [rax+rax+00h]
0x140009443  movups  xmm0, xmmword ptr [rbp+4Fh+var_58.dwLower]
0x140009447  mov     rax, [rbp+4Fh+pAuthData]
0x14000944b  xor     edx, edx; Wait
0x14000944d  or      dword ptr [r15+3Ch], 1
0x140009452  mov     rcx, rbx; Mutex
0x140009455  movdqu  xmmword ptr [r15+50h], xmm0
0x14000945b  mov     [r15+70h], rax
0x14000945f  call    cs:__imp_KeReleaseMutex
0x140009466  nop     dword ptr [rax+rax+00h]
0x14000946b  mov     bl, [rbp+4Fh+var_B0]
0x14000946e  lea     r15, WPP_GLOBAL_Control
0x140009475  test    bl, bl
0x140009477  jz      short loc_1400094A4
0x140009479  mov     [rbp+4Fh+var_58.dwLower], r13
0x14000947d  cmp     [rbp+4Fh+ThreadInformation], r13
0x140009481  jz      short loc_1400094A4
0x140009483  mov     r9d, 8; ThreadInformationLength
0x140009489  lea     r8, [rbp+4Fh+var_58]; ThreadInformation
0x14000948d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140009494  lea     edx, [r9-3]; ThreadInformationClass
0x140009498  call    cs:__imp_ZwSetInformationThread
0x14000949f  nop     dword ptr [rax+rax+00h]
0x1400094a4  mov     rcx, [rbp+4Fh+ThreadInformation]; Handle
0x1400094a8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400094ac  jz      short loc_1400094BA
0x1400094ae  call    cs:__imp_ZwClose
0x1400094b5  nop     dword ptr [rax+rax+00h]
0x1400094ba  test    rsi, rsi
0x1400094bd  jz      short loc_1400094EA
0x1400094bf  mov     ecx, r14d
0x1400094c2  mov     rax, rsi
0x1400094c5  test    r14d, r14d
0x1400094c8  jz      short loc_1400094D6
0x1400094ca  mov     [rax], r13b
0x1400094cd  inc     rax
0x1400094d0  sub     rcx, 1
0x1400094d4  jnz     short loc_1400094CA
0x1400094d6  mov     edx, 504D4554h; Tag
0x1400094db  mov     rcx, rsi; P
0x1400094de  call    cs:__imp_ExFreePoolWithTag
0x1400094e5  nop     dword ptr [rax+rax+00h]
0x1400094ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400094f1  cmp     rcx, r15
0x1400094f4  jz      short loc_140009515
0x1400094f6  mov     eax, [rcx+2Ch]
0x1400094f9  test    al, 1
0x1400094fb  jz      short loc_140009515
0x1400094fd  mov     rcx, [rcx+18h]
0x140009501  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140009508  mov     edx, 48h ; 'H'
0x14000950d  mov     r9d, edi
0x140009510  call    WPP_SF_d
0x140009515  mov     eax, edi
0x140009517  mov     rcx, [rbp+4Fh+var_48]
0x14000951b  xor     rcx, rsp; StackCookie
0x14000951e  call    __security_check_cookie
0x140009523  add     rsp, 0C8h
0x14000952a  pop     r15
0x14000952c  pop     r14
0x14000952e  pop     r13
0x140009530  pop     r12
0x140009532  pop     rdi
0x140009533  pop     rsi
0x140009534  pop     rbx
0x140009535  pop     rbp
0x140009536  retn
```
