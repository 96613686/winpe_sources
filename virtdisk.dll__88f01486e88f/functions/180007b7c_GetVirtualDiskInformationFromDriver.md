# GetVirtualDiskInformationFromDriver

- ea: `0x180007b7c`
- end: `0x180007f24`
- name: `GetVirtualDiskInformationFromDriver`
- size: `936`
- prototype: `__int64 __fastcall(HANDLE hFile, unsigned int, _DWORD *, int *, _DWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800078f4`
- `0x180007a40`
- `0x180007f2c`
- `0x1800085a8`

## callees

- `0x180004110`
- `0x180006edc`
- `0x180007b7c`
- `0x18000ba11`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180007f04`
- `ntdll!RtlFreeHeap` at `0x180007f04`
- `ntdll!RtlAllocateHeap` at `0x180007cc0`
- `ntdll!RtlAllocateHeap` at `0x180007cc0`

## pseudocode

```c
__int64 __fastcall GetVirtualDiskInformationFromDriver(HANDLE hFile, unsigned int a2, _DWORD *a3, int *a4, _DWORD *a5)
{
  unsigned int v8; // esi
  int v9; // ecx
  DWORD v10; // r14d
  unsigned int v11; // r13d
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  unsigned __int8 *Heap; // rbx
  DWORD v24; // eax
  __int64 v25; // r12
  _DWORD *v26; // r14
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // eax
  int v33; // eax
  const wchar_t *v34; // r15
  size_t v35; // r11
  HRESULT v36; // eax
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  unsigned int v42; // [rsp+40h] [rbp-18h]
  DWORD NumberOfBytesTransferred; // [rsp+44h] [rbp-14h] BYREF
  size_t pcchLength[2]; // [rsp+48h] [rbp-10h] BYREF
  int InBuffer; // [rsp+A8h] [rbp+50h] BYREF

  NumberOfBytesTransferred = 0;
  pcchLength[0] = 0;
  if ( a2 < 0x20 )
    return 87;
  v9 = *a3;
  v10 = 32;
  v42 = 0;
  v11 = 0;
  v8 = 14;
  if ( (int)*a3 > 8 )
  {
    v18 = v9 - 9;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 2;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              if ( v22 != 1 )
                return 87;
              v11 = a2 - 18;
              InBuffer = 15;
              v42 = a2 - 18;
              v10 = a2 - 18 + 32;
            }
            else
            {
              InBuffer = 14;
            }
          }
          else
          {
            InBuffer = 13;
          }
        }
        else
        {
          InBuffer = 12;
        }
      }
      else
      {
        InBuffer = 10;
      }
    }
    else
    {
      InBuffer = 9;
    }
