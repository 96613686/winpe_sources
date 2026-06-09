# WinStationOpenServerExW

- ea: `0x180013910`
- end: `0x18001399c`
- name: `WinStationOpenServerExW`
- size: `140`
- prototype: `CPublicBinding *__fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180024650`

## callees

- `0x180005db0`
- `0x180008200`
- `0x180013910`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013972`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013972`

## pseudocode

```c
CPublicBinding *__fastcall WinStationOpenServerExW(unsigned __int16 *a1)
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
    goto LABEL_6;
  }
  v4 = CPublicBinding::CPublicBinding(v3, a1, 1, &dwErrCode);
  v5 = (RPC_BINDING_HANDLE *)v4;
  if ( !v4 )
  {
LABEL_6:
    v6 = 14;
    goto LABEL_7;
  }
  v6 = dwErrCode;
  if ( !dwErrCode )
    v2 = v4;
LABEL_7:
  SetLastError(v6);
  if ( v6 && v5 )
    CPublicBinding::`scalar deleting destructor'(v5, v7);
  return v2;
}

```

## disassembly

```asm
0x180013910  mov     [rsp+arg_0], rbx
0x180013915  mov     [rsp+arg_10], rsi
0x18001391a  push    rdi
0x18001391b  sub     rsp, 20h
0x18001391f  mov     rbx, rcx
0x180013922  mov     [rsp+28h+dwErrCode], 0
0x18001392a  xor     esi, esi
0x18001392c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013933  lea     ecx, [rsi+40h]; unsigned __int64
0x180013936  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001393b  test    rax, rax
0x18001393e  jz      short loc_180013969
0x180013940  lea     r9, [rsp+28h+dwErrCode]; unsigned int *
0x180013945  mov     rdx, rbx; unsigned __int16 *
0x180013948  lea     r8d, [rsi+1]; int
0x18001394c  mov     rcx, rax; this
0x18001394f  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180013954  mov     rbx, rax
0x180013957  test    rax, rax
0x18001395a  jz      short loc_18001396B
0x18001395c  mov     edi, [rsp+28h+dwErrCode]
0x180013960  test    edi, edi
0x180013962  jnz     short loc_180013970
0x180013964  mov     rsi, rax
0x180013967  jmp     short loc_180013970
0x180013969  xor     ebx, ebx
0x18001396b  mov     edi, 0Eh
0x180013970  mov     ecx, edi; dwErrCode
0x180013972  call    cs:__imp_SetLastError
0x180013978  test    edi, edi
0x18001397a  jz      short loc_180013989
0x18001397c  test    rbx, rbx
0x18001397f  jz      short loc_180013989
0x180013981  mov     rcx, rbx; Binding
0x180013984  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x180013989  mov     rbx, [rsp+28h+arg_0]
0x18001398e  mov     rax, rsi
0x180013991  mov     rsi, [rsp+28h+arg_10]
0x180013996  add     rsp, 20h
0x18001399a  pop     rdi
0x18001399b  retn
```
