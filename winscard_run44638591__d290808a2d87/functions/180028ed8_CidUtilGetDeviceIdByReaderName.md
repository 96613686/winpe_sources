# CidUtilGetDeviceIdByReaderName

- ea: `0x180028ed8`
- end: `0x18002900f`
- name: `CidUtilGetDeviceIdByReaderName`
- size: `311`
- prototype: `__int64 __usercall@<rax>(LPCWSTR szReader@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002e84`
- `0x180024b4c`
- `0x180026fb0`

## callees

- `0x180006910`
- `0x180007f40`
- `0x180010c60`
- `0x180011b70`
- `0x180023640`
- `0x1800289ac`
- `0x180028ed8`

## pseudocode

```c
__int64 __fastcall CidUtilGetDeviceIdByReaderName(LPCWSTR szReader, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  SCARDHANDLE v5; // rbx
  SCARDCONTEXT v6; // rsi
  LONG v8; // eax
  unsigned int DeviceId; // edi
  LONG v10; // eax
  __int64 v11; // rbp
  DWORD v12; // r13d
  SCARDHANDLE hCard; // [rsp+30h] [rbp-58h] BYREF
  SCARDCONTEXT phContext[10]; // [rsp+38h] [rbp-50h] BYREF
  DWORD pdwActiveProtocol; // [rsp+98h] [rbp+10h] BYREF

  v5 = 0;
  v6 = 0;
  phContext[0] = 0;
  hCard = 0;
  pdwActiveProtocol = 0;
  if ( a2 && (unsigned int)(a3 - 2) <= 0x22 && a4 && szReader )
  {
    v8 = SCardEstablishContext(0, 0, 0, phContext);
    v6 = phContext[0];
    DeviceId = v8;
    if ( v8 )
      goto LABEL_14;
    v10 = SCardConnectW(phContext[0], szReader, 2u, 3u, &hCard, &pdwActiveProtocol);
    v5 = hCard;
    DeviceId = v10;
    if ( !v10 )
    {
      v11 = a5;
      v12 = pdwActiveProtocol;
      do
      {
        DeviceId = CidUtilGetDeviceId(v5, v11, v12);
        if ( DeviceId != -2146434968 )
          break;
        DeviceId = SCardReconnect(v5, 2u, 3u, 0, 0);
      }
      while ( !DeviceId );
    }
  }
  else
  {
    DeviceId = 87;
  }
  if ( v5 )
    SCardDisconnect(v5, 0);
LABEL_14:
  if ( v6 )
    SCardReleaseContext(v6);
  return DeviceId;
}

```

## disassembly

```asm
0x180028ed8  mov     rax, rsp
0x180028edb  push    rbx
0x180028edc  push    rbp
0x180028edd  push    rsi
0x180028ede  push    rdi
0x180028edf  push    r12
0x180028ee1  push    r13
0x180028ee3  push    r14
0x180028ee5  push    r15
0x180028ee7  sub     rsp, 48h
0x180028eeb  xor     ebx, ebx
0x180028eed  xor     esi, esi
0x180028eef  mov     [rax-50h], rsi
0x180028ef3  mov     r14, r9
0x180028ef6  mov     [rax-58h], rbx
0x180028efa  mov     r15d, r8d
0x180028efd  mov     [rax+10h], ebx
0x180028f00  mov     r12, rdx
0x180028f03  mov     rbp, rcx
0x180028f06  test    rdx, rdx
0x180028f09  jz      loc_180028FDB
0x180028f0f  lea     eax, [r8-2]
0x180028f13  cmp     eax, 22h ; '"'
0x180028f16  ja      loc_180028FDB
0x180028f1c  test    r9, r9
0x180028f1f  jz      loc_180028FDB
0x180028f25  test    rcx, rcx
0x180028f28  jz      loc_180028FDB
0x180028f2e  lea     r9, [rsp+88h+phContext]; phContext
0x180028f33  xor     r8d, r8d; pvReserved2
0x180028f36  xor     edx, edx; pvReserved1
0x180028f38  xor     ecx, ecx; dwScope
0x180028f3a  call    SCardEstablishContext
0x180028f3f  mov     rsi, [rsp+88h+phContext]
0x180028f44  mov     edi, eax
0x180028f46  test    eax, eax
0x180028f48  jnz     loc_180028FEF
0x180028f4e  lea     rax, [rsp+88h+arg_8]
0x180028f56  mov     rdx, rbp; szReader
0x180028f59  mov     [rsp+88h+pdwActiveProtocol], rax; pdwActiveProtocol
0x180028f5e  lea     r9d, [rbx+3]; dwPreferredProtocols
0x180028f62  lea     rax, [rsp+88h+hCard]
0x180028f67  mov     rcx, rsi; hContext
0x180028f6a  lea     r8d, [rbx+2]; dwShareMode
0x180028f6e  mov     [rsp+88h+phCard], rax; phCard
0x180028f73  call    SCardConnectW
0x180028f78  mov     rbx, [rsp+88h+hCard]
0x180028f7d  mov     edi, eax
0x180028f7f  test    eax, eax
0x180028f81  jnz     short loc_180028FE0
0x180028f83  mov     rbp, [rsp+88h+arg_20]
0x180028f8b  mov     r13d, [rsp+88h+arg_8]
0x180028f93  mov     dword ptr [rsp+88h+pdwActiveProtocol], r13d; int
0x180028f98  mov     r9, r14
0x180028f9b  mov     r8d, r15d
0x180028f9e  mov     [rsp+88h+phCard], rbp; __int64
0x180028fa3  mov     rdx, r12
0x180028fa6  mov     rcx, rbx; hCard
0x180028fa9  call    CidUtilGetDeviceId
0x180028fae  mov     edi, eax
0x180028fb0  cmp     eax, 80100068h
0x180028fb5  jnz     short loc_180028FE0
0x180028fb7  xor     r9d, r9d; dwInitialization
0x180028fba  mov     [rsp+88h+phCard], 0; pdwActiveProtocol
0x180028fc3  mov     rcx, rbx; hCard
0x180028fc6  lea     edx, [r9+2]; dwShareMode
0x180028fca  lea     r8d, [r9+3]; dwPreferredProtocols
0x180028fce  call    SCardReconnect
0x180028fd3  mov     edi, eax
0x180028fd5  test    eax, eax
0x180028fd7  jz      short loc_180028F93
0x180028fd9  jmp     short loc_180028FE0
0x180028fdb  mov     edi, 57h ; 'W'
0x180028fe0  test    rbx, rbx
0x180028fe3  jz      short loc_180028FEF
0x180028fe5  xor     edx, edx; dwDisposition
0x180028fe7  mov     rcx, rbx; hCard
0x180028fea  call    SCardDisconnect
0x180028fef  test    rsi, rsi
0x180028ff2  jz      short loc_180028FFC
0x180028ff4  mov     rcx, rsi; hContext
0x180028ff7  call    SCardReleaseContext
0x180028ffc  mov     eax, edi
0x180028ffe  add     rsp, 48h
0x180029002  pop     r15
0x180029004  pop     r14
0x180029006  pop     r13
0x180029008  pop     r12
0x18002900a  pop     rdi
0x18002900b  pop     rsi
0x18002900c  pop     rbp
0x18002900d  pop     rbx
0x18002900e  retn
```
