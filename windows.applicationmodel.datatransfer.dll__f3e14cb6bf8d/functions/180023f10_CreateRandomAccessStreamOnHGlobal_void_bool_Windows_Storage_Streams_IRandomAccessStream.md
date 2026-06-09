# CreateRandomAccessStreamOnHGlobal(void * &&,bool,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x180023f10`
- end: `0x180024029`
- name: `?CreateRandomAccessStreamOnHGlobal@@YAJ$$QEAPEAX_NPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004a1a0`
- `0x180053b00`
- `0x180055ce0`
- `0x180055fe0`

## callees

- `0x180023f10`
- `0x18002415c`
- `0x180036544`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180023fe8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180023fe8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023fd6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023fd6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023f81`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023f81`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180023f5d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180024010`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180023f5d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateRandomAccessStreamOnHGlobal(HGLOBAL *a1, char a2, _QWORD *a3)
{
  HRESULT StreamOnHGlobal; // edi
  HGLOBAL v7; // rbx
  HGLOBAL v8; // rax
  unsigned int StringW; // eax
  HGLOBAL v10; // rcx
  HGLOBAL hGlobal; // [rsp+60h] [rbp+40h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *Buffer; // [rsp+68h] [rbp+48h] BYREF

  *a3 = 0;
  hGlobal = 0;
  if ( a2 )
  {
    GlobalFree(0);
    v7 = *a1;
    *a1 = 0;
  }
  else
  {
    StreamOnHGlobal = GlobalClone(*a1, &hGlobal);
    v7 = hGlobal;
    if ( StreamOnHGlobal < 0 )
      goto LABEL_14;
  }
  hGlobal = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(v7, 1, (LPSTREAM *)&hGlobal);
  if ( StreamOnHGlobal < 0 )
  {
    if ( a2 )
    {
      v8 = v7;
      v7 = 0;
      *a1 = v8;
    }
    goto LABEL_10;
  }
  v7 = 0;
  Buffer = 0;
  StreamOnHGlobal = CreateReadOnlyRandomAccessStreamOverStream((struct IStream *)hGlobal, &Buffer);
  *a3 = Buffer;
  if ( StreamOnHGlobal < 0 )
  {
LABEL_10:
    Buffer = 0;
    StringW = LoadStringW(&_ImageBase, 6u, (LPWSTR)&Buffer, 0);
    if ( StringW )
      RoOriginateErrorW((unsigned int)StreamOnHGlobal, StringW, Buffer);
  }
  v10 = hGlobal;
  if ( hGlobal )
  {
    hGlobal = 0;
    (*(void (__fastcall **)(HGLOBAL))(*(_QWORD *)v10 + 16LL))(v10);
  }
LABEL_14:
  GlobalFree(v7);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180023f10  mov     [rsp-28h+arg_0], rbx
0x180023f15  push    rbp
0x180023f16  push    rsi
0x180023f17  push    rdi
0x180023f18  push    r14
0x180023f1a  push    r15
0x180023f1c  mov     rbp, rsp
0x180023f1f  sub     rsp, 20h
0x180023f23  mov     r15, r8
0x180023f26  mov     r14b, dl
0x180023f29  mov     rsi, rcx
0x180023f2c  mov     qword ptr [r8], 0
0x180023f33  mov     [rbp+hGlobal], 0
0x180023f3b  test    dl, dl
0x180023f3d  jnz     short loc_180023F5B
0x180023f3f  lea     rdx, [rbp+hGlobal]; void **
0x180023f43  mov     rcx, [rcx]; hMem
0x180023f46  call    ?GlobalClone@@YAJPEAXPEAPEAX@Z; GlobalClone(void *,void * *)
0x180023f4b  mov     edi, eax
0x180023f4d  mov     rbx, [rbp+hGlobal]
0x180023f51  test    eax, eax
0x180023f53  js      loc_18002400D
0x180023f59  jmp     short loc_180023F6D
0x180023f5b  xor     ecx, ecx; hMem
0x180023f5d  call    cs:__imp_GlobalFree
0x180023f63  mov     rbx, [rsi]
0x180023f66  mov     qword ptr [rsi], 0
0x180023f6d  mov     [rbp+hGlobal], 0
0x180023f75  lea     r8, [rbp+hGlobal]; ppstm
0x180023f79  mov     edx, 1; fDeleteOnRelease
0x180023f7e  mov     rcx, rbx; hGlobal
0x180023f81  call    cs:__imp_CreateStreamOnHGlobal
0x180023f87  mov     edi, eax
0x180023f89  test    eax, eax
0x180023f8b  js      short loc_180023FAF
0x180023f8d  xor     ebx, ebx
0x180023f8f  mov     [rbp+Buffer], rbx
0x180023f93  lea     rdx, [rbp+Buffer]; struct Windows::Storage::Streams::IRandomAccessStream **
0x180023f97  mov     rcx, [rbp+hGlobal]; struct IStream *
0x180023f9b  call    ?CreateReadOnlyRandomAccessStreamOverStream@@YAJPEAUIStream@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CreateReadOnlyRandomAccessStreamOverStream(IStream *,Windows::Storage::Streams::IRandomAccessStream * *)
0x180023fa0  mov     edi, eax
0x180023fa2  mov     rax, [rbp+Buffer]
0x180023fa6  mov     [r15], rax
0x180023fa9  test    edi, edi
0x180023fab  jns     short loc_180023FEF
0x180023fad  jmp     short loc_180023FBC
0x180023faf  test    r14b, r14b
0x180023fb2  jz      short loc_180023FBC
0x180023fb4  mov     rax, rbx
0x180023fb7  xor     ebx, ebx
0x180023fb9  mov     [rsi], rax
0x180023fbc  mov     [rbp+Buffer], 0
0x180023fc4  xor     r9d, r9d; cchBufferMax
0x180023fc7  lea     r8, [rbp+Buffer]; lpBuffer
0x180023fcb  lea     edx, [r9+6]; uID
0x180023fcf  lea     rcx, __ImageBase; hInstance
0x180023fd6  call    cs:__imp_LoadStringW
0x180023fdc  test    eax, eax
0x180023fde  jz      short loc_180023FEF
0x180023fe0  mov     r8, [rbp+Buffer]
0x180023fe4  mov     edx, eax
0x180023fe6  mov     ecx, edi
0x180023fe8  call    cs:__imp_RoOriginateErrorW
0x180023fee  nop
0x180023fef  mov     rcx, [rbp+hGlobal]
0x180023ff3  test    rcx, rcx
0x180023ff6  jz      short loc_18002400D
0x180023ff8  mov     [rbp+hGlobal], 0
0x180024000  mov     rax, [rcx]
0x180024003  mov     rax, [rax+10h]
0x180024007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002400c  nop
0x18002400d  mov     rcx, rbx; hMem
0x180024010  call    cs:__imp_GlobalFree
0x180024016  mov     eax, edi
0x180024018  mov     rbx, [rsp+20h+arg_0]
0x18002401d  add     rsp, 20h
0x180024021  pop     r15
0x180024023  pop     r14
0x180024025  pop     rdi
0x180024026  pop     rsi
0x180024027  pop     rbp
0x180024028  retn
```
