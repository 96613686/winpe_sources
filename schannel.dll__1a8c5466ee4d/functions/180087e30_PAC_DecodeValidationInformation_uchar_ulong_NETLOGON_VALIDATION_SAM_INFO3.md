# PAC_DecodeValidationInformation(uchar *,ulong,_NETLOGON_VALIDATION_SAM_INFO3 * *)

- ea: `0x180087e30`
- end: `0x180087ed4`
- name: `?PAC_DecodeValidationInformation@@YAJPEAEKPEAPEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `164`
- prototype: `int(unsigned __int8 *, unsigned int, struct _NETLOGON_VALIDATION_SAM_INFO3 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800884f0`

## callees

- `0x180087e30`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x180087ec2`
- `RPCRT4!MesHandleFree` at `0x180087ec2`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x180087e62`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x180087e62`
- `RPCRT4!NdrMesTypeDecode3` at `0x180087ea8`
- `RPCRT4!NdrMesTypeDecode3` at `0x180087ea8`

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
0x180087e30  mov     rax, rsp
0x180087e33  push    rbx
0x180087e34  push    rsi
0x180087e35  push    rdi
0x180087e36  push    r14
0x180087e38  sub     rsp, 48h
0x180087e3c  mov     r14, r8
0x180087e3f  mov     edi, edx
0x180087e41  mov     rsi, rcx
0x180087e44  mov     qword ptr [rax+20h], 0
0x180087e4c  xorps   xmm0, xmm0
0x180087e4f  movups  xmmword ptr [rax-38h], xmm0
0x180087e53  lea     r8, [rax+20h]; pHandle
0x180087e57  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x180087e5e  lea     rcx, [rax-38h]; UserState
0x180087e62  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x180087e68  test    eax, eax
0x180087e6a  jz      short loc_180087E73
0x180087e6c  mov     ebx, 0C000009Ah
0x180087e71  jmp     short loc_180087EB5
0x180087e73  xor     ebx, ebx
0x180087e75  mov     [rsp+68h+var_30], edi
0x180087e79  mov     [rsp+68h+var_38], rsi
0x180087e7e  mov     [rsp+68h+pObject], r14; pObject
0x180087e83  mov     [rsp+68h+nTypeIndex], 1; nTypeIndex
0x180087e8b  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180087e92  lea     r8, pProxyInfo; pProxyInfo
0x180087e99  lea     rdx, pPicklingInfo; pPicklingInfo
0x180087ea0  mov     rcx, [rsp+68h+Handle]; Handle
0x180087ea8  call    cs:__imp_NdrMesTypeDecode3
0x180087eae  jmp     short loc_180087EB5
0x180087eb0  mov     ebx, 0C000000Dh
0x180087eb5  mov     rcx, [rsp+68h+Handle]; Handle
0x180087ebd  test    rcx, rcx
0x180087ec0  jz      short loc_180087EC8
0x180087ec2  call    cs:__imp_MesHandleFree
0x180087ec8  mov     eax, ebx
0x180087eca  add     rsp, 48h
0x180087ece  pop     r14
0x180087ed0  pop     rdi
0x180087ed1  pop     rsi
0x180087ed2  pop     rbx
0x180087ed3  retn
```
