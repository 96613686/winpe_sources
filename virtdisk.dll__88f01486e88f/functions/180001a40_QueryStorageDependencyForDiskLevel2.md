# QueryStorageDependencyForDiskLevel2

- ea: `0x180001a40`
- end: `0x180001fff`
- name: `QueryStorageDependencyForDiskLevel2`
- size: `1471`
- prototype: `DWORD __fastcall(HANDLE hDevice, unsigned int, char *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001a40`
- `0x180002010`
- `0x180005730`
- `0x180009934`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ceb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001ab9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001bb7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001ab9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001bb7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180001e56`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180001e56`
- `ntdll!RtlFreeHeap` at `0x180001c12`
- `ntdll!RtlFreeHeap` at `0x180001c48`
- `ntdll!RtlFreeHeap` at `0x180001d15`
- `ntdll!RtlFreeHeap` at `0x180001fd4`
- `ntdll!RtlFreeHeap` at `0x180001c12`
- `ntdll!RtlFreeHeap` at `0x180001c48`
- `ntdll!RtlFreeHeap` at `0x180001d15`
- `ntdll!RtlFreeHeap` at `0x180001fd4`
- `ntdll!RtlAllocateHeap` at `0x180001b74`
- `ntdll!RtlAllocateHeap` at `0x180001b74`

## pseudocode

