# WriteMetaDataFile

- ea: `0x180019454`
- end: `0x180019598`
- name: `WriteMetaDataFile`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f124`

## callees

- `0x180019454`
- `0x1800195a0`
- `0x1800199c0`
- `0x180023940`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001955f`
- `KERNEL32!HeapFree` at `0x18001955f`
- `KERNEL32!HeapAlloc` at `0x1800194c9`
- `KERNEL32!HeapAlloc` at `0x1800194c9`
- `KERNEL32!GetLastError` at `0x180019523`
- `KERNEL32!GetLastError` at `0x180019523`
- `KERNEL32!CloseHandle` at `0x18001953a`
- `KERNEL32!CloseHandle` at `0x18001953a`
- `KERNEL32!CreateFileW` at `0x18001949d`
- `KERNEL32!CreateFileW` at `0x18001949d`
- `KERNEL32!SetLastError` at `0x180019571`
- `KERNEL32!SetLastError` at `0x180019571`
- `KERNEL32!GetProcessHeap` at `0x1800194b2`
- `KERNEL32!GetProcessHeap` at `0x18001954b`
- `KERNEL32!GetProcessHeap` at `0x1800194b2`
- `KERNEL32!GetProcessHeap` at `0x18001954b`

## pseudocode

```c
__int64 __fastcall WriteMetaDataFile(__int64 a1, __int64 a2, const WCHAR *a3)
{
  void *v5; // rbx
  unsigned int v6; // edi
  DWORD LastError; // esi
  HANDLE FileW; // rbp
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rax
  HANDLE v11; // rax

  v5 = 0;
  v6 = 0;
  LastError = 0;
  FileW = CreateFileW(a3, 0x40000000u, 0, 0, 4u, 0x8000100u, 0);
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_6;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, 0x100018u);
  v5 = v10;
  if ( !v10
    || (v10[1] = 0, v10[2] = 0, *v10 = FileW, (v6 = WriteBinarySecurityData(a1, v10)) == 0)
    || (v6 = 0, !(unsigned int)WriteBinaryDirData(v5, a2, a2, 0))
    || (v6 = FlushWriteBuffer(v5)) == 0 )
  {
LABEL_6:
    LastError = GetLastError();
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v5 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v5);
  }
  if ( LastError )
    SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x180019454  mov     r11, rsp
0x180019457  mov     [r11+8], rbx
0x18001945b  mov     [r11+10h], rbp
0x18001945f  mov     [r11+18h], rsi
0x180019463  push    rdi
0x180019464  push    r14
0x180019466  push    r15
0x180019468  sub     rsp, 40h
0x18001946c  mov     rax, r8
0x18001946f  mov     r14, rdx
0x180019472  mov     r15, rcx
0x180019475  xor     ebx, ebx
0x180019477  and     [r11-28h], rbx
0x18001947b  xor     r9d, r9d; lpSecurityAttributes
0x18001947e  mov     [rsp+58h+dwFlagsAndAttributes], 8000100h; dwFlagsAndAttributes
0x180019486  xor     r8d, r8d; dwShareMode
0x180019489  mov     edx, 40000000h; dwDesiredAccess
0x18001948e  mov     [rsp+58h+dwCreationDisposition], 4; dwCreationDisposition
0x180019496  mov     rcx, rax; lpFileName
0x180019499  xor     edi, edi
0x18001949b  xor     esi, esi
0x18001949d  call    cs:__imp_CreateFileW
0x1800194a4  nop     dword ptr [rax+rax+00h]
0x1800194a9  mov     rbp, rax
0x1800194ac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800194b0  jz      short loc_180019523
0x1800194b2  call    cs:__imp_GetProcessHeap
0x1800194b9  nop     dword ptr [rax+rax+00h]
0x1800194be  xor     edx, edx; dwFlags
0x1800194c0  mov     r8d, 100018h; dwBytes
0x1800194c6  mov     rcx, rax; hHeap
0x1800194c9  call    cs:__imp_HeapAlloc
0x1800194d0  nop     dword ptr [rax+rax+00h]
0x1800194d5  mov     rbx, rax
0x1800194d8  test    rax, rax
0x1800194db  jz      short loc_1800194E8
0x1800194dd  and     [rax+8], rsi
0x1800194e1  and     [rax+10h], rsi
0x1800194e5  mov     [rax], rbp
0x1800194e8  test    rbx, rbx
0x1800194eb  jz      short loc_180019523
0x1800194ed  mov     rdx, rbx
0x1800194f0  mov     rcx, r15
0x1800194f3  call    WriteBinarySecurityData
0x1800194f8  mov     edi, eax
0x1800194fa  test    eax, eax
0x1800194fc  jz      short loc_180019523
0x1800194fe  xor     r9d, r9d
0x180019501  mov     r8, r14
0x180019504  mov     rdx, r14
0x180019507  mov     rcx, rbx
0x18001950a  xor     edi, edi
0x18001950c  call    WriteBinaryDirData
0x180019511  test    eax, eax
0x180019513  jz      short loc_180019523
0x180019515  mov     rcx, rbx
0x180019518  call    FlushWriteBuffer
0x18001951d  mov     edi, eax
0x18001951f  test    eax, eax
0x180019521  jnz     short loc_180019531
0x180019523  call    cs:__imp_GetLastError
0x18001952a  nop     dword ptr [rax+rax+00h]
0x18001952f  mov     esi, eax
0x180019531  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180019535  jz      short loc_180019546
0x180019537  mov     rcx, rbp; hObject
0x18001953a  call    cs:__imp_CloseHandle
0x180019541  nop     dword ptr [rax+rax+00h]
0x180019546  test    rbx, rbx
0x180019549  jz      short loc_18001956B
0x18001954b  call    cs:__imp_GetProcessHeap
0x180019552  nop     dword ptr [rax+rax+00h]
0x180019557  mov     r8, rbx; lpMem
0x18001955a  xor     edx, edx; dwFlags
0x18001955c  mov     rcx, rax; hHeap
0x18001955f  call    cs:__imp_HeapFree
0x180019566  nop     dword ptr [rax+rax+00h]
0x18001956b  test    esi, esi
0x18001956d  jz      short loc_18001957D
0x18001956f  mov     ecx, esi; dwErrCode
0x180019571  call    cs:__imp_SetLastError
0x180019578  nop     dword ptr [rax+rax+00h]
0x18001957d  mov     rbx, [rsp+58h+arg_0]
0x180019582  mov     eax, edi
0x180019584  mov     rbp, [rsp+58h+arg_8]
0x180019589  mov     rsi, [rsp+58h+arg_10]
0x18001958e  add     rsp, 40h
0x180019592  pop     r15
0x180019594  pop     r14
0x180019596  pop     rdi
0x180019597  retn
```
