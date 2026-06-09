# WinStationOpenServerExW

- ea: `0x180014880`
- end: `0x180014913`
- name: `WinStationOpenServerExW`
- size: `147`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180025fb0`

## callees

- `0x180004330`
- `0x180006540`
- `0x180014880`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800148e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800148e2`

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
0x180014880  mov     [rsp+arg_0], rbx
0x180014885  mov     [rsp+arg_10], rsi
0x18001488a  push    rdi
0x18001488b  sub     rsp, 20h
0x18001488f  mov     rbx, rcx
0x180014892  mov     [rsp+28h+dwErrCode], 0
0x18001489a  xor     esi, esi
0x18001489c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800148a3  lea     ecx, [rsi+40h]; unsigned __int64
0x1800148a6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800148ab  test    rax, rax
0x1800148ae  jz      short loc_1800148D9
0x1800148b0  lea     r9, [rsp+28h+dwErrCode]; unsigned int *
0x1800148b5  mov     rdx, rbx; unsigned __int16 *
0x1800148b8  lea     r8d, [rsi+1]; int
0x1800148bc  mov     rcx, rax; this
0x1800148bf  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x1800148c4  mov     rbx, rax
0x1800148c7  test    rax, rax
0x1800148ca  jz      short loc_1800148DB
0x1800148cc  mov     edi, [rsp+28h+dwErrCode]
0x1800148d0  test    edi, edi
0x1800148d2  jnz     short loc_1800148E0
0x1800148d4  mov     rsi, rax
0x1800148d7  jmp     short loc_1800148E0
0x1800148d9  xor     ebx, ebx
0x1800148db  mov     edi, 0Eh
0x1800148e0  mov     ecx, edi; dwErrCode
0x1800148e2  call    cs:__imp_SetLastError
0x1800148e9  nop     dword ptr [rax+rax+00h]
0x1800148ee  test    edi, edi
0x1800148f0  jz      short loc_1800148FF
0x1800148f2  test    rbx, rbx
0x1800148f5  jz      short loc_1800148FF
0x1800148f7  mov     rcx, rbx; Binding
0x1800148fa  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x1800148ff  mov     rbx, [rsp+28h+arg_0]
0x180014904  mov     rax, rsi
0x180014907  mov     rsi, [rsp+28h+arg_10]
0x18001490c  add     rsp, 20h
0x180014910  pop     rdi
0x180014911  retn
```