```c
DWORD __fastcall QueryStorageDependencyForDiskLevel2(HANDLE hDevice, unsigned int a2, char *a3, unsigned int *a4)
{
  __int64 v4; // r13
  char *v5; // r12
  HRESULT v7; // eax
  __int64 v8; // rbx
  bool v9; // zf
  DWORD nOutBufferSize; // ebp
  unsigned __int64 *lpOutBuffer; // rsi
  DWORD LastError; // eax
  int v13; // edi
  unsigned __int64 v14; // rax
  unsigned __int64 *v15; // rbp
  size_t v17; // r8
  int v18; // ecx
  unsigned int v19; // edx
  unsigned __int64 v20; // r13
  char *v21; // rdi
  unsigned __int64 v22; // rax
  char *v23; // rbx
  char *v24; // r14
  char *v25; // r12
  _WORD *v26; // rsi
  unsigned __int64 v27; // r15
  unsigned __int64 v28; // rbx
  unsigned __int64 i; // rbx
  SIZE_T v30; // rax
  __int64 v31; // rax
  char *v32; // r14
  char *v33; // r12
  unsigned __int64 v34; // r15
  char *v35; // r14
  int v36; // ebx
  unsigned int v37; // edi
  int v38; // [rsp+40h] [rbp-2D8h]
  size_t v39; // [rsp+48h] [rbp-2D0h]
  char *v40; // [rsp+50h] [rbp-2C8h]
  DWORD BytesReturned; // [rsp+58h] [rbp-2C0h] BYREF
  DWORD lpBytesReturned; // [rsp+5Ch] [rbp-2BCh] BYREF
  int InBuffer; // [rsp+60h] [rbp-2B8h] BYREF
  unsigned int v44; // [rsp+64h] [rbp-2B4h]
  unsigned int *v45; // [rsp+68h] [rbp-2B0h]
  char *v46; // [rsp+70h] [rbp-2A8h]
  __int64 OutBuffer; // [rsp+78h] [rbp-2A0h] BYREF
  int v48; // [rsp+80h] [rbp-298h]
  wchar_t pszDest[28]; // [rsp+88h] [rbp-290h] BYREF
  WCHAR Src[264]; // [rsp+C0h] [rbp-258h] BYREF

  v4 = a2;
  OutBuffer = 0;
  v48 = 0;
  v5 = a3;
  v45 = a4;
  v46 = a3;
  v44 = a2;
  BytesReturned = 0;
  if ( !DeviceIoControl(hDevice, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
    return GetLastError();
  if ( HIDWORD(OutBuffer) > 0x5F5E0FF )
    return 50;
  if ( (_DWORD)OutBuffer == 7 || (_DWORD)OutBuffer == 36 )
  {
    v7 = StringCchPrintfW(pszDest, 0x1Au, L"\\\\.\\PHYSICALDRIVE%u");
    goto LABEL_5;
  }
  if ( (_DWORD)OutBuffer != 2 )
    return 50;
  v7 = StringCchPrintfW(pszDest, 0x1Au, L"\\\\.\\CDROM%u");
LABEL_5:
  if ( v7 < 0 )
    return GetLastError();
  v8 = -1;
  do
    v9 = pszDest[++v8] == 0;
  while ( !v9 );
  lpBytesReturned = 0;
  nOutBufferSize = 72;
  InBuffer = 2;
  while ( 1 )
  {
    lpOutBuffer = (unsigned __int64 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, nOutBufferSize);
    if ( !lpOutBuffer )
      return 14;
    if ( DeviceIoControl(hDevice, 0x2D118Cu, &InBuffer, 4u, lpOutBuffer, nOutBufferSize, &lpBytesReturned, 0) )
      goto LABEL_15;
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError != 122 && LastError != 234 || (v14 = lpOutBuffer[1], v14 <= nOutBufferSize) )
    {
      if ( v13 == 1 || v13 == 87 || v13 == 50 || v13 == 120 || v13 == -2147467263 )
      {
        *((_DWORD *)lpOutBuffer + 1) = 0;
LABEL_15:
        if ( !*((_DWORD *)lpOutBuffer + 1) )
        {
          v13 = -1069940715;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpOutBuffer);
          return v13;
        }
        v15 = lpOutBuffer;
      }
      else
      {
LABEL_19:
        v15 = 0;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpOutBuffer);
        if ( v13 )
          return v13;
      }
      *(_DWORD *)v5 = 2;
      v17 = 2 * v8 + 2;
      v18 = *((_DWORD *)v15 + 1);
      v19 = 0;
      *((_DWORD *)v5 + 1) = v18;
      v20 = (unsigned __int64)&v5[v4];
      v39 = v17;
      v21 = &v5[64 * (unsigned __int64)*((unsigned int *)v15 + 1) + 8];
      v38 = 0;
      if ( v18 )
      {
        while ( 2 )
        {
          v22 = (unsigned __int64)v19 << 6;
          v23 = &v5[v22];
          v40 = &v5[v22];
          v24 = (char *)v15 + v22;
          if ( (unsigned __int64)&v5[v22 + 72] <= v20 )
          {
            *((_DWORD *)v23 + 2) = *((_DWORD *)v24 + 2);
            *((_DWORD *)v23 + 3) = *((_DWORD *)v24 + 3);
            *((_DWORD *)v23 + 9) = *((_DWORD *)v24 + 14);
            *((_OWORD *)v23 + 1) = *((_OWORD *)v24 + 1);
            *((_DWORD *)v23 + 8) = *((_DWORD *)v24 + 8);
          }
          v25 = &v21[v17];
          if ( (unsigned __int64)&v21[v17] <= v20 )
          {
            memcpy_0(v21, pszDest, v17);
            v19 = v38;
            v17 = v39;
            *((_QWORD *)v23 + 5) = v21;
          }
          v21 = v25;
          v26 = (_WORD *)((char *)v15 + *((unsigned int *)v24 + 15));
          v27 = (unsigned __int64)*((unsigned int *)v24 + 16) >> 1;
          if ( v27 >= 2 && *v26 == 92 && v26[1] == 92 )
          {
            v28 = 2;
            if ( v26[2] != 92 )
            {
              do
              {
                if ( v28 >= v27 )
                  break;
                ++v28;
              }
              while ( v26[v28] != 92 );
            }
            for ( i = v28 + 1; v26[i] != 92; ++i )
            {
              if ( i >= v27 )
                break;
            }
            goto LABEL_63;
          }
          if ( v27 < 8 )
          {
            if ( v27 >= 4 )
              goto LABEL_54;
          }
          else
          {
            v30 = RtlCompareMemory((char *)v15 + *((unsigned int *)v24 + 15), L"\\Device\\", 8u);
            v19 = v38;
            v17 = v39;
            if ( v30 == 8 )
            {
              i = 8;
              goto LABEL_60;
            }
LABEL_54:
            if ( *v26 == 92 && v26[1] == 63 && v26[2] == 63 && v26[3] == 92 )
            {
              i = 4;
              goto LABEL_60;
            }
          }
          i = 0;
LABEL_60:
          while ( i < v27 )
          {
            if ( v26[i] == 92 )
              break;
            ++i;
          }
LABEL_63:
          if ( i && 2 * i <= 0xFFFFFFFF )
          {
            GetVolumeNameFromNtVolumeName(v26, (unsigned int)(2 * i), Src);
            v31 = -1;
            do
              v9 = Src[++v31] == 0;
            while ( !v9 );
            v32 = &v25[2 * v31 + 2];
            if ( (unsigned __int64)v32 > v20 )
            {
              v33 = v40;
            }
            else
            {
              memcpy_0(v25, Src, 2 * v31);
              v33 = v40;
              *((_WORD *)v32 - 1) = 0;
              *((_QWORD *)v40 + 6) = v21;
            }
            v19 = v38;
            v21 = v32;
            v17 = v39;
          }
          else
          {
            v33 = v40;
          }
          if ( i < v27 )
          {
            v34 = v27 - i;
            v35 = &v21[2 * v34 + 2];
            if ( (unsigned __int64)v35 <= v20 )
            {
              memcpy_0(v21, &v26[i], 2 * v34);
              v19 = v38;
              v17 = v39;
              *((_WORD *)v35 - 1) = 0;
              *((_QWORD *)v33 + 8) = v21;
            }
            v21 += 2 * v34 + 2;
          }
          v5 = v46;
          v38 = ++v19;
          if ( v19 >= *((_DWORD *)v46 + 1) )
            break;
          continue;
        }
      }
      if ( (unsigned __int64)(v21 - v5) > 0xFFFFFFFF )
      {
        if ( v45 )
          *v45 = -1;
        goto LABEL_80;
      }
      v37 = (_DWORD)v21 - (_DWORD)v5;
      if ( v45 )
        *v45 = v37;
      if ( v44 >= v37 && v37 )
        v36 = 0;
      else
LABEL_80:
        v36 = 122;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      return v36;
    }
    nOutBufferSize = lpOutBuffer[1];
    if ( v14 != (unsigned int)v14 )
      goto LABEL_19;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpOutBuffer);
  }
}

```

