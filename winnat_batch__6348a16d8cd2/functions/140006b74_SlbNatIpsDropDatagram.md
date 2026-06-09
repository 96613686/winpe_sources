# SlbNatIpsDropDatagram

- ea: `0x140006b74`
- end: `0x140006c78`
- name: `SlbNatIpsDropDatagram`
- size: `260`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400020e0`
- `0x140006340`
- `0x140006558`
- `0x140006764`
- `0x140006f04`
- `0x14001515c`
- `0x140015400`

## callees

- `0x140006b74`
- `0x1400077fc`
- `0x14001ef70`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140006b8f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140006b8f`

## pseudocode

```c
PVOID __fastcall SlbNatIpsDropDatagram(__int64 a1, _QWORD *a2, char a3, int a4)
{
  __int64 CurrentProcessorNumber; // r15
  unsigned int v9; // edi
  _QWORD *v10; // rax
  __int64 v11; // rdx
  PVOID result; // rax
  __int128 v13; // [rsp+40h] [rbp-58h] BYREF
  __int64 v14; // [rsp+50h] [rbp-48h]

  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v9 = 1;
  v13 = 0;
  LOBYTE(v14) = 0;
  if ( Microsoft_Windows_WinNatEnableBits < 0 && *(_WORD *)a1 == 2 )
    SlbNatIpsLogIPv4Datagram(*(_DWORD *)(a1 + 24), *(_DWORD *)(a1 + 32), *(_QWORD *)(a1 + 40), 0, 0, a2, 1, a4);
  v10 = (_QWORD *)*a2;
  while ( v10 )
  {
    v10 = (_QWORD *)*v10;
    ++v9;
  }
  LOBYTE(v13) = 0;
  *((_QWORD *)&v13 + 1) = a2;
  v14 = 0;
  if ( gAccount )
  {
    do
    {
      _InterlockedIncrement64(&gNBLDrop);
      a2 = (_QWORD *)*a2;
    }
    while ( a2 );
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 32LL))(
    *(_QWORD *)(a1 + 8),
    *(_QWORD *)(a1 + 48),
    &v13);
  v11 = 136 * CurrentProcessorNumber;
  *((_QWORD *)qword_140026B68 + 17 * CurrentProcessorNumber + 13) += v9;
  result = qword_140026B68;
  if ( a3 == 6 )
  {
    *(_DWORD *)((char *)qword_140026B68 + v11 + 16) += v9;
  }
  else if ( a3 == 17 )
  {
    *(_DWORD *)((char *)qword_140026B68 + v11 + 40) += v9;
  }
  else
  {
    *(_DWORD *)((char *)qword_140026B68 + v11 + 64) += v9;
  }
  return result;
}

```

## disassembly

```asm
0x140006b74  push    rbx
0x140006b76  push    rbp
0x140006b77  push    rsi
0x140006b78  push    rdi
0x140006b79  push    r14
0x140006b7b  push    r15
0x140006b7d  sub     rsp, 68h
0x140006b81  mov     rsi, rcx
0x140006b84  mov     r14d, r9d
0x140006b87  xor     ecx, ecx; ProcNumber
0x140006b89  mov     bpl, r8b
0x140006b8c  mov     rbx, rdx
0x140006b8f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140006b96  nop     dword ptr [rax+rax+00h]
0x140006b9b  mov     r15d, eax
0x140006b9e  xorps   xmm0, xmm0
0x140006ba1  xor     eax, eax
0x140006ba3  mov     edi, 1
0x140006ba8  cmp     cs:Microsoft_Windows_WinNatEnableBits, al
0x140006bae  movups  [rsp+98h+var_58], xmm0
0x140006bb3  mov     byte ptr [rsp+98h+var_48], al
0x140006bb7  jge     short loc_140006BE3
0x140006bb9  cmp     word ptr [rsi], 2
0x140006bbd  jnz     short loc_140006BE3
0x140006bbf  mov     r8, [rsi+28h]
0x140006bc3  xor     r9d, r9d
0x140006bc6  mov     edx, [rsi+20h]
0x140006bc9  mov     ecx, [rsi+18h]
0x140006bcc  mov     [rsp+98h+var_60], r14d
0x140006bd1  mov     [rsp+98h+var_68], edi
0x140006bd5  mov     [rsp+98h+var_70], rbx
0x140006bda  mov     [rsp+98h+var_78], eax
0x140006bde  call    SlbNatIpsLogIPv4Datagram
0x140006be3  mov     rax, [rbx]
0x140006be6  jmp     short loc_140006BED
0x140006be8  mov     rax, [rax]
0x140006beb  inc     edi
0x140006bed  test    rax, rax
0x140006bf0  jnz     short loc_140006BE8
0x140006bf2  cmp     cs:gAccount, eax
0x140006bf8  mov     byte ptr [rsp+98h+var_58], al
0x140006bfc  mov     qword ptr [rsp+98h+var_58+8], rbx
0x140006c01  mov     [rsp+98h+var_48], rax
0x140006c06  jz      short loc_140006C18
0x140006c08  lock inc cs:gNBLDrop
0x140006c10  mov     rbx, [rbx]
0x140006c13  test    rbx, rbx
0x140006c16  jnz     short loc_140006C08
0x140006c18  mov     rax, [rsi+10h]
0x140006c1c  lea     r8, [rsp+98h+var_58]
0x140006c21  mov     rdx, [rsi+30h]
0x140006c25  mov     rcx, [rsi+8]
0x140006c29  mov     rax, [rax+20h]
0x140006c2d  call    _guard_dispatch_icall
0x140006c32  mov     rcx, cs:qword_140026B68
0x140006c39  imul    rdx, r15, 88h
0x140006c40  mov     eax, edi
0x140006c42  add     [rdx+rcx+68h], rax
0x140006c47  mov     rax, cs:qword_140026B68
0x140006c4e  cmp     bpl, 6
0x140006c52  jnz     short loc_140006C5A
0x140006c54  add     [rdx+rax+10h], edi
0x140006c58  jmp     short loc_140006C6A
0x140006c5a  cmp     bpl, 11h
0x140006c5e  jnz     short loc_140006C66
0x140006c60  add     [rdx+rax+28h], edi
0x140006c64  jmp     short loc_140006C6A
0x140006c66  add     [rdx+rax+40h], edi
0x140006c6a  add     rsp, 68h
0x140006c6e  pop     r15
0x140006c70  pop     r14
0x140006c72  pop     rdi
0x140006c73  pop     rsi
0x140006c74  pop     rbp
0x140006c75  pop     rbx
0x140006c76  retn
```
