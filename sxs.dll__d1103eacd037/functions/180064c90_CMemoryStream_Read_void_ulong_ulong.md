# CMemoryStream::Read(void *,ulong,ulong *)

- ea: `0x180064c90`
- end: `0x180064d19`
- name: `?Read@CMemoryStream@@UEAAJPEAXKPEAK@Z`
- size: `137`
- prototype: `int(CMemoryStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180064c90`

## import_xrefs

- `ntdll!RtlCopyMappedMemory` at `0x180064cd3`
- `ntdll!RtlCopyMappedMemory` at `0x180064cd3`
- `ntdll!RtlNtStatusToDosError` at `0x180064ce5`
- `ntdll!RtlNtStatusToDosError` at `0x180064ce5`

## pseudocode

```c
int __fastcall CMemoryStream::Read(CMemoryStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  char *v4; // rdi
  unsigned __int64 v6; // r10
  unsigned int v7; // ebx
  int result; // eax
  unsigned __int64 v10; // r10
  int v11; // eax

  v4 = (char *)*((_QWORD *)this + 2);
  v6 = *((_QWORD *)this + 4);
  v7 = a3;
  if ( (unsigned __int64)v4 > v6 )
    return -2147023537;
  v10 = v6 - (_QWORD)v4;
  if ( a3 > v10 )
    v7 = v10;
  v11 = RtlCopyMappedMemory(a2, v4, v7);
  if ( v11 >= 0 )
  {
    *((_QWORD *)this + 2) = &v4[v7];
    result = 0;
    *a4 = v7;
  }
  else
  {
    result = RtlNtStatusToDosError(v11);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180064c90  push    rbx
0x180064c92  push    rsi
0x180064c93  push    rdi
0x180064c94  push    r14
0x180064c96  push    r15
0x180064c98  sub     rsp, 20h
0x180064c9c  mov     rdi, [rcx+10h]
0x180064ca0  mov     r15, r9
0x180064ca3  mov     r10, [rcx+20h]
0x180064ca7  mov     r9, rdx
0x180064caa  mov     ebx, r8d
0x180064cad  mov     rsi, rcx
0x180064cb0  cmp     rdi, r10
0x180064cb3  jbe     short loc_180064CBC
0x180064cb5  mov     eax, 8007054Fh
0x180064cba  jmp     short loc_180064D0C
0x180064cbc  sub     r10, rdi
0x180064cbf  cmp     rbx, r10
0x180064cc2  jbe     short loc_180064CC7
0x180064cc4  mov     ebx, r10d
0x180064cc7  mov     r8d, ebx; Size
0x180064cca  mov     rdx, rdi; Source
0x180064ccd  mov     rcx, r9; Destination
0x180064cd0  mov     r14d, ebx
0x180064cd3  call    cs:__imp_RtlCopyMappedMemory
0x180064cda  nop     dword ptr [rax+rax+00h]
0x180064cdf  test    eax, eax
0x180064ce1  jns     short loc_180064CFF
0x180064ce3  mov     ecx, eax; Status
0x180064ce5  call    cs:__imp_RtlNtStatusToDosError
0x180064cec  nop     dword ptr [rax+rax+00h]
0x180064cf1  test    eax, eax
0x180064cf3  jle     short loc_180064D0C
0x180064cf5  movzx   eax, ax
0x180064cf8  or      eax, 80070000h
0x180064cfd  jmp     short loc_180064D0C
0x180064cff  lea     rax, [r14+rdi]
0x180064d03  mov     [rsi+10h], rax
0x180064d07  xor     eax, eax
0x180064d09  mov     [r15], ebx
0x180064d0c  add     rsp, 20h
0x180064d10  pop     r15
0x180064d12  pop     r14
0x180064d14  pop     rdi
0x180064d15  pop     rsi
0x180064d16  pop     rbx
0x180064d17  retn
```
