# RtmCreateNextHopEnum

- ea: `0x180005c00`
- end: `0x180005db8`
- name: `RtmCreateNextHopEnum`
- size: `440`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_ENUM_FLAGS EnumFlags, PRTM_NET_ADDRESS NetAddress, PRTM_ENUM_HANDLE RtmEnumHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ebc`

## callees

- `0x180005c00`
- `0x18001f952`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180005c76`
- `KERNEL32!HeapAlloc` at `0x180005c76`
- `KERNEL32!GetProcessHeap` at `0x180005c64`
- `KERNEL32!GetProcessHeap` at `0x180005d74`
- `KERNEL32!GetProcessHeap` at `0x180005c64`
- `KERNEL32!GetProcessHeap` at `0x180005d74`
- `KERNEL32!HeapFree` at `0x180005d84`
- `KERNEL32!HeapFree` at `0x180005d84`
- `KERNEL32!InitializeCriticalSection` at `0x180005d24`
- `KERNEL32!InitializeCriticalSection` at `0x180005d24`
- `KERNEL32!DeleteCriticalSection` at `0x180005d6e`
- `KERNEL32!DeleteCriticalSection` at `0x180005d6e`

## pseudocode

```c
DWORD __stdcall RtmCreateNextHopEnum(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_ENUM_FLAGS EnumFlags,
        PRTM_NET_ADDRESS NetAddress,
        PRTM_ENUM_HANDLE RtmEnumHandle)
{
  unsigned __int64 v7; // r15
  RTM_ENUM_FLAGS v8; // esi
  HANDLE ProcessHeap; // rax
  _BYTE *v11; // rax
  int v12; // edx
  unsigned __int64 v13; // rbx
  unsigned int v14; // r12d
  __int64 v15; // rsi

  v7 = (unsigned __int64)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32
    || *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
  {
    return 6;
  }
  v8 = EnumFlags & 2;
  if ( (EnumFlags & 1) != 0 && (EnumFlags & 2) != 0 || (EnumFlags & 3) != 0 && !NetAddress )
    return 87;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 0x68u);
  v13 = (unsigned __int64)v11;
  if ( !v11 )
    return 8;
  v11[4] = 9;
  *((_DWORD *)v11 + 2) = EnumFlags;
  if ( v8 )
  {
    v14 = *(_DWORD *)(*(_QWORD *)(v7 + 16) + 8LL);
    *((_WORD *)v11 + 6) = NetAddress->AddressFamily;
    *((_WORD *)v11 + 7) = 8 * v14;
    v15 = 0;
    if ( (NetAddress->NumBits & 0xFFF8) != 0 )
    {
      do
      {
        v11[v15 + 16] = NetAddress->AddrBits[v15];
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < NetAddress->NumBits >> 3 );
    }
    if ( (unsigned int)v15 < v14 )
    {
      LOBYTE(v12) = -1;
      memset_0(&v11[(unsigned int)v15 + 16], v12, v14 - (unsigned int)v15);
      *(_BYTE *)((unsigned int)v15 + v13 + 16) >>= NetAddress->NumBits & 7;
      *(_BYTE *)((unsigned int)v15 + v13 + 16) |= NetAddress->AddrBits[(unsigned int)v15];
    }
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)(v13 + 32));
  if ( NetAddress )
  {
    *(_OWORD *)(v13 + 76) = *(_OWORD *)&NetAddress->AddressFamily;
    *(_DWORD *)(v13 + 92) = *(_DWORD *)&NetAddress->AddrBits[12];
  }
  *(_DWORD *)(v13 + 96) = -1;
  _InterlockedIncrement((volatile signed __int32 *)v7);
  *RtmEnumHandle = (HANDLE)(v13 ^ 0x7754DF32);
  return 0;
}

```

## disassembly

