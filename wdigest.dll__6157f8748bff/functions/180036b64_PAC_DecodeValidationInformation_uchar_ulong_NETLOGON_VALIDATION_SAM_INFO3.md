# PAC_DecodeValidationInformation(uchar *,ulong,_NETLOGON_VALIDATION_SAM_INFO3 * *)

- ea: `0x180036b64`
- end: `0x180036c08`
- name: `?PAC_DecodeValidationInformation@@YAJPEAEKPEAPEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `164`
- prototype: `int(unsigned __int8 *, unsigned int, struct _NETLOGON_VALIDATION_SAM_INFO3 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180037534`

## callees

- `0x180036b64`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x180036bf6`
- `RPCRT4!MesHandleFree` at `0x180036bf6`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x180036b96`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x180036b96`
- `RPCRT4!NdrMesTypeDecode3` at `0x180036bdc`
- `RPCRT4!NdrMesTypeDecode3` at `0x180036bdc`

## pseudocode

```c
__int64 __fastcall PAC_DecodeValidationInformation(
        unsigned __int8 *a1,
        int a2,
        struct _NETLOGON_VALIDATION_SAM_INFO3 **a3)
{
  unsigned int v6; // ebx
  __int128 v8; // [rsp+30h] [rbp-38h] BYREF
  handle_t Handle; // [rsp+88h] [rbp+20h] BYREF

  Handle = 0;
  v8 = 0;
  if ( MesDecodeIncrementalHandleCreate(&v8, PacReadFcn, &Handle) )
  {
    v6 = -1073741670;
  }
  else
  {
    v6 = 0;
    DWORD2(v8) = a2;
    *(_QWORD *)&v8 = a1;
    NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, a3);
  }
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x180036b64  mov     rax, rsp
0x180036b67  push    rbx
0x180036b68  push    rsi
0x180036b69  push    rdi
0x180036b6a  push    r14
0x180036b6c  sub     rsp, 48h
0x180036b70  mov     r14, r8
0x180036b73  mov     edi, edx
0x180036b75  mov     rsi, rcx
0x180036b78  mov     qword ptr [rax+20h], 0
0x180036b80  xorps   xmm0, xmm0
0x180036b83  movups  xmmword ptr [rax-38h], xmm0
0x180036b87  lea     r8, [rax+20h]; pHandle
0x180036b8b  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x180036b92  lea     rcx, [rax-38h]; UserState
0x180036b96  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x180036b9c  test    eax, eax
0x180036b9e  jz      short loc_180036BA7
0x180036ba0  mov     ebx, 0C000009Ah
0x180036ba5  jmp     short loc_180036BE9
0x180036ba7  xor     ebx, ebx
0x180036ba9  mov     [rsp+68h+var_30], edi
0x180036bad  mov     [rsp+68h+var_38], rsi
0x180036bb2  mov     [rsp+68h+pObject], r14; pObject
0x180036bb7  mov     [rsp+68h+nTypeIndex], 1; nTypeIndex
0x180036bbf  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180036bc6  lea     r8, pProxyInfo; pProxyInfo
0x180036bcd  lea     rdx, pPicklingInfo; pPicklingInfo
0x180036bd4  mov     rcx, [rsp+68h+Handle]; Handle
0x180036bdc  call    cs:__imp_NdrMesTypeDecode3
0x180036be2  jmp     short loc_180036BE9
0x180036be4  mov     ebx, 0C000000Dh
0x180036be9  mov     rcx, [rsp+68h+Handle]; Handle
0x180036bf1  test    rcx, rcx
0x180036bf4  jz      short loc_180036BFC
0x180036bf6  call    cs:__imp_MesHandleFree
0x180036bfc  mov     eax, ebx
0x180036bfe  add     rsp, 48h
0x180036c02  pop     r14
0x180036c04  pop     rdi
0x180036c05  pop     rsi
0x180036c06  pop     rbx
0x180036c07  retn
```
