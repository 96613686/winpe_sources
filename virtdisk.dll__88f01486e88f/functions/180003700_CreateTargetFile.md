# CreateTargetFile

- ea: `0x180003700`
- end: `0x1800037eb`
- name: `CreateTargetFile`
- size: `235`
- prototype: `DWORD __fastcall(const WCHAR *, void *, char, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180002740`

## callees

- `0x180003700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000376a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000376a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000377f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000377f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800037d0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800037d0`

## pseudocode

```c
DWORD __fastcall CreateTargetFile(const WCHAR *a1, void *a2, char a3, _QWORD *a4)
{
  struct _SECURITY_ATTRIBUTES *p_SecurityAttributes; // r9
  HANDLE FileW; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-40h] BYREF
  __int16 InBuffer; // [rsp+98h] [rbp+10h] BYREF

  BytesReturned = 0;
  InBuffer = 0;
  p_SecurityAttributes = 0;
  memset(&SecurityAttributes, 0, 20);
  if ( a2 )
  {
    p_SecurityAttributes = &SecurityAttributes;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = a2;
    SecurityAttributes.bInheritHandle = 0;
  }
  FileW = CreateFileW(a1, 0xC0000000, 7u, p_SecurityAttributes, 1u, 0x100080u, 0);
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  if ( !a3 )
  {
    InBuffer = 0;
    DeviceIoControl(FileW, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0);
  }
  *a4 = FileW;
  return 0;
}

```

## disassembly

```asm
0x180003700  push    rbx
0x180003702  push    rbp
0x180003703  push    rsi
0x180003704  push    rdi
0x180003705  sub     rsp, 68h
0x180003709  xor     ebp, ebp
0x18000370b  xor     eax, eax
0x18000370d  mov     [rsp+88h+BytesReturned], ebp
0x180003711  xorps   xmm0, xmm0
0x180003714  mov     [rsp+88h+InBuffer], bp
0x18000371c  mov     rdi, r9
0x18000371f  mov     [rsp+88h+SecurityAttributes.bInheritHandle], eax
0x180003723  movzx   esi, r8b
0x180003727  mov     r9d, ebp
0x18000372a  movups  xmmword ptr [rsp+88h+SecurityAttributes.nLength], xmm0
0x18000372f  test    rdx, rdx
0x180003732  jz      short loc_18000374A
0x180003734  lea     r9, [rsp+88h+SecurityAttributes]; lpSecurityAttributes
0x180003739  mov     [rsp+88h+SecurityAttributes.nLength], 18h
0x180003741  mov     [rsp+88h+SecurityAttributes.lpSecurityDescriptor], rdx
0x180003746  mov     [rsp+88h+SecurityAttributes.bInheritHandle], ebp
0x18000374a  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x18000374f  mov     edx, 0C0000000h; dwDesiredAccess
0x180003754  mov     [rsp+88h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18000375c  mov     r8d, 7; dwShareMode
0x180003762  mov     [rsp+88h+dwCreationDisposition], 1; dwCreationDisposition
0x18000376a  call    cs:__imp_CreateFileW
0x180003771  nop     dword ptr [rax+rax+00h]
0x180003776  mov     rbx, rax
0x180003779  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000377d  jnz     short loc_180003795
0x18000377f  call    cs:__imp_GetLastError
0x180003786  nop     dword ptr [rax+rax+00h]
0x18000378b  add     rsp, 68h
0x18000378f  pop     rdi
0x180003790  pop     rsi
0x180003791  pop     rbp
0x180003792  pop     rbx
0x180003793  retn
0x180003795  test    sil, sil
0x180003798  jnz     short loc_1800037DC
0x18000379a  mov     [rsp+88h+lpOverlapped], rbp; lpOverlapped
0x18000379f  lea     rax, [rsp+88h+BytesReturned]
0x1800037a4  mov     [rsp+88h+hTemplateFile], rax; lpBytesReturned
0x1800037a9  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x1800037b1  mov     [rsp+88h+dwFlagsAndAttributes], ebp; nOutBufferSize
0x1800037b5  mov     r9d, 2; nInBufferSize
0x1800037bb  mov     edx, 9C040h; dwIoControlCode
0x1800037c0  mov     qword ptr [rsp+88h+dwCreationDisposition], rbp; lpOutBuffer
0x1800037c5  mov     rcx, rbx; hDevice
0x1800037c8  mov     [rsp+88h+InBuffer], bp
0x1800037d0  call    cs:__imp_DeviceIoControl
0x1800037d7  nop     dword ptr [rax+rax+00h]
0x1800037dc  mov     [rdi], rbx
0x1800037df  xor     eax, eax
0x1800037e1  add     rsp, 68h
0x1800037e5  pop     rdi
0x1800037e6  pop     rsi
0x1800037e7  pop     rbp
0x1800037e8  pop     rbx
0x1800037e9  retn
```
