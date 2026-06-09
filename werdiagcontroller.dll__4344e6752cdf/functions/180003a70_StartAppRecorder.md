# StartAppRecorder

- ea: `0x180003a70`
- end: `0x180003b50`
- name: `StartAppRecorder`
- size: `224`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003838`
- `0x180003a70`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180003b25`
- `ntdll!DbgPrintEx` at `0x180003b25`
- `ntdll!RtlCreateUserThread` at `0x180003b08`
- `ntdll!RtlCreateUserThread` at `0x180003b08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b42`

## string_xrefs

- `0x180003b17`: `WERDIAG: AppRecorder: Failed creating AppRecorder thread. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 StartAppRecorder()
{
  int v0; // eax
  HANDLE v1; // rcx
  bool v2; // zf
  char *v3; // rax
  NTSTATUS v5; // eax
  NTSTATUS v6; // ebx
  unsigned int v7; // ebx
  __int128 Reserved8; // [rsp+50h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+8h] BYREF

  hObject = 0;
  Reserved8 = 0;
  v0 = IsAppRecorderEnabled();
  v1 = hObject;
  v2 = v0 == 0;
  v3 = (char *)hObject + 1;
  if ( v2 )
  {
    if ( (unsigned __int64)v3 > 1 )
      CloseHandle(hObject);
    return 0;
  }
  else
  {
    hObject = 0;
    if ( (unsigned __int64)v3 > 1 )
      CloseHandle(v1);
    v5 = RtlCreateUserThread(
           (PVOID)0xFFFFFFFFFFFFFFFFLL,
           0,
           0,
           0,
           0,
           0,
           AppRecorderStartThread,
           0,
           &hObject,
           &Reserved8);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v7 = 0;
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: AppRecorder: Failed creating AppRecorder thread. NTSTATUS: %08X\n", v5);
      v7 = v6 | 0x10000000;
    }
    if ( (unsigned __int64)hObject + 1 > 1 )
      CloseHandle(hObject);
    return v7;
  }
}

```

## disassembly

```asm
0x180003a70  push    rbx
0x180003a72  sub     rsp, 60h
0x180003a76  xorps   xmm0, xmm0
0x180003a79  mov     [rsp+68h+hObject], 0
0x180003a82  movups  [rsp+68h+var_18], xmm0
0x180003a87  call    ?IsAppRecorderEnabled@@YAHXZ; IsAppRecorderEnabled(void)
0x180003a8c  mov     rcx, [rsp+68h+hObject]; hObject
0x180003a91  test    eax, eax
0x180003a93  lea     rax, [rcx+1]
0x180003a97  jnz     short loc_180003AAC
0x180003a99  cmp     rax, 1
0x180003a9d  jbe     short loc_180003AA5
0x180003a9f  call    cs:__imp_CloseHandle
0x180003aa5  xor     eax, eax
0x180003aa7  jmp     loc_180003B4A
0x180003aac  mov     [rsp+68h+hObject], 0
0x180003ab5  cmp     rax, 1
0x180003ab9  jbe     short loc_180003AC1
0x180003abb  call    cs:__imp_CloseHandle
0x180003ac1  lea     rax, [rsp+68h+var_18]
0x180003ac6  xor     r9d, r9d; Reserved2
0x180003ac9  mov     [rsp+68h+Reserved8], rax; Reserved8
0x180003ace  xor     r8d, r8d; Reserved1
0x180003ad1  lea     rax, [rsp+68h+hObject]
0x180003ad6  xor     edx, edx; OutThreadHandle
0x180003ad8  mov     [rsp+68h+Reserved7], rax; Reserved7
0x180003add  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180003ae1  mov     [rsp+68h+Reserved6], 0; Reserved6
0x180003aea  lea     rax, AppRecorderStartThread
0x180003af1  mov     [rsp+68h+Reserved5], rax; Reserved5
0x180003af6  mov     [rsp+68h+Reserved4], 0; Reserved4
0x180003aff  mov     [rsp+68h+Reserved3], 0; Reserved3
0x180003b08  call    cs:__imp_RtlCreateUserThread
0x180003b0e  mov     ebx, eax
0x180003b10  test    eax, eax
0x180003b12  jns     short loc_180003B31
0x180003b14  mov     r9d, eax
0x180003b17  lea     r8, aWerdiagAppreco_16; "WERDIAG: AppRecorder: Failed creating A"...
0x180003b1e  xor     edx, edx; Level
0x180003b20  mov     ecx, 96h; ComponentId
0x180003b25  call    cs:__imp_DbgPrintEx
0x180003b2b  bts     ebx, 1Ch
0x180003b2f  jmp     short loc_180003B33
0x180003b31  xor     ebx, ebx
0x180003b33  mov     rcx, [rsp+68h+hObject]; hObject
0x180003b38  lea     rdx, [rcx+1]
0x180003b3c  cmp     rdx, 1
0x180003b40  jbe     short loc_180003B48
0x180003b42  call    cs:__imp_CloseHandle
0x180003b48  mov     eax, ebx
0x180003b4a  add     rsp, 60h
0x180003b4e  pop     rbx
0x180003b4f  retn
```
