# _CreateHGlobalFromStream(IStream *,void * *,ulong *)

- ea: `0x1800520ac`
- end: `0x1800521ae`
- name: `?_CreateHGlobalFromStream@@YAJPEAUIStream@@PEAPEAXPEAK@Z`
- size: `258`
- prototype: `__int64 __fastcall(struct IStream *pstm, void **, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180019f64`
- `0x1800553b0`
- `0x180056160`
- `0x1800619c0`

## callees

- `0x1800520ac`

## import_xrefs

- `SHCORE!IStream_Read` at `0x180052160`
- `SHCORE!IStream_Read` at `0x180052160`
- `SHCORE!IStream_Size` at `0x1800520d8`
- `SHCORE!IStream_Size` at `0x1800520d8`
- `SHCORE!IStream_Reset` at `0x18005214b`
- `SHCORE!IStream_Reset` at `0x18005216f`
- `SHCORE!IStream_Reset` at `0x18005214b`
- `SHCORE!IStream_Reset` at `0x18005216f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180052122`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180052122`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005210f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005210f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180052186`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180052186`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180052133`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180052133`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall _CreateHGlobalFromStream(struct IStream *pstm, void **a2, unsigned int *a3)
{
  ULONG LowPart; // esi
  HRESULT v7; // edi
  unsigned int StringW; // eax
  HGLOBAL v9; // rbx
  void *v10; // rax
  ULARGE_INTEGER pui; // [rsp+58h] [rbp+10h] BYREF
  __int64 Buffer; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  LowPart = 0;
  pui.QuadPart = 0;
  v7 = IStream_Size(pstm, &pui);
  if ( v7 < 0 )
  {
LABEL_4:
    Buffer = 0;
    StringW = LoadStringW(&_ImageBase, 9u, (LPWSTR)&Buffer, 0);
    if ( !StringW )
      goto LABEL_13;
    RoOriginateErrorW((unsigned int)v7, StringW, Buffer);
    if ( v7 < 0 )
      goto LABEL_13;
    goto LABEL_6;
  }
  LowPart = pui.LowPart;
  if ( pui.HighPart )
  {
    v7 = -2147483637;
    goto LABEL_4;
  }
LABEL_6:
  v9 = GlobalAlloc(0x40u, LowPart);
  if ( v9 )
  {
    v7 = IStream_Reset(pstm);
    if ( v7 >= 0 )
    {
      v7 = IStream_Read(pstm, v9, LowPart);
      if ( v7 >= 0 )
      {
        v7 = IStream_Reset(pstm);
        if ( v7 >= 0 )
        {
          v10 = v9;
          v9 = 0;
          *a2 = v10;
        }
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  GlobalFree(v9);
LABEL_13:
  if ( a3 )
  {
    if ( v7 < 0 )
      LowPart = 0;
    *a3 = LowPart;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800520ac  mov     [rsp+arg_0], rbx
0x1800520b1  push    rbp
0x1800520b2  push    rsi
0x1800520b3  push    rdi
0x1800520b4  push    r14
0x1800520b6  push    r15
0x1800520b8  sub     rsp, 20h
0x1800520bc  mov     r15, rdx
0x1800520bf  mov     qword ptr [rdx], 0
0x1800520c6  xor     esi, esi
0x1800520c8  lea     rdx, [rsp+48h+pui]; pui
0x1800520cd  mov     qword ptr [rsp+48h+pui], rsi
0x1800520d2  mov     r14, r8
0x1800520d5  mov     rbp, rcx
0x1800520d8  call    cs:__imp_IStream_Size
0x1800520de  mov     edi, eax
0x1800520e0  test    eax, eax
0x1800520e2  js      short loc_1800520F3
0x1800520e4  cmp     dword ptr [rsp+48h+pui+4], esi
0x1800520e8  mov     esi, dword ptr [rsp+48h+pui]
0x1800520ec  jz      short loc_18005212C
0x1800520ee  mov     edi, 8000000Bh
0x1800520f3  xor     r9d, r9d; cchBufferMax
0x1800520f6  mov     [rsp+48h+Buffer], 0
0x1800520ff  lea     r8, [rsp+48h+Buffer]; lpBuffer
0x180052104  lea     rcx, __ImageBase; hInstance
0x18005210b  lea     edx, [r9+9]; uID
0x18005210f  call    cs:__imp_LoadStringW
0x180052115  test    eax, eax
0x180052117  jz      short loc_18005218C
0x180052119  mov     r8, [rsp+48h+Buffer]
0x18005211e  mov     edx, eax
0x180052120  mov     ecx, edi
0x180052122  call    cs:__imp_RoOriginateErrorW
0x180052128  test    edi, edi
0x18005212a  js      short loc_18005218C
0x18005212c  mov     edx, esi; dwBytes
0x18005212e  mov     ecx, 40h ; '@'; uFlags
0x180052133  call    cs:__imp_GlobalAlloc
0x180052139  mov     rbx, rax
0x18005213c  test    rax, rax
0x18005213f  jnz     short loc_180052148
0x180052141  mov     edi, 8007000Eh
0x180052146  jmp     short loc_180052183
0x180052148  mov     rcx, rbp; pstm
0x18005214b  call    cs:__imp_IStream_Reset
0x180052151  mov     edi, eax
0x180052153  test    eax, eax
0x180052155  js      short loc_180052183
0x180052157  mov     r8d, esi; cb
0x18005215a  mov     rdx, rbx; pv
0x18005215d  mov     rcx, rbp; pstm
0x180052160  call    cs:__imp_IStream_Read
0x180052166  mov     edi, eax
0x180052168  test    eax, eax
0x18005216a  js      short loc_180052183
0x18005216c  mov     rcx, rbp; pstm
0x18005216f  call    cs:__imp_IStream_Reset
0x180052175  mov     edi, eax
0x180052177  test    eax, eax
0x180052179  js      short loc_180052183
0x18005217b  mov     rax, rbx
0x18005217e  xor     ebx, ebx
0x180052180  mov     [r15], rax
0x180052183  mov     rcx, rbx; hMem
0x180052186  call    cs:__imp_GlobalFree
0x18005218c  test    r14, r14
0x18005218f  jz      short loc_18005219B
0x180052191  xor     eax, eax
0x180052193  test    edi, edi
0x180052195  cmovs   esi, eax
0x180052198  mov     [r14], esi
0x18005219b  mov     rbx, [rsp+48h+arg_0]
0x1800521a0  mov     eax, edi
0x1800521a2  add     rsp, 20h
0x1800521a6  pop     r15
0x1800521a8  pop     r14
0x1800521aa  pop     rdi
0x1800521ab  pop     rsi
0x1800521ac  pop     rbp
0x1800521ad  retn
```
