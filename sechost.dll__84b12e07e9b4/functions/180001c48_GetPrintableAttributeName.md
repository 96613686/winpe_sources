# GetPrintableAttributeName

- ea: `0x180001c48`
- end: `0x180001e52`
- name: `GetPrintableAttributeName`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ef0`

## callees

- `0x180001c48`
- `0x180021fd0`
- `0x18004f902`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001d88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001d88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e32`

## string_xrefs

- `0x180001ddf`: `@TOKEN.`

## pseudocode

```c
__int64 __fastcall GetPrintableAttributeName(__int64 a1, int a2, char a3, _QWORD *a4, _DWORD *a5)
{
  unsigned int v5; // edi
  void *v8; // rbp
  unsigned int v9; // ebx
  size_t v10; // r15
  unsigned int v11; // eax
  __int64 v12; // rax
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned __int64 v17; // r14
  char *v18; // rax
  const wchar_t *v19; // rdx
  __int64 v20; // rcx
  size_t v21; // r8
  const void *v22; // rdx
  char *v23; // rcx
  void *v25; // [rsp+20h] [rbp-58h] BYREF

  v5 = 0;
  v25 = 0;
  v8 = 0;
  if ( a1 && a4 && a2 )
  {
    *a5 = 1;
    if ( (unsigned int)(a2 - 1) < 4 || (v10 = *(unsigned int *)(a1 + 1), *a5 = 5, a2 - 5 < (unsigned int)v10) )
    {
      v9 = 1336;
    }
    else
    {
      if ( a3 == -8 )
      {
        v14 = v10 + 2;
        if ( (int)v10 + 2 < (unsigned int)v10 )
          goto LABEL_41;
        v9 = 0;
        LODWORD(v25) = 0;
        goto LABEL_26;
      }
      v11 = EncodeAttributeName(a1 + 5, (unsigned int)v10, &v25);
      v8 = v25;
      v9 = v11;
      if ( !v11 )
      {
        v12 = -1;
        do
          ++v12;
        while ( *((_WORD *)v25 + v12) );
        LODWORD(v25) = 2 * v12;
        v13 = 2 * v12 + 2;
        if ( v13 < 2 * (int)v12 )
          goto LABEL_41;
        if ( a3 == -5 )
        {
          v14 = 2 * v12 + 18;
          if ( v13 + 16 >= v13 )
          {
            v5 = 16;
            goto LABEL_26;
          }
LABEL_41:
          v9 = 534;
          goto LABEL_42;
        }
        v14 = 2 * v12 + 2;
        switch ( a3 )
        {
          case -7:
            v14 = v13 + 12;
            if ( v13 + 12 < v13 )
              goto LABEL_41;
            v5 = 12;
            break;
          case -6:
            v15 = v13 + 20;
            if ( v15 < v14 )
              goto LABEL_41;
            v14 = v15;
            v5 = 20;
            break;
          case -4:
            v16 = v13 + 14;
            if ( v16 < v14 )
              goto LABEL_41;
            v5 = 14;
            v14 = v16;
            break;
        }
LABEL_26:
        v17 = v14;
        v18 = (char *)LocalAlloc(0x40u, v14);
        *a4 = v18;
        if ( !v18 )
        {
          v9 = 8;
          goto LABEL_42;
        }
        switch ( a3 )
        {
          case -5:
            v19 = L"@DEVICE.";
            break;
          case -7:
            v19 = L"@USER.";
            break;
          case -6:
            v19 = L"@RESOURCE.";
            break;
          case -4:
            v19 = L"@TOKEN.";
            break;
          default:
            v20 = v5;
            if ( a3 == -8 )
            {
              v21 = v10;
              v22 = (const void *)(a1 + (unsigned int)*a5);
              v23 = &v18[v5];
              goto LABEL_40;
            }
LABEL_38:
            v21 = (unsigned int)v25;
            v22 = v8;
            v23 = (char *)(*a4 + v20);
LABEL_40:
            memcpy_0(v23, v22, v21);
            *(_WORD *)(*a4 + 2 * (v17 >> 1) - 2) = 0;
            *a5 += v10;
            goto LABEL_42;
        }
        memcpy_0(v18, v19, v5);
        v20 = v5;
        goto LABEL_38;
      }
    }
LABEL_42:
    LocalFree(v8);
    return v9;
  }
  return 87;
}

```

