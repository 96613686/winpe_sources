# CWinInetHelperClass::Repair(tagRepairInfo *,long *,tagREPAIR_STATUS *)

- ea: `0x18000c2a0`
- end: `0x18000c2fe`
- name: `?Repair@CWinInetHelperClass@@UEAAJPEAUtagRepairInfo@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, struct tagRepairInfo *, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x18000c2a0`
- `0x18000e7d0`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::Repair(
        CWinInetHelperClass *this,
        struct tagRepairInfo *a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  __int64 result; // rax

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  if ( ID_WINETHC_REPAIR_AUTOCONFIGPROXY != *(_OWORD *)&a2->guid )
    return 2147500033LL;
  result = _RunAsImpersonatedUser(L"SetAutoDetectProxyFlagForUser");
  *a4 = (((int)result >> 31) & 1) + 1;
  return result;
}

```

## disassembly

```asm
0x18000c2a0  push    rbx
0x18000c2a2  sub     rsp, 20h
0x18000c2a6  mov     rbx, r9
0x18000c2a9  test    rdx, rdx
0x18000c2ac  jz      short loc_18000C2F2
0x18000c2ae  test    r8, r8
0x18000c2b1  jz      short loc_18000C2F2
0x18000c2b3  test    rbx, rbx
0x18000c2b6  jz      short loc_18000C2F2
0x18000c2b8  mov     rax, qword ptr cs:ID_WINETHC_REPAIR_AUTOCONFIGPROXY
0x18000c2bf  cmp     rax, [rdx]
0x18000c2c2  jnz     short loc_18000C2EB
0x18000c2c4  mov     rax, qword ptr cs:ID_WINETHC_REPAIR_AUTOCONFIGPROXY+8
0x18000c2cb  cmp     rax, [rdx+8]
0x18000c2cf  jnz     short loc_18000C2EB
0x18000c2d1  lea     rcx, aSetautodetectp_0; "SetAutoDetectProxyFlagForUser"
0x18000c2d8  call    ?_RunAsImpersonatedUser@@YAJPEBG@Z; _RunAsImpersonatedUser(ushort const *)
0x18000c2dd  mov     ecx, eax
0x18000c2df  sar     ecx, 1Fh
0x18000c2e2  and     ecx, 1
0x18000c2e5  inc     ecx
0x18000c2e7  mov     [rbx], ecx
0x18000c2e9  jmp     short loc_18000C2F7
0x18000c2eb  mov     eax, 80004001h
0x18000c2f0  jmp     short loc_18000C2F7
0x18000c2f2  mov     eax, 80070057h
0x18000c2f7  add     rsp, 20h
0x18000c2fb  pop     rbx
0x18000c2fc  retn
```
