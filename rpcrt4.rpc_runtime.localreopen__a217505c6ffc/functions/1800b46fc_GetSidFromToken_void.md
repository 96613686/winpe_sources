# GetSidFromToken(void *)

- ea: `0x1800b46fc`
- end: `0x1800b47ef`
- name: `?GetSidFromToken@@YAPEAXPEAX@Z`
- size: `243`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b44fc`

## callees

- `0x1800b46fc`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800b473e`
- `KERNELBASE!LocalAlloc` at `0x1800b4793`
- `KERNELBASE!LocalAlloc` at `0x1800b473e`
- `KERNELBASE!LocalAlloc` at `0x1800b4793`
- `ntdll!RtlCopySid` at `0x1800b47af`
- `ntdll!RtlCopySid` at `0x1800b47af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b47c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b47d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b47c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b47d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b4723`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b476d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b4723`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b476d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b4780`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b4780`

## pseudocode

```c
void *__fastcall GetSidFromToken(HANDLE TokenHandle)
{
  void *v1; // rsi
  PSID *v3; // rbx
  ULONG LengthSid; // ebp
  HLOCAL v5; // rax
  void *v6; // rdi
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v3 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v3 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
      {
        LengthSid = GetLengthSid(*v3);
        v5 = LocalAlloc(0x40u, LengthSid);
        v6 = v5;
        if ( v5 )
        {
          if ( RtlCopySid(LengthSid, v5, *v3) )
            LocalFree(v6);
          else
            v1 = v6;
        }
      }
      LocalFree(v3);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800b46fc  push    rbx
0x1800b46fe  push    rbp
0x1800b46ff  push    rsi
0x1800b4700  push    rdi
0x1800b4701  sub     rsp, 38h
0x1800b4705  xor     esi, esi
0x1800b4707  lea     rax, [rsp+58h+TokenInformationLength]
0x1800b470c  xor     r9d, r9d; TokenInformationLength
0x1800b470f  mov     [rsp+58h+TokenInformationLength], esi
0x1800b4713  xor     r8d, r8d; TokenInformation
0x1800b4716  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800b471b  mov     rdi, rcx
0x1800b471e  lea     ebp, [rsi+1]
0x1800b4721  mov     edx, ebp; TokenInformationClass
0x1800b4723  call    cs:__imp_GetTokenInformation
0x1800b472a  nop     dword ptr [rax+rax+00h]
0x1800b472f  test    eax, eax
0x1800b4731  jnz     loc_1800B47E2
0x1800b4737  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x1800b473b  lea     ecx, [rsi+40h]; uFlags
0x1800b473e  call    cs:__imp_LocalAlloc
0x1800b4745  nop     dword ptr [rax+rax+00h]
0x1800b474a  mov     rbx, rax
0x1800b474d  test    rax, rax
0x1800b4750  jz      loc_1800B47E2
0x1800b4756  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800b475b  lea     rax, [rsp+58h+TokenInformationLength]
0x1800b4760  mov     r8, rbx; TokenInformation
0x1800b4763  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800b4768  mov     edx, ebp; TokenInformationClass
0x1800b476a  mov     rcx, rdi; TokenHandle
0x1800b476d  call    cs:__imp_GetTokenInformation
0x1800b4774  nop     dword ptr [rax+rax+00h]
0x1800b4779  test    eax, eax
0x1800b477b  jz      short loc_1800B47D3
0x1800b477d  mov     rcx, [rbx]; pSid
0x1800b4780  call    cs:__imp_GetLengthSid
0x1800b4787  nop     dword ptr [rax+rax+00h]
0x1800b478c  mov     edx, eax; uBytes
0x1800b478e  lea     ecx, [rsi+40h]; uFlags
0x1800b4791  mov     ebp, eax
0x1800b4793  call    cs:__imp_LocalAlloc
0x1800b479a  nop     dword ptr [rax+rax+00h]
0x1800b479f  mov     rdi, rax
0x1800b47a2  test    rax, rax
0x1800b47a5  jz      short loc_1800B47D3
0x1800b47a7  mov     r8, [rbx]; SourceSid
0x1800b47aa  mov     rdx, rax; DestinationSid
0x1800b47ad  mov     ecx, ebp; DestinationSidLength
0x1800b47af  call    cs:__imp_RtlCopySid
0x1800b47b6  nop     dword ptr [rax+rax+00h]
0x1800b47bb  test    eax, eax
0x1800b47bd  jnz     short loc_1800B47C4
0x1800b47bf  mov     rsi, rdi
0x1800b47c2  jmp     short loc_1800B47D3
0x1800b47c4  mov     rcx, rdi; hMem
0x1800b47c7  call    cs:__imp_LocalFree
0x1800b47ce  nop     dword ptr [rax+rax+00h]
0x1800b47d3  mov     rcx, rbx; hMem
0x1800b47d6  call    cs:__imp_LocalFree
0x1800b47dd  nop     dword ptr [rax+rax+00h]
0x1800b47e2  mov     rax, rsi
0x1800b47e5  add     rsp, 38h
0x1800b47e9  pop     rdi
0x1800b47ea  pop     rsi
0x1800b47eb  pop     rbp
0x1800b47ec  pop     rbx
0x1800b47ed  retn
```
