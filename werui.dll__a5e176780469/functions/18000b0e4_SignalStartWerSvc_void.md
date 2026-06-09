# SignalStartWerSvc(void)

- ea: `0x18000b0e4`
- end: `0x18000b1ae`
- name: `?SignalStartWerSvc@@YAJXZ`
- size: `202`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000bb20`

## callees

- `0x18000b0e4`
- `0x180016c50`

## import_xrefs

- `ntdll!ZwQueryWnfStateNameInformation` at `0x18000b12b`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x18000b12b`
- `ntdll!ZwUpdateWnfStateData` at `0x18000b157`
- `ntdll!ZwUpdateWnfStateData` at `0x18000b157`
- `ntdll!EtwEventWriteNoRegistration` at `0x18000b17c`
- `ntdll!EtwEventWriteNoRegistration` at `0x18000b17c`

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
0x18000b0e4  mov     [rsp+arg_0], rbx
0x18000b0e9  push    rsi
0x18000b0ea  sub     rsp, 60h
0x18000b0ee  mov     rax, cs:__security_cookie
0x18000b0f5  xor     rax, rsp
0x18000b0f8  mov     [rsp+68h+var_10], rax
0x18000b0fd  xorps   xmm0, xmm0
0x18000b100  mov     [rsp+68h+var_28], 0
0x18000b108  xor     ebx, ebx
0x18000b10a  mov     dword ptr [rsp+68h+var_48], 4
0x18000b112  lea     r9, [rsp+68h+var_28]
0x18000b117  xor     r8d, r8d
0x18000b11a  lea     rcx, WNF_WER_SERVICE_START
0x18000b121  movups  [rsp+68h+var_20], xmm0
0x18000b126  lea     esi, [rbx+1]
0x18000b129  mov     edx, esi
0x18000b12b  call    cs:__imp_ZwQueryWnfStateNameInformation
0x18000b131  test    eax, eax
0x18000b133  js      short loc_18000B162
0x18000b135  cmp     [rsp+68h+var_28], ebx
0x18000b139  jz      short loc_18000B162
0x18000b13b  mov     [rsp+68h+var_38], ebx
0x18000b13f  lea     rcx, WNF_WER_SERVICE_START
0x18000b146  mov     [rsp+68h+var_40], ebx
0x18000b14a  xor     r9d, r9d
0x18000b14d  xor     r8d, r8d
0x18000b150  mov     [rsp+68h+var_48], rbx
0x18000b155  xor     edx, edx
0x18000b157  call    cs:__imp_ZwUpdateWnfStateData
0x18000b15d  test    eax, eax
0x18000b15f  cmovns  ebx, esi
0x18000b162  xorps   xmm0, xmm0
0x18000b165  lea     rdx, [rsp+68h+var_20]
0x18000b16a  xor     r9d, r9d
0x18000b16d  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x18000b174  xor     r8d, r8d
0x18000b177  movups  [rsp+68h+var_20], xmm0
0x18000b17c  call    cs:__imp_EtwEventWriteNoRegistration
0x18000b182  lea     ecx, [rbx+1]
0x18000b185  mov     edx, 0C0000080h
0x18000b18a  test    eax, eax
0x18000b18c  cmovnz  ecx, ebx
0x18000b18f  xor     eax, eax
0x18000b191  test    ecx, ecx
0x18000b193  cmovz   eax, edx
0x18000b196  mov     rcx, [rsp+68h+var_10]
0x18000b19b  xor     rcx, rsp; StackCookie
0x18000b19e  call    __security_check_cookie
0x18000b1a3  mov     rbx, [rsp+68h+arg_0]
0x18000b1a8  add     rsp, 60h
0x18000b1ac  pop     rsi
0x18000b1ad  retn
```
