# WdipAddParameterToCollection

- ea: `0x180007630`
- end: `0x1800077d5`
- name: `WdipAddParameterToCollection`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800048c0`
- `0x1800077e0`
- `0x18000cc8c`

## callees

- `0x180002ba0`
- `0x180007630`
- `0x18000f1b6`
- `0x18000f1c2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007741`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007741`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000774f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000774f`

## string_xrefs

- `0x18000766b`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x1800077ad`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`

## pseudocode

```c
__int64 __fastcall WdipAddParameterToCollection(__int64 a1, __int64 a2)
{
  int v4; // r8d
  __int64 v6; // rbx
  size_t v7; // r14
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  void *v10; // rsi
  unsigned int v11; // ebx
  unsigned __int64 v12; // rax
  void *v13; // rbx
  HANDLE v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // eax
  int v17; // r8d

  if ( !a1 )
  {
    v4 = 1230;
LABEL_3:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipAddParameterToCollection",
      v4,
      (int)L"Error = %d",
      87);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v4 = 1231;
    goto LABEL_3;
  }
  v6 = *(unsigned int *)(a1 + 4);
  if ( (int)v6 + 1 < (unsigned int)v6 || (_DWORD)v6 + 1 != (unsigned int)(8 * v6 + 8) >> 3 )
    return 2147942934LL;
  v7 = (unsigned int)(8 * v6 + 8);
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v7);
  v10 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, v7);
    v12 = 8LL * *(unsigned int *)(a1 + 4);
    if ( v12 > 0xFFFFFFFF )
    {
      v17 = 1262;
    }
    else
    {
      memcpy_0(v10, *(const void **)(a1 + 8), (unsigned int)v12);
      *((_QWORD *)v10 + v6) = a2;
      v13 = *(void **)(a1 + 8);
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v13);
      *(_QWORD *)(a1 + 8) = v10;
      v15 = *(_DWORD *)a1 + *(_DWORD *)(a2 + 32);
      if ( v15 < *(_DWORD *)a1 )
      {
        *(_DWORD *)a1 = -1;
        v17 = 1276;
      }
      else
      {
        v16 = *(_DWORD *)(a1 + 4);
        *(_DWORD *)a1 = v15;
        if ( v16 + 1 >= v16 )
        {
          *(_DWORD *)(a1 + 4) = v16 + 1;
          return 0;
        }
        *(_DWORD *)(a1 + 4) = -1;
        v17 = 1279;
      }
    }
    v11 = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipAddParameterToCollection",
      v17,
      (int)L"Error = %d",
      22);
    return v11;
  }
  v11 = -2147024882;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
    (int)L"WdipAddParameterToCollection",
    1255,
    (int)L"Error = %d",
    14);
  return v11;
}

