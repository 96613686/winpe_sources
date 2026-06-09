# CspRemoveContainer

- ea: `0x18002e180`
- end: `0x18002e267`
- name: `CspRemoveContainer`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001e590`

## callees

- `0x18000d9d0`
- `0x18002d504`
- `0x18002d61c`
- `0x18002e180`
- `0x18002ee0c`
- `0x180030e7c`

## pseudocode

```c
__int64 __fastcall CspRemoveContainer(__int64 a1, unsigned __int16 *a2, unsigned __int8 a3, int a4)
{
  __int64 v7; // rdx
  unsigned int v8; // edi
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  char *v12; // rbx
  char *v14[5]; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = a4;
  v14[0] = 0;
  LOBYTE(v15) = 0;
  v8 = CspBuildCertificateFilename(a1, a2, 0, 2, v14);
  if ( v8
    || (CspDeleteFile(a1, v7, v9, v14[0]),
        CspFreeH(v14[0]),
        v14[0] = 0,
        (v8 = CspBuildCertificateFilename(a1, a2, 0, 1, v14)) != 0) )
  {
    v12 = v14[0];
  }
  else
  {
    v12 = v14[0];
    CspDeleteFile(a1, v10, v11, v14[0]);
    v8 = CspDeleteContainer(a1, a3);
    if ( !v8 )
      v8 = ContainerMapDeleteContainer(a1, a2, (unsigned __int8 *)&v15);
  }
  if ( v12 )
    CspFreeH(v12);
  return v8;
}

```

## disassembly

```asm
0x18002e180  mov     rax, rsp
0x18002e183  mov     [rax+8], rbx
0x18002e187  mov     [rax+10h], rbp
0x18002e18b  mov     [rax+20h], r9d
0x18002e18f  push    rsi
0x18002e190  push    rdi
0x18002e191  push    r14
0x18002e193  sub     rsp, 40h
0x18002e197  mov     qword ptr [rax-28h], 0
0x18002e19f  mov     r14b, r8b
0x18002e1a2  mov     byte ptr [rax+20h], 0
0x18002e1a6  lea     rax, [rax-28h]
0x18002e1aa  mov     r9d, 2
0x18002e1b0  mov     [rsp+58h+var_38], rax
0x18002e1b5  xor     r8d, r8d
0x18002e1b8  mov     rbp, rdx
0x18002e1bb  mov     rsi, rcx
0x18002e1be  call    CspBuildCertificateFilename
0x18002e1c3  mov     edi, eax
0x18002e1c5  test    eax, eax
0x18002e1c7  jnz     short loc_18002E240
0x18002e1c9  mov     r9, [rsp+58h+var_28]
0x18002e1ce  mov     rcx, rsi
0x18002e1d1  call    CspDeleteFile
0x18002e1d6  mov     rcx, [rsp+58h+var_28]
0x18002e1db  call    CspFreeH
0x18002e1e0  lea     rax, [rsp+58h+var_28]
0x18002e1e5  mov     [rsp+58h+var_28], 0
0x18002e1ee  lea     r9d, [rdi+1]
0x18002e1f2  mov     [rsp+58h+var_38], rax
0x18002e1f7  xor     r8d, r8d
0x18002e1fa  mov     rdx, rbp
0x18002e1fd  mov     rcx, rsi
0x18002e200  call    CspBuildCertificateFilename
0x18002e205  mov     edi, eax
0x18002e207  test    eax, eax
0x18002e209  jnz     short loc_18002E240
0x18002e20b  mov     rbx, [rsp+58h+var_28]
0x18002e210  mov     rcx, rsi
0x18002e213  mov     r9, rbx
0x18002e216  call    CspDeleteFile
0x18002e21b  mov     dl, r14b
0x18002e21e  mov     rcx, rsi
0x18002e221  call    CspDeleteContainer
0x18002e226  mov     edi, eax
0x18002e228  test    eax, eax
0x18002e22a  jnz     short loc_18002E245
0x18002e22c  lea     r8, [rsp+58h+arg_18]
0x18002e231  mov     rdx, rbp
0x18002e234  mov     rcx, rsi
0x18002e237  call    ContainerMapDeleteContainer
0x18002e23c  mov     edi, eax
0x18002e23e  jmp     short loc_18002E245
0x18002e240  mov     rbx, [rsp+58h+var_28]
0x18002e245  test    rbx, rbx
0x18002e248  jz      short loc_18002E252
0x18002e24a  mov     rcx, rbx
0x18002e24d  call    CspFreeH
0x18002e252  mov     rbx, [rsp+58h+arg_0]
0x18002e257  mov     eax, edi
0x18002e259  mov     rbp, [rsp+58h+arg_8]
0x18002e25e  add     rsp, 40h
0x18002e262  pop     r14
0x18002e264  pop     rdi
0x18002e265  pop     rsi
0x18002e266  retn
```
