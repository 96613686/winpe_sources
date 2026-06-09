# CGroupPolicy::DisableAllAccessToAllDevices(_ACL *,void *,ulong,int *)

- ea: `0x18000fc24`
- end: `0x18000fd0c`
- name: `?DisableAllAccessToAllDevices@CGroupPolicy@@IEAAXPEAU_ACL@@PEAXKPEAH@Z`
- size: `232`
- prototype: `void __fastcall(CGroupPolicy *this, struct _ACL *, void *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800069d0`

## callees

- `0x180007160`
- `0x18000eda4`
- `0x18000f390`
- `0x18000fc24`
- `0x1800154fc`

## string_xrefs

- `0x18000fce8`: `Access Code`

## pseudocode

```c
void __fastcall CGroupPolicy::DisableAllAccessToAllDevices(
        CGroupPolicy *this,
        struct _ACL *a2,
        void *a3,
        unsigned int a4,
        int *a5)
{
  __int64 i; // rbx
  CGroupPolicy *v9; // rcx
  __int64 v10; // rdx
  int v11; // [rsp+28h] [rbp-60h]
  struct _GUID Buf1[3]; // [rsp+50h] [rbp-38h] BYREF

  AccessCode = 1;
  for ( i = 0; i != 6; ++i )
  {
    Buf1[0] = *(&GP_WellKnown_GUIDS + i);
    if ( !memcmp_0(Buf1, &GUID_DEVINTERFACE_VOLUME, 0x10u) )
      CGroupPolicy::ApplyGroupPolicyForDiskDevices(v9, a2, a3, a4, a5, v11, 0);
    else
      CGroupPolicy::ApplyGroupPolicyForDevices(v9, Buf1, a2, a3, a4, 0, 0, 1, a5);
  }
  WPDLibSetRegistryValue(
    0,
    v10,
    L"SYSTEM\\CurrentControlSet\\Control\\Storage\\Test",
    L"Access Code",
    4,
    &AccessCode,
    4);
}

```

## disassembly

```asm
0x18000fc24  push    rbx
0x18000fc26  push    rbp
0x18000fc27  push    rsi
0x18000fc28  push    rdi
0x18000fc29  push    r14
0x18000fc2b  sub     rsp, 60h
0x18000fc2f  mov     r14, [rsp+88h+arg_20]
0x18000fc37  mov     edi, r9d
0x18000fc3a  mov     rsi, r8
0x18000fc3d  mov     cs:?AccessCode@@3KA, 1; ulong AccessCode
0x18000fc47  mov     rbp, rdx
0x18000fc4a  xor     ebx, ebx
0x18000fc4c  lea     rcx, ?GP_WellKnown_GUIDS@@3PAU_GUID@@A; _GUID near * GP_WellKnown_GUIDS
0x18000fc53  mov     rax, rbx
0x18000fc56  add     rax, rax
0x18000fc59  lea     rdx, GUID_DEVINTERFACE_VOLUME; Buf2
0x18000fc60  mov     r8d, 10h; Size
0x18000fc66  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18000fc6a  lea     rcx, [rsp+88h+Buf1]; Buf1
0x18000fc6f  movdqu  [rsp+88h+Buf1], xmm0
0x18000fc75  call    memcmp_0
0x18000fc7a  test    eax, eax
0x18000fc7c  jnz     short loc_18000FC97
0x18000fc7e  mov     [rsp+88h+var_58], eax; int
0x18000fc82  mov     r9d, edi; unsigned int
0x18000fc85  mov     r8, rsi; void *
0x18000fc88  mov     [rsp+88h+var_68], r14; int *
0x18000fc8d  mov     rdx, rbp; struct _ACL *
0x18000fc90  call    ?ApplyGroupPolicyForDiskDevices@CGroupPolicy@@IEAAXPEAU_ACL@@PEAXKPEAHHH@Z; CGroupPolicy::ApplyGroupPolicyForDiskDevices(_ACL *,void *,ulong,int *,int,int)
0x18000fc95  jmp     short loc_18000FCC8
0x18000fc97  mov     [rsp+88h+var_48], r14; int *
0x18000fc9c  lea     rdx, [rsp+88h+Buf1]; struct _GUID *
0x18000fca1  mov     [rsp+88h+var_50], 1; int
0x18000fca9  mov     r9, rsi; void *
0x18000fcac  mov     [rsp+88h+var_58], 0; int
0x18000fcb4  mov     r8, rbp; struct _ACL *
0x18000fcb7  mov     [rsp+88h+var_60], 0; int
0x18000fcbf  mov     dword ptr [rsp+88h+var_68], edi; unsigned int
0x18000fcc3  call    ?ApplyGroupPolicyForDevices@CGroupPolicy@@IEAAXPEAU_GUID@@PEAU_ACL@@PEAXKHHHPEAH@Z; CGroupPolicy::ApplyGroupPolicyForDevices(_GUID *,_ACL *,void *,ulong,int,int,int,int *)
0x18000fcc8  inc     rbx
0x18000fccb  cmp     rbx, 6
0x18000fccf  jnz     loc_18000FC4C
0x18000fcd5  lea     ecx, [rbx-2]
0x18000fcd8  mov     [rsp+88h+var_58], ecx
0x18000fcdc  lea     rax, ?AccessCode@@3KA; ulong AccessCode
0x18000fce3  mov     qword ptr [rsp+88h+var_60], rax
0x18000fce8  lea     r9, aAccessCode; "Access Code"
0x18000fcef  mov     dword ptr [rsp+88h+var_68], ecx
0x18000fcf3  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x18000fcfa  xor     ecx, ecx
0x18000fcfc  call    WPDLibSetRegistryValue
0x18000fd01  add     rsp, 60h
0x18000fd05  pop     r14
0x18000fd07  pop     rdi
0x18000fd08  pop     rsi
0x18000fd09  pop     rbp
0x18000fd0a  pop     rbx
0x18000fd0b  retn
```
