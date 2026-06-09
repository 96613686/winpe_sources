# SrvNetCopyIndicationToBufferEx

- ea: `0x140003a90`
- end: `0x140003d68`
- name: `SrvNetCopyIndicationToBufferEx`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140018de0`

## callees

- `0x140003a90`
- `0x1400199ec`
- `0x140019a64`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003cb9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140003cb9`

## pseudocode

```c
__int64 __fastcall SrvNetCopyIndicationToBufferEx(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4, char **a5)
{
  unsigned int v5; // edi
  unsigned int v7; // r12d
  __int64 v8; // r10
  _QWORD *v9; // r14
  bool v10; // zf
  struct _MDL *v11; // rbx
  _QWORD *v12; // r9
  _QWORD *v13; // rax
  int v14; // r13d
  __int64 v15; // rdx
  int v16; // r15d
  char *MappedSystemVa; // r9
  unsigned int v18; // edx
  unsigned int v19; // esi
  char *v21; // rcx
  char *v22; // rax
  int v23; // [rsp+50h] [rbp-48h]
  unsigned int v26; // [rsp+B0h] [rbp+18h]

  v26 = a3;
  v5 = 0;
  v7 = 0;
  v8 = a2;
  v9 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqdd(WPP_GLOBAL_Control->AttachedDevice, 12, a3, a1, a2, a3, a4);
    a3 = v26;
    v8 = a2;
  }
LABEL_2:
  if ( v9 )
  {
    v10 = v5 == a4;
    if ( v5 < a4 )
    {
      v11 = (struct _MDL *)v9[1];
      v12 = v9 + 1;
      v13 = v9;
      v14 = 0;
      v9 = (_QWORD *)*v9;
      v15 = *((unsigned int *)v13 + 6);
      v16 = *((_DWORD *)v13 + 4);
      v23 = *((_DWORD *)v13 + 6);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqdqdd(WPP_GLOBAL_Control->AttachedDevice, v15, a3, v12, v11, v16, v9, v7, v5);
        a3 = v26;
        goto LABEL_21;
      }
      while ( 1 )
      {
LABEL_6:
        if ( !v11 || v5 >= a4 )
          goto LABEL_2;
        if ( (v11->MdlFlags & 5) != 0 )
        {
          MappedSystemVa = (char *)v11->MappedSystemVa;
        }
        else
        {
          v22 = (char *)MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000000u);
          a3 = v26;
          MappedSystemVa = v22;
          LODWORD(v15) = v23;
          v8 = a2;
        }
        if ( !MappedSystemVa )
          return 3221225626LL;
        v18 = v15 - v14;
        if ( v18 >= v11->ByteCount - v16 )
          v18 = v11->ByteCount - v16;
        if ( v7 >= (unsigned int)a3 )
          goto LABEL_14;
        if ( v18 > (unsigned int)a3 - v7 )
          break;
        v11 = v11->Next;
        v14 += v18;
        v8 = a2;
        v7 += v18;
        LODWORD(v15) = v23;
        v16 = 0;
      }
      v16 += a3 - v7;
      v14 += a3 - v7;
      v18 = v7 + v18 - a3;
      v7 = a3;
LABEL_14:
      if ( v18 )
      {
        v19 = a4 - v5;
        if ( v18 < a4 - v5 )
          v19 = v18;
        if ( !v5 )
        {
          if ( a5 )
          {
            v21 = &MappedSystemVa[v16];
            if ( ((unsigned __int8)v21 & 7) == 0 && v19 == a4 )
            {
              *a5 = v21;
              return 3221225489LL;
            }
          }
        }
        memmove((void *)(v8 + v5), &MappedSystemVa[v16], v19);
        a3 = v26;
        v5 += v19;
        v7 += v19;
        v14 += v19;
      }
      v11 = v11->Next;
      v16 = 0;
LABEL_21:
      v8 = a2;
      LODWORD(v15) = v23;
      goto LABEL_6;
    }
  }
  else
  {
    v10 = v5 == a4;
  }
  if ( v10 )
    return 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qqdd(WPP_GLOBAL_Control->AttachedDevice, 14, a3, a1, v8, a3, a4);
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140003a90  mov     [rsp+arg_18], rbx
0x140003a95  mov     [rsp+arg_10], r8d
0x140003a9a  mov     [rsp+arg_8], rdx
0x140003a9f  mov     [rsp+arg_0], rcx
0x140003aa4  push    rbp
0x140003aa5  push    rsi
0x140003aa6  push    rdi
0x140003aa7  push    r12
0x140003aa9  push    r13
0x140003aab  push    r14
0x140003aad  push    r15
0x140003aaf  sub     rsp, 60h
0x140003ab3  xor     edi, edi
0x140003ab5  mov     ebp, r9d
0x140003ab8  xor     r12d, r12d
0x140003abb  mov     r10, rdx
0x140003abe  mov     r9, rcx
0x140003ac1  mov     r14, rcx
0x140003ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x140003acb  lea     r11, WPP_GLOBAL_Control
0x140003ad2  cmp     rcx, r11
0x140003ad5  jnz     loc_140003BE3
0x140003adb  test    r14, r14
0x140003ade  jz      loc_140003BD7
0x140003ae4  cmp     edi, ebp
0x140003ae6  jnb     loc_140003BD9
0x140003aec  mov     rbx, [r14+8]
0x140003af0  lea     r9, [r14+8]
0x140003af4  mov     rax, r14
0x140003af7  xor     r13d, r13d
0x140003afa  mov     r14, [r14]
0x140003afd  mov     edx, [rax+18h]
0x140003b00  mov     r15d, [rax+10h]
0x140003b04  mov     [rsp+98h+var_48], edx
0x140003b08  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b0f  cmp     rcx, r11
0x140003b12  jz      short loc_140003B1F
0x140003b14  mov     eax, [rcx+2Ch]
0x140003b17  test    al, 10h
0x140003b19  jnz     loc_140003CE1
0x140003b1f  lea     r11, WPP_GLOBAL_Control
0x140003b26  test    rbx, rbx
0x140003b29  jz      short loc_140003ADB
0x140003b2b  cmp     edi, ebp
0x140003b2d  jnb     loc_140003C24
0x140003b33  test    byte ptr [rbx+0Ah], 5
0x140003b37  jz      loc_140003C9B
0x140003b3d  mov     r9, [rbx+18h]
0x140003b41  test    r9, r9
0x140003b44  jz      short loc_140003BB9
0x140003b46  mov     ecx, [rbx+28h]
0x140003b49  sub     edx, r13d
0x140003b4c  sub     ecx, r15d
0x140003b4f  cmp     edx, ecx
0x140003b51  cmovnb  edx, ecx
0x140003b54  cmp     r12d, r8d
0x140003b57  jb      loc_140003C30
0x140003b5d  test    edx, edx
0x140003b5f  jz      short loc_140003BA2
0x140003b61  mov     esi, ebp
0x140003b63  sub     esi, edi
0x140003b65  cmp     edx, esi
0x140003b67  cmovb   esi, edx
0x140003b6a  test    edi, edi
0x140003b6c  jnz     short loc_140003B7F
0x140003b6e  mov     rdx, [rsp+98h+arg_20]
0x140003b76  test    rdx, rdx
0x140003b79  jnz     loc_140003C5A
0x140003b7f  mov     edx, r15d
0x140003b82  mov     ecx, edi
0x140003b84  add     rdx, r9; Src
0x140003b87  add     rcx, r10; void *
0x140003b8a  mov     r8d, esi; Size
0x140003b8d  call    memmove
0x140003b92  mov     r8d, [rsp+98h+arg_10]
0x140003b9a  add     edi, esi
0x140003b9c  add     r12d, esi
0x140003b9f  add     r13d, esi
0x140003ba2  mov     rbx, [rbx]
0x140003ba5  xor     r15d, r15d
0x140003ba8  mov     r10, [rsp+98h+arg_8]
0x140003bb0  mov     edx, [rsp+98h+var_48]
0x140003bb4  jmp     loc_140003B1F
0x140003bb9  mov     eax, 0C000009Ah
0x140003bbe  mov     rbx, [rsp+98h+arg_18]
0x140003bc6  add     rsp, 60h
0x140003bca  pop     r15
0x140003bcc  pop     r14
0x140003bce  pop     r13
0x140003bd0  pop     r12
0x140003bd2  pop     rdi
0x140003bd3  pop     rsi
0x140003bd4  pop     rbp
0x140003bd5  retn
0x140003bd7  cmp     edi, ebp
0x140003bd9  jnz     loc_140003D19
0x140003bdf  xor     eax, eax
0x140003be1  jmp     short loc_140003BBE
0x140003be3  mov     eax, [rcx+2Ch]
0x140003be6  test    al, 10h
0x140003be8  jz      loc_140003ADB
0x140003bee  cmp     byte ptr [rcx+29h], 2
0x140003bf2  jb      loc_140003ADB
0x140003bf8  mov     rcx, [rcx+18h]
0x140003bfc  mov     edx, 0Ch
0x140003c01  mov     dword ptr [rsp+98h+var_68], ebp
0x140003c05  mov     [rsp+98h+Priority], r8d
0x140003c0a  mov     qword ptr [rsp+98h+BugCheckOnFailure], r10
0x140003c0f  call    WPP_SF_qqdd
0x140003c14  mov     r8d, [rsp+98h+arg_10]
0x140003c1c  mov     r10, [rsp+98h+arg_8]
0x140003c24  lea     r11, WPP_GLOBAL_Control
0x140003c2b  jmp     loc_140003ADB
0x140003c30  mov     eax, r8d
0x140003c33  sub     eax, r12d
0x140003c36  cmp     edx, eax
0x140003c38  jbe     short loc_140003C7E
0x140003c3a  mov     eax, r8d
0x140003c3d  sub     edx, r8d
0x140003c40  sub     eax, r12d
0x140003c43  add     r15d, eax
0x140003c46  mov     eax, r8d
0x140003c49  sub     eax, r12d
0x140003c4c  add     r13d, eax
0x140003c4f  add     edx, r12d
0x140003c52  mov     r12d, r8d
0x140003c55  jmp     loc_140003B5D
0x140003c5a  mov     ecx, r15d
0x140003c5d  add     rcx, r9
0x140003c60  test    cl, 7
0x140003c63  jnz     loc_140003B7F
0x140003c69  cmp     esi, ebp
0x140003c6b  jnz     loc_140003B7F
0x140003c71  mov     [rdx], rcx
0x140003c74  mov     eax, 0C0000011h
0x140003c79  jmp     loc_140003BBE
0x140003c7e  mov     rbx, [rbx]
0x140003c81  add     r13d, edx
0x140003c84  mov     r10, [rsp+98h+arg_8]
0x140003c8c  add     r12d, edx
0x140003c8f  mov     edx, [rsp+98h+var_48]
0x140003c93  xor     r15d, r15d
0x140003c96  jmp     loc_140003B1F
0x140003c9b  mov     [rsp+98h+Priority], 40000000h; Priority
0x140003ca3  xor     r9d, r9d; RequestedAddress
0x140003ca6  xor     edx, edx; AccessMode
0x140003ca8  mov     [rsp+98h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140003cb0  mov     r8d, 1; CacheType
0x140003cb6  mov     rcx, rbx; MemoryDescriptorList
0x140003cb9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140003cc0  nop     dword ptr [rax+rax+00h]
0x140003cc5  mov     r8d, [rsp+98h+arg_10]
0x140003ccd  mov     r9, rax
0x140003cd0  mov     edx, [rsp+98h+var_48]
0x140003cd4  mov     r10, [rsp+98h+arg_8]
0x140003cdc  jmp     loc_140003B41
0x140003ce1  cmp     byte ptr [rcx+29h], 2
0x140003ce5  jb      loc_140003B1F
0x140003ceb  mov     rcx, [rcx+18h]
0x140003cef  mov     [rsp+98h+var_58], edi
0x140003cf3  mov     [rsp+98h+var_60], r12d
0x140003cf8  mov     [rsp+98h+var_68], r14
0x140003cfd  mov     [rsp+98h+Priority], r15d
0x140003d02  mov     qword ptr [rsp+98h+BugCheckOnFailure], rbx
0x140003d07  call    WPP_SF_qqdqdd
0x140003d0c  mov     r8d, [rsp+98h+arg_10]
0x140003d14  jmp     loc_140003BA8
0x140003d19  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d20  cmp     rcx, r11
0x140003d23  jz      loc_14002AFBA
0x140003d29  mov     eax, [rcx+2Ch]
0x140003d2c  test    al, 10h
0x140003d2e  jz      loc_14002AFBA
0x140003d34  cmp     byte ptr [rcx+29h], 1
0x140003d38  jb      loc_14002AFBA
0x140003d3e  mov     r9, [rsp+98h+arg_0]
0x140003d46  mov     edx, 0Eh
0x140003d4b  mov     rcx, [rcx+18h]
0x140003d4f  mov     dword ptr [rsp+98h+var_68], ebp
0x140003d53  mov     [rsp+98h+Priority], r8d
0x140003d58  mov     qword ptr [rsp+98h+BugCheckOnFailure], r10
0x140003d5d  call    WPP_SF_qqdd
0x140003d62  nop
0x140003d63  jmp     loc_14002AFBA
0x14002afba  mov     eax, 0C000000Dh
0x14002afbf  jmp     loc_140003BBE
```
