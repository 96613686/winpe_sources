# WinNatChecksumDatagram

- ea: `0x14001bb90`
- end: `0x14001bd06`
- name: `WinNatChecksumDatagram`
- size: `374`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006c80`
- `0x140014e38`
- `0x14001cef8`
- `0x14001e8ec`

## callees

- `0x14000caa0`
- `0x14001bb90`
- `0x14001ee10`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001bc6e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001bc6e`

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
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
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
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
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
        MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
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
0x14001bb90  push    rbx
0x14001bb92  push    rbp
0x14001bb93  push    rsi
0x14001bb94  push    rdi
0x14001bb95  push    r12
0x14001bb97  push    r13
0x14001bb99  push    r14
0x14001bb9b  push    r15
0x14001bb9d  sub     rsp, 38h
0x14001bba1  mov     r15, r9
0x14001bba4  mov     rbx, r8
0x14001bba7  mov     ebp, edx
0x14001bba9  mov     r14, rcx
0x14001bbac  test    r8, r8
0x14001bbaf  jz      short loc_14001BC0A
0x14001bbb1  mov     esi, [rsp+78h+arg_28]
0x14001bbb8  cmp     esi, 1
0x14001bbbb  jz      short loc_14001BC0A
0x14001bbbd  test    r9, r9
0x14001bbc0  jnz     short loc_14001BBC7
0x14001bbc2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001bbc7  mov     r8d, [rsp+78h+arg_20]
0x14001bbcf  mov     edi, ebp
0x14001bbd1  mov     rdx, rbx
0x14001bbd4  xor     ecx, ecx
0x14001bbd6  bswap   edi
0x14001bbd8  call    tcpxsum
0x14001bbdd  mov     r8d, [rsp+78h+arg_20]
0x14001bbe5  mov     rdx, r15
0x14001bbe8  xor     ecx, ecx
0x14001bbea  movzx   ebx, ax
0x14001bbed  call    tcpxsum
0x14001bbf2  movzx   ecx, ax
0x14001bbf5  mov     eax, edi
0x14001bbf7  shr     eax, 10h
0x14001bbfa  add     ecx, eax
0x14001bbfc  shl     esi, 8
0x14001bbff  movzx   eax, di
0x14001bc02  add     eax, ebx
0x14001bc04  add     eax, ecx
0x14001bc06  add     esi, eax
0x14001bc08  jmp     short loc_14001BC0C
0x14001bc0a  xor     esi, esi
0x14001bc0c  test    r14, r14
0x14001bc0f  jnz     short loc_14001BC28
0x14001bc11  movzx   eax, si
0x14001bc14  mov     edx, esi
0x14001bc16  shr     edx, 10h
0x14001bc19  add     edx, eax
0x14001bc1b  mov     eax, edx
0x14001bc1d  shr     eax, 10h
0x14001bc20  add     ax, dx
0x14001bc23  jmp     loc_14001BCF4
0x14001bc28  mov     rbx, [r14+8]
0x14001bc2c  xor     r13d, r13d
0x14001bc2f  mov     r15d, [r14+10h]
0x14001bc33  cmp     ebp, [r14+18h]
0x14001bc37  jbe     short loc_14001BC3E
0x14001bc39  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001bc3e  test    ebp, ebp
0x14001bc40  jz      loc_14001BCD6
0x14001bc46  test    byte ptr [rbx+0Ah], 5
0x14001bc4a  jz      short loc_14001BC52
0x14001bc4c  mov     r12, [rbx+18h]
0x14001bc50  jmp     short loc_14001BC7D
0x14001bc52  xor     r9d, r9d; RequestedAddress
0x14001bc55  mov     [rsp+78h+Priority], 40000000h; Priority
0x14001bc5d  xor     edx, edx; AccessMode
0x14001bc5f  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14001bc67  mov     rcx, rbx; MemoryDescriptorList
0x14001bc6a  lea     r8d, [r9+1]; CacheType
0x14001bc6e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001bc75  nop     dword ptr [rax+rax+00h]
0x14001bc7a  mov     r12, rax
0x14001bc7d  test    r12, r12
0x14001bc80  jz      short loc_14001BCD2
0x14001bc82  mov     edi, [rbx+28h]
0x14001bc85  cmp     edi, r15d
0x14001bc88  jnb     short loc_14001BC8F
0x14001bc8a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001bc8f  sub     edi, r15d
0x14001bc92  mov     edx, r15d
0x14001bc95  cmp     edi, ebp
0x14001bc97  mov     r14d, ebp
0x14001bc9a  cmovbe  r14d, edi
0x14001bc9e  add     rdx, r12
0x14001bca1  mov     r8d, r14d
0x14001bca4  xor     ecx, ecx
0x14001bca6  call    tcpxsum
0x14001bcab  movzx   edx, ax
0x14001bcae  test    r13b, 1
0x14001bcb2  jz      short loc_14001BCBF
0x14001bcb4  movzx   ecx, dl
0x14001bcb7  shl     ecx, 8
0x14001bcba  shr     edx, 8
0x14001bcbd  add     edx, ecx
0x14001bcbf  mov     rbx, [rbx]
0x14001bcc2  add     r13d, r14d
0x14001bcc5  sub     ebp, r14d
0x14001bcc8  xor     r15d, r15d
0x14001bccb  add     esi, edx
0x14001bccd  jmp     loc_14001BC3E
0x14001bcd2  xor     eax, eax
0x14001bcd4  jmp     short loc_14001BCF4
0x14001bcd6  movzx   eax, si
0x14001bcd9  mov     ecx, esi
0x14001bcdb  shr     ecx, 10h
0x14001bcde  add     ecx, eax
0x14001bce0  mov     eax, ecx
0x14001bce2  shr     eax, 10h
0x14001bce5  add     eax, ecx
0x14001bce7  cmp     eax, 0FFFFh
0x14001bcec  jz      short loc_14001BCF4
0x14001bcee  not     ax
0x14001bcf1  movzx   eax, ax
0x14001bcf4  add     rsp, 38h
0x14001bcf8  pop     r15
0x14001bcfa  pop     r14
0x14001bcfc  pop     r13
0x14001bcfe  pop     r12
0x14001bd00  pop     rdi
0x14001bd01  pop     rsi
0x14001bd02  pop     rbp
0x14001bd03  pop     rbx
0x14001bd04  retn
```
