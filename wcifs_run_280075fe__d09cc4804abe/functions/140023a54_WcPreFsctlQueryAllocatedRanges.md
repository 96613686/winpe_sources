# WcPreFsctlQueryAllocatedRanges

- ea: `0x140023a54`
- end: `0x140023c3a`
- name: `WcPreFsctlQueryAllocatedRanges`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140023150`

## callees

- `0x140001500`
- `0x140001b94`
- `0x140023a54`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140023b3d`
- `ntoskrnl!ProbeForRead` at `0x140023b3d`
- `ntoskrnl!ProbeForWrite` at `0x140023b51`
- `ntoskrnl!ProbeForWrite` at `0x140023b51`
- `FLTMGR!FltReleaseContext` at `0x140023c15`
- `FLTMGR!FltReleaseContext` at `0x140023c29`
- `FLTMGR!FltReleaseContext` at `0x140023c15`
- `FLTMGR!FltReleaseContext` at `0x140023c29`

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
0x140023a54  mov     r11, rsp
0x140023a57  mov     [r11+18h], r8
0x140023a5b  mov     [r11+8], rcx
0x140023a5f  push    rbx
0x140023a60  push    rsi
0x140023a61  push    rdi
0x140023a62  push    r12
0x140023a64  push    r13
0x140023a66  push    r14
0x140023a68  push    r15
0x140023a6a  sub     rsp, 30h
0x140023a6e  mov     rax, rdx
0x140023a71  mov     r14, rcx
0x140023a74  mov     qword ptr [r11+20h], 0
0x140023a7c  mov     qword ptr [r11+10h], 0
0x140023a84  xor     ebx, ebx
0x140023a86  lea     r15d, [rbx+1]
0x140023a8a  lea     r9, [r11+20h]
0x140023a8e  lea     r8, [r11+10h]
0x140023a92  mov     rdx, [rdx+20h]; FileObject
0x140023a96  mov     rcx, [rax+18h]; Instance
0x140023a9a  call    WcGetContextFileObject
0x140023a9f  test    al, al
0x140023aa1  jnz     short loc_140023ADA
0x140023aa3  mov     [r14+18h], ebx
0x140023aa7  mov     rsi, [rsp+68h+Context]
0x140023aac  test    rsi, rsi
0x140023aaf  jnz     loc_140023C12
0x140023ab5  mov     rdi, [rsp+68h+arg_18]
0x140023abd  test    rdi, rdi
0x140023ac0  jnz     loc_140023C26
0x140023ac6  mov     eax, r15d
0x140023ac9  add     rsp, 30h
0x140023acd  pop     r15
0x140023acf  pop     r14
0x140023ad1  pop     r13
0x140023ad3  pop     r12
0x140023ad5  pop     rdi
0x140023ad6  pop     rsi
0x140023ad7  pop     rbx
0x140023ad8  retn
0x140023ada  mov     rdi, [rsp+68h+arg_18]
0x140023ae2  mov     rdx, rdi
0x140023ae5  mov     rsi, [rsp+68h+Context]
0x140023aea  mov     rcx, rsi
0x140023aed  call    WcIsPlaceHolderStream
0x140023af2  test    al, al
0x140023af4  jz      short loc_140023AA3
0x140023af6  mov     [r14+20h], rbx
0x140023afa  mov     r15d, 4
0x140023b00  mov     [rsp+68h+arg_10], r15d
0x140023b08  mov     rax, [rsi]
0x140023b0b  mov     r12d, [rax+0Ch]
0x140023b0f  mov     r13, [rdi+48h]
0x140023b13  mov     rax, [r14+10h]
0x140023b17  mov     rdi, [rax+38h]
0x140023b1b  mov     esi, [rax+18h]
0x140023b1e  mov     rbx, [rax+30h]
0x140023b22  mov     ecx, [rax+20h]
0x140023b25  cmp     ecx, 10h
0x140023b28  jb      loc_140023BCC
0x140023b2e  cmp     byte ptr [r14+50h], 0
0x140023b33  jz      short loc_140023B5D
0x140023b35  mov     edx, ecx; Length
0x140023b37  mov     r8d, r15d; Alignment
0x140023b3a  mov     rcx, rbx; Address
0x140023b3d  call    cs:__imp_ProbeForRead
0x140023b44  nop     dword ptr [rax+rax+00h]
0x140023b49  mov     edx, esi; Length
0x140023b4b  mov     r8d, r15d; Alignment
0x140023b4e  mov     rcx, rdi; Address
0x140023b51  call    cs:__imp_ProbeForWrite
0x140023b58  nop     dword ptr [rax+rax+00h]
0x140023b5d  mov     rdx, [rbx]
0x140023b60  mov     r8, [rbx+8]
0x140023b64  jmp     short loc_140023B7D
0x140023b66  mov     ebx, 0C00000E8h
0x140023b6b  mov     r14, [rsp+68h+arg_0]
0x140023b70  mov     r15d, [rsp+68h+arg_10]
0x140023b78  jmp     loc_140023AA3
0x140023b7d  test    rdx, rdx
0x140023b80  js      short loc_140023BCC
0x140023b82  test    r8, r8
0x140023b85  js      short loc_140023BCC
0x140023b87  mov     rax, 7FFFFFFFFFFFFFFFh
0x140023b91  sub     rax, rdx
0x140023b94  cmp     r8, rax
0x140023b97  jg      short loc_140023BCC
0x140023b99  test    r8, r8
0x140023b9c  jz      short loc_140023C0B
0x140023b9e  mov     rax, r12
0x140023ba1  lea     rcx, [r13-1]
0x140023ba5  add     rcx, r12
0x140023ba8  neg     rax
0x140023bab  and     rcx, rax
0x140023bae  cmp     rdx, rcx
0x140023bb1  jg      short loc_140023C0B
0x140023bb3  sub     rcx, rdx
0x140023bb6  cmp     rcx, r8
0x140023bb9  cmovge  rcx, r8
0x140023bbd  cmp     esi, 10h
0x140023bc0  jnb     short loc_140023BD6
0x140023bc2  mov     ebx, 0C0000023h
0x140023bc7  jmp     loc_140023AA3
0x140023bcc  mov     ebx, 0C000000Dh
0x140023bd1  jmp     loc_140023AA3
0x140023bd6  mov     [rdi], rdx
0x140023bd9  mov     [rdi+8], rcx
0x140023bdd  mov     qword ptr [r14+20h], 10h
0x140023be5  xor     ebx, ebx
0x140023be7  mov     [rsp+68h+var_48], ebx
0x140023beb  jmp     loc_140023AA3
0x140023bf0  mov     ebx, 0C00000E8h
0x140023bf5  mov     [rsp+68h+var_48], ebx
0x140023bf9  mov     r14, [rsp+68h+arg_0]
0x140023bfe  mov     r15d, [rsp+68h+arg_10]
0x140023c06  jmp     loc_140023AA3
0x140023c0b  xor     ebx, ebx
0x140023c0d  jmp     loc_140023AA3
0x140023c12  mov     rcx, rsi; Context
0x140023c15  call    cs:__imp_FltReleaseContext
0x140023c1c  nop     dword ptr [rax+rax+00h]
0x140023c21  jmp     loc_140023AB5
0x140023c26  mov     rcx, rdi; Context
0x140023c29  call    cs:__imp_FltReleaseContext
0x140023c30  nop     dword ptr [rax+rax+00h]
0x140023c35  jmp     loc_140023AC6
```
