# SmbCompressionLegacyDecompress

- ea: `0x140020c80`
- end: `0x140020d3b`
- name: `SmbCompressionLegacyDecompress`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140020484`
- `0x1400204a8`
- `0x140020c80`

## import_xrefs

- `ntoskrnl!RtlDecompressBufferEx2` at `0x140020d17`
- `ntoskrnl!RtlDecompressBufferEx2` at `0x140020d17`

## pseudocode

```c
__int64 __fastcall SmbCompressionLegacyDecompress(int a1, __int64 a2, int a3, __int64 a4, unsigned int a5, __int64 a6)
{
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  unsigned __int16 v13; // bx
  __int64 v14; // rdi
  __int64 v15; // rcx

  if ( !a1 )
    return (unsigned int)-1073741637;
  v10 = a1 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        if ( v12 != 2 )
          return (unsigned int)-1073741637;
        v13 = 6;
      }
      else
      {
        v13 = 4;
      }
    }
    else
    {
      v13 = 3;
    }
  }
  else
  {
    v13 = 2;
  }
  v14 = PplAllocateFromLookasideList();
  if ( v14 )
  {
    v9 = RtlDecompressBufferEx2(v13, a4, a5, a2, a3, 0, a6, v14);
    PplFreeToLookasideList(v15, v14);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v9;
}

```

## disassembly

```asm
0x140020c80  push    rbx
0x140020c82  push    rbp
0x140020c83  push    rsi
0x140020c84  push    rdi
0x140020c85  push    r14
0x140020c87  sub     rsp, 40h
0x140020c8b  mov     rsi, r9
0x140020c8e  mov     ebp, r8d
0x140020c91  mov     r14, rdx
0x140020c94  test    ecx, ecx
0x140020c96  jnz     short loc_140020CA2
0x140020c98  mov     ebx, 0C00000BBh
0x140020c9d  jmp     loc_140020D2D
0x140020ca2  sub     ecx, 1
0x140020ca5  jz      short loc_140020CCF
0x140020ca7  sub     ecx, 1
0x140020caa  jz      short loc_140020CC8
0x140020cac  sub     ecx, 1
0x140020caf  jz      short loc_140020CC1
0x140020cb1  mov     ebx, 2
0x140020cb6  cmp     ecx, ebx
0x140020cb8  jnz     short loc_140020C98
0x140020cba  mov     ebx, 6
0x140020cbf  jmp     short loc_140020CD4
0x140020cc1  mov     ebx, 4
0x140020cc6  jmp     short loc_140020CD4
0x140020cc8  mov     ebx, 3
0x140020ccd  jmp     short loc_140020CD4
0x140020ccf  mov     ebx, 2
0x140020cd4  call    PplAllocateFromLookasideList
0x140020cd9  mov     rdi, rax
0x140020cdc  test    rax, rax
0x140020cdf  jnz     short loc_140020CE8
0x140020ce1  mov     ebx, 0C000009Ah
0x140020ce6  jmp     short loc_140020D2D
0x140020ce8  mov     rax, [rsp+68h+arg_28]
0x140020cf0  mov     r9, r14
0x140020cf3  mov     r8d, [rsp+68h+arg_20]
0x140020cfb  mov     rdx, rsi
0x140020cfe  mov     [rsp+68h+var_30], rdi
0x140020d03  movzx   ecx, bx
0x140020d06  mov     [rsp+68h+var_38], rax
0x140020d0b  mov     [rsp+68h+var_40], 0
0x140020d13  mov     [rsp+68h+var_48], ebp
0x140020d17  call    cs:__imp_RtlDecompressBufferEx2
0x140020d1e  nop     dword ptr [rax+rax+00h]
0x140020d23  mov     ebx, eax
0x140020d25  mov     rdx, rdi
0x140020d28  call    PplFreeToLookasideList
0x140020d2d  mov     eax, ebx
0x140020d2f  add     rsp, 40h
0x140020d33  pop     r14
0x140020d35  pop     rdi
0x140020d36  pop     rsi
0x140020d37  pop     rbp
0x140020d38  pop     rbx
0x140020d39  retn
```
