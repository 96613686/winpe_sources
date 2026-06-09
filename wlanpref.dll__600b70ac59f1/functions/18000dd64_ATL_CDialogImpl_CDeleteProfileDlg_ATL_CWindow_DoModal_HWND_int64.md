# ATL::CDialogImpl<CDeleteProfileDlg,ATL::CWindow>::DoModal(HWND__ *,__int64)

- ea: `0x18000dd64`
- end: `0x18000de3e`
- name: `?DoModal@?$CDialogImpl@VCDeleteProfileDlg@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dd14`

## callees

- `0x180003014`
- `0x180008560`
- `0x18000dd64`
- `0x1800116a4`
- `0x180026ce0`
- `0x180026df4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000de37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000de37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ddcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ddcb`

## pseudocode

```c
__int64 __fastcall ATL::CDialogImpl<CDeleteProfileDlg,ATL::CWindow>::DoModal(__int64 a1, HWND a2)
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
      JUMPOUT(0x18000DE3DLL);
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
    return IsolationAwareDialogBoxParamW(hInstance, (LPCWSTR)0x4E5C, a2);
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
0x18000dd64  mov     [rsp+arg_0], rbx
0x18000dd69  mov     [rsp+arg_8], rsi
0x18000dd6e  push    rdi
0x18000dd6f  sub     rsp, 40h
0x18000dd73  mov     rax, [rcx+28h]
0x18000dd77  mov     rsi, rdx
0x18000dd7a  mov     rdi, rcx
0x18000dd7d  test    rax, rax
0x18000dd80  jnz     short loc_18000DDAD
0x18000dd82  call    AtlThunk_AllocateData
0x18000dd87  mov     [rdi+28h], rax
0x18000dd8b  test    rax, rax
0x18000dd8e  jnz     short loc_18000DDAD
0x18000dd90  lea     ecx, [rax+0Eh]; dwErrCode
0x18000dd93  call    cs:__imp_SetLastError
0x18000dd99  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dd9d  mov     rbx, [rsp+48h+arg_0]
0x18000dda2  mov     rsi, [rsp+48h+arg_8]
0x18000dda7  add     rsp, 40h
0x18000ddab  pop     rdi
0x18000ddac  retn
0x18000ddad  xor     r8d, r8d; FirstParameter
0x18000ddb0  xor     edx, edx; Proc
0x18000ddb2  mov     rcx, rax; Thunk
0x18000ddb5  call    AtlThunk_InitData
0x18000ddba  lea     rbx, [rdi+10h]
0x18000ddbe  test    rbx, rbx
0x18000ddc1  jz      short loc_18000DE28
0x18000ddc3  test    rdi, rdi
0x18000ddc6  jz      short loc_18000DE28
0x18000ddc8  mov     [rbx], rdi
0x18000ddcb  call    cs:__imp_GetCurrentThreadId
0x18000ddd1  lea     rcx, [rsp+48h+var_18]
0x18000ddd6  mov     [rsp+48h+var_10], 0
0x18000dddb  mov     [rbx+8], eax
0x18000ddde  lea     rax, qword_18003FA18
0x18000dde5  mov     [rsp+48h+var_18], rax
0x18000ddea  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000ddef  test    eax, eax
0x18000ddf1  js      short loc_18000DE05
0x18000ddf3  mov     rax, cs:qword_18003FA40
0x18000ddfa  mov     [rbx+10h], rax
0x18000ddfe  mov     cs:qword_18003FA40, rbx
0x18000de05  lea     rcx, [rsp+48h+var_18]
0x18000de0a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000de0f  mov     rcx, cs:hInstance; hInstance
0x18000de16  mov     r8, rsi; hWndParent
0x18000de19  mov     edx, 4E5Ch; lpTemplateName
0x18000de1e  call    IsolationAwareDialogBoxParamW
0x18000de23  jmp     loc_18000DD9D
0x18000de28  xor     r9d, r9d; lpArguments
0x18000de2b  xor     r8d, r8d; nNumberOfArguments
0x18000de2e  mov     ecx, 0C0000005h; dwExceptionCode
0x18000de33  lea     edx, [r9+1]; dwExceptionFlags
0x18000de37  call    cs:__imp_RaiseException
```
