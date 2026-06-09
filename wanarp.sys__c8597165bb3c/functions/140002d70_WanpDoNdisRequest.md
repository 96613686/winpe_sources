# WanpDoNdisRequest

- ea: `0x140002d70`
- end: `0x140002e13`
- name: `WanpDoNdisRequest`
- size: `163`
- prototype: `__int64 __fastcall(int, int, int, int, PNDIS_OID_REQUEST OidRequest, __int64, char)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400031b0`
- `0x140003210`
- `0x140003280`
- `0x140019970`

## callees

- `0x140002d70`
- `0x1400050f0`

## import_xrefs

- `NDIS!NdisOidRequest` at `0x140002dbd`
- `NDIS!NdisOidRequest` at `0x140002dbd`

## pseudocode

```c
unsigned int __fastcall WanpDoNdisRequest(
        __int64 a1,
        NDIS_OID a2,
        void *a3,
        UINT a4,
        PNDIS_OID_REQUEST OidRequest,
        void (__fastcall *a6)(NDIS_HANDLE, PNDIS_OID_REQUEST, _QWORD),
        char a7)
{
  NDIS_HANDLE v7; // rcx
  unsigned int result; // eax
  unsigned int v9; // edi
  NDIS_HANDLE v10; // rcx

  *(_QWORD *)&OidRequest[1].PortNumber = a6;
  OidRequest->RequestType = NdisRequestSetInformation;
  OidRequest->Header = (NDIS_OBJECT_HEADER)16253334;
  OidRequest->DATA.QUERY_INFORMATION.Oid = a2;
  OidRequest->DATA.QUERY_INFORMATION.InformationBuffer = a3;
  OidRequest->DATA.QUERY_INFORMATION.InformationBufferLength = a4;
  v7 = (NDIS_HANDLE)qword_1400099E8;
  if ( !a7 )
    v7 = NdisBindingHandle;
  result = NdisOidRequest(v7, OidRequest);
  v9 = result;
  if ( result != 259 )
  {
    if ( a6 )
    {
      v10 = (NDIS_HANDLE)qword_1400099E8;
      if ( !a7 )
        v10 = NdisBindingHandle;
      a6(v10, OidRequest, result);
    }
    if ( !v9 )
      return 259;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x140002d70  push    rbx
0x140002d72  push    rsi
0x140002d73  push    rdi
0x140002d74  push    r14
0x140002d76  sub     rsp, 28h
0x140002d7a  mov     rbx, [rsp+48h+OidRequest]
0x140002d7f  mov     rsi, [rsp+48h+arg_28]
0x140002d84  cmp     [rsp+48h+arg_30], 0
0x140002d8c  mov     [rbx+0F8h], rsi
0x140002d93  mov     dword ptr [rbx+4], 1
0x140002d9a  mov     dword ptr [rbx], 0F80196h
0x140002da0  mov     [rbx+20h], edx
0x140002da3  mov     rdx, rbx; OidRequest
0x140002da6  mov     [rbx+28h], r8
0x140002daa  mov     [rbx+30h], r9d
0x140002dae  mov     rcx, cs:qword_1400099E8
0x140002db5  cmovz   rcx, cs:NdisBindingHandle; NdisBindingHandle
0x140002dbd  call    cs:__imp_NdisOidRequest
0x140002dc4  nop     dword ptr [rax+rax+00h]
0x140002dc9  mov     r14d, 103h
0x140002dcf  mov     edi, eax
0x140002dd1  cmp     eax, r14d
0x140002dd4  jz      short loc_140002E08
0x140002dd6  test    rsi, rsi
0x140002dd9  jz      short loc_140002E00
0x140002ddb  cmp     [rsp+48h+arg_30], 0
0x140002de3  mov     r8d, eax
0x140002de6  mov     rcx, cs:qword_1400099E8
0x140002ded  mov     rdx, rbx
0x140002df0  cmovz   rcx, cs:NdisBindingHandle
0x140002df8  mov     rax, rsi
0x140002dfb  call    _guard_dispatch_icall
0x140002e00  test    edi, edi
0x140002e02  cmovz   edi, r14d
0x140002e06  mov     eax, edi
0x140002e08  add     rsp, 28h
0x140002e0c  pop     r14
0x140002e0e  pop     rdi
0x140002e0f  pop     rsi
0x140002e10  pop     rbx
0x140002e11  retn
```
