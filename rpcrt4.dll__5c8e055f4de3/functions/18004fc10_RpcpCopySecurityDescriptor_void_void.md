# RpcpCopySecurityDescriptor(void *,void * *)

- ea: `0x18004fc10`
- end: `0x18004fcf2`
- name: `?RpcpCopySecurityDescriptor@@YAJPEAXPEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(void *Src, void **)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004f938`
- `0x18008e148`
- `0x18009398c`
- `0x180093a50`
- `0x180094444`
- `0x180096ce8`
- `0x1800a4380`
- `0x1800a9100`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18004fc10`
- `0x1800ca031`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fcb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fcb4`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004fcae`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004fcd9`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004fcae`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004fcd9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004fc49`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004fc49`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18004fc34`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18004fc34`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004fc61`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004fc61`

## pseudocode

```c
__int64 __fastcall RpcpCopySecurityDescriptor(void *Src, void **a2)
{
  void *v4; // rax
  void *v6; // rax
  DWORD dwRevision[4]; // [rsp+20h] [rbp-10h] BYREF
  WORD pControl; // [rsp+50h] [rbp+20h] BYREF
  size_t Size; // [rsp+58h] [rbp+28h] BYREF

  pControl = 0;
  dwRevision[0] = 0;
  LODWORD(Size) = 0;
  if ( !IsValidSecurityDescriptor(Src) || !GetSecurityDescriptorControl(Src, &pControl, dwRevision) )
    return 1338;
  if ( (pControl & 0x8000u) == 0 )
  {
    LODWORD(Size) = 0;
    MakeSelfRelativeSD(Src, 0, (LPDWORD)&Size);
    if ( GetLastError() == 122 )
    {
      v6 = AllocWrapper((unsigned int)Size);
      *a2 = v6;
      if ( v6 )
      {
        if ( MakeSelfRelativeSD(Src, v6, (LPDWORD)&Size) )
          return 0;
        FreeWrapper(*a2);
      }
      return 14;
    }
    return 1338;
  }
  LODWORD(Size) = GetSecurityDescriptorLength(Src);
  v4 = AllocWrapper((unsigned int)Size);
  *a2 = v4;
  if ( v4 )
  {
    memcpy_0(v4, Src, (unsigned int)Size);
    return 0;
  }
  return 14;
}

```

## disassembly

```asm
0x18004fc10  mov     [rsp-8+arg_0], rbx
0x18004fc15  mov     [rsp-8+arg_8], rdi
0x18004fc1a  push    rbp
0x18004fc1b  mov     rbp, rsp
0x18004fc1e  sub     rsp, 30h
0x18004fc22  xor     eax, eax
0x18004fc24  mov     rdi, rdx
0x18004fc27  mov     [rbp+pControl], ax
0x18004fc2b  mov     rbx, rcx
0x18004fc2e  mov     [rbp+dwRevision], eax
0x18004fc31  mov     dword ptr [rbp+Size], eax
0x18004fc34  call    cs:__imp_IsValidSecurityDescriptor
0x18004fc3a  test    eax, eax
0x18004fc3c  jz      short loc_18004FC9A
0x18004fc3e  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18004fc42  mov     rcx, rbx; pSecurityDescriptor
0x18004fc45  lea     rdx, [rbp+pControl]; pControl
0x18004fc49  call    cs:__imp_GetSecurityDescriptorControl
0x18004fc4f  test    eax, eax
0x18004fc51  jz      short loc_18004FC9A
0x18004fc53  mov     eax, 8000h
0x18004fc58  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18004fc5b  test    [rbp+pControl], ax
0x18004fc5f  jz      short loc_18004FCA1
0x18004fc61  call    cs:__imp_GetSecurityDescriptorLength
0x18004fc67  mov     ecx, eax; dwBytes
0x18004fc69  mov     dword ptr [rbp+Size], ecx
0x18004fc6c  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18004fc71  mov     [rdi], rax
0x18004fc74  test    rax, rax
0x18004fc77  jz      short loc_18004FCEB
0x18004fc79  mov     r8d, dword ptr [rbp+Size]; Size
0x18004fc7d  mov     rdx, rbx; Src
0x18004fc80  mov     rcx, rax; void *
0x18004fc83  call    memcpy_0
0x18004fc88  xor     eax, eax
0x18004fc8a  mov     rbx, [rsp+30h+arg_0]
0x18004fc8f  mov     rdi, [rsp+30h+arg_8]
0x18004fc94  add     rsp, 30h
0x18004fc98  pop     rbp
0x18004fc99  retn
0x18004fc9a  mov     eax, 53Ah
0x18004fc9f  jmp     short loc_18004FC8A
0x18004fca1  lea     r8, [rbp+Size]; lpdwBufferLength
0x18004fca5  mov     dword ptr [rbp+Size], 0
0x18004fcac  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18004fcae  call    cs:__imp_MakeSelfRelativeSD
0x18004fcb4  call    cs:__imp_GetLastError
0x18004fcba  cmp     eax, 7Ah ; 'z'
0x18004fcbd  jnz     short loc_18004FC9A
0x18004fcbf  mov     ecx, dword ptr [rbp+Size]; dwBytes
0x18004fcc2  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18004fcc7  mov     [rdi], rax
0x18004fcca  test    rax, rax
0x18004fccd  jz      short loc_18004FCEB
0x18004fccf  lea     r8, [rbp+Size]; lpdwBufferLength
0x18004fcd3  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18004fcd6  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18004fcd9  call    cs:__imp_MakeSelfRelativeSD
0x18004fcdf  test    eax, eax
0x18004fce1  jnz     short loc_18004FC88
0x18004fce3  mov     rcx, [rdi]; lpMem
0x18004fce6  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004fceb  mov     eax, 0Eh
0x18004fcf0  jmp     short loc_18004FC8A
```
