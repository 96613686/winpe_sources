# WcPreFsctlQueryAllocatedRanges

- ea: `0x140023aa4`
- end: `0x140023c8a`
- name: `WcPreFsctlQueryAllocatedRanges`
- size: `486`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400231a0`

## callees

- `0x140001500`
- `0x140001b94`
- `0x140023aa4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140023b8d`
- `ntoskrnl!ProbeForRead` at `0x140023b8d`
- `ntoskrnl!ProbeForWrite` at `0x140023ba1`
- `ntoskrnl!ProbeForWrite` at `0x140023ba1`
- `FLTMGR!FltReleaseContext` at `0x140023c65`
- `FLTMGR!FltReleaseContext` at `0x140023c79`
- `FLTMGR!FltReleaseContext` at `0x140023c65`
- `FLTMGR!FltReleaseContext` at `0x140023c79`

## pseudocode

```c
__int64 __fastcall WcPreFsctlQueryAllocatedRanges(__int64 a1, __int64 a2)
{
  int v3; // ebx
  unsigned int v4; // r15d
  __int64 v6; // r12
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 *v9; // rdi
  unsigned int v10; // esi
  __int64 *v11; // rbx
  unsigned int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rcx

  v3 = 0;
  v4 = 1;
  if ( (unsigned __int8)WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32))
    && (unsigned __int8)WcIsPlaceHolderStream(0, 0) )
  {
    *(_QWORD *)(a1 + 32) = 0;
    v4 = 4;
    v6 = *(unsigned int *)(MEMORY[0] + 12LL);
    v7 = MEMORY[0x48];
    v8 = *(_QWORD *)(a1 + 16);
    v9 = *(__int64 **)(v8 + 56);
    v10 = *(_DWORD *)(v8 + 24);
    v11 = *(__int64 **)(v8 + 48);
    v12 = *(_DWORD *)(v8 + 32);
    if ( v12 < 0x10 )
      goto LABEL_16;
    if ( *(_BYTE *)(a1 + 80) )
    {
      ProbeForRead(*(volatile void **)(v8 + 48), v12, 4u);
      ProbeForWrite(v9, v10, 4u);
    }
    v13 = *v11;
    v14 = v11[1];
    if ( *v11 < 0 || v14 < 0 || v14 > 0x7FFFFFFFFFFFFFFFLL - v13 )
    {
LABEL_16:
      v3 = -1073741811;
    }
    else if ( v14 && (v15 = -v6 & (v6 + v7 - 1), v13 <= v15) )
    {
      v16 = v15 - v13;
      if ( v16 >= v14 )
        v16 = v11[1];
      if ( v10 >= 0x10 )
      {
        *v9 = v13;
        v9[1] = v16;
        *(_QWORD *)(a1 + 32) = 16;
        v3 = 0;
      }
      else
      {
        v3 = -1073741789;
      }
    }
    else
    {
      v3 = 0;
    }
  }
  *(_DWORD *)(a1 + 24) = v3;
  return v4;
}

