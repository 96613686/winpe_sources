# RrasSwDeviceCreateCallback

- ea: `0x180007dd0`
- end: `0x180007ecd`
- name: `RrasSwDeviceCreateCallback`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007dd0`
- `0x180007ed4`
- `0x180008eb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007ec1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e42`

## pseudocode

```c
BOOL __fastcall RrasSwDeviceCreateCallback(__int64 a1, size_t a2, __int64 a3, const wchar_t *a4)
{
  HRESULT v6; // eax
  size_t v7; // r14
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v10; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  size_t v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = 0;
  *(_QWORD *)(a3 + 8) = a1;
  *(_DWORD *)(a3 + 16) = a2;
  *(_QWORD *)(a3 + 24) = 0;
  if ( (a2 & 0x80000000) == 0LL )
  {
    if ( a4 )
    {
      v6 = StringLengthWorkerW(a4, a2, &v14);
      if ( v6 >= 0 )
      {
        v7 = v14;
        v8 = 2 * v14 + 2;
        ProcessHeap = GetProcessHeap();
        v10 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v8);
        *(_QWORD *)(a3 + 24) = v10;
        if ( v10 )
        {
          v6 = StringCchCopyW(v10, v7 + 1, a4);
          if ( v6 >= 0 )
            return SetEvent(*(HANDLE *)a3);
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    else
    {
      v6 = -2147024809;
    }
    *(_DWORD *)(a3 + 16) = v6;
    v11 = *(void **)(a3 + 24);
    if ( v11 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v11);
      *(_QWORD *)(a3 + 24) = 0;
    }
  }
  return SetEvent(*(HANDLE *)a3);
}

```

## disassembly

```asm
0x180007dd0  mov     rax, rsp
0x180007dd3  mov     [rax+10h], rbx
0x180007dd7  mov     [rax+18h], rbp
0x180007ddb  push    rsi
0x180007ddc  push    rdi
0x180007ddd  push    r14
0x180007ddf  sub     rsp, 20h
0x180007de3  mov     qword ptr [rax+8], 0
0x180007deb  mov     rbp, r9
0x180007dee  mov     [r8+8], rcx
0x180007df2  mov     rdi, r8
0x180007df5  mov     [r8+10h], edx
0x180007df9  mov     qword ptr [r8+18h], 0
0x180007e01  test    edx, edx
0x180007e03  js      loc_180007EAC
0x180007e09  test    r9, r9
0x180007e0c  jz      short loc_180007E73
0x180007e0e  lea     r8, [rax+8]; pcchLength
0x180007e12  mov     rcx, r9; psz
0x180007e15  call    StringLengthWorkerW
0x180007e1a  test    eax, eax
0x180007e1c  js      short loc_180007E78
0x180007e1e  mov     r14, [rsp+38h+arg_0]
0x180007e23  lea     rbx, ds:2[r14*2]
0x180007e2b  call    cs:__imp_GetProcessHeap
0x180007e32  nop     dword ptr [rax+rax+00h]
0x180007e37  mov     r8, rbx; dwBytes
0x180007e3a  mov     edx, 8; dwFlags
0x180007e3f  mov     rcx, rax; hHeap
0x180007e42  call    cs:__imp_HeapAlloc
0x180007e49  nop     dword ptr [rax+rax+00h]
0x180007e4e  mov     [rdi+18h], rax
0x180007e52  test    rax, rax
0x180007e55  jnz     short loc_180007E5E
0x180007e57  mov     eax, 8007000Eh
0x180007e5c  jmp     short loc_180007E78
0x180007e5e  lea     rdx, [r14+1]; cchDest
0x180007e62  mov     r8, rbp; pszSrc
0x180007e65  mov     rcx, rax; pszDest
0x180007e68  call    StringCchCopyW
0x180007e6d  test    eax, eax
0x180007e6f  jns     short loc_180007EAC
0x180007e71  jmp     short loc_180007E78
0x180007e73  mov     eax, 80070057h
0x180007e78  mov     [rdi+10h], eax
0x180007e7b  mov     rbx, [rdi+18h]
0x180007e7f  test    rbx, rbx
0x180007e82  jz      short loc_180007EAC
0x180007e84  call    cs:__imp_GetProcessHeap
0x180007e8b  nop     dword ptr [rax+rax+00h]
0x180007e90  mov     r8, rbx; lpMem
0x180007e93  xor     edx, edx; dwFlags
0x180007e95  mov     rcx, rax; hHeap
0x180007e98  call    cs:__imp_HeapFree
0x180007e9f  nop     dword ptr [rax+rax+00h]
0x180007ea4  mov     qword ptr [rdi+18h], 0
0x180007eac  mov     rcx, [rdi]
0x180007eaf  mov     rbx, [rsp+38h+arg_8]
0x180007eb4  mov     rbp, [rsp+38h+arg_10]
0x180007eb9  add     rsp, 20h
0x180007ebd  pop     r14
0x180007ebf  pop     rdi
0x180007ec0  pop     rsi
0x180007ec1  jmp     cs:__imp_SetEvent
```
