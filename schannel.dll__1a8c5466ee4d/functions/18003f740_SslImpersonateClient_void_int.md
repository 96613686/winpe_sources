# SslImpersonateClient(void *,int *)

- ea: `0x18003f740`
- end: `0x18003f7aa`
- name: `?SslImpersonateClient@@YAKPEAXPEAH@Z`
- size: `106`
- prototype: `unsigned int __fastcall(void *, int *)`
- caller_count: `21`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003a70`
- `0x180006c38`
- `0x180006f1c`
- `0x1800131c0`
- `0x180038dd4`
- `0x18003f150`
- `0x18004ab48`
- `0x18004ae78`
- `0x18004c5ec`
- `0x18004d500`
- `0x18005c528`
- `0x18005ca90`
- `0x180062de8`
- `0x180071068`
- `0x18007223c`
- `0x180072e04`
- `0x180078a2c`
- `0x180079b58`
- `0x18007ce4c`
- `0x18007db7c`
- `0x180085148`

## callees

- `0x18003f740`
- `0x180091010`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18003f77b`
- `ntdll!NtSetInformationThread` at `0x18003f77b`
- `ntdll!RtlNtStatusToDosError` at `0x18003f78d`
- `ntdll!RtlNtStatusToDosError` at `0x18003f78d`

## pseudocode

```c
unsigned int __fastcall SslImpersonateClient(void *a1, int *a2)
{
  __int64 v2; // rax
  int v4; // eax
  void *ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  ThreadInformation = a1;
  v2 = LsaTable;
  *a2 = 0;
  if ( v2 )
  {
    if ( a1 )
      v4 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    else
      v4 = (*(__int64 (**)(void))(v2 + 88))();
    if ( v4 >= 0 )
      *a2 = 1;
    LODWORD(v2) = RtlNtStatusToDosError(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18003f740  mov     [rsp+ThreadInformation], rcx
0x18003f745  push    rbx
0x18003f746  sub     rsp, 20h
0x18003f74a  mov     rax, cs:LsaTable
0x18003f751  mov     rbx, rdx
0x18003f754  mov     dword ptr [rdx], 0
0x18003f75a  test    rax, rax
0x18003f75d  jz      short loc_18003F799
0x18003f75f  test    rcx, rcx
0x18003f762  jz      short loc_18003F79F
0x18003f764  mov     r9d, 8; ThreadInformationLength
0x18003f76a  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x18003f76f  mov     edx, 5; ThreadInformationClass
0x18003f774  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003f77b  call    cs:__imp_NtSetInformationThread
0x18003f781  test    eax, eax
0x18003f783  js      short loc_18003F78B
0x18003f785  mov     dword ptr [rbx], 1
0x18003f78b  mov     ecx, eax; Status
0x18003f78d  call    cs:__imp_RtlNtStatusToDosError
0x18003f793  add     rsp, 20h
0x18003f797  pop     rbx
0x18003f798  retn
0x18003f799  add     rsp, 20h
0x18003f79d  pop     rbx
0x18003f79e  retn
0x18003f79f  mov     rax, [rax+58h]
0x18003f7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7a8  jmp     short loc_18003F781
```
