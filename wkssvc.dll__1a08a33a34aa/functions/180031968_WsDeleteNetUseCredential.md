# WsDeleteNetUseCredential

- ea: `0x180031968`
- end: `0x1800319c3`
- name: `WsDeleteNetUseCredential`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001750`

## callees

- `0x18001fbd0`
- `0x180031774`
- `0x180031968`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18003199d`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18003199d`

## pseudocode

```c
int __fastcall WsDeleteNetUseCredential(__int64 a1, DWORD a2)
{
  int result; // eax
  WCHAR TargetName[344]; // [rsp+20h] [rbp-2C8h] BYREF

  result = ComputeTargetNameFromUncName(a1, TargetName);
  if ( result )
    return CredDeleteW(TargetName, a2, 0);
  return result;
}

```

## disassembly

```asm
0x180031968  push    rbx
0x18003196a  sub     rsp, 2E0h
0x180031971  mov     rax, cs:__security_cookie
0x180031978  xor     rax, rsp
0x18003197b  mov     [rsp+2E8h+var_18], rax
0x180031983  mov     ebx, edx
0x180031985  lea     rdx, [rsp+2E8h+TargetName]
0x18003198a  call    ComputeTargetNameFromUncName
0x18003198f  test    eax, eax
0x180031991  jz      short loc_1800319A9
0x180031993  xor     r8d, r8d; Flags
0x180031996  lea     rcx, [rsp+2E8h+TargetName]; TargetName
0x18003199b  mov     edx, ebx; Type
0x18003199d  call    cs:__imp_CredDeleteW
0x1800319a4  nop     dword ptr [rax+rax+00h]
0x1800319a9  mov     rcx, [rsp+2E8h+var_18]
0x1800319b1  xor     rcx, rsp; StackCookie
0x1800319b4  call    __security_check_cookie
0x1800319b9  add     rsp, 2E0h
0x1800319c0  pop     rbx
0x1800319c1  retn
```