## disassembly

```asm
0x180001c48  mov     [rsp+arg_0], rcx
0x180001c4d  push    rbx
0x180001c4e  push    rbp
0x180001c4f  push    rsi
0x180001c50  push    rdi
0x180001c51  push    r12
0x180001c53  push    r13
0x180001c55  push    r14
0x180001c57  push    r15
0x180001c59  sub     rsp, 38h
0x180001c5d  xor     edi, edi
0x180001c5f  mov     r13, r9
0x180001c62  mov     [rsp+78h+var_58], rdi
0x180001c67  mov     sil, r8b
0x180001c6a  mov     ebp, edi
0x180001c6c  test    rcx, rcx
0x180001c6f  jz      loc_180001E3C
0x180001c75  test    r9, r9
0x180001c78  jz      loc_180001E3C
0x180001c7e  test    edx, edx
0x180001c80  jz      loc_180001E3C
0x180001c86  mov     r12, [rsp+78h+arg_20]
0x180001c8e  lea     eax, [rdx-1]
0x180001c91  mov     dword ptr [r12], 1
0x180001c99  cmp     eax, 4
0x180001c9c  jnb     short loc_180001CA8
0x180001c9e  mov     ebx, 538h
0x180001ca3  jmp     loc_180001E2F
0x180001ca8  mov     r15d, [rcx+1]
0x180001cac  lea     eax, [rdx-5]
0x180001caf  mov     dword ptr [r12], 5
0x180001cb7  cmp     eax, r15d
0x180001cba  jb      short loc_180001C9E
0x180001cbc  cmp     sil, 0F8h
0x180001cc0  jz      loc_180001D6B
0x180001cc6  add     rcx, 5
0x180001cca  lea     r8, [rsp+78h+var_58]
0x180001ccf  mov     edx, r15d
0x180001cd2  call    EncodeAttributeName
0x180001cd7  mov     rbp, [rsp+78h+var_58]
0x180001cdc  mov     ebx, eax
0x180001cde  test    eax, eax
0x180001ce0  jnz     loc_180001E2F
0x180001ce6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001cea  inc     rax
0x180001ced  cmp     [rbp+rax*2+0], di
0x180001cf2  jnz     short loc_180001CEA
0x180001cf4  add     eax, eax
0x180001cf6  mov     dword ptr [rsp+78h+var_58], eax
0x180001cfa  lea     ecx, [rax+2]
0x180001cfd  cmp     ecx, eax
0x180001cff  jb      loc_180001E2A
0x180001d05  cmp     sil, 0FBh
0x180001d09  jnz     short loc_180001D1D
0x180001d0b  lea     eax, [rcx+10h]
0x180001d0e  cmp     eax, ecx
0x180001d10  jb      loc_180001E2A
0x180001d16  mov     edi, 10h
0x180001d1b  jmp     short loc_180001D7E
0x180001d1d  mov     eax, ecx
0x180001d1f  cmp     sil, 0F9h
0x180001d23  jnz     short loc_180001D37
0x180001d25  lea     eax, [rcx+0Ch]
0x180001d28  cmp     eax, ecx
0x180001d2a  jb      loc_180001E2A
0x180001d30  mov     edi, 0Ch
0x180001d35  jmp     short loc_180001D7E
0x180001d37  cmp     sil, 0FAh
0x180001d3b  jnz     short loc_180001D51
0x180001d3d  add     ecx, 14h
0x180001d40  cmp     ecx, eax
0x180001d42  jb      loc_180001E2A
0x180001d48  mov     eax, ecx
0x180001d4a  mov     edi, 14h
0x180001d4f  jmp     short loc_180001D7E
0x180001d51  cmp     sil, 0FCh
0x180001d55  jnz     short loc_180001D7E
0x180001d57  add     ecx, 0Eh
0x180001d5a  cmp     ecx, eax
0x180001d5c  jb      loc_180001E2A
0x180001d62  mov     edi, 0Eh
0x180001d67  mov     eax, ecx
0x180001d69  jmp     short loc_180001D7E
0x180001d6b  lea     eax, [r15+2]
0x180001d6f  cmp     eax, r15d
0x180001d72  jb      loc_180001E2A
0x180001d78  mov     ebx, edi
0x180001d7a  mov     dword ptr [rsp+78h+var_58], edi
0x180001d7e  mov     edx, eax; uBytes
0x180001d80  mov     ecx, 40h ; '@'; uFlags
0x180001d85  mov     r14d, eax
0x180001d88  call    cs:__imp_LocalAlloc
0x180001d8e  mov     [r13+0], rax
0x180001d92  test    rax, rax
0x180001d95  jnz     short loc_180001D9F
0x180001d97  lea     ebx, [rax+8]
0x180001d9a  jmp     loc_180001E2F
0x180001d9f  cmp     sil, 0FBh
0x180001da3  jnz     short loc_180001DAE
0x180001da5  lea     rdx, aDevice; "@DEVICE."
0x180001dac  jmp     short loc_180001DCA
0x180001dae  cmp     sil, 0F9h
0x180001db2  jnz     short loc_180001DBD
0x180001db4  lea     rdx, aUser; "@USER."
0x180001dbb  jmp     short loc_180001DCA
0x180001dbd  cmp     sil, 0FAh
0x180001dc1  jnz     short loc_180001DD9
0x180001dc3  lea     rdx, aResource; "@RESOURCE."
0x180001dca  mov     r8d, edi; Size
0x180001dcd  mov     rcx, rax; void *
0x180001dd0  call    memcpy_0
0x180001dd5  mov     ecx, edi
0x180001dd7  jmp     short loc_180001DF0
0x180001dd9  cmp     sil, 0FCh
0x180001ddd  jnz     short loc_180001DE8
0x180001ddf  lea     rdx, aToken; "@TOKEN."
0x180001de6  jmp     short loc_180001DCA
0x180001de8  mov     ecx, edi
0x180001dea  cmp     sil, 0F8h
0x180001dee  jz      short loc_180001DFE
0x180001df0  mov     r8d, dword ptr [rsp+78h+var_58]
0x180001df5  mov     rdx, rbp
0x180001df8  add     rcx, [r13+0]
0x180001dfc  jmp     short loc_180001E10
0x180001dfe  mov     edx, [r12]
0x180001e02  mov     r8, r15; Size
0x180001e05  add     rdx, [rsp+78h+arg_0]; Src
0x180001e0d  add     rcx, rax; void *
0x180001e10  call    memcpy_0
0x180001e15  mov     rcx, [r13+0]
0x180001e19  xor     eax, eax
0x180001e1b  shr     r14, 1
0x180001e1e  mov     [rcx+r14*2-2], ax
0x180001e24  add     [r12], r15d
0x180001e28  jmp     short loc_180001E2F
0x180001e2a  mov     ebx, 216h
0x180001e2f  mov     rcx, rbp; hMem
0x180001e32  call    cs:__imp_LocalFree
0x180001e38  mov     eax, ebx
0x180001e3a  jmp     short loc_180001E41
0x180001e3c  mov     eax, 57h ; 'W'
0x180001e41  add     rsp, 38h
0x180001e45  pop     r15
0x180001e47  pop     r14
0x180001e49  pop     r13
0x180001e4b  pop     r12
0x180001e4d  pop     rdi
0x180001e4e  pop     rsi
0x180001e4f  pop     rbp
0x180001e50  pop     rbx
0x180001e51  retn
```
