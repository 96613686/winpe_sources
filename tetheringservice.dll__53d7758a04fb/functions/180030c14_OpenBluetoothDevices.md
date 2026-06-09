# OpenBluetoothDevices

- ea: `0x180030c14`
- end: `0x180030d2e`
- name: `OpenBluetoothDevices`
- size: `282`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180024c38`
- `0x18002621c`
- `0x18002fb08`
- `0x18002fbfc`

## callees

- `0x180030204`
- `0x180030c14`
- `0x180030f78`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030cf6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030cf6`

## pseudocode

```c
__int64 __fastcall OpenBluetoothDevices(_QWORD *a1, unsigned int *a2)
{
  unsigned int v4; // ebx
  __int64 result; // rax
  DWORD v6; // edi
  char *v7; // r14
  _QWORD *v8; // r13
  _QWORD *v9; // r15
  unsigned int i; // ebp
  _QWORD *v11; // rcx
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF
  __int64 v13; // [rsp+68h] [rbp+10h]

  hMem = 0;
  if ( !a1 || !a2 )
    return 87;
  v4 = *a2;
  *a2 = 10;
  *a1 = 0;
  result = EnumBluetoothDevices(a2, &hMem);
  v6 = result;
  if ( (_DWORD)result )
    return result;
  v7 = (char *)hMem;
  if ( !v4 || v4 > *(_DWORD *)hMem )
  {
    v4 = *(_DWORD *)hMem;
    if ( !*(_DWORD *)hMem )
      return 0;
  }
  v8 = 0;
  v9 = 0;
  for ( i = 0; i < v4; v8 = v11 )
  {
    hMem = 0;
    v13 = 102LL * i;
    v6 = OpenNextBlueToothDevice(&hMem, &v7[v13 + 4]);
    if ( v6 )
      break;
    v11 = hMem;
    *((_QWORD *)hMem + 3) = *(_QWORD *)&v7[v13 + 98];
    *v11 = 0;
    if ( v8 )
      *v8 = v11;
    else
      v9 = v11;
    ++i;
  }
  LocalFree(v7);
  if ( !v6 || v9 )
  {
    *a2 = i;
    *a1 = v9;
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180030c14  mov     [rsp+arg_10], rbx
0x180030c19  push    rbp
0x180030c1a  push    rsi
0x180030c1b  push    rdi
0x180030c1c  push    r12
0x180030c1e  push    r13
0x180030c20  push    r14
0x180030c22  push    r15
0x180030c24  sub     rsp, 20h
0x180030c28  mov     [rsp+58h+hMem], 0
0x180030c31  mov     rsi, rdx
0x180030c34  mov     r12, rcx
0x180030c37  test    rcx, rcx
0x180030c3a  jz      loc_180030D14
0x180030c40  test    rdx, rdx
0x180030c43  jz      loc_180030D14
0x180030c49  mov     ebx, [rdx]
0x180030c4b  mov     dword ptr [rdx], 0Ah
0x180030c51  lea     rdx, [rsp+58h+hMem]
0x180030c56  mov     qword ptr [rcx], 0
0x180030c5d  mov     rcx, rsi
0x180030c60  call    EnumBluetoothDevices
0x180030c65  mov     edi, eax
0x180030c67  test    eax, eax
0x180030c69  jnz     loc_180030D19
0x180030c6f  mov     r14, [rsp+58h+hMem]
0x180030c74  test    ebx, ebx
0x180030c76  jz      short loc_180030C7D
0x180030c78  cmp     ebx, [r14]
0x180030c7b  jbe     short loc_180030C8B
0x180030c7d  mov     ebx, [r14]
0x180030c80  test    ebx, ebx
0x180030c82  jnz     short loc_180030C8B
0x180030c84  xor     eax, eax
0x180030c86  jmp     loc_180030D19
0x180030c8b  xor     r13d, r13d
0x180030c8e  xor     r15d, r15d
0x180030c91  xor     ebp, ebp
0x180030c93  test    ebx, ebx
0x180030c95  jz      short loc_180030CF3
0x180030c97  mov     eax, ebp
0x180030c99  lea     rdx, [r14+4]
0x180030c9d  imul    rax, 66h ; 'f'
0x180030ca1  lea     rcx, [rsp+58h+hMem]
0x180030ca6  mov     [rsp+58h+hMem], 0
0x180030caf  add     rdx, rax
0x180030cb2  mov     [rsp+58h+arg_8], rax
0x180030cb7  call    OpenNextBlueToothDevice
0x180030cbc  mov     edi, eax
0x180030cbe  test    eax, eax
0x180030cc0  jnz     short loc_180030CF3
0x180030cc2  mov     rcx, [rsp+58h+hMem]
0x180030cc7  mov     rax, [rsp+58h+arg_8]
0x180030ccc  mov     rax, [rax+r14+62h]
0x180030cd1  mov     [rcx+18h], rax
0x180030cd5  mov     qword ptr [rcx], 0
0x180030cdc  test    r13, r13
0x180030cdf  jz      short loc_180030CE7
0x180030ce1  mov     [r13+0], rcx
0x180030ce5  jmp     short loc_180030CEA
0x180030ce7  mov     r15, rcx
0x180030cea  inc     ebp
0x180030cec  mov     r13, rcx
0x180030cef  cmp     ebp, ebx
0x180030cf1  jb      short loc_180030C97
0x180030cf3  mov     rcx, r14; hMem
0x180030cf6  call    cs:__imp_LocalFree
0x180030cfc  test    edi, edi
0x180030cfe  jz      short loc_180030D09
0x180030d00  test    r15, r15
0x180030d03  jnz     short loc_180030D09
0x180030d05  mov     eax, edi
0x180030d07  jmp     short loc_180030D19
0x180030d09  mov     [rsi], ebp
0x180030d0b  mov     [r12], r15
0x180030d0f  jmp     loc_180030C84
0x180030d14  mov     eax, 57h ; 'W'
0x180030d19  mov     rbx, [rsp+58h+arg_10]
0x180030d1e  add     rsp, 20h
0x180030d22  pop     r15
0x180030d24  pop     r14
0x180030d26  pop     r13
0x180030d28  pop     r12
0x180030d2a  pop     rdi
0x180030d2b  pop     rsi
0x180030d2c  pop     rbp
0x180030d2d  retn
```
