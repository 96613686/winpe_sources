# RdBtLoadOptimalLayout

- ea: `0x18001ad28`
- end: `0x18001af2d`
- name: `RdBtLoadOptimalLayout`
- size: `517`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180019c60`

## callees

- `0x18001ad28`
- `0x18001bfcc`
- `0x18001c020`
- `0x18001eeb0`
- `0x180020ee8`
- `0x180069b60`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001af05`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001af05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aec9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aee4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aec9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aee4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ae20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ae62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ae20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ae62`

## string_xrefs

- `0x18001ad9e`: `ERROR: Could not open optimal layout file: %ws (%x)\n`

## pseudocode

```c
__int64 __fastcall RdBtLoadOptimalLayout(LPCWSTR lpFileName, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  void *v7; // rsi
  void *v8; // r14
  int v9; // edi
  unsigned int File; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  LPVOID v14; // rax
  unsigned int v15; // ebx
  int v16; // eax
  _BYTE v19[8]; // [rsp+40h] [rbp-61h] BYREF
  __int64 v20; // [rsp+48h] [rbp-59h]
  SIZE_T dwBytes[2]; // [rsp+90h] [rbp-11h] BYREF

  *(_OWORD *)dwBytes = 0;
  memset_0(v19, 0, 0x48u);
  v7 = 0;
  v20 = -1;
  v8 = 0;
  v9 = 1;
  File = PfsBcCreateFile(v19, lpFileName, 0);
  v11 = File;
  if ( File )
  {
    v12 = EcbUtilsOut(1, "ERROR: Could not open optimal layout file: %ws (%x)\n", lpFileName, File);
    if ( v12 == 8 || v12 == 1450 )
      goto LABEL_4;
  }
  else
  {
    v11 = PfsBcReadFile(v19, dwBytes, 16);
    if ( !v11 )
    {
      v13 = dwBytes[1];
      if ( LODWORD(dwBytes[1]) <= 0x40000000
        && HIDWORD(dwBytes[1]) <= LODWORD(dwBytes[1]) >> 3
        && dwBytes[0] == 0x152644C69LL )
      {
        v14 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, LODWORD(dwBytes[1]));
        v7 = v14;
        if ( !v14 )
        {
          v11 = 8;
LABEL_4:
          v9 = 0;
          goto LABEL_15;
        }
        v11 = PfsBcReadFile(v19, v14, v13);
        if ( !v11 )
        {
          v15 = 4 * HIDWORD(dwBytes[1]);
          v8 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, (unsigned int)(4 * HIDWORD(dwBytes[1])));
          v11 = PfsBcReadFile(v19, v8, v15);
          if ( !v11 )
          {
            v9 = 0;
            EcbFileNameSpaceReplaceBuffer(a2, v7, LODWORD(dwBytes[1]));
            v7 = 0;
            *(_DWORD *)(a2 + 36) += LODWORD(dwBytes[1]);
            v16 = HIDWORD(dwBytes[1]);
            *a3 = v8;
            v8 = 0;
            *a4 = v16;
          }
        }
      }
      else
      {
        v11 = 1006;
      }
    }
  }
LABEL_15:
  PfsBcClose(v19);
  if ( v8 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v8);
  if ( v7 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v7);
  if ( v9 )
  {
    EcbUtilsOut(16, "Optimal layout FileCorrupt: deleting %ws...\n", lpFileName);
    DeleteFileW(lpFileName);
  }
  return v11;
}

