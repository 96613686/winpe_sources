# VhdmpiCreateBackingStoreOpenEcp(uchar,_IO_DRIVER_CREATE_CONTEXT *)

- ea: `0x1400e5b54`
- end: `0x1400e5df7`
- name: `?VhdmpiCreateBackingStoreOpenEcp@@YAJEPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(char, struct _IO_DRIVER_CREATE_CONTEXT *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400acbbc`
- `0x1400ecb20`

## callees

- `0x140023560`
- `0x140035e94`
- `0x14005d7c0`
- `0x14005dd00`
- `0x1400e5b54`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400e5bce`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400e5cf7`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400e5bce`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400e5cf7`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400e5c7b`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400e5d5d`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400e5c7b`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400e5d5d`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400e5db2`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400e5dc7`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400e5db2`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400e5dc7`

## string_xrefs

- `0x1400e5cb9`: `Could not insert SVHDX extra create parameter into list, status = 0x%08x`
- `0x1400e5c26`: `VhdmpiCreateBackingStoreOpenEcp`
- `0x1400e5c11`: `Could not allocate SVHDX extra create parameter, status = 0x%08x`
- `0x1400e5d93`: `Could not insert RKF bypass extra create parameter into list, status = 0x%08x`
- `0x1400e5d31`: `Could not allocate RKF bypass extra create parameter, status = 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiCreateBackingStoreOpenEcp(char a1, struct _IO_DRIVER_CREATE_CONTEXT *a2)
{
  NTSTATUS Parameter; // ebx
  int v5; // edx
  int v6; // ecx
  char *v7; // rax
  PVOID EcpContext; // [rsp+30h] [rbp-30h] BYREF
  PVOID v10; // [rsp+38h] [rbp-28h] BYREF
  GUID EcpType; // [rsp+40h] [rbp-20h] BYREF

  EcpContext = 0;
  v10 = 0;
  EcpType.Data1 = 37194950;
  *(_DWORD *)&EcpType.Data2 = 1218246460;
  *(_DWORD *)EcpType.Data4 = 1297515138;
  *(_DWORD *)&EcpType.Data4[4] = 454269210;
  Parameter = FsRtlAllocateExtraCreateParameter(&GUID_ECP_OPEN_AS_BLOCK_DEVICE, 0xC0u, 0, 0, 0x6E444856u, &EcpContext);
  if ( Parameter >= 0 )
  {
    memset(EcpContext, 0, 0xC0u);
    *(_DWORD *)EcpContext = 2;
    *((_BYTE *)EcpContext + 4) = 0;
    *((_DWORD *)EcpContext + 7) = 4;
    if ( a1 )
      *((_DWORD *)EcpContext + 7) |= 8u;
    Parameter = FsRtlInsertExtraCreateParameter(a2->ExtraCreateParameter, EcpContext);
    if ( Parameter >= 0 )
    {
      EcpContext = 0;
      if ( a1 )
      {
        Parameter = FsRtlAllocateExtraCreateParameter(&EcpType, 0x68u, 0, 0, 0x6E444856u, &v10);
        if ( Parameter < 0 )
        {
          if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
          {
            v6 = 2669;
            v7 = "Could not allocate RKF bypass extra create parameter, status = 0x%08x";
            goto LABEL_5;
          }
          goto LABEL_23;
        }
        memset(v10, 0, 0x68u);
        *(_DWORD *)v10 = 0;
        Parameter = FsRtlInsertExtraCreateParameter(a2->ExtraCreateParameter, v10);
        if ( Parameter < 0 )
        {
          if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
          {
            v6 = 2681;
            v7 = "Could not insert RKF bypass extra create parameter into list, status = 0x%08x";
            goto LABEL_5;
          }
          goto LABEL_23;
        }
        v10 = 0;
      }
      Parameter = 0;
      goto LABEL_23;
    }
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
    {
      v6 = 2634;
      v7 = "Could not insert SVHDX extra create parameter into list, status = 0x%08x";
      goto LABEL_5;
    }
  }
  else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 2048) )
  {
    v6 = 2617;
    v7 = "Could not allocate SVHDX extra create parameter, status = 0x%08x";
LABEL_5:
    TraceEvents((int)"VhdmpiCreateBackingStoreOpenEcp", v6, 2, v5, v7, Parameter);
  }
LABEL_23:
  if ( EcpContext )
    FsRtlFreeExtraCreateParameter(EcpContext);
  if ( v10 )
    FsRtlFreeExtraCreateParameter(v10);
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x1400e5b54  mov     [rsp-18h+arg_0], rbx
0x1400e5b59  mov     [rsp-18h+arg_10], rsi
0x1400e5b5e  push    rbp
0x1400e5b5f  push    rdi
0x1400e5b60  push    r14
0x1400e5b62  mov     rbp, rsp
0x1400e5b65  sub     rsp, 60h
0x1400e5b69  mov     rax, cs:__security_cookie
0x1400e5b70  xor     rax, rsp
0x1400e5b73  mov     [rbp+var_10], rax
0x1400e5b77  lea     rax, [rbp+var_30]
0x1400e5b7b  mov     [rbp+var_30], 0
0x1400e5b83  mov     r14, rdx
0x1400e5b86  mov     [rsp+60h+EcpContext], rax; EcpContext
0x1400e5b8b  mov     sil, cl
0x1400e5b8e  mov     [rsp+60h+PoolTag], 6E444856h; PoolTag
0x1400e5b96  mov     edi, 0C0h
0x1400e5b9b  mov     [rbp+var_28], 0
0x1400e5ba3  mov     edx, edi; SizeOfContext
0x1400e5ba5  mov     [rbp+EcpType.Data1], 2378CC6h
0x1400e5bac  xor     r9d, r9d; CleanupCallback
0x1400e5baf  mov     dword ptr [rbp+EcpType.Data2], 489CF73Ch
0x1400e5bb6  xor     r8d, r8d; Flags
0x1400e5bb9  mov     dword ptr [rbp+EcpType.Data4], 4D568282h
0x1400e5bc0  lea     rcx, GUID_ECP_OPEN_AS_BLOCK_DEVICE; EcpType
0x1400e5bc7  mov     dword ptr [rbp+EcpType.Data4+4], 1B13991Ah
0x1400e5bce  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x1400e5bd5  nop     dword ptr [rax+rax+00h]
0x1400e5bda  mov     ebx, eax
0x1400e5bdc  test    eax, eax
0x1400e5bde  jns     short loc_1400E5C3A
0x1400e5be0  mov     ecx, cs:dword_140087708
0x1400e5be6  mov     edi, 2
0x1400e5beb  cmp     ecx, edi
0x1400e5bed  jbe     loc_1400E5DA9
0x1400e5bf3  mov     edx, 800h
0x1400e5bf8  lea     rcx, dword_140087708
0x1400e5bff  call    _tlgKeywordOn
0x1400e5c04  test    al, al
0x1400e5c06  jz      loc_1400E5DA9
0x1400e5c0c  mov     ecx, 0A39h
0x1400e5c11  lea     rax, aCouldNotAlloca_1; "Could not allocate SVHDX extra create p"...
0x1400e5c18  mov     r9d, edx; int
0x1400e5c1b  mov     dword ptr [rsp+60h+EcpContext], ebx; char
0x1400e5c1f  mov     edx, ecx; int
0x1400e5c21  mov     qword ptr [rsp+60h+PoolTag], rax; char *
0x1400e5c26  lea     rcx, aVhdmpicreateba_0; "VhdmpiCreateBackingStoreOpenEcp"
0x1400e5c2d  mov     r8d, edi; int
0x1400e5c30  call    TraceEvents
0x1400e5c35  jmp     loc_1400E5DA9
0x1400e5c3a  mov     rcx, [rbp+var_30]; void *
0x1400e5c3e  mov     r8, rdi; Size
0x1400e5c41  xor     edx, edx; Val
0x1400e5c43  call    memset
0x1400e5c48  mov     rax, [rbp+var_30]
0x1400e5c4c  mov     edi, 2
0x1400e5c51  mov     [rax], edi
0x1400e5c53  mov     rax, [rbp+var_30]
0x1400e5c57  mov     byte ptr [rax+4], 0
0x1400e5c5b  mov     rax, [rbp+var_30]
0x1400e5c5f  mov     dword ptr [rax+1Ch], 4
0x1400e5c66  test    sil, sil
0x1400e5c69  jz      short loc_1400E5C73
0x1400e5c6b  mov     rax, [rbp+var_30]
0x1400e5c6f  or      dword ptr [rax+1Ch], 8
0x1400e5c73  mov     rdx, [rbp+var_30]; EcpContext
0x1400e5c77  mov     rcx, [r14+8]; EcpList
0x1400e5c7b  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1400e5c82  nop     dword ptr [rax+rax+00h]
0x1400e5c87  mov     ebx, eax
0x1400e5c89  test    eax, eax
0x1400e5c8b  jns     short loc_1400E5CC5
0x1400e5c8d  mov     eax, cs:dword_140087708
0x1400e5c93  cmp     eax, edi
0x1400e5c95  jbe     loc_1400E5DA9
0x1400e5c9b  mov     edx, 800h
0x1400e5ca0  lea     rcx, dword_140087708
0x1400e5ca7  call    _tlgKeywordOn
0x1400e5cac  test    al, al
0x1400e5cae  jz      loc_1400E5DA9
0x1400e5cb4  mov     ecx, 0A4Ah
0x1400e5cb9  lea     rax, aCouldNotInsert_0; "Could not insert SVHDX extra create par"...
0x1400e5cc0  jmp     loc_1400E5C18
0x1400e5cc5  mov     [rbp+var_30], 0
0x1400e5ccd  test    sil, sil
0x1400e5cd0  jz      loc_1400E5DA7
0x1400e5cd6  xor     r9d, r9d; CleanupCallback
0x1400e5cd9  lea     rax, [rbp+var_28]
0x1400e5cdd  mov     [rsp+60h+EcpContext], rax; EcpContext
0x1400e5ce2  lea     rcx, [rbp+EcpType]; EcpType
0x1400e5ce6  xor     r8d, r8d; Flags
0x1400e5ce9  mov     [rsp+60h+PoolTag], 6E444856h; PoolTag
0x1400e5cf1  lea     esi, [r9+68h]
0x1400e5cf5  mov     edx, esi; SizeOfContext
0x1400e5cf7  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x1400e5cfe  nop     dword ptr [rax+rax+00h]
0x1400e5d03  mov     ebx, eax
0x1400e5d05  test    eax, eax
0x1400e5d07  jns     short loc_1400E5D3D
0x1400e5d09  mov     eax, cs:dword_140087708
0x1400e5d0f  cmp     eax, edi
0x1400e5d11  jbe     loc_1400E5DA9
0x1400e5d17  mov     edx, 800h
0x1400e5d1c  lea     rcx, dword_140087708
0x1400e5d23  call    _tlgKeywordOn
0x1400e5d28  test    al, al
0x1400e5d2a  jz      short loc_1400E5DA9
0x1400e5d2c  mov     ecx, 0A6Dh
0x1400e5d31  lea     rax, aCouldNotAlloca; "Could not allocate RKF bypass extra cre"...
0x1400e5d38  jmp     loc_1400E5C18
0x1400e5d3d  mov     rcx, [rbp+var_28]; void *
0x1400e5d41  mov     r8, rsi; Size
0x1400e5d44  xor     edx, edx; Val
0x1400e5d46  call    memset
0x1400e5d4b  mov     rax, [rbp+var_28]
0x1400e5d4f  mov     dword ptr [rax], 0
0x1400e5d55  mov     rdx, [rbp+var_28]; EcpContext
0x1400e5d59  mov     rcx, [r14+8]; EcpList
0x1400e5d5d  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1400e5d64  nop     dword ptr [rax+rax+00h]
0x1400e5d69  mov     ebx, eax
0x1400e5d6b  test    eax, eax
0x1400e5d6d  jns     short loc_1400E5D9F
0x1400e5d6f  mov     eax, cs:dword_140087708
0x1400e5d75  cmp     eax, edi
0x1400e5d77  jbe     short loc_1400E5DA9
0x1400e5d79  mov     edx, 800h
0x1400e5d7e  lea     rcx, dword_140087708
0x1400e5d85  call    _tlgKeywordOn
0x1400e5d8a  test    al, al
0x1400e5d8c  jz      short loc_1400E5DA9
0x1400e5d8e  mov     ecx, 0A79h
0x1400e5d93  lea     rax, aCouldNotInsert; "Could not insert RKF bypass extra creat"...
0x1400e5d9a  jmp     loc_1400E5C18
0x1400e5d9f  mov     [rbp+var_28], 0
0x1400e5da7  xor     ebx, ebx
0x1400e5da9  mov     rcx, [rbp+var_30]; EcpContext
0x1400e5dad  test    rcx, rcx
0x1400e5db0  jz      short loc_1400E5DBE
0x1400e5db2  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x1400e5db9  nop     dword ptr [rax+rax+00h]
0x1400e5dbe  mov     rcx, [rbp+var_28]; EcpContext
0x1400e5dc2  test    rcx, rcx
0x1400e5dc5  jz      short loc_1400E5DD3
0x1400e5dc7  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x1400e5dce  nop     dword ptr [rax+rax+00h]
0x1400e5dd3  mov     eax, ebx
0x1400e5dd5  mov     rcx, [rbp+var_10]
0x1400e5dd9  xor     rcx, rsp; StackCookie
0x1400e5ddc  call    __security_check_cookie
0x1400e5de1  lea     r11, [rsp+60h+var_s0]
0x1400e5de6  mov     rbx, [r11+20h]
0x1400e5dea  mov     rsi, [r11+30h]
0x1400e5dee  mov     rsp, r11
0x1400e5df1  pop     r14
0x1400e5df3  pop     rdi
0x1400e5df4  pop     rbp
0x1400e5df5  retn
```
