# CloseServiceHandle

- ea: `0x18000b460`
- end: `0x18000b4e6`
- name: `CloseServiceHandle`
- size: `134`
- prototype: `BOOL __stdcall(SC_HANDLE hSCObject)`
- caller_count: `11`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a1f0`
- `0x18000a4f0`
- `0x18000ae80`
- `0x18000b1a0`
- `0x18000bfb0`
- `0x180012840`
- `0x180039710`
- `0x1800397c0`
- `0x180039870`
- `0x180039910`
- `0x18003a330`

## callees

- `0x18000b460`
- `0x18000b4f0`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b4c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b4c2`
- `RPCRT4!NdrClientCall2` at `0x18000b49d`
- `RPCRT4!NdrClientCall2` at `0x18000b49d`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fc1e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fc1e`

## pseudocode

```c
BOOL __stdcall CloseServiceHandle(SC_HANDLE hSCObject)
{
  CLIENT_CALL_RETURN v1; // rax
  struct SC_HANDLE__ *v3; // [rsp+40h] [rbp+8h] BYREF
  CLIENT_CALL_RETURN v4; // [rsp+48h] [rbp+10h] BYREF

  v3 = hSCObject;
  LODWORD(v4.Pointer) = 0;
  LODWORD(v1.Pointer) = ScProcessServiceHandleClose(&v3, (int *)&v4);
  if ( !LODWORD(v4.Pointer) )
  {
    v4.Simple = 0;
    v1.Pointer = NdrClientCall2(&pStubDescriptor, &byte_18005FFA2, &v3).Pointer;
    v4.Pointer = v1.Pointer;
  }
  if ( LODWORD(v1.Pointer) < 0xFFFF75FF && (unsigned int)(LODWORD(v1.Pointer) - 1) > 0xFFFF75FB )
    return 1;
  SetLastError((DWORD)v1.Pointer);
  return 0;
}

```

## disassembly

```asm
0x18000b460  mov     [rsp+arg_0], rcx
0x18000b465  push    rbx
0x18000b466  sub     rsp, 30h
0x18000b46a  xor     ebx, ebx
0x18000b46c  mov     dword ptr [rsp+38h+arg_8], ebx
0x18000b470  lea     rdx, [rsp+38h+arg_8]; int *
0x18000b475  lea     rcx, [rsp+38h+arg_0]; struct SC_HANDLE__ **
0x18000b47a  call    ?ScProcessServiceHandleClose@@YAKPEAPEAUSC_HANDLE__@@PEAH@Z; ScProcessServiceHandleClose(SC_HANDLE__ * *,int *)
0x18000b47f  cmp     dword ptr [rsp+38h+arg_8], ebx
0x18000b483  jnz     short loc_18000B4B9
0x18000b485  mov     [rsp+38h+arg_8], rbx
0x18000b48a  lea     r8, [rsp+38h+arg_0]
0x18000b48f  lea     rdx, byte_18005FFA2; pFormat
0x18000b496  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000b49d  call    cs:__imp_NdrClientCall2
0x18000b4a3  mov     [rsp+38h+arg_8], rax
0x18000b4a8  mov     [rsp+38h+var_18], eax
0x18000b4ac  jmp     short loc_18000B4B9
0x18000b4ae  mov     ecx, eax; unsigned int
0x18000b4b0  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000b4b5  mov     [rsp+38h+var_18], eax
0x18000b4b9  cmp     eax, 0FFFF75FFh
0x18000b4be  jb      short loc_18000B4D0
0x18000b4c0  mov     ecx, eax; dwErrCode
0x18000b4c2  call    cs:__imp_SetLastError
0x18000b4c8  xor     eax, eax
0x18000b4ca  add     rsp, 30h
0x18000b4ce  pop     rbx
0x18000b4cf  retn
0x18000b4d0  lea     ecx, [rax-1]
0x18000b4d3  cmp     ecx, 0FFFF75FBh
0x18000b4d9  jbe     short loc_18000B4C0
0x18000b4db  mov     eax, 1
0x18000b4e0  add     rsp, 30h
0x18000b4e4  pop     rbx
0x18000b4e5  retn
0x18004fc10  push    rbp
0x18004fc12  sub     rsp, 20h
0x18004fc16  mov     rbp, rdx
0x18004fc19  mov     rcx, [rcx]
0x18004fc1c  mov     ecx, [rcx]; ExceptionCode
0x18004fc1e  call    cs:__imp_I_RpcExceptionFilter
0x18004fc24  nop
0x18004fc25  add     rsp, 20h
0x18004fc29  pop     rbp
0x18004fc2a  retn
```
