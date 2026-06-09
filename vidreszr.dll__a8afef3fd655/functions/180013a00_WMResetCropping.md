# WMResetCropping

- ea: `0x180013a00`
- end: `0x180013b84`
- name: `WMResetCropping`
- size: `388`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007e90`
- `0x180012e30`

## callees

- `0x180011bc0`
- `0x1800123a0`
- `0x180013a00`

## pseudocode

```c
__int64 __fastcall WMResetCropping(__int64 *a1, int a2, int a3, int a4, int a5, int a6, int a7, int a8, int a9)
{
  __int64 v12; // r10
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // r9d
  int v19; // ecx
  int v20; // r9d
  int v21; // ecx
  int v22; // r9d
  WMSDKRESIZER *v23; // r10
  int v24; // r11d
  int v25; // eax
  unsigned int v26; // ecx

  if ( a2 < 0 || a3 < 0 || a4 < 1 || a5 < 1 || a6 < 0 || a7 < 0 || a8 < 1 || a9 < 1 )
    return 1;
  v12 = *a1;
  v13 = -*(_DWORD *)(*a1 + 48);
  if ( v13 < 0 )
    v13 = *(_DWORD *)(v12 + 48);
  if ( a2 + a4 > v13 )
    return 1;
  v14 = -*(_DWORD *)(v12 + 52);
  if ( *(int *)(v12 + 52) > 0 )
    v14 = *(_DWORD *)(v12 + 52);
  if ( a3 + a5 > v14 )
    return 1;
  v15 = -*(_DWORD *)(v12 + 56);
  if ( *(int *)(v12 + 56) > 0 )
    v15 = *(_DWORD *)(v12 + 56);
  if ( a6 + a8 > v15 )
    return 1;
  v16 = -*(_DWORD *)(v12 + 60);
  if ( *(int *)(v12 + 60) > 0 )
    v16 = *(_DWORD *)(v12 + 60);
  if ( a7 + a9 > v16
    || CheckSize(*(_DWORD *)(*(_QWORD *)(v12 + 8) + 16LL), a4, a5, *(_DWORD *)(v12 + 1084))
    || CheckSize(v17, a8, a9, v18)
    || CheckSize(v19, a2, a3, v20)
    || CheckSize(v21, a6, a7, v22) )
  {
    return 1;
  }
  *((_DWORD *)v23 + 4) = a2;
  *((_DWORD *)v23 + 5) = a3;
  *((_DWORD *)v23 + 8) = a6;
  *((_DWORD *)v23 + 9) = a7;
  *((_DWORD *)v23 + 6) = a4;
  *((_DWORD *)v23 + 7) = v24;
  *((_DWORD *)v23 + 10) = a8;
  *((_DWORD *)v23 + 11) = a9;
  v25 = WMSDKRESIZER::Reset(v23);
  v26 = 0;
  if ( !v25 )
    return (unsigned int)-2147467259;
  return v26;
}

