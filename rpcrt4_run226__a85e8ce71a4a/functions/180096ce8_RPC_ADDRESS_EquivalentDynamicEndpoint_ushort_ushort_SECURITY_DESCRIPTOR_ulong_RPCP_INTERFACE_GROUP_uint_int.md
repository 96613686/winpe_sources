# RPC_ADDRESS::EquivalentDynamicEndpoint(ushort *,ushort *,_SECURITY_DESCRIPTOR *,ulong,RPCP_INTERFACE_GROUP *,uint,int *)

- ea: `0x180096ce8`
- end: `0x180096e22`
- name: `?EquivalentDynamicEndpoint@RPC_ADDRESS@@QEAAJPEAG0PEAU_SECURITY_DESCRIPTOR@@KPEAVRPCP_INTERFACE_GROUP@@IPEAH@Z`
- size: `314`
- prototype: `__int64 __fastcall(RPC_ADDRESS *this, unsigned __int16 *, unsigned __int16 *, struct _SECURITY_DESCRIPTOR *, unsigned int, struct RPCP_INTERFACE_GROUP *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006d1e4`
- `0x1800b3cd0`

## callees

- `0x180022870`
- `0x18004fc10`
- `0x180096ce8`
- `0x1800ca025`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180096d3d`
- `ntdll!_wcsicmp` at `0x180096deb`
- `ntdll!_wcsicmp` at `0x180096e03`
- `ntdll!_wcsicmp` at `0x180096d3d`
- `ntdll!_wcsicmp` at `0x180096deb`
- `ntdll!_wcsicmp` at `0x180096e03`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180096d82`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180096d91`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180096d82`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180096d91`

## pseudocode

```c
__int64 __fastcall RPC_ADDRESS::EquivalentDynamicEndpoint(
        RPC_ADDRESS *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _SECURITY_DESCRIPTOR *a4,
        unsigned int a5,
        struct RPCP_INTERFACE_GROUP *a6,
        unsigned int a7,
        int *a8)
{
  int *v8; // r14
  PSECURITY_DESCRIPTOR v9; // rdi
  struct RPCP_INTERFACE_GROUP *v10; // rax
  __int64 v14; // rax
  bool v15; // zf
  int v16; // eax
  size_t SecurityDescriptorLength; // rsi
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp+8h] BYREF

  v8 = a8;
  v9 = 0;
  v10 = (struct RPCP_INTERFACE_GROUP *)*((_QWORD *)this + 19);
  pSecurityDescriptor = 0;
  *a8 = 0;
  if ( a6 == v10 )
  {
    v14 = *((_QWORD *)this + 6);
    if ( a2 )
    {
      if ( !v14 )
        return 0;
      v15 = _wcsicmp(*((const wchar_t **)this + 6), a2) == 0;
    }
    else
    {
      v15 = v14 == 0;
    }
    if ( v15
      && !_wcsicmp(*((const wchar_t **)this + 5), a3)
      && *((_DWORD *)this + 37) == a5
      && ((a5 & 0x10) == 0 || _wcsicmp(*((const wchar_t **)this + 5), L"ncacn_ip_tcp") || *((_DWORD *)this + 33) == a7) )
    {
      if ( *((_QWORD *)this + 17) )
      {
        if ( !a4 )
          return 0;
        v16 = RpcpCopySecurityDescriptor(a4, &pSecurityDescriptor);
        v9 = pSecurityDescriptor;
        if ( v16 )
          goto LABEL_12;
        SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
        if ( (_DWORD)SecurityDescriptorLength != GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)this + 17))
          || memcmp_0(v9, *((const void **)this + 17), SecurityDescriptorLength) )
        {
          goto LABEL_12;
        }
      }
      else if ( a4 )
      {
        return 0;
      }
      *v8 = 1;
