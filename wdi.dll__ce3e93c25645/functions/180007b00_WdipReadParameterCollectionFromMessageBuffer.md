# WdipReadParameterCollectionFromMessageBuffer

- ea: `0x180007b00`
- end: `0x180007d37`
- name: `WdipReadParameterCollectionFromMessageBuffer`
- size: `567`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800063d0`
- `0x18000cc8c`
- `0x18000dc50`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180007900`
- `0x180007b00`
- `0x18000e9e0`
- `0x18000f1c2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ce1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cef`

## string_xrefs

- `0x180007b52`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180007d13`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180007b4b`: `WdipReadParameterCollectionFromMessageBuffer`
- `0x180007d0c`: `WdipReadParameterCollectionFromMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipReadParameterCollectionFromMessageBuffer(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int8 *v5; // rcx
  unsigned int v7; // esi
  unsigned int v8; // r14d
  bool v9; // zf
  unsigned __int8 *v10; // rcx
  int v11; // r8d
  int v12; // r13d
  SIZE_T v13; // rcx
  size_t v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // r15
  __int64 v17; // rbx
  struct __WDIP_PARAMETER *v18; // rax
  __int64 i; // rbx
  _QWORD *v20; // rcx
  void *v21; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int j; // ebx
  HANDLE v24; // rax
  unsigned __int8 *v26; // [rsp+80h] [rbp+8h] BYREF

  v5 = (unsigned __int8 *)(*(unsigned int *)(a2 + 124) + a2 + 40);
  v26 = v5;
  if ( !a1 )
  {
    v7 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterCollectionFromMessageBuffer",
      347,
      (int)L"Error = %d",
      87);
    return v7;
  }
  if ( !v5 || (unsigned __int64)v5 < a2 || (unsigned __int64)&v5[-a2] > a3 || a3 + a2 - (_QWORD)v5 < 4 )
  {
    v11 = 354;
    goto LABEL_34;
  }
  v8 = *(_DWORD *)v5;
  v9 = v5 + 4 == 0;
  v10 = v5 + 4;
  v26 = v10;
  if ( v9 || (unsigned __int64)v10 < a2 || (unsigned __int64)&v10[-a2] > a3 || a3 + a2 - (_QWORD)v10 < 4 )
  {
    v11 = 365;
LABEL_34:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterCollectionFromMessageBuffer",
      v11,
      (int)L"Error = %d",
      111);
    return (unsigned int)-2147024362;
  }
  v12 = *(_DWORD *)v10;
  v7 = 0;
  v26 = v10 + 4;
  if ( !v8 )
  {
    *(_DWORD *)(a1 + 4) = 0;
    *(_DWORD *)a1 = v12;
    return v7;
  }
  v13 = 8 * v8;
  if ( v8 != (v8 & 0x1FFFFFFF) )
    return (unsigned int)-2147024362;
  v14 = (unsigned int)v13;
  v15 = WdipAlloc(v13);
  v16 = v15;
  if ( v15 )
  {
    memset_0(v15, 0, v14);
    v17 = 0;
    while ( 1 )
    {
      v18 = WdipReadParameterFromMessageBuffer((struct _DPS_MESSAGE *)a2, a3, &v26);
      v16[v17] = v18;
      if ( !v18 )
        break;
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= v8 )
      {
        if ( *(_QWORD *)(a1 + 8) )
        {
          for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 4); i = (unsigned int)(i + 1) )
          {
            v20 = (_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * i);
            if ( *v20 )
              WdipDeleteParameter(v20);
          }
          v21 = *(void **)(a1 + 8);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v21);
        }
        *(_QWORD *)(a1 + 8) = v16;
        *(_DWORD *)(a1 + 4) = v8;
        *(_DWORD *)a1 = v12;
        return v7;
      }
    }
    for ( j = 0; j < v8; ++j )
    {
      if ( v16[j] )
      {
        WdipDeleteParameter(&v16[j]);
        v16[j] = 0;
      }
    }
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v16);
  }
  else
  {
    v7 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterCollectionFromMessageBuffer",
      386,
      (int)L"Error = %d",
      14);
  }
  return v7;
}

```

