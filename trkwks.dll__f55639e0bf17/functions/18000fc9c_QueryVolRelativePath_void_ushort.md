# QueryVolRelativePath(void *,ushort *)

- ea: `0x18000fc9c`
- end: `0x18000fd42`
- name: `?QueryVolRelativePath@@YAJPEAXPEAG@Z`
- size: `166`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005660`

## callees

- `0x18000b4a0`
- `0x18000fc9c`
- `0x180011000`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18000fcde`
- `ntdll!NtQueryInformationFile` at `0x18000fcde`

## pseudocode

```c
__int64 __fastcall QueryVolRelativePath(void *a1, unsigned __int16 *a2)
{
  NTSTATUS v3; // ebx
  unsigned __int64 v4; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-238h] BYREF
  unsigned int FileInformation; // [rsp+40h] [rbp-228h] BYREF
  unsigned __int16 v8[262]; // [rsp+44h] [rbp-224h] BYREF

  IoStatusBlock = 0;
  v3 = NtQueryInformationFile(a1, &IoStatusBlock, &FileInformation, 0x20Cu, FileNameInformation);
  if ( v3 >= 0 )
  {
    v4 = 520;
    if ( FileInformation <= 0x208 )
      v4 = FileInformation;
    v8[v4 >> 1] = 0;
    if ( (int)StringCchCopyW(a2, 0x104u, v8) < 0 )
      return (unsigned int)-2147483643;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000fc9c  mov     [rsp+arg_10], rbx
0x18000fca1  push    rdi
0x18000fca2  sub     rsp, 260h
0x18000fca9  mov     rax, cs:__security_cookie
0x18000fcb0  xor     rax, rsp
0x18000fcb3  mov     [rsp+268h+var_18], rax
0x18000fcbb  mov     rdi, rdx
0x18000fcbe  mov     [rsp+268h+FileInformationClass], 9; FileInformationClass
0x18000fcc6  xorps   xmm0, xmm0
0x18000fcc9  lea     rdx, [rsp+268h+IoStatusBlock]; IoStatusBlock
0x18000fcce  mov     r9d, 20Ch; Length
0x18000fcd4  lea     r8, [rsp+268h+FileInformation]; FileInformation
0x18000fcd9  movups  xmmword ptr [rsp+268h+IoStatusBlock], xmm0
0x18000fcde  call    cs:__imp_NtQueryInformationFile
0x18000fce4  mov     ebx, eax
0x18000fce6  test    eax, eax
0x18000fce8  js      short loc_18000FD1F
0x18000fcea  mov     ecx, 208h
0x18000fcef  cmp     [rsp+268h+FileInformation], ecx
0x18000fcf3  ja      short loc_18000FCF9
0x18000fcf5  mov     ecx, [rsp+268h+FileInformation]
0x18000fcf9  shr     rcx, 1
0x18000fcfc  lea     r8, [rsp+268h+var_224]; unsigned __int16 *
0x18000fd01  xor     eax, eax
0x18000fd03  mov     edx, 104h; unsigned __int64
0x18000fd08  mov     [rsp+rcx*2+268h+var_224], ax
0x18000fd0d  mov     rcx, rdi; unsigned __int16 *
0x18000fd10  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fd15  test    eax, eax
0x18000fd17  mov     ecx, 80000005h
0x18000fd1c  cmovs   ebx, ecx
0x18000fd1f  mov     eax, ebx
0x18000fd21  mov     rcx, [rsp+268h+var_18]
0x18000fd29  xor     rcx, rsp; StackCookie
0x18000fd2c  call    __security_check_cookie
0x18000fd31  mov     rbx, [rsp+268h+arg_10]
0x18000fd39  add     rsp, 260h
0x18000fd40  pop     rdi
0x18000fd41  retn
```
