# NameTbl::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18002fba0`
- end: `0x18002fd0d`
- name: `?GetIDsOfNames@NameTbl@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `365`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002fba0`
- `0x180076746`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002fbc1`
- `KERNEL32!GetCurrentThreadId` at `0x18002fbc1`

## pseudocode

```c
__int64 __fastcall NameTbl::GetIDsOfNames(
        NameTbl *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        unsigned int a5,
        int *a6)
{
  int v6; // ebx
  __int64 v11; // rax
  unsigned __int16 *v12; // r8
  __int64 v13; // rdx
  unsigned int v14; // r15d
  int v15; // eax
  unsigned __int16 v16; // r9
  int *v17; // rdi
  int v18; // ebx
  bool v19; // sf
  unsigned __int16 *v21; // [rsp+30h] [rbp-38h] BYREF
  __int128 v22; // [rsp+38h] [rbp-30h]
  __int64 v23; // [rsp+70h] [rbp+8h] BYREF

  v6 = *((_DWORD *)this + 8);
  if ( GetCurrentThreadId() != v6 )
    return 2147549183LL;
  v11 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a2->Data1 )
    v11 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)a2->Data4;
  if ( !v11 )
  {
    if ( a4 )
    {
      v12 = *a3;
      v13 = -1;
      v14 = 0;
      v21 = *a3;
      v23 = 0;
      v22 = 0;
      do
        ++v13;
      while ( v12[v13] );
      v15 = 0;
      for ( LODWORD(v22) = v13; (int)v13 > 0; v15 = v16 + 17 * v15 )
      {
        v16 = *v12++;
        LODWORD(v13) = v13 - 1;
        if ( (unsigned __int16)(v16 - 65) <= 0x19u )
          v16 += 32;
      }
      v17 = a6;
      DWORD1(v22) = v15;
      v18 = (*(__int64 (__fastcall **)(NameTbl *, unsigned __int16 **, __int64 *, int *))(*(_QWORD *)this + 240LL))(
              this,
              &v21,
              &v23,
              a6);
      v19 = v18 < 0;
      if ( v18 )
      {
LABEL_13:
        if ( v19 )
          goto LABEL_15;
        goto LABEL_14;
      }
      if ( (*(_BYTE *)(v23 + 24) & 4) != 0 )
      {
LABEL_14:
        v18 = -2147352570;
LABEL_15:
        if ( v14 < a4 )
          memset_0(&v17[v14], -1, 4LL * (a4 - v14));
        return (unsigned int)v18;
      }
      v14 = 1;
      if ( a4 > 1 )
      {
        v19 = 0;
        goto LABEL_13;
      }
    }
    else
    {
      return (unsigned int)-2147352570;
    }
    return (unsigned int)v18;
  }
  return 2147614721LL;
}

