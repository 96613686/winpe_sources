# DkParametersProcessor::ProcessParametersFile(wchar_t const * &)

- ea: `0x1005b26e0`
- end: `0x1005b2916`
- name: `?ProcessParametersFile@DkParametersProcessor@@AEAA?AW4DkParameterErrorEnum@@AEAPEB_W@Z`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1005b2a40`

## callees

- `0x1005b26e0`
- `0x1005b2a40`
- `0x1005b2cb0`
- `0x1005b3220`
- `0x1005b3e80`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1005b27bb`
- `KERNEL32!CreateFileW` at `0x1005b27bb`
- `KERNEL32!ReadFile` at `0x1005b2885`
- `KERNEL32!ReadFile` at `0x1005b2885`
- `KERNEL32!GetFileSize` at `0x1005b27e8`
- `KERNEL32!GetFileSize` at `0x1005b27e8`
- `KERNEL32!CloseHandle` at `0x1005b27d5`
- `KERNEL32!CloseHandle` at `0x1005b2802`
- `KERNEL32!CloseHandle` at `0x1005b2825`
- `KERNEL32!CloseHandle` at `0x1005b2854`
- `KERNEL32!CloseHandle` at `0x1005b28a7`
- `KERNEL32!CloseHandle` at `0x1005b28e8`
- `KERNEL32!CloseHandle` at `0x1005b27d5`
- `KERNEL32!CloseHandle` at `0x1005b2802`
- `KERNEL32!CloseHandle` at `0x1005b2825`
- `KERNEL32!CloseHandle` at `0x1005b2854`
- `KERNEL32!CloseHandle` at `0x1005b28a7`
- `KERNEL32!CloseHandle` at `0x1005b28e8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1005b2749`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1005b2788`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1005b2895`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1005b28d6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1005b2749`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1005b2788`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1005b2895`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1005b28d6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1005b2836`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1005b2836`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DkParametersProcessor::ProcessParametersFile(DkParametersProcessor *a1, const wchar_t **a2)
{
  void *v5; // rcx
  unsigned int v6; // edi
  void *v7; // rcx
  const WCHAR *v8; // rcx
  HANDLE FileW; // rax
  void *v10; // rbx
  DWORD FileSize; // eax
  __int64 v12; // r8
  DWORD v13; // edi
  void *v14; // rax
  void *v15; // rbp
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+8h] BYREF
  int v17; // [rsp+A0h] [rbp+18h] BYREF
  HANDLE v18; // [rsp+A8h] [rbp+20h]

  if ( *(_DWORD *)a1 >= 8u )
    return 10;
  ++*(_DWORD *)a1;
  ++*a2;
  DkParametersProcessor::KillSpaces(a1, a2);
  if ( !*a2 )
    return 15;
  v5 = (void *)*((_QWORD *)a1 + 7);
  if ( v5 )
    free(v5);
  *((_QWORD *)a1 + 7) = 0;
  v17 = 0;
  v6 = DkParametersProcessor::AllocateAndReadNameOrQuotedExpression(a1, a2, (char *)a1 + 56, &v17);
  if ( !v6 )
  {
    v7 = (void *)*((_QWORD *)a1 + 8);
    if ( v7 )
      free(v7);
    *((_QWORD *)a1 + 8) = 0;
    v8 = (const WCHAR *)*((_QWORD *)a1 + 7);
    v18 = 0;
    FileW = CreateFileW(v8, 1u, 1u, 0, 3u, 0, 0);
    v10 = FileW;
    v18 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v6 = 2;
    }
    else
    {
      FileSize = GetFileSize(FileW, 0);
      v13 = FileSize;
      if ( FileSize <= 0x100000 )
      {
        if ( FileSize )
        {
          _mm_lfence();
          v14 = malloc(FileSize);
          v15 = v14;
          if ( !v14 )
          {
            if ( v10 )
            {
              _mm_lfence();
              CloseHandle(v10);
            }
            v6 = 5;
            goto LABEL_31;
          }
          _mm_lfence();
          NumberOfBytesRead = 0;
          if ( !ReadFile(v10, v14, v13, &NumberOfBytesRead, 0) )
          {
            _mm_lfence();
            free(v15);
            if ( v10 )
            {
              _mm_lfence();
              CloseHandle(v10);
            }
            v6 = 6;
            goto LABEL_31;
          }
          _mm_lfence();
          v6 = DkParametersProcessor::ConvertBufferToUnicode(a1, v15, NumberOfBytesRead, (char *)a1 + 64);
          _mm_lfence();
          free(v15);
          if ( v10 )
          {
            _mm_lfence();
            CloseHandle(v10);
          }
          if ( v6 )
            goto LABEL_31;
        }
        else if ( v10 )
        {
          _mm_lfence();
          CloseHandle(v10);
        }
        LOBYTE(v12) = 1;
        v6 = DkParametersProcessor::ProcessBuffer(a1, *((_QWORD *)a1 + 8), v12);
      }
      else
      {
        if ( v10 )
        {
          _mm_lfence();
          CloseHandle(v10);
        }
        v6 = 4;
      }
    }
  }
LABEL_31:
  --*(_DWORD *)a1;
  return v6;
}

```

