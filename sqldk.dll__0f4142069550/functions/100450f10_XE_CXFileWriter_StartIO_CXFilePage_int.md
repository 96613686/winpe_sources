# XE_CXFileWriter::StartIO(CXFilePage *,int)

- ea: `0x100450f10`
- end: `0x1004510fb`
- name: `?StartIO@XE_CXFileWriter@@AEAAHPEAUCXFilePage@@H@Z`
- size: `491`
- prototype: `__int64 __fastcall(XE_CXFileWriter *__hidden this, struct CXFilePage *, int)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10044dfd0`
- `0x100451110`
- `0x100451560`
- `0x1005d74f0`
- `0x1005d78b0`
- `0x1005d7ea0`

## callees

- `0x100450af0`
- `0x100450f10`

## import_xrefs

- `KERNEL32!WriteFile` at `0x100451077`
- `KERNEL32!WriteFile` at `0x100451077`
- `KERNEL32!GetLastError` at `0x100451081`
- `KERNEL32!GetLastError` at `0x1004510a1`
- `KERNEL32!GetLastError` at `0x100451081`
- `KERNEL32!GetLastError` at `0x1004510a1`

## pseudocode

```c
__int64 __fastcall XE_CXFileWriter::StartIO(XE_CXFileWriter *this, struct CXFilePage *a2, int a3)
{
  int v6; // ecx
  int v7; // r10d
  __int64 v8; // r10
  unsigned int v9; // edx
  char *v10; // r8
  __int64 v11; // r9
  char v12; // al
  DWORD v13; // r14d
  const void *v14; // rdx
  __int64 *v15; // rdi
  __int64 v16; // rsi
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 208) )
    return 0;
  *(_DWORD *)(*(_QWORD *)a2 + 8LL) = *((_DWORD *)a2 + 18) - 16;
  if ( *(_DWORD *)(*(_QWORD *)a2 + 8LL) )
  {
    v6 = *((_DWORD *)this + 5);
    if ( (v6 & 1) != 0 || *((_DWORD *)a2 + 18) && !a3 )
    {
      v8 = *((unsigned int *)a2 + 18);
      if ( a3 )
        *((_QWORD *)this + 102) += v8;
    }
    else
    {
      if ( !(unsigned int)XE_CXFileWriter::CompressPage(this, a2) )
        return 0;
      *((_QWORD *)this + 102) += *((unsigned int *)a2 + 18);
      v7 = *(_DWORD *)(*(_QWORD *)a2 + 12LL);
      if ( v7 )
      {
        v6 = *((_DWORD *)this + 5);
        LODWORD(v8) = v7 + 16;
      }
      else
      {
        LODWORD(v8) = *((_DWORD *)a2 + 18);
        v6 = *((_DWORD *)this + 5);
      }
      *((_QWORD *)this + 101) += (unsigned int)v8;
    }
    if ( (v6 & 2) == 0 )
    {
      v9 = -1;
      v10 = (char *)(*((_QWORD *)a2 + 2) + 8LL);
      v11 = (unsigned int)v8 - 16LL;
      if ( (unsigned int)v8 != 16 )
      {
        do
        {
          v12 = *v10++;
          v9 = *((_DWORD *)&crctab + (unsigned __int8)(v12 ^ v9)) ^ (v9 >> 8);
          --v11;
        }
        while ( v11 );
      }
      **(_DWORD **)a2 = v9;
    }
    v13 = v8 + *((_DWORD *)this + 4) - 1 - (unsigned int)(v8 + *((_DWORD *)this + 4) - 1) % *((_DWORD *)this + 4);
    if ( a3 )
      *((_QWORD *)this + 103) += *((_DWORD *)this + 4)
                               - 1
                               - (unsigned int)(v8 + *((_DWORD *)this + 4) - 1) % *((_DWORD *)this + 4);
    NumberOfBytesWritten = 0;
    *(_OWORD *)((char *)a2 + 40) = 0;
    *(_OWORD *)((char *)a2 + 56) = 0;
    v14 = (const void *)*((_QWORD *)a2 + 2);
    *((_QWORD *)a2 + 7) = *((_QWORD *)this + 72);
    *((_QWORD *)a2 + 8) = *((_QWORD *)this + 84);
    if ( WriteFile(*((HANDLE *)this + 73), v14, v13, &NumberOfBytesWritten, (LPOVERLAPPED)((char *)a2 + 40)) )
    {
      ++*((_QWORD *)this + 97);
    }
    else if ( GetLastError() != 997 )
    {
      v15 = (__int64 *)*((_QWORD *)this + 105);
      v16 = *v15;
      LastError = GetLastError();
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, char *))(v16 + 64))(
        v15,
        LastError,
        *((_QWORD *)this + 72),
        v13,
        (char *)this + 32);
      return 0;
    }
    if ( a3 )
      *((_QWORD *)this + 72) += v13;
  }
  return 1;
}

```

