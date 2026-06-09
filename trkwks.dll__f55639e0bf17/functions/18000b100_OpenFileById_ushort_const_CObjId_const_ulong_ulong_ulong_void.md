# OpenFileById(ushort const *,CObjId const &,ulong,ulong,ulong,void * *)

- ea: `0x18000b100`
- end: `0x18000b3e2`
- name: `?OpenFileById@@YAJPEBGAEBUCObjId@@KKKPEAPEAX@Z`
- size: `738`
- prototype: `NTSTATUS __fastcall(WCHAR *, const struct CObjId *, ACCESS_MASK, __int64, unsigned int, void **FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f984`

## callees

- `0x18000b100`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000b37c`
- `ntdll!NtCreateFile` at `0x18000b37c`
- `ntdll!RtlFreeHeap` at `0x18000b3a2`
- `ntdll!RtlFreeHeap` at `0x18000b3a2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000b2dc`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000b2dc`

## pseudocode

```c
NTSTATUS __fastcall OpenFileById(
        WCHAR *a1,
        const struct CObjId *a2,
        ACCESS_MASK a3,
        __int64 a4,
        unsigned int a5,
        void **FileHandle)
{
  WCHAR *v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // r11d
  _WORD *v18; // r9
  const unsigned __int16 *v19; // r10
  WCHAR *i; // rax
  int v21; // r9d
  _WORD *v22; // rcx
  const wchar_t *v23; // r8
  NTSTATUS result; // eax
  PWSTR Buffer; // rbx
  NTSTATUS v26; // edi
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-288h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-278h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-248h] BYREF
  WCHAR DosPathName[261]; // [rsp+B0h] [rbp-238h] BYREF
  _BYTE v31[6]; // [rsp+2BAh] [rbp-2Eh] BYREF

  memset_0(DosPathName, 0, sizeof(DosPathName));
  v9 = DosPathName;
  v10 = 261;
  v11 = 2147483646;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v12 = 261;
  v13 = 2147483646;
  IoStatusBlock = 0;
  NtPathName = 0;
  while ( v13 && *a1 )
  {
    *v9++ = *a1++;
    --v13;
    if ( !--v12 )
      return -2147483643;
  }
  v14 = DosPathName;
  *v9 = 0;
  v15 = 261;
  while ( *v14 )
  {
    ++v14;
    if ( !--v15 )
      return -2147483643;
  }
  v16 = 2147483646;
  v17 = 0;
  v18 = &v31[-2 * v15];
  v19 = L"\\";
  while ( v16 && *v19 )
  {
    *v18++ = *v19++;
    --v16;
    if ( !--v15 )
    {
      --v18;
      v17 = -2147024774;
      break;
    }
  }
  *v18 = 0;
  if ( v17 < 0 )
    return -2147483643;
  for ( i = DosPathName; *i; ++i )
  {
    if ( !--v10 )
      return -2147483643;
  }
  v21 = 0;
  v22 = &v31[-2 * v10];
  v23 = L"12345678";
  while ( v11 && *v23 )
  {
    *v22++ = *v23++;
    --v11;
    if ( !--v10 )
    {
      --v22;
      v21 = -2147024774;
      break;
    }
  }
  *v22 = 0;
  if ( v21 < 0 )
    return -2147483643;
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
    return -1073741773;
  Buffer = NtPathName.Buffer;
  *(_OWORD *)&NtPathName.Buffer[(unsigned __int64)((unsigned int)NtPathName.Length - 16) >> 1] = *(_OWORD *)a2;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtCreateFile(FileHandle, a3, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, a5 | 0x402020, 0, 0);
  v26 = result;
  if ( result < 0 )
    *FileHandle = 0;
  if ( Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    return v26;
  }
  return result;
}

```

## disassembly

