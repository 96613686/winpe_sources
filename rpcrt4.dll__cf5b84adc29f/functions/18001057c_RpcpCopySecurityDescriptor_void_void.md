# RpcpCopySecurityDescriptor(void *,void * *)

- ea: `0x18001057c`
- end: `0x180010687`
- name: `?RpcpCopySecurityDescriptor@@YAJPEAXPEAPEAX@Z`
- size: `267`
- prototype: `__int64 __fastcall(void *Src, void **)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010244`
- `0x18006f3dc`
- `0x18006f71c`
- `0x180091c50`
- `0x180096e78`
- `0x18009a570`
- `0x1800a7a44`
- `0x1800aca60`

## callees

- `0x18001057c`
- `0x180023020`
- `0x180023a40`
- `0x1800cec91`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001063d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001063d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180010631`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180010668`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180010631`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180010668`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800105bb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800105bb`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800105a0`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800105a0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800105d9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800105d9`

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
0x18001057c  mov     [rsp-8+arg_0], rbx
0x180010581  mov     [rsp-8+arg_8], rdi
0x180010586  push    rbp
0x180010587  mov     rbp, rsp
0x18001058a  sub     rsp, 30h
0x18001058e  xor     eax, eax
0x180010590  mov     rdi, rdx
0x180010593  mov     [rbp+pControl], ax
0x180010597  mov     rbx, rcx
0x18001059a  mov     [rbp+dwRevision], eax
0x18001059d  mov     dword ptr [rbp+Size], eax
0x1800105a0  call    cs:__imp_IsValidSecurityDescriptor
0x1800105a7  nop     dword ptr [rax+rax+00h]
0x1800105ac  test    eax, eax
0x1800105ae  jz      short loc_18001061D
0x1800105b0  lea     r8, [rbp+dwRevision]; lpdwRevision
0x1800105b4  mov     rcx, rbx; pSecurityDescriptor
0x1800105b7  lea     rdx, [rbp+pControl]; pControl
0x1800105bb  call    cs:__imp_GetSecurityDescriptorControl
0x1800105c2  nop     dword ptr [rax+rax+00h]
0x1800105c7  test    eax, eax
0x1800105c9  jz      short loc_18001061D
0x1800105cb  mov     eax, 8000h
0x1800105d0  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1800105d3  test    [rbp+pControl], ax
0x1800105d7  jz      short loc_180010624
0x1800105d9  call    cs:__imp_GetSecurityDescriptorLength
0x1800105e0  nop     dword ptr [rax+rax+00h]
0x1800105e5  mov     ecx, eax; dwBytes
0x1800105e7  mov     dword ptr [rbp+Size], ecx
0x1800105ea  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800105ef  mov     [rdi], rax
0x1800105f2  test    rax, rax
0x1800105f5  jz      loc_180010680
0x1800105fb  mov     r8d, dword ptr [rbp+Size]; Size
0x1800105ff  mov     rdx, rbx; Src
0x180010602  mov     rcx, rax; void *
0x180010605  call    memcpy_0
0x18001060a  xor     eax, eax
0x18001060c  mov     rbx, [rsp+30h+arg_0]
0x180010611  mov     rdi, [rsp+30h+arg_8]
0x180010616  add     rsp, 30h
0x18001061a  pop     rbp
0x18001061b  retn
0x18001061d  mov     eax, 53Ah
0x180010622  jmp     short loc_18001060C
0x180010624  lea     r8, [rbp+Size]; lpdwBufferLength
0x180010628  mov     dword ptr [rbp+Size], 0
0x18001062f  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180010631  call    cs:__imp_MakeSelfRelativeSD
0x180010638  nop     dword ptr [rax+rax+00h]
0x18001063d  call    cs:__imp_GetLastError
0x180010644  nop     dword ptr [rax+rax+00h]
0x180010649  cmp     eax, 7Ah ; 'z'
0x18001064c  jnz     short loc_18001061D
0x18001064e  mov     ecx, dword ptr [rbp+Size]; dwBytes
0x180010651  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180010656  mov     [rdi], rax
0x180010659  test    rax, rax
0x18001065c  jz      short loc_180010680
0x18001065e  lea     r8, [rbp+Size]; lpdwBufferLength
0x180010662  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180010665  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180010668  call    cs:__imp_MakeSelfRelativeSD
0x18001066f  nop     dword ptr [rax+rax+00h]
0x180010674  test    eax, eax
0x180010676  jnz     short loc_18001060A
0x180010678  mov     rcx, [rdi]; lpMem
0x18001067b  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180010680  mov     eax, 0Eh
0x180010685  jmp     short loc_18001060C
```
