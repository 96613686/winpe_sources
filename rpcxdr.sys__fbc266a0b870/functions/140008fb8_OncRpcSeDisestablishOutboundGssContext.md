# OncRpcSeDisestablishOutboundGssContext

- ea: `0x140008fb8`
- end: `0x1400090ed`
- name: `OncRpcSeDisestablishOutboundGssContext`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006cc0`

## callees

- `0x140008fb8`
- `0x140015640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140009007`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000907a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009007`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000907a`
- `ntoskrnl!KeReleaseMutex` at `0x14000908e`
- `ntoskrnl!KeReleaseMutex` at `0x14000908e`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000905a`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000905a`
- `ksecdd!FreeCredentialsHandle` at `0x1400090be`
- `ksecdd!FreeCredentialsHandle` at `0x1400090be`
- `ksecdd!DeleteSecurityContext` at `0x1400090a8`
- `ksecdd!DeleteSecurityContext` at `0x1400090a8`

## pseudocode

```c
SECURITY_STATUS __fastcall OncRpcSeDisestablishOutboundGssContext(__int64 a1)
{
  struct _KMUTANT *v1; // rbp
  int v3; // eax
  _SecHandle v4; // xmm0
  struct _SecHandle v5; // xmm1
  bool v6; // si
  char v7; // r14
  int v8; // ebx
  SECURITY_STATUS result; // eax
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp-48h] BYREF
  _SecHandle phContext; // [rsp+38h] [rbp-40h] BYREF
  struct _SecHandle phCredential; // [rsp+48h] [rbp-30h] BYREF

  v1 = (struct _KMUTANT *)(a1 + 128);
  phCredential = 0;
  phContext = 0;
  KeWaitForSingleObject((PVOID)(a1 + 128), Executive, 0, 0, 0);
  v3 = *(_DWORD *)(a1 + 60);
  v4 = *(_SecHandle *)(a1 + 96);
  v5 = *(struct _SecHandle *)(a1 + 80);
  v6 = (v3 & 2) != 0;
  *(_DWORD *)(a1 + 64) = 0;
  v7 = v3 & 1;
  *(_DWORD *)(a1 + 60) = v3 & 0xFFFFFFFC;
  phContext = v4;
  phCredential = v5;
  while ( 1 )
  {
    v8 = *(_DWORD *)(a1 + 4);
    result = KeReleaseMutex(v1, 0);
    if ( !v8 )
      break;
    Interval.QuadPart = 1000000;
    KeDelayExecutionThread(0, 0, &Interval);
    KeWaitForSingleObject(v1, Executive, 0, 0, 0);
  }
  if ( v6 )
    result = DeleteSecurityContext(&phContext);
  if ( v7 )
    return FreeCredentialsHandle(&phCredential);
  return result;
}

```

## disassembly

```asm
0x140008fb8  mov     [rsp+arg_8], rbx
0x140008fbd  mov     [rsp+arg_10], rbp
0x140008fc2  push    rsi
0x140008fc3  push    rdi
0x140008fc4  push    r14
0x140008fc6  sub     rsp, 60h
0x140008fca  mov     rax, cs:__security_cookie
0x140008fd1  xor     rax, rsp
0x140008fd4  mov     [rsp+78h+var_20], rax
0x140008fd9  lea     rbp, [rcx+80h]
0x140008fe0  mov     [rsp+78h+Timeout], 0; Timeout
0x140008fe9  mov     rdi, rcx
0x140008fec  xorps   xmm0, xmm0
0x140008fef  xorps   xmm1, xmm1
0x140008ff2  mov     rcx, rbp; Object
0x140008ff5  xor     r9d, r9d; Alertable
0x140008ff8  xor     r8d, r8d; WaitMode
0x140008ffb  xor     edx, edx; WaitReason
0x140008ffd  movups  xmmword ptr [rsp+78h+phCredential.dwLower], xmm0
0x140009002  movups  xmmword ptr [rsp+78h+phContext.dwLower], xmm1
0x140009007  call    cs:__imp_KeWaitForSingleObject
0x14000900e  nop     dword ptr [rax+rax+00h]
0x140009013  mov     eax, [rdi+3Ch]
0x140009016  mov     esi, eax
0x140009018  movups  xmm0, xmmword ptr [rdi+60h]
0x14000901c  shr     esi, 1
0x14000901e  mov     r14b, al
0x140009021  movups  xmm1, xmmword ptr [rdi+50h]
0x140009025  and     sil, 1
0x140009029  mov     dword ptr [rdi+40h], 0
0x140009030  and     r14b, 1
0x140009034  and     eax, 0FFFFFFFCh
0x140009037  mov     [rdi+3Ch], eax
0x14000903a  movdqu  xmmword ptr [rsp+78h+phContext.dwLower], xmm0
0x140009040  movdqu  xmmword ptr [rsp+78h+phCredential.dwLower], xmm1
0x140009046  jmp     short loc_140009086
0x140009048  lea     r8, [rsp+78h+Interval]; Interval
0x14000904d  mov     qword ptr [rsp+78h+Interval], 0F4240h
0x140009056  xor     edx, edx; Alertable
0x140009058  xor     ecx, ecx; WaitMode
0x14000905a  call    cs:__imp_KeDelayExecutionThread
0x140009061  nop     dword ptr [rax+rax+00h]
0x140009066  xor     r9d, r9d; Alertable
0x140009069  mov     [rsp+78h+Timeout], 0; Timeout
0x140009072  xor     r8d, r8d; WaitMode
0x140009075  xor     edx, edx; WaitReason
0x140009077  mov     rcx, rbp; Object
0x14000907a  call    cs:__imp_KeWaitForSingleObject
0x140009081  nop     dword ptr [rax+rax+00h]
0x140009086  mov     ebx, [rdi+4]
0x140009089  xor     edx, edx; Wait
0x14000908b  mov     rcx, rbp; Mutex
0x14000908e  call    cs:__imp_KeReleaseMutex
0x140009095  nop     dword ptr [rax+rax+00h]
0x14000909a  test    ebx, ebx
0x14000909c  jnz     short loc_140009048
0x14000909e  test    sil, sil
0x1400090a1  jz      short loc_1400090B4
0x1400090a3  lea     rcx, [rsp+78h+phContext]; phContext
0x1400090a8  call    cs:__imp_DeleteSecurityContext
0x1400090af  nop     dword ptr [rax+rax+00h]
0x1400090b4  test    r14b, r14b
0x1400090b7  jz      short loc_1400090CA
0x1400090b9  lea     rcx, [rsp+78h+phCredential]; phCredential
0x1400090be  call    cs:__imp_FreeCredentialsHandle
0x1400090c5  nop     dword ptr [rax+rax+00h]
0x1400090ca  mov     rcx, [rsp+78h+var_20]
0x1400090cf  xor     rcx, rsp; StackCookie
0x1400090d2  call    __security_check_cookie
0x1400090d7  lea     r11, [rsp+78h+var_18]
0x1400090dc  mov     rbx, [r11+28h]
0x1400090e0  mov     rbp, [r11+30h]
0x1400090e4  mov     rsp, r11
0x1400090e7  pop     r14
0x1400090e9  pop     rdi
0x1400090ea  pop     rsi
0x1400090eb  retn
```
