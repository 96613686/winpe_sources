# InitializeHttpCommon(void)

- ea: `0x18000d4fc`
- end: `0x18000d599`
- name: `?InitializeHttpCommon@@YAJXZ`
- size: `157`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c1a0`
- `0x18000c8c0`

## callees

- `0x18000d4fc`
- `0x18000deb0`
- `0x180024629`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000d549`
- `ntdll!RtlNtStatusToDosError` at `0x18000d549`
- `ntdll!NtQuerySystemInformation` at `0x18000d53d`
- `ntdll!NtQuerySystemInformation` at `0x18000d53d`

## pseudocode

```c
ULONG InitializeHttpCommon(void)
{
  int v0; // eax
  _BYTE SystemInformation[64]; // [rsp+20h] [rbp-58h] BYREF

  memset_0(SystemInformation, 0, sizeof(SystemInformation));
  (*((void (**)(void))pRuntimeImportTable + 5))();
  v0 = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  if ( v0 < 0 )
    return RtlNtStatusToDosError(v0);
  gNumberOfProcessors = SystemInformation[56];
  if ( !HTTPTransInfo )
    HTTPTransInfo = (struct TRANS_INFO *)(*((__int64 (__fastcall **)(__int64))pRuntimeImportTable + 8))(31);
  return InitializeReceiveWindows();
}

```

## disassembly

```asm
0x18000d4fc  sub     rsp, 78h
0x18000d500  mov     rax, cs:__security_cookie
0x18000d507  xor     rax, rsp
0x18000d50a  mov     [rsp+78h+var_18], rax
0x18000d50f  xor     edx, edx; Val
0x18000d511  lea     rcx, [rsp+78h+SystemInformation]; void *
0x18000d516  lea     r8d, [rdx+40h]; Size
0x18000d51a  call    memset_0
0x18000d51f  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000d526  mov     rax, [rax+28h]
0x18000d52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d52f  xor     r9d, r9d; ReturnLength
0x18000d532  lea     rdx, [rsp+78h+SystemInformation]; SystemInformation
0x18000d537  xor     ecx, ecx; SystemInformationClass
0x18000d539  lea     r8d, [r9+40h]; SystemInformationLength
0x18000d53d  call    cs:__imp_NtQuerySystemInformation
0x18000d543  test    eax, eax
0x18000d545  jns     short loc_18000D551
0x18000d547  mov     ecx, eax; Status
0x18000d549  call    cs:__imp_RtlNtStatusToDosError
0x18000d54f  jmp     short loc_18000D587
0x18000d551  cmp     cs:?HTTPTransInfo@@3PEAVTRANS_INFO@@EA, 0; TRANS_INFO * HTTPTransInfo
0x18000d559  movsx   eax, [rsp+78h+var_20]
0x18000d55e  mov     cs:?gNumberOfProcessors@@3IA, eax; uint gNumberOfProcessors
0x18000d564  jnz     short loc_18000D582
0x18000d566  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000d56d  mov     ecx, 1Fh
0x18000d572  mov     rax, [rax+40h]
0x18000d576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d57b  mov     cs:?HTTPTransInfo@@3PEAVTRANS_INFO@@EA, rax; TRANS_INFO * HTTPTransInfo
0x18000d582  call    ?InitializeReceiveWindows@@YAJXZ; InitializeReceiveWindows(void)
0x18000d587  mov     rcx, [rsp+78h+var_18]
0x18000d58c  xor     rcx, rsp; StackCookie
0x18000d58f  call    __security_check_cookie
0x18000d594  add     rsp, 78h
0x18000d598  retn
```
