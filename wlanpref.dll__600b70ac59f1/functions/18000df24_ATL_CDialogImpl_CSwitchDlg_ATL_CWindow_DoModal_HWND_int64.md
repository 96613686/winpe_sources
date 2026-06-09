# ATL::CDialogImpl<CSwitchDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x18000df24`
- end: `0x18000dffe`
- name: `?DoModal@?$CDialogImpl@VCSwitchDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fdf0`

## callees

- `0x180003014`
- `0x180008560`
- `0x18000df24`
- `0x1800116a4`
- `0x180026ce0`
- `0x180026df4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dff7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dff7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000df53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000df53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000df8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000df8b`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CSwitchDlg,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x18000DFFDLL);
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
    return IsolationAwareDialogBoxParamW(hInstance, (LPCWSTR)0x4E64, a2);
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
0x18000df24  mov     [rsp+arg_0], rbx
0x18000df29  mov     [rsp+arg_8], rsi
0x18000df2e  push    rdi
0x18000df2f  sub     rsp, 40h
0x18000df33  mov     rax, [rcx+28h]
0x18000df37  mov     rsi, rdx
0x18000df3a  mov     rdi, rcx
0x18000df3d  test    rax, rax
0x18000df40  jnz     short loc_18000DF6D
0x18000df42  call    AtlThunk_AllocateData
0x18000df47  mov     [rdi+28h], rax
0x18000df4b  test    rax, rax
0x18000df4e  jnz     short loc_18000DF6D
0x18000df50  lea     ecx, [rax+0Eh]; dwErrCode
0x18000df53  call    cs:__imp_SetLastError
0x18000df59  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000df5d  mov     rbx, [rsp+48h+arg_0]
0x18000df62  mov     rsi, [rsp+48h+arg_8]
0x18000df67  add     rsp, 40h
0x18000df6b  pop     rdi
0x18000df6c  retn
0x18000df6d  xor     r8d, r8d; FirstParameter
0x18000df70  xor     edx, edx; Proc
0x18000df72  mov     rcx, rax; Thunk
0x18000df75  call    AtlThunk_InitData
0x18000df7a  lea     rbx, [rdi+10h]
0x18000df7e  test    rbx, rbx
0x18000df81  jz      short loc_18000DFE8
0x18000df83  test    rdi, rdi
0x18000df86  jz      short loc_18000DFE8
0x18000df88  mov     [rbx], rdi
0x18000df8b  call    cs:__imp_GetCurrentThreadId
0x18000df91  lea     rcx, [rsp+48h+var_18]
0x18000df96  mov     [rsp+48h+var_10], 0
0x18000df9b  mov     [rbx+8], eax
0x18000df9e  lea     rax, qword_18003FA18
0x18000dfa5  mov     [rsp+48h+var_18], rax
0x18000dfaa  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000dfaf  test    eax, eax
0x18000dfb1  js      short loc_18000DFC5
0x18000dfb3  mov     rax, cs:qword_18003FA40
0x18000dfba  mov     [rbx+10h], rax
0x18000dfbe  mov     cs:qword_18003FA40, rbx
0x18000dfc5  lea     rcx, [rsp+48h+var_18]
0x18000dfca  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000dfcf  mov     rcx, cs:hInstance; hInstance
0x18000dfd6  mov     r8, rsi; hWndParent
0x18000dfd9  mov     edx, 4E64h; lpTemplateName
0x18000dfde  call    IsolationAwareDialogBoxParamW
0x18000dfe3  jmp     loc_18000DF5D
0x18000dfe8  xor     r9d, r9d; lpArguments
0x18000dfeb  xor     r8d, r8d; nNumberOfArguments
0x18000dfee  mov     ecx, 0C0000005h; dwExceptionCode
0x18000dff3  lea     edx, [r9+1]; dwExceptionFlags
0x18000dff7  call    cs:__imp_RaiseException
```
