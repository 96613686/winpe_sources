# SymCryptFdefModulusCreate

- ea: `0x18002bc28`
- end: `0x18002bc85`
- name: `SymCryptFdefModulusCreate`
- size: `93`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180023030`
- `0x1800231c4`
- `0x180023e94`

## callees

- `0x18002bc28`
- `0x18002bd98`
- `0x18002c0f4`

## pseudocode

```c
__int64 __fastcall SymCryptFdefModulusCreate(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  unsigned int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned __int64 v7; // r11

  v3 = 0;
  v4 = SymCryptFdefSizeofModulusFromDigits(a3);
  if ( v4 && v7 >= v4 )
  {
    *(_DWORD *)v6 = 1733099520;
    *(_DWORD *)(v6 + 16) = (_DWORD)v5 << 6;
    v3 = v6;
    *(_DWORD *)(v6 + 4) = v5;
    *(_QWORD *)(v6 + 8) = v4;
    SymCryptFdefDivisorCreate(v6 + 64, v7 - 64, v5);
  }
  return v3;
}

```

## disassembly

```asm
0x18002bc28  push    rbx
0x18002bc2a  sub     rsp, 20h
0x18002bc2e  mov     r9, rcx
0x18002bc31  mov     r11, rdx
0x18002bc34  mov     ecx, r8d
0x18002bc37  xor     ebx, ebx
0x18002bc39  call    SymCryptFdefSizeofModulusFromDigits
0x18002bc3e  mov     r10d, eax
0x18002bc41  test    eax, eax
0x18002bc43  jz      short loc_18002BC7B
0x18002bc45  cmp     r11, r10
0x18002bc48  jb      short loc_18002BC7B
0x18002bc4a  mov     ecx, r8d
0x18002bc4d  mov     dword ptr [r9], 674D0000h
0x18002bc54  shl     ecx, 6
0x18002bc57  lea     rdx, [r11-40h]
0x18002bc5b  mov     [r9+10h], ecx
0x18002bc5f  mov     rbx, r9
0x18002bc62  lea     rcx, [r9+40h]
0x18002bc66  mov     [r9+4], r8d
0x18002bc6a  mov     [r9+8], r10d
0x18002bc6e  mov     dword ptr [r9+0Ch], 0
0x18002bc76  call    SymCryptFdefDivisorCreate
0x18002bc7b  mov     rax, rbx
0x18002bc7e  add     rsp, 20h
0x18002bc82  pop     rbx
0x18002bc83  retn
```
