# NetrpSetFileSecurity

- ea: `0x180020350`
- end: `0x18002043a`
- name: `NetrpSetFileSecurity`
- size: `234`
- prototype: `__int64 __fastcall(PCWSTR, PCWSTR SourceString, const WCHAR *, SECURITY_INFORMATION, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001fdc4`
- `0x180020350`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800203fa`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800203fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020404`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020422`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800203e5`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800203e5`
- `RPCRT4!RpcImpersonateClient` at `0x1800203d0`
- `RPCRT4!RpcImpersonateClient` at `0x1800203d0`
- `RPCRT4!RpcRevertToSelf` at `0x180020417`
- `RPCRT4!RpcRevertToSelf` at `0x180020417`

## pseudocode

```c
__int64 __fastcall NetrpSetFileSecurity(
        PCWSTR a1,
        PCWSTR SourceString,
        const WCHAR *a3,
        SECURITY_INFORMATION a4,
        __int64 a5)
{
  int v9; // edx
  int v10; // ecx
  DWORD LastError; // ebx

  if ( !*(_QWORD *)(a5 + 8) && *(_DWORD *)a5 )
    return 87;
  v9 = ((a4 & 3) != 0 ? 0x80000 : 0) | 0x40000;
  if ( (a4 & 4) == 0 )
    v9 = (a4 & 3) != 0 ? 0x80000 : 0;
  v10 = v9 | 0x1000000;
  if ( (a4 & 8) == 0 )
    v10 = v9;
  LastError = AdtCheckShareAccessAndGetFullPath(SourceString, a1, a3, v10);
  if ( !LastError )
  {
    LastError = RpcImpersonateClient(0);
    if ( !LastError )
    {
      if ( RtlValidRelativeSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a5 + 8), *(_DWORD *)a5, a4) )
      {
        if ( SetFileSecurityW(0, a4, *(PSECURITY_DESCRIPTOR *)(a5 + 8)) )
          LastError = 0;
        else
          LastError = GetLastError();
      }
      else
      {
        LastError = 1338;
      }
      RpcRevertToSelf();
    }
    LocalFree(0);
  }
  return LastError;
}

```

## disassembly

```asm
0x180020350  mov     [rsp+arg_0], rbx
0x180020355  mov     [rsp+arg_8], rsi
0x18002035a  push    rdi
0x18002035b  sub     rsp, 40h
0x18002035f  mov     rdi, [rsp+48h+arg_20]
0x180020364  mov     esi, r9d
0x180020367  mov     r10, rdx
0x18002036a  mov     [rsp+48h+lpFileName], 0
0x180020373  mov     r11, rcx
0x180020376  cmp     qword ptr [rdi+8], 0
0x18002037b  jnz     short loc_18002038C
0x18002037d  cmp     dword ptr [rdi], 0
0x180020380  jbe     short loc_18002038C
0x180020382  mov     eax, 57h ; 'W'
0x180020387  jmp     loc_18002042A
0x18002038c  mov     eax, esi
0x18002038e  lea     r9, [rsp+48h+lpFileName]
0x180020393  and     al, 3
0x180020395  neg     al
0x180020397  sbb     ecx, ecx
0x180020399  and     ecx, 80000h
0x18002039f  mov     edx, ecx
0x1800203a1  bts     edx, 12h
0x1800203a5  test    sil, 4
0x1800203a9  cmovz   edx, ecx
0x1800203ac  mov     ecx, edx
0x1800203ae  bts     ecx, 18h
0x1800203b2  test    sil, 8
0x1800203b6  cmovz   ecx, edx
0x1800203b9  mov     rdx, r11; PCWSTR
0x1800203bc  mov     [rsp+48h+var_28], ecx; int
0x1800203c0  mov     rcx, r10; SourceString
0x1800203c3  call    AdtCheckShareAccessAndGetFullPath
0x1800203c8  mov     ebx, eax
0x1800203ca  test    eax, eax
0x1800203cc  jnz     short loc_180020428
0x1800203ce  xor     ecx, ecx; BindingHandle
0x1800203d0  call    cs:__imp_RpcImpersonateClient
0x1800203d6  mov     ebx, eax
0x1800203d8  test    eax, eax
0x1800203da  jnz     short loc_18002041D
0x1800203dc  mov     edx, [rdi]; SecurityDescriptorLength
0x1800203de  mov     r8d, esi; RequiredInformation
0x1800203e1  mov     rcx, [rdi+8]; SecurityDescriptorInput
0x1800203e5  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800203eb  test    al, al
0x1800203ed  jz      short loc_180020412
0x1800203ef  mov     r8, [rdi+8]; pSecurityDescriptor
0x1800203f3  mov     edx, esi; SecurityInformation
0x1800203f5  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x1800203fa  call    cs:__imp_SetFileSecurityW
0x180020400  test    eax, eax
0x180020402  jnz     short loc_18002040E
0x180020404  call    cs:__imp_GetLastError
0x18002040a  mov     ebx, eax
0x18002040c  jmp     short loc_180020417
0x18002040e  xor     ebx, ebx
0x180020410  jmp     short loc_180020417
0x180020412  mov     ebx, 53Ah
0x180020417  call    cs:__imp_RpcRevertToSelf
0x18002041d  mov     rcx, [rsp+48h+lpFileName]; hMem
0x180020422  call    cs:__imp_LocalFree
0x180020428  mov     eax, ebx
0x18002042a  mov     rbx, [rsp+48h+arg_0]
0x18002042f  mov     rsi, [rsp+48h+arg_8]
0x180020434  add     rsp, 40h
0x180020438  pop     rdi
0x180020439  retn
```