LABEL_32:
    Heap = (unsigned __int8 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    if ( !Heap )
      return v8;
    v24 = IssueSynchronousDeviceIoControl(hFile, 0x2D1940u, &InBuffer, 4u, Heap, v10, &NumberOfBytesTransferred);
    v25 = 0;
    v8 = v24;
    if ( v24 )
    {
LABEL_75:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      return v8;
    }
    v26 = a5;
    if ( a5 )
      *a5 = 32;
    v27 = *a3;
    if ( (int)*a3 > 8 )
    {
      v37 = v27 - 9;
      if ( !v37 )
      {
        a3[2] = *((_DWORD *)Heap + 2);
        a3[3] = *((_DWORD *)Heap + 3);
        a3[4] = Heap[16];
        goto LABEL_75;
      }
      v38 = v37 - 1;
      if ( !v38 || (v39 = v38 - 2) == 0 )
      {
LABEL_44:
        v32 = *((_DWORD *)Heap + 2);
LABEL_45:
        a3[2] = v32;
        goto LABEL_75;
      }
      v40 = v39 - 1;
      if ( v40 )
      {
        if ( v40 == 1 )
          goto LABEL_58;
        if ( !Heap[8] )
        {
          *((_QWORD *)a3 + 1) = 0;
          *((_WORD *)a3 + 8) = 0;
          goto LABEL_75;
        }
        a3[2] = 1;
        a3[3] = Heap[10] != 0;
        if ( Heap[9] )
        {
          if ( *((_DWORD *)Heap + 3) <= v11 )
          {
            memcpy_0(a3 + 4, Heap + 16, *((unsigned int *)Heap + 3));
            *((_WORD *)a3 + ((unsigned __int64)*((unsigned int *)Heap + 3) >> 1) + 8) = 0;
          }
          else
          {
            v8 = 1359;
          }
          goto LABEL_75;
        }
        if ( a4 )
        {
          v33 = *((_DWORD *)Heap + 3) + 18;
          goto LABEL_49;
        }
LABEL_50:
        v8 = 122;
        goto LABEL_75;
      }
    }
    else if ( v27 != 8 )
    {
      v28 = v27 - 1;
      if ( !v28 )
      {
        *((_QWORD *)a3 + 1) = *((_QWORD *)Heap + 1);
        *((_QWORD *)a3 + 2) = *((_QWORD *)Heap + 2);
        a3[6] = *((_DWORD *)Heap + 6);
        a3[7] = *((_DWORD *)Heap + 7);
        goto LABEL_75;
      }
      v29 = v28 - 1;
      if ( !v29 )
        goto LABEL_58;
      v30 = v29 - 1;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( v31 )
        {
          if ( v31 == 2 )
          {
            *(_OWORD *)(a3 + 2) = *(_OWORD *)(Heap + 8);
            a3[6] = *((_DWORD *)Heap + 6);
            goto LABEL_75;
          }
          goto LABEL_44;
        }
LABEL_58:
        *(_OWORD *)(a3 + 2) = *(_OWORD *)(Heap + 8);
        goto LABEL_75;
      }
      a3[2] = Heap[8];
      if ( Heap[9] )
      {
        v34 = (const wchar_t *)(Heap + 16);
        v35 = (unsigned __int64)v42 >> 1;
        do
        {
          v36 = StringCchLengthW(v34, v35, pcchLength);
          if ( v36 < 0 )
          {
            v8 = v36 & 0x80007FFF | 0x401C0000;
            goto LABEL_75;
          }
          v25 += ++pcchLength[0];
          v34 += pcchLength[0];
        }
        while ( *v34 );
        if ( v35 < 2 )
          goto LABEL_50;
        memcpy_0(a3 + 3, Heap + 16, 2 * v25 + 2);
        if ( v26 )
          *v26 += 2 * v25 + 2;
        goto LABEL_75;
      }
      if ( a4 )
      {
        v33 = *((_DWORD *)Heap + 3) + 32;
LABEL_49:
        *a4 = v33;
        goto LABEL_50;
      }
      goto LABEL_50;
    }
    v32 = Heap[8];
    goto LABEL_45;
  }
  if ( v9 == 8 )
  {
    InBuffer = 8;
    goto LABEL_32;
  }
  v12 = v9 - 1;
  if ( !v12 )
  {
    InBuffer = 0;
    goto LABEL_32;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    InBuffer = 1;
    goto LABEL_32;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v11 = a2 - 32;
    InBuffer = 2;
    v42 = a2 - 32;
    v10 = a2;
    goto LABEL_32;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    InBuffer = 3;
    goto LABEL_32;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    InBuffer = 4;
    goto LABEL_32;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    InBuffer = 6;
    goto LABEL_32;
  }
  if ( v17 == 1 )
  {
    InBuffer = 7;
    goto LABEL_32;
  }
  return 87;
}

