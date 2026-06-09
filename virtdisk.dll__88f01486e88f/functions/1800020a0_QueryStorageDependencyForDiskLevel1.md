# QueryStorageDependencyForDiskLevel1

- ea: `0x1800020a0`
- end: `0x1800022ae`
- name: `QueryStorageDependencyForDiskLevel1`
- size: `526`
- prototype: `__int64 __fastcall(HANDLE hDevice, unsigned int, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001010`

## callees

- `0x1800020a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000213a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000213a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000212a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000212a`
- `ntdll!RtlFreeHeap` at `0x180002183`
- `ntdll!RtlFreeHeap` at `0x1800021b5`
- `ntdll!RtlFreeHeap` at `0x18000221b`
- `ntdll!RtlFreeHeap` at `0x180002183`
- `ntdll!RtlFreeHeap` at `0x1800021b5`
- `ntdll!RtlFreeHeap` at `0x18000221b`
- `ntdll!RtlAllocateHeap` at `0x1800020e7`
- `ntdll!RtlAllocateHeap` at `0x1800020e7`

## pseudocode

```c
__int64 __fastcall QueryStorageDependencyForDiskLevel1(HANDLE hDevice, unsigned int a2, _DWORD *a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  DWORD nOutBufferSize; // esi
  unsigned __int64 *lpOutBuffer; // rdi
  DWORD LastError; // eax
  unsigned __int64 *v12; // r8
  unsigned __int64 v13; // rax
  unsigned __int64 *v14; // rsi
  int v16; // ecx
  unsigned int v17; // ecx
  unsigned int i; // r8d
  __int64 v19; // rax
  __int64 v20; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-58h] BYREF
  int InBuffer[21]; // [rsp+44h] [rbp-54h] BYREF

  v4 = 0;
  InBuffer[0] = 1;
  BytesReturned = 0;
  nOutBufferSize = 72;
  while ( 1 )
  {
    lpOutBuffer = (unsigned __int64 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, nOutBufferSize);
    if ( !lpOutBuffer )
      return 14;
    if ( DeviceIoControl(hDevice, 0x2D118Cu, InBuffer, 4u, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
      goto LABEL_8;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError != 122 && LastError != 234 )
      break;
    v13 = lpOutBuffer[1];
    if ( v13 <= nOutBufferSize )
      break;
    nOutBufferSize = lpOutBuffer[1];
    if ( v13 != (unsigned int)v13 )
      goto LABEL_13;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpOutBuffer);
    v4 = 0;
  }
  if ( v4 == 1 || v4 == 87 || v4 == 50 || v4 == 120 || v4 == -2147467263 )
  {
    v4 = 0;
    *((_DWORD *)lpOutBuffer + 1) = 0;
LABEL_8:
    if ( !*((_DWORD *)lpOutBuffer + 1) )
    {
      v4 = -1069940715;
      v12 = lpOutBuffer;
LABEL_10:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      return v4;
    }
    v14 = lpOutBuffer;
LABEL_24:
    v16 = 28 * *((_DWORD *)v14 + 1);
    *a3 = 1;
    a3[1] = *((_DWORD *)v14 + 1);
    v17 = v16 + 72;
    if ( a4 )
      *a4 = v17;
    if ( a2 >= v17 )
    {
      for ( i = 0; i < a3[1]; a3[v20 + 8] = v14[6 * v19 + 4] )
      {
        v19 = i++;
        v20 = 7 * v19;
        a3[v20 + 2] = v14[6 * v19 + 1];
        a3[v20 + 3] = HIDWORD(v14[6 * v19 + 1]);
        *(_OWORD *)&a3[v20 + 4] = *(_OWORD *)&v14[6 * v19 + 2];
      }
    }
    else
    {
      v4 = 122;
    }
    v12 = v14;
    goto LABEL_10;
  }
LABEL_13:
  v14 = 0;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpOutBuffer);
  if ( !v4 )
  {
    v4 = 0;
    goto LABEL_24;
  }
  return v4;
}

```

## disassembly

