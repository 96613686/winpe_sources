# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::StartWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180009360`
- end: `0x180009457`
- name: `?StartWindowProc@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `247`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009360`
- `0x18001401c`
- `0x180014094`
- `0x180014138`
- `0x180015010`

## import_xrefs

- `USER32!SetWindowLongPtrA` at `0x180009430`
- `USER32!SetWindowLongPtrA` at `0x180009430`
- `KERNEL32!GetCurrentThreadId` at `0x180009394`
- `KERNEL32!GetCurrentThreadId` at `0x180009394`
- `KERNEL32!LeaveCriticalSection` at `0x1800093cf`
- `KERNEL32!LeaveCriticalSection` at `0x1800093cf`
- `KERNEL32!EnterCriticalSection` at `0x180009380`
- `KERNEL32!EnterCriticalSection` at `0x180009380`

## pseudocode

```c
__int64 __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::StartWindowProc(
        HWND hWnd,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rdi
  size_t v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v14; // rax
  void *v15; // rdi
  AtlThunkData_t *Data; // rax
  WNDPROC v17; // rbx

  EnterCriticalSection(&CriticalSection);
  v8 = qword_18001B750;
  v9 = 0;
  if ( qword_18001B750 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( 1 )
    {
      v12 = *(_QWORD *)(v8 + 16);
      if ( *(_DWORD *)(v8 + 8) == CurrentThreadId )
        break;
      v11 = v8;
      v8 = *(_QWORD *)(v8 + 16);
      if ( !v12 )
        goto LABEL_10;
    }
    if ( v11 )
      *(_QWORD *)(v11 + 16) = v12;
    else
      qword_18001B750 = *(_QWORD *)(v8 + 16);
    v9 = *(_QWORD *)v8;
  }
LABEL_10:
  LeaveCriticalSection(&CriticalSection);
  if ( !v9 )
    return 0;
  v14 = *(_QWORD *)v9;
  *(_QWORD *)(v9 + 8) = hWnd;
  v15 = (void *)(*(__int64 (__fastcall **)(size_t))(v14 + 16))(v9);
  Data = *(AtlThunkData_t **)(v9 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v9 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v15, v9);
  v17 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v9 + 40));
  SetWindowLongPtrA(hWnd, -4, (LONG_PTR)v17);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v17)(hWnd, a2, a3, a4);
}

```

## disassembly

```asm
0x180009360  push    rbx
0x180009362  push    rbp
0x180009363  push    rsi
0x180009364  push    rdi
0x180009365  push    r14
0x180009367  push    r15
0x180009369  sub     rsp, 38h
0x18000936d  mov     rsi, rcx
0x180009370  mov     rbp, r9
0x180009373  lea     rcx, CriticalSection; lpCriticalSection
0x18000937a  mov     r14, r8
0x18000937d  mov     r15d, edx
0x180009380  call    cs:__imp_EnterCriticalSection
0x180009386  mov     rdi, cs:qword_18001B750
0x18000938d  xor     ebx, ebx
0x18000938f  test    rdi, rdi
0x180009392  jz      short loc_1800093C8
0x180009394  call    cs:__imp_GetCurrentThreadId
0x18000939a  xor     r8d, r8d
0x18000939d  mov     rcx, [rdi+10h]
0x1800093a1  cmp     [rdi+8], eax
0x1800093a4  jz      short loc_1800093B3
0x1800093a6  mov     r8, rdi
0x1800093a9  mov     rdi, rcx
0x1800093ac  test    rcx, rcx
0x1800093af  jnz     short loc_18000939D
0x1800093b1  jmp     short loc_1800093C8
0x1800093b3  test    r8, r8
0x1800093b6  jnz     short loc_1800093C1
0x1800093b8  mov     cs:qword_18001B750, rcx
0x1800093bf  jmp     short loc_1800093C5
0x1800093c1  mov     [r8+10h], rcx
0x1800093c5  mov     rbx, [rdi]
0x1800093c8  lea     rcx, CriticalSection; lpCriticalSection
0x1800093cf  call    cs:__imp_LeaveCriticalSection
0x1800093d5  test    rbx, rbx
0x1800093d8  jnz     short loc_1800093DE
0x1800093da  xor     eax, eax
0x1800093dc  jmp     short loc_18000944A
0x1800093de  mov     rax, [rbx]
0x1800093e1  mov     rcx, rbx
0x1800093e4  mov     [rbx+8], rsi
0x1800093e8  mov     rax, [rax+10h]
0x1800093ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f1  mov     rdi, rax
0x1800093f4  mov     rax, [rbx+28h]
0x1800093f8  test    rax, rax
0x1800093fb  jnz     short loc_18000940B
0x1800093fd  call    AtlThunk_AllocateData
0x180009402  mov     [rbx+28h], rax
0x180009406  test    rax, rax
0x180009409  jz      short loc_180009419
0x18000940b  mov     r8, rbx; FirstParameter
0x18000940e  mov     rdx, rdi; Proc
0x180009411  mov     rcx, rax; Thunk
0x180009414  call    AtlThunk_InitData
0x180009419  mov     rcx, [rbx+28h]; AtlThunkData_t *
0x18000941d  call    AtlThunk_DataToCode
0x180009422  mov     r8, rax; dwNewLong
0x180009425  mov     edx, 0FFFFFFFCh; nIndex
0x18000942a  mov     rcx, rsi; hWnd
0x18000942d  mov     rbx, rax
0x180009430  call    cs:__imp_SetWindowLongPtrA
0x180009436  mov     r9, rbp
0x180009439  mov     r8, r14
0x18000943c  mov     edx, r15d
0x18000943f  mov     rcx, rsi
0x180009442  mov     rax, rbx
0x180009445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000944a  add     rsp, 38h
0x18000944e  pop     r15
0x180009450  pop     r14
0x180009452  pop     rdi
0x180009453  pop     rsi
0x180009454  pop     rbp
0x180009455  pop     rbx
0x180009456  retn
```
