# RrasSwDeviceCreateCallback

- ea: `0x180007660`
- end: `0x180007740`
- name: `RrasSwDeviceCreateCallback`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007660`
- `0x180007748`
- `0x18000864c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007739`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007716`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007716`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007708`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076cc`

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
0x180007660  mov     rax, rsp
0x180007663  mov     [rax+10h], rbx
0x180007667  mov     [rax+18h], rbp
0x18000766b  push    rsi
0x18000766c  push    rdi
0x18000766d  push    r14
0x18000766f  sub     rsp, 20h
0x180007673  mov     qword ptr [rax+8], 0
0x18000767b  mov     rbp, r9
0x18000767e  mov     [r8+8], rcx
0x180007682  mov     rdi, r8
0x180007685  mov     [r8+10h], edx
0x180007689  mov     qword ptr [r8+18h], 0
0x180007691  test    edx, edx
0x180007693  js      loc_180007724
0x180007699  test    r9, r9
0x18000769c  jz      short loc_1800076F7
0x18000769e  lea     r8, [rax+8]; pcchLength
0x1800076a2  mov     rcx, r9; psz
0x1800076a5  call    StringLengthWorkerW
0x1800076aa  test    eax, eax
0x1800076ac  js      short loc_1800076FC
0x1800076ae  mov     r14, [rsp+38h+arg_0]
0x1800076b3  lea     rbx, ds:2[r14*2]
0x1800076bb  call    cs:__imp_GetProcessHeap
0x1800076c1  mov     r8, rbx; dwBytes
0x1800076c4  mov     edx, 8; dwFlags
0x1800076c9  mov     rcx, rax; hHeap
0x1800076cc  call    cs:__imp_HeapAlloc
0x1800076d2  mov     [rdi+18h], rax
0x1800076d6  test    rax, rax
0x1800076d9  jnz     short loc_1800076E2
0x1800076db  mov     eax, 8007000Eh
0x1800076e0  jmp     short loc_1800076FC
0x1800076e2  lea     rdx, [r14+1]; cchDest
0x1800076e6  mov     r8, rbp; pszSrc
0x1800076e9  mov     rcx, rax; pszDest
0x1800076ec  call    StringCchCopyW
0x1800076f1  test    eax, eax
0x1800076f3  jns     short loc_180007724
0x1800076f5  jmp     short loc_1800076FC
0x1800076f7  mov     eax, 80070057h
0x1800076fc  mov     [rdi+10h], eax
0x1800076ff  mov     rbx, [rdi+18h]
0x180007703  test    rbx, rbx
0x180007706  jz      short loc_180007724
0x180007708  call    cs:__imp_GetProcessHeap
0x18000770e  mov     r8, rbx; lpMem
0x180007711  xor     edx, edx; dwFlags
0x180007713  mov     rcx, rax; hHeap
0x180007716  call    cs:__imp_HeapFree
0x18000771c  mov     qword ptr [rdi+18h], 0
0x180007724  mov     rcx, [rdi]
0x180007727  mov     rbx, [rsp+38h+arg_8]
0x18000772c  mov     rbp, [rsp+38h+arg_10]
0x180007731  add     rsp, 20h
0x180007735  pop     r14
0x180007737  pop     rdi
0x180007738  pop     rsi
0x180007739  jmp     cs:__imp_SetEvent
```
