# I_IsUnsignedPEFile(WINTRUST_FILE_INFO_ *)

- ea: `0x1800013f4`
- end: `0x1800014fc`
- name: `?I_IsUnsignedPEFile@@YAHPEAUWINTRUST_FILE_INFO_@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct WINTRUST_FILE_INFO_ *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800020fc`
- `0x18000a380`

## callees

- `0x1800013f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001438`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001438`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180001457`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180001457`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000147b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000147b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800014f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800014f4`
- `imagehlp!ImageEnumerateCertificates` at `0x1800014d3`
- `imagehlp!ImageEnumerateCertificates` at `0x1800014d3`

## pseudocode

```c
__int64 __fastcall I_IsUnsignedPEFile(struct WINTRUST_FILE_INFO_ *a1)
{
  HANDLE hFile; // rbx
  unsigned int v2; // edi
  int v3; // esi
  bool v4; // cf
  int v5; // eax
  unsigned __int8 Buffer; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int8 v8; // [rsp+61h] [rbp+9h]
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF
  DWORD CertificateCount; // [rsp+70h] [rbp+18h] BYREF

  hFile = a1->hFile;
  v2 = 0;
  NumberOfBytesRead = 0;
  CertificateCount = 0;
  if ( !hFile || (v3 = 0, hFile == (HANDLE)-1LL) )
  {
    hFile = CreateFileW(a1->pcwszFilePath, 0x80000000, 5u, 0, 3u, 0x80u, 0);
    if ( hFile == (HANDLE)-1LL )
      return v2;
    v3 = 1;
  }
  if ( !SetFilePointer(hFile, 0, 0, 0) )
  {
    NumberOfBytesRead = 0;
    if ( ReadFile(hFile, &Buffer, 2u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == 2 )
      {
        v4 = Buffer < 0x4Du;
        if ( Buffer == 77 && (v4 = v8 < 0x5Au, v8 == 90) )
          v5 = 0;
        else
          v5 = v4 ? -1 : 1;
        if ( !v5 )
        {
          CertificateCount = 0;
          if ( !ImageEnumerateCertificates(hFile, 0xFFu, &CertificateCount, 0, 0) || !CertificateCount )
            v2 = 1;
        }
      }
    }
  }
  if ( v3 )
    CloseHandle(hFile);
  return v2;
}

```

## disassembly

```asm
0x1800013f4  push    rbx
0x1800013f6  push    rsi
0x1800013f7  push    rdi
0x1800013f8  sub     rsp, 40h
0x1800013fc  mov     rbx, [rcx+10h]
0x180001400  xor     edi, edi
0x180001402  mov     [rsp+58h+NumberOfBytesRead], edi
0x180001406  mov     [rsp+58h+CertificateCount], edi
0x18000140a  test    rbx, rbx
0x18000140d  jnz     loc_1800014AE
0x180001413  mov     rcx, [rcx+8]; lpFileName
0x180001417  xor     r9d, r9d; lpSecurityAttributes
0x18000141a  mov     [rsp+58h+hTemplateFile], rdi; hTemplateFile
0x18000141f  mov     edx, 80000000h; dwDesiredAccess
0x180001424  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000142c  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180001434  lea     r8d, [r9+5]; dwShareMode
0x180001438  call    cs:__imp_CreateFileW
0x18000143e  mov     rbx, rax
0x180001441  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001445  jz      short loc_1800014A4
0x180001447  mov     esi, 1
0x18000144c  xor     r9d, r9d; dwMoveMethod
0x18000144f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180001452  xor     edx, edx; lDistanceToMove
0x180001454  mov     rcx, rbx; hFile
0x180001457  call    cs:__imp_SetFilePointer
0x18000145d  test    eax, eax
0x18000145f  jnz     short loc_1800014A0
0x180001461  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180001466  mov     [rsp+58h+NumberOfBytesRead], edi
0x18000146a  lea     r8d, [rax+2]; nNumberOfBytesToRead
0x18000146e  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOverlapped
0x180001473  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x180001478  mov     rcx, rbx; hFile
0x18000147b  call    cs:__imp_ReadFile
0x180001481  test    eax, eax
0x180001483  jz      short loc_1800014A0
0x180001485  cmp     [rsp+58h+NumberOfBytesRead], 2
0x18000148a  jnz     short loc_1800014A0
0x18000148c  cmp     [rsp+58h+Buffer], 4Dh ; 'M'
0x180001491  jnz     short loc_1800014EA
0x180001493  cmp     [rsp+58h+arg_1], 5Ah ; 'Z'
0x180001498  jnz     short loc_1800014EA
0x18000149a  xor     eax, eax
0x18000149c  test    eax, eax
0x18000149e  jz      short loc_1800014BB
0x1800014a0  test    esi, esi
0x1800014a2  jnz     short loc_1800014F1
0x1800014a4  mov     eax, edi
0x1800014a6  add     rsp, 40h
0x1800014aa  pop     rdi
0x1800014ab  pop     rsi
0x1800014ac  pop     rbx
0x1800014ad  retn
0x1800014ae  xor     esi, esi
0x1800014b0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800014b4  jnz     short loc_18000144C
0x1800014b6  jmp     loc_180001413
0x1800014bb  mov     edx, 0FFh; TypeFilter
0x1800014c0  mov     [rsp+58h+CertificateCount], edi
0x1800014c4  xor     r9d, r9d; Indices
0x1800014c7  mov     [rsp+58h+dwCreationDisposition], edi; IndexCount
0x1800014cb  lea     r8, [rsp+58h+CertificateCount]; CertificateCount
0x1800014d0  mov     rcx, rbx; FileHandle
0x1800014d3  call    cs:__imp_ImageEnumerateCertificates
0x1800014d9  test    eax, eax
0x1800014db  jz      short loc_1800014E3
0x1800014dd  cmp     [rsp+58h+CertificateCount], edi
0x1800014e1  jnz     short loc_1800014A0
0x1800014e3  mov     edi, 1
0x1800014e8  jmp     short loc_1800014A0
0x1800014ea  sbb     eax, eax
0x1800014ec  or      eax, 1
0x1800014ef  jmp     short loc_18000149C
0x1800014f1  mov     rcx, rbx; hObject
0x1800014f4  call    cs:__imp_CloseHandle
0x1800014fa  jmp     short loc_1800014A4
```
