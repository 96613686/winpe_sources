# SHFreeShared

- ea: `0x18001fdd0`
- end: `0x18001fe54`
- name: `SHFreeShared`
- size: `132`
- prototype: `BOOL __stdcall(HANDLE hData, DWORD dwProcessId)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001fdd0`
- `0x180020f00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fdfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fdfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe31`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001fe3c`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18001fe3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe0a`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall SHFreeShared(HANDLE hData, DWORD dwProcessId)
{
  BOOL v3; // edi
  HANDLE hObject; // [rsp+30h] [rbp+8h] BYREF

  v3 = 1;
  if ( hData )
  {
    if ( (char *)hData - 49152 <= (char *)0x3FFF )
    {
      hObject = 0;
      if ( (int)UnpackTransferAtom((ATOM)hData, *(__int64 *)&dwProcessId, 1, &hObject) >= 0 )
        v3 = CloseHandle(hObject);
      GlobalDeleteAtom((ATOM)hData);
    }
    else if ( GetCurrentProcessId() == dwProcessId )
    {
      CoTaskMemFree(hData);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001fdd0  mov     [rsp+arg_8], rbx
0x18001fdd5  mov     [rsp+arg_10], rsi
0x18001fdda  push    rdi
0x18001fddb  sub     rsp, 20h
0x18001fddf  mov     esi, edx
0x18001fde1  mov     rbx, rcx
0x18001fde4  mov     edi, 1
0x18001fde9  test    rcx, rcx
0x18001fdec  jz      short loc_18001FE42
0x18001fdee  lea     rax, [rcx-0C000h]
0x18001fdf5  cmp     rax, 3FFFh
0x18001fdfb  jbe     short loc_18001FE12
0x18001fdfd  call    cs:__imp_GetCurrentProcessId
0x18001fe03  cmp     eax, esi
0x18001fe05  jnz     short loc_18001FE42
0x18001fe07  mov     rcx, rbx; pv
0x18001fe0a  call    cs:__imp_CoTaskMemFree
0x18001fe10  jmp     short loc_18001FE42
0x18001fe12  lea     r9, [rsp+28h+hObject]; void **
0x18001fe17  mov     [rsp+28h+hObject], 0
0x18001fe20  mov     r8d, edi; unsigned int
0x18001fe23  call    ?UnpackTransferAtom@@YAJGKKPEAPEAX@Z; UnpackTransferAtom(ushort,ulong,ulong,void * *)
0x18001fe28  test    eax, eax
0x18001fe2a  js      short loc_18001FE39
0x18001fe2c  mov     rcx, [rsp+28h+hObject]; hObject
0x18001fe31  call    cs:__imp_CloseHandle
0x18001fe37  mov     edi, eax
0x18001fe39  movzx   ecx, bx; nAtom
0x18001fe3c  call    cs:__imp_GlobalDeleteAtom
0x18001fe42  mov     rbx, [rsp+28h+arg_8]
0x18001fe47  mov     eax, edi
0x18001fe49  mov     rsi, [rsp+28h+arg_10]
0x18001fe4e  add     rsp, 20h
0x18001fe52  pop     rdi
0x18001fe53  retn
```
