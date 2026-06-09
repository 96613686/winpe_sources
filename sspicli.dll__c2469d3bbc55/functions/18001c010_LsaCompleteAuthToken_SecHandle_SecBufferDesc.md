# LsaCompleteAuthToken(_SecHandle *,_SecBufferDesc *)

- ea: `0x18001c010`
- end: `0x18001c099`
- name: `?LsaCompleteAuthToken@@YAJPEAU_SecHandle@@PEAU_SecBufferDesc@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(struct _SecHandle *, struct _SecBufferDesc *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003ee0`
- `0x180005cc0`
- `0x18001c010`
- `0x180023010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001c075`
- `ntdll!RtlNtStatusToDosError` at `0x18001c075`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c07d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c07d`

## pseudocode

```c
__int64 __fastcall LsaCompleteAuthToken(struct _SecHandle *a1, struct _SecBufferDesc *a2)
{
  NTSTATUS v4; // ebx
  _QWORD *v5; // r8
  __int64 (__fastcall *v6)(ULONG_PTR, struct _SecBufferDesc *); // rax
  ULONG v7; // eax
  HLOCAL *v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = 0;
  v4 = SecLocatePackageById((HLOCAL)a1->dwLower, &v9);
  if ( v4 < 0 )
    goto LABEL_7;
  v5 = v9[23];
  if ( !v5 || (v6 = (__int64 (__fastcall *)(ULONG_PTR, struct _SecBufferDesc *))v5[8]) == 0 )
  {
    v4 = -2146893054;
LABEL_7:
    v7 = RtlNtStatusToDosError(v4);
    SetLastError(v7);
    return SspNtStatusToSecStatus(v4);
  }
  v4 = v6(a1->dwUpper, a2);
  if ( v4 < 0 )
    goto LABEL_7;
  return SspNtStatusToSecStatus(v4);
}

```

## disassembly

```asm
0x18001c010  mov     rax, rsp
0x18001c013  mov     [rax+10h], rbx
0x18001c017  mov     [rax+18h], rsi
0x18001c01b  push    rdi
0x18001c01c  sub     rsp, 20h
0x18001c020  mov     rsi, rdx
0x18001c023  mov     qword ptr [rax+8], 0
0x18001c02b  mov     rdi, rcx
0x18001c02e  lea     rdx, [rax+8]
0x18001c032  mov     rcx, [rcx]
0x18001c035  call    SecLocatePackageById
0x18001c03a  mov     ebx, eax
0x18001c03c  test    eax, eax
0x18001c03e  js      short loc_18001C073
0x18001c040  mov     rax, [rsp+28h+arg_0]
0x18001c045  mov     r8, [rax+0B8h]
0x18001c04c  test    r8, r8
0x18001c04f  jz      short loc_18001C06E
0x18001c051  mov     rax, [r8+40h]
0x18001c055  test    rax, rax
0x18001c058  jz      short loc_18001C06E
0x18001c05a  mov     rcx, [rdi+8]
0x18001c05e  mov     rdx, rsi
0x18001c061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c066  mov     ebx, eax
0x18001c068  test    eax, eax
0x18001c06a  jns     short loc_18001C083
0x18001c06c  jmp     short loc_18001C073
0x18001c06e  mov     ebx, 80090302h
0x18001c073  mov     ecx, ebx; Status
0x18001c075  call    cs:__imp_RtlNtStatusToDosError
0x18001c07b  mov     ecx, eax; dwErrCode
0x18001c07d  call    cs:__imp_SetLastError
0x18001c083  mov     ecx, ebx
0x18001c085  mov     rbx, [rsp+28h+arg_8]
0x18001c08a  mov     rsi, [rsp+28h+arg_10]
0x18001c08f  add     rsp, 20h
0x18001c093  pop     rdi
0x18001c094  jmp     SspNtStatusToSecStatus
```
