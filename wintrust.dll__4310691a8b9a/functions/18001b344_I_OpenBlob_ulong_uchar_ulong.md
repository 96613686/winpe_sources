# I_OpenBlob(ulong,uchar *,ulong)

- ea: `0x18001b344`
- end: `0x18001b3d5`
- name: `?I_OpenBlob@@YAPEAXKPEAEK@Z`
- size: `145`
- prototype: `void *(unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180010350`
- `0x18001b03c`
- `0x18003f904`

## callees

- `0x18001b344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b3cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b3cb`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18001b381`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18001b381`
- `CRYPT32!CryptMsgUpdate` at `0x18001b39e`
- `CRYPT32!CryptMsgUpdate` at `0x18001b39e`
- `CRYPT32!CryptMsgClose` at `0x18001b3be`
- `CRYPT32!CryptMsgClose` at `0x18001b3be`

## pseudocode

```c
void *__fastcall I_OpenBlob(__int64 a1, unsigned __int8 *a2, DWORD a3)
{
  HCRYPTMSG v5; // rax
  void *v6; // rbx

  if ( !a2 || !a3 )
  {
    SetLastError(0xA0u);
    return 0;
  }
  v5 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v6 = v5;
  if ( v5 && !CryptMsgUpdate(v5, a2, a3, 1) )
  {
    CryptMsgClose(v6);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18001b344  mov     rax, rsp
0x18001b347  mov     [rax+8], rbx
0x18001b34b  mov     [rax+10h], rsi
0x18001b34f  push    rdi
0x18001b350  sub     rsp, 30h
0x18001b354  mov     edi, r8d
0x18001b357  mov     rsi, rdx
0x18001b35a  test    rdx, rdx
0x18001b35d  jz      short loc_18001B3C6
0x18001b35f  test    r8d, r8d
0x18001b362  jz      short loc_18001B3C6
0x18001b364  mov     qword ptr [rax-10h], 0
0x18001b36c  xor     r9d, r9d; hCryptProv
0x18001b36f  xor     r8d, r8d; dwMsgType
0x18001b372  mov     qword ptr [rax-18h], 0
0x18001b37a  xor     edx, edx; dwFlags
0x18001b37c  mov     ecx, 10001h; dwMsgEncodingType
0x18001b381  call    cs:__imp_CryptMsgOpenToDecode
0x18001b387  mov     rbx, rax
0x18001b38a  test    rax, rax
0x18001b38d  jz      short loc_18001B3A8
0x18001b38f  mov     r9d, 1; fFinal
0x18001b395  mov     r8d, edi; cbData
0x18001b398  mov     rdx, rsi; pbData
0x18001b39b  mov     rcx, rax; hCryptMsg
0x18001b39e  call    cs:__imp_CryptMsgUpdate
0x18001b3a4  test    eax, eax
0x18001b3a6  jz      short loc_18001B3BB
0x18001b3a8  mov     rsi, [rsp+38h+arg_8]
0x18001b3ad  mov     rax, rbx
0x18001b3b0  mov     rbx, [rsp+38h+arg_0]
0x18001b3b5  add     rsp, 30h
0x18001b3b9  pop     rdi
0x18001b3ba  retn
0x18001b3bb  mov     rcx, rbx; hCryptMsg
0x18001b3be  call    cs:__imp_CryptMsgClose
0x18001b3c4  jmp     short loc_18001B3D1
0x18001b3c6  mov     ecx, 0A0h; dwErrCode
0x18001b3cb  call    cs:__imp_SetLastError
0x18001b3d1  xor     ebx, ebx
0x18001b3d3  jmp     short loc_18001B3A8
```
