# AslFileMappingDelete

- ea: `0x14000f980`
- end: `0x14000fa5c`
- name: `AslFileMappingDelete`
- size: `220`
- prototype: `BOOLEAN __fastcall(_BYTE *P)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000f644`
- `0x140014574`
- `0x140015934`
- `0x140016198`
- `0x140018e34`

## callees

- `0x14000f980`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14000fa07`
- `ntdll!RtlFreeHeap` at `0x14000fa2c`
- `ntdll!RtlFreeHeap` at `0x14000fa4b`
- `ntdll!RtlFreeHeap` at `0x14000fa07`
- `ntdll!RtlFreeHeap` at `0x14000fa2c`
- `ntdll!RtlFreeHeap` at `0x14000fa4b`
- `ntdll!ZwClose` at `0x14000f9ad`
- `ntdll!ZwClose` at `0x14000f9db`
- `ntdll!ZwClose` at `0x14000f9ad`
- `ntdll!ZwClose` at `0x14000f9db`
- `ntdll!ZwUnmapViewOfSection` at `0x14000f9c6`
- `ntdll!ZwUnmapViewOfSection` at `0x14000f9c6`

## pseudocode

```c
BOOLEAN __fastcall AslFileMappingDelete(_BYTE *P)
{
  char *v1; // rbx
  void *v3; // rdx
  void *v4; // rcx
  void *v5; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v1 = P + 8;
    if ( P != (_BYTE *)-8LL )
    {
      if ( P[48] && *(_QWORD *)v1 )
        ZwClose(*(HANDLE *)v1);
      if ( v1[42] )
      {
        v3 = (void *)*((_QWORD *)v1 + 3);
        if ( v3 )
          ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v3);
      }
      if ( v1[41] )
      {
        v4 = (void *)*((_QWORD *)v1 + 1);
        if ( v4 )
          ZwClose(v4);
      }
      *(_OWORD *)v1 = 0;
      *((_OWORD *)v1 + 1) = 0;
      *((_OWORD *)v1 + 2) = 0;
    }
    v5 = (void *)*((_QWORD *)P + 8);
    if ( v5 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      *((_QWORD *)P + 8) = 0;
    }
    if ( *(_QWORD *)P )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)P);
      *(_QWORD *)P = 0;
    }
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x14000f980  test    rcx, rcx
0x14000f983  jz      locret_14000FA5B
0x14000f989  mov     [rsp+arg_0], rbx
0x14000f98e  push    rdi
0x14000f98f  sub     rsp, 20h
0x14000f993  lea     rbx, [rcx+8]
0x14000f997  mov     rdi, rcx
0x14000f99a  test    rbx, rbx
0x14000f99d  jz      short loc_14000F9EF
0x14000f99f  cmp     byte ptr [rbx+28h], 0
0x14000f9a3  jz      short loc_14000F9B3
0x14000f9a5  mov     rcx, [rbx]; Handle
0x14000f9a8  test    rcx, rcx
0x14000f9ab  jz      short loc_14000F9B3
0x14000f9ad  call    cs:__imp_ZwClose
0x14000f9b3  cmp     byte ptr [rbx+2Ah], 0
0x14000f9b7  jz      short loc_14000F9CC
0x14000f9b9  mov     rdx, [rbx+18h]; BaseAddress
0x14000f9bd  test    rdx, rdx
0x14000f9c0  jz      short loc_14000F9CC
0x14000f9c2  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000f9c6  call    cs:__imp_ZwUnmapViewOfSection
0x14000f9cc  cmp     byte ptr [rbx+29h], 0
0x14000f9d0  jz      short loc_14000F9E1
0x14000f9d2  mov     rcx, [rbx+8]; Handle
0x14000f9d6  test    rcx, rcx
0x14000f9d9  jz      short loc_14000F9E1
0x14000f9db  call    cs:__imp_ZwClose
0x14000f9e1  xorps   xmm0, xmm0
0x14000f9e4  movups  xmmword ptr [rbx], xmm0
0x14000f9e7  movups  xmmword ptr [rbx+10h], xmm0
0x14000f9eb  movups  xmmword ptr [rbx+20h], xmm0
0x14000f9ef  mov     r8, [rdi+40h]; P
0x14000f9f3  test    r8, r8
0x14000f9f6  jz      short loc_14000FA15
0x14000f9f8  mov     rcx, gs:60h
0x14000fa01  xor     edx, edx; Flags
0x14000fa03  mov     rcx, [rcx+30h]; HeapHandle
0x14000fa07  call    cs:__imp_RtlFreeHeap
0x14000fa0d  mov     qword ptr [rdi+40h], 0
0x14000fa15  mov     r8, [rdi]; P
0x14000fa18  test    r8, r8
0x14000fa1b  jz      short loc_14000FA39
0x14000fa1d  mov     rcx, gs:60h
0x14000fa26  xor     edx, edx; Flags
0x14000fa28  mov     rcx, [rcx+30h]; HeapHandle
0x14000fa2c  call    cs:__imp_RtlFreeHeap
0x14000fa32  mov     qword ptr [rdi], 0
0x14000fa39  mov     rcx, gs:60h
0x14000fa42  mov     r8, rdi; P
0x14000fa45  xor     edx, edx; Flags
0x14000fa47  mov     rcx, [rcx+30h]; HeapHandle
0x14000fa4b  call    cs:__imp_RtlFreeHeap
0x14000fa51  mov     rbx, [rsp+28h+arg_0]
0x14000fa56  add     rsp, 20h
0x14000fa5a  pop     rdi
0x14000fa5b  retn
```
