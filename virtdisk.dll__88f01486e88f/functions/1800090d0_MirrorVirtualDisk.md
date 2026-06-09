# MirrorVirtualDisk

- ea: `0x1800090d0`
- end: `0x1800092da`
- name: `MirrorVirtualDisk`
- size: `522`
- prototype: `__int64 __fastcall(char *, int, __int64, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180005fd6`
- `0x1800090d0`
- `0x18000ada0`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800092b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800092b3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000919d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000919d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000929f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000929f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000924d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000924d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000923d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000923d`
- `ntdll!RtlFreeHeap` at `0x18000927f`
- `ntdll!RtlFreeHeap` at `0x18000927f`

## pseudocode

```c
__int64 __fastcall MirrorVirtualDisk(char *a1, int a2, __int64 a3, struct _OVERLAPPED *a4)
{
  char v4; // r14
  _DWORD *v5; // rsi
  char v6; // bp
  unsigned int LastError; // ebx
  LPCWSTR *v8; // rdi
  const WCHAR *v9; // rcx
  __int64 v10; // r15
  DWORD v11; // r12d
  size_t v12; // r13
  _DWORD *v13; // rax
  const void *v14; // rdx
  __int64 v16; // [rsp+40h] [rbp-48h] BYREF
  void *Src[8]; // [rsp+48h] [rbp-40h] BYREF

  Src[0] = 0;
  v4 = 0;
  LODWORD(v16) = 0;
  v5 = 0;
  v6 = a2;
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = 6;
    v8 = (LPCWSTR *)(a3 + 8);
  }
  else
  {
    if ( (a2 & 0xFFFFFFF0) != 0 )
      return 87;
    if ( !a3 )
      return 87;
    if ( *(_DWORD *)a3 != 1 )
      return 87;
    v8 = (LPCWSTR *)(a3 + 8);
    v9 = *(const WCHAR **)(a3 + 8);
    if ( !v9 || !a4 )
      return 87;
    if ( (a2 & 1) != 0 )
    {
      LastError = ValidateFile(v9, 0xC0000000, 3u, (__int64)a4, (LPWSTR *)Src, (DWORD *)&v16);
      if ( !LastError )
      {
LABEL_12:
        v10 = (unsigned int)v16;
        v11 = v16 + 12;
        v12 = (unsigned int)(v16 + 12);
        v13 = malloc(v12);
        v5 = v13;
        if ( v13 )
        {
          memset_0(v13, 0, v12);
          v14 = Src[0];
          v5[1] = v10 - 2;
          *v5 = 12;
          *((_BYTE *)v5 + 8) = (v6 & 2) != 0;
          *((_BYTE *)v5 + 9) = (v6 & 4) != 0;
          *((_BYTE *)v5 + 10) = (v6 & 8) != 0;
          memcpy_0(v5 + 3, v14, v10 - 2);
          if ( !DeviceIoControl(a1, 0x2D1958u, v5, v11, 0, 0, 0, a4) )
            LastError = GetLastError();
        }
        else
        {
          LastError = 14;
        }
      }
    }
    else
    {
      LastError = ValidateFile(v9, 0xC0000000, 1u, (__int64)a4, (LPWSTR *)Src, (DWORD *)&v16);
      if ( !LastError )
      {
        v4 = 1;
        goto LABEL_12;
      }
    }
  }
  if ( Src[0] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Src[0]);
  if ( LastError && LastError != 997 && v4 )
    DeleteFileW(*v8);
  if ( v5 )
    free(v5);
  return LastError;
}