## disassembly

```asm
0x180007b00  push    rbx
0x180007b02  push    rbp
0x180007b03  push    rsi
0x180007b04  push    rdi
0x180007b05  push    r12
0x180007b07  push    r13
0x180007b09  push    r14
0x180007b0b  push    r15
0x180007b0d  sub     rsp, 38h
0x180007b11  mov     eax, [rdx+7Ch]
0x180007b14  mov     rdi, rcx
0x180007b17  lea     rcx, [rdx+28h]
0x180007b1b  mov     r12, r8
0x180007b1e  add     rcx, rax
0x180007b21  mov     rbp, rdx
0x180007b24  mov     [rsp+78h+arg_0], rcx
0x180007b2c  test    rdi, rdi
0x180007b2f  jnz     short loc_180007B63
0x180007b31  mov     esi, 80070057h
0x180007b36  mov     dword ptr [rsp+78h+Args], 57h ; 'W'; Args
0x180007b3e  mov     r8d, 15Bh; int
0x180007b44  lea     r9, aErrorD_0; "Error = %d"
0x180007b4b  lea     rdx, aWdipreadparame_0; "WdipReadParameterCollectionFromMessageB"...
0x180007b52  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007b59  call    WdipTraceError
0x180007b5e  jmp     loc_180007D24
0x180007b63  test    rcx, rcx
0x180007b66  jz      loc_180007CF7
0x180007b6c  cmp     rcx, rbp
0x180007b6f  jb      loc_180007CF7
0x180007b75  mov     rax, rcx
0x180007b78  sub     rax, rbp
0x180007b7b  cmp     rax, r12
0x180007b7e  ja      loc_180007CF7
0x180007b84  mov     rax, rbp
0x180007b87  sub     rax, rcx
0x180007b8a  add     rax, r12
0x180007b8d  cmp     rax, 4
0x180007b91  jb      loc_180007CF7
0x180007b97  mov     r14d, [rcx]
0x180007b9a  add     rcx, 4
0x180007b9e  mov     [rsp+78h+arg_0], rcx
0x180007ba6  jz      short loc_180007BB8
0x180007ba8  cmp     rcx, rbp
0x180007bab  jb      short loc_180007BB8
0x180007bad  mov     rax, rcx
0x180007bb0  sub     rax, rbp
0x180007bb3  cmp     rax, r12
0x180007bb6  jbe     short loc_180007BC3
0x180007bb8  mov     r8d, 16Dh
0x180007bbe  jmp     loc_180007CFD
0x180007bc3  mov     rax, rbp
0x180007bc6  sub     rax, rcx
0x180007bc9  add     rax, r12
0x180007bcc  cmp     rax, 4
0x180007bd0  jb      short loc_180007BB8
0x180007bd2  mov     r13d, [rcx]
0x180007bd5  lea     rax, [rcx+4]
0x180007bd9  xor     esi, esi
0x180007bdb  mov     [rsp+78h+arg_0], rax
0x180007be3  test    r14d, r14d
0x180007be6  jnz     short loc_180007BF3
0x180007be8  mov     [rdi+4], esi
0x180007beb  mov     [rdi], r13d
0x180007bee  jmp     loc_180007D24
0x180007bf3  lea     ecx, ds:0[r14*8]
0x180007bfb  mov     eax, ecx
0x180007bfd  shr     eax, 3
0x180007c00  cmp     r14d, eax
0x180007c03  jnz     loc_180007D1F
0x180007c09  mov     ebx, ecx
0x180007c0b  call    WdipAlloc
0x180007c10  mov     r15, rax
0x180007c13  test    rax, rax
0x180007c16  jnz     short loc_180007C30
0x180007c18  mov     esi, 8007000Eh
0x180007c1d  mov     dword ptr [rsp+78h+Args], 0Eh
0x180007c25  mov     r8d, 182h
0x180007c2b  jmp     loc_180007B44
0x180007c30  mov     r8, rbx; Size
0x180007c33  xor     edx, edx; Val
0x180007c35  mov     rcx, r15; void *
0x180007c38  call    memset_0
0x180007c3d  xor     ebx, ebx
0x180007c3f  test    r14d, r14d
0x180007c42  jz      short loc_180007C73
0x180007c44  nop     dword ptr [rax+00h]
0x180007c48  nop     dword ptr [rax+rax+00000000h]
0x180007c50  lea     r8, [rsp+78h+arg_0]; unsigned __int8 **
0x180007c58  mov     rdx, r12; unsigned __int64
0x180007c5b  mov     rcx, rbp; struct _DPS_MESSAGE *
0x180007c5e  call    ?WdipReadParameterFromMessageBuffer@@YAPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@_KPEAPEAE@Z; WdipReadParameterFromMessageBuffer(_DPS_MESSAGE *,unsigned __int64,uchar * *)
0x180007c63  mov     [r15+rbx*8], rax
0x180007c67  test    rax, rax
0x180007c6a  jz      short loc_180007CBF
0x180007c6c  inc     ebx
0x180007c6e  cmp     ebx, r14d
0x180007c71  jb      short loc_180007C50
0x180007c73  cmp     [rdi+8], rsi
0x180007c77  jz      short loc_180007CB2
0x180007c79  xor     ebx, ebx
0x180007c7b  cmp     [rdi+4], ebx
0x180007c7e  jbe     short loc_180007C9A
0x180007c80  mov     rax, [rdi+8]
0x180007c84  cmp     [rax+rbx*8], rsi
0x180007c88  lea     rcx, [rax+rbx*8]
0x180007c8c  jz      short loc_180007C93
0x180007c8e  call    WdipDeleteParameter
0x180007c93  inc     ebx
0x180007c95  cmp     ebx, [rdi+4]
0x180007c98  jb      short loc_180007C80
0x180007c9a  mov     rbx, [rdi+8]
0x180007c9e  call    cs:__imp_GetProcessHeap
0x180007ca4  mov     r8, rbx; lpMem
0x180007ca7  xor     edx, edx; dwFlags
0x180007ca9  mov     rcx, rax; hHeap
0x180007cac  call    cs:__imp_HeapFree
0x180007cb2  mov     [rdi+8], r15
0x180007cb6  mov     [rdi+4], r14d
0x180007cba  mov     [rdi], r13d
0x180007cbd  jmp     short loc_180007D24
0x180007cbf  xor     ebp, ebp
0x180007cc1  mov     ebx, ebp
0x180007cc3  mov     eax, ebx
0x180007cc5  cmp     [r15+rax*8], rsi
0x180007cc9  lea     rdi, [r15+rax*8]
0x180007ccd  jz      short loc_180007CDA
0x180007ccf  mov     rcx, rdi
0x180007cd2  call    WdipDeleteParameter
0x180007cd7  mov     [rdi], rbp
0x180007cda  inc     ebx
0x180007cdc  cmp     ebx, r14d
0x180007cdf  jb      short loc_180007CC3
0x180007ce1  call    cs:__imp_GetProcessHeap
0x180007ce7  mov     r8, r15; lpMem
0x180007cea  xor     edx, edx; dwFlags
0x180007cec  mov     rcx, rax; hHeap
0x180007cef  call    cs:__imp_HeapFree
0x180007cf5  jmp     short loc_180007D24
0x180007cf7  mov     r8d, 162h; int
0x180007cfd  lea     r9, aErrorD_0; "Error = %d"
0x180007d04  mov     dword ptr [rsp+78h+Args], 6Fh ; 'o'; Args
0x180007d0c  lea     rdx, aWdipreadparame_0; "WdipReadParameterCollectionFromMessageB"...
0x180007d13  lea     rcx, aClientcoreBase_14; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007d1a  call    WdipTraceError
0x180007d1f  mov     esi, 80070216h
0x180007d24  mov     eax, esi
0x180007d26  add     rsp, 38h
0x180007d2a  pop     r15
0x180007d2c  pop     r14
0x180007d2e  pop     r13
0x180007d30  pop     r12
0x180007d32  pop     rdi
0x180007d33  pop     rsi
0x180007d34  pop     rbp
0x180007d35  pop     rbx
0x180007d36  retn
```
