# CheckVolumeWriteProtection(ushort const *,int *)

- ea: `0x1800098bc`
- end: `0x180009974`
- name: `?CheckVolumeWriteProtection@@YAJPEBGPEAH@Z`
- size: `184`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009720`

## callees

- `0x1800098bc`
- `0x1800099ec`
- `0x180011000`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x18000991e`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000991e`
- `ntdll!NtClose` at `0x180009951`
- `ntdll!NtClose` at `0x180009951`

## pseudocode

```c
__int64 __fastcall CheckVolumeWriteProtection(const unsigned __int16 *a1, unsigned int *a2)
{
  NTSTATUS v3; // ebx
  HANDLE FileHandle; // [rsp+30h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-30h] BYREF
  __int128 FsInformation; // [rsp+48h] [rbp-20h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  FsInformation = 0;
  v3 = OpenVolume(a1, &FileHandle);
  if ( v3 >= 0 )
  {
    v3 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x10u, FileFsAttributeInformation);
    if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147483643 )
    {
      *a2 = ((unsigned int)FsInformation >> 19) & 1;
      v3 = 0;
    }
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800098bc  mov     [rsp+arg_10], rbx
0x1800098c1  push    rdi
0x1800098c2  sub     rsp, 60h
0x1800098c6  mov     rax, cs:__security_cookie
0x1800098cd  xor     rax, rsp
0x1800098d0  mov     [rsp+68h+var_10], rax
0x1800098d5  mov     rdi, rdx
0x1800098d8  mov     [rsp+68h+FileHandle], 0
0x1800098e1  xorps   xmm0, xmm0
0x1800098e4  lea     rdx, [rsp+68h+FileHandle]; void **
0x1800098e9  xorps   xmm1, xmm1
0x1800098ec  movups  xmmword ptr [rsp+68h+IoStatusBlock], xmm0
0x1800098f1  movups  [rsp+68h+FsInformation], xmm1
0x1800098f6  call    ?OpenVolume@@YAJPEBGPEAPEAX@Z; OpenVolume(ushort const *,void * *)
0x1800098fb  mov     ebx, eax
0x1800098fd  test    eax, eax
0x1800098ff  js      short loc_180009947
0x180009901  mov     rcx, [rsp+68h+FileHandle]; FileHandle
0x180009906  lea     r8, [rsp+68h+FsInformation]; FsInformation
0x18000990b  mov     r9d, 10h; Length
0x180009911  mov     [rsp+68h+FsInformationClass], 5; FsInformationClass
0x180009919  lea     rdx, [rsp+68h+IoStatusBlock]; IoStatusBlock
0x18000991e  call    cs:__imp_NtQueryVolumeInformationFile
0x180009924  mov     ecx, 80000000h
0x180009929  mov     ebx, eax
0x18000992b  add     eax, ecx
0x18000992d  test    ecx, eax
0x18000992f  jnz     short loc_180009939
0x180009931  cmp     ebx, 80000005h
0x180009937  jnz     short loc_180009947
0x180009939  mov     eax, dword ptr [rsp+68h+FsInformation]
0x18000993d  shr     eax, 13h
0x180009940  and     eax, 1
0x180009943  mov     [rdi], eax
0x180009945  xor     ebx, ebx
0x180009947  mov     rcx, [rsp+68h+FileHandle]; Handle
0x18000994c  test    rcx, rcx
0x18000994f  jz      short loc_180009957
0x180009951  call    cs:__imp_NtClose
0x180009957  mov     eax, ebx
0x180009959  mov     rcx, [rsp+68h+var_10]
0x18000995e  xor     rcx, rsp; StackCookie
0x180009961  call    __security_check_cookie
0x180009966  mov     rbx, [rsp+68h+arg_10]
0x18000996e  add     rsp, 60h
0x180009972  pop     rdi
0x180009973  retn
```
