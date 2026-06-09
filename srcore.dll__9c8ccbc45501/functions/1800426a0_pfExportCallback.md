# pfExportCallback

- ea: `0x1800426a0`
- end: `0x18004283c`
- name: `pfExportCallback`
- size: `412`
- prototype: `DWORD __fastcall(PBYTE pbData, __m128i *pvCallbackContext, ULONG ulLength)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18003fac4`
- `0x1800426a0`
- `0x180052ff2`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180042747`
- `KERNEL32!CloseHandle` at `0x180042747`
- `KERNEL32!WriteFile` at `0x1800427b0`
- `KERNEL32!WriteFile` at `0x1800427b0`
- `KERNEL32!CreateFileW` at `0x180042730`
- `KERNEL32!CreateFileW` at `0x180042730`
- `KERNEL32!GetLastError` at `0x18004280f`
- `KERNEL32!GetLastError` at `0x18004280f`

## pseudocode

```c
DWORD __fastcall pfExportCallback(PBYTE pbData, __m128i *pvCallbackContext, ULONG ulLength)
{
  int v6; // r14d
  unsigned __int32 v7; // eax
  ULONG v8; // edi
  HANDLE FileW; // rax
  char *v10; // rcx
  HANDLE v11; // rdi
  DWORD v12; // r8d
  const void *v13; // rdx
  void *v14; // rcx
  unsigned __int64 v15; // rax
  __m128i v16; // xmm0
  __m128i v17; // xmm1
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-38h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !pbData )
    return 87;
  v6 = 0;
  if ( !pvCallbackContext )
    return 87;
  while ( ulLength )
  {
    v7 = pvCallbackContext[2].m128i_u32[1];
    v8 = pvCallbackContext[2].m128i_i32[0] - v7;
    if ( !v8 )
    {
      if ( !pvCallbackContext[3].m128i_i64[1] )
      {
        sub_18003FAC4((LPCWSTR)pvCallbackContext->m128i_i64[0]);
        FileW = CreateFileW((LPCWSTR)pvCallbackContext->m128i_i64[0], 0x12019Fu, 3u, 0, 2u, 0x2000000u, 0);
        v10 = (char *)pvCallbackContext[1].m128i_i64[0];
        v11 = FileW;
        if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v10);
        pvCallbackContext[1].m128i_i64[0] = (__int64)v11;
        if ( v11 == (HANDLE)-1LL || !v11 )
          return GetLastError();
      }
      v12 = pvCallbackContext[2].m128i_u32[1];
      v13 = (const void *)pvCallbackContext[1].m128i_i64[1];
      v14 = (void *)pvCallbackContext[1].m128i_i64[0];
      Overlapped.OffsetHigh = HIDWORD(pvCallbackContext[3].m128i_i64[1]);
      Overlapped.Offset = pvCallbackContext[3].m128i_u32[2];
      Overlapped.Internal = 0;
      Overlapped.InternalHigh = 0;
      Overlapped.hEvent = 0;
      if ( !WriteFile(v14, v13, v12, &NumberOfBytesWritten, &Overlapped) )
        return GetLastError();
      v15 = NumberOfBytesWritten;
      if ( NumberOfBytesWritten != pvCallbackContext[2].m128i_i32[1] )
        return 234;
      v16 = _mm_loadu_si128(pvCallbackContext + 3);
      v8 = pvCallbackContext[2].m128i_u32[0];
      pvCallbackContext[2].m128i_i32[1] = 0;
      v17 = _mm_unpacklo_epi64((__m128i)v15, (__m128i)v15);
      v7 = 0;
      pvCallbackContext[3] = _mm_add_epi64(v17, v16);
    }
    if ( v8 > ulLength )
      v8 = ulLength;
    memcpy((void *)(pvCallbackContext[1].m128i_i64[1] + v7), &pbData[v6], v8);
    pvCallbackContext[2].m128i_i32[1] += v8;
    v6 += v8;
    ulLength -= v8;
  }
  return 0;
}

