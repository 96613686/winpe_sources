# SDiagPrviCopyPWSTR(ushort const *,ushort * *)

- ea: `0x180002ac4`
- end: `0x180002bea`
- name: `?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z`
- size: `294`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1800087e0`
- `0x18000c980`
- `0x18000e3e8`
- `0x18000f654`
- `0x18000fd98`
- `0x18000fe60`
- `0x180012070`
- `0x1800122b8`

## callees

- `0x180002ac4`
- `0x180003350`
- `0x1800033a4`
- `0x1800034e4`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002b7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002b7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002b16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002bca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002b16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002bca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002b69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002bbc`

## pseudocode

```c
__int64 __fastcall SDiagPrviCopyPWSTR(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // ebx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // r15
  HANDLE v9; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rsi
  HANDLE v12; // rax
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = 0;
  dwBytes = 0;
  if ( a2 && a1 )
  {
    v5 = *a2;
    if ( *a2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      *a2 = 0;
    }
    v4 = StringCchLengthW(a1, 0x7FFFFFFFu, &v15);
    if ( v4 >= 0 )
    {
      v7 = v15;
      v8 = v15 + 1;
      if ( v15 + 1 < v15 )
      {
        return (unsigned int)-2147024362;
      }
      else
      {
        v4 = ULongLongMult(v15 + 1, 2u, &dwBytes);
        if ( v4 >= 0 )
        {
          v9 = GetProcessHeap();
          v10 = (unsigned __int16 *)HeapAlloc(v9, 8u, dwBytes);
          v11 = v10;
          if ( v10 )
          {
            memset_0(v10, 0, dwBytes);
            v4 = StringCchCopyNW(v11, v8, a1, v7);
            if ( v4 < 0 )
            {
              v12 = GetProcessHeap();
              HeapFree(v12, 0, v11);
            }
            else
            {
              *a2 = v11;
            }
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002ac4  mov     [rsp+arg_0], rbx
0x180002ac9  push    rbp
0x180002aca  push    rsi
0x180002acb  push    rdi
0x180002acc  push    r14
0x180002ace  push    r15
0x180002ad0  sub     rsp, 20h
0x180002ad4  mov     [rsp+48h+arg_10], 0
0x180002add  mov     rdi, rdx
0x180002ae0  mov     [rsp+48h+dwBytes], 0
0x180002ae9  mov     r14, rcx
0x180002aec  test    rdx, rdx
0x180002aef  jnz     short loc_180002AFB
0x180002af1  mov     ebx, 80070057h
0x180002af6  jmp     loc_180002BD7
0x180002afb  test    r14, r14
0x180002afe  jz      short loc_180002AF1
0x180002b00  mov     rbx, [rdx]
0x180002b03  test    rbx, rbx
0x180002b06  jz      short loc_180002B23
0x180002b08  call    cs:__imp_GetProcessHeap
0x180002b0e  mov     r8, rbx; lpMem
0x180002b11  xor     edx, edx; dwFlags
0x180002b13  mov     rcx, rax; hHeap
0x180002b16  call    cs:__imp_HeapFree
0x180002b1c  mov     qword ptr [rdi], 0
0x180002b23  lea     r8, [rsp+48h+arg_10]; unsigned __int64 *
0x180002b28  mov     edx, 7FFFFFFFh; unsigned __int64
0x180002b2d  mov     rcx, r14; unsigned __int16 *
0x180002b30  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180002b35  mov     ebx, eax
0x180002b37  test    eax, eax
0x180002b39  js      loc_180002BD7
0x180002b3f  mov     rbp, [rsp+48h+arg_10]
0x180002b44  lea     r15, [rbp+1]
0x180002b48  cmp     r15, rbp
0x180002b4b  jb      loc_180002BD2
0x180002b51  lea     r8, [rsp+48h+dwBytes]; unsigned __int64 *
0x180002b56  mov     edx, 2; unsigned __int64
0x180002b5b  mov     rcx, r15; unsigned __int64
0x180002b5e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180002b63  mov     ebx, eax
0x180002b65  test    eax, eax
0x180002b67  js      short loc_180002BD7
0x180002b69  call    cs:__imp_GetProcessHeap
0x180002b6f  mov     r8, [rsp+48h+dwBytes]; dwBytes
0x180002b74  mov     edx, 8; dwFlags
0x180002b79  mov     rcx, rax; hHeap
0x180002b7c  call    cs:__imp_HeapAlloc
0x180002b82  mov     rsi, rax
0x180002b85  test    rax, rax
0x180002b88  jnz     short loc_180002B91
0x180002b8a  mov     ebx, 8007000Eh
0x180002b8f  jmp     short loc_180002BD7
0x180002b91  mov     r8, [rsp+48h+dwBytes]; Size
0x180002b96  xor     edx, edx; Val
0x180002b98  mov     rcx, rsi; void *
0x180002b9b  call    memset_0
0x180002ba0  mov     r9, rbp; unsigned __int64
0x180002ba3  mov     r8, r14; unsigned __int16 *
0x180002ba6  mov     rdx, r15; unsigned __int64
0x180002ba9  mov     rcx, rsi; unsigned __int16 *
0x180002bac  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180002bb1  mov     ebx, eax
0x180002bb3  test    eax, eax
0x180002bb5  js      short loc_180002BBC
0x180002bb7  mov     [rdi], rsi
0x180002bba  jmp     short loc_180002BD7
0x180002bbc  call    cs:__imp_GetProcessHeap
0x180002bc2  mov     r8, rsi; lpMem
0x180002bc5  xor     edx, edx; dwFlags
0x180002bc7  mov     rcx, rax; hHeap
0x180002bca  call    cs:__imp_HeapFree
0x180002bd0  jmp     short loc_180002BD7
0x180002bd2  mov     ebx, 80070216h
0x180002bd7  mov     eax, ebx
0x180002bd9  mov     rbx, [rsp+48h+arg_0]
0x180002bde  add     rsp, 20h
0x180002be2  pop     r15
0x180002be4  pop     r14
0x180002be6  pop     rdi
0x180002be7  pop     rsi
0x180002be8  pop     rbp
0x180002be9  retn
```
