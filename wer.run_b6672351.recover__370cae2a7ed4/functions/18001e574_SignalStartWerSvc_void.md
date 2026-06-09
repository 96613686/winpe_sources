# SignalStartWerSvc(void)

- ea: `0x18001e574`
- end: `0x18001e651`
- name: `?SignalStartWerSvc@@YAJXZ`
- size: `221`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18001e2c0`

## callees

- `0x18001e574`
- `0x180053300`

## import_xrefs

- `ntdll!ZwQueryWnfStateNameInformation` at `0x18001e5bb`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18001e5bb`
- `ntdll!ZwUpdateWnfStateData` at `0x18001e5ed`
- `ntdll!ZwUpdateWnfStateData` at `0x18001e5ed`
- `ntdll!EtwEventWriteNoRegistration` at `0x18001e618`
- `ntdll!EtwEventWriteNoRegistration` at `0x18001e618`

## pseudocode

```c
__int64 SignalStartWerSvc(void)
{
  BOOL v0; // ebx
  int v1; // eax
  int v2; // ecx
  __int64 result; // rax
  int v4; // [rsp+40h] [rbp-28h] BYREF
  __int128 v5; // [rsp+48h] [rbp-20h] BYREF

  v4 = 0;
  v0 = 0;
  v5 = 0;
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &v4, 4) >= 0 && v4 )
    v0 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  v5 = 0;
  v1 = EtwEventWriteNoRegistration(&`SignalStartWerSvc'::`2'::WerSvcTriggerGuid, &v5, 0, 0);
  v2 = v0 + 1;
  if ( v1 )
    v2 = v0;
  result = 0;
  if ( !v2 )
    return 3221225600LL;
  return result;
}

```

## disassembly

```asm
0x18001e574  mov     [rsp+arg_0], rbx
0x18001e579  push    rsi
0x18001e57a  sub     rsp, 60h
0x18001e57e  mov     rax, cs:__security_cookie
0x18001e585  xor     rax, rsp
0x18001e588  mov     [rsp+68h+var_10], rax
0x18001e58d  xorps   xmm0, xmm0
0x18001e590  mov     [rsp+68h+var_28], 0
0x18001e598  xor     ebx, ebx
0x18001e59a  mov     dword ptr [rsp+68h+var_48], 4
0x18001e5a2  lea     r9, [rsp+68h+var_28]
0x18001e5a7  xor     r8d, r8d
0x18001e5aa  lea     rcx, WNF_WER_SERVICE_START
0x18001e5b1  movups  [rsp+68h+var_20], xmm0
0x18001e5b6  lea     esi, [rbx+1]
0x18001e5b9  mov     edx, esi
0x18001e5bb  call    cs:__imp_ZwQueryWnfStateNameInformation
0x18001e5c2  nop     dword ptr [rax+rax+00h]
0x18001e5c7  test    eax, eax
0x18001e5c9  js      short loc_18001E5FE
0x18001e5cb  cmp     [rsp+68h+var_28], ebx
0x18001e5cf  jz      short loc_18001E5FE
0x18001e5d1  mov     [rsp+68h+var_38], ebx
0x18001e5d5  lea     rcx, WNF_WER_SERVICE_START
0x18001e5dc  mov     [rsp+68h+var_40], ebx
0x18001e5e0  xor     r9d, r9d
0x18001e5e3  xor     r8d, r8d
0x18001e5e6  mov     [rsp+68h+var_48], rbx
0x18001e5eb  xor     edx, edx
0x18001e5ed  call    cs:__imp_ZwUpdateWnfStateData
0x18001e5f4  nop     dword ptr [rax+rax+00h]
0x18001e5f9  test    eax, eax
0x18001e5fb  cmovns  ebx, esi
0x18001e5fe  xorps   xmm0, xmm0
0x18001e601  lea     rdx, [rsp+68h+var_20]
0x18001e606  xor     r9d, r9d
0x18001e609  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x18001e610  xor     r8d, r8d
0x18001e613  movups  [rsp+68h+var_20], xmm0
0x18001e618  call    cs:__imp_EtwEventWriteNoRegistration
0x18001e61f  nop     dword ptr [rax+rax+00h]
0x18001e624  lea     ecx, [rbx+1]
0x18001e627  mov     edx, 0C0000080h
0x18001e62c  test    eax, eax
0x18001e62e  cmovnz  ecx, ebx
0x18001e631  xor     eax, eax
0x18001e633  test    ecx, ecx
0x18001e635  cmovz   eax, edx
0x18001e638  mov     rcx, [rsp+68h+var_10]
0x18001e63d  xor     rcx, rsp; StackCookie
0x18001e640  call    __security_check_cookie
0x18001e645  mov     rbx, [rsp+68h+arg_0]
0x18001e64a  add     rsp, 60h
0x18001e64e  pop     rsi
0x18001e64f  retn
```