```

## disassembly

```asm
0x180007b7c  push    rbp
0x180007b7e  push    rbx
0x180007b7f  push    rsi
0x180007b80  push    rdi
0x180007b81  push    r12
0x180007b83  push    r13
0x180007b85  push    r14
0x180007b87  push    r15
0x180007b89  mov     rbp, rsp
0x180007b8c  sub     rsp, 58h
0x180007b90  mov     rdi, r8
0x180007b93  mov     r15, r9
0x180007b96  xor     r8d, r8d
0x180007b99  mov     r12, rcx
0x180007b9c  mov     [rbp+NumberOfBytesTransferred], r8d
0x180007ba0  mov     [rbp+pcchLength], r8
0x180007ba4  cmp     edx, 20h ; ' '
0x180007ba7  jnb     short loc_180007BB3
0x180007ba9  mov     esi, 57h ; 'W'
0x180007bae  jmp     loc_180007F10
0x180007bb3  mov     ecx, [rdi]
0x180007bb5  mov     r14d, 20h ; ' '
0x180007bbb  mov     [rbp+var_18], r8d
0x180007bbf  mov     r13d, r8d
0x180007bc2  lea     esi, [r14-12h]
0x180007bc6  cmp     ecx, 8
0x180007bc9  jg      loc_180007C50
0x180007bcf  jz      short loc_180007C47
0x180007bd1  sub     ecx, 1
0x180007bd4  jz      short loc_180007C41
0x180007bd6  sub     ecx, 1
0x180007bd9  jz      short loc_180007C38
0x180007bdb  sub     ecx, 1
0x180007bde  jz      short loc_180007C24
0x180007be0  sub     ecx, 1
0x180007be3  jz      short loc_180007C18
0x180007be5  sub     ecx, 1
0x180007be8  jz      short loc_180007C0C
0x180007bea  sub     ecx, 1
0x180007bed  jz      short loc_180007C00
0x180007bef  cmp     ecx, 1
0x180007bf2  jnz     short loc_180007BA9
0x180007bf4  mov     [rbp+InBuffer], 7
0x180007bfb  jmp     loc_180007CAE
0x180007c00  mov     [rbp+InBuffer], 6
0x180007c07  jmp     loc_180007CAE
0x180007c0c  mov     [rbp+InBuffer], 4
0x180007c13  jmp     loc_180007CAE
0x180007c18  mov     [rbp+InBuffer], 3
0x180007c1f  jmp     loc_180007CAE
0x180007c24  lea     r13d, [rdx-20h]
0x180007c28  mov     [rbp+InBuffer], 2
0x180007c2f  mov     [rbp+var_18], r13d
0x180007c33  mov     r14d, edx
0x180007c36  jmp     short loc_180007CAE
0x180007c38  mov     [rbp+InBuffer], 1
0x180007c3f  jmp     short loc_180007CAE
0x180007c41  mov     [rbp+InBuffer], r8d
0x180007c45  jmp     short loc_180007CAE
0x180007c47  mov     [rbp+InBuffer], 8
0x180007c4e  jmp     short loc_180007CAE
0x180007c50  sub     ecx, 9
0x180007c53  jz      short loc_180007CA7
0x180007c55  sub     ecx, 1
0x180007c58  jz      short loc_180007C9E
0x180007c5a  sub     ecx, 2
0x180007c5d  jz      short loc_180007C95
0x180007c5f  sub     ecx, 1
0x180007c62  jz      short loc_180007C8C
0x180007c64  sub     ecx, 1
0x180007c67  jz      short loc_180007C87
0x180007c69  cmp     ecx, 1
0x180007c6c  jnz     loc_180007BA9
0x180007c72  lea     r13d, [rdx-12h]
0x180007c76  mov     [rbp+InBuffer], 0Fh
0x180007c7d  mov     [rbp+var_18], r13d
0x180007c81  lea     r14d, [r13+20h]
0x180007c85  jmp     short loc_180007CAE
0x180007c87  mov     [rbp+InBuffer], esi
0x180007c8a  jmp     short loc_180007CAE
0x180007c8c  mov     [rbp+InBuffer], 0Dh
0x180007c93  jmp     short loc_180007CAE
0x180007c95  mov     [rbp+InBuffer], 0Ch
0x180007c9c  jmp     short loc_180007CAE
0x180007c9e  mov     [rbp+InBuffer], 0Ah
0x180007ca5  jmp     short loc_180007CAE
0x180007ca7  mov     [rbp+InBuffer], 9
0x180007cae  mov     rcx, gs:60h
0x180007cb7  xor     edx, edx; Flags
0x180007cb9  mov     r8d, r14d; Size
0x180007cbc  mov     rcx, [rcx+30h]; HeapHandle
0x180007cc0  call    cs:__imp_RtlAllocateHeap
0x180007cc7  nop     dword ptr [rax+rax+00h]
0x180007ccc  mov     rbx, rax
0x180007ccf  test    rax, rax
0x180007cd2  jz      loc_180007F10
0x180007cd8  lea     rax, [rbp+NumberOfBytesTransferred]
0x180007cdc  mov     r9d, 4; nInBufferSize
0x180007ce2  mov     [rsp+58h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180007ce7  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180007ceb  mov     [rsp+58h+var_30], r14d; DWORD
0x180007cf0  mov     edx, 2D1940h; dwIoControlCode
0x180007cf5  mov     rcx, r12; hFile
0x180007cf8  mov     [rsp+58h+var_38], rbx; LPVOID
0x180007cfd  call    IssueSynchronousDeviceIoControl
0x180007d02  xor     r12d, r12d
0x180007d05  mov     esi, eax
0x180007d07  test    eax, eax
0x180007d09  jnz     loc_180007EF2
0x180007d0f  mov     r14, [rbp+arg_20]
0x180007d13  test    r14, r14
0x180007d16  jz      short loc_180007D1F
0x180007d18  mov     dword ptr [r14], 20h ; ' '
0x180007d1f  mov     ecx, [rdi]
0x180007d21  cmp     ecx, 8
0x180007d24  jg      loc_180007E4F
0x180007d2a  jz      loc_180007E46
0x180007d30  sub     ecx, 1
0x180007d33  jz      loc_180007E25
0x180007d39  sub     ecx, 1
0x180007d3c  jz      loc_180007E17
0x180007d42  sub     ecx, 1
0x180007d45  jz      short loc_180007D78
0x180007d47  sub     ecx, 1
0x180007d4a  jz      loc_180007E17
0x180007d50  sub     ecx, 1
0x180007d53  jz      short loc_180007D6D
0x180007d55  cmp     ecx, 1
0x180007d58  jnz     short loc_180007D6D
0x180007d5a  movups  xmm0, xmmword ptr [rbx+8]
0x180007d5e  movups  xmmword ptr [rdi+8], xmm0
0x180007d62  mov     eax, [rbx+18h]
0x180007d65  mov     [rdi+18h], eax
0x180007d68  jmp     loc_180007EF2
0x180007d6d  mov     eax, [rbx+8]
0x180007d70  mov     [rdi+8], eax
0x180007d73  jmp     loc_180007EF2
0x180007d78  movzx   eax, byte ptr [rbx+8]
0x180007d7c  mov     [rdi+8], eax
0x180007d7f  cmp     [rbx+9], r12b
0x180007d83  jnz     short loc_180007D9D
0x180007d85  test    r15, r15
0x180007d88  jz      short loc_180007D93
0x180007d8a  mov     eax, [rbx+0Ch]
0x180007d8d  add     eax, 20h ; ' '
0x180007d90  mov     [r15], eax
0x180007d93  mov     esi, 7Ah ; 'z'
0x180007d98  jmp     loc_180007EF2
0x180007d9d  mov     r11d, [rbp+var_18]
0x180007da1  lea     r15, [rbx+10h]
0x180007da5  shr     r11, 1
0x180007da8  lea     r8, [rbp+pcchLength]; pcchLength
0x180007dac  mov     rdx, r11; cchMax
0x180007daf  mov     rcx, r15; psz
0x180007db2  call    StringCchLengthW
0x180007db7  xor     ecx, ecx
0x180007db9  test    eax, eax
0x180007dbb  js      short loc_180007E04
0x180007dbd  mov     rax, [rbp+pcchLength]
0x180007dc1  inc     rax
0x180007dc4  add     r12, rax
0x180007dc7  mov     [rbp+pcchLength], rax
0x180007dcb  lea     r15, [r15+rax*2]
0x180007dcf  cmp     [r15], cx
0x180007dd3  jnz     short loc_180007DA8
0x180007dd5  cmp     r11, 2
0x180007dd9  jb      short loc_180007D93
0x180007ddb  lea     r15, ds:2[r12*2]
0x180007de3  mov     r8, r15; Size
0x180007de6  lea     rcx, [rdi+0Ch]; void *
0x180007dea  lea     rdx, [rbx+10h]; Src
0x180007dee  call    memcpy_0
0x180007df3  test    r14, r14
0x180007df6  jz      loc_180007EF2
0x180007dfc  add     [r14], r15d
0x180007dff  jmp     loc_180007EF2
0x180007e04  mov     esi, eax
0x180007e06  and     esi, 0C01C7FFFh
0x180007e0c  or      esi, 401C0000h
0x180007e12  jmp     loc_180007EF2
0x180007e17  movups  xmm0, xmmword ptr [rbx+8]
0x180007e1b  movdqu  xmmword ptr [rdi+8], xmm0
0x180007e20  jmp     loc_180007EF2
0x180007e25  mov     rax, [rbx+8]
0x180007e29  mov     [rdi+8], rax
0x180007e2d  mov     rax, [rbx+10h]
0x180007e31  mov     [rdi+10h], rax
0x180007e35  mov     eax, [rbx+18h]
0x180007e38  mov     [rdi+18h], eax
0x180007e3b  mov     eax, [rbx+1Ch]
0x180007e3e  mov     [rdi+1Ch], eax
0x180007e41  jmp     loc_180007EF2
0x180007e46  movzx   eax, byte ptr [rbx+8]
0x180007e4a  jmp     loc_180007D70
0x180007e4f  sub     ecx, 9
0x180007e52  jz      loc_180007EDF
0x180007e58  sub     ecx, 1
0x180007e5b  jz      loc_180007D6D
0x180007e61  sub     ecx, 2
0x180007e64  jz      loc_180007D6D
0x180007e6a  sub     ecx, 1
0x180007e6d  jz      short loc_180007E46
0x180007e6f  cmp     ecx, 1
0x180007e72  jz      short loc_180007E17
0x180007e74  cmp     [rbx+8], r12b
0x180007e78  jz      short loc_180007ED4
0x180007e7a  mov     dword ptr [rdi+8], 1
0x180007e81  mov     eax, r12d
0x180007e84  cmp     [rbx+0Ah], r12b
0x180007e88  setnz   al
0x180007e8b  mov     [rdi+0Ch], eax
0x180007e8e  cmp     [rbx+9], r12b
0x180007e92  jnz     short loc_180007EA8
0x180007e94  test    r15, r15
0x180007e97  jz      loc_180007D93
0x180007e9d  mov     eax, [rbx+0Ch]
0x180007ea0  add     eax, 12h
0x180007ea3  jmp     loc_180007D90
0x180007ea8  cmp     [rbx+0Ch], r13d
0x180007eac  jbe     short loc_180007EB5
0x180007eae  mov     esi, 54Fh
0x180007eb3  jmp     short loc_180007EF2
0x180007eb5  mov     r8d, [rbx+0Ch]; Size
0x180007eb9  lea     rdx, [rbx+10h]; Src
0x180007ebd  lea     rcx, [rdi+10h]; void *
0x180007ec1  call    memcpy_0
0x180007ec6  mov     ecx, [rbx+0Ch]
0x180007ec9  shr     rcx, 1
0x180007ecc  mov     [rdi+rcx*2+10h], r12w
0x180007ed2  jmp     short loc_180007EF2
0x180007ed4  mov     [rdi+8], r12
0x180007ed8  mov     [rdi+10h], r12w
0x180007edd  jmp     short loc_180007EF2
0x180007edf  mov     eax, [rbx+8]
0x180007ee2  mov     [rdi+8], eax
0x180007ee5  mov     eax, [rbx+0Ch]
0x180007ee8  mov     [rdi+0Ch], eax
0x180007eeb  movzx   eax, byte ptr [rbx+10h]
0x180007eef  mov     [rdi+10h], eax
0x180007ef2  mov     rcx, gs:60h
0x180007efb  mov     r8, rbx; P
0x180007efe  xor     edx, edx; Flags
0x180007f00  mov     rcx, [rcx+30h]; HeapHandle
0x180007f04  call    cs:__imp_RtlFreeHeap
0x180007f0b  nop     dword ptr [rax+rax+00h]
0x180007f10  mov     eax, esi
0x180007f12  add     rsp, 58h
0x180007f16  pop     r15
0x180007f18  pop     r14
0x180007f1a  pop     r13
0x180007f1c  pop     r12
0x180007f1e  pop     rdi
0x180007f1f  pop     rsi
0x180007f20  pop     rbx
0x180007f21  pop     rbp
0x180007f22  retn
```
