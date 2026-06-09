# RetrieveFormatFileAttributes(ushort const *,int *,_LARGE_INTEGER *)

- ea: `0x383aa1a20`
- end: `0x383aa1b6e`
- name: `?RetrieveFormatFileAttributes@@YAJPEBGPEAHPEAT_LARGE_INTEGER@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *, union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x38396dd70`
- `0x383a30320`

## callees

- `0x383a9fea0`
- `0x383aa1a20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383aa1ad1`
- `KERNEL32!GetLastError` at `0x383aa1ad1`
- `KERNEL32!CloseHandle` at `0x383aa1a8a`
- `KERNEL32!CloseHandle` at `0x383aa1b51`
- `KERNEL32!CloseHandle` at `0x383aa1a8a`
- `KERNEL32!CloseHandle` at `0x383aa1b51`
- `KERNEL32!ReadFile` at `0x383aa1ac7`
- `KERNEL32!ReadFile` at `0x383aa1ac7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetrieveFormatFileAttributes(const unsigned __int16 *a1, int *a2, union _LARGE_INTEGER *a3)
{
  int v5; // edi
  signed int LastError; // eax
  bool v8; // sf
  DWORD v9; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+38h] [rbp-40h]
  void **v12; // [rsp+40h] [rbp-38h] BYREF
  int v13; // [rsp+48h] [rbp-30h]
  HANDLE hObject; // [rsp+50h] [rbp-28h]
  LONGLONG v15; // [rsp+58h] [rbp-20h]
  char Buffer; // [rsp+98h] [rbp+20h] BYREF
  char Buffer_1; // [rsp+99h] [rbp+21h]

  v11 = -2;
  v12 = &CFileReadStream::`vftable';
  v13 = 1;
  hObject = (HANDLE)-1LL;
  v15 = -1;
  NumberOfBytesRead = 0;
  v5 = CFileReadStream::Open((CFileReadStream *)&v12, a1);
  if ( v5 < 0 )
  {
    v12 = &CFileReadStream::`vftable';
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    return (unsigned int)v5;
  }
  if ( !a2 )
    goto LABEL_23;
  NumberOfBytesRead = 0;
  if ( hObject == (HANDLE)-1LL )
    goto LABEL_14;
  if ( ReadFile(hObject, &Buffer, 2u, &NumberOfBytesRead, 0) )
  {
    v9 = NumberOfBytesRead;
    if ( !NumberOfBytesRead )
    {
LABEL_14:
      *a2 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError > 0 )
      v8 = 1;
    if ( v8 )
      goto LABEL_14;
    v9 = NumberOfBytesRead;
  }
  if ( v9 != 2 )
    goto LABEL_14;
LABEL_15:
  if ( Buffer == 49 )
  {
    if ( Buffer_1 != 49 && Buffer_1 != 48 )
    {
LABEL_22:
      *a2 = 1;
      goto LABEL_23;
    }
  }
  else if ( (unsigned __int8)(Buffer - 52) > 5u || Buffer_1 != 46 )
  {
    goto LABEL_22;
  }
  *a2 = 0;
LABEL_23:
  if ( a3 )
    a3->QuadPart = v15;
  v12 = &CFileReadStream::`vftable';
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x383aa1a20  mov     rax, rsp
0x383aa1a23  push    rsi
0x383aa1a24  push    rdi
0x383aa1a25  push    r14
0x383aa1a27  sub     rsp, 60h
0x383aa1a2b  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x383aa1a33  mov     [rax+8], rbx
0x383aa1a37  mov     [rax+10h], rbp
0x383aa1a3b  mov     rsi, r8
0x383aa1a3e  mov     rbx, rdx
0x383aa1a41  lea     r14, ??_7CFileReadStream@@6B@; const CFileReadStream::`vftable'
0x383aa1a48  mov     [rax-38h], r14
0x383aa1a4c  mov     dword ptr [rax-30h], 1
0x383aa1a53  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFFh
0x383aa1a5b  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFFh
0x383aa1a63  xor     ebp, ebp
0x383aa1a65  mov     [rax-48h], ebp
0x383aa1a68  mov     rdx, rcx; unsigned __int16 *
0x383aa1a6b  lea     rcx, [rax-38h]; this
0x383aa1a6f  call    ?Open@CFileReadStream@@UEAAJPEBG@Z; CFileReadStream::Open(ushort const *)
0x383aa1a74  mov     edi, eax
0x383aa1a76  test    eax, eax
0x383aa1a78  jns     short loc_383AA1A97
0x383aa1a7a  mov     [rsp+78h+var_38], r14
0x383aa1a7f  mov     rcx, [rsp+78h+hObject]; hObject
0x383aa1a84  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383aa1a88  jz      short loc_383AA1A90
0x383aa1a8a  call    cs:__imp_CloseHandle
0x383aa1a90  mov     eax, edi
0x383aa1a92  jmp     loc_383AA1B59
0x383aa1a97  test    rbx, rbx
0x383aa1a9a  jz      loc_383AA1B34
0x383aa1aa0  mov     [rsp+78h+NumberOfBytesRead], ebp
0x383aa1aa4  mov     rcx, [rsp+78h+hObject]; hFile
0x383aa1aa9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383aa1aad  jz      short loc_383AA1AFA
0x383aa1aaf  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x383aa1ab4  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x383aa1ab9  mov     r8d, 2; nNumberOfBytesToRead
0x383aa1abf  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x383aa1ac7  call    cs:__imp_ReadFile
0x383aa1acd  test    eax, eax
0x383aa1acf  jnz     short loc_383AA1AED
0x383aa1ad1  call    cs:__imp_GetLastError
0x383aa1ad7  test    eax, eax
0x383aa1ad9  jle     short loc_383AA1AE5
0x383aa1adb  movzx   eax, ax
0x383aa1ade  or      eax, 80070000h
0x383aa1ae3  test    eax, eax
0x383aa1ae5  js      short loc_383AA1AFA
0x383aa1ae7  mov     eax, [rsp+78h+NumberOfBytesRead]
0x383aa1aeb  jmp     short loc_383AA1AF5
0x383aa1aed  mov     eax, [rsp+78h+NumberOfBytesRead]
0x383aa1af1  test    eax, eax
0x383aa1af3  jz      short loc_383AA1AFA
0x383aa1af5  cmp     eax, 2
0x383aa1af8  jz      short loc_383AA1AFC
0x383aa1afa  mov     [rbx], ebp
0x383aa1afc  movzx   eax, [rsp+78h+Buffer]
0x383aa1b04  cmp     al, 31h ; '1'
0x383aa1b06  jnz     short loc_383AA1B1A
0x383aa1b08  movzx   eax, byte ptr [rsp+78h+Buffer+1]
0x383aa1b10  cmp     al, 31h ; '1'
0x383aa1b12  jz      short loc_383AA1B2A
0x383aa1b14  cmp     al, 30h ; '0'
0x383aa1b16  jz      short loc_383AA1B2A
0x383aa1b18  jmp     short loc_383AA1B2E
0x383aa1b1a  sub     al, 34h ; '4'
0x383aa1b1c  cmp     al, 5
0x383aa1b1e  ja      short loc_383AA1B2E
0x383aa1b20  cmp     byte ptr [rsp+78h+Buffer+1], 2Eh ; '.'
0x383aa1b28  jnz     short loc_383AA1B2E
0x383aa1b2a  mov     [rbx], ebp
0x383aa1b2c  jmp     short loc_383AA1B34
0x383aa1b2e  mov     dword ptr [rbx], 1
0x383aa1b34  test    rsi, rsi
0x383aa1b37  jz      short loc_383AA1B41
0x383aa1b39  mov     rax, [rsp+78h+var_20]
0x383aa1b3e  mov     [rsi], rax
0x383aa1b41  mov     [rsp+78h+var_38], r14
0x383aa1b46  mov     rcx, [rsp+78h+hObject]; hObject
0x383aa1b4b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383aa1b4f  jz      short loc_383AA1B57
0x383aa1b51  call    cs:__imp_CloseHandle
0x383aa1b57  xor     eax, eax
0x383aa1b59  lea     r11, [rsp+78h+var_18]
0x383aa1b5e  mov     rbx, [r11+20h]
0x383aa1b62  mov     rbp, [r11+28h]
0x383aa1b66  mov     rsp, r11
0x383aa1b69  pop     r14
0x383aa1b6b  pop     rdi
0x383aa1b6c  pop     rsi
0x383aa1b6d  retn
```
