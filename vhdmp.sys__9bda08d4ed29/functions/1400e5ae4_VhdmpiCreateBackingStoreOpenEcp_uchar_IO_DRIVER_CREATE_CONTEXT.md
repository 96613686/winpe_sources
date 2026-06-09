# VhdmpiCreateBackingStoreOpenEcp(uchar,_IO_DRIVER_CREATE_CONTEXT *)

- ea: `0x1400e5ae4`
- end: `0x1400e5d87`
- name: `?VhdmpiCreateBackingStoreOpenEcp@@YAJEPEAU_IO_DRIVER_CREATE_CONTEXT@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(char, struct _IO_DRIVER_CREATE_CONTEXT *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400acbbc`
- `0x1400ecab0`

## callees

- `0x140023980`
- `0x140036284`
- `0x14005dbb0`
- `0x14005e100`
- `0x1400e5ae4`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400e5b5e`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400e5c87`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400e5b5e`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400e5c87`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400e5c0b`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400e5ced`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400e5c0b`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400e5ced`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400e5d42`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400e5d57`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400e5d42`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400e5d57`

## string_xrefs

- `0x1400e5cc1`: `Could not allocate RKF bypass extra create parameter, status = 0x%08x`
- `0x1400e5c49`: `Could not insert SVHDX extra create parameter into list, status = 0x%08x`
- `0x1400e5bb6`: `VhdmpiCreateBackingStoreOpenEcp`
- `0x1400e5ba1`: `Could not allocate SVHDX extra create parameter, status = 0x%08x`
- `0x1400e5d23`: `Could not insert RKF bypass extra create parameter into list, status = 0x%08x`

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
          if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
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
          if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
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
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
    {
      v6 = 2634;
      v7 = "Could not insert SVHDX extra create parameter into list, status = 0x%08x";
      goto LABEL_5;
    }
  }
  else if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2048) )
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
0x1400e5ae4  mov     [rsp-18h+arg_0], rbx
0x1400e5ae9  mov     [rsp-18h+arg_10], rsi
0x1400e5aee  push    rbp
0x1400e5aef  push    rdi
0x1400e5af0  push    r14
0x1400e5af2  mov     rbp, rsp
0x1400e5af5  sub     rsp, 60h
0x1400e5af9  mov     rax, cs:__security_cookie
0x1400e5b00  xor     rax, rsp
0x1400e5b03  mov     [rbp+var_10], rax
0x1400e5b07  lea     rax, [rbp+var_30]
0x1400e5b0b  mov     [rbp+var_30], 0
0x1400e5b13  mov     r14, rdx
0x1400e5b16  mov     [rsp+60h+EcpContext], rax; EcpContext
0x1400e5b1b  mov     sil, cl
0x1400e5b1e  mov     [rsp+60h+PoolTag], 6E444856h; PoolTag
0x1400e5b26  mov     edi, 0C0h
0x1400e5b2b  mov     [rbp+var_28], 0
0x1400e5b33  mov     edx, edi; SizeOfContext
0x1400e5b35  mov     [rbp+EcpType.Data1], 2378CC6h
0x1400e5b3c  xor     r9d, r9d; CleanupCallback
0x1400e5b3f  mov     dword ptr [rbp+EcpType.Data2], 489CF73Ch
0x1400e5b46  xor     r8d, r8d; Flags
0x1400e5b49  mov     dword ptr [rbp+EcpType.Data4], 4D568282h
0x1400e5b50  lea     rcx, GUID_ECP_OPEN_AS_BLOCK_DEVICE; EcpType
0x1400e5b57  mov     dword ptr [rbp+EcpType.Data4+4], 1B13991Ah
0x1400e5b5e  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x1400e5b65  nop     dword ptr [rax+rax+00h]
0x1400e5b6a  mov     ebx, eax
0x1400e5b6c  test    eax, eax
0x1400e5b6e  jns     short loc_1400E5BCA
0x1400e5b70  mov     ecx, cs:dword_1400876D0
0x1400e5b76  mov     edi, 2
0x1400e5b7b  cmp     ecx, edi
0x1400e5b7d  jbe     loc_1400E5D39
0x1400e5b83  mov     edx, 800h
0x1400e5b88  lea     rcx, dword_1400876D0
0x1400e5b8f  call    _tlgKeywordOn
0x1400e5b94  test    al, al
0x1400e5b96  jz      loc_1400E5D39
0x1400e5b9c  mov     ecx, 0A39h
0x1400e5ba1  lea     rax, aCouldNotAlloca_1; "Could not allocate SVHDX extra create p"...
0x1400e5ba8  mov     r9d, edx; int
0x1400e5bab  mov     dword ptr [rsp+60h+EcpContext], ebx; char
0x1400e5baf  mov     edx, ecx; int
0x1400e5bb1  mov     qword ptr [rsp+60h+PoolTag], rax; char *
0x1400e5bb6  lea     rcx, aVhdmpicreateba_0; "VhdmpiCreateBackingStoreOpenEcp"
0x1400e5bbd  mov     r8d, edi; int
0x1400e5bc0  call    TraceEvents
0x1400e5bc5  jmp     loc_1400E5D39
0x1400e5bca  mov     rcx, [rbp+var_30]; void *
0x1400e5bce  mov     r8, rdi; Size
0x1400e5bd1  xor     edx, edx; Val
0x1400e5bd3  call    memset
0x1400e5bd8  mov     rax, [rbp+var_30]
0x1400e5bdc  mov     edi, 2
0x1400e5be1  mov     [rax], edi
0x1400e5be3  mov     rax, [rbp+var_30]
0x1400e5be7  mov     byte ptr [rax+4], 0
0x1400e5beb  mov     rax, [rbp+var_30]
0x1400e5bef  mov     dword ptr [rax+1Ch], 4
0x1400e5bf6  test    sil, sil
0x1400e5bf9  jz      short loc_1400E5C03
0x1400e5bfb  mov     rax, [rbp+var_30]
0x1400e5bff  or      dword ptr [rax+1Ch], 8
0x1400e5c03  mov     rdx, [rbp+var_30]; EcpContext
0x1400e5c07  mov     rcx, [r14+8]; EcpList
0x1400e5c0b  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1400e5c12  nop     dword ptr [rax+rax+00h]
0x1400e5c17  mov     ebx, eax
0x1400e5c19  test    eax, eax
0x1400e5c1b  jns     short loc_1400E5C55
0x1400e5c1d  mov     eax, cs:dword_1400876D0
0x1400e5c23  cmp     eax, edi
0x1400e5c25  jbe     loc_1400E5D39
0x1400e5c2b  mov     edx, 800h
0x1400e5c30  lea     rcx, dword_1400876D0
0x1400e5c37  call    _tlgKeywordOn
0x1400e5c3c  test    al, al
0x1400e5c3e  jz      loc_1400E5D39
0x1400e5c44  mov     ecx, 0A4Ah
0x1400e5c49  lea     rax, aCouldNotInsert_0; "Could not insert SVHDX extra create par"...
0x1400e5c50  jmp     loc_1400E5BA8
0x1400e5c55  mov     [rbp+var_30], 0
0x1400e5c5d  test    sil, sil
0x1400e5c60  jz      loc_1400E5D37
0x1400e5c66  xor     r9d, r9d; CleanupCallback
0x1400e5c69  lea     rax, [rbp+var_28]
0x1400e5c6d  mov     [rsp+60h+EcpContext], rax; EcpContext
0x1400e5c72  lea     rcx, [rbp+EcpType]; EcpType
0x1400e5c76  xor     r8d, r8d; Flags
0x1400e5c79  mov     [rsp+60h+PoolTag], 6E444856h; PoolTag
0x1400e5c81  lea     esi, [r9+68h]
0x1400e5c85  mov     edx, esi; SizeOfContext
0x1400e5c87  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x1400e5c8e  nop     dword ptr [rax+rax+00h]
0x1400e5c93  mov     ebx, eax
0x1400e5c95  test    eax, eax
0x1400e5c97  jns     short loc_1400E5CCD
0x1400e5c99  mov     eax, cs:dword_1400876D0
0x1400e5c9f  cmp     eax, edi
0x1400e5ca1  jbe     loc_1400E5D39
0x1400e5ca7  mov     edx, 800h
0x1400e5cac  lea     rcx, dword_1400876D0
0x1400e5cb3  call    _tlgKeywordOn
0x1400e5cb8  test    al, al
0x1400e5cba  jz      short loc_1400E5D39
0x1400e5cbc  mov     ecx, 0A6Dh
0x1400e5cc1  lea     rax, aCouldNotAlloca; "Could not allocate RKF bypass extra cre"...
0x1400e5cc8  jmp     loc_1400E5BA8
0x1400e5ccd  mov     rcx, [rbp+var_28]; void *
0x1400e5cd1  mov     r8, rsi; Size
0x1400e5cd4  xor     edx, edx; Val
0x1400e5cd6  call    memset
0x1400e5cdb  mov     rax, [rbp+var_28]
0x1400e5cdf  mov     dword ptr [rax], 0
0x1400e5ce5  mov     rdx, [rbp+var_28]; EcpContext
0x1400e5ce9  mov     rcx, [r14+8]; EcpList
0x1400e5ced  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1400e5cf4  nop     dword ptr [rax+rax+00h]
0x1400e5cf9  mov     ebx, eax
0x1400e5cfb  test    eax, eax
0x1400e5cfd  jns     short loc_1400E5D2F
0x1400e5cff  mov     eax, cs:dword_1400876D0
0x1400e5d05  cmp     eax, edi
0x1400e5d07  jbe     short loc_1400E5D39
0x1400e5d09  mov     edx, 800h
0x1400e5d0e  lea     rcx, dword_1400876D0
0x1400e5d15  call    _tlgKeywordOn
0x1400e5d1a  test    al, al
0x1400e5d1c  jz      short loc_1400E5D39
0x1400e5d1e  mov     ecx, 0A79h
0x1400e5d23  lea     rax, aCouldNotInsert; "Could not insert RKF bypass extra creat"...
0x1400e5d2a  jmp     loc_1400E5BA8
0x1400e5d2f  mov     [rbp+var_28], 0
0x1400e5d37  xor     ebx, ebx
0x1400e5d39  mov     rcx, [rbp+var_30]; EcpContext
0x1400e5d3d  test    rcx, rcx
0x1400e5d40  jz      short loc_1400E5D4E
0x1400e5d42  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x1400e5d49  nop     dword ptr [rax+rax+00h]
0x1400e5d4e  mov     rcx, [rbp+var_28]; EcpContext
0x1400e5d52  test    rcx, rcx
0x1400e5d55  jz      short loc_1400E5D63
0x1400e5d57  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x1400e5d5e  nop     dword ptr [rax+rax+00h]
0x1400e5d63  mov     eax, ebx
0x1400e5d65  mov     rcx, [rbp+var_10]
0x1400e5d69  xor     rcx, rsp; StackCookie
0x1400e5d6c  call    __security_check_cookie
0x1400e5d71  lea     r11, [rsp+60h+var_s0]
0x1400e5d76  mov     rbx, [r11+20h]
0x1400e5d7a  mov     rsi, [r11+30h]
0x1400e5d7e  mov     rsp, r11
0x1400e5d81  pop     r14
0x1400e5d83  pop     rdi
0x1400e5d84  pop     rbp
0x1400e5d85  retn
```
