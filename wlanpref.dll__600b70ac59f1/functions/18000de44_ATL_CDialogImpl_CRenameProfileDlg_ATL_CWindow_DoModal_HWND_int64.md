# ATL::CDialogImpl<CRenameProfileDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x18000de44`
- end: `0x18000df1e`
- name: `?DoModal@?$CDialogImpl@VCRenameProfileDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800114c0`

## callees

- `0x180003014`
- `0x180008560`
- `0x18000de44`
- `0x1800116a4`
- `0x180026ce0`
- `0x180026df4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000df17`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000df17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000de73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000de73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000deab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000deab`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CRenameProfileDlg,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
{
  AtlThunkData_t *Data; // rax
  __int64 *v6; // [rsp+30h] [rbp-18h] BYREF
  char v7; // [rsp+38h] [rbp-10h]

  Data = *(AtlThunkData_t **)(a1 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(a1 + 40) = Data) != 0) )
  {
    AtlThunk_InitData(Data, 0, 0);
    if ( a1 == -16 || !a1 )
    {
      RaiseException(0xC0000005, 1u, 0, 0);
      JUMPOUT(0x18000DF1DLL);
    }
    *(_QWORD *)(a1 + 16) = a1;
    v7 = 0;
    *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
    v6 = qword_18003FA18;
    if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v6) >= 0 )
    {
      *(_QWORD *)(a1 + 32) = qword_18003FA40;
      qword_18003FA40 = a1 + 16;
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v6);
    return IsolationAwareDialogBoxParamW(hInstance, (LPCWSTR)0x4E5F, a2);
  }
  else
  {
    SetLastError(0xEu);
    return -1;
  }
}

```

## disassembly

```asm
0x18000de44  mov     [rsp+arg_0], rbx
0x18000de49  mov     [rsp+arg_8], rsi
0x18000de4e  push    rdi
0x18000de4f  sub     rsp, 40h
0x18000de53  mov     rax, [rcx+28h]
0x18000de57  mov     rsi, rdx
0x18000de5a  mov     rdi, rcx
0x18000de5d  test    rax, rax
0x18000de60  jnz     short loc_18000DE8D
0x18000de62  call    AtlThunk_AllocateData
0x18000de67  mov     [rdi+28h], rax
0x18000de6b  test    rax, rax
0x18000de6e  jnz     short loc_18000DE8D
0x18000de70  lea     ecx, [rax+0Eh]; dwErrCode
0x18000de73  call    cs:__imp_SetLastError
0x18000de79  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000de7d  mov     rbx, [rsp+48h+arg_0]
0x18000de82  mov     rsi, [rsp+48h+arg_8]
0x18000de87  add     rsp, 40h
0x18000de8b  pop     rdi
0x18000de8c  retn
0x18000de8d  xor     r8d, r8d; FirstParameter
0x18000de90  xor     edx, edx; Proc
0x18000de92  mov     rcx, rax; Thunk
0x18000de95  call    AtlThunk_InitData
0x18000de9a  lea     rbx, [rdi+10h]
0x18000de9e  test    rbx, rbx
0x18000dea1  jz      short loc_18000DF08
0x18000dea3  test    rdi, rdi
0x18000dea6  jz      short loc_18000DF08
0x18000dea8  mov     [rbx], rdi
0x18000deab  call    cs:__imp_GetCurrentThreadId
0x18000deb1  lea     rcx, [rsp+48h+var_18]
0x18000deb6  mov     [rsp+48h+var_10], 0
0x18000debb  mov     [rbx+8], eax
0x18000debe  lea     rax, qword_18003FA18
0x18000dec5  mov     [rsp+48h+var_18], rax
0x18000deca  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000decf  test    eax, eax
0x18000ded1  js      short loc_18000DEE5
0x18000ded3  mov     rax, cs:qword_18003FA40
0x18000deda  mov     [rbx+10h], rax
0x18000dede  mov     cs:qword_18003FA40, rbx
0x18000dee5  lea     rcx, [rsp+48h+var_18]
0x18000deea  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000deef  mov     rcx, cs:hInstance; hInstance
0x18000def6  mov     r8, rsi; hWndParent
0x18000def9  mov     edx, 4E5Fh; lpTemplateName
0x18000defe  call    IsolationAwareDialogBoxParamW
0x18000df03  jmp     loc_18000DE7D
0x18000df08  xor     r9d, r9d; lpArguments
0x18000df0b  xor     r8d, r8d; nNumberOfArguments
0x18000df0e  mov     ecx, 0C0000005h; dwExceptionCode
0x18000df13  lea     edx, [r9+1]; dwExceptionFlags
0x18000df17  call    cs:__imp_RaiseException
```
