# SrvClientCertificatesAccessCheckStart

- ea: `0x140048520`
- end: `0x1400486c7`
- name: `SrvClientCertificatesAccessCheckStart`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400491e0`

## callees

- `0x14001389c`
- `0x14001baac`
- `0x14001bbd8`
- `0x140048520`
- `0x14004ac3c`
- `0x14004adf0`

## import_xrefs

- `msrpc!I_RpcExceptionFilter` at `0x140057566`
- `msrpc!I_RpcExceptionFilter` at `0x140057566`
- `msrpc!RpcAsyncInitializeHandle` at `0x14004853d`
- `msrpc!RpcAsyncInitializeHandle` at `0x14004853d`

## pseudocode

```c
__int64 __fastcall SrvClientCertificatesAccessCheckStart(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        ADDRESS_FAMILY *a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  RPC_STATUS v11; // ebx
  UCHAR v12; // al

  v11 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)a1, 0x58u);
  if ( v11 >= 0 )
  {
    *(_DWORD *)(a1 + 44) = 2;
    *(_QWORD *)(a1 + 48) = SrvClientCertificatesAccessCheckComplete;
    v11 = RfsRpcBindingBeginRpcCall(&SrvIdSegRpcBinding);
    if ( v11 >= 0 )
    {
      v12 = SOCKADDR_SIZE(*a4);
      ClientCertificatesAccessCheck(
        a1,
        (_DWORD)SrvIdSegRpcBinding,
        *(_DWORD *)a2,
        *(_QWORD *)(a2 + 8),
        *(_DWORD *)(a2 + 4),
        *(_QWORD *)(a3 + 8),
        *(_WORD *)a3,
        (__int64)a4,
        v12,
        a5,
        a6,
        a7);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids,
          (unsigned int)v11);
      }
      return (unsigned int)-1073741790;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids, (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140048520  push    rbx
0x140048522  push    rsi
0x140048523  push    rdi
0x140048524  push    r14
0x140048526  push    r15
0x140048528  sub     rsp, 60h
0x14004852c  mov     r14, r9
0x14004852f  mov     r15, r8
0x140048532  mov     rsi, rdx
0x140048535  mov     rdi, rcx
0x140048538  mov     edx, 58h ; 'X'; Size
0x14004853d  call    cs:__imp_RpcAsyncInitializeHandle
0x140048544  nop     dword ptr [rax+rax+00h]
0x140048549  mov     ebx, eax
0x14004854b  test    eax, eax
0x14004854d  jns     short loc_14004859A
0x14004854f  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140048556  mov     rcx, cs:WPP_GLOBAL_Control
0x14004855d  cmp     rcx, rax
0x140048560  jz      loc_1400486B8
0x140048566  test    dword ptr [rcx+2Ch], 40000h
0x14004856d  jz      loc_1400486B8
0x140048573  cmp     byte ptr [rcx+29h], 1
0x140048577  jb      loc_1400486B8
0x14004857d  mov     edx, 14h
0x140048582  mov     r9d, ebx
0x140048585  lea     r8, WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids
0x14004858c  mov     rcx, [rcx+18h]
0x140048590  call    WPP_SF_d
0x140048595  jmp     loc_1400486B8
0x14004859a  mov     dword ptr [rdi+2Ch], 2
0x1400485a1  lea     rax, SrvClientCertificatesAccessCheckComplete
0x1400485a8  mov     [rdi+30h], rax
0x1400485ac  lea     rcx, SrvIdSegRpcBinding
0x1400485b3  call    RfsRpcBindingBeginRpcCall
0x1400485b8  mov     ebx, eax
0x1400485ba  test    eax, eax
0x1400485bc  jns     short loc_140048602
0x1400485be  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400485c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400485cc  cmp     rcx, rax
0x1400485cf  jz      short loc_1400485F8
0x1400485d1  test    dword ptr [rcx+2Ch], 40000h
0x1400485d8  jz      short loc_1400485F8
0x1400485da  cmp     byte ptr [rcx+29h], 1
0x1400485de  jb      short loc_1400485F8
0x1400485e0  mov     edx, 15h
0x1400485e5  mov     r9d, ebx
0x1400485e8  lea     r8, WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids
0x1400485ef  mov     rcx, [rcx+18h]
0x1400485f3  call    WPP_SF_d
0x1400485f8  mov     ebx, 0C0000022h
0x1400485fd  jmp     loc_1400486B8
0x140048602  movzx   ecx, word ptr [r14]; af
0x140048606  call    SOCKADDR_SIZE
0x14004860b  movzx   edx, al
0x14004860e  mov     rax, [rsp+88h+arg_30]
0x140048616  mov     [rsp+88h+var_30], rax
0x14004861b  mov     eax, [rsp+88h+arg_28]
0x140048622  mov     [rsp+88h+var_38], eax
0x140048626  mov     rax, [rsp+88h+arg_20]
0x14004862e  mov     [rsp+88h+var_40], rax
0x140048633  mov     [rsp+88h+var_48], edx
0x140048637  mov     [rsp+88h+var_50], r14
0x14004863c  movzx   eax, word ptr [r15]
0x140048640  mov     [rsp+88h+var_58], ax
0x140048645  mov     rax, [r15+8]
0x140048649  mov     [rsp+88h+var_60], rax
0x14004864e  mov     eax, [rsi+4]
0x140048651  mov     [rsp+88h+var_68], eax
0x140048655  mov     r9, [rsi+8]
0x140048659  mov     r8d, [rsi]
0x14004865c  mov     rdx, cs:SrvIdSegRpcBinding
0x140048663  mov     rcx, rdi
0x140048666  call    ClientCertificatesAccessCheck
0x14004866b  jmp     short loc_1400486B8
0x14004866d  mov     ebx, eax
0x14004866f  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140048676  mov     rcx, cs:WPP_GLOBAL_Control
0x14004867d  cmp     rcx, rax
0x140048680  jz      short loc_1400486A9
0x140048682  test    dword ptr [rcx+2Ch], 40000h
0x140048689  jz      short loc_1400486A9
0x14004868b  cmp     byte ptr [rcx+29h], 1
0x14004868f  jb      short loc_1400486A9
0x140048691  mov     edx, 16h
0x140048696  mov     r9d, ebx
0x140048699  lea     r8, WPP_3bb578cf2b8e3f8c9711c1265018cc4d_Traceguids
0x1400486a0  mov     rcx, [rcx+18h]
0x1400486a4  call    WPP_SF_d
0x1400486a9  mov     edx, ebx
0x1400486ab  lea     rcx, SrvIdSegRpcBinding
0x1400486b2  call    RfsRpcBindingEndRpcCall
0x1400486b7  nop
0x1400486b8  mov     eax, ebx
0x1400486ba  add     rsp, 60h
0x1400486be  pop     r15
0x1400486c0  pop     r14
0x1400486c2  pop     rdi
0x1400486c3  pop     rsi
0x1400486c4  pop     rbx
0x1400486c5  retn
0x140057558  push    rbp
0x14005755a  sub     rsp, 60h
0x14005755e  mov     rbp, rdx
0x140057561  mov     rcx, [rcx]
0x140057564  mov     ecx, [rcx]; ExceptionCode
0x140057566  call    cs:__imp_I_RpcExceptionFilter
0x14005756d  nop     dword ptr [rax+rax+00h]
0x140057572  nop
0x140057573  add     rsp, 60h
0x140057577  pop     rbp
0x140057578  retn
```