```

## disassembly

```asm
0x1800426a0  mov     rax, rsp
0x1800426a3  mov     [rax+10h], rbx
0x1800426a7  mov     [rax+18h], rbp
0x1800426ab  push    rsi
0x1800426ac  push    rdi
0x1800426ad  push    r14
0x1800426af  sub     rsp, 60h
0x1800426b3  mov     dword ptr [rax+8], 0
0x1800426ba  xorps   xmm0, xmm0
0x1800426bd  mov     esi, r8d
0x1800426c0  mov     rbx, rdx
0x1800426c3  mov     rbp, rcx
0x1800426c6  movups  xmmword ptr [rax-38h], xmm0
0x1800426ca  movups  xmmword ptr [rax-28h], xmm0
0x1800426ce  test    rcx, rcx
0x1800426d1  jz      loc_180042822
0x1800426d7  xor     r14d, r14d
0x1800426da  test    rdx, rdx
0x1800426dd  jz      loc_180042822
0x1800426e3  test    esi, esi
0x1800426e5  jz      loc_18004281E
0x1800426eb  mov     edi, [rbx+20h]
0x1800426ee  mov     eax, [rbx+24h]
0x1800426f1  sub     edi, eax
0x1800426f3  jnz     loc_1800427E9
0x1800426f9  cmp     qword ptr [rbx+38h], 0
0x1800426fe  jnz     short loc_180042764
0x180042700  mov     rcx, [rbx]; lpFileName
0x180042703  call    sub_18003FAC4
0x180042708  mov     rcx, [rbx]; lpFileName
0x18004270b  lea     r8d, [rdi+3]; dwShareMode
0x18004270f  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180042718  xor     r9d, r9d; lpSecurityAttributes
0x18004271b  mov     [rsp+78h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180042723  mov     edx, 12019Fh; dwDesiredAccess
0x180042728  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x180042730  call    cs:CreateFileW
0x180042736  mov     rcx, [rbx+10h]; hObject
0x18004273a  mov     rdi, rax
0x18004273d  lea     rdx, [rcx-1]
0x180042741  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180042745  ja      short loc_18004274D
0x180042747  call    cs:CloseHandle
0x18004274d  mov     [rbx+10h], rdi
0x180042751  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180042755  jz      loc_18004280F
0x18004275b  test    rdi, rdi
0x18004275e  jz      loc_18004280F
0x180042764  mov     rax, [rbx+38h]
0x180042768  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180042770  mov     r8d, [rbx+24h]; nNumberOfBytesToWrite
0x180042774  mov     rdx, [rbx+18h]; lpBuffer
0x180042778  mov     rcx, [rbx+10h]; hFile
0x18004277c  shr     rax, 20h
0x180042780  mov     dword ptr [rsp+78h+Overlapped.10h+4], eax
0x180042784  mov     eax, [rbx+38h]
0x180042787  mov     dword ptr [rsp+78h+Overlapped.10h], eax
0x18004278b  lea     rax, [rsp+78h+Overlapped]
0x180042790  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpOverlapped
0x180042795  mov     [rsp+78h+Overlapped.Internal], 0
0x18004279e  mov     [rsp+78h+Overlapped.InternalHigh], 0
0x1800427a7  mov     [rsp+78h+Overlapped.hEvent], 0
0x1800427b0  call    cs:WriteFile
0x1800427b6  test    eax, eax
0x1800427b8  jz      short loc_18004280F
0x1800427ba  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x1800427c1  cmp     eax, [rbx+24h]
0x1800427c4  jnz     short loc_180042817
0x1800427c6  movdqu  xmm0, xmmword ptr [rbx+30h]
0x1800427cb  mov     edi, [rbx+20h]
0x1800427ce  movq    xmm1, rax
0x1800427d3  mov     dword ptr [rbx+24h], 0
0x1800427da  punpcklqdq xmm1, xmm1
0x1800427de  xor     eax, eax
0x1800427e0  paddq   xmm1, xmm0
0x1800427e4  movdqu  xmmword ptr [rbx+30h], xmm1
0x1800427e9  mov     ecx, eax
0x1800427eb  cmp     edi, esi
0x1800427ed  mov     edx, r14d
0x1800427f0  cmova   edi, esi
0x1800427f3  add     rcx, [rbx+18h]; void *
0x1800427f7  mov     r8d, edi; Size
0x1800427fa  add     rdx, rbp; Src
0x1800427fd  call    memcpy
0x180042802  add     [rbx+24h], edi
0x180042805  add     r14d, edi
0x180042808  sub     esi, edi
0x18004280a  jmp     loc_1800426E3
0x18004280f  call    cs:GetLastError
0x180042815  jmp     short loc_180042827
0x180042817  mov     eax, 0EAh
0x18004281c  jmp     short loc_180042827
0x18004281e  xor     eax, eax
0x180042820  jmp     short loc_180042827
0x180042822  mov     eax, 57h ; 'W'
0x180042827  lea     r11, [rsp+78h+var_18]
0x18004282c  mov     rbx, [r11+28h]
0x180042830  mov     rbp, [r11+30h]
0x180042834  mov     rsp, r11
0x180042837  pop     r14
0x180042839  pop     rdi
0x18004283a  pop     rsi
0x18004283b  retn
```
