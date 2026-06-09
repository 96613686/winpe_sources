# ATL::CDialogImplBaseT<WTL::CPropertyPageWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000d070`
- end: `0x18000d181`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCPropertyPageWindow@WTL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `273`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800034c4`
- `0x18000a494`
- `0x18000d070`
- `0x18000ea20`
- `0x18000ea98`
- `0x18000eb34`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0c2`
- `USER32!SetWindowLongPtrW` at `0x18000d15a`
- `USER32!SetWindowLongPtrW` at `0x18000d15a`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImplBaseT<WTL::CPropertyPageWindow>::StartDialogProc(
        HWND hWnd,
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
  v17 = qword_18004D8E8;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v17) < 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v17);
    return 0;
  }
  v8 = qword_18004D910;
  v9 = 0;
  if ( qword_18004D910 )
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
          qword_18004D910 = *(_QWORD *)(v8 + 16);
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
  *(_QWORD *)(v9 + 8) = hWnd;
  v14 = (void *)(*(__int64 (__fastcall **)(size_t))(v13 + 16))(v9);
  Data = *(AtlThunkData_t **)(v9 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v9 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v14, v9);
  v16 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v9 + 40));
  SetWindowLongPtrW(hWnd, 8, (LONG_PTR)v16);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v16)(hWnd, a2, a3, a4);
}

```

## disassembly

```asm
0x18000d070  push    rbx
0x18000d072  push    rbp
0x18000d073  push    rsi
0x18000d074  push    rdi
0x18000d075  push    r14
0x18000d077  push    r15
0x18000d079  sub     rsp, 48h
0x18000d07d  mov     rsi, rcx
0x18000d080  mov     [rsp+78h+var_40], 0
0x18000d085  lea     rax, qword_18004D8E8
0x18000d08c  mov     rbp, r9
0x18000d08f  lea     rcx, [rsp+78h+var_48]
0x18000d094  mov     [rsp+78h+var_48], rax
0x18000d099  mov     r14, r8
0x18000d09c  mov     r15d, edx
0x18000d09f  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000d0a4  test    eax, eax
0x18000d0a6  jns     short loc_18000D0B4
0x18000d0a8  lea     rcx, [rsp+78h+var_48]
0x18000d0ad  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000d0b2  jmp     short loc_18000D104
0x18000d0b4  mov     rbx, cs:qword_18004D910
0x18000d0bb  xor     edi, edi
0x18000d0bd  test    rbx, rbx
0x18000d0c0  jz      short loc_18000D0F5
0x18000d0c2  call    cs:__imp_GetCurrentThreadId
0x18000d0c8  xor     edx, edx
0x18000d0ca  test    rbx, rbx
0x18000d0cd  jz      short loc_18000D0F5
0x18000d0cf  mov     rcx, [rbx+10h]
0x18000d0d3  cmp     [rbx+8], eax
0x18000d0d6  jz      short loc_18000D0E0
0x18000d0d8  mov     rdx, rbx
0x18000d0db  mov     rbx, rcx
0x18000d0de  jmp     short loc_18000D0CA
0x18000d0e0  test    rdx, rdx
0x18000d0e3  jnz     short loc_18000D0EE
0x18000d0e5  mov     cs:qword_18004D910, rcx
0x18000d0ec  jmp     short loc_18000D0F2
0x18000d0ee  mov     [rdx+10h], rcx
0x18000d0f2  mov     rdi, [rbx]
0x18000d0f5  lea     rcx, [rsp+78h+var_48]
0x18000d0fa  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000d0ff  test    rdi, rdi
0x18000d102  jnz     short loc_18000D108
0x18000d104  xor     eax, eax
0x18000d106  jmp     short loc_18000D174
0x18000d108  mov     rax, [rdi]
0x18000d10b  mov     rcx, rdi
0x18000d10e  mov     [rdi+8], rsi
0x18000d112  mov     rax, [rax+10h]
0x18000d116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d11b  mov     rbx, rax
0x18000d11e  mov     rax, [rdi+28h]
0x18000d122  test    rax, rax
0x18000d125  jnz     short loc_18000D135
0x18000d127  call    AtlThunk_AllocateData
0x18000d12c  mov     [rdi+28h], rax
0x18000d130  test    rax, rax
0x18000d133  jz      short loc_18000D143
0x18000d135  mov     r8, rdi; FirstParameter
0x18000d138  mov     rdx, rbx; Proc
0x18000d13b  mov     rcx, rax; Thunk
0x18000d13e  call    AtlThunk_InitData
0x18000d143  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x18000d147  call    AtlThunk_DataToCode
0x18000d14c  mov     r8, rax; dwNewLong
0x18000d14f  mov     edx, 8; nIndex
0x18000d154  mov     rcx, rsi; hWnd
0x18000d157  mov     rbx, rax
0x18000d15a  call    cs:__imp_SetWindowLongPtrW
0x18000d160  mov     r9, rbp
0x18000d163  mov     r8, r14
0x18000d166  mov     edx, r15d
0x18000d169  mov     rcx, rsi
0x18000d16c  mov     rax, rbx
0x18000d16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d174  add     rsp, 48h
0x18000d178  pop     r15
0x18000d17a  pop     r14
0x18000d17c  pop     rdi
0x18000d17d  pop     rsi
0x18000d17e  pop     rbp
0x18000d17f  pop     rbx
0x18000d180  retn
```
