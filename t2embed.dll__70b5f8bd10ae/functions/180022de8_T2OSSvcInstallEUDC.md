# T2OSSvcInstallEUDC

- ea: `0x180022de8`
- end: `0x180022f0a`
- name: `T2OSSvcInstallEUDC`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1800190a4`

## callees

- `0x180019dc0`
- `0x18001ba0c`
- `0x18001c87c`
- `0x180021ed4`
- `0x18002231c`
- `0x180022828`
- `0x180022de8`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x180022ed9`
- `KERNEL32!DeleteFileA` at `0x180022ed9`

## pseudocode

```c
__int64 __fastcall T2OSSvcInstallEUDC(__int64 a1, unsigned int a2, unsigned int a3, int a4, __int64 a5)
{
  __int64 v5; // rbx
  int v7; // eax
  int UniqueEUDCFileName; // eax
  int v13; // r9d
  STRSAFE_LPCSTR pszSrc[7]; // [rsp+20h] [rbp-38h] BYREF
  __int16 v15; // [rsp+60h] [rbp+8h] BYREF

  v5 = a5;
  v15 = 0;
  v7 = *(_DWORD *)(a1 + 164);
  pszSrc[0] = 0;
  *(_DWORD *)(a5 + 928) = v7;
  if ( !(unsigned int)AllocConvertToMultiByte(pszSrc, &v15, *(_QWORD *)(a1 + 88)) )
    return 0;
  StringCchCopyA((STRSAFE_LPSTR)(v5 + 844), 0x40u, pszSrc[0]);
  T2free((LPVOID)pszSrc[0]);
  UniqueEUDCFileName = MakeUniqueEUDCFileName(v5 + 844, v5 + 520, a2, a3);
  if ( UniqueEUDCFileName
    || (!a2 || a3 ? (v13 = 1) : (v13 = 0),
        (UniqueEUDCFileName = CopyEmbeddedFontDataToFile(
                                *(LPCVOID *)(a1 + 192),
                                *(_DWORD *)(a1 + 188),
                                (LPCSTR)(v5 + 520),
                                v13)) != 0) )
  {
    *(_DWORD *)(v5 + 944) = UniqueEUDCFileName;
    return 0;
  }
  if ( !SetEUDCRegEntry((LPCSTR)(v5 + 844), (BYTE *)(v5 + 520), *(_DWORD *)(a1 + 164), a4) )
  {
    DeleteFileA((LPCSTR)(v5 + 520));
    return 0;
  }
  *(_DWORD *)(v5 + 912) = 1;
  return 1;
}

```

## disassembly

```asm
0x180022de8  mov     r11, rsp
0x180022deb  mov     [r11+10h], rbx
0x180022def  mov     [r11+18h], rbp
0x180022df3  push    rsi
0x180022df4  push    rdi
0x180022df5  push    r12
0x180022df7  push    r14
0x180022df9  push    r15
0x180022dfb  sub     rsp, 30h
0x180022dff  mov     rbx, [rsp+58h+arg_20]
0x180022e07  xor     eax, eax
0x180022e09  mov     [rsp+58h+arg_0], ax
0x180022e0e  mov     r14d, r8d
0x180022e11  mov     eax, [rcx+0A4h]
0x180022e17  mov     ebp, edx
0x180022e19  mov     rsi, rcx
0x180022e1c  mov     qword ptr [r11-38h], 0
0x180022e24  mov     [rbx+3A0h], eax
0x180022e2a  lea     rdx, [r11+8]
0x180022e2e  mov     r8, [rcx+58h]
0x180022e32  mov     r12d, r9d
0x180022e35  lea     rcx, [r11-38h]
0x180022e39  call    AllocConvertToMultiByte
0x180022e3e  test    eax, eax
0x180022e40  jnz     short loc_180022E49
0x180022e42  xor     eax, eax
0x180022e44  jmp     loc_180022EF3
0x180022e49  mov     r8, [rsp+58h+pszSrc]; pszSrc
0x180022e4e  lea     r15, [rbx+34Ch]
0x180022e55  mov     rcx, r15; pszDest
0x180022e58  mov     edx, 40h ; '@'; cchDest
0x180022e5d  call    StringCchCopyA
0x180022e62  mov     rcx, [rsp+58h+pszSrc]; lpMem
0x180022e67  call    T2free
0x180022e6c  lea     rdi, [rbx+208h]
0x180022e73  mov     r9d, r14d
0x180022e76  mov     rdx, rdi
0x180022e79  mov     r8d, ebp
0x180022e7c  mov     rcx, r15
0x180022e7f  call    MakeUniqueEUDCFileName
0x180022e84  test    eax, eax
0x180022e86  jz      short loc_180022E90
0x180022e88  mov     [rbx+3B0h], eax
0x180022e8e  jmp     short loc_180022E42
0x180022e90  test    ebp, ebp
0x180022e92  jz      short loc_180022E9E
0x180022e94  test    r14d, r14d
0x180022e97  jnz     short loc_180022E9E
0x180022e99  xor     r9d, r9d
0x180022e9c  jmp     short loc_180022EA4
0x180022e9e  mov     r9d, 1
0x180022ea4  mov     edx, [rsi+0BCh]; nNumberOfBytesToWrite
0x180022eaa  mov     r8, rdi; lpFileName
0x180022ead  mov     rcx, [rsi+0C0h]; lpBuffer
0x180022eb4  call    CopyEmbeddedFontDataToFile
0x180022eb9  test    eax, eax
0x180022ebb  jnz     short loc_180022E88
0x180022ebd  mov     r8d, [rsi+0A4h]
0x180022ec4  mov     r9d, r12d
0x180022ec7  mov     rdx, rdi; lpData
0x180022eca  mov     rcx, r15; lpValueName
0x180022ecd  call    SetEUDCRegEntry
0x180022ed2  test    eax, eax
0x180022ed4  jnz     short loc_180022EE4
0x180022ed6  mov     rcx, rdi; lpFileName
0x180022ed9  call    cs:__imp_DeleteFileA
0x180022edf  jmp     loc_180022E42
0x180022ee4  mov     dword ptr [rbx+390h], 1
0x180022eee  mov     eax, 1
0x180022ef3  mov     rbx, [rsp+58h+arg_8]
0x180022ef8  mov     rbp, [rsp+58h+arg_10]
0x180022efd  add     rsp, 30h
0x180022f01  pop     r15
0x180022f03  pop     r14
0x180022f05  pop     r12
0x180022f07  pop     rdi
0x180022f08  pop     rsi
0x180022f09  retn
```
