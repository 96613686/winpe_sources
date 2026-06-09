# DVRCreateReader

- ea: `0x180068940`
- end: `0x180068cd4`
- name: `DVRCreateReader`
- size: `916`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int64, HANDLE hSourceHandle, unsigned int, void **, int, int, __int64)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800261a0`
- `0x1800262c0`
- `0x180027c5c`
- `0x18003bb88`
- `0x180062e40`
- `0x180066a68`
- `0x180066db4`

## callees

- `0x1800017a0`
- `0x180001c00`
- `0x180063528`
- `0x180068940`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x180068adb`
- `KERNEL32!DuplicateHandle` at `0x180068adb`
- `KERNEL32!GetLastError` at `0x180068ae5`
- `KERNEL32!GetLastError` at `0x180068ae5`
- `KERNEL32!GetCurrentProcess` at `0x180068aa3`
- `KERNEL32!GetCurrentProcess` at `0x180068aac`
- `KERNEL32!GetCurrentProcess` at `0x180068aa3`
- `KERNEL32!GetCurrentProcess` at `0x180068aac`
- `ADVAPI32!RegCloseKey` at `0x180068c8f`
- `ADVAPI32!RegCloseKey` at `0x180068ca2`
- `ADVAPI32!RegCloseKey` at `0x1800b3d03`
- `ADVAPI32!RegCloseKey` at `0x1800b3d16`
- `ADVAPI32!RegCloseKey` at `0x180068c8f`
- `ADVAPI32!RegCloseKey` at `0x180068ca2`
- `ADVAPI32!RegCloseKey` at `0x1800b3d03`
- `ADVAPI32!RegCloseKey` at `0x1800b3d16`
- `ADVAPI32!RegCreateKeyExW` at `0x180068a9b`
- `ADVAPI32!RegCreateKeyExW` at `0x180068b57`
- `ADVAPI32!RegCreateKeyExW` at `0x180068a9b`
- `ADVAPI32!RegCreateKeyExW` at `0x180068b57`

## string_xrefs

- `0x180068b50`: `IO\Reader`

## pseudocode

