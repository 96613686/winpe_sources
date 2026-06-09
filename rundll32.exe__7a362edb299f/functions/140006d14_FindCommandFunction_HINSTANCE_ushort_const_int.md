# _FindCommandFunction(HINSTANCE__ *,ushort const *,int *)

- ea: `0x140006d14`
- end: `0x140006e3e`
- name: `?_FindCommandFunction@@YAP6AXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z12PEAH@Z`
- size: `298`
- prototype: `void (*__fastcall(HINSTANCE hModule, LPCWCH lpWideCharStr, int *))(HWND, HINSTANCE, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006e44`

## callees

- `0x140006d14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140006d4d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140006d4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006de1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006e18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006de1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006e18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140006d85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140006d85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006e24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006e24`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140006db8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140006db8`

## pseudocode

```c
void (*__fastcall _FindCommandFunction(
        HINSTANCE hModule,
        LPCWCH lpWideCharStr,
        int *a3))(HWND, HINSTANCE, const unsigned __int16 *, int)
{
  FARPROC ProcAddress; // rdi
  unsigned __int16 v7; // ax
  __int64 v8; // rbp
  __int64 v9; // rax
  int v10; // r12d
  CHAR *lpMultiByteStr; // rax
  CHAR *v12; // rbx

  *a3 = 0;
  ProcAddress = 0;
  if ( lpWideCharStr )
  {
    if ( *lpWideCharStr == 35 && lpWideCharStr[1] )
    {
      v7 = _o__wtoi();
      return (void (*)(HWND, HINSTANCE, const unsigned __int16 *, int))GetProcAddress(hModule, (LPCSTR)v7);
    }
    else
    {
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( lpWideCharStr[v9] );
      v10 = v9 + 1;
      lpMultiByteStr = (CHAR *)LocalAlloc(0, (unsigned int)(2 * (v9 + 1) + 2));
      v12 = lpMultiByteStr;
      if ( lpMultiByteStr )
      {
        if ( WideCharToMultiByte(0, 0x400u, lpWideCharStr, v10, lpMultiByteStr, 2 * v10, 0, 0) )
        {
          do
            ++v8;
          while ( v12[v8] );
          v12[(unsigned int)(v8 + 1)] = 0;
          v12[(unsigned int)v8] = 87;
          ProcAddress = GetProcAddress(hModule, v12);
          if ( !ProcAddress )
          {
            *a3 = 1;
            v12[(unsigned int)v8] = 65;
            ProcAddress = GetProcAddress(hModule, v12);
            if ( !ProcAddress )
            {
              v12[(unsigned int)v8] = 0;
              ProcAddress = GetProcAddress(hModule, v12);
            }
          }
        }
        LocalFree(v12);
      }
    }
  }
  return (void (*)(HWND, HINSTANCE, const unsigned __int16 *, int))ProcAddress;
}

```

## disassembly

```asm
0x140006d14  push    rbx
0x140006d16  push    rbp
0x140006d17  push    rsi
0x140006d18  push    rdi
0x140006d19  push    r12
0x140006d1b  push    r13
0x140006d1d  push    r14
0x140006d1f  push    r15
0x140006d21  sub     rsp, 48h
0x140006d25  mov     rsi, rdx
0x140006d28  mov     r15, r8
0x140006d2b  xor     edx, edx
0x140006d2d  mov     r14, rcx
0x140006d30  mov     [r8], edx
0x140006d33  mov     edi, edx
0x140006d35  test    rsi, rsi
0x140006d38  jz      loc_140006E2A
0x140006d3e  cmp     word ptr [rsi], 23h ; '#'
0x140006d42  jnz     short loc_140006D67
0x140006d44  lea     rcx, [rsi+2]
0x140006d48  cmp     [rcx], dx
0x140006d4b  jz      short loc_140006D67
0x140006d4d  call    cs:__imp__o__wtoi
0x140006d53  movzx   edx, ax; lpProcName
0x140006d56  mov     rcx, r14; hModule
0x140006d59  call    cs:__imp_GetProcAddress
0x140006d5f  mov     rdi, rax
0x140006d62  jmp     loc_140006E2A
0x140006d67  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140006d6b  mov     rax, rbp
0x140006d6e  inc     rax
0x140006d71  cmp     [rsi+rax*2], dx
0x140006d75  jnz     short loc_140006D6E
0x140006d77  lea     r12d, [rax+1]
0x140006d7b  xor     ecx, ecx; uFlags
0x140006d7d  lea     r13d, [r12+r12]
0x140006d81  lea     edx, [r13+2]; uBytes
0x140006d85  call    cs:__imp_LocalAlloc
0x140006d8b  mov     rbx, rax
0x140006d8e  test    rax, rax
0x140006d91  jz      loc_140006E2A
0x140006d97  mov     [rsp+88h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x140006d9c  mov     r9d, r12d; cchWideChar
0x140006d9f  mov     [rsp+88h+lpDefaultChar], rdi; lpDefaultChar
0x140006da4  mov     r8, rsi; lpWideCharStr
0x140006da7  mov     [rsp+88h+cbMultiByte], r13d; cbMultiByte
0x140006dac  mov     edx, 400h; dwFlags
0x140006db1  xor     ecx, ecx; CodePage
0x140006db3  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x140006db8  call    cs:__imp_WideCharToMultiByte
0x140006dbe  xor     r12d, r12d
0x140006dc1  test    eax, eax
0x140006dc3  jz      short loc_140006E21
0x140006dc5  inc     rbp
0x140006dc8  cmp     [rbx+rbp], r12b
0x140006dcc  jnz     short loc_140006DC5
0x140006dce  lea     eax, [rbp+1]
0x140006dd1  mov     esi, ebp
0x140006dd3  mov     rdx, rbx; lpProcName
0x140006dd6  mov     [rax+rbx], r12b
0x140006dda  mov     rcx, r14; hModule
0x140006ddd  mov     byte ptr [rsi+rbx], 57h ; 'W'
0x140006de1  call    cs:__imp_GetProcAddress
0x140006de7  mov     rdi, rax
0x140006dea  test    rax, rax
0x140006ded  jnz     short loc_140006E21
0x140006def  mov     rdx, rbx; lpProcName
0x140006df2  mov     dword ptr [r15], 1
0x140006df9  mov     rcx, r14; hModule
0x140006dfc  mov     byte ptr [rsi+rbx], 41h ; 'A'
0x140006e00  call    cs:__imp_GetProcAddress
0x140006e06  mov     rdi, rax
0x140006e09  test    rax, rax
0x140006e0c  jnz     short loc_140006E21
0x140006e0e  mov     rdx, rbx; lpProcName
0x140006e11  mov     [rsi+rbx], r12b
0x140006e15  mov     rcx, r14; hModule
0x140006e18  call    cs:__imp_GetProcAddress
0x140006e1e  mov     rdi, rax
0x140006e21  mov     rcx, rbx; hMem
0x140006e24  call    cs:__imp_LocalFree
0x140006e2a  mov     rax, rdi
0x140006e2d  add     rsp, 48h
0x140006e31  pop     r15
0x140006e33  pop     r14
0x140006e35  pop     r13
0x140006e37  pop     r12
0x140006e39  pop     rdi
0x140006e3a  pop     rsi
0x140006e3b  pop     rbp
0x140006e3c  pop     rbx
0x140006e3d  retn
```
