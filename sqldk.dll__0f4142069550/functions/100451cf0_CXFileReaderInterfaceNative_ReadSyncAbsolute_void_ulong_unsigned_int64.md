# CXFileReaderInterfaceNative::ReadSyncAbsolute(void *,ulong,unsigned __int64)

- ea: `0x100451cf0`
- end: `0x100451db1`
- name: `?ReadSyncAbsolute@CXFileReaderInterfaceNative@@UEAAHPEAXK_K@Z`
- size: `193`
- prototype: `__int64 __fastcall(CXFileReaderInterfaceNative *__hidden this, void *, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x100451cf0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x100451d61`
- `KERNEL32!GetOverlappedResult` at `0x100451d61`
- `KERNEL32!ReadFile` at `0x100451d33`
- `KERNEL32!ReadFile` at `0x100451d33`
- `KERNEL32!GetLastError` at `0x100451d3d`
- `KERNEL32!GetLastError` at `0x100451d6b`
- `KERNEL32!GetLastError` at `0x100451d3d`
- `KERNEL32!GetLastError` at `0x100451d6b`

## pseudocode

```c
__int64 __fastcall CXFileReaderInterfaceNative::ReadSyncAbsolute(
        CXFileReaderInterfaceNative *this,
        void *a2,
        DWORD a3,
        void *a4)
{
  void *v5; // rcx
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+8h] BYREF

  Overlapped.Pointer = a4;
  v5 = (void *)*((_QWORD *)this + 74);
  NumberOfBytesTransferred = 0;
  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  Overlapped.hEvent = 0;
  if ( ReadFile(v5, a2, a3, &NumberOfBytesTransferred, &Overlapped)
    || GetLastError() == 997 && GetOverlappedResult(*((HANDLE *)this + 74), &Overlapped, &NumberOfBytesTransferred, 1) )
  {
    if ( NumberOfBytesTransferred == a3 )
    {
      return 1;
    }
    else
    {
      *((_DWORD *)this + 152) = 13;
      return 0;
    }
  }
  else
  {
    *((_DWORD *)this + 152) = GetLastError();
    return 0;
  }
}

```

## disassembly

```asm
0x100451cf0  mov     r11, rsp
0x100451cf3  mov     [r11+10h], rbx
0x100451cf7  push    rdi
0x100451cf8  sub     rsp, 50h
0x100451cfc  xor     eax, eax
0x100451cfe  mov     [r11-18h], r9d
0x100451d02  shr     r9, 20h
0x100451d06  mov     rbx, rcx
0x100451d09  mov     rcx, [rcx+250h]; hFile
0x100451d10  mov     edi, r8d
0x100451d13  mov     [rsp+58h+NumberOfBytesTransferred], eax
0x100451d17  mov     [r11-28h], rax
0x100451d1b  mov     [r11-20h], rax
0x100451d1f  mov     [r11-10h], rax
0x100451d23  lea     rax, [r11-28h]
0x100451d27  mov     [r11-14h], r9d
0x100451d2b  lea     r9, [r11+8]; lpNumberOfBytesRead
0x100451d2f  mov     [r11-38h], rax
0x100451d33  call    cs:__imp_ReadFile
0x100451d39  test    eax, eax
0x100451d3b  jnz     short loc_100451D84
0x100451d3d  call    cs:__imp_GetLastError
0x100451d43  cmp     eax, 3E5h
0x100451d48  jnz     short loc_100451D6B
0x100451d4a  mov     rcx, [rbx+250h]; hFile
0x100451d51  lea     r8, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x100451d56  mov     r9d, 1; bWait
0x100451d5c  lea     rdx, [rsp+58h+Overlapped]; lpOverlapped
0x100451d61  call    cs:__imp_GetOverlappedResult
0x100451d67  test    eax, eax
0x100451d69  jnz     short loc_100451D84
0x100451d6b  call    cs:__imp_GetLastError
0x100451d71  mov     [rbx+260h], eax
0x100451d77  xor     eax, eax
0x100451d79  mov     rbx, [rsp+58h+arg_8]
0x100451d7e  add     rsp, 50h
0x100451d82  pop     rdi
0x100451d83  retn
0x100451d84  cmp     [rsp+58h+NumberOfBytesTransferred], edi
0x100451d88  jz      short loc_100451DA1
0x100451d8a  mov     dword ptr [rbx+260h], 0Dh
0x100451d94  xor     eax, eax
0x100451d96  mov     rbx, [rsp+58h+arg_8]
0x100451d9b  add     rsp, 50h
0x100451d9f  pop     rdi
0x100451da0  retn
0x100451da1  mov     rbx, [rsp+58h+arg_8]
0x100451da6  mov     eax, 1
0x100451dab  add     rsp, 50h
0x100451daf  pop     rdi
0x100451db0  retn
```