## disassembly

```asm
0x180001a40  push    rdi
0x180001a42  push    r12
0x180001a44  push    r13
0x180001a46  push    r15
0x180001a48  sub     rsp, 2F8h
0x180001a4f  mov     rax, cs:__security_cookie
0x180001a56  xor     rax, rsp
0x180001a59  mov     [rsp+318h+var_48], rax
0x180001a61  xor     eax, eax
0x180001a63  mov     r13d, edx
0x180001a66  mov     [rsp+318h+OutBuffer], rax
0x180001a6b  xor     edi, edi
0x180001a6d  mov     [rsp+318h+var_298], eax
0x180001a74  mov     r12, r8
0x180001a77  mov     [rsp+318h+lpOverlapped], rdi; lpOverlapped
0x180001a7c  lea     rax, [rsp+318h+BytesReturned]
0x180001a81  mov     [rsp+318h+lpBytesReturned], rax; lpBytesReturned
0x180001a86  mov     edx, 2D1080h; dwIoControlCode
0x180001a8b  lea     rax, [rsp+318h+OutBuffer]
0x180001a90  mov     [rsp+318h+var_2B0], r9
0x180001a95  mov     [rsp+318h+var_2A8], r8
0x180001a9a  xor     r9d, r9d; nInBufferSize
0x180001a9d  mov     [rsp+318h+nOutBufferSize], 0Ch; nOutBufferSize
0x180001aa5  xor     r8d, r8d; lpInBuffer
0x180001aa8  mov     [rsp+318h+lpOutBuffer], rax; lpOutBuffer
0x180001aad  mov     r15, rcx
0x180001ab0  mov     [rsp+318h+var_2B4], r13d
0x180001ab5  mov     [rsp+318h+BytesReturned], edi
0x180001ab9  call    cs:__imp_DeviceIoControl
0x180001ac0  nop     dword ptr [rax+rax+00h]
0x180001ac5  test    eax, eax
0x180001ac7  jz      loc_180001CEB
0x180001acd  mov     r9d, dword ptr [rsp+318h+OutBuffer+4]
0x180001ad2  cmp     r9d, 5F5E0FFh
0x180001ad9  ja      loc_180001CF9
0x180001adf  mov     eax, dword ptr [rsp+318h+OutBuffer]
0x180001ae3  cmp     eax, 7
0x180001ae6  jnz     loc_180001CD1
0x180001aec  lea     r8, aPhysicaldriveU; "\\\\.\\PHYSICALDRIVE%u"
0x180001af3  mov     edx, 1Ah; cchDest
0x180001af8  lea     rcx, [rsp+318h+pszDest]; pszDest
0x180001b00  call    StringCchPrintfW
0x180001b05  test    eax, eax
0x180001b07  js      loc_180001CEB
0x180001b0d  mov     [rsp+318h+arg_8], rbx
0x180001b15  lea     rax, [rsp+318h+pszDest]
0x180001b1d  mov     [rsp+318h+var_28], rbp
0x180001b25  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001b2c  mov     [rsp+318h+var_30], rsi
0x180001b34  mov     [rsp+318h+var_38], r14
0x180001b3c  nop     dword ptr [rax+00h]
0x180001b40  cmp     [rax+rbx*2+2], di
0x180001b45  lea     rbx, [rbx+1]
0x180001b49  jnz     short loc_180001B40
0x180001b4b  mov     [rsp+318h+var_2BC], edi
0x180001b4f  mov     ebp, 48h ; 'H'
0x180001b54  mov     [rsp+318h+InBuffer], 2
0x180001b5c  mov     rcx, gs:60h
0x180001b65  mov     edx, 8; Flags
0x180001b6a  mov     r8d, ebp; Size
0x180001b6d  mov     r14d, ebp
0x180001b70  mov     rcx, [rcx+30h]; HeapHandle
0x180001b74  call    cs:__imp_RtlAllocateHeap
0x180001b7b  nop     dword ptr [rax+rax+00h]
0x180001b80  mov     rsi, rax
0x180001b83  test    rax, rax
0x180001b86  jz      loc_180001C9E
0x180001b8c  mov     [rsp+318h+lpOverlapped], rdi; lpOverlapped
0x180001b91  lea     rax, [rsp+318h+var_2BC]
0x180001b96  mov     [rsp+318h+lpBytesReturned], rax; lpBytesReturned
0x180001b9b  lea     r8, [rsp+318h+InBuffer]; lpInBuffer
0x180001ba0  mov     [rsp+318h+nOutBufferSize], ebp; nOutBufferSize
0x180001ba4  mov     r9d, 4; nInBufferSize
0x180001baa  mov     edx, 2D118Ch; dwIoControlCode
0x180001baf  mov     [rsp+318h+lpOutBuffer], rsi; lpOutBuffer
0x180001bb4  mov     rcx, r15; hDevice
0x180001bb7  call    cs:__imp_DeviceIoControl
0x180001bbe  nop     dword ptr [rax+rax+00h]
0x180001bc3  test    eax, eax
0x180001bc5  jnz     short loc_180001BF1
0x180001bc7  call    cs:__imp_GetLastError
0x180001bce  nop     dword ptr [rax+rax+00h]
0x180001bd3  mov     edi, eax
0x180001bd5  cmp     eax, 7Ah ; 'z'
0x180001bd8  jz      short loc_180001C20
0x180001bda  cmp     eax, 0EAh
0x180001bdf  jz      short loc_180001C20
0x180001be1  cmp     edi, 1
0x180001be4  jnz     loc_180001CA5
0x180001bea  mov     dword ptr [rsi+4], 0
0x180001bf1  cmp     dword ptr [rsi+4], 0
0x180001bf5  jnz     loc_180001D28
0x180001bfb  mov     rcx, gs:60h
0x180001c04  mov     r8, rsi; P
0x180001c07  xor     edx, edx; Flags
0x180001c09  mov     edi, 0C03A0015h
0x180001c0e  mov     rcx, [rcx+30h]; HeapHandle
0x180001c12  call    cs:__imp_RtlFreeHeap
0x180001c19  nop     dword ptr [rax+rax+00h]
0x180001c1e  jmp     short loc_180001C5C
0x180001c20  mov     rax, [rsi+8]
0x180001c24  cmp     rax, r14
0x180001c27  jbe     short loc_180001BE1
0x180001c29  mov     ebp, eax
0x180001c2b  cmp     rax, rbp
0x180001c2e  jz      loc_180001D03
0x180001c34  mov     rcx, gs:60h
0x180001c3d  mov     r8, rsi; P
0x180001c40  xor     edx, edx; Flags
0x180001c42  xor     ebp, ebp
0x180001c44  mov     rcx, [rcx+30h]; HeapHandle
0x180001c48  call    cs:__imp_RtlFreeHeap
0x180001c4f  nop     dword ptr [rax+rax+00h]
0x180001c54  test    edi, edi
0x180001c56  jz      loc_180001D2B
0x180001c5c  mov     eax, edi
0x180001c5e  mov     rsi, [rsp+318h+var_30]
0x180001c66  mov     rbp, [rsp+318h+var_28]
0x180001c6e  mov     rbx, [rsp+318h+arg_8]
0x180001c76  mov     r14, [rsp+318h+var_38]
0x180001c7e  mov     rcx, [rsp+318h+var_48]
0x180001c86  xor     rcx, rsp; StackCookie
0x180001c89  call    __security_check_cookie
0x180001c8e  add     rsp, 2F8h
0x180001c95  pop     r15
0x180001c97  pop     r13
0x180001c99  pop     r12
0x180001c9b  pop     rdi
0x180001c9c  retn
0x180001c9e  mov     edi, 0Eh
0x180001ca3  jmp     short loc_180001C5C
0x180001ca5  cmp     edi, 57h ; 'W'
0x180001ca8  jz      loc_180001BEA
0x180001cae  cmp     edi, 32h ; '2'
0x180001cb1  jz      loc_180001BEA
0x180001cb7  cmp     edi, 78h ; 'x'
0x180001cba  jz      loc_180001BEA
0x180001cc0  cmp     edi, 80004001h
0x180001cc6  jz      loc_180001BEA
0x180001ccc  jmp     loc_180001C34
0x180001cd1  cmp     eax, 24h ; '$'
0x180001cd4  jz      loc_180001AEC
0x180001cda  cmp     eax, 2
0x180001cdd  jnz     short loc_180001CF9
0x180001cdf  lea     r8, aCdromU; "\\\\.\\CDROM%u"
0x180001ce6  jmp     loc_180001AF3
0x180001ceb  call    cs:__imp_GetLastError
0x180001cf2  nop     dword ptr [rax+rax+00h]
0x180001cf7  jmp     short loc_180001C7E
0x180001cf9  mov     eax, 32h ; '2'
0x180001cfe  jmp     loc_180001C7E
0x180001d03  mov     rcx, gs:60h
0x180001d0c  mov     r8, rsi; P
0x180001d0f  xor     edx, edx; Flags
0x180001d11  mov     rcx, [rcx+30h]; HeapHandle
0x180001d15  call    cs:__imp_RtlFreeHeap
0x180001d1c  nop     dword ptr [rax+rax+00h]
0x180001d21  xor     edi, edi
0x180001d23  jmp     loc_180001B5C
0x180001d28  mov     rbp, rsi
0x180001d2b  mov     dword ptr [r12], 2
0x180001d33  lea     r8, ds:2[rbx*2]; Size
0x180001d3b  mov     ecx, [rbp+4]
0x180001d3e  xor     edx, edx
0x180001d40  mov     [r12+4], ecx
0x180001d45  add     r13, r12
0x180001d48  mov     edi, [rbp+4]
0x180001d4b  mov     r9d, 0FFFFFFFFh
0x180001d51  shl     rdi, 6
0x180001d55  add     rdi, 8
0x180001d59  mov     [rsp+318h+var_2D0], r8
0x180001d5e  add     rdi, r12
0x180001d61  mov     [rsp+318h+var_2D8], edx
0x180001d65  test    ecx, ecx
0x180001d67  jz      loc_180001FA5
0x180001d6d  mov     eax, edx
0x180001d6f  shl     rax, 6
0x180001d73  lea     rcx, [rax+r12]
0x180001d77  lea     rbx, [rax+r12]
0x180001d7b  mov     [rsp+318h+var_2C8], rcx
0x180001d80  lea     r14, [rax+rbp]
0x180001d84  lea     rax, [rbx+48h]
0x180001d88  cmp     rax, r13
0x180001d8b  ja      short loc_180001DB2
0x180001d8d  mov     eax, [r14+8]
0x180001d91  mov     [rbx+8], eax
0x180001d94  mov     eax, [r14+0Ch]
0x180001d98  mov     [rbx+0Ch], eax
0x180001d9b  mov     eax, [r14+38h]
0x180001d9f  mov     [rbx+24h], eax
0x180001da2  movups  xmm0, xmmword ptr [r14+10h]
0x180001da7  movups  xmmword ptr [rbx+10h], xmm0
0x180001dab  mov     eax, [r14+20h]
0x180001daf  mov     [rbx+20h], eax
0x180001db2  lea     r12, [r8+rdi]
0x180001db6  cmp     r12, r13
0x180001db9  ja      short loc_180001DDE
0x180001dbb  lea     rdx, [rsp+318h+pszDest]; Src
0x180001dc3  mov     rcx, rdi; void *
0x180001dc6  call    memcpy_0
0x180001dcb  mov     edx, [rsp+318h+var_2D8]
0x180001dcf  mov     r9d, 0FFFFFFFFh
0x180001dd5  mov     r8, [rsp+318h+var_2D0]
0x180001dda  mov     [rbx+28h], rdi
0x180001dde  mov     esi, [r14+3Ch]
0x180001de2  mov     rdi, r12
0x180001de5  mov     r15d, [r14+40h]
0x180001de9  add     rsi, rbp
0x180001dec  shr     r15, 1
0x180001def  cmp     r15, 2
0x180001df3  jb      short loc_180001E40
0x180001df5  cmp     word ptr [rsi], 5Ch ; '\'
0x180001df9  jnz     short loc_180001E40
0x180001dfb  cmp     word ptr [rsi+2], 5Ch ; '\'
0x180001e00  jnz     short loc_180001E40
0x180001e02  cmp     word ptr [rsi+4], 5Ch ; '\'
0x180001e07  mov     ebx, 2
0x180001e0c  jz      short loc_180001E1D
0x180001e0e  cmp     rbx, r15
0x180001e11  jnb     short loc_180001E1D
0x180001e13  inc     rbx
0x180001e16  cmp     word ptr [rsi+rbx*2], 5Ch ; '\'
0x180001e1b  jnz     short loc_180001E0E
0x180001e1d  inc     rbx
0x180001e20  cmp     word ptr [rsi+rbx*2], 5Ch ; '\'
0x180001e25  jz      loc_180001EBA
0x180001e2b  cmp     rbx, r15
0x180001e2e  jnb     loc_180001EBA
0x180001e34  inc     rbx
0x180001e37  cmp     word ptr [rsi+rbx*2], 5Ch ; '\'
0x180001e3c  jnz     short loc_180001E2B
0x180001e3e  jmp     short loc_180001EBA
0x180001e40  cmp     r15, 8
0x180001e44  jb      short loc_180001E7C
0x180001e46  mov     r8d, 8; Length
0x180001e4c  lea     rdx, aDevice; "\\Device\\"
0x180001e53  mov     rcx, rsi; Source1
0x180001e56  call    cs:__imp_RtlCompareMemory
0x180001e5d  nop     dword ptr [rax+rax+00h]
0x180001e62  mov     edx, [rsp+318h+var_2D8]
0x180001e66  mov     r9d, 0FFFFFFFFh
0x180001e6c  mov     r8, [rsp+318h+var_2D0]
0x180001e71  cmp     rax, 8
0x180001e75  jnz     short loc_180001E82
0x180001e77  mov     rbx, rax
0x180001e7a  jmp     short loc_180001EA6
0x180001e7c  cmp     r15, 4
0x180001e80  jb      short loc_180001EA4
0x180001e82  cmp     word ptr [rsi], 5Ch ; '\'
0x180001e86  jnz     short loc_180001EA4
0x180001e88  cmp     word ptr [rsi+2], 3Fh ; '?'
0x180001e8d  jnz     short loc_180001EA4
0x180001e8f  cmp     word ptr [rsi+4], 3Fh ; '?'
0x180001e94  jnz     short loc_180001EA4
0x180001e96  cmp     word ptr [rsi+6], 5Ch ; '\'
0x180001e9b  jnz     short loc_180001EA4
0x180001e9d  mov     ebx, 4
0x180001ea2  jmp     short loc_180001EA6
0x180001ea4  xor     ebx, ebx
0x180001ea6  cmp     rbx, r15
0x180001ea9  jnb     short loc_180001EBA
0x180001eab  cmp     word ptr [rsi+rbx*2], 5Ch ; '\'
0x180001eb0  jz      short loc_180001EBA
0x180001eb2  inc     rbx
0x180001eb5  cmp     rbx, r15
0x180001eb8  jb      short loc_180001EAB
0x180001eba  test    rbx, rbx
0x180001ebd  jz      loc_180001F47
0x180001ec3  lea     rax, [rbx+rbx]
0x180001ec7  cmp     rax, r9
0x180001eca  ja      short loc_180001F47
0x180001ecc  lea     edx, [rbx+rbx]; Size
0x180001ecf  mov     rcx, rsi; Src
0x180001ed2  lea     r8, [rsp+318h+Src]; void *
0x180001eda  call    GetVolumeNameFromNtVolumeName
0x180001edf  lea     rcx, [rsp+318h+Src]
0x180001ee7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001eee  cmp     word ptr [rcx+rax*2+2], 0
0x180001ef4  lea     rax, [rax+1]
0x180001ef8  jnz     short loc_180001EEE
0x180001efa  lea     r14, [rax+1]
0x180001efe  lea     r14, [r12+r14*2]
0x180001f02  cmp     r14, r13
0x180001f05  ja      short loc_180001F2E
0x180001f07  lea     r8, [rax+rax]; Size
0x180001f0b  mov     rcx, rdi; void *
0x180001f0e  lea     rdx, [rsp+318h+Src]; Src
0x180001f16  call    memcpy_0
0x180001f1b  mov     r12, [rsp+318h+var_2C8]
0x180001f20  xor     eax, eax
0x180001f22  mov     [r14-2], ax
0x180001f27  mov     [r12+30h], rdi
0x180001f2c  jmp     short loc_180001F33
0x180001f2e  mov     r12, [rsp+318h+var_2C8]
0x180001f33  mov     edx, [rsp+318h+var_2D8]
0x180001f37  mov     rdi, r14
0x180001f3a  mov     r8, [rsp+318h+var_2D0]
0x180001f3f  mov     r9d, 0FFFFFFFFh
0x180001f45  jmp     short loc_180001F4C
0x180001f47  mov     r12, [rsp+318h+var_2C8]
  ... truncated ...
```
