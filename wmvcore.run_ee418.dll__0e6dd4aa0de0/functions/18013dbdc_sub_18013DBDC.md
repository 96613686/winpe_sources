# sub_18013DBDC

- ea: `0x18013dbdc`
- end: `0x18013dcf9`
- name: `sub_18013DBDC`
- size: `285`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, HMODULE phModule, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800796e0`

## callees

- `0x18003f3b4`
- `0x18013da48`
- `0x18013dbdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18013dc92`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18013dc92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18013dcb9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18013dcb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18013dc41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18013dc41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013dc51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013dc51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013dcda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013dcda`

## pseudocode

```c
__int64 __fastcall sub_18013DBDC(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        HMODULE phModule,
        __int64 a8)
{
  void *v9; // rsi
  __int64 v10; // rdx
  _QWORD *v11; // rdi
  unsigned int v12; // ebx
  signed int LastError; // eax

  HIDWORD(a8) = HIDWORD(a3);
  phModule = 0;
  LODWORD(a8) = 0;
  if ( !a4 )
    return 2147942487LL;
  if ( !a6 )
    return 0;
  v9 = 0;
  v11 = (_QWORD *)sub_18013DA48(a1, 0);
  if ( v11 )
  {
    if ( GetModuleHandleExA(4u, (LPCSTR)sub_18013DD00, &phModule)
      && (*v11 = phModule, (v9 = (void *)o__beginthreadex(v11, 0, 0, 0, sub_18013DD00, v11)) != 0) )
    {
      v12 = 0;
      phModule = 0;
      v11 = 0;
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v12 = -2147024882;
  }
  if ( phModule )
    FreeLibrary(phModule);
  if ( v11 )
    j_j__o_free(v11, v9, v10, v11);
  if ( v9 )
    CloseHandle(v9);
  return v12;
}

```

## disassembly

```asm
0x18013dbdc  mov     rax, rsp
0x18013dbdf  mov     [rax+18h], rbx
0x18013dbe3  mov     [rax+20h], rsi
0x18013dbe7  mov     [rax+10h], rdx
0x18013dbeb  push    rdi
0x18013dbec  sub     rsp, 30h
0x18013dbf0  mov     qword ptr [rax+8], 0
0x18013dbf8  mov     dword ptr [rax+10h], 0
0x18013dbff  test    rcx, rcx
0x18013dc02  jnz     short loc_18013DC0E
0x18013dc04  mov     eax, 80070057h
0x18013dc09  jmp     loc_18013DCE8
0x18013dc0e  test    r9d, r9d
0x18013dc11  jnz     short loc_18013DC1A
0x18013dc13  xor     eax, eax
0x18013dc15  jmp     loc_18013DCE8
0x18013dc1a  xor     esi, esi
0x18013dc1c  call    sub_18013DA48
0x18013dc21  mov     rdi, rax
0x18013dc24  test    rax, rax
0x18013dc27  jnz     short loc_18013DC30
0x18013dc29  mov     ebx, 8007000Eh
0x18013dc2e  jmp     short loc_18013DCAF
0x18013dc30  lea     r8, [rsp+38h+phModule]; phModule
0x18013dc35  mov     ecx, 4; dwFlags
0x18013dc3a  lea     rdx, sub_18013DD00; lpModuleName
0x18013dc41  call    cs:GetModuleHandleExA
0x18013dc48  nop     dword ptr [rax+rax+00h]
0x18013dc4d  test    eax, eax
0x18013dc4f  jnz     short loc_18013DC6E
0x18013dc51  call    cs:GetLastError
0x18013dc58  nop     dword ptr [rax+rax+00h]
0x18013dc5d  mov     ebx, eax
0x18013dc5f  test    eax, eax
0x18013dc61  jle     short loc_18013DCAF
0x18013dc63  movzx   ebx, ax
0x18013dc66  or      ebx, 80070000h
0x18013dc6c  jmp     short loc_18013DCAF
0x18013dc6e  mov     rax, [rsp+38h+phModule]
0x18013dc73  lea     r8, sub_18013DD00
0x18013dc7a  mov     [rdi], rax
0x18013dc7d  mov     r9, rdi
0x18013dc80  lea     rax, [rsp+38h+arg_8]
0x18013dc85  xor     edx, edx
0x18013dc87  mov     [rsp+38h+var_10], rax
0x18013dc8c  xor     ecx, ecx
0x18013dc8e  mov     [rsp+38h+var_18], esi
0x18013dc92  call    cs:_o__beginthreadex
0x18013dc99  nop     dword ptr [rax+rax+00h]
0x18013dc9e  mov     rsi, rax
0x18013dca1  test    rax, rax
0x18013dca4  jz      short loc_18013DC51
0x18013dca6  xor     ebx, ebx
0x18013dca8  mov     [rsp+38h+phModule], rbx
0x18013dcad  xor     edi, edi
0x18013dcaf  mov     rcx, [rsp+38h+phModule]; hLibModule
0x18013dcb4  test    rcx, rcx
0x18013dcb7  jz      short loc_18013DCC5
0x18013dcb9  call    cs:FreeLibrary
0x18013dcc0  nop     dword ptr [rax+rax+00h]
0x18013dcc5  test    rdi, rdi
0x18013dcc8  jz      short loc_18013DCD2
0x18013dcca  mov     rcx, rdi
0x18013dccd  call    j_j__o_free
0x18013dcd2  test    rsi, rsi
0x18013dcd5  jz      short loc_18013DCE6
0x18013dcd7  mov     rcx, rsi; hObject
0x18013dcda  call    cs:CloseHandle
0x18013dce1  nop     dword ptr [rax+rax+00h]
0x18013dce6  mov     eax, ebx
0x18013dce8  mov     rbx, [rsp+38h+arg_10]
0x18013dced  mov     rsi, [rsp+38h+arg_18]
0x18013dcf2  add     rsp, 30h
0x18013dcf6  pop     rdi
0x18013dcf7  retn
```
