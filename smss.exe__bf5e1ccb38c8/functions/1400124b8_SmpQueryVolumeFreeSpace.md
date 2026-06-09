# SmpQueryVolumeFreeSpace

- ea: `0x1400124b8`
- end: `0x140012600`
- name: `SmpQueryVolumeFreeSpace`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011d24`

## callees

- `0x1400124b8`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140012593`
- `ntdll!NtOpenFile` at `0x140012593`
- `ntdll!NtClose` at `0x1400125bd`
- `ntdll!NtClose` at `0x1400125bd`
- `ntdll!NtQueryVolumeInformationFile` at `0x1400125b1`
- `ntdll!NtQueryVolumeInformationFile` at `0x1400125b1`

## pseudocode

```c
NTSTATUS __fastcall SmpQueryVolumeFreeSpace(__m128i *a1, _QWORD *a2)
{
  __int16 *v3; // rcx
  int v4; // edx
  __int16 v5; // ax
  NTSTATUS result; // eax
  NTSTATUS v7; // ebx
  void *FileHandle; // [rsp+30h] [rbp-29h] BYREF
  __m128i v9; // [rsp+38h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-11h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp+1Fh] BYREF
  __int128 FsInformation; // [rsp+88h] [rbp+2Fh] BYREF
  __int64 v13; // [rsp+98h] [rbp+3Fh]

  FileHandle = 0;
  v13 = 0;
  FsInformation = 0;
  v9 = *a1;
  v3 = (__int16 *)v9.m128i_i64[1];
  v4 = (unsigned __int16)_mm_cvtsi128_si32(v9);
  v9.m128i_i16[0] = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  while ( v4 )
  {
    v5 = *v3++;
    if ( v5 == 58 && *v3 == 92 )
    {
      LOWORD(v3) = (_WORD)v3 + 2;
      break;
    }
    v4 -= 2;
  }
  v9.m128i_i16[0] = (_WORD)v3 - v9.m128i_i16[4];
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v9;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x21u);
  if ( result >= 0 )
  {
    v7 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
    NtClose(FileHandle);
    if ( v7 >= 0 )
    {
      result = 0;
      *a2 = *((_QWORD *)&FsInformation + 1) * (unsigned int)v13 * (unsigned __int64)HIDWORD(v13);
    }
    else
    {
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400124b8  mov     [rsp-8+arg_10], rbx
0x1400124bd  mov     [rsp-8+arg_18], rdi
0x1400124c2  push    rbp
0x1400124c3  lea     rbp, [rsp-57h]
0x1400124c8  sub     rsp, 0B0h
0x1400124cf  mov     rax, cs:__security_cookie
0x1400124d6  xor     rax, rsp
0x1400124d9  mov     [rbp+57h+var_10], rax
0x1400124dd  xorps   xmm0, xmm0
0x1400124e0  mov     [rbp+57h+FileHandle], 0
0x1400124e8  xor     eax, eax
0x1400124ea  xorps   xmm1, xmm1
0x1400124ed  mov     [rbp+57h+var_18], rax
0x1400124f1  mov     rdi, rdx
0x1400124f4  movups  [rbp+57h+FsInformation], xmm1
0x1400124f8  movups  xmm1, xmmword ptr [rcx]
0x1400124fb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400124ff  movd    eax, xmm1
0x140012503  movups  [rbp+57h+var_78], xmm1
0x140012507  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x14001250b  movzx   edx, ax
0x14001250e  xor     eax, eax
0x140012510  mov     word ptr [rbp+57h+var_78], ax
0x140012514  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140012518  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001251c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140012520  mov     r8, rcx
0x140012523  test    edx, edx
0x140012525  jz      short loc_140012543
0x140012527  movzx   eax, word ptr [rcx]
0x14001252a  lea     rcx, [rcx+2]
0x14001252e  cmp     ax, 3Ah ; ':'
0x140012532  jnz     short loc_14001253A
0x140012534  cmp     word ptr [rcx], 5Ch ; '\'
0x140012538  jz      short loc_14001253F
0x14001253a  add     edx, 0FFFFFFFEh
0x14001253d  jmp     short loc_140012520
0x14001253f  add     rcx, 2
0x140012543  sub     cx, word ptr [rbp+57h+var_78+8]
0x140012547  lea     rax, [rbp+57h+var_78]
0x14001254b  mov     word ptr [rbp+57h+var_78], cx
0x14001254f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140012553  xorps   xmm0, xmm0
0x140012556  mov     [rsp+0B0h+OpenOptions], 21h ; '!'; OpenOptions
0x14001255e  mov     ebx, 3
0x140012563  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001256a  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001256e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140012576  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001257a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140012581  mov     edx, 100001h; DesiredAccess
0x140012586  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001258a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001258f  mov     [rsp+0B0h+ShareAccess], ebx; ShareAccess
0x140012593  call    cs:__imp_NtOpenFile
0x140012599  test    eax, eax
0x14001259b  js      short loc_1400125DF
0x14001259d  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400125a1  lea     r9d, [rbx+15h]; Length
0x1400125a5  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x1400125a9  mov     [rsp+0B0h+ShareAccess], ebx; FsInformationClass
0x1400125ad  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400125b1  call    cs:__imp_NtQueryVolumeInformationFile
0x1400125b7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400125bb  mov     ebx, eax
0x1400125bd  call    cs:__imp_NtClose
0x1400125c3  test    ebx, ebx
0x1400125c5  jns     short loc_1400125CB
0x1400125c7  mov     eax, ebx
0x1400125c9  jmp     short loc_1400125DF
0x1400125cb  mov     eax, dword ptr [rbp+57h+var_18]
0x1400125ce  mov     ecx, dword ptr [rbp+57h+var_18+4]
0x1400125d1  imul    rcx, rax
0x1400125d5  imul    rcx, qword ptr [rbp+57h+FsInformation+8]
0x1400125da  xor     eax, eax
0x1400125dc  mov     [rdi], rcx
0x1400125df  mov     rcx, [rbp+57h+var_10]
0x1400125e3  xor     rcx, rsp; StackCookie
0x1400125e6  call    __security_check_cookie
0x1400125eb  lea     r11, [rsp+0B0h+var_s0]
0x1400125f3  mov     rbx, [r11+20h]
0x1400125f7  mov     rdi, [r11+28h]
0x1400125fb  mov     rsp, r11
0x1400125fe  pop     rbp
0x1400125ff  retn
```
