# _tsrpcOpenServer(ushort const *)

- ea: `0x180010aec`
- end: `0x180010b79`
- name: `?_tsrpcOpenServer@@YAPEAXPEBG@Z`
- size: `141`
- prototype: `CPublicBinding *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800109d0`
- `0x180010ae0`

## callees

- `0x180005db0`
- `0x180008200`
- `0x180010aec`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010b44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010b44`

## pseudocode

```c
CPublicBinding *__fastcall _tsrpcOpenServer(const unsigned __int16 *a1)
{
  CPublicBinding *v2; // rsi
  CPublicBinding *v3; // rax
  CPublicBinding *v4; // rax
  RPC_BINDING_HANDLE *v5; // rbx
  DWORD v6; // edi
  unsigned int v7; // edx
  DWORD dwErrCode; // [rsp+38h] [rbp+10h] BYREF

  dwErrCode = 0;
  v2 = 0;
  v3 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v3 )
  {
    v5 = 0;
    goto LABEL_8;
  }
  v4 = CPublicBinding::CPublicBinding(v3, a1, 0, &dwErrCode);
  v5 = (RPC_BINDING_HANDLE *)v4;
  if ( !v4 )
  {
LABEL_8:
    v6 = 14;
    goto LABEL_5;
  }
  v6 = dwErrCode;
  if ( !dwErrCode )
    v2 = v4;
LABEL_5:
  SetLastError(v6);
  if ( v6 && v5 )
    CPublicBinding::`scalar deleting destructor'(v5, v7);
  return v2;
}

```

## disassembly

```asm
0x180010aec  mov     [rsp+arg_0], rbx
0x180010af1  mov     [rsp+arg_10], rsi
0x180010af6  push    rdi
0x180010af7  sub     rsp, 20h
0x180010afb  mov     rbx, rcx
0x180010afe  mov     [rsp+28h+dwErrCode], 0
0x180010b06  xor     esi, esi
0x180010b08  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010b0f  lea     ecx, [rsi+40h]; unsigned __int64
0x180010b12  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010b17  test    rax, rax
0x180010b1a  jz      short loc_180010B61
0x180010b1c  lea     r9, [rsp+28h+dwErrCode]; unsigned int *
0x180010b21  xor     r8d, r8d; int
0x180010b24  mov     rdx, rbx; unsigned __int16 *
0x180010b27  mov     rcx, rax; this
0x180010b2a  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180010b2f  mov     rbx, rax
0x180010b32  test    rax, rax
0x180010b35  jz      short loc_180010B63
0x180010b37  mov     edi, [rsp+28h+dwErrCode]
0x180010b3b  test    edi, edi
0x180010b3d  jnz     short loc_180010B42
0x180010b3f  mov     rsi, rax
0x180010b42  mov     ecx, edi; dwErrCode
0x180010b44  call    cs:__imp_SetLastError
0x180010b4a  test    edi, edi
0x180010b4c  jnz     short loc_180010B6A
0x180010b4e  mov     rbx, [rsp+28h+arg_0]
0x180010b53  mov     rax, rsi
0x180010b56  mov     rsi, [rsp+28h+arg_10]
0x180010b5b  add     rsp, 20h
0x180010b5f  pop     rdi
0x180010b60  retn
0x180010b61  xor     ebx, ebx
0x180010b63  mov     edi, 0Eh
0x180010b68  jmp     short loc_180010B42
0x180010b6a  test    rbx, rbx
0x180010b6d  jz      short loc_180010B4E
0x180010b6f  mov     rcx, rbx; Binding
0x180010b72  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x180010b77  jmp     short loc_180010B4E
```
