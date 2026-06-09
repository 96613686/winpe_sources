# CMemFileReader::Open(ushort const *)

- ea: `0x383a89960`
- end: `0x383a89a91`
- name: `?Open@CMemFileReader@@UEAAJPEBG@Z`
- size: `305`
- prototype: `__int64 __fastcall(CMemFileReader *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x38391aed0`
- `0x383a89100`
- `0x383a89960`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x383a89a5b`
- `KERNEL32!CloseHandle` at `0x383a89a5b`
- `KERNEL32!MapViewOfFile` at `0x383a89a24`
- `KERNEL32!MapViewOfFile` at `0x383a89a24`
- `KERNEL32!CreateFileMappingW` at `0x383a899ed`
- `KERNEL32!CreateFileMappingW` at `0x383a899ed`

## pseudocode

```c
int __fastcall CMemFileReader::Open(HANDLE *this, const unsigned __int16 *a2)
{
  int result; // eax
  int v4; // edi
  HANDLE FileMappingW; // r11
  unsigned int v6; // ecx
  LPVOID v7; // rax

  result = CFileReader::Open((CFileReader *)this, a2);
  v4 = result;
  if ( result < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
      {
        bidTraceW(off_383B43488[0], 496681, off_383B49128[0], (unsigned int)result);
        return v4;
      }
    }
    return result;
  }
  if ( (__int64)this[2] <= 0 )
    return v4;
  FileMappingW = CreateFileMappingW(this[1], 0, 2u, 0, 0, 0);
  this[5] = FileMappingW;
  if ( !FileMappingW )
    return 1;
  v6 = 0x100000;
  if ( (__int64)this[2] <= 0x100000 )
    v6 = *((_DWORD *)this + 4);
  *((_DWORD *)this + 19) = v6;
  v7 = MapViewOfFile(FileMappingW, 4u, 0, 0, v6);
  this[6] = v7;
  if ( v7 )
  {
    this[7] = 0;
    this[8] = 0;
    *((_DWORD *)this + 18) = 0;
    *((_DWORD *)this + 8) = 1;
    return v4;
  }
  else
  {
    CloseHandle(this[5]);
    this[5] = 0;
    return 1;
  }
}

```

## disassembly

```asm
0x383a89960  mov     [rsp+arg_8], rbx
0x383a89965  push    rdi
0x383a89966  sub     rsp, 30h
0x383a8996a  mov     rbx, rcx
0x383a8996d  call    ?Open@CFileReader@@UEAAJPEBG@Z; CFileReader::Open(ushort const *)
0x383a89972  mov     edi, eax
0x383a89974  test    eax, eax
0x383a89976  jns     short loc_383A899C5
0x383a89978  test    byte ptr cs:_bidGblFlags, 2
0x383a8997f  jz      loc_383A89A86
0x383a89985  mov     rcx, cs:off_383B43488; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a8998c  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a89993  test    rdx, rdx
0x383a89996  jz      loc_383A89A86
0x383a8999c  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a899a3  mov     r9d, eax
0x383a899a6  mov     edx, 79429h
0x383a899ab  mov     [rsp+38h+dwMaximumSizeLow], 1E5h
0x383a899b3  call    _bidTraceW
0x383a899b8  mov     eax, edi
0x383a899ba  mov     rbx, [rsp+38h+arg_8]
0x383a899bf  add     rsp, 30h
0x383a899c3  pop     rdi
0x383a899c4  retn
0x383a899c5  cmp     qword ptr [rbx+10h], 0
0x383a899ca  mov     [rsp+38h+arg_0], rsi
0x383a899cf  jle     loc_383A89A7F
0x383a899d5  mov     rcx, [rbx+8]; hFile
0x383a899d9  xor     esi, esi
0x383a899db  xor     r9d, r9d; dwMaximumSizeHigh
0x383a899de  lea     r8d, [rsi+2]; flProtect
0x383a899e2  xor     edx, edx; lpFileMappingAttributes
0x383a899e4  mov     [rsp+38h+lpName], rsi; lpName
0x383a899e9  mov     [rsp+38h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x383a899ed  call    cs:__imp_CreateFileMappingW
0x383a899f3  mov     r11, rax
0x383a899f6  mov     [rbx+28h], rax
0x383a899fa  test    rax, rax
0x383a899fd  jz      short loc_383A89A7A
0x383a899ff  mov     ecx, 100000h
0x383a89a04  cmp     [rbx+10h], rcx
0x383a89a08  jg      short loc_383A89A0D
0x383a89a0a  mov     ecx, [rbx+10h]
0x383a89a0d  mov     eax, ecx
0x383a89a0f  xor     r9d, r9d; dwFileOffsetLow
0x383a89a12  mov     [rbx+4Ch], ecx
0x383a89a15  lea     edx, [r9+4]; dwDesiredAccess
0x383a89a19  xor     r8d, r8d; dwFileOffsetHigh
0x383a89a1c  mov     rcx, r11; hFileMappingObject
0x383a89a1f  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x383a89a24  call    cs:__imp_MapViewOfFile
0x383a89a2a  mov     [rbx+30h], rax
0x383a89a2e  test    rax, rax
0x383a89a31  jz      short loc_383A89A57
0x383a89a33  mov     [rbx+38h], rsi
0x383a89a37  mov     [rbx+40h], rsi
0x383a89a3b  mov     [rbx+48h], esi
0x383a89a3e  mov     rsi, [rsp+38h+arg_0]
0x383a89a43  mov     dword ptr [rbx+20h], 1
0x383a89a4a  mov     eax, edi
0x383a89a4c  mov     rbx, [rsp+38h+arg_8]
0x383a89a51  add     rsp, 30h
0x383a89a55  pop     rdi
0x383a89a56  retn
0x383a89a57  mov     rcx, [rbx+28h]; hObject
0x383a89a5b  call    cs:__imp_CloseHandle
0x383a89a61  mov     [rbx+28h], rsi
0x383a89a65  mov     rsi, [rsp+38h+arg_0]
0x383a89a6a  mov     eax, 1
0x383a89a6f  mov     rbx, [rsp+38h+arg_8]
0x383a89a74  add     rsp, 30h
0x383a89a78  pop     rdi
0x383a89a79  retn
0x383a89a7a  mov     edi, 1
0x383a89a7f  mov     rsi, [rsp+38h+arg_0]
0x383a89a84  mov     eax, edi
0x383a89a86  mov     rbx, [rsp+38h+arg_8]
0x383a89a8b  add     rsp, 30h
0x383a89a8f  pop     rdi
0x383a89a90  retn
```