```

## disassembly

```asm
0x180013a00  push    rbx
0x180013a02  push    rbp
0x180013a03  push    rsi
0x180013a04  push    rdi
0x180013a05  push    r12
0x180013a07  push    r14
0x180013a09  push    r15
0x180013a0b  sub     rsp, 20h
0x180013a0f  mov     r15d, r9d
0x180013a12  mov     esi, r8d
0x180013a15  mov     r12d, edx
0x180013a18  test    edx, edx
0x180013a1a  js      loc_180013B70
0x180013a20  test    r8d, r8d
0x180013a23  js      loc_180013B70
0x180013a29  cmp     r9d, 1
0x180013a2d  jl      loc_180013B70
0x180013a33  mov     r11d, [rsp+58h+arg_20]
0x180013a3b  cmp     r11d, 1
0x180013a3f  jl      loc_180013B70
0x180013a45  mov     ebx, [rsp+58h+arg_28]
0x180013a4c  test    ebx, ebx
0x180013a4e  js      loc_180013B70
0x180013a54  mov     edi, [rsp+58h+arg_30]
0x180013a5b  test    edi, edi
0x180013a5d  js      loc_180013B70
0x180013a63  mov     ebp, [rsp+58h+arg_38]
0x180013a6a  cmp     ebp, 1
0x180013a6d  jl      loc_180013B70
0x180013a73  mov     r14d, [rsp+58h+arg_40]
0x180013a7b  cmp     r14d, 1
0x180013a7f  jl      loc_180013B70
0x180013a85  mov     r10, [rcx]
0x180013a88  lea     eax, [rdx+r9]
0x180013a8c  mov     ecx, [r10+30h]
0x180013a90  neg     ecx
0x180013a92  cmovs   ecx, [r10+30h]
0x180013a97  cmp     eax, ecx
0x180013a99  jg      loc_180013B70
0x180013a9f  mov     ecx, [r10+34h]
0x180013aa3  lea     eax, [r8+r11]
0x180013aa7  neg     ecx
0x180013aa9  cmovs   ecx, [r10+34h]
0x180013aae  cmp     eax, ecx
0x180013ab0  jg      loc_180013B70
0x180013ab6  mov     ecx, [r10+38h]
0x180013aba  lea     eax, [rbx+rbp]
0x180013abd  neg     ecx
0x180013abf  cmovs   ecx, [r10+38h]
0x180013ac4  cmp     eax, ecx
0x180013ac6  jg      loc_180013B70
0x180013acc  mov     ecx, [r10+3Ch]
0x180013ad0  lea     eax, [rdi+r14]
0x180013ad4  neg     ecx
0x180013ad6  cmovs   ecx, [r10+3Ch]
0x180013adb  cmp     eax, ecx
0x180013add  jg      loc_180013B70
0x180013ae3  mov     rax, [r10+8]
0x180013ae7  mov     r8d, r11d; int
0x180013aea  mov     r9d, [r10+43Ch]; int
0x180013af1  mov     edx, r15d; int
0x180013af4  mov     ecx, [rax+10h]; int
0x180013af7  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180013afc  test    eax, eax
0x180013afe  jnz     short loc_180013B70
0x180013b00  mov     r8d, r14d; int
0x180013b03  mov     edx, ebp; int
0x180013b05  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180013b0a  test    eax, eax
0x180013b0c  jnz     short loc_180013B70
0x180013b0e  mov     r8d, esi; int
0x180013b11  mov     edx, r12d; int
0x180013b14  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180013b19  test    eax, eax
0x180013b1b  jnz     short loc_180013B70
0x180013b1d  mov     r8d, edi; int
0x180013b20  mov     edx, ebx; int
0x180013b22  call    ?CheckSize@@YAJJJJH@Z; CheckSize(long,long,long,int)
0x180013b27  test    eax, eax
0x180013b29  jnz     short loc_180013B70
0x180013b2b  mov     rcx, r10; this
0x180013b2e  mov     [r10+10h], r12d
0x180013b32  mov     [r10+14h], esi
0x180013b36  mov     [r10+20h], ebx
0x180013b3a  mov     [r10+24h], edi
0x180013b3e  mov     [r10+18h], r15d
0x180013b42  mov     [r10+1Ch], r11d
0x180013b46  mov     [r10+28h], ebp
0x180013b4a  mov     [r10+2Ch], r14d
0x180013b4e  call    ?Reset@WMSDKRESIZER@@QEAAHXZ; WMSDKRESIZER::Reset(void)
0x180013b53  xor     ecx, ecx
0x180013b55  mov     edx, 80004005h
0x180013b5a  test    eax, eax
0x180013b5c  cmovz   ecx, edx
0x180013b5f  mov     eax, ecx
0x180013b61  add     rsp, 20h
0x180013b65  pop     r15
0x180013b67  pop     r14
0x180013b69  pop     r12
0x180013b6b  pop     rdi
0x180013b6c  pop     rsi
0x180013b6d  pop     rbp
0x180013b6e  pop     rbx
0x180013b6f  retn
0x180013b70  mov     eax, 1
0x180013b75  add     rsp, 20h
0x180013b79  pop     r15
0x180013b7b  pop     r14
0x180013b7d  pop     r12
0x180013b7f  pop     rdi
0x180013b80  pop     rsi
0x180013b81  pop     rbp
0x180013b82  pop     rbx
0x180013b83  retn
```
