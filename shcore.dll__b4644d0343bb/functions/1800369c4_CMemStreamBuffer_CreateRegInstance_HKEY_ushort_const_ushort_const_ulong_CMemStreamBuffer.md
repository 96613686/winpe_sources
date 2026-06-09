# CMemStreamBuffer::CreateRegInstance(HKEY__ *,ushort const *,ushort const *,ulong,CMemStreamBuffer * *)

- ea: `0x1800369c4`
- end: `0x180036b7b`
- name: `?CreateRegInstance@CMemStreamBuffer@@SAJPEAUHKEY__@@PEBG1KPEAPEAV1@@Z`
- size: `439`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValueName@<r8>, unsigned int@<r9d>, struct CMemStreamBuffer **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180036918`

## callees

- `0x1800203f0`
- `0x180020e5c`
- `0x1800369c4`
- `0x180036c3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036aca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036aca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036b5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036b5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036afe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036b3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036afe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036b3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036a3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036a96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036a3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036a96`

## pseudocode

```c
__int64 __fastcall CMemStreamBuffer::CreateRegInstance(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        int a4,
        struct CMemStreamBuffer **phkResult)
{
  struct CMemStreamBuffer **v5; // r15
  int Instance; // ebx
  __int64 v11; // rdi
  int v12; // esi
  LSTATUS Key; // eax
  HKEY v14; // rcx
  DWORD Type[2]; // [rsp+50h] [rbp-18h] BYREF

  v5 = phkResult;
  *(_QWORD *)Type = 0;
  *phkResult = 0;
  Instance = CMemStreamBuffer::CreateInstance(0, 0, lpValueName, (struct CMemStreamBuffer **)Type);
  if ( Instance >= 0 )
  {
    v11 = *(_QWORD *)Type;
    *(_DWORD *)(*(_QWORD *)Type + 24LL) = a4;
    if ( lpSubKey && *lpSubKey )
    {
      v12 = a4 & 3;
      if ( v12 )
        Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, (PHKEY)(v11 + 32), 0);
      else
        Key = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, (PHKEY)(v11 + 32));
      if ( Key )
        *(_QWORD *)(v11 + 32) = 0;
      v5 = phkResult;
    }
    else
    {
      phkResult = 0;
      RegOpenKeyExW(hKey, 0, 0, 0x2000000u, (PHKEY)&phkResult);
      v12 = a4 & 3;
      *(_QWORD *)(v11 + 32) = phkResult;
    }
    v14 = *(HKEY *)(v11 + 32);
    if ( !v14 )
      goto LABEL_10;
    if ( v12 != 1 )
    {
      Type[0] = 0;
      LODWORD(phkResult) = 0;
      if ( !RegQueryValueExW(v14, lpValueName, 0, Type, 0, (LPDWORD)&phkResult) && (_DWORD)phkResult )
      {
        if ( (int)CMemStreamBuffer::GrowBuffer((CMemStreamBuffer *)v11, (unsigned int)phkResult) < 0 )
        {
LABEL_10:
          Instance = -2147467259;
LABEL_11:
          CMemStreamBuffer::Release((CMemStreamBuffer *)v11);
          return (unsigned int)Instance;
        }
        if ( RegQueryValueExW(*(HKEY *)(v11 + 32), lpValueName, 0, Type, *(LPBYTE *)(v11 + 8), (LPDWORD)&phkResult) )
          Instance = -2147467259;
        else
          *(_DWORD *)(v11 + 20) = (_DWORD)phkResult;
        if ( Instance < 0 )
          goto LABEL_11;
      }
      if ( !v12 )
      {
        RegCloseKey(*(HKEY *)(v11 + 32));
        *(_QWORD *)(v11 + 32) = 0;
      }
    }
    _InterlockedIncrement((volatile signed __int32 *)v11);
    *v5 = (struct CMemStreamBuffer *)v11;
    goto LABEL_11;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800369c4  push    rbp