```

## disassembly

```asm
0x180007630  mov     [rsp+arg_10], rbx
0x180007635  mov     [rsp+arg_18], rbp
0x18000763a  push    rdi
0x18000763b  sub     rsp, 30h
0x18000763f  mov     rbp, rdx
0x180007642  mov     rdi, rcx
0x180007645  test    rcx, rcx
0x180007648  jnz     short loc_180007689
0x18000764a  mov     r8d, 4CEh; int
0x180007650  lea     r9, aErrorD_0; "Error = %d"
0x180007657  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x18000765f  lea     rdx, aWdipaddparamet; "WdipAddParameterToCollection"
0x180007666  mov     ebx, 80070057h
0x18000766b  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007672  call    WdipTraceError
0x180007677  mov     eax, ebx
0x180007679  mov     rbx, [rsp+38h+arg_10]
0x18000767e  mov     rbp, [rsp+38h+arg_18]
0x180007683  add     rsp, 30h
0x180007687  pop     rdi
0x180007688  retn
0x180007689  test    rbp, rbp
0x18000768c  jnz     short loc_180007696
0x18000768e  mov     r8d, 4CFh
0x180007694  jmp     short loc_180007650
0x180007696  mov     ebx, [rcx+4]
0x180007699  lea     ecx, [rbx+1]
0x18000769c  cmp     ecx, ebx
0x18000769e  jnb     short loc_1800076B7
0x1800076a0  mov     ebx, 80070216h
0x1800076a5  mov     eax, ebx
0x1800076a7  mov     rbx, [rsp+38h+arg_10]
0x1800076ac  mov     rbp, [rsp+38h+arg_18]
0x1800076b1  add     rsp, 30h
0x1800076b5  pop     rdi
0x1800076b6  retn
0x1800076b7  lea     edx, ds:8[rbx*8]
0x1800076be  mov     eax, edx
0x1800076c0  shr     eax, 3
0x1800076c3  cmp     ecx, eax
0x1800076c5  jnz     short loc_1800076A0
0x1800076c7  mov     [rsp+38h+arg_0], rsi
0x1800076cc  mov     [rsp+38h+arg_8], r14
0x1800076d1  mov     r14d, edx
0x1800076d4  call    cs:__imp_GetProcessHeap
0x1800076da  mov     r8d, r14d; dwBytes
0x1800076dd  mov     edx, 8; dwFlags
0x1800076e2  mov     rcx, rax; hHeap
0x1800076e5  call    cs:__imp_HeapAlloc
0x1800076eb  mov     rsi, rax
0x1800076ee  test    rax, rax
0x1800076f1  jnz     short loc_18000770B
0x1800076f3  mov     ebx, 8007000Eh
0x1800076f8  mov     dword ptr [rsp+38h+Args], 0Eh
0x180007700  mov     r8d, 4E7h
0x180007706  jmp     loc_18000779F
0x18000770b  mov     r8, r14; Size
0x18000770e  xor     edx, edx; Val
0x180007710  mov     rcx, rsi; void *
0x180007713  call    memset_0
0x180007718  mov     eax, [rdi+4]
0x18000771b  mov     r14d, 0FFFFFFFFh
0x180007721  shl     rax, 3
0x180007725  cmp     rax, r14
0x180007728  ja      short loc_18000778C
0x18000772a  mov     rdx, [rdi+8]; Src
0x18000772e  mov     rcx, rsi; void *
0x180007731  mov     r8d, eax; Size
0x180007734  call    memcpy_0
0x180007739  mov     [rsi+rbx*8], rbp
0x18000773d  mov     rbx, [rdi+8]
0x180007741  call    cs:__imp_GetProcessHeap
0x180007747  mov     r8, rbx; lpMem
0x18000774a  xor     edx, edx; dwFlags
0x18000774c  mov     rcx, rax; hHeap
0x18000774f  call    cs:__imp_HeapFree
0x180007755  mov     [rdi+8], rsi
0x180007759  mov     edx, [rbp+20h]
0x18000775c  add     edx, [rdi]
0x18000775e  cmp     edx, [rdi]
0x180007760  jb      short loc_180007781
0x180007762  mov     eax, [rdi+4]
0x180007765  mov     [rdi], edx
0x180007767  lea     ecx, [rax+1]
0x18000776a  cmp     ecx, eax
0x18000776c  jb      short loc_180007775
0x18000776e  mov     [rdi+4], ecx
0x180007771  xor     ebx, ebx
0x180007773  jmp     short loc_1800077B9
0x180007775  mov     [rdi+4], r14d
0x180007779  mov     r8d, 4FFh
0x18000777f  jmp     short loc_180007792
0x180007781  mov     [rdi], r14d
0x180007784  mov     r8d, 4FCh
0x18000778a  jmp     short loc_180007792
0x18000778c  mov     r8d, 4EEh; int
0x180007792  mov     ebx, 80070216h
0x180007797  mov     dword ptr [rsp+38h+Args], 216h; Args
0x18000779f  lea     r9, aErrorD_0; "Error = %d"
0x1800077a6  lea     rdx, aWdipaddparamet; "WdipAddParameterToCollection"
0x1800077ad  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800077b4  call    WdipTraceError
0x1800077b9  mov     rsi, [rsp+38h+arg_0]
0x1800077be  mov     r14, [rsp+38h+arg_8]
0x1800077c3  mov     rbp, [rsp+38h+arg_18]
0x1800077c8  mov     eax, ebx
0x1800077ca  mov     rbx, [rsp+38h+arg_10]
0x1800077cf  add     rsp, 30h
0x1800077d3  pop     rdi
0x1800077d4  retn
```
