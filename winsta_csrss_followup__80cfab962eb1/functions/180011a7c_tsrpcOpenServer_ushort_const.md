# _tsrpcOpenServer(ushort const *)

- ea: `0x180011a7c`
- end: `0x180011b10`
- name: `?_tsrpcOpenServer@@YAPEAXPEBG@Z`
- size: `148`
- prototype: `void *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180011950`
- `0x180011a70`

## callees

- `0x180004330`
- `0x180006540`
- `0x180011a7c`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011ad4`

## pseudocode

```c
CPublicBinding *__fastcall _tsrpcOpenServer(unsigned __int16 *a1)
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
0x180011a7c  mov     [rsp+arg_0], rbx
0x180011a81  mov     [rsp+arg_10], rsi
0x180011a86  push    rdi
0x180011a87  sub     rsp, 20h
0x180011a8b  mov     rbx, rcx
0x180011a8e  mov     [rsp+28h+dwErrCode], 0
0x180011a96  xor     esi, esi
0x180011a98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011a9f  lea     ecx, [rsi+40h]; unsigned __int64
0x180011aa2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011aa7  test    rax, rax
0x180011aaa  jz      short loc_180011AF8
0x180011aac  lea     r9, [rsp+28h+dwErrCode]; unsigned int *
0x180011ab1  xor     r8d, r8d; int
0x180011ab4  mov     rdx, rbx; unsigned __int16 *
0x180011ab7  mov     rcx, rax; this
0x180011aba  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180011abf  mov     rbx, rax
0x180011ac2  test    rax, rax
0x180011ac5  jz      short loc_180011AFA
0x180011ac7  mov     edi, [rsp+28h+dwErrCode]
0x180011acb  test    edi, edi
0x180011acd  jnz     short loc_180011AD2
0x180011acf  mov     rsi, rax
0x180011ad2  mov     ecx, edi; dwErrCode
0x180011ad4  call    cs:__imp_SetLastError
0x180011adb  nop     dword ptr [rax+rax+00h]
0x180011ae0  test    edi, edi
0x180011ae2  jnz     short loc_180011B01
0x180011ae4  mov     rbx, [rsp+28h+arg_0]
0x180011ae9  mov     rax, rsi
0x180011aec  mov     rsi, [rsp+28h+arg_10]
0x180011af1  add     rsp, 20h
0x180011af5  pop     rdi
0x180011af6  retn
0x180011af8  xor     ebx, ebx
0x180011afa  mov     edi, 0Eh
0x180011aff  jmp     short loc_180011AD2
0x180011b01  test    rbx, rbx
0x180011b04  jz      short loc_180011AE4
0x180011b06  mov     rcx, rbx; Binding
0x180011b09  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x180011b0e  jmp     short loc_180011AE4
```