```asm
0x180005c00  mov     [rsp+arg_8], rbx
0x180005c05  mov     [rsp+arg_10], rsi
0x180005c0a  mov     [rsp+arg_18], r9
0x180005c0f  push    rdi
0x180005c10  push    r12
0x180005c12  push    r13
0x180005c14  push    r14
0x180005c16  push    r15
0x180005c18  sub     rsp, 30h
0x180005c1c  mov     r13, r9
0x180005c1f  mov     rdi, r8
0x180005c22  mov     r14d, edx
0x180005c25  mov     r15, rcx
0x180005c28  xor     r15, 7754DF32h
0x180005c2f  jz      loc_180005D9B
0x180005c35  cmp     dword ptr [r15+30h], 1
0x180005c3a  jz      loc_180005D9B
0x180005c40  mov     esi, edx
0x180005c42  and     esi, 2
0x180005c45  test    r14b, 1
0x180005c49  jz      short loc_180005C4F
0x180005c4b  test    esi, esi
0x180005c4d  jnz     short loc_180005C5A
0x180005c4f  test    r14b, 3
0x180005c53  jz      short loc_180005C64
0x180005c55  test    rdi, rdi
0x180005c58  jnz     short loc_180005C64
0x180005c5a  mov     eax, 57h ; 'W'
0x180005c5f  jmp     loc_180005DA0
0x180005c64  call    cs:__imp_GetProcessHeap
0x180005c6a  mov     rcx, rax; hHeap
0x180005c6d  mov     edx, 8; dwFlags
0x180005c72  lea     r8d, [rdx+60h]; dwBytes
0x180005c76  call    cs:__imp_HeapAlloc
0x180005c7c  mov     rbx, rax
0x180005c7f  mov     [rsp+58h+lpMem], rax
0x180005c84  test    rax, rax
0x180005c87  jnz     short loc_180005C93
0x180005c89  mov     eax, 8
0x180005c8e  jmp     loc_180005DA0
0x180005c93  mov     byte ptr [rax+4], 9
0x180005c97  mov     [rax+8], r14d
0x180005c9b  test    esi, esi
0x180005c9d  jz      short loc_180005D18
0x180005c9f  mov     rax, [r15+10h]
0x180005ca3  mov     r12d, [rax+8]
0x180005ca7  movzx   eax, word ptr [rdi]
0x180005caa  mov     [rbx+0Ch], ax
0x180005cae  movzx   eax, r12w
0x180005cb2  shl     ax, 3
0x180005cb6  mov     [rbx+0Eh], ax
0x180005cba  xor     esi, esi
0x180005cbc  movzx   eax, word ptr [rdi+2]
0x180005cc0  test    eax, 0FFFFFFF8h
0x180005cc5  jbe     short loc_180005CDC
0x180005cc7  mov     al, [rsi+rdi+4]
0x180005ccb  mov     [rsi+rbx+10h], al
0x180005ccf  inc     esi
0x180005cd1  movzx   eax, word ptr [rdi+2]
0x180005cd5  shr     eax, 3
0x180005cd8  cmp     esi, eax
0x180005cda  jb      short loc_180005CC7
0x180005cdc  mov     r14d, esi
0x180005cdf  cmp     esi, r12d
0x180005ce2  jnb     short loc_180005D18
0x180005ce4  mov     r8d, r12d
0x180005ce7  sub     r8d, esi; Size
0x180005cea  lea     rcx, [rbx+10h]
0x180005cee  add     rcx, r14; void *
0x180005cf1  mov     dl, 0FFh; Val
0x180005cf3  call    memset_0
0x180005cf8  cmp     esi, r12d
0x180005cfb  jnb     short loc_180005D18
0x180005cfd  movzx   ecx, word ptr [rdi+2]
0x180005d01  and     ecx, 7
0x180005d04  shr     byte ptr [r14+rbx+10h], cl
0x180005d09  mov     al, [r14+rbx+10h]
0x180005d0e  or      al, [r14+rdi+4]
0x180005d13  mov     [r14+rbx+10h], al
0x180005d18  mov     [rsp+58h+var_38], 0
0x180005d20  lea     rcx, [rbx+20h]; lpCriticalSection
0x180005d24  call    cs:__imp_InitializeCriticalSection
0x180005d2a  mov     [rsp+58h+var_38], 1
0x180005d32  test    rdi, rdi
0x180005d35  jz      short loc_180005D44
0x180005d37  movups  xmm0, xmmword ptr [rdi]
0x180005d3a  movups  xmmword ptr [rbx+4Ch], xmm0
0x180005d3e  mov     eax, [rdi+10h]
0x180005d41  mov     [rbx+5Ch], eax
0x180005d44  mov     dword ptr [rbx+60h], 0FFFFFFFFh
0x180005d4b  lock inc dword ptr [r15]
0x180005d4f  xor     rbx, 7754DF32h
0x180005d56  mov     [r13+0], rbx
0x180005d5a  xor     eax, eax
0x180005d5c  jmp     short loc_180005DA0
0x180005d5e  cmp     [rsp+58h+var_38], 0
0x180005d63  jz      short loc_180005D74
0x180005d65  mov     rcx, [rsp+58h+lpMem]
0x180005d6a  add     rcx, 20h ; ' '; lpCriticalSection
0x180005d6e  call    cs:__imp_DeleteCriticalSection
0x180005d74  call    cs:__imp_GetProcessHeap
0x180005d7a  mov     rcx, rax; hHeap
0x180005d7d  mov     r8, [rsp+58h+lpMem]; lpMem
0x180005d82  xor     edx, edx; dwFlags
0x180005d84  call    cs:__imp_HeapFree
0x180005d8a  mov     rax, [rsp+58h+arg_18]
0x180005d8f  mov     qword ptr [rax], 0
0x180005d96  jmp     loc_180005C89
0x180005d9b  mov     eax, 6
0x180005da0  mov     rbx, [rsp+58h+arg_8]
0x180005da5  mov     rsi, [rsp+58h+arg_10]
0x180005daa  add     rsp, 30h
0x180005dae  pop     r15
0x180005db0  pop     r14
0x180005db2  pop     r13
0x180005db4  pop     r12
0x180005db6  pop     rdi
0x180005db7  retn
```
