# CACSecurityPage::SetNewIHVSecurityProfileData(ushort *)

- ea: `0x18000cdc4`
- end: `0x18000ce64`
- name: `?SetNewIHVSecurityProfileData@CACSecurityPage@@AEAA_JPEAG@Z`
- size: `160`
- prototype: `__int64 __fastcall(CACSecurityPage *this, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009380`
- `0x18000a29c`
- `0x18000a4b4`
- `0x18000a690`
- `0x18000d714`

## callees

- `0x180001e26`
- `0x18000cdc4`

## import_xrefs

- `wlanapi!WpFreeMemory` at `0x18000ce10`
- `wlanapi!WpFreeMemory` at `0x18000ce10`
- `wlanapi!WpAllocMemory` at `0x18000ce20`
- `wlanapi!WpAllocMemory` at `0x18000ce20`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::SetNewIHVSecurityProfileData(CACSecurityPage *this, unsigned __int16 *a2)
{
  int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rsi
  size_t v6; // r14
  void *v7; // rax
  void *v8; // rbp

  v3 = 0;
  if ( a2 )
  {
    v4 = -1;
    v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 552LL) + 32LL);
    do
      ++v4;
    while ( a2[v4] );
    v6 = 2 * v4 + 2;
    if ( *(_QWORD *)(v5 + 440) )
    {
      WpFreeMemory();
      *(_QWORD *)(v5 + 440) = 0;
    }
    v7 = (void *)WpAllocMemory(v6);
    v8 = v7;
    if ( v7 )
    {
      memcpy_0(v7, a2, v6);
      *(_QWORD *)(v5 + 440) = v8;
      *(_DWORD *)(v5 + 432) = 1;
    }
    else
    {
      return -2147024882;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000cdc4  push    rbx
0x18000cdc6  push    rbp
0x18000cdc7  push    rsi
0x18000cdc8  push    rdi
0x18000cdc9  push    r14
0x18000cdcb  push    r15
0x18000cdcd  sub     rsp, 28h
0x18000cdd1  xor     r15d, r15d
0x18000cdd4  mov     rdi, rdx
0x18000cdd7  mov     ebx, r15d
0x18000cdda  test    rdx, rdx
0x18000cddd  jz      short loc_18000CE54
0x18000cddf  mov     rax, [rcx+28h]
0x18000cde3  mov     rcx, [rax+228h]
0x18000cdea  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cdee  mov     rsi, [rcx+20h]
0x18000cdf2  inc     rax
0x18000cdf5  cmp     [rdx+rax*2], r15w
0x18000cdfa  jnz     short loc_18000CDF2
0x18000cdfc  mov     rcx, [rsi+1B8h]
0x18000ce03  lea     r14, ds:2[rax*2]
0x18000ce0b  test    rcx, rcx
0x18000ce0e  jz      short loc_18000CE1D
0x18000ce10  call    cs:__imp_WpFreeMemory
0x18000ce16  mov     [rsi+1B8h], r15
0x18000ce1d  mov     rcx, r14
0x18000ce20  call    cs:__imp_WpAllocMemory
0x18000ce26  mov     rbp, rax
0x18000ce29  test    rax, rax
0x18000ce2c  jnz     short loc_18000CE35
0x18000ce2e  mov     ebx, 8007000Eh
0x18000ce33  jmp     short loc_18000CE54
0x18000ce35  mov     r8, r14; Size
0x18000ce38  mov     rdx, rdi; Src
0x18000ce3b  mov     rcx, rbp; void *
0x18000ce3e  call    memcpy_0
0x18000ce43  mov     [rsi+1B8h], rbp
0x18000ce4a  mov     dword ptr [rsi+1B0h], 1
0x18000ce54  movsxd  rax, ebx
0x18000ce57  add     rsp, 28h
0x18000ce5b  pop     r15
0x18000ce5d  pop     r14
0x18000ce5f  pop     rdi
0x18000ce60  pop     rsi
0x18000ce61  pop     rbp
0x18000ce62  pop     rbx
0x18000ce63  retn
```
