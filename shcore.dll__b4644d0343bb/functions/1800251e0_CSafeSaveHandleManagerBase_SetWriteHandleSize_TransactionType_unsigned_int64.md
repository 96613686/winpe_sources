# CSafeSaveHandleManagerBase::_SetWriteHandleSize(TransactionType,unsigned __int64)

- ea: `0x1800251e0`
- end: `0x1800252c3`
- name: `?_SetWriteHandleSize@CSafeSaveHandleManagerBase@@AEAAJW4TransactionType@@_K@Z`
- size: `227`
- prototype: `int __high(enum TransactionType, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008930`
- `0x180026c50`
- `0x180049180`

## callees

- `0x18000ddd4`
- `0x180023730`
- `0x1800251e0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002525d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002525d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180025273`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180025273`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSafeSaveHandleManagerBase::_SetWriteHandleSize(__int64 a1, unsigned int a2, LARGE_INTEGER a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64 *); // rbx
  int v7; // ebx
  HANDLE v8; // rdi
  BOOL v9; // eax
  BOOL v10; // eax
  __int64 v11; // rcx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp+20h] BYREF

  v13 = 0;
  v5 = a1 + 8;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)(a1 + 8) + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v13);
  v7 = v6(v5, a2, &v13);
  if ( v7 >= 0 )
  {
    hFile = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v13 + 24LL))(v13, &hFile);
    if ( v7 >= 0 )
    {
      v8 = hFile;
      v9 = SetFilePointerEx(hFile, a3, 0, 0);
      v7 = ResultFromWin32Bool(v9);
      if ( v7 >= 0 )
      {
        v10 = SetEndOfFile(v8);
        v7 = ResultFromWin32Bool(v10);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
    }
  }
  v11 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800251e0  mov     [rsp+arg_8], rbx
0x1800251e5  push    rbp
0x1800251e6  push    rsi
0x1800251e7  push    rdi
0x1800251e8  sub     rsp, 20h
0x1800251ec  mov     rbp, r8
0x1800251ef  mov     esi, edx
0x1800251f1  mov     [rsp+38h+arg_0], 0
0x1800251fa  lea     rdi, [rcx+8]
0x1800251fe  mov     rax, [rdi]
0x180025201  mov     rbx, [rax+20h]
0x180025205  lea     rcx, [rsp+38h+arg_0]
0x18002520a  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18002520f  lea     r8, [rsp+38h+arg_0]
0x180025214  mov     edx, esi
0x180025216  mov     rcx, rdi
0x180025219  mov     rax, rbx
0x18002521c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025221  mov     ebx, eax
0x180025223  test    eax, eax
0x180025225  js      short loc_180025294
0x180025227  mov     rcx, [rsp+38h+arg_0]
0x18002522c  mov     [rsp+38h+hFile], 0
0x180025235  mov     rax, [rcx]
0x180025238  lea     rdx, [rsp+38h+hFile]
0x18002523d  mov     rax, [rax+18h]
0x180025241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025246  mov     ebx, eax
0x180025248  test    eax, eax
0x18002524a  js      short loc_180025294
0x18002524c  mov     rdi, [rsp+38h+hFile]
0x180025251  xor     r9d, r9d; dwMoveMethod
0x180025254  xor     r8d, r8d; lpNewFilePointer
0x180025257  mov     rdx, rbp; liDistanceToMove
0x18002525a  mov     rcx, rdi; hFile
0x18002525d  call    cs:__imp_SetFilePointerEx
0x180025263  mov     ecx, eax; int
0x180025265  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18002526a  mov     ebx, eax
0x18002526c  test    eax, eax
0x18002526e  js      short loc_180025282
0x180025270  mov     rcx, rdi; hFile
0x180025273  call    cs:__imp_SetEndOfFile
0x180025279  mov     ecx, eax; int
0x18002527b  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180025280  mov     ebx, eax
0x180025282  mov     rcx, [rsp+38h+arg_0]
0x180025287  mov     rax, [rcx]
0x18002528a  mov     rax, [rax+20h]
0x18002528e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025293  nop
0x180025294  mov     rcx, [rsp+38h+arg_0]
0x180025299  test    rcx, rcx
0x18002529c  jz      short loc_1800252B4
0x18002529e  mov     [rsp+38h+arg_0], 0
0x1800252a7  mov     rax, [rcx]
0x1800252aa  mov     rax, [rax+10h]
0x1800252ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252b3  nop
0x1800252b4  mov     eax, ebx
0x1800252b6  mov     rbx, [rsp+38h+arg_8]
0x1800252bb  add     rsp, 20h
0x1800252bf  pop     rdi
0x1800252c0  pop     rsi
0x1800252c1  pop     rbp
0x1800252c2  retn
```