```

## disassembly

```asm
0x1800090d0  mov     rax, rsp
0x1800090d3  mov     [rax+10h], rbx
0x1800090d7  mov     [rax+20h], r9
0x1800090db  mov     [rax+8], rcx
0x1800090df  push    rbp
0x1800090e0  push    rsi
0x1800090e1  push    rdi
0x1800090e2  push    r12
0x1800090e4  push    r13
0x1800090e6  push    r14
0x1800090e8  push    r15
0x1800090ea  sub     rsp, 50h
0x1800090ee  mov     qword ptr [rax-40h], 0
0x1800090f6  xor     r14b, r14b
0x1800090f9  mov     dword ptr [rax-48h], 0
0x180009100  xor     esi, esi
0x180009102  lea     rax, [rcx-1]
0x180009106  mov     ebp, edx
0x180009108  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000910c  ja      loc_18000925D
0x180009112  test    edx, 0FFFFFFF0h
0x180009118  jz      short loc_180009124
0x18000911a  mov     ebx, 57h ; 'W'
0x18000911f  jmp     loc_1800092BF
0x180009124  test    r8, r8
0x180009127  jz      short loc_18000911A
0x180009129  cmp     dword ptr [r8], 1
0x18000912d  jnz     short loc_18000911A
0x18000912f  lea     rdi, [r8+8]
0x180009133  mov     rcx, [rdi]; lpFileName
0x180009136  test    rcx, rcx
0x180009139  jz      short loc_18000911A
0x18000913b  test    r9, r9
0x18000913e  jz      short loc_18000911A
0x180009140  lea     rax, [rsp+88h+var_48]
0x180009145  mov     edx, 0C0000000h
0x18000914a  mov     qword ptr [rsp+88h+nOutBufferSize], rax; __int64
0x18000914f  lea     rax, [rsp+88h+Src]
0x180009154  mov     [rsp+88h+lpOutBuffer], rax; __int64
0x180009159  test    bpl, 1
0x18000915d  jnz     short loc_180009179
0x18000915f  mov     r8d, 1
0x180009165  call    ValidateFile
0x18000916a  mov     ebx, eax
0x18000916c  test    eax, eax
0x18000916e  jnz     loc_180009266
0x180009174  mov     r14b, 1
0x180009177  jmp     short loc_18000918E
0x180009179  mov     r8d, 3
0x18000917f  call    ValidateFile
0x180009184  mov     ebx, eax
0x180009186  test    eax, eax
0x180009188  jnz     loc_180009266
0x18000918e  mov     r15d, dword ptr [rsp+88h+var_48]
0x180009193  lea     r12d, [r15+0Ch]
0x180009197  mov     ecx, r12d; Size
0x18000919a  mov     r13d, r12d
0x18000919d  call    cs:__imp_malloc
0x1800091a4  nop     dword ptr [rax+rax+00h]
0x1800091a9  mov     rsi, rax
0x1800091ac  test    rax, rax
0x1800091af  jnz     short loc_1800091B9
0x1800091b1  lea     ebx, [rax+0Eh]
0x1800091b4  jmp     loc_180009266
0x1800091b9  mov     r8, r13; Size
0x1800091bc  xor     edx, edx; Val
0x1800091be  mov     rcx, rsi; void *
0x1800091c1  call    memset_0
0x1800091c6  mov     rdx, [rsp+88h+Src]; Src
0x1800091cb  lea     eax, [r15-2]
0x1800091cf  mov     [rsi+4], eax
0x1800091d2  lea     r8, [r15-2]; Size
0x1800091d6  mov     eax, ebp
0x1800091d8  mov     dword ptr [rsi], 0Ch
0x1800091de  shr     eax, 1
0x1800091e0  lea     rcx, [rsi+0Ch]; void *
0x1800091e4  and     al, 1
0x1800091e6  mov     [rsi+8], al
0x1800091e9  mov     eax, ebp
0x1800091eb  shr     eax, 2
0x1800091ee  and     al, 1
0x1800091f0  shr     ebp, 3
0x1800091f3  and     bpl, 1
0x1800091f7  mov     [rsi+9], al
0x1800091fa  mov     [rsi+0Ah], bpl
0x1800091fe  call    memcpy_0
0x180009203  mov     rax, [rsp+88h+arg_18]
0x18000920b  mov     r9d, r12d; nInBufferSize
0x18000920e  mov     rcx, [rsp+88h+hDevice]; hDevice
0x180009216  mov     r8, rsi; lpInBuffer
0x180009219  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x18000921e  mov     edx, 2D1958h; dwIoControlCode
0x180009223  mov     [rsp+88h+lpBytesReturned], 0; lpBytesReturned
0x18000922c  mov     [rsp+88h+nOutBufferSize], 0; nOutBufferSize
0x180009234  mov     [rsp+88h+lpOutBuffer], 0; lpOutBuffer
0x18000923d  call    cs:__imp_DeviceIoControl
0x180009244  nop     dword ptr [rax+rax+00h]
0x180009249  test    eax, eax
0x18000924b  jnz     short loc_180009266
0x18000924d  call    cs:__imp_GetLastError
0x180009254  nop     dword ptr [rax+rax+00h]
0x180009259  mov     ebx, eax
0x18000925b  jmp     short loc_180009266
0x18000925d  mov     ebx, 6
0x180009262  lea     rdi, [r8+8]
0x180009266  mov     r8, [rsp+88h+Src]; P
0x18000926b  test    r8, r8
0x18000926e  jz      short loc_18000928B
0x180009270  mov     rcx, gs:60h
0x180009279  xor     edx, edx; Flags
0x18000927b  mov     rcx, [rcx+30h]; HeapHandle
0x18000927f  call    cs:__imp_RtlFreeHeap
0x180009286  nop     dword ptr [rax+rax+00h]
0x18000928b  test    ebx, ebx
0x18000928d  jz      short loc_1800092AB
0x18000928f  cmp     ebx, 3E5h
0x180009295  jz      short loc_1800092AB
0x180009297  test    r14b, r14b
0x18000929a  jz      short loc_1800092AB
0x18000929c  mov     rcx, [rdi]; lpFileName
0x18000929f  call    cs:__imp_DeleteFileW
0x1800092a6  nop     dword ptr [rax+rax+00h]
0x1800092ab  test    rsi, rsi
0x1800092ae  jz      short loc_1800092BF
0x1800092b0  mov     rcx, rsi; Block
0x1800092b3  call    cs:__imp_free
0x1800092ba  nop     dword ptr [rax+rax+00h]
0x1800092bf  mov     eax, ebx
0x1800092c1  mov     rbx, [rsp+88h+arg_8]
0x1800092c9  add     rsp, 50h
0x1800092cd  pop     r15
0x1800092cf  pop     r14
0x1800092d1  pop     r13
0x1800092d3  pop     r12
0x1800092d5  pop     rdi
0x1800092d6  pop     rsi
0x1800092d7  pop     rbp
0x1800092d8  retn
```
