# LogEtwDebugRpcInterfaceRegistrationEvent(_GUID *,_GUID *,uint,uint,void *)

- ea: `0x180091c50`
- end: `0x180091d0c`
- name: `?LogEtwDebugRpcInterfaceRegistrationEvent@@YAXPEAU_GUID@@0IIPEAX@Z`
- size: `188`
- prototype: `void __fastcall(struct _GUID *, struct _GUID *, unsigned int, unsigned int, void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800900a0`

## callees

- `0x18001057c`
- `0x180023a40`
- `0x180091c50`
- `0x180091d14`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180091c7c`
- `ntdll!EtwEventEnabled` at `0x180091c7c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180091cde`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180091cde`

## pseudocode

```c
void __fastcall LogEtwDebugRpcInterfaceRegistrationEvent(
        struct _GUID *a1,
        struct _GUID *a2,
        char a3,
        char a4,
        void *Src)
{
  int v5; // r15d
  int v8; // r14d
  int v9; // edx
  int v10; // ecx
  PSECURITY_DESCRIPTOR v11; // rbx
  DWORD SecurityDescriptorLength; // edi
  int v13; // eax
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp-48h] BYREF

  v5 = (int)a1;
  v8 = (int)a2;
  if ( RpcEtwGuid_Context && (unsigned __int8)EtwEventEnabled(RpcEtwGuid_Context, RpcGeneralDebugEvent) )
  {
    v10 = (int)Src;
    v11 = 0;
    SecurityDescriptorLength = 0;
    pSecurityDescriptor = 0;
    if ( Src )
    {
      v13 = RpcpCopySecurityDescriptor(Src, &pSecurityDescriptor);
      v11 = pSecurityDescriptor;
      if ( !v13 )
        SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
    }
    if ( (Microsoft_Windows_RPCEnableBits & 2) != 0 )
      McTemplateU0jjqqqbr4_EtwEventWriteTransfer(v10, v9, v5, v8, a3, a4, SecurityDescriptorLength, (__int64)v11);
    if ( v11 )
      FreeWrapper(v11);
  }
}

```

## disassembly

```asm
0x180091c50  push    rbx
0x180091c52  push    rbp
0x180091c53  push    rsi
0x180091c54  push    rdi
0x180091c55  push    r14
0x180091c57  push    r15
0x180091c59  sub     rsp, 58h
0x180091c5d  mov     r15, rcx
0x180091c60  mov     esi, r9d
0x180091c63  mov     rcx, cs:RpcEtwGuid_Context
0x180091c6a  mov     ebp, r8d
0x180091c6d  mov     r14, rdx
0x180091c70  test    rcx, rcx
0x180091c73  jz      short loc_180091C8C
0x180091c75  lea     rdx, RpcGeneralDebugEvent
0x180091c7c  call    cs:__imp_EtwEventEnabled
0x180091c83  nop     dword ptr [rax+rax+00h]
0x180091c88  test    al, al
0x180091c8a  jnz     short loc_180091C9A
0x180091c8c  add     rsp, 58h
0x180091c90  pop     r15
0x180091c92  pop     r14
0x180091c94  pop     rdi
0x180091c95  pop     rsi
0x180091c96  pop     rbp
0x180091c97  pop     rbx
0x180091c98  retn
0x180091c9a  mov     rcx, [rsp+88h+Src]; Src
0x180091ca2  xor     ebx, ebx
0x180091ca4  xor     edi, edi
0x180091ca6  mov     [rsp+88h+pSecurityDescriptor], rbx
0x180091cab  test    rcx, rcx
0x180091cae  jnz     short loc_180091CC8
0x180091cb0  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x180091cb7  jnz     short loc_180091CEE
0x180091cb9  test    rbx, rbx
0x180091cbc  jz      short loc_180091C8C
0x180091cbe  mov     rcx, rbx; lpMem
0x180091cc1  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180091cc6  jmp     short loc_180091C8C
0x180091cc8  lea     rdx, [rsp+88h+pSecurityDescriptor]; void **
0x180091ccd  call    ?RpcpCopySecurityDescriptor@@YAJPEAXPEAPEAX@Z; RpcpCopySecurityDescriptor(void *,void * *)
0x180091cd2  mov     rbx, [rsp+88h+pSecurityDescriptor]
0x180091cd7  test    eax, eax
0x180091cd9  jnz     short loc_180091CB0
0x180091cdb  mov     rcx, rbx; pSecurityDescriptor
0x180091cde  call    cs:__imp_GetSecurityDescriptorLength
0x180091ce5  nop     dword ptr [rax+rax+00h]
0x180091cea  mov     edi, eax
0x180091cec  jmp     short loc_180091CB0
0x180091cee  mov     [rsp+88h+var_50], rbx
0x180091cf3  mov     r9, r14
0x180091cf6  mov     [rsp+88h+var_58], edi
0x180091cfa  mov     r8, r15
0x180091cfd  mov     [rsp+88h+var_60], esi
0x180091d01  mov     [rsp+88h+var_68], ebp
0x180091d05  call    McTemplateU0jjqqqbr4_EtwEventWriteTransfer
0x180091d0a  jmp     short loc_180091CB9
```
