# VaultDeserialize(uchar * &,ulong &,ushort * &)

- ea: `0x18001a924`
- end: `0x18001aa1f`
- name: `?VaultDeserialize@@YAKAEAPEAEAEAKAEAPEAG@Z`
- size: `251`
- prototype: `unsigned int __fastcall(unsigned __int8 **, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a760`
- `0x18002a9e0`

## callees

- `0x18001a924`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a9ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a9f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a9ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a9f9`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001a98a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001a98a`

## pseudocode

```c
__int64 __fastcall VaultDeserialize(unsigned __int8 **a1, unsigned int *a2, unsigned __int16 **a3)
{
  bool v4; // cf
  SIZE_T v7; // rbx
  unsigned int i; // esi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v11; // rax
  __int16 Source2; // [rsp+68h] [rbp+10h] BYREF

  v4 = *a2 < 4;
  Source2 = 0;
  if ( v4 )
    return 122;
  v7 = *(unsigned int *)*a1;
  *a1 += 4;
  *a2 -= 4;
  if ( (unsigned int)v7 < 2 )
  {
    *a3 = 0;
LABEL_15:
    v11 = (unsigned __int16 *)LocalAlloc(0x40u, 2u);
    *a3 = v11;
    if ( !v11 )
      return 14;
    *v11 = 0;
    return 0;
  }
  if ( (unsigned int)v7 > *a2 )
    return 122;
  if ( (v7 & 1) == 0 )
  {
    for ( i = 0; i < (unsigned int)v7; i += 2 )
    {
      if ( RtlCompareMemory(&(*a1)[i], &Source2, 2u) == 2 )
      {
        if ( i != v7 - 2 )
          return 1358;
        v9 = (unsigned __int16 *)LocalAlloc(0x40u, v7);
        *a3 = v9;
        if ( !v9 )
          return 14;
        memcpy_0(v9, *a1, v7);
        *a1 += v7;
        *a2 -= v7;
        if ( !*a3 )
          goto LABEL_15;
        return 0;
      }
    }
  }
  return 1358;
}

```

## disassembly

```asm
0x18001a924  push    rbx
0x18001a926  push    rsi
0x18001a927  push    rdi
0x18001a928  push    r12
0x18001a92a  push    r14
0x18001a92c  push    r15
0x18001a92e  sub     rsp, 28h
0x18001a932  xor     eax, eax
0x18001a934  mov     r15, r8
0x18001a937  cmp     dword ptr [rdx], 4
0x18001a93a  mov     rdi, rdx
0x18001a93d  mov     r14, rcx
0x18001a940  mov     [rsp+58h+Source2], ax
0x18001a945  jb      loc_18001AA18
0x18001a94b  mov     rax, [rcx]
0x18001a94e  mov     ebx, [rax]
0x18001a950  add     rax, 4
0x18001a954  mov     [rcx], rax
0x18001a957  add     dword ptr [rdx], 0FFFFFFFCh
0x18001a95a  cmp     ebx, 2
0x18001a95d  jb      loc_18001A9EA
0x18001a963  cmp     ebx, [rdx]
0x18001a965  ja      loc_18001AA18
0x18001a96b  test    bl, 1
0x18001a96e  jnz     short loc_18001A9E3
0x18001a970  xor     esi, esi
0x18001a972  cmp     esi, ebx
0x18001a974  jnb     short loc_18001A9E3
0x18001a976  mov     rcx, [r14]
0x18001a979  lea     rdx, [rsp+58h+Source2]; Source2
0x18001a97e  mov     r12d, esi
0x18001a981  mov     r8d, 2; Length
0x18001a987  add     rcx, r12; Source1
0x18001a98a  call    cs:__imp_RtlCompareMemory
0x18001a990  cmp     rax, 2
0x18001a994  jz      short loc_18001A99B
0x18001a996  add     esi, 2
0x18001a999  jmp     short loc_18001A972
0x18001a99b  lea     rax, [rbx-2]
0x18001a99f  cmp     r12, rax
0x18001a9a2  jnz     short loc_18001A9E3
0x18001a9a4  mov     rdx, rbx; uBytes
0x18001a9a7  mov     ecx, 40h ; '@'; uFlags
0x18001a9ac  call    cs:__imp_LocalAlloc
0x18001a9b2  mov     [r15], rax
0x18001a9b5  test    rax, rax
0x18001a9b8  jz      short loc_18001AA11
0x18001a9ba  mov     rdx, [r14]; Src
0x18001a9bd  mov     r8, rbx; Size
0x18001a9c0  mov     rcx, rax; void *
0x18001a9c3  call    memcpy_0
0x18001a9c8  add     [r14], rbx
0x18001a9cb  sub     [rdi], ebx
0x18001a9cd  cmp     qword ptr [r15], 0
0x18001a9d1  jz      short loc_18001A9F1
0x18001a9d3  xor     eax, eax
0x18001a9d5  add     rsp, 28h
0x18001a9d9  pop     r15
0x18001a9db  pop     r14
0x18001a9dd  pop     r12
0x18001a9df  pop     rdi
0x18001a9e0  pop     rsi
0x18001a9e1  pop     rbx
0x18001a9e2  retn
0x18001a9e3  mov     eax, 54Eh
0x18001a9e8  jmp     short loc_18001A9D5
0x18001a9ea  mov     qword ptr [r8], 0
0x18001a9f1  mov     edx, 2; uBytes
0x18001a9f6  lea     ecx, [rdx+3Eh]; uFlags
0x18001a9f9  call    cs:__imp_LocalAlloc
0x18001a9ff  mov     [r15], rax
0x18001aa02  mov     rcx, rax
0x18001aa05  test    rax, rax
0x18001aa08  jz      short loc_18001AA11
0x18001aa0a  xor     eax, eax
0x18001aa0c  mov     [rcx], ax
0x18001aa0f  jmp     short loc_18001A9D3
0x18001aa11  mov     eax, 0Eh
0x18001aa16  jmp     short loc_18001A9D5
0x18001aa18  mov     eax, 7Ah ; 'z'
0x18001aa1d  jmp     short loc_18001A9D5
```
