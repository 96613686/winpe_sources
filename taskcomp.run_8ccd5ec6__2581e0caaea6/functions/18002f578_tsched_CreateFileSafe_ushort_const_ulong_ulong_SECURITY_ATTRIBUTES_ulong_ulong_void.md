# tsched::CreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18002f578`
- end: `0x18002f606`
- name: `?CreateFileSafe@tsched@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `142`
- prototype: `void *__fastcall(wchar_t *String2, const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006964`

## callees

- `0x18002f578`
- `0x18002f86c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f5d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f5d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f5e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f5a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f5a8`

## pseudocode

```c
void *__fastcall tsched::CreateFileSafe(wchar_t *String2, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  void *v4; // r8
  __int64 v5; // rbx
  void *v6; // rdi

  FileW = CreateFileW(String2, (DWORD)a2, 1u, 0, 3u, 0x2000000u, 0);
  v5 = -1;
  v6 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( (int)tsched::VerifyJobFilePath(String2, FileW, v4) >= 0 )
    {
      return v6;
    }
    else
    {
      SetLastError(5u);
      CloseHandle(v6);
    }
  }
  return (void *)v5;
}

```

## disassembly

```asm
0x18002f578  mov     rax, rsp
0x18002f57b  mov     [rax+8], rbx
0x18002f57f  mov     [rax+10h], rsi
0x18002f583  push    rdi
0x18002f584  sub     rsp, 40h
0x18002f588  mov     qword ptr [rax-18h], 0
0x18002f590  xor     r9d, r9d; lpSecurityAttributes
0x18002f593  mov     dword ptr [rax-20h], 2000000h
0x18002f59a  mov     rsi, rcx
0x18002f59d  mov     dword ptr [rax-28h], 3
0x18002f5a4  lea     r8d, [r9+1]; dwShareMode
0x18002f5a8  call    cs:__imp_CreateFileW
0x18002f5af  nop     dword ptr [rax+rax+00h]
0x18002f5b4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f5b8  mov     rdi, rax
0x18002f5bb  cmp     rax, rbx
0x18002f5be  jz      short loc_18002F5F2
0x18002f5c0  mov     rdx, rax; hFile
0x18002f5c3  mov     rcx, rsi; String2
0x18002f5c6  call    ?VerifyJobFilePath@tsched@@YAJPEBGPEAX@Z; tsched::VerifyJobFilePath(ushort const *,void *)
0x18002f5cb  test    eax, eax
0x18002f5cd  jns     short loc_18002F5EF
0x18002f5cf  lea     ecx, [rbx+6]; dwErrCode
0x18002f5d2  call    cs:__imp_SetLastError
0x18002f5d9  nop     dword ptr [rax+rax+00h]
0x18002f5de  mov     rcx, rdi; hObject
0x18002f5e1  call    cs:__imp_CloseHandle
0x18002f5e8  nop     dword ptr [rax+rax+00h]
0x18002f5ed  jmp     short loc_18002F5F2
0x18002f5ef  mov     rbx, rdi
0x18002f5f2  mov     rsi, [rsp+48h+arg_8]
0x18002f5f7  mov     rax, rbx
0x18002f5fa  mov     rbx, [rsp+48h+arg_0]
0x18002f5ff  add     rsp, 40h
0x18002f603  pop     rdi
0x18002f604  retn
```
