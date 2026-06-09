# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::SubclassWindow(HWND__ *)

- ea: `0x140008a74`
- end: `0x140008afd`
- name: `?SubclassWindow@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAHPEAUHWND__@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(size_t FirstParameter, HWND hWnd)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002f70`
- `0x140003470`
- `0x140003d60`

## callees

- `0x140008a74`
- `0x14000d780`
- `0x14000d7f8`
- `0x14000d89c`
- `0x14000f010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x140008ad1`
- `USER32!SetWindowLongPtrW` at `0x140008ad1`

## pseudocode

```c
__int64 __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::SubclassWindow(
        size_t FirstParameter,
        HWND hWnd)
{
  void *v4; // rsi
  AtlThunkData_t *Data; // rax
  WNDPROC v6; // rax
  LONG_PTR v7; // rax
  __int64 result; // rax

  v4 = (void *)(*(__int64 (__fastcall **)(size_t))(*(_QWORD *)FirstParameter + 8LL))(FirstParameter);
  Data = *(AtlThunkData_t **)(FirstParameter + 40);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *(_QWORD *)(FirstParameter + 40) = Data;
    if ( !Data )
      return 0;
  }
  AtlThunk_InitData(Data, v4, FirstParameter);
  v6 = AtlThunk_DataToCode(*(AtlThunkData_t **)(FirstParameter + 40));
  v7 = SetWindowLongPtrW(hWnd, -4, (LONG_PTR)v6);
  if ( !v7 )
    return 0;
  *(_QWORD *)(FirstParameter + 56) = v7;
  result = 1;
  *(_QWORD *)(FirstParameter + 8) = hWnd;
  return result;
}

```

## disassembly

```asm
0x140008a74  mov     [rsp+arg_0], rbx
0x140008a79  mov     [rsp+arg_8], rsi
0x140008a7e  push    rdi
0x140008a7f  sub     rsp, 20h
0x140008a83  mov     rax, [rcx]
0x140008a86  mov     rdi, rdx
0x140008a89  mov     rbx, rcx
0x140008a8c  mov     rax, [rax+8]
0x140008a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a95  mov     rsi, rax
0x140008a98  mov     rax, [rbx+28h]
0x140008a9c  test    rax, rax
0x140008a9f  jnz     short loc_140008AAF
0x140008aa1  call    AtlThunk_AllocateData
0x140008aa6  mov     [rbx+28h], rax
0x140008aaa  test    rax, rax
0x140008aad  jz      short loc_140008ADC
0x140008aaf  mov     r8, rbx; FirstParameter
0x140008ab2  mov     rdx, rsi; Proc
0x140008ab5  mov     rcx, rax; Thunk
0x140008ab8  call    AtlThunk_InitData
0x140008abd  mov     rcx, [rbx+28h]; AtlThunkData_t *
0x140008ac1  call    AtlThunk_DataToCode
0x140008ac6  mov     r8, rax; dwNewLong
0x140008ac9  mov     edx, 0FFFFFFFCh; nIndex
0x140008ace  mov     rcx, rdi; hWnd
0x140008ad1  call    cs:__imp_SetWindowLongPtrW
0x140008ad7  test    rax, rax
0x140008ada  jnz     short loc_140008AE0
0x140008adc  xor     eax, eax
0x140008ade  jmp     short loc_140008AED
0x140008ae0  mov     [rbx+38h], rax
0x140008ae4  mov     eax, 1
0x140008ae9  mov     [rbx+8], rdi
0x140008aed  mov     rbx, [rsp+28h+arg_0]
0x140008af2  mov     rsi, [rsp+28h+arg_8]
0x140008af7  add     rsp, 20h
0x140008afb  pop     rdi
0x140008afc  retn
```
