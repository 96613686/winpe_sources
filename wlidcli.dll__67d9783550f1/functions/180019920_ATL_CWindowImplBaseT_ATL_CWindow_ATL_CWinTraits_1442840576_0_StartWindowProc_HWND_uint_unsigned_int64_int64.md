# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::StartWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180019920`
- end: `0x180019a31`
- name: `?StartWindowProc@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `273`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000c354`
- `0x18000c830`
- `0x180019920`
- `0x180042c18`
- `0x180042c90`
- `0x180042d2c`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019972`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019972`
- `USER32!SetWindowLongPtrW` at `0x180019a0a`
- `USER32!SetWindowLongPtrW` at `0x180019a0a`

## pseudocode

```c
__int64 __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::StartWindowProc(
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
  v17 = qword_1800946C8;
  if ( (int)CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(&v17) < 0 )
  {
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v17);
    return 0;
  }
  v8 = qword_1800946F0;
  v9 = 0;
  if ( qword_1800946F0 )
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
          qword_1800946F0 = *(_QWORD *)(v8 + 16);
        v9 = *(_QWORD *)v8;
        break;
      }
      v11 = v8;
      v8 = *(_QWORD *)(v8 + 16);
    }
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v17);
  if ( !v9 )
    return 0;
  v13 = *(_QWORD *)v9;
  *(_QWORD *)(v9 + 8) = hWnd;
  v14 = (void *)(*(__int64 (__fastcall **)(size_t))(v13 + 16))(v9);
  Data = *(AtlThunkData_t **)(v9 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v9 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v14, v9);
  v16 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v9 + 40));
  SetWindowLongPtrW(hWnd, -4, (LONG_PTR)v16);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v16)(hWnd, a2, a3, a4);
}

```

## disassembly

```asm
0x180019920  push    rbx
0x180019922  push    rbp
0x180019923  push    rsi
0x180019924  push    rdi
0x180019925  push    r14
0x180019927  push    r15
0x180019929  sub     rsp, 48h
0x18001992d  mov     rsi, rcx
0x180019930  mov     [rsp+78h+var_40], 0
0x180019935  lea     rax, qword_1800946C8
0x18001993c  mov     rbp, r9
0x18001993f  lea     rcx, [rsp+78h+var_48]
0x180019944  mov     [rsp+78h+var_48], rax
0x180019949  mov     r14, r8
0x18001994c  mov     r15d, edx
0x18001994f  call    ?Lock@?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAAJXZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(void)
0x180019954  test    eax, eax
0x180019956  jns     short loc_180019964
0x180019958  lea     rcx, [rsp+78h+var_48]
0x18001995d  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180019962  jmp     short loc_1800199B4
0x180019964  mov     rbx, cs:qword_1800946F0
0x18001996b  xor     edi, edi
0x18001996d  test    rbx, rbx
0x180019970  jz      short loc_1800199A5
0x180019972  call    cs:__imp_GetCurrentThreadId
0x180019978  xor     edx, edx
0x18001997a  test    rbx, rbx
0x18001997d  jz      short loc_1800199A5
0x18001997f  mov     rcx, [rbx+10h]
0x180019983  cmp     [rbx+8], eax
0x180019986  jz      short loc_180019990
0x180019988  mov     rdx, rbx
0x18001998b  mov     rbx, rcx
0x18001998e  jmp     short loc_18001997A
0x180019990  test    rdx, rdx
0x180019993  jnz     short loc_18001999E
0x180019995  mov     cs:qword_1800946F0, rcx
0x18001999c  jmp     short loc_1800199A2
0x18001999e  mov     [rdx+10h], rcx
0x1800199a2  mov     rdi, [rbx]
0x1800199a5  lea     rcx, [rsp+78h+var_48]
0x1800199aa  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800199af  test    rdi, rdi
0x1800199b2  jnz     short loc_1800199B8
0x1800199b4  xor     eax, eax
0x1800199b6  jmp     short loc_180019A24
0x1800199b8  mov     rax, [rdi]
0x1800199bb  mov     rcx, rdi
0x1800199be  mov     [rdi+8], rsi
0x1800199c2  mov     rax, [rax+10h]
0x1800199c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199cb  mov     rbx, rax
0x1800199ce  mov     rax, [rdi+28h]
0x1800199d2  test    rax, rax
0x1800199d5  jnz     short loc_1800199E5
0x1800199d7  call    AtlThunk_AllocateData
0x1800199dc  mov     [rdi+28h], rax
0x1800199e0  test    rax, rax
0x1800199e3  jz      short loc_1800199F3
0x1800199e5  mov     r8, rdi; FirstParameter
0x1800199e8  mov     rdx, rbx; Proc
0x1800199eb  mov     rcx, rax; Thunk
0x1800199ee  call    AtlThunk_InitData
0x1800199f3  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x1800199f7  call    AtlThunk_DataToCode
0x1800199fc  mov     r8, rax; dwNewLong
0x1800199ff  mov     edx, 0FFFFFFFCh; nIndex
0x180019a04  mov     rcx, rsi; hWnd
0x180019a07  mov     rbx, rax
0x180019a0a  call    cs:__imp_SetWindowLongPtrW
0x180019a10  mov     r9, rbp
0x180019a13  mov     r8, r14
0x180019a16  mov     edx, r15d
0x180019a19  mov     rcx, rsi
0x180019a1c  mov     rax, rbx
0x180019a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a24  add     rsp, 48h
0x180019a28  pop     r15
0x180019a2a  pop     r14
0x180019a2c  pop     rdi
0x180019a2d  pop     rsi
0x180019a2e  pop     rbp
0x180019a2f  pop     rbx
0x180019a30  retn
```
