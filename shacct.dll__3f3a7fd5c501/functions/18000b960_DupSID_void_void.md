# DupSID(void *,void * *)

- ea: `0x18000b960`
- end: `0x18000b9cb`
- name: `?DupSID@@YAJPEAXPEAPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800063b0`
- `0x180007070`
- `0x180007970`
- `0x18000e3a0`
- `0x1800145c4`

## callees

- `0x18000b960`
- `0x18000bcc0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b996`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b996`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b976`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b980`

## pseudocode

```c
__int64 __fastcall DupSID(PSID pSourceSid, void **a2)
{
  DWORD LengthSid; // ebp
  void *v5; // rax
  void *v6; // rbx
  unsigned int Error; // edi

  *a2 = 0;
  LengthSid = GetLengthSid(pSourceSid);
  v5 = CoTaskMemAlloc(LengthSid);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  if ( CopySid(LengthSid, v5, pSourceSid) )
  {
    *a2 = v6;
    v6 = 0;
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
  }
  CoTaskMemFree(v6);
  return Error;
}

```

## disassembly

```asm
0x18000b960  push    rbx
0x18000b962  push    rbp
0x18000b963  push    rsi
0x18000b964  push    rdi
0x18000b965  sub     rsp, 28h
0x18000b969  mov     rdi, rdx
0x18000b96c  mov     qword ptr [rdx], 0
0x18000b973  mov     rsi, rcx
0x18000b976  call    cs:__imp_GetLengthSid
0x18000b97c  mov     ecx, eax; cb
0x18000b97e  mov     ebp, eax
0x18000b980  call    cs:__imp_CoTaskMemAlloc
0x18000b986  mov     rbx, rax
0x18000b989  test    rax, rax
0x18000b98c  jz      short loc_18000B9BD
0x18000b98e  mov     r8, rsi; pSourceSid
0x18000b991  mov     rdx, rax; pDestinationSid
0x18000b994  mov     ecx, ebp; nDestinationSidLength
0x18000b996  call    cs:__imp_CopySid
0x18000b99c  test    eax, eax
0x18000b99e  jz      short loc_18000B9A9
0x18000b9a0  mov     [rdi], rbx
0x18000b9a3  xor     ebx, ebx
0x18000b9a5  xor     edi, edi
0x18000b9a7  jmp     short loc_18000B9B0
0x18000b9a9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b9ae  mov     edi, eax
0x18000b9b0  mov     rcx, rbx; pv
0x18000b9b3  call    cs:__imp_CoTaskMemFree
0x18000b9b9  mov     eax, edi
0x18000b9bb  jmp     short loc_18000B9C2
0x18000b9bd  mov     eax, 8007000Eh
0x18000b9c2  add     rsp, 28h
0x18000b9c6  pop     rdi
0x18000b9c7  pop     rsi
0x18000b9c8  pop     rbp
0x18000b9c9  pop     rbx
0x18000b9ca  retn
```
