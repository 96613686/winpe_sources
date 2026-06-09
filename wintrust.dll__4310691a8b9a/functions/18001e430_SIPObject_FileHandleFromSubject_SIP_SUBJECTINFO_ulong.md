# SIPObject_::FileHandleFromSubject(SIP_SUBJECTINFO_ *,ulong)

- ea: `0x18001e430`
- end: `0x18001e4d6`
- name: `?FileHandleFromSubject@SIPObject_@@MEAAHPEAUSIP_SUBJECTINFO_@@K@Z`
- size: `166`
- prototype: `int(SIPObject_ *__hidden this, struct SIP_SUBJECTINFO_ *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001e430`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e4bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e4bd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001e45d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001e45d`

## pseudocode

```c
__int64 __fastcall SIPObject_::FileHandleFromSubject(SIPObject_ *this, struct SIP_SUBJECTINFO_ *a2, DWORD a3)
{
  char *hFile; // rcx
  HANDLE FileW; // rax

  *((_DWORD *)this + 12) = a3;
  hFile = (char *)a2->hFile;
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      return (*(__int64 (__fastcall **)(SIPObject_ *))(*(_QWORD *)this + 144LL))(this);
    FileW = CreateFileW(a2->pwsFileName, a3, 5u, 0, 3u, 0x80u, 0);
    *((_QWORD *)this + 1) = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      *((_DWORD *)this + 13) = 1;
      return (*(__int64 (__fastcall **)(SIPObject_ *))(*(_QWORD *)this + 144LL))(this);
    }
  }
  else
  {
    *((_QWORD *)this + 1) = hFile;
    if ( SetFilePointer(hFile, 0, 0, 0) != -1 )
      return (*(__int64 (__fastcall **)(SIPObject_ *))(*(_QWORD *)this + 144LL))(this);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e430  push    rbx
0x18001e432  sub     rsp, 40h
0x18001e436  mov     rbx, rcx
0x18001e439  mov     [rcx+30h], r8d
0x18001e43d  mov     rcx, [rdx+10h]; hFile
0x18001e441  mov     r10d, r8d
0x18001e444  mov     r11, rdx
0x18001e447  lea     rax, [rcx-1]
0x18001e44b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e44f  ja      short loc_18001E487
0x18001e451  xor     r9d, r9d; dwMoveMethod
0x18001e454  mov     [rbx+8], rcx
0x18001e458  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001e45b  xor     edx, edx; lDistanceToMove
0x18001e45d  call    cs:__imp_SetFilePointer
0x18001e463  cmp     eax, 0FFFFFFFFh
0x18001e466  jz      short loc_18001E47F
0x18001e468  mov     rax, [rbx]
0x18001e46b  mov     rcx, rbx
0x18001e46e  mov     rax, [rax+90h]
0x18001e475  add     rsp, 40h
0x18001e479  pop     rbx
0x18001e47a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18001e47f  xor     eax, eax
0x18001e481  add     rsp, 40h
0x18001e485  pop     rbx
0x18001e486  retn
0x18001e487  mov     rax, [rbx+8]
0x18001e48b  inc     rax
0x18001e48e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001e494  jnz     short loc_18001E468
0x18001e496  mov     rcx, [r11+18h]; lpFileName
0x18001e49a  xor     r9d, r9d; lpSecurityAttributes
0x18001e49d  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001e4a6  mov     edx, r10d; dwDesiredAccess
0x18001e4a9  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001e4b1  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18001e4b9  lea     r8d, [r9+5]; dwShareMode
0x18001e4bd  call    cs:__imp_CreateFileW
0x18001e4c3  mov     [rbx+8], rax
0x18001e4c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e4cb  jz      short loc_18001E47F
0x18001e4cd  mov     dword ptr [rbx+34h], 1
0x18001e4d4  jmp     short loc_18001E468
```