0x1800369c6  push    rbx
0x1800369c7  push    rsi
0x1800369c8  push    rdi
0x1800369c9  push    r12
0x1800369cb  push    r13
0x1800369cd  push    r14
0x1800369cf  push    r15
0x1800369d1  mov     rbp, rsp
0x1800369d4  sub     rsp, 68h
0x1800369d8  mov     r15, [rbp+arg_20]
0x1800369dc  mov     esi, r9d
0x1800369df  mov     r14, rdx
0x1800369e2  mov     qword ptr [rbp+Type], 0
0x1800369ea  mov     r12, rcx
0x1800369ed  lea     r9, [rbp+Type]; struct CMemStreamBuffer **
0x1800369f1  xor     edx, edx; Size
0x1800369f3  xor     ecx, ecx; Src
0x1800369f5  mov     qword ptr [r15], 0
0x1800369fc  mov     r13, r8
0x1800369ff  call    ?CreateInstance@CMemStreamBuffer@@SAJPEBEIPEBGPEAPEAV1@@Z; CMemStreamBuffer::CreateInstance(uchar const *,uint,ushort const *,CMemStreamBuffer * *)
0x180036a04  mov     ebx, eax
0x180036a06  xor     eax, eax
0x180036a08  test    ebx, ebx
0x180036a0a  js      short loc_180036A65
0x180036a0c  mov     rdi, qword ptr [rbp+Type]
0x180036a10  mov     [rdi+18h], esi
0x180036a13  test    r14, r14
0x180036a16  jz      short loc_180036A78
0x180036a18  cmp     [r14], ax
0x180036a1c  jz      short loc_180036A78
0x180036a1e  lea     r15, [rdi+20h]
0x180036a22  mov     rdx, r14; lpSubKey
0x180036a25  mov     rcx, r12; hKey
0x180036a28  and     esi, 3
0x180036a2b  jnz     short loc_180036AA9
0x180036a2d  mov     r9d, 20019h; samDesired
0x180036a33  mov     [rsp+68h+phkResult], r15; phkResult
0x180036a38  xor     r8d, r8d; ulOptions
0x180036a3b  call    cs:__imp_RegOpenKeyExW
0x180036a41  xor     r14d, r14d
0x180036a44  test    eax, eax
0x180036a46  jz      short loc_180036A4B
0x180036a48  mov     [r15], r14
0x180036a4b  mov     r15, [rbp+arg_20]
0x180036a4f  mov     rcx, [rdi+20h]; hKey
0x180036a53  test    rcx, rcx
0x180036a56  jnz     short loc_180036AD5
0x180036a58  mov     ebx, 80004005h
0x180036a5d  mov     rcx, rdi; this
0x180036a60  call    ?Release@CMemStreamBuffer@@QEAAIXZ; CMemStreamBuffer::Release(void)
0x180036a65  mov     eax, ebx
0x180036a67  add     rsp, 68h
0x180036a6b  pop     r15
0x180036a6d  pop     r14
0x180036a6f  pop     r13
0x180036a71  pop     r12
0x180036a73  pop     rdi
0x180036a74  pop     rsi
0x180036a75  pop     rbx
0x180036a76  pop     rbp
0x180036a77  retn
0x180036a78  lea     rax, [rbp+arg_20]
0x180036a7c  xor     r14d, r14d
0x180036a7f  mov     r9d, 2000000h; samDesired
0x180036a85  mov     [rbp+arg_20], r14
0x180036a89  xor     r8d, r8d; ulOptions
0x180036a8c  mov     [rsp+68h+phkResult], rax; phkResult
0x180036a91  xor     edx, edx; lpSubKey
0x180036a93  mov     rcx, r12; hKey
0x180036a96  call    cs:__imp_RegOpenKeyExW
0x180036a9c  mov     rax, [rbp+arg_20]
0x180036aa0  and     esi, 3
0x180036aa3  mov     [rdi+20h], rax
0x180036aa7  jmp     short loc_180036A4F
0x180036aa9  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180036aae  xor     r9d, r9d; lpClass
0x180036ab1  mov     [rsp+68h+var_30], r15; phkResult
0x180036ab6  xor     r8d, r8d; Reserved
0x180036ab9  mov     [rsp+68h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180036abe  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180036ac6  mov     dword ptr [rsp+68h+phkResult], eax; dwOptions
0x180036aca  call    cs:__imp_RegCreateKeyExW
0x180036ad0  jmp     loc_180036A41
0x180036ad5  cmp     esi, 1
0x180036ad8  jz      loc_180036B69
0x180036ade  lea     rax, [rbp+arg_20]
0x180036ae2  mov     [rbp+Type], r14d
0x180036ae6  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180036aeb  lea     r9, [rbp+Type]; lpType
0x180036aef  xor     r8d, r8d; lpReserved
0x180036af2  mov     [rsp+68h+phkResult], r14; lpData
0x180036af7  mov     rdx, r13; lpValueName
0x180036afa  mov     dword ptr [rbp+arg_20], r14d
0x180036afe  call    cs:__imp_RegQueryValueExW
0x180036b04  test    eax, eax
0x180036b06  jnz     short loc_180036B57
0x180036b08  mov     edx, dword ptr [rbp+arg_20]; unsigned int
0x180036b0b  test    edx, edx
0x180036b0d  jz      short loc_180036B57
0x180036b0f  mov     rcx, rdi; this
0x180036b12  call    ?GrowBuffer@CMemStreamBuffer@@QEAAJK@Z; CMemStreamBuffer::GrowBuffer(ulong)
0x180036b17  test    eax, eax
0x180036b19  js      loc_180036A58
0x180036b1f  mov     rcx, [rdi+20h]; hKey
0x180036b23  lea     rax, [rbp+arg_20]
0x180036b27  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180036b2c  lea     r9, [rbp+Type]; lpType
0x180036b30  mov     rax, [rdi+8]
0x180036b34  xor     r8d, r8d; lpReserved
0x180036b37  mov     rdx, r13; lpValueName
0x180036b3a  mov     [rsp+68h+phkResult], rax; lpData
0x180036b3f  call    cs:__imp_RegQueryValueExW
0x180036b45  test    eax, eax
0x180036b47  jnz     short loc_180036B74
0x180036b49  mov     eax, dword ptr [rbp+arg_20]
0x180036b4c  mov     [rdi+14h], eax
0x180036b4f  test    ebx, ebx
0x180036b51  js      loc_180036A5D
0x180036b57  test    esi, esi
0x180036b59  jnz     short loc_180036B69
0x180036b5b  mov     rcx, [rdi+20h]; hKey
0x180036b5f  call    cs:__imp_RegCloseKey
0x180036b65  mov     [rdi+20h], r14
0x180036b69  lock inc dword ptr [rdi]
0x180036b6c  mov     [r15], rdi
0x180036b6f  jmp     loc_180036A5D
0x180036b74  mov     ebx, 80004005h
0x180036b79  jmp     short loc_180036B4F
```