LABEL_12:
      if ( v9 )
        FreeWrapper(v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180096ce8  mov     [rsp+arg_8], rbx
0x180096ced  mov     [rsp+arg_10], rbp
0x180096cf2  push    rsi
0x180096cf3  push    rdi
0x180096cf4  push    r14
0x180096cf6  sub     rsp, 20h
0x180096cfa  mov     r14, [rsp+38h+arg_38]
0x180096cff  xor     edi, edi
0x180096d01  mov     rax, [rcx+98h]
0x180096d08  mov     rsi, r9
0x180096d0b  mov     rbp, r8
0x180096d0e  mov     rbx, rcx
0x180096d11  mov     [rsp+38h+pSecurityDescriptor], rdi
0x180096d16  mov     [r14], edi
0x180096d19  cmp     [rsp+38h+arg_28], rax
0x180096d1e  jnz     loc_180096DA8
0x180096d24  mov     rax, [rcx+30h]
0x180096d28  test    rdx, rdx
0x180096d2b  jnz     loc_180096DE3
0x180096d31  test    rax, rax
0x180096d34  jnz     short loc_180096DA8
0x180096d36  mov     rcx, [rbx+28h]; String1
0x180096d3a  mov     rdx, rbp; String2
0x180096d3d  call    cs:__imp__wcsicmp
0x180096d43  test    eax, eax
0x180096d45  jnz     short loc_180096DA8
0x180096d47  mov     eax, [rsp+38h+arg_20]
0x180096d4b  cmp     [rbx+94h], eax
0x180096d51  jnz     short loc_180096DA8
0x180096d53  test    al, 10h
0x180096d55  jnz     loc_180096DF8
0x180096d5b  cmp     [rbx+88h], rdi
0x180096d62  jz      short loc_180096DDC
0x180096d64  test    rsi, rsi
0x180096d67  jz      short loc_180096DA8
0x180096d69  lea     rdx, [rsp+38h+pSecurityDescriptor]; void **
0x180096d6e  mov     rcx, rsi; Src
0x180096d71  call    ?RpcpCopySecurityDescriptor@@YAJPEAXPEAPEAX@Z; RpcpCopySecurityDescriptor(void *,void * *)
0x180096d76  mov     rdi, [rsp+38h+pSecurityDescriptor]
0x180096d7b  test    eax, eax
0x180096d7d  jnz     short loc_180096D9B
0x180096d7f  mov     rcx, rdi; pSecurityDescriptor
0x180096d82  call    cs:__imp_GetSecurityDescriptorLength
0x180096d88  mov     rcx, [rbx+88h]; pSecurityDescriptor
0x180096d8f  mov     esi, eax
0x180096d91  call    cs:__imp_GetSecurityDescriptorLength
0x180096d97  cmp     esi, eax
0x180096d99  jz      short loc_180096DBD
0x180096d9b  test    rdi, rdi
0x180096d9e  jz      short loc_180096DA8
0x180096da0  mov     rcx, rdi; lpMem
0x180096da3  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180096da8  mov     rbx, [rsp+38h+arg_8]
0x180096dad  xor     eax, eax
0x180096daf  mov     rbp, [rsp+38h+arg_10]
0x180096db4  add     rsp, 20h
0x180096db8  pop     r14
0x180096dba  pop     rdi
0x180096dbb  pop     rsi
0x180096dbc  retn
0x180096dbd  mov     rdx, [rbx+88h]; Buf2
0x180096dc4  mov     r8, rsi; Size
0x180096dc7  mov     rcx, rdi; Buf1
0x180096dca  call    memcmp_0
0x180096dcf  test    eax, eax
0x180096dd1  jnz     short loc_180096D9B
0x180096dd3  mov     dword ptr [r14], 1
0x180096dda  jmp     short loc_180096D9B
0x180096ddc  test    rsi, rsi
0x180096ddf  jz      short loc_180096DD3
0x180096de1  jmp     short loc_180096DA8
0x180096de3  test    rax, rax
0x180096de6  jz      short loc_180096DA8
0x180096de8  mov     rcx, rax; String1
0x180096deb  call    cs:__imp__wcsicmp
0x180096df1  test    eax, eax
0x180096df3  jmp     loc_180096D34
0x180096df8  mov     rcx, [rbx+28h]; String1
0x180096dfc  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180096e03  call    cs:__imp__wcsicmp
0x180096e09  test    eax, eax
0x180096e0b  jnz     loc_180096D5B
0x180096e11  mov     eax, [rsp+38h+arg_30]
0x180096e15  cmp     [rbx+84h], eax
0x180096e1b  jnz     short loc_180096DA8
0x180096e1d  jmp     loc_180096D5B
```