```

## disassembly

```asm
0x18001ad28  push    rbp
0x18001ad2a  push    rbx
0x18001ad2b  push    rsi
0x18001ad2c  push    rdi
0x18001ad2d  push    r12
0x18001ad2f  push    r13
0x18001ad31  push    r14
0x18001ad33  push    r15
0x18001ad35  lea     rbp, [rsp-17h]
0x18001ad3a  sub     rsp, 0B8h
0x18001ad41  mov     rax, cs:__security_cookie
0x18001ad48  xor     rax, rsp
0x18001ad4b  mov     [rbp+4Fh+var_50], rax
0x18001ad4f  mov     r12, rdx
0x18001ad52  mov     [rbp+4Fh+var_C0], r9
0x18001ad56  xor     edx, edx; Val
0x18001ad58  mov     r13, r8
0x18001ad5b  mov     r15, rcx
0x18001ad5e  xorps   xmm0, xmm0
0x18001ad61  lea     rcx, [rbp+4Fh+var_B0]; void *
0x18001ad65  movups  xmmword ptr [rbp+4Fh+dwBytes], xmm0
0x18001ad69  lea     r8d, [rdx+48h]; Size
0x18001ad6d  call    memset_0
0x18001ad72  xor     esi, esi
0x18001ad74  mov     [rbp+4Fh+var_A8], 0FFFFFFFFFFFFFFFFh
0x18001ad7c  xor     r8d, r8d
0x18001ad7f  mov     [rsp+0F0h+var_D0], esi
0x18001ad83  mov     rdx, r15
0x18001ad86  lea     rcx, [rbp+4Fh+var_B0]
0x18001ad8a  xor     r14d, r14d
0x18001ad8d  lea     edi, [rsi+1]
0x18001ad90  call    PfsBcCreateFile
0x18001ad95  mov     ebx, eax
0x18001ad97  test    eax, eax
0x18001ad99  jz      short loc_18001ADC6
0x18001ad9b  mov     r9d, eax
0x18001ad9e  lea     rdx, aErrorCouldNotO_0; "ERROR: Could not open optimal layout fi"...
0x18001ada5  mov     r8, r15
0x18001ada8  mov     ecx, edi
0x18001adaa  call    EcbUtilsOut
0x18001adaf  cmp     eax, 8
0x18001adb2  jz      short loc_18001ADBF
0x18001adb4  cmp     eax, 5AAh
0x18001adb9  jnz     loc_18001AEAB
0x18001adbf  xor     edi, edi
0x18001adc1  jmp     loc_18001AEAB
0x18001adc6  mov     r8d, 10h
0x18001adcc  lea     rdx, [rbp+4Fh+dwBytes]
0x18001add0  lea     rcx, [rbp+4Fh+var_B0]
0x18001add4  call    PfsBcReadFile
0x18001add9  mov     ebx, eax
0x18001addb  test    eax, eax
0x18001addd  jnz     loc_18001AEAB
0x18001ade3  mov     ebx, dword ptr [rbp+4Fh+dwBytes+8]
0x18001ade6  cmp     ebx, 40000000h
0x18001adec  jbe     short loc_18001ADF8
0x18001adee  mov     ebx, 3EEh
0x18001adf3  jmp     loc_18001AEAB
0x18001adf8  mov     eax, ebx
0x18001adfa  shr     eax, 3
0x18001adfd  cmp     dword ptr [rbp+4Fh+dwBytes+0Ch], eax
0x18001ae00  ja      short loc_18001ADEE
0x18001ae02  cmp     dword ptr [rbp+4Fh+dwBytes], 52644C69h
0x18001ae09  jnz     short loc_18001ADEE
0x18001ae0b  cmp     dword ptr [rbp+4Fh+dwBytes+4], edi
0x18001ae0e  jnz     short loc_18001ADEE
0x18001ae10  mov     rcx, cs:PfSvcGlobals
0x18001ae17  mov     r8, rbx; dwBytes
0x18001ae1a  xor     edx, edx; dwFlags
0x18001ae1c  mov     rcx, [rcx+58h]; hHeap
0x18001ae20  call    cs:__imp_HeapAlloc
0x18001ae26  mov     rsi, rax
0x18001ae29  test    rax, rax
0x18001ae2c  jnz     short loc_18001AE33
0x18001ae2e  lea     ebx, [rax+8]
0x18001ae31  jmp     short loc_18001ADBF
0x18001ae33  mov     r8d, ebx
0x18001ae36  lea     rcx, [rbp+4Fh+var_B0]
0x18001ae3a  mov     rdx, rsi
0x18001ae3d  call    PfsBcReadFile
0x18001ae42  mov     ebx, eax
0x18001ae44  test    eax, eax
0x18001ae46  jnz     short loc_18001AEAB
0x18001ae48  mov     eax, dword ptr [rbp+4Fh+dwBytes+0Ch]
0x18001ae4b  xor     edx, edx; dwFlags
0x18001ae4d  mov     rcx, cs:PfSvcGlobals
0x18001ae54  lea     ebx, ds:0[rax*4]
0x18001ae5b  mov     rcx, [rcx+58h]; hHeap
0x18001ae5f  mov     r8d, ebx; dwBytes
0x18001ae62  call    cs:__imp_HeapAlloc
0x18001ae68  mov     r8d, ebx
0x18001ae6b  lea     rcx, [rbp+4Fh+var_B0]
0x18001ae6f  mov     rdx, rax
0x18001ae72  mov     r14, rax
0x18001ae75  call    PfsBcReadFile
0x18001ae7a  mov     ebx, eax
0x18001ae7c  test    eax, eax
0x18001ae7e  jnz     short loc_18001AEAB
0x18001ae80  mov     r8d, dword ptr [rbp+4Fh+dwBytes+8]
0x18001ae84  mov     rdx, rsi
0x18001ae87  mov     rcx, r12
0x18001ae8a  xor     edi, edi
0x18001ae8c  call    EcbFileNameSpaceReplaceBuffer
0x18001ae91  mov     eax, dword ptr [rbp+4Fh+dwBytes+8]
0x18001ae94  xor     esi, esi
0x18001ae96  add     [r12+24h], eax
0x18001ae9b  mov     rcx, [rbp+4Fh+var_C0]
0x18001ae9f  mov     eax, dword ptr [rbp+4Fh+dwBytes+0Ch]
0x18001aea2  mov     [r13+0], r14
0x18001aea6  xor     r14d, r14d
0x18001aea9  mov     [rcx], eax
0x18001aeab  lea     rcx, [rbp+4Fh+var_B0]
0x18001aeaf  call    PfsBcClose
0x18001aeb4  test    r14, r14
0x18001aeb7  jz      short loc_18001AECF
0x18001aeb9  mov     rcx, cs:PfSvcGlobals
0x18001aec0  mov     r8, r14; lpMem
0x18001aec3  xor     edx, edx; dwFlags
0x18001aec5  mov     rcx, [rcx+58h]; hHeap
0x18001aec9  call    cs:__imp_HeapFree
0x18001aecf  test    rsi, rsi
0x18001aed2  jz      short loc_18001AEEA
0x18001aed4  mov     rcx, cs:PfSvcGlobals
0x18001aedb  mov     r8, rsi; lpMem
0x18001aede  xor     edx, edx; dwFlags
0x18001aee0  mov     rcx, [rcx+58h]; hHeap
0x18001aee4  call    cs:__imp_HeapFree
0x18001aeea  test    edi, edi
0x18001aeec  jz      short loc_18001AF0B
0x18001aeee  mov     r8, r15
0x18001aef1  lea     rdx, aOptimalLayoutF; "Optimal layout FileCorrupt: deleting %w"...
0x18001aef8  mov     ecx, 10h
0x18001aefd  call    EcbUtilsOut
0x18001af02  mov     rcx, r15; lpFileName
0x18001af05  call    cs:__imp_DeleteFileW
0x18001af0b  mov     eax, ebx
0x18001af0d  mov     rcx, [rbp+4Fh+var_50]
0x18001af11  xor     rcx, rsp; StackCookie
0x18001af14  call    __security_check_cookie
0x18001af19  add     rsp, 0B8h
0x18001af20  pop     r15
0x18001af22  pop     r14
0x18001af24  pop     r13
0x18001af26  pop     r12
0x18001af28  pop     rdi
0x18001af29  pop     rsi
0x18001af2a  pop     rbx
0x18001af2b  pop     rbp
0x18001af2c  retn
```
