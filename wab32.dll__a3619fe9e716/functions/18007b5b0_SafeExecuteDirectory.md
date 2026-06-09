# _SafeExecuteDirectory

- ea: `0x18007b5b0`
- end: `0x18007b69b`
- name: `_SafeExecuteDirectory`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18007b378`

## callees

- `0x180005d08`
- `0x18007b5b0`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18007b661`
- `SHELL32!ShellExecuteExW` at `0x18007b661`
- `SHELL32!SHParseDisplayName` at `0x18007b5e6`
- `SHELL32!SHParseDisplayName` at `0x18007b5e6`
- `ole32!CoTaskMemFree` at `0x18007b682`
- `ole32!CoTaskMemFree` at `0x18007b682`

## pseudocode

```c
__int64 __fastcall SafeExecuteDirectory(const WCHAR *a1)
{
  HRESULT LastError; // ebx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-19h] BYREF
  SFGAOF psfgaoOut; // [rsp+B8h] [rbp+6Fh] BYREF
  LPITEMIDLIST ppidl; // [rsp+C0h] [rbp+77h] BYREF

  psfgaoOut = 0;
  ppidl = 0;
  LastError = SHParseDisplayName(a1, 0, &ppidl, 0x60000000u, &psfgaoOut);
  if ( LastError >= 0 )
  {
    if ( (psfgaoOut & 0x20000000) != 0 && (psfgaoOut & 0x40000000) != 0 )
    {
      pExecInfo.cbSize = 112;
      pExecInfo.hwnd = 0;
      pExecInfo.lpVerb = L"explore";
      memset(&pExecInfo.lpClass, 0, 40);
      pExecInfo.lpIDList = ppidl;
      memset(&pExecInfo.lpFile, 0, 24);
      *(_QWORD *)&pExecInfo.nShow = 1;
      pExecInfo.hInstApp = 0;
      pExecInfo.fMask = 1048580;
      if ( !ShellExecuteExW(&pExecInfo) )
        LastError = HrGetLastError();
    }
    else
    {
      LastError = -2147418113;
    }
  }
  if ( ppidl )
    CoTaskMemFree(ppidl);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18007b5b0  mov     [rsp-8+arg_0], rbx
0x18007b5b5  push    rbp
0x18007b5b6  lea     rbp, [rsp-57h]
0x18007b5bb  sub     rsp, 0A0h
0x18007b5c2  lea     rax, [rbp+57h+arg_8]
0x18007b5c6  mov     [rbp+57h+arg_8], 0
0x18007b5cd  mov     r9d, 60000000h; sfgaoIn
0x18007b5d3  mov     [rsp+0A0h+psfgaoOut], rax; psfgaoOut
0x18007b5d8  lea     r8, [rbp+57h+ppidl]; ppidl
0x18007b5dc  mov     [rbp+57h+ppidl], 0
0x18007b5e4  xor     edx, edx; pbc
0x18007b5e6  call    cs:__imp_SHParseDisplayName
0x18007b5ec  mov     ebx, eax
0x18007b5ee  test    eax, eax
0x18007b5f0  js      loc_18007B679
0x18007b5f6  test    [rbp+57h+arg_8], 20000000h
0x18007b5fd  jz      short loc_18007B674
0x18007b5ff  test    [rbp+57h+arg_8], 40000000h
0x18007b606  jz      short loc_18007B674
0x18007b608  xorps   xmm0, xmm0
0x18007b60b  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x18007b612  lea     rax, aExplore; "explore"
0x18007b619  mov     [rbp+57h+pExecInfo.hwnd], 0
0x18007b621  mov     [rbp+57h+pExecInfo.lpVerb], rax
0x18007b625  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x18007b629  mov     rax, [rbp+57h+ppidl]
0x18007b62d  movups  xmmword ptr [rbp+57h+pExecInfo.lpIDList], xmm0
0x18007b631  mov     [rbp+57h+pExecInfo.lpIDList], rax
0x18007b635  mov     [rbp+57h+pExecInfo.lpFile], 0
0x18007b63d  movdqa  xmmword ptr [rbp+57h+pExecInfo.lpParameters], xmm0
0x18007b642  mov     qword ptr [rbp+57h+pExecInfo.nShow], 1
0x18007b64a  mov     [rbp+57h+pExecInfo.hInstApp], 0
0x18007b652  movups  xmmword ptr [rbp+57h+pExecInfo.hkeyClass], xmm0
0x18007b656  mov     [rbp+57h+pExecInfo.fMask], 100004h
0x18007b65d  movups  xmmword ptr [rbp+57h+pExecInfo.60h], xmm0
0x18007b661  call    cs:__imp_ShellExecuteExW
0x18007b667  test    eax, eax
0x18007b669  jnz     short loc_18007B679
0x18007b66b  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18007b670  mov     ebx, eax
0x18007b672  jmp     short loc_18007B679
0x18007b674  mov     ebx, 8000FFFFh
0x18007b679  mov     rcx, [rbp+57h+ppidl]; pv
0x18007b67d  test    rcx, rcx
0x18007b680  jz      short loc_18007B688
0x18007b682  call    cs:__imp_CoTaskMemFree
0x18007b688  mov     eax, ebx
0x18007b68a  mov     rbx, [rsp+0A0h+arg_0]
0x18007b692  add     rsp, 0A0h
0x18007b699  pop     rbp
0x18007b69a  retn
```
