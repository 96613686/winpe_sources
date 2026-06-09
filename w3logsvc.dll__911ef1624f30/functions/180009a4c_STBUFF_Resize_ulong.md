# STBUFF::Resize(ulong)

- ea: `0x180009a4c`
- end: `0x180009add`
- name: `?Resize@STBUFF@@QEAAJK@Z`
- size: `145`
- prototype: `__int64 __fastcall(const void **this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c84`
- `0x18000c1b4`

## callees

- `0x180009a4c`
- `0x18000e96e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009ab4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009ab4`

## pseudocode

```c
__int64 __fastcall STBUFF::Resize(const void **this, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 v4; // rsi
  HLOCAL v5; // rax
  HLOCAL v6; // rbp
  char *v7; // rcx

  v2 = 0;
  if ( a2 >= *((_DWORD *)this + 5) )
  {
    v4 = *((unsigned int *)this + 6);
    if ( a2 > (unsigned int)v4 )
      return (unsigned int)-2147024882;
    if ( (a2 & 0x3F) != 0 )
      a2 = (a2 & 0xFFFFFFC0) + 64;
    if ( a2 <= (unsigned int)v4 )
      v4 = a2;
    v5 = LocalAlloc(0x40u, (unsigned int)(v4 + 2));
    v6 = v5;
    if ( v5 )
    {
      if ( *((_DWORD *)this + 4) )
        memcpy_0(v5, this[1], *((unsigned int *)this + 4));
      v7 = (char *)this[1];
      if ( v7 != (char *)this + 28 )
        LocalFree(v7);
      this[1] = v6;
      *((_DWORD *)this + 5) = v4;
      *((_BYTE *)v6 + v4) = 0;
      *((_BYTE *)this[1] + (unsigned int)(*((_DWORD *)this + 5) + 1)) = 0;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180009a4c  push    rbx
0x180009a4e  push    rbp
0x180009a4f  push    rsi
0x180009a50  push    rdi
0x180009a51  sub     rsp, 28h
0x180009a55  xor     edi, edi
0x180009a57  mov     rbx, rcx
0x180009a5a  cmp     edx, [rcx+14h]
0x180009a5d  jb      short loc_180009AD2
0x180009a5f  mov     esi, [rcx+18h]
0x180009a62  cmp     edx, esi
0x180009a64  jbe     short loc_180009A6D
0x180009a66  mov     edi, 8007000Eh
0x180009a6b  jmp     short loc_180009AD2
0x180009a6d  mov     ecx, 40h ; '@'; uFlags
0x180009a72  test    dl, 3Fh
0x180009a75  jz      short loc_180009A7C
0x180009a77  and     edx, 0FFFFFFC0h
0x180009a7a  add     edx, ecx
0x180009a7c  cmp     edx, esi
0x180009a7e  cmovbe  esi, edx
0x180009a81  lea     edx, [rsi+2]; uBytes
0x180009a84  call    cs:__imp_LocalAlloc
0x180009a8a  mov     rbp, rax
0x180009a8d  test    rax, rax
0x180009a90  jz      short loc_180009A66
0x180009a92  cmp     [rbx+10h], edi
0x180009a95  jz      short loc_180009AA7
0x180009a97  mov     r8d, [rbx+10h]; Size
0x180009a9b  mov     rcx, rax; void *
0x180009a9e  mov     rdx, [rbx+8]; Src
0x180009aa2  call    memcpy_0
0x180009aa7  mov     rcx, [rbx+8]; hMem
0x180009aab  lea     rax, [rbx+1Ch]
0x180009aaf  cmp     rcx, rax
0x180009ab2  jz      short loc_180009ABA
0x180009ab4  call    cs:__imp_LocalFree
0x180009aba  mov     [rbx+8], rbp
0x180009abe  mov     [rbx+14h], esi
0x180009ac1  mov     [rsi+rbp], dil
0x180009ac5  mov     edx, [rbx+14h]
0x180009ac8  mov     rcx, [rbx+8]
0x180009acc  inc     edx
0x180009ace  mov     [rdx+rcx], dil
0x180009ad2  mov     eax, edi
0x180009ad4  add     rsp, 28h
0x180009ad8  pop     rdi
0x180009ad9  pop     rsi
0x180009ada  pop     rbp
0x180009adb  pop     rbx
0x180009adc  retn
```