```asm
0x18000b100  mov     [rsp+arg_8], rbx
0x18000b105  mov     [rsp+arg_18], rbp
0x18000b10a  push    rdi
0x18000b10b  push    r14
0x18000b10d  push    r15
0x18000b10f  sub     rsp, 2D0h
0x18000b116  mov     rax, cs:__security_cookie
0x18000b11d  xor     rax, rsp
0x18000b120  mov     [rsp+2E8h+var_28], rax
0x18000b128  mov     r14, [rsp+2E8h+FileHandle]
0x18000b130  mov     r15d, r8d
0x18000b133  mov     rbp, rdx
0x18000b136  mov     rbx, rcx
0x18000b139  xor     edx, edx; Val
0x18000b13b  lea     rcx, [rsp+2E8h+DosPathName]; void *
0x18000b143  mov     r8d, 20Ah; Size
0x18000b149  call    memset_0
0x18000b14e  xorps   xmm0, xmm0
0x18000b151  mov     [rsp+2E8h+arg_0], rsi
0x18000b159  xorps   xmm1, xmm1
0x18000b15c  lea     r9, [rsp+2E8h+DosPathName]
0x18000b164  mov     edx, 105h
0x18000b169  mov     edi, 7FFFFFFEh
0x18000b16e  movups  xmmword ptr [rsp+2E8h+ObjectAttributes.Length], xmm0
0x18000b173  mov     r8d, edx
0x18000b176  mov     ecx, edi
0x18000b178  movups  xmmword ptr [rsp+2E8h+ObjectAttributes.ObjectName], xmm0
0x18000b180  movups  xmmword ptr [rsp+2E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b188  movups  xmmword ptr [rsp+2E8h+IoStatusBlock], xmm0
0x18000b190  movups  xmmword ptr [rsp+2E8h+NtPathName.Length], xmm1
0x18000b195  test    rcx, rcx
0x18000b198  jz      short loc_18000B1C5
0x18000b19a  movzx   eax, word ptr [rbx]
0x18000b19d  test    ax, ax
0x18000b1a0  jz      short loc_18000B1BC
0x18000b1a2  mov     [r9], ax
0x18000b1a6  add     rbx, 2
0x18000b1aa  add     r9, 2
0x18000b1ae  dec     rcx
0x18000b1b1  sub     r8, 1
0x18000b1b5  jnz     short loc_18000B195
0x18000b1b7  jmp     loc_18000B2BF
0x18000b1bc  test    r8, r8
0x18000b1bf  jz      loc_18000B2BF
0x18000b1c5  xor     esi, esi
0x18000b1c7  lea     rax, [rsp+2E8h+DosPathName]
0x18000b1cf  mov     [r9], si
0x18000b1d3  mov     rcx, rdx
0x18000b1d6  cmp     [rax], si
0x18000b1d9  jz      short loc_18000B1EA
0x18000b1db  add     rax, 2
0x18000b1df  sub     rcx, 1
0x18000b1e3  jnz     short loc_18000B1D6
0x18000b1e5  jmp     loc_18000B2BF
0x18000b1ea  lea     rax, [rcx+rcx]
0x18000b1ee  mov     r8, rdi
0x18000b1f1  lea     r9, [rsp+2E8h+var_2E]
0x18000b1f9  mov     r11d, esi
0x18000b1fc  sub     r9, rax
0x18000b1ff  lea     r10, asc_180015BC8; "\\"
0x18000b206  test    rcx, rcx
0x18000b209  jz      short loc_18000B233
0x18000b20b  nop     dword ptr [rax+rax+00h]
0x18000b210  test    r8, r8
0x18000b213  jz      short loc_18000B244
0x18000b215  movzx   eax, word ptr [r10]
0x18000b219  test    ax, ax
0x18000b21c  jz      short loc_18000B23F
0x18000b21e  mov     [r9], ax
0x18000b222  add     r10, 2
0x18000b226  add     r9, 2
0x18000b22a  dec     r8
0x18000b22d  sub     rcx, 1
0x18000b231  jnz     short loc_18000B210
0x18000b233  sub     r9, 2
0x18000b237  mov     r11d, 8007007Ah
0x18000b23d  jmp     short loc_18000B244
0x18000b23f  test    rcx, rcx
0x18000b242  jz      short loc_18000B233
0x18000b244  mov     [r9], si
0x18000b248  test    r11d, r11d
0x18000b24b  js      short loc_18000B2BF
0x18000b24d  lea     rax, [rsp+2E8h+DosPathName]
0x18000b255  cmp     [rax], si
0x18000b258  jz      short loc_18000B266
0x18000b25a  add     rax, 2
0x18000b25e  sub     rdx, 1
0x18000b262  jnz     short loc_18000B255
0x18000b264  jmp     short loc_18000B2BF
0x18000b266  lea     rax, [rdx+rdx]
0x18000b26a  mov     r9d, esi
0x18000b26d  lea     rcx, [rsp+2E8h+var_2E]
0x18000b275  sub     rcx, rax
0x18000b278  lea     r8, a12345678; "12345678"
0x18000b27f  test    rdx, rdx
0x18000b282  jz      short loc_18000B2A6
0x18000b284  test    rdi, rdi
0x18000b287  jz      short loc_18000B2B7
0x18000b289  movzx   eax, word ptr [r8]
0x18000b28d  test    ax, ax
0x18000b290  jz      short loc_18000B2B2
0x18000b292  mov     [rcx], ax
0x18000b295  add     r8, 2
0x18000b299  add     rcx, 2
0x18000b29d  dec     rdi
0x18000b2a0  sub     rdx, 1
0x18000b2a4  jnz     short loc_18000B284
0x18000b2a6  sub     rcx, 2
0x18000b2aa  mov     r9d, 8007007Ah
0x18000b2b0  jmp     short loc_18000B2B7
0x18000b2b2  test    rdx, rdx
0x18000b2b5  jz      short loc_18000B2A6
0x18000b2b7  mov     [rcx], si
0x18000b2ba  test    r9d, r9d
0x18000b2bd  jns     short loc_18000B2C9
0x18000b2bf  mov     eax, 80000005h
0x18000b2c4  jmp     loc_18000B3AA
0x18000b2c9  xor     r9d, r9d; DirectoryInfo
0x18000b2cc  lea     rdx, [rsp+2E8h+NtPathName]; NtPathName
0x18000b2d1  xor     r8d, r8d; NtFileNamePart
0x18000b2d4  lea     rcx, [rsp+2E8h+DosPathName]; DosPathName
0x18000b2dc  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000b2e2  test    al, al
0x18000b2e4  jz      loc_18000B3DB
0x18000b2ea  movzx   ecx, [rsp+2E8h+NtPathName.Length]
0x18000b2ef  lea     rax, [rsp+2E8h+NtPathName]
0x18000b2f4  movups  xmm0, xmmword ptr [rbp+0]
0x18000b2f8  mov     rbx, [rsp+2E8h+NtPathName.Buffer]
0x18000b2fd  lea     r9, [rsp+2E8h+IoStatusBlock]; IoStatusBlock
0x18000b305  mov     [rsp+2E8h+EaLength], esi; EaLength
0x18000b309  lea     r8, [rsp+2E8h+ObjectAttributes]; ObjectAttributes
0x18000b30e  mov     [rsp+2E8h+EaBuffer], rsi; EaBuffer
0x18000b313  sub     ecx, 10h
0x18000b316  shr     rcx, 1
0x18000b319  mov     edx, r15d; DesiredAccess
0x18000b31c  movups  xmmword ptr [rbx+rcx*2], xmm0
0x18000b320  mov     [rsp+2E8h+ObjectAttributes.ObjectName], rax
0x18000b328  mov     rcx, r14; FileHandle
0x18000b32b  mov     eax, [rsp+2E8h+arg_20]
0x18000b332  xorps   xmm0, xmm0
0x18000b335  or      eax, 402020h
0x18000b33a  mov     [rsp+2E8h+ObjectAttributes.Length], 30h ; '0'
0x18000b342  mov     [rsp+2E8h+CreateOptions], eax; CreateOptions
0x18000b346  mov     [rsp+2E8h+CreateDisposition], 1; CreateDisposition
0x18000b34e  mov     [rsp+2E8h+ShareAccess], 7; ShareAccess
0x18000b356  mov     [rsp+2E8h+FileAttributes], 80h; FileAttributes
0x18000b35e  mov     [rsp+2E8h+AllocationSize], rsi; AllocationSize
0x18000b363  mov     [rsp+2E8h+ObjectAttributes.RootDirectory], rsi
0x18000b368  mov     [rsp+2E8h+ObjectAttributes.Attributes], 40h ; '@'
0x18000b373  movdqu  xmmword ptr [rsp+2E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b37c  call    cs:__imp_NtCreateFile
0x18000b382  mov     edi, eax
0x18000b384  test    eax, eax
0x18000b386  jns     short loc_18000B38B
0x18000b388  mov     [r14], rsi
0x18000b38b  test    rbx, rbx
0x18000b38e  jz      short loc_18000B3AA
0x18000b390  mov     rcx, gs:60h
0x18000b399  mov     r8, rbx; P
0x18000b39c  xor     edx, edx; Flags
0x18000b39e  mov     rcx, [rcx+30h]; HeapHandle
0x18000b3a2  call    cs:__imp_RtlFreeHeap
0x18000b3a8  mov     eax, edi
0x18000b3aa  mov     rsi, [rsp+2E8h+arg_0]
0x18000b3b2  mov     rcx, [rsp+2E8h+var_28]
0x18000b3ba  xor     rcx, rsp; StackCookie
0x18000b3bd  call    __security_check_cookie
0x18000b3c2  lea     r11, [rsp+2E8h+var_18]
0x18000b3ca  mov     rbx, [r11+28h]
0x18000b3ce  mov     rbp, [r11+38h]
0x18000b3d2  mov     rsp, r11
0x18000b3d5  pop     r15
0x18000b3d7  pop     r14
0x18000b3d9  pop     rdi
0x18000b3da  retn
0x18000b3db  mov     eax, 0C0000033h
0x18000b3e0  jmp     short loc_18000B3AA
```
