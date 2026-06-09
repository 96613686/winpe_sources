# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::StartWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140008980`
- end: `0x140008a6e`
- name: `?StartWindowProc@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `238`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140008980`
- `0x14000d780`
- `0x14000d7f8`
- `0x14000d89c`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400089b4`
- `KERNEL32!GetCurrentThreadId` at `0x1400089b4`
- `KERNEL32!LeaveCriticalSection` at `0x1400089ef`
- `KERNEL32!LeaveCriticalSection` at `0x1400089ef`
- `KERNEL32!EnterCriticalSection` at `0x1400089a2`
- `KERNEL32!EnterCriticalSection` at `0x1400089a2`
- `USER32!SetWindowLongPtrW` at `0x140008a47`
- `USER32!SetWindowLongPtrW` at `0x140008a47`

## pseudocode

```c
__int64 __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::StartWindowProc(
        HWND hWnd,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  size_t v8; // rdi
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rax
  void *v14; // rbx
  AtlThunkData_t *Data; // rax
  WNDPROC v16; // rbx

  v8 = 0;
  EnterCriticalSection(&CriticalSection);
  v9 = qword_140015468;
  if ( qword_140015468 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( 1 )
    {
      v12 = *(_QWORD *)(v9 + 16);
      if ( *(_DWORD *)(v9 + 8) == CurrentThreadId )
        break;
      v11 = v9;
      v9 = *(_QWORD *)(v9 + 16);
      if ( !v12 )
        goto LABEL_10;
    }
    if ( v11 )
      *(_QWORD *)(v11 + 16) = v12;
    else
      qword_140015468 = *(_QWORD *)(v9 + 16);
    v8 = *(_QWORD *)v9;
  }
LABEL_10:
  LeaveCriticalSection(&CriticalSection);
  v13 = *(_QWORD *)v8;
  *(_QWORD *)(v8 + 8) = hWnd;
  v14 = (void *)(*(__int64 (__fastcall **)(size_t))(v13 + 8))(v8);
  Data = *(AtlThunkData_t **)(v8 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v8 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v14, v8);
  v16 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v8 + 40));
  SetWindowLongPtrW(hWnd, -4, (LONG_PTR)v16);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v16)(hWnd, a2, a3, a4);
}

```

## disassembly

```asm
0x140008980  push    rbx
0x140008982  push    rbp
0x140008983  push    rsi
0x140008984  push    rdi
0x140008985  push    r14
0x140008987  push    r15
0x140008989  sub     rsp, 38h
0x14000898d  mov     rsi, rcx
0x140008990  mov     rbp, r9
0x140008993  lea     rcx, CriticalSection; lpCriticalSection
0x14000899a  mov     r14, r8
0x14000899d  mov     r15d, edx
0x1400089a0  xor     edi, edi
0x1400089a2  call    cs:__imp_EnterCriticalSection
0x1400089a8  mov     rbx, cs:qword_140015468
0x1400089af  test    rbx, rbx
0x1400089b2  jz      short loc_1400089E8
0x1400089b4  call    cs:__imp_GetCurrentThreadId
0x1400089ba  xor     r8d, r8d
0x1400089bd  mov     rcx, [rbx+10h]
0x1400089c1  cmp     [rbx+8], eax
0x1400089c4  jz      short loc_1400089D3
0x1400089c6  mov     r8, rbx
0x1400089c9  mov     rbx, rcx
0x1400089cc  test    rcx, rcx
0x1400089cf  jnz     short loc_1400089BD
0x1400089d1  jmp     short loc_1400089E8
0x1400089d3  test    r8, r8
0x1400089d6  jnz     short loc_1400089E1
0x1400089d8  mov     cs:qword_140015468, rcx
0x1400089df  jmp     short loc_1400089E5
0x1400089e1  mov     [r8+10h], rcx
0x1400089e5  mov     rdi, [rbx]
0x1400089e8  lea     rcx, CriticalSection; lpCriticalSection
0x1400089ef  call    cs:__imp_LeaveCriticalSection
0x1400089f5  mov     rax, [rdi]
0x1400089f8  mov     rcx, rdi
0x1400089fb  mov     [rdi+8], rsi
0x1400089ff  mov     rax, [rax+8]
0x140008a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a08  mov     rbx, rax
0x140008a0b  mov     rax, [rdi+28h]
0x140008a0f  test    rax, rax
0x140008a12  jnz     short loc_140008A22
0x140008a14  call    AtlThunk_AllocateData
0x140008a19  mov     [rdi+28h], rax
0x140008a1d  test    rax, rax
0x140008a20  jz      short loc_140008A30
0x140008a22  mov     r8, rdi; FirstParameter
0x140008a25  mov     rdx, rbx; Proc
0x140008a28  mov     rcx, rax; Thunk
0x140008a2b  call    AtlThunk_InitData
0x140008a30  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x140008a34  call    AtlThunk_DataToCode
0x140008a39  mov     r8, rax; dwNewLong
0x140008a3c  mov     edx, 0FFFFFFFCh; nIndex
0x140008a41  mov     rcx, rsi; hWnd
0x140008a44  mov     rbx, rax
0x140008a47  call    cs:__imp_SetWindowLongPtrW
0x140008a4d  mov     r9, rbp
0x140008a50  mov     r8, r14
0x140008a53  mov     edx, r15d
0x140008a56  mov     rcx, rsi
0x140008a59  mov     rax, rbx
0x140008a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a61  add     rsp, 38h
0x140008a65  pop     r15
0x140008a67  pop     r14
0x140008a69  pop     rdi
0x140008a6a  pop     rsi
0x140008a6b  pop     rbp
0x140008a6c  pop     rbx
0x140008a6d  retn
```