## disassembly

```asm
0x1005b26e0  push    rbx
0x1005b26e2  push    rbp
0x1005b26e3  push    rsi
0x1005b26e4  push    rdi
0x1005b26e5  push    r12
0x1005b26e7  push    r14
0x1005b26e9  push    r15
0x1005b26eb  sub     rsp, 50h
0x1005b26ef  mov     [rsp+88h+var_48], 0FFFFFFFFFFFFFFFEh
0x1005b26f8  mov     rbx, rdx
0x1005b26fb  mov     rsi, rcx
0x1005b26fe  mov     eax, [rcx]
0x1005b2700  cmp     eax, 8
0x1005b2703  jb      short loc_1005B2719
0x1005b2705  mov     eax, 0Ah
0x1005b270a  add     rsp, 50h
0x1005b270e  pop     r15
0x1005b2710  pop     r14
0x1005b2712  pop     r12
0x1005b2714  pop     rdi
0x1005b2715  pop     rsi
0x1005b2716  pop     rbp
0x1005b2717  pop     rbx
0x1005b2718  retn
0x1005b2719  inc     eax
0x1005b271b  mov     [rcx], eax
0x1005b271d  add     qword ptr [rdx], 2
0x1005b2721  call    ?KillSpaces@DkParametersProcessor@@AEAAXAEAPEB_W@Z; DkParametersProcessor::KillSpaces(wchar_t const * &)
0x1005b2726  cmp     qword ptr [rbx], 0
0x1005b272a  jnz     short loc_1005B2740
0x1005b272c  mov     eax, 0Fh
0x1005b2731  add     rsp, 50h
0x1005b2735  pop     r15
0x1005b2737  pop     r14
0x1005b2739  pop     r12
0x1005b273b  pop     rdi
0x1005b273c  pop     rsi
0x1005b273d  pop     rbp
0x1005b273e  pop     rbx
0x1005b273f  retn
0x1005b2740  mov     rcx, [rsi+38h]; Block
0x1005b2744  test    rcx, rcx
0x1005b2747  jz      short loc_1005B274F
0x1005b2749  call    cs:__imp_free
0x1005b274f  xor     r12d, r12d
0x1005b2752  mov     [rsi+38h], r12
0x1005b2756  mov     [rsp+88h+arg_10], r12d
0x1005b275e  lea     r9, [rsp+88h+arg_10]
0x1005b2766  lea     r8, [rsi+38h]
0x1005b276a  mov     rdx, rbx
0x1005b276d  mov     rcx, rsi
0x1005b2770  call    ?AllocateAndReadNameOrQuotedExpression@DkParametersProcessor@@AEAA?AW4DkParameterErrorEnum@@AEAPEB_WPEAPEA_WAEAI@Z; DkParametersProcessor::AllocateAndReadNameOrQuotedExpression(wchar_t const * &,wchar_t * *,uint &)
0x1005b2775  mov     edi, eax
0x1005b2777  test    eax, eax
0x1005b2779  jnz     loc_1005B2903
0x1005b277f  mov     rcx, [rsi+40h]; Block
0x1005b2783  test    rcx, rcx
0x1005b2786  jz      short loc_1005B278E
0x1005b2788  call    cs:__imp_free
0x1005b278e  mov     [rsi+40h], r12
0x1005b2792  mov     rcx, [rsi+38h]; lpFileName
0x1005b2796  mov     [rsp+88h+arg_18], r12
0x1005b279e  mov     [rsp+88h+hTemplateFile], r12; hTemplateFile
0x1005b27a3  mov     [rsp+88h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1005b27a8  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1005b27b0  xor     r9d, r9d; lpSecurityAttributes
0x1005b27b3  mov     edx, 1; dwDesiredAccess
0x1005b27b8  mov     r8d, edx; dwShareMode
0x1005b27bb  call    cs:__imp_CreateFileW
0x1005b27c1  mov     rbx, rax
0x1005b27c4  mov     [rsp+88h+arg_18], rax
0x1005b27cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1005b27d0  jnz     short loc_1005B27E3
0x1005b27d2  mov     rcx, rax; hObject
0x1005b27d5  call    cs:__imp_CloseHandle
0x1005b27db  lea     edi, [rbx+3]
0x1005b27de  jmp     loc_1005B2903
0x1005b27e3  xor     edx, edx; lpFileSizeHigh
0x1005b27e5  mov     rcx, rbx; hFile
0x1005b27e8  call    cs:__imp_GetFileSize
0x1005b27ee  mov     edi, eax
0x1005b27f0  cmp     eax, 100000h
0x1005b27f5  jbe     short loc_1005B2812
0x1005b27f7  test    rbx, rbx
0x1005b27fa  jz      short loc_1005B2808
0x1005b27fc  lfence
0x1005b27ff  mov     rcx, rbx; hObject
0x1005b2802  call    cs:__imp_CloseHandle
0x1005b2808  mov     edi, 4
0x1005b280d  jmp     loc_1005B2903
0x1005b2812  test    eax, eax
0x1005b2814  jnz     short loc_1005B2830
0x1005b2816  test    rbx, rbx
0x1005b2819  jz      loc_1005B28F2
0x1005b281f  lfence
0x1005b2822  mov     rcx, rbx; hObject
0x1005b2825  call    cs:__imp_CloseHandle
0x1005b282b  jmp     loc_1005B28F2
0x1005b2830  lfence
0x1005b2833  mov     rcx, rdi; Size
0x1005b2836  call    cs:__imp_malloc
0x1005b283c  mov     rbp, rax
0x1005b283f  mov     [rsp+88h+var_40], rax
0x1005b2844  test    rax, rax
0x1005b2847  jnz     short loc_1005B2864
0x1005b2849  test    rbx, rbx
0x1005b284c  jz      short loc_1005B285A
0x1005b284e  lfence
0x1005b2851  mov     rcx, rbx; hObject
0x1005b2854  call    cs:__imp_CloseHandle
0x1005b285a  mov     edi, 5
0x1005b285f  jmp     loc_1005B2903
0x1005b2864  lfence
0x1005b2867  mov     [rsp+88h+NumberOfBytesRead], r12d
0x1005b286f  mov     qword ptr [rsp+88h+dwCreationDisposition], r12; lpOverlapped
0x1005b2874  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1005b287c  mov     r8d, edi; nNumberOfBytesToRead
0x1005b287f  mov     rdx, rbp; lpBuffer
0x1005b2882  mov     rcx, rbx; hFile
0x1005b2885  call    cs:__imp_ReadFile
0x1005b288b  test    eax, eax
0x1005b288d  jnz     short loc_1005B28B4
0x1005b288f  lfence
0x1005b2892  mov     rcx, rbp; Block
0x1005b2895  call    cs:__imp_free
0x1005b289b  nop
0x1005b289c  test    rbx, rbx
0x1005b289f  jz      short loc_1005B28AD
0x1005b28a1  lfence
0x1005b28a4  mov     rcx, rbx; hObject
0x1005b28a7  call    cs:__imp_CloseHandle
0x1005b28ad  mov     edi, 6
0x1005b28b2  jmp     short loc_1005B2903
0x1005b28b4  lfence
0x1005b28b7  lea     r9, [rsi+40h]
0x1005b28bb  mov     r8d, [rsp+88h+NumberOfBytesRead]
0x1005b28c3  mov     rdx, rbp
0x1005b28c6  mov     rcx, rsi
0x1005b28c9  call    ?ConvertBufferToUnicode@DkParametersProcessor@@AEAA?AW4DkParameterErrorEnum@@PEBEKPEAPEA_W@Z; DkParametersProcessor::ConvertBufferToUnicode(uchar const *,ulong,wchar_t * *)
0x1005b28ce  mov     edi, eax
0x1005b28d0  lfence
0x1005b28d3  mov     rcx, rbp; Block
0x1005b28d6  call    cs:__imp_free
0x1005b28dc  nop
0x1005b28dd  test    rbx, rbx
0x1005b28e0  jz      short loc_1005B28EE
0x1005b28e2  lfence
0x1005b28e5  mov     rcx, rbx; hObject
0x1005b28e8  call    cs:__imp_CloseHandle
0x1005b28ee  test    edi, edi
0x1005b28f0  jnz     short loc_1005B2903
0x1005b28f2  mov     r8b, 1
0x1005b28f5  mov     rdx, [rsi+40h]
0x1005b28f9  mov     rcx, rsi
0x1005b28fc  call    ?ProcessBuffer@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@PEB_W_N@Z; DkParametersProcessor::ProcessBuffer(wchar_t const *,bool)
0x1005b2901  mov     edi, eax
0x1005b2903  dec     dword ptr [rsi]
0x1005b2905  mov     eax, edi
0x1005b2907  add     rsp, 50h
0x1005b290b  pop     r15
0x1005b290d  pop     r14
0x1005b290f  pop     r12
0x1005b2911  pop     rdi
0x1005b2912  pop     rsi
0x1005b2913  pop     rbp
0x1005b2914  pop     rbx
0x1005b2915  retn
```
