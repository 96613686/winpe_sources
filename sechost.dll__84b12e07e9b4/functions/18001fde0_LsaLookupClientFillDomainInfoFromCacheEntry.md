# LsaLookupClientFillDomainInfoFromCacheEntry

- ea: `0x18001fde0`
- end: `0x18001fe98`
- name: `LsaLookupClientFillDomainInfoFromCacheEntry`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000de94`
- `0x18001ffd4`

## callees

- `0x180013ea8`
- `0x18001fdb4`
- `0x18001fde0`
- `0x18004f902`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18001fe34`
- `ntdll!RtlCopySid` at `0x18001fe34`
- `ntdll!RtlValidSid` at `0x18001fdf8`
- `ntdll!RtlValidSid` at `0x18001fdf8`
- `ntdll!RtlLengthSid` at `0x18001fe0d`
- `ntdll!RtlLengthSid` at `0x18001fe0d`

## pseudocode

```c
__int64 __fastcall LsaLookupClientFillDomainInfoFromCacheEntry(__int64 a1, unsigned __int16 *a2)
{
  _QWORD *v3; // r14
  NTSTATUS v5; // ebx
  ULONG v6; // ebx
  void *Memory; // rax
  __int64 v8; // rcx
  void *v9; // rax

  v3 = a2 + 8;
  if ( RtlValidSid(*(PSID *)(a1 + 8)) )
  {
    v6 = RtlLengthSid(*(PSID *)(a1 + 8));
    Memory = (void *)LsaLookupClientAllocateMemory(v6);
    *v3 = Memory;
    if ( Memory
      && (v5 = RtlCopySid(v6, Memory, *(PSID *)(a1 + 8)),
          *a2 = *(_WORD *)(a1 + 72),
          v8 = *(unsigned __int16 *)(a1 + 74),
          a2[1] = *(_WORD *)(a1 + 74),
          v9 = (void *)LsaLookupClientAllocateMemory(v8),
          (*((_QWORD *)a2 + 1) = v9) != 0) )
    {
      memcpy_0(v9, *(const void **)(a1 + 80), *a2);
      if ( v5 >= 0 )
        return (unsigned int)v5;
    }
    else
    {
      v5 = -1073741801;
    }
  }
  else
  {
    v5 = -1073741811;
  }
  if ( *v3 )
    LsaLookupClientFreeMemory(v3);
  if ( *((_QWORD *)a2 + 1) )
    LsaLookupClientFreeMemory(a2 + 4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001fde0  push    rbx
0x18001fde2  push    rsi
0x18001fde3  push    rdi
0x18001fde4  push    r14
0x18001fde6  sub     rsp, 28h
0x18001fdea  mov     rsi, rcx
0x18001fded  lea     r14, [rdx+10h]
0x18001fdf1  mov     rcx, [rcx+8]; Sid
0x18001fdf5  mov     rdi, rdx
0x18001fdf8  call    cs:__imp_RtlValidSid
0x18001fdfe  test    al, al
0x18001fe00  jnz     short loc_18001FE09
0x18001fe02  mov     ebx, 0C000000Dh
0x18001fe07  jmp     short loc_18001FE6F
0x18001fe09  mov     rcx, [rsi+8]; Sid
0x18001fe0d  call    cs:__imp_RtlLengthSid
0x18001fe13  mov     ecx, eax
0x18001fe15  mov     ebx, eax
0x18001fe17  call    LsaLookupClientAllocateMemory
0x18001fe1c  mov     [r14], rax
0x18001fe1f  test    rax, rax
0x18001fe22  jnz     short loc_18001FE2B
0x18001fe24  mov     ebx, 0C0000017h
0x18001fe29  jmp     short loc_18001FE6F
0x18001fe2b  mov     r8, [rsi+8]; SourceSid
0x18001fe2f  mov     rdx, rax; DestinationSid
0x18001fe32  mov     ecx, ebx; DestinationSidLength
0x18001fe34  call    cs:__imp_RtlCopySid
0x18001fe3a  mov     ebx, eax
0x18001fe3c  movzx   eax, word ptr [rsi+48h]
0x18001fe40  mov     [rdi], ax
0x18001fe43  movzx   eax, word ptr [rsi+4Ah]
0x18001fe47  mov     ecx, eax
0x18001fe49  mov     [rdi+2], ax
0x18001fe4d  call    LsaLookupClientAllocateMemory
0x18001fe52  mov     [rdi+8], rax
0x18001fe56  test    rax, rax
0x18001fe59  jz      short loc_18001FE24
0x18001fe5b  movzx   r8d, word ptr [rdi]; Size
0x18001fe5f  mov     rcx, rax; void *
0x18001fe62  mov     rdx, [rsi+50h]; Src
0x18001fe66  call    memcpy_0
0x18001fe6b  test    ebx, ebx
0x18001fe6d  jns     short loc_18001FE8C
0x18001fe6f  cmp     qword ptr [r14], 0
0x18001fe73  jz      short loc_18001FE7D
0x18001fe75  mov     rcx, r14
0x18001fe78  call    LsaLookupClientFreeMemory
0x18001fe7d  lea     rcx, [rdi+8]
0x18001fe81  cmp     qword ptr [rcx], 0
0x18001fe85  jz      short loc_18001FE8C
0x18001fe87  call    LsaLookupClientFreeMemory
0x18001fe8c  mov     eax, ebx
0x18001fe8e  add     rsp, 28h
0x18001fe92  pop     r14
0x18001fe94  pop     rdi
0x18001fe95  pop     rsi
0x18001fe96  pop     rbx
0x18001fe97  retn
```
