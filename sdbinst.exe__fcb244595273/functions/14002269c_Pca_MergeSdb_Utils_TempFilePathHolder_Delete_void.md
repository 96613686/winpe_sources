# Pca::MergeSdb::Utils::TempFilePathHolder::Delete(void)

- ea: `0x14002269c`
- end: `0x14002273d`
- name: `?Delete@TempFilePathHolder@Utils@MergeSdb@Pca@@QEAAXXZ`
- size: `161`
- prototype: `void __fastcall(LPCWSTR *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1400222f4`
- `0x140024958`
- `0x14002be40`

## callees

- `0x14001008c`
- `0x14002269c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400226cd`
- `KERNEL32!GetLastError` at `0x140022702`
- `KERNEL32!GetLastError` at `0x1400226cd`
- `KERNEL32!GetLastError` at `0x140022702`
- `KERNEL32!DeleteFileW` at `0x1400226c3`
- `KERNEL32!DeleteFileW` at `0x1400226c3`
- `KERNEL32!GetProcessHeap` at `0x14002270a`
- `KERNEL32!GetProcessHeap` at `0x14002270a`
- `KERNEL32!SetLastError` at `0x140022720`
- `KERNEL32!SetLastError` at `0x140022720`
- `KERNEL32!HeapFree` at `0x140022718`
- `KERNEL32!HeapFree` at `0x140022718`
- `ntdll!RtlDoesFileExists_U` at `0x1400226b6`
- `ntdll!RtlDoesFileExists_U` at `0x1400226b6`

## string_xrefs

- `0x1400226e1`: `Pca::MergeSdb::Utils::TempFilePathHolder::Delete`
- `0x1400226d8`: `DeleteFileW failed to remove temp sdb (%d)`

## pseudocode

```c
void __fastcall Pca::MergeSdb::Utils::TempFilePathHolder::Delete(LPCWSTR *this)
{
  const WCHAR *v2; // rcx
  DWORD LastError; // eax
  WCHAR *v4; // rsi
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v7; // [rsp+20h] [rbp-18h]

  v2 = *this;
  if ( v2 && RtlDoesFileExists_U(v2) )
  {
    if ( !DeleteFileW(*this) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1;
      v7 = LastError;
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::TempFilePathHolder::Delete",
        154,
        "DeleteFileW failed to remove temp sdb (%d)",
        v7);
    }
    v4 = (WCHAR *)*this;
    if ( *this )
    {
      v5 = GetLastError();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
      SetLastError(v5);
    }
    *this = 0;
  }
}

```

## disassembly

```asm
0x14002269c  mov     [rsp+arg_0], rbx
0x1400226a1  mov     [rsp+arg_8], rsi
0x1400226a6  push    rdi
0x1400226a7  sub     rsp, 30h
0x1400226ab  mov     rdi, rcx
0x1400226ae  mov     rcx, [rcx]; FileName
0x1400226b1  test    rcx, rcx
0x1400226b4  jz      short loc_14002272D
0x1400226b6  call    cs:__imp_RtlDoesFileExists_U
0x1400226bc  test    al, al
0x1400226be  jz      short loc_14002272D
0x1400226c0  mov     rcx, [rdi]; lpFileName
0x1400226c3  call    cs:__imp_DeleteFileW
0x1400226c9  test    eax, eax
0x1400226cb  jnz     short loc_1400226FA
0x1400226cd  call    cs:__imp_GetLastError
0x1400226d3  mov     ecx, 1
0x1400226d8  lea     r9, aDeletefilewFai_0; "DeleteFileW failed to remove temp sdb ("...
0x1400226df  test    eax, eax
0x1400226e1  lea     rdx, aPcaMergesdbUti_1; "Pca::MergeSdb::Utils::TempFilePathHolde"...
0x1400226e8  mov     r8d, 9Ah
0x1400226ee  cmovz   eax, ecx
0x1400226f1  mov     [rsp+38h+var_18], eax
0x1400226f5  call    AslLogCallPrintf
0x1400226fa  mov     rsi, [rdi]
0x1400226fd  test    rsi, rsi
0x140022700  jz      short loc_140022726
0x140022702  call    cs:__imp_GetLastError
0x140022708  mov     ebx, eax
0x14002270a  call    cs:__imp_GetProcessHeap
0x140022710  mov     r8, rsi; lpMem
0x140022713  xor     edx, edx; dwFlags
0x140022715  mov     rcx, rax; hHeap
0x140022718  call    cs:__imp_HeapFree
0x14002271e  mov     ecx, ebx; dwErrCode
0x140022720  call    cs:__imp_SetLastError
0x140022726  mov     qword ptr [rdi], 0
0x14002272d  mov     rbx, [rsp+38h+arg_0]
0x140022732  mov     rsi, [rsp+38h+arg_8]
0x140022737  add     rsp, 30h
0x14002273b  pop     rdi
0x14002273c  retn
```
