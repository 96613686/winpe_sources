# HbDrvGetHybridDiskInfo

- ea: `0x1800a1580`
- end: `0x1800a1907`
- name: `HbDrvGetHybridDiskInfo`
- size: `903`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x180064170`
- `0x18009f8a8`
- `0x1800a081c`
- `0x1800a2aa0`

## callees

- `0x1800076c4`
- `0x180078746`
- `0x1800a1580`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800a167c`
- `ntdll!NtOpenFile` at `0x1800a167c`
- `ntdll!RtlInitUnicodeString` at `0x1800a1628`
- `ntdll!RtlInitUnicodeString` at `0x1800a1628`
- `ntdll!RtlNtStatusToDosError` at `0x1800a1688`
- `ntdll!RtlNtStatusToDosError` at `0x1800a1688`
- `ntdll!NtClose` at `0x1800a18dc`
- `ntdll!NtClose` at `0x1800a18dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a17d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a17d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a16b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a18af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a18c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a16b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a18af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a18c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a16c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1803`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a16c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a1803`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a175e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a17cc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a175e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a17cc`

## pseudocode

```c
__int64 __fastcall HbDrvGetHybridDiskInfo(__int64 a1, _QWORD *a2, _QWORD *a3, _BYTE *a4, _DWORD *a5, _DWORD *a6)
{
  __int64 v7; // rdx
  int v9; // eax
  DWORD LastError; // ebx
  _DWORD *v11; // rdi
  DWORD i; // esi
  _DWORD *v13; // rax
  unsigned int v14; // ecx
  _QWORD *v15; // rax
  _QWORD *v16; // rsi
  int v17; // edx
  _QWORD *v18; // rcx
  __int64 v19; // rax
  char v20; // cl
  unsigned int v21; // r8d
  unsigned int v22; // edx
  unsigned int v23; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v27; // [rsp+50h] [rbp-B0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  _QWORD InBuffer[2]; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD OutBuffer[2]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR SourceString[264]; // [rsp+E0h] [rbp-20h] BYREF

  v27 = a3;
  v7 = *(_QWORD *)(a1 + 8);
  memset(OutBuffer, 0, 28);
  BytesReturned = 0;
  memset(&ObjectAttributes.ObjectName, 0, 32);
  memset(InBuffer, 0, 12);
  FileHandle = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  IoStatusBlock = 0;
  PfScStringCopy(*(_QWORD *)&PfSvcGlobals + 96LL, *(_QWORD *)(v7 + 16), SourceString, 260);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  v9 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  if ( v9 >= 0 )
  {
    v11 = 0;
    for ( i = 272; ; i *= 2 )
    {
      if ( v11 )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v11);
      v13 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, i);
      v11 = v13;
      if ( !v13 )
        break;
      memset_0(v13, 0, i);
      *v11 = 28;
      v11[6] = i - 28;
      LastError = 0;
      v11[3] = 30;
      v11[4] = 1771040;
      *(_QWORD *)(v11 + 1) = 0x4B53494452425948LL;
      v11[8] = 24;
      v11[7] = 1;
      v11[9] = 1;
      v14 = (*v11 + 31) & 0xFFFFFFF8;
      v11[11] = v14;
      v11[12] = i - v14;
      if ( DeviceIoControl(FileHandle, 0x4D008u, v11, i, v11, i, &BytesReturned, 0) )
      {
        memset(OutBuffer, 0, 28);
        *(_QWORD *)((char *)InBuffer + 4) = 0;
        LODWORD(InBuffer[0]) = 6;
        if ( DeviceIoControl(FileHandle, 0x2D1400u, InBuffer, 0xCu, OutBuffer, 0x1Cu, &BytesReturned, 0) )
        {
          if ( LODWORD(OutBuffer[1]) )
          {
            v15 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, (unsigned int)v11[12]);
            v16 = v15;
            if ( v15 )
            {
              memcpy_0(v15, (char *)v11 + (unsigned int)v11[11], (unsigned int)v11[12]);
              if ( v16[4] && *((_DWORD *)v16 + 6) && *((_BYTE *)v16 + 44) )
              {
                v17 = OutBuffer[1];
                v18 = v27;
                v19 = LODWORD(OutBuffer[1]);
                *a2 = v16;
                *v18 = v16[4] * v19;
                if ( a5 )
                  *a5 = v17;
                if ( a4 )
                {
                  v20 = *((_BYTE *)v16 + 46);
                  v21 = 0x10000;
                  if ( (unsigned __int8)(v20 - 1) <= 0xFDu )
                  {
                    v22 = v17 << v20;
                    if ( v22 <= 0x40000 )
                    {
                      if ( v22 < 0x10000 )
                        v22 = 0x10000;
                      v21 = v22;
                    }
                    else
                    {
                      v21 = 0x40000;
                    }
                  }
                  _BitScanForward(&v23, v21);
                  *a4 = v23;
                }
                if ( a6 )
                  *a6 = 0;
              }
              else
              {
                LastError = 11;
                HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v16);
              }
            }
            else
            {
              LastError = 8;
            }
          }
          else
          {
            LastError = 15;
          }
        }
        else
        {
          LastError = GetLastError();
        }
LABEL_32:
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v11);
        goto LABEL_34;
      }
      LastError = GetLastError();
      if ( LastError != 234 )
        goto LABEL_32;
    }
    LastError = 8;
  }
  else
  {
    LastError = RtlNtStatusToDosError(v9);
  }
LABEL_34:
  if ( FileHandle )
    NtClose(FileHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800a1580  push    rbp
0x1800a1582  push    rbx
0x1800a1583  push    rsi
0x1800a1584  push    rdi
0x1800a1585  push    r12
0x1800a1587  push    r13
0x1800a1589  push    r14
0x1800a158b  push    r15
0x1800a158d  lea     rbp, [rsp-208h]
0x1800a1595  sub     rsp, 308h
0x1800a159c  mov     rax, cs:__security_cookie
0x1800a15a3  xor     rax, rsp
0x1800a15a6  mov     [rbp+240h+var_50], rax
0x1800a15ad  mov     r15, [rbp+240h+arg_20]
0x1800a15b4  xorps   xmm0, xmm0
0x1800a15b7  mov     r14, [rbp+240h+arg_28]
0x1800a15be  xor     eax, eax
0x1800a15c0  mov     r13, rdx
0x1800a15c3  mov     [rsp+340h+var_2F0], r8
0x1800a15c8  mov     rdx, [rcx+8]
0x1800a15cc  lea     r8, [rbp+240h+SourceString]
0x1800a15d0  mov     rcx, cs:PfSvcGlobals
0x1800a15d7  mov     r12, r9
0x1800a15da  movups  [rbp+240h+OutBuffer], xmm0
0x1800a15de  mov     [rsp+340h+BytesReturned], 0
0x1800a15e6  add     rcx, 60h ; '`'
0x1800a15ea  movups  xmmword ptr [rsp+340h+ObjectAttributes.ObjectName], xmm0
0x1800a15ef  mov     [rbp+240h+InBuffer], rax
0x1800a15f3  mov     r9d, 104h
0x1800a15f9  mov     [rbp+240h+var_290], eax
0x1800a15fc  movups  [rbp+240h+OutBuffer+0Ch], xmm0
0x1800a1600  mov     [rsp+340h+FileHandle], rax
0x1800a1605  movups  xmmword ptr [rbp+240h+DestinationString.Length], xmm0
0x1800a1609  movups  xmmword ptr [rsp+340h+ObjectAttributes.Length], xmm0
0x1800a160e  movups  xmmword ptr [rsp+340h+ObjectAttributes+1Ch], xmm0
0x1800a1613  movups  xmmword ptr [rbp+240h+IoStatusBlock], xmm0
0x1800a1617  mov     rdx, [rdx+10h]
0x1800a161b  call    PfScStringCopy
0x1800a1620  lea     rdx, [rbp+240h+SourceString]; SourceString
0x1800a1624  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x1800a1628  call    cs:__imp_RtlInitUnicodeString
0x1800a162e  lea     rax, [rbp+240h+DestinationString]
0x1800a1632  mov     [rsp+340h+OpenOptions], 0; OpenOptions
0x1800a163a  xorps   xmm0, xmm0
0x1800a163d  mov     [rsp+340h+ObjectAttributes.ObjectName], rax
0x1800a1642  lea     r9, [rbp+240h+IoStatusBlock]; IoStatusBlock
0x1800a1646  mov     [rsp+340h+ObjectAttributes.Length], 30h ; '0'
0x1800a164e  lea     r8, [rsp+340h+ObjectAttributes]; ObjectAttributes
0x1800a1653  mov     [rsp+340h+ObjectAttributes.RootDirectory], 0
0x1800a165c  mov     edx, 12019Fh; DesiredAccess
0x1800a1661  mov     [rsp+340h+ObjectAttributes.Attributes], 40h ; '@'
0x1800a1669  lea     rcx, [rsp+340h+FileHandle]; FileHandle
0x1800a166e  mov     [rsp+340h+ShareAccess], 7; ShareAccess
0x1800a1676  movdqu  xmmword ptr [rsp+340h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a167c  call    cs:__imp_NtOpenFile
0x1800a1682  test    eax, eax
0x1800a1684  jns     short loc_1800A1695
0x1800a1686  mov     ecx, eax; Status
0x1800a1688  call    cs:__imp_RtlNtStatusToDosError
0x1800a168e  mov     ebx, eax
0x1800a1690  jmp     loc_1800A18D2
0x1800a1695  xor     edi, edi
0x1800a1697  mov     esi, 110h
0x1800a169c  test    rdi, rdi
0x1800a169f  jz      short loc_1800A16B7
0x1800a16a1  mov     rcx, cs:PfSvcGlobals
0x1800a16a8  mov     r8, rdi; lpMem
0x1800a16ab  xor     edx, edx; dwFlags
0x1800a16ad  mov     rcx, [rcx+58h]; hHeap
0x1800a16b1  call    cs:__imp_HeapFree
0x1800a16b7  mov     rcx, cs:PfSvcGlobals
0x1800a16be  xor     edx, edx; dwFlags
0x1800a16c0  mov     r8d, esi; dwBytes
0x1800a16c3  mov     ebx, esi
0x1800a16c5  mov     rcx, [rcx+58h]; hHeap
0x1800a16c9  call    cs:__imp_HeapAlloc
0x1800a16cf  mov     rdi, rax
0x1800a16d2  test    rax, rax
0x1800a16d5  jz      loc_1800A18CD
0x1800a16db  mov     r8d, ebx; Size
0x1800a16de  xor     edx, edx; Val
0x1800a16e0  mov     rcx, rax; void *
0x1800a16e3  call    memset_0
0x1800a16e8  mov     dword ptr [rdi], 1Ch
0x1800a16ee  lea     eax, [rsi-1Ch]
0x1800a16f1  mov     [rdi+18h], eax
0x1800a16f4  xor     ebx, ebx
0x1800a16f6  mov     dword ptr [rdi+0Ch], 1Eh
0x1800a16fd  mov     rax, 4B53494452425948h
0x1800a1707  mov     dword ptr [rdi+10h], 1B0620h
0x1800a170e  mov     r9d, esi; nInBufferSize
0x1800a1711  mov     [rdi+4], rax
0x1800a1715  mov     r8, rdi; lpInBuffer
0x1800a1718  mov     eax, 1
0x1800a171d  mov     dword ptr [rdi+20h], 18h
0x1800a1724  mov     [rdi+1Ch], eax
0x1800a1727  mov     edx, 4D008h; dwIoControlCode
0x1800a172c  mov     [rdi+24h], eax
0x1800a172f  mov     eax, esi
0x1800a1731  mov     ecx, [rdi]
0x1800a1733  add     ecx, 1Fh
0x1800a1736  mov     [rsp+340h+lpOverlapped], rbx; lpOverlapped
0x1800a173b  and     ecx, 0FFFFFFF8h
0x1800a173e  sub     eax, ecx
0x1800a1740  mov     [rdi+2Ch], ecx
0x1800a1743  mov     [rdi+30h], eax
0x1800a1746  lea     rax, [rsp+340h+BytesReturned]
0x1800a174b  mov     rcx, [rsp+340h+FileHandle]; hDevice
0x1800a1750  mov     [rsp+340h+lpBytesReturned], rax; lpBytesReturned
0x1800a1755  mov     [rsp+340h+OpenOptions], esi; nOutBufferSize
0x1800a1759  mov     qword ptr [rsp+340h+ShareAccess], rdi; lpOutBuffer
0x1800a175e  call    cs:__imp_DeviceIoControl
0x1800a1764  test    eax, eax
0x1800a1766  jnz     short loc_1800A1782
0x1800a1768  call    cs:__imp_GetLastError
0x1800a176e  mov     ebx, eax
0x1800a1770  cmp     eax, 0EAh
0x1800a1775  jnz     loc_1800A18B5
0x1800a177b  add     esi, esi
0x1800a177d  jmp     loc_1800A169C
0x1800a1782  mov     rcx, [rsp+340h+FileHandle]; hDevice
0x1800a1787  lea     rax, [rsp+340h+BytesReturned]
0x1800a178c  mov     [rsp+340h+lpOverlapped], rbx; lpOverlapped
0x1800a1791  lea     r8, [rbp+240h+InBuffer]; lpInBuffer
0x1800a1795  mov     [rsp+340h+lpBytesReturned], rax; lpBytesReturned
0x1800a179a  xorps   xmm0, xmm0
0x1800a179d  lea     rax, [rbp+240h+OutBuffer]
0x1800a17a1  mov     [rsp+340h+OpenOptions], 1Ch; nOutBufferSize
0x1800a17a9  movups  [rbp+240h+OutBuffer], xmm0
0x1800a17ad  mov     r9d, 0Ch; nInBufferSize
0x1800a17b3  mov     qword ptr [rsp+340h+ShareAccess], rax; lpOutBuffer
0x1800a17b8  mov     edx, 2D1400h; dwIoControlCode
0x1800a17bd  mov     [rbp+240h+InBuffer+4], rbx
0x1800a17c1  movups  [rbp+240h+OutBuffer+0Ch], xmm0
0x1800a17c5  mov     dword ptr [rbp+240h+InBuffer], 6
0x1800a17cc  call    cs:__imp_DeviceIoControl
0x1800a17d2  test    eax, eax
0x1800a17d4  jnz     short loc_1800A17E3
0x1800a17d6  call    cs:__imp_GetLastError
0x1800a17dc  mov     ebx, eax
0x1800a17de  jmp     loc_1800A18B5
0x1800a17e3  cmp     [rbp+240h+var_278], ebx
0x1800a17e6  jnz     short loc_1800A17F2
0x1800a17e8  mov     ebx, 0Fh
0x1800a17ed  jmp     loc_1800A18B5
0x1800a17f2  mov     rcx, cs:PfSvcGlobals
0x1800a17f9  xor     edx, edx; dwFlags
0x1800a17fb  mov     r8d, [rdi+30h]; dwBytes
0x1800a17ff  mov     rcx, [rcx+58h]; hHeap
0x1800a1803  call    cs:__imp_HeapAlloc
0x1800a1809  mov     rsi, rax
0x1800a180c  test    rax, rax
0x1800a180f  jnz     short loc_1800A1819
0x1800a1811  lea     ebx, [rax+8]
0x1800a1814  jmp     loc_1800A18B5
0x1800a1819  mov     edx, [rdi+2Ch]
0x1800a181c  mov     rcx, rsi; void *
0x1800a181f  mov     r8d, [rdi+30h]; Size
0x1800a1823  add     rdx, rdi; Src
0x1800a1826  call    memcpy_0
0x1800a182b  cmp     [rsi+20h], rbx
0x1800a182f  jz      short loc_1800A189A
0x1800a1831  cmp     [rsi+18h], ebx
0x1800a1834  jz      short loc_1800A189A
0x1800a1836  cmp     [rsi+2Ch], bl
0x1800a1839  jz      short loc_1800A189A
0x1800a183b  mov     edx, [rbp+240h+var_278]
0x1800a183e  mov     rcx, [rsp+340h+var_2F0]
0x1800a1843  mov     eax, edx
0x1800a1845  mov     [r13+0], rsi
0x1800a1849  imul    rax, [rsi+20h]
0x1800a184e  mov     [rcx], rax
0x1800a1851  test    r15, r15
0x1800a1854  jz      short loc_1800A1859
0x1800a1856  mov     [r15], edx
0x1800a1859  test    r12, r12
0x1800a185c  jz      short loc_1800A1890
0x1800a185e  mov     cl, [rsi+2Eh]
0x1800a1861  mov     r8d, 10000h
0x1800a1867  lea     eax, [rcx-1]
0x1800a186a  cmp     al, 0FDh
0x1800a186c  ja      short loc_1800A1888
0x1800a186e  shl     edx, cl
0x1800a1870  mov     eax, 40000h
0x1800a1875  cmp     edx, eax
0x1800a1877  jbe     short loc_1800A187E
0x1800a1879  mov     r8d, eax
0x1800a187c  jmp     short loc_1800A1888
0x1800a187e  cmp     edx, r8d
0x1800a1881  cmovb   edx, r8d
0x1800a1885  mov     r8d, edx
0x1800a1888  bsf     eax, r8d
0x1800a188c  mov     [r12], al
0x1800a1890  test    r14, r14
0x1800a1893  jz      short loc_1800A18B5
0x1800a1895  mov     [r14], ebx
0x1800a1898  jmp     short loc_1800A18B5
0x1800a189a  mov     ebx, 0Bh
0x1800a189f  mov     rcx, cs:PfSvcGlobals
0x1800a18a6  mov     r8, rsi; lpMem
0x1800a18a9  xor     edx, edx; dwFlags
0x1800a18ab  mov     rcx, [rcx+58h]; hHeap
0x1800a18af  call    cs:__imp_HeapFree
0x1800a18b5  mov     rcx, cs:PfSvcGlobals
0x1800a18bc  mov     r8, rdi; lpMem
0x1800a18bf  xor     edx, edx; dwFlags
0x1800a18c1  mov     rcx, [rcx+58h]; hHeap
0x1800a18c5  call    cs:__imp_HeapFree
0x1800a18cb  jmp     short loc_1800A18D2
0x1800a18cd  mov     ebx, 8
0x1800a18d2  mov     rcx, [rsp+340h+FileHandle]; Handle
0x1800a18d7  test    rcx, rcx
0x1800a18da  jz      short loc_1800A18E2
0x1800a18dc  call    cs:__imp_NtClose
0x1800a18e2  mov     eax, ebx
0x1800a18e4  mov     rcx, [rbp+240h+var_50]
0x1800a18eb  xor     rcx, rsp; StackCookie
0x1800a18ee  call    __security_check_cookie
0x1800a18f3  add     rsp, 308h
0x1800a18fa  pop     r15
0x1800a18fc  pop     r14
0x1800a18fe  pop     r13
0x1800a1900  pop     r12
0x1800a1902  pop     rdi
0x1800a1903  pop     rsi
0x1800a1904  pop     rbx
0x1800a1905  pop     rbp
0x1800a1906  retn
```
