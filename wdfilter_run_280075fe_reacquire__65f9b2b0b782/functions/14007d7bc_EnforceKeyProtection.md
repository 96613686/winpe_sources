# EnforceKeyProtection

- ea: `0x14007d7bc`
- end: `0x14007d9eb`
- name: `EnforceKeyProtection`
- size: `559`
- prototype: `__int64 __fastcall(HANDLE Handle, HANDLE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007d5d4`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x14007d7bc`
- `0x140080374`

## import_xrefs

- `ntoskrnl!ZwQuerySecurityObject` at `0x14007d80e`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14007d8e0`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14007d80e`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14007d8e0`
- `ntoskrnl!ZwSetSecurityObject` at `0x14007d95b`
- `ntoskrnl!ZwSetSecurityObject` at `0x14007d95b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d9bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d9bb`

## pseudocode

```c
__int64 __fastcall EnforceKeyProtection(HANDLE Handle, HANDLE a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rdx
  void *PoolWithTag; // rdi
  __int64 v7; // rdx
  int LengthNeeded; // [rsp+20h] [rbp-38h]
  ULONG Length; // [rsp+30h] [rbp-28h] BYREF

  Length = 0;
  if ( Handle && a2 )
  {
    v4 = ZwQuerySecurityObject(a2, 4u, 0, 0, &Length);
    if ( v4 != -1073741789 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return (unsigned int)v4;
      v5 = 175;
      LengthNeeded = v4;
      goto LABEL_7;
    }
    PoolWithTag = (void *)MpAllocatePoolWithTag(1, Length, 1685278797);
    if ( !PoolWithTag )
    {
      v4 = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return (unsigned int)v4;
      v5 = 176;
      LengthNeeded = -1073741670;
LABEL_7:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        LengthNeeded);
      return (unsigned int)v4;
    }
    v4 = ZwQuerySecurityObject(a2, 4u, PoolWithTag, Length, &Length);
    if ( v4 >= 0 )
    {
      _mm_lfence();
      v4 = MpRemoveAdminAndNonAdminSidsFromSd(PoolWithTag);
      if ( v4 >= 0 )
      {
        _mm_lfence();
        v4 = ZwSetSecurityObject(Handle, 0x80000004, PoolWithTag);
        if ( v4 >= 0
          || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        {
          goto LABEL_25;
        }
        v7 = 179;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_25;
        v7 = 178;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_25;
      v7 = 177;
    }
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
      KeGetCurrentThread(),
      v4);
LABEL_25:
    ExFreePoolWithTag(PoolWithTag, 0x6473504Du);
    return (unsigned int)v4;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14007d7bc  mov     [rsp+arg_10], rbx
0x14007d7c1  push    rbp
0x14007d7c2  push    rsi
0x14007d7c3  push    rdi
0x14007d7c4  sub     rsp, 40h
0x14007d7c8  mov     rax, cs:__security_cookie
0x14007d7cf  xor     rax, rsp
0x14007d7d2  mov     [rsp+58h+var_20], rax
0x14007d7d7  mov     [rsp+58h+Length], 0
0x14007d7df  mov     rsi, rdx
0x14007d7e2  mov     rbp, rcx
0x14007d7e5  test    rcx, rcx
0x14007d7e8  jz      loc_14007D9CB
0x14007d7ee  test    rdx, rdx
0x14007d7f1  jz      loc_14007D9CB
0x14007d7f7  xor     r9d, r9d; Length
0x14007d7fa  lea     rax, [rsp+58h+Length]
0x14007d7ff  xor     r8d, r8d; SecurityDescriptor
0x14007d802  mov     qword ptr [rsp+58h+LengthNeeded], rax; LengthNeeded
0x14007d807  mov     rcx, rsi; Handle
0x14007d80a  lea     edx, [r9+4]; SecurityInformation
0x14007d80e  call    cs:__imp_ZwQuerySecurityObject
0x14007d815  nop     dword ptr [rax+rax+00h]
0x14007d81a  mov     ebx, eax
0x14007d81c  cmp     eax, 0C0000023h
0x14007d821  jz      short loc_14007D874
0x14007d823  mov     rax, cs:WPP_GLOBAL_Control
0x14007d82a  lea     rcx, WPP_GLOBAL_Control
0x14007d831  cmp     rax, rcx
0x14007d834  jz      loc_14007D9C7
0x14007d83a  mov     ecx, [rax+2Ch]
0x14007d83d  test    cl, 1
0x14007d840  jz      loc_14007D9C7
0x14007d846  mov     edx, 0AFh
0x14007d84b  mov     [rsp+58h+LengthNeeded], ebx
0x14007d84f  mov     r9, gs:188h
0x14007d858  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14007d85f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d866  mov     rcx, [rcx+18h]
0x14007d86a  call    WPP_SF_qD
0x14007d86f  jmp     loc_14007D9C7
0x14007d874  mov     edx, [rsp+58h+Length]
0x14007d878  mov     ecx, 1
0x14007d87d  mov     r8d, 6473504Dh
0x14007d883  call    MpAllocatePoolWithTag
0x14007d888  mov     rdi, rax
0x14007d88b  test    rax, rax
0x14007d88e  jnz     short loc_14007D8C6
0x14007d890  mov     ebx, 0C000009Ah
0x14007d895  mov     rax, cs:WPP_GLOBAL_Control
0x14007d89c  lea     rcx, WPP_GLOBAL_Control
0x14007d8a3  cmp     rax, rcx
0x14007d8a6  jz      loc_14007D9C7
0x14007d8ac  mov     eax, [rax+2Ch]
0x14007d8af  test    al, 1
0x14007d8b1  jz      loc_14007D9C7
0x14007d8b7  mov     edx, 0B0h
0x14007d8bc  mov     [rsp+58h+LengthNeeded], 0C000009Ah
0x14007d8c4  jmp     short loc_14007D84F
0x14007d8c6  mov     r9d, [rsp+58h+Length]; Length
0x14007d8cb  lea     rax, [rsp+58h+Length]
0x14007d8d0  mov     r8, rdi; SecurityDescriptor
0x14007d8d3  mov     qword ptr [rsp+58h+LengthNeeded], rax; LengthNeeded
0x14007d8d8  mov     edx, 4; SecurityInformation
0x14007d8dd  mov     rcx, rsi; Handle
0x14007d8e0  call    cs:__imp_ZwQuerySecurityObject
0x14007d8e7  nop     dword ptr [rax+rax+00h]
0x14007d8ec  mov     ebx, eax
0x14007d8ee  test    eax, eax
0x14007d8f0  jns     short loc_14007D91B
0x14007d8f2  mov     rax, cs:WPP_GLOBAL_Control
0x14007d8f9  lea     rcx, WPP_GLOBAL_Control
0x14007d900  cmp     rax, rcx
0x14007d903  jz      loc_14007D9B3
0x14007d909  mov     eax, [rax+2Ch]
0x14007d90c  test    al, 1
0x14007d90e  jz      loc_14007D9B3
0x14007d914  mov     edx, 0B1h
0x14007d919  jmp     short loc_14007D98C
0x14007d91b  lfence
0x14007d91e  mov     rcx, rdi; SecurityDescriptor
0x14007d921  call    MpRemoveAdminAndNonAdminSidsFromSd
0x14007d926  mov     ebx, eax
0x14007d928  test    eax, eax
0x14007d92a  jns     short loc_14007D94D
0x14007d92c  mov     rax, cs:WPP_GLOBAL_Control
0x14007d933  lea     rcx, WPP_GLOBAL_Control
0x14007d93a  cmp     rax, rcx
0x14007d93d  jz      short loc_14007D9B3
0x14007d93f  mov     eax, [rax+2Ch]
0x14007d942  test    al, 1
0x14007d944  jz      short loc_14007D9B3
0x14007d946  mov     edx, 0B2h
0x14007d94b  jmp     short loc_14007D98C
0x14007d94d  lfence
0x14007d950  mov     r8, rdi; SecurityDescriptor
0x14007d953  mov     edx, 80000004h; SecurityInformation
0x14007d958  mov     rcx, rbp; Handle
0x14007d95b  call    cs:__imp_ZwSetSecurityObject
0x14007d962  nop     dword ptr [rax+rax+00h]
0x14007d967  mov     ebx, eax
0x14007d969  test    eax, eax
0x14007d96b  jns     short loc_14007D9B3
0x14007d96d  mov     rax, cs:WPP_GLOBAL_Control
0x14007d974  lea     rcx, WPP_GLOBAL_Control
0x14007d97b  cmp     rax, rcx
0x14007d97e  jz      short loc_14007D9B3
0x14007d980  mov     eax, [rax+2Ch]
0x14007d983  test    al, 1
0x14007d985  jz      short loc_14007D9B3
0x14007d987  mov     edx, 0B3h
0x14007d98c  lfence
0x14007d98f  mov     r9, gs:188h
0x14007d998  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14007d99f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d9a6  mov     [rsp+58h+LengthNeeded], ebx
0x14007d9aa  mov     rcx, [rcx+18h]
0x14007d9ae  call    WPP_SF_qD
0x14007d9b3  mov     edx, 6473504Dh; Tag
0x14007d9b8  mov     rcx, rdi; P
0x14007d9bb  call    cs:__imp_ExFreePoolWithTag
0x14007d9c2  nop     dword ptr [rax+rax+00h]
0x14007d9c7  mov     eax, ebx
0x14007d9c9  jmp     short loc_14007D9D0
0x14007d9cb  mov     eax, 0C000000Dh
0x14007d9d0  mov     rcx, [rsp+58h+var_20]
0x14007d9d5  xor     rcx, rsp; StackCookie
0x14007d9d8  call    __security_check_cookie
0x14007d9dd  mov     rbx, [rsp+58h+arg_10]
0x14007d9e2  add     rsp, 40h
0x14007d9e6  pop     rdi
0x14007d9e7  pop     rsi
0x14007d9e8  pop     rbp
0x14007d9e9  retn
```
