# ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000baa0`
- end: `0x18000bbb1`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `273`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180003014`
- `0x180008560`
- `0x18000baa0`
- `0x180026ce0`
- `0x180026d58`
- `0x180026df4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000baf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000baf2`
- `USER32!SetWindowLongPtrW` at `0x18000bb8a`
- `USER32!SetWindowLongPtrW` at `0x18000bb8a`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(
        HWND a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rbx
  size_t v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // rdx
  __int64 v13; // rax
  void *v14; // rbx
  AtlThunkData_t *Data; // rax
  WNDPROC v16; // rbx
  __int64 *v17; // [rsp+30h] [rbp-48h] BYREF
  char v18; // [rsp+38h] [rbp-40h]

  v18 = 0;
  v17 = qword_18003FA18;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v17) < 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v17);
    return 0;
  }
  v8 = qword_18003FA40;
  v9 = 0;
  if ( qword_18003FA40 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( v8 )
    {
      if ( *(_DWORD *)(v8 + 8) == CurrentThreadId )
      {
        if ( v11 )
          *(_QWORD *)(v11 + 16) = *(_QWORD *)(v8 + 16);
        else
          qword_18003FA40 = *(_QWORD *)(v8 + 16);
        v9 = *(_QWORD *)v8;
        break;
      }
      v11 = v8;
      v8 = *(_QWORD *)(v8 + 16);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v17);
  if ( !v9 )
    return 0;
  v13 = *(_QWORD *)v9;
  *(_QWORD *)(v9 + 8) = a1;
  v14 = (void *)(*(__int64 (__fastcall **)(size_t))(v13 + 16))(v9);
  Data = *(AtlThunkData_t **)(v9 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v9 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v14, v9);
  v16 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v9 + 40));
  SetWindowLongPtrW(a1, 8, (LONG_PTR)v16);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v16)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000baa0  push    rbx
0x18000baa2  push    rbp
0x18000baa3  push    rsi
0x18000baa4  push    rdi
0x18000baa5  push    r14
0x18000baa7  push    r15
0x18000baa9  sub     rsp, 48h
0x18000baad  mov     rsi, rcx
0x18000bab0  mov     [rsp+78h+var_40], 0
0x18000bab5  lea     rax, qword_18003FA18
0x18000babc  mov     rbp, r9
0x18000babf  lea     rcx, [rsp+78h+var_48]
0x18000bac4  mov     [rsp+78h+var_48], rax
0x18000bac9  mov     r14, r8
0x18000bacc  mov     r15d, edx
0x18000bacf  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000bad4  test    eax, eax
0x18000bad6  jns     short loc_18000BAE4
0x18000bad8  lea     rcx, [rsp+78h+var_48]
0x18000badd  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000bae2  jmp     short loc_18000BB34
0x18000bae4  mov     rbx, cs:qword_18003FA40
0x18000baeb  xor     edi, edi
0x18000baed  test    rbx, rbx
0x18000baf0  jz      short loc_18000BB25
0x18000baf2  call    cs:__imp_GetCurrentThreadId
0x18000baf8  xor     edx, edx
0x18000bafa  test    rbx, rbx
0x18000bafd  jz      short loc_18000BB25
0x18000baff  mov     rcx, [rbx+10h]
0x18000bb03  cmp     [rbx+8], eax
0x18000bb06  jz      short loc_18000BB10
0x18000bb08  mov     rdx, rbx
0x18000bb0b  mov     rbx, rcx
0x18000bb0e  jmp     short loc_18000BAFA
0x18000bb10  test    rdx, rdx
0x18000bb13  jnz     short loc_18000BB1E
0x18000bb15  mov     cs:qword_18003FA40, rcx
0x18000bb1c  jmp     short loc_18000BB22
0x18000bb1e  mov     [rdx+10h], rcx
0x18000bb22  mov     rdi, [rbx]
0x18000bb25  lea     rcx, [rsp+78h+var_48]
0x18000bb2a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000bb2f  test    rdi, rdi
0x18000bb32  jnz     short loc_18000BB38
0x18000bb34  xor     eax, eax
0x18000bb36  jmp     short loc_18000BBA4
0x18000bb38  mov     rax, [rdi]
0x18000bb3b  mov     rcx, rdi
0x18000bb3e  mov     [rdi+8], rsi
0x18000bb42  mov     rax, [rax+10h]
0x18000bb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb4b  mov     rbx, rax
0x18000bb4e  mov     rax, [rdi+28h]
0x18000bb52  test    rax, rax
0x18000bb55  jnz     short loc_18000BB65
0x18000bb57  call    AtlThunk_AllocateData
0x18000bb5c  mov     [rdi+28h], rax
0x18000bb60  test    rax, rax
0x18000bb63  jz      short loc_18000BB73
0x18000bb65  mov     r8, rdi; FirstParameter
0x18000bb68  mov     rdx, rbx; Proc
0x18000bb6b  mov     rcx, rax; Thunk
0x18000bb6e  call    AtlThunk_InitData
0x18000bb73  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x18000bb77  call    AtlThunk_DataToCode
0x18000bb7c  mov     r8, rax; dwNewLong
0x18000bb7f  mov     edx, 8; nIndex
0x18000bb84  mov     rcx, rsi; hWnd
0x18000bb87  mov     rbx, rax
0x18000bb8a  call    cs:__imp_SetWindowLongPtrW
0x18000bb90  mov     r9, rbp
0x18000bb93  mov     r8, r14
0x18000bb96  mov     edx, r15d
0x18000bb99  mov     rcx, rsi
0x18000bb9c  mov     rax, rbx
0x18000bb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bba4  add     rsp, 48h
0x18000bba8  pop     r15
0x18000bbaa  pop     r14
0x18000bbac  pop     rdi
0x18000bbad  pop     rsi
0x18000bbae  pop     rbp
0x18000bbaf  pop     rbx
0x18000bbb0  retn
```
