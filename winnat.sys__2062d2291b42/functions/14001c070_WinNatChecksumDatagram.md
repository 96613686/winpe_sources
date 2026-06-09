# WinNatChecksumDatagram

- ea: `0x14001c070`
- end: `0x14001c1e6`
- name: `WinNatChecksumDatagram`
- size: `374`
- prototype: `__int16 __fastcall(__int64, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006c80`
- `0x1400157b4`
- `0x14001d3d8`
- `0x14001ee24`

## callees

- `0x14000caa0`
- `0x14001c070`
- `0x14001f350`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001c14e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001c14e`

## pseudocode

```c
__int16 __fastcall WinNatChecksumDatagram(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5, int a6)
{
  unsigned int v8; // ebp
  __int64 v9; // r14
  unsigned __int32 v10; // edi
  int v11; // ebx
  unsigned int v12; // esi
  unsigned int v13; // eax
  struct _MDL *v14; // rbx
  char v15; // r13
  unsigned int v16; // r15d
  char *MappedSystemVa; // r12
  unsigned int ByteCount; // edi
  unsigned int v19; // edi
  unsigned int v20; // r14d

  v8 = a2;
  v9 = a1;
  if ( !a3 || a6 == 1 )
  {
    v12 = 0;
  }
  else
  {
    if ( !a4 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
    v10 = _byteswap_ulong(v8);
    v11 = (unsigned __int16)tcpxsum(0, a3, a5);
    a1 = HIWORD(v10) + (unsigned __int16)tcpxsum(0, a4, a5);
    v12 = a1 + v11 + (unsigned __int16)v10 + (a6 << 8);
  }
  if ( v9 )
  {
    v14 = *(struct _MDL **)(v9 + 8);
    v15 = 0;
    v16 = *(_DWORD *)(v9 + 16);
    if ( v8 > *(_DWORD *)(v9 + 24) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
    while ( v8 )
    {
      if ( (v14->MdlFlags & 5) != 0 )
        MappedSystemVa = (char *)v14->MappedSystemVa;
      else
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000000u);
      if ( !MappedSystemVa )
      {
        LOWORD(v13) = 0;
        return v13;
      }
      ByteCount = v14->ByteCount;
      if ( ByteCount < v16 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
      v19 = ByteCount - v16;
      v20 = v8;
      if ( v19 <= v8 )
        v20 = v19;
      a2 = (unsigned __int16)tcpxsum(0, &MappedSystemVa[v16], v20);
      if ( (v15 & 1) != 0 )
      {
        a1 = (unsigned __int8)a2 << 8;
        a2 = (unsigned int)a1 + ((unsigned int)a2 >> 8);
      }
      v14 = v14->Next;
      v15 += v20;
      v8 -= v20;
      v16 = 0;
      v12 += a2;
    }
    v13 = (unsigned __int16)v12 + HIWORD(v12) + ((unsigned int)((unsigned __int16)v12 + HIWORD(v12)) >> 16);
    if ( v13 != 0xFFFF )
      LOWORD(v13) = ~(_WORD)v13;
  }
  else
  {
    LOWORD(v13) = v12 + HIWORD(v12) + ((unsigned int)((unsigned __int16)v12 + HIWORD(v12)) >> 16);
  }
  return v13;
}

```

## disassembly

```asm
0x14001c070  push    rbx
0x14001c072  push    rbp
0x14001c073  push    rsi
0x14001c074  push    rdi
0x14001c075  push    r12
0x14001c077  push    r13
0x14001c079  push    r14
0x14001c07b  push    r15
0x14001c07d  sub     rsp, 38h
0x14001c081  mov     r15, r9
0x14001c084  mov     rbx, r8
0x14001c087  mov     ebp, edx
0x14001c089  mov     r14, rcx
0x14001c08c  test    r8, r8
0x14001c08f  jz      short loc_14001C0EA
0x14001c091  mov     esi, [rsp+78h+arg_28]
0x14001c098  cmp     esi, 1
0x14001c09b  jz      short loc_14001C0EA
0x14001c09d  test    r9, r9
0x14001c0a0  jnz     short loc_14001C0A7
0x14001c0a2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c0a7  mov     r8d, [rsp+78h+arg_20]
0x14001c0af  mov     edi, ebp
0x14001c0b1  mov     rdx, rbx
0x14001c0b4  xor     ecx, ecx
0x14001c0b6  bswap   edi
0x14001c0b8  call    tcpxsum
0x14001c0bd  mov     r8d, [rsp+78h+arg_20]
0x14001c0c5  mov     rdx, r15
0x14001c0c8  xor     ecx, ecx
0x14001c0ca  movzx   ebx, ax
0x14001c0cd  call    tcpxsum
0x14001c0d2  movzx   ecx, ax
0x14001c0d5  mov     eax, edi
0x14001c0d7  shr     eax, 10h
0x14001c0da  add     ecx, eax
0x14001c0dc  shl     esi, 8
0x14001c0df  movzx   eax, di
0x14001c0e2  add     eax, ebx
0x14001c0e4  add     eax, ecx
0x14001c0e6  add     esi, eax
0x14001c0e8  jmp     short loc_14001C0EC
0x14001c0ea  xor     esi, esi
0x14001c0ec  test    r14, r14
0x14001c0ef  jnz     short loc_14001C108
0x14001c0f1  movzx   eax, si
0x14001c0f4  mov     edx, esi
0x14001c0f6  shr     edx, 10h
0x14001c0f9  add     edx, eax
0x14001c0fb  mov     eax, edx
0x14001c0fd  shr     eax, 10h
0x14001c100  add     ax, dx
0x14001c103  jmp     loc_14001C1D4
0x14001c108  mov     rbx, [r14+8]
0x14001c10c  xor     r13d, r13d
0x14001c10f  mov     r15d, [r14+10h]
0x14001c113  cmp     ebp, [r14+18h]
0x14001c117  jbe     short loc_14001C11E
0x14001c119  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c11e  test    ebp, ebp
0x14001c120  jz      loc_14001C1B6
0x14001c126  test    byte ptr [rbx+0Ah], 5
0x14001c12a  jz      short loc_14001C132
0x14001c12c  mov     r12, [rbx+18h]
0x14001c130  jmp     short loc_14001C15D
0x14001c132  xor     r9d, r9d; RequestedAddress
0x14001c135  mov     [rsp+78h+Priority], 40000000h; Priority
0x14001c13d  xor     edx, edx; AccessMode
0x14001c13f  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14001c147  mov     rcx, rbx; MemoryDescriptorList
0x14001c14a  lea     r8d, [r9+1]; CacheType
0x14001c14e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001c155  nop     dword ptr [rax+rax+00h]
0x14001c15a  mov     r12, rax
0x14001c15d  test    r12, r12
0x14001c160  jz      short loc_14001C1B2
0x14001c162  mov     edi, [rbx+28h]
0x14001c165  cmp     edi, r15d
0x14001c168  jnb     short loc_14001C16F
0x14001c16a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c16f  sub     edi, r15d
0x14001c172  mov     edx, r15d
0x14001c175  cmp     edi, ebp
0x14001c177  mov     r14d, ebp
0x14001c17a  cmovbe  r14d, edi
0x14001c17e  add     rdx, r12
0x14001c181  mov     r8d, r14d
0x14001c184  xor     ecx, ecx
0x14001c186  call    tcpxsum
0x14001c18b  movzx   edx, ax
0x14001c18e  test    r13b, 1
0x14001c192  jz      short loc_14001C19F
0x14001c194  movzx   ecx, dl
0x14001c197  shl     ecx, 8
0x14001c19a  shr     edx, 8
0x14001c19d  add     edx, ecx
0x14001c19f  mov     rbx, [rbx]
0x14001c1a2  add     r13d, r14d
0x14001c1a5  sub     ebp, r14d
0x14001c1a8  xor     r15d, r15d
0x14001c1ab  add     esi, edx
0x14001c1ad  jmp     loc_14001C11E
0x14001c1b2  xor     eax, eax
0x14001c1b4  jmp     short loc_14001C1D4
0x14001c1b6  movzx   eax, si
0x14001c1b9  mov     ecx, esi
0x14001c1bb  shr     ecx, 10h
0x14001c1be  add     ecx, eax
0x14001c1c0  mov     eax, ecx
0x14001c1c2  shr     eax, 10h
0x14001c1c5  add     eax, ecx
0x14001c1c7  cmp     eax, 0FFFFh
0x14001c1cc  jz      short loc_14001C1D4
0x14001c1ce  not     ax
0x14001c1d1  movzx   eax, ax
0x14001c1d4  add     rsp, 38h
0x14001c1d8  pop     r15
0x14001c1da  pop     r14
0x14001c1dc  pop     r13
0x14001c1de  pop     r12
0x14001c1e0  pop     rdi
0x14001c1e1  pop     rsi
0x14001c1e2  pop     rbp
0x14001c1e3  pop     rbx
0x14001c1e4  retn
```