```

## disassembly

```asm
0x140023aa4  mov     r11, rsp
0x140023aa7  mov     [r11+18h], r8
0x140023aab  mov     [r11+8], rcx
0x140023aaf  push    rbx
0x140023ab0  push    rsi
0x140023ab1  push    rdi
0x140023ab2  push    r12
0x140023ab4  push    r13
0x140023ab6  push    r14
0x140023ab8  push    r15
0x140023aba  sub     rsp, 30h
0x140023abe  mov     rax, rdx
0x140023ac1  mov     r14, rcx
0x140023ac4  mov     qword ptr [r11+20h], 0
0x140023acc  mov     qword ptr [r11+10h], 0
0x140023ad4  xor     ebx, ebx
0x140023ad6  lea     r15d, [rbx+1]
0x140023ada  lea     r9, [r11+20h]
0x140023ade  lea     r8, [r11+10h]
0x140023ae2  mov     rdx, [rdx+20h]; FileObject
0x140023ae6  mov     rcx, [rax+18h]; Instance
0x140023aea  call    WcGetContextFileObject
0x140023aef  test    al, al
0x140023af1  jnz     short loc_140023B2A
0x140023af3  mov     [r14+18h], ebx
0x140023af7  mov     rsi, [rsp+68h+Context]
0x140023afc  test    rsi, rsi
0x140023aff  jnz     loc_140023C62
0x140023b05  mov     rdi, [rsp+68h+arg_18]
0x140023b0d  test    rdi, rdi
0x140023b10  jnz     loc_140023C76
0x140023b16  mov     eax, r15d
0x140023b19  add     rsp, 30h
0x140023b1d  pop     r15
0x140023b1f  pop     r14
0x140023b21  pop     r13
0x140023b23  pop     r12
0x140023b25  pop     rdi
0x140023b26  pop     rsi
0x140023b27  pop     rbx
0x140023b28  retn
0x140023b2a  mov     rdi, [rsp+68h+arg_18]
0x140023b32  mov     rdx, rdi
0x140023b35  mov     rsi, [rsp+68h+Context]
0x140023b3a  mov     rcx, rsi
0x140023b3d  call    WcIsPlaceHolderStream
0x140023b42  test    al, al
0x140023b44  jz      short loc_140023AF3
0x140023b46  mov     [r14+20h], rbx
0x140023b4a  mov     r15d, 4
0x140023b50  mov     [rsp+68h+arg_10], r15d
0x140023b58  mov     rax, [rsi]
0x140023b5b  mov     r12d, [rax+0Ch]
0x140023b5f  mov     r13, [rdi+48h]
0x140023b63  mov     rax, [r14+10h]
0x140023b67  mov     rdi, [rax+38h]
0x140023b6b  mov     esi, [rax+18h]
0x140023b6e  mov     rbx, [rax+30h]
0x140023b72  mov     ecx, [rax+20h]
0x140023b75  cmp     ecx, 10h
0x140023b78  jb      loc_140023C1C
0x140023b7e  cmp     byte ptr [r14+50h], 0
0x140023b83  jz      short loc_140023BAD
0x140023b85  mov     edx, ecx; Length
0x140023b87  mov     r8d, r15d; Alignment
0x140023b8a  mov     rcx, rbx; Address
0x140023b8d  call    cs:__imp_ProbeForRead
0x140023b94  nop     dword ptr [rax+rax+00h]
0x140023b99  mov     edx, esi; Length
0x140023b9b  mov     r8d, r15d; Alignment
0x140023b9e  mov     rcx, rdi; Address
0x140023ba1  call    cs:__imp_ProbeForWrite
0x140023ba8  nop     dword ptr [rax+rax+00h]
0x140023bad  mov     rdx, [rbx]
0x140023bb0  mov     r8, [rbx+8]
0x140023bb4  jmp     short loc_140023BCD
0x140023bb6  mov     ebx, 0C00000E8h
0x140023bbb  mov     r14, [rsp+68h+arg_0]
0x140023bc0  mov     r15d, [rsp+68h+arg_10]
0x140023bc8  jmp     loc_140023AF3
0x140023bcd  test    rdx, rdx
0x140023bd0  js      short loc_140023C1C
0x140023bd2  test    r8, r8
0x140023bd5  js      short loc_140023C1C
0x140023bd7  mov     rax, 7FFFFFFFFFFFFFFFh
0x140023be1  sub     rax, rdx
0x140023be4  cmp     r8, rax
0x140023be7  jg      short loc_140023C1C
0x140023be9  test    r8, r8
0x140023bec  jz      short loc_140023C5B
0x140023bee  mov     rax, r12
0x140023bf1  lea     rcx, [r13-1]
0x140023bf5  add     rcx, r12
0x140023bf8  neg     rax
0x140023bfb  and     rcx, rax
0x140023bfe  cmp     rdx, rcx
0x140023c01  jg      short loc_140023C5B
0x140023c03  sub     rcx, rdx
0x140023c06  cmp     rcx, r8
0x140023c09  cmovge  rcx, r8
0x140023c0d  cmp     esi, 10h
0x140023c10  jnb     short loc_140023C26
0x140023c12  mov     ebx, 0C0000023h
0x140023c17  jmp     loc_140023AF3
0x140023c1c  mov     ebx, 0C000000Dh
0x140023c21  jmp     loc_140023AF3
0x140023c26  mov     [rdi], rdx
0x140023c29  mov     [rdi+8], rcx
0x140023c2d  mov     qword ptr [r14+20h], 10h
0x140023c35  xor     ebx, ebx
0x140023c37  mov     [rsp+68h+var_48], ebx
0x140023c3b  jmp     loc_140023AF3
0x140023c40  mov     ebx, 0C00000E8h
0x140023c45  mov     [rsp+68h+var_48], ebx
0x140023c49  mov     r14, [rsp+68h+arg_0]
0x140023c4e  mov     r15d, [rsp+68h+arg_10]
0x140023c56  jmp     loc_140023AF3
0x140023c5b  xor     ebx, ebx
0x140023c5d  jmp     loc_140023AF3
0x140023c62  mov     rcx, rsi; Context
0x140023c65  call    cs:__imp_FltReleaseContext
0x140023c6c  nop     dword ptr [rax+rax+00h]
0x140023c71  jmp     loc_140023B05
0x140023c76  mov     rcx, rdi; Context
0x140023c79  call    cs:__imp_FltReleaseContext
0x140023c80  nop     dword ptr [rax+rax+00h]
0x140023c85  jmp     loc_140023B16
```
