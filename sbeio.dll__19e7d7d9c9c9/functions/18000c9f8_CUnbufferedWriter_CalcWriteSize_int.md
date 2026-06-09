# CUnbufferedWriter::CalcWriteSize(int)

- ea: `0x18000c9f8`
- end: `0x18000cb08`
- name: `?CalcWriteSize@CUnbufferedWriter@@AEAAJH@Z`
- size: `272`
- prototype: `__int64 __fastcall(CUnbufferedWriter *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cd9c`

## callees

- `0x1800011ec`
- `0x1800015f0`
- `0x180001f1c`
- `0x18000c9f8`

## import_xrefs

- `KERNEL32!GlobalMemoryStatus` at `0x18000ca4a`
- `KERNEL32!GlobalMemoryStatus` at `0x18000ca4a`

## pseudocode

```c
__int64 __fastcall CUnbufferedWriter::CalcWriteSize(CUnbufferedWriter *this, int a2)
{
  unsigned __int64 v3; // rcx
  SIZE_T dwAvailPhys; // rax
  void *v5; // rax
  unsigned int v6; // edi
  __int64 i; // r8
  __int64 v8; // rdx
  _MEMORYSTATUS Buffer; // [rsp+20h] [rbp-48h] BYREF

  memset(&Buffer, 0, sizeof(Buffer));
  if ( a2 )
  {
    *((_DWORD *)this + 10) = 0x20000;
    v3 = 4;
LABEL_5:
    *((_DWORD *)this + 11) = v3;
    goto LABEL_9;
  }
  Buffer.dwLength = 56;
  GlobalMemoryStatus(&Buffer);
  dwAvailPhys = Buffer.dwAvailPhys;
  if ( Buffer.dwAvailPhys <= 0x600000 )
  {
    *((_DWORD *)this + 10) = 0x100000;
    v3 = 6;
    goto LABEL_5;
  }
  v3 = 4;
  *((_DWORD *)this + 11) = 4;
  if ( dwAvailPhys > 0x2000000 )
    *((_DWORD *)this + 10) = 6291456;
  else
    *((_DWORD *)this + 10) = 0x400000;
LABEL_9:
  v5 = operator new[](saturated_mul(v3, 0x30u));
  *((_QWORD *)this + 10) = v5;
  if ( v5 )
  {
    v6 = 0;
    memset_0(v5, 0, 48LL * *((unsigned int *)this + 11));
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 11); *(_DWORD *)(*((_QWORD *)this + 10) + 8 * v8 + 44) = 0 )
    {
      v8 = 6 * i;
      i = (unsigned int)(i + 1);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c9f8  mov     [rsp+arg_8], rbx
0x18000c9fd  push    rdi
0x18000c9fe  sub     rsp, 60h
0x18000ca02  mov     rax, cs:__security_cookie
0x18000ca09  xor     rax, rsp
0x18000ca0c  mov     [rsp+68h+var_10], rax
0x18000ca11  xorps   xmm0, xmm0
0x18000ca14  xor     eax, eax
0x18000ca16  mov     [rsp+68h+Buffer.dwAvailVirtual], rax
0x18000ca1b  mov     rbx, rcx
0x18000ca1e  movups  xmmword ptr [rsp+68h+Buffer.dwLength], xmm0
0x18000ca23  movups  xmmword ptr [rsp+68h+Buffer.dwAvailPhys], xmm0
0x18000ca28  movups  xmmword ptr [rsp+68h+Buffer.dwAvailPageFile], xmm0
0x18000ca2d  test    edx, edx
0x18000ca2f  jz      short loc_18000CA3D
0x18000ca31  mov     dword ptr [rcx+28h], 20000h
0x18000ca38  lea     ecx, [rax+4]
0x18000ca3b  jmp     short loc_18000CA6B
0x18000ca3d  lea     rcx, [rsp+68h+Buffer]; lpBuffer
0x18000ca42  mov     [rsp+68h+Buffer.dwLength], 38h ; '8'
0x18000ca4a  call    cs:__imp_GlobalMemoryStatus
0x18000ca50  mov     rax, [rsp+68h+Buffer.dwAvailPhys]
0x18000ca55  mov     edx, 600000h
0x18000ca5a  cmp     rax, rdx
0x18000ca5d  ja      short loc_18000CA70
0x18000ca5f  mov     dword ptr [rbx+28h], 100000h
0x18000ca66  mov     ecx, 6
0x18000ca6b  mov     [rbx+2Ch], ecx
0x18000ca6e  jmp     short loc_18000CA8C
0x18000ca70  mov     ecx, 4
0x18000ca75  mov     [rbx+2Ch], ecx
0x18000ca78  cmp     rax, 2000000h
0x18000ca7e  ja      short loc_18000CA89
0x18000ca80  mov     dword ptr [rbx+28h], 400000h
0x18000ca87  jmp     short loc_18000CA8C
0x18000ca89  mov     [rbx+28h], edx
0x18000ca8c  mov     eax, 30h ; '0'
0x18000ca91  mul     rcx
0x18000ca94  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ca9b  cmovb   rax, rcx
0x18000ca9f  mov     rcx, rax; unsigned __int64
0x18000caa2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000caa7  mov     [rbx+50h], rax
0x18000caab  mov     rcx, rax; void *
0x18000caae  test    rax, rax
0x18000cab1  jnz     short loc_18000CABA
0x18000cab3  mov     edi, 8007000Eh
0x18000cab8  jmp     short loc_18000CAEE
0x18000caba  mov     eax, [rbx+2Ch]
0x18000cabd  xor     edx, edx; Val
0x18000cabf  xor     edi, edi
0x18000cac1  lea     r8, [rax+rax*2]
0x18000cac5  shl     r8, 4; Size
0x18000cac9  call    memset_0
0x18000cace  xor     r8d, r8d
0x18000cad1  cmp     [rbx+2Ch], edi
0x18000cad4  jbe     short loc_18000CAEE
0x18000cad6  mov     rcx, [rbx+50h]
0x18000cada  lea     rdx, [r8+r8*2]
0x18000cade  add     rdx, rdx
0x18000cae1  inc     r8d
0x18000cae4  mov     [rcx+rdx*8+2Ch], edi
0x18000cae8  cmp     r8d, [rbx+2Ch]
0x18000caec  jb      short loc_18000CAD6
0x18000caee  mov     eax, edi
0x18000caf0  mov     rcx, [rsp+68h+var_10]
0x18000caf5  xor     rcx, rsp; StackCookie
0x18000caf8  call    __security_check_cookie
0x18000cafd  mov     rbx, [rsp+68h+arg_8]
0x18000cb02  add     rsp, 60h
0x18000cb06  pop     rdi
0x18000cb07  retn
```
