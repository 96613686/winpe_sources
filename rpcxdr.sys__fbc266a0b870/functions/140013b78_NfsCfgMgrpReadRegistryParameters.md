# NfsCfgMgrpReadRegistryParameters

- ea: `0x140013b78`
- end: `0x140013ddd`
- name: `NfsCfgMgrpReadRegistryParameters`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140024b80`

## callees

- `0x1400122e0`
- `0x140013b78`
- `0x140013fd4`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140013c1e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140013d10`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140013c1e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140013d10`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013c72`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013d74`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013c72`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013d74`
- `ntoskrnl!ZwClose` at `0x140013db9`
- `ntoskrnl!ZwClose` at `0x140013db9`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x140013d57`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x140013d57`
- `ntoskrnl!ZwOpenKey` at `0x140013bcc`
- `ntoskrnl!ZwOpenKey` at `0x140013bcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013cb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013d8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013cb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013d8d`
- `ntoskrnl!ExAllocatePool2` at `0x140013bf5`
- `ntoskrnl!ExAllocatePool2` at `0x140013ce5`
- `ntoskrnl!ExAllocatePool2` at `0x140013bf5`
- `ntoskrnl!ExAllocatePool2` at `0x140013ce5`

## pseudocode

```c
__int64 __fastcall NfsCfgMgrpReadRegistryParameters(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // ebx
  ULONG v2; // r14d
  unsigned __int16 *Pool2; // rsi
  __int64 v4; // rdi
  __int64 v5; // rdx
  NTSTATUS v6; // eax
  unsigned int v7; // eax
  unsigned __int32 v8; // eax
  _QWORD *v9; // rax
  _BYTE LockHandle[32]; // [rsp+20h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PVOID RestartKey; // [rsp+90h] [rbp+20h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp+28h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  RestartKey = 0;
  ObjectAttributes.RootDirectory = 0;
  memset(LockHandle, 0, sizeof(LockHandle));
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v1 >= 0 )
  {
    v2 = 128;
    Pool2 = (unsigned __int16 *)ExAllocatePool2(66, 128, 1363300931);
    if ( Pool2 )
    {
      v1 = 0;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)NfsResMgrpRoot + 3, (PKLOCK_QUEUE_HANDLE)LockHandle);
      LockHandle[24] = 1;
      RestartKey = 0;
      while ( 1 )
      {
        v9 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)((char *)NfsResMgrpRoot + 48), &RestartKey);
        if ( !v9 )
          break;
        v4 = v9[4];
        if ( (*(_DWORD *)(v4 + 412) & 1) == 0 )
        {
          v5 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(v4 + 4));
          if ( NfsRefHistoryTracingpGlobal )
            NfsReferenceHistoryCaptureRecord(v4, v5, 0);
          LockHandle[24] = 0;
          KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
          do
          {
            while ( 1 )
            {
              v6 = NfsCfgMgrpReadRegistryValueFetchAndValidate(v4, KeyHandle, v2, Pool2);
              v1 = v6;
              if ( (v6 == -2147483643 || v6 == -1073741789) && v2 < 0x2000 )
                break;
              if ( v6 != -1073741267 )
                goto LABEL_15;
            }
            ExFreePoolWithTag(Pool2, 0x51425243u);
            v7 = 0x2000;
            if ( 2 * v2 < 0x2000 )
              v7 = 2 * v2;
            v2 = v7;
            Pool2 = (unsigned __int16 *)ExAllocatePool2(66, v7, 1363300931);
          }
          while ( Pool2 );
          v2 = 0;
          v1 = -1073741670;