```

## disassembly

```asm
0x18002fba0  mov     [rsp+arg_10], rbx
0x18002fba5  mov     [rsp+arg_18], rbp
0x18002fbaa  push    rsi
0x18002fbab  push    rdi
0x18002fbac  push    r14
0x18002fbae  sub     rsp, 50h
0x18002fbb2  mov     ebx, [rcx+20h]
0x18002fbb5  mov     ebp, r9d
0x18002fbb8  mov     rsi, r8
0x18002fbbb  mov     rdi, rdx
0x18002fbbe  mov     r14, rcx
0x18002fbc1  call    cs:__imp_GetCurrentThreadId
0x18002fbc7  cmp     eax, ebx
0x18002fbc9  jnz     loc_18002FCC2
0x18002fbcf  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18002fbd6  sub     rax, [rdi]
0x18002fbd9  jnz     short loc_18002FBE6
0x18002fbdb  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18002fbe2  sub     rax, [rdi+8]
0x18002fbe6  test    rax, rax
0x18002fbe9  jnz     loc_18002FCFB
0x18002fbef  test    ebp, ebp
0x18002fbf1  jz      loc_18002FD02
0x18002fbf7  mov     r8, [rsi]
0x18002fbfa  xorps   xmm0, xmm0
0x18002fbfd  mov     [rsp+68h+arg_8], r15
0x18002fc02  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18002fc09  xor     r15d, r15d
0x18002fc0c  mov     [rsp+68h+var_38], r8
0x18002fc11  mov     [rsp+68h+arg_0], r15
0x18002fc16  movdqu  [rsp+68h+var_30], xmm0
0x18002fc1c  nop     dword ptr [rax+00h]
0x18002fc20  inc     rdx
0x18002fc23  cmp     [r8+rdx*2], r15w
0x18002fc28  jnz     short loc_18002FC20
0x18002fc2a  xor     eax, eax
0x18002fc2c  mov     dword ptr [rsp+68h+var_30], edx
0x18002fc30  test    edx, edx
0x18002fc32  jle     short loc_18002FC61
0x18002fc34  nop     dword ptr [rax+00h]
0x18002fc38  nop     dword ptr [rax+rax+00000000h]
0x18002fc40  movzx   r9d, word ptr [r8]
0x18002fc44  lea     r8, [r8+2]
0x18002fc48  dec     edx
0x18002fc4a  lea     ecx, [r9-41h]
0x18002fc4e  cmp     cx, 19h
0x18002fc52  jbe     short loc_18002FCBB
0x18002fc54  imul    eax, 11h
0x18002fc57  movzx   ecx, r9w
0x18002fc5b  add     eax, ecx
0x18002fc5d  test    edx, edx
0x18002fc5f  jg      short loc_18002FC40
0x18002fc61  mov     rdi, [rsp+68h+arg_28]
0x18002fc69  lea     r8, [rsp+68h+arg_0]
0x18002fc6e  mov     dword ptr [rsp+68h+var_30+4], eax
0x18002fc72  lea     rdx, [rsp+68h+var_38]
0x18002fc77  mov     rax, [r14]
0x18002fc7a  mov     r9, rdi
0x18002fc7d  mov     rcx, r14
0x18002fc80  mov     rax, [rax+0F0h]
0x18002fc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc8c  mov     ebx, eax
0x18002fc8e  test    eax, eax
0x18002fc90  jz      short loc_18002FCC9
0x18002fc92  js      short loc_18002FC99
0x18002fc94  mov     ebx, 80020006h
0x18002fc99  cmp     r15d, ebp
0x18002fc9c  jnb     short loc_18002FCDF
0x18002fc9e  mov     eax, r15d
0x18002fca1  sub     ebp, r15d
0x18002fca4  mov     r8d, ebp
0x18002fca7  mov     edx, 0FFFFFFFFh; Val
0x18002fcac  shl     r8, 2; Size
0x18002fcb0  lea     rcx, [rdi+rax*4]; void *
0x18002fcb4  call    memset_0
0x18002fcb9  jmp     short loc_18002FCDF
0x18002fcbb  add     r9w, 20h ; ' '
0x18002fcc0  jmp     short loc_18002FC54
0x18002fcc2  mov     eax, 8000FFFFh
0x18002fcc7  jmp     short loc_18002FCE6
0x18002fcc9  mov     rcx, [rsp+68h+arg_0]
0x18002fcce  test    byte ptr [rcx+18h], 4
0x18002fcd2  jnz     short loc_18002FC94
0x18002fcd4  mov     r15d, 1
0x18002fcda  cmp     ebp, r15d
0x18002fcdd  ja      short loc_18002FD09
0x18002fcdf  mov     r15, [rsp+68h+arg_8]
0x18002fce4  mov     eax, ebx
0x18002fce6  lea     r11, [rsp+68h+var_18]
0x18002fceb  mov     rbx, [r11+30h]
0x18002fcef  mov     rbp, [r11+38h]
0x18002fcf3  mov     rsp, r11
0x18002fcf6  pop     r14
0x18002fcf8  pop     rdi
0x18002fcf9  pop     rsi
0x18002fcfa  retn
0x18002fcfb  mov     eax, 80020001h
0x18002fd00  jmp     short loc_18002FCE6
0x18002fd02  mov     ebx, 80020006h
0x18002fd07  jmp     short loc_18002FCE4
0x18002fd09  test    eax, eax
0x18002fd0b  jmp     short loc_18002FC92
```