```c
__int64 __fastcall DVRCreateReader(
        struct CPVRIOCounters *a1,
        unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        void (*a6)(void *, unsigned int, __int64, __int64),
        void *a7,
        HANDLE hSourceHandle,
        unsigned int a9,
        void **a10,
        int a11,
        int a12,
        _QWORD *a13)
{
  _QWORD *v13; // rbx
  int v14; // edi
  CDVRReader *v15; // rsi
  int v16; // r14d
  HANDLE CurrentProcess; // rbx
  HANDLE v18; // rax
  signed int LastError; // eax
  CDVRReader *v20; // rcx
  int v22; // [rsp+80h] [rbp-A8h] BYREF
  int v23; // [rsp+84h] [rbp-A4h]
  int v24; // [rsp+88h] [rbp-A0h]
  int v25; // [rsp+8Ch] [rbp-9Ch]
  unsigned int v26; // [rsp+90h] [rbp-98h]
  unsigned int v27; // [rsp+94h] [rbp-94h]
  int v28; // [rsp+98h] [rbp-90h]
  CDVRReader *v29; // [rsp+A0h] [rbp-88h]
  _QWORD *v30; // [rsp+A8h] [rbp-80h]
  void *v31; // [rsp+B0h] [rbp-78h]
  void (*v32)(void *, unsigned int, __int64, __int64); // [rsp+B8h] [rbp-70h]
  unsigned __int16 *v33; // [rsp+C0h] [rbp-68h]
  struct CPVRIOCounters *v34; // [rsp+C8h] [rbp-60h]
  HKEY hKey; // [rsp+D0h] [rbp-58h] BYREF
  HKEY phkResult; // [rsp+D8h] [rbp-50h] BYREF

  v27 = a4;
  v28 = a3;
  v33 = a2;
  v34 = a1;
  v26 = a5;
  v32 = a6;
  v31 = a7;
  v25 = a11;
  v24 = a12;
  v13 = a13;
  v30 = a13;
  if ( !a13 || !a2 )
    return 2147942487LL;
  if ( a9 )
  {
    if ( a10 )
      goto LABEL_7;
    return 2147942487LL;
  }
  if ( a10 )
    return 2147942487LL;
LABEL_7:
  v14 = 0;
  v22 = 0;
  v15 = 0;
  v29 = 0;
  phkResult = 0;
  hKey = 0;
  v16 = 1;
  v23 = 1;
  *a13 = 0;
  if ( hSourceHandle )
  {
    CurrentProcess = GetCurrentProcess();
    v18 = GetCurrentProcess();
    if ( !DuplicateHandle(v18, hSourceHandle, CurrentProcess, (LPHANDLE)&hKey, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_12;
    }
    v13 = v30;
  }
  else
  {
    RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\DVR", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  }
  if ( hKey )
    RegCreateKeyExW(hKey, L"IO\\Reader", 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  v20 = (CDVRReader *)operator new(0x1F8u);
  if ( v20 )
  {
    v15 = CDVRReader::CDVRReader(v20, v34, v33, a9, a10, v28, v27, v26, v32, v31, hKey, phkResult, v25, v24, &v22);
    v14 = v22;
  }
  else
  {
    v15 = 0;
  }
  v29 = v15;
  if ( v15 )
  {
    v16 = 0;
    v23 = 0;
    if ( v14 >= 0 )
    {
      v14 = (**(__int64 (__fastcall ***)(CDVRReader *, GUID *, _QWORD *))v15)(v15, &IID_IDVRReader, v13);
      v22 = v14;
    }
    goto LABEL_23;
  }
  v14 = -2147024882;
LABEL_12:
  v22 = v14;
LABEL_23:
  if ( v14 < 0 )
  {
    if ( v15 )
      (*(void (__fastcall **)(CDVRReader *, __int64))(*(_QWORD *)v15 + 136LL))(v15, 1);
    if ( v16 )
    {
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180068940  push    rbx
0x180068942  push    rsi
0x180068943  push    rdi
0x180068944  push    r12
0x180068946  push    r13
0x180068948  push    r14
0x18006894a  push    r15
0x18006894c  sub     rsp, 0F0h
0x180068953  mov     rax, cs:__security_cookie
0x18006895a  xor     rax, rsp
0x18006895d  mov     [rsp+128h+var_48], rax
0x180068965  mov     [rsp+128h+var_94], r9d
0x18006896d  mov     [rsp+128h+var_90], r8d
0x180068975  mov     rax, rdx
0x180068978  mov     [rsp+128h+var_68], rdx
0x180068980  mov     [rsp+128h+var_60], rcx
0x180068988  mov     ecx, [rsp+128h+arg_20]
0x18006898f  mov     [rsp+128h+var_98], ecx
0x180068996  mov     rcx, [rsp+128h+arg_28]
0x18006899e  mov     [rsp+128h+var_70], rcx
0x1800689a6  mov     rcx, [rsp+128h+arg_30]
0x1800689ae  mov     [rsp+128h+var_78], rcx
0x1800689b6  mov     r13, [rsp+128h+hSourceHandle]
0x1800689be  mov     r15d, [rsp+128h+arg_40]
0x1800689c6  mov     r12, [rsp+128h+arg_48]
0x1800689ce  mov     ecx, [rsp+128h+arg_50]
0x1800689d5  mov     [rsp+128h+var_9C], ecx
0x1800689dc  mov     ecx, [rsp+128h+arg_58]
0x1800689e3  mov     [rsp+128h+var_A0], ecx
0x1800689ea  mov     rbx, [rsp+128h+arg_60]
0x1800689f2  mov     [rsp+128h+var_80], rbx
0x1800689fa  xor     ecx, ecx
0x1800689fc  test    rbx, rbx
0x1800689ff  jz      loc_180068CAC
0x180068a05  test    rax, rax
0x180068a08  jz      loc_180068CAC
0x180068a0e  test    r15d, r15d
0x180068a11  jnz     short loc_180068A21
0x180068a13  test    r12, r12
0x180068a16  jnz     loc_180068CAC
0x180068a1c  test    r15d, r15d
0x180068a1f  jz      short loc_180068A2A
0x180068a21  test    r12, r12
0x180068a24  jz      loc_180068CAC
0x180068a2a  mov     edi, ecx
0x180068a2c  mov     [rsp+128h+var_A8], ecx
0x180068a33  mov     rsi, rcx
0x180068a36  mov     [rsp+128h+var_88], rcx
0x180068a3e  mov     [rsp+128h+var_50], rcx
0x180068a46  mov     [rsp+128h+hKey], rcx
0x180068a4e  mov     r14d, 1
0x180068a54  mov     [rsp+128h+var_A4], r14d
0x180068a5c  mov     [rbx], rcx
0x180068a5f  test    r13, r13
0x180068a62  jnz     short loc_180068AA3
0x180068a64  mov     [rsp+128h+lpdwDisposition], rcx; lpdwDisposition
0x180068a69  lea     rax, [rsp+128h+hKey]
0x180068a71  mov     [rsp+128h+phkResult], rax; phkResult
0x180068a76  mov     [rsp+128h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180068a7b  mov     [rsp+128h+samDesired], 2001Fh; samDesired
0x180068a83  mov     [rsp+128h+dwOptions], ecx; dwOptions
0x180068a87  xor     r9d, r9d; lpClass
0x180068a8a  xor     r8d, r8d; Reserved
0x180068a8d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\DVR"
0x180068a94  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180068a9b  call    cs:__imp_RegCreateKeyExW
0x180068aa1  jmp     short loc_180068B0E
0x180068aa3  call    cs:__imp_GetCurrentProcess
0x180068aa9  mov     rbx, rax
0x180068aac  call    cs:__imp_GetCurrentProcess
0x180068ab2  mov     dword ptr [rsp+128h+lpSecurityAttributes], 2; dwOptions
0x180068aba  mov     [rsp+128h+samDesired], 0; bInheritHandle
0x180068ac2  mov     [rsp+128h+dwOptions], 0; dwDesiredAccess
0x180068aca  lea     r9, [rsp+128h+hKey]; lpTargetHandle
0x180068ad2  mov     r8, rbx; hTargetProcessHandle
0x180068ad5  mov     rdx, r13; hSourceHandle
0x180068ad8  mov     rcx, rax; hSourceProcessHandle
0x180068adb  call    cs:__imp_DuplicateHandle
0x180068ae1  test    eax, eax
0x180068ae3  jnz     short loc_180068B06
0x180068ae5  call    cs:__imp_GetLastError
0x180068aeb  mov     edi, eax
0x180068aed  test    eax, eax
0x180068aef  jle     short loc_180068AFA
0x180068af1  movzx   edi, ax
0x180068af4  or      edi, 80070000h
0x180068afa  mov     [rsp+128h+var_A8], edi
0x180068b01  jmp     loc_180068C5D
0x180068b06  mov     rbx, [rsp+128h+var_80]
0x180068b0e  mov     rcx, [rsp+128h+hKey]; hKey
0x180068b16  test    rcx, rcx
0x180068b19  jz      short loc_180068B5D
0x180068b1b  mov     [rsp+128h+lpdwDisposition], 0; lpdwDisposition
0x180068b24  lea     rax, [rsp+128h+var_50]
0x180068b2c  mov     [rsp+128h+phkResult], rax; phkResult
0x180068b31  mov     [rsp+128h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180068b3a  mov     [rsp+128h+samDesired], 2001Fh; samDesired
0x180068b42  mov     [rsp+128h+dwOptions], 0; dwOptions
0x180068b4a  xor     r9d, r9d; lpClass
0x180068b4d  xor     r8d, r8d; Reserved
0x180068b50  lea     rdx, aIoReader; "IO\\Reader"
0x180068b57  call    cs:__imp_RegCreateKeyExW
0x180068b5d  mov     ecx, 1F8h; Size
0x180068b62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068b67  mov     rcx, rax; this
0x180068b6a  test    rax, rax
0x180068b6d  jz      loc_180068C14
0x180068b73  lea     rax, [rsp+128h+var_A8]
0x180068b7b  mov     [rsp+128h+var_B8], rax; int *
0x180068b80  mov     eax, [rsp+128h+var_A0]
0x180068b87  mov     [rsp+128h+var_C0], eax; int
0x180068b8b  mov     eax, [rsp+128h+var_9C]
0x180068b92  mov     [rsp+128h+var_C8], eax; int
0x180068b96  mov     rax, [rsp+128h+var_50]
0x180068b9e  mov     [rsp+128h+var_D0], rax; HKEY
0x180068ba3  mov     rax, [rsp+128h+hKey]
0x180068bab  mov     [rsp+128h+var_D8], rax; HKEY
0x180068bb0  mov     rax, [rsp+128h+var_78]
0x180068bb8  mov     [rsp+128h+var_E0], rax; void *
0x180068bbd  mov     rax, [rsp+128h+var_70]
0x180068bc5  mov     [rsp+128h+lpdwDisposition], rax; void (*)(void *, unsigned int, __int64, __int64)
0x180068bca  mov     eax, [rsp+128h+var_98]
0x180068bd1  mov     dword ptr [rsp+128h+phkResult], eax; unsigned int
0x180068bd5  mov     eax, [rsp+128h+var_94]
0x180068bdc  mov     dword ptr [rsp+128h+lpSecurityAttributes], eax; unsigned int
0x180068be0  mov     eax, [rsp+128h+var_90]
0x180068be7  mov     [rsp+128h+samDesired], eax; int
0x180068beb  mov     qword ptr [rsp+128h+dwOptions], r12; void **
0x180068bf0  mov     r9d, r15d; unsigned int
0x180068bf3  mov     r8, [rsp+128h+var_68]; unsigned __int16 *
0x180068bfb  mov     rdx, [rsp+128h+var_60]; struct CPVRIOCounters *
0x180068c03  call    ??0CDVRReader@@QEAA@PEAVCPVRIOCounters@@PEBGKPEAPEAXHKKP6AXPEAXK_J4@Z3PEAUHKEY__@@6HHPEAJ@Z; CDVRReader::CDVRReader(CPVRIOCounters *,ushort const *,ulong,void * *,int,ulong,ulong,void (*)(void *,ulong,__int64,__int64),void *,HKEY__ *,HKEY__ *,int,int,long *)
0x180068c08  mov     rsi, rax
0x180068c0b  mov     edi, [rsp+128h+var_A8]
0x180068c12  jmp     short loc_180068C16
0x180068c14  xor     esi, esi
0x180068c16  mov     [rsp+128h+var_88], rsi
0x180068c1e  test    rsi, rsi
0x180068c21  jnz     short loc_180068C2D
0x180068c23  mov     edi, 8007000Eh
0x180068c28  jmp     loc_180068AFA
0x180068c2d  xor     r14d, r14d
0x180068c30  mov     [rsp+128h+var_A4], r14d
0x180068c38  test    edi, edi
0x180068c3a  js      short loc_180068C5D
0x180068c3c  mov     rax, [rsi]
0x180068c3f  mov     r8, rbx
0x180068c42  lea     rdx, IID_IDVRReader
0x180068c49  mov     rcx, rsi
0x180068c4c  mov     rax, [rax]
0x180068c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c54  mov     edi, eax
0x180068c56  mov     [rsp+128h+var_A8], eax
0x180068c5d  test    edi, edi
0x180068c5f  jns     short loc_180068CA8
0x180068c61  test    rsi, rsi
0x180068c64  jz      short loc_180068C7D
0x180068c66  mov     rax, [rsi]
0x180068c69  mov     edx, 1
0x180068c6e  mov     rcx, rsi
0x180068c71  mov     rax, [rax+88h]
0x180068c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c7d  test    r14d, r14d
0x180068c80  jz      short loc_180068CA8
0x180068c82  mov     rcx, [rsp+128h+var_50]; hKey
0x180068c8a  test    rcx, rcx
0x180068c8d  jz      short loc_180068C95
0x180068c8f  call    cs:__imp_RegCloseKey
0x180068c95  mov     rcx, [rsp+128h+hKey]; hKey
0x180068c9d  test    rcx, rcx
0x180068ca0  jz      short loc_180068CA8
0x180068ca2  call    cs:__imp_RegCloseKey
0x180068ca8  mov     eax, edi
0x180068caa  jmp     short loc_180068CB1
0x180068cac  mov     eax, 80070057h
0x180068cb1  mov     rcx, [rsp+128h+var_48]
0x180068cb9  xor     rcx, rsp; StackCookie
0x180068cbc  call    __security_check_cookie
0x180068cc1  add     rsp, 0F0h
0x180068cc8  pop     r15
0x180068cca  pop     r14
0x180068ccc  pop     r13
0x180068cce  pop     r12
0x180068cd0  pop     rdi
0x180068cd1  pop     rsi
0x180068cd2  pop     rbx
0x180068cd3  retn
0x1800b3cb8  push    rbp
0x1800b3cba  sub     rsp, 80h
0x1800b3cc1  mov     rbp, rdx
0x1800b3cc4  cmp     dword ptr [rbp+80h], 0
0x1800b3ccb  jge     short loc_1800B3D1D
0x1800b3ccd  mov     rcx, [rbp+0A0h]
0x1800b3cd4  test    rcx, rcx
0x1800b3cd7  jz      short loc_1800B3CEE
0x1800b3cd9  mov     rax, [rcx]
0x1800b3cdc  mov     edx, 1
0x1800b3ce1  mov     rax, [rax+88h]
0x1800b3ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ced  nop
0x1800b3cee  cmp     dword ptr [rbp+84h], 0
0x1800b3cf5  jz      short loc_1800B3D1D
0x1800b3cf7  mov     rcx, [rbp+0D8h]; hKey
0x1800b3cfe  test    rcx, rcx
0x1800b3d01  jz      short loc_1800B3D0A
0x1800b3d03  call    cs:__imp_RegCloseKey
0x1800b3d09  nop
0x1800b3d0a  mov     rcx, [rbp+0D0h]; hKey
0x1800b3d11  test    rcx, rcx
0x1800b3d14  jz      short loc_1800B3D1D
0x1800b3d16  call    cs:__imp_RegCloseKey
0x1800b3d1c  nop
0x1800b3d1d  add     rsp, 80h
0x1800b3d24  pop     rbp
0x1800b3d25  retn
```
