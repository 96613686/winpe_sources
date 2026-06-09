# MvmpNegotiateProtocol

- ea: `0x14000dc20`
- end: `0x14000dcd9`
- name: `MvmpNegotiateProtocol`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000d704`

## callees

- `0x14000dc20`
- `0x14000dde8`
- `0x14000df90`
- `0x14000e008`

## pseudocode

```c
__int64 __fastcall MvmpNegotiateProtocol(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  _DWORD *v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx

  v4 = 3;
  v5 = (_DWORD *)(qword_140020980 + ((unsigned __int64)(unsigned int)dword_1400209BC << 8));
  while ( *v5 )
    MvmpCompleteMessage(&CrashMiniVmbusContext, a3);
  v6 = 0;
  do
  {
    v7 = *((unsigned int *)MvmSupportedVmbusVersions + v6);
    dword_140020A00 = *((_DWORD *)MvmSupportedVmbusVersions + v6);
    if ( byte_140020A92 && (unsigned int)v7 < 0x40000 )
      return v4;
    v8 = MvmpSendInitiateContact(v7, a2, a3);
    v4 = v8;
    if ( v8 != 3 )
      break;
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (unsigned int)v6 < 3 );
  if ( v8 )
    return v4;
  if ( !byte_140020A92 || (unsigned int)dword_140020A00 < 0x40000 )
    return 0;
  MvmpSendUnload(v9, a3);
  return MvmpSendInitiateContact(v12, v11, a3);
}

```

## disassembly

```asm
0x14000dc20  mov     [rsp+arg_0], rbx
0x14000dc25  mov     [rsp+arg_8], rsi
0x14000dc2a  push    rdi
0x14000dc2b  sub     rsp, 20h
0x14000dc2f  mov     ebx, cs:dword_1400209BC
0x14000dc35  mov     rsi, r8
0x14000dc38  shl     rbx, 8
0x14000dc3c  mov     edi, 3
0x14000dc41  add     rbx, cs:qword_140020980
0x14000dc48  jmp     short loc_14000DC59
0x14000dc4a  mov     rdx, rsi
0x14000dc4d  lea     rcx, CrashMiniVmbusContext
0x14000dc54  call    MvmpCompleteMessage
0x14000dc59  mov     eax, [rbx]
0x14000dc5b  test    eax, eax
0x14000dc5d  jnz     short loc_14000DC4A
0x14000dc5f  xor     ebx, ebx
0x14000dc61  cmp     cs:byte_140020A92, 0
0x14000dc68  lea     rcx, MvmSupportedVmbusVersions
0x14000dc6f  mov     ecx, [rcx+rbx*4]
0x14000dc72  mov     cs:dword_140020A00, ecx
0x14000dc78  jz      short loc_14000DC82
0x14000dc7a  cmp     ecx, 40000h
0x14000dc80  jb      short loc_14000DC9B
0x14000dc82  mov     r8, rsi
0x14000dc85  call    MvmpSendInitiateContact
0x14000dc8a  mov     edi, eax
0x14000dc8c  cmp     eax, 3
0x14000dc8f  jnz     short loc_14000DC97
0x14000dc91  inc     ebx
0x14000dc93  cmp     ebx, eax
0x14000dc95  jb      short loc_14000DC61
0x14000dc97  test    eax, eax
0x14000dc99  jz      short loc_14000DC9F
0x14000dc9b  mov     eax, edi
0x14000dc9d  jmp     short loc_14000DCC8
0x14000dc9f  cmp     cs:byte_140020A92, 0
0x14000dca6  jz      short loc_14000DCC6
0x14000dca8  cmp     cs:dword_140020A00, 40000h
0x14000dcb2  jb      short loc_14000DCC6
0x14000dcb4  mov     rdx, rsi
0x14000dcb7  call    MvmpSendUnload
0x14000dcbc  mov     r8, rsi
0x14000dcbf  call    MvmpSendInitiateContact
0x14000dcc4  jmp     short loc_14000DCC8
0x14000dcc6  xor     eax, eax
0x14000dcc8  mov     rbx, [rsp+28h+arg_0]
0x14000dccd  mov     rsi, [rsp+28h+arg_8]
0x14000dcd2  add     rsp, 20h
0x14000dcd6  pop     rdi
0x14000dcd7  retn
```
