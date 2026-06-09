# LogEtwDebugRpcInterfaceRegistrationEvent(_GUID *,_GUID *,uint,uint,void *)

- ea: `0x18008e148`
- end: `0x18008e1f7`
- name: `?LogEtwDebugRpcInterfaceRegistrationEvent@@YAXPEAU_GUID@@0IIPEAX@Z`
- size: `175`
- prototype: `void __fastcall(struct _GUID *, struct _GUID *, unsigned int, unsigned int, void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006dac0`

## callees

- `0x180022870`
- `0x18004fc10`
- `0x18008e148`
- `0x18008e200`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18008e174`
- `ntdll!EtwEventEnabled` at `0x18008e174`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008e1cf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18008e1cf`

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
0x18008e148  push    rbx
0x18008e14a  push    rbp
0x18008e14b  push    rsi
0x18008e14c  push    rdi
0x18008e14d  push    r14
0x18008e14f  push    r15
0x18008e151  sub     rsp, 58h
0x18008e155  mov     r15, rcx
0x18008e158  mov     esi, r9d
0x18008e15b  mov     rcx, cs:RpcEtwGuid_Context
0x18008e162  mov     ebp, r8d
0x18008e165  mov     r14, rdx
0x18008e168  test    rcx, rcx
0x18008e16b  jz      short loc_18008E17E
0x18008e16d  lea     rdx, RpcGeneralDebugEvent
0x18008e174  call    cs:__imp_EtwEventEnabled
0x18008e17a  test    al, al
0x18008e17c  jnz     short loc_18008E18B
0x18008e17e  add     rsp, 58h
0x18008e182  pop     r15
0x18008e184  pop     r14
0x18008e186  pop     rdi
0x18008e187  pop     rsi
0x18008e188  pop     rbp
0x18008e189  pop     rbx
0x18008e18a  retn
0x18008e18b  mov     rcx, [rsp+88h+Src]; Src
0x18008e193  xor     ebx, ebx
0x18008e195  xor     edi, edi
0x18008e197  mov     [rsp+88h+pSecurityDescriptor], rbx
0x18008e19c  test    rcx, rcx
0x18008e19f  jnz     short loc_18008E1B9
0x18008e1a1  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x18008e1a8  jnz     short loc_18008E1D9
0x18008e1aa  test    rbx, rbx
0x18008e1ad  jz      short loc_18008E17E
0x18008e1af  mov     rcx, rbx; lpMem
0x18008e1b2  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18008e1b7  jmp     short loc_18008E17E
0x18008e1b9  lea     rdx, [rsp+88h+pSecurityDescriptor]; void **
0x18008e1be  call    ?RpcpCopySecurityDescriptor@@YAJPEAXPEAPEAX@Z; RpcpCopySecurityDescriptor(void *,void * *)
0x18008e1c3  mov     rbx, [rsp+88h+pSecurityDescriptor]
0x18008e1c8  test    eax, eax
0x18008e1ca  jnz     short loc_18008E1A1
0x18008e1cc  mov     rcx, rbx; pSecurityDescriptor
0x18008e1cf  call    cs:__imp_GetSecurityDescriptorLength
0x18008e1d5  mov     edi, eax
0x18008e1d7  jmp     short loc_18008E1A1
0x18008e1d9  mov     [rsp+88h+var_50], rbx
0x18008e1de  mov     r9, r14
0x18008e1e1  mov     [rsp+88h+var_58], edi
0x18008e1e5  mov     r8, r15
0x18008e1e8  mov     [rsp+88h+var_60], esi
0x18008e1ec  mov     [rsp+88h+var_68], ebp
0x18008e1f0  call    McTemplateU0jjqqqbr4_EtwEventWriteTransfer
0x18008e1f5  jmp     short loc_18008E1AA
```
