# CLogFile::SetSize(ulong)

- ea: `0x18000ecb4`
- end: `0x18000ed15`
- name: `?SetSize@CLogFile@@AEAAHK@Z`
- size: `97`
- prototype: `__int64 __fastcall(CLogFile *this, LONG)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009ce8`
- `0x18000e7c0`
- `0x18000eac0`

## callees

- `0x18000d558`
- `0x18000ecb4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000ecd1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000ecd1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000ece8`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000ece8`

## pseudocode

```c
__int64 __fastcall CLogFile::SetSize(CLogFile *this, LONG a2)
{
  DWORD v4; // eax
  BOOL v5; // eax

  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  v4 = SetFilePointer(*((HANDLE *)this + 2), a2, 0, 0);
  _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( v4 == -1 )
    return 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  v5 = SetEndOfFile(*((HANDLE *)this + 2));
  _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !v5 )
    return 0;
  *((_DWORD *)this + 17) = a2;
  CLogFile::CalcNumEntriesInFile(this);
  return 1;
}

```

## disassembly

```asm
0x18000ecb4  mov     [rsp+arg_0], rbx
0x18000ecb9  push    rdi
0x18000ecba  sub     rsp, 20h
0x18000ecbe  mov     edi, edx
0x18000ecc0  mov     rbx, rcx
0x18000ecc3  lock inc dword ptr [rcx+18h]
0x18000ecc7  mov     rcx, [rcx+10h]; hFile
0x18000eccb  xor     r9d, r9d; dwMoveMethod
0x18000ecce  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000ecd1  call    cs:__imp_SetFilePointer
0x18000ecd7  lock dec dword ptr [rbx+18h]
0x18000ecdb  cmp     eax, 0FFFFFFFFh
0x18000ecde  jz      short loc_18000ED08
0x18000ece0  lock inc dword ptr [rbx+18h]
0x18000ece4  mov     rcx, [rbx+10h]; hFile
0x18000ece8  call    cs:__imp_SetEndOfFile
0x18000ecee  lock dec dword ptr [rbx+18h]
0x18000ecf2  test    eax, eax
0x18000ecf4  jz      short loc_18000ED08
0x18000ecf6  mov     rcx, rbx; this
0x18000ecf9  mov     [rbx+44h], edi
0x18000ecfc  call    ?CalcNumEntriesInFile@CLogFile@@AEAAKXZ; CLogFile::CalcNumEntriesInFile(void)
0x18000ed01  mov     eax, 1
0x18000ed06  jmp     short loc_18000ED0A
0x18000ed08  xor     eax, eax
0x18000ed0a  mov     rbx, [rsp+28h+arg_0]
0x18000ed0f  add     rsp, 20h
0x18000ed13  pop     rdi
0x18000ed14  retn
```