```asm
0x1800020a0  push    rbx
0x1800020a2  push    rbp
0x1800020a3  push    rsi
0x1800020a4  push    rdi
0x1800020a5  push    r12
0x1800020a7  push    r13
0x1800020a9  push    r14
0x1800020ab  push    r15
0x1800020ad  sub     rsp, 58h
0x1800020b1  xor     ebx, ebx
0x1800020b3  mov     [rsp+98h+InBuffer], 1
0x1800020bb  mov     [rsp+98h+BytesReturned], ebx
0x1800020bf  mov     r12, r9
0x1800020c2  mov     r15, r8
0x1800020c5  mov     r13d, edx
0x1800020c8  mov     r14, rcx
0x1800020cb  mov     esi, 48h ; 'H'
0x1800020d0  mov     rcx, gs:60h
0x1800020d9  mov     edx, 8; Flags
0x1800020de  mov     r8d, esi; Size
0x1800020e1  mov     ebp, esi
0x1800020e3  mov     rcx, [rcx+30h]; HeapHandle
0x1800020e7  call    cs:__imp_RtlAllocateHeap
0x1800020ee  nop     dword ptr [rax+rax+00h]
0x1800020f3  mov     rdi, rax
0x1800020f6  test    rax, rax
0x1800020f9  jz      loc_1800021D9
0x1800020ff  mov     [rsp+98h+lpOverlapped], rbx; lpOverlapped
0x180002104  lea     rax, [rsp+98h+BytesReturned]
0x180002109  mov     [rsp+98h+lpBytesReturned], rax; lpBytesReturned
0x18000210e  lea     r8, [rsp+98h+InBuffer]; lpInBuffer
0x180002113  mov     [rsp+98h+nOutBufferSize], esi; nOutBufferSize
0x180002117  mov     r9d, 4; nInBufferSize
0x18000211d  mov     edx, 2D118Ch; dwIoControlCode
0x180002122  mov     [rsp+98h+lpOutBuffer], rdi; lpOutBuffer
0x180002127  mov     rcx, r14; hDevice
0x18000212a  call    cs:__imp_DeviceIoControl
0x180002131  nop     dword ptr [rax+rax+00h]
0x180002136  test    eax, eax
0x180002138  jnz     short loc_180002162
0x18000213a  call    cs:__imp_GetLastError
0x180002141  nop     dword ptr [rax+rax+00h]
0x180002146  mov     ebx, eax
0x180002148  cmp     eax, 7Ah ; 'z'
0x18000214b  jz      short loc_180002191
0x18000214d  cmp     eax, 0EAh
0x180002152  jz      short loc_180002191
0x180002154  cmp     ebx, 1
0x180002157  jnz     loc_1800021E0
0x18000215d  xor     ebx, ebx
0x18000215f  mov     [rdi+4], ebx
0x180002162  cmp     dword ptr [rdi+4], 0
0x180002166  jnz     loc_180002232
0x18000216c  mov     ebx, 0C03A0015h
0x180002171  mov     r8, rdi; P
0x180002174  mov     rcx, gs:60h
0x18000217d  xor     edx, edx; Flags
0x18000217f  mov     rcx, [rcx+30h]; HeapHandle
0x180002183  call    cs:__imp_RtlFreeHeap
0x18000218a  nop     dword ptr [rax+rax+00h]
0x18000218f  jmp     short loc_1800021C5
0x180002191  mov     rax, [rdi+8]
0x180002195  cmp     rax, rbp
0x180002198  jbe     short loc_180002154
0x18000219a  mov     esi, eax
0x18000219c  cmp     rax, rsi
0x18000219f  jz      short loc_180002209
0x1800021a1  mov     rcx, gs:60h
0x1800021aa  mov     r8, rdi; P
0x1800021ad  xor     edx, edx; Flags
0x1800021af  xor     esi, esi
0x1800021b1  mov     rcx, [rcx+30h]; HeapHandle
0x1800021b5  call    cs:__imp_RtlFreeHeap
0x1800021bc  nop     dword ptr [rax+rax+00h]
0x1800021c1  test    ebx, ebx
0x1800021c3  jz      short loc_18000222E
0x1800021c5  mov     eax, ebx
0x1800021c7  add     rsp, 58h
0x1800021cb  pop     r15
0x1800021cd  pop     r14
0x1800021cf  pop     r13
0x1800021d1  pop     r12
0x1800021d3  pop     rdi
0x1800021d4  pop     rsi
0x1800021d5  pop     rbp
0x1800021d6  pop     rbx
0x1800021d7  retn
0x1800021d9  mov     ebx, 0Eh
0x1800021de  jmp     short loc_1800021C5
0x1800021e0  cmp     ebx, 57h ; 'W'
0x1800021e3  jz      loc_18000215D
0x1800021e9  cmp     ebx, 32h ; '2'
0x1800021ec  jz      loc_18000215D
0x1800021f2  cmp     ebx, 78h ; 'x'
0x1800021f5  jz      loc_18000215D
0x1800021fb  cmp     ebx, 80004001h
0x180002201  jz      loc_18000215D
0x180002207  jmp     short loc_1800021A1
0x180002209  mov     rcx, gs:60h
0x180002212  mov     r8, rdi; P
0x180002215  xor     edx, edx; Flags
0x180002217  mov     rcx, [rcx+30h]; HeapHandle
0x18000221b  call    cs:__imp_RtlFreeHeap
0x180002222  nop     dword ptr [rax+rax+00h]
0x180002227  xor     ebx, ebx
0x180002229  jmp     loc_1800020D0
0x18000222e  xor     ebx, ebx
0x180002230  jmp     short loc_180002235
0x180002232  mov     rsi, rdi
0x180002235  imul    ecx, [rsi+4], 1Ch
0x180002239  mov     dword ptr [r15], 1
0x180002240  mov     eax, [rsi+4]
0x180002243  mov     [r15+4], eax
0x180002247  add     ecx, 48h ; 'H'
0x18000224a  test    r12, r12
0x18000224d  jz      short loc_180002253
0x18000224f  mov     [r12], ecx
0x180002253  cmp     r13d, ecx
0x180002256  jnb     short loc_18000225F
0x180002258  mov     ebx, 7Ah ; 'z'
0x18000225d  jmp     short loc_1800022A6
0x18000225f  cmp     dword ptr [r15+4], 0
0x180002264  mov     r8d, ebx
0x180002267  jbe     short loc_1800022A6
0x180002269  mov     eax, r8d
0x18000226c  inc     r8d
0x18000226f  imul    rcx, rax, 1Ch
0x180002273  lea     rdx, [rax+rax*2]
0x180002277  add     rdx, rdx
0x18000227a  mov     eax, [rsi+rdx*8+8]
0x18000227e  mov     [rcx+r15+8], eax
0x180002283  mov     eax, [rsi+rdx*8+0Ch]
0x180002287  mov     [rcx+r15+0Ch], eax
0x18000228c  movups  xmm0, xmmword ptr [rsi+rdx*8+10h]
0x180002291  movups  xmmword ptr [r15+rcx+10h], xmm0
0x180002297  mov     eax, [rsi+rdx*8+20h]
0x18000229b  mov     [r15+rcx+20h], eax
0x1800022a0  cmp     r8d, [r15+4]
0x1800022a4  jb      short loc_180002269
0x1800022a6  mov     r8, rsi
0x1800022a9  jmp     loc_180002174
```
