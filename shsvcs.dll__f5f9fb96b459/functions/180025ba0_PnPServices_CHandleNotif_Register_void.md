# PnPServices::CHandleNotif::_Register(void)

- ea: `0x180025ba0`
- end: `0x180025c24`
- name: `?_Register@CHandleNotif@PnPServices@@AEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180024aa0`

## callees

- `0x18002557c`
- `0x180025ba0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c05`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025bd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025bd5`

## pseudocode

```c
__int64 __fastcall PnPServices::CHandleNotif::_Register(LPCWSTR *this)
{
  HANDLE FileW; // rax
  void *v3; // rdi
  int v4; // ebx

  FileW = CreateFileW(this[1], 0, 3u, 0, 3u, 0, 0);
  v3 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    this[17] = (LPCWSTR)FileW;
    v4 = CRegisterNotificationOnHandle::Register((CRegisterNotificationOnHandle *)(this + 13));
    if ( v4 >= 0 )
      this[17] = 0;
    CloseHandle(v3);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025ba0  mov     rax, rsp
0x180025ba3  mov     [rax+8], rbx
0x180025ba7  mov     [rax+10h], rsi
0x180025bab  push    rdi
0x180025bac  sub     rsp, 40h
0x180025bb0  mov     qword ptr [rax-18h], 0
0x180025bb8  mov     rsi, rcx
0x180025bbb  mov     rcx, [rcx+8]; lpFileName
0x180025bbf  mov     r8d, 3; dwShareMode
0x180025bc5  mov     dword ptr [rax-20h], 0
0x180025bcc  xor     r9d, r9d; lpSecurityAttributes
0x180025bcf  xor     edx, edx; dwDesiredAccess
0x180025bd1  mov     [rax-28h], r8d
0x180025bd5  call    cs:__imp_CreateFileW
0x180025bdb  mov     rdi, rax
0x180025bde  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025be2  jz      short loc_180025C0D
0x180025be4  lea     rcx, [rsi+68h]; this
0x180025be8  mov     [rcx+20h], rax
0x180025bec  call    ?Register@CRegisterNotificationOnHandle@@QEAAJXZ; CRegisterNotificationOnHandle::Register(void)
0x180025bf1  mov     ebx, eax
0x180025bf3  test    eax, eax
0x180025bf5  js      short loc_180025C02
0x180025bf7  mov     qword ptr [rsi+88h], 0
0x180025c02  mov     rcx, rdi; hObject
0x180025c05  call    cs:__imp_CloseHandle
0x180025c0b  jmp     short loc_180025C12
0x180025c0d  mov     ebx, 80004005h
0x180025c12  mov     rsi, [rsp+48h+arg_8]
0x180025c17  mov     eax, ebx
0x180025c19  mov     rbx, [rsp+48h+arg_0]
0x180025c1e  add     rsp, 40h
0x180025c22  pop     rdi
0x180025c23  retn
```