LABEL_15:
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)NfsResMgrpRoot + 3, (PKLOCK_QUEUE_HANDLE)LockHandle);
          LockHandle[24] = 1;
          v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 4), 0, 0);
          if ( NfsRefHistoryTracingpGlobal )
            NfsReferenceHistoryCaptureRecord(v4, v8, 1);
          _InterlockedDecrement((volatile signed __int32 *)(v4 + 4));
          if ( v1 < 0 )
            break;
        }
      }
      LockHandle[24] = 0;
      KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
      if ( Pool2 )
        ExFreePoolWithTag(Pool2, 0x51425243u);
    }
    else
    {
      v1 = -1073741670;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140013b78  mov     [rsp-18h+arg_10], rbx
0x140013b7d  mov     [rsp-18h+arg_18], rsi
0x140013b82  push    rbp
0x140013b83  push    rdi
0x140013b84  push    r14
0x140013b86  mov     rbp, rsp
0x140013b89  sub     rsp, 70h
0x140013b8d  xorps   xmm0, xmm0
0x140013b90  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140013b94  xor     eax, eax
0x140013b96  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140013b9e  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140013ba2  mov     [rbp+KeyHandle], rax
0x140013ba6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140013baa  mov     [rbp+RestartKey], rax
0x140013bae  mov     edx, 20019h; DesiredAccess
0x140013bb3  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140013bb7  movups  xmmword ptr [rbp+LockHandle], xmm0
0x140013bbb  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140013bc3  movups  xmmword ptr [rbp+LockHandle+10h], xmm0
0x140013bc7  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140013bcc  call    cs:__imp_ZwOpenKey
0x140013bd3  nop     dword ptr [rax+rax+00h]
0x140013bd8  mov     ebx, eax
0x140013bda  test    eax, eax
0x140013bdc  js      loc_140013DB0
0x140013be2  mov     r14d, 80h
0x140013be8  mov     r8d, 51425243h
0x140013bee  mov     edx, r14d
0x140013bf1  lea     ecx, [r14-3Eh]
0x140013bf5  call    cs:__imp_ExAllocatePool2
0x140013bfc  nop     dword ptr [rax+rax+00h]
0x140013c01  mov     rsi, rax
0x140013c04  test    rax, rax
0x140013c07  jz      loc_140013DAB
0x140013c0d  mov     rcx, cs:NfsResMgrpRoot
0x140013c14  lea     rdx, [rbp+LockHandle]; LockHandle
0x140013c18  add     rcx, 18h; SpinLock
0x140013c1c  xor     ebx, ebx
0x140013c1e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140013c25  nop     dword ptr [rax+rax+00h]
0x140013c2a  mov     [rbp+LockHandle+18h], 1
0x140013c2e  mov     [rbp+RestartKey], rbx
0x140013c32  jmp     loc_140013D48
0x140013c37  mov     rdi, [rax+20h]
0x140013c3b  mov     eax, [rdi+19Ch]
0x140013c41  test    al, 1
0x140013c43  jnz     loc_140013D48
0x140013c49  mov     edx, 1
0x140013c4e  lock xadd [rdi+4], edx
0x140013c53  inc     edx
0x140013c55  cmp     cs:NfsRefHistoryTracingpGlobal, 0
0x140013c5d  jz      short loc_140013C6A
0x140013c5f  xor     r8d, r8d
0x140013c62  mov     rcx, rdi
0x140013c65  call    NfsReferenceHistoryCaptureRecord
0x140013c6a  lea     rcx, [rbp+LockHandle]; LockHandle
0x140013c6e  mov     [rbp+LockHandle+18h], 0
0x140013c72  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140013c79  nop     dword ptr [rax+rax+00h]
0x140013c7e  mov     rdx, [rbp+KeyHandle]
0x140013c82  mov     r9, rsi
0x140013c85  mov     r8d, r14d
0x140013c88  mov     rcx, rdi
0x140013c8b  call    NfsCfgMgrpReadRegistryValueFetchAndValidate
0x140013c90  mov     ebx, eax
0x140013c92  cmp     eax, 80000005h
0x140013c97  jz      short loc_140013CA4
0x140013c99  cmp     eax, 0C0000023h
0x140013c9e  jnz     loc_140013D9B
0x140013ca4  cmp     r14d, 2000h
0x140013cab  jnb     loc_140013D9B
0x140013cb1  mov     edx, 51425243h; Tag
0x140013cb6  mov     rcx, rsi; P
0x140013cb9  call    cs:__imp_ExFreePoolWithTag
0x140013cc0  nop     dword ptr [rax+rax+00h]
0x140013cc5  lea     ecx, [r14+r14]
0x140013cc9  mov     edx, 2000h
0x140013cce  cmp     ecx, edx
0x140013cd0  mov     eax, edx
0x140013cd2  mov     r8d, 51425243h
0x140013cd8  cmovb   eax, ecx
0x140013cdb  mov     ecx, 42h ; 'B'
0x140013ce0  mov     edx, eax
0x140013ce2  mov     r14d, eax
0x140013ce5  call    cs:__imp_ExAllocatePool2
0x140013cec  nop     dword ptr [rax+rax+00h]
0x140013cf1  mov     rsi, rax
0x140013cf4  test    rax, rax
0x140013cf7  jnz     short loc_140013C7E
0x140013cf9  xor     r14d, r14d
0x140013cfc  mov     ebx, 0C000009Ah
0x140013d01  mov     rcx, cs:NfsResMgrpRoot
0x140013d08  lea     rdx, [rbp+LockHandle]; LockHandle
0x140013d0c  add     rcx, 18h; SpinLock
0x140013d10  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140013d17  nop     dword ptr [rax+rax+00h]
0x140013d1c  xor     ecx, ecx
0x140013d1e  mov     [rbp+LockHandle+18h], 1
0x140013d22  xor     eax, eax
0x140013d24  lock cmpxchg [rdi+4], ecx
0x140013d29  cmp     cs:NfsRefHistoryTracingpGlobal, rcx
0x140013d30  jz      short loc_140013D40
0x140013d32  lea     r8d, [rcx+1]
0x140013d36  mov     edx, eax
0x140013d38  mov     rcx, rdi
0x140013d3b  call    NfsReferenceHistoryCaptureRecord
0x140013d40  lock dec dword ptr [rdi+4]
0x140013d44  test    ebx, ebx
0x140013d46  js      short loc_140013D6C
0x140013d48  mov     rcx, cs:NfsResMgrpRoot
0x140013d4f  lea     rdx, [rbp+RestartKey]; RestartKey
0x140013d53  add     rcx, 30h ; '0'; Table
0x140013d57  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x140013d5e  nop     dword ptr [rax+rax+00h]
0x140013d63  test    rax, rax
0x140013d66  jnz     loc_140013C37
0x140013d6c  lea     rcx, [rbp+LockHandle]; LockHandle
0x140013d70  mov     [rbp+LockHandle+18h], 0
0x140013d74  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140013d7b  nop     dword ptr [rax+rax+00h]
0x140013d80  test    rsi, rsi
0x140013d83  jz      short loc_140013DB0
0x140013d85  mov     edx, 51425243h; Tag
0x140013d8a  mov     rcx, rsi; P
0x140013d8d  call    cs:__imp_ExFreePoolWithTag
0x140013d94  nop     dword ptr [rax+rax+00h]
0x140013d99  jmp     short loc_140013DB0
0x140013d9b  cmp     eax, 0C000022Dh
0x140013da0  jz      loc_140013C7E
0x140013da6  jmp     loc_140013D01
0x140013dab  mov     ebx, 0C000009Ah
0x140013db0  mov     rcx, [rbp+KeyHandle]; Handle
0x140013db4  test    rcx, rcx
0x140013db7  jz      short loc_140013DC5
0x140013db9  call    cs:__imp_ZwClose
0x140013dc0  nop     dword ptr [rax+rax+00h]
0x140013dc5  lea     r11, [rsp+70h+var_s0]
0x140013dca  mov     eax, ebx
0x140013dcc  mov     rbx, [r11+30h]
0x140013dd0  mov     rsi, [r11+38h]
0x140013dd4  mov     rsp, r11
0x140013dd7  pop     r14
0x140013dd9  pop     rdi
0x140013dda  pop     rbp
0x140013ddb  retn
```
