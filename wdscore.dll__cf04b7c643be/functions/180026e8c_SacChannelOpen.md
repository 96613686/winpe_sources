# SacChannelOpen

- ea: `0x180026e8c`
- end: `0x18002716f`
- name: `SacChannelOpen`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026ca0`

## callees

- `0x180026e8c`
- `0x18002730c`
- `0x18002735c`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026fe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026fe1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027114`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800298a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027114`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800298a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026fc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002988c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026fc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002988c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800270bd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800270bd`

## pseudocode

```c
__int64 __fastcall SacChannelOpen(__int64 a1, __int64 a2)
{
  _WORD *v4; // rsi
  int v5; // eax
  int v6; // eax
  HANDLE ProcessHeap; // rax
  _OWORD *v8; // rax
  unsigned int v9; // edi
  _OWORD *v10; // rcx
  __int64 v11; // rdx
  HANDLE v12; // r15
  HANDLE v13; // rax
  HANDLE hDevice; // [rsp+48h] [rbp-60h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-58h] BYREF
  _OWORD *v17; // [rsp+58h] [rbp-50h]
  __int64 v18; // [rsp+60h] [rbp-48h]
  __int128 OutBuffer; // [rsp+68h] [rbp-40h] BYREF
  __int64 v20; // [rsp+78h] [rbp-30h]

  v18 = a1;
  OutBuffer = 0;
  v20 = 0;
  BytesReturned = 0;
  v4 = 0;
  v17 = 0;
  hDevice = (HANDLE)-1LL;
  if ( a1
    && a2
    && SacHandleOpen(&hDevice)
    && hDevice != (HANDLE)-1LL
    && ((v5 = *(_DWORD *)(a2 + 648), (v5 & 2) != 0) && *(_QWORD *)(a2 + 656)
     || (*(_DWORD *)(a2 + 648) & 2) == 0 && !*(_QWORD *)(a2 + 656))
    && ((v5 & 4) != 0 && *(_QWORD *)(a2 + 664) || (v5 & 4) == 0 && !*(_QWORD *)(a2 + 664))
    && ((v5 & 8) != 0 && *(_QWORD *)(a2 + 672) || (v5 & 8) == 0 && !*(_QWORD *)(a2 + 672))
    && ((v6 = v5 & 0x10) != 0 && *(_QWORD *)(a2 + 680) || !v6 && !*(_QWORD *)(a2 + 680))
    && (*(_DWORD *)a2 == 2 || a2 != -4) )
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0x2C0u);
    v4 = v8;
    v17 = v8;
    if ( v8 )
    {
      v10 = (_OWORD *)a2;
      v11 = 5;
      do
      {
        *v8 = *v10;
        v8[1] = v10[1];
        v8[2] = v10[2];
        v8[3] = v10[3];
        v8[4] = v10[4];
        v8[5] = v10[5];
        v8[6] = v10[6];
        v8[7] = v10[7];
        v8 += 8;
        v10 += 8;
        --v11;
      }
      while ( v11 );
      *v8 = *v10;
      v8[1] = v10[1];
      v8[2] = v10[2];
      v8[3] = v10[3];
      if ( *(_DWORD *)a2 == 2 )
      {
        v4[2] = 0;
        v4[67] = 0;
      }
      v12 = hDevice;
      v9 = DeviceIoControl(hDevice, 0x228004u, v4, 0x2C0u, &OutBuffer, 0x18u, &BytesReturned, 0);
      if ( v9 )
      {
        *(_QWORD *)(a1 + 16) = v12;
        *(_OWORD *)a1 = OutBuffer;
      }
    }
    else
    {
      v9 = 0;
    }
  }
  else
  {
    v9 = 0;
  }
  if ( v4 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v4);
  }
  if ( !v9 && hDevice != (HANDLE)-1LL )
  {
    SacHandleClose(&hDevice);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180026e8c  mov     r11, rsp
0x180026e8f  mov     [r11+10h], rbx
0x180026e93  mov     [r11+18h], rsi
0x180026e97  push    rdi
0x180026e98  push    r14
0x180026e9a  push    r15
0x180026e9c  sub     rsp, 90h
0x180026ea3  mov     rax, cs:__security_cookie
0x180026eaa  xor     rax, rsp
0x180026ead  mov     [rsp+0A8h+var_28], rax
0x180026eb5  mov     rdi, rdx
0x180026eb8  mov     r14, rcx
0x180026ebb  mov     [rsp+0A8h+var_48], rcx
0x180026ec0  xorps   xmm0, xmm0
0x180026ec3  xor     eax, eax
0x180026ec5  movups  [rsp+0A8h+OutBuffer], xmm0
0x180026eca  mov     [r11-30h], rax
0x180026ece  xor     ebx, ebx
0x180026ed0  mov     [rsp+0A8h+BytesReturned], ebx
0x180026ed4  mov     [rsp+0A8h+var_68], ebx
0x180026ed8  mov     esi, ebx
0x180026eda  mov     [r11-50h], rbx
0x180026ede  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFFh
0x180026ee6  test    rcx, rcx
0x180026ee9  jz      loc_1800270F5
0x180026eef  test    rdx, rdx
0x180026ef2  jz      loc_1800270F5
0x180026ef8  lea     rcx, [r11-60h]
0x180026efc  call    SacHandleOpen
0x180026f01  mov     [rsp+0A8h+var_68], eax
0x180026f05  cmp     eax, 1
0x180026f08  jnz     loc_1800270F5
0x180026f0e  cmp     [rsp+0A8h+hDevice], 0FFFFFFFFFFFFFFFFh
0x180026f14  jz      loc_1800270F5
0x180026f1a  mov     eax, [rdi+288h]
0x180026f20  mov     ecx, eax
0x180026f22  and     ecx, 2
0x180026f25  jz      short loc_180026F30
0x180026f27  cmp     [rdi+290h], rbx
0x180026f2e  jnz     short loc_180026F45
0x180026f30  test    ecx, ecx
0x180026f32  jnz     loc_1800270F5
0x180026f38  cmp     [rdi+290h], rbx
0x180026f3f  jnz     loc_1800270F5
0x180026f45  mov     ecx, eax
0x180026f47  and     ecx, 4
0x180026f4a  jz      short loc_180026F55
0x180026f4c  cmp     [rdi+298h], rbx
0x180026f53  jnz     short loc_180026F6A
0x180026f55  test    ecx, ecx
0x180026f57  jnz     loc_1800270F5
0x180026f5d  cmp     [rdi+298h], rbx
0x180026f64  jnz     loc_1800270F5
0x180026f6a  mov     ecx, eax
0x180026f6c  and     ecx, 8
0x180026f6f  jz      short loc_180026F7A
0x180026f71  cmp     [rdi+2A0h], rbx
0x180026f78  jnz     short loc_180026F8F
0x180026f7a  test    ecx, ecx
0x180026f7c  jnz     loc_1800270F5
0x180026f82  cmp     [rdi+2A0h], rbx
0x180026f89  jnz     loc_1800270F5
0x180026f8f  and     eax, 10h
0x180026f92  jz      short loc_180026F9D
0x180026f94  cmp     [rdi+2A8h], rbx
0x180026f9b  jnz     short loc_180026FB2
0x180026f9d  test    eax, eax
0x180026f9f  jnz     loc_1800270F5
0x180026fa5  cmp     [rdi+2A8h], rbx
0x180026fac  jnz     loc_1800270F5
0x180026fb2  cmp     dword ptr [rdi], 2
0x180026fb5  jz      short loc_180026FC4
0x180026fb7  lea     rax, [rdi+4]
0x180026fbb  test    rax, rax
0x180026fbe  jz      loc_1800270F5
0x180026fc4  call    cs:__imp_GetProcessHeap
0x180026fcb  nop     dword ptr [rax+rax+00h]
0x180026fd0  mov     rcx, rax; hHeap
0x180026fd3  mov     r15d, 2C0h
0x180026fd9  mov     r8d, r15d; dwBytes
0x180026fdc  mov     edx, 8; dwFlags
0x180026fe1  call    cs:__imp_HeapAlloc
0x180026fe8  nop     dword ptr [rax+rax+00h]
0x180026fed  mov     rsi, rax
0x180026ff0  mov     [rsp+0A8h+var_50], rax
0x180026ff5  test    rax, rax
0x180026ff8  jnz     short loc_180027005
0x180026ffa  mov     edi, ebx
0x180026ffc  mov     [rsp+0A8h+var_68], ebx
0x180027000  jmp     loc_1800270E1
0x180027005  mov     rcx, rdi
0x180027008  mov     edx, 5
0x18002700d  lea     r8d, [rdx+7Bh]
0x180027011  movups  xmm0, xmmword ptr [rcx]
0x180027014  movups  xmmword ptr [rax], xmm0
0x180027017  movups  xmm1, xmmword ptr [rcx+10h]
0x18002701b  movups  xmmword ptr [rax+10h], xmm1
0x18002701f  movups  xmm0, xmmword ptr [rcx+20h]
0x180027023  movups  xmmword ptr [rax+20h], xmm0
0x180027027  movups  xmm1, xmmword ptr [rcx+30h]
0x18002702b  movups  xmmword ptr [rax+30h], xmm1
0x18002702f  movups  xmm0, xmmword ptr [rcx+40h]
0x180027033  movups  xmmword ptr [rax+40h], xmm0
0x180027037  movups  xmm1, xmmword ptr [rcx+50h]
0x18002703b  movups  xmmword ptr [rax+50h], xmm1
0x18002703f  movups  xmm0, xmmword ptr [rcx+60h]
0x180027043  movups  xmmword ptr [rax+60h], xmm0
0x180027047  movups  xmm1, xmmword ptr [rcx+70h]
0x18002704b  movups  xmmword ptr [rax+70h], xmm1
0x18002704f  add     rax, r8
0x180027052  add     rcx, r8
0x180027055  sub     rdx, 1
0x180027059  jnz     short loc_180027011
0x18002705b  movups  xmm0, xmmword ptr [rcx]
0x18002705e  movups  xmmword ptr [rax], xmm0
0x180027061  movups  xmm1, xmmword ptr [rcx+10h]
0x180027065  movups  xmmword ptr [rax+10h], xmm1
0x180027069  movups  xmm0, xmmword ptr [rcx+20h]
0x18002706d  movups  xmmword ptr [rax+20h], xmm0
0x180027071  movups  xmm1, xmmword ptr [rcx+30h]
0x180027075  movups  xmmword ptr [rax+30h], xmm1
0x180027079  cmp     dword ptr [rdi], 2
0x18002707c  jnz     short loc_180027089
0x18002707e  mov     [rsi+4], bx
0x180027082  mov     [rsi+86h], bx
0x180027089  mov     [rsp+0A8h+lpOverlapped], rbx; lpOverlapped
0x18002708e  lea     rax, [rsp+0A8h+BytesReturned]
0x180027093  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x180027098  mov     [rsp+0A8h+nOutBufferSize], 18h; nOutBufferSize
0x1800270a0  lea     rax, [rsp+0A8h+OutBuffer]
0x1800270a5  mov     [rsp+0A8h+lpOutBuffer], rax; lpOutBuffer
0x1800270aa  mov     r9d, r15d; nInBufferSize
0x1800270ad  mov     r8, rsi; lpInBuffer
0x1800270b0  mov     edx, 228004h; dwIoControlCode
0x1800270b5  mov     r15, [rsp+0A8h+hDevice]
0x1800270ba  mov     rcx, r15; hDevice
0x1800270bd  call    cs:__imp_DeviceIoControl
0x1800270c4  nop     dword ptr [rax+rax+00h]
0x1800270c9  mov     edi, eax
0x1800270cb  mov     [rsp+0A8h+var_68], eax
0x1800270cf  test    eax, eax
0x1800270d1  jz      short loc_1800270E1
0x1800270d3  mov     [r14+10h], r15
0x1800270d7  movups  xmm0, [rsp+0A8h+OutBuffer]
0x1800270dc  movdqu  xmmword ptr [r14], xmm0
0x1800270e1  jmp     short loc_1800270FB
0x1800270e3  xor     edi, edi
0x1800270e5  mov     [rsp+0A8h+var_68], edi
0x1800270e9  mov     rsi, [rsp+0A8h+var_50]
0x1800270ee  mov     r14, [rsp+0A8h+var_48]
0x1800270f3  jmp     short loc_1800270FB
0x1800270f5  mov     [rsp+0A8h+var_68], ebx
0x1800270f9  mov     edi, ebx
0x1800270fb  test    rsi, rsi
0x1800270fe  jz      short loc_180027120
0x180027100  call    cs:__imp_GetProcessHeap
0x180027107  nop     dword ptr [rax+rax+00h]
0x18002710c  mov     rcx, rax; hHeap
0x18002710f  mov     r8, rsi; lpMem
0x180027112  xor     edx, edx; dwFlags
0x180027114  call    cs:__imp_HeapFree
0x18002711b  nop     dword ptr [rax+rax+00h]
0x180027120  test    edi, edi
0x180027122  jnz     short loc_180027143
0x180027124  cmp     [rsp+0A8h+hDevice], 0FFFFFFFFFFFFFFFFh
0x18002712a  jz      short loc_180027143
0x18002712c  lea     rcx, [rsp+0A8h+hDevice]
0x180027131  call    SacHandleClose
0x180027136  xorps   xmm0, xmm0
0x180027139  xor     eax, eax
0x18002713b  movups  xmmword ptr [r14], xmm0
0x18002713f  mov     [r14+10h], rax
0x180027143  mov     eax, edi
0x180027145  mov     rcx, [rsp+0A8h+var_28]
0x18002714d  xor     rcx, rsp; StackCookie
0x180027150  call    __security_check_cookie
0x180027155  lea     r11, [rsp+0A8h+var_18]
0x18002715d  mov     rbx, [r11+28h]
0x180027161  mov     rsi, [r11+30h]
0x180027165  mov     rsp, r11
0x180027168  pop     r15
0x18002716a  pop     r14
0x18002716c  pop     rdi
0x18002716d  retn
0x180029879  push    rbx
0x18002987b  push    rbp
0x18002987c  sub     rsp, 48h
0x180029880  mov     rbp, rdx
0x180029883  mov     rbx, [rbp+58h]
0x180029887  test    rbx, rbx
0x18002988a  jz      short loc_1800298AD
0x18002988c  call    cs:__imp_GetProcessHeap
0x180029893  nop     dword ptr [rax+rax+00h]
0x180029898  mov     rcx, rax; hHeap
0x18002989b  mov     r8, rbx; lpMem
0x18002989e  xor     edx, edx; dwFlags
0x1800298a0  call    cs:__imp_HeapFree
0x1800298a7  nop     dword ptr [rax+rax+00h]
0x1800298ac  nop
0x1800298ad  cmp     dword ptr [rbp+40h], 0
0x1800298b1  jnz     short loc_1800298D3
0x1800298b3  cmp     qword ptr [rbp+48h], 0FFFFFFFFFFFFFFFFh
0x1800298b8  jz      short loc_1800298D3
0x1800298ba  lea     rcx, [rbp+48h]
0x1800298be  call    SacHandleClose
0x1800298c3  xorps   xmm0, xmm0
0x1800298c6  xor     ecx, ecx
0x1800298c8  mov     rax, [rbp+60h]
0x1800298cc  movups  xmmword ptr [rax], xmm0
0x1800298cf  mov     [rax+10h], rcx
0x1800298d3  add     rsp, 48h
0x1800298d7  pop     rbp
0x1800298d8  pop     rbx
0x1800298d9  retn
```
