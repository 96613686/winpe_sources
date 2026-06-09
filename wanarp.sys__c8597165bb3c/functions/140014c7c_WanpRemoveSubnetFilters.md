# WanpRemoveSubnetFilters

- ea: `0x140014c7c`
- end: `0x140014dd6`
- name: `WanpRemoveSubnetFilters`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004124`
- `0x140010448`
- `0x14001324c`

## callees

- `0x1400143e4`
- `0x140014c7c`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteById0` at `0x140014d0b`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140014d37`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140014d7a`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140014da6`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140014d0b`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140014d37`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140014d7a`
- `fwpkclnt!FwpmFilterDeleteById0` at `0x140014da6`

## pseudocode

```c
__int64 __fastcall WanpRemoveSubnetFilters(unsigned int *a1, int a2)
{
  int v2; // r11d
  unsigned int v3; // r10d
  int v6; // r8d
  int v7; // r10d
  int v8; // r11d
  unsigned int *v9; // rsi
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // rsi
  UINT64 v13; // rdx
  UINT64 v14; // rdx
  __int64 v15; // rdi
  UINT64 v16; // rdx
  UINT64 v17; // rdx
  int v19; // [rsp+50h] [rbp+8h] BYREF

  v2 = a1[1];
  v3 = *a1;
  v19 = 0;
  v6 = ComputeSizeOfSubnetFilterInfoRequired(v3, v2, &v19);
  if ( v6 >= 0 )
  {
    if ( a2 == v19 )
    {
      v9 = a1 + 2;
      if ( v8 )
        v9 = 0;
      v10 = 0;
      v11 = (unsigned __int64)(a1 + 2) & -(__int64)(v8 != 0);
      if ( v8 )
      {
        if ( v7 )
        {
          do
          {
            v12 = 184LL * v10;
            v13 = *(_QWORD *)(v12 + v11 + 80);
            if ( v13 )
            {
              v6 = FwpmFilterDeleteById0(engineHandle, v13);
              *(_QWORD *)(v12 + v11 + 80) = 0;
            }
            v14 = *(_QWORD *)(v12 + v11 + 168);
            if ( v14 )
            {
              v6 = FwpmFilterDeleteById0(engineHandle, v14);
              *(_QWORD *)(v12 + v11 + 168) = 0;
            }
            ++v10;
          }
          while ( v10 < *a1 );
        }
      }
      else if ( v7 )
      {
        do
        {
          v15 = 50LL * v10;
          v16 = *(_QWORD *)&v9[v15 + 20];
          if ( v16 )
          {
            v6 = FwpmFilterDeleteById0(engineHandle, v16);
            *(_QWORD *)&v9[v15 + 20] = 0;
          }
          v17 = *(_QWORD *)&v9[v15 + 42];
          if ( v17 )
          {
            v6 = FwpmFilterDeleteById0(engineHandle, v17);
            *(_QWORD *)&v9[v15 + 42] = 0;
          }
          ++v10;
        }
        while ( v10 < *a1 );
      }
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140014c7c  push    rbx
0x140014c7e  push    rsi
0x140014c7f  push    rdi
0x140014c80  push    r14
0x140014c82  sub     rsp, 28h
0x140014c86  mov     r11d, [rcx+4]
0x140014c8a  lea     r8, [rsp+48h+arg_0]
0x140014c8f  mov     r10d, [rcx]
0x140014c92  mov     ebx, edx
0x140014c94  mov     r14, rcx
0x140014c97  mov     [rsp+48h+arg_0], 0
0x140014c9f  mov     edx, r11d
0x140014ca2  mov     ecx, r10d
0x140014ca5  call    ComputeSizeOfSubnetFilterInfoRequired
0x140014caa  mov     r8d, eax
0x140014cad  test    eax, eax
0x140014caf  js      loc_140014DC8
0x140014cb5  cmp     ebx, [rsp+48h+arg_0]
0x140014cb9  jz      short loc_140014CC6
0x140014cbb  mov     r8d, 0C000000Dh
0x140014cc1  jmp     loc_140014DC8
0x140014cc6  xor     eax, eax
0x140014cc8  lea     rcx, [r14+8]
0x140014ccc  test    r11d, r11d
0x140014ccf  mov     rsi, rcx
0x140014cd2  cmovnz  rsi, rax
0x140014cd6  mov     eax, r11d
0x140014cd9  neg     eax
0x140014cdb  sbb     rdi, rdi
0x140014cde  xor     ebx, ebx
0x140014ce0  and     rdi, rcx
0x140014ce3  test    r11d, r11d
0x140014ce6  jz      short loc_140014D5B
0x140014ce8  test    r10d, r10d
0x140014ceb  jz      loc_140014DC8
0x140014cf1  mov     eax, ebx
0x140014cf3  imul    rsi, rax, 0B8h
0x140014cfa  mov     rdx, [rsi+rdi+50h]; id
0x140014cff  test    rdx, rdx
0x140014d02  jz      short loc_140014D23
0x140014d04  mov     rcx, cs:engineHandle; engineHandle
0x140014d0b  call    cs:__imp_FwpmFilterDeleteById0
0x140014d12  nop     dword ptr [rax+rax+00h]
0x140014d17  mov     r8d, eax
0x140014d1a  mov     qword ptr [rsi+rdi+50h], 0
0x140014d23  mov     rdx, [rsi+rdi+0A8h]; id
0x140014d2b  test    rdx, rdx
0x140014d2e  jz      short loc_140014D52
0x140014d30  mov     rcx, cs:engineHandle; engineHandle
0x140014d37  call    cs:__imp_FwpmFilterDeleteById0
0x140014d3e  nop     dword ptr [rax+rax+00h]
0x140014d43  mov     r8d, eax
0x140014d46  mov     qword ptr [rsi+rdi+0A8h], 0
0x140014d52  inc     ebx
0x140014d54  cmp     ebx, [r14]
0x140014d57  jb      short loc_140014CF1
0x140014d59  jmp     short loc_140014DC8
0x140014d5b  test    r10d, r10d
0x140014d5e  jz      short loc_140014DC8
0x140014d60  mov     eax, ebx
0x140014d62  imul    rdi, rax, 0C8h
0x140014d69  mov     rdx, [rdi+rsi+50h]; id
0x140014d6e  test    rdx, rdx
0x140014d71  jz      short loc_140014D92
0x140014d73  mov     rcx, cs:engineHandle; engineHandle
0x140014d7a  call    cs:__imp_FwpmFilterDeleteById0
0x140014d81  nop     dword ptr [rax+rax+00h]
0x140014d86  mov     r8d, eax
0x140014d89  mov     qword ptr [rdi+rsi+50h], 0
0x140014d92  mov     rdx, [rdi+rsi+0A8h]; id
0x140014d9a  test    rdx, rdx
0x140014d9d  jz      short loc_140014DC1
0x140014d9f  mov     rcx, cs:engineHandle; engineHandle
0x140014da6  call    cs:__imp_FwpmFilterDeleteById0
0x140014dad  nop     dword ptr [rax+rax+00h]
0x140014db2  mov     r8d, eax
0x140014db5  mov     qword ptr [rdi+rsi+0A8h], 0
0x140014dc1  inc     ebx
0x140014dc3  cmp     ebx, [r14]
0x140014dc6  jb      short loc_140014D60
0x140014dc8  mov     eax, r8d
0x140014dcb  add     rsp, 28h
0x140014dcf  pop     r14
0x140014dd1  pop     rdi
0x140014dd2  pop     rsi
0x140014dd3  pop     rbx
0x140014dd4  retn
```
