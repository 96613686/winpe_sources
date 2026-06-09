# RPC_ADDRESS::EquivalentDynamicEndpoint(ushort *,ushort *,_SECURITY_DESCRIPTOR *,ulong,RPCP_INTERFACE_GROUP *,uint,int *)

- ea: `0x18009a570`
- end: `0x18009a6d5`
- name: `?EquivalentDynamicEndpoint@RPC_ADDRESS@@QEAAJPEAG0PEAU_SECURITY_DESCRIPTOR@@KPEAVRPCP_INTERFACE_GROUP@@IPEAH@Z`
- size: `357`
- prototype: `int(RPC_ADDRESS *__hidden this, unsigned __int16 *, unsigned __int16 *, struct _SECURITY_DESCRIPTOR *, unsigned int, struct RPCP_INTERFACE_GROUP *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008f718`
- `0x1800b7d18`

## callees

- `0x18001057c`
- `0x180023a40`
- `0x18009a570`
- `0x1800cec85`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18009a5c9`
- `ntdll!_wcsicmp` at `0x18009a68e`
- `ntdll!_wcsicmp` at `0x18009a6ac`
- `ntdll!_wcsicmp` at `0x18009a5c9`
- `ntdll!_wcsicmp` at `0x18009a68e`
- `ntdll!_wcsicmp` at `0x18009a6ac`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18009a618`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18009a62d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18009a618`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18009a62d`

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
0x18009a570  mov     [rsp+arg_8], rbx
0x18009a575  mov     [rsp+arg_10], rbp
0x18009a57a  push    rsi
0x18009a57b  push    rdi
0x18009a57c  push    r14
0x18009a57e  sub     rsp, 20h
0x18009a582  mov     r14, [rsp+38h+arg_38]
0x18009a587  xor     edi, edi
0x18009a589  mov     rax, [rcx+98h]
0x18009a590  mov     rsi, r9
0x18009a593  mov     rbp, r8
0x18009a596  mov     rbx, rcx
0x18009a599  mov     [rsp+38h+pSecurityDescriptor], rdi
0x18009a59e  mov     [r14], edi
0x18009a5a1  cmp     [rsp+38h+arg_28], rax
0x18009a5a6  jnz     loc_18009A64A
0x18009a5ac  mov     rax, [rcx+30h]
0x18009a5b0  test    rdx, rdx
0x18009a5b3  jnz     loc_18009A686
0x18009a5b9  test    rax, rax
0x18009a5bc  jnz     loc_18009A64A
0x18009a5c2  mov     rcx, [rbx+28h]; String1
0x18009a5c6  mov     rdx, rbp; String2
0x18009a5c9  call    cs:__imp__wcsicmp
0x18009a5d0  nop     dword ptr [rax+rax+00h]
0x18009a5d5  test    eax, eax
0x18009a5d7  jnz     short loc_18009A64A
0x18009a5d9  mov     eax, [rsp+38h+arg_20]
0x18009a5dd  cmp     [rbx+94h], eax
0x18009a5e3  jnz     short loc_18009A64A
0x18009a5e5  test    al, 10h
0x18009a5e7  jnz     loc_18009A6A1
0x18009a5ed  cmp     [rbx+88h], rdi
0x18009a5f4  jz      loc_18009A67F
0x18009a5fa  test    rsi, rsi
0x18009a5fd  jz      short loc_18009A64A
0x18009a5ff  lea     rdx, [rsp+38h+pSecurityDescriptor]; void **
0x18009a604  mov     rcx, rsi; Src
0x18009a607  call    ?RpcpCopySecurityDescriptor@@YAJPEAXPEAPEAX@Z; RpcpCopySecurityDescriptor(void *,void * *)
0x18009a60c  mov     rdi, [rsp+38h+pSecurityDescriptor]
0x18009a611  test    eax, eax
0x18009a613  jnz     short loc_18009A63D
0x18009a615  mov     rcx, rdi; pSecurityDescriptor
0x18009a618  call    cs:__imp_GetSecurityDescriptorLength
0x18009a61f  nop     dword ptr [rax+rax+00h]
0x18009a624  mov     rcx, [rbx+88h]; pSecurityDescriptor
0x18009a62b  mov     esi, eax
0x18009a62d  call    cs:__imp_GetSecurityDescriptorLength
0x18009a634  nop     dword ptr [rax+rax+00h]
0x18009a639  cmp     esi, eax
0x18009a63b  jz      short loc_18009A660
0x18009a63d  test    rdi, rdi
0x18009a640  jz      short loc_18009A64A
0x18009a642  mov     rcx, rdi; lpMem
0x18009a645  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009a64a  mov     rbx, [rsp+38h+arg_8]
0x18009a64f  xor     eax, eax
0x18009a651  mov     rbp, [rsp+38h+arg_10]
0x18009a656  add     rsp, 20h
0x18009a65a  pop     r14
0x18009a65c  pop     rdi
0x18009a65d  pop     rsi
0x18009a65e  retn
0x18009a660  mov     rdx, [rbx+88h]; Buf2
0x18009a667  mov     r8, rsi; Size
0x18009a66a  mov     rcx, rdi; Buf1
0x18009a66d  call    memcmp_0
0x18009a672  test    eax, eax
0x18009a674  jnz     short loc_18009A63D
0x18009a676  mov     dword ptr [r14], 1
0x18009a67d  jmp     short loc_18009A63D
0x18009a67f  test    rsi, rsi
0x18009a682  jz      short loc_18009A676
0x18009a684  jmp     short loc_18009A64A
0x18009a686  test    rax, rax
0x18009a689  jz      short loc_18009A64A
0x18009a68b  mov     rcx, rax; String1
0x18009a68e  call    cs:__imp__wcsicmp
0x18009a695  nop     dword ptr [rax+rax+00h]
0x18009a69a  test    eax, eax
0x18009a69c  jmp     loc_18009A5BC
0x18009a6a1  mov     rcx, [rbx+28h]; String1
0x18009a6a5  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x18009a6ac  call    cs:__imp__wcsicmp
0x18009a6b3  nop     dword ptr [rax+rax+00h]
0x18009a6b8  test    eax, eax
0x18009a6ba  jnz     loc_18009A5ED
0x18009a6c0  mov     eax, [rsp+38h+arg_30]
0x18009a6c4  cmp     [rbx+84h], eax
0x18009a6ca  jnz     loc_18009A64A
0x18009a6d0  jmp     loc_18009A5ED
```