## disassembly

```asm
0x100450f10  mov     [rsp+arg_10], rbx
0x100450f15  push    rbp
0x100450f16  push    rdi
0x100450f17  push    r14
0x100450f19  sub     rsp, 30h
0x100450f1d  cmp     dword ptr [rcx+340h], 0
0x100450f24  mov     edi, r8d
0x100450f27  mov     rbx, rdx
0x100450f2a  mov     rbp, rcx
0x100450f2d  jnz     loc_1004510C3
0x100450f33  mov     rax, [rdx]
0x100450f36  mov     r9d, [rdx+48h]
0x100450f3a  sub     r9d, 10h
0x100450f3e  mov     [rax+8], r9d
0x100450f42  mov     rax, [rdx]
0x100450f45  cmp     dword ptr [rax+8], 0
0x100450f49  jz      loc_1004510E8
0x100450f4f  mov     ecx, [rcx+14h]
0x100450f52  test    cl, 1
0x100450f55  jnz     short loc_100450FAE
0x100450f57  cmp     dword ptr [rdx+48h], 0
0x100450f5b  jz      short loc_100450F62
0x100450f5d  test    r8d, r8d
0x100450f60  jz      short loc_100450FAE
0x100450f62  mov     rcx, rbp; this
0x100450f65  call    ?CompressPage@XE_CXFileWriter@@AEAAHPEAUCXFilePage@@@Z; XE_CXFileWriter::CompressPage(CXFilePage *)
0x100450f6a  test    eax, eax
0x100450f6c  jz      loc_1004510C3
0x100450f72  mov     eax, [rbx+48h]
0x100450f75  add     [rbp+330h], rax
0x100450f7c  mov     rax, [rbx]
0x100450f7f  mov     r10d, [rax+0Ch]
0x100450f83  test    r10d, r10d
0x100450f86  jz      short loc_100450F9B
0x100450f88  mov     ecx, [rbp+14h]
0x100450f8b  add     r10d, 10h
0x100450f8f  mov     eax, r10d
0x100450f92  add     [rbp+328h], rax
0x100450f99  jmp     short loc_100450FBD
0x100450f9b  mov     r10d, [rbx+48h]
0x100450f9f  mov     ecx, [rbp+14h]
0x100450fa2  mov     eax, r10d
0x100450fa5  add     [rbp+328h], rax
0x100450fac  jmp     short loc_100450FBD
0x100450fae  mov     r10d, [rdx+48h]
0x100450fb2  test    edi, edi
0x100450fb4  jz      short loc_100450FBD
0x100450fb6  add     [rbp+330h], r10
0x100450fbd  test    cl, 2
0x100450fc0  jnz     short loc_100451002
0x100450fc2  mov     r8, [rbx+10h]
0x100450fc6  mov     edx, 0FFFFFFFFh
0x100450fcb  add     r8, 8
0x100450fcf  mov     r9d, r10d
0x100450fd2  sub     r9, 10h
0x100450fd6  jz      short loc_100450FFD
0x100450fd8  lea     r11, ?crctab@@3QBKB; ulong const near * const crctab
0x100450fdf  nop
0x100450fe0  movzx   eax, byte ptr [r8]
0x100450fe4  lea     r8, [r8+1]
0x100450fe8  mov     ecx, edx
0x100450fea  shr     edx, 8
0x100450fed  xor     rcx, rax
0x100450ff0  movzx   eax, cl
0x100450ff3  xor     edx, [r11+rax*4]
0x100450ff7  sub     r9, 1
0x100450ffb  jnz     short loc_100450FE0
0x100450ffd  mov     rax, [rbx]
0x100451000  mov     [rax], edx
0x100451002  mov     ecx, [rbp+10h]
0x100451005  xor     edx, edx
0x100451007  lea     r14d, [rcx-1]
0x10045100b  add     r14d, r10d
0x10045100e  mov     eax, r14d
0x100451011  div     ecx
0x100451013  sub     r14d, edx
0x100451016  test    edi, edi
0x100451018  jz      short loc_100451027
0x10045101a  mov     eax, r14d
0x10045101d  sub     eax, r10d
0x100451020  add     [rbp+338h], rax
0x100451027  lea     rcx, [rbx+28h]
0x10045102b  mov     [rsp+48h+NumberOfBytesWritten], 0
0x100451033  xorps   xmm0, xmm0
0x100451036  mov     [rsp+48h+lpOverlapped], rcx; lpOverlapped
0x10045103b  movups  xmmword ptr [rcx], xmm0
0x10045103e  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100451043  mov     r8d, r14d; nNumberOfBytesToWrite
0x100451046  movups  xmmword ptr [rcx+10h], xmm0
0x10045104a  mov     eax, [rbp+240h]
0x100451050  mov     rdx, [rbx+10h]; lpBuffer
0x100451054  mov     [rbx+38h], eax
0x100451057  mov     rax, [rbp+240h]
0x10045105e  shr     rax, 20h
0x100451062  mov     [rbx+3Ch], eax
0x100451065  mov     rax, [rbp+2A0h]
0x10045106c  mov     [rbx+40h], rax
0x100451070  mov     rcx, [rbp+248h]; hFile
0x100451077  call    cs:__imp_WriteFile
0x10045107d  test    eax, eax
0x10045107f  jnz     short loc_1004510D3
0x100451081  call    cs:__imp_GetLastError
0x100451087  cmp     eax, 3E5h
0x10045108c  jz      short loc_1004510DA
0x10045108e  mov     rdi, [rbp+348h]
0x100451095  lea     rbx, [rbp+20h]
0x100451099  mov     [rsp+48h+arg_8], rsi
0x10045109e  mov     rsi, [rdi]
0x1004510a1  call    cs:__imp_GetLastError
0x1004510a7  mov     r8, [rbp+240h]
0x1004510ae  mov     r9d, r14d
0x1004510b1  mov     edx, eax
0x1004510b3  mov     [rsp+48h+lpOverlapped], rbx
0x1004510b8  mov     rcx, rdi
0x1004510bb  call    qword ptr [rsi+40h]
0x1004510be  mov     rsi, [rsp+48h+arg_8]
0x1004510c3  xor     eax, eax
0x1004510c5  mov     rbx, [rsp+48h+arg_10]
0x1004510ca  add     rsp, 30h
0x1004510ce  pop     r14
0x1004510d0  pop     rdi
0x1004510d1  pop     rbp
0x1004510d2  retn
0x1004510d3  inc     qword ptr [rbp+308h]
0x1004510da  test    edi, edi
0x1004510dc  jz      short loc_1004510E8
0x1004510de  mov     eax, r14d
0x1004510e1  add     [rbp+240h], rax
0x1004510e8  mov     rbx, [rsp+48h+arg_10]
0x1004510ed  mov     eax, 1
0x1004510f2  add     rsp, 30h
0x1004510f6  pop     r14
0x1004510f8  pop     rdi
0x1004510f9  pop     rbp
0x1004510fa  retn
```
