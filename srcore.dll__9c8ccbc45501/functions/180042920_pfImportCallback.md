# pfImportCallback

- ea: `0x180042920`
- end: `0x180042a41`
- name: `pfImportCallback`
- size: `289`
- prototype: `DWORD __fastcall(PBYTE pbData, unsigned int *pvCallbackContext, PULONG ulLength)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180042920`
- `0x180052ff2`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800429d4`
- `KERNEL32!ReadFile` at `0x1800429d4`
- `KERNEL32!GetLastError` at `0x180042a21`
- `KERNEL32!GetLastError` at `0x180042a21`

## pseudocode

```c
DWORD __fastcall pfImportCallback(PBYTE pbData, unsigned int *pvCallbackContext, PULONG ulLength)
{
  DWORD v6; // ebp
  int v7; // r15d
  DWORD v8; // edi
  char *v9; // rcx
  DWORD v10; // r8d
  void *v11; // rdx
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-58h] BYREF
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !pbData || !pvCallbackContext || !ulLength )
    return 87;
  v6 = *ulLength;
  v7 = 0;
  while ( v6 )
  {
    v8 = pvCallbackContext[10];
    if ( !v8 )
    {
      v9 = (char *)*((_QWORD *)pvCallbackContext + 2);
      if ( (unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        break;
      v10 = pvCallbackContext[8];
      v11 = (void *)*((_QWORD *)pvCallbackContext + 3);
      Overlapped.OffsetHigh = HIDWORD(*((_QWORD *)pvCallbackContext + 7));
      Overlapped.Offset = pvCallbackContext[14];
      Overlapped.Internal = 0;
      Overlapped.InternalHigh = 0;
      Overlapped.hEvent = 0;
      if ( !ReadFile(v9, v11, v10, &NumberOfBytesRead, &Overlapped) )
        return GetLastError();
      v8 = NumberOfBytesRead;
      if ( !NumberOfBytesRead )
        break;
      *((_QWORD *)pvCallbackContext + 7) += NumberOfBytesRead;
      pvCallbackContext[9] = 0;
      pvCallbackContext[10] = v8;
    }
    if ( v8 > v6 )
      v8 = v6;
    memcpy(&pbData[v7], (const void *)(*((_QWORD *)pvCallbackContext + 3) + pvCallbackContext[9]), v8);
    pvCallbackContext[9] += v8;
    v7 += v8;
    pvCallbackContext[10] -= v8;
    v6 -= v8;
  }
  *ulLength -= v6;
  return 0;
}

```

## disassembly

```asm
0x180042920  mov     rax, rsp
0x180042923  push    rbx
0x180042924  push    rbp
0x180042925  push    rsi
0x180042926  push    rdi
0x180042927  push    r14
0x180042929  push    r15
0x18004292b  sub     rsp, 58h
0x18004292f  mov     dword ptr [rax+8], 0
0x180042936  xorps   xmm0, xmm0
0x180042939  mov     rsi, r8
0x18004293c  mov     rbx, rdx
0x18004293f  mov     r14, rcx
0x180042942  movups  xmmword ptr [rax-58h], xmm0
0x180042946  movups  xmmword ptr [rax-48h], xmm0
0x18004294a  test    rcx, rcx
0x18004294d  jz      loc_180042A2F
0x180042953  test    rdx, rdx
0x180042956  jz      loc_180042A2F
0x18004295c  test    r8, r8
0x18004295f  jz      loc_180042A2F
0x180042965  mov     ebp, [r8]
0x180042968  xor     r15d, r15d
0x18004296b  test    ebp, ebp
0x18004296d  jz      loc_180042A29
0x180042973  mov     edi, [rbx+28h]
0x180042976  test    edi, edi
0x180042978  jnz     short loc_1800429F7
0x18004297a  mov     rcx, [rbx+10h]; hFile
0x18004297e  lea     rax, [rcx-1]
0x180042982  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180042986  ja      loc_180042A29
0x18004298c  mov     rax, [rbx+38h]
0x180042990  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042998  mov     r8d, [rbx+20h]; nNumberOfBytesToRead
0x18004299c  mov     rdx, [rbx+18h]; lpBuffer
0x1800429a0  shr     rax, 20h
0x1800429a4  mov     dword ptr [rsp+88h+Overlapped.10h+4], eax
0x1800429a8  mov     eax, [rbx+38h]
0x1800429ab  mov     dword ptr [rsp+88h+Overlapped.10h], eax
0x1800429af  lea     rax, [rsp+88h+Overlapped]
0x1800429b4  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x1800429b9  mov     [rsp+88h+Overlapped.Internal], 0
0x1800429c2  mov     [rsp+88h+Overlapped.InternalHigh], 0
0x1800429cb  mov     [rsp+88h+Overlapped.hEvent], 0
0x1800429d4  call    cs:ReadFile
0x1800429da  test    eax, eax
0x1800429dc  jz      short loc_180042A21
0x1800429de  mov     edi, [rsp+88h+NumberOfBytesRead]
0x1800429e5  test    edi, edi
0x1800429e7  jz      short loc_180042A29
0x1800429e9  add     [rbx+38h], rdi
0x1800429ed  mov     dword ptr [rbx+24h], 0
0x1800429f4  mov     [rbx+28h], edi
0x1800429f7  mov     edx, [rbx+24h]
0x1800429fa  cmp     edi, ebp
0x1800429fc  mov     ecx, r15d
0x1800429ff  cmova   edi, ebp
0x180042a02  add     rdx, [rbx+18h]; Src
0x180042a06  mov     r8d, edi; Size
0x180042a09  add     rcx, r14; void *
0x180042a0c  call    memcpy
0x180042a11  add     [rbx+24h], edi
0x180042a14  add     r15d, edi
0x180042a17  sub     [rbx+28h], edi
0x180042a1a  sub     ebp, edi
0x180042a1c  jmp     loc_18004296B
0x180042a21  call    cs:GetLastError
0x180042a27  jmp     short loc_180042A34
0x180042a29  sub     [rsi], ebp
0x180042a2b  xor     eax, eax
0x180042a2d  jmp     short loc_180042A34
0x180042a2f  mov     eax, 57h ; 'W'
0x180042a34  add     rsp, 58h
0x180042a38  pop     r15
0x180042a3a  pop     r14
0x180042a3c  pop     rdi
0x180042a3d  pop     rsi
0x180042a3e  pop     rbp
0x180042a3f  pop     rbx
0x180042a40  retn
```
